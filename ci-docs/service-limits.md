---
title: Giới hạn dịch vụ trong Dynamics 365 Customer Insights
description: Hiểu các giới hạn và hạn chế.
ms.date: 09/03/2021
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: e2e7fc3033c25646693831d4c4c800d84ae6d6da
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 04/27/2022
ms.locfileid: "8641788"
---
# <a name="service-limits-in-customer-insights"></a>Giới hạn dịch vụ trong Thông tin chi tiết về khách hàng

Bài viết này mô tả các giới hạn tích hợp đối với dịch vụ Customer Insights, được thiết kế để bảo đảm độ tin cậy và ổn định của dịch vụ. Mọi yêu cầu thay đổi có thể được đưa ra thông qua [Diễn đàn ý tưởng](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="customer-insights"></a>Customer Insights

| Diện tích  | Giới hạn  | Ghi chú |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Phân đoạn, thước đo và dự đoán | 300  | Tổng số [phân đoạn](segments.md),[đo](measures.md), và [phỏng đoán](predictions.md) kết hợp không được vượt quá 300.  |
| Quan hệ | 20 cấp độ chuyên sâu về các mối quan hệ trong các đường dẫn thực thể. | Khi tạo [phân đoạn](segments.md) hoặc [đo lường](measures.md) sử dụng giao diện trình tạo, đường dẫn thực thể có thể có tối đa 20 bước quan hệ giữa thực thể bắt đầu và thực thể đích.  |


[!INCLUDE [footer-include](includes/footer-banner.md)]
