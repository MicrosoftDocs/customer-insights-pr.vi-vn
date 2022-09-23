---
title: Quản lý hồ sơ không xác định với Thông tin chi tiết về khách hàng
description: Làm việc với hồ sơ khách hàng không xác định được tạo và quản lý trong Dynamics 365 Customer Insights.
ms.date: 09/14/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: andtapia
ms.author: andreatapia
manager: shellyha
ms.openlocfilehash: d7e5050ee5832df5ecf40a352f7ea8d42830fa45
ms.sourcegitcommit: f6b6a4c4ce9cf12e449488b24aab80a2cbfe0c47
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 09/21/2022
ms.locfileid: "9556422"
---
# <a name="manage-unknown-profiles-with-customer-insights"></a>Quản lý hồ sơ không xác định với Thông tin chi tiết về khách hàng

Người dùng Internet thường không được xác định danh tính và ẩn danh trên mạng. Nếu họ không đăng nhập vì họ sử dụng các thiết bị hoặc kênh khác nhau, điều đó thậm chí đúng với những khách hàng trung thành nhất. Với việc cookie của bên thứ ba có thể sẽ sớm biến mất, việc quản lý tùy chọn của người dùng dựa trên dữ liệu của bên thứ nhất là rất quan trọng để đạt được trải nghiệm được cá nhân hóa khác biệt. Đối với nhiều thương hiệu, người dùng đã biết hoặc đã xác thực là thiểu số mặc dù kỳ vọng của khách hàng ngày càng tăng về cá nhân hóa. Thật tuyệt vời cho các doanh nghiệp khi biết khách hàng của họ là ai, dựa trên dữ liệu đáng tin cậy, chi tiết và thống nhất.

Cá nhân hóa đáng nhớ phụ thuộc vào sự phong phú và đầy đủ của dữ liệu khách hàng của bạn và Thông tin chi tiết về khách hàng giúp bạn đạt được những mục tiêu này. Bạn không phải giới hạn hoặc ngừng sử dụng dữ liệu được thu thập khi bắt đầu hành trình của khách hàng. Thông tin chi tiết về khách hàng cho phép bạn sử dụng dữ liệu của riêng mình để tạo hồ sơ khách hàng cho những người dùng không xác định. Sau đó, bạn có thể sử dụng hồ sơ đó cho các hành động khác, mặc dù thiếu thông tin liên hệ. Nhập dữ liệu của bên thứ nhất từ các nguồn như web, thiết bị di động hoặc hệ thống CRM vào Thông tin chi tiết về khách hàng để liên tục làm phong phú hồ sơ khách hàng. Khi bạn hợp nhất nhiều tương tác hơn, [biến *không xác định* khách hàng thành một *đã biết* khách hàng](unknown-to-known.md).

## <a name="sample-scenario"></a>Kịch bản mẫu

Thương mại điện tử là kênh phát triển nhanh nhất trong thập kỷ qua. Giả sử một người dùng sử dụng thiết bị di động của họ để duyệt trang thương mại điện tử của bạn. Trang web chỉ định khách truy cập "mobile_guest123" làm số nhận dạng duy nhất và bạn bắt đầu thu thập các hoạt động hành vi dựa trên hoạt động trực tuyến của họ. Ví dụ: họ đã truy cập những trang nào, họ đã dành bao nhiêu thời gian trên những trang đó hoặc họ đã nhấp vào liên kết nào. Bạn không biết tên hoặc địa chỉ email của họ, nhưng dữ liệu này có thể giúp cung cấp cho các thương hiệu thông tin chi tiết có ý nghĩa về người dùng cụ thể này. Đổi lại, bạn có thể đưa những thông tin chi tiết đó hoạt động vào lần tiếp theo người dùng truy cập trang web. Truy vấn Thông tin chi tiết về khách hàng cho "mobile_guest123" để truy xuất danh sách phân khúc của người dùng, chẳng hạn như "không phải trả tiền", "khách hàng đặt trước trên thiết bị di động", "khách hàng có giá trị cao", v.v. hoặc truy xuất hồ sơ để tạo trải nghiệm web được cá nhân hóa. Bạn cũng có thể xuất dữ liệu sang bất kỳ hệ thống kích hoạt nào để làm điều tương tự.

## <a name="prerequisites"></a>Điều kiện tiên quyết

- Nhập dữ liệu của bên thứ nhất vào Thông tin chi tiết về khách hàng
- Mỗi thực thể có một ID duy nhất được đặt làm khóa chính
- Mỗi thực thể có khóa chính để cá nhân hóa là hợp nhất
- Hệ thống quản lý nội dung trên trang web của bạn có thể sử dụng các API (để cá nhân hóa web dựa trên giao tiếp trực tiếp với Customer Insights)

Bảng sau đây cho thấy một ví dụ đơn giản về cách các sự kiện web có giá trị cao có thể được ghi lại.

|EventID|EventTimeStamp|Tên người dùng|Khóa chính|EventName|
|--|--|--|--|--|
|1|09-15-2022 9:00:00|abc123|CookieID1|Xem sản phẩm|
|2|09-18-2022 10:05:00|abc123|CookieID1|Xem sản phẩm|
|3|09-18-2022 10:10:00|abc123|CookieID1|Thêm vào giỏ|
|Tệp 4|09-21-2022 09:05:00|abc123|CookieID1|Xem sản phẩm|

## <a name="data-ingestion"></a>Nhập dữ liệu

Để biết thêm thông tin về các tùy chọn có sẵn để nhập dữ liệu, hãy xem [Tổng quan về nguồn dữ liệu](data-sources.md).

## <a name="data-unification"></a>Hợp nhất dữ liệu

Để biết thêm thông tin về việc hợp nhất hồ sơ khách hàng, hãy xem [Tổng quan về hợp nhất dữ liệu](data-unification.md).

## <a name="get-insights"></a>Tải thông tin chuyên sâu

[Làm giàu](enrichment-hub.md) dữ liệu của bạn, xây dựng [đo](measures.md) và tạo [phân đoạn](segments.md) để kích hoạt thêm.

Ví dụ: bạn có thể tạo phân đoạn người dùng không xác định đã duyệt qua các trang sản phẩm giống nhau nhưng chưa bao giờ hoàn thành thanh toán.

## <a name="activation"></a>Kích hoạt

Với dữ liệu của bạn trong Thông tin chi tiết về khách hàng và thông tin chi tiết của bạn đã sẵn sàng hoạt động, bạn có thể sử dụng Thông tin chi tiết về khách hàng để cá nhân hóa:

1. Sử dụng [API OData](apis.md) để truy xuất thành viên phân khúc hoặc hồ sơ khách hàng Để biết thêm ví dụ, hãy xem [Ví dụ về truy vấn OData cho API thông tin chi tiết về khách hàng](odata-examples.md).

1. [Xuất khẩu](export-destinations.md) dữ liệu của bạn vào hệ thống kích hoạt của bạn.

Ví dụ: Một người dùng không xác định truy cập trang web nhiều lần và truy cập các trang sản phẩm để tìm nhiều mẫu giày da khác nhau. Với dữ liệu đó có sẵn trong Thông tin chi tiết về khách hàng, bạn có thể đưa người dùng không xác định vào phân khúc những người quan tâm đến giày da. Sử dụng phân đoạn này để thông báo cho việc xây dựng trang web của bạn được cá nhân hóa cho những khách truy cập trở lại. Trong lần truy cập tiếp theo, trang web nhận ra người dùng không xác định và có thể cung cấp cho họ phiếu giảm giá 10% cho giày da.

[!INCLUDE [footer-include](includes/footer-banner.md)]
