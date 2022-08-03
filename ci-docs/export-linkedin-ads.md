---
title: Xuất phân khúc sang LinkedIn Ads (xem trước)
description: Tìm hiểu cách đặt cấu hình kết nối và xuất sang LinkedIn Ads.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d1a9ae985043398f4bc38163be26ecf0c3c8e2ba
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196834"
---
# <a name="export-segments-to-linkedin-ads-preview"></a>Xuất phân khúc sang LinkedIn Ads (xem trước)

Xuất phân khúc hồ sơ khách hàng hợp nhất sang LinkedIn Ads để tạo đối tượng phù hợp. Sử dụng đối tượng phù hợp để nhắm mục tiêu công ty và nhắm mục tiêu người liên hệ.

## <a name="prerequisites"></a>Điều kiện tiên quyết

- Một [LinkedIn Campaign Manager tài khoản](https://business.linkedin.com/marketing-solutions/ads) và thông tin đăng nhập quản trị viên tương ứng.
- Một [LinkedIn Campaign Manager ID tài khoản](https://www.linkedin.com/help/lms/answer/a424270).
- [Các phân đoạn đã định cấu hình](segments.md) trong Thông tin chi tiết về khách hàng.
- Hồ sơ khách hàng hợp nhất trong các phân khúc đã xuất chứa các trường đại diện cho địa chỉ email.

## <a name="known-limitations"></a>Các hạn chế đã biết

- Lên đến 100.000 hồ sơ khách hàng cho mỗi lần xuất sang Quảng cáo LinkedIn, có thể mất tới 10 phút để hoàn thành.
- Chỉ phân đoạn. Một phân đoạn phải chứa ít nhất 300 cấu hình duy nhất.

## <a name="set-up-connection-to-linkedin-ads"></a>Thiết lập kết nối với Quảng cáo LinkedIn

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Đi đến **Quản trị viên** > **Kết nối**.

1. Lựa chọn **Thêm kết nối** và lựa chọn **Quảng cáo LinkedIn**.

1. Đặt tên dễ nhận biết cho kết nối trong trường **Tên hiển thị**. Tên và loại kết nối mô tả kết nối này. Bạn nên chọn một tên giải thích mục đích và mục tiêu của kết nối.

1. Chọn người có thể sử dụng kết nối này. Theo mặc định, giá trị này là quản trị viên. Để biết thêm thông tin, hãy xem [Cho phép người đóng góp sử dụng một kết nối cho các lần xuất](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Cung cấp của bạn LinkedIn Campaign Manager ID tài khoản.

1. Xem lại [quyền riêng tư và tuân thủ dữ liệu](connections.md#data-privacy-and-compliance) và chọn **tôi đồng ý**.

1. Lựa chọn **Liên kết** để khởi tạo kết nối.

1. Chọn **Xác thực với LinkedIn** và cung cấp thông tin xác thực quản trị viên của bạn cho LinkedIn Campaign Manager.

1. Chọn **Thêm chính bạn là người dùng xuất** và cung cấp thông tin xác thực Customer Insights.

1. Chọn **Lưu** để hoàn thành kết nối.

## <a name="configure-an-export"></a>Định cấu hình xuất

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Đi tới **Dữ liệu** > **Nội dung xuất**.

1. Lựa chọn **Thêm xuất khẩu**.

1. Trong trường **Kết nối để xuất**, hãy chọn một kết nối từ phần LinkedIn Ads. Liên hệ với quản trị viên nếu không có kết nối.

1. Nhập tên cho lần xuất.

1. Chọn xem bạn muốn xuất dữ liệu để [nhắm mục tiêu người liên hệ](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) hay [nhắm mục tiêu công ty](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) trên LinkedIn.

1. Trong phần **Đối sánh dữ liệu**, để nhắm mục tiêu theo địa chỉ liên hệ, hãy chọn ít nhất một trường đại diện cho địa chỉ email của khách hàng, ID quảng cáo Apple, ID quảng cáo của Google, ID người dùng Google hoặc họ và tên. Nếu bạn chọn nhắm mục tiêu theo công ty, hãy chọn ít nhất một trường đại diện cho tên công ty, miền email, URL trang LinkedIn, biểu tượng Stock hoặc Trang web.

1. Theo tùy chọn, thêm các trường để xác định rõ hơn quá trình xuất của bạn. Chọn **Thêm thuộc tính** để ánh xạ những trường này.

1. Chọn phân khúc mà bạn muốn xuất. Đối tượng phù hợp trong LinkedIn Campaign Manager sẽ được tạo tự động với tên của các phân khúc mà bạn đã chọn để xuất. Mỗi phân khúc sẽ cho ra một đối tượng phù hợp riêng biệt.

1. Chọn **Lưu.**

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
