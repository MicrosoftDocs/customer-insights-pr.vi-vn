---
title: Giới hạn dịch vụ trong Thông tin chi tiết về khách hàng
description: Hiểu các giới hạn và hạn chế trong dịch vụ SaaS Thông tin chi tiết về khách hàng.
ms.date: 08/30/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 7f38b7d9985368fc38107f1f360f0603a7fcc8e6
ms.sourcegitcommit: 3c7cdfc8bd83ca236e4777240e08a541dc955d34
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 09/07/2022
ms.locfileid: "9411811"
---
# <a name="service-limits-in-customer-insights"></a>Giới hạn dịch vụ trong Thông tin chi tiết về khách hàng

 Thông tin chi tiết về khách hàng có các giới hạn tích hợp được thiết kế để đảm bảo độ tin cậy và ổn định của dịch vụ. Mọi yêu cầu thay đổi có thể được đưa ra thông qua [Diễn đàn ý tưởng](https://go.microsoft.com/fwlink/?linkid=2074172).

## <a name="customer-insights"></a>Customer Insights

| Diện tích  | Giới hạn  | Ghi chú |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Phân đoạn, thước đo và dự đoán | 300  | Tổng số của [phân đoạn](segments.md),[đo](measures.md), và [phỏng đoán](predictions-overview.md) kết hợp không được vượt quá 300.  |
| Quan hệ | 20 cấp độ chuyên sâu về các mối quan hệ trong các đường dẫn thực thể. | Khi tạo [phân đoạn](segments.md) hoặc [đo lường](measures.md) sử dụng giao diện trình tạo, đường dẫn thực thể có thể có tối đa 20 bước quan hệ giữa thực thể bắt đầu và thực thể đích.  |

## <a name="fair-scheduling-of-jobs"></a>Lập kế hoạch công việc hợp lý

Thông tin chi tiết về khách hàng là một dịch vụ SaaS sử dụng tài nguyên Azure được chia sẻ. Khách hàng có xu hướng có khối lượng công việc với cường độ thay đổi và theo các lịch trình khác nhau. Để đảm bảo quyền truy cập hợp lý vào các tài nguyên cơ bản, chúng tôi đảm bảo các quy trình hệ thống được thực thi theo thứ tự hợp lý. Ví dụ về quy trình hệ thống là các công việc liên quan đến hợp nhất dữ liệu, cập nhật phân đoạn hoặc tính toán đo lường. Việc lập lịch trình hợp lý bảo vệ bạn khỏi phải xếp hàng đợi các nguồn lực nếu có sự gia tăng đột biến về số lượng công việc được yêu cầu. Đồng thời, Customer Insights không đảm bảo tất cả các công việc bạn xếp hàng sẽ được xử lý song song.

[!INCLUDE [footer-include](includes/footer-banner.md)]
