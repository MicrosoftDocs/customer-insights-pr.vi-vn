---
title: Cập nhật cài đặt hợp nhất khách hàng, tài khoản hoặc liên hệ
description: Cập nhật các quy tắc trùng lặp, quy tắc đối sánh hoặc các trường hợp nhất trong cài đặt hợp nhất tài khoản hoặc khách hàng.
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: Scott-Stabbert
ms.author: sstabbert
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: f2c14c169f5973b5f400989b9eeea593eba09182
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304361"
---
# <a name="update-unification-settings"></a>Cập nhật cài đặt hợp nhất

Để xem lại hoặc thay đổi bất kỳ cài đặt hợp nhất nào sau khi một cấu hình hợp nhất đã được tạo, hãy thực hiện các bước sau.

1. Đi đến **Dữ liệu** > **Hợp nhất**.

   Đối với khách hàng cá nhân (B-to-C), **Thống nhất** trang hiển thị số lượng hồ sơ khách hàng hợp nhất và các ô cho mỗi bước hợp nhất.

   :::image type="content" source="media/m3_unified.png" alt-text="Ảnh chụp màn hình của trang Data Unify sau khi dữ liệu được thống nhất." lightbox="media/m3_unified.png":::

   Đối với tài khoản doanh nghiệp (B-to-B), **Thống nhất** trang hiển thị số lượng hồ sơ tài khoản hợp nhất và các ô cho mỗi bước hợp nhất tài khoản. Nếu các địa chỉ liên hệ được hợp nhất, số lượng cấu hình liên hệ thống nhất và các ô cho mỗi bước hợp nhất địa chỉ liên hệ sẽ hiển thị. Chọn ô thích hợp bên dưới **Hợp nhất các tài khoản** hoặc **Hợp nhất Danh bạ (xem trước)** tùy thuộc vào những gì bạn muốn cập nhật.

   :::image type="content" source="media/b2b_unified.png" alt-text="Ảnh chụp màn hình của trang Thống nhất dữ liệu sau khi dữ liệu tài khoản và liên hệ được hợp nhất." lightbox="media/b2b_unified.png":::

   > [!TIP]
   > Các **Điều kiện phù hợp** chỉ hiển thị nếu nhiều thực thể đã được chọn.

1. Chọn những gì bạn muốn cập nhật:
   - [Các trường nguồn](#edit-source-fields) để thêm thực thể hoặc thuộc tính hoặc thay đổi loại thuộc tính.
   - [Bản ghi trùng lặp](#manage-deduplication-rules) để quản lý các quy tắc chống trùng lặp hoặc hợp nhất các tùy chọn.
   - [Điều kiện phù hợp](#manage-match-rules) để cập nhật các quy tắc phù hợp trên hai hoặc nhiều thực thể.
   - [Các trường khách hàng hợp nhất](#manage-unified-fields) để kết hợp hoặc loại trừ các trường. Bạn cũng có thể nhóm các cấu hình liên quan thành các cụm.
   - [Trường ngữ nghĩa](#manage-semantic-fields-for-unified-contacts) để quản lý các kiểu ngữ nghĩa cho các trường liên hệ thống nhất.
   - [Các mối quan hệ](#manage-contact-and-account-relationships) để quản lý mối quan hệ liên hệ với tài khoản.

1. Sau khi thực hiện các thay đổi, hãy chọn tùy chọn tiếp theo của bạn:

   - [Chạy các điều kiện phù hợp](#run-matching-conditions) để nhanh chóng đánh giá chất lượng của các điều kiện đối sánh của bạn (quy tắc trùng lặp và đối sánh) mà không cần cập nhật hồ sơ hợp nhất. Các **Chỉ chạy các điều kiện phù hợp** tùy chọn không hiển thị cho một thực thể.
   - [Hợp nhất hồ sơ](#run-updates-to-the-unified-profile) để chạy các điều kiện phù hợp và cập nhật thực thể hồ sơ hợp nhất mà không ảnh hưởng đến các yếu tố phụ thuộc (chẳng hạn như bổ sung, phân đoạn hoặc đo lường). Các quy trình phụ thuộc không được chạy, nhưng sẽ được làm mới dưới dạng [được xác định trong lịch trình làm mới](schedule-refresh.md).
   - [Hợp nhất hồ sơ và phụ thuộc](#run-updates-to-the-unified-profile) để chạy các điều kiện phù hợp, cập nhật thực thể cấu hình hợp nhất và cập nhật tất cả các phần phụ thuộc (chẳng hạn như phần bổ sung, phân đoạn hoặc số đo). Tất cả các quá trình được chạy lại tự động. Trong B-to-B, quá trình hợp nhất được chạy trên cả tài khoản và các thực thể liên hệ cập nhật cấu hình hợp nhất.

## <a name="edit-source-fields"></a>Chỉnh sửa trường nguồn

Bạn không thể xóa một thuộc tính hoặc một thực thể nếu chúng đã được hợp nhất.

1. Lựa chọn **Chỉnh sửa** trên **Các trường nguồn** ngói.

   :::image type="content" source="media/m3_source_edit.png" alt-text="Ảnh chụp màn hình trang Trường nguồn hiển thị số lượng khóa chính, các trường được ánh xạ và chưa được ánh xạ":::

   Số lượng các trường được ánh xạ và chưa được ánh xạ hiển thị.

1. Để thêm các thuộc tính hoặc thực thể khác, hãy chọn **Chọn các thực thể và trường**.

1. Theo tùy chọn, bạn có thể thay đổi khóa chính cho một thực thể, các loại thuộc tính và chuyển đổi **Lập bản đồ thông minh** bật hoặc tắt. Để biết thêm thông tin, hãy xem [Chọn các trường nguồn](map-entities.md).

1. Lựa chọn **Tiếp theo** để thực hiện các thay đổi đối với các quy tắc loại bỏ trùng lặp hoặc chọn **Lưu và đóng** và trở lại [Cập nhật cài đặt hợp nhất](#update-unification-settings).

## <a name="manage-deduplication-rules"></a>Quản lý các quy tắc chống trùng lặp

1. Lựa chọn **Chỉnh sửa** trên **Bản ghi trùng lặp** ngói.

   :::image type="content" source="media/m3_duplicates_edit.png" alt-text="Ảnh chụp màn hình trang Bản ghi trùng lặp hiển thị số lượng bản ghi trùng lặp" lightbox="media/m3_duplicates_edit.png":::

   Số lượng bản ghi trùng lặp được tìm thấy hiển thị trong **Trùng lặp**. Các **Hồ sơ được loại bỏ trùng lặp** cột hiển thị thực thể nào có bản ghi trùng lặp và tỷ lệ phần trăm bản ghi trùng lặp.

1. Để sử dụng một thực thể được bổ sung chi tiết, hãy chọn **Sử dụng các thực thể được bổ sung chi tiết**. Để biết thêm thông tin, hãy xem [Làm giàu cho các nguồn dữ liệu](data-sources-enrichment.md).

1. Để quản lý các quy tắc chống trùng lặp, hãy chọn bất kỳ tùy chọn nào sau đây:
   - **Tạo quy tắc mới** : Lựa chọn **Thêm quy tắc** dưới thực thể thích hợp. Để biết thêm thông tin, hãy xem [Xác định quy tắc khử trùng lặp](remove-duplicates.md#define-deduplication-rules).
   - **Thay đổi điều kiện quy tắc** : Chọn quy tắc và sau đó **Chỉnh sửa**. Thay đổi các trường, thêm hoặc bớt các điều kiện hoặc thêm hoặc bớt các trường hợp ngoại lệ.
   - **Xem trước** : Chọn quy tắc và sau đó **Xem trước** để xem kết quả chạy cuối cùng cho quy tắc này.
   - **Hủy kích hoạt quy tắc** : Chọn quy tắc và sau đó **Hủy kích hoạt** để giữ lại quy tắc loại trừ trùng lặp trong khi loại trừ nó khỏi quy trình đối sánh.
   - **Sao chép một quy tắc** : Chọn quy tắc và sau đó **Nhân bản** để tạo một quy tắc tương tự với các sửa đổi.
   - **Xóa quy tắc** : Chọn quy tắc và sau đó **Xóa bỏ**.

1. Để thay đổi tùy chọn hợp nhất, hãy chọn thực thể. Bạn chỉ có thể thay đổi tùy chọn nếu quy tắc được tạo.
   1. Lựa chọn **Chỉnh sửa tùy chọn hợp nhất** và thay đổi **Ghi lại để lưu giữ** quyền mua.
   1. Để thay đổi tùy chọn hợp nhất trên các thuộc tính riêng lẻ của một thực thể, hãy chọn **Nâng cao** và thực hiện các thay đổi cần thiết.

   1. Chọn **Xong**.

1. Lựa chọn **Tiếp theo** để thực hiện các thay đổi đối với các điều kiện phù hợp hoặc chọn **Lưu và đóng** và trở lại [Cập nhật cài đặt hợp nhất](#update-unification-settings).

## <a name="manage-match-rules"></a>Quản lý quy tắc so khớp

Bạn có thể định cấu hình lại và tinh chỉnh hầu hết các thông số khớp. Bạn không thể thêm hoặc xóa các thực thể. Quy tắc đối sánh không áp dụng cho một thực thể.

1. Lựa chọn **Chỉnh sửa** trên **Điều kiện phù hợp** ngói.

   :::image type="content" source="media/m3_match_edit.png" alt-text="Ảnh chụp màn hình của trang Quy tắc và điều kiện đối sánh với số liệu thống kê." lightbox="media/m3_match_edit.png":::

   Trang hiển thị thứ tự đối sánh và các quy tắc đã xác định và các thống kê sau:
   - **Bản ghi nguồn duy nhất** hiển thị số lượng bản ghi nguồn riêng lẻ đã được xử lý trong lần chạy đối sánh cuối cùng.
   - **Bản ghi phù hợp và không khớp** đánh dấu số lượng bản ghi duy nhất còn lại sau khi xử lý các quy tắc đối sánh.
   - **Chỉ các bản ghi phù hợp** hiển thị số lượng trận đấu trên tất cả các cặp đối sánh của bạn.

1. Để xem kết quả của tất cả các quy tắc và điểm số của chúng, hãy chọn **Xem lần chạy cuối cùng**. Kết quả hiển thị, bao gồm cả ID liên hệ thay thế. Bạn có thể tải xuống kết quả.

1. Để xem kết quả và điểm số của một quy tắc cụ thể, hãy chọn quy tắc và sau đó **Xem trước**. Kết quả hiển thị. Bạn có thể tải xuống kết quả.

1. Để xem kết quả của một điều kiện cụ thể trên một quy tắc, hãy chọn quy tắc và sau đó **Chỉnh sửa**. Trên ngăn Chỉnh sửa, hãy chọn **Xem trước** trong điều kiện. Bạn có thể tải xuống kết quả.

   :::image type="content" source="media/m3_match_condition_preview.png" alt-text="Biểu diễn đồ họa của các bản ghi chưa khớp và đã khớp bao gồm danh sách dữ liệu.":::

1. Nếu bạn đã thêm một thực thể được bổ sung chi tiết, hãy chọn **Sử dụng các thực thể được bổ sung chi tiết**. Để biết thêm thông tin, hãy xem [Làm giàu cho các nguồn dữ liệu](data-sources-enrichment.md).

1. Để quản lý các quy tắc, hãy chọn bất kỳ tùy chọn nào sau đây:
   - **Tạo quy tắc mới** : Lựa chọn **Thêm quy tắc** dưới thực thể thích hợp. Để biết thêm thông tin, hãy xem [Xác định quy tắc cho các cặp đối sánh](match-entities.md#define-rules-for-match-pairs).
   - **Thay đổi thứ tự các quy tắc của bạn** nếu bạn đã xác định nhiều quy tắc: Kéo và thả các quy tắc vào thứ tự bạn muốn. Để biết thêm thông tin, hãy xem [Chỉ định thứ tự khớp](match-entities.md#specify-the-match-order).
   - **Thay đổi điều kiện quy tắc** : Chọn quy tắc và sau đó **Chỉnh sửa**. Thay đổi các trường, thêm hoặc bớt các điều kiện hoặc thêm hoặc bớt các trường hợp ngoại lệ.
   - **Hủy kích hoạt quy tắc** : Chọn quy tắc và sau đó **Hủy kích hoạt** để giữ lại quy tắc đối sánh trong khi loại trừ nó khỏi quy trình đối sánh.
   - **Sao chép một quy tắc** : Chọn quy tắc và sau đó **Nhân bản** để tạo một quy tắc tương tự với các sửa đổi.
   - **Xóa quy tắc** : Chọn quy tắc và sau đó **Xóa bỏ**.

1. Lựa chọn **Tiếp theo** để thực hiện các thay đổi đối với các trường hợp nhất hoặc chọn **Lưu và đóng** và trở lại [Cập nhật cài đặt hợp nhất](#update-unification-settings).

## <a name="manage-unified-fields"></a>Quản lý các trường hợp nhất

1. Lựa chọn **Chỉnh sửa** trên **Các trường khách hàng hợp nhất** ngói.

    :::image type="content" source="media/m3_merge_edit.png" alt-text="Ảnh chụp màn hình các trường khách hàng hợp nhất":::

1. Xem lại các trường được kết hợp và bị loại trừ và thực hiện bất kỳ thay đổi nào nếu cần. Thêm hoặc chỉnh sửa khóa CustomerID hoặc nhóm cấu hình thành các cụm. Để biết thêm thông tin, hãy xem [Hợp nhất các trường khách hàng](merge-entities.md).

1. Đối với khách hàng hoặc tài khoản, hãy chọn **Tiếp theo** để xem xét và [cập nhật hồ sơ hợp nhất và các phụ thuộc](#run-updates-to-the-unified-profile). Hoặc chọn **Lưu và đóng** và trở lại [Cập nhật cài đặt hợp nhất](#update-unification-settings) để thực hiện nhiều thay đổi hơn.

   Đối với các liên hệ, hãy chọn **Tiếp theo** để quản lý các trường ngữ nghĩa. Hoặc chọn **Lưu và đóng** và trở lại [Cập nhật cài đặt hợp nhất](#update-unification-settings) để thực hiện nhiều thay đổi hơn.

## <a name="manage-semantic-fields-for-unified-contacts"></a>Quản lý các trường ngữ nghĩa cho các liên hệ hợp nhất

1. Lựa chọn **Chỉnh sửa** trên **Trường ngữ nghĩa** ngói.

1. Để thay đổi kiểu ngữ nghĩa cho một trường thống nhất, hãy chọn một kiểu mới. Để biết thêm thông tin, hãy xem [Xác định các trường ngữ nghĩa cho các liên hệ hợp nhất](data-unification-contacts.md#define-the-semantic-fields-for-unified-contacts).

1. Lựa chọn **Tiếp theo** để quản lý tài khoản và mối quan hệ liên hệ, hoặc chọn **Lưu và đóng** và trở lại [Cập nhật cài đặt hợp nhất](#update-unification-settings) để thực hiện nhiều thay đổi hơn.

## <a name="manage-contact-and-account-relationships"></a>Quản lý các mối quan hệ liên hệ và tài khoản

1. Lựa chọn **Chỉnh sửa** trên **Các mối quan hệ** ngói.

1. Để thay đổi mối quan hệ liên hệ và tài khoản, hãy thay đổi bất kỳ thông tin nào sau đây:

   - **Khóa ngoại từ thực thể liên hệ** : Chọn thuộc tính kết nối thực thể liên hệ của bạn với tài khoản.
   - **Tới thực thể tài khoản** : Chọn thực thể tài khoản được liên kết với địa chỉ liên hệ.

1. Lựa chọn **Tiếp theo** để xem lại cài đặt hợp nhất và [cập nhật hồ sơ hợp nhất và các phụ thuộc](#run-updates-to-the-unified-profile) hoặc chọn **Lưu và đóng** và trở lại [Cập nhật cài đặt hợp nhất](#update-unification-settings) để thực hiện nhiều thay đổi hơn.

## <a name="run-matching-conditions"></a>Chạy các điều kiện phù hợp

Chạy các điều kiện đối sánh chỉ chạy các quy tắc trùng lặp và đối sánh và cập nhật *Deduplication_* * và *ConflationMatchPair* các thực thể.

1. Từ **Dữ liệu** > **Thống nhất** trang, chọn **Chỉ chạy các điều kiện phù hợp**.

   Các **Bản ghi trùng lặp** và **Điều kiện phù hợp** gạch hiển thị **Đã xếp hàng** hoặc **Làm mới** trạng thái.

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

1. Khi quá trình đối sánh hoàn tất, hãy chọn **Chỉnh sửa** trên **Điều kiện phù hợp** ngói.

   :::image type="content" source="media/match-KPIs.png" alt-text="Ảnh chụp màn hình đã cắt của các chỉ số chính trên trang So khớp với các con số và chi tiết.":::

1. Để thực hiện các thay đổi, hãy xem [Quản lý các quy tắc chống trùng lặp](#manage-deduplication-rules) hoặc [Quản lý quy tắc đối sánh](#manage-match-rules).

1. Chạy lại quá trình đối sánh hoặc [chạy cập nhật cho hồ sơ](#run-updates-to-the-unified-profile).

## <a name="run-updates-to-the-unified-profile"></a>Chạy cập nhật cho cấu hình hợp nhất

- Để chạy các điều kiện phù hợp và cập nhật thực thể hồ sơ hợp nhất *không có* tác động đến các yếu tố phụ thuộc (chẳng hạn như thẻ khách hàng, mức độ phong phú, phân khúc hoặc thước đo), chọn **Hợp nhất hồ sơ khách hàng**. Đối với tài khoản, hãy chọn **Hợp nhất các tài khoản** > **Hợp nhất hồ sơ**. Đối với các liên hệ, hãy chọn **Hợp nhất danh bạ (xem trước)** > **Hợp nhất hồ sơ**. Các quy trình phụ thuộc không được chạy, nhưng sẽ được làm mới dưới dạng [được xác định trong lịch trình làm mới](schedule-refresh.md).
- Để chạy các điều kiện phù hợp, hãy cập nhật cấu hình hợp nhất và chạy tất cả các phần phụ thuộc, hãy chọn **Hợp nhất hồ sơ khách hàng và sự phụ thuộc**. Tất cả các quá trình được chạy lại tự động. Đối với tài khoản và danh bạ, hãy chọn **Hợp nhất các tài khoản** > **Hợp nhất hồ sơ và phụ thuộc**. Điều kiện đối sánh được chạy cho cả tài khoản và danh bạ cập nhật cả cấu hình hợp nhất và tất cả các phần phụ thuộc khác đều được chạy.

Tất cả các ô ngoại trừ **Các trường nguồn** buổi bieu diễn **Đã xếp hàng** hoặc **Làm mới**.

[!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Kết quả của một lần chạy thành công hiển thị trên **Thống nhất** trang hiển thị số lượng cấu hình hợp nhất.
