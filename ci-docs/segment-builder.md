---
title: Tạo phân đoạn phức tạp với trình tạo phân đoạn
description: Sử dụng trình tạo phân khúc để tạo các phân khúc khách hàng phức tạp bằng cách nhóm họ dựa trên các thuộc tính khác nhau.
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-segments
- ci-segment-builder
- ci-segment-details
- customerInsights
ms.openlocfilehash: 7f691fd0b2ea76a2960d5adf766a4b166f02ebb4
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304775"
---
# <a name="create-complex-segments-with-segment-builder"></a>Tạo phân đoạn phức tạp với trình tạo phân đoạn

Xác định các bộ lọc phức tạp xung quanh khách hàng hợp nhất hoặc liên hệ hợp nhất và các thực thể có liên quan. Mỗi phân đoạn, sau khi xử lý, sẽ tạo một tập hợp các bản ghi khách hàng hoặc liên hệ mà bạn có thể xuất và thực hiện hành động.

> [!TIP]
> Phân khúc dựa trên **khách hàng cá nhân** tự động bao gồm thông tin liên hệ có sẵn cho các thành phần phân khúc. Trong **tài khoản kinh doanh**, nếu bạn [thống nhât](data-unification.md) cả tài khoản và địa chỉ liên hệ, chọn phân đoạn dựa trên tài khoản hoặc địa chỉ liên hệ công việc. Để xuất đến một điểm đến cần thông tin liên hệ, hãy sử dụng một phân đoạn các địa chỉ liên hệ. Để xuất thông tin tài khoản đến đích, hãy sử dụng một phân đoạn tài khoản.

## <a name="segment-builder"></a>Trình tạo phân khúc

Hình ảnh sau đây minh họa các khía cạnh khác nhau của trình tạo phân khúc. Hình ảnh đó cho thấy một phân khúc dẫn đến một nhóm khách hàng. Khách hàng đặt hàng trong một khung thời gian cụ thể và tích lũy điểm thưởng hoặc chi tiêu một số tiền nhất định.

:::image type="content" source="media/segment-builder-overview.png" alt-text="Các yếu tố của trình tạo phân khúc." lightbox="media/segment-builder-overview.png":::

1. Tổ chức phân khúc của bạn bằng các quy tắc và quy tắc phụ. Mỗi quy tắc hoặc quy tắc con bao gồm các điều kiện. Kết hợp các điều kiện với các toán tử logic.

1. Chọn [đường dẫn mối quan hệ](relationships.md) giữa các thực thể áp dụng cho một quy tắc. Đường dẫn mối quan hệ xác định thuộc tính nào có thể được sử dụng trong một điều kiện.

1. Quản lý quy tắc và quy tắc phụ. Thay đổi vị trí của quy tắc hoặc xóa quy tắc đó.

1. Thêm điều kiện và tạo cấp độ lồng phù hợp bằng các quy tắc phụ.

1. Áp dụng các hoạt động đã thiết lập cho các quy tắc được kết nối.

1. Sử dụng ngăn thuộc tính để thêm các thuộc tính thực thể có sẵn hoặc tạo điều kiện dựa trên thuộc tính. Ngăn hiển thị danh sách các thực thể và thuộc tính, dựa trên đường dẫn mối quan hệ đã chọn, có sẵn cho quy tắc đã chọn.

1. Thêm các điều kiện dựa trên thuộc tính vào các quy tắc và quy tắc phụ hiện có hoặc thêm nó vào một quy tắc mới.

1. Hoàn tác và thực hiện lại các thay đổi trong khi xây dựng phân khúc.

Ví dụ trên minh họa khả năng phân khúc. Chúng tôi đã xác định một phân khúc cho những khách hàng đã mua ít nhất $500 hàng hóa trực tuyến *và* quan tâm đến phát triển phần mềm.

## <a name="create-a-new-segment-with-segment-builder"></a>Tạo phân đoạn mới với trình tạo phân đoạn

1. Đi đến **Phân khúc**.

1. Chọn **Mới** > **Xây dựng phân khúc của riêng bạn**. Trên trang trình dựng phân khúc, bạn xác định hoặc soạn các quy tắc. Quy tắc bao gồm một hoặc nhiều điều kiện xác định một tập khách hàng.

   > [!NOTE]
   > Đối với môi trường dựa trên tài khoản doanh nghiệp, hãy chọn **Mới** > **Phân đoạn tài khoản** hoặc **Phân đoạn Danh bạ (xem trước)** dựa trên loại phân đoạn bạn muốn tạo. Nếu một [phân cấp tài khoản](relationships.md#set-up-account-hierarchies) đã được xác định và bạn muốn tạo quy tắc để lọc ra dữ liệu dựa trên mối quan hệ con và mẹ, hãy chọn **Sử dụng hệ thống phân cấp? (xem trước)**, chọn hệ thống phân cấp, sau đó **Ứng dụng**.
   >
   > :::image type="content" source="media/segment_acct_hierarchy.png" alt-text="Phân đoạn chọn ngăn phân cấp tài khoản.":::

1. Lựa chọn **Chỉnh sửa chi tiết** bên cạnh Phân đoạn không có tiêu đề. Cung cấp tên cho phân khúc và cập nhật **Tên thực thể đầu ra** đã đề xuất cho phân khúc. Theo tùy chọn, thêm mô tả và [thẻ](work-with-tags-columns.md#manage-tags) đến phân khúc.

   :::image type="content" source="media/segments_edit_details.png" alt-text="Hộp thoại chỉnh sửa chi tiết.":::

1. Bên trong **Quy tắc 1**, chọn một thuộc tính của thực thể mà bạn muốn lọc khách hàng. Có hai cách để chọn thuộc tính:
   - Xem lại danh sách các thực thể và thuộc tính có sẵn trong ngăn **Thêm vào quy tắc** và chọn biểu tượng **+** bên cạnh thuộc tính cần thêm. Chọn nếu bạn muốn thêm thuộc tính vào quy tắc hiện có hoặc sử dụng thuộc tính đó để tạo quy tắc mới.
   - Nhập tên của thuộc tính vào phần quy tắc để xem các đề xuất phù hợp.

1. Chọn các toán tử để chỉ định các giá trị phù hợp của điều kiện. Thuộc tính có thể có một trong bốn kiểu dữ liệu dưới dạng giá trị: số, chuỗi, ngày tháng hoặc Boolean. Tùy thuộc vào kiểu dữ liệu của thuộc tính, các toán tử khác nhau có sẵn để chỉ định điều kiện.

1. Chọn **Thêm điều kiện** để thêm nhiều điều kiện hơn vào quy tắc. Để tạo quy tắc theo quy tắc hiện tại, hãy chọn **Thêm quy tắc phụ**.

1. Nếu một quy tắc sử dụng các thực thể khác với *khách hàng* thực thể (hoặc *ContactProfile* thực thể cho B-to-B), chọn **Đặt đường dẫn mối quan hệ** để ánh xạ thực thể đã chọn với thực thể khách hàng hợp nhất. Nếu chỉ có một đường dẫn mối quan hệ khả thi, hệ thống sẽ tự động chọn đường dẫn đó. Khác nhau [con đường quan hệ](relationships.md#relationship-paths) có thể mang lại các kết quả khác nhau. Mọi quy tắc đều có thể có đường dẫn mối quan hệ riêng.

   :::image type="content" source="media/relationship-path.png" alt-text="Đường dẫn mối quan hệ tiềm năng khi tạo quy tắc dựa trên một thực thể được ánh xạ tới thực thể khách hàng hợp nhất.":::

1. Nếu bạn có nhiều điều kiện trong một quy tắc, hãy chọn toán tử logic nào kết nối chúng.  
   - Toán tử **VÀ**: Tất cả các điều kiện phải được đáp ứng để bao gồm một bản ghi trong phân khúc. Sử dụng tùy chọn này khi bạn xác định các điều kiện trên các thực thể khác nhau.
   - Toán tử **HOẶC**: Phải đáp ứng một trong các điều kiện để đưa bản ghi vào phân khúc. Sử dụng tùy chọn này khi bạn xác định nhiều điều kiện cho cùng một thực thể.

   :::image type="content" source="media/segmentation-either-condition.png" alt-text="Quy tắc với hai điều kiện VÀ.":::

   Khi sử dụng toán tử HOẶC, tất cả các điều kiện phải dựa trên các thực thể có trong đường dẫn mối quan hệ.

1. Để tạo các bộ hồ sơ khách hàng khác nhau, hãy tạo nhiều quy tắc. Để bao gồm những khách hàng cần thiết cho trường hợp kinh doanh của bạn, hãy kết hợp các nhóm. Cụ thể, nếu bạn không thể bao gồm một thực thể trong một quy tắc do đường dẫn mối quan hệ đã chỉ định, hãy tạo một quy tắc mới để chọn các thuộc tính từ nó.

      :::image type="content" source="media/segment-rule-grouping.png" alt-text="Thêm quy tắc mới vào một phân khúc và chọn toán tử đặt.":::

   1. Lựa chọn **Thêm quy tắc**.
   1. Chọn một trong các toán tử đã đặt: **Hợp nhất**, **Giao nhau** hoặc **Ngoại trừ**.

      - **Hợp nhất** sẽ hợp nhất hai nhóm với nhau.
      - **Giao nhau** sẽ chồng chéo hai nhóm với nhau. Chỉ dữ liệu mà cả hai nhóm *có chung* vẫn nằm trong nhóm hợp nhất.
      - **Trừ** kết hợp hai nhóm với nhau. Chỉ dữ liệu trong nhóm A mà *không có chung* với dữ liệu trong nhóm B được giữ lại.

1. Theo mặc định, thực thể đầu ra sẽ tự động chứa tất cả các thuộc tính của hồ sơ khách hàng phù hợp với các bộ lọc đã xác định. Trong B-to-B khi sử dụng *ContactProfile* thực thể, ID tài khoản được tự động bao gồm. Nếu một phân đoạn dựa trên các thực thể khác với *khách hàng* thực thể hoặc bao gồm nhiều thuộc tính hơn từ *ContactProfile*, lựa chọn **Thuộc tính dự án** để thêm nhiều thuộc tính hơn từ các thực thể này vào thực thể đầu ra.
 
   Ví dụ: Một phân khúc được dựa trên thực thể chứa dữ liệu mua hàng, liên quan đến thực thể *Khách hàng*. Phân khúc này dành cho tất cả khách hàng đến từ Tây Ban Nha đã mua hàng trong năm hiện tại. Bạn có thể chọn thêm các thuộc tính như giá hàng hóa hoặc ngày mua hàng vào tất cả các bản ghi khách hàng phù hợp trong thực thể đầu ra. Thông tin này có thể hữu ích để phân tích mối tương quan giữa mùa vụ với tổng chi tiêu.

   :::image type="content" source="media/segments-project-attributes.png" alt-text="Ví dụ về các thuộc tính dự kiến được chọn trong ngăn bên để được thêm vào thực thể đầu ra.":::
 
   Đầu ra mẫu cho một phân khúc dựa trên tài khoản doanh nghiệp với các thuộc tính dự kiến của địa chỉ liên hệ sẽ có dạng như thế này:

   |ID  |Tên Khách hàng  |Doanh thu  |Tên liên hệ  | Vai trò liên hệ|
   |---------|---------|---------|---------|---|
   |10021     | Contoso | 100.000 | [Abbie Moss, Ruth Soto]  | [CEO, Quản lý thu mua]

   > [!NOTE]
   > - **Thuộc tính dự án** chỉ hoạt động cho các thực thể có mối quan hệ một-nhiều với *khách hàng* hoặc *ContactProfile* thực thể. Ví dụ: một khách hàng có thể có nhiều gói đăng ký.
   > - Nếu thuộc tính bạn muốn chiếu xa hơn một bước so với *khách hàng* hoặc *ContactProfile* thực thể, như được xác định bởi mối quan hệ, thuộc tính đó nên được sử dụng trong mọi quy tắc của truy vấn phân đoạn mà bạn đang tạo.
   > - Nếu thuộc tính bạn muốn chiếu chỉ còn cách *khách hàng* hoặc *ContactProfile* thực thể, thuộc tính đó không cần phải có trong mọi quy tắc của truy vấn phân đoạn mà bạn đang tạo.
   > - **Các thuộc tính dự kiến** được coi như yếu tố khi sử dụng các toán tử tập hợp.

1. Lựa chọn **Chạy** để tạo phân khúc. Lựa chọn **Tiết kiệm** nếu bạn muốn giữ cấu hình hiện tại và chạy phân đoạn sau. Các **Phân đoạn** hiển thị trang.

### <a name="segment-builder-tips"></a>Mẹo về trình tạo phân đoạn

Khi tạo phân đoạn bằng trình tạo phân đoạn, hãy ghi nhớ các mẹo sau:

- Trình tạo phân khúc sẽ không đề xuất các giá trị hợp lệ từ các thực thể khi đặt toán tử cho các điều kiện. Bạn có thể chuyển đến phần **Dữ liệu** > **Thực thể** và tải xuống dữ liệu thực thể để xem những giá trị nào có sẵn.
- Các điều kiện dựa trên ngày cho phép bạn chuyển đổi giữa các ngày cố định và một phạm vi ngày thực.
- Nếu bạn có nhiều quy tắc cho phân khúc của mình, quy tắc bạn đang chỉnh sửa có một đường thẳng đứng màu xanh lam bên cạnh.
- Bạn có thể di chuyển các quy tắc và điều kiện đến các vị trí khác trong định nghĩa phân khúc. Chọn dấu chấm lửng dọc (&vellip;) bên cạnh một quy tắc hoặc điều kiện và chọn cách thức và vị trí để di chuyển nó.
- Các điều khiển **Hoàn tác** và **Làm lại** trong thanh lệnh cho phép bạn khôi phục các thay đổi.
- Sau khi tạo phân đoạn, một số phân đoạn cho phép bạn [theo dõi việc sử dụng phân đoạn](segments.md#track-usage-of-a-segment).

## <a name="next-steps"></a>Các bước tiếp theo

[Xuất một phân khúc](export-destinations.md) và khám phá [Tích hợp thẻ khách hàng](customer-card-add-in.md) để sử dụng các phân khúc trong các ứng dụng khác.

[!INCLUDE [footer-include](includes/footer-banner.md)]
