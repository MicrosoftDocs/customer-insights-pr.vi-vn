---
title: Xuất dữ liệu Customer Insights sang RollWorks
description: Tìm hiểu cách đặt cấu hình kết nối và xuất sang RollWorks.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d8ce4d867835dcb7cf56c6fffff4e25d1f5c109af0e401fc0eb8b3a7427c1de4
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034616"
---
# <a name="export-segments-to-rollworks-preview"></a>Xuất phân khúc sang RollWorks (xem trước)

Xuất các phân khúc hồ sơ khách hàng hợp nhất sang RollWorks và sử dụng chúng cho quảng cáo. 

## <a name="prerequisites-for-a-connection"></a>Điều kiện tiên quyết để kết nối

-   Bạn có một [Tài khoản RollWorks](https://www.rollworks.com/) và thông tin xác thực tương ứng của quản trị viên.
-   Bạn có [các phân khúc được định cấu hình](segments.md) trong thông tin chuyên sâu về đối tượng.
-   Hồ sơ khách hàng hợp nhất trong các phân khúc đã xuất chứa các trường đại diện cho địa chỉ email.

## <a name="known-limitations"></a>Các giới hạn đã biết

- Bạn có thể xuất tối đa 250.000 hồ sơ trong mỗi lần xuất sang RollWorks.
- Bạn không thể xuất các phân khúc có ít hơn 100 hồ sơ sang RollWorks. 
- Bạn chỉ xuất được phân khúc sang RollWorks.
- Có thể mất tới 10 phút để hoàn thành quá trình xuất tối đa 250.000 hồ sơ sang RollWorks. 
- Số lượng hồ sơ mà bạn có thể xuất sang RollWorks phụ thuộc và bị giới hạn theo hợp đồng của bạn với RollWorks.

## <a name="set-up-connection-to-rollworks"></a>Thiết lập kết nối với RollWorks

1. Đi đến **Quản trị viên** > **Kết nối**.

1. Chọn **Thêm kết nối** rồi chọn **RollWorks** để đặt cấu hình kết nối.

1. Đặt tên dễ nhận biết cho kết nối trong trường **Tên hiển thị**. Tên và loại kết nối mô tả kết nối này. Bạn nên chọn một tên giải thích mục đích và mục tiêu của kết nối.

1. Chọn người có thể sử dụng kết nối này. Nếu bạn không thực hiện hành động nào, giá trị mặc định sẽ là Quản trị viên. Để biết thêm thông tin, hãy xem [Cho phép người đóng góp sử dụng một kết nối cho các lần xuất](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Chọn **Tôi đồng ý** để xác nhận **Quyền riêng tư về dữ liệu và sự tuân thủ**.

1. Chọn **Kết nối** để khởi tạo kết nối với RollWorks.

1. Chọn **Xác thực với RollWorks** và cung cấp thông tin xác thực quản trị viên của bạn cho RollWorks.

1. Chọn **Thêm chính bạn là người dùng xuất** và cung cấp thông tin xác thực Customer Insights.

1. Chọn **Lưu** để hoàn thành kết nối.

## <a name="configure-an-export"></a>Định cấu hình xuất

Bạn có thể định cấu hình lần xuất này nếu bạn có quyền truy cập vào kết nối thuộc loại này. Để biết thêm thông tin, hãy xem [Các quyền cần thiết để định cấu hình xuất](export-destinations.md#set-up-a-new-export).

1. Đi tới **Dữ liệu** > **Nội dung xuất**.

1. Để tạo một nội dung xuất mới, hãy chọn **Thêm đích**.

1. Trong trường **Kết nối để xuất**, hãy chọn một kết nối từ phần RollWorks. Nếu bạn không thấy tên phần này, tức là không có kết nối nào thuộc loại này dành cho bạn.

1. Nhập **ID nhà quảng cáo RollWorks** của bạn [Có thể quảng cáo trên RollWorks](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).

3. Trong phần **So khớp dữ liệu**, trong trường **Email**, chọn trường trong hồ sơ khách hàng hợp nhất trình bày địa chỉ email của khách hàng. Bạn phải xuất các phân khúc sang RollWorks.

1. Chọn phân khúc mà bạn muốn xuất. Chọn một phân khúc có ít nhất 100 thành viên. Bạn không thể xuất các phân khúc nhỏ hơn. Ngoài ra, kích thước tối đa của một phân khúc để xuất là 250.000 thành viên cho mỗi lần xuất. 

1. Chọn **Lưu**.

Việc lưu một nội dung xuất sẽ không chạy nội dung xuất đó ngay lập tức.

Nội dung xuất chạy trong mỗi lần [làm mới theo lịch trình](system.md#schedule-tab). Bạn cũng có thể [xuất dữ liệu theo yêu cầu](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Quyền riêng tư về dữ liệu và sự tuân thủ

Khi bật Dynamics 365 Customer Insights để truyền dữ liệu đến RollWorks, bạn cho phép chuyển dữ liệu ra bên ngoài ranh giới tuân thủ của Dynamics 365 Customer Insights, bao gồm cả dữ liệu có thể nhạy cảm như Dữ liệu cá nhân. Microsoft sẽ chuyển những dữ liệu đó theo chỉ dẫn của bạn, nhưng bạn có trách nhiệm đảm bảo rằng RollWorks đáp ứng mọi nghĩa vụ về quyền riêng tư hoặc bảo mật mà bạn có thể có. Để biết thêm thông tin, hãy xem [Tuyên bố về Quyền riêng tư của Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Quản trị viên Dynamics 365 Customer Insights của bạn có thể xóa đích xuất này bất cứ lúc nào để ngừng việc sử dụng chức năng này.
