---
title: Xuất dữ liệu Customer Insights sang AdRoll
description: Tìm hiểu cách định cấu hình kết nối và xuất sang AdRoll.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f9373ea18e77723c988392a5a2959baa66d8eae9
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 10/08/2021
ms.locfileid: "7617425"
---
# <a name="export-segments-to-adroll-preview"></a>Xuất phân khúc sang AdRoll (xem trước)

Xuất phân khúc hồ sơ khách hàng hợp nhất sang AdRoll và sử dụng các phân khúc đó để quảng cáo. 

## <a name="prerequisites-for-a-connection"></a>Điều kiện tiên quyết để kết nối

-   Bạn có một [tài khoản AdRoll](https://www.adroll.com/) và thông tin đăng nhập tương ứng của quản trị viên.
-   Bạn có [các phân khúc được định cấu hình](segments.md) trong thông tin chuyên sâu về đối tượng.
-   Hồ sơ khách hàng hợp nhất trong các phân khúc đã xuất chứa các trường đại diện cho địa chỉ email.

## <a name="known-limitations"></a>Các hạn chế đã biết

- Bạn có thể xuất tối đa 250.000 hồ sơ khách hàng cùng một lúc sang AdRoll.
- Bạn không thể xuất các phân khúc có ít hơn 100 hồ sơ khách hàng sang AdRoll. 
- Bạn chỉ xuất được phân khúc sang AdRoll.
- Có thể mất tới 10 phút để hoàn tất việc xuất tối đa 250.000 hồ sơ khách hàng sang AdRoll. 
- Số lượng hồ sơ khách hàng mà bạn có thể xuất sang AdRoll tùy thuộc vào hợp đồng của bạn với AdRoll.

## <a name="set-up-connection-to-adroll"></a>Thiết lập kết nối với AdRoll

1. Đi đến **Quản trị viên** > **Kết nối**.

1. Chọn **Thêm kết nối** rồi chọn **AdRoll** để định cấu hình kết nối.

1. Đặt tên dễ nhận biết cho kết nối trong trường **Tên hiển thị**. Tên và loại kết nối mô tả kết nối này. Bạn nên chọn một tên giải thích mục đích và mục tiêu của kết nối.

1. Chọn người có thể sử dụng kết nối này. Nếu bạn không thực hiện hành động nào, giá trị mặc định sẽ là Quản trị viên. Để biết thêm thông tin, hãy xem [Cho phép người đóng góp sử dụng một kết nối cho các lần xuất](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Chọn **Tôi đồng ý** để xác nhận **Quyền riêng tư về dữ liệu và sự tuân thủ**.

1. Chọn **Kết nối** để khởi tạo kết nối với AdRoll.

1. Chọn **Xác thực bằng AdRoll** và cung cấp thông tin đăng nhập quản trị viên cho AdRoll. 

1. Chọn **Thêm chính bạn là người dùng xuất** và cung cấp thông tin xác thực Customer Insights.

1. Chọn **Lưu** để hoàn thành kết nối.

## <a name="configure-an-export"></a>Định cấu hình xuất

Bạn có thể định cấu hình lần xuất này nếu bạn có quyền truy cập vào kết nối thuộc loại này. Để biết thêm thông tin, hãy xem [Các quyền cần thiết để định cấu hình xuất](export-destinations.md#set-up-a-new-export).

1. Đi tới **Dữ liệu** > **Nội dung xuất**.

1. Để tạo một nội dung xuất mới, hãy chọn **Thêm đích**.

1. Trong trường **Kết nối để xuất**, hãy chọn một kết nối từ phần AdRoll. Nếu bạn không thấy tên phần này thì có nghĩa là không có kết nối nào thuộc loại này khả dụng cho bạn.

1. Nhập **ID nhà quảng cáo AdRoll**. Để biết thêm thông tin, hãy xem [Hồ sơ Nhà quảng cáo AdRoll](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).

1. Trong phần **Đối sánh dữ liệu**, trong trường **Email**, chọn trường có địa chỉ email của khách hàng. Bắt buộc phải xuất các phân khúc sang AdRoll.

1. Chọn phân khúc mà bạn muốn xuất. Chọn một phân khúc có ít nhất 100 thành viên. Bạn không thể xuất các phân khúc nhỏ hơn. Ngoài ra, kích thước tối đa của một phân khúc có thể xuất là 250.000 thành viên/lần. 

1. Chọn **Lưu**.

Việc lưu một nội dung xuất sẽ không chạy nội dung xuất đó ngay lập tức.

Nội dung xuất chạy trong mỗi lần [làm mới theo lịch trình](system.md#schedule-tab). 

Bạn cũng có thể [xuất dữ liệu theo yêu cầu](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Quyền riêng tư về dữ liệu và sự tuân thủ

Khi bật Dynamics 365 Customer Insights để truyền dữ liệu sang AdRoll, bạn cho phép truyền dữ liệu ra ngoài ranh giới tuân thủ của Dynamics 365 Customer Insights, bao gồm cả dữ liệu nhạy cảm như Dữ liệu cá nhân. Microsoft sẽ chuyển những dữ liệu đó theo chỉ dẫn của bạn, nhưng bạn có trách nhiệm đảm bảo rằng AdRoll đáp ứng mọi nghĩa vụ về quyền riêng tư hoặc bảo mật mà bạn có thể có. Để biết thêm thông tin, hãy xem [Tuyên bố về Quyền riêng tư của Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Quản trị viên Dynamics 365 Customer Insights của bạn có thể xóa đích xuất này bất cứ lúc nào để ngừng việc sử dụng chức năng này.
