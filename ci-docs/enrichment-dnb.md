---
title: Làm phong phú hồ sơ công ty với Dun & Bradstreet (xem trước)
description: Thông tin chung về cách làm giàu của bên thứ ba Dun & Bradstreet.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: e89b64774dcb519a071dd3d403473807a50e7f33
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 08/08/2022
ms.locfileid: "9237930"
---
# <a name="enrich-company-profiles-with-dun--bradstreet-preview"></a>Làm phong phú hồ sơ công ty với Dun & Bradstreet (xem trước)

Dun & Bradstreet cung cấp dữ liệu thương mại, phân tích và thông tin chi tiết cho các doanh nghiệp. Công ty này hỗ trợ hồ sơ khách hàng hợp nhất cho các công ty để tăng cường dữ liệu của họ. Sự phong phú bao gồm các thuộc tính như số DUNS, quy mô công ty, vị trí, ngành, v.v.

## <a name="prerequisites"></a>Điều kiện tiên quyết

- Một hoạt động [Dun & Bradstreet](https://www.dnb.com/marketing/media/give-your-data-a-boost.html?source=microsoft_audience_insights) giấy phép.
- [Hồ sơ khách hàng hợp nhất](customer-profiles.md) cho các công ty.
- A Dun & Bradstreet [dự án](#set-up-your-dun--bradstreet-project) đã thiết lập.
- A Dun & Bradstreet [sự liên quan](connections.md) Là [đã cấu hình](#configure-a-connection-for-dun--bradstreet) bởi một quản trị viên.

## <a name="set-up-your-dun--bradstreet-project"></a>Thiết lập dự án Dun & Bradstreet của bạn

Là người dùng được cấp phép của Dun & Bradstreet, bạn có thể thiết lập một dự án trong [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights).

1. đăng nhập vào [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights). Để truy xuất thông tin đăng nhập, [khôi phục mật khẩu của bạn](https://sso.dnb.com/signin/forgot-password?lead_source=microsoft_audienceinsights).

1. Tải xuống [tệp mẫu csv của chúng tôi](https://c360devenrichment.blob.core.windows.net/mapping/DnBCIdatamapping.csv) sẽ được sử dụng để ánh xạ các trường Thông tin chi tiết về khách hàng với các trường Dun & Bradstreet tương ứng.

1. Tải lên tệp trong **Tải dữ liệu lên** bước của trải nghiệm tạo dự án Dun & Bradstreet.

1. Chọn các dấu chấm ngang dưới liên quan **nguồn** trong dự án Dun & Bradstreet mới được tạo để xem các tùy chọn có sẵn.

   :::image type="content" source="media/enrichment-dnb-dots.png" alt-text="Ảnh chụp màn hình các dấu chấm trong một dự án Dun & Bradstreet.":::

1. Chọn **Nhận thông tin chi tiết về S3**. Lưu trữ thông tin này ở một nơi an toàn. Bạn sẽ cần nó để [thiết lập kết nối để làm giàu](#configure-a-connection-for-dun--bradstreet) trong Thông tin chi tiết về khách hàng.

   :::image type="content" source="media/enrichment-dnb-s3info.png" alt-text="Ảnh chụp màn hình lựa chọn thông tin s3 trong một dự án Dun & Bradstreet.":::

## <a name="configure-a-connection-for-dun--bradstreet"></a>Định cấu hình kết nối cho Dun & Bradstreet

Bạn phải là một [người quản lý](permissions.md#admin) trong Thông tin chi tiết về khách hàng và có bằng chứng xác thực từ Dun & Bradstreet Connect.

1. Lựa chọn **Thêm kết nối** khi định cấu hình phần bổ sung hoặc đi đến **Quản trị viên** > **Kết nối** và chọn **Cài đặt** trên ngói Dun & Bradstreet.

1. Nhập tên cho kết nối.

1. Cung cấp thông tin đăng nhập Dun & Bradstreet hợp lệ và chi tiết dự án Dun & Bradstreet *Khu vực, đường dẫn thư mục Drop và tên thư mục Drop*. Bạn [lấy thông tin này](#set-up-your-dun--bradstreet-project) từ dự án Dun & Bradstreet.

1. Xem lại [quyền riêng tư và tuân thủ dữ liệu](connections.md#data-privacy-and-compliance) và chọn **tôi đồng ý**.

1. Lựa chọn **Kiểm chứng** để xác thực cấu hình và sau đó chọn **Tiết kiệm**.

   :::image type="content" source="media/enrichment-dnb-connection.png" alt-text="Trang cấu hình kết nối Dun & Bradstreet.":::

## <a name="supported-countries-or-regions"></a>Các quốc gia hoặc khu vực được hỗ trợ

Chúng tôi hiện hỗ trợ các tùy chọn quốc gia / khu vực sau: Canada (tiếng Anh) hoặc Hoa Kỳ (tiếng Anh).

## <a name="configure-the-enrichment"></a>Đặt cấu hình dữ liệu tăng cường

1. Đi đến **Dữ liệu** > **Tăng cường** rồi chọn tab **Khám phá**.

1. Lựa chọn **Làm phong phú dữ liệu của tôi** trên **Dữ liệu công ty** cho ngói Dun & Bradstreet.

   :::image type="content" source="media/enrichment-dnb-tile.png" alt-text="Ảnh chụp màn hình lát gạch Dun & Bradstreet.":::

1. Xem lại tổng quan và sau đó chọn **Tiếp theo**.

1. Chọn kết nối và xác nhận. Liên hệ với quản trị viên nếu không có kết nối.

1. Chọn **Tiếp theo**.

1. Chọn **Tập dữ liệu khách hàng** và chọn hồ sơ hoặc phân đoạn bạn muốn làm phong phú thêm với dữ liệu công ty từ Dun & Bradstreet. Các *khách hàng* thực thể làm phong phú tất cả hồ sơ khách hàng của bạn trong khi một phân khúc chỉ làm phong phú thêm hồ sơ khách hàng có trong phân khúc đó.

1. Xác định loại trường nào từ hồ sơ hợp nhất của bạn để sử dụng để khớp với dữ liệu công ty từ Dun & Bradstreet. Ít nhất một trong các trường **Tên và địa chỉ**, **Điện thoại** hoặc **Email** là bắt buộc.

1. Chọn **Tiếp theo**

1. Ánh xạ các trường của bạn với dữ liệu công ty từ Dun & Bradstreet. Một trong hai **Số DUNS** hoặc **Tên công ty** và **Quốc gia** Mục này bắt buộc.

      :::image type="content" source="media/enrichment-dnb-mapping.png" alt-text="Ngăn ánh xạ trường Dun & Bradstreet.":::

1. Chọn **Tiếp** để hoàn thành quá trình ánh xạ trường.

1. Cung cấp một **Tên** để làm giàu và **Tên thực thể đầu ra**.

1. Chọn **Lưu dữ liệu tăng cường** sau khi xem xét các lựa chọn của bạn.

1. Lựa chọn **Chạy** để bắt đầu quá trình làm giàu hoặc đóng để quay lại **Làm giàu** trang.

## <a name="view-enrichment-results"></a>Xem kết quả bổ sung

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

## <a name="next-steps"></a>Các bước tiếp theo

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](includes/footer-banner.md)]
