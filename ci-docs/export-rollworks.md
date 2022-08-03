---
title: Xuất phân khúc sang RollWorks (xem trước)
description: Tìm hiểu cách đặt cấu hình kết nối và xuất sang RollWorks.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e13aeca4ee5309f85e7de2986cd1a2ba5d2992fb
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195638"
---
# <a name="export-segments-to-rollworks-preview"></a>Xuất phân khúc sang RollWorks (xem trước)

Xuất các phân khúc hồ sơ khách hàng hợp nhất sang RollWorks và sử dụng chúng cho quảng cáo.

## <a name="prerequisites"></a>Điều kiện tiên quyết

- Một [Tài khoản RollWorks](https://www.rollworks.com/) và thông tin đăng nhập quản trị viên tương ứng.
- Một [ID nhà quảng cáo RollWorks](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).
- [Các phân đoạn đã định cấu hình](segments.md) trong Thông tin chi tiết về khách hàng.
- Hồ sơ khách hàng hợp nhất trong các phân khúc đã xuất chứa các trường đại diện cho địa chỉ email.

## <a name="known-limitations"></a>Các hạn chế đã biết

- Lên đến 250.000 hồ sơ khách hàng cho mỗi lần xuất sang RollWorks, có thể mất tới 10 phút để hoàn thành. Số lượng hồ sơ khách hàng mà bạn có thể xuất sang RollWorks tùy thuộc vào hợp đồng của bạn với RollWorks.
- Chỉ phân đoạn.

## <a name="set-up-connection-to-rollworks"></a>Thiết lập kết nối với RollWorks

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Đi đến **Quản trị viên** > **Kết nối**.

1. Lựa chọn **Thêm kết nối** và lựa chọn **RollWorks**.

1. Đặt tên dễ nhận biết cho kết nối trong trường **Tên hiển thị**. Tên và loại kết nối mô tả kết nối này. Bạn nên chọn một tên giải thích mục đích và mục tiêu của kết nối.

1. Chọn người có thể sử dụng kết nối này.  Theo mặc định, giá trị này là quản trị viên. Để biết thêm thông tin, hãy xem [Cho phép người đóng góp sử dụng một kết nối cho các lần xuất](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Xem lại [quyền riêng tư và tuân thủ dữ liệu](connections.md#data-privacy-and-compliance) và chọn **tôi đồng ý**.

1. Lựa chọn **Liên kết** để khởi tạo kết nối.

1. Chọn **Xác thực với RollWorks** và cung cấp thông tin xác thực quản trị viên của bạn cho RollWorks.

1. Chọn **Thêm chính bạn là người dùng xuất** và cung cấp thông tin xác thực Customer Insights.

1. Chọn **Lưu** để hoàn thành kết nối.

## <a name="configure-an-export"></a>Định cấu hình xuất

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Đi tới **Dữ liệu** > **Nội dung xuất**.

1. Lựa chọn **Thêm xuất khẩu**.

1. Trong trường **Kết nối để xuất**, hãy chọn một kết nối từ phần RollWorks. Liên hệ với quản trị viên nếu không có kết nối.

1. Nhập tên cho lần xuất.

1. Nhập của bạn **ID nhà quảng cáo RollWorks**.

1. Trong phần **Đối sánh dữ liệu**, trong trường **Email**, chọn trường có địa chỉ email của khách hàng.

1. Chọn phân khúc mà bạn muốn xuất.

1. Chọn **Lưu.**

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
