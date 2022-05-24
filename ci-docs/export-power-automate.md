---
title: Trình kết nối Power Automate | Microsoft Docs
description: Tạo quy trình trong Microsoft Power Automate từ Dynamics 365 Customer Insights.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d22c4c785695b23a257a89f1ffa519fdc18b443e
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741205"
---
# <a name="power-automate-connector-preview"></a>Trình kết nối Power Automate (xem trước)

Kích hoạt các sự kiện cụ thể xảy ra tự động khi dữ liệu của bạn thay đổi và quản lý các dòng phức tạp hơn trực tiếp trong [Power Automate](https://flow.microsoft.com/).

## <a name="known-limitations"></a>Các hạn chế đã biết

- Bạn có thể thực hiện tối đa 100 cuộc gọi mỗi 60 giây. Bạn có thể gọi điểm cuối API nhiều lần bằng cách sử dụng tham số $ bỏ qua. [Tìm hiểu thêm về thông số $ bỏ qua](/connectors/customerinsights/#get-items-from-an-entity).

## <a name="power-automate-triggers"></a>Trình kích hoạt Power Automate

Sử dụng trình kích hoạt để tạo luồng đám mây và tự động hóa các tác vụ lặp lại, chẳng hạn như thông báo hoặc các hành động nâng cao hơn.

- Kích hoạt khi làm mới nguồn dữ liệu không thành công.
- Kích hoạt khi làm mới nguồn dữ liệu thành công.
- Kích hoạt khi ngưỡng vượt quá trên một phân khúc. Kích hoạt bị giới hạn để vượt quá ngưỡng.
- Kích hoạt khi ngưỡng vượt quá trên một giá trị đo kinh doanh. Chỉ hỗ trợ giá trị đo công việc không có kích thước. Kích hoạt bị giới hạn để vượt quá ngưỡng.
- Kích hoạt khi hoàn thành quá trình làm mới đầy đủ (nguồn dữ liệu, phân khúc, đo lường,...).
- Kích hoạt khi quá trình làm mới hoàn tất.

[Định cấu hình trình kích hoạt trong Power Automate.](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a>Hành động Power Automate

Trình kết nối Power Automate cung cấp các hành động khác ngoài trình kích hoạt có sẵn. Để biết thêm thông tin, xem [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>Tạo một Dòng Power Automate

1. Đi tới **Quản trị viên** > **Đích xuất**.

1. Trên lát **Power Automate**, chọn **Thiết lập**.

1. Trình kết nối Customer Insights (xem trước) trong Power Automate mở ra. **Đăng nhập** vào Power Automate.

1. Chọn một trong các trình kích hoạt có sẵn và thêm các bước khác vào quy trình mới của bạn. Để biết thêm thông tin, hãy xem [Tạo luồng đám mây trong Power Automate](/power-automate/get-started-logic-flow).

Ví dụ về cách sử dụng các quy trình: 
- Đăng tin nhắn lên một kênh Microsoft Teams nếu làm mới nguồn dữ liệu không thành công. 
- Gửi email cho chủ sở hữu dữ liệu khi vượt qua ngưỡng trên một phân khúc.



[!INCLUDE [footer-include](includes/footer-banner.md)]
