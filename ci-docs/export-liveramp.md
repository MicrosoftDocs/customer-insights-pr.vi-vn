---
title: Xuất phân khúc sang LiveRamp (bản xem trước)
description: Tìm hiểu cách đặt cấu hình kết nối và xuất sang LiveRamp.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 55eacea3af83f46583a3a43797d625479f56586b
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196742"
---
# <a name="export-segments-to-liverampreg-preview"></a>Xuất phân khúc sang LiveRamp&reg; (bản xem trước)

Kích hoạt dữ liệu của bạn trong LiveRamp để kết nối với hơn 500 nền tảng kỹ thuật số, mạng xã hội và TV. Làm việc với dữ liệu của bạn trong LiveRamp nhắm mục tiêu, chặn và cá nhân hóa chiến dịch quảng cáo.

## <a name="prerequisites"></a>Điều kiện tiên quyết

- Đăng ký LiveRamp để sử dụng trình kết nối này. Để đăng ký, hãy trực tiếp [liên hệ với LiveRamp](https://liveramp.com/contact/). [Tìm hiểu thêm về LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).

## <a name="known-limitations"></a>Các hạn chế đã biết

- Xuất LiveRamp đang sử dụng xuất SFTP. Các điểm đến SFTP sau tường lửa hiện không được hỗ trợ.
- Nếu bạn sử dụng khóa SSH để xác thực, hãy đảm bảo rằng bạn [tạo khóa riêng của bạn](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example) ở định dạng PEM hoặc SSH.COM. Nếu bạn đang sử dụng Putty, hãy chuyển đổi khóa cá nhân của bạn bằng cách xuất thành Open SSH. Các định dạng khóa riêng tư sau được hỗ trợ:
  - RSA ở định dạng OpenSSL PEM và ssh.com
  - DSA ở định dạng OpenSSL PEM và ssh.com
  - ECDSA 256/384/521 ở định dạng OpenSSL PEM
  - ED25519 và RSA ở định dạng khóa OpenSSH
- Thời gian chạy của một lần xuất phụ thuộc vào hiệu suất hệ thống của bạn. Chúng tôi khuyên bạn nên sử dụng máy chủ có tối thiểu hai lõi CPU và bộ nhớ 1 Gb.
- Việc xuất các thực thể với tối đa 100 triệu hồ sơ khách hàng có thể mất 90 phút khi sử dụng cấu hình tối thiểu được khuyến nghị gồm CPU 2 lõi và 1 Gb bộ nhớ.
- Số lượng cấu hình (hoặc dữ liệu) thực tế mà bạn có thể xuất sang LiveRamp tùy thuộc vào đăng ký của bạn với LiveRamp.

## <a name="set-up-connection-to-liveramp"></a>Thiết lập kết nối với LiveRamp

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Đi đến **Quản trị viên** > **Kết nối**.

1. Lựa chọn **Thêm kết nối** và lựa chọn **LiveRamp**.

1. Đặt tên dễ nhận biết cho kết nối trong trường **Tên hiển thị**. Tên và loại kết nối mô tả kết nối này. Bạn nên chọn một tên giải thích mục đích và mục tiêu của kết nối.

1. Chọn người có thể sử dụng kết nối này. Theo mặc định, giá trị này là quản trị viên. Để biết thêm thông tin, hãy xem [Cho phép người đóng góp sử dụng một kết nối cho các lần xuất](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Chọn xem bạn muốn xác thực thông qua SSH hoặc tên người dùng / mật khẩu cho kết nối của mình và cung cấp các chi tiết cần thiết.

1. Chọn **Xác minh** để kiểm tra kết nối với LiveRamp.

1. Sau khi xác minh thành công, hãy xem lại [quyền riêng tư và tuân thủ dữ liệu](connections.md#data-privacy-and-compliance) và chọn **tôi đồng ý**.

1. Chọn **Lưu** để hoàn thành kết nối.

## <a name="configure-an-export"></a>Định cấu hình xuất

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Đi tới **Dữ liệu** > **Nội dung xuất**.

1. Lựa chọn **Thêm xuất khẩu**.

1. Trong trường **Kết nối để xuất**, hãy chọn một kết nối từ phần LiveRamp. Liên hệ với quản trị viên nếu không có kết nối.

1. Nhập tên cho lần xuất.

1. Bên trong **Kết nối dữ liệu** trường, chọn **E-mail**, **và địa chỉ**, hoặc **Điện thoại** để gửi tới LiveRamp để giải quyết danh tính.

   :::image type="content" source="media/export-liveramp-segments.png" alt-text="Trình kết nối LiveRamp khi ánh xạ thuộc tính.":::

1. Ánh xạ các thuộc tính tương ứng từ thực thể *Khách hàng* cho số nhận dạng khóa đã chọn.

1. Chọn **Thêm thuộc tính** để ánh xạ thêm các thuộc tính cho mục đích gửi đến LiveRamp.

   > [!TIP]
   > Khi gửi thêm thuộc tính khóa định danh đến LiveRamp, bạn sẽ có tỷ lệ khớp cao hơn.

1. Chọn phân khúc mà bạn muốn xuất.

1. Chọn **Lưu.**

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
