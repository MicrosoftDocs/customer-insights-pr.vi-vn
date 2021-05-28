---
title: Xuất dữ liệu Customer Insights sang máy chủ SFTP
description: Tìm hiểu cách đặt cấu hình kết nối và xuất sang vị trí SFTP.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3663a48955f0b1db8a96e25403e5f8947bc6a220
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976965"
---
# <a name="export-segment-lists-and-other-data-to-sftp-preview"></a>Xuất danh sách phân khúc và dữ liệu khác sang SFTP (bản xem trước)

Sử dụng dữ liệu khách hàng của bạn trong các ứng dụng của bên thứ ba bằng cách xuất chúng sang vị trí Giao thức truyền tệp bảo mật (SFTP).

## <a name="prerequisites-for-connection"></a>Điều kiện tiên quyết để kết nối

- Tính khả dụng của máy chủ SFTP và thông tin đăng nhập tương ứng.

## <a name="known-limitations"></a>Các giới hạn đã biết

- Thời gian chạy của một lần xuất phụ thuộc vào hiệu suất hệ thống của bạn. Chúng tôi khuyên bạn nên sử dụng máy chủ có tối thiểu hai lõi CPU và bộ nhớ 1 Gb. 
- Việc xuất các thực thể với tối đa 100 triệu hồ sơ khách hàng có thể mất 90 phút khi sử dụng cấu hình tối thiểu được khuyến nghị gồm CPU 2 lõi và 1 Gb bộ nhớ. 

## <a name="set-up-connection-to-sftp"></a>Thiết lập kết nối với SFTP

1. Đi đến **Quản trị viên** > **Kết nối**.

1. Chọn **Thêm kết nối** rồi chọn **SFTP** để đặt cấu hình kết nối.

1. Đặt tên dễ nhận biết cho kết nối trong trường **Tên hiển thị**. Tên và loại kết nối mô tả kết nối này. Bạn nên chọn một tên giải thích mục đích và mục tiêu của kết nối.

1. Chọn người có thể sử dụng kết nối này. Nếu bạn không thực hiện hành động nào, giá trị mặc định sẽ là Quản trị viên. Để biết thêm thông tin, hãy xem [Cho phép người đóng góp sử dụng một kết nối cho các lần xuất](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Cung cấp **Tên người dùng**, **Mật khẩu**, **Tên máy chủ** và **Thư mục xuất** cho tài khoản SFTP của bạn.

1. Chọn **Xác minh** để kiểm tra kết nối.

1. Chọn nếu bạn muốn xuất dữ liệu **Đã nén** hoặc **Đã giải nén** của mình và **dấu tách trường** cho các tệp đã xuất.

1. Chọn **Tôi đồng ý** để xác nhận **Quyền riêng tư về dữ liệu và sự tuân thủ**.

1. Chọn **Lưu** để hoàn thành kết nối.

## <a name="configure-an-export"></a>Đặt cấu hình xuất

Bạn có thể đặt cấu hình lần xuất này nếu bạn có quyền truy cập vào kết nối thuộc loại này. Để biết thêm thông tin, hãy xem [Các quyền cần thiết để đặt cấu hình xuất](export-destinations.md#set-up-a-new-export).

1. Đi tới **Dữ liệu** > **Nội dung xuất**.

1. Để tạo một nội dung xuất mới, hãy chọn **Thêm đích**.

1. Trong trường **Kết nối để xuất**, hãy chọn một kết nối từ phần SFTP. Nếu bạn không thấy tên phần này, tức là không có kết nối nào thuộc loại này dành cho bạn.

1. Chọn các thực thể, ví dụ như phân đoạn, bạn muốn xuất.

   > [!NOTE]
   > Mỗi thực thể đã chọn sẽ được chia thành tối đa năm tệp đầu ra khi xuất. 

1. Chọn **Lưu**.

Việc lưu một nội dung xuất sẽ không chạy nội dung xuất đó ngay lập tức.

Nội dung xuất chạy trong mỗi lần [làm mới theo lịch trình](system.md#schedule-tab). Bạn cũng có thể [xuất dữ liệu theo yêu cầu](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Quyền riêng tư về dữ liệu và sự tuân thủ

Khi bật Dynamics 365 Customer Insights để truyền dữ liệu qua SFTP, bạn cho phép chuyển dữ liệu ra bên ngoài ranh giới tuân thủ cho Dynamics 365 Customer Insights, bao gồm dữ liệu nhạy cảm tiềm ẩn như Dữ liệu cá nhân. Microsoft sẽ chuyển những dữ liệu đó theo chỉ dẫn của bạn, nhưng bạn có trách nhiệm đảm bảo rằng điểm đến xuất đáp ứng mọi nghĩa vụ về quyền riêng tư hoặc bảo mật mà bạn có thể có. Để biết thêm thông tin, hãy xem [Tuyên bố về Quyền riêng tư của Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Quản trị viên Dynamics 365 Customer Insights của bạn có thể xóa đích xuất này bất cứ lúc nào để ngừng sử dụng chức năng này.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
