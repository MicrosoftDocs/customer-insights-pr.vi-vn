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
ms.openlocfilehash: 9bf8f03b785fb3035e3fc979a3304d4e98fd8d28
ms.sourcegitcommit: 1946d7af0bd2ca216885bec3c5c95009996d9a28
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 02/25/2022
ms.locfileid: "8350433"
---
# <a name="service-limits-in-customer-insights-capabilities"></a>Giới hạn dịch vụ trong các tính năng của Customer Insights

Bài viết này mô tả các giới hạn tích hợp đối với dịch vụ Customer Insights, được thiết kế để bảo đảm độ tin cậy và ổn định của dịch vụ. Mọi yêu cầu thay đổi có thể được đưa ra thông qua [Diễn đàn ý tưởng](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="audience-insights"></a>Thông tin chi tiết về đối tượng

| Diện tích  | Giới hạn  | Ghi chú |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Phân đoạn, thước đo và dự đoán | 300  | Tổng số [phân đoạn](audience-insights/segments.md),[đo](audience-insights/measures.md), và [phỏng đoán](audience-insights/predictions.md) kết hợp không được vượt quá 300.  |
| Quan hệ | 20 cấp độ chuyên sâu về các mối quan hệ trong các đường dẫn thực thể. | Khi tạo [phân đoạn](audience-insights/segments.md) hoặc [đo lường](audience-insights/measures.md) sử dụng giao diện trình tạo, đường dẫn thực thể có thể có tối đa 20 bước quan hệ giữa thực thể bắt đầu và thực thể đích.  |

<!--
## Engagement insights

### Workspace and event quotas

Engagement insights is a highly scalable application that can support millions of events per second. During public preview, events have a volume threshold. There's also a limit to the number of workspaces in an organization.

### Engagement insights limits

- Maximum event volume per workspace  = 100 events per second

- Maximum number of workspaces per organization = 100

When events exceed the threshold, it can lead to loss of data in reports based on those events. You can [contact support](https://go.microsoft.com/fwlink/?linkid=2145734) to request a volume increase before you exceed limits. We'll work with you to determine your need for a volume increase and support your request.
-->

[!INCLUDE[footer-include](includes/footer-banner.md)]
