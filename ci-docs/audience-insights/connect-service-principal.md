---
title: Kết nối với một tài khoản Azure Data Lake Storage bằng cách sử dụng tên dịch vụ chính
description: Sử dụng tên dịch vụ chính Azure để kết nối với kho dữ liệu của riêng bạn.
ms.date: 09/08/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: b96c7f580b4067e059e00a9cdb4e872e9acd4a5c
ms.sourcegitcommit: 5704002484cdf85ebbcf4e7e4fd12470fd8e259f
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 09/08/2021
ms.locfileid: "7483551"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Kết nối với một tài khoản Azure Data Lake Storage bằng cách sử dụng tên dịch vụ chính Azure

Các công cụ tự động sử dụng dịch vụ Azure luôn phải có các quyền hạn chế. Thay vì để các ứng dụng đăng nhập với tư cách là người dùng có đầy đủ đặc quyền, Azure cung cấp các dịch vụ chính. Đọc tiếp để tìm hiểu cách kết nối Dynamics 365 Customer Insights với một tài khoản Azure Data Lake Storage bằng cách sử dụng tên dịch vụ chính Azure thay vì khóa tài khoản lưu trữ. 

Bạn có thể sử dụng tên dịch vụ chính để [thêm hoặc chỉnh sửa thư mục Common Data Model một cách an toàn dưới dạng nguồn dữ liệu](connect-common-data-model.md) hoặc [tạo hoặc cập nhật môi trường](get-started-paid.md).

> [!IMPORTANT]
> - Tài khoản Data Lake Storage sẽ sử dụng dịch vụ chính phải đã bật tính năng [không gian tên theo cấp bậc](/azure/storage/blobs/data-lake-storage-namespace).
> - Bạn cần quyền quản trị cho đăng ký Azure của mình để tạo dịch vụ chính.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Tạo một tên dịch vụ chính Azure cho Customer Insights

Trước khi tạo một tên dịch vụ chính mới để có thông tin chi tiết về đối tượng hoặc thông tin chi tiết về mức độ tương tác, hãy kiểm tra xem nó đã tồn tại trong tổ chức của bạn chưa.

### <a name="look-for-an-existing-service-principal"></a>Tìm một dịch vụ chính hiện có

1. Đi tới [Cổng quản trị Azure](https://portal.azure.com) và đăng nhập vào tổ chức của bạn.

2. Từ **Dịch vụ Azure**, hãy chọn **Azure Active Directory**.

3. Trong **Quản lý**, chọn **Ứng dụng doanh nghiệp**.

4. Tìm kiếm ID ứng dụng Microsoft:
   - Thông tin chi tiết về đối tượng: `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` có tên `Dynamics 365 AI for Customer Insights`
   - Thông tin chi tiết về tương tác: `ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd` có tên `Dynamics 365 AI for Customer Insights engagement insights`

5. Nếu bạn tìm thấy một bản ghi phù hợp, điều đó có nghĩa là tên dịch vụ chính đã tồn tại. 
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Ảnh chụp màn hình hiển thị một tên dịch vụ chính hiện có.":::
   
6. Nếu không có kết quả nào được trả lại, hãy tạo một dịch vụ chính mới.

>[!NOTE]
>Để tận dụng toàn bộ sức mạnh của Dynamics 365 Customer Insights, chúng tôi khuyên bạn nên thêm cả hai ứng dụng vào tên dịch vụ chính.

### <a name="create-a-new-service-principal"></a>Tạo dịch vụ chính mới

1. Cài đặt phiên bản mới nhất của Azure Active Directory PowerShell for Graph. Để biết thêm thông tin, hãy truy cập [Cài đặt Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).

   1. Trên PC, chọn phím Windows trên bàn phím và tìm kiếm **Windows PowerShell** và chọn **Chạy với tư cách quản trị viên**.
   
   1. Trong cửa sổ PowerShell mở ra, hãy nhập `Install-Module AzureAD`.

2. Tạo tên dịch vụ chính cho Customer Insights với mô-đun Azure AD PowerShell.

   1. Trong cửa sổ PowerShell, hãy nhập `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`. Thay thế *[ID đối tượng thuê của bạn]* bằng ID thực tế của đối tượng thuê mà bạn muốn tạo dịch vụ chính. Tham số tên môi trường `AzureEnvironmentName` là không bắt buộc.
  
   1. Nhập `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Lệnh này tạo dịch vụ chính cho thông tin chi tiết về đối tượng trên đối tượng thuê đã chọn. 

   1. Nhập `New-AzureADServicePrincipal -AppId "ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd" -DisplayName "Dynamics 365 AI for Customer Insights engagement insights"`. Lệnh này tạo tên dịch vụ chính cho thông tin chi tiết về mức độ tương tác đối với người thuê đã chọn.

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Cấp quyền cho dịch vụ chính để truy cập vào tài khoản lưu trữ

Truy cập cổng Azure để cấp quyền cho dịch vụ chính đối với tài khoản lưu trữ mà bạn muốn sử dụng trong thông tin chi tiết về đối tượng.

1. Đi tới [Cổng quản trị Azure](https://portal.azure.com) và đăng nhập vào tổ chức của bạn.

1. Mở tài khoản lưu trữ mà bạn muốn dịch vụ chính cho thông tin chi tiết về đối tượng có quyền truy cập.

1. Trên ngăn bên trái, hãy chọn **Kiểm soát truy cập (IAM)**, sau đó chọn **Thêm vào** > **Thêm gán vai trò**.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Ảnh chụp màn hình hiển thị cổng thông tin Azure trong khi thêm gán vai trò.":::

1. Trên ngăn **Thêm gán vai trò**, đặt các thuộc tính sau:
   - Vai trò: **Người đóng góp dữ liệu Storage Blob**
   - Gán quyền truy cập cho: **Người dùng, nhóm hoặc dịch vụ chính**
   - Chọn: **Dynamics 365 AI cho Customer Insights** và **Dynamics 365 AI cho thông tin chi tiết về mức độ tương tác Customer Insights** (2 [tên dịch vụ chính](#create-a-new-service-principal) mà bạn đã tạo trong quy trình này)

1.  Chọn **Lưu**.

Có thể mất đến 15 phút để các thay đổi được thực hiện.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a>Nhập ID tài nguyên Azure hoặc chi tiết đăng ký Azure trong tệp đính kèm tài khoản lưu trữ cho thông tin chi tiết về đối tượng

Bạn có thể đính kèm tài khoản Data Lake Storage trong thông tin chi tiết về đối tượng [lưu trữ dữ liệu đầu ra](manage-environments.md) hoặc [sử dụng làm nguồn dữ liệu](connect-common-data-service-lake.md). Tùy chọn này cho phép bạn chọn giữa cách tiếp cận dựa trên tài nguyên hoặc dựa trên đăng ký. Tùy thuộc vào cách tiếp cận bạn chọn, hãy làm theo quy trình ở một trong các phần sau.

### <a name="resource-based-storage-account-connection"></a>Kết nối tài khoản lưu trữ dựa trên tài nguyên

1. Đi tới [Cổng thông tin quản trị Azure](https://portal.azure.com), đăng nhập vào gói đăng ký của bạn và mở tài khoản lưu trữ.

1. Trên ngăn bên trái, đi tới **Cài đặt** > **Thuộc tính**.

1. Sao chép giá trị ID tài nguyên tài khoản lưu trữ.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Sao chép ID tài nguyên tài khoản lưu trữ.":::

1. Trong thông tin chi tiết về đối tượng, hãy chèn ID tài nguyên vào trường tài nguyên được hiển thị trên màn hình kết nối tài khoản lưu trữ.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Nhập thông tin ID tài nguyên tài khoản lưu trữ.":::   

1. Tiếp tục với các bước còn lại trong thông tin chi tiết về đối tượng để đính kèm tài khoản lưu trữ.

### <a name="subscription-based-storage-account-connection"></a>Kết nối tài khoản lưu trữ dựa trên đăng ký

1. Đi tới [Cổng thông tin quản trị Azure](https://portal.azure.com), đăng nhập vào gói đăng ký của bạn và mở tài khoản lưu trữ.

1. Trên ngăn bên trái, đi tới **Cài đặt** > **Thuộc tính**.

1. Xem lại **Đăng ký**, **Nhóm tài nguyên** và **Tên** của tài khoản lưu trữ để đảm bảo bạn chọn đúng giá trị trong thông tin chi tiết về đối tượng.

1. Trong thông tin chi tiết về đối tượng, hãy chọn giá trị cho các trường tương ứng khi đính kèm tài khoản lưu trữ.

1. Tiếp tục với các bước còn lại trong thông tin chi tiết về đối tượng để đính kèm tài khoản lưu trữ.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
