---
title: Xuất phân khúc sang Sendinblue (bản xem trước)
description: Tìm hiểu cách định cấu hình kết nối và xuất sang Sendinblue.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 816a3b242fadaa5a75db878adf0a76baf638e41c
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196972"
---
# <a name="export-segments-to-sendinblue-preview"></a>Xuất phân khúc sang Sendinblue (bản xem trước)

Xuất các phân khúc hồ sơ khách hàng hợp nhất để tạo chiến dịch, cung cấp email tiếp thị và sử dụng các nhóm khách hàng cụ thể với Sendinblue.

## <a name="prerequisites"></a>Điều kiện tiên quyết

- Một [Tài khoản Sendinblue](https://www.sendinblue.com/) và thông tin đăng nhập quản trị viên tương ứng.
- Một [Khóa API SendinBlue](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key).
- Danh sách hiện có trong Sendinblue và các ID tương ứng.
- [Các phân đoạn được định cấu hình](segments.md).
- Hồ sơ khách hàng hợp nhất trong các phân khúc đã xuất chứa các trường đại diện cho địa chỉ email.

## <a name="known-limitations"></a>Các hạn chế đã biết

- Lên đến 1 triệu hồ sơ khách hàng cho mỗi lần xuất sang Sendinblue, có thể mất đến 90 phút để hoàn thành. Số lượng hồ sơ khách hàng mà bạn có thể xuất sang Sendinblue tùy thuộc vào hợp đồng của bạn với Sendinblue.
- Chỉ phân đoạn.

## <a name="set-up-connection-to-sendinblue"></a>Thiết lập kết nối đến Sendinblue

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Đi đến **Quản trị viên** > **Kết nối**.

1. Lựa chọn **Thêm kết nối** và lựa chọn **Sendinblue**.

1. Đặt tên dễ nhận biết cho kết nối trong trường **Tên hiển thị**. Tên và loại kết nối mô tả kết nối này. Bạn nên chọn một tên giải thích mục đích và mục tiêu của kết nối.

1. Chọn người có thể sử dụng kết nối này. Theo mặc định, giá trị này là quản trị viên. Để biết thêm thông tin, hãy xem [Cho phép người đóng góp sử dụng một kết nối cho các lần xuất](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Nhập của bạn **Khóa API SendinBlue**.

1. Xem lại [quyền riêng tư và tuân thủ dữ liệu](connections.md#data-privacy-and-compliance) và chọn **tôi đồng ý**.

1. Lựa chọn **Liên kết** để khởi tạo kết nối.

1. Chọn **Thêm chính bạn là người dùng xuất** và cung cấp thông tin xác thực Customer Insights.

1. Chọn **Lưu** để hoàn thành kết nối.

## <a name="configure-an-export"></a>Định cấu hình xuất

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Đi tới **Dữ liệu** > **Nội dung xuất**.

1. Lựa chọn **Thêm xuất khẩu**.

1. Trong trường **Kết nối để xuất**, hãy chọn một kết nối từ phần Sendinblue. Liên hệ với quản trị viên nếu không có kết nối.

1. Nhập tên cho lần xuất.

1. Nhập của bạn **ID danh sách Sendinblue**.

1. Trong phần **Đối sánh dữ liệu**, trong trường **Email**, chọn trường có địa chỉ email của khách hàng.

1. Tùy chọn, xuất **tên**, **·**, và **Điện thoại** để tạo nhiều email được cá nhân hóa hơn. Chọn **Thêm thuộc tính** để ánh xạ những trường này.

1. Chọn phân khúc mà bạn muốn xuất.

1. Chọn **Lưu.**

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
