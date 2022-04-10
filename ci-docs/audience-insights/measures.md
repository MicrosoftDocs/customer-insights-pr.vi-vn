---
title: Hiểu và quản lý các biện pháp
description: Tìm hiểu cách các biện pháp giúp phân tích và phản ánh hiệu quả hoạt động của doanh nghiệp bạn.
ms.date: 02/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-measures
- ci-measure-builder
- ci-measure-template
- ci-enrichment-details
- customerInsights
ms.openlocfilehash: c46fcc3baba1d6c92c2c0fe459a62277343cc0e4
ms.sourcegitcommit: cf6a0ed44915908a44c70889a2dd199a9d0d4798
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 02/28/2022
ms.locfileid: "8359821"
---
# <a name="measures-overview"></a>Tổng quan về các biện pháp

Giá trị đo giúp bạn hiểu rõ hơn về hành vi của khách hàng và hiệu quả kinh doanh. Giá trị đo xem xét các giá trị có liên quan từ [hồ sơ hợp nhất](data-unification.md). Ví dụ: một doanh nghiệp muốn xem *tổng mức chi tiêu của mỗi khách hàng* để nắm được lịch sử mua hàng của một khách hàng cá nhân hoặc đo lường *tổng doanh số của công ty* để nắm được tổng doanh thu của toàn bộ doanh nghiệp.  

Các biện pháp được tạo ra [sử dụng công cụ xây dựng thước đo](measure-builder.md), một nền tảng truy vấn dữ liệu với nhiều toán tử khác nhau và các tùy chọn ánh xạ đơn giản. Nó cho phép bạn lọc dữ liệu, nhóm kết quả, phát hiện [đường dẫn mối quan hệ thực thể](relationships.md) và xem trước đầu ra. Bạn có thể [sử dụng các mẫu được xác định trước](measure-templates.md) để cấu hình hiệu quả các biện pháp thường được sử dụng.

Hãy sử dụng trình tạo giá trị đo để lập kế hoạch hoạt động kinh doanh bằng cách truy vấn dữ liệu khách hàng và trích xuất thông tin chi tiết. Ví dụ: tạo một giá trị đo *tổng chi tiêu mỗi khách hàng* và *tổng lợi nhuận trên mỗi khách hàng* giúp xác định nhóm khách hàng có mức chi tiêu cao nhưng lợi nhuận thu về cao. Bạn có thể [tạo một phân khúc](segments.md) dựa trên các biện pháp này để thúc đẩy các hành động tốt nhất tiếp theo. 

## <a name="manage-your-measures"></a>Quản lý các giá trị đo của bạn

Bạn có thể tìm thấy danh sách các giá trị đo trên trang **Giá trị đo**.

Bạn sẽ tìm thấy thông tin về loại giá trị đo, người tạo, ngày tạo, trạng thái và tình trạng. Khi chọn một giá trị đo từ danh sách, bạn có thể xem trước kết quả đầu ra và tải xuống tệp CSV.

Để làm mới tất cả các giá trị đo của bạn cùng một lúc, hãy chọn **Làm mới tất cả** mà không chọn một giá trị đo cụ thể.

:::image type="content" source="media/measure-actions.png" alt-text="Các hành động để quản lý các giá trị đo đơn lẻ.":::

Chọn một giá trị đo từ danh sách cho các tùy chọn sau:

- Chọn tên giá trị đo để xem chi tiết về giá trị đo đó.
- **Chỉnh sửa** cấu hình của giá trị đo.
- **Làm mới** giá trị đo dựa trên dữ liệu mới nhất.
- **Đổi tên** giá trị đo.
- **Xóa** giá trị đo.
- **Kích hoạt** hoặc **hủy kích hoạt**. Các giá trị đo không hoạt động sẽ không được làm mới trong [quá trình làm mới theo lịch trình](system.md#schedule-tab).

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="next-step"></a>Bước tiếp theo

Bạn có thể sử dụng các giá trị đo hiện có để tạo [một phân khúc khách hàng](segments.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
