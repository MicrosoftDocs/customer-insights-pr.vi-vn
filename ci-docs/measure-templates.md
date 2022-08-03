---
title: Tạo các thước đo từ các mẫu
description: Xác định các biện pháp sử dụng mẫu cho các trường hợp sử dụng phổ biến.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measure-template
- customerInsights
ms.openlocfilehash: 6dc7fce78d10ba91de4b2abf54c6c6ab1c919d3a
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170799"
---
# <a name="create-measures-from-templates"></a>Tạo các thước đo từ các mẫu

Sử dụng các mẫu được xác định trước thường được sử dụng [đo](measures.md) để tạo ra chúng. Các mẫu xây dựng dựa trên dữ liệu được ánh xạ từ thực thể *Hoạt động được hợp nhất*. Vì vậy, hãy đảm bảo rằng bạn đã định cấu hình [hoạt động của khách hàng](activities.md) trước khi tạo giá trị đo từ một mẫu.

Các mẫu đo lường chỉ được hỗ trợ trong các môi trường dành cho **khách hàng cá nhân**. Để tạo các biện pháp tùy chỉnh hoặc tạo các thước đo cho B-to-B, hãy xem [Sử dụng trình tạo thước đo](measure-builder.md).

Các mẫu giá trị đo sẵn có:
- Giá trị giao dịch trung bình (ATV)
- Tổng giá trị giao dịch
- Doanh thu trung bình hàng ngày
- Doanh thu trung bình hàng tháng
- Doanh thu trung bình hàng năm
- Số lượng giao dịch
- Điểm khách hàng thân thiết kiếm được
- Điểm khách hàng thân thiết đã quy đổi
- Số dư điểm khách hàng thân thiết
- Quãng thời gian khách hàng hoạt động
- Thời lượng là thành viên khách hàng thân thiết
- Thời gian kể từ giao dịch mua gần nhất

## <a name="build-a-new-measure-using-a-template"></a>Xây dựng một thước đo mới bằng cách sử dụng một mẫu

1. Đi đến **Đo**.

1. Chọn **Mới** rồi chọn **Chọn một mẫu**.

   :::image type="content" source="media/measure-use-template.png" alt-text="Ảnh chụp màn hình của menu thả xuống khi tạo một giá trị đo mới được tô sáng trên mẫu.":::

1. Tìm mẫu phù hợp với nhu cầu của bạn rồi chọn **Chọn mẫu**.

1. Xem lại dữ liệu bắt buộc rồi chọn **Bắt đầu** nếu bạn có sẵn tất cả dữ liệu.

1. Lựa chọn **Chỉnh sửa chi tiết** bên cạnh Tên số đo. Cung cấp tên cho biện pháp. Tùy chọn, thêm [thẻ](work-with-tags-columns.md#manage-tags) để đo lường.

   :::image type="content" source="media/measures_edit_details.png" alt-text="Hộp thoại chỉnh sửa chi tiết.":::

1. Chọn **Xong**.

1. Bên trong **Đặt khoảng thời gian**, xác định khung thời gian của dữ liệu. Chọn **Mọi lúc** nếu bạn muốn giá trị đo mới bao quát toàn bộ tập dữ liệu hoặc chọn **Khoảng thời gian cụ thể** nếu muốn giá trị đo tập trung vào một khoảng thời gian.

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Ảnh chụp màn hình về phần khoảng thời gian khi định cấu hình giá trị đo từ một mẫu.":::

1. Trong phần tiếp theo, hãy chọn **Thêm dữ liệu** để chọn các hoạt động rồi ánh xạ dữ liệu tương ứng từ thực thể *Hoạt động được hợp nhất*.

    1. Bước 1/2: Trong mục **Loại hoạt động**, hãy chọn loại thực thể mà bạn muốn sử dụng. Vì **Các hoạt động**, chọn các thực thể bạn muốn ánh xạ, sau đó chọn **Tiếp theo**.
    1. Bước 2/2: Chọn thuộc tính từ *Hoạt động được hợp nhất* cho thành phần theo yêu cầu của công thức. Ví dụ: đối với giá trị giao dịch Trung bình, đó là thuộc tính đại diện cho Giá trị giao dịch. Vì **Dấu thời gian hoạt động**, chọn thuộc tính từ *Hoạt động hợp nhất* thực thể đại diện cho ngày và giờ của hoạt động.
    1. Chọn **Lưu.**

    Khi ánh xạ dữ liệu thành công, trạng thái hiển thị **Hoàn thành** và tên của các hoạt động được ánh xạ và hiển thị thuộc tính.

1. Lựa chọn **Chạy** để tính toán kết quả của phép đo. Lựa chọn **Lưu bản nháp** nếu bạn muốn giữ cấu hình hiện tại và chạy biện pháp sau. Các **Đo** hiển thị trang.

## <a name="next-step"></a>Bước tiếp theo

Sử dụng các biện pháp hiện có để tạo [một phân khúc khách hàng](segments.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
