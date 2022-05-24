---
title: Dự đoán đề xuất sản phẩm
description: Dự đoán các sản phẩm mà khách hàng có khả năng mua hoặc tương tác.
ms.date: 05/09/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: 9b3e60c49d294d031f43ef0594cb69707bb64019
ms.sourcegitcommit: 82f417cfb0a16600e9f552d7a21d598cc8f5a267
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 05/16/2022
ms.locfileid: "8762758"
---
# <a name="product-recommendation-prediction"></a>Dự đoán đề xuất sản phẩm

Mô hình đề xuất sản phẩm tạo ra các bộ đề xuất sản phẩm dự đoán. Các đề xuất dựa trên hành vi mua hàng trước đó và những khách hàng có kiểu mua hàng tương tự. Bạn có thể tạo dự đoán đề xuất sản phẩm mới trên trang **Thông tin** > **Dự đoán**. Chọn **Dự đoán của tôi** để xem các dự đoán khác mà bạn đã tạo.

Các đề xuất về sản phẩm có thể tuân theo luật pháp và quy định của địa phương cũng như đáp ứng kỳ vọng của khách hàng. Đây là những yếu tố mà mô hình này không tính đến cụ thể.  Là người dùng nguồn lực dự đoán này, **bạn phải xem xét các đề xuất trước khi gửi cho khách hàng của bạn** để đảm bảo rằng bạn đang tuân thủ mọi luật hoặc quy định hiện hành cũng như kỳ vọng của khách hàng đối với những gì bạn có thể đề xuất.

Ngoài ra, đầu ra của mô hình này sẽ cung cấp cho bạn các đề xuất dựa trên ID sản phẩm. Cơ chế gửi của bạn sẽ cần ánh xạ các ID sản phẩm được dự đoán với nội dung phù hợp để khách hàng của bạn tính đến nội dung bản địa hóa, nội dung hình ảnh và nội dung hoặc hành vi khác theo từng doanh nghiệp.

## <a name="sample-guide"></a>Hướng dẫn mẫu

Nếu bạn muốn thử tính năng này nhưng không có dữ liệu để hoàn thành các yêu cầu bên dưới, bạn có thể [tạo một triển khai mẫu](sample-guide-predict-product-recommendation.md).

## <a name="prerequisites"></a>Điều kiện tiên quyết

- Ít nhất [Quyền của người đóng góp](permissions.md) trong Customer Insights.

- Kiến thức kinh doanh để hiểu các loại sản phẩm khác nhau cho doanh nghiệp của bạn và cách khách hàng của bạn tương tác với chúng. Chúng tôi hỗ trợ đề xuất các sản phẩm đã được khách hàng của bạn mua trước đó hoặc đề xuất các sản phẩm mới.

- Môi trường của bạn phải được định cấu hình cho **người tiêu dùng cá nhân** đối tượng mục tiêu chính.

- Dữ liệu về các giao dịch, mua hàng và lịch sử của họ:
  - Mã định danh giao dịch để phân biệt mua hàng hoặc giao dịch.
  - Mã định danh khách hàng để ánh xạ các giao dịch với khách hàng của bạn.
  - Ngày sự kiện giao dịch xác định ngày giao dịch diễn ra.
  - Thông tin ID sản phẩm cho giao dịch.
  - (Tùy chọn) Một thực thể dữ liệu danh mục sản phẩm để sử dụng bộ lọc sản phẩm.
  - (Tùy chọn) Liệu một giao dịch có phải là giao dịch trả lại hàng hay không.
  - Lược đồ dữ liệu ngữ nghĩa yêu cầu thông tin sau:
    - **ID giao dịch:** Mã định danh duy nhất của một giao dịch mua hàng.
    - **Ngày giao dịch:** Ngày mua hoặc giao dịch.
    - **Giá trị của giao dịch:** Giá trị số của giao dịch hoặc mặt hàng.
    - **ID sản phẩm duy nhất:** ID của sản phẩm hoặc dịch vụ đã mua nếu dữ liệu của bạn ở cấp mục hàng.
    - (Tùy chọn) **Mua hoặc trả lại:** Một trường boolean trong đó giá trị *true* xác định rằng một giao dịch là giao dịch trả lại. Nếu dữ liệu Mua hoặc Trả lại không được cung cấp mô hình và **Giá trị của giao dịch** là số âm, chúng tôi cũng sẽ sử dụng thông tin này để suy ra giao dịch trả lại.
- Đặc điểm dữ liệu được đề xuất:
  - Đủ dữ liệu lịch sử: Ít nhất một năm dữ liệu giao dịch, tốt nhất là hai đến ba năm để bao gồm một số tính thời vụ.
  - Nhiều giao dịch mua trên mỗi khách hàng: Ba giao dịch trở lên trên mỗi ID khách hàng
  - Số lượng khách hàng: Tối thiểu 100 khách hàng, tốt nhất là 10.000 khách hàng. Mô hình sẽ không thành công nếu dưới 100 khách hàng.

> [!NOTE]
>
> - Mô hình yêu cầu phải có lịch sử giao dịch của khách hàng. Định nghĩa về một giao dịch là khá linh hoạt. Bất kỳ dữ liệu nào mô tả sự tương tác giữa người dùng với sản phẩm đều có thể hoạt động như một dữ liệu đầu vào. Ví dụ: mua một sản phẩm, tham gia một lớp học hoặc tham dự một sự kiện.
> - Hiện chỉ có thể đặt cấu hình một thực thể lịch sử giao dịch. Nếu có nhiều thực thể mua hàng, hãy kết hợp chúng thành Power Query trước khi nhập dữ liệu.
> - Nếu đơn hàng và chi tiết đơn hàng là các thực thể khác nhau, hãy liên kết chúng trước khi sử dụng trong mô hình. Mô hình không hoạt động chỉ với ID đơn hàng hoặc ID biên nhận trong một thực thể.

## <a name="create-a-product-recommendation-prediction"></a>Tạo dự đoán đề xuất sản phẩm

1. Trong Customer Insights, chuyển đến phần **Thông tin** > **Dự đoán**.

1. Chọn **Mô hình đề xuất sản phẩm** gạch và chọn **Sử dụng mô hình này**.
   > [!div class="mx-imgBorder"]
   > ![Ô mô hình Đề xuất Sản phẩm có nút Sử dụng mô hình này.](media/product-recommendation-usethismodel.PNG "Ô mô hình Đề xuất Sản phẩm có nút Sử dụng mô hình này")

1. Xem lại thông tin về các yêu cầu của mô hình. Nếu bạn có dữ liệu cần thiết, hãy chọn **Bắt đầu**.

### <a name="name-model"></a>Đặt tên mô hình

1. Cung cấp tên cho mô hình để phân biệt với các mô hình khác.

1. Nhập tên cho thực thể đầu ra chỉ bằng chữ cái và số, không có bất kỳ khoảng trắng nào. Đó là tên mà thực thể mô hình sẽ sử dụng. Sau đó, chọn **Tiếp**.

### <a name="define-product-recommendation-configuration"></a>Xác đặt cấu hình đề xuất sản phẩm

1. Đặt **Số lượng sản phẩm** bạn muốn giới thiệu cho khách hàng. Giá trị này phụ thuộc vào cách phương thức phân phối của bạn điền vào dữ liệu. Nếu bạn có thể đề xuất ba sản phẩm, hãy đặt giá trị này cho phù hợp.

   >[!TIP]
   > Bạn có thể chọn **Lưu bản nháp** bất kỳ lúc nào để lưu dự đoán dưới dạng bản nháp. Bạn sẽ tìm thấy dự đoán dự thảo trong tab **Dự đoán của tôi**.

1. Chọn xem bạn có muốn đưa các sản phẩm mà khách hàng đã mua gần đây vào **Các giao dịch mua lặp lại dự kiến** đồng ruộng.

1. Đặt **Cửa sổ nhìn lại**. Cài đặt này chỉ định khung thời gian mà mô hình xem xét trước khi giới thiệu lại sản phẩm cho người dùng. Ví dụ: cho biết một khách hàng mua máy tính xách tay hai năm một lần. Cửa sổ này sẽ xem xét lịch sử mua hàng trong hai năm qua và nếu tìm thấy một mặt hàng, thì mặt hàng đó sẽ được lọc khỏi các đề xuất.

1. Chọn **Tiếp theo**

### <a name="add-required-data"></a>Thêm dữ liệu bắt buộc

1. Chọn **Thêm dữ liệu** và chọn loại hoạt động trong ngăn bên có chứa thông tin lịch sử giao dịch hoặc mua hàng được yêu cầu.

1. Trong phần **Chọn các hoạt động**, chọn các hoạt động cụ thể từ hoạt động đã chọn mà bạn muốn tính toán tập trung vào.

   :::image type="content" source="media/product-recommendation-select-semantic-activity.PNG" alt-text="Ngăn bên hiển thị việc chọn các hoạt động cụ thể theo loại ngữ nghĩa.":::

1. Nếu bạn chưa ánh xạ hoạt động tới một loại ngữ nghĩa, hãy chọn **Chỉnh sửa** để làm vậy. Trải nghiệm được hướng dẫn để ánh xạ các hoạt động ngữ nghĩa sẽ mở ra. Ánh xạ dữ liệu của bạn đến các trường tương ứng trong loại hoạt động đã chọn.

   :::image type="content" source="media/product-recommendation-set-activity-type.PNG" alt-text="Loại hoạt động thiết đặt trang.":::

1. Sau khi ánh xạ hoạt động sang loại ngữ nghĩa tương ứng, hãy chọn **Kế tiếp** tiến hành với.

1. Ánh xạ các thuộc tính ngữ nghĩa đến các trường được yêu cầu để chạy mô hình.

1. Chọn **Lưu**.

1. Chọn **Tiếp theo**.

### <a name="configure-product-filters"></a>Đặt cấu hình bộ lọc sản phẩm

Đôi khi, chỉ một số sản phẩm là có lợi hoặc phù hợp với loại dự đoán mà bạn đưa ra. Bộ lọc sản phẩm cho phép bạn xác định một tập hợp con các sản phẩm có đặc điểm cụ thể để đề xuất với khách hàng của mình. Mô hình sẽ sử dụng tất cả các sản phẩm có sẵn để tìm hiểu các thói quen nhưng chỉ sử dụng các sản phẩm khớp với bộ lọc sản phẩm trong đầu ra của nó.

1. Trong bước **Thêm thông tin sản phẩm**, hãy thêm danh mục sản phẩm của bạn cùng với thông tin cho từng sản phẩm. Ánh xạ thông tin được yêu cầu rồi chọn **Tiếp**.

1. Trong trang **Bộ lọc sản phẩm**, hãy chọn giữa các tùy chọn sau đây.

   - **Không có bộ lọc**: Sử dụng tất cả các sản phẩm trong phần dự đoán đề xuất về sản phẩm.

   - **Xác định bộ lọc sản phẩm cụ thể**: Sử dụng các sản phẩm cụ thể trong phần dự đoán đề xuất về sản phẩm.

1. Chọn **Tiếp theo**.

1. Nếu chọn xác định một bộ lọc sản phẩm, bạn cần xác định bộ lọc đó ngay bây giờ. Trong ngắn **Thuộc tính danh mục sản phẩm**, hãy chọn các thuộc tính từ *Thực thể Danh mục sản phẩm* mà bạn muốn đưa vào bộ lọc.

   :::image type="content" source="media/product-filters-sidepane.png" alt-text="Ngăn bên hiển thị thuộc tính trong thực thể danh mục sản phẩm để chọn cho bộ lọc sản phẩm.":::

1. Chọn xem bạn muốn bộ lọc sản phẩm sử dụng từ nối **và** hay **hoặc** để kết hợp hợp lý các thuộc tính mà bạn đã chọn từ danh mục sản phẩm.

   :::image type="content" source="media/product-filters-sample.png" alt-text="Cấu hình mẫu của bộ lọc sản phẩm kết hợp với các từ nối VÀ hợp lý.":::

1. Chọn **Tiếp theo**.

### <a name="set-update-schedule-and-review-configuration"></a>Đặt lịch cập nhật và xem xét cấu hình

1. Đặt tần số để đào tạo lại mô hình của bạn. Thiết đặt này rất quan trọng để cập nhật tính chính xác của các dự đoán khi dữ liệu mới được nhập vào Customer Insights. Hầu hết các doanh nghiệp đều có thể đào tạo lại một lần mỗi tháng và có dự đoán chính xác cao.

1. Chọn **Tiếp theo**.

1. Xem lại cấu hình. Bạn có thể quay lại bất kỳ phần nào của cấu hình dự đoán bằng cách chọn **Chỉnh sửa** bên dưới giá trị hiển thị. Hoặc bạn có thể chọn một bước cấu hình từ chỉ báo tiến trình.

1. Nếu tất cả giá trị được đặt cấu hình chính xác, hãy chọn **Lưu và chạy** để bắt đầu quá trình dự đoán. Trên tab **Dự đoán của tôi**, bạn có thể xem trạng thái dự đoán. Quá trình này có thể mất vài giờ mới hoàn thành, tùy thuộc vào lượng dữ liệu dùng trong dự đoán.

## <a name="review-a-prediction-status-and-results"></a>Xem lại trạng thái dự đoán và kết quả

1. Chuyển đến tab **Dự đoán của tôi** trên **Thông tin** > **Dự đoán**.
   > [!div class="mx-imgBorder"]
   > ![Xem trang Dự đoán của tôi.](media/product-recommendation-mypredictions.PNG "Xem trang Dự đoán của tôi")

1. Chọn dự đoán bạn muốn xem lại.
   - **Tên dự đoán:** Tên của dự đoán được cung cấp khi tạo.
   - **Loại dự đoán:** Loại mô hình dùng cho dự đoán
   - **Thực thể đầu ra:** Tên của thực thể để lưu trữ đầu ra của dự đoán. Bạn có thể tìm thấy thực thể có tên này trên **Dữ liệu** > **Thực thể**.
      *Điểm* trong thực thể đầu ra là giá trị đo lường đề xuất theo định lượng. Mô hình đề xuất các sản phẩm có điểm cao hơn so với các sản phẩm có điểm thấp hơn.
   - **Trường được dự đoán:** Trường này chỉ được điền cho một số loại dự đoán và không được dùng trong Dự đoán đề xuất về sản phẩm.
   - **Trạng thái:** Trạng thái hiện tại của lần chạy dự đoán.
        - **Xếp hàng đợi:"** Dự đoán hiện đang chờ quá trình khác chạy.
        - **Làm mới:** Dự đoán hiện đang chạy giai đoạn "điểm số" của quá trình để tạo ra các kết quả sẽ chuyển đến thực thể đầu ra.
        - **Không thành công:** dự đoán không thành công. Chọn **Nhật ký** để biết thêm chi tiết.
        - **Thành công:** dự đoán đã thành công. Chọn **Xem** bên dưới các hình elip dọc để xem xét dự đoán
   - **Đã chỉnh sửa:** Ngày thay đổi cấu hình của dự đoán.
   - **Làm mới lần gần đây nhất** Ngày dự đoán làm mới kết quả trong thực thể đầu ra.

1. Chọn các hình elip dọc bên cạnh dự đoán bạn muốn xem lại kết quả rồi chọn **Xem**.
   > [!div class="mx-imgBorder"]
   > ![Xem các tùy chọn trong menu hình elip dọc để dự đoán bao gồm chỉnh sửa, làm mới, xem, ghi nhật ký và xóa.](media/product-recommendation-verticalellipses.PNG "Xem các tùy chọn trong menu hình elip dọc để dự đoán bao gồm chỉnh sửa, làm mới, xem, ghi nhật ký và xóa")

1. Có năm phần dữ liệu chính trong trang kết quả:
    1. **Hiệu suất mô hình đào tạo:** A, B hoặc C là các điểm số có thể có. Điểm số này cho biết hiệu suất của dự đoán và có thể giúp bạn ra quyết định sử dụng kết quả được lưu trữ trong thực thể đầu ra.
        - Điểm số được xác định dựa trên các quy tắc sau:
            - **A** Mô hình sẽ được xem xét có chất lượng **A** nếu chỉ số "Thành công @ K" cao hơn đường cơ sở ít nhất 10%. 
            - **B** Mô hình sẽ được coi là có chất lượng **B** nếu chỉ số "Thành công @ K" là cao hơn từ 0% đến 10% so với đường cơ sở.
            - **C** Mô hình sẽ được coi là có chất lượng **C** nếu chỉ số "Thành công @ K" là nhỏ hơn đường cơ sở.

               > [!div class="mx-imgBorder"]
               > ![Xem kết quả hiệu suất của mô hình.](media/product-recommendation-modelperformance.PNG "Xem kết quả hiệu suất của mô hình")
            - **Đường cơ sở**: Mô hình lấy các sản phẩm được đề xuất nhiều nhất theo số lượng mua của tất cả các khách hàng và sử dụng các quy tắc đã học do mô hình xác định để tạo một tập hợp các đề xuất cho khách hàng. Sau đó, các dự đoán được so sánh với các sản phẩm hàng đầu, được tính bằng số lượng khách hàng đã mua sản phẩm. Nếu khách hàng có ít nhất một sản phẩm trong các sản phẩm được đề xuất cũng có trong các sản phẩm được mua nhiều nhất, thì chúng được coi là một phần của đường cơ sở. Nếu có 10 khách hàng trong số này đã mua sản phẩm được đề xuất trong tổng số 100 khách hàng, thì mức cơ bản sẽ là 10%.
            - **Thành công @ K**: Sử dụng tập hợp xác thực khoảng thời gian của các giao dịch, các đề xuất được tạo cho tất cả khách hàng và được so sánh với tập hợp xác thực của các giao dịch. Ví dụ: trong khoảng thời gian 12 tháng, tháng 12 có thể được dành làm tập hợp dữ liệu xác thực. Nếu mô hình dự đoán ít nhất một thứ bạn sẽ mua trong tháng 12 dựa trên những gì đã học được từ 11 tháng trước, thì khách hàng sẽ tăng chỉ số "Thành công @ K".

    1. **Các sản phẩm được đề xuất nhiều nhất (có kiểm đếm):** Năm sản phẩm hàng đầu được dự đoán cho khách hàng của bạn.
       > [!div class="mx-imgBorder"]
       > ![Biểu đồ hiển thị 5 sản phẩm được đề xuất hàng đầu.](media/product-recommendation-topproducts.PNG "Biểu đồ hiển thị 5 sản phẩm được đề xuất hàng đầu")

    1. **Các yếu tố đề xuất chính:** Mô hình sử dụng lịch sử giao dịch của khách hàng để đưa ra các đề xuất về sản phẩm. Mô hình học các thói quen dựa trên những giao dịch mua hàng trước đây và tìm ra những điểm tương đồng giữa khách hàng và sản phẩm. Những điểm tương đồng này sau đó được sử dụng để đưa ra các đề xuất về sản phẩm.
    Sau đây là các yếu tố có thể ảnh hưởng đến đề xuất về sản phẩm do mô hình đưa ra.
        - **Giao dịch trước đây**: Các thói quen mua hàng trước đây đã được mô hình này sử dụng để đưa ra các đề xuất về sản phẩm. Ví dụ: mô hình có thể đề xuất *Chuột Surface Arc* nếu ai đó gần đây đã mua *Surface Book 3* và *Bút Surface*. Mô hình học được rằng trước đây, nhiều khách hàng đã mua *Chuột Surface Arc* sau khi mua *Surface Book 3* và *Bút Surface*.
        - **Sự tương đồng của khách hàng**: Trước đây, những khách hàng khác có thói quen mua hàng tương tự đã mua một sản phẩm được đề xuất. Ví dụ: John được đề xuất *Tai nghe Surface 2* bởi vì Jennifer và Brad gần đây đã mua *Tai nghe Surface2*. Mô hình tin rằng John giống Jennifer và Brad vì trước đây họ đã từng có những thói quen mua hàng tương tự.
        - **Sự tương đồng của sản phẩm**: Một sản phẩm được đề xuất tương tự như các sản phẩm khác mà khách hàng đã mua trước đó. Mô hình coi hai sản phẩm là tương tự nhau nếu chúng được mua cùng nhau hoặc được mua bởi những khách hàng tương đồng. Ví dụ: ai đó nhận được đề xuất về *Ổ lưu trữ USB* bởi vì trước đó họ đã mua *Bộ chuyển đổi USB-C sang USB* và mô hình tin rằng *Ổ lưu trữ USB* tương tự như *Bộ chuyển đổi USB-C sang USB* dựa trên các thói quen mua hàng trước đây.

        Mọi đề xuất về sản phẩm đều chịu ảnh hưởng của một hoặc nhiều yếu tố này. Tỷ lệ phần trăm đề xuất (trong đó mỗi yếu tố ảnh hưởng đóng một vai trò) được minh họa trong biểu đồ. Trong ví dụ sau, 100% đề xuất bị ảnh hưởng bởi các giao dịch trước đây, 60% bị ảnh hưởng bởi sự tương đồng của khách hàng và 22% bị ảnh hưởng bởi sự tương đồng của sản phẩm. Di chuột qua các thanh trong biểu đồ để xem chính xác tỷ lệ phần trăm mà các yếu tố ảnh hưởng đã đóng góp.

        > [!div class="mx-imgBorder"]
        > ![Các yếu tố đề xuất chính.](media/product-recommendation-keyrecommendationfactors.png "Các yếu tố đề xuất chính mà mô hình học được để đưa ra các đề xuất về sản phẩm")

   1. **Thống kê dữ liệu**: Cung cấp tổng quan về số lượng giao dịch, khách hàng và sản phẩm mà mô hình xem xét. Thống kê này dựa trên dữ liệu đầu vào được dùng để tìm hiểu các thói quen và đưa ra đề xuất về sản phẩm.

      > [!div class="mx-imgBorder"]
      > ![Thống kê dữ liệu.](media/product-recommendation-datastatistics.png "Thống kê dữ liệu xoay quanh dữ liệu đầu vào được mô hình sử dụng để tìm hiểu các thói quen")

      Phần này hiển thị số liệu thống kê xoay quanh các điểm dữ liệu đã được mô hình sử dụng để tìm hiểu các thói quen và đưa ra đề xuất về sản phẩm. Chế độ lọc, như được đặt cấu hình trong cấu hình mô hình, sẽ áp dụng trên đầu ra do mô hình tạo. Tuy nhiên, mô hình sử dụng tất cả dữ liệu có sẵn để tìm hiểu các thói quen. Do đó, nếu bạn sử dụng tính năng lọc sản phẩm trong cấu hình mô hình, phần này sẽ hiển thị tổng số sản phẩm mà mô hình đã phân tích để tìm hiểu các thói quen. Số liệu này có thể khác với số lượng sản phẩm khớp với tiêu chí lọc đã xác định.

   1. **Đề xuất sản phẩm có độ tin cậy cao:** Một mẫu đề xuất được cung cấp cho khách hàng của bạn mà mô hình đó tin rằng khách hàng có thể mua.    
      Nếu danh mục sản phẩm được thêm vào, ID sản phẩm sẽ được thay thế bằng tên sản phẩm. Tên sản phẩm cung cấp thông tin trực quan và hữu ích hơn về các dự đoán.
       > [!div class="mx-imgBorder"]
       > ![Danh sách hiển thị các đề xuất có độ tin cậy cao cho một nhóm khách hàng cá nhân được chọn.](media/product-recommendation-highconfidence.PNG "Danh sách hiển thị các đề xuất có độ tin cậy cao cho một nhóm khách hàng cá nhân được chọn")

## <a name="manage-predictions"></a>Quản lý dự đoán

Bạn có thể tối ưu hóa, khắc phục sự cố, làm mới hoặc xóa dự đoán. Hãy xem lại báo cáo khả năng sử dụng dữ liệu đầu vào để tìm hiểu cách giúp dự đoán nhanh hơn và đáng tin cậy hơn. Để biết thêm thông tin, hãy xem phần [Quản lý dự đoán](manage-predictions.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
