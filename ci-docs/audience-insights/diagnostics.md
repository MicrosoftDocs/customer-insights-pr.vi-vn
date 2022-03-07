---
title: Kiểm toán Dynamics 365 Customer Insights với Azure Monitor
description: Tìm hiểu cách gửi nhật ký tới Microsoft Azure Màn hình.
ms.date: 12/14/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: article
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 2e0801c2b6af591e48a7df485a8523903c07617c
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 02/25/2022
ms.locfileid: "8354434"
---
# <a name="log-forwarding-in-dynamics-365-customer-insights-with-azure-monitor-preview"></a>Đăng nhập chuyển tiếp Dynamics 365 Customer Insights với Azure Monitor (Xem trước)

Dynamics 365 Customer Insights cung cấp tích hợp trực tiếp với Azure Monitor. Nhật ký tài nguyên Azure Monitor cho phép bạn theo dõi và gửi nhật ký tới [Kho lưu trữ Azure](https://azure.microsoft.com/services/storage/),[Phân tích nhật ký Azure](/azure/azure-monitor/logs/log-analytics-overview) hoặc truyền chúng tới [Trung tâm sự kiện Azure](https://azure.microsoft.com/services/event-hubs/).

Thông tin chi tiết về khách hàng sẽ gửi các nhật ký sự kiện sau:

- **Sự kiện kiểm tra**
  - **APIEvent** - cho phép theo dõi thay đổi được thực hiện thông qua Dynamics 365 Customer Insights Giao diện người dùng.
- **Sự kiện hoạt động**
  - **WorkflowEvent** - Quy trình làm việc cho phép một người thiết lập [Nguồn dữ liệu](data-sources.md),[thống nhất](data-unification.md) và [làm giàu](enrichment-hub.md) và cuối cùng [xuất khẩu](export-destinations.md) dữ liệu vào các hệ thống khác. Tất cả các bước đó có thể được thực hiện riêng lẻ (ví dụ: kích hoạt một lần xuất duy nhất) hoặc được tổ chức (ví dụ: làm mới dữ liệu từ các nguồn dữ liệu sẽ kích hoạt quá trình hợp nhất sẽ kéo thêm các bước bổ sung và sau khi hoàn thành xuất dữ liệu vào một hệ thống khác). Để biết thêm chi tiết, hãy xem [Lược đồ WorkflowEvent](#workflow-event-schema).
  - **APIEvent** - tất cả các lệnh gọi API đến phiên bản khách hàng để Dynamics 365 Customer Insights. Để biết thêm chi tiết, hãy xem [Lược đồ APIEvent](#api-event-schema).

## <a name="set-up-the-diagnostic-settings"></a>Thiết lập cài đặt chẩn đoán

### <a name="prerequisites"></a>Điều kiện tiên quyết

Để định cấu hình chẩn đoán trong Thông tin chi tiết về khách hàng, bạn phải đáp ứng các điều kiện tiên quyết sau:

- Bạn có một hoạt động [Đăng ký Azure](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/).
- Bạn có [Người quản lý](permissions.md#administrator) quyền trong Thông tin chi tiết về khách hàng.
- Bạn có **Người đóng góp** và **Quản trị viên Quyền truy cập Người dùng** vai trò của tài nguyên đích trên Azure. Tài nguyên có thể là tài khoản Azure Storage, Trung tâm sự kiện Azure hoặc không gian làm việc Azure Log Analytics. Để biết thêm thông tin, hãy xem [Thêm hoặc xóa các nhiệm vụ vai trò Azure bằng cách sử dụng cổng Azure](/azure/role-based-access-control/role-assignments-portal).
- [Yêu cầu về điểm đến](/azure/azure-monitor/platform/diagnostic-settings#destination-requirements) cho Azure Storage, Azure Event Hub hoặc Azure Log Analytics đã đáp ứng.
- Bạn có ít nhất **Người đọc** vai trò trên nhóm tài nguyên mà tài nguyên đó thuộc về.

### <a name="set-up-diagnostics-with-azure-monitor"></a>Thiết lập chẩn đoán với Azure Monitor

1. Trong Thông tin chi tiết về khách hàng, hãy chọn **Hệ thống** > **Chẩn đoán** để xem các đích chẩn đoán được định cấu hình trong trường hợp này.

1. Lựa chọn **Thêm điểm đến**.

   > [!div class="mx-imgBorder"]
   > ![Kết nối chẩn đoán](media/diagnostics-pane.png "Kết nối chẩn đoán")

1. Cung cấp tên trong **Tên cho điểm đến chẩn đoán** đồng ruộng.

1. Chọn **Người thuê nhà** đăng ký Azure với tài nguyên đích và chọn **đăng nhập**.

1. Chọn **Loại tài nguyên** (Tài khoản lưu trữ, Trung tâm sự kiện hoặc phân tích nhật ký).

1. Chọn **Đăng ký** cho tài nguyên đích.

1. Chọn **Nhóm tài nguyên** cho tài nguyên đích.

1. Chọn **Nguồn**.

1. Xác nhận **Quyền riêng tư và tuân thủ dữ liệu** tuyên bố.

1. Lựa chọn **Kết nối với hệ thống** để kết nối với tài nguyên đích. Các bản ghi bắt đầu xuất hiện ở đích sau 15 phút, nếu API đang được sử dụng và tạo sự kiện.

### <a name="remove-a-destination"></a>Xóa điểm đến

1. Đi đến **Hệ thống** > **Chẩn đoán**.

1. Chọn đích chẩn đoán trong danh sách.

1. Bên trong **Hành động** chọn cột **Xóa bỏ** biểu tượng.

1. Xác nhận việc xóa để dừng chuyển tiếp nhật ký. Tài nguyên trên đăng ký Azure sẽ không bị xóa. Bạn có thể chọn liên kết trong **Hành động** để mở cổng Azure cho tài nguyên đã chọn và xóa nó ở đó.

## <a name="log-categories-and-event-schemas"></a>Ghi danh mục và lược đồ sự kiện

Hiện tại [Sự kiện API](apis.md) và các sự kiện quy trình làm việc được hỗ trợ và áp dụng các danh mục và lược đồ sau.
Lược đồ nhật ký theo sau [Lược đồ chung Azure Monitor](/azure/azure-monitor/platform/resource-logs-schema#top-level-common-schema).

### <a name="categories"></a>Thể loại

Thông tin chi tiết về khách hàng cung cấp hai danh mục:

- **Kiểm tra sự kiện** :[Sự kiện API](#api-event-schema) để theo dõi các thay đổi cấu hình trên dịch vụ. `POST|PUT|DELETE|PATCH` hoạt động đi vào danh mục này.
- **Sự kiện hoạt động** :[Sự kiện API](#api-event-schema) hoặc [sự kiện quy trình làm việc](#workflow-event-schema) được tạo ra trong khi sử dụng dịch vụ.  Ví dụ,`GET` các yêu cầu hoặc các sự kiện thực thi của một quy trình làm việc.

## <a name="configuration-on-the-destination-resource"></a>Cấu hình trên tài nguyên đích

Dựa trên lựa chọn của bạn về loại tài nguyên, các bước sau sẽ tự động áp dụng:

### <a name="storage-account"></a>Tài khoản lưu trữ

Dịch vụ Customer Insights chính nhận được **Người đóng góp tài khoản lưu trữ** quyền trên tài nguyên đã chọn và tạo hai vùng chứa trong không gian tên đã chọn:

- `insight-logs-audit` chứa đựng **sự kiện kiểm toán**
- `insight-logs-operational` chứa đựng **sự kiện hoạt động**

### <a name="event-hub"></a>Hub sự kiện

Dịch vụ Customer Insights chính nhận được **Chủ sở hữu dữ liệu của trung tâm sự kiện Azure** quyền trên tài nguyên và sẽ tạo hai Trung tâm sự kiện trong không gian tên đã chọn:

- `insight-logs-audit` chứa đựng **sự kiện kiểm toán**
- `insight-logs-operational` chứa đựng **sự kiện hoạt động**

### <a name="log-analytics"></a>Ghi nhật ký phân tích

Dịch vụ Customer Insights chính nhận được **Ghi nhật ký Người đóng góp Analytics** quyền trên tài nguyên. Các bản ghi sẽ có sẵn dưới **Nhật ký** > **Những cái bàn** > **Quản lý nhật ký** trên không gian làm việc Log Analytics đã chọn. Mở rộng **Quản lý nhật ký** giải pháp và xác định vị trí`CIEventsAudit` và`CIEventsOperational` những cái bàn.

- `CIEventsAudit` chứa đựng **sự kiện kiểm toán**
- `CIEventsOperational` chứa đựng **sự kiện hoạt động**

Bên dưới **Truy vấn** cửa sổ, mở rộng **Kiểm toán** giải pháp và xác định vị trí các truy vấn mẫu được cung cấp bằng cách tìm kiếm `CIEvents`.

## <a name="event-schemas"></a>Lược đồ sự kiện

Các sự kiện API và sự kiện quy trình làm việc có cấu trúc chung và chi tiết chúng khác nhau ở điểm nào, hãy xem [Lược đồ sự kiện API](#api-event-schema) hoặc [giản đồ sự kiện quy trình làm việc](#workflow-event-schema).

### <a name="api-event-schema"></a>Lược đồ sự kiện API

| Trường             | Loại dữ liệu  | Bắt buộc / Tùy chọn | Description       | Ví dụ:        |
| ----------------- | --------- | ----------------- | --------------------- | ------------------------ |
| `time`            | Dấu thời gian | Bắt buộc          | Dấu thời gian của sự kiện (UTC)       | `2020-09-08T09:48:14.8050869Z`         |
| `resourceId`      | String    | Bắt buộc          | ResourceId của phiên bản phát ra sự kiện         | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX`  |
| `operationName`   | String    | Bắt buộc          | Tên của hoạt động được đại diện bởi sự kiện này.                                                                                                                | `Workflows.GetWorkFlowStatusAsync`                                                                                                                                       |
| `category`        | String    | Bắt buộc          | Ghi danh mục của sự kiện. Hoặc`Operational` hoặc `Audit`. Tất cả các yêu cầu HTTP POST / PUT / PATCH / DELETE đều được gắn thẻ`Audit`, mọi thứ khác với`Operational` | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resultType`      | String    | Bắt buộc          | Tình trạng của sự kiện. `Success`,`ClientError`,`Failure`                                                                                                        |                                                                                                                                                                          |
| `resultSignature` | String    | Không bắt buộc          | Trạng thái kết quả của sự kiện. Nếu thao tác tương ứng với lệnh gọi REST API, thì đó là mã trạng thái HTTP.        | `200`             |
| `durationMs`      | Dài      | Không bắt buộc          | Thời lượng của hoạt động tính bằng mili giây.     | `133`     |
| `callerIpAddress` | String    | Không bắt buộc          | Địa chỉ IP của người gọi, nếu thao tác tương ứng với lệnh gọi API đến từ địa chỉ IP có sẵn công khai.                                                 | `144.318.99.233`         |
| `identity`        | String    | Không bắt buộc          | Đối tượng JSON mô tả danh tính của người dùng hoặc ứng dụng đã thực hiện hoạt động.       | Xem [Xác thực](#identity-schema) tiết diện.     |  |
| `properties`      | String    | Không bắt buộc          | Đối tượng JSON với nhiều thuộc tính hơn cho danh mục sự kiện cụ thể.      | Xem [Tính chất](#api-properties-schema) tiết diện.    |
| `level`           | String    | Bắt buộc          | Mức độ nghiêm trọng của sự kiện.    | `Informational`,`Warning`,`Error`, hoặc `Critical`.           |
| `uri`             | String    | Không bắt buộc          | URI yêu cầu tuyệt đối.    |               |

#### <a name="identity-schema"></a>Lược đồ danh tính

Các`identity` Đối tượng JSON có cấu trúc sau

```json
{
  "Authorization" : {
    "UserRole": "Admin",
    "RequiredRoles": [
      "Contributor",
      "Viewer"
      ]
    },
  "Claims" {
    "claimNameX" : "claimValueX",
    "claimNameY" : "claimValueY"
   }
}  
```

| Trường                         | Description                                                                                                                          |
| ----------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| `Authorization.UserRole`      | Đã chỉ định vai trò cho người dùng hoặc ứng dụng. Để biết thêm thông tin, hãy xem [Quyền Người dùng](permissions.md).                                     |
| `Authorization.RequiredRoles` | Các vai trò cần thiết để thực hiện hoạt động. `Admin` vai trò được phép làm tất cả các hoạt động.                                                    |
| `Claims`                      | Khiếu nại về mã thông báo web JSON của người dùng hoặc ứng dụng (JWT). Các thuộc tính xác nhận quyền sở hữu khác nhau tùy theo tổ chức và Azure Active Directory cấu hình. |

#### <a name="api-properties-schema"></a>Lược đồ thuộc tính API

[Sự kiện API](apis.md) có các thuộc tính sau.

| Trường                        | Description                                                                                                            |
| ---------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| `properties.eventType`       | Luôn`ApiEvent`, đánh dấu sự kiện nhật ký là sự kiện API.                                                                 |
| `properties.userAgent`       | Tác nhân trình duyệt gửi yêu cầu hoặc `unknown`.                                                                        |
| `properties.method`          | Phương thức HTTP:`GET/POST/PUT/PATCH/HEAD`.                                                                                |
| `properties.path`            | Đường dẫn tương đối của yêu cầu.                                                                                          |
| `properties.origin`          | URI cho biết nơi tìm nạp đến từ hoặc `unknown`.                                                                  |
| `properties.operationStatus` | `Success` cho mã Trạng thái HTTP <400 <br> `ClientError` cho mã Trạng thái HTTP <500 <br> `Error` cho Trạng thái HTTP> = 500 |
| `properties.tenantId`        | ID tổ chức                                                                                                        |
| `properties.tenantName`      | Tên của tổ chức.                                                                                              |
| `properties.callerObjectId`  | Azure Active Directory ObjectId của người gọi.                                                                         |
| `properties.instanceId`      | Thấu hiểu khách hàng`instanceId`                                                                                         |

### <a name="workflow-event-schema"></a>Lược đồ sự kiện quy trình làm việc

Quy trình làm việc bao gồm nhiều bước. [Nhập nguồn dữ liệu](data-sources.md),[thống nhất](data-unification.md),[làm giàu](enrichment-hub.md), và [xuất khẩu](export-destinations.md) dữ liệu. Tất cả các bước đó có thể chạy riêng lẻ hoặc được tổ chức với các quy trình sau. 

#### <a name="operation-types"></a>Các loại hoạt động

| OperationType     | Nhóm                                     |
| ----------------- | ----------------------------------------- |
| Nuốt phải         | [Nguồn dữ liệu](data-sources.md)           |
| Chuẩn bị dữ liệu   | [Nguồn dữ liệu](data-sources.md)           |
| Bản đồ               | [Hợp nhất dữ liệu](data-unification.md)   |
| Kết quả khớp             | [Hợp nhất dữ liệu](data-unification.md)   |
| Hợp nhất             | [Hợp nhất dữ liệu](data-unification.md)   |
| ProfileStore      | [Hồ sơ khách hàng](customer-profiles.md) |
| Tìm kiếm            | [Hồ sơ khách hàng](customer-profiles.md) |
| Hoạt động          | [Hoạt động](activities.md)                  |
| AttributeMeasures | [Phân đoạn và Biện pháp](segments.md)      |
| EntityMeasures    | [Phân đoạn và Biện pháp](segments.md)      |
| Measures          | [Phân đoạn và Biện pháp](segments.md)      |
| Phân đoạn      | [Phân đoạn và Biện pháp](segments.md)      |
| Enrichment        | [Enrichment](enrichment-hub.md)                                          |
| Thông tin      | [Dự đoán](predictions-overview.md)                                          |
| AiBuilder         | [Dự đoán](predictions-overview.md)                                          |
| Thông tin chuyên sâu          | [Dự đoán](predictions-overview.md)                                          |
| Export            | [Nội dung xuất](export-destinations.md)                                          |
| ModelManagement   | [Dự đoán](custom-models.md)                                           |
| Mối quan hệ      | [Hợp nhất dữ liệu](relationships.md)                                           |

#### <a name="field-description"></a>Mô tả lĩnh vực

| Trường           | Loại dữ liệu  | Bắt buộc / Tùy chọn | Description                                                                                                                                                   | Ví dụ:                                                                                                                                                                  |
| --------------- | --------- | ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `time`          | Dấu thời gian | Bắt buộc          | Dấu thời gian của sự kiện (UTC).                                                                                                                                 | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resourceId`    | String    | Bắt buộc          | ResourceId của phiên bản phát ra sự kiện.                                                                                                            | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX` |
| `operationName` | String    | Bắt buộc          | Tên của hoạt động được đại diện bởi sự kiện này. `{OperationType}.[WorkFlow|Task][Started|Completed]`. Xem [Các loại hoạt động](#operation-types) để tham khảo. | `Segmentation.WorkflowStarted`,<br> `Segmentation.TaskStarted`, <br> `Segmentation.TaskCompleted`, <br> `Segmentation.WorkflowCompleted`                                 |
| `category`      | String    | Bắt buộc          | Ghi danh mục của sự kiện. Luôn`Operational` cho các sự kiện Quy trình làm việc                                                                                           | `Operational`                                                                                                                                                            | 
| `resultType`    | String    | Bắt buộc          | Tình trạng của sự kiện. `Running`,`Skipped`,`Successful`,`Failure`                                                                                            |                                                                                                                                                                          |
| `durationMs`    | Dài      | Không bắt buộc          | Thời lượng của hoạt động tính bằng mili giây.                                                                                                                    | `133`                                                                                                                                                                    |
| `properties`    | String    | Không bắt buộc          | Đối tượng JSON với nhiều thuộc tính hơn cho danh mục sự kiện cụ thể.                                                                                        | Xem phần phụ [Thuộc tính quy trình làm việc](#workflow-properties-schema)                                                                                                       |
| `level`         | String    | Bắt buộc          | Mức độ nghiêm trọng của sự kiện.                                                                                                                                  | `Informational`, `Warning`, hoặc `Error`                                                                                                                                   |
|                 |

#### <a name="workflow-properties-schema"></a>Lược đồ thuộc tính quy trình làm việc

Các sự kiện quy trình làm việc có các thuộc tính sau.

| Trường              | Workflow | Tác vụ | Description            |
| ------------------------------- | -------- | ---- | ----------- |
| `properties.eventType`                       | Có      | Có  | Luôn`WorkflowEvent`, đánh dấu sự kiện là sự kiện quy trình làm việc.                                                                                                                                                                                                |
| `properties.workflowJobId`                   | Có      | Có  | Định danh của dòng công việc chạy. Tất cả các sự kiện công việc và quy trình công việc trong quá trình thực thi quy trình công việc đều giống nhau `workflowJobId`.                                                                                                                                   |
| `properties.operationType`                   | Có      | Có  | Số nhận dạng của hoạt động, xem [Loại hoạt động]. (# Kiểu hoạt động)                                                                                                                                                                                       |
| `properties.tasksCount`                      | Có      | No   | Chỉ quy trình làm việc. Số tác vụ mà quy trình làm việc kích hoạt.                                                                                                                                                                                                       |
| `properties.submittedBy`                     | Có      | No   | Tùy chọn. Chỉ sự kiện quy trình làm việc. Các Azure Active Directory [objectId của người dùng](/azure/marketplace/find-tenant-object-id#find-user-object-id) ai đã kích hoạt quy trình làm việc, hãy xem thêm `properties.workflowSubmissionKind`.                                   |
| `properties.workflowType`                    | Có      | No   | `full` hoặc`incremental` Làm tươi.                                                                                                                                                                                                                            |
| `properties.workflowSubmissionKind`          | Có      | No   | `OnDemand` hoặc `Scheduled`.                                                                                                                                                                                                                                  |
| `properties.workflowStatus`                  | Có      | No   | `Running` hoặc `Successful`.                                                                                                                                                                                                                                 |
| `properties.startTimestamp`                  | Có      | Có  | Dấu thời gian UTC`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.endTimestamp`                    | Có      | Có  | Dấu thời gian UTC`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.submittedTimestamp`              | Có      | Có  | Dấu thời gian UTC`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.instanceId`                      | Có      | Có  | Thấu hiểu khách hàng`instanceId`                                                                                                                                                                                                                              |  |
| `properties.identifier`                      | No       | Có  | - Đối với OperationType =`Export`, số nhận dạng là hướng dẫn của cấu hình xuất. <br> - Đối với OperationType =`Enrichment`, đó là phương châm làm giàu <br> - Đối với OperationType`Measures` và`Segmentation`, định danh là tên thực thể. |
| `properties.friendlyName`                    | No       | Có  | Tên thân thiện với người dùng của quá trình xuất hoặc đối tượng được xử lý.                                                                                                                                                                                           |
| `properties.error`                           | No       | Có  | Tùy chọn. Thông báo lỗi với nhiều chi tiết hơn.                                                                                                                                                                                                                  |
| `properties.additionalInfo.Kind`             | No       | Có  | Tùy chọn. Đối với OperationType`Export` chỉ một. Xác định loại xuất. Để biết thêm thông tin, hãy xem [tổng quan về các điểm đến xuất khẩu](export-destinations.md).                                                                                          |
| `properties.additionalInfo.AffectedEntities` | No       | Có  | Tùy chọn. Đối với OperationType`Export` chỉ một. Chứa danh sách các thực thể đã định cấu hình trong quá trình xuất.                                                                                                                                                            |
| `properties.additionalInfo.MessageCode`      | No       | Có  | Tùy chọn. Đối với OperationType`Export` chỉ một. Thông báo chi tiết cho việc xuất.                                                                                                                                                                                 |
| `properties.additionalInfo.entityCount`      | No       | Có  | Tùy chọn. Đối với OperationType`Segmentation` chỉ một. Cho biết tổng số thành viên mà phân khúc có.                                                                                                                                                    |
