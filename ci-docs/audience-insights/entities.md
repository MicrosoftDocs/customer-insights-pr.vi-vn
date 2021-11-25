---
title: Thực thể và tập hợp dữ liệu
description: Xem dữ liệu trên trang Thực thể.
ms.date: 11/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 2a207a3dcad4bf192efb6ee1554195f10b19670b
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732107"
---
# <a name="entities-in-audience-insights"></a>Các thực thể trong thông tin chi tiết về đối tượng

Sau khi [định cấu hình nguồn dữ liệu](data-sources.md), hãy truy cập trang [Thực thể](data-sources.md) để đánh giá chất lượng của dữ liệu được nhập. Các thực thể được coi là tập hợp dữ liệu. Nhiều khả năng của Dynamics 365 Customer Insights được xây dựng xung quanh các thực thể này. Việc xem xét chúng một cách chi tiết có thể giúp bạn xác thực đầu ra của những khả năng.

Trang **Thực thể** liệt kê các thực thể và bao gồm một số cột:

- **Tên**: Tên của thực thể dữ liệu của bạn. Nếu bạn thấy biểu tượng cảnh báo bên cạnh tên thực thể, điều đó có nghĩa là dữ liệu cho thực thể đó không tải thành công.
- **Nguồn**: Hiển thị loại nguồn dữ liệu được nhập vào thực thể
- **Người tạo**: Tên của người đã tạo thực thể
- **Ngày tạo**: Ngày và giờ tạo thực thể
- **Đã cập nhật** : Tên của người đã cập nhật thực thể
- **Trạng thái** : Thông tin chi tiết về bản cập nhật cuối cùng của thực thể

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="explore-a-specific-entitys-data"></a>Khám phá dữ liệu của một thực thể cụ thể

Chọn một thực thể để khám phá các trường và bản ghi khác nhau được bao gồm trong thực thể đó.

> [!div class="mx-imgBorder"]
> ![Chọn thực thể.](media/data-manager-entities-data.png "Chọn thực thể")

- Tab **Dữ liệu** hiển thị một bảng liệt kê chi tiết về các bản ghi riêng lẻ của thực thể.

> [!div class="mx-imgBorder"]
> ![Bảng trường.](media/data-manager-entities-fields.PNG "Bảng trường")

- Tab **Thuộc tính** được chọn theo mặc định và hiển thị một bảng để bạn xem xét thông tin chi tiết của thực thể đã chọn, chẳng hạn như tên trường, kiểu dữ liệu và loại thực thể. Cột **Loại** hiển thị các loại liên kết Common Data Model được tự động xác định bởi hệ thống hoặc [được ánh xạ thủ công](map-entities.md) bởi người dùng. Những kiểu ngữ nghĩa này có thể khác với kiểu dữ liệu của thuộc tính. Ví dụ: trường *Email* bên dưới có một kiểu dữ liệu *Văn bản* nhưng kiểu Common Data Model (ngữ nghĩa) có thể là *Email* hoặc *Địa chỉ email*.

> [!NOTE]
> Cả hai bảng chỉ hiển thị một mẫu dữ liệu của thực thể của bạn. Để xem tập dữ liệu đầy đủ, hãy đi tới trang **Nguồn dữ liệu**, chọn một thực thể, chọn **Chỉnh sửa**, sau đó xem dữ liệu của thực thể này bằng trình chỉnh sửa Power Query như giải thích trong [Nguồn dữ liệu](data-sources.md).

Để tìm hiểu thêm về dữ liệu được nhập vào thực thể, cột **Tóm tắt** cung cấp cho bạn một số đặc điểm quan trọng của dữ liệu, chẳng hạn như giá trị rỗng, các giá trị còn thiếu, giá trị duy nhất, số lượng và phân phối, như áp dụng cho dữ liệu của bạn.

Chọn biểu tượng biểu đồ để xem tóm tắt dữ liệu.

> [!div class="mx-imgBorder"]
> ![Biểu tượng tóm tắt.](media/data-manager-entities-summary.png "Bảng tóm tắt dữ liệu")

## <a name="entity-specific-information"></a>Thông tin về thực thể

Phần sau cung cấp thông tin về một số thực thể do hệ thống tạo.

### <a name="corrupted-data-sources"></a>Nguồn dữ liệu bị lỗi

Các trường từ nguồn dữ liệu đã nhập có thể chứa dữ liệu bị hỏng. Các bản ghi có các trường bị hỏng được hiển thị trong các thực thể do hệ thống tạo. Biết các bản ghi bị hỏng sẽ giúp bạn xác định dữ liệu nào cần xem lại và cập nhật trên hệ thống nguồn. Sau lần làm mới tiếp theo của nguồn dữ liệu, các bản ghi đã sửa sẽ được nhập vào Customer Insights và được chuyển cho các quy trình tiếp theo. 

Ví dụ: cột "ngày sinh" có loại dữ liệu được đặt là "ngày". Hồ sơ khách hàng có ngày sinh của họ được nhập là "01/01/19777". Hệ thống sẽ gắn cờ bản ghi này là bị hỏng. Bây giờ ai đó có thể thay đổi ngày sinh trong hệ thống nguồn thành "1977". Sau khi tự động làm mới nguồn dữ liệu, trường hiện có định dạng hợp lệ và bản ghi sẽ bị xóa khỏi thực thể bị hỏng. 

Đi đến **Dữ liệu** > **Thực thể** và tìm kiếm các thực thể bị hỏng trong phần **Hệ thống**. Lược đồ đặt tên của các thực thể bị hỏng: "DataSourceName_EntityName_corrupt".

Customer Insights vẫn xử lý các hồ sơ bị hỏng. Tuy nhiên, chúng có thể gây ra sự cố khi làm việc với dữ liệu hợp nhất.

Các bước kiểm tra sau chạy trên dữ liệu đã nhập để hiển thị các bản ghi bị hỏng: 

- Giá trị của một trường không khớp với kiểu dữ liệu của cột.
- Các trường chứa các ký tự khiến các cột không khớp với lược đồ mong đợi. Ví dụ: dấu ngoặc kép được định dạng không chính xác, dấu ngoặc kép không thoát hoặc ký tự dòng mới.
- Nếu có các cột datetime/date/datetimeoffset, định dạng của cột cần được chỉ định trong mô hình nếu không tuân theo định dạng ISO tiêu chuẩn.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
