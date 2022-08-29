---
title: Loại bỏ các bản sao trước khi hợp nhất dữ liệu
description: Bước thứ hai trong quá trình hợp nhất là chọn bản ghi nào sẽ giữ lại khi tìm thấy các bản sao.
recommendations: false
ms.date: 08/01/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: sstabbert
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-map
- ci-match
- customerInsights
ms.openlocfilehash: 3f84c1c149f0befcbe489ccdd8a666ce6d5d798a
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304499"
---
# <a name="remove-duplicates-before-unifying-data"></a>Loại bỏ các bản sao trước khi hợp nhất dữ liệu

Bước tùy chọn này trong hợp nhất cho phép bạn thiết lập các quy tắc để loại bỏ các bản ghi trùng lặp **ở trong** một thực thể. Phép trùng lặp xác định nhiều bản ghi cho một khách hàng và chọn bản ghi tốt nhất để giữ (dựa trên các tùy chọn hợp nhất cơ bản) hoặc hợp nhất các bản ghi thành một (dựa trên tùy chọn hợp nhất nâng cao). Bản ghi nguồn được liên kết với bản ghi đã hợp nhất bằng các ID thay thế. Nếu các quy tắc không được định cấu hình, các quy tắc do hệ thống xác định sẽ được áp dụng.

## <a name="default-deduplication"></a>Khử trùng lặp mặc định

Các quy tắc do hệ thống xác định được áp dụng nếu không có quy tắc nào được thêm vào.

- Khóa chính được loại bỏ trùng lặp.
  Đối với bất kỳ bản ghi nào có cùng khóa chính, **Được lấp đầy nhiều nhất** kỷ lục (kỷ lục có ít giá trị rỗng nhất) là người chiến thắng.
- Mọi quy tắc đối sánh giữa nhiều thực thể đều được áp dụng cho thực thể.
  Ví dụ: Trong bước đối sánh, nếu đối tượng A được đối sánh với đối tượng B trên *Họ và tên* và *Ngày sinh*, thì thực thể A cũng được loại bỏ trùng lặp bởi *Họ và tên* và *Ngày sinh*. Tại vì *Họ và tên* và *Ngày sinh* là các khóa hợp lệ để xác định khách hàng trong thực thể A, các khóa này cũng hợp lệ để xác định các khách hàng trùng lặp trong thực thể A.

## <a name="include-enriched-entities-preview"></a>Bao gồm các thực thể được bổ sung chi tiết (xem trước)

Nếu bạn đã làm giàu các thực thể ở cấp nguồn dữ liệu để giúp cải thiện kết quả hợp nhất của mình, hãy chọn chúng. Để biết thêm thông tin, hãy xem [Làm giàu cho các nguồn dữ liệu](data-sources-enrichment.md).

1. Trên **Bản ghi trùng lặp** trang, chọn **Sử dụng các thực thể được bổ sung chi tiết** trên đầu của trang.

1. Từ **Sử dụng các thực thể được bổ sung chi tiết**, chọn một hoặc nhiều thực thể được bổ sung.

1. Chọn **Xong**.

## <a name="define-deduplication-rules"></a>Xác định quy tắc khử trùng lặp

1. Trên **Bản ghi trùng lặp** trang, chọn một thực thể và chọn **Thêm quy tắc** để xác định các quy tắc trùng lặp.

   :::image type="content" source="media/m3_duplicates_showmore.png" alt-text="Ảnh chụp màn hình của trang Bản ghi trùng lặp với thực thể được đánh dấu và Thêm quy tắc được hiển thị"  lightbox="media/m3_duplicates_showmore.png":::

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

   1. Tùy ý, chọn **cộng** > **Thêm điều kiện** để thêm nhiều điều kiện hơn vào quy tắc. Các điều kiện được kết nối với một toán tử logic AND và do đó chỉ được thực thi nếu tất cả các điều kiện được đáp ứng.

   1. Tùy ý, **cộng** > **Thêm ngoại lệ** đến [thêm ngoại lệ vào quy tắc](match-entities.md#add-exceptions-to-a-rule). Các trường hợp ngoại lệ được sử dụng để giải quyết các trường hợp hiếm hoi về dương tính giả và âm tính giả.

   1. Lựa chọn **Xong** để tạo quy tắc.

1. Không bắt buộc, [thêm các quy tắc khác](#define-deduplication-rules).

1. Chọn một thực thể và sau đó **Chỉnh sửa tùy chọn hợp nhất**.

1. Bên trong **Hợp nhất các tùy chọn** ngăn:
   1. Chọn một trong ba tùy chọn để xác định bản ghi nào cần giữ nếu tìm thấy bản sao:
      - **Điền nhiều nhất**: Xác định bản ghi có các trường thuộc tính được điền nhiều nhất là bản ghi được chọn. Đây là tùy chọn phối mặc định.
      - **Gần đây nhất**: Xác định bản ghi chiến thắng dựa trên lần truy cập gần đây nhất. Yêu cầu ngày hoặc trường số để xác định lần truy cập gần đây.
      - **Cách đây xa nhất**: Xác định bản ghi chiến thắng dựa trên lần truy cập cách đây xa nhất. Yêu cầu ngày hoặc trường số để xác định lần truy cập gần đây.

      Trong trường hợp hòa, bản ghi chiến thắng là bản ghi có giá trị MAX (PK) hoặc khóa chính lớn hơn.

   1. Theo tùy chọn, để xác định tùy chọn hợp nhất trên các thuộc tính riêng lẻ của một thực thể, hãy chọn **Nâng cao** ở cuối ngăn. Ví dụ: bạn có thể chọn giữ lại email mới nhất VÀ địa chỉ đầy đủ nhất từ các bản ghi khác nhau. Mở rộng thực thể để xem tất cả các thuộc tính của nó và xác định tùy chọn nào sẽ sử dụng cho các thuộc tính riêng lẻ. Nếu bạn chọn tùy chọn dựa trên lần truy cập gần đây, bạn cũng cần chỉ định trường ngày / giờ xác định lần truy cập gần đây.

      :::image type="content" source="media/m3_adv_merge.png" alt-text="Ngăn tùy chọn hợp nhất nâng cao hiển thị email gần đây và địa chỉ đầy đủ":::

   1. Lựa chọn **Xong** để áp dụng các tùy chọn hợp nhất của bạn.

1. Sau khi xác định các quy tắc loại bỏ trùng lặp và các tùy chọn hợp nhất, hãy chọn **Tiếp theo**.
  
> [!div class="nextstepaction"]
> [Bước tiếp theo cho một thực thể: Hợp nhất các trường](merge-entities.md)

> [!div class="nextstepaction"]
> [Bước tiếp theo cho nhiều thực thể: Điều kiện đối sánh](match-entities.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
