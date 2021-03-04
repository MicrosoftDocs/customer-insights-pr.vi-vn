---
title: Tăng cường hồ sơ khách hàng với Microsoft Graph
description: Sử dụng dữ liệu độc quyền từ Microsoft Graph để làm phong phú dữ liệu khách hàng của bạn với các mối quan hệ thương hiệu và sở thích.
ms.date: 12/10/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 2c95369c778f592bc1460799aca0fa8cff813d68
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269356"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a>Làm phong phú hồ sơ khách hàng với mối quan hệ thương hiệu và sở thích (xem trước)

Sử dụng dữ liệu độc quyền từ Microsoft Graph để làm phong phú dữ liệu khách hàng của bạn với các mối quan hệ thương hiệu và sở thích. Những mối quan hệ này được xác định dựa trên dữ liệu từ những người có nhân khẩu học tương tự với khách hàng của bạn. Thông tin này giúp bạn hiểu rõ hơn và phân khúc khách hàng của bạn dựa trên mối quan hệ của họ với các nhãn hiệu và sở thích cụ thể.

Trong thông tin chi tiết về đối tượng, hãy đi tới **Dữ liệu** > **Làm phong phú** để [định cấu hình và xem các chức năng làm phong phú](enrichment-hub.md).

Để đặt cấu hình nội dung phong phú phụ cho thương hiệu, hãy chuyển đến tab **Khám phá** và chọn **Làm phong phú dữ liệu của tôi** trên ngăn xếp **Thương hiệu**.

Để đặt cấu hình nội dung phong phú phụ cho sở thích, hãy chuyển đến tab **Khám phá** rồi chọn **Làm phong phú dữ liệu của tôi** trên ngăn xếp **Sở thích**.

   > [!div class="mx-imgBorder"]
   > ![Ngăn xếp Thương hiệu & Sở thích](media/BrandsInterest-tile-Hub.png "Ngăn xếp Thương hiệu & Sở thích")

## <a name="about-microsoft-graph"></a>Giới thiệu về Microsoft Graph

Chúng tôi sử dụng dữ liệu tìm kiếm trực tuyến từ Microsoft Graph để tìm mối quan hệ với các thương hiệu và sở thích trên các phân khúc nhân khẩu học khác nhau (được xác định theo độ tuổi, giới tính hoặc vị trí). Khối lượng tìm kiếm trực tuyến cho một thương hiệu hoặc sở thích xác định mức độ quan hệ của một phân khúc nhân khẩu học, so với các phân khúc khác, đối với thương hiệu hoặc sở thích đó.

[Tìm hiểu thêm về Microsoft Graph](https://docs.microsoft.com/graph/overview).

## <a name="affinity-level-and-score"></a>Mức độ sở thích và điểm số

Trên mỗi hồ sơ khách hàng được làm phong phú, chúng tôi cung cấp hai giá trị liên quan - mức độ sở thích và điểm số sở thích. Những giá trị này giúp bạn xác định mức độ quan tâm đối với phân đoạn nhân khẩu học của hồ sơ đó, đối với thương hiệu hoặc sở thích so với các phân đoạn nhân khẩu học khác.

*Mức độ sở thích* bao gồm bốn cấp độ và *điểm sở thích* được tính toán trên thang điểm 100 ánh xạ tới các mức độ sở thích.


|Mức độ sở thích |Điểm mối quan hệ  |
|---------|---------|
|Rất cao     | 85-100       |
|Cao     | 70-84        |
|Trung bình     | 35-69        |
|Thấp     | 1-34        |

Tùy thuộc vào mức độ chi tiết mà bạn muốn đo lường sở thích, bạn có thể sử dụng mức độ hoặc điểm số sở thích. Điểm số sở thích giúp bạn kiểm soát chính xác hơn.

## <a name="supported-countriesregions"></a>Khu vực/vùng lãnh thổ được hỗ trợ

Chúng tôi hiện hỗ trợ các tùy chọn quốc gia/vùng sau đây: Úc, Canada (Tiếng Anh), Pháp, Đức, Vương quốc Anh hoặc Hoa Kỳ (Tiếng Anh).

Để chọn quốc gia, hãy mở trình đơn **Làm phong phú thương hiệu** hoặc **Làm phong phú sở thích** rồi chọn **Thay đổi** bên cạnh **Quốc gia/Vùng lãnh thổ**. Trong ngăn **Thiết đặt quốc gia/vùng lãnh thổ**, chọn một tùy chọn rồi chọn **Áp dụng**.

### <a name="implications-related-to-country-selection"></a>Ý nghĩa liên quan đến chọn quốc gia

- Khi [chọn thương hiệu của riêng bạn](#define-your-brands-or-interests), hệ thống cung cấp các đề xuất dựa trên quốc gia hoặc khu vực đã chọn.

- Khi [chọn một ngành](#define-your-brands-or-interests), bạn sẽ nhận được các thương hiệu hoặc sở thích phù hợp nhất dựa trên quốc gia hoặc khu vực đã chọn.

- Khi [làm phong phú hồ sơ](#refresh-enrichment), chúng tôi sẽ làm phong phú thêm tất cả các hồ sơ khách hàng mà chúng tôi lấy dữ liệu cho các thương hiệu và sở thích đã chọn. Bao gồm các hồ sơ không thuộc quốc gia hoặc khu vực đã chọn. Ví dụ: nếu bạn đã chọn Đức, chúng tôi sẽ làm phong phú các hồ sơ ở Hoa Kỳ nếu chúng tôi có dữ liệu Microsoft Graph cho thương hiệu và sở thích đã chọn ở Hoa Kỳ.

## <a name="configure-enrichment"></a>Cấu hình làm phong phú

### <a name="define-your-brands-or-interests"></a>Xác định thương hiệu hoặc sở thích của bạn

Chọn một trong các tùy chọn sau:

- **Ngành**: Hệ thống xác định thương hiệu hoặc sở thích hàng đầu liên quan đến ngành của bạn và làm phong phú dữ liệu khách hàng với họ.
- **Chọn tùy chọn của riêng bạn**: Chọn tối đa 5 mục từ danh sách các thương hiệu hoặc sở thích phù hợp nhất với tổ chức của bạn.

Để thêm thương hiệu hoặc sở thích, hãy nhập dữ liệu liệu vào khu vực đầu vào để nhận đề xuất dựa trên các điều khoản phù hợp. Nếu chúng tôi không liệt kê một thương hiệu hoặc sở thích mà bạn đang tìm kiếm, hãy gửi cho chúng tôi thông tin phản hồi bằng cách sử dụng liên kết **Đề xuất**.

### <a name="review-enrichment-preferences"></a>Xem xét các tùy chọn làm phong phú

Xem lại các tùy chọn làm phong phú mặc định của bạn và cập nhật chúng nếu cần.

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Ảnh chụp màn hình của cửa sổ tùy chọn làm phong phú.":::

### <a name="select-entity-to-enrich"></a>Chọn thực thể để làm phong phú

Chọn **Thực thể làm phong phú** và chọn tập dữ liệu bạn muốn làm phong phú bằng dữ liệu công ty từ Microsoft Graph. Bạn có thể chọn thực thể khách hàng để làm phong phú tất cả hồ sơ khách hàng của bạn hoặc chọn một thực thể phân khúc để chỉ làm phong phú thêm hồ sơ khách hàng có trong phân khúc đó.

### <a name="map-your-fields"></a>Ánh xạ trường của bạn

Ánh xạ các trường từ thực thể khách hàng hợp nhất để xác định phân đoạn nhân khẩu học mà bạn muốn hệ thống sử dụng để làm phong phú dữ liệu khách hàng của bạn. Ánh xạ Quốc gia/Khu vực và tối thiểu là thuộc tính Ngày sinh hoặc Giới tính. Ngoài ra, bạn phải ánh xạ tối thiểu là Thành phố (và Tiểu bang/Tỉnh) hoặc Mã bưu chính. Chọn **Chỉnh sửa** để xác định ánh xạ của các trường và chọn **Áp dụng** khi bạn hoàn thành. Chọn **Lưu** để hoàn tất quá trình ánh xạ trường.

Các định dạng và giá trị sau được hỗ trợ, giá trị không phân biệt chữ hoa chữ thường:

- **Ngày sinh**: Ngày sinh nên chuyển thành loại DateTime trong khi nhập dữ liệu. Ngoài ra, ngày sinh có thể là chuỗi ở định dạng [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) "yyyy-MM-dd" hoặc "yyyy-MM-ddTHH:mm:ssZ".
- **Giới tính**: Nam, nữ, không rõ
- **Mã bưu chính**: Mã ZIP năm chữ số cho Hoa Kỳ, mã bưu chính tiêu chuẩn ở mọi nơi khác
- **Thành phố**: Tên thành phố bằng Tiếng Anh
- **Bang/Tỉnh**: Từ viết tắt 2 chữ cái của Hoa Kỳ và Canada. Từ viết tắt 2 hoặc 3 chữ cái cho Úc. Không áp dụng với Pháp, Đức hoặc Vương quốc Anh.
- **Quốc gia/Vùng lãnh thổ**:

  - US: Hợp chủng quốc Hoa Kỳ, Hoa Kỳ, USA, US, Mỹ
  - CA: Canada, CA
  - GB: Vương quốc Anh, UK, Great Britain, GB, Vương quốc Liên hiệp Anh và Bắc Ireland, Vương quốc Liên hiệp Anh
  - AU: Úc, AU, Liên bang Australia
  - FR: Pháp, FR, Cộng hòa Pháp
  - DE: Đức, German, Deutschland, Allemagne, DE, Cộng hòa Liên bang Đức, Cộng hòa Đức

## <a name="refresh-enrichment"></a>Làm mới nội dung phong phú

Chạy quá trình cung cấp thông tin phong phú sau khi đặt cấu hình thương hiệu, sở thích và ánh xạ trường cho nhân khẩu học. Để bắt đầu quá trình, chọn **Chạy** trên trang cấu hình thương hiệu hoặc sở thích. Ngoài ra, bạn có thể để hệ thống tự động chạy làm phong phú như một phần của việc làm mới theo lịch trình.
Tùy thuộc vào kích thước dữ liệu khách hàng của bạn, có thể mất vài phút để quá trình cung cấp thông tin phong phú hoàn tất.

> [!TIP]
> Có [6 loại trạng thái](system.md#status-types) cho các nhiệm vụ/quy trình. Ngoài ra, hầu hết các quy trình [phụ thuộc vào các quá trình hạ nguồn khác](system.md#refresh-policies). Bạn có thể chọn trạng thái của một quy trình để xem chi tiết về tiến trình của toàn bộ công việc. Sau khi chọn **Xem chi tiết** đối với một trong các tác vụ của công việc, bạn sẽ tìm thấy thông tin bổ sung: thời gian xử lý, ngày xử lý gần nhất và tất cả các lỗi và cảnh báo liên quan đến tác vụ.

## <a name="enrichment-results"></a>Kết quả làm phong phú

Sau khi chạy quá trình làm phong phú, hãy chuyển đến **Nội dung phong phú của tôi** để xem lại tổng số khách hàng làm phong phú và số liệu phân tích về các thương hiệu hoặc sở thích trong hồ sơ khách hàng được làm phong phú.

:::image type="content" source="media/my-enrichments.png" alt-text="Xem trước kết quả sau khi chạy quy trình làm phong phú":::

Xem lại dữ liệu được làm phong phú bằng cách chọn **Xem dữ liệu phong phú** trong biểu đồ. Dữ liệu phong phú cho các thương hiệu đi đến thực thể **BrandAffinityFromMicrosoft**. Dữ liệu cho sở thích trong thực thể **InterestAffinityFromMicrosoft**. Bạn cũng sẽ tìm thấy các thực thể được liệt kê trong nhóm **Làm phong phú** trong **Dữ liệu** > **Các thực thể**.

## <a name="see-enrichment-data-on-the-customer-card"></a>Xem dữ liệu làm phong phú trên thẻ khách hàng

Các mối quan hệ thương hiệu và lợi ích cũng có thể được xem trên thẻ khách hàng cá nhân. Đi đến **Khách hàng** và chọn một hồ sơ khách hàng. Trong thẻ khách hàng, bạn sẽ tìm thấy biểu đồ cho các thương hiệu hoặc sở thích mà mọi người trong hồ sơ nhân khẩu học của khách hàng có ái lực.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Thẻ khách hàng với dữ liệu phong phú":::

## <a name="next-steps"></a>Bước tiếp theo

Xây dựng dựa trên dữ liệu khách hàng phong phú của bạn. Tạo [Phân khúc](segments.md), [Biện pháp](measures.md) và [xuất dữ liệu](export-destinations.md) để cung cấp trải nghiệm cá nhân cho khách hàng của bạn.


[!INCLUDE[footer-include](../includes/footer-banner.md)]