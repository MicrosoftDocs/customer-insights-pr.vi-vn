---
title: Xuất phân đoạn sang Klaviyo (xem trước)
description: Tìm hiểu cách định cấu hình kết nối và xuất sang Klaviyo.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 075e6758f2c6992a1185756f9beecf852fdd0a96
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724659"
---
# <a name="export-segments-to-klaviyo-preview"></a>Xuất phân đoạn sang Klaviyo (xem trước)

Xuất phân khúc hồ sơ khách hàng hợp nhất sang Klaviyo và sử dụng chúng cho các hoạt động tiếp thị.

## <a name="prerequisites"></a>Điều kiện tiên quyết

- Một [Tài khoản Klaviyo](https://www.klaviyo.com/) và thông tin đăng nhập quản trị viên tương ứng.
- Một [Khóa API Klaviyo](https://help.klaviyo.com/hc/articles/115005062267-How-to-Manage-Your-Account-s-API-Keys).
- Một [ID danh sách Klaviyo](https://help.klaviyo.com/hc/articles/115005078647-How-to-Find-a-List-ID).
- [Các phân đoạn đã định cấu hình](segments.md) trong Thông tin chi tiết về khách hàng.
- Hồ sơ khách hàng hợp nhất trong các phân khúc đã xuất chứa các trường đại diện cho địa chỉ email.

## <a name="known-limitations"></a>Các hạn chế đã biết

- Liên kết riêng tư kết hợp với Mang theo bộ nhớ của riêng bạn (BYOS) không được hỗ trợ.
- Lên đến 1 triệu hồ sơ khách hàng cho mỗi lần xuất sang Klaviyo, có thể mất tới 20 phút để hoàn thành. Số lượng hồ sơ khách hàng mà bạn có thể xuất sang Klaviyo tùy thuộc vào hợp đồng của bạn với Klaviyo.
- Chỉ phân đoạn.

## <a name="set-up-connection-to-klaviyo"></a>Thiết lập kết nối đến Klaviyo

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Đi đến **Quản trị viên** > **Kết nối**.

1. Lựa chọn **Thêm kết nối** và lựa chọn **Klaviyo**.

1. Đặt tên dễ nhận biết cho kết nối trong trường **Tên hiển thị**. Tên và loại kết nối mô tả kết nối này. Bạn nên chọn một tên giải thích mục đích và mục tiêu của kết nối.

1. Chọn người có thể sử dụng kết nối này. Theo mặc định, giá trị này là quản trị viên. Để biết thêm thông tin, hãy xem [Cho phép người đóng góp sử dụng một kết nối cho các lần xuất](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Cung cấp khóa API Klaviyo của bạn để tiếp tục đăng nhập.

1. Xem lại [quyền riêng tư và tuân thủ dữ liệu](connections.md#data-privacy-and-compliance) và chọn **tôi đồng ý**.

1. Lựa chọn **Liên kết** để khởi tạo kết nối.

1. Chọn **Xác thực với Klaviyo** và cung cấp thông tin đăng nhập quản trị viên của bạn cho Klaviyo.

1. Chọn **Thêm chính bạn là người dùng xuất** và cung cấp thông tin xác thực Customer Insights.

1. Chọn **Lưu** để hoàn thành kết nối.

## <a name="configure-an-export"></a>Định cấu hình xuất

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Đi tới **Dữ liệu** > **Nội dung xuất**.

1. Lựa chọn **Thêm xuất khẩu**.

1. Trong trường **Kết nối để xuất**, hãy chọn một kết nối từ phần Klaviyo. Liên hệ với quản trị viên nếu không có kết nối.

1. Nhập tên cho lần xuất.

1. Nhập của bạn **ID danh sách Klaviyo**.

1. Trong phần **Đối sánh dữ liệu**, trong trường **Email**, chọn trường có địa chỉ email của khách hàng.

1. Chọn phân khúc mà bạn muốn xuất.

1. Chọn **Lưu.**

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
