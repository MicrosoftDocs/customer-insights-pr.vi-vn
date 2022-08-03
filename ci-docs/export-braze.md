---
title: Xuất phân đoạn sang Braze (xem trước)
description: Tìm hiểu cách định cấu hình kết nối và xuất sang Braze.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 84dc7f13f30e0334d431fe5b5866c7f87e82ab27
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195133"
---
# <a name="export-segments-to-braze-preview"></a>Xuất phân đoạn sang Braze (xem trước)

Xuất các phân đoạn hồ sơ khách hàng hợp nhất sang Braze và sử dụng chúng cho các hoạt động tiếp thị.

## <a name="prerequisites"></a>Điều kiện tiên quyết

- Một [Braze tài khoản](https://www.braze.com/) và thông tin đăng nhập quản trị viên tương ứng.
- Một [Khóa API Braze](https://www.braze.com/docs/api/basics/)
- [Các phân đoạn đã định cấu hình](segments.md) trong Thông tin chi tiết về khách hàng.
- Hồ sơ khách hàng hợp nhất trong các phân đoạn đã xuất chứa trường đại diện cho địa chỉ email và ID khách hàng Braze.

## <a name="known-limitations"></a>Các hạn chế đã biết

- Lên 1 triệu hồ sơ khách hàng cho Braze, có thể mất tới 40 phút để hoàn thành. Số lượng hồ sơ khách hàng mà bạn có thể xuất sang Braze tùy thuộc vào hợp đồng của bạn với Braze.
- Chỉ phân đoạn.

## <a name="set-up-connection-to-braze"></a>Thiết lập kết nối với Braze

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Đi đến **Quản trị viên** > **Kết nối**.

1. Lựa chọn **Thêm kết nối** và lựa chọn **Phanh**.

1. Đặt tên dễ nhận biết cho kết nối trong trường **Tên hiển thị**. Tên và loại kết nối mô tả kết nối này. Bạn nên chọn một tên giải thích mục đích và mục tiêu của kết nối.

1. Chọn người có thể sử dụng kết nối này. Theo mặc định, giá trị này là quản trị viên. Để biết thêm thông tin, hãy xem [Cho phép người đóng góp sử dụng một kết nối cho các lần xuất](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Cung cấp khóa API Braze của bạn để tiếp tục đăng nhập.

1. Xem lại [quyền riêng tư và tuân thủ dữ liệu](connections.md#data-privacy-and-compliance) và chọn **tôi đồng ý**.

1. Lựa chọn **Liên kết** để khởi tạo kết nối.

1. Chọn **Thêm chính bạn là người dùng xuất** và cung cấp thông tin xác thực Customer Insights.

1. Chọn **Lưu** để hoàn thành kết nối.

## <a name="configure-an-export"></a>Định cấu hình xuất

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Đi tới **Dữ liệu** > **Nội dung xuất**.

1. Lựa chọn **Thêm xuất khẩu**.

1. Bên trong **Kết nối để xuất**, hãy chọn một kết nối từ phần Braze. Liên hệ với quản trị viên nếu không có kết nối.

1. Nhập tên cho lần xuất.

1. Trong phần **Đối sánh dữ liệu**, trong trường **Email**, chọn trường có địa chỉ email của khách hàng. Bên trong **ID khách hàng**, chọn trường đại diện cho Braze ID của khách hàng. Các phân đoạn trong Braze sẽ được tạo với cùng tên của phân đoạn như trong Dynamics 365 Customer Insights. Bạn có thể chọn thêm, các trường tùy chọn để khớp dữ liệu.

1. Chọn các thực thể hoặc phân đoạn bạn muốn xuất.

1. Chọn **Lưu.**

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
