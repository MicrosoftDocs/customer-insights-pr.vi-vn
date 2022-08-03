---
title: Xem xét hợp nhất dữ liệu
description: Xem lại các bước hợp nhất dữ liệu, tạo hồ sơ khách hàng hợp nhất và xem xét kết quả
ms.date: 06/02/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: adkuppa
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: 20728ffaef9bb705410b3ac22d19868ffd5d1243
ms.sourcegitcommit: 3c5b0b40b2b45e420015bbdd228ce0e610245e6f
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 07/12/2022
ms.locfileid: "9139610"
---
# <a name="review-data-unification"></a>Xem xét hợp nhất dữ liệu

Bước cuối cùng trong quy trình hợp nhất này hiển thị tóm tắt các bước trong quy trình và cung cấp cơ hội thực hiện các thay đổi trước khi bạn tạo hồ sơ hợp nhất.

:::image type="content" source="media/m3_review.png" alt-text="Ảnh chụp màn hình Đánh giá và Tạo hồ sơ khách hàng.":::

## <a name="review-the-data-unification-steps"></a>Xem lại các bước hợp nhất dữ liệu

1. Lựa chọn **Chỉnh sửa** về bất kỳ bước hợp nhất dữ liệu nào để xem xét và thực hiện bất kỳ thay đổi nào.

1. Nếu bạn hài lòng với lựa chọn của mình, hãy chọn **Tạo hồ sơ khách hàng**. Các **Thống nhất** trang hiển thị trong khi hồ sơ khách hàng hợp nhất đang được tạo. Tất cả các ô ngoại trừ **Các trường nguồn** buổi bieu diễn **Đã xếp hàng** hoặc **Làm mới** trạng thái.

   :::image type="content" source="media/m3_unify_refreshing.png" alt-text="Ảnh chụp màn hình của trang Unify với các ô hiển thị Đã xếp hàng hoặc Đang làm mới.":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Thuật toán hợp nhất cần một thời gian để hoàn thành và bạn không thể thay đổi cấu hình cho đến khi hoàn tất. Khi quá trình hợp nhất hoàn tất, thực thể hồ sơ khách hàng hợp nhất, được gọi là *khách hàng*, được liệt kê trên **Thực thể** trang trong **Hồ sơ** tiết diện. Lần chạy hợp nhất thành công đầu tiên tạo ra sự hợp nhất *khách hàng* thực thể. Tất cả các lần chạy tiếp theo sẽ mở rộng thực thể đó.

## <a name="review-the-results-of-data-unification"></a>Xem lại kết quả của việc hợp nhất dữ liệu

Sau khi thống nhất, **Dữ liệu** > **Thống nhất** trang hiển thị số lượng hồ sơ khách hàng hợp nhất. Kết quả của mỗi bước trong quá trình hợp nhất hiển thị trên mỗi ô. Ví dụ, **Các trường nguồn** hiển thị số lượng thuộc tính được ánh xạ (trường) và **Bản ghi trùng lặp** hiển thị số lượng bản ghi trùng lặp được tìm thấy.

:::image type="content" source="media/m3_unified.png" alt-text="Ảnh chụp màn hình của trang Data Unify sau khi dữ liệu được thống nhất.":::

> [!TIP]
> Các **Điều kiện phù hợp** chỉ hiển thị nếu nhiều thực thể đã được chọn.

Chúng tôi khuyên bạn nên xem lại kết quả, đặc biệt là chất lượng của [phù hợp với các quy tắc](data-unification-update.md#manage-match-rules) và tinh chỉnh chúng nếu cần thiết.

Khi cần, [thực hiện các thay đổi đối với cài đặt hợp nhất](data-unification-update.md) và chạy lại cấu hình hợp nhất.

## <a name="next-step"></a>Bước tiếp theo

Định cấu hình [các hoạt động](activities.md),[làm giàu](enrichment-hub.md),[các mối quan hệ](relationships.md), hoặc [đo](measures.md) để có thêm thông tin chi tiết về khách hàng của bạn.

[!INCLUDE[footer-include](includes/footer-banner.md)]
