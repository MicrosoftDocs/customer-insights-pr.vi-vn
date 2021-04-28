---
title: Xuất dữ liệu Customer Insights sang Campaign Monitor
description: Tìm hiểu cách đặt cấu hình kết nối và xuất sang Campaign Monitor.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 7fd6af37b40e21d030a1ace0cd5f8fcc7861c3fa
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760667"
---
# <a name="export-segment-lists-to-campaign-monitor-preview"></a>Xuất danh sách phân khúc sang Campaign Monitor (bản xem trước)

Xuất các phân khúc hồ sơ khách hàng hợp nhất sang Campaign Monitor và sử dụng chúng cho các hoạt động tiếp thị.

## <a name="prerequisites"></a>Điều kiện tiên quyết

-   Bạn có một [Tài khoản Campaign Monitor](https://www.campaignmonitor.com/) và thông tin xác thực tương ứng của quản trị viên.
-   Bạn có [các phân đoạn được định cấu hình](segments.md) trong thông tin chi tiết về đối tượng.
-   Hồ sơ khách hàng hợp nhất trong các phân đoạn đã xuất chứa các trường đại diện cho địa chỉ email.

## <a name="known-limitations"></a>Các giới hạn đã biết

- Bạn có thể xuất tối đa 1 triệu hồ sơ trong mỗi lần xuất sang Campaign Monitor.
- Chỉ được xuất các phân khúc sang Campaign Monitor.
- Có thể mất tới 20 phút để hoàn thành quá trình xuất tối đa 1 triệu hồ sơ sang Campaign Monitor. 
- Số lượng hồ sơ mà bạn có thể xuất sang Campaign Monitor phụ thuộc và bị giới hạn theo hợp đồng của bạn với Campaign Monitor.

## <a name="set-up-connection-to-campaign-monitor"></a>Thiết lập kết nối với Campaign Monitor

1. Đi đến **Quản trị viên** > **Kết nối**.

1. Chọn **Thêm kết nối** rồi chọn **Campaign Monitor** để đặt cấu hình kết nối.

1. Đặt tên dễ nhận biết cho kết nối trong trường **Tên hiển thị**. Tên và loại kết nối mô tả kết nối này. Bạn nên chọn một tên giải thích mục đích và mục tiêu của kết nối.

1. Chọn người có thể sử dụng kết nối này. Nếu bạn không thực hiện hành động nào, giá trị mặc định sẽ là Quản trị viên. Để biết thêm thông tin, hãy xem [Cho phép người đóng góp sử dụng một kết nối cho các lần xuất](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Chọn **Tôi đồng ý** để xác nhận **Quyền riêng tư về dữ liệu và sự tuân thủ**.

1. Chọn **Kết nối** để khởi tạo kết nối với Campaign Monitor.

1. Chọn **Xác thực với Campaign Monitor** và cung cấp thông tin xác thực quản trị viên của bạn cho Campaign Monitor.

1. Chọn **Thêm chính bạn là người dùng xuất** và cung cấp thông tin xác thực Customer Insights.

1. Chọn **Lưu** để hoàn thành kết nối.

## <a name="configure-an-export"></a>Đặt cấu hình xuất

Bạn có thể đặt cấu hình lần xuất này nếu bạn có quyền truy cập vào kết nối thuộc loại này. Để biết thêm thông tin, hãy xem [Các quyền cần thiết để đặt cấu hình xuất](export-destinations.md#set-up-a-new-export).

1. Đi tới **Dữ liệu** > **Nội dung xuất**.

1. Để tạo một nội dung xuất mới, hãy chọn **Thêm đích**.

1. Trong trường **Kết nối để xuất**, hãy chọn một kết nối từ phần Campaign Monitor. Nếu bạn không thấy tên phần này, tức là không có kết nối nào thuộc loại này dành cho bạn.

1. Nhập [**ID danh sách Campaign Monitor**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).    
   [Tạo khóa API](https://www.campaignmonitor.com/api/getting-started/) từ **Cài đặt tài khoản** trong Campaign Monitor trước tiên để xem ID danh sách API.  

3. Trong phần **So khớp dữ liệu**, trong trường **Email**, chọn trường trong hồ sơ khách hàng hợp nhất trình bày địa chỉ email của khách hàng. Bạn phải xuất các phân khúc sang Campaign Monitor.

1. Chọn **Lưu**.

Việc lưu một nội dung xuất sẽ không chạy nội dung xuất đó ngay lập tức.

Nội dung xuất chạy trong mỗi lần [làm mới theo lịch trình](system.md#schedule-tab). Bạn cũng có thể [xuất dữ liệu theo yêu cầu](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Quyền riêng tư về dữ liệu và sự tuân thủ

Khi bật Dynamics 365 Customer Insights để truyền dữ liệu đến Campaign Monitor, bạn cho phép chuyển dữ liệu ra bên ngoài ranh giới tuân thủ của Dynamics 365 Customer Insights, bao gồm cả dữ liệu có thể nhạy cảm như Dữ liệu cá nhân. Microsoft sẽ chuyển những dữ liệu đó theo chỉ dẫn của bạn, nhưng bạn có trách nhiệm đảm bảo rằng Campaign Monitor đáp ứng mọi nghĩa vụ về quyền riêng tư hoặc bảo mật mà bạn có thể có. Để biết thêm thông tin, hãy xem [Tuyên bố về Quyền riêng tư của Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Quản trị viên Dynamics 365 Customer Insights của bạn có thể xóa đích xuất này bất cứ lúc nào để ngừng sử dụng chức năng này.
