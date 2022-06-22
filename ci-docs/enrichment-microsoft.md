---
title: Làm phong phú hồ sơ khách hàng với dữ liệu thương hiệu và sở thích từ Microsoft
description: Sử dụng dữ liệu độc quyền từ Microsoft để làm phong phú thêm dữ liệu khách hàng của bạn với các mối quan hệ và chia sẻ tiếng nói.
ms.date: 03/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
searchScope:
- ci-enrichments
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: 61262980cafdcd130430e200e466ce7da6cc4d07
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 06/13/2022
ms.locfileid: "8953791"
---
# <a name="enrich-customer-profiles-with-affinities-and-share-of-voice-preview"></a>Làm phong phú hồ sơ khách hàng với sở thích và chia sẻ tiếng nói (xem trước)

Sử dụng dữ liệu độc quyền của Microsoft để làm phong phú thêm dữ liệu khách hàng của bạn với mối quan tâm thương hiệu, mối quan tâm và sự chia sẻ tiếng nói (SoV). Những mối quan hệ và SoV này dựa trên dữ liệu từ những người có nhân khẩu học tương tự như khách hàng của bạn. Thông tin này giúp bạn hiểu rõ hơn và phân khúc khách hàng của mình dựa trên sở thích của họ hoặc SoV với các thương hiệu và sở thích cụ thể.

## <a name="how-we-determine-affinities-and-sov"></a>Cách chúng tôi xác định mối quan hệ và SoV

Chúng tôi sử dụng dữ liệu tìm kiếm trực tuyến của Microsoft để tìm sở thích và SoV cho các thương hiệu và sở thích trên các phân khúc nhân khẩu học khác nhau (được xác định theo độ tuổi, giới tính hoặc vị trí). Khối lượng tìm kiếm trực tuyến cho một thương hiệu hoặc sở thích là cơ sở để xác định mối quan hệ hoặc SoV. Tuy nhiên, mỗi cách cung cấp một góc nhìn khác nhau để hiểu khách hàng của bạn.

- Sở thích là một so sánh giữa các phân đoạn nhân khẩu học. Bạn có thể sử dụng thông tin này để xác định các phân đoạn nhân khẩu học có mức độ quan tâm cao nhất đối với một thương hiệu hoặc mối quan tâm nhất định, so với các phân đoạn khác.

- Chia sẻ tiếng nói là một so sánh giữa các thương hiệu hoặc sở thích đã chọn của bạn. Bạn có thể sử dụng thông tin này để xác định thương hiệu hoặc sở thích nào có tỷ lệ quan tâm cao nhất cho một phân khúc nhân khẩu học nhất định, so với các thương hiệu hoặc sở thích khác mà bạn đã chọn.

## <a name="affinity-level-and-score"></a>Mức độ và điểm số mối quan hệ

Trên mỗi hồ sơ khách hàng được tăng cường dữ liệu, chúng tôi cung cấp hai giá trị liên quan: mức độ mối quan hệ và điểm số mối quan hệ. Những giá trị này giúp bạn xác định mức độ quan tâm đối với phân khúc nhân khẩu học của hồ sơ đó, đối với thương hiệu hoặc sở thích so với các phân khúc nhân khẩu học khác.

*Mức độ mối quan hệ* bao gồm 4 cấp độ và *điểm mối quan hệ* được tính toán trên thang điểm 100 ánh xạ tới các mức độ mối quan hệ.

|Mức độ mối quan hệ |Điểm số mối quan hệ  |
|---------|---------|
|Rất cao     | 85-100       |
|Cao     | 70-84        |
|Trung bình     | 35-69        |
|Thấp     | 1-34        |

Tùy thuộc vào mức độ chi tiết mà bạn muốn đo lường mối quan hệ, bạn có thể sử dụng mức độ hoặc điểm số mối quan hệ. Điểm số mối quan hệ giúp bạn kiểm soát chính xác hơn.

## <a name="share-of-voice-sov"></a>Chia sẻ giọng nói (SoV)

Chúng tôi tính SoV trên thang điểm 100. Tổng số SoV trên tất cả các thương hiệu hoặc sở thích cho mỗi hồ sơ khách hàng được bổ sung thêm tối đa 100. Không giống như mối quan hệ, SoV có liên quan đến thương hiệu và sở thích mà bạn chọn. Ví dụ: các giá trị SoV cho 'Microsoft' có thể khác nhau nếu các thương hiệu đã chọn là ('Microsoft', 'GitHub') so với ('Microsoft', 'LinkedIn').

## <a name="supported-countriesregions"></a>Quốc gia/khu vực được hỗ trợ

Chúng tôi hiện hỗ trợ các tùy chọn quốc gia/vùng sau đây: Úc, Canada (Tiếng Anh), Pháp, Đức, Vương quốc Anh hoặc Hoa Kỳ (Tiếng Anh).

## <a name="configure-the-enrichment"></a>Đặt cấu hình dữ liệu tăng cường

1. Đi đến **Dữ liệu** > **Tăng cường** rồi chọn tab **Khám phá**.

   - Để định cấu hình sở thích thương hiệu và làm giàu SoV, hãy chọn **Làm phong phú dữ liệu của tôi** trên **Nhãn hiệu** ngói.

   - Để định cấu hình sở thích và làm giàu SoV, hãy chọn **Làm phong phú dữ liệu của tôi** trên **Sở thích** ngói.

   > [!div class="mx-imgBorder"]
   > ![Ngăn xếp Thương hiệu và Sở thích.](media/BrandsInterest-tile-Hub.png "Ngăn xếp Thương hiệu và Sở thích")

1. Xem lại tổng quan và sau đó chọn **Tiếp theo**.

1. Để thay đổi quốc gia hoặc khu vực của bạn, hãy chọn **Biến đổi** kế bên **Quốc gia / Khu vực**. Bên trong **Cài đặt quốc gia / khu vực** ngăn, chọn một [quốc gia / khu vực được hỗ trợ](#supported-countriesregions) và chọn **Ứng dụng**.

   > [!NOTE]
   > Khi chọn thương hiệu của riêng bạn, hệ thống cung cấp các đề xuất dựa trên quốc gia hoặc khu vực đã chọn. Khi chọn một ngành, bạn sẽ nhận được các thương hiệu hoặc sở thích phù hợp nhất dựa trên quốc gia hoặc khu vực đã chọn.

1. Chọn tối đa 5 thương hiệu hoặc sở thích bằng cách sử dụng một hoặc cả hai tùy chọn sau:

   - **Ngành**: Chọn ngành của bạn từ danh sách thả xuống, sau đó chọn trong số các thương hiệu hoặc sở thích hàng đầu cho ngành đó.
   - **Tự chọn**: Nhập thương hiệu hoặc sở thích có liên quan đến tổ chức của bạn, sau đó chọn trong số các đề xuất phù hợp. Nếu chúng tôi không liệt kê một thương hiệu hoặc sở thích mà bạn đang tìm kiếm, hãy gửi cho chúng tôi thông tin phản hồi bằng cách sử dụng liên kết **Đề xuất**.

1. Lựa chọn **Tiếp theo** và xem lại các tùy chọn bổ sung mặc định của bạn và cập nhật chúng nếu cần.

   :::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Ảnh chụp màn hình của cửa sổ tùy chọn tăng cường dữ liệu.":::

1. Chọn **Tiếp theo**.

1. Chọn **Tập dữ liệu khách hàng** và chọn cấu hình hoặc phân đoạn bạn muốn bổ sung thêm dữ liệu từ Microsoft. Các *khách hàng* thực thể làm phong phú tất cả hồ sơ khách hàng của bạn trong khi một phân khúc chỉ làm phong phú thêm hồ sơ khách hàng có trong phân khúc đó.

1. Chọn **Tiếp theo**.

1. Ánh xạ các trường của bạn từ thực thể khách hàng hợp nhất của bạn với dữ liệu Microsoft.

   > [!NOTE]
   > Ít nhất thuộc tính Ngày sinh hoặc Giới tính là bắt buộc. Quốc gia / Khu vực và ít nhất là Thành phố (và Tiểu bang / Tỉnh) hoặc mã Bưu điện là bắt buộc. Chúng tôi khuyên bạn nên chuyển đổi ngày sinh thành loại DateTime trong quá trình nhập dữ liệu. Ngoài ra, giá trị này có thể là một chuỗi theo định dạng của [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) là "yyyy-MM-dd" or "yyyy-MM-ddTHH:mm:ss".

1. Chọn **Tiếp** để hoàn thành quá trình ánh xạ trường.

1. Đặt tên cho dữ liệu tăng cường. Các **Tên thực thể đầu ra** được chọn tự động.

   :::image type="content" source="media/enrichment-interests-summary.png" alt-text="Trang xem xét và đặt tên cho sở thích.":::

1. Chọn **Lưu dữ liệu tăng cường** sau khi xem xét các lựa chọn của bạn.

1. Lựa chọn **Chạy** để bắt đầu quá trình làm giàu hoặc đóng để quay lại **Làm giàu** trang.

   Khi tăng cường dữ liệu hồ sơ, chúng tôi sẽ bổ sung thông tin cho tất cả hồ sơ khách hàng mà chúng tôi lấy dữ liệu cho thương hiệu và sở thích đã chọn, bao gồm cả các hồ sơ không thuộc quốc gia hoặc khu vực đã chọn. Ví dụ: nếu bạn đã chọn Đức, chúng tôi sẽ tăng cường dữ liệu cho hồ sơ ở Hoa Kỳ nếu có sẵn dữ liệu về các thương hiệu và sở thích đã chọn ở Hoa Kỳ.

## <a name="enrichment-results"></a>Kết quả tăng cường

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

:::image type="content" source="media/my-enrichments.png" alt-text="Xem trước kết quả sau khi chạy quy trình tăng cường.":::

Kết quả bao gồm **Mức độ chung sở thích** hoặc **Chia sẻ giọng nói** các biểu đồ.

Các thực thể được tạo ra từ phần bổ sung được liệt kê trong **Làm giàu** nhóm trong **Dữ liệu** > **Thực thể**. Dữ liệu phong phú cho các thương hiệu được chuyển đến **BrandAffinityFromMicrosoft** và **BrandShareOfVoiceFromMicrosoft** các thực thể. Dữ liệu cho sở thích nằm trong **Sở thíchAffinityFromMicrosoft** và **InterestShareOfVoiceFromMicrosoft** các thực thể.

## <a name="see-enrichment-data-on-the-customer-card"></a>Xem dữ liệu tăng cường trên thẻ khách hàng

SoV thương hiệu và sở thích cũng có thể được xem trên thẻ khách hàng cá nhân. Đi đến **Khách hàng** rồi chọn một hồ sơ khách hàng. Trong thẻ khách hàng, bạn sẽ tìm thấy các biểu đồ cho thương hiệu hoặc SoV quan tâm dựa trên những người trong hồ sơ nhân khẩu học của khách hàng đó.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Thẻ khách hàng với dữ liệu tăng cường.":::

## <a name="next-steps"></a>Các bước tiếp theo

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]


[!INCLUDE [footer-include](includes/footer-banner.md)]
