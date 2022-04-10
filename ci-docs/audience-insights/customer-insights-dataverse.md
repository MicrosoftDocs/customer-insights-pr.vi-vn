---
title: Dữ liệu Customer Insights trong Microsoft Dataverse
description: Sử dụng các thực thể Customer Insights dưới dạng bảng trong Microsoft Dataverse.
ms.date: 11/25/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 9f730f5856221592cddf34b714beeaca24c52130
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 02/25/2022
ms.locfileid: "8355455"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Làm việc với dữ liệu Customer Insights trong Microsoft Dataverse

Customer Insights cung cấp tùy chọn để hiển thị các thực thể đầu ra trong [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro.md). Phần tích hợp này giúp chia sẻ dữ liệu dễ dàng và phát triển tùy chỉnh thông qua cách tiếp cận ít dùng mã/không dùng mã. Các thực thể đầu ra sẽ có sẵn dưới dạng bảng trong Dataverse. Các bảng này hỗ trợ các kịch bản như [quy trình làm việc tự động thông qua Power Automate](/power-automate/getting-started), [ứng dụng dựa trên mô hình](/powerapps/maker/model-driven-apps/) và [ứng dụng canvas](/powerapps/maker/canvas-apps/) thông qua Power Apps. Bạn có thể sử dụng dữ liệu cho bất kỳ ứng dụng nào khác dựa trên bảng Dataverse. Quy trình triển khai hiện tại chủ yếu hỗ trợ các lượt tra cứu trong đó dữ liệu từ các thực thể thông tin chuyên sâu về đối tượng có sẵn có thể được tìm nạp cho một ID khách hàng nhất định.

## <a name="attach-a-dataverse-environment-to-customer-insights"></a>Đính kèm môi trường Dataverse vào Customer Insights

**Tổ chức đã có môi trường Dataverse**

Các tổ chức đã sử dụng Dataverse có thể [dùng một trong các môi trường Dataverse hiện có của họ](create-environment.md) khi quản trị viên thiết lập thông tin chuyên sâu về đối tượng. Bằng cách cung cấp URL cho môi trường Dataverse, môi trường đó sẽ đính kèm vào môi trường thông tin chuyên sâu về đối tượng mới của họ. Để đảm bảo hiệu suất tốt nhất có thể, môi trường Customer Insights và Dataverse phải được lưu trữ trong cùng một khu vực.

**Tổ chức mới**

Nếu tạo một tổ chức mới khi thiết lập Customer Insights, bạn sẽ tự động nhận được môi trường Dataverse mới.

> [!NOTE]
> Nếu các tổ chức của bạn đã sử dụng Dataverse trong đối tượng thuê của họ, bạn cần lưu ý rằng [Việc tạo môi trường Dataverse sẽ do quản trị viên kiểm soát](/power-platform/admin/control-environment-creation.md). Ví dụ: nếu bạn đang thiết lập một môi trường thông tin chuyên sâu về đối tượng mới bằng tài khoản tổ chức của mình và quản trị viên đã tắt chức năng tạo môi trường dùng thử Dataverse cho tất cả mọi người ngoại trừ quản trị viên, thì bạn không thể tạo môi trường dùng thử mới.
> 
> Các môi trường dùng thử Dataverse được tạo trong Customer Insights có 3 GB dung lượng lưu trữ. Dung lượng lưu trữ này sẽ không được tính vào dung lượng tổng thể mà đối tượng thuê được hưởng. Các gói đăng ký trả phí được hưởng quyền lợi Dataverse là 15 GB cho cơ sở dữ liệu và 20 GB để lưu trữ tệp.

## <a name="output-entities"></a>Các thực thể đầu ra

Một số thực thể đầu ra của thông tin chuyên sâu về đối tượng có sẵn dưới dạng bảng trong Dataverse. Các phần dưới đây mô tả sơ đồ dự kiến của các bảng này.

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
| SegmentProvider      | String       | Ứng dụng xuất bản các phân đoạn. Mặc định: Thông tin chi tiết về đối tượng         |
| SegmentMembershipType | String       | Loại khách hàng hồ sơ thành viên phân khúc này. Hỗ trợ nhiều loại như Khách hàng, Liên hệ hoặc Tài khoản. Mặc định: Khách hàng  |
| Phân khúc       | Chuỗi JSON  | Danh sách các phân đoạn duy nhất mà hồ sơ khách hàng là thành viên của      |
| msdynci_identifier  | String   | Định danh duy nhất của bản ghi thành viên phân khúc. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | GUID      | GUID xác định được tạo từ`msdynci_identifier`          |
