---
title: Xuất dữ liệu Customer Insights sang Marketo
description: Tìm hiểu cách định cấu hình kết nối với Marketo.
ms.date: 11/12/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: e0245f2d01aabc86f43532822c056965ff7ae67a
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267107"
---
# <a name="connector-for-marketo-preview"></a>Trình kết nối cho Marketo (bản xem trước)

Xuất các phân đoạn hồ sơ khách hàng hợp nhất để tạo chiến dịch, cung cấp email tiếp thị và tận dụng các nhóm khách hàng cụ thể với Marketo.

## <a name="prerequisites"></a>Điều kiện tiên quyết

-   Bạn có một [Tài khoản Marketo](https://login.marketo.com/) và thông tin đăng nhập quản trị viên tương ứng.
-   Có danh sách hiện có trong Marketo và các ID tương ứng. Để biết thêm thông tin, hãy xem phần [Danh sách Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).
-   Bạn có [các phân đoạn được định cấu hình](segments.md).
-   Hồ sơ khách hàng hợp nhất trong các phân đoạn đã xuất chứa các trường đại diện cho địa chỉ email.

## <a name="connect-to-marketo"></a>Kết nối với Marketo

1. Đi tới **Quản trị viên** > **Đích xuất**.

1. Trong **Marketo**, chọn **Thiết lập**.

1. Trong trường **Tên hiển thị**, hãy đặt cho đích xuất một cái tên dễ nhận biết.

1. Nhập **[ID máy khách Marketo, Mã bí mật máy khách và Tên máy chủ điểm cuối REST](https://developers.marketo.com/rest-api/authentication/)**.

1. Nhập **[ID danh sách Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)** 

1. Chọn **Tôi đồng ý** để xác nhận **Quyền riêng tư về dữ liệu và sự tuân thủ** và chọn **Kết nối** để khởi tạo kết nối với Marketo.

1. Chọn **Thêm chính bạn là người dùng xuất** và cung cấp thông tin xác thực Customer Insights.

   :::image type="content" source="media/export-connect-marketo.png" alt-text="Xuất ảnh chụp màn hình cho kết nối Marketo":::

1. Chọn **Tiếp** để định cấu hình xuất.

## <a name="configure-the-connector"></a>Đặt cấu hình trình kết nối

1. Trong phần **So khớp dữ liệu**, trong trường **Email**, chọn trường trong hồ sơ khách hàng hợp nhất trình bày địa chỉ email của khách hàng. 

1. Theo tùy chọn, bạn có thể xuất **Tên**, **Họ**, **Thành phố**, **Tiểu bang** và **Quốc gia/Khu vực** dưới dạng các trường bổ sung để tạo email cá nhân hóa hơn. Chọn **Thêm thuộc tính** để ánh xạ những trường này.

1. Chọn phân khúc mà bạn muốn xuất. Bạn có thể xuất tổng cộng tối đa 1 triệu hồ sơ khách hàng sang Marketo.

   :::image type="content" source="media/export-segment-marketo.png" alt-text="Chọn các trường và phân đoạn để xuất sang Marketo":::

1. Chọn **Lưu**.

## <a name="export-the-data"></a>Xuất dữ liệu

Bạn có thể [xuất dữ liệu theo nhu cầu](export-destinations.md). Mỗi lần [làm mới theo lịch](system.md#schedule-tab), tác vụ xuất cũng sẽ chạy. Trong Marketo, bạn hiện có thể tìm thấy các phân đoạn của mình trong [Danh sách Marketo](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).

## <a name="known-limitations"></a>Các giới hạn đã biết

- Lên đến 1 triệu hồ sơ mỗi lần xuất sang Marketo.
- Việc xuất sang Marketo bị giới hạn ở các phân đoạn.
- Quá trình xuất phân đoạn với tổng số 1 triệu hồ sơ có thể mất đến 3 giờ. 
- Số lượng hồ sơ mà bạn có thể xuất sang Marketo phụ thuộc và giới hạn vào hợp đồng của bạn với Marketo.

## <a name="data-privacy-and-compliance"></a>Quyền riêng tư về dữ liệu và tuân thủ

Khi bật Dynamics 365 Customer Insights để truyền dữ liệu tới Marketo, bạn cho phép chuyển dữ liệu ra bên ngoài ranh giới tuân thủ cho Dynamics 365 Customer Insights, bao gồm dữ liệu nhạy cảm tiềm ẩn như Dữ liệu cá nhân. Microsoft sẽ chuyển những dữ liệu đó theo chỉ dẫn của bạn, nhưng bạn có trách nhiệm đảm bảo rằng Marketo đáp ứng mọi nghĩa vụ về quyền riêng tư hoặc bảo mật mà bạn có thể có. Để biết thêm thông tin, hãy xem [Tuyên bố về Quyền riêng tư của Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Quản trị viên Dynamics 365 Customer Insights của bạn có thể xóa đích xuất này bất cứ lúc nào để ngừng sử dụng chức năng này.


[!INCLUDE[footer-include](../includes/footer-banner.md)]