---
title: Xuất dữ liệu Customer Insights sang Marketo
description: Tìm hiểu cách đặt cấu hình kết nối và xuất sang Marketo.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b5a644e286bd44d4ebf7d1837255326c005b48d6
ms.sourcegitcommit: 74cd4fa9cbb784d9dff174c0eec7b4dcb408d66b
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059342"
---
# <a name="export-segments-to-marketo-preview"></a>Xuất phân khúc sang Marketo (bản xem trước)

Xuất các phân đoạn hồ sơ khách hàng hợp nhất để tạo chiến dịch, cung cấp email tiếp thị và tận dụng các nhóm khách hàng cụ thể với Marketo.

## <a name="prerequisites-for-connection"></a>Điều kiện tiên quyết để kết nối

-   Bạn có một [Tài khoản Marketo](https://login.marketo.com/) và thông tin đăng nhập quản trị viên tương ứng.
-   Có danh sách hiện có trong Marketo và các ID tương ứng. Để biết thêm thông tin, hãy xem phần [Danh sách Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).
-   Bạn có [các phân đoạn được định cấu hình](segments.md).
-   Hồ sơ khách hàng hợp nhất trong các phân đoạn đã xuất chứa các trường đại diện cho địa chỉ email.

## <a name="known-limitations"></a>Các giới hạn đã biết

- Lên đến 1 triệu hồ sơ mỗi lần xuất sang Marketo.
- Việc xuất sang Marketo bị giới hạn ở các phân đoạn.
- Quá trình xuất phân đoạn với tổng số 1 triệu hồ sơ có thể mất đến 3 giờ. 
- Số lượng hồ sơ mà bạn có thể xuất sang Marketo phụ thuộc và giới hạn vào hợp đồng của bạn với Marketo.

## <a name="set-up-connection-to-marketo"></a>Thiết lập kết nối với Marketo

1. Đi đến **Quản trị viên** > **Kết nối**.

1. Chọn **Thêm kết nối** rồi chọn **Marketo** để đặt cấu hình kết nối.

1. Đặt tên dễ nhận biết cho kết nối trong trường **Tên hiển thị**. Tên và loại kết nối mô tả kết nối này. Bạn nên chọn một tên giải thích mục đích và mục tiêu của kết nối.

1. Chọn người có thể sử dụng kết nối này. Nếu bạn không thực hiện hành động nào, giá trị mặc định sẽ là Quản trị viên. Để biết thêm thông tin, hãy xem [Cho phép người đóng góp sử dụng một kết nối cho các lần xuất](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Nhập **[ID máy khách Marketo, Mã bí mật máy khách và Tên máy chủ điểm cuối REST](https://developers.marketo.com/rest-api/authentication/)**. Tên máy chủ điểm cuối REST chỉ là tên máy chủ, không có `https://`. Ví dụ: `xyz-abc-123.mktorest.com`. 

1. Chọn **Tôi đồng ý** để xác nhận **Quyền riêng tư về dữ liệu và sự tuân thủ** và chọn **Kết nối** để khởi tạo kết nối với Marketo.

1. Chọn **Thêm chính bạn là người dùng xuất** và cung cấp thông tin xác thực Customer Insights.

1. Chọn **Lưu** để hoàn thành kết nối.

## <a name="configure-an-export"></a>Đặt cấu hình xuất

Bạn có thể đặt cấu hình lần xuất này nếu bạn có quyền truy cập vào kết nối thuộc loại này. Để biết thêm thông tin, hãy xem [Các quyền cần thiết để đặt cấu hình xuất](export-destinations.md#set-up-a-new-export).

1. Đi tới **Dữ liệu** > **Nội dung xuất**.

1. Để tạo một nội dung xuất mới, hãy chọn **Thêm đích**.

1. Trong trường **Kết nối để xuất**, hãy chọn một kết nối từ phần Marketo. Nếu bạn không thấy tên phần này, tức là không có kết nối nào thuộc loại này dành cho bạn.

1. Nhập **[ID danh sách Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)** của bạn. ID danh sách là một giá trị số đơn thuần. Ví dụ: nếu ID danh sách Marketo của bạn là ST12345A7, hãy xóa ký tự đứng trước và sau các chữ số và nhập `12345`. 

1. Trong phần **So khớp dữ liệu**, trong trường **Email**, chọn trường trong hồ sơ khách hàng hợp nhất trình bày địa chỉ email của khách hàng. 

1. Bạn có thể tùy ý xuất **Tên**, **Họ**, **Thành phố**, **Tiểu bang** và **Quốc gia/Khu vực** để tạo thêm nhiều email được cá nhân hóa hơn. Chọn **Thêm thuộc tính** để ánh xạ những trường này.

1. Chọn phân khúc mà bạn muốn xuất. Bạn có thể xuất tổng cộng tối đa 1 triệu hồ sơ khách hàng sang Marketo.

1. Chọn **Lưu**.

Việc lưu một nội dung xuất sẽ không chạy nội dung xuất đó ngay lập tức.

Nội dung xuất chạy trong mỗi lần [làm mới theo lịch trình](system.md#schedule-tab). Bạn cũng có thể [xuất dữ liệu theo yêu cầu](export-destinations.md#run-exports-on-demand). Trong Marketo, bạn hiện có thể tìm thấy các phân đoạn của mình trong [Danh sách Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).


## <a name="data-privacy-and-compliance"></a>Quyền riêng tư về dữ liệu và sự tuân thủ

Khi bật Dynamics 365 Customer Insights để truyền dữ liệu tới Marketo, bạn cho phép chuyển dữ liệu ra bên ngoài ranh giới tuân thủ cho Dynamics 365 Customer Insights, bao gồm dữ liệu nhạy cảm tiềm ẩn như Dữ liệu cá nhân. Microsoft sẽ chuyển những dữ liệu đó theo chỉ dẫn của bạn, nhưng bạn có trách nhiệm đảm bảo rằng Marketo đáp ứng mọi nghĩa vụ về quyền riêng tư hoặc bảo mật mà bạn có thể có. Để biết thêm thông tin, hãy xem [Tuyên bố về Quyền riêng tư của Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Quản trị viên Dynamics 365 Customer Insights của bạn có thể xóa đích xuất này bất cứ lúc nào để ngừng sử dụng chức năng này.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
