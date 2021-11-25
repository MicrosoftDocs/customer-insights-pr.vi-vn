---
title: Tăng cường thông tin hồ sơ khách hàng bằng dữ liệu từ Microsoft
description: Sử dụng dữ liệu độc quyền từ Microsoft để bổ sung các mối quan hệ về thương hiệu và sở thích cho dữ liệu khách hàng của bạn.
ms.date: 11/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: c25dbb7a877da2d3fccc1a4e5b219b9792bc6402
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732568"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a>Tăng cường dữ liệu hồ sơ khách hàng bằng mối quan hệ thương hiệu và sở thích (bản xem trước)

Sử dụng dữ liệu độc quyền của Microsoft để bổ sung các mối quan hệ về sở thích và thương hiệu cho dữ liệu khách hàng của bạn. Các mối quan hệ này dựa trên dữ liệu từ những người thuộc nhóm nhân khẩu học tương tự với khách hàng của bạn. Thông tin này giúp bạn hiểu rõ hơn và chia phân khúc khách hàng của bạn dựa trên mối quan hệ của họ với các thương hiệu và sở thích cụ thể.

Trong thông tin chi tiết về đối tượng, hãy đi tới **Dữ liệu** > **Tăng cường dữ liệu** để [đặt cấu hình và xem dữ liệu tăng cường](enrichment-hub.md).

Để đặt cấu hình dữ liệu tăng cường phụ về mối quan hệ thương hiệu, hãy chuyển đến tab **Khám phá** rồi chọn **Tăng cường dữ liệu của tôi** trên ngăn xếp **Thương hiệu**.

Để đặt cấu hình dữ liệu tăng cường mối quan hệ về sở thích, hãy chuyển đến tab **Khám phá** rồi chọn **Tăng cường dữ liệu của tôi** trên ngăn xếp **Sở thích**.

   > [!div class="mx-imgBorder"]
   > ![Ngăn xếp Thương hiệu và Sở thích.](media/BrandsInterest-tile-Hub.png "Ngăn xếp Thương hiệu và Sở thích")

## <a name="how-we-determine-affinities"></a>Cách chúng tôi xác định mối quan hệ

Chúng tôi sử dụng dữ liệu tìm kiếm trực tuyến của Microsoft để tìm mối quan hệ về thương hiệu và sở thích trên các phân khúc nhân khẩu học khác nhau (được xác định theo độ tuổi, giới tính hoặc vị trí). Khối lượng tìm kiếm trực tuyến cho một thương hiệu hoặc sở thích xác định mức độ quan hệ của một phân khúc nhân khẩu học, so với các phân khúc khác, đối với thương hiệu hoặc sở thích đó.

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

## <a name="supported-countriesregions"></a>Quốc gia/khu vực được hỗ trợ

Chúng tôi hiện hỗ trợ các tùy chọn quốc gia/vùng sau đây: Úc, Canada (Tiếng Anh), Pháp, Đức, Vương quốc Anh hoặc Hoa Kỳ (Tiếng Anh).

Để chọn một quốc gia hoặc khu vực, hãy mở **Dữ liệu tăng cường về thương hiệu** hoặc **Dữ liệu tăng cường về sở thích** rồi chọn **Thay đổi** bên cạnh **Quốc gia/Khu vực**. Trong ngăn **Cài đặt Quốc gia/Khu vực**, chọn một tùy chọn rồi chọn **Áp dụng**.

### <a name="implications-related-to-country-selection"></a>Ý nghĩa liên quan đến chọn quốc gia

- Khi [chọn thương hiệu của riêng bạn](#define-your-brands-or-interests), hệ thống cung cấp các đề xuất dựa trên quốc gia hoặc khu vực đã chọn.

- Khi [chọn một ngành](#define-your-brands-or-interests), bạn sẽ nhận được các thương hiệu hoặc sở thích phù hợp nhất dựa trên quốc gia hoặc khu vực đã chọn.

- Khi [tăng cường dữ liệu hồ sơ](#refresh-enrichment), chúng tôi sẽ bổ sung thông tin cho tất cả hồ sơ khách hàng mà chúng tôi lấy dữ liệu cho thương hiệu và sở thích đã chọn, bao gồm cả các hồ sơ không thuộc quốc gia hoặc khu vực đã chọn. Ví dụ: nếu bạn đã chọn Đức, chúng tôi sẽ tăng cường dữ liệu cho hồ sơ ở Hoa Kỳ nếu có sẵn dữ liệu về các thương hiệu và sở thích đã chọn ở Hoa Kỳ.

## <a name="configure-enrichment"></a>Đặt cấu hình dữ liệu tăng cường

Trải nghiệm có hướng dẫn sẽ giúp bạn hoàn thành quá trình cấu hình dữ liệu tăng cường. 

### <a name="define-your-brands-or-interests"></a>Xác định thương hiệu hoặc sở thích của bạn

Chọn tối đa 5 thương hiệu hoặc sở thích bằng cách sử dụng một hoặc cả hai tùy chọn sau:

- **Ngành**: Chọn ngành của bạn từ danh sách thả xuống, sau đó chọn trong số các thương hiệu hoặc sở thích hàng đầu cho ngành đó.
- **Tự chọn**: Nhập thương hiệu hoặc sở thích có liên quan đến tổ chức của bạn, sau đó chọn trong số các đề xuất phù hợp. Nếu chúng tôi không liệt kê một thương hiệu hoặc sở thích mà bạn đang tìm kiếm, hãy gửi cho chúng tôi thông tin phản hồi bằng cách sử dụng liên kết **Đề xuất**.

### <a name="review-enrichment-preferences"></a>Xem xét các tùy chọn tăng cường dữ liệu

Xem xét các tùy chọn tăng cường dữ liệu mặc định của bạn và cập nhật chúng nếu cần.

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Ảnh chụp màn hình của cửa sổ tùy chọn tăng cường dữ liệu.":::

### <a name="select-entity-to-enrich"></a>Chọn thực thể để tăng cường

Chọn **Thực thể được tăng cường** rồi chọn tập hợp dữ liệu mà bạn muốn bổ sung thêm dữ liệu công ty từ Microsoft. Bạn có thể chọn thực thể khách hàng để tăng cường dữ liệu cho tất cả hồ sơ khách hàng của bạn hoặc chọn một thực thể phân khúc để chỉ tăng cường dữ liệu cho hồ sơ khách hàng có trong phân khúc đó.

### <a name="map-your-fields"></a>Ánh xạ trường của bạn

Ánh xạ các trường từ thực thể khách hàng hợp nhất để xác định phân khúc nhân khẩu học mà bạn muốn hệ thống sử dụng để tăng cường dữ liệu khách hàng của bạn. Ánh xạ Quốc gia/Khu vực và tối thiểu là thuộc tính Ngày sinh hoặc Giới tính. Ngoài ra, bạn phải ánh xạ tối thiểu là Thành phố (và Tiểu bang/Tỉnh) hoặc Mã bưu chính. Chọn **Chỉnh sửa** để xác định ánh xạ của các trường rồi chọn **Áp dụng** khi bạn hoàn thành. Chọn **Lưu** để hoàn tất quá trình ánh xạ trường.

Các định dạng và giá trị sau được hỗ trợ (giá trị không phân biệt chữ hoa hay chữ thường):

- **Ngày sinh**: Ngày sinh nên chuyển thành loại DateTime trong khi nhập dữ liệu. Ngoài ra, giá trị này có thể là một chuỗi theo định dạng của [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) là "yyyy-MM-dd" or "yyyy-MM-ddTHH:mm:ss".
- **Giới tính**: Nam, nữ, không xác định.
- **Mã bưu chính**: Mã ZIP gồm 5 chữ số ở Hoa Kỳ hoặc mã bưu chính tiêu chuẩn ở mọi nơi khác.
- **Thành phố**: Tên thành phố bằng tiếng Anh.
- **Bang/Tỉnh**: Từ viết tắt gồm 2 chữ cái cho Hoa Kỳ và Canada. Từ viết tắt gồm 2 hoặc 3 chữ cái cho Úc. Không áp dụng với Pháp, Đức hoặc Vương quốc Anh.
- **Quốc gia/Khu vực**:

  - US: Hợp chủng quốc Hoa Kỳ, Hoa Kỳ, USA, US, Mỹ
  - CA: Canada, CA
  - GB: Vương quốc Anh, UK, Great Britain, GB, Vương quốc Liên hiệp Anh và Bắc Ireland, Vương quốc Liên hiệp Anh
  - AU: Úc, AU, Liên bang Úc
  - FR: Pháp, FR, Cộng hòa Pháp
  - DE: Đức, German, Deutschland, Allemagne, DE, Cộng hòa Liên bang Đức, Cộng hòa Đức

## <a name="review-and-name-the-enrichment"></a>Xem xét và đặt tên cho dữ liệu tăng cường

Cuối cùng, bạn phải xem xét thông tin và đặt tên cho dữ liệu tăng cường.

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="Trang xem xét và đặt tên cho sở thích.":::

## <a name="refresh-enrichment"></a>Làm mới dữ liệu tăng cường

Chạy quá trình cung cấp dữ liệu tăng cường sau khi đặt cấu hình thương hiệu, sở thích và ánh xạ trường cho nhân khẩu học. Để bắt đầu quá trình, chọn **Chạy** trên trang cấu hình thương hiệu hoặc sở thích. Ngoài ra, bạn có thể để hệ thống tự động chạy tính năng tăng cường như một phần của việc làm mới theo lịch trình.

Tùy thuộc vào kích thước dữ liệu khách hàng của bạn, có thể mất vài phút để quá trình cung cấp dữ liệu tăng cường hoàn tất.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="enrichment-results"></a>Kết quả tăng cường

Sau khi chạy quá trình tăng cường, hãy chuyển đến **Dữ liệu tăng cường của tôi** để xem xét tổng số khách hàng được tăng cường dữ liệu và số liệu phân tích về các thương hiệu hoặc sở thích trong hồ sơ khách hàng được tăng cường dữ liệu.

:::image type="content" source="media/my-enrichments.png" alt-text="Xem trước kết quả sau khi chạy quy trình tăng cường.":::

Xem xét dữ liệu tăng cường bằng cách chọn **Xem dữ liệu tăng cường** trong biểu đồ. Dữ liệu tăng cường cho các thương hiệu đi đến thực thể **BrandAffinityFromMicrosoft**. Dữ liệu cho sở thích trong thực thể **InterestAffinityFromMicrosoft**. Bạn cũng sẽ tìm thấy các thực thể được liệt kê trong nhóm **Tăng cường** trong **Dữ liệu** > **Thực thể**.

Bạn sẽ thấy biểu đồ với số lượng hồ sơ khách hàng được tăng cường theo thời gian và bản xem trước của thực thể được tăng cường. Chọn **Hiển thị thêm** trong ô xem trước để mở thực thể được tăng cường.

## <a name="see-enrichment-data-on-the-customer-card"></a>Xem dữ liệu tăng cường trên thẻ khách hàng

Các mối quan hệ về thương hiệu và sở thích cũng có thể được xem trên thẻ khách hàng cá nhân. Đi đến **Khách hàng** rồi chọn một hồ sơ khách hàng. Trong thẻ khách hàng, bạn sẽ tìm thấy biểu đồ cho các thương hiệu hoặc sở thích mà mọi người trong hồ sơ nhân khẩu học của khách hàng có mối quan hệ.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Thẻ khách hàng với dữ liệu tăng cường.":::

## <a name="next-steps"></a>Các bước tiếp theo

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]


[!INCLUDE[footer-include](../includes/footer-banner.md)]
