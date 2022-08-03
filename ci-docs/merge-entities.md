---
title: Hợp nhất các trường khách hàng để hợp nhất dữ liệu
description: Trộn các thực thể để tạo hồ sơ khách hàng hợp nhất.
recommendations: false
ms.date: 05/04/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-merge
- ci-match
- ci-relationships
- customerInsights
ms.openlocfilehash: 4a19b753e7a5979fe72d7e96bc4452d7795c2d48
ms.sourcegitcommit: 3c5b0b40b2b45e420015bbdd228ce0e610245e6f
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 07/12/2022
ms.locfileid: "9139697"
---
# <a name="unify-customer-fields-for-data-unification"></a>Hợp nhất các trường khách hàng để hợp nhất dữ liệu

Trong bước này của quá trình hợp nhất, hãy chọn và loại trừ các thuộc tính để hợp nhất trong thực thể hồ sơ hợp nhất của bạn. Ví dụ: nếu ba thực thể có dữ liệu email, bạn có thể muốn giữ cả ba trường email riêng biệt hoặc hợp nhất chúng thành một trường email duy nhất cho cấu hình hợp nhất. Một số thuộc tính được hệ thống tự động kết hợp. Bạn có thể tạo ID khách hàng ổn định và duy nhất và nhóm các hồ sơ liên quan thành một cụm.

:::image type="content" source="media/m3_unify.png" alt-text="Khi phối trang trong quá trình hợp nhất dữ liệu, một bảng với các trường đã hợp nhất xác định hồ sơ khách hàng hợp nhất sẽ xuất hiện.":::

## <a name="review-and-update-the-customer-fields"></a>Xem xét và cập nhật các trường khách hàng

1. Xem lại danh sách các trường sẽ được hợp nhất trong **Lĩnh vực khách hàng** tab của bảng. Thực hiện bất kỳ thay đổi nào nếu có.

   1. Đối với bất kỳ trường kết hợp nào, bạn có thể:
      - [Chỉnh sửa](#edit-a-merged-field)
      - [Đổi tên](#rename-fields)
      - [Tách biệt](#separate-merged-fields)
      - [Loại trừ](#exclude-fields)
      - [Di chuyển lên hoặc xuống](#change-the-order-of-fields)

   1. Đối với bất kỳ trường đơn lẻ nào, bạn có thể:
      - [Kết hợp các trường](#combine-fields-manually)
      - [Kết hợp một nhóm trường](#combine-a-group-of-fields)
      - [Đổi tên](#rename-fields)
      - [Loại trừ](#exclude-fields)
      - [Di chuyển lên hoặc xuống](#change-the-order-of-fields)

1. Tùy ý, [tạo cấu hình ID khách hàng](#configure-customer-id-generation).

1. Tùy ý, [nhóm hồ sơ thành các hộ gia đình hoặc cụm](#group-profiles-into-households-or-clusters).

> [!div class="nextstepaction"]
> [Bước tiếp theo: Xem xét sự hợp nhất](review-unification.md)

### <a name="edit-a-merged-field"></a>Chỉnh sửa trường đã hợp nhất

1. Chọn một trường đã hợp nhất và chọn **Chỉnh sửa**. Ngăn Kết hợp các trường hiển thị.

1. Chỉ định cách kết hợp hoặc hợp nhất các trường từ một trong ba tùy chọn:
    - **Quan trọng**: Xác định giá trị chiến thắng dựa trên xếp hạng quan trọng được chỉ định cho các trường tham gia. Đây là tùy chọn phối mặc định. Chọn **Di chuyển lên/xuống** để thiết lập xếp hạng mức độ quan trọng.

      :::image type="content" source="media/importance-merge-option.png" alt-text="Tùy chọn quan trọng trong hộp thoại hợp nhất các trường.":::

    - **Gần đây nhất**: Xác định giá trị chiến thắng dựa trên giá trị gần đây nhất. Yêu cầu ngày hoặc trường số cho mọi thực thể tham gia trong phạm vi trường hợp nhất để xác định giá trị gần đây.

      :::image type="content" source="media/recency-merge-option.png" alt-text="Tùy chọn gần đây trong hộp thoại hợp nhất các trường.":::

    - **Cách đây xa nhất**: Xác định giá trị chiến thắng dựa trên giá trị cách đây xa nhất. Yêu cầu ngày hoặc trường số cho mọi thực thể tham gia trong phạm vi trường hợp nhất để xác định giá trị gần đây.

1. Bạn có thể thêm nhiều trường khác để tham gia vào quá trình hợp nhất.

1. Bạn có thể đổi tên trường đã hợp nhất.

1. Chọn **Xong** để áp dụng các thay đổi của bạn.

### <a name="rename-fields"></a>Đổi tên các trường

Thay đổi tên hiển thị của các trường được hợp nhất hoặc tách biệt. Bạn không thể thay đổi tên của thực thể đầu ra.

1. Chọn trường và chọn **Đổi tên**.

1. Nhập tên hiển thị mới.

1. Chọn **Xong**.

### <a name="separate-merged-fields"></a>Tách trường đã hợp nhất

Để tách các trường đã hợp nhất, hãy tìm thuộc tính trong bảng. Các trường được tách sẽ hiển thị dưới dạng các điểm dữ liệu riêng lẻ trên hồ sơ khách hàng hợp nhất.

1. Chọn trường đã hợp nhất và chọn **Các trường riêng biệt**.

1. Xác nhận việc tách trường.

### <a name="exclude-fields"></a>Loại trừ các trường

Loại trừ trường đã hợp nhất hoặc trường riêng biệt khỏi hồ sơ khách hàng hợp nhất. Nếu trường được sử dụng trong các quy trình khác, ví dụ như trong một phân khúc, hãy xóa trường khỏi các quy trình này trước khi loại trừ trường khỏi hồ sơ khách hàng.

1. Chọn một trường và chọn **Loại trừ**.

1. Xác nhận việc loại trừ.

Để xem danh sách tất cả các trường bị loại trừ, hãy chọn **Các trường bị loại trừ**. Nếu cần, bạn có thể đọc lại trường bị loại trừ.

### <a name="change-the-order-of-fields"></a>Thay đổi thứ tự trường

Một số thực thể chứa nhiều chi tiết hơn những thực thể khác. Nếu một thực thể bao gồm dữ liệu mới nhất về một trường, bạn có thể ưu tiên thực thể này hơn khi hợp nhất các giá trị.

1. Chọn trường.
  
1. Chọn **Di chuyển lên / xuống** để đặt thứ tự hoặc kéo và thả chúng vào vị trí mong muốn.

### <a name="combine-fields-manually"></a>Kết hợp các trường theo cách thủ công

Kết hợp các trường đã tách để tạo thuộc tính được hợp nhất.

1. Lựa chọn **Kết hợp** > **Lĩnh vực**. Ngăn Kết hợp các trường hiển thị.

1. Chỉ định chính sách hợp nhất người chiến thắng trong trình đơn thả xuống **Kết hợp các trường theo**.

1. Lựa chọn **Thêm các lĩnh vực** để kết hợp nhiều trường hơn.

1. Đặt **Tên** và **Tên trường đầu ra**.

1. Chọn **Xong** để áp dụng các thay đổi.

### <a name="combine-a-group-of-fields"></a>Kết hợp một nhóm trường

Coi một nhóm trường như một đơn vị duy nhất. Ví dụ: nếu bản ghi của chúng tôi chứa các trường Address1, Address2, City, State và Zip, chúng tôi không muốn hợp nhất trong Address2 của một bản ghi khác, vì nghĩ rằng nó sẽ làm cho dữ liệu của chúng tôi đầy đủ hơn.

1. Lựa chọn **Kết hợp** > **Nhóm lĩnh vực**.

1. Chỉ định chính sách hợp nhất người chiến thắng trong **Xếp hạng các nhóm theo** thả xuống.

1. Lựa chọn **cộng** và chọn nếu bạn muốn thêm nhiều trường hoặc nhóm vào các trường.

1. Cung cấp một **Tên** và một **Tên đầu ra** cho mọi trường kết hợp.

1. Cung cấp một **Tên** cho nhóm trường.

1. Chọn **Xong** để áp dụng các thay đổi.

## <a name="configure-customer-id-generation"></a>Định cấu hình tạo ID khách hàng

Xác định cách tạo giá trị ID khách hàng, giá trị nhận dạng hồ sơ khách hàng duy nhất. Bước hợp nhất các trường trong quy trình hợp nhất dữ liệu tạo ra mã định danh hồ sơ khách hàng duy nhất. Định danh là *ID khách hàng* bên trong *khách hàng* thực thể là kết quả của quá trình hợp nhất dữ liệu.

Các *ID khách hàng*  dựa trên một băm của giá trị đầu tiên của khóa chính chiến thắng không rỗng. Các khóa này đến từ các thực thể được sử dụng trong hợp nhất dữ liệu và chịu ảnh hưởng của thứ tự đối sánh.Vì vậy, ID khách hàng đã tạo có thể thay đổi khi giá trị khóa chính thay đổi trong thực thể chính của đơn hàng đối sánh. Giá trị khóa chính có thể không phải lúc nào cũng đại diện cho cùng một khách hàng.

Khi đặt cấu hình ID khách hàng ổn định, bạn có thể tránh được hành vi đó.

1. Chọn tab **Khóa**.

1. Di chuột trên **ID khách hàng** hàng và chọn **Định cấu hình**.
   :::image type="content" source="media/customize-stable-id.png" alt-text="Kiểm soát để tùy chỉnh quy trình tạo ID.":::

1. Chọn tối đa 5 trường sẽ bao gồm một ID khách hàng duy nhất và ổn định hơn. Thay vào đó, các bản ghi không khớp với cấu hình của bạn sử dụng ID do hệ thống đặt cấu hình.  

1. Chọn **Xong**.

## <a name="group-profiles-into-households-or-clusters"></a>Nhóm hồ sơ thành các hộ gia đình hoặc cụm

Bạn có thể xác định các quy tắc để nhóm các cấu hình liên quan thành một cụm. Hiện tại có 2 loại cụm – cụm hộ gia đình và cụm tùy chỉnh. Hệ thống tự động chọn một gia đình có các quy tắc định sẵn nếu thực thể *Khách hàng* chứa trường ngữ nghĩa *Person.LastName* và *Location.Address*. Bạn cũng có thể tạo một cụm có các quy tắc và điều kiện của riêng mình, tương tự như [quy tắc so khớp](match-entities.md#define-rules-for-match-pairs).

1. Lựa chọn **Nâng cao** > **Tạo cụm**.

   :::image type="content" source="media/create-cluster.png" alt-text="Điều khiển để tạo một cụm mới.":::

1. Chọn giữa **Hộ gia đình** hoặc một cụm **Tùy chỉnh**. Nếu trường ngữ nghĩa *Person.LastName* và *Location.Address* có trong thực thể *Customer*, hộ gia đình sẽ tự động được chọn.

1. Cung cấp tên cho cụm rồi chọn **Xong**.

1. Chọn tab **Cụm** để tìm cụm mà bạn đã tạo.

1. Chỉ định các quy tắc và điều kiện để xác định cụm của bạn.

1. Chọn **Xong**. Cụm được tạo khi quá trình hợp nhất hoàn tất. Các số nhận dạng cụm được thêm vào dưới dạng các trường mới vào *khách hàng* thực thể.

> [!div class="nextstepaction"]
> [Bước tiếp theo: Xem xét sự hợp nhất](review-unification.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
