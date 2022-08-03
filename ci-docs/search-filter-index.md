---
title: Quản lý chỉ mục tìm kiếm và lọc cho hồ sơ khách hàng
description: Nhanh chóng tìm thông tin về hồ sơ khách hàng thống nhất và lọc các thuộc tính được chỉ định.
ms.date: 07/22/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-search-filter
- customerInsights
ms.openlocfilehash: dfbfcbff3ffb3e4483252377e591229631d38556
ms.sourcegitcommit: c45c3e044034bf866b0662f80a59166cee4ababe
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 07/22/2022
ms.locfileid: "9187935"
---
# <a name="manage-the-search--filter-index-for-customer-profiles"></a>Quản lý chỉ mục tìm kiếm và lọc cho hồ sơ khách hàng

Kết quả của việc hợp nhất dữ liệu khách hàng của bạn là *khách hàng* thực thể cung cấp một cái nhìn thống nhất về tổng cơ sở khách hàng của bạn. Để người dùng nhanh chóng [tìm thông tin về một khách hàng hoặc một nhóm khách hàng cụ thể](customer-profiles.md), quản trị viên phải định cấu hình **Tìm kiếm** và **Lọc** khả năng cho **Khách hàng** trang.

   :::image type="content" source="media/search-filter.png" alt-text="Bộ lọc tìm kiếm":::

## <a name="define-searchable-attributes-and-indexed-fields"></a>Xác định các thuộc tính có thể tìm kiếm và các trường được lập chỉ mục

Nếu đây là lần đầu tiên bạn xác định các thuộc tính có thể tìm kiếm với tư cách là quản trị viên, trước tiên hãy xác định các trường được lập chỉ mục. Chúng tôi khuyên bạn nên chọn tất cả các thuộc tính mà người dùng có thể tìm kiếm và lọc trên trang **Khách hàng**. Chỉ các thuộc tính tồn tại trong *khách hàng* thực thể được tạo trong quá trình hợp nhất dữ liệu có thể được chỉ định.

1. Đi đến **Khách hàng** và chọn **Tìm kiếm & lọc chỉ mục**.

1. Lựa chọn **+ Thêm**.

1. Chọn các thuộc tính trong danh sách bạn muốn thêm làm trường được lập chỉ mục và nhấp vào **Ứng dụng**.

1. Để thêm các thuộc tính khác, hãy chọn **cộng**. Để xóa một thuộc tính đã chọn, hãy chọn thuộc tính và sau đó **Xóa bỏ**.

   :::image type="content" source="media/search-filter-index.png" alt-text="Tìm kiếm & lọc trang chỉ mục.":::

1. Lựa chọn **Chạy** khi bạn đã sẵn sàng áp dụng cài đặt tìm kiếm và bộ lọc của mình. Sau khi các thay đổi được xử lý, hãy xem chúng trong [thẻ khách hàng trên trang Khách hàng](customer-profiles.md).

## <a name="define-filtering-options-for-a-given-attribute"></a>Xác định các tùy chọn lọc cho một thuộc tính nhất định

Thiết lập các trường có thể được sử dụng để lọc khách hàng trên **Khách hàng** trang.

1. Đi đến **Khách hàng** và chọn **Tìm kiếm & lọc chỉ mục**.

1. Chọn một thuộc tính và **Thêm bộ lọc**. Xác định số lượng kết quả và thứ tự sắp xếp chúng. Tùy thuộc vào kiểu dữ liệu của thuộc tính, một trong các ngăn sau sẽ xuất hiện.

   - Thuộc tính kiểu chuỗi: Chỉ định số lượng kết quả mong muốn trên **Bộ lọc chuỗi** và chính sách đặt hàng mà chúng sẽ được sắp xếp.

   - Thuộc tính kiểu số: Chỉ định khoảng thời gian được bao gồm trên **Bộ lọc số** và chính sách đặt hàng mà chúng sẽ được sắp xếp.

   - Thuộc tính loại ngày: Chỉ định khoảng thời gian được bao gồm trên **Bộ lọc ngày** và chính sách đặt hàng mà chúng sẽ được sắp xếp.

1. Chọn **OK**. Lặp lại cho tất cả các thuộc tính bạn muốn lọc.

1. Lựa chọn **Chạy** khi bạn đã sẵn sàng áp dụng cài đặt tìm kiếm và bộ lọc của mình. Sau khi các thay đổi được xử lý, hãy xem chúng trong [thẻ khách hàng trên trang Khách hàng](customer-profiles.md).

## <a name="view-indexed-customer-fields"></a>Xem các trường khách hàng đã lập chỉ mục

Các **Tìm kiếm & lọc chỉ mục** trang hiển thị các thông tin sau:

- **Tên** : Đại diện cho tên của thuộc tính khi nó xuất hiện trong *khách hàng* thực thể.
- **Loại dữ liệu**: Chỉ định loại dữ liệu là một chuỗi, số hoặc một ngày.
- **Bao gồm trong tìm kiếm** Cho biết liệu một thuộc tính có thể dùng để tìm kiếm khách hàng trên trang **Khách hàng** bằng trường **Tìm kiếm** hay không.
- **Thêm bộ lọc**: Kiểm soát để xác định cách các thuộc tính này có thể được sử dụng để lọc trên trang **Khách hàng**.

## <a name="next-steps"></a>Các bước tiếp theo

Xem lại [trang hồ sơ hợp nhất](customer-profiles.md) để tìm kiếm các hồ sơ hoặc sử dụng các trường được lập chỉ mục để xem một tập hợp con của tất cả các hồ sơ hợp nhất.

[!INCLUDE [footer-include](includes/footer-banner.md)]
