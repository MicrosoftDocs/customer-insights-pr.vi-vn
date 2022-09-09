---
title: Làm việc với dữ liệu Customer Insights trong Microsoft Dataverse
description: Tìm hiểu cách kết nối Thông tin chi tiết về khách hàng và Microsoft Dataverse và hiểu các thực thể đầu ra được xuất sang Dataverse.
ms.date: 08/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: dfa63110fc5291f2b63aebf588d6fdd20ed4ab67
ms.sourcegitcommit: 134aac66e3e0b77b2e96a595d6acbb91bf9afda2
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 09/07/2022
ms.locfileid: "9424335"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Làm việc với dữ liệu Customer Insights trong Microsoft Dataverse

Customer Insights cung cấp tùy chọn để hiển thị các thực thể đầu ra trong [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Sự tích hợp này cho phép chia sẻ dữ liệu dễ dàng và phát triển tùy chỉnh thông qua cách tiếp cận mã thấp / không mã. Các [thực thể đầu ra](#output-entities) có sẵn dưới dạng bảng trong một Dataverse Môi trường. Bạn có thể sử dụng dữ liệu cho bất kỳ ứng dụng nào khác dựa trên Dataverse những cái bàn. Các bảng này cho phép các tình huống như quy trình làm việc tự động thông qua Power Automate hoặc xây dựng ứng dụng với Power Apps.

Đang kết nối với của bạn Dataverse môi trường cũng cho phép bạn [nhập dữ liệu từ tại chỗ nguồn dữ liệu bằng cách sử dụng Power Platform luồng dữ liệu và cổng kết nối](connect-power-query.md#add-data-from-on-premises-data-sources).

## <a name="prerequisites"></a>Điều kiện tiên quyết

- Thông tin chi tiết về khách hàng và Dataverse môi trường phải được lưu trữ trong cùng một khu vực.
- Một vai trò quản trị viên toàn cầu được thiết lập trong Dataverse Môi trường. Xác minh nếu điều này [Dataverse môi trường được liên kết](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) vào các nhóm bảo mật nhất định và đảm bảo rằng bạn đã được thêm vào các nhóm bảo mật đó.
- Không có môi trường Thông tin chi tiết về khách hàng nào khác đã được liên kết với Dataverse môi trường bạn muốn kết nối. Học cách [loại bỏ một kết nối hiện có với một Dataverse Môi trường](#remove-an-existing-connection-to-a-dataverse-environment).
- Một Microsoft Dataverse môi trường được kết nối với một tài khoản lưu trữ nếu bạn định cấu hình môi trường để [sử dụng của bạn Azure Data Lake Storage](own-data-lake-storage.md).

## <a name="dataverse-storage-capacity-entitlement"></a>Dataverse quyền dung lượng lưu trữ

Đăng ký Thông tin chi tiết về khách hàng cho phép bạn tăng thêm dung lượng cho tổ chức của bạn hiện có [Dataverse khả năng lưu trữ](/power-platform/admin/capacity-storage). Dung lượng thêm vào phụ thuộc vào số lượng cấu hình mà thuê bao của bạn sử dụng.

**Ví dụ:**

Giả sử bạn nhận được 15 GB bộ nhớ cơ sở dữ liệu và 20 GB bộ nhớ tệp cho mỗi 100.000 hồ sơ khách hàng. Nếu đăng ký của bạn bao gồm 300.000 hồ sơ khách hàng, thì tổng dung lượng lưu trữ của bạn là 45 GB (3 x 15 GB) bộ nhớ cơ sở dữ liệu và 60 GB bộ nhớ tệp (3 x 20 GB). Tương tự, nếu bạn có đăng ký B-to-B với 30 nghìn tài khoản, tổng dung lượng lưu trữ của bạn là 45 GB (3 x 15 GB) bộ nhớ cơ sở dữ liệu và 60 GB bộ nhớ tệp (3 x 20 GB).

Dung lượng nhật ký không gia tăng và cố định cho tổ chức của bạn.

Để biết thêm thông tin về các quyền năng lực chi tiết, hãy xem [Hướng dẫn cấp phép Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

## <a name="connect-a-dataverse-environment-to-customer-insights"></a>Kết nối một Dataverse môi trường để Thông tin chi tiết về khách hàng

Các **Microsoft Dataverse** bước cho phép bạn kết nối Thông tin chi tiết về khách hàng với Dataverse môi trường trong khi [tạo môi trường Thông tin chi tiết về khách hàng](create-environment.md).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="chia sẻ dữ liệu với Microsoft Dataverse tự động bật cho môi trường mới.":::

1. Cung cấp URL cho của bạn Dataverse hoặc để trống để tạo một môi trường cho bạn.

   > [!NOTE]
   > Sau khi thiết lập kết nối giữa Thông tin chi tiết về khách hàng và Dataverse, không thay đổi tên tổ chức cho Dataverse Môi trường. Tên của tổ chức được sử dụng trong Dataverse URL và tên đã thay đổi phá vỡ kết nối với Thông tin chi tiết về khách hàng.

   [Power Platform quản trị viên có thể kiểm soát ai có thể tạo Dataverse môi trường](/power-platform/admin/control-environment-creation). Nếu bạn đang cố gắng thiết lập môi trường Thông tin chi tiết về khách hàng mới và không thể, quản trị viên có thể đã vô hiệu hóa việc tạo Dataverse môi trường cho tất cả mọi người ngoại trừ quản trị viên.

1. Nếu bạn đang sử dụng tài khoản Data Lake Storage của riêng mình:
   1. Lựa chọn **Bật chia sẻ dữ liệu** với Dataverse.
   1. Nhập **Định danh quyền**. Để nhận số nhận dạng quyền, [cho phép chia sẻ dữ liệu với Dataverse từ của riêng bạn Azure Data Lake Storage](#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview).

## <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Bật chia sẻ dữ liệu với Dataverse từ của riêng bạn Azure Data Lake Storage (xem trước)

Trong [của riêng bạn Azure Data Lake Storage tài khoản](own-data-lake-storage.md), xác minh rằng người dùng thiết lập môi trường Thông tin chi tiết về khách hàng có ít nhất **Bộ đọc dữ liệu khối lưu trữ** quyền trên`customerinsights` vùng chứa trong tài khoản lưu trữ.

### <a name="limitations"></a>Giới hạn

- Chỉ ánh xạ 1-1 giữa một Dataverse tổ chức và một Azure Data Lake Storage tài khoản. Một lần Dataverse tổ chức được kết nối với tài khoản lưu trữ, tổ chức không thể kết nối với tài khoản lưu trữ khác. Hạn chế này ngăn cản Dataverse từ việc điền nhiều tài khoản lưu trữ.
- Chia sẻ dữ liệu sẽ không hoạt động nếu cần thiết lập Azure Private Link để truy cập vào Azure Data Lake Storage vì nó nằm sau tường lửa. Dataverse hiện không hỗ trợ kết nối với điểm cuối riêng tư thông qua Liên kết riêng tư.

### <a name="set-up-security-groups-on-your-own-azure-data-lake-storage"></a>Tự thiết lập các nhóm bảo mật Azure Data Lake Storage

1. Tạo hai nhóm bảo mật trên đăng ký Azure của bạn - một nhóm **Người đọc** nhóm an ninh và một **Người đóng góp** nhóm bảo mật và thiết lập Microsoft Dataverse dịch vụ với tư cách là chủ sở hữu cho cả hai nhóm bảo mật.

1. Quản lý Danh sách Kiểm soát Truy cập (ACL) trên`customerinsights` vùng chứa trong tài khoản lưu trữ của bạn thông qua các nhóm bảo mật này.
   1. Thêm Microsoft Dataverse dịch vụ và bất kỳ Dataverse các ứng dụng kinh doanh dựa trên cơ sở như Dynamics 365 Marketing cho **Người đọc** nhóm an ninh với **chỉ đọc** quyền.
   1. cộng *chỉ có* ứng dụng Thông tin chi tiết về khách hàng cho **Người đóng góp** nhóm bảo mật để cấp cho cả hai **đọc và viết** quyền để viết tiểu sử và thông tin chi tiết.

### <a name="set-up-powershell"></a>Thiết lập PowerShell

Thiết lập PowerShell để thực thi các tập lệnh PowerShell.

1. Cài đặt phiên bản mới nhất của [Azure Active Directory PowerShell cho đồ thị](/powershell/azure/active-directory/install-adv2).
   1. Trên PC, chọn phím Windows trên bàn phím và tìm kiếm **Windows PowerShell** và chọn **Chạy với tư cách quản trị viên**.
   1. Trong cửa sổ PowerShell mở ra, hãy nhập `Install-Module AzureAD`.

1. Nhập ba mô-đun.
   1. Trong cửa sổ PowerShell, hãy nhập`Install-Module -Name Az.Accounts` và làm theo các bước.
   1. Lặp lại cho`Install-Module -Name Az.Resources` và `Install-Module -Name Az.Storage`.

### <a name="execute-powershell-scripts-and-obtain-the-permission-identifier"></a>Thực thi các tập lệnh PowerShell và lấy Mã nhận dạng quyền

1. Tải xuống hai tập lệnh PowerShell bạn cần để chạy từ kỹ sư của chúng tôi [GitHub repo](https://github.com/trin-msft/byol).
   - `CreateSecurityGroups.ps1`: Yêu cầu quyền quản trị của người thuê.
   - `ByolSetup.ps1`: Yêu cầu quyền của Chủ sở hữu dữ liệu khối lưu trữ ở cấp tài khoản lưu trữ / vùng chứa. Tập lệnh này sẽ tạo ra sự cho phép dành cho bạn. Nhiệm vụ của bạn có thể được xóa theo cách thủ công sau khi chạy thành công tập lệnh.

1. Hành hình`CreateSecurityGroups.ps1` trong Windows PowerShell bằng cách cung cấp ID đăng ký Azure chứa Azure Data Lake Storage. Mở tập lệnh PowerShell trong trình chỉnh sửa để xem lại thông tin bổ sung và logic được triển khai.

   Tập lệnh này tạo hai nhóm bảo mật trên đăng ký Azure của bạn: một cho nhóm Người đọc và một nhóm khác cho nhóm Cộng tác viên. Microsoft Dataverse dịch vụ là chủ sở hữu cho cả hai nhóm bảo mật này.

1. Lưu cả hai giá trị ID nhóm bảo mật được tạo bởi tập lệnh này để sử dụng trong`ByolSetup.ps1` script.

   > [!NOTE]
   > Đối tượng thuê của bạn có thể tắt tính năng tạo nhóm bảo mật. Trong trường hợp đó, cần thiết lập thủ công và Azure AD quản trị viên sẽ phải [cho phép tạo nhóm bảo mật](/azure/active-directory/enterprise-users/groups-self-service-management).

1. Hành hình`ByolSetup.ps1` trong Windows PowerShell bằng cách cung cấp ID đăng ký Azure chứa Azure Data Lake Storage, tên tài khoản lưu trữ, tên nhóm tài nguyên và các giá trị ID nhóm bảo mật Reader và Contributor. Mở tập lệnh PowerShell trong trình chỉnh sửa để xem lại thông tin bổ sung và logic được triển khai.

   Tập lệnh này thêm kiểm soát truy cập dựa trên vai trò bắt buộc cho Microsoft Dataverse dịch vụ và bất kỳ Dataverse ứng dụng kinh doanh dựa trên cơ sở. Nó cũng cập nhật Danh sách kiểm soát truy cập (ACL) trên`customerinsights` vùng chứa cho các nhóm bảo mật được tạo bằng`CreateSecurityGroups.ps1` script. Nhóm Contributor được cung cấp *rwx* quyền và nhóm độc giả được cấp *rx* chỉ sự cho phép.

1. Sao chép chuỗi đầu ra giống như sau:`https://DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`

1. Nhập chuỗi đầu ra đã sao chép vào **Mã định danh quyền** trường của bước cấu hình môi trường cho Microsoft Dataverse.

   :::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Tùy chọn cấu hình để cho phép chia sẻ dữ liệu từ của riêng bạn Azure Data Lake Storage với Microsoft Dataverse .":::

## <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>Xóa kết nối hiện có với một Dataverse Môi trường

Khi kết nối với một Dataverse môi trường, thông báo lỗi **Tổ chức CDS này đã được gắn với một phiên bản Thông tin chi tiết về khách hàng khác** có nghĩa là Dataverse môi trường đã được sử dụng trong môi trường Thông tin chi tiết về khách hàng. Bạn có thể xóa kết nối hiện có với tư cách là quản trị viên toàn cầu trên Dataverse Môi trường. Có thể mất vài giờ để điền các thay đổi.

1. Truy cập [Power Apps](https://make.powerapps.com).
1. Chọn môi trường từ bộ chọn môi trường.
1. Đi đến **Các giải pháp**.
1. Gỡ cài đặt hoặc xóa giải pháp có tên **Dynamics 365 Customer Insights Bổ trợ Thẻ khách hàng (Xem trước)**.

HOẶC

1. Mở của bạn Dataverse Môi trường.
1. Đi đến **Cài đặt nâng cao** > **Các giải pháp**.
1. Gỡ cài đặt **CustomerInsightsCustomerCard** dung dịch.

Nếu việc loại bỏ kết nối không thành công do các phần phụ thuộc, bạn cũng cần phải loại bỏ các phần phụ thuộc. Để biết thêm thông tin, hãy xem [Loại bỏ các phụ thuộc](/power-platform/alm/removing-dependencies).

## <a name="output-entities"></a>Các thực thể đầu ra

Một số thực thể đầu ra từ Thông tin chi tiết về khách hàng có sẵn dưới dạng bảng trong Dataverse. Các phần dưới đây mô tả sơ đồ dự kiến của các bảng này.

- [CustomerProfile](#customerprofile)
- [Hồ sơ liên hệ](#contactprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Enrichment](#enrichment)
- [Prediction](#prediction)
- [Thành viên phân khúc](#segment-membership)

### <a name="customerprofile"></a>CustomerProfile

Bảng này chứa hồ sơ khách hàng hợp nhất từ Customer Insights. Lược đồ cho hồ sơ khách hàng hợp nhất phụ thuộc vào các thực thể và thuộc tính được sử dụng trong quá trình hợp nhất dữ liệu. Sơ đồ hồ sơ khách hàng thường chứa một tập hợp con các thuộc tính từ [Định nghĩa Common Data Model CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile). Đối với kịch bản B-to-B, hồ sơ khách hàng chứa các tài khoản hợp nhất và giản đồ thường chứa một tập hợp con các thuộc tính từ [Định nghĩa Mô hình Dữ liệu Chung về Tài khoản](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/account).

### <a name="contactprofile"></a>Hồ sơ liên hệ

Một ContactProfile chứa thông tin hợp nhất về một số liên lạc. Liên hệ là [các cá nhân được ánh xạ tới một tài khoản](data-unification-contacts.md) trong kịch bản B-to-B.

| Column                       | Loại                | Description     |
| ---------------------------- | ------------------- | --------------- |
|  Ngày sinh            | Ngày giờ       |  Ngày sinh của liên hệ               |
|  Thành phố                 | Văn bản |  Thành phố của địa chỉ liên hệ               |
|  ContactId            | Văn bản |  ID của hồ sơ liên hệ               |
|  ContactProfileId     | Mã định danh duy nhất   |  HƯỚNG DẪN cho số liên lạc               |
|  CountryOrRegion      | Văn bản |  Quốc gia / Khu vực của địa chỉ liên hệ               |
|  CustomerId           | Văn bản |  ID của tài khoản mà liên hệ được ánh xạ tới               |
|  EntityName           | Văn bản |  Thực thể mà từ đó dữ liệu đến từ                |
|  FirstName            | Văn bản |  Tên của liên hệ               |
|  Giới tính               | Văn bản |  Giới tính của người liên hệ               |
|  ID                   | Văn bản |  GUID xác định dựa trên`Identifier`               |
|  Identifier           | Văn bản |  ID nội bộ của hồ sơ liên hệ:`ContactProfile|CustomerId|ContactId`               |
|  JobTitle             | Văn bản |  Chức vụ của người liên hệ               |
|  LastName             | Văn bản |  Họ của địa chỉ liên hệ               |
|  PostalCode           | Văn bản |  Mã ZIP của địa chỉ liên hệ               |
|  Email chính         | Văn bản |  Địa chỉ email của liên hệ               |
|  Điện thoại chính         | Văn bản |  Số điện thoại của người liên hệ               |
|  Bang hoặc tỉnh      | Văn bản |  Tiểu bang hoặc tỉnh của địa chỉ liên hệ               |
|  StreetAddress        | Văn bản |  Đường của địa chỉ liên hệ               |

### <a name="alternatekey"></a>AlternateKey

Bảng AlternateKey chứa khóa của các thực thể đã tham gia vào quá trình hợp nhất.

|Column  |Loại  |Description  |
|---------|---------|---------|
|DataSourceName    |Văn bản         | Tên nguồn dữ liệu. Ví dụ: `datasource5`        |
|EntityName        | Văn bản        | Tên của pháp nhân trong Thông tin chi tiết về khách hàng. Ví dụ: `contact1`        |
|AlternateValue    |Văn bản         |ID thay thế được ánh xạ tới ID khách hàng. Ví dụ: `cntid_1078`         |
|KeyRing           | Văn bản        | Giá trị JSON  </br> Ví dụ: [{"dataSourceName":" datasource5 ",</br>"entityName":" contact1",</br>"preferredKey":" cntid_1078",</br>"keys":[" cntid_1078"]}]       |
|CustomerId         | Văn bản        | ID của hồ sơ khách hàng hợp nhất.         |
|AlternateKeyId     | Mã định danh duy nhất        |  HƯỚNG DẪN xác định AlternateKey dựa trên`Identifier`      |
|Identifier |   Văn bản      |   `DataSourceName|EntityName|AlternateValue`  </br> Ví dụ: `testdatasource|contact1|cntid_1078`    |

### <a name="unifiedactivity"></a>UnifiedActivity

Bảng này chứa các hoạt động của người dùng có trong Customer Insights.

| Column            | Loại        | Description                                                                              |
|-------------------|-------------|------------------------------------------------------------------------------------------|
| CustomerId        | Văn bản      | ID hồ sơ khách hàng                                                                      |
| ActivityId        | Văn bản      | ID nội bộ của hoạt động khách hàng (khóa chính)                                       |
| SourceEntityName  | Văn bản      | Tên của thực thể nguồn                                                                |
| SourceActivityId  | Văn bản      | Khóa chính từ thực thể nguồn                                                       |
| ActivityType      | Văn bản      | Loại hoạt động ngữ nghĩa hoặc tên của hoạt động tùy chỉnh                                        |
| ActivityTimeStamp | Ngày giờ    | Dấu thời gian hoạt động                                                                      |
| Title             | Văn bản      | Tiêu đề hoặc tên của hoạt động                                                               |
| Description       | Văn bản      | Nội dung mô tả hoạt động                                                                     |
| URL               | Văn bản      | Liên kết đến một URL bên ngoài cụ thể cho hoạt động                                         |
| SemanticData      | Văn bản | Bao gồm danh sách các cặp khóa-giá trị cho các trường ánh xạ ngữ nghĩa cụ thể cho loại hoạt động |
| RangeIndex        | Văn bản      | Dấu thời gian Unix dùng để sắp xếp dòng thời gian hoạt động và truy vấn phạm vi hiệu quả |
| UnifiedActivityId   | Mã định danh duy nhất | ID nội bộ của hoạt động khách hàng (ActivityId) |

### <a name="customermeasure"></a>CustomerMeasure

Bảng này chứa dữ liệu đầu ra của các giá trị đo dựa trên thuộc tính khách hàng.

| Column             | Loại             | Description                 |
|--------------------|------------------|-----------------------------|
| CustomerId         | Văn bản           | ID hồ sơ khách hàng        |
| Measures           | Văn bản      | Bao gồm danh sách các cặp khóa-giá trị cho tên giá trị đo và các giá trị cho khách hàng nhất định |
| Identifier | Văn bản           | `Customer_Measure|CustomerId` |
| CustomerMeasureId | Mã định danh duy nhất     | ID hồ sơ khách hàng |

### <a name="enrichment"></a>Enrichment

Bảng này chứa kết quả đầu ra của quá trình tăng cường.

| Column               | Loại             |  Description                                          |
|----------------------|------------------|------------------------------------------------------|
| CustomerId           | Văn bản           | ID hồ sơ khách hàng                                 |
| EnrichmentProvider   | Văn bản           | Tên nhà cung cấp cho quá trình tăng cường                                  |
| EnrichmentType       | Văn bản           | Loại tăng cường                                      |
| Values               | Văn bản      | Danh sách các thuộc tính do quá trình tăng cường tạo ra |
| EnrichmentId | Mã định danh duy nhất            | GUID xác định được tạo từ`Identifier` |
| Identifier   | Văn bản           | `EnrichmentProvider|EnrichmentType|CustomerId`         |

### <a name="prediction"></a>Prediction

Bảng này chứa kết quả đầu ra của lượt dự đoán mô hình.

| Column               | Loại        | Description                                          |
|----------------------|-------------|------------------------------------------------------|
| CustomerId           | Văn bản      | ID hồ sơ khách hàng                                  |
| ModelProvider        | Văn bản      | Tên nhà cung cấp mô hình                                      |
| Model                | Văn bản      | Tên mô hình                                                |
| Values               | Văn bản | Danh sách các thuộc tính do mô hình tạo ra |
| Dự đoánId | Mã định danh duy nhất       | GUID xác định được tạo từ`Identifier` |
| Identifier   | Văn bản      |  `Model|ModelProvider|CustomerId`                      |

### <a name="segment-membership"></a>Thành viên phân khúc

Bảng này chứa thông tin thành viên phân khúc của hồ sơ khách hàng.

| Column        | Loại | Description                        |
|--------------------|--------------|-----------------------------|
| CustomerId        | Văn bản       | ID hồ sơ khách hàng        |
| SegmentProvider      | Văn bản       | Ứng dụng xuất bản các phân đoạn.      |
| SegmentMembershipType | Văn bản       | Loại khách hàng cho hồ sơ thành viên phân khúc này. Hỗ trợ nhiều loại như Khách hàng, Liên hệ hoặc Tài khoản. Mặc định: Khách hàng  |
| Phân khúc       | Văn bản  | Danh sách các phân đoạn duy nhất mà hồ sơ khách hàng là thành viên của      |
| Identifier  | Văn bản   | Định danh duy nhất của bản ghi thành viên phân khúc. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| SegmentMembershipId | Mã định danh duy nhất      | GUID xác định được tạo từ`Identifier`          |

[!INCLUDE [footer-include](includes/footer-banner.md)]
