---
title: Xuất phân đoạn sang MoEngage
description: Tìm hiểu cách định cấu hình kết nối và xuất sang MoEngage.
ms.date: 07/26/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ffc591c01a5a9434cde41f2da25fa930a515b8c1
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 07/27/2022
ms.locfileid: "9199238"
---
# <a name="export-segments-to-moengage-preview"></a>Xuất phân đoạn sang MoEngage (xem trước)

Xuất các phân đoạn hồ sơ khách hàng thống nhất sang MoEngage và sử dụng chúng để tiếp thị qua email trong MoEngage.

## <a name="prerequisites-for-a-connection"></a>Điều kiện tiên quyết để kết nối

- [Tài khoản MoEngage](https://www.moengage.com/) và thông tin đăng nhập quản trị viên tương ứng.
- Khóa API MoEngage từ Cài đặt> API trong MoEngage.
- [Các phân đoạn đã định cấu hình](segments.md) trong Thông tin chi tiết về khách hàng.

## <a name="known-limitations"></a>Các hạn chế đã biết

- Lên đến 100.000 hồ sơ khách hàng cho mỗi lần xuất sang MoEngage, có thể mất đến 15 phút. Số lượng hồ sơ khách hàng mà bạn có thể xuất sang MoEngage tùy thuộc vào hợp đồng của bạn với MoEngage.
- Chỉ phân đoạn.

## <a name="set-up-connection-to-moengage"></a>Thiết lập kết nối với MoEngage

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Đi đến **Quản trị viên** > **Kết nối**.

1. Lựa chọn **Thêm kết nối** và lựa chọn **MoEngage** để cấu hình kết nối.

1. Đặt tên dễ nhận biết cho kết nối trong trường **Tên hiển thị**. Tên và loại kết nối mô tả kết nối này. Bạn nên chọn một tên giải thích mục đích và mục tiêu của kết nối.

1. Chọn người có thể sử dụng kết nối này. Nếu bạn không thực hiện hành động nào, giá trị mặc định sẽ là Quản trị viên. Để biết thêm thông tin, hãy xem [Cho phép người đóng góp sử dụng một kết nối cho các lần xuất](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Nhập của bạn [ID API dữ liệu MoEngage và khóa API](https://developers.moengage.com/hc/articles/4404674776724-Overview#:~:text=Navigate%20to%20Settings%20%3E%20APIs%20%3E%20DATA,ID%20Password%20%2D%20DATA%20API%20KEY).

1. Xem lại [quyền riêng tư và tuân thủ dữ liệu](connections.md#data-privacy-and-compliance) và chọn **tôi đồng ý**.

1. Lựa chọn **Liên kết** để khởi tạo kết nối với MoEngage.

1. Chọn **Thêm chính bạn là người dùng xuất** và cung cấp thông tin xác thực Customer Insights.

1. Chọn **Lưu** để hoàn thành kết nối.

## <a name="configure-an-export"></a>Định cấu hình xuất

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Đi tới **Dữ liệu** > **Nội dung xuất**.

1. Để tạo nội dung xuất mới, hãy chọn **Thêm nội dung xuất**.

1. Bên trong **Kết nối để xuất**, chọn một kết nối từ phần MoEngage. Nếu bạn không thấy tên phần này, tức là không có kết nối nào thuộc loại này dành cho bạn.

1. Trong phần **Đối sánh dữ liệu**, trong trường **Email**, chọn trường có địa chỉ email của khách hàng. Lặp lại các bước tương tự cho các trường tùy chọn khác.

1. Chọn phân khúc mà bạn muốn xuất. Chúng tôi sẽ tạo một hoặc nhiều phân đoạn có cùng tên với các phân đoạn đã chọn trong MoEngage trong **Phân đoạn** > **Phân đoạn tùy chỉnh**.

1. Chọn **Lưu.**

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
