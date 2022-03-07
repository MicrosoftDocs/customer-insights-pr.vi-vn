---
title: Xuất dữ liệu Customer Insights sang Constant Contact
description: Tìm hiểu cách đặt cấu hình kết nối và xuất sang Constant Contact.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8841945814397ffa70c56638a8bed25499c1a06f
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 02/16/2022
ms.locfileid: "8226429"
---
# <a name="export-segments-to-constant-contact-preview"></a>Xuất phân khúc sang Constant Contact (xem trước)

Xuất các phân khúc hồ sơ khách hàng hợp nhất sang Constant Contact và sử dụng chúng cho các hoạt động tiếp thị. 

## <a name="prerequisites-for-a-connection"></a>Điều kiện tiên quyết để kết nối

-   Bạn có một [Tài khoản Constant Contact](https://www.constantcontact.com/account-home) và thông tin xác thực tương ứng của quản trị viên.
-   Bạn có [các phân khúc được định cấu hình](segments.md) trong thông tin chuyên sâu về đối tượng.
-   Hồ sơ khách hàng hợp nhất trong các phân khúc đã xuất chứa các trường đại diện cho địa chỉ email.

## <a name="known-limitations"></a>Các hạn chế đã biết

- Bạn có thể xuất tối đa 1 triệu hồ sơ khách hàng cho mỗi lần xuất sang Constant Contact.
- Bạn chỉ xuất được phân khúc sang Constant Contact.
- Có thể mất tới 1 giờ để hoàn tất việc xuất tối đa 1 triệu hồ sơ khách hàng sang Constant Contact. 
- Số lượng hồ sơ khách hàng mà bạn có thể xuất sang Constant Contact tùy thuộc vào và giới hạn trong hợp đồng của bạn với Constant Contact.

## <a name="set-up-connection-to-constant-contact"></a>Thiết lập kết nối với Constant Contact

1. Đi đến **Quản trị viên** > **Kết nối**.

1. Chọn **Thêm kết nối** rồi chọn **Constant Contact** để đặt cấu hình kết nối.

1. Đặt tên dễ nhận biết cho kết nối trong trường **Tên hiển thị**. Tên và loại kết nối mô tả kết nối này. Bạn nên chọn một tên giải thích mục đích và mục tiêu của kết nối.

1. Chọn người có thể sử dụng kết nối này. Nếu bạn không thực hiện hành động nào, giá trị mặc định sẽ là Quản trị viên. Để biết thêm thông tin, hãy xem [Cho phép người đóng góp sử dụng một kết nối cho các lần xuất](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Chọn **Tôi đồng ý** để xác nhận **Quyền riêng tư về dữ liệu và sự tuân thủ**.

1. Chọn **Kết nối** để khởi tạo kết nối với Constant Contact.

1. Chọn **Xác thực với Constant Contact** và cung cấp thông tin đăng nhập quản trị viên của bạn cho Constant Contact. 

1. Chọn **Thêm chính bạn là người dùng xuất** và cung cấp thông tin xác thực Customer Insights.

1. Chọn **Lưu** để hoàn thành kết nối.

## <a name="configure-an-export"></a>Định cấu hình xuất

Bạn có thể định cấu hình lần xuất này nếu bạn có quyền truy cập vào kết nối thuộc loại này. Để biết thêm thông tin, hãy xem [Các quyền cần thiết để định cấu hình xuất](export-destinations.md#set-up-a-new-export).

1. Đi tới **Dữ liệu** > **Nội dung xuất**.

1. Để tạo một nội dung xuất mới, hãy chọn **Thêm đích**.

1. Trong trường **Kết nối để xuất**, hãy chọn một kết nối từ phần Constant Contact. Nếu bạn không thấy tên phần này, tức là không có kết nối nào thuộc loại này dành cho bạn.

1. Nhập [**ID danh sách Constant Contact**](https://app.constantcontact.com/pages/contacts/ui#lists). Mở một danh sách trong Constant Contact để tìm ID danh sách trong URL.

1. Trong phần **Đối sánh dữ liệu**, trong trường **Email**, chọn trường có địa chỉ email của khách hàng. Bạn phải xuất các phân khúc sang Constant Contact.

1. Theo tùy chọn, bạn có thể xuất Tên và Họ dưới dạng trường bổ sung để tạo thêm email cá nhân hóa. Chọn **Thêm thuộc tính** để ánh xạ những trường này.

1. Chọn phân khúc mà bạn muốn xuất.

1. Chọn **Lưu**.

Việc lưu một nội dung xuất sẽ không chạy nội dung xuất đó ngay lập tức.

Nội dung xuất chạy trong mỗi lần [làm mới theo lịch trình](system.md#schedule-tab). Bạn cũng có thể [xuất dữ liệu theo yêu cầu](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Quyền riêng tư về dữ liệu và sự tuân thủ

Khi bật Dynamics 365 Customer Insights để truyền dữ liệu đến Constant Contact, bạn cho phép chuyển dữ liệu ra bên ngoài ranh giới tuân thủ của Dynamics 365 Customer Insights, bao gồm cả dữ liệu có thể nhạy cảm như Dữ liệu cá nhân. Microsoft sẽ chuyển những dữ liệu đó theo chỉ dẫn của bạn, nhưng bạn có trách nhiệm đảm bảo rằng Constant Contact đáp ứng mọi nghĩa vụ về quyền riêng tư hoặc bảo mật mà bạn có thể có. Để biết thêm thông tin, hãy xem [Tuyên bố về Quyền riêng tư của Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Quản trị viên Dynamics 365 Customer Insights của bạn có thể xóa đích xuất này bất cứ lúc nào để ngừng việc sử dụng chức năng này.
