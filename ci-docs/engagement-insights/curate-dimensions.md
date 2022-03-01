---
title: Sử dụng thứ nguyên nhân khẩu học để phân chia dữ liệu hành vi (thứ nguyên được sắp xếp)
description: Sử dụng các thứ nguyên được sắp xếp theo hồ sơ thống nhất để cho phép đối tượng hiểu rõ các thuộc tính hồ sơ khách hàng.
ms.date: 07/27/2021
ms.service: customer-insights
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 50bb800c9e097d03cc6f26f79819c741ab5e8baf
ms.sourcegitcommit: 1c396394470df8e68c2fafe3106567536ff87194
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 08/30/2021
ms.locfileid: "7461129"
---
# <a name="use-demographic-dimensions-for-splitting-behavioral-data"></a>Sử dụng thứ nguyên nhân khẩu học để phân chia dữ liệu hành vi

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Bằng cách sử dụng các thứ nguyên nhân khẩu học hồ sơ thống nhất, người dùng thông tin chi tiết về mức độ tương tác có thể truy cập các thuộc tính hồ sơ thông tin chi tiết về đối tượng. Sau đó, bạn có thể sử dụng các thuộc tính này trong các phân tích tương tác về dữ liệu hành vi, bao gồm cả dữ liệu được thu thập bởi thông tin chi tiết về mức độ tương tác trên trang web hoặc ứng dụng dành cho thiết bị di động của bạn.

>[!NOTE]
> Thông tin chuyên sâu về tương tác bao gồm các thứ nguyên có sẵn cho các thuộc tính sự kiện. Thông tin thêm: [Xem và tạo thứ nguyên](dimensions.md)

## <a name="prerequisite"></a>Điều kiện tiên quyết

- Môi trường thông tin chi tiết về mức độ tương tác trong đó bạn có dữ liệu hồ sơ khách hàng được liên kết với môi trường thông tin chi tiết về đối tượng nơi hồ sơ khách hàng được tạo. Thông tin thêm: [Tạo mối liên kết giữa thông tin chi tiết về đối tượng và thông tin chi tiết về mức độ tương tác](integrate-audience-insights-engagement-insights.md)

> [!NOTE]
> Sau khi bạn tạo liên kết giữa môi trường thông tin chi tiết về đối tượng và thông tin chi tiết về mức độ tương tác, bạn có thể chỉ muốn dữ liệu cụ thể cho các thuộc tính hồ sơ khách hàng, dữ liệu này có thể hữu ích như là thứ nguyên trong thông tin chi tiết về mức độ tương tác. Để biết thêm thông tin, hãy truy cập [Bật các phân đoạn và thuộc tính hồ sơ hợp nhất thông tin chi tiết về đối tượng](integrate-audience-insights-engagement-insights.md#enable-audience-insights-unified-profiles-attributes-and-segments).<!--note from editor: Suggested. -->

## <a name="create-a-new-custom-report"></a>Tạo một báo cáo tùy chỉnh mới

1. Trên ngăn bên trái, hãy chọn **Tùy chỉnh** > **Báo cáo mới**, rồi chọn số liệu bạn muốn. (Đối với ví dụ này, chúng tôi đã chọn **Số lượt xem trang theo giờ**.)

    :::image type="content" source="media/curated-dimensions1.png" alt-text="Chọn một số liệu.":::

2. Trong trình chỉnh sửa Trực quan hóa, hãy chọn **Kích thước**, sau đó chọn **Nhân khẩu học** trong menu thả xuống **Loại kích thước**.

    :::image type="content" source="media/curated-dimensions2.png" alt-text="Chọn nhân khẩu học.":::

3. Chọn kích thước **Signal.Customer.*xxx***. (Ví dụ này hiển thị Signal.Customer.Country.)

    :::image type="content" source="media/curated-dimensions3.png" alt-text="Chọn kích thước.":::
  
## <a name="limitations"></a>Giới hạn

Hiện tại, bạn chỉ có thể sử dụng thứ nguyên nhân khẩu học để phân chia dữ liệu hành vi.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
