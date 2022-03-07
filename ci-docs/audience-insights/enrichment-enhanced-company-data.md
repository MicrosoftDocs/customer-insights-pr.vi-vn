---
title: Nâng cao dữ liệu công ty
description: Làm phong phú và bình thường hóa dữ liệu công ty với các mô hình của Microsoft.
ms.date: 01/19/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 693e2f410a77cbf2e87ff0132ce963aab7e8e3e4
ms.sourcegitcommit: 4c9db6c124d7244e7e8bb2f8bfdc697523781c31
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 01/19/2022
ms.locfileid: "8010955"
---
# <a name="enrichment-of-company-profiles-with-enhanced-company-data"></a>Làm phong phú hồ sơ công ty với dữ liệu công ty nâng cao

Sử dụng các mô hình của Microsoft và dữ liệu công ty đã biên dịch để sửa chữa, bổ sung và chuẩn hóa hồ sơ công ty của bạn. Chúng tôi sẽ sử dụng [Định dạng mô hình dữ liệu chung](/common-data-model/schema/core/applicationcommon/account) để có độ chính xác và thông tin chi tiết tốt hơn.

## <a name="how-we-enhance-company-data"></a>Cách chúng tôi nâng cao dữ liệu công ty

Mô hình của chúng tôi trải qua quy trình hai bước để nâng cao hồ sơ công ty. Đầu tiên, nó bình thường hóa tên công ty. Ví dụ, *Microsoft Corp* sẽ được sửa chữa và tiêu chuẩn hóa để *Tập đoàn Microsoft*. Nó cố gắng tìm sự trùng khớp trong dữ liệu công ty đã biên dịch của Microsoft. Nếu tìm thấy sự trùng khớp, chúng tôi làm phong phú hồ sơ công ty bằng thông tin từ dữ liệu công ty đã biên dịch của chúng tôi, bao gồm cả tên công ty.


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

1.  Xác nhận danh tính của công ty. Chúng tôi không xác minh xem đầu vào là một tổ chức hiện có hay một công ty sử dụng đầu ra làm tên tiêu chuẩn của nó.
2.  Bao quát toàn diện các công ty trên toàn cầu. Dữ liệu công ty được biên dịch của Microsoft có phạm vi bao phủ toàn cầu, nhưng cung cấp hầu hết các phạm vi ở Úc, Canada, Vương quốc Anh và Hoa Kỳ.
3.  Chuẩn hóa địa chỉ công ty trên toàn cầu. Chúng tôi hiện hỗ trợ tiêu chuẩn hóa địa chỉ ở các quốc gia hoặc khu vực sau: Úc, Canada, Pháp, Đức, Ý, Nhật Bản, Vương quốc Anh và Hoa Kỳ.
4.  Đảm bảo tính chính xác hoặc độ mới của dữ liệu. Do thông tin doanh nghiệp thường thay đổi, chúng tôi không thể đảm bảo rằng dữ liệu công ty nâng cao được cung cấp luôn chính xác hoặc cập nhật.

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

Bạn có thể xem một mẫu dữ liệu được bổ sung chi tiết trong **Phong phú khách hàng xem trước** ngói. Lựa chọn **Xem thêm** và chọn **Dữ liệu** để truy cập chế độ xem chi tiết của từng hồ sơ được bổ sung chi tiết.

### <a name="overview-card"></a>Thẻ tổng quan

Thẻ tổng quan hiển thị chi tiết về phạm vi bổ sung. 

* **Các công ty đã xử lý và thay đổi** : Số lượng hồ sơ công ty của khách hàng đã được bổ sung thành công.

* **Các công ty đã xử lý và không thay đổi** : Số lượng hồ sơ công ty của khách hàng đã được công nhận nhưng không thay đổi. Điều này thường xảy ra khi dữ liệu đầu vào hợp lệ và không thể cải thiện bằng cách bổ sung.

* **Các công ty không được xử lý và không thay đổi** : Số lượng hồ sơ công ty của khách hàng không được công nhận. Điều này thường xảy ra đối với dữ liệu đầu vào không hợp lệ hoặc không được bổ sung hỗ trợ.

## <a name="next-steps"></a>Các bước tiếp theo

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](../includes/footer-banner.md)]
