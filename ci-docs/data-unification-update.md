---
title: Cập nhật cài đặt hợp nhất
description: Cập nhật các quy tắc trùng lặp, quy tắc đối sánh hoặc các trường hợp nhất trong cài đặt hợp nhất.
ms.date: 06/01/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: 590a2996cf8b2b1c6def59b78583169ec1910b59
ms.sourcegitcommit: 760fbac397c738407c7dea59297d54cae19b6f57
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 06/03/2022
ms.locfileid: "8844066"
---
# <a name="update-the-unification-settings"></a>Cập nhật cài đặt hợp nhất

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Để xem lại hoặc thay đổi bất kỳ cài đặt hợp nhất nào sau khi một cấu hình hợp nhất đã được tạo, hãy thực hiện các bước sau.

1. Đi đến **Dữ liệu** > **Hợp nhất**.

   :::image type="content" source="media/m3_unified.png" alt-text="Ảnh chụp màn hình của trang Data Unify sau khi dữ liệu được thống nhất.":::

   > [!TIP]
   > Các **Điều kiện phù hợp** chỉ hiển thị nếu nhiều thực thể đã được chọn.

1. Chọn những gì bạn muốn cập nhật:
   - [Các trường nguồn](#edit-source-fields) để thêm thực thể hoặc thuộc tính hoặc thay đổi loại thuộc tính.
   - [Bản ghi trùng lặp](#manage-deduplication-rules) để quản lý các quy tắc chống trùng lặp hoặc hợp nhất các tùy chọn.
   - [Điều kiện phù hợp](#manage-match-rules) để cập nhật các quy tắc phù hợp trên hai hoặc nhiều thực thể.
   - [Các trường khách hàng hợp nhất](#manage-unified-fields) để kết hợp hoặc loại trừ các trường. Bạn cũng có thể nhóm các cấu hình liên quan thành các cụm.

1. Sau khi thực hiện các thay đổi, hãy chọn tùy chọn tiếp theo của bạn:

   :::image type="content" source="media/m3_run_match_merge.png" alt-text="Ảnh chụp màn hình của trang Thống nhất dữ liệu với các tùy chọn Hợp nhất được đánh dấu.":::

   - [Chạy các điều kiện phù hợp](#run-matching-conditions) để nhanh chóng đánh giá chất lượng của các điều kiện đối sánh của bạn (quy tắc loại bỏ trùng lặp và đối sánh) mà không cần cập nhật hồ sơ hợp nhất. Các **Chỉ chạy các điều kiện phù hợp** tùy chọn không hiển thị cho một thực thể.
   - [Hợp nhất hồ sơ khách hàng](#run-updates-to-the-unified-customer-profile) để chạy các điều kiện phù hợp và cập nhật thực thể hồ sơ khách hàng hợp nhất mà không ảnh hưởng đến các yếu tố phụ thuộc (chẳng hạn như bổ sung, phân đoạn hoặc đo lường). Các quy trình phụ thuộc không được chạy, nhưng sẽ được làm mới dưới dạng [được xác định trong lịch trình làm mới](system.md#schedule-tab).
   - [Hợp nhất hồ sơ khách hàng và sự phụ thuộc](#run-updates-to-the-unified-customer-profile) để chạy các điều kiện phù hợp và cập nhật thực thể hồ sơ khách hàng hợp nhất và tất cả các yếu tố phụ thuộc (chẳng hạn như bổ sung, phân đoạn hoặc đo lường). Tất cả các quá trình được chạy lại tự động.

## <a name="edit-source-fields"></a>Chỉnh sửa các trường nguồn

Bạn không thể xóa một thuộc tính hoặc một thực thể nếu chúng đã được hợp nhất.

1. Lựa chọn **Chỉnh sửa** trên **Các trường nguồn** ngói.

   :::image type="content" source="media/m3_source_edit.png" alt-text="Ảnh chụp màn hình trang Trường nguồn hiển thị số lượng khóa chính, các trường được ánh xạ và chưa được ánh xạ":::

   Số lượng các trường được ánh xạ và chưa được ánh xạ hiển thị.

1. Lựa chọn **Chọn các thực thể và trường** để thêm các thuộc tính hoặc thực thể khác. Sử dụng tìm kiếm hoặc cuộn để tìm và chọn các thuộc tính và thực thể bạn quan tâm. Chọn **Áp dụng**.

1. Theo tùy chọn, bạn có thể thay đổi khóa chính cho một thực thể, các loại thuộc tính và chuyển đổi **Lập bản đồ thông minh** bật hoặc tắt. Để biết thêm thông tin, hãy xem [Chọn khóa chính và loại ngữ nghĩa cho các thuộc tính](map-entities.md#select-primary-key-and-semantic-type-for-attributes).

1. Lựa chọn **Tiếp theo** để thực hiện các thay đổi đối với các quy tắc loại bỏ trùng lặp hoặc chọn **Lưu và đóng** và quay trở lại [Cập nhật cài đặt hợp nhất](#update-the-unification-settings).

## <a name="manage-deduplication-rules"></a>Quản lý các quy tắc chống trùng lặp

1. Lựa chọn **Chỉnh sửa** trên **Bản ghi trùng lặp** ngói.

   :::image type="content" source="media/m3_duplicates_edit.png" alt-text="Ảnh chụp màn hình của trang Bản ghi trùng lặp hiển thị số lượng bản ghi trùng lặp" lightbox="media/m3_duplicates_edit.png":::

   Số lượng bản ghi trùng lặp được tìm thấy hiển thị trong **Trùng lặp**. Các **Hồ sơ được loại bỏ trùng lặp** cột hiển thị thực thể nào có bản ghi trùng lặp và tỷ lệ phần trăm bản ghi trùng lặp.

1. Nếu bạn đã thêm một thực thể được bổ sung chi tiết, hãy chọn **Sử dụng các thực thể được bổ sung chi tiết**. Để biết thêm thông tin, hãy xem [Làm giàu cho các nguồn dữ liệu](data-sources-enrichment.md).

1. Để quản lý các quy tắc chống trùng lặp, hãy chọn bất kỳ tùy chọn nào sau đây:
   - **Tạo quy tắc mới** : Lựa chọn **Thêm quy tắc** dưới thực thể thích hợp. Để biết thêm thông tin, hãy xem [Xác định quy tắc khử trùng lặp](remove-duplicates.md#define-deduplication-rules).
   - **Thay đổi điều kiện quy tắc** : Chọn quy tắc và sau đó **Chỉnh sửa**. Thay đổi các trường, thêm hoặc bớt các điều kiện, hoặc thêm hoặc bớt các trường hợp ngoại lệ.
   - **Xem trước** : Chọn quy tắc và sau đó **Xem trước** để xem kết quả chạy cuối cùng cho quy tắc này.
   - **Hủy kích hoạt quy tắc** : Chọn quy tắc và sau đó **Hủy kích hoạt** để giữ lại quy tắc loại bỏ trùng lặp trong khi loại trừ nó khỏi quy trình đối sánh.
   - **Sao chép một quy tắc** : Chọn quy tắc và sau đó **Nhân bản** để tạo một quy tắc tương tự với các sửa đổi.
   - **Xóa quy tắc** : Chọn quy tắc và sau đó **Xóa bỏ**.

1. Để thay đổi tùy chọn hợp nhất, hãy chọn thực thể. Bạn chỉ có thể thay đổi tùy chọn nếu quy tắc được tạo.
   1. Lựa chọn **Chỉnh sửa tùy chọn hợp nhất** và thay đổi **Ghi lại để lưu giữ** quyền mua.
   1. Để thay đổi tùy chọn hợp nhất trên các thuộc tính riêng lẻ của một thực thể, hãy chọn **Nâng cao** và thực hiện các thay đổi cần thiết.

      :::image type="content" source="media/m3_adv_merge.png" alt-text="Ảnh chụp màn hình các tùy chọn hợp nhất nâng cao hiển thị email gần đây nhất và địa chỉ đầy đủ nhất":::

   1. Chọn **Xong**.

1. Lựa chọn **Tiếp theo** để thực hiện các thay đổi đối với các điều kiện phù hợp hoặc chọn **Lưu và đóng** và quay trở lại [Cập nhật cài đặt hợp nhất](#update-the-unification-settings).

## <a name="manage-match-rules"></a>Quản lý quy tắc so khớp

Bạn có thể định cấu hình lại và tinh chỉnh hầu hết các thông số khớp. Bạn không thể thêm hoặc xóa các thực thể. Quy tắc đối sánh không áp dụng cho một thực thể.

1. Lựa chọn **Chỉnh sửa** trên **Điều kiện phù hợp** ngói.

   :::image type="content" source="media/m3_match_edit.png" alt-text="Ảnh chụp màn hình của trang Quy tắc và điều kiện đối sánh với số liệu thống kê." lightbox="media/m3_match_edit.png":::

   Trang hiển thị thứ tự đối sánh và các quy tắc đã xác định và các thống kê sau:
   - **Bản ghi nguồn duy nhất** hiển thị số lượng bản ghi nguồn riêng lẻ đã được xử lý trong lần chạy so khớp cuối cùng.
   - **Bản ghi khớp và không khớp** làm nổi bật số lượng bản ghi duy nhất còn lại sau khi xử lý các quy tắc so khớp.
   - **Chỉ các bản ghi khớp** hiển thị số lượng trận đấu trên tất cả các cặp so khớp của bạn.

1. Để xem kết quả của tất cả các quy tắc và điểm số của chúng, hãy chọn **Xem lần chạy cuối cùng**. Kết quả hiển thị, bao gồm cả ID liên hệ thay thế. Bạn có thể tải xuống kết quả.

1. Để xem kết quả và điểm của một quy tắc cụ thể, hãy chọn quy tắc và sau đó **Xem trước**. Kết quả hiển thị. Bạn có thể tải xuống kết quả.

1. Để xem kết quả của một điều kiện cụ thể trên một quy tắc, hãy chọn quy tắc và sau đó **Chỉnh sửa**. Trên ngăn Chỉnh sửa, hãy chọn **Xem trước** trong điều kiện. Bạn có thể tải xuống kết quả.

   :::image type="content" source="media/m3_match_condition_preview.png" alt-text="Biểu diễn đồ họa của các bản ghi chưa khớp và đã khớp bao gồm danh sách dữ liệu.":::

1. Nếu bạn đã thêm một thực thể được bổ sung chi tiết, hãy chọn **Sử dụng các thực thể được bổ sung chi tiết**. Để biết thêm thông tin, hãy xem [Làm giàu cho các nguồn dữ liệu](data-sources-enrichment.md).

1. Để quản lý các quy tắc, hãy chọn bất kỳ tùy chọn nào sau đây:
   - **Tạo quy tắc mới** : Lựa chọn **Thêm quy tắc** dưới thực thể thích hợp. Để biết thêm thông tin, hãy xem [Xác định quy tắc cho các cặp đối sánh](match-entities.md#define-rules-for-match-pairs).
   - **Thay đổi thứ tự các quy tắc của bạn** nếu bạn đã xác định nhiều quy tắc: Kéo và thả các quy tắc vào thứ tự bạn muốn. Để biết thêm thông tin, hãy xem [Chỉ định thứ tự khớp](match-entities.md#specify-the-match-order).
   - **Thay đổi điều kiện quy tắc** : Chọn quy tắc và sau đó **Chỉnh sửa**. Thay đổi các trường, thêm hoặc bớt các điều kiện, hoặc thêm hoặc bớt các trường hợp ngoại lệ.
   - **Hủy kích hoạt quy tắc** : Chọn quy tắc và sau đó **Hủy kích hoạt** để giữ lại quy tắc đối sánh trong khi loại trừ nó khỏi quy trình đối sánh.
   - **Sao chép một quy tắc** : Chọn quy tắc và sau đó **Nhân bản** để tạo một quy tắc tương tự với các sửa đổi.
   - **Xóa quy tắc** : Chọn quy tắc và sau đó **Xóa bỏ**.

1. Lựa chọn **Tiếp theo** để thực hiện các thay đổi đối với các trường hợp nhất hoặc chọn **Lưu và đóng** và quay trở lại [Cập nhật cài đặt hợp nhất](#update-the-unification-settings).

## <a name="manage-unified-fields"></a>Quản lý các trường hợp nhất

1. Lựa chọn **Chỉnh sửa** trên **Các trường khách hàng hợp nhất** ngói.

    :::image type="content" source="media/m3_merge_edit.png" alt-text="Ảnh chụp màn hình các trường khách hàng hợp nhất":::

1. Xem lại các trường được kết hợp và bị loại trừ, đồng thời thực hiện bất kỳ thay đổi nào nếu cần. Thêm hoặc chỉnh sửa khóa CustomerID hoặc nhóm cấu hình thành các cụm. Để biết thêm thông tin, hãy xem [Hợp nhất các trường khách hàng](merge-entities.md).

1. Lựa chọn **Tiếp theo** để xem lại cài đặt hợp nhất và [cập nhật hồ sơ hợp nhất và các phụ thuộc](#run-updates-to-the-unified-customer-profile) hoặc chọn **Lưu và đóng** và quay trở lại [Cập nhật cài đặt hợp nhất](#update-the-unification-settings) để thực hiện nhiều thay đổi hơn.

## <a name="run-matching-conditions"></a>Chạy các điều kiện phù hợp

Chạy các điều kiện đối sánh chỉ chạy các quy tắc trùng lặp và đối sánh và cập nhật *Deduplication_* và *ConflationMatchPair* các thực thể.

1. Từ **Dữ liệu** > **Thống nhất** trang, chọn **Chỉ chạy các điều kiện phù hợp**.

   Các **Bản ghi trùng lặp** và **Điều kiện phù hợp** gạch hiển thị **Đã xếp hàng** hoặc **Làm mới** trạng thái.

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

1. Khi quá trình đối sánh hoàn tất, hãy chọn **Chỉnh sửa** trên **Điều kiện phù hợp** ngói.

   :::image type="content" source="media/match-KPIs.png" alt-text="Ảnh chụp màn hình đã cắt của các chỉ số chính trên trang So khớp với các con số và chi tiết.":::

1. Để thực hiện các thay đổi, hãy xem [Quản lý các quy tắc chống trùng lặp](#manage-deduplication-rules) hoặc [Quản lý quy tắc đối sánh](#manage-match-rules).

1. Chạy lại quá trình đối sánh hoặc [chạy cập nhật cho hồ sơ khách hàng](#run-updates-to-the-unified-customer-profile).

## <a name="run-updates-to-the-unified-customer-profile"></a>Chạy cập nhật cho hồ sơ khách hàng hợp nhất

1. Từ **Dữ liệu** > **Thống nhất** trang, chọn:

   - **Hợp nhất hồ sơ khách hàng** : Chạy các điều kiện phù hợp và cập nhật thực thể hồ sơ khách hàng hợp nhất mà không ảnh hưởng đến các yếu tố phụ thuộc (chẳng hạn như bổ sung, phân khúc hoặc đo lường). Các quy trình phụ thuộc không được chạy, nhưng sẽ được làm mới dưới dạng [được xác định trong lịch trình làm mới](system.md#schedule-tab).

   - **Hợp nhất hồ sơ khách hàng và sự phụ thuộc** : Chạy các điều kiện phù hợp và cập nhật cấu hình hợp nhất và tất cả các phần phụ thuộc. Tất cả các quá trình được chạy lại tự động. Sau khi tất cả các quy trình hạ nguồn đã hoàn tất, hồ sơ khách hàng phản ánh dữ liệu được cập nhật.

   Các **Bản ghi trùng lặp**, **kiện phù hợp**, và **Các trường khách hàng hợp nhất** gạch hiển thị **Đã xếp hàng** hoặc **Làm mới** trạng thái.

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Kết quả của một lần chạy thành công hiển thị trên **Thống nhất** trang hiển thị số lượng hồ sơ khách hàng hợp nhất.
