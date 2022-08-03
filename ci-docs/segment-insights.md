---
title: Thông tin chuyên sâu về phân khúc (xem trước)
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
ms.openlocfilehash: ccb33594a3a92e87d307f3300c77772ef8b4a82f
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 07/18/2022
ms.locfileid: "9171029"
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

1. Sau khi hoàn thành phân tích, bạn có thể tìm thấy thống tin chuyên sâu trong mục **Phân khúc** > **Thông tin chuyên sâu (xem trước)**.

   :::image type="content" source="media/segment-overlap.png" alt-text="Thông tin chuyên sâu về phân khúc chồng chéo.":::

1. Chọn một thông tin chuyên sâu để xem kết quả phân tích:

   - Số lượng thành viên chồng chéo với phân khúc đã chọn cho phép phân tích.
   - Số lượng thành viên có trong một phân khúc nhưng không có trong các phân khúc còn lại.
   - Nếu bạn đã chọn các trường trong khi định cấu hình phép phân tích sự chồng chéo, bạn sẽ thấy các trường đó trong tab tương ứng. Bạn có thể sử dụng danh sách thả xuống của bộ lọc để chọn bất kỳ mức độ quan tâm thuộc tính nào và bảng ở dưới cùng sẽ hiển thị dữ liệu tương ứng.

## <a name="segment-differentiators"></a>Điểm khác biệt của phân đoạn

Bạn có thể dựa vào các nhân tố khác biệt của phân khúc để tìm ra sự khác nhau của một phân khúc so với số khách hàng còn lại hoặc so với một phân khúc khác. Chọn một phân đoạn và hệ thống xác định các thuộc tính cấu hình và các thước đo để phân biệt phân đoạn đã chọn.

### <a name="run-a-differentiator-analysis"></a>Chạy phép phân tích nhân tố khác biệt

1. Đi tới **Phân khúc** rồi chọn tab **Thông tin chi tiết (xem trước)**.

1. Lựa chọn **Mới** và chọn **Người khác biệt** tùy chọn trong **Chọn loại thông tin chi tiết** ngăn.

1. Chọn phân khúc bạn muốn phân tích làm **Phân khúc chính** rồi chọn **Tiếp**.

1. Chọn **Tất cả khách hàng** hoặc **Phân khúc phụ** cần so sánh với phân khúc chính rồi bấm vào **Tiếp**.

1. Không bắt buộc: Chọn một hoặc nhiều trường bạn muốn tập trung phân tích một số thuộc tính cụ thể, sau đó chọn **Tiếp**.

1. Cung cấp tên cho bạn phân tích điểm khác biệt, tên hiển thị tùy chọn và mô tả.

1. Chọn **Lưu** để bắt đầu phân tích. Phân tích điểm khác biệt đã sẵn sàng khi trạng thái thay đổi từ Làm mới thành Thành công.

### <a name="view-and-optimize-a-differentiators-analysis"></a>Xem và tối ưu hóa phép phân tích nhân tố khác biệt

1. Sau khi hoàn thành phân tích, hãy chuyển đến **Phân đoạn** > **Thông tin chi tiết (xem trước)**.

   :::image type="content" source="media/segment-differentiators.png" alt-text="Thông tin chi tiết về nhân tố khác biệt của phân khúc.":::

1. Chọn một thông tin chuyên sâu để xem kết quả phân tích. Phép phân tích nhân tố khác biệt gồm có 2 tab. Tab **Thuộc tính** liệt kê các thuộc tính hồ sơ, được coi là nhân tố khác biệt. Tab **Phép đo** liệt kê các nhân tố khác biệt. Mỗi tab bao gồm những thông tin sau:

   - Danh sách xếp hạng các nhân tố khác biệt, được sắp xếp theo điểm chênh lệch.
   - **Điểm chênh lệch** của từng nhân tố khác biệt. Điểm chênh lệch cho biết mức độ khác biệt của một thuộc tính giữa 2 phân khúc. Điểm chênh lệch càng cao thì càng có nhiều thuộc tính khác nhau giữa 2 phân khúc. Chọn một điểm số để mở ngăn **Điểm chênh lệch**, chứa giá trị phân phối của thuộc tính đó.

## <a name="manage-segment-insights"></a>Quản lý thông tin chuyên sâu về phân khúc

Đi đến **Phân đoạn** > **Thông tin chi tiết (xem trước)** để xem thông tin chi tiết về phân khúc của bạn và quản lý chúng. Chọn thông tin chi tiết về phân đoạn để xem các hành động có sẵn.

- **Lượt xem** phân tích cái nhìn sâu sắc
- **Chỉnh sửa** cái nhìn sâu sắc để thay đổi các thuộc tính của nó
- **Làm mới** cái nhìn sâu sắc để chạy lại phân tích
- **Đổi tên** sự thấu hiểu
- **Xóa bỏ** sự thấu hiểu

[!INCLUDE [footer-include](includes/footer-banner.md)]
