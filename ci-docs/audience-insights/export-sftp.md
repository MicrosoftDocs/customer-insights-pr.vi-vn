---
title: Xuất dữ liệu Customer Insights sang máy chủ SFTP
description: Tìm hiểu cách định cấu hình kết nối tới máy chủ SFTP.
ms.date: 01/27/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 9ec14fafa8f99e34b95349371298082e166535d0
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598411"
---
# <a name="connector-for-sftp-preview"></a>Trình kết nối cho SFTP (bản xem trước)

Sử dụng dữ liệu khách hàng của bạn trong các ứng dụng bên thứ ba bằng cách xuất sang máy chủ Giao thức truyền tệp bảo mật (SFTP).

## <a name="prerequisites"></a>Điều kiện tiên quyết

- Tính khả dụng của máy chủ SFTP và thông tin đăng nhập tương ứng.

## <a name="connect-to-sftp"></a>Kết nối với SFTP

1. Đi tới **Quản trị viên** > **Đích xuất**.

1. Trong phần **SFTP**, chọn **Thiết lập**.

1. Trong trường **Tên hiển thị**, hãy đặt tên cho vị trí để dễ nhận diện.

1. Cung cấp **Tên người dùng**, **Mật khẩu**, **Tên máy chủ** và **Thư mục xuất** cho tài khoản SFTP của bạn.

1. Chọn **Xác minh** để kiểm tra kết nối.

1. Sau khi xác minh thành công, hãy chọn xem bạn muốn xuất dữ liệu **Gzipped** hay **Đã giải nén** và chọn **dấu phân cách trường** cho các tệp đã xuất.

1. Chọn **Tôi đồng ý** để xác nhận **Quyền riêng tư về dữ liệu và sự tuân thủ**.

1. Chọn **Tiếp** để bắt đầu định cấu hình xuất.

## <a name="configure-the-export"></a>Xuất cấu hình

1. Chọn các thực thể, ví dụ như phân đoạn, bạn muốn xuất.

   > [!NOTE]
   > Mỗi thực thể được chọn sẽ có tối đa năm tệp đầu ra khi xuất. 

1. Chọn **Lưu**.

## <a name="export-the-data"></a>Xuất dữ liệu

Bạn có thể [xuất dữ liệu theo nhu cầu](export-destinations.md). Mỗi lần [làm mới theo lịch](system.md#schedule-tab), tác vụ xuất cũng sẽ chạy.

## <a name="known-limitations"></a>Các giới hạn đã biết

- Thời gian chạy của một lần xuất phụ thuộc vào hiệu suất hệ thống của bạn. Chúng tôi khuyên bạn nên sử dụng máy chủ có tối thiểu hai lõi CPU và bộ nhớ 1 Gb. 
- Việc xuất các thực thể với tối đa 100 triệu hồ sơ khách hàng có thể mất 90 phút khi sử dụng cấu hình tối thiểu được khuyến nghị gồm CPU 2 lõi và 1 Gb bộ nhớ. 

## <a name="data-privacy-and-compliance"></a>Quyền riêng tư về dữ liệu và sự tuân thủ

Khi bật Dynamics 365 Customer Insights để truyền dữ liệu qua SFTP, bạn cho phép chuyển dữ liệu ra bên ngoài ranh giới tuân thủ cho Dynamics 365 Customer Insights, bao gồm dữ liệu nhạy cảm tiềm ẩn như Dữ liệu cá nhân. Microsoft sẽ chuyển những dữ liệu đó theo chỉ dẫn của bạn, nhưng bạn có trách nhiệm đảm bảo rằng điểm đến xuất đáp ứng mọi nghĩa vụ về quyền riêng tư hoặc bảo mật mà bạn có thể có. Để biết thêm thông tin, hãy xem [Tuyên bố về Quyền riêng tư của Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Quản trị viên Dynamics 365 Customer Insights của bạn có thể xóa đích xuất này bất cứ lúc nào để ngừng sử dụng chức năng này.


[!INCLUDE[footer-include](../includes/footer-banner.md)]