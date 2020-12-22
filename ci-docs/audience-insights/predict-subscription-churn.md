---
title: Dự đoán khả năng rời bỏ đăng ký
description: Dự đoán xem khách hàng có nguy cơ không sử dụng sản phẩm hoặc dịch vụ đăng ký của công ty bạn nữa không.
ms.date: 08/19/2020
ms.reviewer: zacook
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 03178fc1bfe611b1b0ced08bbbef876035875825
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643754"
---
# <a name="subscription-churn-prediction-preview"></a>Dự đoán sự rời đi đăng ký (xem trước)

Dự đoán sự rời đi đăng ký giúp dự đoán xem khách hàng có nguy cơ không sử dụng sản phẩm hoặc dịch vụ đăng ký của công ty bạn nữa không. Bạn có thể tạo dự đoán rời đi đăng ký mới trên trang **Thông tin** > **Dự đoán**. Chọn **Dự đoán của tôi** để xem các dự đoán khác mà bạn đã tạo.

> [!TIP]
> Hãy thử hướng dẫn cho dự đoán rời khỏi đăng ký bằng dữ liệu mẫu: [Hướng dẫn mẫu về dự đoán rời khỏi đăng ký](sample-guide-predict-subscription-churn.md).

## <a name="prerequisites"></a>Điều kiện tiên quyết

- Tối thiểu [Quyền của cộng tác viên](permissions.md).
- Kiến thức kinh doanh để hiểu ý nghĩa của việc rời đi với doanh nghiệp bạn. Chúng tôi hỗ trợ các định nghĩa về rời đi theo thời gian, nghĩa là một khách hàng được xem là đã rời đi một thời gian sau khi gói đăng ký kết thúc.
- Dữ liệu về gói đăng ký và lịch sử:
    - Mã định danh đăng ký để phân biệt đăng ký.
    - Mã định danh khách hàng để khớp đăng ký với khách hàng.
    - Ngày sự kiện đăng ký, trong đó xác định ngày bắt đầu, ngày kết thúc và ngày diễn ra sự kiện đăng ký.
    - Thông tin đăng ký để xác định xem đó có phải là đăng ký định kỳ không và tần suất gia hạn.
    - Lược đồ dữ liệu ngữ nghĩa cho các đăng ký yêu cầu thông tin sau:
        - **ID đăng ký:** Mã định danh duy nhất của một đăng ký.
        - **Ngày kết thúc đăng ký:** Ngày đăng ký hết hạn cho khách hàng.
        - **Ngày bắt đầu đăng ký:** Ngày đăng ký bắt đầu cho khách hàng.
        - **Ngày giao dịch:** Ngày xảy ra thay đổi đăng ký. Ví dụ: một khách hàng mua hoặc hủy đăng ký.
        - **Đây có phải là đăng ký định kỳ:** Trường đúng/sai boolean xác định xem đăng ký có gia hạn bằng cùng ID đăng ký mà không cần sự can thiệp của khách hàng không
        - **Tần suất lặp lại (tính theo tháng):** Đối với đăng ký định kỳ, đó là khoảng thời gian đăng ký sẽ gia hạn. Tần suất này được biểu thị bằng tháng. Ví dụ: đăng ký hàng năm tự động gia hạn cho khách hàng mỗi năm cho một năm khác có giá trị 12.
        - (Không bắt buộc) **Số tiền đăng ký:** Số tiền mà khách hàng trả cho việc gia hạn đăng ký. Số tiền đó có thể giúp xác định các mẫu cho các cấp độ đăng ký khác nhau.
- Dữ liệu về hoạt động của khách hàng:
    - Mã định danh hoạt động để phân biệt các hoạt động cùng loại.
    - Mã định danh khách hàng để khớp hoạt động với khách hàng.
    - Thông tin hoạt động chứa tên và ngày của hoạt động.
    - Lược đồ dữ liệu ngữ nghĩa cho hoạt động của khách hàng bao gồm:
        - **Khóa chính:** Mã định danh duy nhất cho một hoạt động. Ví dụ: một lượt truy cập trang web hoặc bản ghi sử dụng cho thấy khách hàng đã xem một tập chương trình truyền hình.
        - **Dấu thời gian:** Ngày và giờ của sự kiện do khóa chính xác định.
        - **Sự kiện:** Tên của sự kiện bạn muốn sử dụng. Ví dụ: một trường có tên "UserAction" trong dịch vụ truyền phát video có thể có giá trị là "Đã xem".
        - **Chi tiết:** Thông tin chi tiết về sự kiện. Ví dụ: một trường có tên "ShowTitle" trong dịch vụ truyền phát video có thể có giá trị là video mà khách hàng đã xem.
   > [!NOTE]
   > Bạn sẽ cần ít nhất hai bản ghi hoạt động cho 50% khách hàng mà bạn muốn tính toán sự rời bỏ.

## <a name="create-a-subscription-churn-prediction"></a>Tạo dự đoán rời bỏ đăng ký

1. Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Thông tin** > **Dự đoán**.
1. Chọn tiêu đề **Mô hình rời bỏ đăng ký (xem trước)** và chọn **Sử dụng mô hình này**.
   > [!div class="mx-imgBorder"]
   > ![Tiêu đề mô hình rời bỏ đăng ký có nút Sử dụng mô hình này](media/subscription-churn-usethismodel.PNG "Tiêu đề mô hình rời bỏ đăng ký có nút Sử dụng mô hình này")

### <a name="name-model"></a>Đặt tên mô hình

1. Cung cấp tên cho mô hình để phân biệt với các mô hình khác.
1. Cung cấp tên cho thực thể đầu ra chỉ bằng chữ cái và chữ số, không có khoảng trắng. Đó là tên mà thực thể mô hình sẽ sử dụng. Sau đó, chọn **Tiếp**.

### <a name="define-customer-churn"></a>Xác định khách hàng rời đi

1. Nhập số **Ngày kể từ khi đăng ký kết thúc** mà doanh nghiệp của bạn xem xét một khách hàng là đang ở trong trạng thái rời đi. Giai đoạn này thường giống như các hoạt động kinh doanh như chào hàng hoặc các nỗ lực tiếp thị khác nhằm cố ngăn chặn mất khách hàng.
1. Nhập số lượng **Ngày xem xét trong tương lai để dự đoán sự rời đi** để đặt cửa sổ dự đoán sự rời bỏ. Ví dụ: để dự đoán nguy cơ khách hàng rời đi trong 90 ngày tới để phù hợp với nỗ lực duy trì hoạt động tiếp thị của bạn. Việc dự đoán rủi ro rời bỏ trong khoảng thời gian dài hơn hoặc ngắn hơn có thể khiến việc giải quyết các yếu tố trong hồ sơ rủi ro rời bỏ trở nên khó khăn hơn, nhưng điều này phụ thuộc nhiều vào các yêu cầu kinh doanh cụ thể của bạn. Chọn **Tiếp** tiếp tục
   >[!TIP]
   > Bạn có thể chọn **Lưu và đóng** bất cứ lúc nào để lưu dự đoán dưới dạng bản nháp. Bạn sẽ tìm thấy dự đoán nháp trong tab **Dự đoán của tôi** để tiếp tục.

### <a name="add-required-data"></a>Thêm dữ liệu bắt buộc

1. Chọn **Thêm dữ liệu** cho **Lịch sử đăng ký** và chọn thực thể cung cấp thông tin lịch sử đăng ký như mô tả trong [điều kiện tiên quyết](#prerequisites).
1. Nếu các trường bên dưới không được điền, hãy đặt cấu hình mối quan hệ từ thực thể lịch sử đăng ký tới thực thể Khách hàng.
    1. Chọn **Thực thể lịch sử đăng ký**.
    1. Chọn **Trường** xác định khách hàng trong thực thể lịch sử đăng ký. Trường đó cần liên quan đến ID khách hàng chính của thực thể khách hàng.
    1. Chọn **Thực thể khách hàng** khớp với thực thể khách hàng chính của bạn.
    1. Nhập tên mô tả mối quan hệ.
       > [!div class="mx-imgBorder"]
       > ![Trang lịch sử đăng ký thể hiện việc tạo mối quan hệ với khách hàng](media/subscription-churn-subscriptionhistoryrelationship.PNG "Trang lịch sử đăng ký thể hiện việc tạo mối quan hệ với khách hàng")
1. Chọn **Tiếp theo**.
1. Ánh xạ các trường ngữ nghĩa đến các thuộc tính trong thực thể lịch sử đăng ký rồi chọn **Lưu**. Để biết mô tả về các trường, hãy xem [điều kiện tiên quyết](#prerequisites).
   > [!div class="mx-imgBorder"]
   > ![Trang lịch sử đăng ký hiển thị các thuộc tính ngữ nghĩa được ánh xạ tới các trường trong thực thể lịch sử đăng ký đã chọn.](media/subscription-churn-subscriptionhistorymapping.PNG "Trang lịch sử đăng ký hiển thị các thuộc tính ngữ nghĩa được ánh xạ tới các trường trong thực thể lịch sử đăng ký đã chọn.")
1. Chọn **Thêm dữ liệu** cho **Hoạt động khách hàng** rồi chọn thực thể cung cấp thông tin về hoạt động khách hàng như mô tả trong điều kiện tiên quyết.
1. Chọn loại hoạt động phù hợp với loại hoạt động khách hàng mà bạn đang đặt cấu hình.  Chọn **Tạo mới** và cung cấp tên nếu bạn không thấy tùy chọn khớp với loại hoạt động bạn cần.
1. Bạn sẽ cần đặt cấu hình mối quan hệ từ thực thể hoạt động khách hàng tới thực thể khách hàng.
    1. Chọn trường xác định khách hàng trong bảng hoạt động khách hàng, có thể liên quan trực tiếp đến ID khách hàng chính của thực thể khách hàng.
    1. Chọn thực thể khách hàng khớp với thực thể khách hàng chính của bạn
    1. Nhập tên mô tả mối quan hệ.
1. Chọn **Tiếp theo**.
1. Ánh xạ các trường ngữ nghĩa đến các thuộc tính trong thực thể hoạt động khách hàng rồi chọn **Lưu**. Để biết mô tả về các trường, hãy xem [điều kiện tiên quyết](#prerequisites).
1. (Tùy chọn) Nếu bạn có bất kỳ hoạt động nào khác của khách hàng mà bạn muốn đưa vào, hãy lặp lại các bước ở trên.
   > [!div class="mx-imgBorder"]
   > ![Xác định mối quan hệ của thực thể](media/subscription-churn-customeractivitiesmapping.PNG "Trang hoạt động khách hàng hiển thị các thuộc tính ngữ nghĩa được ánh xạ tới các trường trong thực thể hoạt động khách hàng")
1. Chọn **Tiếp theo**.

### <a name="set-schedule-and-review-configuration"></a>Đặt lịch và xem xét cấu hình

1. Đặt tần số để đào tạo lại mô hình của bạn. Cài đặt này rất quan trọng để cập nhật độ chính xác của các dự đoán vì dữ liệu mới được nhập vào thông tin chi tiết về đối tượng. Hầu hết các doanh nghiệp đều có thể đào tạo lại một lần mỗi tháng và có dự đoán chính xác cao.
1. Chọn **Tiếp theo**.
1. Xem lại cấu hình. Bạn có thể quay lại bất kỳ phần nào của cấu hình dự đoán bằng cách chọn **Chỉnh sửa** bên dưới giá trị hiển thị. Hoặc bạn có thể chọn một bước cấu hình từ chỉ báo tiến trình.
1. Nếu tất cả giá trị được đặt cấu hình chính xác, hãy chọn **Lưu và chạy** để bắt đầu quá trình dự đoán. Trên tab **Dự đoán của tôi**, bạn có thể xem trạng thái dự đoán. Quá trình này có thể mất vài giờ mới hoàn thành, tùy thuộc vào lượng dữ liệu dùng trong dự đoán.

## <a name="review-a-prediction-status-and-results"></a>Xem lại trạng thái dự đoán và kết quả

1. Chuyển đến tab **Dự đoán của tôi** trên **Thông tin** > **Dự đoán**.
   > [!div class="mx-imgBorder"]
   > ![Xem trang Dự đoán của tôi](media/subscription-churn-mypredictions.PNG "Xem trang Dự đoán của tôi")
1. Chọn dự đoán bạn muốn xem lại.
   - **Tên dự đoán:** Tên của dự đoán được cung cấp khi tạo.
   - **Loại dự đoán:** Loại mô hình dùng cho dự đoán
   - **Thực thể đầu ra:** Tên của thực thể để lưu trữ đầu ra của dự đoán. Bạn có thể tìm thấy thực thể có tên này trên **Dữ liệu** > **Thực thể**.
   - **Trường dự đoán:** Trường này chỉ được điền cho một số loại dự đoán và không được sử dụng trong dự đoán rời bỏ đăng ký.
   - **Trạng thái:** Trạng thái hiện tại của lần chạy dự đoán.
        - **Xếp hàng đợi:"** Dự đoán hiện đang chờ quá trình khác chạy.
        - **Làm mới:** Dự đoán hiện đang chạy giai đoạn "điểm số" của quá trình để tạo ra các kết quả sẽ chuyển đến thực thể đầu ra.
        - **Không thành công:** dự đoán không thành công. Chọn **Nhật ký** để biết thêm chi tiết.
        - **Thành công:** dự đoán đã thành công. Chọn **Xem** bên dưới các hình elip dọc để xem xét dự đoán
   - **Đã chỉnh sửa:** Ngày thay đổi cấu hình của dự đoán.
   - **Làm mới lần gần đây nhất** Ngày dự đoán làm mới kết quả trong thực thể đầu ra.
1. Chọn các hình elip dọc bên cạnh dự đoán bạn muốn xem lại kết quả rồi chọn **Xem**.
   > [!div class="mx-imgBorder"]
   > ![Xem các tùy chọn trong menu hình elip dọc để dự đoán bao gồm chỉnh sửa, làm mới, xem, ghi nhật ký và xóa](media/subscription-churn-verticalellipses.PNG "Xem các tùy chọn trong menu hình elip dọc để dự đoán bao gồm chỉnh sửa, làm mới, xem, ghi nhật ký và xóa")
1. Có 3 phần dữ liệu chính trong trang kết quả:
    1. **Hiệu suất mô hình đào tạo:** A, B hoặc C là các điểm số có thể có. Điểm số này cho biết hiệu suất của dự đoán và có thể giúp bạn ra quyết định sử dụng kết quả được lưu trữ trong thực thể đầu ra.
        - Điểm số được xác định dựa trên các quy tắc sau:
            - **A** khi mô hình dự đoán chính xác 50% tổng số dự đoán và khi tỷ lệ dự đoán chính xác đối với khách hàng rời đi lớn hơn so với tỷ lệ rời đi trung bình trước đây ít nhất là 10%.
            - **B** khi mô hình dự đoán chính xác 50% tổng số dự đoán và khi tỷ lệ dự đoán chính xác đối với khách hàng rời đi lớn hơn so với tỷ lệ rời đi trung bình trước đây tối đa là là 10%.
            - **C** khi mô hình dự đoán chính xác dưới 50% tổng số dự đoán, hoặc khi tỷ lệ dự đoán chính xác đối với khách hàng rời đi thấp hơn tỷ lệ rời đi trung bình trước đây.
               > [!div class="mx-imgBorder"]
               > ![Xem kết quả hiệu suất của mô hình](media/subscription-churn-modelperformance.PNG "Xem kết quả hiệu suất của mô hình")
    1. **Khả năng rời bỏ (số lượng khách hàng):** Các nhóm khách hàng dựa trên rủi ro rời bỏ dự đoán của họ. Dữ liệu này có thể giúp bạn về sau này nếu muốn tạo phân khúc khách hàng có khả năng rời bỏ cao. Những phân khúc này giúp hiểu được điểm cắt nên dành cho các thành phần phân khúc.
       > [!div class="mx-imgBorder"]
       > ![Biểu đồ hiển thị mức độ phân phối kết quả rời bỏ, chia thành các phạm vi từ 0-100%](media/subscription-churn-resultdistribution.PNG "Biểu đồ hiển thị mức độ phân phối kết quả rời bỏ, chia thành các phạm vi từ 0-100%")
    1. **Các yếu tố có ảnh hưởng nhất:** Có nhiều yếu tố được tính đến khi tạo dự đoán. Mỗi yếu tố có tầm quan trọng được tính toán cho các dự đoán tổng hợp mà một mô hình tạo ra. Bạn có thể sử dụng các yếu tố này để giúp xác nhận kết quả dự đoán. Hoặc bạn có thể sử dụng thông tin này sau để [tạo phân khúc](segments.md) có thể giúp ảnh hưởng đến rủi ro rời bỏ của khách hàng.
       > [!div class="mx-imgBorder"]
       > ![Danh sách cho thấy các yếu tố ảnh hưởng và tầm quan trọng của chúng trong việc dự đoán kết quả rời bỏ](media/subscription-churn-influentialfactors.PNG "Danh sách cho thấy các yếu tố ảnh hưởng và tầm quan trọng của chúng trong việc dự đoán kết quả rời bỏ")

## <a name="fix-a-failed-prediction"></a>Khắc phục một dự đoán không thành công

1. Chuyển đến tab **Dự đoán của tôi** trên **Thông tin** > **Dự đoán**.
1. Chọn một dự đoán mà bạn muốn xem nhật ký lỗi rồi chọn **Nhật ký**.
   > [!div class="mx-imgBorder"]
   > ![Xem thanh menu kết quả bao gồm các nút đóng, chỉnh sửa mô hình và nhật ký](media/subscription-churn-logsbutton.PNG "Xem thanh menu kết quả bao gồm các nút đóng, chỉnh sửa mô hình và nhật ký")
1. Xem lại tất cả lỗi. Có một số loại lỗi có thể xảy ra và chúng mô tả nguyên nhân gây ra lỗi. Ví dụ: lỗi không có đủ dữ liệu để dự đoán chính xác thường được giải quyết bằng cách tải thêm dữ liệu.

## <a name="refresh-a-prediction"></a>Làm mới một dự đoán

Các dự đoán sẽ tự động làm mới trên cùng một [trình làm mới dữ liệu](system.md#schedule-tab) như đặt cấu hình trong thiết đặt.

1. Chuyển đến tab **Dự đoán của tôi** trên **Thông tin** > **Dự đoán**.
1. Chọn các hình elip dọc bên cạnh dự đoán bạn muốn làm mới.
1. Chọn **Làm mới**.

## <a name="delete-a-prediction"></a>Xóa dự đoán

1. Chuyển đến tab **Dự đoán của tôi** trên **Thông tin** > **Dự đoán**.
1. Chọn các hình elip dọc bên cạnh dự đoán bạn muốn xóa.
1. Chọn **Xóa**.

> [!NOTE]
> Khi xóa dự đoán, thực thể đầu ra của dự đoán đó cũng sẽ bị xóa.
