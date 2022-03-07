---
title: Tăng cường nâng cao địa chỉ
description: Tăng cường và chuẩn hóa thông tin địa chỉ của hồ sơ khách hàng bằng các mô hình của Microsoft.
ms.date: 07/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: f56be1f4ecdac124ed76a0fb0eb1e313099248bf
ms.sourcegitcommit: 1565f4f7b4e131ede6ae089c5d21a79b02bba645
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 10/14/2021
ms.locfileid: "7643451"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a>Tăng cường hồ sơ khách hàng với các địa chỉ nâng cao

Địa chỉ trong dữ liệu của bạn có thể phi cấu trúc, không đầy đủ hoặc không chính xác. Sử dụng các mô hình của Microsoft để chuẩn hóa và tăng cường các địa chỉ của bạn tại [định dạng Common Data Model](/common-data-model/schema/core/applicationcommon/address) để có thông tin chi tiết và độ chính xác cao hơn.

## <a name="how-we-enhance-addresses"></a>Cách chúng tôi nâng cao địa chỉ

Mô hình của chúng tôi nâng cao địa chỉ thông qua một quy trình gồm hai bước. Đầu tiên, mô hình phân tích cú pháp địa chỉ để xác định các thành phần của địa chỉ này và đưa chúng vào một định dạng có cấu trúc. Sau đó, chúng tôi sử dụng AI để sửa, hoàn thiện và chuẩn hóa các giá trị trong địa chỉ.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWNewo]

### <a name="example"></a>Ví dụ:

Thông tin địa chỉ có thể ở định dạng không chuẩn và có lỗi chính tả. Mô hình có thể khắc phục những vấn đề này và tạo địa chỉ nhất quán trong hồ sơ khách hàng hợp nhất.

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

Mô hình sử dụng các kỹ thuật dựa trên máy học để nâng cao địa chỉ. Mặc dù chúng tôi áp dụng ngưỡng tin cậy cao cho việc mô hình thay đổi giá trị đầu vào, như với mọi mô hình học trên máy, nhưng sẽ không đảm bảo độ chính xác 100%.

## <a name="supported-countries-or-regions"></a>Các quốc gia hoặc khu vực được hỗ trợ

Chúng tôi hiện hỗ trợ tăng cường địa chỉ ở các quốc gia hoặc khu vực sau: 

- Australia
- Canada
- Pháp
- Đức
- Italy
- Nhật Bản
- Vương quốc Anh
- Hoa Kỳ

Địa chỉ phải có giá trị quốc gia/khu vực. Chúng tôi không xử lý các địa chỉ có quốc gia hoặc khu vực không được hỗ trợ và các địa chỉ không có thông tin quốc gia hoặc khu vực được cung cấp.

## <a name="configure-the-enrichment"></a>Định cấu hình dữ liệu tăng cường

1. Chuyển tới **Dữ liệu** > **Tăng cường**.

1. Chọn **Tăng cường dữ liệu của tôi** trên ngăn xếp **Địa chỉ nâng cao**.

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="Ảnh chụp màn hình ngăn xếp Địa chỉ nâng cao.":::

1. Chọn **Tập hợp dữ liệu khách hàng** rồi chọn thực thể chứa các địa chỉ bạn muốn tăng cường. Bạn có thể chọn thực thể *Khách hàng* để tăng cường địa chỉ có trong tất cả các hồ sơ khách hàng của bạn hoặc chọn một thực thể phân khúc để tăng cường duy nhất địa chỉ có trong hồ sơ khách hàng thuộc phân khúc đó.

1. Chọn cách định dạng địa chỉ trong tập hợp dữ liệu của bạn. Chọn **Địa chỉ một thuộc tính** nếu địa chỉ trong dữ liệu của bạn sử dụng một trường. Chọn **Địa chỉ nhiều thuộc tính** nếu địa chỉ trong dữ liệu của bạn sử dụng nhiều hơn một trường.

   > [!NOTE]
   > Quốc gia/Khu vực là giá trị bắt buộc trong cả địa chỉ một thuộc tính và địa chỉ nhiều thuộc tính. Chúng tôi sẽ không tăng cường các địa chỉ không chứa giá trị quốc gia/khu vực hợp lệ hoặc được hỗ trợ.

1.  Ánh xạ các trường địa chỉ từ thực thể khách hàng hợp nhất của bạn.

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Trang ánh xạ trường địa chỉ nâng cao.":::

1. Chọn **Tiếp** để hoàn thành quá trình ánh xạ trường.

1. Đặt tên cho dữ liệu tăng cường và thực thể đầu ra.

1. Chọn **Lưu dữ liệu tăng cường** sau khi xem xét các lựa chọn của bạn.

## <a name="enrichment-results"></a>Kết quả tăng cường

Để bắt đầu quá trình tăng cường, hãy chọn **Chạy** từ thanh lệnh. Bạn cũng có thể để hệ thống chạy quá trình tăng cường tự động như một phần của [làm mới theo lịch trình](system.md#schedule-tab). Thời gian xử lý phụ thuộc vào kích thước dữ liệu khách hàng của bạn.

Sau khi quá trình tăng cường hoàn tất, bạn có thể xem xét dữ liệu hồ sơ khách hàng mới được bổ sung trong **Dữ liệu tăng cường của tôi**. Ngoài ra, bạn sẽ tìm thấy thời gian của lần cập nhật gần nhất và số lượng hồ sơ được tăng cường.

Bạn có thể truy cập dạng xem chi tiết của từng hồ sơ được tăng cường dữ liệu bằng cách chọn **Xem dữ liệu tăng cường**.

## <a name="next-steps"></a>Các bước tiếp theo

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](../includes/footer-banner.md)]
