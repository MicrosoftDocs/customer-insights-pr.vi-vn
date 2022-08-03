---
title: Xuất phân khúc sang Marketo (bản xem trước)
description: Tìm hiểu cách đặt cấu hình kết nối và xuất sang Marketo.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f57cdfbb24df8a8ffa1670b426d50dbba2c5f40f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195270"
---
# <a name="export-segments-to-marketo-preview"></a>Xuất phân khúc sang Marketo (bản xem trước)

Xuất các phân đoạn hồ sơ khách hàng hợp nhất để tạo chiến dịch, cung cấp email tiếp thị và tận dụng các nhóm khách hàng cụ thể với Marketo.

## <a name="prerequisites"></a>Điều kiện tiên quyết

- Một [Tài khoản Marketo](https://login.marketo.com/) và thông tin đăng nhập quản trị viên tương ứng.
- Một [ID ứng dụng khách Marketo, bí mật ứng dụng khách và Tên máy chủ điểm cuối REST](https://developers.marketo.com/rest-api/authentication/).
- [Danh sách hiện có trong Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists) và các ID tương ứng.
- [Các phân đoạn được định cấu hình](segments.md).
- Hồ sơ khách hàng hợp nhất trong các phân khúc đã xuất chứa các trường đại diện cho địa chỉ email.

## <a name="known-limitations"></a>Các hạn chế đã biết

- Lên đến 1 triệu hồ sơ khách hàng cho mỗi lần xuất sang Marketo, có thể mất đến 3 giờ. Số lượng hồ sơ khách hàng mà bạn có thể xuất sang Marketo tùy thuộc vào hợp đồng của bạn với Marketo.
- Chỉ phân đoạn.

## <a name="set-up-connection-to-marketo"></a>Thiết lập kết nối với Marketo

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Đi đến **Quản trị viên** > **Kết nối**.

1. Lựa chọn **Thêm kết nối** và lựa chọn **Marketo**.

1. Đặt tên dễ nhận biết cho kết nối trong trường **Tên hiển thị**. Tên và loại kết nối mô tả kết nối này. Bạn nên chọn một tên giải thích mục đích và mục tiêu của kết nối.

1. Chọn người có thể sử dụng kết nối này. Theo mặc định, giá trị này là quản trị viên. Để biết thêm thông tin, hãy xem [Cho phép người đóng góp sử dụng một kết nối cho các lần xuất](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Nhập của bạn **ID khách hàng Marketo, bí mật khách hàng và tên máy chủ điểm cuối REST**. Tên máy chủ điểm cuối REST chỉ là tên máy chủ, không có https://. Ví dụ: xyz-abc-123.mktorest.com.

1. Xem lại [quyền riêng tư và tuân thủ dữ liệu](connections.md#data-privacy-and-compliance) và chọn **tôi đồng ý**.

1. Lựa chọn **Liên kết** để khởi tạo kết nối.

1. Chọn **Thêm chính bạn là người dùng xuất** và cung cấp thông tin xác thực Customer Insights.

1. Chọn **Lưu** để hoàn thành kết nối.

## <a name="configure-an-export"></a>Định cấu hình xuất

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Đi tới **Dữ liệu** > **Nội dung xuất**.

1. Lựa chọn **Thêm xuất khẩu**.

1. Trong trường **Kết nối để xuất**, hãy chọn một kết nối từ phần Marketo. Liên hệ với quản trị viên nếu không có kết nối.

1. Nhập tên cho lần xuất.

1. Nhập của bạn **ID danh sách thị trường**. ID danh sách là một giá trị số đơn thuần. Ví dụ: nếu ID danh sách Marketo của bạn là ST12345A7, hãy xóa ký tự trước và sau các chữ số và nhập *12345*.

1. Bên trong **Đối sánh dữ liệu**, hãy chọn ít nhất một trường đại diện cho địa chỉ email của khách hàng hoặc ID thị trường của khách hàng.

1. Tùy chọn, xuất **tên**, **·**, **phố**, **bang**, và **Quốc gia / Khu vực** để tạo nhiều email được cá nhân hóa hơn. Chọn **Thêm thuộc tính** để ánh xạ những trường này.

1. Chọn phân khúc mà bạn muốn xuất.

1. Chọn **Lưu.**

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Trong Marketo, hãy tìm các phân đoạn của bạn trong [Danh sách thị trường](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).

[!INCLUDE [footer-include](includes/footer-banner.md)]
