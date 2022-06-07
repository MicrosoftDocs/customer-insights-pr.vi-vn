---
title: Làm việc với dữ liệu Customer Insights trong Microsoft Dataverse
description: Tìm hiểu cách kết nối Thông tin chi tiết về khách hàng và Microsoft Dataverse và hiểu các thực thể đầu ra được xuất sang Dataverse.
ms.date: 05/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 3848e143bc7cb2f345bc698a274b92148ef00669
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833702"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Làm việc với dữ liệu Customer Insights trong Microsoft Dataverse

Thông tin chi tiết về khách hàng cung cấp tùy chọn để cung cấp các thực thể đầu ra dưới dạng [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Sự tích hợp này cho phép chia sẻ dữ liệu dễ dàng và phát triển tùy chỉnh thông qua cách tiếp cận mã thấp / không mã. Các [thực thể đầu ra](#output-entities) có sẵn dưới dạng bảng trong một Dataverse Môi trường. Bạn có thể sử dụng dữ liệu cho bất kỳ ứng dụng nào khác dựa trên Dataverse những cái bàn. Các bảng này cho phép các tình huống như quy trình làm việc tự động thông qua Power Automate hoặc xây dựng ứng dụng với Power Apps.

Đang kết nối với của bạn Dataverse môi trường cũng cho phép bạn [nhập dữ liệu từ tại chỗ nguồn dữ liệu bằng cách sử dụng Power Platform luồng dữ liệu và các cổng](data-sources.md#add-data-from-on-premises-data-sources).

## <a name="prerequisites"></a>Điều kiện tiên quyết

- Thông tin chi tiết về khách hàng và Dataverse môi trường phải được lưu trữ trong cùng một khu vực.
- Bạn phải có vai trò quản trị viên toàn cầu trong Dataverse Môi trường. Xác minh nếu điều này [Dataverse môi trường được liên kết](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) vào các nhóm bảo mật nhất định và đảm bảo rằng bạn đã được thêm vào các nhóm bảo mật đó.
- Không có môi trường Thông tin chi tiết về khách hàng nào khác được liên kết với Dataverse môi trường bạn muốn kết nối. Học cách [loại bỏ một kết nối hiện có với một Dataverse Môi trường](#remove-an-existing-connection-to-a-dataverse-environment).
- Một Microsoft Dataverse môi trường chỉ có thể kết nối với một tài khoản lưu trữ duy nhất. Nó chỉ áp dụng nếu bạn định cấu hình môi trường để [sử dụng của bạn Azure Data Lake Storage](own-data-lake-storage.md).

## <a name="connect-a-dataverse-environment-to-customer-insights"></a>Kết nối một Dataverse môi trường để Thông tin chi tiết về khách hàng

Các **Microsoft Dataverse** bước cho phép bạn kết nối Thông tin chi tiết về khách hàng với Dataverse môi trường trong khi [tạo môi trường Thông tin chi tiết về khách hàng](create-environment.md).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="chia sẻ dữ liệu với Microsoft Dataverse tự động bật cho môi trường mới thuần.":::

Quản trị viên có thể định cấu hình Thông tin chi tiết về khách hàng để kết nối Dataverse Môi trường. Bằng cách cung cấp URL cho Dataverse môi trường, nó gắn liền với môi trường Thông tin chi tiết về khách hàng mới của họ.

Nếu bạn không muốn sử dụng Dataverse môi trường, hệ thống tạo ra một môi trường mới cho dữ liệu Thông tin chi tiết về khách hàng trong đối tượng thuê của bạn. [Power Platform quản trị viên có thể kiểm soát ai có thể tạo môi trường](/power-platform/admin/control-environment-creation). Khi bạn đang thiết lập môi trường Thông tin chi tiết về khách hàng và quản trị viên đã vô hiệu hóa việc tạo Dataverse môi trường dành cho tất cả mọi người ngoại trừ quản trị viên, bạn có thể không tạo được môi trường mới.

**Bật chia sẻ dữ liệu** với Dataverse bằng cách chọn hộp kiểm chia sẻ dữ liệu.

Nếu bạn đang sử dụng tài khoản Data Lake Storage của riêng mình, bạn cũng cần **Định danh quyền**. Để biết thêm thông tin về cách lấy số nhận dạng quyền, hãy xem lại phần sau.

## <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Bật chia sẻ dữ liệu với Dataverse từ của riêng bạn Azure Data Lake Storage (Xem trước)

Cho phép chia sẻ dữ liệu với Microsoft Dataverse khi môi trường của bạn [sử dụng của riêng bạn Azure Data Lake Storage tài khoản](own-data-lake-storage.md) cần một số cấu hình bổ sung. Người dùng thiết lập môi trường Thông tin chi tiết về khách hàng phải có ít nhất **Bộ đọc dữ liệu khối lưu trữ** quyền trên *Thấu hiểu khách hàng* thùng chứa trong Azure Data Lake Storage tài khoản.

1. Tạo hai nhóm bảo mật trên đăng ký Azure của bạn - một **Người đọc** nhóm an ninh và một **Người đóng góp** nhóm bảo mật và thiết lập Microsoft Dataverse dịch vụ với tư cách là chủ sở hữu cho cả hai nhóm bảo mật.
2. Quản lý Danh sách kiểm soát truy cập (ACL) trên vùng chứa CustomerInsights trong tài khoản lưu trữ của bạn thông qua các nhóm bảo mật này. Thêm Microsoft Dataverse dịch vụ và bất kỳ Dataverse các ứng dụng kinh doanh dựa trên cơ sở như Dynamics 365 Marketing cho **Người đọc** nhóm an ninh với **chỉ đọc** quyền. cộng *chỉ có* ứng dụng Thông tin chi tiết về khách hàng cho **Người đóng góp** nhóm bảo mật để cấp cho cả hai **đọc và viết** quyền để viết tiểu sử và thông tin chi tiết.

### <a name="limitations"></a>Giới hạn

Có hai hạn chế khi sử dụng Dataverse với riêng của bạn Azure Data Lake Storage tài khoản:

- Có một ánh xạ 1-1 giữa Dataverse tổ chức và một Azure Data Lake Storage tài khoản. Một lần Dataverse tổ chức được kết nối với tài khoản lưu trữ, tổ chức không thể kết nối với tài khoản lưu trữ khác. Hạn chế này ngăn cản rằng một Dataverse không điền nhiều tài khoản lưu trữ.
- Chia sẻ dữ liệu sẽ không hoạt động nếu cần thiết lập Azure Private Link để truy cập vào tài khoản lưu trữ Azure Data Lake của bạn vì nó nằm sau tường lửa. Dataverse hiện không hỗ trợ kết nối với các điểm cuối riêng tư thông qua Liên kết riêng.

### <a name="set-up-powershell"></a>Thiết lập PowerShell

Để thực thi các tập lệnh PowerShell, trước tiên bạn cần thiết lập PowerShell cho phù hợp.

1. Cài đặt phiên bản mới nhất của [Azure Active Directory PowerShell cho đồ thị](/powershell/azure/active-directory/install-adv2).
   1. Trên PC, chọn phím Windows trên bàn phím và tìm kiếm **Windows PowerShell** và chọn **Chạy với tư cách quản trị viên**.
   1. Trong cửa sổ PowerShell mở ra, hãy nhập `Install-Module AzureAD`.
2. Nhập ba mô-đun.
    1. Trong cửa sổ PowerShell, hãy nhập`Install-Module -Name Az.Accounts` và làm theo các bước.
    1. Lặp lại cho`Install-Module -Name Az.Resources` và `Install-Module -Name Az.Storage`.

### <a name="configuration-steps"></a>Các bước cấu hình

1. Tải xuống hai tập lệnh PowerShell bạn cần để chạy từ kỹ sư của chúng tôi [GitHub repo](https://github.com/trin-msft/byol).
    1. `CreateSecurityGroups.ps1`
       - Bạn cần *quản trị viên thuê nhà* quyền để chạy tập lệnh PowerShell này.
       - Tập lệnh PowerShell này tạo hai nhóm bảo mật trên đăng ký Azure của bạn. Một cho nhóm Người đọc và một cho nhóm Cộng tác viên và sẽ tạo Microsoft Dataverse dịch vụ với tư cách là chủ sở hữu cho cả hai nhóm bảo mật này.
       - Thực thi tập lệnh PowerShell này trong Windows PowerShell bằng cách cung cấp ID đăng ký Azure chứa Azure Data Lake Storage. Mở tập lệnh PowerShell trong trình chỉnh sửa để xem xét thông tin bổ sung và logic được triển khai.
       - Lưu cả hai giá trị ID nhóm bảo mật được tạo bởi tập lệnh này vì chúng tôi sẽ sử dụng chúng trong`ByolSetup.ps1` script.

        > [!NOTE]
        > Đối tượng thuê của bạn có thể tắt tính năng tạo nhóm bảo mật. Trong trường hợp đó, cần thiết lập thủ công và Azure AD quản trị viên sẽ phải [cho phép tạo nhóm bảo mật](/azure/active-directory/enterprise-users/groups-self-service-management).

    2. `ByolSetup.ps1`
        - Bạn cần *Chủ sở hữu dữ liệu khối lưu trữ* quyền ở cấp tài khoản lưu trữ / vùng chứa để chạy tập lệnh này hoặc tập lệnh này sẽ tạo một tập lệnh cho bạn. Nhiệm vụ của bạn có thể được xóa theo cách thủ công sau khi chạy thành công tập lệnh.
        - Tập lệnh PowerShell này thêm điều khiển truy cập dựa trên tole bắt buộc (RBAC) cho Microsoft Dataverse dịch vụ và bất kỳ Dataverse ứng dụng kinh doanh dựa trên cơ sở. Nó cũng cập nhật Danh sách kiểm soát truy cập (ACL) trên vùng chứa CustomerInsights cho các nhóm bảo mật được tạo bằng`CreateSecurityGroups.ps1` script. Nhóm Cộng tác viên sẽ có *rwx* quyền và nhóm độc giả sẽ có *rx* chỉ sự cho phép.
        - Thực thi tập lệnh PowerShell này trong Windows PowerShell bằng cách cung cấp ID đăng ký Azure chứa Azure Data Lake Storage, tên tài khoản lưu trữ, tên nhóm tài nguyên và các giá trị ID nhóm bảo mật Người đọc và Người đóng góp. Mở tập lệnh PowerShell trong trình chỉnh sửa để xem xét thông tin bổ sung và logic được triển khai.
        - Sao chép chuỗi đầu ra sau khi chạy thành công tập lệnh. Chuỗi đầu ra trông giống như sau:`https://DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`

2. Nhập chuỗi đầu ra được sao chép từ bên trên vào **Định danh quyền** của bước cấu hình môi trường cho Microsoft Dataverse.

:::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Tùy chọn cấu hình để cho phép chia sẻ dữ liệu từ của riêng bạn Azure Data Lake Storage với Microsoft Dataverse .":::

### <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>Xóa kết nối hiện có với một Dataverse Môi trường

Khi kết nối với một Dataverse môi trường, thông báo lỗi **Tổ chức CDS này đã được đính kèm với một phiên bản Thông tin chi tiết về khách hàng khác** có nghĩa là Dataverse môi trường đã được sử dụng trong môi trường Thông tin chi tiết về khách hàng. Bạn có thể xóa kết nối hiện có với tư cách là quản trị viên toàn cầu trên Dataverse Môi trường. Có thể mất vài giờ để điền các thay đổi.

1. Truy cập [Power Apps](https://make.powerapps.com).
1. Chọn môi trường từ bộ chọn môi trường.
1. Đi đến **Các giải pháp**
1. Gỡ cài đặt hoặc xóa giải pháp có tên **Dynamics 365 Customer Insights Bổ trợ Thẻ khách hàng (Xem trước)**.

HOẶC

1. Mở của bạn Dataverse Môi trường.
1. Đi đến **Cài đặt nâng cao** > **Các giải pháp**.
1. Gỡ cài đặt **CustomerInsightsCustomerCard** dung dịch.

Nếu việc loại bỏ kết nối không thành công do các phần phụ thuộc, bạn cũng cần phải loại bỏ các phần phụ thuộc. Để biết thêm thông tin, hãy xem [Loại bỏ các phụ thuộc](/power-platform/alm/removing-dependencies).

## <a name="output-entities"></a>Các thực thể đầu ra

Một số thực thể đầu ra từ Thông tin chi tiết về khách hàng có sẵn dưới dạng bảng trong Dataverse. Các phần dưới đây mô tả sơ đồ dự kiến của các bảng này.

- [CustomerProfile](#customerprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Enrichment](#enrichment)
- [Prediction](#prediction)
- [Thành viên phân khúc](#segment-membership)

### <a name="customerprofile"></a>CustomerProfile

Bảng này chứa hồ sơ khách hàng hợp nhất từ Customer Insights. Lược đồ cho hồ sơ khách hàng hợp nhất phụ thuộc vào các thực thể và thuộc tính được sử dụng trong quá trình hợp nhất dữ liệu. Sơ đồ hồ sơ khách hàng thường chứa một tập hợp con các thuộc tính từ [Định nghĩa Common Data Model CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile).

### <a name="alternatekey"></a>AlternateKey

Bảng AlternateKey chứa khóa của các thực thể đã tham gia vào quá trình hợp nhất.

|Cột  |Loại  |Mô tả  |
|---------|---------|---------|
|DataSourceName    |Chuỗi         | Tên nguồn dữ liệu. Ví dụ: `datasource5`        |
|EntityName        | String        | Tên của pháp nhân trong Thông tin chi tiết về khách hàng. Ví dụ: `contact1`        |
|AlternateValue    |String         |ID thay thế được ánh xạ tới ID khách hàng. Ví dụ: `cntid_1078`         |
|KeyRing           | Văn bản nhiều dòng        | Giá trị JSON  </br> Ví dụ: [{"dataSourceName":" datasource5 ",</br>"entityName":" contact1",</br>"preferredKey":" cntid_1078",</br>"keys":[" cntid_1078"]}]       |
|CustomerId         | Chuỗi        | ID của hồ sơ khách hàng hợp nhất.         |
|AlternateKeyId     | GUID         |  GUID tất định của AlternateKey dựa trên msdynci_identifier       |
|msdynci_identifier |   Chuỗi      |   `DataSourceName|EntityName|AlternateValue`  </br> Ví dụ: `testdatasource|contact1|cntid_1078`    |

### <a name="unifiedactivity"></a>UnifiedActivity

Bảng này chứa các hoạt động của người dùng có trong Customer Insights.

| Cột            | Loại        | Mô tả                                                                              |
|-------------------|-------------|------------------------------------------------------------------------------------------|
| CustomerId        | Chuỗi      | ID hồ sơ khách hàng                                                                      |
| ActivityId        | Chuỗi      | ID nội bộ của hoạt động khách hàng (khóa chính)                                       |
| SourceEntityName  | Chuỗi      | Tên của thực thể nguồn                                                                |
| SourceActivityId  | Chuỗi      | Khóa chính từ thực thể nguồn                                                       |
| ActivityType      | Chuỗi      | Loại hoạt động ngữ nghĩa hoặc tên của hoạt động tùy chỉnh                                        |
| ActivityTimeStamp | DATETIME    | Dấu thời gian hoạt động                                                                      |
| Title             | Chuỗi      | Tiêu đề hoặc tên của hoạt động                                                               |
| Description       | Chuỗi      | Nội dung mô tả hoạt động                                                                     |
| URL               | Chuỗi      | Liên kết đến một URL bên ngoài cụ thể cho hoạt động                                         |
| SemanticData      | Chuỗi JSON | Bao gồm danh sách các cặp khóa-giá trị cho các trường ánh xạ ngữ nghĩa cụ thể cho loại hoạt động |
| RangeIndex        | Chuỗi      | Dấu thời gian Unix dùng để sắp xếp dòng thời gian hoạt động và truy vấn phạm vi hiệu quả |
| mydynci_unifiedactivityid   | GUID | ID nội bộ của hoạt động khách hàng (ActivityId) |

### <a name="customermeasure"></a>CustomerMeasure

Bảng này chứa dữ liệu đầu ra của các giá trị đo dựa trên thuộc tính khách hàng.

| Cột             | Loại             | Mô tả                 |
|--------------------|------------------|-----------------------------|
| CustomerId         | Chuỗi           | ID hồ sơ khách hàng        |
| Measures           | Chuỗi JSON      | Bao gồm danh sách các cặp khóa-giá trị cho tên giá trị đo và các giá trị cho khách hàng nhất định | 
| msdynci_identifier | Chuỗi           | `Customer_Measure|CustomerId` |
| msdynci_customermeasureid | GUID      | ID hồ sơ khách hàng |


### <a name="enrichment"></a>Enrichment

Bảng này chứa kết quả đầu ra của quá trình tăng cường.

| Cột               | Loại             |  Mô tả                                          |
|----------------------|------------------|------------------------------------------------------|
| CustomerId           | Chuỗi           | ID hồ sơ khách hàng                                 |
| EnrichmentProvider   | Chuỗi           | Tên nhà cung cấp cho quá trình tăng cường                                  |
| EnrichmentType       | Chuỗi           | Loại tăng cường                                      |
| Values               | Chuỗi JSON      | Danh sách các thuộc tính do quá trình tăng cường tạo ra |
| msdynci_enrichmentid | GUID             | GUID tất định được tạo từ msdynci_identifier |
| msdynci_identifier   | Chuỗi           | `EnrichmentProvider|EnrichmentType|CustomerId`         |

### <a name="prediction"></a>Prediction

Bảng này chứa kết quả đầu ra của lượt dự đoán mô hình.

| Cột               | Loại        | Mô tả                                          |
|----------------------|-------------|------------------------------------------------------|
| CustomerId           | Chuỗi      | ID hồ sơ khách hàng                                  |
| ModelProvider        | Chuỗi      | Tên nhà cung cấp mô hình                                      |
| Model                | Chuỗi      | Tên mô hình                                                |
| Values               | Chuỗi JSON | Danh sách các thuộc tính do mô hình tạo ra |
| msdynci_predictionid | GUID        | GUID tất định được tạo từ msdynci_identifier | 
| msdynci_identifier   | String      |  `Model|ModelProvider|CustomerId`                      |

### <a name="segment-membership"></a>Thành viên phân khúc

Bảng này chứa thông tin thành viên phân khúc của hồ sơ khách hàng.

| Column        | Loại | Description                        |
|--------------------|--------------|-----------------------------|
| CustomerId        | String       | ID hồ sơ khách hàng        |
| SegmentProvider      | String       | Ứng dụng xuất bản các phân đoạn.      |
| SegmentMembershipType | String       | Loại khách hàng hồ sơ thành viên phân khúc này. Hỗ trợ nhiều loại như Khách hàng, Liên hệ hoặc Tài khoản. Mặc định: Khách hàng  |
| Phân khúc       | Chuỗi JSON  | Danh sách các phân đoạn duy nhất mà hồ sơ khách hàng là thành viên của      |
| msdynci_identifier  | String   | Định danh duy nhất của bản ghi thành viên phân khúc. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | GUID      | GUID xác định được tạo từ`msdynci_identifier`          |

<!--
## FAQ: Update existing environments to use Microsoft Dataverse

Between mid-May 2022 and June 13, 2022, administrators can update the environment settings with a Dataverse environment that Customer Insights can use. On June 13, 2022, your environment will be updated automatically and we'll create a Dataverse environment on your tenant for you.

1. My environment uses my own Azure Data Lake Storage account. Do I still need to update?

   If there's already a Dataverse environment configured in your environment, the update isn't required. If no Dataverse is environment configured, the **Update now** button will create a Dataverse environment and update from the Customer Insights database to a Dataverse database.

1. Will we get extra Dataverse capacity, or will the update use my existing Dataverse capacity?

   - If there's already a Dataverse environment configured in your Customer Insights environment, or connected with other Dynamics 365 or Power Apps applications, the capacity remains unchanged.
   - If the Dataverse environment is new, it will add new storage and database capacity. The capacity added varies per environment and entitlements. You'll get 3 GB for trial and sandbox environment. Production environments get 15 GB.

1. I proceeded with the update and it seems like nothing happened. Is the update complete?

   If the notification in Customer Insights doesn't show anymore, the update is complete. You can check the status of the update by reviewing your environment settings.

1. Why do I still see the banner after completing the update steps?

   It can happen due to an upgrade or refresh failure. Contact support.

1. I received a "Failed to provision Dataverse environment" error after starting the update. What happened?

   It can happen due to an upgrade or refresh failure. Contact support.
   Common causes:
    - Insufficient capacity. There's no more capacity to create more environments. For more information, see [Manage capacity action](/power-platform/admin/capacity-storage#actions-to-take-for-a-storage-capacity-deficit).
    - Region mismatch between tenant region and Customer Insights environment region in the Australia and India regions.
    - Insufficient privileges to provision Dataverse. The users starting the update needs a Dynamics 365 admin role.
    - -->
