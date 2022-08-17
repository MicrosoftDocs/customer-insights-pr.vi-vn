---
title: Xuất nhật ký chẩn đoán (xem trước)
description: Tìm hiểu cách gửi nhật ký tới Microsoft Azure Màn hình.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: article
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 60b039173fd938482c782c7394420d4951c222a7
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245951"
---
# <a name="export-diagnostic-logs-preview"></a>Xuất nhật ký chẩn đoán (xem trước)

Chuyển tiếp nhật ký từ Thông tin chi tiết về khách hàng bằng Azure Monitor. Nhật ký tài nguyên Azure Monitor cho phép bạn theo dõi và gửi nhật ký đến [Kho lưu trữ Azure](https://azure.microsoft.com/services/storage/),[Phân tích nhật ký Azure](/azure/azure-monitor/logs/log-analytics-overview) hoặc truyền chúng tới [Trung tâm sự kiện Azure](https://azure.microsoft.com/services/event-hubs/).

Thông tin chi tiết về khách hàng gửi các nhật ký sự kiện sau:

- **Sự kiện kiểm tra**
  - **APIEvent** - cho phép theo dõi thay đổi thông qua Dynamics 365 Customer Insights Giao diện người dùng.
- **Sự kiện hoạt động**
  - **WorkflowEvent** - cho phép bạn thiết lập [nguồn dữ liệu](data-sources.md),[thống nhất](data-unification.md),[làm giàu](enrichment-hub.md), và [xuất khẩu](export-destinations.md) dữ liệu vào các hệ thống khác. Các bước này có thể được thực hiện riêng lẻ (ví dụ: kích hoạt một lần xuất). Chúng cũng có thể chạy theo dàn (ví dụ: làm mới dữ liệu từ các nguồn dữ liệu kích hoạt quá trình hợp nhất, quá trình này sẽ bổ sung và xuất dữ liệu sang một hệ thống khác). Để biết thêm thông tin, hãy xem [Lược đồ WorkflowEvent](#workflow-event-schema).
  - **APIEvent** - gửi tất cả các lệnh gọi API của phiên bản khách hàng tới Dynamics 365 Customer Insights. Để biết thêm thông tin, hãy xem [Lược đồ APIEvent](#api-event-schema).

## <a name="set-up-the-diagnostic-settings"></a>Thiết lập cài đặt chẩn đoán

### <a name="prerequisites"></a>Điều kiện tiên quyết

- Một hoạt động [Đăng ký Azure](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/).
- [Người quản lý](permissions.md#admin) quyền trong Thông tin chi tiết về khách hàng.
- [Người đóng góp và vai trò Quản trị viên quyền truy cập của người dùng](/azure/role-based-access-control/role-assignments-portal) trên tài nguyên đích trên Azure. Tài nguyên có thể là một Azure Data Lake Storage tài khoản, Trung tâm sự kiện Azure hoặc không gian làm việc Azure Log Analytics. Quyền này là cần thiết khi định cấu hình cài đặt chẩn đoán trong Thông tin chi tiết về khách hàng, nhưng bạn có thể thay đổi quyền này sau khi thiết lập thành công.
- [Yêu cầu về điểm đến](/azure/azure-monitor/platform/diagnostic-settings#destination-requirements) cho Azure Storage, Azure Event Hub hoặc Azure Log Analytics đều được đáp ứng.
- Ít nhất **Người đọc** vai trò trên nhóm tài nguyên mà tài nguyên đó thuộc về.

### <a name="set-up-diagnostics-with-azure-monitor"></a>Thiết lập chẩn đoán với Azure Monitor

1. Trong Thông tin chi tiết về khách hàng, hãy chuyển đến **Quản trị viên** > **Hệ thống** và chọn **Chẩn đoán** chuyển hướng.

1. Lựa chọn **Thêm điểm đến**.

   :::image type="content" source="media/diagnostics-pane.png" alt-text="Kết nối chẩn đoán.":::

1. Cung cấp tên trong **Tên cho điểm đến chẩn đoán** đồng ruộng.

1. Chọn **Loại tài nguyên** (Tài khoản lưu trữ, Trung tâm sự kiện hoặc Phân tích nhật ký).

1. Chọn **Đăng ký**, **tài nguyên**, và **Nguồn** cho tài nguyên đích. Nhìn thấy [Cấu hình trên tài nguyên đích](#configuration-on-the-destination-resource) cho phép và thông tin nhật ký.

1. Xem lại [quyền riêng tư và tuân thủ dữ liệu](connections.md#data-privacy-and-compliance) và chọn **tôi đồng ý**.

1. Lựa chọn **Kết nối với hệ thống** để kết nối với tài nguyên đích. Các bản ghi bắt đầu xuất hiện ở đích sau 15 phút, nếu API đang được sử dụng và tạo ra các sự kiện.

## <a name="configuration-on-the-destination-resource"></a>Cấu hình trên tài nguyên đích

Dựa trên lựa chọn của bạn về loại tài nguyên, các thay đổi sau sẽ tự động xảy ra:

### <a name="storage-account"></a>Tài khoản lưu trữ

Chính của dịch vụ Customer Insights nhận được **Người đóng góp tài khoản lưu trữ** quyền trên tài nguyên đã chọn và tạo hai vùng chứa trong không gian tên đã chọn:

- `insight-logs-audit` chứa đựng **sự kiện kiểm toán**
- `insight-logs-operational` chứa đựng **sự kiện hoạt động**

### <a name="event-hub"></a>Hub sự kiện

Dịch vụ Customer Insights chính nhận được **Chủ sở hữu dữ liệu của Trung tâm sự kiện Azure** quyền trên tài nguyên và tạo hai Trung tâm sự kiện trong không gian tên đã chọn:

- `insight-logs-audit` chứa đựng **sự kiện kiểm toán**
- `insight-logs-operational` chứa đựng **sự kiện hoạt động**

### <a name="log-analytics"></a>Ghi nhật ký phân tích

Dịch vụ Customer Insights chính nhận được **Ghi nhật ký Người đóng góp Analytics** quyền trên tài nguyên. Các bản ghi có sẵn dưới **Nhật ký** > **Những cái bàn** > **Quản lý nhật ký** trên không gian làm việc Log Analytics đã chọn. Mở rộng **Quản lý nhật ký** giải pháp và xác định vị trí`CIEventsAudit` và`CIEventsOperational` những cái bàn.

- `CIEventsAudit` chứa đựng **sự kiện kiểm toán**
- `CIEventsOperational` chứa đựng **sự kiện hoạt động**

Bên dưới **Truy vấn** cửa sổ, mở rộng **Kiểm toán** giải pháp và xác định các truy vấn mẫu được cung cấp bằng cách tìm kiếm `CIEvents`.

## <a name="remove-a-diagnostics-destination"></a>Xóa điểm đến chẩn đoán

1. Đi đến **Quản trị viên** > **Hệ thống** và chọn **Chẩn đoán** chuyển hướng.

1. Chọn đích chẩn đoán trong danh sách.

   > [!TIP]
   > Xóa đích sẽ dừng chuyển tiếp nhật ký, nhưng không xóa tài nguyên trên đăng ký Azure. Để xóa tài nguyên trong Azure, hãy chọn liên kết trong **Hành động** để mở cổng Azure cho tài nguyên đã chọn và xóa nó ở đó. Sau đó, xóa đích chẩn đoán.

1. Bên trong **Hành động** chọn cột **Xóa bỏ** biểu tượng.

1. Xác nhận việc xóa để xóa điểm đến và dừng chuyển tiếp nhật ký.

## <a name="log-categories-and-event-schemas"></a>Ghi danh mục và lược đồ sự kiện

Hiện nay [Sự kiện API](apis.md) và các sự kiện quy trình làm việc được hỗ trợ và áp dụng các danh mục và lược đồ sau.
Lược đồ nhật ký theo sau [Lược đồ chung Azure Monitor](/azure/azure-monitor/platform/resource-logs-schema#top-level-common-schema).

### <a name="categories"></a>Thể loại

Thông tin chi tiết về khách hàng cung cấp hai danh mục:

- **Kiểm tra sự kiện** :[Sự kiện API](#api-event-schema) để theo dõi các thay đổi cấu hình trên dịch vụ. `POST|PUT|DELETE|PATCH` hoạt động đi vào danh mục này.
- **Sự kiện hoạt động** :[Sự kiện API](#api-event-schema) hoặc [sự kiện quy trình làm việc](#workflow-event-schema) được tạo ra trong khi sử dụng dịch vụ.  Ví dụ,`GET` các yêu cầu hoặc các sự kiện thực thi của một dòng công việc.

## <a name="event-schemas"></a>Lược đồ sự kiện

Sự kiện API và sự kiện quy trình làm việc có cấu trúc chung, nhưng có một vài điểm khác biệt. Để biết thêm thông tin, hãy xem [Lược đồ sự kiện API](#api-event-schema) hoặc [lược đồ sự kiện quy trình làm việc](#workflow-event-schema).

### <a name="api-event-schema"></a>Lược đồ sự kiện API

| Trường             | Loại dữ liệu  | Bắt buộc / Tùy chọn | Description       | Ví dụ:        |
| ----------------- | --------- | ----------------- | --------------------- | ------------------------ |
| `time`            | Dấu thời gian | Bắt buộc          | Dấu thời gian của sự kiện (UTC)       | `2020-09-08T09:48:14.8050869Z`         |
| `resourceId`      | String    | Bắt buộc          | ResourceId của phiên bản phát ra sự kiện         | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX`  |
| `operationName`   | String    | Bắt buộc          | Tên của hoạt động được đại diện bởi sự kiện này.                                                                                                                | `Workflows.GetWorkFlowStatusAsync`                                                                                                                                       |
| `category`        | String    | Bắt buộc          | Ghi danh mục của sự kiện. Một trong hai`Operational` hoặc `Audit`. Tất cả các yêu cầu HTTP POST / PUT / PATCH / DELETE đều được gắn thẻ`Audit`, mọi thứ khác với`Operational` | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resultType`      | String    | Bắt buộc          | Tình trạng của sự kiện. `Success`,`ClientError`,`Failure`                                                                                                        |                                                                                                                                                                          |
| `resultSignature` | String    | Không bắt buộc          | Trạng thái kết quả của sự kiện. Nếu thao tác tương ứng với lệnh gọi REST API, thì đó là mã trạng thái HTTP.        | `200`             |
| `durationMs`      | Dài      | Không bắt buộc          | Thời lượng của hoạt động tính bằng mili giây.     | `133`     |
| `callerIpAddress` | String    | Không bắt buộc          | Địa chỉ IP của người gọi, nếu thao tác tương ứng với lệnh gọi API đến từ địa chỉ IP có sẵn công khai.                                                 | `144.318.99.233`         |
| `identity`        | String    | Không bắt buộc          | Đối tượng JSON mô tả danh tính của người dùng hoặc ứng dụng đã thực hiện hoạt động.       | Nhìn thấy [Xác thực](#identity-schema) tiết diện.     |  
| `properties`      | String    | Không bắt buộc          | Đối tượng JSON với nhiều thuộc tính hơn cho danh mục sự kiện cụ thể.      | Nhìn thấy [Đặc tính](#api-properties-schema) tiết diện.    |
| `level`           | String    | Bắt buộc          | Mức độ nghiêm trọng của sự kiện.    | `Informational`,`Warning`,`Error`, hoặc `Critical`.           |
| `uri`             | String    | Không bắt buộc          | URI yêu cầu tuyệt đối.    |               |

#### <a name="identity-schema"></a>Lược đồ nhận dạng

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
| `Authorization.RequiredRoles` | Các vai trò bắt buộc để thực hiện hoạt động. `Admin` vai trò được phép làm tất cả các hoạt động.                                                    |
| `Claims`                      | Khiếu nại về mã thông báo web JSON của người dùng hoặc ứng dụng (JWT). Thuộc tính xác nhận quyền sở hữu khác nhau tùy theo tổ chức và Azure Active Directory cấu hình. |

#### <a name="api-properties-schema"></a>Lược đồ thuộc tính API

[Sự kiện API](apis.md) có các thuộc tính sau.

| Trường                        | Description                                                                                                            |
| ---------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| `properties.eventType`       | Luôn luôn`ApiEvent`, đánh dấu sự kiện nhật ký là sự kiện API.                                                                 |
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
| AttributeMeasures | [Phân đoạn và biện pháp](segments.md)      |
| EntityMeasures    | [Phân đoạn và biện pháp](segments.md)      |
| Measures          | [Phân đoạn và biện pháp](segments.md)      |
| Phân đoạn      | [Phân đoạn và biện pháp](segments.md)      |
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
| `resourceId`    | String    | Bắt buộc          | ResourceId của cá thể đã phát ra sự kiện.                                                                                                            | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX` |
| `operationName` | String    | Bắt buộc          | Tên của hoạt động được đại diện bởi sự kiện này. `{OperationType}.[WorkFlow|Task][Started|Completed]`. Nhìn thấy [Các loại hoạt động](#operation-types) để tham khảo. | `Segmentation.WorkflowStarted`,<br> `Segmentation.TaskStarted`, <br> `Segmentation.TaskCompleted`, <br> `Segmentation.WorkflowCompleted`                                 |
| `category`      | String    | Bắt buộc          | Ghi danh mục của sự kiện. Luôn luôn`Operational` cho các sự kiện Dòng công việc                                                                                           | `Operational`                                                                                                                                                            |
| `resultType`    | String    | Bắt buộc          | Tình trạng của sự kiện. `Running`,`Skipped`,`Successful`,`Failure`                                                                                            |                                                                                                                                                                          |
| `durationMs`    | Dài      | Không bắt buộc          | Thời lượng của hoạt động tính bằng mili giây.                                                                                                                    | `133`                                                                                                                                                                    |
| `properties`    | String    | Không bắt buộc          | Đối tượng JSON với nhiều thuộc tính hơn cho danh mục sự kiện cụ thể.                                                                                        | Xem phần phụ [Thuộc tính quy trình làm việc](#workflow-properties-schema)                                                                                                       |
| `level`         | String    | Bắt buộc          | Mức độ nghiêm trọng của sự kiện.                                                                                                                                  | `Informational`, `Warning`, hoặc `Error`                                                                                                                                   |

#### <a name="workflow-properties-schema"></a>Lược đồ thuộc tính quy trình làm việc

Các sự kiện quy trình làm việc có các thuộc tính sau.

| Trường              | Workflow | Tác vụ | Description            |
| ------------------------------- | -------- | ---- | ----------- |
| `properties.eventType`                       | Có      | Có  | Luôn luôn`WorkflowEvent`, đánh dấu sự kiện là sự kiện quy trình làm việc.                                                                                                                                                                                                |
| `properties.workflowJobId`                   | Có      | Có  | Định danh của dòng công việc chạy. Tất cả các sự kiện dòng công việc và tác vụ trong quá trình thực thi dòng công việc đều giống nhau `workflowJobId`.                                                                                                                                   |
| `properties.operationType`                   | Có      | Có  | Định danh của hoạt động, xem [Các loại hoạt động](#operation-types).                                                                                                                                                                               |
| `properties.tasksCount`                      | Có      | No   | Chỉ quy trình làm việc. Số tác vụ mà quy trình làm việc kích hoạt.                                                                                                                                                                                                       |
| `properties.submittedBy`                     | Có      | No   | Tùy chọn. Chỉ sự kiện quy trình làm việc. Các Azure Active Directory [objectId của người dùng](/azure/marketplace/find-tenant-object-id#find-user-object-id) ai đã kích hoạt quy trình làm việc, hãy xem thêm `properties.workflowSubmissionKind`.                                   |
| `properties.workflowType`                    | Có      | No   | `full` hoặc`incremental` Làm tươi.                                                                                                                                                                                                                            |
| `properties.workflowSubmissionKind`          | Có      | No   | `OnDemand` hoặc `Scheduled`.                                                                                                                                                                                                                                  |
| `properties.workflowStatus`                  | Có      | No   | `Running` hoặc `Successful`.                                                                                                                                                                                                                                 |
| `properties.startTimestamp`                  | Có      | Có  | Dấu thời gian UTC`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.endTimestamp`                    | Có      | Có  | Dấu thời gian UTC`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.submittedTimestamp`              | Có      | Có  | Dấu thời gian UTC`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.instanceId`                      | Có      | Có  | Thấu hiểu khách hàng`instanceId`                                                                                                                                                                                                                              |  
| `properties.identifier`                      | No       | Có  | - Đối với OperationType =`Export`, số nhận dạng là hướng dẫn của cấu hình xuất. <br> - Đối với OperationType =`Enrichment`, đó là phương châm làm giàu <br> - Đối với OperationType`Measures` và`Segmentation`, định danh là tên thực thể. |
| `properties.friendlyName`                    | No       | Có  | Tên thân thiện với người dùng của quá trình xuất hoặc thực thể được xử lý.                                                                                                                                                                                           |
| `properties.error`                           | No       | Có  | Tùy chọn. Thông báo lỗi với nhiều chi tiết hơn.                                                                                                                                                                                                                  |
| `properties.additionalInfo.Kind`             | No       | Có  | Tùy chọn. Đối với OperationType`Export` chỉ có. Xác định loại xuất. Để biết thêm thông tin, hãy xem [tổng quan về các điểm đến xuất khẩu](export-destinations.md).                                                                                          |
| `properties.additionalInfo.AffectedEntities` | No       | Có  | Tùy chọn. Đối với OperationType`Export` chỉ có. Chứa danh sách các thực thể được định cấu hình trong quá trình xuất.                                                                                                                                                            |
| `properties.additionalInfo.MessageCode`      | No       | Có  | Tùy chọn. Đối với OperationType`Export` chỉ có. Thông báo chi tiết cho việc xuất.                                                                                                                                                                                 |
| `properties.additionalInfo.entityCount`      | No       | Có  | Tùy chọn. Đối với OperationType`Segmentation` chỉ có. Cho biết tổng số thành viên mà phân khúc có.                                                                                                                                                    |

[!INCLUDE [footer-include](includes/footer-banner.md)]
