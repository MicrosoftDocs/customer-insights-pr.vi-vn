---
title: Xuất dữ liệu Thông tin chi tiết về khách hàng sang HubSpot
description: Tìm hiểu cách định cấu hình kết nối và xuất sang HubSpot.
ms.date: 09/23/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b34f1d54fa499f6c6b80fa547a8aaf61af3b35a1
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725380"
---
# <a name="export-segments-to-hubspot-preview"></a>Xuất phân đoạn sang HubSpot (xem trước)

Xuất các phân đoạn hồ sơ khách hàng hợp nhất sang HubSpot và sử dụng chúng cho tiếp thị qua email.

## <a name="prerequisites-for-a-connection"></a>Điều kiện tiên quyết để kết nối

- Một [Tài khoản HubSpot](https://www.hubspot.com/) và thông tin đăng nhập quản trị viên tương ứng.
- [Mã API](https://knowledge.hubspot.com/Integrations/How-do-I-get-my-HubSpot-API-key) từ HubSpot.
- [Các phân đoạn đã định cấu hình](segments.md) trong Thông tin chi tiết về khách hàng.

## <a name="known-limitations"></a>Các hạn chế đã biết

- Liên kết riêng tư kết hợp với Mang theo bộ nhớ của riêng bạn (BYOS) không được hỗ trợ.
- Lên đến 100.000 hồ sơ khách hàng cho mỗi lần xuất sang HubSpot, có thể mất tới 15 phút để hoàn thành. Số lượng hồ sơ khách hàng mà bạn có thể xuất sang HubSpot phụ thuộc và giới hạn vào hợp đồng của bạn với HubSpot.
- Chỉ phân đoạn.

## <a name="set-up-connection-to-hubspot"></a>Thiết lập kết nối với HubSpot

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Đi đến **Quản trị viên** > **Kết nối**.

1. Lựa chọn **Thêm kết nối** và lựa chọn **HubSpot** để cấu hình kết nối.

1. Đặt tên dễ nhận biết cho kết nối trong trường **Tên hiển thị**. Tên và loại kết nối mô tả kết nối này. Bạn nên chọn một tên giải thích mục đích và mục tiêu của kết nối.

1. Chọn người có thể sử dụng kết nối này. Nếu bạn không thực hiện hành động nào, giá trị mặc định sẽ là Quản trị viên. Để biết thêm thông tin, hãy xem [Cho phép người đóng góp sử dụng một kết nối cho các lần xuất](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Nhập thông tin đăng nhập HubSpot của bạn khi được nhắc.

1. Xem lại [quyền riêng tư và tuân thủ dữ liệu](connections.md#data-privacy-and-compliance) và chọn **tôi đồng ý**.

1. Lựa chọn **Liên kết** để khởi tạo kết nối tới HubSpot.

1. Chọn **Thêm chính bạn là người dùng xuất** và cung cấp thông tin xác thực Customer Insights.

1. Chọn **Lưu** để hoàn thành kết nối.

## <a name="configure-an-export"></a>Định cấu hình xuất

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Đi tới **Dữ liệu** > **Nội dung xuất**.

1. Để tạo nội dung xuất mới, hãy chọn **Thêm nội dung xuất**.

1. Bên trong **Kết nối để xuất**, chọn một kết nối từ phần HubSpot. Nếu bạn không thấy tên phần này, tức là không có kết nối nào thuộc loại này dành cho bạn.

1. Trong phần **Đối sánh dữ liệu**, trong trường **Email**, chọn trường có địa chỉ email của khách hàng. Lặp lại các bước tương tự cho các trường tùy chọn khác.

1. Chọn phân khúc mà bạn muốn xuất.

1. Chọn **Lưu.**

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
