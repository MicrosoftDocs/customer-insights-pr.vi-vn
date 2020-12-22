---
title: Tăng cường hồ sơ khách hàng với Microsoft Graph
description: Sử dụng dữ liệu độc quyền từ Microsoft Graph để làm phong phú dữ liệu khách hàng của bạn với các mối quan hệ thương hiệu và sở thích.
ms.date: 09/28/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 4f93a2337815f76b98185ecb3755e08443031748
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407301"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a>Làm phong phú hồ sơ khách hàng với mối quan hệ thương hiệu và sở thích (xem trước)

Sử dụng dữ liệu độc quyền từ Microsoft Graph để làm phong phú dữ liệu khách hàng của bạn với các mối quan hệ thương hiệu và sở thích. Những mối quan hệ này được xác định dựa trên dữ liệu từ những người có nhân khẩu học tương tự với khách hàng của bạn. Thông tin này giúp bạn hiểu rõ hơn và phân khúc khách hàng của bạn dựa trên mối quan hệ của họ với các nhãn hiệu và sở thích cụ thể.

Trong thông tin chi tiết về đối tượng, hãy đi tới **Dữ liệu** > **Tăng cường** để [định cấu hình và xem các chức năng tăng cường](enrichment-hub.md).

Để đặt cấu hình nội dung phong phú phụ cho thương hiệu, hãy chuyển đến tab **Khám phá** và chọn **Làm phong phú dữ liệu của tôi** trên ngăn xếp **Thương hiệu**.

Để đặt cấu hình nội dung phong phú phụ cho sở thích, hãy chuyển đến tab **Khám phá** rồi chọn **Làm phong phú dữ liệu của tôi** trên ngăn xếp **Sở thích**.

   > [!div class="mx-imgBorder"]
   > ![Ngăn xếp Thương hiệu & Sở thích](media/BrandsInterest-tile-Hub.png "Ngăn xếp Thương hiệu & Sở thích")

## <a name="about-microsoft-graph"></a>Giới thiệu về Microsoft Graph

Chúng tôi sử dụng dữ liệu tìm kiếm trực tuyến từ Microsoft Graph để tìm mối quan hệ với các thương hiệu và sở thích trên các phân khúc nhân khẩu học khác nhau (được xác định theo độ tuổi, giới tính hoặc vị trí). Khối lượng tìm kiếm trực tuyến cho một thương hiệu hoặc sở thích xác định mức độ quan hệ của một phân khúc nhân khẩu học, so với các phân khúc khác, đối với thương hiệu hoặc sở thích đó.

[Tìm hiểu thêm về Microsoft Graph](https://docs.microsoft.com/graph/overview).

## <a name="affinity-score-and-confidence"></a>Điểm mối quan hệ và độ tin cậy

**Điểm mối quan hệ** được tính theo thang điểm 100, với 100 đại diện cho phân khúc có mối quan hệ cao nhất đối với thương hiệu hoặc sở thích.

**Độ tin cậy của mối quan hệ** cũng được tính theo thang điểm 100. Chỉ số này cho biết mức độ tin cậy của hệ thống rằng một phân khúc có mối quan hệ với thương hiệu hoặc sở thích. Mức độ tin cậy dựa trên kích thước phân khúc và độ chi tiết của phân khúc. Kích thước phân khúc được xác định bởi lượng dữ liệu chúng tôi có cho một phân khúc nhất định. Độ chi tiết của phân đoạn được xác định bởi số thuộc tính (tuổi, giới tính, vị trí) có sẵn trong một hồ sơ.

Chúng tôi không bình thường hóa điểm số cho tập dữ liệu của bạn. Do đó, bạn có thể không thấy tất cả các giá trị điểm mối quan hệ có thể có cho tập dữ liệu của mình. Ví dụ: có thể không có hồ sơ khách hàng phong phú với điểm số mối quan hệ 100 trong dữ liệu của bạn. Điều đó có thể nếu không có khách hàng tồn tại trong phân đoạn nhân khẩu học đạt 100 điểm cho một thương hiệu hoặc sở thích nhất định.

> [!TIP]
> Khi [tạo phân khúc](segments.md) sử dụng điểm số mối quan hệ, xem xét phân phối điểm mối quan hệ cho tập dữ liệu của bạn trước khi quyết định ngưỡng điểm thích hợp. Ví dụ: điểm mối quan hệ là 10 có thể được coi là đáng kể trong bộ dữ liệu có điểm mối quan hệ cao nhất chỉ 25 cho một thương hiệu hoặc sở thích nhất định.

## <a name="supported-countriesregions"></a>Khu vực/vùng lãnh thổ được hỗ trợ

Chúng tôi hiện hỗ trợ các tùy chọn quốc gia/vùng sau đây: Úc, Canada (Tiếng Anh), Pháp, Đức, Vương quốc Anh hoặc Hoa Kỳ (Tiếng Anh).

Để chọn quốc gia, hãy mở trình đơn **Làm phong phú thương hiệu** hoặc **Làm phong phú sở thích** rồi chọn **Thay đổi** bên cạnh **Quốc gia/Vùng lãnh thổ**. Trong ngăn **Thiết đặt quốc gia/vùng lãnh thổ**, chọn một tùy chọn rồi chọn **Áp dụng**.

### <a name="implications-related-to-country-selection"></a>Ý nghĩa liên quan đến chọn quốc gia

- Khi [chọn thương hiệu của riêng bạn](#define-your-brands-or-interests), chúng tôi sẽ đưa ra đề xuất dựa trên quốc gia/vùng lãnh thổ đã chọn.

- Khi [chọn ngành](#define-your-brands-or-interests), chúng tôi sẽ xác định các thương hiệu hoặc sở thích có liên quan nhất dựa trên quốc gia/khu vực đã chọn.

- Khi [ánh xạ các trường](#map-your-fields), nếu trường Quốc gia/Vùng lãnh thổ không được ánh xạ, chúng tôi sẽ sử dụng dữ liệu Microsoft Graph từ quốc gia/vùng lãnh thổ đã chọn để làm phong phú hồ sơ của khách hàng. Chúng tôi cũng sẽ dùng lựa chọn đó để làm phong phú hồ sơ khách hàng không có sẵn dữ liệu quốc gia/vùng lãnh thổ.

- Khi [làm phong phú hồ sơ](#refresh-enrichment), chúng tôi sẽ làm phong phú hồ sơ khách hàng mà có dữ liệu Microsoft Graph cho các thương hiệu và sở thích đã chọn, bao gồm các hồ sơ không có ở quốc gia/vùng lãnh thổ đã chọn. Ví dụ: nếu bạn đã chọn Đức, chúng tôi sẽ làm phong phú các hồ sơ ở Hoa Kỳ nếu chúng tôi có dữ liệu Microsoft Graph cho thương hiệu và sở thích đã chọn ở Hoa Kỳ.

## <a name="configure-enrichment"></a>Cấu hình làm phong phú

Quá trình đặt cấu hình nội dung phong phú cho thương hiệu hoặc sở thích bao gồm 2 bước:

### <a name="define-your-brands-or-interests"></a>Xác định thương hiệu hoặc sở thích của bạn

Chọn một trong các tùy chọn sau:

- **Ngành**: Hệ thống xác định thương hiệu hoặc sở thích hàng đầu liên quan đến ngành của bạn và làm phong phú dữ liệu khách hàng với họ.
- **Chọn tùy chọn của riêng bạn**: Chọn tối đa 5 mục từ danh sách các thương hiệu hoặc sở thích phù hợp nhất với tổ chức của bạn.

Để thêm thương hiệu hoặc sở thích, hãy nhập dữ liệu liệu vào khu vực đầu vào để nhận đề xuất dựa trên các điều khoản phù hợp. Nếu chúng tôi không liệt kê một thương hiệu hoặc sở thích mà bạn đang tìm kiếm, hãy gửi cho chúng tôi thông tin phản hồi bằng cách sử dụng liên kết **Đề xuất**.

### <a name="map-your-fields"></a>Ánh xạ trường của bạn

Ánh xạ trường từ thực thể khách hàng hợp nhất của bạn đến ít nhất hai thuộc tính để xác định phân đoạn nhân khẩu học mà bạn muốn chúng tôi sử dụng để làm phong phú dữ liệu khách hàng của bạn. Chọn **Chỉnh sửa** để xác định ánh xạ của các trường và chọn **Áp dụng** khi bạn hoàn thành. Chọn **Lưu** để hoàn tất quá trình ánh xạ trường.

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
