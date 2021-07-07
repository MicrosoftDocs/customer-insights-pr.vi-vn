---
title: Trộn các thực thể trong hợp nhất dữ liệu
description: Trộn các thực thể để tạo hồ sơ khách hàng hợp nhất.
ms.date: 05/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 86ab3cefa70e5fab4bdb27cde363adee26efee4c
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305685"
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

1. Chọn trường hợp nhất.
  
1. Chọn **Hiển thị thêm** và chọn **Loại trừ**.

1. Xác nhận việc loại trừ.

1. Chọn **Lưu** và **Chạy** để thay đổi. 

Trên trang **Hợp nhất**, chọn **Các trường bị loại trừ** để xem danh sách tất cả các trường đã loại trừ. Bạn có thể thêm lại các trường bị loại trừ trong ngăn này.

## <a name="manually-combine-fields"></a>Các trường kết hợp theo cách thủ công

Chỉ định một thuộc tính đã hợp nhất theo cách thủ công. 

1. Trên trang **Hợp nhất**, chọn **Kết hợp các trường**.

1. Đặt **Tên** và **Tên trường đầu ra**.

1. Chọn trường để thêm vào. Chọn **Thêm trường** để kết hợp nhiều trường.

1. Xác nhận việc loại trừ.

1. Chọn **Lưu** và **Chạy** để thay đổi. 

## <a name="change-the-order-of-fields"></a>Thay đổi thứ tự trường

Một số thực thể chứa nhiều chi tiết hơn những thực thể khác. Nếu một thực thể bao gồm dữ liệu mới nhất về một trường, bạn có thể ưu tiên thực thể này hơn khi hợp nhất các giá trị.

1. Chọn trường hợp nhất.
  
1. Chọn **Hiển thị thêm** và chọn **Chỉnh sửa**.

1. Trong ngăn **Kết hợp các trường**, chọn **Di chuyển lên/xuống** để đặt thứ tự hoặc kéo và thả các trường vào vị trí mong muốn.

1. Xác nhận thay đổi.

1. Chọn **Lưu** và **Chạy** để thay đổi.

## <a name="run-your-merge"></a>Chạy hợp nhất của bạn

Cho dù bạn hợp nhất thủ công các thuộc tính hay để hệ thống hợp nhất chúng, bạn luôn có thể chạy hợp nhất. Chọn **Chạy** trên trang **Hợp nhất** để bắt đầu quy trình.

> [!div class="mx-imgBorder"]
> ![Lưu và chạy hợp nhất dữ liệu](media/configure-data-merge-save-run.png "Lưu và chạy hợp nhất dữ liệu")

Chọn **Chỉ chạy Hợp nhất** nếu bạn chỉ muốn xem kết quả đầu ra được phản ánh trong thực thể khách hàng hợp nhất. Các quy trình xuôi dòng sẽ được làm mới như [đã xác định trong lịch trình làm mới](system.md#schedule-tab).

Chọn **Chạy các quy trình Hợp nhất và xuôi dòng** để làm mới hệ thống với các thay đổi của bạn. Tất cả các quy trình, bao gồm tăng cường, phân đoạn và đo lường sẽ tự động chạy lại. Sau khi tất cả các quy trình xuôi dòng đã hoàn tất, hồ sơ khách hàng hiển thị mọi thay đổi bạn đã thực hiện.

Để thực hiện thêm nhiều thay đổi và chạy lại bước, bạn có thể hủy quá trình hợp nhất đang diễn ra. Chọn **Đang làm mới ...** rồi chọn **Hủy công việc**  trong ngăn bên xuất hiện.

> [!TIP]
> Có [6 loại trạng thái](system.md#status-types) cho các nhiệm vụ/quy trình. Ngoài ra, hầu hết các quy trình [phụ thuộc vào các quá trình hạ nguồn khác](system.md#refresh-policies). Bạn có thể chọn trạng thái của một quy trình để xem chi tiết về tiến trình của toàn bộ công việc. Sau khi chọn **Xem chi tiết** đối với một trong các tác vụ của công việc, bạn sẽ tìm thấy thông tin bổ sung: thời gian xử lý, ngày xử lý gần nhất và tất cả các lỗi và cảnh báo liên quan đến tác vụ.

## <a name="next-step"></a>Bước tiếp theo

Định cấu hình [hoạt động](activities.md), [nội dung phong phú](enrichment-hub.md) hoặc [mối quan hệ](relationships.md) để hiểu thêm về khách hàng của bạn.

Nếu bạn đã định cấu hình các hoạt động, quá trình tăng cường hoặc phân đoạn, những phần này sẽ được xử lý tự động để sử dụng dữ liệu khách hàng mới nhất.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
