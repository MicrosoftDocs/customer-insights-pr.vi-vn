---
title: Xuất dữ liệu Thông tin chi tiết về khách hàng sang Braze
description: Tìm hiểu cách định cấu hình kết nối và xuất sang Braze.
ms.date: 03/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: bfc9b34506dc3385b5edf12b31e74d05f2d20655
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 04/27/2022
ms.locfileid: "8644009"
---
# <a name="export-segment-lists-to-braze-preview"></a>Xuất danh sách phân đoạn sang Braze (xem trước)

Xuất các phân đoạn hồ sơ khách hàng hợp nhất sang Braze và sử dụng chúng cho các hoạt động tiếp thị.

## <a name="prerequisites"></a>Điều kiện tiên quyết

-   Bạn có một [Braze tài khoản](https://www.braze.com/) và thông tin đăng nhập quản trị viên tương ứng.
-   Bạn có [phân đoạn được định cấu hình](segments.md) trong Thông tin chi tiết về khách hàng.
-   Hồ sơ khách hàng hợp nhất trong các phân đoạn đã xuất chứa trường đại diện cho địa chỉ email và ID khách hàng Braze. 

## <a name="known-limitations"></a>Các hạn chế đã biết

- Xuất sang Braze bị giới hạn ở các phân đoạn.
- Quá trình xuất lên đến 1 triệu hồ sơ khách hàng sang Braze có thể mất tới 40 phút để hoàn thành. 
- Số lượng hồ sơ khách hàng mà bạn có thể xuất sang Braze phụ thuộc và bị giới hạn vào hợp đồng của bạn với Braze.

## <a name="set-up-connection-to-braze"></a>Thiết lập kết nối với Braze

1. Đi đến **Quản trị viên** > **Kết nối**.

1. Lựa chọn **Thêm kết nối** và lựa chọn **Braze** để cấu hình kết nối.

1. Đặt tên dễ nhận biết cho kết nối trong trường **Tên hiển thị**. Tên và loại kết nối mô tả kết nối này. Bạn nên chọn một tên giải thích mục đích và mục tiêu của kết nối.

1. Chọn người có thể sử dụng kết nối này. Nếu bạn không thực hiện hành động nào, giá trị mặc định sẽ là Quản trị viên. Để biết thêm thông tin, hãy xem [Cho phép người đóng góp sử dụng một kết nối cho các lần xuất](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Cung cấp của bạn [Khóa API Braze](https://www.braze.com/docs/api/basics/) để tiếp tục đăng nhập. 

1. Chọn **Tôi đồng ý** để xác nhận **Quyền riêng tư về dữ liệu và sự tuân thủ**.

1. Lựa chọn **Kết nối** để khởi tạo kết nối với Braze.

1. Chọn **Thêm chính bạn là người dùng xuất** và cung cấp thông tin xác thực Customer Insights.

1. Chọn **Lưu** để hoàn thành kết nối.

## <a name="configure-an-export"></a>Định cấu hình xuất

Bạn có thể định cấu hình lần xuất này nếu bạn có quyền truy cập vào kết nối thuộc loại này. Để biết thêm thông tin, hãy xem [Các quyền cần thiết để định cấu hình xuất](export-destinations.md#set-up-a-new-export).

1. Đi tới **Dữ liệu** > **Nội dung xuất**.

1. Để tạo một nội dung xuất mới, hãy chọn **Thêm đích**.

1. Bên trong **Kết nối để xuất**, hãy chọn một kết nối từ phần Braze. Nếu bạn không thấy tên phần này, tức là không có kết nối nào thuộc loại này dành cho bạn.  

3. Bên trong **Đối sánh dữ liệu** phần, trong **E-mail**, hãy chọn trường đại diện cho địa chỉ email của khách hàng, trong trường "ID khách hàng", hãy chọn trường đại diện cho Braze ID của khách hàng. Bắt buộc phải xuất các phân đoạn sang Braze. Các phân đoạn trong Braze sẽ được tạo với cùng tên của phân đoạn như trong Dynamics 365 Customer Insights. Bạn có thể chọn các trường bổ sung, tùy chọn để phù hợp với dữ liệu. 

1. Chọn **Lưu.**

Việc lưu một nội dung xuất sẽ không chạy nội dung xuất đó ngay lập tức.

Nội dung xuất chạy trong mỗi lần [làm mới theo lịch trình](system.md#schedule-tab). Bạn cũng có thể [xuất dữ liệu theo yêu cầu](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Quyền riêng tư về dữ liệu và sự tuân thủ

Khi bạn bật Dynamics 365 Customer Insights để truyền dữ liệu tới Braze, bạn cho phép chuyển dữ liệu ra bên ngoài ranh giới tuân thủ đối với Dynamics 365 Customer Insights, bao gồm dữ liệu nhạy cảm tiềm ẩn như Dữ liệu cá nhân. Microsoft sẽ chuyển những dữ liệu đó theo chỉ dẫn của bạn, nhưng bạn có trách nhiệm đảm bảo rằng Braze đáp ứng mọi nghĩa vụ về quyền riêng tư hoặc bảo mật mà bạn có thể có. Để biết thêm thông tin, hãy xem [Tuyên bố về Quyền riêng tư của Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Quản trị viên Dynamics 365 Customer Insights của bạn có thể xóa đích xuất này bất cứ lúc nào để ngừng việc sử dụng chức năng này.
