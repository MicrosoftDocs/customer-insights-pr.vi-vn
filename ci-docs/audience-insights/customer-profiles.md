---
title: Xem hồ sơ khách hàng
description: Nhận thông tin kết hợp về dữ liệu khách hàng hợp nhất của bạn.
ms.date: 09/30/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
searchScope:
- ci-customers-page
- ci-customer-card
- ci-activities
- ci-activities-wizard
- customerInsights
ms.openlocfilehash: 074d84eff65d52b083fff6c161282d4fafa1af85
ms.sourcegitcommit: 5bd07f3a1288f003704acd576741cf6aedc1ac33
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 03/31/2022
ms.locfileid: "8523763"
---
# <a name="customer-profiles"></a>Hồ sơ khách hàng

Trang **Khách hàng** hiển thị chế độ xem tổng hợp về hồ sơ khách hàng hợp nhất của bạn. Hồ sơ khách hàng có sẵn sau khi bạn [đã tạo thực thể Khách hàng hợp nhất](data-unification.md). Trang cho phép bạn tìm kiếm khách hàng và xác định chỉ mục cho tìm kiếm đó.

Khách hàng có thể là cá nhân hoặc tổ chức. Mỗi hồ sơ khách hàng được thể hiện bằng một ô. Sử dụng các điều khiển phân trang để nhận được nhiều bản ghi hơn. Thẻ hiển thị các trường từ thực thể *Khách hàng* như được định nghĩa trong **Tìm kiếm và lọc chỉ mục**. Thứ tự của các trường trong mỗi thẻ do hệ thống chọn.

Chọn một ô để xem dữ liệu cho khách hàng đã chọn trong một trang dành riêng được gọi là [Trang chi tiết khách hàng](customer-profiles.md#customer-details-page).

> [!div class="mx-imgBorder"] 
> ![Trang khách hàng hiển thị các ô kết quả](media/customers-page-result-tiles-B2C.png "Trang khách hàng hiển thị các ô kết quả")

> [!NOTE]
> Nếu bạn không thể nhìn thấy các ô khi bạn chọn **Khách hàng** trong điều hướng, quản trị viên của bạn cần [xác định ít nhất một thuộc tính có thể tìm kiếm](search-filter-index.md) trong **Tìm kiếm và lọc chỉ mục**.

## <a name="search-for-customers"></a>Tìm kiếm khách hàng

Tìm kiếm khách hàng bằng cách nhập tên hoặc một số thuộc tính khác vào hộp tìm kiếm. Tìm kiếm chỉ hoạt động trong thực thể _Khách hàng_ được tạo trong quá trình hợp nhất dữ liệu.

Là quản trị viên, bạn có thể định cấu hình các thuộc tính có thể tìm kiếm bằng cách sử dụng trang **Tìm kiếm và lọc chỉ mục**. Để biết thêm thông tin, hãy truy cập [Quản lý tìm kiếm và lọc chỉ mục](search-filter-index.md).

## <a name="filter-customers"></a>Lọc khách hàng

Bạn có thể lọc khách hàng theo các trường thực thể _Khách hàng_. Tương tự như tìm kiếm, trước tiên, quản trị viên của bạn sẽ cần xác định các trường là có thể lọc bằng cách sử dụng trang **Tìm kiếm và lọc chỉ mục**.

1. Chọn **Hiện bộ lọc** trên trang **Khách hàng**.

1. Chọn các hộp bên cạnh các thuộc tính bạn muốn lọc khách hàng.

1. Xóa bộ lọc của bạn bằng cách chọn **Xóa bộ lọc** trên trang **Khách hàng**.

## <a name="customer-details-page"></a>Trang thông tin chi tiết về khách hàng

Chọn bất kỳ ngăn xếp khách hàng nào để mở **Trang thông tin chi tiết về khách hàng**. Chế độ xem này chứa thông tin hợp nhất cho khách hàng đã chọn. Thông tin chi tiết về khách hàng bao gồm các nội dung sau:

**Ô hồ sơ khách hàng**: Ô này hiển thị các giá trị khác với thực thể hợp nhất _Khách hàng_. Nếu một trường không có giá trị cho hồ sơ khách hàng đã chọn, trường đó sẽ không hiển thị. Ô được cấu trúc thành các phần:  
  - Phần đầu tiên hiển thị một tập hợp các trường được xác định trước, theo sau là tất cả các trường là một phần của tìm kiếm và lọc chỉ mục. Tất cả các trường liên quan đến địa chỉ được kết hợp thành một dòng nếu hồ sơ có chứa các trường như vậy. 
  - **Liên hệ cho khách hàng này**: Trong môi trường dành cho tài khoản doanh nghiệp, bạn sẽ thấy tất cả các liên hệ có liên quan cho khách hàng này dưới dạng phần thứ hai. Mỗi liên hệ được hiển thị với các trường của họ. Các trường trống bị ẩn.
  - **Các trường bổ sung**: Hiển thị các trường còn lại của khách hàng đã chọn, ngoại trừ ID. 
  - **ID**: Liệt kê tất cả các ID dưới tên thực thể tương ứng của chúng. Các trường được xác định là ID theo ngữ nghĩa của chúng, phân loại chúng như vậy.

**Dòng thời gian hoạt động**: Hiển thị dữ liệu nếu bạn đã đặt cấu hình các hoạt động. Chế độ xem dòng thời gian chứa các hoạt động được sắp xếp theo thứ tự thời gian của khách hàng đã chọn, bắt đầu với hoạt động gần đây nhất. Để biết thêm thông tin, hãy truy cập [Hoạt động khách hàng](activities.md).

**Thông tin chuyên sâu**:  
  - **Đo lường**: Hiển thị nếu bạn đã đặt cấu hình một hoặc nhiều biện pháp đo lường thuộc tính khách hàng. Chúng bao gồm các KPI được tính toán xung quanh khách hàng của bạn ở cấp độ khách hàng cá nhân. Để biết thêm thông tin, hãy truy cập [Xác định và quản lý các biện pháp](measures.md).

  - **Sở thích tiềm năng, thương hiệu tiềm năng**: Hiển thị nếu bạn đã đặt cấu hình tăng cường mối quan hệ sở thích hoặc thương hiệu. Nó thể hiện sở thích và mối quan hệ tiềm năng đối với thương hiệu dựa trên những khách hàng khác có hồ sơ tương tự với hồ sơ khách hàng đã chọn. Để biết thêm thông tin, hãy truy cập [Làm phong phú hồ sơ khách hàng với mối quan hệ thương hiệu và sở thích](enrichment-microsoft.md).

Để quay lại trang tìm kiếm của khách hàng, hãy chọn **Quay lại khách hàng**.

## <a name="next-steps"></a>Các bước tiếp theo

[Thêm nhiều nguồn dữ liệu hơn](data-sources.md), [làm phong phú hồ sơ hợp nhất](enrichment-hub.md) hoặc [tạo phân đoạn](segments.md) để làm việc với hồ sơ khách hàng thống nhất trong các ứng dụng khác.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
