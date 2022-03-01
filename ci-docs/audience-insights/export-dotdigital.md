---
title: Xuất dữ liệu Customer Insights sang DotDigital
description: Tìm hiểu cách định cấu hình kết nối với DotDigital.
ms.date: 11/14/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ed6bd40e8575fc90258f79f60abffe54f136d274
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644474"
---
# <a name="connector-for-dotdigital-preview"></a>Trình kết nối cho DotDigital (bản xem trước)

Xuất các phân đoạn hồ sơ khách hàng hợp nhất sang sổ địa chỉ DotDigital và sử dụng chúng cho các chiến dịch, tiếp thị qua email và để xây dựng phân khúc khách hàng với DotDigital. 

## <a name="prerequisites"></a>Điều kiện tiên quyết

-   Bạn có một [Tài khoản DotDigital](https://dotdigital.com/) và thông tin đăng nhập quản trị viên tương ứng.
-   Có sổ địa chỉ hiện có trong DotDigital và các ID tương ứng. Có thể tìm thấy ID trong URL khi bạn chọn và mở sổ địa chỉ. Để biết thêm thông tin, hãy xem [Sổ địa chỉ DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).
-   Bạn có [các phân đoạn được định cấu hình](segments.md) trong thông tin chi tiết về đối tượng.
-   Hồ sơ khách hàng hợp nhất trong các phân đoạn đã xuất chứa các trường đại diện cho địa chỉ email.

## <a name="connect-to-dotdigital"></a>Kết nối với DotDigital

1. Đi tới **Quản trị viên** > **Đích xuất**.

1. Trong **DotDigital**, chọn **Thiết lập**.

1. Trong trường **Tên hiển thị**, hãy đặt cho đích xuất một cái tên dễ nhận biết.

   :::image type="content" source="media/DotDigital_config.PNG" alt-text="Ngăn cấu hình để xuất DotDigital.":::

1. Nhập **Tên người dùng và mật khẩu DotDigital**.

1. Nhập **[ID sổ địa chỉ DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.

1. Chọn **Tôi đồng ý** để xác nhận **Quyền riêng tư về dữ liệu và sự tuân thủ**.

1. Chọn **Kết nối** để khởi tạo kết nối với DotDigital.

1. Chọn **Thêm chính bạn là người dùng xuất** và cung cấp thông tin xác thực Customer Insights.

1. Chọn **Tiếp** để định cấu hình xuất.

## <a name="configure-the-connector"></a>Đặt cấu hình trình kết nối

1. Trong phần **So khớp dữ liệu**, trong trường **Email**, chọn trường trong hồ sơ khách hàng hợp nhất trình bày địa chỉ email của khách hàng. Lặp lại các bước tương tự cho các trường tùy chọn khác như **Tên**, **Họ**, **Họ và tên**, **Giới tính** và **Mã bưu điện**.

1. Chọn phân khúc mà bạn muốn xuất. Bạn có thể xuất tổng cộng tối đa 1 triệu hồ sơ khách hàng sang DotDigital.

1. Chọn **Lưu**.

## <a name="export-the-data"></a>Xuất dữ liệu

Bạn có thể [xuất dữ liệu theo nhu cầu](export-destinations.md). Mỗi lần [làm mới theo lịch](system.md#schedule-tab), tác vụ xuất cũng sẽ chạy. Trong DotDigital, bây giờ bạn có thể tìm thấy các phân đoạn của mình trong [Sổ địa chỉ DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).

## <a name="known-limitations"></a>Các giới hạn đã biết

- Lên đến 1 triệu hồ sơ mỗi lần xuất sang DotDigital.
- Việc xuất sang DotDigital bị giới hạn ở các phân đoạn.
- Việc xuất các phân đoạn với tổng số 1 triệu hồ sơ có thể mất đến 3 giờ vì những hạn chế từ phía nhà cung cấp. 
- Số lượng hồ sơ mà bạn có thể xuất sang DotDigital phụ thuộc và giới hạn vào hợp đồng của bạn với DotDigital.

## <a name="data-privacy-and-compliance"></a>Quyền riêng tư về dữ liệu và tuân thủ

Khi bật Dynamics 365 Customer Insights để truyền dữ liệu tới DotDigital, bạn cho phép chuyển dữ liệu ra bên ngoài ranh giới tuân thủ cho Dynamics 365 Customer Insights, bao gồm dữ liệu nhạy cảm tiềm ẩn như Dữ liệu cá nhân. Microsoft sẽ chuyển những dữ liệu đó theo chỉ dẫn của bạn, nhưng bạn có trách nhiệm đảm bảo rằng DotDigital đáp ứng mọi nghĩa vụ về quyền riêng tư hoặc bảo mật mà bạn có thể có. Để biết thêm thông tin, hãy xem [Tuyên bố về Quyền riêng tư của Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Quản trị viên Dynamics 365 Customer Insights của bạn có thể xóa đích xuất này bất cứ lúc nào để ngừng sử dụng chức năng này.
