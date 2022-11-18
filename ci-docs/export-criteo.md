---
title: Xuất phân đoạn sang Criteo (xem trước)
description: Tìm hiểu cách định cấu hình kết nối và xuất sang Criteo.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 811752da943cd5e40608d48644a1744c7971d3c8
ms.sourcegitcommit: 40ae3322ac95913e485607494754dd03814e42bb
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 11/11/2022
ms.locfileid: "9760053"
---
# <a name="export-segments-to-criteo-preview"></a>Xuất phân đoạn sang Criteo (xem trước)

Xuất các phân đoạn hồ sơ khách hàng hợp nhất để tạo chiến dịch, cung cấp tiếp thị qua email và sử dụng các nhóm khách hàng cụ thể với Criteo.

## <a name="prerequisites"></a>Điều kiện tiên quyết

- Một [Tài khoản nhắm mục tiêu lại Criteo Dynamics](https://www.criteo.com/login/) và thông tin xác thực quản trị viên tương ứng.
- [Các phân đoạn được định cấu hình](segments.md).
- Hồ sơ khách hàng hợp nhất trong các phân khúc đã xuất chứa các trường đại diện cho địa chỉ email.

## <a name="known-limitations"></a>Các hạn chế đã biết

- Tối đa 1 triệu hồ sơ khách hàng mỗi lần xuất sang Criteo, có thể mất tới 30 phút để hoàn thành. Số lượng hồ sơ khách hàng mà bạn có thể xuất sang Criteo tùy thuộc vào hợp đồng của bạn với Criteo.
- Chỉ phân khúc.

## <a name="set-up-connection-to-criteo"></a>Thiết lập kết nối với Criteo

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Đi đến **Quản trị viên** > **Kết nối**.

1. Lựa chọn **Thêm kết nối** và lựa chọn **Criteo**.

1. Đặt tên dễ nhận biết cho kết nối trong trường **Tên hiển thị**. Tên và loại kết nối mô tả kết nối này. Bạn nên chọn một tên giải thích mục đích và mục tiêu của kết nối.

1. Chọn người có thể sử dụng kết nối này. Theo mặc định, giá trị này là quản trị viên. Để biết thêm thông tin, hãy xem [Cho phép người đóng góp sử dụng một kết nối cho các lần xuất](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Xem lại [quyền riêng tư và tuân thủ dữ liệu](connections.md#data-privacy-and-compliance) và chọn **tôi đồng ý**.

1. Lựa chọn **Liên kết** để khởi tạo kết nối.

1. Lựa chọn **Xác thực với Criteo** và cung cấp tên người dùng và thông tin đăng nhập Quản trị viên của bạn cho Criteo.

1. Chọn **Thêm chính bạn là người dùng xuất** và cung cấp thông tin xác thực Customer Insights.

1. Chọn **Lưu** để hoàn thành kết nối.

## <a name="configure-an-export"></a>Định cấu hình xuất

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Đi tới **Dữ liệu** > **Nội dung xuất**.

1. Lựa chọn **thêm xuất khẩu**.

1. Bên trong **Kết nối xuất khẩu** trường, hãy chọn một kết nối từ phần Criteo. Liên hệ với quản trị viên nếu không có kết nối.

1. Nhập tên để xuất.

1. Trong phần **Đối sánh dữ liệu**, trong trường **Email**, chọn trường có địa chỉ email của khách hàng.

1. Chọn phân khúc mà bạn muốn xuất.

1. Chọn **Lưu.**

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
