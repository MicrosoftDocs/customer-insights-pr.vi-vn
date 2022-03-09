---
title: Xem và tạo chỉ số
description: Cách tạo, chỉnh sửa và xóa chỉ số.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 7e8c96f38af74f25080a40fd92e73f05c71320a8
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 02/16/2022
ms.locfileid: "8229842"
---
# <a name="view-and-create-metrics"></a>Xem và tạo chỉ số

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Các chỉ số giúp bạn hiểu hành vi của khách truy cập. Chỉ số tổng hợp các thuộc tính sự kiện, đồng thời đo lường số liệu thống kê và hiệu suất của các thuộc tính web.  

Giả sử rằng bạn đang chạy một chương trình khuyến mãi tiếp thị trên trang web của mình. Bạn có thể sử dụng các chỉ số để theo dõi số lượng khách truy cập duy nhất hoặc người dùng đã truy cập vào trang web của mình trong thời gian khuyến mãi. Khi phân tích các chỉ số, bạn sẽ hiểu rõ hơn về đối tượng trên trang web của mình. Bạn có thể kết hợp các chỉ số với [các thứ nguyên](dimensions.md) trên [báo cáo tùy chỉnh](custom-reports.md) để đo lường hành vi nhằm thấu hiểu người dùng. Ví dụ: bạn có thể tách biệt khách truy cập thành các danh mục mới và cũ để xác định sự khác biệt về sở thích và ý định giữa các nhóm.

## <a name="view-metrics"></a>Xem chỉ số

Thông tin chuyên sâu về tương tác bao gồm dữ liệu tổng hợp thường dùng về các thuộc tính sự kiện dưới dạng các chỉ số hệ thống: 

- Khách truy cập
- Lượt truy cập
- Lượt xem trang
- Lượt bấm

Các chỉ số hệ thống này dựa trên các thuộc tính sự kiện hiện có trong sự kiện cơ sở.

1. Chuyển đến phần **Dữ liệu** ở ngăn điều hướng bên trái. 
1. Chọn tab **Chỉ số** để xem danh sách tất cả các chỉ số trong không gian làm việc. 
   > [!NOTE]
   > Các chỉ số do hệ thống tạo đều ở chế độ chỉ đọc. Bạn không thể chỉnh sửa hoặc xóa chúng. Bạn chỉ có thể tạo và chỉnh sửa chỉ số tùy chỉnh.

## <a name="create-a-metric"></a>Tạo chỉ số

Quản trị viên môi trường và không gian làm việc có thể tạo chỉ số. Các thuộc tính sự kiện phải được gửi đến không gian làm việc trước khi bạn tạo chỉ số. Bạn có thể tạo chỉ số dựa trên các thuộc tính sự kiện do sự kiện cơ sở gửi hoặc sử dụng SDK web để [gửi thuộc tính sự kiện tùy chỉnh](advanced-SDK-implementation.md).

1. Chuyển đến phần **Dữ liệu** > **Chỉ số**.
1. Chọn **Số liệu mới** để mở hộp thoại **Thư viện nguồn lực** và **Số liệu mới không có tiêu đề**.

   :::image type="content" source="media/new-metric.png" alt-text="Thêm số liệu vào sự kiện.":::

1. Trong hộp thoại **Số liệu mới không có tiêu đề**, chọn danh sách thả xuống **Định dạng** rồi chọn loại dữ liệu **Số nguyên** hoặc **Kép**. Số nguyên là một số nguyên. Đối với Kép, bạn có thể chọn một và ba chữ số thập phân.

   :::image type="content" source="media/create-new-metric.png" alt-text="Tạo số liệu mới.":::
   
5. Trong ngăn **Thư viện tài nguyên**, hãy tìm thuộc tính sự kiện làm cơ sở cho số liệu.
6. Chọn **dấu cộng (+)** bên cạnh thuộc tính để sử dụng thuộc tính đó trong công thức. Bạn chỉ có thể tạo công thức dựa trên một thuộc tính. 
7. Chọn một trong số các chức năng tổng hợp sau. 

   - Tổng: tổng số học của tất cả các giá trị 
   - Trung bình: giá trị trung bình của tất cả các giá trị
   - Đếm: tổng số giá trị
   - Đếm riêng biệt: tổng số giá trị riêng biệt

   Sau khi xác định chỉ số, bạn sẽ thấy bản xem trước hoạt động của chỉ số trong một giờ qua.

1. Chọn **Lưu**. 
1. Nhập tên cho chỉ số rồi chọn **Lưu**.

Có thể mất đến một phút cho chỉ số trước khi bạn có thể sử dụng để [tạo báo cáo tùy chỉnh](custom-reports.md).

## <a name="edit-a-metric"></a>Chỉnh sửa chỉ số

Bạn chỉ có thể chỉnh sửa các số liệu tùy chỉnh.

1. Chuyển đến phần **Dữ liệu** > **Chỉ số**.
1. Chọn chỉ số trong danh sách.
1. Thay đổi định nghĩa của chỉ số
1. Chọn **Lưu**.

## <a name="change-the-name-of-a-metric"></a>Thay đổi tên chỉ số

Bạn chỉ có thể thay đổi tên của số liệu tùy chỉnh.

1. Chuyển đến phần **Dữ liệu** > **Chỉ số**.
1. Chọn **Thêm [...]** cho một chỉ số rồi chọn **Chỉnh sửa tên**.
1. Thay đổi tên. 
1. Chọn **Đổi tên**.

## <a name="delete-a-metric"></a>Xóa chỉ số

Bạn chỉ có thể xóa các số liệu tùy chỉnh.

1. Chuyển đến phần **Dữ liệu** > **Chỉ số**.
1. Chọn **Thêm [...]** cho một chỉ số rồi chọn **Xóa**.

   :::image type="content" source="media/delete-metric.png" alt-text="Xóa số liệu khỏi sự kiện.":::

1. Chọn **Xóa** để xác nhận thao tác xóa.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
