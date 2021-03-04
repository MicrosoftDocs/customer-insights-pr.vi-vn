---
title: Hoạt động của khách hàng
description: Xác định các hoạt động của khách hàng và xem chúng trong dòng thời gian của khách hàng.
ms.date: 10/13/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: adkuppa
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: dcef8f0547009e1488f1abe91423fa0bf5b061de
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267458"
---
# <a name="customer-activities"></a>Hoạt động của khách hàng

Kết hợp các hoạt động của khách hàng từ [nhiều nguồn dữ liệu khác nhau](data-sources.md) trong Dynamics 365 Customer Insights để tạo dòng thời gian của khách hàng liệt kê các hoạt động theo thứ tự thời gian. Bạn có thể bao gồm tiến trình trong các ứng dụng tương tác với khách hàng trong Dynamics 365 thông qua [Phần bổ trợ Thẻ khách hàng](customer-card-add-in.md) hoặc trong bảng điều khiển Power BI.

## <a name="define-an-activity"></a>Xác định hoạt động

Nguồn dữ liệu của bạn bao gồm các thực thể có dữ liệu giao dịch và hoạt động từ nhiều nguồn dữ liệu. Xác định các thực thể này và chọn các hoạt động bạn muốn xem trên dòng thời gian của khách hàng. Chọn thực thể bao gồm hoạt động mục tiêu hoặc hoạt động của bạn.

1. Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Dữ liệu** > **Hoạt động**.

1. Chọn **Thêm hoạt động**.

   > [!NOTE]
   > Một thực thể phải có ít nhất một thuộc tính loại **Ngày** để được đưa vào dòng thời gian của khách hàng và bạn không thể thêm các thực thể mà không có trường **Ngày**. Kiểm soát **Thêm hoạt động** bị vô hiệu hóa nếu không tìm thấy thực thể đó.

1. Trong ngăn **Thêm hoạt động**, đặt các giá trị cho các trường sau:

   - **Thực thể**: Chọn một thực thể bao gồm dữ liệu giao dịch hoặc hoạt động.
   - **Khóa chính**: Chọn trường xác định duy nhất một bản ghi. Nó không nên chứa bất kỳ giá trị trùng lặp, giá trị trống hoặc giá trị thiếu nào.
   - **Dấu thời gian**: Chọn trường đại diện cho thời gian bắt đầu hoạt động của bạn.
   - **Biến cố**: Chọn trường là sự kiện cho hoạt động.
   - **Địa chỉ web**: Chọn trường đại diện cho một URL cung cấp thông tin bổ sung về hoạt động này. Ví dụ: hệ thống giao dịch lấy nguồn từ hoạt động này. URL này có thể là bất kỳ trường nào từ nguồn dữ liệu hoặc được xây dựng làm một trường mới bằng cách chuyển đổi Power Query. Dữ liệu URL này sẽ được lưu trữ trong thực thể Hoạt động hợp nhất, có thể được dùng xuôi dòng bằng API.
   - **Chi tiết**: Hoặc chọn trường được thêm vào để biết thêm chi tiết.
   - **Biểu tượng**: Hoặc chọn biểu tượng đại diện cho hoạt động này.
   - **Loại hoạt động**: Xác định tham chiếu loại hoạt động cho Common Data Model mô tả chính xác nhất định nghĩa ngữ nghĩa của hoạt động.

1. Trong phần **Thiết lập mối quan hệ**, đặt cấu hình chi tiết để kết nối dữ liệu hoạt động của bạn với khách hàng tương ứng.

    - **Trường thực thể hoạt động**: Chọn trường trong thực thể hoạt động của bạn sẽ được sử dụng để thiết lập mối quan hệ với thực thể khác.
    - **Thực thể khách hàng**: Chọn thực thể khách hàng nguồn tương ứng mà thực thể hoạt động của bạn sẽ có mối quan hệ. Bạn chỉ có thể liên quan đến những thực thể khách hàng nguồn được sử dụng trong quy trình hợp nhất dữ liệu.
    - **Trường thực thể khách hàng**: Trường này hiển thị khóa chính của thực thể khách hàng nguồn như được chọn trong quy trình bản đồ. Trường khóa chính này trong thực thể khách hàng nguồn được sử dụng để thiết lập mối quan hệ với thực thể hoạt động.
    - **Tên**: Nếu mối quan hệ giữa thực thể hoạt động này và thực thể khách hàng nguồn được chọn đã tồn tại, thì tên mối quan hệ sẽ ở chế độ chỉ đọc. Nếu không có mối quan hệ như vậy tồn tại, một mối quan hệ mới sẽ được tạo ra với tên được cung cấp ở đây.
   
   > [!div class="mx-imgBorder"]
   > ![Xác định mối quan hệ của thực thể](media/activities-entities-define.png "Xác định mối quan hệ của thực thể")

1. Chọn **Lưu** để áp dụng thay đổi.

1. Trên trang **Hoạt động**, chọn **Chạy**.

> [!TIP]
> Có [6 loại trạng thái](system.md#status-types) cho các nhiệm vụ/quy trình. Ngoài ra, hầu hết các quy trình [phụ thuộc vào các quá trình hạ nguồn khác](system.md#refresh-policies). Bạn có thể chọn trạng thái của một quy trình để xem chi tiết về tiến trình của toàn bộ công việc. Sau khi chọn **Xem chi tiết** đối với một trong các tác vụ của công việc, bạn sẽ tìm thấy thông tin bổ sung: thời gian xử lý, ngày xử lý gần nhất và tất cả các lỗi và cảnh báo liên quan đến tác vụ.

## <a name="edit-an-activity"></a>Chỉnh sửa hoạt động

1. Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Dữ liệu** > **Hoạt động**.

2. Chọn thực thể hoạt động bạn muốn chỉnh sửa và chọn **Chỉnh sửa**. Hoặc, bạn có thể di chuột qua hàng thực thể và chọn biểu tượng **Chỉnh sửa**.

3. Bấm vào biểu tượng **Chỉnh sửa**.

4. Trong ngăn **Chỉnh sửa hoạt động**, cập nhật các giá trị và chọn **Lưu**.

5. Trên trang **Hoạt động**, chọn **Chạy**.

## <a name="delete-an-activity"></a>Xóa hoạt động

1. Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Dữ liệu** > **Hoạt động**.

2. Chọn thực thể hoạt động bạn muốn xóa và chọn **Xóa**. Hoặc, bạn có thể di chuột qua hàng thực thể và chọn biểu tượng **Xóa**. Ngoài ra, bạn có thể chọn nhiều thực thể hoạt động sẽ bị xóa cùng một lúc.
   > [!div class="mx-imgBorder"]
   > ![Chỉnh sửa hoặc xóa mối quan hệ thực thể](media/activities-entities-edit-delete.png "Chỉnh sửa hoặc xóa mối quan hệ thực thể")

3. Chọn biểu tượng **Xóa**.

4. Xác nhận tác vụ xóa của bạn.


[!INCLUDE[footer-include](../includes/footer-banner.md)]