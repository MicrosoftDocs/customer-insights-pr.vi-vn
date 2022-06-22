---
title: Làm giàu nâng cao địa chỉ (chứa video)
description: Tăng cường và chuẩn hóa thông tin địa chỉ của hồ sơ khách hàng bằng các mô hình của Microsoft.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
searchScope:
- ci-data-sources-enrichment
- ci-data-sources-enrichment-details
- ci-enrichments
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: f6279b9bb721d99d66f73e8dc839a92f1ad90140
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 06/13/2022
ms.locfileid: "8953837"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a>Tăng cường hồ sơ khách hàng với các địa chỉ nâng cao

Địa chỉ trong dữ liệu của bạn có thể phi cấu trúc, không đầy đủ hoặc không chính xác. Sử dụng các mô hình của Microsoft để chuẩn hóa và tăng cường các địa chỉ của bạn tại [định dạng Common Data Model](/common-data-model/schema/core/applicationcommon/address) để có thông tin chi tiết và độ chính xác cao hơn.

Bạn cũng có thể [làm giàu địa chỉ trên các nguồn dữ liệu](data-sources-enrichment.md) để cải thiện độ chính xác đối sánh trong quá trình hợp nhất dữ liệu. 

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

Mô hình sử dụng các kỹ thuật dựa trên máy học để nâng cao địa chỉ. Như với bất kỳ mô hình dựa trên máy học nào, độ chính xác 100% không được đảm bảo.

## <a name="supported-countries-or-regions"></a>Các quốc gia hoặc khu vực được hỗ trợ

Chúng tôi hiện hỗ trợ tăng cường địa chỉ ở các quốc gia hoặc khu vực sau:

- Australia
- Ca-na-đa
- Pháp
- Đức
- Italy
- Nhật Bản
- Vương quốc Anh
- Hoa Kỳ

## <a name="configure-the-enrichment"></a>Đặt cấu hình dữ liệu tăng cường

1. Đi đến **Dữ liệu** > **Tăng cường** rồi chọn tab **Khám phá**.

1. Chọn **Tăng cường dữ liệu của tôi** trên ngăn xếp **Địa chỉ nâng cao**.

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="Ảnh chụp màn hình ngăn xếp Địa chỉ nâng cao.":::

1. Xem lại tổng quan và sau đó chọn **Tiếp theo**.

1. Chọn **Tập dữ liệu khách hàng** và chọn hồ sơ hoặc phân đoạn bạn muốn làm phong phú thêm. Các *khách hàng* thực thể làm phong phú tất cả hồ sơ khách hàng của bạn trong khi một phân khúc chỉ làm phong phú thêm hồ sơ khách hàng có trong phân khúc đó.

1. Chọn cách định dạng địa chỉ trong tập hợp dữ liệu của bạn. Chọn **Địa chỉ một thuộc tính** nếu địa chỉ trong dữ liệu của bạn sử dụng một trường. Chọn **Địa chỉ nhiều thuộc tính** nếu địa chỉ trong dữ liệu của bạn sử dụng nhiều hơn một trường.

1. Lựa chọn **Tiếp theo** và ánh xạ các trường địa chỉ từ thực thể khách hàng hợp nhất của bạn.

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Trang ánh xạ trường địa chỉ nâng cao.":::

   > [!NOTE]
   > Quốc gia/Khu vực là giá trị bắt buộc trong cả địa chỉ một thuộc tính và địa chỉ nhiều thuộc tính. Chúng tôi sẽ không tăng cường các địa chỉ không chứa giá trị quốc gia/khu vực hợp lệ hoặc được hỗ trợ.

1. Chọn **Tiếp** để hoàn thành quá trình ánh xạ trường.

1. Cung cấp một **Tên** để làm giàu và **Thực thể đầu ra**.

1. Chọn **Lưu dữ liệu tăng cường** sau khi xem xét các lựa chọn của bạn.

## <a name="enrichment-results"></a>Kết quả tăng cường

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Các **Số lượng khách hàng phong phú theo lĩnh vực** cung cấp thông tin chi tiết về phạm vi bao phủ của từng trường được bổ sung chi tiết.

### <a name="overview-card"></a>Thẻ tổng quan

Các **Tổng quan về các thay đổi của khách hàng** thẻ hiển thị chi tiết về phạm vi làm giàu:

- **Địa chỉ được xử lý và thay đổi** : Số lượng hồ sơ khách hàng có địa chỉ đã được bổ sung thành công.
- **Địa chỉ được xử lý và không thay đổi** : Số lượng hồ sơ khách hàng có địa chỉ đã được nhận dạng nhưng không thay đổi. Điều này thường xảy ra khi dữ liệu đầu vào hợp lệ và không thể cải thiện bằng cách bổ sung.
- **Địa chỉ không được xử lý và không thay đổi** : Số lượng cấu hình có địa chỉ không được nhận dạng. Thông thường đối với dữ liệu đầu vào không hợp lệ hoặc không được bổ sung hỗ trợ.

## <a name="next-steps"></a>Các bước tiếp theo

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
