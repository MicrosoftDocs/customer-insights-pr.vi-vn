---
title: Nâng cao dữ liệu công ty
description: Làm phong phú và bình thường hóa dữ liệu công ty với các mô hình của Microsoft.
ms.date: 11/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: d11700c87f31cedc40d32b201251d8a9e2e2c312
ms.sourcegitcommit: dfc4843cc78857f1e3ca49d7b938e3ba77969169
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 11/15/2021
ms.locfileid: "7813943"
---
# <a name="enrichment-of-company-profiles-with-enhanced-company-data"></a>Làm phong phú hồ sơ công ty với dữ liệu công ty nâng cao

Sử dụng các mô hình của Microsoft và dữ liệu công ty đã biên dịch để sửa chữa, bổ sung và chuẩn hóa hồ sơ công ty của bạn. Chúng tôi sẽ sử dụng [Định dạng mô hình dữ liệu chung](/common-data-model/schema/core/applicationcommon/account) để có độ chính xác và thông tin chi tiết tốt hơn.

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

Có một số hạn chế với dữ liệu nâng cao. Các mục trong danh sách dưới đây không được hỗ trợ bởi mô hình.

1.  Xác nhận danh tính của công ty. Chúng tôi không xác minh xem đầu vào là một tổ chức hiện có hay một công ty sử dụng đầu ra làm tên tiêu chuẩn.
2.  Bao quát toàn diện các công ty trên toàn cầu. Dữ liệu công ty được biên dịch của Microsoft có phạm vi toàn cầu, nhưng cung cấp hầu hết các phạm vi bao phủ ở Úc, Canada, Vương quốc Anh và Hoa Kỳ.
3.  Chuẩn hóa địa chỉ công ty trên toàn cầu. Chúng tôi hiện hỗ trợ tiêu chuẩn hóa địa chỉ ở các quốc gia hoặc khu vực sau: Úc, Canada, Pháp, Đức, Ý, Nhật Bản, Vương quốc Anh và Hoa Kỳ.
4.  Đảm bảo độ chính xác hoặc độ mới của dữ liệu. Vì thông tin doanh nghiệp thường thay đổi, chúng tôi không thể đảm bảo rằng dữ liệu công ty nâng cao được cung cấp luôn chính xác hoặc cập nhật.

## <a name="configure-the-enrichment"></a>Đặt cấu hình dữ liệu tăng cường

1. Chuyển tới **Dữ liệu** > **Dữ liệu tăng cường**.

1. Lựa chọn **Làm phong phú dữ liệu của tôi** trên **Dữ liệu công ty nâng cao** ngói.

   :::image type="content" source="media/enhanced-company-data-tile.png" alt-text="Ô phong phú trong trung tâm phong phú cho dữ liệu công ty.":::

1. Chọn **Tập hợp dữ liệu khách hàng** rồi chọn thực thể chứa các địa chỉ bạn muốn tăng cường. Bạn có thể chọn thực thể *Khách hàng* để tăng cường địa chỉ có trong tất cả các hồ sơ khách hàng của bạn hoặc chọn một thực thể phân khúc để tăng cường duy nhất địa chỉ có trong hồ sơ khách hàng thuộc phân khúc đó.

1. Chọn loại trường nào từ hồ sơ công ty của bạn sẽ được sử dụng để khớp với dữ liệu công ty đã biên dịch của Microsoft. Lựa chọn này sẽ ảnh hưởng đến các trường ánh xạ mà bạn có quyền truy cập trong bước tiếp theo.

1.  Ánh xạ các trường của công ty từ thực thể khách hàng hợp nhất của bạn. Bạn càng ánh xạ nhiều số nhận dạng và trường chính, thì khả năng tỷ lệ đối sánh càng cao.

    :::image type="content" source="media/enhanced-company-data-mapping.png" alt-text="Bước ánh xạ dữ liệu khi định cấu hình làm giàu cho công ty.":::

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
