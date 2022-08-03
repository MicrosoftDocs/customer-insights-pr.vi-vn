---
title: Các thực thể trong Customer Insights
description: Xem dữ liệu trên trang Thực thể.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-entities
- customerInsight
ms.openlocfilehash: 0beaa46d47545ac195ced876b509dfc57821bfaf
ms.sourcegitcommit: ad74ace653db9a25fce4343adef7db1c9b0d8904
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 07/21/2022
ms.locfileid: "9183611"
---
# <a name="entities-in-customer-insights"></a>Các thực thể trong Customer Insights

Sau khi [định cấu hình nguồn dữ liệu](data-sources.md), hãy truy cập trang **Thực thể** để đánh giá chất lượng của dữ liệu được nhập. Các thực thể được coi là tập hợp dữ liệu. Nhiều chức năng của Dynamics 365 Customer Insights được xây dựng liên quan đến những thực thể này. Việc xem xét chúng một cách chi tiết có thể giúp bạn xác thực đầu ra của những khả năng.

Khi bạn làm việc trong Thông tin chi tiết về khách hàng để làm phong phú thêm dữ liệu của mình hoặc tạo phân đoạn, biện pháp và hoạt động, các thực thể được tạo từ những hành động đó sẽ hiển thị trên **Thực thể** trang.

## <a name="view-a-list-of-entities"></a>Xem danh sách các thực thể

Đi đến **Dữ liệu** > **Thực thể** để xem danh sách các thực thể. Thông tin sau sẽ hiển thị cho từng thực thể.

- **Tên** : Tên của thực thể dữ liệu. Nếu bạn thấy biểu tượng cảnh báo bên cạnh tên thực thể, điều đó có nghĩa là dữ liệu cho thực thể đó không tải thành công.
- **Nguồn** : Loại nguồn dữ liệu đã nhập thực thể.
- **Đã cập nhật** : Thời gian thực thể được cập nhật lần cuối.
- **Trạng thái** : Thông tin chi tiết về lần cập nhật cuối cùng của thực thể.

## <a name="explore-a-specific-entitys-data"></a>Khám phá dữ liệu của một thực thể cụ thể

1. Đi đến **Dữ liệu** > **Thực thể**.
1. Chọn một thực thể để mở trang chi tiết.  
1. Khám phá các trường và bản ghi khác nhau được bao gồm cho thực thể đó.

- Các **Thuộc tính** tab được chọn theo mặc định và hiển thị chi tiết cho thực thể đã chọn, chẳng hạn như tên trường, kiểu dữ liệu và loại. Cột **Loại** hiển thị các loại liên kết Common Data Model được tự động xác định bởi hệ thống hoặc [được ánh xạ thủ công](map-entities.md) bởi người dùng. Những kiểu ngữ nghĩa này có thể khác với kiểu dữ liệu của thuộc tính. Ví dụ, trường *E-mail* bên dưới có một kiểu dữ liệu *Sợi dây* nhưng kiểu Mô hình Dữ liệu Chung (ngữ nghĩa) của nó có thể là *E-mail*, *chỉ email*, hoặc *Identity.Service.Email*.

   :::image type="content" source="media/data-manager-entities-fields.png" alt-text="Bảng trường.":::

   > [!NOTE]
   > Trang này chỉ hiển thị một mẫu dữ liệu của tổ chức của bạn. Để xem toàn bộ tập dữ liệu, hãy chuyển đến **Nguồn dữ liệu** trang, chọn một thực thể, chọn **Chỉnh sửa** và sau đó xem dữ liệu của thực thể này với Power Query biên tập viên như được giải thích trong [Nguồn dữ liệu](data-sources.md).

   Để tìm hiểu thêm về dữ liệu được nhập vào thực thể, **Bản tóm tắt** cột cung cấp một số đặc điểm dữ liệu quan trọng, chẳng hạn như giá trị rỗng, giá trị bị thiếu, giá trị duy nhất, số lượng và phân phối, bất cứ điều gì có thể áp dụng cho dữ liệu của bạn. Chọn biểu tượng biểu đồ để xem tóm tắt dữ liệu.

   :::image type="content" source="media/data-manager-entities-summary.png" alt-text="Bảng tổng hợp dữ liệu.":::

- Các **Dữ liệu** tab hiển thị chi tiết về các bản ghi riêng lẻ của thực thể. Chi tiết được liệt kê tùy thuộc vào loại dữ liệu của thực thể.

   :::image type="content" source="media/data-manager-entities-data.png" alt-text="Chọn thực thể.":::

- Các **Báo cáo** (có sẵn cho một số thực thể) cho phép bạn trực quan hóa dữ liệu của mình bằng cách tạo một báo cáo, bao gồm các cột sau:

  - **Tên báo cáo** : Tên của báo cáo.
  - **Được tạo bởi** : Tên của người đã tạo ra thực thể.
  - **Tạo** : Ngày và giờ tạo thực thể.
  - **Sửa bởi** : Tên của người đã sửa đổi thực thể.
  - **Đã chỉnh sửa** : Ngày và giờ sửa đổi thực thể.

## <a name="entity-specific-information"></a>Thông tin về thực thể

Phần sau cung cấp thông tin về một số thực thể do hệ thống tạo.

### <a name="corrupted-data-sources"></a>Nguồn dữ liệu bị lỗi

Các trường từ nguồn dữ liệu đã nhập có thể chứa dữ liệu bị hỏng. Các bản ghi có các trường bị hỏng được hiển thị trong các thực thể do hệ thống tạo. Biết các bản ghi bị hỏng sẽ giúp bạn xác định dữ liệu nào cần xem lại và cập nhật trên hệ thống nguồn. Sau lần làm mới tiếp theo của nguồn dữ liệu, các bản ghi đã sửa sẽ được nhập vào Customer Insights và được chuyển cho các quy trình tiếp theo. 

Ví dụ: cột "ngày sinh" có loại dữ liệu được đặt là "ngày". Hồ sơ khách hàng có ngày sinh của họ được nhập là "01/01/19777". Hệ thống sẽ gắn cờ bản ghi này là bị hỏng. Bây giờ ai đó có thể thay đổi ngày sinh trong hệ thống nguồn thành "1977". Sau khi tự động làm mới nguồn dữ liệu, trường hiện có định dạng hợp lệ và bản ghi sẽ bị xóa khỏi thực thể bị hỏng.

Đi đến **Dữ liệu** > **Thực thể** và tìm kiếm các thực thể bị hỏng trong phần **Hệ thống**. Lược đồ đặt tên của các thực thể bị hỏng: "DataSourceName_EntityName_corrupt". Chọn một thực thể bị hỏng để xác định các trường bị hỏng và lý do ở cấp bản ghi riêng lẻ.

   :::image type="content" source="media/corruption-reason.png" alt-text="Lý do tham nhũng.":::

Customer Insights vẫn xử lý các hồ sơ bị hỏng. Tuy nhiên, chúng có thể gây ra sự cố khi làm việc với dữ liệu hợp nhất.

Các bước kiểm tra sau chạy trên dữ liệu đã nhập để hiển thị các bản ghi bị hỏng:

- Giá trị của một trường không khớp với kiểu dữ liệu của cột.
- Các trường chứa các ký tự khiến các cột không khớp với lược đồ mong đợi. Ví dụ: dấu ngoặc kép được định dạng không chính xác, dấu ngoặc kép không thoát hoặc ký tự dòng mới.
- Nếu có các cột datetime / date / datetimeoffset, định dạng của chúng cần được chỉ định trong mô hình nếu nó không tuân theo định dạng ISO tiêu chuẩn.

[!INCLUDE [footer-include](includes/footer-banner.md)]
