---
title: Xuất dữ liệu Customer Insights sang Dynamics 365 Marketing
description: Tìm hiểu cách đặt cấu hình kết nối và xuất sang Dynamics 365 Marketing.
ms.date: 08/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b8e63a738abaf4fbb902e3edbf83f5a815978478
ms.sourcegitcommit: 8e89575fe2acb4b289fc157fa7c4c29caf9be967
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 08/24/2021
ms.locfileid: "7417231"
---
# <a name="use-segments-in-dynamics-365-marketing-preview"></a>Sử dụng các phân khúc trong Dynamics 365 Marketing (bản xem trước)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Dùng [các phân đoạn](segments.md) để tạo chiến dịch và liên hệ với các nhóm khách hàng cụ thể với Dynamics 365 Marketing. Để biết thêm thông tin, hãy xem [Sử dụng phân khúc từ Dynamics 365 Customer Insights với Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments).

Nếu bạn đang sử dụng các tính năng mới của Dynamics 365 Marketing để điều phối hành trình của khách hàng thời gian thực trong một tổ chức Dataverse, bạn không cần tạo một bản xuất chuẩn sang Dynamics 365 Marketing. Địa chỉ liên hệ và phân khúc từ thông tin chi tiết về đối tượng có sẵn ngay trong Dynamics 365 Marketing sau khi kết nối Marketing và Customer Insights. Trước khi bạn xóa các bản xuất hiện có, hãy xem lại tài liệu về [cách kết nối thông tin chi tiết về đối tượng và phối hợp hành trình của khách hàng Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile).

## <a name="prerequisite-for-a-connection"></a>Điều kiện tiên quyết để kết nối

- Hồ sơ liên hệ phải có trong Dynamics 365 Marketing trước khi bạn có thể xuất một phân đoạn từ Customer Insights sang Marketing. Đọc thêm về cách nhập liên hệ vào [Dynamics 365 Marketing bằng Microsoft Dataverse](connect-power-query.md).

  > [!NOTE]
  > Việc xuất các phân đoạn từ thông tin chi tiết về đối tượng sang Marketing sẽ không tạo hồ sơ liên hệ mới trong các phiên bản Marketing. Các bản ghi liên hệ từ Marketing phải được nhập vào thông tin chi tiết về đối tượng và được sử dụng làm nguồn dữ liệu. Chúng cũng cần được đưa vào thực thể Khách hàng hợp nhất để ánh xạ ID khách hàng với ID liên hệ trước khi có thể xuất phân đoạn.

## <a name="set-up-connection-to-marketing"></a>Thiết lập kết nối với Marketing

1. Đi đến **Quản trị viên** > **Kết nối**.

1. Chọn **Thêm kết nối** rồi chọn **Dynamics 365 Marketing** để đặt cấu hình kết nối.

1. Đặt tên dễ nhận biết cho kết nối trong trường **Tên hiển thị**. Tên và loại kết nối mô tả kết nối này. Bạn nên chọn một tên giải thích mục đích và mục tiêu của kết nối.

1. Chọn người có thể sử dụng kết nối này. Nếu bạn không thực hiện hành động nào, giá trị mặc định sẽ là Quản trị viên. Để biết thêm thông tin, hãy xem [Cho phép người đóng góp sử dụng một kết nối cho các lần xuất](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Nhập URL Marketing của tổ chức bạn vào trường **Địa chỉ máy chủ**.

1. Trong phần **Tài khoản quản trị viên máy chủ**, chọn **Đăng nhập** rồi chọn tài khoản Dynamics 365 Marketing.

1. Ánh xạ trường ID khách hàng với ID liên hệ Dynamics 365.

1. Chọn **Lưu** để hoàn thành kết nối. 

## <a name="configure-an-export"></a>Đặt cấu hình xuất

Bạn có thể định cấu hình lần xuất này nếu bạn có quyền truy cập vào kết nối thuộc loại này. Để biết thêm thông tin, hãy xem [Các quyền cần thiết để định cấu hình xuất](export-destinations.md#set-up-a-new-export).

1. Đi tới **Dữ liệu** > **Nội dung xuất**.

1. Để tạo một nội dung xuất mới, hãy chọn **Thêm đích**.

1. Trong trường **Kết nối để xuất**, hãy chọn một kết nối từ phần Dynamics 365 Marketing. Nếu bạn không thấy tên phần này, tức là không có kết nối nào thuộc loại này dành cho bạn.

1. Chọn một hoặc nhiều phân khúc.

1. Chọn **Lưu**.

Việc lưu một nội dung xuất sẽ không chạy nội dung xuất đó ngay lập tức.

Nội dung xuất chạy trong mỗi lần [làm mới theo lịch trình](system.md#schedule-tab). Bạn cũng có thể [xuất dữ liệu theo yêu cầu](export-destinations.md#run-exports-on-demand). 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
