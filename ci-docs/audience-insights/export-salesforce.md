---
title: Xuất dữ liệu Customer Insights sang Salesforce Marketing Cloud
description: Tìm hiểu cách định cấu hình kết nối và xuất sang Salesforce Marketing Cloud.
ms.date: 07/23/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b50539d6478a8fe196048f0fb421e5856f713a3ddc6577a637e593f90857ae8b
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035579"
---
# <a name="export-segments-and-other-data-to-salesforce-marketing-cloud-preview"></a>Xuất các phân khúc và dữ liệu khác sang Salesforce Marketing Cloud (bản xem trước)

Sử dụng dữ liệu khách hàng của bạn trong Salesforce Marketing Cloud bằng cách xuất sang vị trí Giao thức truyền tệp bảo mật (SFTP).

## <a name="prerequisites-for-connection"></a>Điều kiện tiên quyết để kết nối

- Tính khả dụng của máy chủ SFTP và thông tin xác thực tương ứng của quản trị viên. [Cách thiết lập vị trí SFTP cho Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) 

## <a name="set-up-the-connection-to-salesforce-marketing-cloud"></a>Thiết lập kết nối đến Salesforce Marketing Cloud

1. Đi đến **Quản trị viên** > **Kết nối**.

1. Chọn **Thêm kết nối** rồi chọn **Salesforce Marketing Cloud** để định cấu hình kết nối.

1. Đặt tên dễ nhận biết cho kết nối trong trường **Tên hiển thị**. Tên và loại kết nối mô tả kết nối này. Bạn nên chọn một tên giải thích mục đích và mục tiêu của kết nối.

1. Chọn người có thể sử dụng kết nối này. Nếu bạn không thực hiện hành động nào, giá trị mặc định sẽ là Quản trị viên. Để biết thêm thông tin, hãy xem [Cho phép người đóng góp sử dụng một kết nối cho các lần xuất](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Cung cấp **Tên người dùng**, **Mật khẩu**, **Tên máy chủ** và **Thư mục xuất** cho tài khoản SFTP của bạn.

1. Chọn **Xác minh** để kiểm tra kết nối.

1. Chọn **Tôi đồng ý** để xác nhận **Quyền riêng tư về dữ liệu và sự tuân thủ**.

1. Chọn **Lưu** để hoàn thành kết nối.

## <a name="configure-an-export"></a>Định cấu hình xuất

Bạn có thể định cấu hình lần xuất này nếu bạn có quyền truy cập vào kết nối thuộc loại này. Để biết thêm thông tin, hãy xem [Các quyền cần thiết để định cấu hình xuất](export-destinations.md#set-up-a-new-export).

1. Đi tới **Dữ liệu** > **Nội dung xuất**.

1. Để tạo một nội dung xuất mới, hãy chọn **Thêm đích**.

1. Trong trường **Kết nối để xuất**, hãy chọn một kết nối từ phần SFTP. Nếu bạn không thấy tên phần này, tức là không có kết nối nào thuộc loại này dành cho bạn.

1. Chọn nếu bạn muốn xuất dữ liệu **Đã nén** hoặc **Đã giải nén** của mình và **dấu tách trường** cho các tệp đã xuất.

1. Chọn các thực thể, ví dụ như phân khúc, bạn muốn xuất.

   > [!NOTE]
   > Mỗi thực thể đã chọn sẽ được chia thành tối đa năm tệp đầu ra khi xuất. 

1. Chọn **Lưu**.

Việc lưu một nội dung xuất sẽ không chạy nội dung xuất đó ngay lập tức.

Nội dung xuất chạy trong mỗi lần [làm mới theo lịch trình](system.md#schedule-tab). Bạn cũng có thể [xuất dữ liệu theo yêu cầu](export-destinations.md#run-exports-on-demand). 

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a>Nhập dữ liệu Customer Insights từ vị trí SFTP sang Salesforce Marketing Cloud

1. Tạo [phần mở rộng dữ liệu trong Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) để nhập tệp dữ liệu Customer Insights từ vị trí SFTP.

2. [Nhập dữ liệu từ vị trí SFTP](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) vào phần mở rộng dữ liệu Salesforce Marketing Cloud. 

3. Thiết lập quy trình tự động hóa để nhập dữ liệu vào phần mở rộng dữ liệu. Tìm hiểu thêm về [quy trình tự động thả tệp và tự động hóa theo lịch trình](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).

   Xác định một [quy trình tự động thả tệp](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) hoặc một [quy trình tự động hóa theo lịch trình](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5). 

Sau đây là một ví dụ về [quy trình tự động hóa với SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).

## <a name="data-privacy-and-compliance"></a>Quyền riêng tư về dữ liệu và sự tuân thủ

Khi bật Dynamics 365 Customer Insights để truyền dữ liệu qua SFTP, bạn cho phép truyền dữ liệu ra ngoài phạm vi tuân thủ cho Dynamics 365 Customer Insights, bao gồm dữ liệu có khả năng là thông tin nhạy cảm, chẳng hạn như Dữ liệu cá nhân. Microsoft sẽ truyền những dữ liệu đó theo chỉ dẫn của bạn, nhưng bạn có trách nhiệm đảm bảo rằng điểm đến xuất đáp ứng mọi nghĩa vụ về quyền riêng tư hoặc bảo mật mà bạn có thể có. Để biết thêm thông tin, hãy xem [Tuyên bố về Quyền riêng tư của Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Quản trị viên Dynamics 365 Customer Insights của bạn có thể xóa đích xuất này bất cứ lúc nào để ngừng việc sử dụng chức năng này.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
