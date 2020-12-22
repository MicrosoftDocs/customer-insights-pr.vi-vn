---
title: Trình kết nối Power Automate | Microsoft Docs
description: Tạo dòng trong Microsoft Power Automate từ Dynamics 365 Customer Insights.
ms.date: 08/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: ffe92414365b0b777691a4a2d585100e4fbea591
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407289"
---
# <a name="power-automate-connector-preview"></a>Trình kết nối Power Automate (xem trước)

Kích hoạt các sự kiện cụ thể xảy ra tự động khi dữ liệu của bạn thay đổi và quản lý các dòng phức tạp hơn trực tiếp trong [Power Automate](https://flow.microsoft.com/).

## <a name="power-automate-triggers"></a>Trình kích hoạt Power Automate

Bạn có thể sử dụng nhiều trình kích hoạt cho phép bạn tạo các quy trình để tự động hóa tác vụ lặp lại, chẳng hạn như thông báo hoặc hành động nâng cao hơn. 

- Kích hoạt khi làm mới nguồn dữ liệu không thành công. 
- Kích hoạt khi làm mới nguồn dữ liệu thành công.
- Kích hoạt khi ngưỡng vượt quá trên một phân khúc. Kích hoạt bị giới hạn để vượt quá ngưỡng.
- Kích hoạt khi ngưỡng vượt quá trên một giá trị đo kinh doanh. Kích hoạt bị giới hạn vượt quá ngưỡng.
- Kích hoạt khi hoàn thành quá trình làm mới đầy đủ (nguồn dữ liệu, phân đoạn, đo lường...).
- Kích hoạt khi hoàn tất quá trình làm mới quy trình hợp nhất (ánh xạ, khớp, hợp nhất).

[Đặt cấu hình trình kích hoạt trong Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).

## <a name="power-automate-actions"></a>Hành động Power Automate
Trình kết nối Power Automate cung cấp các hành động khác ngoài trình kích hoạt có sẵn. Để biết thêm thông tin, xem [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).

## <a name="create-a-power-automate-flow-in-audience-insights"></a>Tạo quy trình Power Automate trong thông tin chi tiết về đối tượng

1. Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Quản trị viên** > **Hệ thống**.

1. Trên trang **Hệ thống**, hãy chọn tab **Trạng thái**.

1. Trong phần **Nguồn dữ liệu**, hãy chọn **Dòng** rồi chọn **Tạo một dòng** từ danh sách thả xuống.
   > [!div class="mx-imgBorder"]
   > ![Trình kết nối Power Automate hiển thị hành động Tạo dòng](media/power-automate-connector-create-flow.png "Trình kết nối Power Automate hiển thị hành động Tạo dòng")

1. Trong Power Automate, hãy chọn một trong các trình kích hoạt có sẵn để tạo dòng ưa thích của bạn. Nếu bạn đang tạo dòng đầu tiên của mình, bạn cần xác thực bằng trình kết nối Power Automate trước tiên.
