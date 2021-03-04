---
title: Xuất dữ liệu Customer Insights sang SendGrid
description: Tìm hiểu cách định cấu hình kết nối với SendGrid.
ms.date: 12/08/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f16d69deb2a0b48270ed04f9b72f03056f20b619
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268758"
---
# <a name="connector-for-sendgrid-preview"></a>Trình kết nối cho SendGrid (bản xem trước)

Xuất phân đoạn hồ sơ khách hàng hợp nhất sang danh sách liên hệ SendGrid và sử dụng chúng cho các chiến dịch và tiếp thị qua email trong SendGrid. 

## <a name="prerequisites"></a>Điều kiện tiên quyết

-   Bạn có một [Tài khoản SendGrid](https://sendgrid.com/) và thông tin đăng nhập quản trị viên tương ứng.
-   Có danh sách liên hệ hiện có trong SendGrid và các ID tương ứng. Để biết thêm thông tin, hãy xem [SendGrid - Quản lý liên hệ](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).
-   Bạn có [các phân đoạn được định cấu hình](segments.md) trong thông tin chi tiết về đối tượng.
-   Hồ sơ khách hàng hợp nhất trong các phân đoạn đã xuất chứa các trường đại diện cho địa chỉ email.

## <a name="connect-to-sendgrid"></a>Kết nối với SendGrid

1. Đi tới **Quản trị viên** > **Đích xuất**.

1. Trong **SendGrid**, chọn **Thiết lập**.

1. Trong trường **Tên hiển thị**, hãy đặt cho đích xuất một cái tên dễ nhận biết.

   :::image type="content" source="media/export-sendgrid.PNG" alt-text="Ngăn cấu hình xuất SendGrid.":::

1. Nhập **Khóa API SendGrid** [Khóa API SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).

1. Nhập **[ID danh sách SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.

1. Chọn **Tôi đồng ý** để xác nhận **Quyền riêng tư về dữ liệu và sự tuân thủ**.

1. Chọn **Kết nối** để khởi tạo kết nối với SendGrid.

1. Chọn **Thêm chính bạn là người dùng xuất** và cung cấp thông tin xác thực Customer Insights.

1. Chọn **Tiếp** để định cấu hình xuất.

## <a name="configure-the-connector"></a>Đặt cấu hình trình kết nối

1. Trong phần **So khớp dữ liệu**, trong trường **Email**, chọn trường trong hồ sơ khách hàng hợp nhất trình bày địa chỉ email của khách hàng. Lặp lại các bước tương tự cho các trường tùy chọn khác như **Tên**, **Họ**, **Quốc gia/Khu vực**, **Tiểu bang**, **Thành phố** và **Mã bưu điện**.

1. Chọn phân khúc mà bạn muốn xuất. Chúng tôi **khuyên bạn không nên xuất tổng cộng hơn 100.000 hồ sơ khách hàng** tới SendGrid. 

1. Chọn **Lưu**.

## <a name="export-the-data"></a>Xuất dữ liệu

Bạn có thể [xuất dữ liệu theo nhu cầu](export-destinations.md). Mỗi lần [làm mới theo lịch](system.md#schedule-tab), tác vụ xuất cũng sẽ chạy.

## <a name="known-limitations"></a>Các giới hạn đã biết

- Tối đa 100.000 hồ sơ trên SendGrid.
- Việc xuất sang SendGrid bị giới hạn ở các phân đoạn.
- Có thể mất tới vài giờ để hoàn thành việc xuất lên đến 100.000 hồ sơ sang SendGrid. 
- Số lượng hồ sơ mà bạn có thể xuất sang SendGrid còn phụ thuộc vào giới hạn cho hợp đồng của bạn với SendGrid.

## <a name="data-privacy-and-compliance"></a>Quyền riêng tư về dữ liệu và sự tuân thủ

Khi bật Dynamics 365 Customer Insights để truyền dữ liệu tới SendGrid, bạn cho phép chuyển dữ liệu ra bên ngoài ranh giới tuân thủ cho Dynamics 365 Customer Insights, bao gồm dữ liệu nhạy cảm tiềm ẩn như Dữ liệu cá nhân. Microsoft sẽ chuyển những dữ liệu đó theo chỉ dẫn của bạn, nhưng bạn có trách nhiệm đảm bảo rằng SendGrid đáp ứng mọi nghĩa vụ về quyền riêng tư hoặc bảo mật mà bạn có thể có. Để biết thêm thông tin, hãy xem [Tuyên bố về Quyền riêng tư của Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Quản trị viên Dynamics 365 Customer Insights của bạn có thể xóa đích xuất này bất cứ lúc nào để ngừng sử dụng chức năng này.


[!INCLUDE[footer-include](../includes/footer-banner.md)]