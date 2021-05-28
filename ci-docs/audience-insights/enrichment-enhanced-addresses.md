---
title: Tăng cường nâng cao địa chỉ
description: Tăng cường và chuẩn hóa thông tin địa chỉ của hồ sơ khách hàng bằng các mô hình của Microsoft.
ms.date: 04/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 07271d491460764f2c738e760e41c3492f2b6de9
ms.sourcegitcommit: 27f9dd837304ef9fc00f055a6e900fbf6fce1429
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 04/30/2021
ms.locfileid: "5965604"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a>Tăng cường hồ sơ khách hàng với các địa chỉ nâng cao

Địa chỉ trong dữ liệu của bạn có thể phi cấu trúc, không đầy đủ hoặc không chính xác. Sử dụng các mô hình của Microsoft để chuẩn hóa và tăng cường các địa chỉ của bạn tại [định dạng Common Data Model](/common-data-model/schema/core/applicationcommon/address) để có thông tin chi tiết và độ chính xác cao hơn.

## <a name="how-we-enhance-addresses"></a>Cách chúng tôi nâng cao địa chỉ

Mô hình của chúng tôi nâng cao địa chỉ thông qua một quy trình hai bước. Đầu tiên, mô hình phân tích cú pháp địa chỉ để xác định các thành phần của địa chỉ này và đưa chúng vào một định dạng có cấu trúc. Sau đó, chúng tôi sử dụng trí tuệ nhân tạo để chỉnh sửa, hoàn thiện và chuẩn hóa các giá trị trong địa chỉ.

### <a name="example"></a>Ví dụ:

Thông tin địa chỉ có thể ở định dạng phi tiêu chuẩn và có lỗi chính tả. Mô hình có thể khắc phục những vấn đề này và tạo địa chỉ nhất quán trong hồ sơ khách hàng hợp nhất.

```Input
4567 w main stret californa missouri 54321 us
```

```Output
- Street1: 4567 W Main St
- City: California
- StateOrProvince: MO
- ZipOrPostalCode: 54321
- CountryOrRegion: United States of America

- Address: 4567 W Main St, California, MO, 54321, United States of America
```

### <a name="limitations"></a>Giới hạn

Địa chỉ nâng cao chỉ hoạt động với các giá trị đã tồn tại trong dữ liệu địa chỉ đã nhập của bạn. Mô hình không: 

1. Xác minh tính hợp lệ của địa chỉ.
2. Xác minh tính hợp lệ của bất kỳ giá trị nào, chẳng hạn như mã ZIP hoặc tên phố.
3. Thay đổi các giá trị mà mô hình không nhận dạng được.

Mô hình sử dụng các kỹ thuật dựa trên máy học để nâng cao địa chỉ. Mặc dù áp dụng ngưỡng tin cậy cao khi mô hình thay đổi giá trị đầu vào nhưng giống với các mô hình dựa trên máy học khác, chúng tôi không thể đảm bảo độ chính xác 100%.

## <a name="supported-countries-or-regions"></a>Các quốc gia hoặc vùng lãnh thổ được hỗ trợ

Chúng tôi hiện hỗ trợ tăng cường địa chỉ ở các quốc gia hoặc vùng lãnh thổ sau: 

- Australia
- Canada
- Vương quốc Anh
- Hoa Kỳ

Địa chỉ phải có thông tin quốc gia/vùng lãnh thổ. Chúng tôi không xử lý các địa chỉ có quốc gia hoặc vùng lãnh thổ không được hỗ trợ và các địa chỉ không có thông tin quốc gia hoặc vùng lãnh thổ được cung cấp.

## <a name="configure-the-enrichment"></a>Đặt cấu hình nội dung bổ sung

1. Chuyển tới **Dữ liệu** > **Nội dung phong phú**.

1. Chọn **Tăng cường dữ liệu của tôi** trên ngăn xếp **Địa chỉ nâng cao**.

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="Ảnh chụp màn hình ngăn xếp Địa chỉ nâng cao.":::

1. Chọn **Tập hợp dữ liệu khách hàng** và chọn thực thể chứa các địa chỉ bạn muốn tăng cường. Bạn có thể chọn thực thể *Khách hàng* để tăng cường địa chỉ có trong tất cả các hồ sơ khách hàng của bạn hoặc chọn một thực thể phân khúc để tăng cường duy nhất địa chỉ có trong hồ sơ khách hàng thuộc phân khúc đó.

1. Chọn cách định dạng địa chỉ trong tập hợp dữ liệu của bạn. Chọn **Địa chỉ một thuộc tính** nếu địa chỉ trong dữ liệu của bạn sử dụng một trường. Chọn **Địa chỉ nhiều thuộc tính** nếu địa chỉ trong dữ liệu của bạn sử dụng nhiều hơn một trường.

   > [!NOTE]
   > Bạn cần có thông tin về Quốc gia/Vùng lãnh thổ trong cả địa chỉ một thuộc tính đơn và địa chỉ nhiều thuộc tính. Chúng tôi sẽ không tăng cường các địa chỉ không chứa giá trị quốc gia/vùng lãnh thổ hợp lệ hoặc được hỗ trợ

1.  Ánh xạ các trường địa chỉ từ thực thể khách hàng hợp nhất của bạn.

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Trang ánh xạ trường địa chỉ nâng cao.":::

1. Chọn **Tiếp** để hoàn thành quá trình ánh xạ trường.

1. Cung cấp tên cho nội dung bổ sung và thực thể đầu ra.

1. Chọn **Lưu nội dung bổ sung** sau khi xem xét các lựa chọn của bạn.

## <a name="enrichment-results"></a>Kết quả làm phong phú

Để bắt đầu quá trình tăng cường, hãy chọn **Chạy** từ thanh lệnh. Bạn cũng có thể để hệ thống chạy quá trình tăng cường tự động như một phần của [làm mới theo lịch trình](system.md#schedule-tab). Thời gian xử lý phụ thuộc vào kích thước dữ liệu khách hàng của bạn.

Sau khi quá trình tăng cường hoàn tất, bạn có thể xem lại dữ liệu hồ sơ khách hàng mới được bổ sung trong **Nội dung tăng cường của tôi**. Ngoài ra, bạn sẽ tìm thấy thời gian của lần cập nhật gần nhất và số lượng hồ sơ được tăng cường.

Bạn có thể truy cập dạng xem chi tiết của từng hồ sơ được làm phong phú bằng cách chọn **Xem dữ liệu được làm phong phú**.

## <a name="next-steps"></a>Các bước tiếp theo

Xây dựng dựa trên dữ liệu khách hàng phong phú của bạn. Tạo [phân khúc](segments.md), [biện pháp](measures.md) và [xuất dữ liệu](export-destinations.md) để cung cấp trải nghiệm cá nhân cho khách hàng của bạn.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
