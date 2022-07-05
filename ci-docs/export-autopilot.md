---
title: Xuất phân khúc sang Autopilot (bản xem trước)
description: Tìm hiểu cách đặt cấu hình kết nối và xuất sang Autopilot.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e3af3d03e70c4ce9d229c84c582ec4f302be8c9f
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082545"
---
# <a name="export-segments-to-autopilot-preview"></a>Xuất phân khúc sang Autopilot (bản xem trước)

Xuất phân đoạn hồ sơ khách hàng hợp nhất sang Autopilot và sử dụng chúng cho các chiến dịch và tiếp thị qua email trong Autopilot. 

## <a name="prerequisites-for-a-connection"></a>Điều kiện tiên quyết để kết nối

-   Bạn có một [Tài khoản Autopilot](https://www.autopilothq.com/) và thông tin đăng nhập quản trị viên tương ứng.
-   Bạn có [phân đoạn được định cấu hình](segments.md) trong Thông tin chi tiết về khách hàng.
-   Hồ sơ khách hàng hợp nhất trong các phân khúc đã xuất chứa các trường đại diện cho địa chỉ email.

## <a name="known-limitations"></a>Các hạn chế đã biết

- Bạn có thể xuất tối đa 100.000 hồ sơ khách hàng sang Autopilot.
- Việc xuất sang Autopilot bị giới hạn ở các phân đoạn.
- Có thể mất tới vài phút để hoàn tất việc xuất tối đa 100.000 hồ sơ khách hàng sang Autopilot. 
- Số lượng hồ sơ khách hàng mà bạn có thể xuất sang Autopilot tùy thuộc vào và giới hạn trong hợp đồng của bạn với Autopilot.

## <a name="set-up-connection-to-autopilot"></a>Thiết lập kết nối với Autopilot

1. Đi đến **Quản trị viên** > **Kết nối**.

1. Chọn **Thêm kết nối** rồi chọn **Autopilot** để đặt cấu hình kết nối.

1. Đặt tên dễ nhận biết cho kết nối trong trường **Tên hiển thị**. Tên và loại kết nối mô tả kết nối này. Bạn nên chọn một tên giải thích mục đích và mục tiêu của kết nối.

1. Chọn người có thể sử dụng kết nối này. Nếu bạn không thực hiện hành động nào, giá trị mặc định sẽ là Quản trị viên. Để biết thêm thông tin, hãy xem [Cho phép người đóng góp sử dụng một kết nối cho các lần xuất](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Nhập [khóa API Autopilot](https://autopilot.docs.apiary.io/#).

1. Chọn **Tôi đồng ý** để xác nhận **Quyền riêng tư về dữ liệu và sự tuân thủ**.

1. Chọn **Kết nối** để khởi tạo kết nối với Autopilot.

1. Chọn **Thêm chính bạn là người dùng xuất** và cung cấp thông tin xác thực Customer Insights.

1. Chọn **Lưu** để hoàn thành kết nối.

## <a name="configure-an-export"></a>Định cấu hình xuất

Bạn có thể định cấu hình lần xuất này nếu bạn có quyền truy cập vào kết nối thuộc loại này. Để biết thêm thông tin, hãy xem [Các quyền cần thiết để định cấu hình xuất](export-destinations.md#set-up-a-new-export).

1. Đi tới **Dữ liệu** > **Nội dung xuất**.

1. Để tạo một nội dung xuất mới, hãy chọn **Thêm đích**.

1. Trong trường **Kết nối để xuất**, hãy chọn một kết nối từ phần Autopilot. Nếu bạn không thấy tên phần này, tức là không có kết nối nào thuộc loại này dành cho bạn.

1. Trong phần **Đối sánh dữ liệu**, trong trường **Email**, chọn trường có địa chỉ email của khách hàng. Lặp lại các bước tương tự cho các trường tùy chọn khác như **Tên**, **Họ**.

1. Chọn phân khúc mà bạn muốn xuất. Chúng tôi **khuyên bạn không nên xuất tổng cộng hơn 100.000 hồ sơ khách hàng** tới Autopilot. 

1. Chọn **Lưu**.

Việc lưu một nội dung xuất sẽ không chạy nội dung xuất đó ngay lập tức.

Nội dung xuất chạy trong mỗi lần [làm mới theo lịch trình](system.md#schedule-tab). Bạn cũng có thể [xuất dữ liệu theo yêu cầu](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Quyền riêng tư về dữ liệu và sự tuân thủ

Khi bật Dynamics 365 Customer Insights để truyền dữ liệu tới Autopilot, bạn cho phép chuyển dữ liệu ra bên ngoài ranh giới tuân thủ cho Dynamics 365 Customer Insights, bao gồm dữ liệu nhạy cảm tiềm ẩn như Dữ liệu cá nhân. Microsoft sẽ chuyển những dữ liệu đó theo chỉ dẫn của bạn, nhưng bạn có trách nhiệm đảm bảo rằng Autopilot đáp ứng mọi nghĩa vụ về quyền riêng tư hoặc bảo mật mà bạn có thể có. Để biết thêm thông tin, hãy xem [Tuyên bố về Quyền riêng tư của Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Quản trị viên Dynamics 365 Customer Insights của bạn có thể xóa đích xuất này bất cứ lúc nào để ngừng việc sử dụng chức năng này.


[!INCLUDE [footer-include](includes/footer-banner.md)]
