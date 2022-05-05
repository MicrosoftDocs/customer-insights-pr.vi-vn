---
title: Xuất dữ liệu Customer Insights sang SendGrid
description: Tìm hiểu cách đặt cấu hình kết nối và xuất sang SendGrid.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 38dd782fdf06d5970e79e6deb6e8fc94252da585
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 04/27/2022
ms.locfileid: "8644122"
---
# <a name="export-segments-to-sendgrid-preview"></a>Xuất phân khúc sang SendGrid (bản xem trước)

Xuất phân đoạn hồ sơ khách hàng hợp nhất sang danh sách liên hệ SendGrid và sử dụng chúng cho các chiến dịch và tiếp thị qua email trong SendGrid. 

## <a name="prerequisites-for-a-connection"></a>Điều kiện tiên quyết để kết nối

-   Bạn có một [Tài khoản SendGrid](https://sendgrid.com/) và thông tin đăng nhập quản trị viên tương ứng.
-   Có danh sách liên hệ hiện có trong SendGrid và các ID tương ứng. Để biết thêm thông tin, hãy xem [SendGrid - Quản lý liên hệ](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).
-   Bạn có [phân đoạn được định cấu hình](segments.md) trong Thông tin chi tiết về khách hàng.
-   Hồ sơ khách hàng hợp nhất trong các phân khúc đã xuất chứa các trường đại diện cho địa chỉ email.

## <a name="known-limitations"></a>Các hạn chế đã biết

- Có tới 100.000 hồ sơ khách hàng trên SendGrid.
- Việc xuất sang SendGrid bị giới hạn ở các phân đoạn.
- Có thể mất tới vài phút để hoàn tất việc xuất tối đa 100.000 hồ sơ khách hàng sang SendGrid. 
- Số lượng hồ sơ khách hàng mà bạn có thể xuất sang SendGrid tùy thuộc vào và giới hạn trong hợp đồng của bạn với SendGrid.

## <a name="set-up-connection-to-sendgrid"></a>Thiết lập kết nối với SendGrid

1. Đi đến **Quản trị viên** > **Kết nối**.

1. Chọn **Thêm kết nối** rồi chọn **SendGrid** để đặt cấu hình kết nối.

1. Đặt tên dễ nhận biết cho kết nối trong trường **Tên hiển thị**. Tên và loại kết nối mô tả kết nối này. Bạn nên chọn một tên giải thích mục đích và mục tiêu của kết nối.

1. Chọn người có thể sử dụng kết nối này. Nếu bạn không thực hiện hành động nào, giá trị mặc định sẽ là Quản trị viên. Để biết thêm thông tin, hãy xem [Cho phép người đóng góp sử dụng một kết nối cho các lần xuất](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Nhập **Khóa API SendGrid** [Khóa API SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).

1. Chọn **Tôi đồng ý** để xác nhận **Quyền riêng tư về dữ liệu và sự tuân thủ**.

1. Chọn **Kết nối** để khởi tạo kết nối với SendGrid.

1. Chọn **Thêm chính bạn là người dùng xuất** và cung cấp thông tin xác thực Customer Insights.

1. Chọn **Lưu** để hoàn thành kết nối.

## <a name="configure-an-export"></a>Định cấu hình xuất

Bạn có thể định cấu hình lần xuất này nếu bạn có quyền truy cập vào kết nối thuộc loại này. Để biết thêm thông tin, hãy xem [Các quyền cần thiết để định cấu hình xuất](export-destinations.md#set-up-a-new-export).

1. Đi tới **Dữ liệu** > **Nội dung xuất**.

1. Để tạo một nội dung xuất mới, hãy chọn **Thêm đích**.

1. Trong trường **Kết nối để xuất**, hãy chọn một kết nối từ phần SendGrid. Nếu bạn không thấy tên phần này, tức là không có kết nối nào thuộc loại này dành cho bạn.

1. Nhập **[ID danh sách SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.

1. Trong phần **Đối sánh dữ liệu**, trong trường **Email**, chọn trường có địa chỉ email của khách hàng. Lặp lại các bước tương tự cho các trường tùy chọn khác như **Tên**, **Họ**, **Quốc gia/Khu vực**, **Tiểu bang**, **Thành phố** và **Mã bưu điện**.

1. Chọn phân khúc mà bạn muốn xuất. Chúng tôi **khuyên bạn không nên xuất tổng cộng hơn 100.000 hồ sơ khách hàng** tới SendGrid. 

1. Chọn **Lưu**.

Việc lưu một nội dung xuất sẽ không chạy nội dung xuất đó ngay lập tức.

Nội dung xuất chạy trong mỗi lần [làm mới theo lịch trình](system.md#schedule-tab). Bạn cũng có thể [xuất dữ liệu theo yêu cầu](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Quyền riêng tư về dữ liệu và sự tuân thủ

Khi bật Dynamics 365 Customer Insights để truyền dữ liệu tới SendGrid, bạn cho phép chuyển dữ liệu ra bên ngoài ranh giới tuân thủ cho Dynamics 365 Customer Insights, bao gồm dữ liệu nhạy cảm tiềm ẩn như Dữ liệu cá nhân. Microsoft sẽ chuyển những dữ liệu đó theo chỉ dẫn của bạn, nhưng bạn có trách nhiệm đảm bảo rằng SendGrid đáp ứng mọi nghĩa vụ về quyền riêng tư hoặc bảo mật mà bạn có thể có. Để biết thêm thông tin, hãy xem [Tuyên bố về Quyền riêng tư của Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Quản trị viên Dynamics 365 Customer Insights của bạn có thể xóa đích xuất này bất cứ lúc nào để ngừng việc sử dụng chức năng này.


[!INCLUDE [footer-include](includes/footer-banner.md)]
