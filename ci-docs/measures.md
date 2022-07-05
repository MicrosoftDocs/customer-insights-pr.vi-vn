---
title: Tổng quan về các biện pháp
description: Tìm hiểu cách các biện pháp giúp phân tích và phản ánh hiệu quả hoạt động của doanh nghiệp bạn.
ms.date: 03/24/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measures
- ci-measure-builder
- ci-measure-template
- ci-enrichment-details
- customerInsights
ms.openlocfilehash: 880c06bffcfa269151d96cb4c597eed4832fc61b
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 06/29/2022
ms.locfileid: "9083133"
---
# <a name="measures-overview"></a>Tổng quan về các biện pháp

Giá trị đo giúp bạn hiểu rõ hơn về hành vi của khách hàng và hiệu quả kinh doanh. Giá trị đo xem xét các giá trị có liên quan từ [hồ sơ hợp nhất](data-unification.md). Ví dụ: một doanh nghiệp muốn xem *tổng mức chi tiêu của mỗi khách hàng* để nắm được lịch sử mua hàng của một khách hàng cá nhân hoặc đo lường *tổng doanh số của công ty* để nắm được tổng doanh thu của toàn bộ doanh nghiệp.  

Các biện pháp được tạo ra [sử dụng công cụ xây dựng thước đo](measure-builder.md), một nền tảng truy vấn dữ liệu với nhiều toán tử khác nhau và các tùy chọn ánh xạ đơn giản. Nó cho phép bạn lọc dữ liệu, nhóm kết quả, phát hiện [đường dẫn mối quan hệ thực thể](relationships.md) và xem trước đầu ra. Bạn có thể [sử dụng các mẫu được xác định trước](measure-templates.md) để cấu hình hiệu quả các biện pháp thường được sử dụng.

Hãy sử dụng trình tạo giá trị đo để lập kế hoạch hoạt động kinh doanh bằng cách truy vấn dữ liệu khách hàng và trích xuất thông tin chi tiết. Ví dụ: tạo một giá trị đo *tổng chi tiêu mỗi khách hàng* và *tổng lợi nhuận trên mỗi khách hàng* giúp xác định nhóm khách hàng có mức chi tiêu cao nhưng lợi nhuận thu về cao. Bạn có thể [tạo một phân đoạn](segments.md) dựa trên các biện pháp này để thúc đẩy các hành động tốt nhất tiếp theo.

## <a name="manage-your-measures"></a>Quản lý các giá trị đo của bạn

Bạn có thể tìm thấy danh sách các giá trị đo trên trang **Giá trị đo**.

Bạn sẽ tìm thấy thông tin về loại giá trị đo, người tạo, ngày tạo, trạng thái và tình trạng. Khi chọn một giá trị đo từ danh sách, bạn có thể xem trước kết quả đầu ra và tải xuống tệp CSV.

:::image type="content" source="media/measures-actions.png" alt-text="Các hành động để quản lý các giá trị đo đơn lẻ."lightbox="media/measures-actions.png":::

Các hành động sau đây khả dụng khi bạn chọn một thước đo:

- **Chỉnh sửa** cấu hình của giá trị đo.
- **Nhân bản** một biện pháp. Bạn có thể chọn chỉnh sửa các thuộc tính của nó ngay lập tức hoặc chỉ cần lưu bản sao.
- **Làm mới** giá trị đo dựa trên dữ liệu mới nhất. Để làm mới tất cả các biện pháp của bạn cùng một lúc, hãy chọn tất cả các biện pháp và sau đó **Làm mới**.
- **Đổi tên** giá trị đo.
- **Kích hoạt** hoặc **hủy kích hoạt**. Các giá trị đo không hoạt động sẽ không được làm mới trong [quá trình làm mới theo lịch trình](system.md#schedule-tab).
- **Nhãn** đến [quản lý thẻ](work-with-tags-columns.md#manage-tags) cho phân khúc.
- **Xóa** giá trị đo.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="next-step"></a>Bước tiếp theo

Bạn có thể sử dụng các giá trị đo hiện có để tạo [một phân khúc khách hàng](segments.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
