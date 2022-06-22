---
title: Nâng cao dữ liệu công ty
description: Làm phong phú và bình thường hóa dữ liệu công ty với các mô hình của Microsoft.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 4247d59806468907d93fc7848231ec5a2985580e
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 06/13/2022
ms.locfileid: "8953975"
---
# <a name="enrichment-of-company-profiles-with-enhanced-company-data"></a>Làm phong phú hồ sơ công ty với dữ liệu công ty nâng cao

Sử dụng các mô hình của Microsoft và dữ liệu công ty đã biên dịch để chỉnh sửa, bổ sung và chuẩn hóa hồ sơ công ty của bạn. Chúng tôi sẽ sử dụng [Định dạng mô hình dữ liệu chung](/common-data-model/schema/core/applicationcommon/account) để có độ chính xác và thông tin chi tiết tốt hơn.

Bạn cũng có thể [nâng cao dữ liệu của công ty trên các nguồn dữ liệu](data-sources-enrichment.md) để cải thiện độ chính xác đối sánh trong quá trình hợp nhất dữ liệu.

Đối với các công ty đại chúng ở Hoa Kỳ, các thông tin như doanh thu, mã chứng khoán, ngành, v.v. đều có sẵn.  

## <a name="how-we-enhance-company-data"></a>Cách chúng tôi nâng cao dữ liệu công ty

Mô hình của chúng tôi trải qua quy trình hai bước để nâng cao hồ sơ công ty. Đầu tiên, nó bình thường hóa tên công ty. Ví dụ, *Microsoft Corp* sẽ được sửa chữa và tiêu chuẩn hóa để *Tập đoàn Microsoft*. Nó cố gắng tìm sự trùng khớp trong dữ liệu công ty đã biên dịch của Microsoft. Nếu tìm thấy sự trùng khớp, chúng tôi sẽ làm phong phú thêm hồ sơ công ty với thông tin từ dữ liệu công ty đã tổng hợp của chúng tôi, bao gồm cả tên công ty.

### <a name="example"></a>Ví dụ:

Thông tin công ty của bạn có thể không tuân theo định dạng chuẩn hóa và có lỗi chính tả. Mô hình cố gắng khắc phục những vấn đề này và tạo ra thông tin nhất quán.

```Input
Microsft
```

```Output
- AccountName: Microsoft Corporation
- MainPhoneNumber: 8006427676
- Website: https://www.microsoft.com/
- Street1: One Microsoft Way
- City: Redmond
- StateOrProvince: Washington
- County: King
- ZipOrPostalCode: 98052
- CountryOrRegion: United States
```

## <a name="limitations"></a>Giới hạn

Mô hình không:

- Xác nhận danh tính của công ty. Chúng tôi không xác minh xem đầu vào là một tổ chức hiện có hay một công ty sử dụng đầu ra làm tên tiêu chuẩn.
- Bao quát toàn diện các công ty trên toàn cầu. Dữ liệu công ty được biên dịch của Microsoft có phạm vi toàn cầu, nhưng cung cấp hầu hết các phạm vi bao phủ ở Úc, Canada, Vương quốc Anh và Hoa Kỳ.
- Chuẩn hóa địa chỉ công ty trên toàn cầu. Chúng tôi hiện hỗ trợ tiêu chuẩn hóa địa chỉ ở các quốc gia hoặc khu vực sau: Úc, Canada, Pháp, Đức, Ý, Nhật Bản, Vương quốc Anh và Hoa Kỳ.
- Đảm bảo độ chính xác hoặc độ mới của dữ liệu. Vì thông tin doanh nghiệp thường thay đổi, chúng tôi không thể đảm bảo rằng dữ liệu công ty nâng cao được cung cấp luôn chính xác hoặc cập nhật.

## <a name="configure-the-enrichment"></a>Đặt cấu hình dữ liệu tăng cường

1. Đi đến **Dữ liệu** > **Tăng cường** rồi chọn tab **Khám phá**.

1. Lựa chọn **Làm phong phú dữ liệu của tôi** trên **Dữ liệu công ty nâng cao** ngói.

   :::image type="content" source="media/enhanced-company-data-tile.png" alt-text="Ô phong phú trong trung tâm phong phú cho dữ liệu công ty.":::

1. Xem lại tổng quan và sau đó chọn **Tiếp theo**.

1. Chọn **Tập dữ liệu khách hàng** và chọn hồ sơ hoặc phân đoạn bạn muốn làm phong phú thêm. Các *khách hàng* thực thể làm phong phú tất cả hồ sơ khách hàng của bạn trong khi một phân khúc chỉ làm phong phú thêm hồ sơ khách hàng có trong phân khúc đó.

1. Chọn loại trường từ hồ sơ công ty của bạn để sử dụng để khớp với dữ liệu công ty đã biên dịch của Microsoft. Lựa chọn này sẽ ảnh hưởng đến các trường ánh xạ mà bạn có quyền truy cập trong bước tiếp theo.

1. Chọn **Tiếp theo**.

1. Ánh xạ các trường của công ty bạn với dữ liệu công ty từ Microsoft. Để có độ chính xác đối sánh cao hơn, hãy thêm nhiều trường hơn.

    :::image type="content" source="media/enhanced-company-data-mapping.png" alt-text="Bước ánh xạ dữ liệu khi định cấu hình làm giàu cho công ty.":::

1. Chọn **Tiếp** để hoàn thành quá trình ánh xạ trường.

1. Cung cấp một **Tên** để làm giàu và **Thực thể đầu ra**.

1. Chọn **Lưu dữ liệu tăng cường** sau khi xem xét các lựa chọn của bạn.

1. Lựa chọn **Chạy** để bắt đầu quá trình làm giàu hoặc đóng để quay lại **Làm giàu** trang.

## <a name="enrichment-results"></a>Kết quả tăng cường

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

### <a name="overview-card"></a>Thẻ tổng quan

Các **Tổng quan về các thay đổi của khách hàng** ô hiển thị chi tiết về phạm vi bao phủ của phần làm giàu

- **Các công ty đã xử lý và thay đổi** : Số lượng hồ sơ công ty khách hàng đã được bổ sung thành công.
- **Các công ty đã xử lý và không thay đổi** : Số lượng hồ sơ công ty của khách hàng đã được công nhận nhưng không thay đổi. Điều này thường xảy ra khi dữ liệu đầu vào hợp lệ và không thể cải thiện bằng cách bổ sung.
- **Các công ty không được xử lý và không thay đổi** : Số lượng hồ sơ công ty của khách hàng không được nhận dạng. Điều này thường xảy ra đối với dữ liệu đầu vào không hợp lệ hoặc không được bổ sung hỗ trợ.

## <a name="next-steps"></a>Các bước tiếp theo

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
