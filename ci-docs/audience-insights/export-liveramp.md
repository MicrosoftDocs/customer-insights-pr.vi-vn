---
title: Trình kết nối LiveRamp
description: Tìm hiểu cách xuất dữ liệu sang LiveRamp.
ms.date: 12/02/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 6ef4388b0e8ba8bc5866807765d8a872d41c9c14
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597583"
---
# <a name="liverampreg-connector-preview"></a>Trình kết nối LiveRamp&reg; (xem trước)

Kích hoạt dữ liệu của bạn trong LiveRamp để kết nối với hơn 500 nền tảng trên hệ sinh thái kỹ thuật số, mạng xã hội và TV. Làm việc với dữ liệu của bạn trong LiveRamp nhắm mục tiêu, chặn và cá nhân hóa chiến dịch quảng cáo.

## <a name="prerequisites"></a>Điều kiện tiên quyết

- Bạn phải có gói đăng ký LiveRamp thì mới dùng được trình kết nối này.
- Để đăng ký, hãy trực tiếp [liên hệ với LiveRamp](https://liveramp.com/contact/). [Tìm hiểu thêm về LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).

## <a name="connect-to-liveramp"></a>Kết nối với LiveRamp

1. Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Quản trị viên** > **Nơi xuất đích**.

1. Trong ngăn xếp **LiveRamp**, chọn **Thiết lập**.

1. Trong trường **Tên hiển thị**, hãy đặt tên cho vị trí để dễ nhận diện.

1. Điền **Tên người dùng** và **Mật khẩu** cho tài khoản LiveRamp Secure FTP (SFTP) của bạn.
Thông tin đăng nhập này có thể khác với thông tin đăng nhập LiveRamp Onboarding.

1. Chọn **Xác minh** để kiểm tra kết nối với LiveRamp.

1. Sau khi xác minh xong, hãy đồng ý với **Quyền riêng tư và tuân thủ dữ liệu** bằng cách đánh dấu vào ô **Tôi đồng ý**.

1. Chọn **Tiếp** để thiết lập trình kết nối LiveRamp.

## <a name="configure-the-connector"></a>Đặt cấu hình trình kết nối

1. Trong trường **Chọn khóa định danh**, chọn **Email**,  **Tên và địa chỉ** hoặc **Điện thoại** để gửi phương án định danh cho LiveRamp.

1. Ánh xạ các thuộc tính tương ứng từ thực thể khách hàng hợp nhất của bạn cho khóa định danh đã chọn.

1. Chọn **Thêm thuộc tính** để ánh xạ thêm các thuộc tính cần gửi đến LiveRamp.

   > [!TIP]
   > Khi gửi thêm thuộc tính khóa định danh đến LiveRamp, bạn sẽ có tỷ lệ khớp cao hơn.

1. Chọn các phân đoạn bạn muốn xuất sang LiveRamp.

1. Chọn **Lưu**.

> [!div class="mx-imgBorder"]
> ![Trình kết nối LiveRamp khi ánh xạ thuộc tính](media/export-liveramp-segments.png "Trình kết nối LiveRamp khi ánh xạ thuộc tính")

## <a name="export-the-data"></a>Xuất dữ liệu

Tác vụ xuất sẽ bắt đầu ngay khi mọi điều kiện tiên quyết đã được đáp ứng. Mỗi lần [làm mới theo lịch](system.md#schedule-tab), tác vụ xuất cũng sẽ chạy.
Khi quá trình xuất hoàn thành, bạn có thể đăng nhập vào LiveRamp Onboarding để kích hoạt và phân phối dữ liệu.

## <a name="data-privacy-and-compliance"></a>Quyền riêng tư về dữ liệu và tuân thủ

Khi bật Dynamics 365 Customer Insights để truyền dữ liệu tới Liveramp, bạn cho phép chuyển dữ liệu ra bên ngoài ranh giới tuân thủ cho Dynamics 365 Customer Insights, bao gồm dữ liệu nhạy cảm tiềm ẩn như Dữ liệu cá nhân. Microsoft sẽ chuyển những dữ liệu đó theo chỉ dẫn của bạn, nhưng bạn có trách nhiệm đảm bảo rằng Liveramp đáp ứng mọi nghĩa vụ về quyền riêng tư hoặc bảo mật mà bạn có thể có. Để biết thêm thông tin, hãy xem [Tuyên bố về Quyền riêng tư của Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Quản trị viên Dynamics 365 Customer Insights của bạn có thể xóa đích xuất này bất cứ lúc nào để ngừng sử dụng chức năng này.

[!INCLUDE[footer-include](../includes/footer-banner.md)]