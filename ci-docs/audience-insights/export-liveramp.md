---
title: Trình kết nối LiveRamp
description: Tìm hiểu cách đặt cấu hình kết nối và xuất sang LiveRamp.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 4c0f58083e8486d2042d8efcc8b3690020efb1c3
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 02/16/2022
ms.locfileid: "8226378"
---
# <a name="export-segments-to-liverampreg-preview"></a>Xuất phân khúc sang LiveRamp&reg; (bản xem trước)

Kích hoạt dữ liệu của bạn trong LiveRamp để kết nối với hơn 500 nền tảng kỹ thuật số, mạng xã hội và TV. Làm việc với dữ liệu của bạn trong LiveRamp nhắm mục tiêu, chặn và cá nhân hóa chiến dịch quảng cáo.

## <a name="prerequisites-for-a-connection"></a>Điều kiện tiên quyết để kết nối

- Bạn phải có gói đăng ký LiveRamp thì mới dùng được trình kết nối này.
- Để đăng ký, hãy trực tiếp [liên hệ với LiveRamp](https://liveramp.com/contact/). [Tìm hiểu thêm về LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).

## <a name="set-up-connection-to-liveramp"></a>Thiết lập kết nối với LiveRamp

1. Đi đến **Quản trị viên** > **Kết nối**.

1. Chọn **Thêm kết nối** rồi chọn **LiveRamp** để đặt cấu hình kết nối.

1. Đặt tên dễ nhận biết cho kết nối trong trường **Tên hiển thị**. Tên và loại kết nối mô tả kết nối này. Bạn nên chọn một tên giải thích mục đích và mục tiêu của kết nối.

1. Chọn người có thể sử dụng kết nối này. Nếu bạn không thực hiện hành động nào, giá trị mặc định sẽ là Quản trị viên. Để biết thêm thông tin, hãy xem [Cho phép người đóng góp sử dụng một kết nối cho các lần xuất](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Điền **Tên người dùng** và **Mật khẩu** cho tài khoản LiveRamp Secure FTP (SFTP) của bạn.
Thông tin đăng nhập này có thể khác với thông tin đăng nhập LiveRamp Onboarding.

1. Chọn **Xác minh** để kiểm tra kết nối với LiveRamp.

1. Sau khi xác minh xong, hãy đồng ý với **Quyền riêng tư và tuân thủ dữ liệu** bằng cách đánh dấu vào ô **Tôi đồng ý**.

1. Chọn **Lưu** để hoàn thành kết nối.

## <a name="configure-an-export"></a>Đặt cấu hình xuất

Bạn có thể định cấu hình lần xuất này nếu bạn có quyền truy cập vào kết nối thuộc loại này. Để biết thêm thông tin, hãy xem [Các quyền cần thiết để định cấu hình xuất](export-destinations.md#set-up-a-new-export).

1. Đi tới **Dữ liệu** > **Nội dung xuất**.

1. Để tạo một nội dung xuất mới, hãy chọn **Thêm đích**.

1. Trong trường **Kết nối để xuất**, hãy chọn một kết nối từ phần LiveRamp. Nếu bạn không thấy tên phần này, tức là không có kết nối nào thuộc loại này dành cho bạn.

1. Trong trường **Chọn khóa định danh**, chọn **Email**,  **Tên và địa chỉ** hoặc **Điện thoại** để gửi phương án định danh cho LiveRamp.
   > [!div class="mx-imgBorder"]
   > ![Trình kết nối LiveRamp khi ánh xạ thuộc tính.](media/export-liveramp-segments.png "Trình kết nối LiveRamp khi ánh xạ thuộc tính")

1. Ánh xạ các thuộc tính tương ứng từ thực thể *Khách hàng* cho số nhận dạng khóa đã chọn.

1. Chọn **Thêm thuộc tính** để ánh xạ thêm các thuộc tính cho mục đích gửi đến LiveRamp.

   > [!TIP]
   > Khi gửi thêm thuộc tính khóa định danh đến LiveRamp, bạn sẽ có tỷ lệ khớp cao hơn.

1. Chọn các phân đoạn bạn muốn xuất sang LiveRamp.

1. Chọn **Lưu**.

Việc lưu một nội dung xuất sẽ không chạy nội dung xuất đó ngay lập tức.

Nội dung xuất chạy trong mỗi lần [làm mới theo lịch trình](system.md#schedule-tab). Bạn cũng có thể [xuất dữ liệu theo yêu cầu](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Quyền riêng tư về dữ liệu và sự tuân thủ

Khi bật Dynamics 365 Customer Insights để truyền dữ liệu tới Liveramp, bạn cho phép chuyển dữ liệu ra bên ngoài ranh giới tuân thủ cho Dynamics 365 Customer Insights, bao gồm dữ liệu nhạy cảm tiềm ẩn như Dữ liệu cá nhân. Microsoft sẽ chuyển những dữ liệu đó theo chỉ dẫn của bạn, nhưng bạn có trách nhiệm đảm bảo rằng Liveramp đáp ứng mọi nghĩa vụ về quyền riêng tư hoặc bảo mật mà bạn có thể có. Để biết thêm thông tin, hãy xem [Tuyên bố về Quyền riêng tư của Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Quản trị viên Dynamics 365 Customer Insights của bạn có thể xóa đích xuất này bất cứ lúc nào để ngừng sử dụng chức năng này.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
