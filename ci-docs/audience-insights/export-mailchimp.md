---
title: Xuất dữ liệu Customer Insights sang Mailchimp
description: Tìm hiểu cách đặt cấu hình kết nối và xuất sang Mailchimp.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 94a9fead56ce8c40b35d4eb41ebdc0d672798dce
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 10/08/2021
ms.locfileid: "7618641"
---
# <a name="export-segments-to-mailchimp-preview"></a>Xuất phân khúc sang Mailchimp (xem trước)

Xuất phân khúc hồ sơ khách hàng hợp nhất sang Mailchimp để tạo bản tin và chiến dịch email.

## <a name="prerequisites-for-connection"></a>Điều kiện tiên quyết để kết nối

-   Bạn có một [Tài khoản Mailchimp](https://mailchimp.com/) và thông tin đăng nhập quản trị viên tương ứng.
-   Có đối tượng hiện có trong Mailchimp và các ID tương ứng. Để biết thêm thông tin, hãy xem [Đối tượng Mailchimp](https://mailchimp.com/help/create-audience/).
-   Bạn có [các phân khúc được định cấu hình](segments.md)
-   Hồ sơ khách hàng hợp nhất trong các phân khúc đã xuất chứa các trường đại diện cho địa chỉ email.

## <a name="known-limitations"></a>Các hạn chế đã biết

- Lên đến 1 triệu hồ sơ khách hàng cho mỗi lần xuất sang Mailchimp.
- Bạn chỉ xuất được phân khúc sang Mailchimp.
- Quá trình xuất phân khúc với 1 triệu hồ sơ khách hàng có thể mất đến 3 giờ. 
- Số lượng hồ sơ khách hàng mà bạn có thể xuất sang Mailchimp tùy thuộc vào và giới hạn trong hợp đồng của bạn với Mailchimp.

## <a name="set-up-connection-to-mailchimp"></a>Thiết lập kết nối với Mailchimp

1. Đi đến **Quản trị viên** > **Kết nối**.

1. Chọn **Thêm kết nối** rồi chọn **Mailchimp** để định cấu hình kết nối.

1. Đặt tên dễ nhận biết cho kết nối trong trường **Tên hiển thị**. Tên và loại kết nối mô tả kết nối này. Bạn nên chọn một tên giải thích mục đích và mục tiêu của kết nối.

1. Chọn người có thể sử dụng kết nối này. Nếu bạn không thực hiện hành động nào, giá trị mặc định sẽ là Quản trị viên. Để biết thêm thông tin, hãy xem [Cho phép người đóng góp sử dụng một kết nối cho các lần xuất](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Chọn **Tôi đồng ý** để xác nhận **Quyền riêng tư về dữ liệu và sự tuân thủ**.

1. Chọn **Kết nối** để khởi tạo kết nối với Mailchimp.

1. Chọn **Xác thực bằng Mailchimp** và cung cấp thông tin đăng nhập Mailchimp của bạn.

1. Chọn **Thêm chính bạn là người dùng xuất** và cung cấp thông tin xác thực Customer Insights.

1. Chọn **Lưu** để hoàn thành kết nối. 

## <a name="configure-the-connector"></a>Đặt cấu hình trình kết nối

Bạn có thể đặt cấu hình lần xuất này nếu bạn có quyền truy cập vào kết nối thuộc loại này. Để biết thêm thông tin, hãy xem [Các quyền cần thiết để định cấu hình xuất](export-destinations.md#set-up-a-new-export).

1. Đi tới **Dữ liệu**> **Nội dung xuất**.

1. Để tạo một nội dung xuất mới, hãy chọn **Thêm đích**.

1. Trong trường **Kết nối để xuất**, hãy chọn một kết nối từ phần Mailchimp. Nếu bạn không thấy tên phần này, tức là không có kết nối nào thuộc loại này dành cho bạn.

1. Nhập **[ID đối tượng Mailchimp](https://mailchimp.com/help/find-audience-id/)** của bạn

1. Trong phần **Đối sánh dữ liệu**, trong trường **Email**, chọn trường có địa chỉ email của khách hàng. 

1. Bạn có thể tùy ý xuất **Tên** và **Họ** để tạo nhiều email được cá nhân hóa hơn. Chọn **Thêm thuộc tính** để ánh xạ những trường này.

1. Chọn phân khúc mà bạn muốn xuất. Bạn có thể xuất tổng cộng tối đa 1 triệu hồ sơ khách hàng sang Mailchimp.

1. Chọn **Lưu**.

Việc lưu một nội dung xuất sẽ không chạy nội dung xuất đó ngay lập tức.

Nội dung xuất chạy trong mỗi lần [làm mới theo lịch trình](system.md#schedule-tab). Bạn cũng có thể [xuất dữ liệu theo yêu cầu](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Quyền riêng tư về dữ liệu và sự tuân thủ

Khi bật Dynamics 365 Customer Insights để truyền dữ liệu tới Mailchimp, bạn cho phép chuyển dữ liệu ra bên ngoài ranh giới tuân thủ cho Dynamics 365 Customer Insights, bao gồm dữ liệu nhạy cảm tiềm ẩn như Dữ liệu cá nhân. Microsoft sẽ chuyển những dữ liệu đó theo chỉ dẫn của bạn, nhưng bạn có trách nhiệm đảm bảo rằng Mailchimp đáp ứng mọi nghĩa vụ về quyền riêng tư hoặc bảo mật mà bạn có thể có. Để biết thêm thông tin, hãy xem [Tuyên bố về Quyền riêng tư của Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Quản trị viên Dynamics 365 Customer Insights của bạn có thể xóa đích xuất này bất cứ lúc nào để ngừng việc sử dụng chức năng này.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
