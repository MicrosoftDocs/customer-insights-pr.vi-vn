---
title: Xuất dữ liệu Customer Insights sang Google Ads
description: Tìm hiểu cách định cấu hình kết nối với Google Ads.
ms.date: 11/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 06aa0b6ff3125d8735adc8c8f9f6dad69087d9f8
ms.sourcegitcommit: ff824bbbd31fd666ab0da682bf48ea31580d242c
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 11/18/2020
ms.locfileid: "4568520"
---
# <a name="connector-for-google-ads-preview"></a>Trình kết nối cho Google Ads (bản xem trước)

Xuất các phân đoạn hồ sơ khách hàng hợp nhất sang danh sách đối tượng Google Ads và sử dụng chúng để quảng cáo trên Google Tìm kiếm, Gmail, YouTube và Mạng hiển thị của Google. 

## <a name="prerequisites"></a>Điều kiện tiên quyết

-   Bạn có một [Tài khoản Google Ads](https://ads.google.com/) và thông tin đăng nhập quản trị viên tương ứng.
-   Có đối tượng hiện có trong Google Ads và các ID tương ứng. Để biết thêm thông tin, hãy xem [Đối tượng Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).
-   Bạn có [các phân đoạn được định cấu hình](segments.md)
-   Hồ sơ khách hàng hợp nhất trong các phân đoạn đã xuất chứa các trường đại diện cho địa chỉ email, tên và họ

## <a name="connect-to-google-ads"></a>Kết nối với Google Ads

1. Đi tới **Quản trị viên** > **Đích xuất**.

1. Trong **Google Ads**, chọn **Thiết lập**.

1. Trong trường **Tên hiển thị**, hãy đặt cho đích xuất một cái tên dễ nhận biết.

1. Nhập **[ID khách hàng Google Ads](https://support.google.com/google-ads/answer/1704344)**.

1. Nhập **[Mã thông báo nhà phát triển được Google Ads phê duyệt](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.

1. Chọn **Tôi đồng ý** để xác nhận **Quyền riêng tư về dữ liệu và sự tuân thủ**.

1. Nhập **[ID đối tượng Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** và chọn **Kết nối** để khởi tạo kết nối với Google Ads.

1. Chọn **Xác thực bằng Google Ads** và cung cấp thông tin đăng nhập Google Ads của bạn.

1. Chọn **Thêm chính bạn là người dùng xuất** và cung cấp thông tin xác thực Customer Insights.

   :::image type="content" source="media/export-segments-googleads.PNG" alt-text="Xuất ảnh chụp màn hình cho kết nối Google Ads":::

1. Chọn **Tiếp** để định cấu hình xuất.

## <a name="configure-the-connector"></a>Đặt cấu hình trình kết nối

1. Trong phần **So khớp dữ liệu**, trong trường **Email**, chọn trường trong hồ sơ khách hàng hợp nhất trình bày địa chỉ email của khách hàng. Lặp lại các bước tương tự cho các trường **Tên** và **Họ**.

1. Chọn phân khúc mà bạn muốn xuất. Bạn có thể xuất tổng cộng tối đa 1 triệu hồ sơ khách hàng sang Google Ads.

1. Chọn **Lưu**.

## <a name="export-the-data"></a>Xuất dữ liệu

Bạn có thể [xuất dữ liệu theo nhu cầu](export-destinations.md). Mỗi lần [làm mới theo lịch](system.md#schedule-tab), tác vụ xuất cũng sẽ chạy. Trong Google Ads, bạn hiện có thể tìm thấy các phân đoạn của mình trong [Đối tượng Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en/).

## <a name="known-limitations"></a>Các giới hạn đã biết

- Lên đến 1 triệu hồ sơ mỗi lần xuất sang Google Ads.
- Việc xuất sang Google Ads bị giới hạn ở các phân đoạn.
- Việc xuất các phân đoạn với tổng số 1 triệu hồ sơ có thể mất đến 5 phút vì những hạn chế từ phía nhà cung cấp. 
- Quá trình so khớp trong Google Ads có thể mất đến 48 giờ.

## <a name="data-privacy-and-compliance"></a>Quyền riêng tư về dữ liệu và tuân thủ

Khi bật Dynamics 365 Customer Insights để truyền dữ liệu tới Google Ads, bạn cho phép chuyển dữ liệu ra bên ngoài ranh giới tuân thủ cho Dynamics 365 Customer Insights, bao gồm dữ liệu nhạy cảm tiềm ẩn như Dữ liệu cá nhân. Microsoft sẽ chuyển những dữ liệu đó theo chỉ dẫn của bạn, nhưng bạn có trách nhiệm đảm bảo rằng Google Ads đáp ứng mọi nghĩa vụ về quyền riêng tư hoặc bảo mật mà bạn có thể có. Để biết thêm thông tin, hãy xem [Tuyên bố về Quyền riêng tư của Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Quản trị viên Dynamics 365 Customer Insights của bạn có thể xóa đích xuất này bất cứ lúc nào để ngừng sử dụng chức năng này.
