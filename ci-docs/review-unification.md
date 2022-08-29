---
title: Xem xét hợp nhất dữ liệu
description: Xem lại các bước hợp nhất dữ liệu, tạo hồ sơ khách hàng hợp nhất và xem xét kết quả
ms.date: 08/12/2022
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
ms.openlocfilehash: b4d77effc347e40fecde625a1a42a24900456471
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303993"
---
# <a name="review-data-unification"></a>Xem xét hợp nhất dữ liệu

Xem lại bản tóm tắt các thay đổi, tạo hồ sơ hợp nhất và xem xét kết quả.

## <a name="review-and-create-customer-profiles"></a>Xem xét và tạo hồ sơ khách hàng

Bước cuối cùng trong quy trình hợp nhất này hiển thị tóm tắt các bước trong quy trình và cung cấp cơ hội thực hiện các thay đổi trước khi bạn tạo hồ sơ hợp nhất.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

:::image type="content" source="media/m3_review.png" alt-text="Ảnh chụp màn hình Đánh giá và tạo hồ sơ khách hàng.":::

1. Lựa chọn **Chỉnh sửa** về bất kỳ bước hợp nhất dữ liệu nào để xem xét và thực hiện bất kỳ thay đổi nào.

1. Nếu bạn hài lòng với lựa chọn của mình, hãy chọn **Tạo hồ sơ khách hàng** (hoặc **Tạo hồ sơ tài khoản** cho B-to-B). Các **Thống nhất** trang hiển thị trong khi hồ sơ khách hàng hợp nhất đang được tạo.

   :::image type="content" source="media/m3_unify_refreshing.png" alt-text="Ảnh chụp màn hình của trang Unify với các ô hiển thị Đã xếp hàng hoặc Đang làm mới.":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Thuật toán hợp nhất cần một thời gian để hoàn thành và bạn không thể thay đổi cấu hình cho đến khi hoàn tất.

## <a name="view-the-results-of-data-unification"></a>Xem kết quả hợp nhất dữ liệu

Sau khi thống nhất, **Dữ liệu** > **Thống nhất** trang hiển thị số lượng hồ sơ khách hàng hợp nhất (hoặc hồ sơ tài khoản cho B-to-B). Kết quả của mỗi bước trong quá trình hợp nhất hiển thị trên mỗi ô. Ví dụ, **Các trường nguồn** hiển thị số lượng thuộc tính được ánh xạ (trường) và **Bản ghi trùng lặp** hiển thị số lượng bản ghi trùng lặp được tìm thấy.

:::image type="content" source="media/m3_unified.png" alt-text="Ảnh chụp màn hình của trang Data Unify sau khi dữ liệu được thống nhất.":::

> [!TIP]
> Các **Điều kiện phù hợp** chỉ hiển thị nếu nhiều thực thể đã được chọn.

Chúng tôi khuyên bạn nên xem lại kết quả, đặc biệt là chất lượng của [phù hợp với các quy tắc](data-unification-update.md#manage-match-rules) và tinh chỉnh chúng nếu cần thiết.

Khi cần, [thực hiện các thay đổi đối với cài đặt hợp nhất](data-unification-update.md) và chạy lại cấu hình hợp nhất.

### <a name="verify-output-entities-from-data-unification"></a>Xác minh các thực thể đầu ra từ hợp nhất dữ liệu

Đi đến **Dữ liệu** > **Thực thể** để xác minh các thực thể đầu ra.

Thực thể hồ sơ khách hàng hợp nhất, được gọi là *khách hàng*, hiển thị trong **Hồ sơ** tiết diện. Lần chạy hợp nhất thành công đầu tiên tạo ra sự hợp nhất *khách hàng* thực thể. Tất cả các lần chạy tiếp theo sẽ mở rộng thực thể đó.

Các thực thể trùng lặp và hỗn hợp được tạo và hiển thị trong **Hệ thống** tiết diện. Thực thể loại trừ trùng lặp cho mỗi thực thể nguồn được tạo với tên **Deduplication_DataSource_Entity**. Các **ConflationMatchPairs** thực thể chứa thông tin về các đối sánh giữa nhiều thực thể.

Thực thể đầu ra loại bỏ trùng lặp chứa thông tin sau:
- ID/Khóa
  - Trường khóa chính và ID thay thế. Trường ID thay thế bao gồm tất cả các ID thay thế được xác định cho một bản ghi.
  - Trường Deduplication_GroupId hiển thị nhóm hoặc cụm được xác định trong một thực thể sẽ nhóm tất cả các bản ghi tương tự dựa trên các trường loại bỏ trùng lặp được chỉ định. Tính năng này được sử dụng cho mục đích xử lý hệ thống. Nếu không có quy tắc khử trùng lặp thủ công nào được chỉ định và áp dụng quy tắc khử trùng lặp do hệ thống xác định, bạn có thể không tìm thấy trường này trong thực thể đầu ra khử trùng lặp.
  - Deduplication_WinnerId: Trường này chứa ID chiến thắng từ các nhóm hoặc cụm đã xác định. Nếu Deduplication_WinnerId giống với giá trị Khóa chính của một bản ghi, điều đó có nghĩa là bản ghi đó là bản ghi chiến thắng.
- Các trường được sử dụng để xác định các quy tắc khử trùng lặp.
- Các trường Quy tắc và Điểm để biểu thị quy tắc khử trùng lặp đã được áp dụng và điểm mà thuật toán so khớp trả về.

## <a name="next-step"></a>Bước tiếp theo

- Đối với B-to-B, tùy chọn thực hiện [liên hệ thống nhất](data-unification-contacts.md).

- Đối với B-to-C, hãy cấu hình [các hoạt động](activities.md),[sự làm giàu](enrichment-hub.md),[các mối quan hệ](relationships.md), hoặc [đo](measures.md) để có thêm thông tin chi tiết về khách hàng của bạn.

[!INCLUDE[footer-include](includes/footer-banner.md)]
