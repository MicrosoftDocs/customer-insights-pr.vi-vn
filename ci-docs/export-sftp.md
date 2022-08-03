---
title: Xuất dữ liệu sang máy chủ SFTP (xem trước) (chứa video)
description: Tìm hiểu cách đặt cấu hình kết nối và xuất sang vị trí SFTP.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b12d25ecbd2e5fb31d7d5a6bb775dc3e7c1bf007
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 07/28/2022
ms.locfileid: "9207255"
---
# <a name="export-data-to-sftp-hosts-preview"></a>Xuất dữ liệu sang máy chủ SFTP (xem trước)

Sử dụng dữ liệu khách hàng của bạn trong các ứng dụng của bên thứ ba bằng cách xuất chúng sang vị trí Giao thức truyền tệp bảo mật (SFTP).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO94X]

## <a name="prerequisites"></a>Điều kiện tiên quyết

- Tính khả dụng của máy chủ SFTP và thông tin đăng nhập tương ứng.

## <a name="known-limitations"></a>Các hạn chế đã biết

- Các điểm đến SFTP sau tường lửa hiện không được hỗ trợ.
- Thời gian chạy của một lần xuất phụ thuộc vào hiệu suất hệ thống của bạn. Chúng tôi khuyên bạn nên sử dụng máy chủ có tối thiểu hai lõi CPU và bộ nhớ 1 Gb.
- Lên đến 100 triệu hồ sơ khách hàng, có thể mất 90 phút khi sử dụng cấu hình tối thiểu được khuyến nghị gồm hai lõi CPU và 1 Gb bộ nhớ.
- Nếu bạn sử dụng khóa SSH để xác thực, hãy đảm bảo rằng bạn [tạo khóa riêng của bạn](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example) ở định dạng PEM hoặc SSH.COM. Nếu bạn đang sử dụng Putty, hãy chuyển đổi khóa cá nhân của bạn bằng cách xuất thành Open SSH. Các định dạng khóa riêng tư sau được hỗ trợ:
  - RSA ở định dạng OpenSSL PEM và ssh.com
  - DSA ở định dạng OpenSSL PEM và ssh.com
  - ECDSA 256/384/521 ở định dạng OpenSSL PEM
  - ED25519 và RSA ở định dạng khóa OpenSSH

## <a name="set-up-connection-to-sftp"></a>Thiết lập kết nối với SFTP

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Đi đến **Quản trị viên** > **Kết nối**.

1. Lựa chọn **Thêm kết nối** và lựa chọn **SFTP**.

1. Đặt tên dễ nhận biết cho kết nối trong trường **Tên hiển thị**. Tên và loại kết nối mô tả kết nối này. Bạn nên chọn một tên giải thích mục đích và mục tiêu của kết nối.

1. Chọn người có thể sử dụng kết nối này. Theo mặc định, giá trị này là quản trị viên. Để biết thêm thông tin, hãy xem [Cho phép người đóng góp sử dụng một kết nối cho các lần xuất](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Chọn xem bạn muốn xác thực thông qua SSH hoặc tên người dùng / mật khẩu cho kết nối của mình và cung cấp các chi tiết cần thiết. Nếu bạn sử dụng khóa SSH để xác thực, hãy đảm bảo rằng bạn [tạo khóa riêng của bạn](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example) ở định dạng PEM hoặc SSH.COM. Nếu bạn đang sử dụng Putty, hãy chuyển đổi khóa cá nhân của bạn bằng cách xuất thành Open SSH. Các định dạng khóa riêng tư sau được hỗ trợ:
   - RSA ở định dạng OpenSSL PEM và ssh.com
   - DSA ở định dạng OpenSSL PEM và ssh.com
   - ECDSA 256/384/521 ở định dạng OpenSSL PEM
   - ED25519 và RSA ở định dạng khóa OpenSSH

1. Chọn **Xác minh** để kiểm tra kết nối.

1. Xem lại [quyền riêng tư và tuân thủ dữ liệu](connections.md#data-privacy-and-compliance) và chọn **tôi đồng ý**.

1. Chọn **Lưu** để hoàn thành kết nối.

## <a name="configure-an-export"></a>Định cấu hình xuất

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Đi tới **Dữ liệu** > **Nội dung xuất**.

1. Lựa chọn **Thêm xuất khẩu**.

1. Trong trường **Kết nối để xuất**, hãy chọn một kết nối từ phần SFTP. Liên hệ với quản trị viên nếu không có kết nối.

1. Nhập tên cho lần xuất.

1. Chọn nếu bạn muốn xuất dữ liệu **Đã nén** hoặc **Đã giải nén** của mình và **dấu tách trường** cho các tệp đã xuất.

1. Chọn các thực thể, ví dụ như phân đoạn, mà bạn muốn xuất.

   > [!NOTE]
   > Mỗi thực thể đã chọn sẽ được chia thành tối đa năm tệp đầu ra khi xuất.

1. Chọn **Lưu.**

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!TIP]
> Việc xuất các thực thể chứa một lượng lớn dữ liệu có thể dẫn đến nhiều tệp CSV trong cùng một thư mục cho mỗi lần xuất. Việc chia nhỏ xuất khẩu xảy ra vì lý do hiệu suất để giảm thiểu thời gian hoàn thành xuất khẩu.

[!INCLUDE [footer-include](includes/footer-banner.md)]
