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
ms.openlocfilehash: f6bcdfc45a49c36f22d6ebc6e919f43b27f899d8
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 06/29/2022
ms.locfileid: "9051710"
---
# <a name="create-measures-from-templates"></a>Tạo các thước đo từ các mẫu

Bạn có thể sử dụng các mẫu được xác định trước thường được sử dụng [đo](measures.md) để tạo ra chúng. Mô tả chi tiết về các mẫu và trải nghiệm có hướng dẫn sẽ giúp bạn tạo giá trị đo hiệu quả. Các mẫu xây dựng dựa trên dữ liệu được ánh xạ từ thực thể *Hoạt động được hợp nhất*. Vì vậy, hãy đảm bảo rằng bạn đã định cấu hình [hoạt động của khách hàng](activities.md) trước khi tạo giá trị đo từ một mẫu.

Để tạo các biện pháp tùy chỉnh, hãy xem [Sử dụng trình tạo thước đo để tạo các thước đo từ đầu](measure-builder.md).

# <a name="individual-consumers-b-to-c"></a>[Người tiêu dùng cá nhân (B2C)](#tab/b2c)

Các mẫu giá trị đo sẵn có: 
- Giá trị giao dịch trung bình (ATV)
- Tổng giá trị giao dịch
- Doanh thu trung bình hàng ngày
- Doanh thu trung bình hàng năm
- Số lượng giao dịch
- Điểm khách hàng thân thiết kiếm được
- Điểm khách hàng thân thiết đã quy đổi
- Số dư điểm khách hàng thân thiết
- Quãng thời gian khách hàng hoạt động
- Thời lượng là thành viên khách hàng thân thiết
- Thời gian kể từ giao dịch mua gần nhất

## <a name="build-a-new-measure-using-a-template"></a>Tạo một thước đo mới bằng cách sử dụng một mẫu

1. Đi đến **Đo**.

1. Chọn **Mới** rồi chọn **Chọn một mẫu**.

   :::image type="content" source="media/measure-use-template.png" alt-text="Ảnh chụp màn hình của menu thả xuống khi tạo một giá trị đo mới được tô sáng trên mẫu.":::

1. Tìm mẫu phù hợp với nhu cầu của bạn rồi chọn **Chọn mẫu**.

1. Xem lại dữ liệu bắt buộc rồi chọn **Bắt đầu** nếu bạn có sẵn tất cả dữ liệu.

1. Lựa chọn **Chỉnh sửa chi tiết** bên cạnh Tên số đo. Cung cấp tên cho biện pháp. Tùy chọn, thêm [thẻ](work-with-tags-columns.md#manage-tags) để đo lường.

   :::image type="content" source="media/measures_edit_details.png" alt-text="Hộp thoại chỉnh sửa chi tiết.":::

1. Chọn **Xong**.

1. Trong phần **Đặt khoảng thời gian**, hãy xác định khung thời gian của dữ liệu sẽ sử dụng. Chọn **Mọi lúc** nếu bạn muốn giá trị đo mới bao quát toàn bộ tập dữ liệu hoặc chọn **Khoảng thời gian cụ thể** nếu muốn giá trị đo tập trung vào một khoảng thời gian.

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Ảnh chụp màn hình về phần khoảng thời gian khi định cấu hình giá trị đo từ một mẫu.":::

1. Trong phần tiếp theo, hãy chọn **Thêm dữ liệu** để chọn các hoạt động rồi ánh xạ dữ liệu tương ứng từ thực thể *Hoạt động được hợp nhất*.

    1. Bước 1/2: Trong mục **Loại hoạt động**, hãy chọn loại thực thể mà bạn muốn sử dụng. Đối với **Hoạt động**, hãy chọn các thực thể mà bạn muốn ánh xạ.
    1. Bước 2/2: Chọn thuộc tính từ *Hoạt động được hợp nhất* cho thành phần theo yêu cầu của công thức. Ví dụ: đối với giá trị giao dịch Trung bình, đó là thuộc tính đại diện cho Giá trị giao dịch. Đối với **Dấu thời gian hoạt động**, hãy chọn thuộc tính từ thực thể Hoạt động được hợp nhất đại diện cho ngày và giờ của hoạt động.
   
1. Khi ánh xạ dữ liệu thành công, bạn có thể thấy trạng thái là **Hoàn thành** cũng như tên của các hoạt động và thuộc tính được ánh xạ.

1. Bây giờ, bạn có thể chọn **Chạy** để tính toán kết quả của giá trị đo. Để tinh chỉnh giá trị đo về sau, hãy chọn **Lưu bản nháp**.

# <a name="business-accounts-b-to-b"></a>[Tài khoản doanh nghiệp (B2B)](#tab/b2b)

Tính năng này chỉ dùng được cho các giá trị đo được tạo trong môi trường có khách hàng riêng lẻ là đối tượng mục tiêu chính.

---
