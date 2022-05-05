---
title: Xuất dữ liệu Customer Insights sang Google Ads
description: Tìm hiểu cách định cấu hình kết nối và xuất sang Google Ads.
ms.date: 03/31/2022
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 3e0eb91be97d69a999e90708d29c572f0055527e
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 04/27/2022
ms.locfileid: "8644062"
---
# <a name="export-segments-to-google-ads-preview"></a>Xuất phân khúc sang Google Ads (bản xem trước)

Xuất các phân khúc hồ sơ khách hàng hợp nhất sang danh sách đối tượng Google Ads và sử dụng chúng để quảng cáo trên Google Tìm kiếm, Gmail, YouTube và Google Display Network. 


## <a name="prerequisites-for-connection"></a>Điều kiện tiên quyết để kết nối

-   Bạn có một [Tài khoản Google Ads](https://ads.google.com/) và thông tin đăng nhập quản trị viên tương ứng.
-   Bạn đáp ứng các yêu cầu của [Chính sách đối sánh khách hàng](https://support.google.com/adspolicy/answer/6299717).
-   Bạn đáp ứng các yêu cầu về [kích thước danh sách tiếp thị lại](https://support.google.com/google-ads/answer/7558048).
-   Bạn có [các phân đoạn được định cấu hình](segments.md).
-   Hồ sơ khách hàng hợp nhất trong các phân đoạn đã xuất chứa các trường đại diện cho địa chỉ email, điện thoại, ID nhà quảng cáo trên thiết bị di động, ID người dùng bên thứ ba hoặc địa chỉ.

## <a name="known-limitations"></a>Các hạn chế đã biết

- Việc xuất sang Google Ads bị giới hạn ở các phân khúc.
- Việc xuất các phân khúc với tổng số 1 triệu hồ sơ khách hàng có thể mất tới 30 phút vì những giới hạn từ phía nhà cung cấp. 
- Quá trình so khớp trong Google Ads có thể mất đến 48 giờ.

## <a name="set-up-connection-to-google-ads"></a>Thiết lập kết nối với Google Ads

1. Đi đến **Quản trị viên** > **Kết nối**.

1. Chọn **Thêm kết nối** rồi chọn **Google Ads** để định cấu hình kết nối.

1. Đặt tên dễ nhận biết cho kết nối trong trường **Tên hiển thị**. Tên và loại kết nối mô tả kết nối này. Bạn nên chọn một tên giải thích mục đích và mục tiêu của kết nối.

1. Chọn người có thể sử dụng kết nối này. Nếu bạn không thực hiện hành động nào, giá trị mặc định sẽ là Quản trị viên. Để biết thêm thông tin, hãy xem [Cho phép người đóng góp sử dụng một kết nối cho các lần xuất](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Nhập **[ID khách hàng Google Ads](https://support.google.com/google-ads/answer/1704344)**.

1. Chọn **Tôi đồng ý** để xác nhận **Quyền riêng tư về dữ liệu và sự tuân thủ**.

1. Chọn **Xác thực bằng Google Ads** và cung cấp thông tin đăng nhập Google Ads của bạn.

1. Chọn **Thêm chính bạn là người dùng xuất** và cung cấp thông tin xác thực Customer Insights.

1. Chọn **Lưu** để hoàn thành kết nối. 

## <a name="configure-an-export"></a>Định cấu hình xuất

Bạn có thể định cấu hình lần xuất này nếu bạn có quyền truy cập vào kết nối thuộc loại này. Để biết thêm thông tin, hãy xem [Các quyền cần thiết để định cấu hình xuất](export-destinations.md#set-up-a-new-export).

1. Đi tới **Dữ liệu** > **Nội dung xuất**.

1. Để tạo một nội dung xuất mới, hãy chọn **Thêm đích**.

1. Trong trường **Kết nối để xuất**, hãy chọn một kết nối từ phần Google Ads. Nếu bạn không thấy tên phần này thì có nghĩa là không có kết nối nào thuộc loại này khả dụng cho bạn.

1. Nếu bạn muốn tạo đối tượng mới, hãy để trống trường ID đối tượng của Google. Chúng tôi sẽ tự động tạo đối tượng mới trong tài khoản Google Ads của bạn và sử dụng tên của phân khúc đã xuất. Nếu bạn muốn cập nhật đối tượng Google Ads hiện có, hãy nhập [ID đối tượng Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)

1. Bên trong **Đối sánh dữ liệu**, chọn một hoặc nhiều trường dữ liệu để xuất và chọn trường đại diện cho các trường dữ liệu tương ứng trong Thông tin chi tiết về khách hàng.

1. Chọn phân khúc mà bạn muốn xuất. 

Việc lưu một nội dung xuất sẽ không chạy nội dung xuất đó ngay lập tức.

Nội dung xuất chạy trong mỗi lần [làm mới theo lịch trình](system.md#schedule-tab). 

Bạn cũng có thể [xuất dữ liệu theo yêu cầu](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Quyền riêng tư về dữ liệu và sự tuân thủ

Khi bật Dynamics 365 Customer Insights để truyền dữ liệu tới Google Ads, bạn cho phép chuyển dữ liệu ra bên ngoài ranh giới tuân thủ cho Dynamics 365 Customer Insights, bao gồm dữ liệu nhạy cảm tiềm ẩn như Dữ liệu cá nhân. Microsoft sẽ chuyển những dữ liệu đó theo chỉ dẫn của bạn, nhưng bạn có trách nhiệm đảm bảo rằng Google Ads đáp ứng mọi nghĩa vụ về quyền riêng tư hoặc bảo mật mà bạn có thể có. Để biết thêm thông tin, hãy xem [Tuyên bố về Quyền riêng tư của Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Quản trị viên Dynamics 365 Customer Insights của bạn có thể xóa đích xuất này bất cứ lúc nào để ngừng việc sử dụng chức năng này.


[!INCLUDE [footer-include](includes/footer-banner.md)]
