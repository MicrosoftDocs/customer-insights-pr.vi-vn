---
title: Trộn các thực thể trong hợp nhất dữ liệu
description: Trộn các thực thể để tạo hồ sơ khách hàng hợp nhất.
ms.date: 01/28/2022
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-merge
ms.openlocfilehash: eb08ab38d23bf22a17896b63c93e6821431b002a
ms.sourcegitcommit: 3807202283dd116a30f900a163d8141db621e5a8
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 01/28/2022
ms.locfileid: "8046649"
---
# <a name="merge-entities"></a>Hợp nhất thực thể

Giai đoạn hợp nhất là giai đoạn cuối cùng trong quy trình hợp nhất dữ liệu. Mục đích của nó là đối chiếu dữ liệu xung đột. Ví dụ về dữ liệu xung đột có thể bao gồm tên khách hàng được tìm thấy trong hai bộ dữ liệu của bạn nhưng hiển thị hơi khác nhau trong mỗi dữ liệu ("Grant Marshall" so với "Grant Marshal") hoặc số điện thoại khác nhau ở định dạng (617-803-091X so với 617803091X). Việc hợp nhất các điểm dữ liệu xung đột đó được thực hiện trên cơ sở từng thuộc tính.

:::image type="content" source="media/merge-fields-page.png" alt-text="Khi phối trang trong quá trình hợp nhất dữ liệu, một bảng với các trường đã hợp nhất xác định hồ sơ khách hàng hợp nhất sẽ xuất hiện.":::

Sau khi hoàn thành [giai đoạn so khớp](match-entities.md), bạn có thể bắt đầu giai đoạn hợp nhất bằng cách chọn lát **Hợp nhất** trên trang **Hợp nhất**.

## <a name="review-system-recommendations"></a>Xem lại đề xuất hệ thống

Trong mục **Dữ liệu** > **Hợp nhất** > **Hợp nhất**, bạn chọn và loại trừ các thuộc tính để hợp nhất trong thực thể hồ sơ khách hàng hợp nhất của mình. Hồ sơ khách hàng hợp nhất là kết quả của quá trình hợp nhất dữ liệu. Một số thuộc tính được hệ thống tự động hợp nhất.

Để xem các thuộc tính có trong thuộc tính được hợp nhất tự động của bạn, hãy chọn thuộc tính được hợp nhất đó trong tab **Trường khách hàng** của bảng. Thuộc tính cấu thành thuộc tính được hợp nhất đó sẽ hiển thị trong hai hàng mới bên dưới thuộc tính được hợp nhất.

## <a name="separate-rename-exclude-and-edit-merged-fields"></a>Tách, đổi tên, loại trừ và chỉnh sửa các trường đã hợp nhất

Bạn có thể thay đổi cách hệ thống xử lý các thuộc tính đã hợp nhất để tạo hồ sơ khách hàng hợp nhất. Chọn **Hiển thị thêm** và chọn những phần bạn muốn thay đổi.

:::image type="content" source="media/manage-merged-attributes.png" alt-text="Các tùy chọn trong menu thả xuống Hiển thị thêm để quản lý các thuộc tính đã hợp nhất.":::

Xem phần sau đây để biết thêm thông tin.

## <a name="separate-merged-fields"></a>Tách trường đã hợp nhất

Để tách các trường đã hợp nhất, hãy tìm thuộc tính trong bảng. Các trường được tách sẽ hiển thị dưới dạng các điểm dữ liệu riêng lẻ trên hồ sơ khách hàng hợp nhất. 

1. Chọn trường hợp nhất.
  
1. Chọn **Hiển thị thêm** và chọn **Các trường riêng biệt**.
 
1. Xác nhận việc tách trường.

1. Chọn **Lưu** và **Chạy** để thay đổi.

## <a name="rename-merged-fields"></a>Đổi tên các trường đã hợp nhất

Thay đổi tên hiển thị của các thuộc tính đã hợp nhất. Bạn không thể thay đổi tên của thực thể đầu ra.

1. Chọn trường hợp nhất.
  
1. Chọn **Hiển thị thêm** và chọn **Đổi tên**.

1. Xác nhận tên hiển thị đã thay đổi. 

1. Chọn **Lưu** và **Chạy** để thay đổi.

## <a name="exclude-merged-fields"></a>Các trường đã hợp nhất bị loại trừ

Loại trừ một thuộc tính khỏi hồ sơ khách hàng hợp nhất. Nếu trường được sử dụng trong các quy trình khác, ví dụ như trong một phân khúc, hãy xóa trường khỏi các quy trình này trước khi loại trừ trường khỏi hồ sơ khách hàng. 

1. Chọn trường đã hợp nhất.
  
1. Chọn **Hiển thị thêm** và chọn **Loại trừ**.

1. Xác nhận việc loại trừ.

1. Chọn **Lưu** và **Chạy** để thay đổi. 

Trên trang **Hợp nhất**, chọn **Các trường bị loại trừ** để xem danh sách tất cả các trường đã loại trừ. Bạn có thể thêm lại các trường bị loại trừ trong ngăn này.

## <a name="edit-a-merged-field"></a>Chỉnh sửa trường đã hợp nhất

1.  Chọn trường đã hợp nhất.

1.  Chọn **Hiển thị thêm** và chọn **Chỉnh sửa**.

1.  Chỉ định cách kết hợp hoặc hợp nhất các trường từ một trong ba tùy chọn:
    - **Quan trọng**: Xác định giá trị chiến thắng dựa trên xếp hạng quan trọng được chỉ định cho các trường tham gia. Đây là tùy chọn phối mặc định. Chọn **Di chuyển lên/xuống** để thiết lập xếp hạng mức độ quan trọng.
    :::image type="content" source="media/importance-merge-option.png" alt-text="Tùy chọn quan trọng trong hộp thoại hợp nhất các trường."::: 
    - **Gần đây nhất**: Xác định giá trị chiến thắng dựa trên giá trị gần đây nhất. Yêu cầu ngày hoặc trường số cho mọi thực thể tham gia trong phạm vi trường hợp nhất để xác định giá trị gần đây.
    :::image type="content" source="media/recency-merge-option.png" alt-text="Tùy chọn gần đây trong hộp thoại hợp nhất các trường.":::
    - **Cách đây xa nhất**: Xác định giá trị chiến thắng dựa trên giá trị cách đây xa nhất. Yêu cầu ngày hoặc trường số cho mọi thực thể tham gia trong phạm vi trường hợp nhất để xác định giá trị gần đây.

1.  Bạn có thể thêm nhiều trường khác để tham gia vào quá trình hợp nhất.

1.  Bạn có thể đổi tên trường đã hợp nhất.

1. Chọn **Xong** để áp dụng các thay đổi của bạn.

1. Chọn **Lưu** và **Chạy** để thay đổi. 

## <a name="combine-fields-manually"></a>Kết hợp các trường theo cách thủ công

Chỉ định một thuộc tính đã hợp nhất theo cách thủ công.

1. Trên **Hợp nhất** trang, chọn **Phối hợp**.

1. Chọn **Lĩnh vực** lựa chọn.

1. Chỉ định chính sách hợp nhất người chiến thắng trong trình đơn thả xuống **Kết hợp các trường theo**.

1. Chọn trường để thêm vào. Chọn **Thêm trường** để kết hợp nhiều trường.

1. Đặt **Tên** và **Tên trường đầu ra**.

1. Chọn **Xong** để áp dụng các thay đổi.

1. Chọn **Lưu** và **Chạy** để thay đổi. 

## <a name="combine-a-group-of-fields"></a>Kết hợp một nhóm trường

Coi một nhóm trường như một đơn vị duy nhất. Ví dụ: khi bản ghi của chúng tôi chứa các trường Address1, Address2, City, State và Zip. Chúng tôi có thể không muốn hợp nhất trong Address2 của một bản ghi khác, vì nghĩ rằng nó sẽ làm cho dữ liệu của chúng tôi đầy đủ hơn

1. Trên **Hợp nhất** trang, chọn **Phối hợp**.

1. Chọn **Nhóm lĩnh vực** lựa chọn.

1. Chỉ định chính sách hợp nhất người chiến thắng trong **Xếp hạng các nhóm theo** trình đơn thả xuống.

1. Lựa chọn **cộng** và chọn nếu bạn muốn thêm nhiều trường hoặc nhóm bổ sung vào các trường.

1. Cung cấp một **Tên** và một **Tên đầu ra** cho mọi trường kết hợp.

1. Cung cấp một **Tên** cho nhóm trường. 

1. Chọn **Xong** để áp dụng các thay đổi.

1. Chọn **Lưu** và **Chạy** để thay đổi.

## <a name="change-the-order-of-fields"></a>Thay đổi thứ tự trường

Một số thực thể chứa nhiều chi tiết hơn những thực thể khác. Nếu một thực thể bao gồm dữ liệu mới nhất về một trường, bạn có thể ưu tiên thực thể này hơn khi hợp nhất các giá trị.

1. Chọn trường hợp nhất.
  
1. Chọn **Hiển thị thêm** và chọn **Chỉnh sửa**.

1. Trong ngăn **Kết hợp các trường**, chọn **Di chuyển lên/xuống** để đặt thứ tự hoặc kéo và thả các trường vào vị trí mong muốn.

1. Xác nhận thay đổi.

1. Chọn **Lưu** và **Chạy** để thay đổi.

## <a name="configure-customer-id-generation"></a>Đặt cấu hình tạo ID khách hàng 

Sau khi đặt cấu hình các trường hợp nhất, bạn có thể xác định cách tạo giá trị CustomerId, mã nhận dạng hồ sơ khách hàng duy nhất. Bước hợp nhất trong quy trình hợp nhất dữ liệu tạo ra mã nhận dạng hồ sơ khách hàng duy nhất. Mã định danh là CustomerId trong thực thể *Khách hàng* là kết quả của quá trình hợp nhất dữ liệu. 

CustomerId trong thực thể Khách hàng dựa trên hàm băm của giá trị đầu tiên của các khóa chính chiến thắng không rỗng. Các khóa này đến từ các thực thể được sử dụng trong giai đoạn so khớp và hợp nhất, đồng thời chịu ảnh hưởng của thứ tự so khớp. Vì vậy, CustomerID đã tạo có thể thay đổi khi giá trị khóa chính thay đổi trong thực thể chính của thứ tự so khớp. Giá trị khóa chính có thể không phải lúc nào cũng đại diện cho cùng một khách hàng.

Khi đặt cấu hình ID khách hàng ổn định, bạn có thể tránh được hành vi đó.

**Đặt cấu hình một ID khách hàng duy nhất**

1. Chuyển đến **Thống nhất** > **Hợp nhất**.

1. Chọn tab **Khóa**. 

1. Di chuột trên hàng **CustomerId** và chọn tùy chọn **Đặt cấu hình**.
   :::image type="content" source="media/customize-stable-id.png" alt-text="Kiểm soát để tùy chỉnh quy trình tạo ID.":::

1. Chọn tối đa 5 trường sẽ bao gồm một ID khách hàng duy nhất và ổn định hơn. Thay vào đó, các bản ghi không khớp với cấu hình của bạn sử dụng ID do hệ thống đặt cấu hình.  

1. Chọn **Xong** và chạy quy trình hợp nhất để áp dụng các thay đổi của bạn.

## <a name="group-profiles-into-households-or-clusters"></a>Nhóm hồ sơ thành các hộ gia đình hoặc cụm

Trong quá trình đặt cấu hình tạo hồ sơ khách hàng, bạn có thể xác định quy tắc để nhóm các hồ sơ liên quan vào một cụm. Hiện tại có 2 loại cụm – cụm hộ gia đình và cụm tùy chỉnh. Hệ thống tự động chọn một gia đình có các quy tắc định sẵn nếu thực thể *Khách hàng* chứa trường ngữ nghĩa *Person.LastName* và *Location.Address*. Bạn cũng có thể tạo một cụm có các quy tắc và điều kiện của riêng mình, tương tự như [quy tắc so khớp](match-entities.md#define-rules-for-match-pairs).

**Xác định một hộ gia đình hoặc một cụm**

1. Chuyển đến **Thống nhất** > **Hợp nhất**.

1. Trên tab **Hợp nhất**, chọn **Nâng cao** > **Tạo cụm**.

   :::image type="content" source="media/create-cluster.png" alt-text="Điều khiển để tạo một cụm mới.":::

1. Chọn giữa **Hộ gia đình** hoặc một cụm **Tùy chỉnh**. Nếu trường ngữ nghĩa *Person.LastName* và *Location.Address* có trong thực thể *Customer*, hộ gia đình sẽ tự động được chọn.

1. Cung cấp tên cho cụm rồi chọn **Xong**.

1. Chọn tab **Cụm** để tìm cụm mà bạn đã tạo.

1. Chỉ định các quy tắc và điều kiện để xác định cụm của bạn.

1. Chọn **Chạy** để chạy quá trình hợp nhất và tạo cụm.

Sau khi chạy quá trình hợp nhất, các giá trị nhận dạng cụm được thêm thành các trường mới vào thực thể *Khách hàng*.

## <a name="run-your-merge"></a>Chạy hợp nhất của bạn

Cho dù bạn hợp nhất thủ công các thuộc tính hay để hệ thống hợp nhất chúng, bạn luôn có thể chạy hợp nhất. Chọn **Chạy** trên trang **Hợp nhất** để bắt đầu quy trình.

> [!div class="mx-imgBorder"]
> ![Lưu và chạy hợp nhất dữ liệu.](media/configure-data-merge-save-run.png "Lưu và chạy hợp nhất dữ liệu")

Chọn **Chỉ chạy Hợp nhất** nếu bạn chỉ muốn xem kết quả đầu ra được phản ánh trong thực thể khách hàng hợp nhất. Các quy trình xuôi dòng sẽ được làm mới như [đã xác định trong lịch trình làm mới](system.md#schedule-tab).

Chọn **Chạy các quy trình Hợp nhất và xuôi dòng** để làm mới hệ thống với các thay đổi của bạn. Tất cả các quy trình, bao gồm tăng cường, phân khúc và đo lường sẽ tự động chạy lại. Sau khi tất cả các quy trình xuôi dòng đã hoàn tất, hồ sơ khách hàng hiển thị mọi thay đổi bạn đã thực hiện.

Để thực hiện thêm nhiều thay đổi và chạy lại bước, bạn có thể hủy quá trình hợp nhất đang diễn ra. Chọn **Đang làm mới ...** rồi chọn **Hủy công việc**  trong ngăn bên xuất hiện.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

:::image type="content" source="media/process-detail-path.png" alt-text="Đường dẫn xem chi tiết để xử lý chi tiết từ liên kết trạng thái nhiệm vụ.":::

## <a name="next-step"></a>Bước tiếp theo

Đặt cấu hình [hoạt động](activities.md), [nội dung phong phú](enrichment-hub.md) hoặc [mối quan hệ](relationships.md) để hiểu thêm về khách hàng của bạn.

Nếu bạn đã đặt cấu hình các hoạt động, quá trình tăng cường hoặc phân khúc, những phần này sẽ được xử lý tự động để sử dụng dữ liệu khách hàng mới nhất.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
