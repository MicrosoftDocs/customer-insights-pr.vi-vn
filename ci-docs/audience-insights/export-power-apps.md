---
title: Trình kết nối Power Apps
description: Kết nối với Power Apps và Power Automate.
ms.date: 01/19/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: fc0af656cd5b436d9efd65b2a2c75dde9c9deb9dbcdd56ffc6a960f5878a631f
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 08/10/2021
ms.locfileid: "7031821"
---
# <a name="microsoft-power-apps-connector-preview"></a>Trình kết nối Microsoft Power Apps (xem trước)

Đưa hồ sơ khách hàng hợp nhất vào các ứng dụng được cá nhân hóa của bạn với Power Apps.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Kết nối Power Apps và Dynamics 365 Customer Insights

Customer Insights là một trong số nhiều [nguồn có sẵn cho dữ liệu trong Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).

Tham khảo tài liệu Power Apps để tìm hiểu cách [thêm kết nối dữ liệu tới ứng dụng](/powerapps/maker/canvas-apps/add-data-connection). Ngoài ra, bạn nên xem [cách Power Apps sử dụng đại diện để xử lý tập dữ liệu lớn trong ứng dụng Canvas](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="available-entities"></a>Các thực thể sẵn có

Sau khi thêm Customer Insights làm kết nối dữ liệu, bạn có thể chọn các thực thể sau trong Power Apps:

- Khách hàng: để sử dụng dữ liệu từ [hồ sơ khách hàng hợp nhất](customer-profiles.md).
- UnifiedActivity: để hiển thị [dòng thời gian hoạt động](activities.md) trên ứng dụng.

## <a name="limitations"></a>Giới hạn

### <a name="retrievable-entities"></a>Các thực thể có thể truy xuất

Bạn chỉ có thể truy xuất các thực thể **Khách hàng**, **UnifiedActivity** và **Phân khúc** thông qua trình kết nối Power Apps. Các thực thể khác được hiển thị vì trình kết nối cơ bản hỗ trợ chúng thông qua trình kích hoạt trong Power Automate.  

### <a name="delegation"></a>Đại diện

Ủy quyền hoạt động cho thực thể Khách hàng và thực thể UnifiedActivity. 

- Ủy quyền cho thực thể **Khách hàng**: Để sử dụng ủy quyền cho thực thể này, cần lập chỉ mục các trường trong [Chỉ mục tìm kiếm và lọc](search-filter-index.md).  

- Ủy quyền cho **UnifiedActivity**: Ủy quyền cho thực thể này chỉ hoạt động cho các trường **ActivityId** và **CustomerId**.  

- Để biết thêm thông tin về ủy quyền, hãy xem [Hoạt động và các chức năng có thể ủy quyền Power Apps](/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps). 

## <a name="example-gallery-control"></a>Kiểm soát thư viện ví dụ

Ví dụ: bạn thêm hồ sơ khách hàng vào [kiểm soát thư viện](/powerapps/maker/canvas-apps/add-gallery).

1. Thêm một kiểm soát **Thư viện** vào ứng dụng bạn đang xây dựng.

> [!div class="mx-imgBorder"]
> ![Thêm một thành phần thư viện.](media/connector-powerapps9.png "Thêm một thành phần thư viện")

1. Chọn **Khách hàng** làm nguồn dữ liệu cho các mặt hàng.

    > [!div class="mx-imgBorder"]
    > ![Chọn nguồn dữ liệu.](media/choose-datasource-powerapps.png "Chọn nguồn dữ liệu")

1. Bạn có thể thay đổi bảng dữ liệu ở bên phải để chọn trường cho thực thể Khách hàng hiển thị trên thư viện.

1. Nếu bạn muốn hiển thị bất kỳ trường nào từ khách hàng đã chọn trên thư viện, hãy điền vào thuộc tính Văn bản của nhãn: **{Name_of_the_gallery}.Đã chọn.{property_name}**

    Ví dụ: Gallery1.Selected.address1_city

1. Để hiển thị dòng thời gian hợp nhất cho khách hàng, hãy thêm phần tử Thư viện và thuộc tính Items: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**

    Ví dụ: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)


[!INCLUDE[footer-include](../includes/footer-banner.md)]