---
title: Xuất phân khúc sang Autopilot (bản xem trước)
description: Tìm hiểu cách đặt cấu hình kết nối và xuất sang Autopilot.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b4b14ba9de2c7e20175fac664a705f2212a411fd
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724828"
---
# <a name="export-segments-to-autopilot-preview"></a>Xuất phân khúc sang Autopilot (bản xem trước)

Xuất phân đoạn hồ sơ khách hàng hợp nhất sang Autopilot và sử dụng chúng cho các chiến dịch và tiếp thị qua email trong Autopilot.

## <a name="prerequisites-for-a-connection"></a>Điều kiện tiên quyết để kết nối

- Một [Tài khoản lái tự động](https://www.autopilothq.com/) và thông tin đăng nhập quản trị viên tương ứng.
- Một [Khóa API Autopilot](https://autopilot.docs.apiary.io/#)
- [Các phân đoạn đã định cấu hình](segments.md) trong Thông tin chi tiết về khách hàng.
- Hồ sơ khách hàng hợp nhất trong các phân khúc đã xuất chứa các trường đại diện cho địa chỉ email.

## <a name="known-limitations"></a>Các hạn chế đã biết

- Liên kết riêng tư kết hợp với Mang theo bộ nhớ của riêng bạn (BYOS) không được hỗ trợ.
- Lên đến 100.000 hồ sơ khách hàng cho mỗi lần xuất sang Autopilot, có thể mất đến vài giờ để hoàn thành. Số lượng hồ sơ khách hàng mà bạn có thể xuất sang Autopilot tùy thuộc vào hợp đồng của bạn với Autopilot.
- Chỉ phân đoạn.

## <a name="set-up-connection-to-autopilot"></a>Thiết lập kết nối với Autopilot

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Đi đến **Quản trị viên** > **Kết nối**.

1. Lựa chọn **Thêm kết nối** và lựa chọn **Lái tự động**.

1. Đặt tên dễ nhận biết cho kết nối trong trường **Tên hiển thị**. Tên và loại kết nối mô tả kết nối này. Bạn nên chọn một tên giải thích mục đích và mục tiêu của kết nối.

1. Chọn người có thể sử dụng kết nối này. Theo mặc định, giá trị này là quản trị viên. Để biết thêm thông tin, hãy xem [Cho phép người đóng góp sử dụng một kết nối cho các lần xuất](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Nhập khóa API Autopilot.

1. Xem lại [quyền riêng tư và tuân thủ dữ liệu](connections.md#data-privacy-and-compliance) và chọn **tôi đồng ý**.

1. Lựa chọn **Liên kết** để khởi tạo kết nối.

1. Chọn **Thêm chính bạn là người dùng xuất** và cung cấp thông tin xác thực Customer Insights.

1. Chọn **Lưu** để hoàn thành kết nối.

## <a name="configure-an-export"></a>Định cấu hình xuất

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Đi tới **Dữ liệu** > **Nội dung xuất**.

1. Lựa chọn **Thêm xuất khẩu**.

1. Trong trường **Kết nối để xuất**, hãy chọn một kết nối từ phần Autopilot. Liên hệ với quản trị viên nếu không có kết nối.

1. Nhập tên cho lần xuất.

1. Trong phần **Đối sánh dữ liệu**, trong trường **Email**, chọn trường có địa chỉ email của khách hàng.

1. Theo tùy chọn, xuất các trường khác như **tên** và **họ**.

1. Chọn các phân đoạn bạn muốn xuất theo các giới hạn đã biết.

1. Chọn **Lưu.**

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
