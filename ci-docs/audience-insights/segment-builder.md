---
title: Tạo phân khúc bằng trình tạo phân khúc
description: Tạo phân khúc khách hàng để nhóm họ lại dựa trên các đặc điểm khác nhau.
ms.date: 10/18/2021
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-segments
- ci-segment-builder
- ci-segment-details
- customerInsights
ms.openlocfilehash: 6fa6f0738bf7fba94b2fb84a70ea17483aae8dac
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 02/25/2022
ms.locfileid: "8354581"
---
# <a name="create-segments"></a>Tạo phân khúc

Xác định các bộ lọc phức hợp xung quanh thực thể khách hàng hợp nhất và các thực thể có liên quan. Mỗi phân khúc, sau khi xử lý, sẽ tạo một bộ hồ sơ khách hàng mà bạn có thể xuất và hành động. Các phân khúc được quản lý trên trang **Phân khúc**. Bạn có thể [tạo phân khúc mới](#create-a-new-segment) bằng trình dựng phân khúc hoặc [tạo phân khúc nhanh](#quick-segments) từ các khía cạnh khác của ứng dụng. 

> [!TIP]
> - Phân khúc nhanh chỉ được hỗ trợ trong các môi trường cho **khách hàng cá nhân**.    
> - Phân khúc dựa trên **khách hàng cá nhân** tự động bao gồm thông tin liên hệ có sẵn cho các thành phần phân khúc. Trong môi trường cho **tài khoản doanh nghiệp**, các phân khúc được dựa trên tài khoản (công ty hoặc đại lý). Để bao gồm thông tin liên hệ trong phân khúc, hãy sử dụng chức năng **Thuộc tính dự án** trong trình dựng phân khúc.
>    - Đảm bảo rằng các nguồn dữ liệu liên hệ là [ánh xạ ngữ nghĩa tới ContactProfile](semantic-mappings.md#define-a-contactprofile-semantic-entity-mapping) thực thể.

## <a name="segment-builder"></a>Trình tạo phân khúc

Hình ảnh sau đây minh họa các khía cạnh khác nhau của trình tạo phân khúc. Hình ảnh đó cho thấy một phân khúc dẫn đến một nhóm khách hàng. Khách hàng đặt hàng trong một khung thời gian cụ thể và tích lũy điểm thưởng hoặc chi tiêu một số tiền nhất định. 

:::image type="content" source="media/segment-builder-overview.png" alt-text="Các yếu tố của trình tạo phân khúc." lightbox="media/segment-builder-overview.png":::

1. Tổ chức phân khúc của bạn bằng các quy tắc và quy tắc phụ. Mỗi quy tắc hoặc quy tắc con bao gồm các điều kiện. Kết hợp các điều kiện với các toán tử logic

1. Chọn [đường dẫn mối quan hệ](relationships.md) giữa các thực thể áp dụng cho một quy tắc. Đường dẫn mối quan hệ xác định thuộc tính nào có thể được sử dụng trong một điều kiện.

1. Quản lý quy tắc và quy tắc phụ. Thay đổi vị trí của quy tắc hoặc xóa quy tắc đó.

1. Thêm điều kiện và tạo cấp độ lồng phù hợp bằng các quy tắc phụ.

1. Áp dụng các hoạt động đã thiết lập cho các quy tắc được kết nối.

1. Sử dụng ngăn thuộc tính để thêm các thuộc tính thực thể có sẵn hoặc tạo điều kiện dựa trên thuộc tính. Ngăn hiển thị danh sách các thực thể và thuộc tính, dựa trên đường dẫn mối quan hệ đã chọn, có sẵn cho quy tắc đã chọn.

1. Thêm các điều kiện dựa trên thuộc tính vào các quy tắc và quy tắc phụ hiện có hoặc thêm nó vào một quy tắc mới.

1. Hoàn tác và thực hiện lại các thay đổi trong khi xây dựng phân khúc.

Ví dụ trên minh họa khả năng phân khúc. Chúng tôi đã xác định một phân khúc cho những khách hàng đã mua ít nhất $500 hàng hóa trực tuyến *và* quan tâm đến phát triển phần mềm.

## <a name="create-a-new-segment"></a>Tạo phân khúc mới

Có nhiều cách để tạo một phân khúc mới. Phần này mô tả cách tạo phân khúc của riêng bạn từ đầu. Bạn cũng có thể tạo một *phân khúc nhanh* dựa trên các thực thể hiện có hoặc sử dụng các mô hình máy học để có được *phân khúc đề xuất*. Để biết thêm thông tin, hãy chuyển đến [Tổng quan về phân khúc](segments.md).

Trong khi tạo phân khúc, bạn có thể lưu bản nháp. Trong giai đoạn nháp, một phân khúc được lưu dưới dạng phân khúc không hoạt động. Khi bạn hoàn thành cấu hình phân khúc, hãy chạy cấu hình để kích hoạt phân khúc. Ngoài ra, bạn có thể **Kích hoạt** một phân khúc từ trang **Tất cả phân khúc**.

1. Chuyển đến trang **Phân khúc**.

1. Chọn **Mới** > **Xây dựng phân khúc của riêng bạn**.

1. Trên trang trình dựng phân khúc, bạn xác định hoặc soạn các quy tắc. Quy tắc bao gồm một hoặc nhiều điều kiện xác định một tập khách hàng.

1. Trong phần **Quy tắc 1**, chọn một thuộc tính của thực thể mà bạn muốn lọc khách hàng. Có hai cách để chọn thuộc tính: 
   - Xem lại danh sách các thực thể và thuộc tính có sẵn trong ngăn **Thêm vào quy tắc** và chọn biểu tượng **+** bên cạnh thuộc tính cần thêm. Chọn nếu bạn muốn thêm thuộc tính vào quy tắc hiện có hoặc sử dụng thuộc tính đó để tạo quy tắc mới.
   - Nhập tên của thuộc tính vào phần quy tắc để xem các đề xuất phù hợp.

1. Chọn các toán tử để chỉ định các giá trị phù hợp của điều kiện. Thuộc tính có thể có một trong bốn kiểu dữ liệu dưới dạng giá trị: số, chuỗi, ngày tháng hoặc Boolean. Tùy thuộc vào kiểu dữ liệu của thuộc tính, các toán tử khác nhau có sẵn để chỉ định điều kiện. Đối với các phân khúc có tài khoản doanh nghiệp, hai toán tử đặc biệt có sẵn để bao gồm phân cấp tiềm năng giữa các tài khoản đã nhập. Sử dụng toán tử *child of* và *parent of* để bao gồm các tài khoản liên quan. 

1. Chọn **Thêm điều kiện** để thêm nhiều điều kiện hơn vào quy tắc. Để tạo quy tắc theo quy tắc hiện tại, hãy chọn **Thêm quy tắc phụ**.

1. Nếu một quy tắc sử dụng các thực thể khác với thực thể *Khách hàng*, bạn phải thiết lập đường dẫn mối quan hệ. Đường dẫn mối quan hệ được yêu cầu để thông báo cho hệ thống về mối quan hệ nào bạn muốn truy cập vào thực thể khách hàng hợp nhất. Chọn **Đặt đường dẫn mối quan hệ** để ánh xạ thực thể đã chọn với thực thể khách hàng hợp nhất. Nếu chỉ có một đường dẫn mối quan hệ khả thi, hệ thống sẽ tự động chọn đường dẫn đó. Các đường dẫn mối quan hệ khác nhau có thể mang lại những kết quả khác nhau. Mọi quy tắc đều có thể có đường dẫn mối quan hệ riêng.

   :::image type="content" source="media/relationship-path.png" alt-text="Đường dẫn mối quan hệ tiềm năng khi tạo quy tắc dựa trên một thực thể được ánh xạ tới thực thể khách hàng hợp nhất.":::

   Ví dụ: thực thể *eCommerce_eCommercePurchases* trong ảnh chụp màn hình có bốn tùy chọn để ánh xạ đến thực thể *Khách hàng*: 
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > Khách hàng
   - eCommerce_eCommercePurchases > Khách hàng
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > Khách hàng
   - eCommerce_eCommercePurchases> eCommerce_eCommerceContacts> POS_posPurchases >yalScheme_loyCustomers> Khách hàng Khi chọn tùy chọn cuối cùng, chúng tôi có thể bao gồm các thuộc tính từ tất cả các thực thể được liệt kê trong điều kiện quy tắc. Chúng ta có thể nhận được ít kết quả hơn do bản ghi khách hàng khớp cần phải là một phần của tất cả thực thể. Trong ví dụ này, họ đã mua hàng thông qua thương mại điện tử(*eCommerce_eCommercePurchases*) làm điểm bán hàng(*POS_posPurchases*) và tham gia vào chương trình khách hàng thân thiết (*loyaltyScheme_loyCustomers*). Khi chọn tùy chọn thứ hai, chúng tôi chỉ có thể chọn các thuộc tính từ *eCommerce_eCommercePurchases* và thực thể *Khách hàng*. Điều này có thể dẫn đến nhiều hồ sơ khách hàng hơn.

1. Nếu bạn có nhiều điều kiện trong một quy tắc, bạn có thể chọn toán tử logic nào kết nối chúng.  
   - Toán tử **VÀ**: Tất cả các điều kiện phải được đáp ứng để bao gồm một bản ghi trong phân khúc. Tùy chọn này hữu ích nhất khi bạn xác định các điều kiện trên các thực thể khác nhau.
   - Toán tử **HOẶC**: Phải đáp ứng một trong các điều kiện để đưa bản ghi vào phân khúc. Tùy chọn này hữu ích nhất khi bạn xác định nhiều điều kiện cho cùng một thực thể.

   :::image type="content" source="media/segmentation-either-condition.png" alt-text="Quy tắc với hai điều kiện VÀ.":::

   Khi sử dụng toán tử HOẶC, tất cả các điều kiện phải dựa trên các thực thể có trong đường dẫn mối quan hệ.

   - Bạn có thể tạo nhiều quy tắc để tạo các bộ hồ sơ khách hàng khác nhau. Bạn có thể kết hợp các nhóm để có được những khách hàng cần thiết cho hoạt động kinh doanh của bạn. Để tạo một quy tắc mới, hãy chọn **Thêm quy tắc**. Cụ thể, nếu bạn không thể bao gồm và thực thể trong một quy tắc vì đường dẫn mối quan hệ đã chỉ định, bạn phải tạo một quy tắc mới để chọn các thuộc tính tạo thành quy tắc đó.

      :::image type="content" source="media/segment-rule-grouping.png" alt-text="Thêm quy tắc mới vào một phân khúc và chọn toán tử đặt.":::

   - Chọn một trong các toán tử đã đặt: **Hợp nhất**, **Giao nhau** hoặc **Ngoại trừ**.

      - **Hợp nhất** sẽ hợp nhất hai nhóm với nhau.
      - **Giao nhau** sẽ chồng chéo hai nhóm với nhau. Chỉ dữ liệu mà cả hai nhóm *có chung* vẫn nằm trong nhóm hợp nhất.
      - **Trừ** kết hợp hai nhóm với nhau. Chỉ dữ liệu trong nhóm A mà *không có chung* với dữ liệu trong nhóm B được giữ lại.

1. Theo mặc định, các phân khúc tạo thực thể đầu ra chứa tất cả các thuộc tính của hồ sơ khách hàng phù hợp với các bộ lọc đã xác định. Nếu một phân khúc dựa trên các thực thể khác với *Khách hàng*, bạn có thể thêm nhiều thuộc tính hơn từ các thực thể này vào thực thể đầu ra. Chọn **Thuộc tính dự án** để chọn các thuộc tính sẽ được thêm vào thực thể đầu ra. 

   > [!IMPORTANT]
   > Đối với các phân khúc dựa trên tài khoản doanh nghiệp, chi tiết của một hoặc nhiều liên hệ của từng tài khoản từ thực thể *ContactProfile* cần được bao gồm trong phân khúc để cho phép phân khúc được kích hoạt hoặc xuất sang các đích cần thông tin liên hệ. Để biết thêm thông tin về thực thể *ContactProfile*, xem [Ánh xạ ngữ nghĩa](semantic-mappings.md).
   > Đầu ra mẫu cho một phân khúc dựa trên tài khoản doanh nghiệp với các thuộc tính dự kiến của địa chỉ liên hệ sẽ có dạng như thế này: 
   >
   > |ID  |Tên Khách hàng  |Doanh thu  |Tên liên hệ  | Vai trò liên hệ|
   > |---------|---------|---------|---------|---|
   > |10021     | Contoso | 100.000 | [Abbie Moss, Ruth Soto]  | [CEO, Quản lý thu mua]

   :::image type="content" source="media/segments-project-attributes.png" alt-text="Ví dụ về các thuộc tính dự kiến được chọn trong ngăn bên để được thêm vào thực thể đầu ra.":::
  
   Ví dụ: Một phân khúc được dựa trên thực thể chứa dữ liệu mua hàng, liên quan đến thực thể *Khách hàng*. Phân khúc này dành cho tất cả khách hàng đến từ Tây Ban Nha đã mua hàng trong năm hiện tại. Bạn có thể chọn thêm các thuộc tính như giá hàng hóa hoặc ngày mua hàng vào tất cả các hồ sơ khách hàng phù hợp trong thực thể đầu ra. Thông tin này có thể hữu ích để phân tích mối tương quan giữa mùa vụ với tổng chi tiêu.

   > [!NOTE]
   > - **Thuộc tính dự án** chỉ hoạt động cho các thực thể có mối quan hệ một-nhiều với thực thể khách hàng. Ví dụ: một khách hàng có thể có nhiều gói đăng ký.
   > - Nếu thuộc tính bạn muốn chiếu xa hơn một bước so với thực thể *Khách hàng*, như xác định theo mối quan hệ, rằng thuộc tính đó nên được sử dụng trong mọi quy tắc của truy vấn phân khúc mà bạn đang xây dựng. 
   > - Nếu thuộc tính bạn muốn chiếu chỉ cách thực thể *Khách hàng* một bước, thuộc tính đó không cần xuất hiện trong mọi quy tắc của truy vấn phân khúc mà bạn đang xây dựng. 
   > - **Các thuộc tính dự kiến** được coi như yếu tố khi sử dụng các toán tử tập hợp.

1. Trước khi bạn lưu và chạy phân khúc, hãy chọn **Chỉnh sửa chi tiết** bên cạnh tên phân khúc. Cung cấp tên cho phân khúc và cập nhật **Tên thực thể đầu ra** đã đề xuất cho phân khúc. Bạn cũng có thể thêm mô tả vào phân khúc.

1. Chọn **Chạy** để lưu phân khúc, kích hoạt và bắt đầu xử lý phân khúc của bạn dựa trên tất cả các quy tắc và điều kiện. Nếu không, nó sẽ được lưu dưới dạng một phân khúc không hoạt động.
   
1. Chọn **Quay lại phân khúc** để quay lại trang **Phân khúc**.

1. Theo mặc định, phân khúc được tạo dưới dạng phân khúc động. Điều đó có nghĩa là phân khúc được làm mới trong quá trình làm mới hệ thống. Để [dừng làm mới tự động](segments.md#manage-existing-segments), chọn phân khúc chọn tùy chọn **Thiết lập tĩnh**. Các phân khúc tĩnh có thể được [làm mới theo cách thủ công](segments.md#refresh-segments) bất cứ lúc nào.

> [!TIP]
> - Trình tạo phân khúc sẽ không đề xuất các giá trị hợp lệ từ các thực thể khi đặt toán tử cho các điều kiện. Bạn có thể chuyển đến phần **Dữ liệu** > **Thực thể** và tải xuống dữ liệu thực thể để xem những giá trị nào có sẵn.
> - Các điều kiện dựa trên ngày cho phép bạn chuyển đổi giữa các ngày cố định và một phạm vi ngày thực.
> - Nếu bạn có nhiều quy tắc cho phân khúc của mình, quy tắc bạn đang chỉnh sửa có một đường thẳng đứng màu xanh lam bên cạnh. 
> - Bạn có thể di chuyển các quy tắc và điều kiện đến các vị trí khác trong định nghĩa phân khúc. Chọn [...] bên cạnh một quy tắc hoặc điều kiện và chọn cách thức và vị trí để di chuyển nó.
> - Các điều khiển **Hoàn tác** và **Làm lại** trong thanh lệnh cho phép bạn khôi phục các thay đổi.

## <a name="quick-segments"></a>Phân khúc nhanh

Phân khúc nhanh cho phép bạn tạo nhanh các phân khúc đơn giản với một toán tử để có thông tin chi tiết nhanh chóng hơn.

1. Trên trang **Phân khúc**, chọn **Mới** > **Tạo từ**.
   - Chọn **Hồ sơ** để xây dựng phân khúc dựa trên thực thể *khách hàng hợp nhất*.
   - Chọn tùy chọn **Giá trị đo** để tạo một phân khúc xoay quanh các giá trị đo mà bạn đã tạo trước đó.
   - Chọn tùy chọn **Thông tin** để xây dựng một phân khúc xung quanh một trong các thực thể đầu ra mà bạn tạo bằng một trong hai chức năng **Dự đoán** hoặc **Mô hình tùy chỉnh**.

2. Trong hộp thoại **Phân khúc nhanh mới**, hãy chọn một thuộc tính từ mục thả xuống **Trường**.

3. Hệ thống sẽ cung cấp thêm thông tin chi tiết giúp bạn tạo phân khúc khách hàng tốt hơn.
   - Đối với các trường có phân loại, chúng tôi sẽ hiển thị 10 lượt khách hàng tốt nhất. Chọn **Giá trị** rồi chọn **Xem lại**.
   - Đối với một thuộc tính số, hệ thống sẽ hiển thị giá trị thuộc tính nào nằm trong phần trăm của mỗi khách hàng. Chọn một **Toán tử** và một **Giá trị**, sau đó chọn **Xem lại**.

4. Hệ thống sẽ cung cấp cho bạn một **Kích cỡ phân khúc ước tính**. Bạn có thể chọn tạo phân khúc bạn đã xác định hoặc truy cập lại vào phân khúc đó để có kích cỡ phân khúc khác.

    > [!div class="mx-imgBorder"]
    > ![Tên và ước tính cho một phân khúc nhanh.](media/quick-segment-name.png "Tên và ước tính cho một phân khúc nhanh")

5. Đặt **Tên** cho phân khúc của bạn. Bạn cũng có thể cung cấp **Tên hiển thị**.

6. Chọn **Lưu** để tạo phân khúc.

7. Sau khi phân khúc đã xử lý xong, bạn có thể xem nó như bất kỳ phân khúc nào khác mà bạn đã tạo.

## <a name="next-steps"></a>Các bước tiếp theo

[Xuất một phân khúc](export-destinations.md) và khám phá [Tích hợp thẻ khách hàng](customer-card-add-in.md) để sử dụng các phân khúc trong các ứng dụng khác.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
