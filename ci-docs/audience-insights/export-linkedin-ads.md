---
title: Xuất dữ liệu Customer Insights sang LinkedIn Ads
description: Tìm hiểu cách đặt cấu hình kết nối và xuất sang LinkedIn Ads.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 867a6541734746f75a35faaa8d3861e0479d6114
ms.sourcegitcommit: 9558ff772ee6c944fcb8db4bfc8cda13b38a1bff
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 11/29/2021
ms.locfileid: "7866914"
---
# <a name="export-segments-to-linkedin-ads-preview"></a>Xuất phân khúc sang LinkedIn Ads (xem trước)

Xuất phân khúc hồ sơ khách hàng hợp nhất sang LinkedIn Ads để tạo đối tượng phù hợp. Sử dụng đối tượng phù hợp để nhắm mục tiêu công ty và nhắm mục tiêu người liên hệ.

## <a name="prerequisites"></a>Điều kiện tiên quyết

-   Bạn có một [tài khoản LinkedIn Campaign Manager](https://business.linkedin.com/marketing-solutions/ads) và thông tin đăng nhập quản trị viên tương ứng.
-   Bạn có [các phân khúc đã đặt cấu hình](segments.md) trong thông tin chuyên sâu về đối tượng.
-   Hồ sơ khách hàng trong các phân khúc đã xuất chứa trường có địa chỉ email.

## <a name="known-limitations"></a>Các hạn chế đã biết

- Phân đoạn của bạn trong Thông tin chi tiết về khách hàng cần phải chứa ít nhất 300 hồ sơ duy nhất. 
- Bạn có thể xuất tối đa 100.000 hồ sơ khách hàng mỗi lần sang LinkedIn Ads.
- Bạn chỉ xuất được phân khúc sang LinkedIn Ads.
- Có thể mất tới 10 phút để hoàn tất việc xuất tối đa 100 nghìn hồ sơ khách hàng sang LinkedIn Ads. 

## <a name="set-up-the-connection-to-linkedin-ads"></a>Thiết lập kết nối với LinkedIn Ads

1. Trong thông tin chuyên sâu về đối tượng, hãy đi đến **Quản trị viên** > **Kết nối**.

1. Chọn **Thêm kết nối** rồi chọn **LinkedIn Ads** để đặt cấu hình kết nối.

1. Đặt tên dễ nhận biết cho kết nối trong trường **Tên hiển thị**. Tên và loại kết nối mô tả kết nối này. Bạn nên chọn một tên giải thích mục đích và mục tiêu của kết nối.

1. Chọn người có thể sử dụng kết nối này. Nếu bạn không làm gì cả, giá trị mặc định sẽ là quản trị viên. Để biết thêm thông tin, hãy xem [Cho phép người đóng góp sử dụng một kết nối cho các lần xuất](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Cung cấp của bạn [LinkedIn Campaign Manager ID tài khoản](https://www.linkedin.com/help/lms/answer/a424270).

1. Chọn **Tôi đồng ý** để xác nhận **Quyền riêng tư về dữ liệu và sự tuân thủ**.

1. Chọn **Kết nối** để khởi tạo kết nối với Campaign Monitor.

1. Lựa chọn **Xác thực với LinkedIn** và cung cấp thông tin đăng nhập quản trị viên của bạn cho LinkedIn Campaign Manager.

1. Chọn **Thêm chính bạn là người dùng xuất** và cung cấp thông tin xác thực Customer Insights.

1. Chọn **Lưu** để hoàn thành kết nối.

## <a name="configure-an-export"></a>Định cấu hình xuất

Bạn có thể định cấu hình nội dung xuất nếu có quyền truy cập vào kết nối thuộc loại này. Để biết thêm thông tin, hãy xem [Các quyền cần thiết để định cấu hình xuất](export-destinations.md#set-up-a-new-export).

1. Đi tới **Dữ liệu** > **Nội dung xuất**.

1. Để tạo một nội dung xuất mới, hãy chọn **Thêm đích**.

1. Trong trường **Kết nối để xuất**, hãy chọn một kết nối từ phần LinkedIn Ads. Nếu bạn không thấy tên phần này, tức là không có kết nối nào thuộc loại này dành cho bạn.

1. Chọn xem bạn muốn xuất dữ liệu để [nhắm mục tiêu người liên hệ](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) hay [nhắm mục tiêu công ty](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) trên LinkedIn. 

1. Trong phần **Đối sánh dữ liệu**, để nhắm mục tiêu theo địa chỉ liên hệ, hãy chọn ít nhất một trường đại diện cho địa chỉ email của khách hàng, ID quảng cáo Apple, ID quảng cáo của Google, ID người dùng Google hoặc họ và tên. Nếu bạn chọn nhắm mục tiêu theo công ty, hãy chọn ít nhất một trường đại diện cho tên công ty, miền email, URL trang LinkedIn, biểu tượng Stock hoặc Trang web. Các trường bổ sung có thể được chọn để xác định rõ hơn bản xuất của bạn. 

1. Chọn phân khúc mà bạn muốn xuất. Các đối tượng phù hợp trong LinkedIn Campaign Manager sẽ tự động được tạo với tên của các phân đoạn mà bạn đã chọn để xuất. Mỗi phân khúc sẽ cho ra một đối tượng phù hợp riêng biệt. 

1. Chọn **Lưu**.

Việc lưu một nội dung xuất sẽ không chạy nội dung xuất đó ngay lập tức.

Nội dung xuất chạy trong mỗi lần [làm mới theo lịch trình](system.md#schedule-tab). Bạn cũng có thể [xuất dữ liệu theo yêu cầu](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Quyền riêng tư về dữ liệu và sự tuân thủ

Khi bạn bật Dynamics 365 Customer Insights để truyền dữ liệu đến Quảng cáo trên LinkedIn, bạn cho phép chuyển dữ liệu ra bên ngoài ranh giới tuân thủ cho Dynamics 365 Customer Insights, bao gồm cả dữ liệu nhạy cảm tiềm ẩn như Dữ liệu cá nhân. Microsoft sẽ chuyển những dữ liệu đó theo chỉ dẫn của bạn, nhưng bạn có trách nhiệm đảm bảo rằng LinkedIn Ads đáp ứng mọi nghĩa vụ về quyền riêng tư hoặc bảo mật mà bạn có thể có. Để biết thêm thông tin, hãy xem [Tuyên bố về Quyền riêng tư của Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Quản trị viên Dynamics 365 Customer Insights của bạn có thể xóa đích xuất này bất kỳ lúc nào để ngừng sử dụng chức năng này.
