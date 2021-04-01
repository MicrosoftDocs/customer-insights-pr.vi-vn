---
title: Xem hồ sơ khách hàng
description: Nhận thông tin kết hợp về dữ liệu khách hàng hợp nhất của bạn.
ms.date: 12/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: d6a9e7872a488b6d68afce35b547f93cc4a7c652
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596893"
---
# <a name="customer-profiles"></a>Hồ sơ khách hàng

Trang **Khách hàng** hiển thị thông tin kết hợp về khách hàng của bạn, dựa trên dữ liệu hồ sơ thu thập được từ [tất cả nguồn dữ liệu](data-sources.md). Hồ sơ khách hàng có sẵn sau khi bạn [tạo thực thể khách hàng thống nhất](data-unification.md). Hãy chắc chắn rằng bạn hoàn thành quy trình hợp nhất dữ liệu để có được dạng xem phong phú hơn về khách hàng của mình. Trang cũng cho phép bạn tìm kiếm khách hàng.

Khách hàng có thể là cá nhân hoặc tổ chức (xem trước). Mỗi hồ sơ khách hàng hoặc tổ chức được đại diện bởi một ngăn xếp. Chọn một ngăn xếp để xem thông tin bổ sung về khách hàng hoặc tổ chức cụ thể đó. Sử dụng các điều khiển phân trang ở cuối trang để xem các bản ghi bổ sung.

> [!div class="mx-imgBorder"] 
> ![Hồ sơ khách hàng B2C](media/profiles-customers.png "Hồ sơ khách hàng B2C")

Tổ chức (Xem trước)
> [!div class="mx-imgBorder"] 
> ![Hồ sơ khách hàng B2B](media/profile-customers-b2b.png "Hồ sơ khách hàng B2B")

> [!NOTE]
> Nếu bạn không thể nhìn thấy lát khi bạn chọn **Khách hàng** trong điều hướng, quản trị viên của bạn cần phải [xác định ít nhất một thuộc tính có thể tìm kiếm](search-filter-index.md) trên **Chỉ mục tìm kiếm & lọc**.

## <a name="search-for-customers"></a>Tìm kiếm khách hàng

Tìm kiếm khách hàng bằng cách nhập tên hoặc một số thuộc tính khác vào hộp tìm kiếm. Tìm kiếm chỉ hoạt động trong thực thể Hồ sơ khách hàng được tạo trong quá trình hợp nhất dữ liệu.

Là quản trị viên, bạn có thể định cấu hình các thuộc tính có thể tìm kiếm bằng cách sử dụng trang **Tìm kiếm và lọc chỉ mục**. Để biết thêm thông tin, hãy xem [Quản lý tìm kiếm và lọc chỉ mục](search-filter-index.md).

## <a name="filter-customers"></a>Lọc khách hàng

Bạn có thể lọc khách hàng theo các trường thực thể Hồ sơ khách hàng. Tương tự như tìm kiếm, trước tiên, quản trị viên của bạn sẽ cần xác định các trường là có thể lọc bằng cách sử dụng trang **Tìm kiếm và lọc chỉ mục**.

1. Chọn **Bộ lọc** trên trang **Khách hàng**.

2. Chọn các hộp bên cạnh các thuộc tính bạn muốn lọc khách hàng.

   > [!div class="mx-imgBorder"] 
   > ![Hồ sơ khách hàng](media/profiles-customers3.png "Hồ sơ khách hàng")

3. Xóa bộ lọc của bạn bằng cách chọn **Xóa bộ lọc** trên trang **Khách hàng**.

##  <a name="customer-details-page"></a>Trang thông tin chi tiết về khách hàng

Chọn bất kỳ lát khách hàng nào để mở **Trang thông tin chi tiết về khách hàng**. Chế độ xem này chứa thông tin hợp nhất cho khách hàng đã chọn.

Thông tin chi tiết về khách hàng bao gồm:

-   **Lát hồ sơ khách hàng:** Lát này hiển thị các giá trị khác nhau từ thực thể hồ sơ khách hàng hợp nhất. Những chi tiết này có thể bao gồm địa chỉ email, tên, thành phố, v.v. 

-   **Sở thích tiềm năng, thương hiệu tiềm năng:** Hiển thị nếu bạn đã định cấu hình phần bổ sung của bên thứ nhất. Nó thể hiện sở thích và mối quan hệ tiềm năng đối với các thương hiệu mà một khách hàng có hồ sơ tương tự như khách hàng này có thể có. Để biết thêm thông tin, hãy xem [Làm phong phú hồ sơ khách hàng bằng thương hiệu và sở thích](enrichment-microsoft-graph.md).

-   **Đo lường:** Hiển thị nếu bạn đã định cấu hình một hoặc nhiều loại biện pháp đo lường cụ thể: đo lường thuộc tính khách hàng. Chúng bao gồm các KPI được tính toán xung quanh khách hàng của bạn ở cấp độ khách hàng cá nhân. Để biết thêm thông tin, hãy xem [Xác định và quản lý các biện pháp](measures.md).

-   **Tiến trình hoạt động:** Hiển thị nếu bạn đã định cấu hình các hoạt động. Chế độ xem dòng thời gian chứa các hoạt động được sắp xếp theo thứ tự thời gian của khách hàng này, bắt đầu với hoạt động gần đây nhất. Để biết thêm thông tin, hãy xem [Hoạt động của khách hàng](activities.md).

Chọn **Quay lại khách hàng** để quay lại trang tìm kiếm của khách hàng.

## <a name="next-steps"></a>Các bước tiếp theo

[Thêm nhiều nguồn dữ liệu](data-sources.md) hoặc [tạo phân khúc khách hàng](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]