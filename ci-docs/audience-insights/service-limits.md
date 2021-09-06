---
title: Giới hạn dịch vụ
description: Hiểu các giới hạn và hạn chế.
ms.date: 07/08/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 2966f2ede1ddbe0245471771365cbf5b593be608764aa10ed28d962c52bb8067
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034890"
---
# <a name="service-limits-in-dynamics-365-customer-insights-audience-insights-capability"></a>Giới hạn dịch vụ trong khả năng thông tin chi tiết về đối tượng Dynamics 365 Customer Insights

Bài viết này mô tả các giới hạn tích hợp đối với dịch vụ Customer Insights, được thiết kế để bảo đảm độ tin cậy và ổn định của dịch vụ. Mọi yêu cầu thay đổi có thể được đưa ra thông qua [Diễn đàn ý tưởng](https://go.microsoft.com/fwlink/?linkid=2074172). 
 
| Diện tích  | Giới hạn  | Ghi chú |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Phân khúc và phép đo | 100 phân khúc hoặc giá trị đo. | Tổng số [phân khúc](segments.md) và [giá trị đo](measures.md) hiện hoạt được kết hợp không được vượt quá 100.  |
| Mối quan hệ | 20 cấp độ chuyên sâu về các mối quan hệ trong các đường dẫn thực thể. | Khi tạo [phân đoạn](segments.md) hoặc [đo lường](measures.md) sử dụng giao diện trình tạo, đường dẫn thực thể có thể có tối đa 20 bước quan hệ giữa thực thể bắt đầu và thực thể đích.  |


[!INCLUDE[footer-include](../includes/footer-banner.md)]