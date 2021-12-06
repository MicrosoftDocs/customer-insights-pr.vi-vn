---
title: Dữ liệu Thông tin chi tiết về khách hàng trong Microsoft Dataverse
description: Sử dụng các thực thể Thông tin chi tiết về khách hàng dưới dạng bảng trong Microsoft Dataverse.
ms.date: 11/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 6f74559b34a95ed976a4e353c2dbabe59e1a8839
ms.sourcegitcommit: 9558ff772ee6c944fcb8db4bfc8cda13b38a1bff
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 11/29/2021
ms.locfileid: "7866960"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Làm việc với dữ liệu Thông tin chi tiết về khách hàng trong Microsoft Dataverse

Thông tin chi tiết về khách hàng cung cấp tùy chọn để cung cấp các thực thể đầu ra trong [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro.md). Phần tích hợp này giúp chia sẻ dữ liệu dễ dàng và phát triển tùy chỉnh thông qua cách tiếp cận ít dùng mã/không dùng mã. Các thực thể đầu ra sẽ có sẵn dưới dạng bảng trong Dataverse. Các bảng này cho phép các tình huống như [quy trình công việc tự động thông qua Power Automate](/power-automate/getting-started),[ứng dụng hướng mô hình](/powerapps/maker/model-driven-apps/) và [ứng dụng canvas](/powerapps/maker/canvas-apps/) thông qua Power Apps. Bạn có thể sử dụng dữ liệu cho bất kỳ ứng dụng nào khác dựa trên bảng Dataverse. Quy trình triển khai hiện tại chủ yếu hỗ trợ các lượt tra cứu trong đó dữ liệu từ các thực thể thông tin chuyên sâu về đối tượng có sẵn có thể được tìm nạp cho một ID khách hàng nhất định.

## <a name="attach-a-dataverse-environment-to-customer-insights"></a>Đính kèm môi trường Dataverse vào Thông tin chi tiết về khách hàng

**Các tổ chức có môi trường Dataverse hiện có**

Các tổ chức đã sử dụng Dataverse có thể [sử dụng một trong các môi trường Dataverse hiện có của họ](create-environment.md) khi quản trị viên thiết lập thông tin chi tiết về đối tượng. Bằng cách cung cấp URL cho môi trường Dataverse, URL sẽ gắn với môi trường thông tin chi tiết về đối tượng mới của họ. Để đảm bảo hiệu suất tốt nhất có thể, môi trường Customer Insights và Dataverse phải được lưu trữ trong cùng một khu vực.

**Tổ chức mới**

Nếu bạn tạo một tổ chức mới khi thiết lập Thông tin chi tiết về khách hàng, bạn sẽ tự động nhận được môi trường Dataverse mới.

> [!NOTE]
> Nếu tổ chức của bạn đã sử dụng Dataverse trong đối tượng thuê của họ, thì điều quan trọng cần nhớ là [Dataverse tạo môi trường do quản trị viên kiểm soát](/power-platform/admin/control-environment-creation.md) . Ví dụ: nếu bạn đang thiết lập môi trường thông tin chi tiết về đối tượng mới bằng tài khoản tổ chức của mình và quản trị viên đã tắt tính năng tạo môi trường dùng thử Dataverse cho mọi người ngoại trừ quản trị viên, bạn không thể tạo môi trường dùng thử mới.
> 
> Môi trường dùng thử Dataverse được tạo trong Thông tin chi tiết về khách hàng có 3 GB dung lượng lưu trữ, sẽ không được tính vào dung lượng tổng thể mà đối tượng thuê. Đăng ký trả phí nhận được quyền Dataverse 15 GB cho cơ sở dữ liệu và 20 GB cho bộ nhớ tệp.

## <a name="output-entities"></a>Các thực thể đầu ra

Một số thực thể đầu ra từ thông tin chi tiết về đối tượng có sẵn dưới dạng bảng trong Dataverse. Các phần dưới đây mô tả sơ đồ dự kiến của các bảng này.

- [CustomerProfile](#customerprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Enrichment](#enrichment)
- [Prediction](#prediction)
- [Thành viên phân khúc](#segment-membership)


### <a name="customerprofile"></a>CustomerProfile

Bảng này chứa hồ sơ khách hàng hợp nhất từ Customer Insights. Sơ đồ của hồ sơ khách hàng hợp nhất phụ thuộc vào các thực thể và thuộc tính dùng trong quá trình hợp nhất. Sơ đồ hồ sơ khách hàng thường chứa một tập hợp con các thuộc tính từ [Định nghĩa Common Data Model CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile).

### <a name="alternatekey"></a>AlternateKey

Bảng AlternateKey chứa khóa của các thực thể đã tham gia vào quá trình hợp nhất.

|Cột  |Loại  |Mô tả  |
|---------|---------|---------|
|DataSourceName    |Chuỗi         | Tên nguồn dữ liệu. Ví dụ: `datasource5`        |
|EntityName        | Chuỗi        | Tên của thực thể trong thông tin chuyên sâu về đối tượng. Ví dụ: `contact1`        |
|AlternateValue    |Chuỗi         |ID thay thế được ánh xạ tới ID khách hàng. Ví dụ: `cntid_1078`         |
|KeyRing           | Văn bản nhiều dòng        | Giá trị JSON  </br> Mẫu: [{"dataSourceName": "datasource5",</br>"entityName":" contact1",</br>"preferredKey":" cntid_1078",</br>"khóa": ["cntid_1078"]}]       |
|CustomerId         | String        | ID của hồ sơ khách hàng hợp nhất.         |
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
| SegmentProvider      | String       | Ứng dụng xuất bản các phân đoạn. Mặc định: Thông tin chi tiết về đối tượng         |
| SegmentMembershipType | String       | Loại khách hàng hồ sơ thành viên phân khúc này. Hỗ trợ nhiều loại như Khách hàng, Liên hệ hoặc Tài khoản. Mặc định: Khách hàng  |
| Phân khúc       | Chuỗi JSON  | Danh sách các phân đoạn duy nhất mà hồ sơ khách hàng là thành viên của      |
| msdynci_identifier  | String   | Định danh duy nhất của bản ghi thành viên phân khúc. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | GUID      | GUID xác định được tạo từ`msdynci_identifier`          |
