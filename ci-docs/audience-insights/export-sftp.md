---
title: Xuất dữ liệu Customer Insights sang máy chủ SFTP
description: Tìm hiểu cách định cấu hình kết nối tới máy chủ SFTP.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c2529744d7a26a06324b79cad6a8001d75903545
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643529"
---
# <a name="connector-for-sftp-preview"></a>Trình kết nối cho SFTP (bản xem trước)

Sử dụng dữ liệu khách hàng của bạn trong các ứng dụng bên thứ ba bằng cách xuất sang máy chủ Giao thức truyền tệp bảo mật (SFTP).

## <a name="prerequisites"></a>Điều kiện tiên quyết

- Tính khả dụng của máy chủ SFTP và thông tin xác thực tương ứng.

## <a name="connect-to-sftp"></a>Kết nối với SFTP

1. Đi tới **Quản trị viên** > **Đích xuất**.

1. Trong phần **SFTP**, chọn **Thiết lập**.

1. Trong trường **Tên hiển thị**, hãy đặt tên cho vị trí để dễ nhận diện.

1. Cung cấp **Tên người dùng**, **Mật khẩu** và **Tên máy chủ** cho tài khoản SFTP của bạn. Ví dụ: Nếu thư mục gốc của máy chủ SFTP là /root/folder và bạn muốn xuất dữ liệu sang /root/folder/ci_export_destination_folder, máy chủ sẽ là sftp://<server_address>/ci_export_destination_folder".

1. Chọn **Xác minh** để kiểm tra kết nối.

1. Sau khi đã xác minh, chọn xem bạn muốn xuất dữ liệu **Nén** hay **Không nén** rồi chọn **dấu tách trường** cho các tệp đã xuất.

1. Chọn **Tôi đồng ý** để xác nhận **Quyền riêng tư về dữ liệu và sự tuân thủ**.

1. Chọn **Tiếp** để bắt đầu định cấu hình xuất.

## <a name="configure-the-connection"></a>Định cấu hình kết nối

1. Chọn **thuộc tính khách hàng** mà bạn muốn xuất. Bạn có thể xuất một hoặc nhiều thuộc tính.

1. Chọn **Tiếp theo**.

1. Chọn phân khúc mà bạn muốn xuất.

1. Chọn **Lưu**.

## <a name="export-the-data"></a>Xuất dữ liệu

Bạn có thể [xuất dữ liệu theo nhu cầu](export-destinations.md). Mỗi lần [làm mới theo lịch](system.md#schedule-tab), tác vụ xuất cũng sẽ chạy.

## <a name="data-privacy-and-compliance"></a>Quyền riêng tư về dữ liệu và tuân thủ

Khi bật Dynamics 365 Customer Insights để truyền dữ liệu qua SFTP, bạn cho phép chuyển dữ liệu ra bên ngoài ranh giới tuân thủ cho Dynamics 365 Customer Insights, bao gồm dữ liệu nhạy cảm tiềm ẩn như Dữ liệu cá nhân. Microsoft sẽ chuyển những dữ liệu đó theo chỉ dẫn của bạn, nhưng bạn có trách nhiệm đảm bảo rằng điểm đến xuất đáp ứng mọi nghĩa vụ về quyền riêng tư hoặc bảo mật mà bạn có thể có. Để biết thêm thông tin, hãy xem [Tuyên bố về Quyền riêng tư của Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Quản trị viên Dynamics 365 Customer Insights của bạn có thể xóa đích xuất này bất cứ lúc nào để ngừng sử dụng chức năng này.
