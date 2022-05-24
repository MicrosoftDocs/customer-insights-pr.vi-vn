---
title: Loại bỏ các bản sao trước khi hợp nhất dữ liệu
description: Bước thứ hai trong quá trình hợp nhất là chọn bản ghi nào sẽ giữ lại khi tìm thấy các bản sao.
recommendations: false
ms.date: 04/22/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-map
- ci-match
- customerInsights
ms.openlocfilehash: 27dff3551ab411a12c273536d7431d651c48573e
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 05/11/2022
ms.locfileid: "8742983"
---
# <a name="remove-duplicates-before-unifying-data"></a>Loại bỏ các bản sao trước khi hợp nhất dữ liệu

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Bước hợp nhất này tùy ý cho phép bạn thiết lập các quy tắc để xử lý các bản ghi trùng lặp trong một thực thể. *Sự trùng lặp* xác định các bản ghi trùng lặp và hợp nhất chúng thành một bản ghi. Bản ghi nguồn được liên kết với bản ghi đã hợp nhất bằng các ID thay thế. Nếu các quy tắc không được định cấu hình, các quy tắc do hệ thống xác định sẽ được áp dụng.

## <a name="include-enriched-entities-preview"></a>Bao gồm các thực thể được bổ sung chi tiết (xem trước)

Nếu bạn đã làm giàu các thực thể ở cấp nguồn dữ liệu để giúp cải thiện kết quả hợp nhất của mình, hãy chọn chúng. Để biết thêm thông tin, hãy xem [Làm giàu cho các nguồn dữ liệu](data-sources-enrichment.md).

1. Trên **Bản ghi trùng lặp** trang, chọn **Sử dụng các thực thể được bổ sung chi tiết** trên đầu của trang.

1. Từ **Sử dụng các thực thể được bổ sung chi tiết**, hãy chọn một hoặc nhiều thực thể được bổ sung.

1. Chọn **Xong**.

## <a name="define-deduplication-rules"></a>Xác định quy tắc khử trùng lặp

1. Trên **Bản ghi trùng lặp** trang, chọn một thực thể và chọn **Thêm quy tắc** để xác định các quy tắc trùng lặp.

   :::image type="content" source="media/m3_duplicates_showmore.png" alt-text="Ảnh chụp màn hình của các trang bản ghi trùng lặp với Hiển thị thêm được đánh dấu":::

   1. Bên trong **Thêm quy tắc**, nhập thông tin sau:
      - **Chọn lĩnh vực** : Chọn từ danh sách các trường có sẵn từ thực thể mà bạn muốn kiểm tra các trường trùng lặp. Chọn các trường có thể là duy nhất cho mọi khách hàng. Ví dụ: địa chỉ email hoặc sự kết hợp của tên, thành phố và số điện thoại.
      - **Bình thường hóa**: Chọn trong số các tùy chọn chuẩn hóa sau cho các thuộc tính đã chọn.
        - **Chữ số** : Chuyển đổi các hệ thống chữ số khác, chẳng hạn như chữ số La Mã, sang chữ số Ả Rập. *VIII* trở thành *8*.
        - **Ký hiệu** : Loại bỏ tất cả các ký hiệu và ký tự đặc biệt. *Head&Shoulder* trở thành *HeadShoulder*.
        - **Văn bản thành chữ thường: Chuyển đổi tất cả các ký tự thành chữ thường**. *ALL CAPS and Title Case* trở thành *all caps and title case*.
        - **Loại (Điện thoại, Tên, Địa chỉ, Tổ chức)** : Chuẩn hóa tên, chức danh, số điện thoại, địa chỉ, v.v.
        - **Unicode sang ASCII** : Chuyển đổi ký hiệu unicode thành ký tự ASCII. */u00B2* trở thành *2*.
        - **Khoảng trắng** : Loại bỏ tất cả các khoảng trắng. *Hello   World* trở thành *HelloWorld*.
      - **Độ chính xác**: Đặt mức độ chính xác để áp dụng cho điều kiện này.
        - **Nền tảng** : Chọn từ *Thấp (30%)*, *bình (60%)*, *(80%)*, và *Chính xác (100%)*. Lựa chọn **Chính xác** để chỉ khớp các bản ghi khớp 100 phần trăm.
        - **Tùy chỉnh**: Đặt tỷ lệ phần trăm mà bản ghi cần so khớp. Hệ thống sẽ chỉ khớp các bản ghi vượt qua ngưỡng này.
      - **Tên** : Đặt tên cho quy tắc.

      :::image type="content" source="media/m3_duplicates_add.png" alt-text="Ảnh chụp màn hình của ngăn Thêm quy tắc để xóa các bản sao.":::

   1. Tùy ý, chọn **Thêm vào** > **Thêm điều kiện** để thêm nhiều điều kiện hơn vào quy tắc. Các điều kiện được kết nối với một toán tử logic AND và do đó chỉ được thực thi nếu tất cả các điều kiện được đáp ứng.

   1. Tùy ý, **Thêm vào** > **Thêm ngoại lệ** đến [thêm ngoại lệ vào quy tắc](match-entities.md#add-exceptions-to-a-rule). Các trường hợp ngoại lệ được sử dụng để giải quyết các trường hợp hiếm hoi về dương tính giả và âm tính giả.

   1. Lựa chọn **Xong** để tạo quy tắc.

1. Không bắt buộc, [thêm các quy tắc khác](#define-deduplication-rules).

1. Chọn một thực thể và sau đó **Chỉnh sửa tùy chọn hợp nhất**.

1. Bên trong **Hợp nhất các tùy chọn** ngăn:
   1. Chọn một trong ba tùy chọn để xác định bản ghi nào cần giữ nếu tìm thấy bản sao:
      - **Điền nhiều nhất**: Xác định bản ghi có các trường thuộc tính được điền nhiều nhất là bản ghi được chọn. Đây là tùy chọn phối mặc định.
      - **Gần đây nhất**: Xác định bản ghi chiến thắng dựa trên lần truy cập gần đây nhất. Yêu cầu ngày hoặc trường số để xác định lần truy cập gần đây.
      - **Cách đây xa nhất**: Xác định bản ghi chiến thắng dựa trên lần truy cập cách đây xa nhất. Yêu cầu ngày hoặc trường số để xác định lần truy cập gần đây.
      
      Trong trường hợp hòa, bản ghi chiến thắng là bản ghi có giá trị MAX (PK) hoặc khóa chính lớn hơn.
      
   1. Theo tùy chọn, để xác định tùy chọn hợp nhất trên các thuộc tính riêng lẻ của một thực thể, hãy chọn **Trình độ cao** ở cuối ngăn. Ví dụ: bạn có thể chọn giữ lại email mới nhất VÀ địa chỉ đầy đủ nhất từ các bản ghi khác nhau. Mở rộng thực thể để xem tất cả các thuộc tính của nó và xác định tùy chọn nào sẽ sử dụng cho các thuộc tính riêng lẻ. Nếu bạn chọn tùy chọn dựa trên lần truy cập gần đây, bạn cũng cần chỉ định trường ngày / giờ xác định lần truy cập gần đây.

      :::image type="content" source="media/m3_adv_merge.png" alt-text="Ngăn tùy chọn hợp nhất nâng cao hiển thị email gần đây và địa chỉ đầy đủ":::

   1. Lựa chọn **Xong** để áp dụng các tùy chọn hợp nhất của bạn.

1. Sau khi xác định các quy tắc loại bỏ trùng lặp và các tùy chọn hợp nhất, hãy chọn **Kế tiếp**.
  
> [!div class="nextstepaction"]
> [Bước tiếp theo cho một thực thể: Hợp nhất các trường](merge-entities.md)

> [!div class="nextstepaction"]
> [Bước tiếp theo cho nhiều thực thể: Điều kiện đối sánh](match-entities.md)

## <a name="deduplication-output-as-an-entity"></a>Đầu ra khử trùng lặp dưới dạng một thực thể

Quá trình khử trùng lặp tạo ra một thực thể được khử trùng lặp mới cho mỗi thực thể nguồn. Có thể tìm thấy các thực thể cùng với **ConflationMatchPairs:CustomerInsights** trong phần **Hệ thống** trên trang **Thực thể**, với tên **Deduplication_DataSource_Entity**.

Thực thể đầu ra loại bỏ trùng lặp chứa thông tin sau:

- ID/Khóa
  - Trường khóa chính và ID thay thế. Trường ID thay thế bao gồm tất cả các ID thay thế được xác định cho một bản ghi.
  - Trường Deduplication_GroupId hiển thị nhóm hoặc cụm được xác định trong một thực thể sẽ nhóm tất cả các bản ghi tương tự dựa trên các trường loại bỏ trùng lặp được chỉ định. Tính năng này được sử dụng cho mục đích xử lý hệ thống. Nếu không có quy tắc khử trùng lặp thủ công nào được chỉ định và áp dụng quy tắc khử trùng lặp do hệ thống xác định, bạn có thể không tìm thấy trường này trong thực thể đầu ra khử trùng lặp.
  - Deduplication_WinnerId: Trường này chứa ID chiến thắng từ các nhóm hoặc cụm đã xác định. Nếu Deduplication_WinnerId giống với giá trị Khóa chính của một bản ghi, điều đó có nghĩa là bản ghi đó là bản ghi chiến thắng.
- Các trường được sử dụng để xác định các quy tắc khử trùng lặp.
- Các trường Quy tắc và Điểm để biểu thị quy tắc khử trùng lặp đã được áp dụng và điểm mà thuật toán so khớp trả về.

[!INCLUDE[footer-include](includes/footer-banner.md)]
