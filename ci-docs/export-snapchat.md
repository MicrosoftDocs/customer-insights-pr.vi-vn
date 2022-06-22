---
title: Xuất dữ liệu Customer Insights sang Snapchat
description: Tìm hiểu cách đặt cấu hình kết nối và xuất sang Snapchat.
ms.date: 06/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d64b482c322af8632e29ec41d6e34c390c5e646c
ms.sourcegitcommit: 8e9f0a9693fd8d91ad0227735ff03688fef5406f
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 06/10/2022
ms.locfileid: "8947302"
---
# <a name="export-segments-to-snapchat-preview"></a>Xuất phân khúc sang Snapchat (xem trước)

Xuất các phân khúc hồ sơ khách hàng hợp nhất sang Snapchat và sử dụng chúng cho quảng cáo. 

## <a name="prerequisites-for-a-connection"></a>Điều kiện tiên quyết để kết nối

-   Bạn có một [Tài khoản Snapchat Business](https://business.snapchat.com/), một [Tài khoản Snapchat Ads](https://ads.snapchat.com/) và thông tin xác thực tương ứng của quản trị viên. YOu ít nhất phải là thành viên của Tài khoản tổ chức và Người quản lý dữ liệu của một Tài khoản quảng cáo cụ thể. 
-   Bạn có ít nhất một đối tượng trong Trình quản lý đối tượng của Snapchat thuộc loại SAM (Đối sánh đối tượng trên Snap). 
-   Bạn có [phân đoạn được định cấu hình](segments.md) trong Thông tin chi tiết về khách hàng.
-   Hồ sơ khách hàng hợp nhất trong các phân khúc đã xuất chứa các trường đại diện cho địa chỉ email.

## <a name="known-limitations"></a>Các giới hạn đã biết

- Bạn chỉ xuất được phân khúc sang Snapchat.
- Có thể mất tới 15 phút để hoàn tất việc xuất tối đa 1 triệu hồ sơ khách hàng sang Snapchat. 

## <a name="set-up-connection-to-snapchat"></a>Thiết lập kết nối với Snapchat

1. Đi đến **Quản trị viên** > **Kết nối**.

1. Chọn **Thêm kết nối** rồi chọn **Snapchat** để đặt cấu hình kết nối.

1. Đặt tên dễ nhận biết cho kết nối trong trường **Tên hiển thị**. Tên và loại kết nối mô tả kết nối này. Bạn nên chọn một tên giải thích mục đích và mục tiêu của kết nối.

1. Chọn người có thể sử dụng kết nối này. Nếu bạn không thực hiện hành động nào, giá trị mặc định sẽ là Quản trị viên. Để biết thêm thông tin, hãy xem [Cho phép người đóng góp sử dụng một kết nối cho các lần xuất](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Chọn **Tôi đồng ý** để xác nhận **Quyền riêng tư về dữ liệu và sự tuân thủ**.

1. Chọn **Kết nối** để khởi tạo kết nối với Snapchat.

1. Chọn **Xác thực với Snapchat** và cung cấp thông tin xác thực quản trị viên của bạn cho Snapchat. 

1. Chọn **Thêm chính bạn là người dùng xuất** và cung cấp thông tin xác thực Customer Insights.

1. Chọn **Lưu** để hoàn thành kết nối.

## <a name="configure-an-export"></a>Định cấu hình xuất

Bạn có thể định cấu hình lần xuất này nếu bạn có quyền truy cập vào kết nối thuộc loại này. Để biết thêm thông tin, hãy xem [Các quyền cần thiết để định cấu hình xuất](export-destinations.md#set-up-a-new-export).

1. Đi tới **Dữ liệu** > **Nội dung xuất**.

1. Để tạo một nội dung xuất mới, hãy chọn **Thêm đích**.

1. Trong trường **Kết nối để xuất**, hãy chọn một kết nối từ phần Snapchat. Nếu bạn không thấy tên phần này, tức là không có kết nối nào thuộc loại này dành cho bạn.

1. Nhập [**Phân khúc Snapchat / ID đối tượng**](https://businesshelp.snapchat.com/s/article/custom-audiences). Bạn có thể tìm thấy ID của đối tượng trong URL sau khi chọn đối tượng trong Trình quản lý đối tượng của Snapchat. 

1. Trong phần **Đối sánh dữ liệu**, trong trường **Email**, chọn trường có địa chỉ email của khách hàng. Bạn phải xuất các phân khúc sang Snapchat.

1. Chọn phân khúc mà bạn muốn xuất. 

1. Chọn **Lưu**.

Việc lưu một nội dung xuất sẽ không chạy nội dung xuất đó ngay lập tức.

Nội dung xuất chạy trong mỗi lần [làm mới theo lịch trình](system.md#schedule-tab). Bạn cũng có thể [xuất dữ liệu theo yêu cầu](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Quyền riêng tư về dữ liệu và sự tuân thủ

Khi bật Dynamics 365 Customer Insights để truyền dữ liệu đến Snapchat, bạn cho phép chuyển dữ liệu ra bên ngoài ranh giới tuân thủ của Dynamics 365 Customer Insights, bao gồm cả dữ liệu có thể nhạy cảm như Dữ liệu cá nhân. Microsoft sẽ chuyển những dữ liệu đó theo chỉ dẫn của bạn, nhưng bạn có trách nhiệm đảm bảo rằng Snapchat đáp ứng mọi nghĩa vụ về quyền riêng tư hoặc bảo mật mà bạn có thể có. Để biết thêm thông tin, hãy xem [Tuyên bố về Quyền riêng tư của Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Quản trị viên Dynamics 365 Customer Insights của bạn có thể xóa đích xuất này bất cứ lúc nào để ngừng việc sử dụng chức năng này.
