---
title: Xuất dữ liệu Customer Insights sang Google Ads
description: Tìm hiểu cách định cấu hình kết nối và xuất sang Google Ads.
ms.date: 09/27/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: c958f58c927b76364f305dad8f524dde29b2a638
ms.sourcegitcommit: f1e3cc51ea4cf68210eaf0210ad6e14b15ac4fe8
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 09/27/2021
ms.locfileid: "7558998"
---
# <a name="export-segments-to-google-ads-preview"></a>Xuất phân khúc sang Google Ads (bản xem trước)

Xuất các phân khúc hồ sơ khách hàng hợp nhất sang danh sách đối tượng Google Ads và sử dụng chúng để quảng cáo trên Google Tìm kiếm, Gmail, YouTube và Google Display Network. 

> [!IMPORTANT]
> Hiện tại, bạn chỉ có thể tạo một kết nối mới và xuất dữ liệu sang Google Ads nếu bạn đã có mã thông báo Nhà phát triển Google Ads được chấp thuận. Do các thay đổi về chính sách, chúng tôi sẽ sớm cập nhật quá trình xuất Google Ads và cung cấp tùy chọn xuất không yêu cầu mã thông báo của nhà phát triển để đảm bảo trải nghiệm của bạn liên tục và đơn giản hóa quá trình xuất sang Google Ads. Chúng tôi khuyên bạn không nên thiết lập thêm kết nối với Google Ads để tạo điều kiện chuyển sang tùy chọn xuất mới dễ dàng hơn.

## <a name="prerequisites-for-connection"></a>Điều kiện tiên quyết để kết nối

-   Bạn có một [Tài khoản Google Ads](https://ads.google.com/) và thông tin đăng nhập quản trị viên tương ứng.
-   Bạn có một [Mã thông báo Nhà phát triển Google Ads được chấp thuận](https://developers.google.com/google-ads/api/docs/first-call/dev-token). 
-   Bạn đáp ứng các yêu cầu của [Chính sách đối sánh khách hàng](https://support.google.com/adspolicy/answer/6299717).
-   Bạn đáp ứng các yêu cầu về [kích thước danh sách tiếp thị lại](https://support.google.com/google-ads/answer/7558048).
-   Có đối tượng hiện có trong Google Ads và các ID tương ứng. Để biết thêm thông tin, hãy xem [Đối tượng Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).
-   Bạn có [các phân khúc được định cấu hình](segments.md).
-   Hồ sơ khách hàng hợp nhất trong các phân khúc đã xuất chứa các trường đại diện cho địa chỉ email, tên và họ.

## <a name="known-limitations"></a>Các hạn chế đã biết

- Lên đến 1 triệu hồ sơ mỗi lần xuất sang Google Ads.
- Việc xuất sang Google Ads bị giới hạn ở các phân khúc.
- Việc xuất các phân khúc với tổng số 1 triệu hồ sơ có thể mất đến 5 phút vì những hạn chế từ phía nhà cung cấp. 
- Quá trình so khớp trong Google Ads có thể mất đến 48 giờ.

## <a name="set-up-connection-to-google-ads"></a>Thiết lập kết nối với Google Ads

1. Đi đến **Quản trị viên** > **Kết nối**.

1. Chọn **Thêm kết nối** rồi chọn **Google Ads** để định cấu hình kết nối.

1. Đặt tên dễ nhận biết cho kết nối trong trường **Tên hiển thị**. Tên và loại kết nối mô tả kết nối này. Bạn nên chọn một tên giải thích mục đích và mục tiêu của kết nối.

1. Chọn người có thể sử dụng kết nối này. Nếu bạn không thực hiện hành động nào, giá trị mặc định sẽ là Quản trị viên. Để biết thêm thông tin, hãy xem [Cho phép người đóng góp sử dụng một kết nối cho các lần xuất](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Nhập **[ID khách hàng Google Ads](https://support.google.com/google-ads/answer/1704344)**.

1. Nhập **[Mã thông báo nhà phát triển được Google Ads phê duyệt](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.

1. Chọn **Tôi đồng ý** để xác nhận **Quyền riêng tư về dữ liệu và sự tuân thủ**.

1. Chọn **Xác thực bằng Google Ads** và cung cấp thông tin đăng nhập Google Ads của bạn.

1. Chọn **Thêm chính bạn là người dùng xuất** và cung cấp thông tin xác thực Customer Insights.

1. Chọn **Lưu** để hoàn thành kết nối. 

## <a name="configure-an-export"></a>Định cấu hình xuất

Bạn có thể định cấu hình lần xuất này nếu bạn có quyền truy cập vào kết nối thuộc loại này. Để biết thêm thông tin, hãy xem [Các quyền cần thiết để định cấu hình xuất](export-destinations.md#set-up-a-new-export).

1. Đi tới **Dữ liệu** > **Nội dung xuất**.

1. Để tạo một nội dung xuất mới, hãy chọn **Thêm đích**.

1. Trong trường **Kết nối để xuất**, hãy chọn một kết nối từ phần Google Ads. Nếu bạn không thấy tên phần này thì có nghĩa là không có kết nối nào thuộc loại này khả dụng cho bạn.

1. Nhập **[ID đối tượng Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** và chọn **Kết nối** để khởi tạo kết nối với Google Ads.

1. Trong phần **So khớp dữ liệu**, trong trường **Email**, chọn trường trong hồ sơ khách hàng hợp nhất trình bày địa chỉ email của khách hàng.

1. Chọn phân khúc mà bạn muốn xuất. Bạn có thể xuất tổng cộng tối đa 1 triệu hồ sơ khách hàng sang Google Ads.

Việc lưu một nội dung xuất sẽ không chạy nội dung xuất đó ngay lập tức.

Nội dung xuất chạy trong mỗi lần [làm mới theo lịch trình](system.md#schedule-tab). 

Bạn cũng có thể [xuất dữ liệu theo yêu cầu](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Quyền riêng tư về dữ liệu và sự tuân thủ

Khi bật Dynamics 365 Customer Insights để truyền dữ liệu tới Google Ads, bạn cho phép chuyển dữ liệu ra bên ngoài ranh giới tuân thủ cho Dynamics 365 Customer Insights, bao gồm dữ liệu nhạy cảm tiềm ẩn như Dữ liệu cá nhân. Microsoft sẽ chuyển những dữ liệu đó theo chỉ dẫn của bạn, nhưng bạn có trách nhiệm đảm bảo rằng Google Ads đáp ứng mọi nghĩa vụ về quyền riêng tư hoặc bảo mật mà bạn có thể có. Để biết thêm thông tin, hãy xem [Tuyên bố về Quyền riêng tư của Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Quản trị viên Dynamics 365 Customer Insights của bạn có thể xóa đích xuất này bất cứ lúc nào để ngừng việc sử dụng chức năng này.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
