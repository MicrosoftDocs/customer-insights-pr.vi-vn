---
title: Dự đoán rời bỏ giao dịch
description: Dự đoán xem khách hàng có nguy cơ không mua sản phẩm hoặc dịch vụ của bạn nữa không.
ms.date: 11/12/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 43fcd37f8dd71e2890334a4cc53d49dae97d63c6
ms.sourcegitcommit: 6d5dd572f75ba4c0303ec77c3b74e4318d52705c
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 04/16/2021
ms.locfileid: "5906882"
---
# <a name="transactional-churn-prediction-preview"></a>Dự đoán rời bỏ giao dịch (bản xem trước)

Dự đoán rời bỏ giao dịch giúp dự đoán liệu khách hàng có mua sản phẩm hoặc dịch vụ của bạn trong một khoảng thời gian nhất định hay không. Bạn có thể tạo dự đoán rời bỏ mới trên **Thông tin** > **Dự đoán**. Chọn **Dự đoán của tôi** để xem các dự đoán khác mà bạn đã tạo.

> [!TIP]
> Hãy thử hướng dẫn cho dự đoán rời bỏ giao dịch bằng dữ liệu mẫu: [Hướng dẫn mẫu về dự đoán rời bỏ giao dịch (bản xem trước)](sample-guide-predict-transactional-churn.md).

## <a name="prerequisites"></a>Điều kiện tiên quyết

- Ít nhất [Quyền của người đóng góp](permissions.md) trong Customer Insights.
- Kiến thức kinh doanh để hiểu ý nghĩa của việc rời đi với doanh nghiệp bạn. Chúng tôi hỗ trợ các định nghĩa rời bỏ dựa trên thời gian, có nghĩa là một khách hàng được coi là đã rời bỏ sau một khoảng thời gian không mua hàng.
- Dữ liệu về các giao dịch/mua hàng của bạn và lịch sử của chúng:
    - Định danh giao dịch để phân biệt mua hàng/giao dịch.
    - Định danh khách hàng để so khớp các giao dịch với khách hàng của bạn.
    - Ngày sự kiện giao dịch, xác định ngày giao dịch diễn ra.
    - Lược đồ dữ liệu ngữ nghĩa cho mua hàng/giao dịch yêu cầu thông tin sau:
        - **ID giao dịch:** Mã định danh duy nhất của một giao dịch mua hàng.
        - **Ngày giao dịch:** Ngày mua hoặc giao dịch.
        - **Giá trị của giao dịch:** Số lượng tiền tệ/giá trị số của giao dịch/mặt hàng.
        - (Không bắt buộc) **ID sản phẩm duy nhất:** ID của sản phẩm hoặc dịch vụ đã mua nếu dữ liệu của bạn ở cấp mục hàng.
        - (Không bắt buộc) **Liệu giao dịch này có phải là trả lại hay không:** Trường true/false xác định liệu giao dịch có phải là trả lại hay không. Nếu **Giá trị của giao dịch** là âm, chúng tôi cũng sẽ sử dụng thông tin này để suy ra lợi nhuận.
- (Tùy chọn) Dữ liệu về các hoạt động của khách hàng:
    - Mã định danh hoạt động để phân biệt các hoạt động cùng loại.
    - Mã định danh khách hàng để khớp hoạt động với khách hàng.
    - Thông tin hoạt động chứa tên và ngày của hoạt động.
    - Lược đồ dữ liệu ngữ nghĩa cho hoạt động của khách hàng bao gồm:
        - **Khóa chính:** Mã định danh duy nhất cho một hoạt động. Ví dụ: một lượt truy cập trang web hoặc hồ sơ sử dụng cho thấy khách hàng đã thử một mẫu sản phẩm của bạn.
        - **Dấu thời gian:** Ngày và giờ của sự kiện do khóa chính xác định.
        - **Sự kiện:** Tên của sự kiện bạn muốn sử dụng. Ví dụ: trường có tên "UserAction" trong cửa hàng tạp hóa có thể được khách hàng sử dụng phiếu giảm giá.
        - **Chi tiết:** Thông tin chi tiết về sự kiện. Ví dụ: trường có tên "CouponValue" trong cửa hàng tạp hóa có thể là giá trị tiền tệ của phiếu giảm giá.
- Đặc điểm dữ liệu được đề xuất:
    - Đủ dữ liệu lịch sử: Dữ liệu giao dịch cho ít nhất gấp đôi khoảng thời gian đã chọn. Tốt nhất là hai đến ba năm dữ liệu gói đăng ký. 
    - Nhiều giao dịch mua trên mỗi khách hàng: Lý tưởng là tối thiểu hai giao dịch trở lên trên mỗi khách hàng.
    - Số lượng khách hàng: Tối thiểu 10 hồ sơ khách hàng, tốt nhất là 1.000 khách hàng. Mô hình sẽ không thành công nếu dưới 10 khách hàng và không đủ dữ liệu lịch sử.
    - Tính đầy đủ của dữ liệu: Ít hơn 20% giá trị bị thiếu trong trường dữ liệu của thực thể được cung cấp.

> [!NOTE]
> Đối với doanh nghiệp có tần suất mua hàng của khách hàng cao (vài tuần một lần), bạn nên chọn khoảng thời gian dự đoán ngắn hơn và xác định rủi ro khách hàng ngừng giao dịch. Đối với tần suất mua hàng thấp (vài tháng một lần hoặc một năm một lần), hãy chọn khoảng thời gian dự đoán dài hơn và xác định rủi ro khách hàng ngừng giao dịch.

## <a name="create-a-transactional-churn-prediction"></a>Tạo dự đoán rời bỏ giao dịch

1. Trong Customer Insights, chuyển đến phần **Thông tin** > **Dự đoán**.

1. Chọn ngăn xếp **Mô hình khách hàng rời đi (bản xem trước)** và chọn **Sử dụng mô hình này**.
   
1. Trong ngăn xếp **Mô hình khách hàng rời đi**, chọn **Giao dịch** và chọn **Bắt đầu**.

:::image type="content" source="media/select-transaction-churn.PNG" alt-text="Ảnh chụp màn hình với tùy chọn giao dịch đã chọn trong ngăn Mô hình khách hàng rời đi.":::

### <a name="name-model"></a>Đặt tên mô hình

1. Cung cấp tên cho mô hình để phân biệt với các mô hình khác.

1. Cung cấp tên cho thực thể đầu ra chỉ bằng chữ cái và chữ số, không có khoảng trắng. Đó là tên mà thực thể mô hình sẽ sử dụng. 

1. Chọn **Tiếp theo**.

### <a name="define-customer-churn"></a>Xác định khách hàng rời đi

1. Đặt khoảng thời gian trong ngày để dự đoán khả năng rời đi trong trường **Xác định những khách hàng có thể rời đi trong thời gian tới**. Ví dụ: dự đoán nguy cơ khách hàng rời đi trong 90 ngày tới để phù hợp với nỗ lực duy trì hoạt động tiếp thị của bạn. Việc dự đoán rủi ro rời đi trong một khoảng thời gian dài hơn hoặc ngắn hơn có thể gây khó khăn hơn cho việc giải quyết các yếu tố trong hồ sơ rủi ro rời đi của bạn, nhưng nó phụ thuộc vào yêu cầu kinh doanh cụ thể của bạn. 
   >[!TIP]
   > Bạn có thể chọn **Lưu và đóng** bất cứ lúc nào để lưu dự đoán dưới dạng bản nháp. Bạn sẽ tìm thấy dự đoán nháp trong tab **Dự đoán của tôi** để tiếp tục.

1. Nhập số ngày để xác định thời gian rời đi trong trường **Một khách hàng đã rời đi nếu họ không mua hàng trong:**. Ví dụ: nếu khách hàng không mua hàng nào trong 30 ngày qua, họ có thể được coi là đã bỏ qua doanh nghiệp của bạn. 

1. Chọn **Tiếp** tiếp tục

### <a name="add-required-data"></a>Thêm dữ liệu bắt buộc

1. Chọn **Thêm dữ liệu** cho **Lịch sử mua hàng** và chọn thực thể cung cấp thông tin lịch sử giao dịch/mua hàng như được mô tả trong [điều kiện tiên quyết](#prerequisites).

1. Ánh xạ các trường ngữ nghĩa với các thuộc tính trong thực thể lịch sử mua hàng của bạn và chọn **Tiếp theo**. Để biết mô tả về các trường, hãy xem [điều kiện tiên quyết](#prerequisites).

   :::image type="content" source="media/model-map-purchase-entity.PNG" alt-text="Ánh xạ các trường ngữ nghĩa của thực thể mua.":::

1. Nếu các trường bên dưới không được điền, hãy định cấu hình mối quan hệ từ thực thể lịch sử mua hàng của bạn với thực thể Khách hàng.
    1. Chọn **Thực thể lịch sử mua hàng**.
    1. Chọn **Trường** xác định khách hàng trong thực thể lịch sử mua hàng. Trường đó cần liên quan đến ID khách hàng chính của thực thể khách hàng.
    1. Chọn **Thực thể khách hàng** khớp với thực thể khách hàng chính của bạn.
    1. Nhập tên mô tả mối quan hệ.

    :::image type="content" source="media/model-purchase-join.PNG" alt-text="Trang lịch sử mua hàng hiển thị việc tạo mối quan hệ với khách hàng.":::
   
1. Chọn **Tiếp theo**.

1. Theo tùy chọn, chọn **Thêm dữ liệu** cho **Hoạt động của khách hàng**. Chọn thực thể cung cấp thông tin hoạt động của khách hàng như được mô tả trong điều kiện tiên quyết.

1. Ánh xạ các trường ngữ nghĩa với các thuộc tính trong thực thể hoạt động của khách hàng và chọn **Tiếp theo**. Để biết mô tả về các trường, hãy xem [điều kiện tiên quyết](#prerequisites).

   :::image type="content" source="media/map-transaction-data-fields.png" alt-text="Ánh xạ các trường của khách hàng cho dữ liệu giao dịch.":::

1. Chọn loại hoạt động phù hợp với loại hoạt động khách hàng mà bạn đang đặt cấu hình. Chọn **Tạo mới** và chọn một loại hoạt động có sẵn hoặc tạo một loại mới.

1. Bạn sẽ cần đặt cấu hình mối quan hệ từ thực thể hoạt động khách hàng tới thực thể khách hàng.
    1. Chọn trường xác định khách hàng trong bảng hoạt động của khách hàng. Nó có thể liên quan trực tiếp đến ID khách hàng chính của thực thể Khách hàng của bạn.
    1. Chọn thực thể khách hàng khớp với thực thể khách hàng chính của bạn
    1. Nhập tên mô tả mối quan hệ.

1. Chọn **Lưu**.

1. Nếu bạn có bất kỳ hoạt động khách hàng nào khác mà bạn muốn bao gồm, hãy lặp lại các bước ở trên.

1. Chọn **Tiếp theo**.

### <a name="set-schedule-and-review-configuration"></a>Đặt lịch và xem xét cấu hình

1. Đặt tần số để đào tạo lại mô hình của bạn. Cài đặt này rất quan trọng để cập nhật độ chính xác của các dự đoán vì dữ liệu mới được nhập vào thông tin chi tiết về đối tượng. Hầu hết các doanh nghiệp đều có thể đào tạo lại một lần mỗi tháng và có dự đoán chính xác cao.

1. Chọn **Tiếp theo**.

1. Xem lại cấu hình dự đoán. Bạn có thể quay lại các bước trước bằng cách chọn **Chỉnh sửa** dưới giá trị hiển thị. Hoặc bạn có thể chọn một bước cấu hình từ chỉ báo tiến trình.

1. Nếu tất cả giá trị được đặt cấu hình chính xác, hãy chọn **Lưu và chạy** để bắt đầu quá trình dự đoán. Trên tab **Dự đoán của tôi**, bạn có thể xem trạng thái dự đoán. Quá trình này có thể mất vài giờ mới hoàn thành, tùy thuộc vào lượng dữ liệu dùng trong dự đoán.

## <a name="review-a-prediction-status-and-results"></a>Xem lại trạng thái dự đoán và kết quả

1. Đi đến **Thông tin** > **Dự đoán** và chọn tab **Dự đoán của tôi**.

1. Chọn dự đoán bạn muốn xem lại.
   - **Tên dự đoán:** Tên của dự đoán được cung cấp khi tạo.
   - **Loại dự đoán:** Loại mô hình được sử dụng cho dự đoán
   - **Thực thể đầu ra:** Tên của thực thể để lưu trữ đầu ra của dự đoán. Bạn có thể tìm thấy thực thể có tên này trên **Dữ liệu** > **Thực thể**.    
     Trong thực thể đầu ra, *ChurnScore* là xác suất dự đoán về khả năng khách hàng ngừng sử dụng gói đăng ký và *IsChurn* là một nhãn nhị phân dựa trên *ChurnScore* với ngưỡng 0,5. Ngưỡng mặc định có thể không hoạt động trong trường hợp của bạn. [Tạo một phân khúc mới](segments.md#create-a-new-segment) với ngưỡng bạn muốn.
     Không phải khách hàng nào cũng nhất thiết phải là khách hàng hiện hoạt. Một số khách hàng có thể không có bất kỳ hoạt động nào trong một thời gian dài và được coi là đã ngừng giao dịch, dựa trên sự xác định của bạn về khách hàng ngừng giao dịch. Việc dự đoán rủi ro khách hàng ngừng giao dịch đối với những khách hàng đã ngừng giao dịch là không hữu ích vì họ không phải là đối tượng cần quan tâm.
   - **Trường dự đoán:** Trường này chỉ được điền cho một số loại dự đoán và không được sử dụng trong dự đoán rời đi.
   - **Trạng thái:** Trạng thái chạy dự đoán.
        - **Đã xếp hàng:** Dự đoán đang đợi các quy trình khác chạy.
        - **Làm mới:** Dự đoán hiện đang chạy để tạo ra kết quả sẽ chuyển vào thực thể đầu ra.
        - **Thất bại:** Dự đoán chạy không thành công. [Xem lại nhật ký](#troubleshoot-a-failed-prediction) để biết thêm chi tiết.
        - **Đã thành công:** Dự đoán đã thành công. Chọn **Xem** bên dưới các hình elip dọc để xem xét dự đoán
   - **Đã chỉnh sửa:** Ngày thay đổi cấu hình của dự đoán.
   - **Làm mới lần gần đây nhất** Ngày dự đoán làm mới kết quả trong thực thể đầu ra.

1. Chọn các hình elip dọc bên cạnh dự đoán bạn muốn xem lại kết quả rồi chọn **Xem**.

   :::image type="content" source="media/model-subs-view.PNG" alt-text="Kiểm soát dạng xem để xem kết quả của dự đoán.":::   

1. Có 3 phần dữ liệu chính trong trang kết quả:
    1. **Hiệu suất mô hình đào tạo:** A, B hoặc C là các điểm số có thể có. Điểm số này cho biết hiệu suất của dự đoán và có thể giúp bạn ra quyết định sử dụng kết quả được lưu trữ trong thực thể đầu ra. Điểm số được xác định dựa trên các quy tắc sau:
         
         - **A** khi mô hình dự đoán chính xác ít nhất 50% tổng số dự đoán và khi tỷ lệ dự đoán chính xác cho khách hàng đã dự đoán lớn hơn tỷ lệ cơ sở ít nhất 10%.
            
         - **B** khi mô hình dự đoán chính xác ít nhất 50% tổng số dự đoán và khi tỷ lệ dự đoán chính xác cho khách hàng đã rời đi lớn hơn tỷ lệ cơ sở tối đa 10%.
            
         - **C** khi mô hình dự đoán chính xác dưới 50% tổng số dự đoán hoặc khi tỷ lệ dự đoán chính xác cho khách hàng đã rời đi nhỏ hơn tỷ lệ cơ sở.
               
         - **Đường cơ sở** lấy đầu vào cửa sổ thời gian dự đoán cho mô hình (ví dụ: một năm) và mô hình tạo ra các phần thời gian khác nhau bằng cách chia nó cho 2 cho đến khi đạt một tháng hoặc ít hơn. Nó sử dụng các phân số này để tạo quy tắc công việc cho những khách hàng chưa mua hàng trong khung thời gian này. Những khách hàng này được coi là đã rời đi. Quy tắc công việc dựa trên thời gian với khả năng dự đoán cao nhất ai có khả năng rời đi được chọn làm mô hình cơ sở.
            
    1. **Khả năng rời bỏ (số lượng khách hàng):** Các nhóm khách hàng dựa trên rủi ro rời bỏ dự đoán của họ. Dữ liệu này có thể giúp bạn về sau này nếu muốn tạo phân khúc khách hàng có khả năng rời bỏ cao. Những phân khúc này giúp hiểu được điểm cắt nên dành cho các thành phần phân khúc.
       
    1. **Các yếu tố có ảnh hưởng nhất:** Có nhiều yếu tố được tính đến khi tạo dự đoán. Mỗi yếu tố có tầm quan trọng được tính toán cho các dự đoán tổng hợp mà một mô hình tạo ra. Bạn có thể sử dụng các yếu tố này để giúp xác nhận kết quả dự đoán. Hoặc bạn có thể sử dụng thông tin này sau để [tạo phân khúc](segments.md) có thể giúp ảnh hưởng đến rủi ro rời bỏ của khách hàng.

## <a name="troubleshoot-a-failed-prediction"></a>Khắc phục sự cố dự đoán không thành công

1. Đi đến **Thông tin** > **Dự đoán** và chọn tab **Dự đoán của tôi**.

1. Chọn dấu chấm lửng dọc bên cạnh dự đoán mà bạn muốn xem nhật ký lỗi.

1. Chọn **Nhật ký**.

1. Xem lại tất cả lỗi. Có một số loại lỗi có thể xảy ra và chúng mô tả nguyên nhân gây ra lỗi. Ví dụ: một lỗi không đủ dữ liệu để dự đoán chính xác thường được giải quyết bằng cách tải thêm dữ liệu vào Customer Insights.

## <a name="refresh-a-prediction"></a>Làm mới một dự đoán

Các dự đoán sẽ tự động làm mới trên cùng một [trình làm mới dữ liệu](system.md#schedule-tab) như đặt cấu hình trong thiết đặt. Bạn cũng có thể làm mới chúng theo cách thủ công.

1. Đi đến **Thông tin** > **Dự đoán** và chọn tab **Dự đoán của tôi**.

1. Chọn các hình elip dọc bên cạnh dự đoán bạn muốn làm mới.

1. Chọn **Làm mới**.

## <a name="delete-a-prediction"></a>Xóa dự đoán

Xóa dự đoán cũng xóa thực thể đầu ra của nó.

1. Đi đến **Thông tin** > **Dự đoán** và chọn tab **Dự đoán của tôi**.

1. Chọn các hình elip dọc bên cạnh dự đoán bạn muốn xóa.

1. Chọn **Xóa**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
