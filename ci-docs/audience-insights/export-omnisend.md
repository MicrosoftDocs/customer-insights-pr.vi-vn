---
title: Xuất dữ liệu Customer Insights sang Omnisend
description: Tìm hiểu cách đặt cấu hình kết nối và xuất sang Omnisend.
ms.date: 05/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8bd692819fa8451ded5e74191ee717f81f87425d
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124571"
---
# <a name="export-segments-to-omnisend-preview"></a>Xuất phân khúc sang Omnisend (xem trước)

Xuất các phân khúc hồ sơ khách hàng hợp nhất sang Omnisend để dùng cho các hoạt động tiếp thị.

## <a name="prerequisites"></a>Điều kiện tiên quyết

-   Bạn có một [tài khoản Omnisend](https://www.omnisend.com/) và thông tin xác thực tương ứng của quản trị viên.
-   Bạn có [các phân khúc đã đặt cấu hình](segments.md) trong thông tin chuyên sâu về đối tượng.
-   Hồ sơ khách hàng hợp nhất trong các phân khúc đã xuất chứa các trường đại diện cho địa chỉ email.

## <a name="known-limitations"></a>Các giới hạn đã biết

- Bạn có thể xuất tối đa 1 triệu hồ sơ trong mỗi lần xuất sang Omnisend và có thể mất tới 4 giờ để hoàn tất.
- Bạn chỉ xuất được phân khúc sang Omnisend.
- Số lượng hồ sơ mà bạn có thể xuất sang Omnisend tùy thuộc vào hợp đồng của bạn với Omnisend.

## <a name="set-up-connection-to-omnisend"></a>Thiết lập kết nối với Omnisend

1. Đi đến **Quản trị viên** > **Kết nối**.

1. Chọn **Thêm kết nối** rồi chọn **Omnisend** để đặt cấu hình kết nối.

1. Đặt tên dễ nhận biết cho kết nối trong trường **Tên hiển thị**. Tên và loại kết nối mô tả kết nối này. Bạn nên chọn một tên giải thích mục đích và mục tiêu của kết nối.

1. Chọn người có thể sử dụng kết nối này. Theo mặc định, giá trị này là quản trị viên. Để biết thêm thông tin, hãy xem [Cho phép người đóng góp sử dụng một kết nối cho các lần xuất](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Nhập [khóa API Omnisend](https://support.omnisend.com/en/articles/1061890-generating-api-key) của bạn.

1. Chọn **Tôi đồng ý** để xác nhận **Quyền riêng tư về dữ liệu và sự tuân thủ**.

1. Chọn **Kết nối** để khởi tạo kết nối với Omnisend.

1. Chọn **Thêm chính bạn là người dùng xuất** và cung cấp thông tin xác thực Customer Insights.

1. Chọn **Lưu** để hoàn thành kết nối.

## <a name="configure-an-export"></a>Đặt cấu hình xuất

Bạn có thể đặt cấu hình lần xuất này nếu bạn có quyền truy cập vào kết nối thuộc loại này. Để biết thêm thông tin, hãy xem [Các quyền cần thiết để đặt cấu hình xuất](export-destinations.md#set-up-a-new-export).

1. Đi tới **Dữ liệu** > **Nội dung xuất**.

1. Để tạo một nội dung xuất mới, hãy chọn **Thêm đích**.

1. Trong trường **Kết nối để xuất**, hãy chọn một kết nối từ phần Omnisend. Nếu bạn không thấy tên phần này, tức là không có kết nối nào thuộc loại này dành cho bạn.

1. Trong phần **So khớp dữ liệu**, trong trường **Email**, chọn trường trong hồ sơ khách hàng hợp nhất trình bày địa chỉ email của khách hàng. Bạn phải xuất các phân khúc sang Omnisend. Bạn có thể tùy ý xuất Tên, Họ, Địa chỉ, Quốc gia/Khu vực, Tiểu bang, Thành phố và Mã bưu chính để tạo thêm nhiều email được cá nhân hóa. Chọn **Thêm thuộc tính** để ánh xạ những trường này.

1. Chọn **Lưu**.

Việc lưu một nội dung xuất sẽ không chạy nội dung xuất đó ngay lập tức.

Nội dung xuất chạy trong mỗi lần [làm mới theo lịch trình](system.md#schedule-tab). Bạn cũng có thể [xuất dữ liệu theo yêu cầu](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Quyền riêng tư về dữ liệu và sự tuân thủ

Khi bật Dynamics 365 Customer Insights để truyền dữ liệu đến Omnisend, bạn cho phép chuyển dữ liệu ra bên ngoài ranh giới tuân thủ của Dynamics 365 Customer Insights, bao gồm cả dữ liệu có thể nhạy cảm như Dữ liệu cá nhân. Microsoft sẽ chuyển những dữ liệu đó theo chỉ dẫn của bạn, nhưng bạn có trách nhiệm đảm bảo rằng Omnisend đáp ứng mọi nghĩa vụ về quyền riêng tư hoặc bảo mật mà bạn có thể có. Để biết thêm thông tin, hãy xem [Tuyên bố về Quyền riêng tư của Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Quản trị viên Dynamics 365 Customer Insights của bạn có thể xóa đích xuất này bất cứ lúc nào để ngừng việc sử dụng chức năng này.
