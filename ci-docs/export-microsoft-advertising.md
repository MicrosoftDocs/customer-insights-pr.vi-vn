---
title: Xuất dữ liệu Customer Insights sang Microsoft Advertising
description: Tìm hiểu cách đặt cấu hình kết nối và xuất sang Microsoft Advertising.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 14479e915dd6ae76e018b59bee5980a600bb222d
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 04/27/2022
ms.locfileid: "8644169"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a>Xuất phân khúc sang Microsoft Advertising (xem trước)

Xuất phân khúc Customer Insights sang Microsoft Advertising để tạo đối tượng Customer Match. Sử dụng những đối tượng này cho chiến dịch quảng cáo của bạn.

## <a name="prerequisites"></a>Điều kiện tiên quyết

-   Một [tài khoản Microsoft Advertising](https://ads.microsoft.com/) và thông tin xác thực tương ứng của quản trị viên.
-   Bạn đã chấp nhận điều khoản sử dụng của Customer Match. 
-   [Các phân đoạn đã định cấu hình](segments.md) trong Thông tin chi tiết về khách hàng.
-   Hồ sơ khách hàng hợp nhất trong các phân khúc đã xuất chứa trường có địa chỉ email.

## <a name="known-limitations"></a>Các hạn chế đã biết

- Bạn có thể xuất tối đa 500.000 hồ sơ khách hàng mỗi lần sang Microsoft Advertising.
- Bạn chỉ xuất được phân khúc sang Microsoft Advertising.
- Có thể mất tới 10 phút để hoàn tất việc xuất tối đa 500.000 hồ sơ khách hàng sang Microsoft Advertising. 


## <a name="set-up-the-connection-to-microsoft-advertising"></a>Thiết lập kết nối với Microsoft Advertising

1. Đi đến **Quản trị viên** > **Kết nối**.

1. Chọn **Thêm kết nối** rồi chọn **Microsoft Advertising** để đặt cấu hình kết nối.

1. Đặt tên dễ nhận biết cho kết nối trong trường **Tên hiển thị**. Tên và loại kết nối mô tả kết nối này. Bạn nên chọn một tên giải thích mục đích và mục tiêu của kết nối.

1. Chọn người có thể sử dụng kết nối này. Giá trị mặc định là quản trị viên. Để biết thêm thông tin, hãy xem [Cho phép người đóng góp sử dụng một kết nối cho các lần xuất](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Chọn **Tôi đồng ý** để xác nhận **Quyền riêng tư về dữ liệu và sự tuân thủ**.

1. Chọn **Kết nối** để khởi tạo kết nối với Microsoft Advertising.

1. Chọn **Xác thực với Microsoft Advertising** và cung cấp thông tin xác thực quản trị viên của bạn cho Microsoft Advertising.

1. Chọn **Thêm chính bạn là người dùng xuất** và cung cấp thông tin xác thực Customer Insights.

1. Chọn **Lưu** để hoàn thành kết nối.

## <a name="configure-an-export"></a>Định cấu hình xuất

Bạn có thể định cấu hình lần xuất này nếu bạn có quyền truy cập vào kết nối thuộc loại này. Để biết thêm thông tin, hãy xem [Các quyền cần thiết để định cấu hình xuất](export-destinations.md#set-up-a-new-export).

1. Đi tới **Dữ liệu** > **Nội dung xuất**.

1. Để tạo một nội dung xuất mới, hãy chọn **Thêm đích**.

1. Trong trường **Kết nối để xuất**, hãy chọn một kết nối từ phần Microsoft Advertising. Nếu bạn không thấy tên phần này, tức là không có kết nối nào thuộc loại này dành cho bạn.

1. Chọn phân khúc để xuất. Các đối tượng Customer Match trong Microsoft Advertising được tạo tự động với tên của các phân khúc mà bạn đã chọn để xuất. Mỗi phân khúc sẽ cho ra một đối tượng Customer Match riêng biệt. 

1. Nhập **ID tài khoản và ID khách hàng Microsoft Advertising**. Bạn có thể tìm thấy ID khách hàng (`cid`) và ID tài khoản (`aid`) trong các tham số của URL khi bạn đăng nhập vào Microsoft Advertising.

1. Trong phần **Đối sánh dữ liệu**, trong trường **Email**, chọn trường có địa chỉ email của khách hàng. Bạn phải xuất các phân khúc sang Microsoft Advertising.

1. Chọn **Lưu**.

Việc lưu một nội dung xuất sẽ không chạy nội dung xuất đó ngay lập tức.

Nội dung xuất chạy trong mỗi lần [làm mới theo lịch trình](system.md#schedule-tab). Bạn cũng có thể [xuất dữ liệu theo yêu cầu](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Quyền riêng tư về dữ liệu và sự tuân thủ

Khi bật Dynamics 365 Customer Insights để truyền dữ liệu đến Microsoft Advertising, bạn cho phép chuyển dữ liệu ra bên ngoài ranh giới tuân thủ của Dynamics 365 Customer Insights, bao gồm cả dữ liệu có thể nhạy cảm như Dữ liệu cá nhân. Microsoft sẽ chuyển những dữ liệu đó theo chỉ dẫn của bạn, nhưng bạn có trách nhiệm đảm bảo rằng Microsoft Advertising đáp ứng mọi nghĩa vụ về quyền riêng tư hoặc bảo mật mà bạn có thể có. Để biết thêm thông tin, hãy xem [Tuyên bố về Quyền riêng tư của Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Quản trị viên Dynamics 365 Customer Insights của bạn có thể xóa đích xuất này bất cứ lúc nào để ngừng việc sử dụng chức năng này.
