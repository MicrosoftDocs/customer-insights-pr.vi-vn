---
title: Kết nối với tài khoản Azure Data Lake Storage Gen2 có dịch vụ chính
description: Dùng dịch vụ chính Azure cho thông tin chi tiết về đối tượng để kết nối với kho dữ liệu của riêng bạn khi đính kèm với thông tin chi tiết về đối tượng.
ms.date: 02/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: eebbac1370a847869d98beaf70db49b809d762e7
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267748"
---
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a>Kết nối với tài khoản Azure Data Lake Storage Gen2 có dịch vụ chính Azure để biết thông tin chi tiết về đối tượng

Các công cụ tự động sử dụng dịch vụ Azure luôn phải có các quyền hạn chế. Thay vì để các ứng dụng đăng nhập với tư cách là người dùng có đầy đủ đặc quyền, Azure cung cấp các dịch vụ chính. Đọc tiếp để tìm hiểu cách kết nối thông tin chi tiết về đối tượng với tài khoản Azure Data Lake Storage Gen2 sử dụng dịch vụ chính Azure thay vì khóa tài khoản lưu trữ. 

Bạn có thể sử dụng dịch vụ chính để [thêm hoặc chỉnh sửa an toàn thư mục Common Data Model dưới dạng nguồn dữ liệu](connect-common-data-model.md) hoặc [tạo mới hoặc cập nhật môi trường hiện có](manage-environments.md#create-an-environment-in-an-existing-organization).

> [!IMPORTANT]
> - Tài khoản lưu trữ Azure Data Lake thế hệ 2 dự định sử dụng dịch vụ chính phải [Đã bật Không gian Tên phân cấp (HNS)](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-namespace).
> - Bạn cần quyền quản trị cho đăng ký Azure của mình để tạo dịch vụ chính.

## <a name="create-azure-service-principal-for-audience-insights"></a>Tạo dịch vụ chính Azure để có thông tin chi tiết về đối tượng

Trước khi tạo một dịch vụ chính mới để có thông tin chi tiết về đối tượng, hãy kiểm tra xem dịch vụ đó đã tồn tại trong tổ chức của bạn chưa.

### <a name="look-for-an-existing-service-principal"></a>Tìm một dịch vụ chính hiện có

1. Đi tới [Cổng quản trị Azure](https://portal.azure.com) và đăng nhập vào tổ chức của bạn.

2. Chọn **Azure Active Directory** từ các dịch vụ Azure.

3. Trong **Quản lý**, chọn **Ứng dụng doanh nghiệp**.

4. Tìm kiếm ID ứng dụng của bên thứ nhất thông tin chi tiết về đối tượng `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` hoặc tên `Dynamics 365 AI for Customer Insights`.

5. Nếu bạn tìm thấy một bản ghi phù hợp, điều đó có nghĩa là dịch vụ chính cho thông tin chi tiết về đối tượng tồn tại. Bạn không cần tạo lại dịch vụ chính.
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Ảnh chụp màn hình hiển thị dịch vụ chính hiện có.":::
   
6. Nếu không có kết quả nào được trả lại, hãy tạo một dịch vụ chính mới.

### <a name="create-a-new-service-principal"></a>Tạo dịch vụ chính mới

1. Cài đặt phiên bản mới nhất của **Azure Active Directory PowerShell for Graph**. Để biết thêm thông tin, hãy xem [Cài đặt Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).
   - Trên PC, chọn phím Windows trên bàn phím và tìm kiếm **Windows PowerShell** và **Chạy với tư cách quản trị viên**.
   
   - Trong cửa sổ PowerShell mở ra, hãy nhập `Install-Module AzureAD`.

2. Tạo dịch vụ chính cho thông tin chi tiết về đối tượng với mô-đun Azure AD PowerShell.
   - Trong cửa sổ PowerShell, hãy nhập `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`. Thay thế “ID đối tượng thuê của bạn” bằng ID thực tế của đối tượng thuê mà bạn muốn tạo dịch vụ chính. Tham số tên môi trường `AzureEnvironmentName` là không bắt buộc.
  
   - Nhập `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Lệnh này tạo dịch vụ chính cho thông tin chi tiết về đối tượng trên đối tượng thuê đã chọn.  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Cấp quyền cho dịch vụ chính để truy cập vào tài khoản lưu trữ

Truy cập cổng Azure để cấp quyền cho dịch vụ chính đối với tài khoản lưu trữ mà bạn muốn sử dụng trong thông tin chi tiết về đối tượng.

1. Đi tới [Cổng quản trị Azure](https://portal.azure.com) và đăng nhập vào tổ chức của bạn.

1. Mở tài khoản lưu trữ mà bạn muốn dịch vụ chính cho thông tin chi tiết về đối tượng có quyền truy cập.

1. Chọn **Kiểm soát truy cập (IAM)** từ ngăn điều hướng và chọn **Thêm** > **Thêm gán vai trò**.
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Ảnh chụp màn hình hiển thị cổng Azure trong khi thêm gán vai trò.":::
   
1. Trong ngăn **Thêm gán vai trò**, hãy đặt các thuộc tính sau:
   - Vai trò: *Người đóng góp dữ liệu Storage Blob*
   - Gán quyền truy cập cho: *Người dùng, nhóm hoặc dịch vụ chính*
   - Chọn: *Dynamics 365 AI cho Customer Insights* ([dịch vụ chính mà bạn đã tạo](#create-a-new-service-principal))

1.  Chọn **Lưu**.

Có thể mất đến 15 phút để các thay đổi được thực hiện.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a>Nhập ID tài nguyên Azure hoặc chi tiết Đăng ký Azure trong tệp đính kèm tài khoản lưu trữ cho Audience Insights.

Đính kèm tài khoản lưu trữ Azure Data Lake trong thông tin chi tiết về đối tượng để [lưu trữ dữ liệu kết quả](manage-environments.md) hoặc [sử dụng làm nguồn dữ liệu](connect-common-data-service-lake.md). Chọn tùy chọn Azure Data Lake cho phép bạn chọn giữa phương pháp dựa trên tài nguyên hoặc dựa trên đăng ký.

Thực hiện theo các bước dưới đây để cung cấp thông tin cần thiết về phương pháp đã chọn.

### <a name="resource-based-storage-account-connection"></a>Kết nối tài khoản lưu trữ dựa trên tài nguyên

1. Đi tới [Cổng quản trị Azure](https://portal.azure.com), đăng nhập vào gói đăng ký của bạn và mở tài khoản lưu trữ.

1. Đi đến **Cài đặt** > **Thuộc tính** trên ngăn điều hướng.

1. Sao chép giá trị ID tài nguyên tài khoản lưu trữ.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Sao chép ID tài nguyên tài khoản lưu trữ.":::

1. Trong thông tin chi tiết về đối tượng, hãy chèn ID tài nguyên vào trường tài nguyên được hiển thị trong màn hình kết nối tài khoản lưu trữ.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Nhập thông tin ID tài nguyên tài khoản lưu trữ.":::   
   
1. Tiếp tục với các bước còn lại trong thông tin chi tiết về đối tượng để đính kèm tài khoản lưu trữ.

### <a name="subscription-based-storage-account-connection"></a>Kết nối tài khoản lưu trữ dựa trên đăng ký

1. Đi tới [Cổng quản trị Azure](https://portal.azure.com), đăng nhập vào gói đăng ký của bạn và mở tài khoản lưu trữ.

1. Đi đến **Cài đặt** > **Thuộc tính** trên ngăn điều hướng.

1. Xem lại **Đăng ký**, **Nhóm tài nguyên** và **Tên** của tài khoản lưu trữ để đảm bảo bạn chọn đúng giá trị trong thông tin chi tiết về đối tượng.

1. Trong thông tin chi tiết về đối tượng, hãy chọn giá trị hoặc cho các trường tương ứng khi đính kèm tài khoản lưu trữ.
   
1. Tiếp tục với các bước còn lại trong thông tin chi tiết về đối tượng để đính kèm tài khoản lưu trữ.


[!INCLUDE[footer-include](../includes/footer-banner.md)]