---
title: Quản lý hồ sơ không xác định với Customer Insights
description: Làm việc với hồ sơ khách hàng không xác định được tạo và quản lý trong Dynamics 365 Customer Insights.
ms.date: 09/14/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: andtapia
ms.author: andreatapia
manager: shellyha
ms.openlocfilehash: 0e12f64a22b93d117009fb8aee76d02a7583e699
ms.sourcegitcommit: 24627d53dcdf607baaab1cc3c299a3584c386173
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 11/15/2022
ms.locfileid: "9776847"
---
# <a name="manage-unknown-profiles-with-customer-insights"></a>Quản lý hồ sơ không xác định với Customer Insights

Người dùng Internet thường không được xác định hoặc ẩn danh trực tuyến. Ngay cả những khách hàng trung thành nhất cũng có thể bị coi là "không xác định" nếu họ không đăng nhập trên các thiết bị khác nhau. Đối với nhiều thương hiệu, người dùng đã biết hoặc xác thực chiếm thiểu số mặc dù kỳ vọng của khách hàng về việc cá nhân hóa ngày càng tăng. Với tương lai của cookie bên thứ ba đang được đặt câu hỏi, thay vào đó, việc quản lý tùy chọn người dùng dựa trên dữ liệu của bên thứ nhất là rất quan trọng để đạt được trải nghiệm cá nhân hóa.

Cá nhân hóa đáng nhớ phụ thuộc vào mức độ hiểu biết của bạn về khách hàng và Customer Insights giúp bạn thực hiện điều đó bằng cách theo dõi tất cả khách hàng của mình.  Bạn không phải giới hạn hoặc ngừng sử dụng dữ liệu được thu thập khi bắt đầu hành trình của khách hàng. Thông tin chi tiết về khách hàng cho phép bạn sử dụng dữ liệu của riêng mình để tạo hồ sơ khách hàng cho những người dùng không xác định. Sau đó, bạn có thể sử dụng hồ sơ đó cho các hành động tiếp theo, mặc dù thiếu thông tin liên hệ. Nhập dữ liệu của bên thứ nhất từ các nguồn như web, thiết bị di động hoặc hệ thống CRM vào Customer Insights để liên tục làm phong phú thêm hồ sơ khách hàng. Khi bạn hợp nhất nhiều tương tác hơn, [biến *không xác định* khách hàng thành một *đã biết* khách hàng](unknown-to-known.md).

## <a name="sample-scenario"></a>Kịch bản mẫu

Giả sử người dùng sử dụng thiết bị di động của họ để duyệt trang web thương mại điện tử của bạn. Trang web chỉ định khách truy cập "mobile_guest123" làm mã định danh duy nhất và bạn bắt đầu thu thập các hoạt động hành vi dựa trên hoạt động trực tuyến của họ. Ví dụ: họ đã truy cập những trang nào, họ đã dành bao nhiêu thời gian cho những trang đó hoặc họ đã nhấp vào liên kết nào. Bạn không biết tên hoặc địa chỉ email của họ nhưng dữ liệu này có thể giúp cung cấp cho thương hiệu những hiểu biết có ý nghĩa về người dùng cụ thể này. Đổi lại, bạn có thể đưa những thông tin chi tiết đó hoạt động vào lần tiếp theo khi người dùng đó truy cập trang web. Truy vấn Customer Insights cho "mobile_guest123" để truy xuất danh sách phân khúc của người dùng, chẳng hạn như "không phải trả tiền", "khách hàng đặt hàng trước trên thiết bị di động", "khách hàng có giá trị cao", v.v. hoặc truy xuất hồ sơ để tạo trải nghiệm web được cá nhân hóa. Bạn cũng có thể xuất dữ liệu sang bất kỳ hệ thống kích hoạt nào để làm điều tương tự.

## <a name="prerequisites"></a>Điều kiện tiên quyết

- Nhập dữ liệu của bên thứ nhất vào Customer Insights
- Mỗi thực thể có một ID duy nhất được đặt làm khóa chính
- Mỗi thực thể có khóa chính để cá nhân hóa được thống nhất
- Hệ thống quản lý nội dung trên trang web của bạn có thể sử dụng API (để cá nhân hóa web dựa trên giao tiếp trực tiếp với Customer Insights)

Bảng sau đây cho thấy một ví dụ đơn giản về cách các sự kiện web có giá trị cao có thể được ghi lại.

|ID sự kiện|Thời gian sự kiệnStamp|Tên người dùng|Khóa chính|Tên sự kiện|
|--|--|--|--|--|
|1|09-15-2022 9:00:00|abc123|CookieID1|xem sản phẩm|
|2|09-18-2022 10:05:00|abc123|CookieID1|xem sản phẩm|
|3|09-18-2022 10:10:00|abc123|CookieID1|Thêm vào giỏ|
|Tệp 4|09-21-2022 09:05:00|abc123|CookieID1|xem sản phẩm|

## <a name="data-ingestion"></a>Nhập dữ liệu

Để biết thêm thông tin về các tùy chọn có sẵn để nhập dữ liệu, hãy xem [Tổng quan về nguồn dữ liệu](data-sources.md)

## <a name="data-unification"></a>Hợp nhất dữ liệu

Để biết thêm thông tin về thống nhất hồ sơ khách hàng, hãy xem [Tổng quan về hợp nhất dữ liệu](data-unification.md) .

## <a name="get-insights"></a>Tải thông tin chuyên sâu

[làm giàu](enrichment-hub.md) dữ liệu của bạn, xây dựng [đo](measures.md) và tạo [phân đoạn](segments.md) để kích hoạt thêm.

Ví dụ: bạn có thể tạo các phân đoạn gồm những người dùng không xác định đã duyệt qua cùng một trang sản phẩm nhưng chưa bao giờ hoàn tất quy trình thanh toán.

## <a name="activation"></a>Kích hoạt

Với dữ liệu của bạn trong Customer Insights và thông tin chi tiết của bạn đã sẵn sàng hoạt động, bạn có thể sử dụng Customer Insights để cá nhân hóa:

1. Sử dụng [API OData](apis.md) để truy xuất tư cách thành viên phân khúc hoặc hồ sơ khách hàng Để biết thêm ví dụ, hãy xem [Ví dụ về truy vấn OData cho API Customer Insights](odata-examples.md) .

1. [Xuất khẩu](export-destinations.md) dữ liệu của bạn vào hệ thống kích hoạt của bạn.

Ví dụ: Một người dùng không xác định truy cập một trang web nhiều lần và truy cập các trang sản phẩm cho các mẫu giày da khác nhau. Với dữ liệu có sẵn trong Customer Insights, bạn có thể đưa người dùng chưa biết vào phân khúc những người quan tâm đến giày da. Sử dụng phân đoạn này để thông báo về quá trình cá nhân hóa bản dựng trang web của bạn cho những khách truy cập quay lại. Trong lần truy cập tiếp theo, trang web nhận ra người dùng không xác định và có thể cung cấp cho họ phiếu giảm giá 10% cho giày da.

[!INCLUDE [footer-include](includes/footer-banner.md)]
