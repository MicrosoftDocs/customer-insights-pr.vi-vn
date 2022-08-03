---
title: Xuất phân khúc sang SendGrid (bản xem trước)
description: Tìm hiểu cách đặt cấu hình kết nối và xuất sang SendGrid.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f2990ad410dda0cbf952f82f3fc30b3a53a7bcd4
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 07/27/2022
ms.locfileid: "9197018"
---
# <a name="export-segments-to-sendgrid-preview"></a>Xuất phân khúc sang SendGrid (bản xem trước)

Xuất phân đoạn hồ sơ khách hàng hợp nhất sang danh sách liên hệ SendGrid và sử dụng chúng cho các chiến dịch và tiếp thị qua email trong SendGrid.

## <a name="prerequisites"></a>Điều kiện tiên quyết

- Một [Tài khoản SendGrid](https://sendgrid.com/) và thông tin đăng nhập quản trị viên tương ứng.
- [Danh sách liên hệ hiện có trong SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts) và các ID tương ứng.
- Một [Khóa API SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).
- [Các phân đoạn đã định cấu hình](segments.md) trong Thông tin chi tiết về khách hàng.
- Hồ sơ khách hàng hợp nhất trong các phân khúc đã xuất chứa các trường đại diện cho địa chỉ email.

## <a name="known-limitations"></a>Các hạn chế đã biết

- Tổng cộng có tới 100.000 hồ sơ khách hàng trên SendGrid, có thể mất đến vài giờ để hoàn thành. Số lượng hồ sơ khách hàng mà bạn có thể xuất sang SendGrid tùy thuộc vào hợp đồng của bạn với SendGrid.
- Chỉ phân đoạn.

## <a name="set-up-connection-to-sendgrid"></a>Thiết lập kết nối với SendGrid

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Đi đến **Quản trị viên** > **Kết nối**.

1. Lựa chọn **Thêm kết nối** và lựa chọn **SendGrid**.

1. Đặt tên dễ nhận biết cho kết nối trong trường **Tên hiển thị**. Tên và loại kết nối mô tả kết nối này. Bạn nên chọn một tên giải thích mục đích và mục tiêu của kết nối.

1. Chọn người có thể sử dụng kết nối này. Theo mặc định, giá trị này là quản trị viên. Để biết thêm thông tin, hãy xem [Cho phép người đóng góp sử dụng một kết nối cho các lần xuất](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Nhập của bạn **Khóa API SendGrid**.

1. Xem lại [quyền riêng tư và tuân thủ dữ liệu](connections.md#data-privacy-and-compliance) và chọn **tôi đồng ý**.

1. Lựa chọn **Liên kết** để khởi tạo kết nối.

1. Chọn **Thêm chính bạn là người dùng xuất** và cung cấp thông tin xác thực Customer Insights.

1. Chọn **Lưu** để hoàn thành kết nối.

## <a name="configure-an-export"></a>Định cấu hình xuất

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Đi tới **Dữ liệu** > **Nội dung xuất**.

1. Lựa chọn **Thêm xuất khẩu**.

1. Trong trường **Kết nối để xuất**, hãy chọn một kết nối từ phần SendGrid. Liên hệ với quản trị viên nếu không có kết nối.

1. Nhập tên cho lần xuất.

1. Nhập của bạn **ID danh sách SendGrid**.

1. Trong phần **Đối sánh dữ liệu**, trong trường **Email**, chọn trường có địa chỉ email của khách hàng.

1. Theo tùy chọn, hãy chọn các trường như **tên**, **·**, **gia / Khu vực**, **bang**, **phố**, và **Mã bưu điện**.

1. Chọn các phân đoạn bạn muốn xuất theo các giới hạn đã biết.

1. Chọn **Lưu.**

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
