---
title: Trình kết nối Power Apps
description: Kết nối với Power Apps và Power Automate.
ms.date: 10/01/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: ae2a3b7c05e9ed860da31853c47af2aec8634e7a
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 02/16/2022
ms.locfileid: "8229058"
---
# <a name="microsoft-power-apps-connector-preview"></a>Trình kết nối Microsoft Power Apps (xem trước)

Đưa hồ sơ khách hàng hợp nhất vào các ứng dụng được cá nhân hóa của bạn với Power Apps.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Kết nối Power Apps và Dynamics 365 Customer Insights

Customer Insights là một trong số nhiều [nguồn có sẵn cho dữ liệu trong Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).

Tham khảo tài liệu Power Apps để tìm hiểu cách [thêm kết nối dữ liệu tới ứng dụng](/powerapps/maker/canvas-apps/add-data-connection). Ngoài ra, bạn nên xem [cách Power Apps sử dụng đại diện để xử lý tập dữ liệu lớn trong ứng dụng Canvas](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="available-entities"></a>Các thực thể sẵn có

Sau khi thêm Customer Insights làm kết nối dữ liệu, bạn có thể chọn các thực thể sau trong Power Apps:

- **Khách hàng**: để sử dụng dữ liệu từ [hồ sơ khách hàng hợp nhất](customer-profiles.md).
- **UnifiedActivity**: để hiển thị [dòng thời gian hoạt động](activities.md) trong ứng dụng.
- **ContactProfile**: để hiển thị danh bạ của khách hàng. Thực thể này chỉ có sẵn trong môi trường thông tin chuyên sâu về đối tượng cho tài khoản doanh nghiệp.

## <a name="limitations"></a>Giới hạn

### <a name="retrievable-entities"></a>Các thực thể có thể truy xuất

Bạn chỉ có thể truy xuất các thực thể **Khách hàng**, **UnifiedActivity**, **Phân khúc** và **ContactProfile** thông qua trình kết nối Power Apps. ContactProfile chỉ có sẵn trong phiên bản thông tin chuyên sâu về đối tượng cho tài khoản doanh nghiệp. Các thực thể khác được hiển thị vì trình kết nối cơ bản hỗ trợ chúng thông qua trình kích hoạt trong Power Automate.

### <a name="delegation"></a>Đại diện

Ủy quyền hoạt động cho thực thể **Khách hàng** và thực thể **UnifiedActivity**. 

- Ủy quyền cho thực thể **Khách hàng**: Để sử dụng ủy quyền cho thực thể này, cần lập chỉ mục các trường trong [Chỉ mục tìm kiếm và lọc](search-filter-index.md).  
- Ủy quyền cho **UnifiedActivity**: Ủy quyền cho thực thể này chỉ hoạt động cho các trường **ActivityId** và **CustomerId**.  
- Ủy quyền cho **ContactProfile**: Ủy quyền cho thực thể này chỉ hoạt động cho các trường **ContactId** và **CustomerId**. ContactProfile chỉ có sẵn trong môi trường thông tin chuyên sâu về đối tượng cho tài khoản doanh nghiệp.

Để biết thêm thông tin về ủy quyền, hãy truy cập [Chức năng và hoạt động có thể ủy quyền của Power Apps](/powerapps/maker/canvas-apps/delegation-overview). 

## <a name="example-gallery-control"></a>Kiểm soát thư viện ví dụ

Bạn có thể thêm hồ sơ khách hàng vào [điều khiển thư viện](/powerapps/maker/canvas-apps/add-gallery).

1. Thêm điều khiển **thư viện** vào ứng dụng bạn đang xây dựng.

    > [!div class="mx-imgBorder"]
    > ![Thêm một thành phần thư viện.](media/connector-powerapps9.png "Thêm một thành phần thư viện.")

2. Chọn **Khách hàng** làm nguồn dữ liệu cho các mặt hàng.

    > [!div class="mx-imgBorder"]
    > ![Chọn nguồn dữ liệu.](media/choose-datasource-powerapps.png "Chọn nguồn dữ liệu.")

3. Bạn có thể thay đổi bảng dữ liệu ở bên phải để chọn trường cho thực thể Khách hàng hiển thị trên thư viện.

4. Nếu bạn muốn hiển thị bất kỳ trường nào từ khách hàng đã chọn trên thư viện, hãy điền vào thuộc tính **Văn bản** của nhãn bằng cách sử dụng **{Name_of_the_gallery}.Đã chọn.{property_name}**  
    - Ví dụ: _Gallery1.Selected.address1_city_

5. Để hiển thị dòng thời gian hợp nhất cho khách hàng, hãy thêm phần tử thư viện và thêm thuộc tính **Mục** bằng cách dùng **Bộ lọc('UnifiedActivity', CustomerId = {Customer_Id})**  
    - Ví dụ: _Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)_


[!INCLUDE[footer-include](../includes/footer-banner.md)]
