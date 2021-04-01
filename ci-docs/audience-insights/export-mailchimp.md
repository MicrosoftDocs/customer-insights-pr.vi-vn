---
title: Xuất dữ liệu Customer Insights sang Mailchimp
description: Tìm hiểu cách định cấu hình kết nối với Mailchimp.
ms.date: 10/26/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 9f86616731c3cc3d26370727103ea9c5d4288c8d
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598227"
---
# <a name="connector-for-mailchimp-preview"></a>Trình kết nối cho Mailchimp (bản xem trước)

Xuất phân đoạn hồ sơ khách hàng hợp nhất sang Mailchimp để tạo bản tin và chiến dịch email.

## <a name="prerequisites"></a>Điều kiện tiên quyết

-   Bạn có một [Tài khoản Mailchimp](https://mailchimp.com/) và thông tin đăng nhập quản trị viên tương ứng.
-   Có đối tượng hiện có trong Mailchimp và các ID tương ứng. Để biết thêm thông tin, hãy xem [Đối tượng Mailchimp](https://mailchimp.com/help/create-audience/).
-   Bạn có [các phân đoạn được định cấu hình](segments.md)
-   Hồ sơ khách hàng hợp nhất trong các phân đoạn đã xuất chứa các trường đại diện cho địa chỉ email.

## <a name="connect-to-mailchimp"></a>Kết nối với MailChimp

1. Đi tới **Quản trị viên** > **Đích xuất**.

1. Trong **Mailchimp**, chọn **Thiết lập**.

1. Trong trường **Tên hiển thị**, hãy đặt cho đích xuất một cái tên dễ nhận biết.

1. Chọn **Tôi đồng ý** để xác nhận **Quyền riêng tư về dữ liệu và sự tuân thủ**.

1. Nhập **[ID đối tượng Mailchimp](https://mailchimp.com/help/find-audience-id/)** và chọn **Kết nối** để khởi tạo kết nối với Mailchimp.

1. Chọn **Xác thực bằng Mailchimp** và cung cấp thông tin đăng nhập Mailchimp của bạn.

1. Chọn **Thêm chính bạn là người dùng xuất** và cung cấp thông tin xác thực Customer Insights.

   :::image type="content" source="media/export-connect-mailchimp.png" alt-text="Xuất ảnh chụp màn hình cho kết nối Mailchimp":::

1. Chọn **Tiếp** để định cấu hình xuất.

## <a name="configure-the-connector"></a>Đặt cấu hình trình kết nối

1. Trong phần **So khớp dữ liệu**, trong trường **Email**, chọn trường trong hồ sơ khách hàng hợp nhất trình bày địa chỉ email của khách hàng. 

1. Theo tùy chọn, bạn có thể xuất **Tên** và **Họ** dưới dạng trường bổ sung để tạo thêm email cá nhân hóa. Chọn **Thêm thuộc tính** để ánh xạ những trường này.

1. Chọn phân khúc mà bạn muốn xuất. Bạn có thể xuất tổng cộng tối đa 1 triệu hồ sơ khách hàng sang Mailchimp.

   :::image type="content" source="media/export-segments-mailchimp.png" alt-text="Chọn các trường và phân đoạn để xuất sang Mailchimp":::

1. Chọn **Lưu**.

## <a name="export-the-data"></a>Xuất dữ liệu

Bạn có thể [xuất dữ liệu theo nhu cầu](export-destinations.md). Mỗi lần [làm mới theo lịch](system.md#schedule-tab), tác vụ xuất cũng sẽ chạy. Trong Mailchimp, bạn hiện có thể tìm thấy các phân đoạn của mình trong [Đối tượng Mailchimp](https://mailchimp.com/help/create-audience/).

## <a name="known-limitations"></a>Các giới hạn đã biết

- Lên đến 1 triệu hồ sơ mỗi lần xuất sang Mailchimp.
- Việc xuất sang Mailchimp bị giới hạn ở các phân đoạn.
- Việc xuất các phân đoạn với tổng số 1 triệu hồ sơ có thể mất đến 3 giờ do những hạn chế từ phía nhà cung cấp. 
- Số lượng hồ sơ mà bạn có thể xuất sang Mailchimp phụ thuộc và giới hạn vào hợp đồng của bạn với Mailchimp.

## <a name="data-privacy-and-compliance"></a>Quyền riêng tư về dữ liệu và tuân thủ

Khi bật Dynamics 365 Customer Insights để truyền dữ liệu tới Mailchimp, bạn cho phép chuyển dữ liệu ra bên ngoài ranh giới tuân thủ cho Dynamics 365 Customer Insights, bao gồm dữ liệu nhạy cảm tiềm ẩn như Dữ liệu cá nhân. Microsoft sẽ chuyển những dữ liệu đó theo chỉ dẫn của bạn, nhưng bạn có trách nhiệm đảm bảo rằng Mailchimp đáp ứng mọi nghĩa vụ về quyền riêng tư hoặc bảo mật mà bạn có thể có. Để biết thêm thông tin, hãy xem [Tuyên bố về Quyền riêng tư của Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Quản trị viên Dynamics 365 Customer Insights của bạn có thể xóa đích xuất này bất cứ lúc nào để ngừng sử dụng chức năng này.


[!INCLUDE[footer-include](../includes/footer-banner.md)]