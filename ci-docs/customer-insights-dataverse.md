---
title: Dữ liệu Customer Insights trong Microsoft Dataverse
description: Sử dụng các thực thể Customer Insights dưới dạng bảng trong Microsoft Dataverse.
ms.date: 04/05/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 85995cbd7f797810bfb6ecdc8a24d56542f0b5a9
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643993"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Làm việc với dữ liệu Customer Insights trong Microsoft Dataverse

Customer Insights cung cấp tùy chọn để hiển thị các thực thể đầu ra trong [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Sự tích hợp này cho phép chia sẻ dữ liệu dễ dàng và phát triển tùy chỉnh thông qua cách tiếp cận mã thấp / không mã. Các [thực thể đầu ra](#output-entities) có sẵn dưới dạng bảng trong một Dataverse môi trường. Bạn có thể sử dụng dữ liệu cho bất kỳ ứng dụng nào khác dựa trên Dataverse những cái bàn. Các bảng này cho phép các tình huống như quy trình làm việc tự động thông qua Power Automate hoặc xây dựng ứng dụng với Power Apps. Việc triển khai hiện tại chủ yếu hỗ trợ tra cứu trong đó dữ liệu từ các thực thể Thông tin khách hàng có sẵn có thể được tìm nạp cho một ID khách hàng nhất định.

## <a name="attach-a-dataverse-environment-to-customer-insights"></a>Đính kèm môi trường Dataverse vào Customer Insights

**Tổ chức hiện tại**

Quản trị viên có thể định cấu hình Thông tin chi tiết về khách hàng để [sử dụng một hiện có Dataverse môi trường](create-environment.md) khi họ tạo môi trường Thông tin chi tiết về khách hàng. Bằng cách cung cấp URL cho Dataverse môi trường, nó gắn liền với môi trường Thông tin chi tiết về khách hàng mới của họ. Thông tin chi tiết về khách hàng và Dataverse môi trường phải được lưu trữ trong cùng một khu vực. 

Nếu bạn không muốn sử dụng Dataverse môi trường, hệ thống tạo ra một môi trường mới cho dữ liệu Thông tin chi tiết về khách hàng trong đối tượng thuê của bạn. 

> [!NOTE]
> Nếu tổ chức của bạn đã sử dụng Dataverse đối với người thuê của họ, điều quan trọng cần nhớ là [Dataverse tạo môi trường do quản trị viên kiểm soát](/power-platform/admin/control-environment-creation) . Ví dụ: nếu bạn đang thiết lập môi trường Thông tin chi tiết về khách hàng mới với tài khoản tổ chức của mình và quản trị viên đã vô hiệu hóa việc tạo Dataverse môi trường dùng thử cho tất cả mọi người ngoại trừ quản trị viên, bạn không thể tạo môi trường dùng thử mới.
> 
> Các môi trường dùng thử Dataverse được tạo trong Customer Insights có 3 GB dung lượng lưu trữ. Dung lượng lưu trữ này sẽ không được tính vào dung lượng tổng thể mà đối tượng thuê được hưởng. Các gói đăng ký trả phí được hưởng quyền lợi Dataverse là 15 GB cho cơ sở dữ liệu và 20 GB để lưu trữ tệp.

**Tổ chức mới**

Nếu bạn tạo một tổ chức mới khi thiết lập Thông tin chi tiết về khách hàng, hệ thống sẽ tự động tạo một tổ chức mới Dataverse môi trường trong tổ chức của bạn cho bạn.

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

Bảng này chứa hồ sơ khách hàng hợp nhất từ Customer Insights. Sơ đồ của hồ sơ khách hàng hợp nhất phụ thuộc vào các thực thể và thuộc tính dùng trong quá trình hợp nhất. Sơ đồ hồ sơ khách hàng thường chứa một tập hợp con các thuộc tính từ [Định nghĩa Common Data Model CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile).

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
