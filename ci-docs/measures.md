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
ms.openlocfilehash: 99368a7ab2e8d7b3e53c04fbf25bb23bd2e550a9
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245399"
---
# <a name="measures-overview"></a>Tổng quan về các biện pháp

Giá trị đo giúp bạn hiểu rõ hơn về hành vi của khách hàng và hiệu quả kinh doanh. Giá trị đo xem xét các giá trị có liên quan từ [hồ sơ hợp nhất](data-unification.md). Ví dụ: một doanh nghiệp muốn xem *tổng mức chi tiêu của mỗi khách hàng* để nắm được lịch sử mua hàng của một khách hàng cá nhân hoặc đo lường *tổng doanh số của công ty* để nắm được tổng doanh thu của toàn bộ doanh nghiệp.

Tạo các biện pháp để lập kế hoạch hoạt động kinh doanh bằng cách truy vấn dữ liệu khách hàng và trích xuất thông tin chi tiết. Ví dụ: tạo một thước đo về *tổng chi tiêu cho mỗi khách hàng* và *tổng lợi nhuận trên mỗi khách hàng* để giúp xác định nhóm khách hàng có mức chi tiêu cao nhưng lợi nhuận thu về cao. Sau đó, [tạo một phân đoạn](segments.md) dựa trên các biện pháp này để thúc đẩy các hành động tốt nhất tiếp theo.

## <a name="create-a-measure"></a>Tạo giá trị đo

Chọn cách tạo thước đo dựa trên đối tượng mục tiêu của bạn.

# <a name="individual-consumers-b-to-c"></a>[Người tiêu dùng cá nhân (B2C)](#tab/b2c)

- Từ đầu với trình tạo thước đo: [Xây dựng của riêng bạn](measure-builder.md).
- Từ các biện pháp thường dùng: [Sử dụng các mẫu được xác định trước](measure-templates.md).

# <a name="business-accounts-b-to-b"></a>[Tài khoản doanh nghiệp (B2B)](#tab/b2b)

Từ đầu với trình tạo thước đo: [Xây dựng của riêng bạn](measure-builder.md).

---

## <a name="manage-existing-measures"></a>Quản lý các biện pháp hiện có

Đi đến **Đo** để xem các thước đo bạn đã tạo, trạng thái, loại thước đo và lần cuối cùng dữ liệu được làm mới. Bạn có thể sắp xếp danh sách các thước đo theo bất kỳ cột nào hoặc sử dụng hộp tìm kiếm để tìm thước đo bạn muốn quản lý.

Chọn bên cạnh một biện pháp để xem các hành động có sẵn. Chọn tên thước đo để xem trước kết quả đầu ra và tải xuống tệp CSV.

:::image type="content" source="media/measures-actions.png" alt-text="Các hành động để quản lý các giá trị đo đơn lẻ."lightbox="media/measures-actions.png":::

- **Chỉnh sửa** các biện pháp để thay đổi các thuộc tính của nó.
- **Làm mới** biện pháp bao gồm dữ liệu mới nhất.
- **Đổi tên** giá trị đo.
- **Hoạt động** hoặc **Hủy kích hoạt** các biện pháp. Các biện pháp không hoạt động sẽ không được làm mới trong thời gian [làm mới theo lịch trình](schedule-refresh.md) và có **Trạng thái** được liệt kê là **Đã bỏ qua**, cho thấy rằng việc làm mới thậm chí còn chưa được thử.
- **Nhãn** đến [quản lý thẻ](work-with-tags-columns.md#manage-tags) cho các biện pháp.
- **Xóa** giá trị đo.
- **Cột** đến [tùy chỉnh các cột](work-with-tags-columns.md#customize-columns) màn hình đó.
- **Lọc** đến [lọc trên các thẻ](work-with-tags-columns.md#filter-on-tags).
- **Tim kiêm tên** để tìm kiếm theo tên số đo.

## <a name="refresh-measures"></a>Làm mới các biện pháp

Các phép đo có thể được làm mới theo lịch trình tự động hoặc được làm mới theo cách thủ công theo yêu cầu. Để làm mới một hoặc nhiều biện pháp theo cách thủ công, hãy chọn chúng và chọn **Làm mới**. Đến [lên lịch làm mới tự động](schedule-refresh.md), đi đến **Quản trị viên** > **Hệ thống** > **Lịch trình**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
