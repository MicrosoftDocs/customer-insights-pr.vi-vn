---
title: Sử dụng phân đoạn thông tin chi tiết về đối tượng để lọc báo cáo thông tin chi tiết về mức độ tương tác
description: Sử dụng phân đoạn thông tin chi tiết về đối tượng trong các phân tích tương tác về dữ liệu hành vi được thu thập bởi thông tin chi tiết về mức độ tương tác trên trang web của khách hàng.
ms.date: 07/27/2021
ms.service: customer-insights
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: bdd5641bb17384725491f22f70ae967ad90b1696
ms.sourcegitcommit: 1c396394470df8e68c2fafe3106567536ff87194
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 08/30/2021
ms.locfileid: "7461084"
---
# <a name="use-audience-insights-segments-to-filter-engagement-insights-reports"></a>Sử dụng phân đoạn thông tin chi tiết về đối tượng để lọc báo cáo thông tin chi tiết về mức độ tương tác

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Với thông tin chi tiết về mức độ tương tác, bạn có thể sử dụng phân đoạn thông tin chi tiết về đối tượng trong các phân tích tương tác về dữ liệu hành vi được thu thập bởi thông tin chi tiết về mức độ tương tác trên trang web của bạn.

## <a name="prerequisite"></a>Điều kiện tiên quyết

- Môi trường thông tin chi tiết về mức độ tương tác trong đó bạn có dữ liệu phân đoạn thông tin chi tiết về đối tượng được liên kết với môi trường thông tin chi tiết về đối tượng nơi hồ sơ khách hàng và phân đoạn được tạo. Thông tin thêm: [Tạo mối liên kết giữa thông tin chi tiết về đối tượng và thông tin chi tiết về mức độ tương tác](integrate-audience-insights-engagement-insights.md)

## <a name="create-audience-insights-segments"></a>Tạo phân đoạn thông tin chi tiết về đối tượng 

> [!IMPORTANT]
> Để phân đoạn thông tin chi tiết về đối tượng hiển thị trong thông tin chi tiết về mức độ tương tác, trước tiên bạn phải [chạy các quy trình hợp nhất và xuôi dòng](../audience-insights/merge-entities.md). Các quy trình xuôi dòng rất quan trọng vì chúng tạo ra một bảng duy nhất chuẩn bị cho các phân đoạn thông tin chi tiết về đối tượng được chia sẻ với thông tin chi tiết về mức độ tương tác. (Nếu quá trình làm mới hệ thống được lên lịch, nó sẽ tự động bao gồm các quy trình xuôi dòng.)

Bạn có thể sử dụng các phân đoạn thông tin chi tiết về đối tượng trong báo cáo có sẵn thông tin chi tiết về đối tượng hoặc báo cáo tùy chỉnh mà bạn đã tạo. Để biết thêm thông tin, hãy truy cập [Báo cáo hồ sơ có sẵn](profile-reports.md) và [Tạo và chỉnh sửa các báo cáo tùy chỉnh](custom-reports.md).

**Để sử dụng phân đoạn thông tin chi tiết về đối tượng trong báo cáo thông tin chi tiết về mức độ tương tác**

1. Từ trang **Không gian làm việc**, chọn **Dữ liệu**, sau đó chọn tab **Phân đoạn**.

    :::image type="content" source="media/integrate-audience-insights-segments1.png" alt-text="Chọn tab Phân đoạn.":::

   >[!NOTE]
   > Việc chọn phân đoạn thông tin chi tiết về đối tượng sẽ đưa bạn đến thông tin chi tiết về đối tượng, nơi bạn có thể tìm hiểu cách phân đoạn đó được tạo theo các quy tắc và logic. Để biết thêm thông tin về phân khúc thông tin chi tiết về đối tượng, hãy truy cập [Xem và tạo các phân khúc](../audience-insights/segments.md).

2. Chọn một báo cáo có sẵn hoặc [tạo một báo cáo tùy chỉnh](custom-reports.md), sau đó chọn **Thêm điều kiện**. (Đối với ví dụ này, chúng tôi đã chọn báo cáo **Số lượt xem trang**.)

    :::image type="content" source="media/integrate-audience-insights-segments2.png" alt-text="Thêm điều kiện.":::

3. Chọn **Lọc theo phân khúc**, mở rộng danh sách **Loại phân khúc**, sau đó chọn **Nhân khẩu học**.

    :::image type="content" source="media/integrate-audience-insights-segments3.png" alt-text="Chọn loại phân khúc Nhân khẩu học.":::

4. Mở rộng danh sách **Tên phân khúc**, sau đó chọn phân khúc thông tin chi tiết về đối tượng.

    :::image type="content" source="media/integrate-audience-insights-segments4.png" alt-text="Chọn một phân khúc.":::

5. Bạn có thể áp dụng một hoặc nhiều phân khúc, bao gồm phân khúc hành vi (thông tin chi tiết về mức độ tương tác) và nhân khẩu học (thông tin chi tiết về đối tượng). 

    :::image type="content" source="media/integrate-audience-insights-segments6.png" alt-text="Báo cáo lượt xem trang bị hạn chế đối với khách hàng Hoa Kỳ và phân khúc Trang chủ.":::

Trong hình ảnh trước, các phân khúc **Khách hàng Hoa Kỳ** và **Trang chủ** đã được chọn, điều này hạn chế báo cáo **Số lượt xem trang** để chỉ hiển thị hai phân khúc đó. 


>[!NOTE]
> Bạn có thể sử dụng các phân khúc thông tin chi tiết về đối tượng để lọc báo cáo có sẵn, báo cáo tùy chỉnh và phễu trong thông tin chi tiết về mức độ tương tác. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]