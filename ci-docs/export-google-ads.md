---
title: Xuất phân khúc sang Google Ads (bản xem trước)
description: Tìm hiểu cách định cấu hình kết nối và xuất sang Google Ads.
ms.date: 07/25/2022
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: a46623e609665f8031f223593a6644147e5209d8
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725104"
---
# <a name="export-segments-to-google-ads-preview"></a>Xuất phân khúc sang Google Ads (bản xem trước)

Xuất các phân khúc hồ sơ khách hàng hợp nhất sang danh sách đối tượng Google Ads và sử dụng chúng để quảng cáo trên Google Tìm kiếm, Gmail, YouTube và Google Display Network.

## <a name="prerequisites"></a>Điều kiện tiên quyết

- Một [Tài khoản Google Ads](https://ads.google.com/) và thông tin đăng nhập quản trị viên tương ứng.
- Một [ID khách hàng Google Ads](https://support.google.com/google-ads/answer/1704344).
- Các yêu cầu của [Chính sách Đối sánh Khách hàng](https://support.google.com/adspolicy/answer/6299717) được đáp ứng.
- Các yêu cầu của [kích thước danh sách tiếp thị lại](https://support.google.com/google-ads/answer/7558048) được đáp ứng.
- [Các phân đoạn đã định cấu hình](segments.md).
- Hồ sơ khách hàng hợp nhất trong các phân đoạn đã xuất chứa các trường đại diện cho địa chỉ email, điện thoại, ID nhà quảng cáo trên thiết bị di động, ID người dùng bên thứ ba hoặc địa chỉ.

## <a name="known-limitations"></a>Các hạn chế đã biết

- Liên kết riêng tư kết hợp với Mang theo bộ nhớ của riêng bạn (BYOS) không được hỗ trợ.
- Xuất tối đa 1 triệu hồ sơ khách hàng cho mỗi lần xuất sang Google Ads. Quá trình này có thể mất tới 30 phút để hoàn thành do các giới hạn từ phía nhà cung cấp.
- Chỉ phân đoạn.
- Đối sánh trong Google Ads có thể mất đến 48 giờ.

## <a name="set-up-connection-to-google-ads"></a>Thiết lập kết nối với Google Ads

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Đi đến **Quản trị viên** > **Kết nối**.

1. Lựa chọn **Thêm kết nối** và lựa chọn **Google Ads**.

1. Đặt tên dễ nhận biết cho kết nối trong trường **Tên hiển thị**. Tên và loại kết nối mô tả kết nối này. Bạn nên chọn một tên giải thích mục đích và mục tiêu của kết nối.

1. Chọn người có thể sử dụng kết nối này. Theo mặc định, giá trị này là quản trị viên. Để biết thêm thông tin, hãy xem [Cho phép người đóng góp sử dụng một kết nối cho các lần xuất](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Nhập ID khách hàng Google Ads của bạn.

1. Xem lại [quyền riêng tư và tuân thủ dữ liệu](connections.md#data-privacy-and-compliance) và chọn **tôi đồng ý**.

1. Chọn **Xác thực bằng Google Ads** và cung cấp thông tin đăng nhập Google Ads của bạn.

1. Chọn **Thêm chính bạn là người dùng xuất** và cung cấp thông tin xác thực Customer Insights.

1. Chọn **Lưu** để hoàn thành kết nối.

## <a name="configure-an-export"></a>Định cấu hình xuất

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Đi tới **Dữ liệu** > **Nội dung xuất**.

1. Lựa chọn **Thêm xuất khẩu**.

1. Trong trường **Kết nối để xuất**, hãy chọn một kết nối từ phần Google Ads. Liên hệ với quản trị viên nếu không có kết nối.

1. Nhập tên cho lần xuất.

1. Chọn sử dụng đối tượng hiện có hay tạo đối tượng mới:
   - Để cập nhật đối tượng Google Ads hiện có, hãy nhập [ID đối tượng Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns).
   - Để tạo đối tượng mới, hãy để trống trường ID đối tượng của Google. Thông tin chi tiết về khách hàng sẽ tự động tạo đối tượng mới trong tài khoản Google Ads của bạn và sử dụng tên của phân khúc đã xuất.

1. Bên trong **Đối sánh dữ liệu**, chọn một hoặc nhiều trường dữ liệu để xuất và chọn trường đại diện cho các trường dữ liệu tương ứng trong Thông tin chi tiết về khách hàng.

1. Chọn phân khúc mà bạn muốn xuất.

1. Chọn **Lưu.**

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
