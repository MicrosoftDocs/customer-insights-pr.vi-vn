---
title: Xuất dữ liệu Customer Insights sang Autopilot
description: Tìm hiểu cách định cấu hình kết nối với Autopilot.
ms.date: 12/08/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 33a8cd1ae4a77ce2248bc2805d25687c9a2c2732
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269264"
---
# <a name="connector-for-autopilot-preview"></a>Trình kết nối cho Autopilot (bản xem trước)

Xuất phân đoạn hồ sơ khách hàng hợp nhất sang Autopilot và sử dụng chúng cho các chiến dịch và tiếp thị qua email trong Autopilot. 

## <a name="prerequisites"></a>Điều kiện tiên quyết

-   Bạn có một [Tài khoản Autopilot](https://www.autopilothq.com/) và thông tin đăng nhập quản trị viên tương ứng.
-   Bạn có [các phân đoạn được định cấu hình](segments.md) trong thông tin chi tiết về đối tượng.
-   Hồ sơ khách hàng hợp nhất trong các phân đoạn đã xuất chứa các trường đại diện cho địa chỉ email.

## <a name="connect-to-autopilot"></a>Kết nối với AutoPilot

1. Đi tới **Quản trị viên** > **Đích xuất**.

1. Trong **Autopilot**, chọn **Thiết lập**.

1. Trong trường **Tên hiển thị**, hãy đặt cho đích xuất một cái tên dễ nhận biết.

   :::image type="content" source="media/export-autopilot.PNG" alt-text="Ngăn cấu hình cho kết nối Autopilot.":::

1. Nhập **Khóa API Autopilot** [Khóa API Autopilot](https://autopilot.docs.apiary.io/#).

1. Chọn **Tôi đồng ý** để xác nhận **Quyền riêng tư về dữ liệu và sự tuân thủ**.

1. Chọn **Kết nối** để khởi tạo kết nối với Autopilot.

1. Chọn **Thêm chính bạn là người dùng xuất** và cung cấp thông tin xác thực Customer Insights.

1. Chọn **Tiếp** để định cấu hình xuất.

## <a name="configure-the-connector"></a>Đặt cấu hình trình kết nối

1. Trong phần **So khớp dữ liệu**, trong trường **Email**, chọn trường trong hồ sơ khách hàng hợp nhất trình bày địa chỉ email của khách hàng. Lặp lại các bước tương tự cho các trường tùy chọn khác như **Tên**, **Họ**.

1. Chọn phân khúc mà bạn muốn xuất. Chúng tôi **khuyên bạn không nên xuất tổng cộng hơn 100.000 hồ sơ khách hàng** tới Autopilot. 

1. Chọn **Lưu**.

## <a name="export-the-data"></a>Xuất dữ liệu

Bạn có thể [xuất dữ liệu theo nhu cầu](export-destinations.md). Mỗi lần [làm mới theo lịch](system.md#schedule-tab), tác vụ xuất cũng sẽ chạy.

## <a name="known-limitations"></a>Các giới hạn đã biết

- Bạn có thể xuất tổng cộng tối đa 100.000 hồ sơ khách hàng sang Autopilot.
- Việc xuất sang Autopilot bị giới hạn ở các phân đoạn.
- Có thể mất tới vài giờ để hoàn thành việc xuất lên đến 100.000 hồ sơ sang Autopilot. 
- Số lượng hồ sơ mà bạn có thể xuất sang Autopilot phụ thuộc vào giới hạn đối với hợp đồng của bạn với Autopilot.

## <a name="data-privacy-and-compliance"></a>Quyền riêng tư về dữ liệu và sự tuân thủ

Khi bật Dynamics 365 Customer Insights để truyền dữ liệu tới Autopilot, bạn cho phép chuyển dữ liệu ra bên ngoài ranh giới tuân thủ cho Dynamics 365 Customer Insights, bao gồm dữ liệu nhạy cảm tiềm ẩn như Dữ liệu cá nhân. Microsoft sẽ chuyển những dữ liệu đó theo chỉ dẫn của bạn, nhưng bạn có trách nhiệm đảm bảo rằng Autopilot đáp ứng mọi nghĩa vụ về quyền riêng tư hoặc bảo mật mà bạn có thể có. Để biết thêm thông tin, hãy xem [Tuyên bố về Quyền riêng tư của Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Quản trị viên Dynamics 365 Customer Insights của bạn có thể xóa đích xuất này bất cứ lúc nào để ngừng sử dụng chức năng này.


[!INCLUDE[footer-include](../includes/footer-banner.md)]