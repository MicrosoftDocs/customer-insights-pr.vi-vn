---
title: Trộn các thực thể trong hợp nhất dữ liệu
description: Trộn các thực thể để tạo hồ sơ khách hàng hợp nhất.
ms.date: 04/16/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 4ad06a0baf57e612fc0e0214dfd23d28e7d2b6be
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896537"
---
# <a name="merge-entities"></a>Hợp nhất thực thể

Giai đoạn hợp nhất là giai đoạn cuối cùng trong quy trình hợp nhất dữ liệu. Mục đích của nó là đối chiếu dữ liệu xung đột. Ví dụ về dữ liệu xung đột có thể bao gồm tên khách hàng được tìm thấy trong hai bộ dữ liệu của bạn nhưng hiển thị hơi khác nhau trong mỗi dữ liệu ("Grant Marshall" so với "Grant Marshal") hoặc số điện thoại khác nhau ở định dạng (617-803-091X so với 617803091X). Việc hợp nhất các điểm dữ liệu xung đột đó được thực hiện trên cơ sở từng thuộc tính.

Sau khi hoàn thành [giai đoạn so khớp](match-entities.md), bạn có thể bắt đầu giai đoạn hợp nhất bằng cách chọn lát **Hợp nhất** trên trang **Hợp nhất**.

## <a name="review-system-recommendations"></a>Xem lại đề xuất hệ thống

Trên trang **Hợp nhất**, bạn có thể chọn và loại trừ các thuộc tính được hợp nhất trong thực thể hồ sơ khách hàng đã hợp nhất của bạn (kết quả của quá trình cấu hình). Một số thuộc tính được hệ thống tự động hợp nhất.

### <a name="view-merged-attributes"></a>Xem thuộc tính đã hợp nhất

Để xem các thuộc tính được bao gồm trong một trong các thuộc tính được hợp nhất tự động của bạn, hãy chọn thuộc tính được hợp nhất đó. Hai thuộc tính cấu thành thuộc tính được hợp nhất đó sẽ hiển thị trong hai hàng mới bên dưới thuộc tính được hợp nhất.

> [!div class="mx-imgBorder"]
> ![Chọn thuộc tính đã hợp nhất](media/configure-data-merge-profile-attributes.png "Chọn thuộc tính đã hợp nhất")

### <a name="separate-merged-attributes"></a>Tách thuộc tính đã hợp nhất

Để tách hoặc hủy hợp nhất tách bất kỳ thuộc tính được hợp nhất tự động nào, hãy tìm thuộc tính đó trong bảng **Thuộc tính hồ sơ**.

1. Chọn nút dấu chấm lửng (...).
  
2. Trong danh sách thả xuống, chọn **Tách các trường**.

### <a name="remove-merged-attributes"></a>Xóa thuộc tính đã hợp nhất

Để loại trừ một thuộc tính khỏi thực thể hồ sơ khách hàng cuối cùng, hãy tìm thuộc tính đó trong bảng **Thuộc tính hồ sơ**.

1. Chọn nút dấu chấm lửng (...).
  
2. Trong danh sách thả xuống, chọn **Không hợp nhất**.

   Thuộc tính được chuyển đến phần **Xóa khỏi hồ sơ khách hàng**.

## <a name="manually-add-a-merged-attribute"></a>Thêm thủ công một thuộc tính hợp nhất

Để thêm một thuộc tính được hợp nhất, hãy đi đến trang **Hợp nhất**.

1. Chọn **Thêm thuộc tính đã hợp nhất**.

2. Cung cấp một **Tên** để xác định thuộc tính đó trên trang **Hợp nhất** vào lúc khác.

3. Hoặc bạn có thể cung cấp một **Tên hiển thị** để xuất hiện trong thực thể Hồ sơ khách hàng hợp nhất.

4. Cấu hình **Chọn các thuộc tính trùng lặp** để chọn các thuộc tính mà bạn muốn hợp nhất từ các thực thể phù hợp. Bạn cũng có thể tìm kiếm các thuộc tính.

5. Đặt **Xếp hạng theo mức độ quan trọng** để ưu tiên một thuộc tính so với các thuộc tính khác. Ví dụ: nếu thực thể *WebAccountCSV* bao gồm dữ liệu chính xác nhất về thuộc tín *Tên đầy đủ*, thì bạn có thể ưu tiên thực thể này so với *ContactCSV* bằng việc chọn *WebAccountCSV*. Kết quả là *WebAccountCSV* chuyển sang ưu tiên hàng đầu, trong khi *ContactCSV* chuyển sang ưu tiên thứ hai khi kéo các giá trị cho thuộc tính *Họ và tên*.

## <a name="run-your-merge"></a>Chạy hợp nhất của bạn

Cho dù bạn hợp nhất thủ công các thuộc tính hay để hệ thống hợp nhất chúng, bạn luôn có thể chạy hợp nhất. Chọn **Chạy** trên trang **Hợp nhất** để bắt đầu quy trình.

> [!div class="mx-imgBorder"]
> ![Lưu và chạy hợp nhất dữ liệu](media/configure-data-merge-save-run.png "Lưu và chạy hợp nhất dữ liệu")

Để thực hiện các thay đổi bổ sung và chạy lại bước này, bạn có thể hủy hợp nhất đang thực hiện. Chọn **Đang làm mới ...** rồi chọn **Hủy công việc**  trong ngăn bên xuất hiện.

Sau khi văn bản **Đang làm mới ...** thay đổi thành **Thành công**, quá trình hợp nhất đã hoàn tất và đã giải quyết mẫu thuẫn trong dữ liệu theo các chính sách bạn đã xác định. Các thuộc tính được hợp nhất và chưa được hợp nhất được bao gồm trong thực thể hồ sơ hợp nhất. Các thuộc tính bị loại trừ chưa được bao gồm trong thực thể hồ sơ hợp nhất.

Nếu đó không phải là lần đầu tiên bạn thực hiện hợp nhất thành công, tất cả các quy trình hạ nguồn, bao gồm làm giàu, phân đoạn và các biện pháp sẽ tự động chạy lại. Sau khi tất cả các quy trình hạ nguồn đã được chạy lại, hồ sơ khách hàng phản ánh bất kỳ thay đổi nào bạn đã thực hiện.

> [!TIP]
> Có [6 loại trạng thái](system.md#status-types) cho các nhiệm vụ/quy trình. Ngoài ra, hầu hết các quy trình [phụ thuộc vào các quá trình hạ nguồn khác](system.md#refresh-policies). Bạn có thể chọn trạng thái của một quy trình để xem chi tiết về tiến trình của toàn bộ công việc. Sau khi chọn **Xem chi tiết** đối với một trong các tác vụ của công việc, bạn sẽ tìm thấy thông tin bổ sung: thời gian xử lý, ngày xử lý gần nhất và tất cả các lỗi và cảnh báo liên quan đến tác vụ.

## <a name="next-step"></a>Bước tiếp theo

Đặt cấu hình [hoạt động](activities.md), [nội dung phong phú](enrichment-hub.md) hoặc [mối quan hệ](relationships.md) để hiểu thêm về khách hàng của bạn.

Nếu bạn đã định cấu hình các hoạt động, nội dung phong phú hoặc các mối quan hệ hoặc nếu bạn đã xác định các phân khúc, chúng sẽ được xử lý tự động để sử dụng dữ liệu khách hàng mới nhất.




[!INCLUDE[footer-include](../includes/footer-banner.md)]