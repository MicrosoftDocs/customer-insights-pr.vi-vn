---
title: Trình kết nối Power Apps (xem trước)
description: Kết nối với Power Apps và Power Automate.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 8807e82e65ea20d1a7f7dc07552229f377927eed
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196926"
---
# <a name="power-apps-connector-preview"></a>Trình kết nối Power Apps (xem trước)

Đưa hồ sơ khách hàng hợp nhất vào các ứng dụng được cá nhân hóa của bạn với Microsoft Power Apps.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Kết nối Power Apps và Dynamics 365 Customer Insights

Customer Insights là một trong số nhiều [nguồn có sẵn cho dữ liệu trong Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).

Tham khảo tài liệu Power Apps để tìm hiểu cách [thêm kết nối dữ liệu tới ứng dụng](/powerapps/maker/canvas-apps/add-data-connection). Ngoài ra, bạn nên xem [cách Power Apps sử dụng đại diện để xử lý tập dữ liệu lớn trong ứng dụng Canvas](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="available-entities"></a>Các thực thể sẵn có

Sau khi thêm Thông tin chi tiết về khách hàng làm kết nối dữ liệu, hãy chọn các thực thể sau trong Power Apps:

- **Khách hàng**: để sử dụng dữ liệu từ [hồ sơ khách hàng hợp nhất](customer-profiles.md).
- **UnifiedActivity**: để hiển thị [dòng thời gian hoạt động](activities.md) trong ứng dụng.
- **ContactProfile**: để hiển thị danh bạ của khách hàng. Thực thể này chỉ khả dụng trong môi trường Thông tin chi tiết về khách hàng cho tài khoản doanh nghiệp.

## <a name="limitations"></a>Giới hạn

### <a name="retrievable-entities"></a>Các thực thể có thể truy xuất

Bạn chỉ có thể truy xuất các thực thể **Khách hàng**, **UnifiedActivity**, **Phân khúc** và **ContactProfile** thông qua trình kết nối Power Apps. ContactProfile chỉ khả dụng trong môi trường Customer Insights cho tài khoản doanh nghiệp. Các thực thể khác được hiển thị vì trình kết nối cơ bản hỗ trợ chúng thông qua trình kích hoạt trong Power Automate.

Bạn có thể thực hiện tối đa 100 cuộc gọi mỗi 60 giây. Bạn có thể gọi điểm cuối API nhiều lần bằng cách sử dụng tham số $ bỏ qua. [Tìm hiểu thêm về thông số $ bỏ qua](/connectors/customerinsights/#get-items-from-an-entity).

### <a name="delegation"></a>Đại diện

Ủy quyền hoạt động cho thực thể **Khách hàng** và thực thể **UnifiedActivity**.

- Ủy quyền cho **khách hàng** entity: Để sử dụng ủy quyền cho thực thể này, các trường cần được lập chỉ mục trong [tìm kiếm & chỉ mục lọc](search-filter-index.md).  
- Ủy quyền cho **UnifiedActivity**: Ủy quyền cho thực thể này chỉ hoạt động cho các trường **ActivityId** và **CustomerId**.  
- Ủy quyền cho **ContactProfile**: Ủy quyền cho thực thể này chỉ hoạt động cho các trường **ContactId** và **CustomerId**. ContactProfile chỉ khả dụng trong môi trường Customer Insights cho tài khoản doanh nghiệp.

Để biết thêm thông tin về ủy quyền, hãy truy cập [Chức năng và hoạt động có thể ủy quyền của Power Apps](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="example-gallery-control"></a>Kiểm soát thư viện ví dụ

Theo tùy chọn, thêm hồ sơ khách hàng vào [kiểm soát thư viện](/powerapps/maker/canvas-apps/add-gallery).

1. Thêm điều khiển **thư viện** vào ứng dụng bạn đang xây dựng.
  
   :::image type="content" source="media/connector-powerapps9.png" alt-text="Thêm một thành phần thư viện.":::

1. Chọn **Khách hàng** làm nguồn dữ liệu cho các mặt hàng.

   :::image type="content" source="media/choose-datasource-powerapps.png" alt-text="Chọn nguồn dữ liệu.":::

1. Thay đổi bảng dữ liệu ở bên phải để chọn trường cho thực thể Khách hàng hiển thị trên thư viện.

1. Nếu bạn muốn hiển thị bất kỳ trường nào từ khách hàng đã chọn trên thư viện, hãy điền vào thuộc tính **Văn bản** của nhãn bằng cách sử dụng **{Name_of_the_gallery}.Đã chọn.{property_name}**  
    - Ví dụ: _Gallery1.Selected.address1_city_

1. Để hiển thị dòng thời gian hợp nhất cho khách hàng, hãy thêm phần tử thư viện và thêm thuộc tính **Mục** bằng cách dùng **Bộ lọc('UnifiedActivity', CustomerId = {Customer_Id})**  
    - Ví dụ: _Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)_

[!INCLUDE [footer-include](includes/footer-banner.md)]
