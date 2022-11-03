---
title: Xuất phân khúc sang DotDigital (xem trước)
description: Tìm hiểu cách đặt cấu hình kết nối và xuất sang DotDigital.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8f3e3378dce9177c6645b91140884ae135540243
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725012"
---
# <a name="export-segments-to-dotdigital-preview"></a>Xuất phân khúc sang DotDigital (xem trước)

Xuất các phân khúc hồ sơ khách hàng hợp nhất sang sổ địa chỉ DotDigital và sử dụng chúng cho các chiến dịch, tiếp thị qua email và để xây dựng phân khúc khách hàng với DotDigital.

## <a name="prerequisites"></a>Điều kiện tiên quyết

- Một [Tài khoản DotDigital](https://dotdigital.com/) và một [Người dùng API](https://support.dotdigital.com/hc/articles/115001718730-How-do-I-create-an-API-user).
- ID số chấm từ một [Mới](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book) hoặc sổ địa chỉ hiện có trong DotDigital. Có thể tìm thấy ID trong URL khi bạn chọn và mở sổ địa chỉ.
- [Các phân đoạn đã định cấu hình](segments.md) trong Thông tin chi tiết về khách hàng.
- Hồ sơ khách hàng hợp nhất trong các phân khúc đã xuất chứa các trường đại diện cho địa chỉ email.

## <a name="known-limitations"></a>Các hạn chế đã biết

- Liên kết riêng tư kết hợp với Mang theo bộ nhớ của riêng bạn (BYOS) không được hỗ trợ.
- Lên đến 1 triệu hồ sơ khách hàng cho mỗi lần xuất sang DotDigital, có thể mất đến ba giờ để hoàn thành vì những hạn chế từ phía nhà cung cấp. Số lượng hồ sơ khách hàng mà bạn có thể xuất sang DotDigital tùy thuộc vào hợp đồng của bạn với DotDigital.
- Chỉ phân đoạn.

## <a name="set-up-connection-to-dotdigital"></a>Thiết lập kết nối với DotDigital

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Đi đến **Quản trị viên** > **Kết nối**.

1. Lựa chọn **Thêm kết nối** và lựa chọn **DotDigital**.

1. Đặt tên dễ nhận biết cho kết nối trong trường **Tên hiển thị**. Tên và loại kết nối mô tả kết nối này. Bạn nên chọn một tên giải thích mục đích và mục tiêu của kết nối.

1. Chọn người có thể sử dụng kết nối này. Theo mặc định, giá trị này là quản trị viên. Để biết thêm thông tin, hãy xem [Cho phép người đóng góp sử dụng một kết nối cho các lần xuất](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Nhập **Tên người dùng và mật khẩu API DotDigital**.

1. Nhập của bạn **ID sổ địa chỉ DotDigital**.

1. Xem lại [quyền riêng tư và tuân thủ dữ liệu](connections.md#data-privacy-and-compliance) và chọn **tôi đồng ý**.

1. Lựa chọn **Liên kết** để khởi tạo kết nối.

1. Chọn **Thêm chính bạn là người dùng xuất** và cung cấp thông tin xác thực Customer Insights.

1. Chọn **Lưu** để hoàn thành kết nối.

## <a name="configure-an-export"></a>Định cấu hình xuất

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Đi tới **Dữ liệu** > **Nội dung xuất**.

1. Lựa chọn **Thêm xuất khẩu**.

1. Trong trường **Kết nối để xuất**, hãy chọn một kết nối từ phần DotDigital. Liên hệ với quản trị viên nếu không có kết nối.

1. Nhập tên cho lần xuất.

1. Trong phần **Đối sánh dữ liệu**, trong trường **Email**, chọn trường có địa chỉ email của khách hàng.

1. Tùy chọn, xuất **tên**, **·**, **và tên**, **tính**, và **Mã bưu điện**.

1. Chọn phân khúc mà bạn muốn xuất.

1. Chọn **Lưu.**

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Trong DotDigital, hãy tìm các phân đoạn của bạn trong [Sổ địa chỉ DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).

[!INCLUDE [footer-include](includes/footer-banner.md)]
