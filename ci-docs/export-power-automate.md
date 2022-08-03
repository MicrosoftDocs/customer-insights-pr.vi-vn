---
title: Power Automate kết nối (xem trước) | Tài liệu Microsoft
description: Tạo quy trình trong Microsoft Power Automate từ Dynamics 365 Customer Insights.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f87bd6db7143294a264813f6c5c7d7963f303628
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196144"
---
# <a name="power-automate-connector-preview"></a>Trình kết nối Power Automate (xem trước)

Kích hoạt các sự kiện cụ thể xảy ra tự động khi dữ liệu của bạn thay đổi và quản lý các dòng phức tạp hơn trực tiếp trong [Microsoft Power Automate](https://flow.microsoft.com/).

## <a name="known-limitations"></a>Các hạn chế đã biết

- Tối đa 100 cuộc gọi mỗi 60 giây. Sử dụng [$ bỏ qua tham số](/connectors/customerinsights/#get-items-from-an-entity) để gọi điểm cuối API nhiều lần.

## <a name="power-automate-triggers"></a>Trình kích hoạt Power Automate

Sử dụng trình kích hoạt để tạo luồng đám mây và tự động hóa các tác vụ lặp lại, chẳng hạn như thông báo hoặc các hành động nâng cao hơn. Sử dụng trình kích hoạt khi:

- Làm mới nguồn dữ liệu không thành công.
- Làm mới nguồn dữ liệu thành công.
- Một ngưỡng được vượt qua trên một đoạn. Kích hoạt bị giới hạn để vượt quá ngưỡng.
- Một ngưỡng được vượt qua trên một biện pháp kinh doanh. Chỉ hỗ trợ giá trị đo công việc không có kích thước. Kích hoạt bị giới hạn để vượt quá ngưỡng.
- Quá trình làm mới đầy đủ theo lịch đã hoàn tất. Trình kích hoạt này không hoạt động đối với các lần làm mới được bắt đầu theo cách thủ công.
- Quá trình hợp nhất được làm mới đã hoàn tất.

[Định cấu hình trình kích hoạt trong Power Automate.](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a>Hành động Power Automate

Trình kết nối Power Automate cung cấp các hành động khác ngoài trình kích hoạt có sẵn. Để biết thêm thông tin, xem [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>Tạo một Dòng Power Automate

1. Đi đến **Quản trị viên** > **Kết nối**.

1. Trên lát **Power Automate**, chọn **Thiết lập**.

1. Trình kết nối Customer Insights (xem trước) trong Power Automate mở ra. **Đăng nhập** vào Power Automate.

1. Chọn một trong các trình kích hoạt có sẵn và thêm các bước khác vào quy trình mới của bạn. Để biết thêm thông tin, hãy xem [Tạo luồng đám mây trong Power Automate](/power-automate/get-started-logic-flow).

Ví dụ về cách sử dụng các quy trình: 
- Đăng tin nhắn lên một kênh Microsoft Teams nếu làm mới nguồn dữ liệu không thành công. 
- Gửi email cho chủ sở hữu dữ liệu khi vượt qua ngưỡng trên một phân khúc.

[!INCLUDE [footer-include](includes/footer-banner.md)]
