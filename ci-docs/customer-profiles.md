---
title: Xem hồ sơ khách hàng
description: Xem dữ liệu khách hàng hợp nhất của bạn bao gồm cả việc sử dụng tìm kiếm và bộ lọc
ms.date: 06/08/2022
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
ms.openlocfilehash: 0c8edfd8f45ce7770d568811df2b38be1b04e73a
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303809"
---
# <a name="view-customer-profiles"></a>Xem hồ sơ khách hàng

Hồ sơ khách hàng có sẵn sau khi bạn [tạo ra sự thống nhất *khách hàng* thực thể](data-unification.md). Chế độ xem kết hợp của hồ sơ khách hàng hợp nhất của bạn hiển thị trên **Khách hàng** trang. Khách hàng có thể là cá nhân hoặc tổ chức.

Đi đến **Khách hàng** trang để xem khách hàng của bạn và hồ sơ của họ. Mỗi hồ sơ khách hàng được thể hiện bằng một ô. Sử dụng các điều khiển phân trang để nhận được nhiều bản ghi hơn. Thẻ hiển thị các trường từ thực thể *Khách hàng* như được định nghĩa trong **Tìm kiếm và lọc chỉ mục**. Thứ tự của các trường trong mỗi thẻ do hệ thống chọn.

> [!NOTE]
> Nếu bạn không thể nhìn thấy các ô khi bạn chọn **Khách hàng**, quản trị viên của bạn cần [xác định ít nhất một thuộc tính có thể tìm kiếm](search-filter-index.md) bên trong **Tìm kiếm & lọc chỉ mục**.

:::image type="content" source="media/customers-page-result-tiles-B2C.png" alt-text="Trang khách hàng hiển thị các ô kết quả.":::

Chọn bất kỳ hành động nào sau đây:
- [Xem chi tiết khách hàng](#view-customer-details)
- [Quản lý chỉ mục tìm kiếm và lọc](search-filter-index.md) (chỉ dành cho quản trị viên)
- [Lọc khách hàng](#filter-customers)
- **Mở rộng thẻ** hoặc **Thu gọn thẻ** để mở rộng hoặc thu gọn thông tin được hiển thị trên ô khách hàng
- **Sắp xếp theo** một thuộc tính cụ thể
- [Tìm kiếm khách hàng](#search-for-customers)

  > [!NOTE]
  > Để sử dụng tìm kiếm và bộ lọc, quản trị viên phải định cấu hình các thuộc tính có thể tìm kiếm và xác định các trường có thể lọc bằng chỉ mục tìm kiếm & bộ lọc.

## <a name="search-for-customers"></a>Tìm kiếm khách hàng

Tìm kiếm khách hàng bằng cách nhập tên hoặc một số thuộc tính khác vào **Tìm kiếm khách hàng**. Các thuộc tính có thể tìm kiếm được do quản trị viên xác định và đến từ các thuộc tính hợp nhất *khách hàng* thực thể.

> [!NOTE]
> **Sợi dây** là kiểu dữ liệu duy nhất được đưa vào tìm kiếm. Sử dụng nó trong **Tìm kiếm khách hàng** trên trang Khách hàng để tìm kiếm khách hàng.

## <a name="filter-customers"></a>Lọc khách hàng

Lọc khách hàng theo *khách hàng* các trường thực thể. Các trường có thể lọc được xác định bởi quản trị viên.

1. Trên **Khách hàng** trang, chọn **Hiển thị bộ lọc**. Ngăn Bộ lọc hiển thị.

1. Chọn các hộp bên cạnh các thuộc tính bạn muốn lọc khách hàng.

1. Xóa tất cả các bộ lọc bằng cách chọn **Xóa bộ lọc** hoặc xóa hộp kiểm bên cạnh thuộc tính đã chọn.

1. Lựa chọn **Ẩn bộ lọc** để đóng ngăn bộ lọc.

1. Để lưu kết quả bộ lọc dưới dạng [bộ phận](segments.md), lựa chọn **Lưu bộ lọc dưới dạng phân đoạn**.
   1. Nhập tên cho phân đoạn.
   1. Lựa chọn **Tiết kiệm** để lưu phân đoạn.
   1. Chọn có chạy phân đoạn ngay bây giờ hay không bằng cách chọn **Hoạt động** hoặc chạy nó **Sau**.

## <a name="view-customer-details"></a>Xem chi tiết khách hàng

Trên **Khách hàng** trang, chọn một ô khách hàng để xem chi tiết cho khách hàng đã chọn.

:::image type="content" source="media/customers-details-B2C.png" alt-text="Trang chi tiết khách hàng.":::

Thông tin chi tiết về khách hàng bao gồm:

**Ô hồ sơ khách hàng** hiển thị các giá trị khác với giá trị hợp nhất *khách hàng* thực thể. Nếu một trường không có giá trị cho hồ sơ khách hàng đã chọn, nó sẽ không hiển thị ngoại trừ trường địa chỉ. Ô được cấu trúc thành các phần:

- Phần đầu tiên hiển thị một tập hợp các trường được xác định trước, theo sau là tất cả các trường là một phần của tìm kiếm và lọc chỉ mục. Tất cả các trường liên quan đến địa chỉ được kết hợp thành một dòng duy nhất, hiển thị ngay cả khi hồ sơ không chứa thông tin địa chỉ.
- **Địa chỉ liên hệ cho khách hàng này** hiển thị trong môi trường dành cho tài khoản doanh nghiệp (B-to-B). Mỗi liên hệ được hiển thị với các trường của họ. Các trường trống bị ẩn.
- **Các trường bổ sung** hiển thị các trường còn lại của khách hàng đã chọn, ngoại trừ ID.
- **ID** liệt kê tất cả các ID dưới tên thực thể tương ứng của chúng. Các trường được xác định là ID theo ngữ nghĩa của chúng.

**Dòng thời gian hoạt động** hiển thị dữ liệu nếu bạn đã định cấu hình [các hoạt động](activities.md). Chế độ xem dòng thời gian chứa các hoạt động được sắp xếp theo thứ tự thời gian của khách hàng đã chọn, bắt đầu với hoạt động gần đây nhất.

**Thông tin chuyên sâu**:

- **Đo** hiển thị nếu bạn đã cấu hình [các biện pháp thuộc tính khách hàng](measures.md). Chúng bao gồm các KPI được tính toán xung quanh khách hàng của bạn ở cấp độ khách hàng cá nhân.

- **Sở thích tiềm năng, thương hiệu tiềm năng** hiển thị nếu bạn đã định cấu hình [làm giàu thương hiệu hoặc sở thích](enrichment-microsoft.md). Nó thể hiện sở thích và mối quan hệ tiềm năng đối với thương hiệu dựa trên những khách hàng khác có hồ sơ tương tự với hồ sơ khách hàng đã chọn.

Để trở lại **Khách hàng** trang, chọn **Quay lại khách hàng**.

## <a name="next-steps"></a>Các bước tiếp theo

[Thêm nhiều nguồn dữ liệu hơn](data-sources.md), [làm phong phú hồ sơ hợp nhất](enrichment-hub.md) hoặc [tạo phân đoạn](segments.md) để làm việc với hồ sơ khách hàng thống nhất trong các ứng dụng khác.

[!INCLUDE [footer-include](includes/footer-banner.md)]
