---
title: Thông tin chi tiết về phân khúc cho các phân khúc hiện tại
description: Nhận thông tin chi tiết về các phân khúc hiện có để thấy điểm khác biệt và điểm chung.
ms.date: 06/10/2020
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-segment-insights
- customerInsights
ms.openlocfilehash: 526b593ba9b038de3d3c27f6a7683ca76b3f2319
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 04/27/2022
ms.locfileid: "8644022"
---
# <a name="segment-insights-preview"></a>Thông tin chuyên sâu về phân khúc (xem trước)

Khám phá thông tin chuyên sâu và chi tiết hơn về các phân khúc hiện có. Tìm hiểu xem 2 phân khúc có gì khác hoặc tương tự nhau.

## <a name="segment-overlap"></a>Phân khúc chồng chéo

Phép phân tích chồng chéo phân khúc sẽ cho biết có bao nhiêu và khách hàng nào xuất hiện ở 2 phân khúc trở lên. Ví dụ: làm thế nào một phân khúc gồm khách hàng thường xuyên lại chồng chéo với phân khúc khác gồm những khách hàng hài lòng với dịch vụ hoặc sản phẩm của bạn.
Bạn cũng có thể phân tính xem sự chồng chéo thay đổi như thế nào đối với các thuộc tính cụ thể.

### <a name="run-an-overlap-analysis"></a>Chạy phép phân tích sự chồng chéo

1. Đi tới **Phân khúc** rồi chọn tab **Thông tin chi tiết (xem trước)**.

1. Chọn **Mới** rồi bấm vào tùy chọn **Chồng chéo** trong ngăn **Chọn loại thông tin chuyên sâu**.

1. Chọn các phân khúc bạn quan tâm rồi bấm vào **Tiếp**.

1. Không bắt buộc: chọn một hoặc nhiều trường bạn muốn phân tích sự chồng chéo cho từng trường nếu khả thi, sau đó bấm vào **Tiếp**.

1. Đặt tên cho phép phân tích sự chồng chéo, tên hiển thị (không bắt buộc) và thông tin mô tả.

1. Chọn **Lưu** để bắt đầu phân tích. Phép phân tích sự chồng chéo sẽ sẵn sàng khi trạng thái chuyển từ Đang làm mới sang Thành công.

### <a name="view-and-optimize-an-overlap-analysis"></a>Xem và tối ưu hóa phép phân tích sự chồng chéo

Sau khi hoàn thành phân tích, bạn có thể tìm thấy thống tin chuyên sâu trong mục **Phân khúc** > **Thông tin chuyên sâu (xem trước)**.

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-overlap.png" alt-text="Thông tin chuyên sâu về phân khúc chồng chéo.":::

Chọn một thông tin chuyên sâu để xem kết quả phân tích:

- Số lượng thành viên chồng chéo với phân khúc đã chọn cho phép phân tích.
- Số lượng thành viên có trong một phân khúc nhưng không có trong các phân khúc còn lại.
- Nếu bạn đã chọn các trường trong khi định cấu hình phép phân tích sự chồng chéo, bạn sẽ thấy các trường đó trong tab tương ứng. Bạn có thể sử dụng danh sách thả xuống của bộ lọc để chọn bất kỳ mức độ quan tâm thuộc tính nào và bảng ở dưới cùng sẽ hiển thị dữ liệu tương ứng.

## <a name="segment-differentiators"></a>Điểm khác biệt của phân đoạn

Bạn có thể dựa vào các nhân tố khác biệt của phân khúc để tìm ra sự khác nhau của một phân khúc so với số khách hàng còn lại hoặc so với một phân khúc khác. Bạn chỉ cần chọn một phân khúc. Hệ thống sẽ xác định các thuộc tính và phép đo giúp phân biệt phân khúc đã chọn.

### <a name="run-a-differentiator-analysis"></a>Chạy phép phân tích nhân tố khác biệt

1. Đi tới **Phân khúc** rồi chọn tab **Thông tin chi tiết (xem trước)**.

1. Chọn **Mới** rồi bấm vào tùy chọn **Chồng chéo** trong ngăn **Chọn loại thông tin chuyên sâu**.

1. Chọn phân khúc bạn muốn phân tích làm **Phân khúc chính** rồi chọn **Tiếp**.

1. Chọn **Tất cả khách hàng** hoặc **Phân khúc phụ** cần so sánh với phân khúc chính rồi bấm vào **Tiếp**.

1. Không bắt buộc: Chọn một hoặc nhiều trường bạn muốn tập trung phân tích một số thuộc tính cụ thể, sau đó chọn **Tiếp**.

1. Đặt tên cho phép phân tích sự chồng chéo, tên hiển thị (không bắt buộc) và thông tin mô tả.

1. Chọn **Lưu** để bắt đầu phân tích. Phép phân tích sự chồng chéo sẽ sẵn sàng khi trạng thái chuyển từ Đang làm mới sang Thành công.

### <a name="view-and-optimize-a-differentiators-analysis"></a>Xem và tối ưu hóa phép phân tích nhân tố khác biệt

Sau khi hoàn thành phân tích, bạn có thể tìm thấy thống tin chuyên sâu trong mục **Phân khúc** > **Thông tin chuyên sâu (xem trước)**.

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-differentiators.png" alt-text="Thông tin chi tiết về nhân tố khác biệt của phân khúc.":::

Chọn một thông tin chuyên sâu để xem kết quả phân tích. Phép phân tích nhân tố khác biệt gồm có 2 tab. Tab **Thuộc tính** liệt kê các thuộc tính hồ sơ, được coi là nhân tố khác biệt. Tab **Phép đo** liệt kê các nhân tố khác biệt. Mỗi tab bao gồm những thông tin sau:

- Danh sách xếp hạng các nhân tố khác biệt, được sắp xếp theo điểm chênh lệch.
- **Điểm chênh lệch** của từng nhân tố khác biệt. Điểm chênh lệch cho biết mức độ khác biệt của một thuộc tính giữa 2 phân khúc. Điểm chênh lệch càng cao thì càng có nhiều thuộc tính khác nhau giữa 2 phân khúc. Chọn một điểm số để mở ngăn **Điểm chênh lệch**, chứa giá trị phân phối của thuộc tính đó.

## <a name="manage-segment-insights"></a>Quản lý thông tin chuyên sâu về phân khúc

Từ thanh lệnh, bạn có thể dùng những tùy chọn sau cho thông tin chuyên sâu:

- **Quay lại** để trở lại danh sách thông tin chuyên sâu
- **Làm mới** để chạy lại phép phân tích
- **Xóa** để xóa thông tin chuyên sâu này


[!INCLUDE [footer-include](includes/footer-banner.md)]
