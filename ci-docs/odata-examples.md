---
title: Các ví dụ về OData cho Dynamics 365 Customer Insights API
description: Các ví dụ thường được sử dụng về Giao thức dữ liệu mở (OData) để truy vấn API thông tin chi tiết về khách hàng để xem xét dữ liệu.
ms.date: 05/10/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 007278e1330e1a8e64d524ded8496acaf83b874c
ms.sourcegitcommit: a50c5e70d2baf4db41a349162fd1b1f84c3e03b6
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 05/11/2022
ms.locfileid: "8740079"
---
# <a name="odata-query-examples"></a>Ví dụ về truy vấn OData

Giao thức Dữ liệu Mở (OData) là một giao thức truy cập dữ liệu được xây dựng trên các giao thức cốt lõi như HTTP. Nó sử dụng các phương pháp luận thường được chấp nhận như REST cho web. Có nhiều loại thư viện và công cụ khác nhau có thể được sử dụng để sử dụng các dịch vụ OData.

Bài viết này liệt kê một số truy vấn mẫu được yêu cầu thường xuyên để giúp bạn xây dựng các triển khai của riêng mình dựa trên [API thông tin chi tiết về khách hàng](apis.md).

Bạn phải sửa đổi các mẫu truy vấn để làm cho chúng hoạt động trên các môi trường đích: 

- {serviceRoot}:`https://api.ci.ai.dynamics.com/v1/instances/{instanceId}` ở đâu{instanceId} là HƯỚNG DẪN của môi trường Thông tin chi tiết về khách hàng mà bạn muốn truy vấn. Các [Hoạt động ListAllInstances](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) cho phép bạn tìm thấy{InstanceId} bạn có quyền truy cập vào.
- {CID}: HƯỚNG DẪN của một hồ sơ khách hàng thống nhất. Ví dụ: `ce759201f786d590bf2134bff576c369`.
- {AlternateKey}: Định danh của khóa chính của hồ sơ khách hàng trong nguồn dữ liệu. Ví dụ: `CNTID_1002`
- {DSname}: Chuỗi với tên thực thể của nguồn dữ liệu được nhập vào Thông tin chi tiết về khách hàng. Ví dụ: `Website_contacts`.
- {SegmentName}: Chuỗi với tên thực thể đầu ra của một phân khúc trong Thông tin chi tiết về khách hàng. Ví dụ: `Male_under_40`.

## <a name="customer"></a>Quý khách hàng

Bảng sau đây chứa một tập hợp các truy vấn mẫu cho *Khách hàng* thực thể.


|Loại truy vấn |Ví dụ:  | Lưu ý  |
|---------|---------|---------|
|ID khách hàng duy nhất     | `{serviceRoot}/Customer?$filter=CustomerId eq '{CID}'`          |  |
|Khóa thay thế    | `{serviceRoot}/Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} eq '{AlternateKey}' `         |  Các khóa thay thế vẫn tồn tại trong thực thể khách hàng hợp nhất       |
|Chọn   | `{serviceRoot}/Customer?$select=CustomerId,FullName&$filter=customerid eq '1'`        |         |
|Vào    | `{serviceRoot}/Customer?$filter=CustomerId in ('{CID1}',’{CID2}’)`        |         |
|Khóa thay thế + Trong   | `Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} in ('{AlternateKey}','{AlternateKey}')`         |         |
|Tìm kiếm  | `{serviceRoot}/Customer?$top=10&$skip=0&$search="string"`        |   Trả về 10 kết quả hàng đầu cho một chuỗi tìm kiếm      |
|Thành viên phân khúc  | `{serviceRoot}/Customer?select=*&$filter=IsMemberOfSegment('{SegmentName}')&$top=10  `     | Trả về số hàng đặt trước từ thực thể phân đoạn.      |

## <a name="unified-activity"></a>Hoạt động hợp nhất

Bảng sau đây chứa một tập hợp các truy vấn mẫu cho *UnifiedActivity* thực thể.

|Loại truy vấn |Ví dụ:  | Lưu ý  |
|---------|---------|---------|
|Hoạt động của CID     | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}'`          | Liệt kê các hoạt động của một hồ sơ khách hàng cụ thể |
|Khung thời gian hoạt động    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityTime gt 2017-01-01T00:00:00.000Z and ActivityTime lt 2020-01-01T00:00:00.000Z`     |  Các hoạt động của hồ sơ khách hàng trong một khung thời gian       |
|Loại hoạt động    |   `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityType eq '{ActivityName}'`        |         |
|Hoạt động theo tên hiển thị     | `{serviceRoot}/UnifiedActivity$filter=CustomerId eq ‘{CID}’ and ActivityTypeDisplay eq ‘{ActivityDisplayName}’ `        | |
|Phân loại hoạt động    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq ‘{CID}’ & $orderby=ActivityTime asc`     |  Sắp xếp các hoạt động tăng dần hoặc giảm dần       |
|Hoạt động được mở rộng từ thành viên phân khúc  |   `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId eq '{CID}'`     |         |

## <a name="other-examples"></a>Ví dụ khác

Bảng sau chứa một tập hợp các truy vấn mẫu cho các thực thể khác.

|Loại truy vấn |Ví dụ:  | Lưu ý  |
|---------|---------|---------|
|Các biện pháp của CID    | `{serviceRoot}/Customer_Measure?$filter=CustomerId eq '{CID}'`          |  |
|Các thương hiệu phong phú của CID    | `{serviceRoot}/BrandShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`  |       |
|Lợi ích phong phú của CID    |   `{serviceRoot}/InterestShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`       |         |
|Trong mệnh đề + Mở rộng     | `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId in ('{CID}', '{CID}')`         | |
