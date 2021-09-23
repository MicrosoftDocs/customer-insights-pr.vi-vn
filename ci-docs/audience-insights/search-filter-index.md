---
title: Tìm và lọc hồ sơ khách hàng
description: Nhanh chóng tìm thông tin về hồ sơ khách hàng thống nhất và lọc các thuộc tính được chỉ định.
ms.date: 01/19/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 9eaeb0c93481283324f21122c9528ff5896b9866
ms.sourcegitcommit: b9a81c2acd42d774669d2db3d0430c7d81de991c
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 09/02/2021
ms.locfileid: "7470055"
---
# <a name="customer-profiles-search--filter-index"></a>Hồ sơ khách hàng: Chỉ mục tìm kiếm và lọc

Kết quả của việc thống nhất dữ liệu khách hàng của bạn là một thực thể Hồ sơ khách hàng cung cấp một cái nhìn tổng hợp vào toàn bộ cơ sở khách hàng của bạn. Để nhanh chóng [tìm thông tin về một khách hàng hoặc một nhóm khách hàng cụ thể](customer-profiles.md), bạn có thể đặt cấu hình khả năng **Tìm kiếm** và **Bộ lọc** trên trang **Khách hàng**. Đọc để tìm hiểu cách quản trị viên có thể chỉnh sửa các thuộc tính trên trang **Tìm kiếm và lọc chỉ mục**, trong đó có sẵn cho người dùng để tìm kiếm và lọc.

> [!div class="mx-imgBorder"]
> ![Bộ lọc tìm kiếm.](media/search-filter.png "Bộ lọc tìm kiếm")

## <a name="add-fields-and-specify-attributes"></a>Thêm trường và chỉ định thuộc tính

Nếu đó là lần đầu tiên bạn xác định các thuộc tính có thể tìm kiếm với tư cách là quản trị viên, trước tiên, bạn cần xác định các trường được lập chỉ mục. Chúng tôi khuyên bạn nên chọn tất cả các thuộc tính mà người dùng có thể tìm kiếm và lọc trên trang **Khách hàng**. Bạn chỉ có thể chỉ định các thuộc tính tồn tại trong thực thể hồ sơ khách hàng mà bạn đã tạo trong quá trình thống nhất dữ liệu.

1. Mở trang **Khách hàng** rồi chọn **Tìm kiếm & lọc chỉ mục**.

2. Chọn **+ Thêm** để chỉ định trường lập chỉ mục.

3. Chọn các thuộc tính trong danh sách mà bạn muốn thêm dưới dạng các trường đã lập chỉ mục. Bạn luôn có thể thêm các thuộc tính bằng cách chọn **Thêm**. Bạn cũng có thể xóa bất kỳ thuộc tính nào đã chọn bằng cách chọn biểu tượng **Loại bỏ**.

## <a name="explore-the-indexed-customer-fields-table"></a>Khám phá bảng trường khách hàng đã lập chỉ mục

Các thông tin sau đây được trình bày trong bảng.

- **Tên**: Biểu thị tên của thuộc tính khi nó xuất hiện trong thực thể hồ sơ khách hàng.
- **Loại dữ liệu**: Chỉ định loại dữ liệu là một chuỗi, số hoặc một ngày.
- **Bao gồm trong tìm kiếm** Cho biết liệu một thuộc tính có thể dùng để tìm kiếm khách hàng trên trang **Khách hàng** bằng trường **Tìm kiếm** hay không.
- **Thêm bộ lọc**: Kiểm soát để xác định cách các thuộc tính này có thể được sử dụng để lọc trên trang **Khách hàng**.

## <a name="editing-filtering-options-for-a-given-attribute"></a>Chỉnh sửa các tùy chọn lọc cho một thuộc tính nhất định

Menu **Bộ lọc** trên trang **Khách hàng** có thể bao gồm một số mức thuộc tính khác nhau (ví dụ: các nhóm tuổi khác nhau để lọc khách hàng).

1. Chọn **Thêm bộ lọc** cho một thuộc tính nhất định trên trang **Tìm kiếm và lọc chỉ mục**. Bạn có thể xác định số lượng kết quả và thứ tự mà chúng sẽ được tổ chức. Tùy thuộc vào loại dữ liệu của thuộc tính, một trong các ngăn sau xuất hiện.

- Thuộc tính loại chuỗi: Cho biết số kết quả mong muốn trên bảng điều khiển **Tùy chọn Bộ lọc chuỗi** và chính sách thứ tự mà họ sẽ tổ chức.

- Thuộc tính loại số: Cho biết khoảng thời gian trên bảng điều khiển **Tùy chọn Bộ lọc số** và chính sách thứ tự mà họ sẽ tổ chức.

- Thuộc tính loại ngày: Cho biết khoảng thời gian trên bảng điều khiển **Tùy chọn Bộ lọc ngày** và chính sách thứ tự mà họ sẽ tổ chức.

2. Chọn **Lưu** để áp dụng thay đổi.

3. Chọn **Chạy** sau khi bạn đã sẵn sàng áp dụng cài đặt của mình. Sau khi các thay đổi được xử lý, bạn sẽ thấy chúng trong [thẻ khách hàng trên trang Khách hàng](customer-profiles.md). 

## <a name="next-steps"></a>Các bước tiếp theo

Xem lại [trang hồ sơ hợp nhất](customer-profiles.md) để tìm kiếm các hồ sơ hoặc sử dụng các trường được lập chỉ mục để xem một tập hợp con của tất cả các hồ sơ hợp nhất.


[!INCLUDE[footer-include](../includes/footer-banner.md)]