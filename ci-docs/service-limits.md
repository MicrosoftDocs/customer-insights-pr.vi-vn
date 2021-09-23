---
title: Giới hạn dịch vụ trong Dynamics 365 Customer Insights
description: Hiểu các giới hạn và hạn chế.
ms.date: 09/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: eba7871faf304d5945191b5b9bc215243b4f8a05
ms.sourcegitcommit: 5704002484cdf85ebbcf4e7e4fd12470fd8e259f
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 09/08/2021
ms.locfileid: "7483721"
---
# <a name="service-limits-in-customer-insights-capabilities"></a>Giới hạn dịch vụ trong các tính năng của Customer Insights

Bài viết này mô tả các giới hạn tích hợp đối với dịch vụ Customer Insights, được thiết kế để bảo đảm độ tin cậy và ổn định của dịch vụ. Mọi yêu cầu thay đổi có thể được đưa ra thông qua [Diễn đàn ý tưởng](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="audience-insights"></a>Thông tin chi tiết về đối tượng

### <a name="service-limits-in-dynamics-365-customer-insights-audience-insights-capability"></a>Giới hạn dịch vụ trong khả năng thông tin chi tiết về đối tượng Dynamics 365 Customer Insights

| Diện tích  | Giới hạn  | Ghi chú |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Phân khúc và giá trị đo | 100 phân khúc hoặc giá trị đo. | Tổng số [phân khúc](audience-insights/segments.md) và [giá trị đo](audience-insights/measures.md) hiện hoạt được kết hợp không được vượt quá 100.  |
| Mối quan hệ | 20 cấp độ chuyên sâu về các mối quan hệ trong các đường dẫn thực thể. | Khi tạo [phân khúc](audience-insights/segments.md) hoặc [đo lường](audience-insights/measures.md) sử dụng giao diện trình tạo, đường dẫn thực thể có thể có tối đa 20 bước quan hệ giữa thực thể bắt đầu và thực thể đích.  |


## <a name="engagement-insights"></a>Thông tin chi tiết về tương tác

### <a name="workspace-and-event-quotas"></a>Hạn mức sự kiện và không gian làm việc

Thông tin chi tiết về tương tác là một ứng dụng có khả năng mở rộng cao, có thể hỗ trợ hàng triệu sự kiện mỗi giây. Trong bản xem trước công khai, các sự kiện có ngưỡng khối lượng. Cũng có giới hạn về số lượng không gian làm việc trong một tổ chức.

### <a name="engagement-insights-limits"></a>Giới hạn thông tin chi tiết về tương tác

- Khối lượng sự kiện tối đa trên mỗi không gian làm việc = 100 sự kiện mỗi giây

- Số lượng không gian làm việc tối đa cho mỗi tổ chức = 100

Khi các sự kiện vượt quá ngưỡng, điều này có thể dẫn đến mất dữ liệu trong các báo cáo dựa trên các sự kiện đó. Bạn có thể [liên hệ với bộ phận hỗ trợ](https://go.microsoft.com/fwlink/?linkid=2145734) để yêu cầu tăng khối lượng trước khi vượt quá giới hạn. Chúng tôi sẽ hợp tác với bạn để xác định nhu cầu tăng khối lượng và hỗ trợ yêu cầu của bạn.


[!INCLUDE[footer-include](includes/footer-banner.md)]