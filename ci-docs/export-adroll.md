---
title: Xuất phân khúc sang AdRoll (xem trước)
description: Tìm hiểu cách định cấu hình kết nối và xuất sang AdRoll.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8110eab199920ab8fc2ea15678139faf264a242a
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195776"
---
# <a name="export-segments-to-adroll-preview"></a>Xuất phân khúc sang AdRoll (xem trước)

Xuất phân khúc hồ sơ khách hàng hợp nhất sang AdRoll và sử dụng các phân khúc đó để quảng cáo.

## <a name="prerequisites"></a>Điều kiện tiên quyết

- Một [Tài khoản AdRoll](https://www.adroll.com/) và thông tin đăng nhập quản trị viên tương ứng.
- Một [ID nhà quảng cáo AdRoll](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).
- [Các phân đoạn đã định cấu hình](segments.md) trong Thông tin chi tiết về khách hàng.
- Hồ sơ khách hàng hợp nhất trong các phân khúc đã xuất chứa các trường đại diện cho địa chỉ email.

## <a name="known-limitations"></a>Các hạn chế đã biết

- Lên đến 250.000 hồ sơ khách hàng cho mỗi lần xuất sang AdRoll, có thể mất tới 10 phút để hoàn thành. Số lượng hồ sơ khách hàng mà bạn có thể xuất sang AdRoll tùy thuộc vào hợp đồng của bạn với AdRoll.
- Chỉ phân đoạn. Một phân khúc phải chứa ít nhất 100 hồ sơ khách hàng.

## <a name="set-up-connection-to-adroll"></a>Thiết lập kết nối với AdRoll

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Đi đến **Quản trị viên** > **Kết nối**.

1. Lựa chọn **Thêm kết nối** và lựa chọn **AdRoll**.

1. Đặt tên dễ nhận biết cho kết nối trong trường **Tên hiển thị**. Tên và loại kết nối mô tả kết nối này. Bạn nên chọn một tên giải thích mục đích và mục tiêu của kết nối.

1. Chọn người có thể sử dụng kết nối này. Theo mặc định, giá trị này là quản trị viên. Để biết thêm thông tin, hãy xem [Cho phép người đóng góp sử dụng một kết nối cho các lần xuất](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Xem lại [quyền riêng tư và tuân thủ dữ liệu](connections.md#data-privacy-and-compliance) và chọn **tôi đồng ý**.

1. Lựa chọn **Liên kết** để khởi tạo kết nối.

1. Chọn **Xác thực bằng AdRoll** và cung cấp thông tin đăng nhập quản trị viên cho AdRoll.

1. Chọn **Thêm chính bạn là người dùng xuất** và cung cấp thông tin xác thực Customer Insights.

1. Chọn **Lưu** để hoàn thành kết nối.

## <a name="configure-an-export"></a>Định cấu hình xuất

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Đi tới **Dữ liệu** > **Nội dung xuất**.

1. Lựa chọn **Thêm xuất khẩu**.

1. Trong trường **Kết nối để xuất**, hãy chọn một kết nối từ phần AdRoll. Liên hệ với quản trị viên nếu không có kết nối.

1. Nhập tên cho lần xuất.

1. Nhập **ID nhà quảng cáo AdRoll**.

1. Trong phần **Đối sánh dữ liệu**, trong trường **Email**, chọn trường có địa chỉ email của khách hàng.

1. Chọn phân khúc mà bạn muốn xuất.

1. Chọn **Lưu.**

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
