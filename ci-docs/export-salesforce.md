---
title: Xuất dữ liệu sang Đám mây Tiếp thị Salesforce (xem trước)
description: Tìm hiểu cách định cấu hình kết nối và xuất sang Salesforce Marketing Cloud.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 58e76e51c18c25177f9b4551b70b25b41248b142
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 07/27/2022
ms.locfileid: "9197064"
---
# <a name="export-data-to-salesforce-marketing-cloud-preview"></a>Xuất dữ liệu sang Đám mây Tiếp thị Salesforce (xem trước)

Sử dụng dữ liệu khách hàng của bạn trong Salesforce Marketing Cloud bằng cách xuất sang vị trí Giao thức truyền tệp bảo mật (SFTP).

## <a name="prerequisites"></a>Điều kiện tiên quyết

- Một [Máy chủ SFTP cho Đám mây Tiếp thị Salesforce](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) và thông tin đăng nhập quản trị viên tương ứng.

## <a name="set-up-connection-to-salesforce-marketing-cloud"></a>Thiết lập kết nối với Đám mây Tiếp thị Salesforce

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Đi đến **Quản trị viên** > **Kết nối**.

1. Lựa chọn **Thêm kết nối** và lựa chọn **Đám mây Tiếp thị Salesforce**.

1. Đặt tên dễ nhận biết cho kết nối trong trường **Tên hiển thị**. Tên và loại kết nối mô tả kết nối này. Bạn nên chọn một tên giải thích mục đích và mục tiêu của kết nối.

1. Chọn người có thể sử dụng kết nối này. Theo mặc định, giá trị này là quản trị viên. Để biết thêm thông tin, hãy xem [Cho phép người đóng góp sử dụng một kết nối cho các lần xuất](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Cung cấp **Tên người dùng**, **Mật khẩu**, **Tên máy chủ** và **Thư mục xuất** cho tài khoản SFTP của bạn.

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

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a>Nhập dữ liệu Customer Insights từ vị trí SFTP sang Salesforce Marketing Cloud

1. Tạo [phần mở rộng dữ liệu trong Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) để nhập tệp dữ liệu Customer Insights từ vị trí SFTP.

2. [Nhập dữ liệu từ vị trí SFTP](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) vào phần mở rộng dữ liệu Salesforce Marketing Cloud.

3. Thiết lập quy trình tự động hóa để nhập dữ liệu vào phần mở rộng dữ liệu. Tìm hiểu thêm về [quy trình tự động thả tệp và tự động hóa theo lịch trình](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).

   Xác định một [quy trình tự động thả tệp](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) hoặc một [quy trình tự động hóa theo lịch trình](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).

Sau đây là một ví dụ về [quy trình tự động hóa với SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).

[!INCLUDE [footer-include](includes/footer-banner.md)]
