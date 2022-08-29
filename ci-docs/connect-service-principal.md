---
title: Kết nối với một tài khoản Azure Data Lake Storage bằng cách sử dụng tên dịch vụ chính Azure
description: Sử dụng tên dịch vụ chính Azure để kết nối với kho dữ liệu của riêng bạn.
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: eba10068c48db5c147100c25a397bcc13b014784
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304223"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Kết nối với một tài khoản Azure Data Lake Storage bằng cách sử dụng tên dịch vụ chính Azure

Dynamics 365 Customer Insights cung cấp một tùy chọn để kết nối với một Azure Data Lake Storage tài khoản bằng cách sử dụng chính dịch vụ Azure thay vì các khóa tài khoản lưu trữ.

Các công cụ tự động sử dụng dịch vụ Azure phải có quyền hạn chế. Thay vì để các ứng dụng đăng nhập với tư cách là người dùng có đầy đủ đặc quyền, Azure cung cấp các dịch vụ chính. Sử dụng các nguyên tắc dịch vụ để bảo mật [thêm hoặc chỉnh sửa thư mục Mô hình Dữ liệu Chung dưới dạng nguồn dữ liệu](connect-common-data-model.md) hoặc [tạo hoặc cập nhật môi trường](create-environment.md).

## <a name="prerequisites"></a>Điều kiện tiên quyết

- Tài khoản Data Lake Storage sẽ sử dụng dịch vụ chính phải là Gen2. Tài khoản lưu trữ Azure Data Lake Gen1 không được hỗ trợ.
- Tài khoản Data Lake Storage có [không gian tên phân cấp được bật](/azure/storage/blobs/data-lake-storage-namespace).
- Quyền quản trị đối với Azure Tenant của bạn, nếu bạn phải tạo dịch vụ chính mới.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Tạo một tên dịch vụ chính Azure cho Customer Insights

Trước khi tạo dịch vụ chính mới cho Thông tin chi tiết về khách hàng, hãy kiểm tra xem nó đã tồn tại trong tổ chức của bạn chưa. Trong hầu hết các trường hợp, nó đã tồn tại.

### <a name="look-for-an-existing-service-principal"></a>Tìm một dịch vụ chính hiện có

1. Đi tới [Cổng quản trị Azure](https://portal.azure.com) và đăng nhập vào tổ chức của bạn.

2. Từ **Dịch vụ Azure**, hãy chọn **Azure Active Directory**.

3. Dưới **Quản lý**, lựa chọn **Ứng dụng Microsoft**.

4. Thêm bộ lọc cho **ID ứng dụng bắt đầu bằng**`0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` hoặc tìm kiếm tên `Dynamics 365 AI for Customer Insights`.

5. Nếu bạn tìm thấy một bản ghi phù hợp, điều đó có nghĩa là tên dịch vụ chính đã tồn tại. [Cấp quyền](#grant-permissions-to-the-service-principal-to-access-the-storage-account) để hiệu trưởng dịch vụ truy cập vào tài khoản lưu trữ.

   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Ảnh chụp màn hình hiển thị một tên dịch vụ chính hiện có.":::

6. Nếu không có kết quả nào được trả lại, [tạo một dịch vụ chính mới](#create-a-new-service-principal).

### <a name="create-a-new-service-principal"></a>Tạo dịch vụ chính mới

1. Cài đặt phiên bản mới nhất của Azure Active Directory PowerShell for Graph. Để biết thêm thông tin, hãy truy cập [Cài đặt Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).

   1. Trên PC, nhấn phím Windows trên bàn phím và tìm kiếm **Windows PowerShell** và chọn **Chạy như quản trị viên**.

   1. Trong cửa sổ PowerShell mở ra, hãy nhập `Install-Module AzureAD`.

2. Tạo tên dịch vụ chính cho Customer Insights với mô-đun Azure AD PowerShell.

   1. Trong cửa sổ PowerShell, hãy nhập `Connect-AzureAD -TenantId "[your Directory ID]" -AzureEnvironmentName Azure`. Thay thế *[ID thư mục của bạn]* với ID thư mục thực tế của đăng ký Azure của bạn nơi bạn muốn tạo dịch vụ chính. Tham số tên môi trường `AzureEnvironmentName` là không bắt buộc.
  
   1. Nhập `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Lệnh này tạo dịch vụ chính cho Thông tin chi tiết về khách hàng trên đăng ký Azure đã chọn.

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Cấp quyền cho dịch vụ chính để truy cập vào tài khoản lưu trữ

Để cấp quyền cho người quản lý dịch vụ đối với tài khoản lưu trữ bạn muốn sử dụng trong Thông tin chi tiết về khách hàng, một trong các vai trò sau đây phải được chỉ định cho tài khoản lưu trữ hoặc vùng chứa:

|Chứng chỉ|Yêu cầu|
|----------|------------|
|Người dùng hiện đã đăng nhập|**Vai diễn** : Bộ đọc dữ liệu khối lưu trữ, Người đóng góp khối lưu trữ hoặc Chủ sở hữu khối khối lưu trữ.<br>**Mức độ** : Quyền được cấp trên tài khoản lưu trữ hoặc vùng chứa.</br>|
|Khách hàng chính của dịch vụ thông tin chi tiết -<br>Sử dụng Azure Data Lake Storage với tư cách là nguồn dữ liệu</br>|Tùy chọn 1<ul><li>**Vai diễn** : Trình đọc dữ liệu Blob lưu trữ, Người đóng góp dữ liệu Blob lưu trữ hoặc Chủ sở hữu dữ liệu Blob lưu trữ.</li><li>**Mức độ** : Quyền được cấp trên tài khoản lưu trữ.</li></ul>Lựa chọn 2 *(không chia sẻ quyền truy cập Chính của Dịch vụ vào tài khoản lưu trữ)*<ul><li>**Vai trò 1** : Trình đọc dữ liệu Blob lưu trữ, Người đóng góp dữ liệu Blob lưu trữ hoặc Chủ sở hữu dữ liệu Blob lưu trữ.</li><li>**Mức độ** : Quyền được cấp trên vùng chứa.</li><li>**Vai trò 2** : Bộ xóa dữ liệu khối lưu trữ.</li><li>**Mức độ** : Quyền được cấp trên tài khoản lưu trữ.</li></ul>|
|Khách hàng chính của dịch vụ thông tin chi tiết - <br>Sử dụng Azure Data Lake Storage như một đầu ra hoặc điểm đến</br>|Tùy chọn 1<ul><li>**Vai diễn** : Người đóng góp dữ liệu khối lưu trữ hoặc Chủ sở hữu khối khối lưu trữ.</li><li>**Mức độ** : Quyền được cấp trên tài khoản lưu trữ.</li></ul>Lựa chọn 2 *(không chia sẻ quyền truy cập Chính của Dịch vụ vào tài khoản lưu trữ)*<ul><li>**Vai diễn** : Người đóng góp dữ liệu khối lưu trữ hoặc Chủ sở hữu khối khối lưu trữ.</li><li>**Mức độ** : Quyền được cấp trên vùng chứa.</li><li>**Vai trò 2** : Bộ lưu trữ Blob Delegator.</li><li>**Mức độ** : Quyền được cấp trên tài khoản lưu trữ.</li></ul>|

1. Đi tới [Cổng quản trị Azure](https://portal.azure.com) và đăng nhập vào tổ chức của bạn.

1. Mở tài khoản lưu trữ mà bạn muốn người dùng chính của dịch vụ để Customer Insights có quyền truy cập.

1. Trên ngăn bên trái, hãy chọn **Kiểm soát truy cập (IAM)**, sau đó chọn **Thêm vào** > **Thêm gán vai trò**.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Ảnh chụp màn hình hiển thị cổng thông tin Azure trong khi thêm gán vai trò.":::

1. Trên ngăn **Thêm gán vai trò**, đặt các thuộc tính sau:
   - **Vai diễn** : Trình đọc dữ liệu Blob lưu trữ, Người đóng góp Blob lưu trữ hoặc Chủ sở hữu Blob lưu trữ dựa trên thông tin đăng nhập được liệt kê ở trên.
   - **Chỉ định quyền truy cập cho** :**Người dùng, nhóm hoặc dịch vụ chính**
   - **Lựa chọn** các thành viên: **Dynamics 365 AI cho thông tin chi tiết về khách hàng** (các [dịch vụ chính](#create-a-new-service-principal) bạn đã tra cứu trước đó trong quy trình này)

1. Lựa chọn **Đánh giá + chỉ định**.

Có thể mất đến 15 phút để các thay đổi được thực hiện.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-customer-insights"></a>Nhập ID tài nguyên Azure hoặc chi tiết đăng ký Azure trong tệp đính kèm tài khoản lưu trữ cho Thông tin chi tiết về khách hàng

Đính kèm tài khoản Data Lake Storage trong Thông tin chi tiết về khách hàng với [lưu trữ dữ liệu đầu ra](manage-environments.md) hoặc [sử dụng nó như một nguồn dữ liệu](connect-dataverse-managed-lake.md). Chọn giữa một [dựa trên tài nguyên](#resource-based-storage-account-connection) hoặc một [dựa trên đăng ký](#subscription-based-storage-account-connection) tiếp cận và làm theo các bước đó.

### <a name="resource-based-storage-account-connection"></a>Kết nối tài khoản lưu trữ dựa trên tài nguyên

1. Đi tới [Cổng thông tin quản trị Azure](https://portal.azure.com), đăng nhập vào gói đăng ký của bạn và mở tài khoản lưu trữ.

1. Trên ngăn bên trái, đi tới **Cài đặt** > **Điểm cuối**.

1. Sao chép giá trị ID tài nguyên tài khoản lưu trữ.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Sao chép ID tài nguyên tài khoản lưu trữ.":::

1. Trong Thông tin chi tiết về khách hàng, hãy chèn ID tài nguyên vào trường tài nguyên được hiển thị trên màn hình kết nối tài khoản lưu trữ.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Nhập thông tin ID tài nguyên tài khoản lưu trữ.":::

1. Tiếp tục với các bước còn lại trong Thông tin chi tiết về khách hàng để đính kèm tài khoản lưu trữ.

### <a name="subscription-based-storage-account-connection"></a>Kết nối tài khoản lưu trữ dựa trên đăng ký

1. Đi tới [Cổng thông tin quản trị Azure](https://portal.azure.com), đăng nhập vào gói đăng ký của bạn và mở tài khoản lưu trữ.

1. Trên ngăn bên trái, đi tới **Cài đặt** > **Thuộc tính**.

1. Xem lại **Đăng ký**, **tài nguyên**, và **Tên** của tài khoản lưu trữ để đảm bảo rằng bạn chọn các giá trị phù hợp trong Thông tin chi tiết về khách hàng.

1. Trong Thông tin chi tiết về khách hàng, hãy chọn giá trị cho các trường tương ứng khi đính kèm tài khoản lưu trữ.

1. Tiếp tục với các bước còn lại trong Thông tin chi tiết về khách hàng để đính kèm tài khoản lưu trữ.

[!INCLUDE [footer-include](includes/footer-banner.md)]
