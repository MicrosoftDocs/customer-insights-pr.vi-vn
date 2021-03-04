---
title: Dự đoán đề xuất sản phẩm
description: Dự đoán các sản phẩm mà khách hàng có khả năng mua hoặc tương tác.
ms.date: 02/15/2021
ms.reviewer: zacook
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 5a2eb2b4697e51a0abb933b654a9b0b150dfa6a3
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270547"
---
# <a name="product-recommendation-prediction-preview"></a>Dự đoán đề xuất sản phẩm (xem trước)

Mô hình đề xuất sản phẩm tạo ra các bộ đề xuất sản phẩm dự đoán. Các đề xuất dựa trên hành vi mua hàng trước đó và những khách hàng có kiểu mua hàng tương tự. Bạn có thể tạo dự đoán đề xuất sản phẩm mới trên trang **Thông tin** > **Dự đoán**. Chọn **Dự đoán của tôi** để xem các dự đoán khác mà bạn đã tạo.

Các đề xuất về sản phẩm có thể tuân theo luật và quy định của địa phương cũng như mong đợi của khách hàng, mà mô hình này không được xây dựng để tính đến cụ thể.  Là người dùng khả năng dự đoán này, **bạn phải xem xét các đề xuất trước khi phân phối chúng cho khách hàng của bạn** để đảm bảo rằng bạn đang tuân thủ mọi luật hoặc quy định hiện hành, cũng như mong đợi của khách hàng đối với những gì bạn có thể đề xuất. 

Ngoài ra, đầu ra của mô hình này sẽ cung cấp cho bạn các đề xuất dựa trên ID sản phẩm. Cơ chế phân phối của bạn sẽ cần lấy các ID sản phẩm được dự đoán và ánh xạ chúng đến nội dung phù hợp với khách hàng của bạn để tính đến nội dung bản địa hóa, nội dung hình ảnh và nội dung hoặc hành vi cụ thể khác của doanh nghiệp.

## <a name="sample-guide"></a>Hướng dẫn mẫu

Nếu bạn muốn thử tính năng này nhưng không có dữ liệu để hoàn thành các yêu cầu bên dưới, bạn có thể [tạo một triển khai mẫu](sample-guide-predict-product-recommendation.md).

## <a name="prerequisites"></a>Điều kiện tiên quyết

- Ít nhất [Quyền của người đóng góp](permissions.md) trong Customer Insights.
- Kiến thức kinh doanh để hiểu các loại sản phẩm khác nhau cho doanh nghiệp của bạn và cách khách hàng của bạn tương tác với chúng. Chúng tôi hỗ trợ đề xuất các sản phẩm đã được khách hàng của bạn mua trước đó hoặc đề xuất các sản phẩm mới.
- Dữ liệu về các giao dịch, mua hàng và lịch sử của họ:
    - Mã định danh giao dịch để phân biệt mua hàng hoặc giao dịch.
    - Mã định danh khách hàng để ánh xạ các giao dịch với khách hàng của bạn.
    - Ngày sự kiện giao dịch xác định ngày giao dịch diễn ra.
    - (Tùy chọn) Thông tin ID sản phẩm cho giao dịch.
    - (Tùy chọn) Liệu một giao dịch có phải là giao dịch trả lại hàng hay không.
    - Lược đồ dữ liệu ngữ nghĩa yêu cầu thông tin sau:
        - **ID giao dịch:** Mã định danh duy nhất của một giao dịch mua hàng.
        - **Ngày giao dịch:** Ngày mua hoặc giao dịch.
        - **Giá trị của giao dịch:** Giá trị số của giao dịch hoặc mặt hàng.
        - **ID sản phẩm duy nhất:** ID của sản phẩm hoặc dịch vụ đã mua nếu dữ liệu của bạn ở cấp mục hàng.
        - (Không bắt buộc) **Giao dịch mua hay trả lại hàng:** Trường true/false xác định liệu giao dịch có phải là trả lại hay không. Nếu **Giá trị của giao dịch** là âm, chúng tôi cũng sẽ sử dụng thông tin này để suy ra lợi nhuận.


## <a name="create-a-product-recommendation-prediction"></a>Tạo dự đoán đề xuất sản phẩm

1. Trong Customer Insights, chuyển đến phần **Thông tin** > **Dự đoán**.

1. Chọn ngăn xếp **Mô hình đề xuất sản phẩm (bản xem trước)** và chọn **Sử dụng mô hình này**.
   > [!div class="mx-imgBorder"]
   > ![Ô mô hình Đề xuất Sản phẩm có nút Sử dụng mô hình này](media/product-recommendation-usethismodel.PNG "Ô mô hình Đề xuất Sản phẩm có nút Sử dụng mô hình này")

1. Xem lại thông tin về các yêu cầu của mô hình. Nếu bạn có dữ liệu cần thiết, hãy chọn **Bắt đầu**.

### <a name="name-model"></a>Đặt tên mô hình

1. Cung cấp tên cho mô hình để phân biệt với các mô hình khác.

1. Nhập tên cho thực thể đầu ra chỉ bằng chữ cái và số, không có bất kỳ khoảng trắng nào. Đó là tên mà thực thể mô hình sẽ sử dụng. Sau đó, chọn **Tiếp**.

### <a name="define-product-recommendation-configuration"></a>Xác định cấu hình đề xuất sản phẩm

1. Đặt **Số lượng sản phẩm** bạn muốn giới thiệu cho khách hàng. Giá trị này phụ thuộc vào cách phương thức phân phối của bạn điền vào dữ liệu. Nếu bạn có thể đề xuất ba sản phẩm, hãy đặt giá trị này cho phù hợp.
   
   >[!TIP]
   > Bạn có thể chọn **Lưu và đóng** bất cứ lúc nào để lưu dự đoán dưới dạng bản nháp. Bạn sẽ tìm thấy dự đoán dự thảo trong tab **Dự đoán của tôi**.

1. Chọn xem bạn muốn **Đề xuất sản phẩm khách hàng đã mua gần đây hay không**.

1. Nếu bạn đã chọn *không* giới thiệu các sản phẩm đã mua gần đây, hãy đặt **Khoảng thời gian nhìn lại**. Cài đặt này chỉ định khung thời gian mà mô hình xem xét trước khi giới thiệu lại sản phẩm cho người dùng. Ví dụ: cho biết một khách hàng mua máy tính xách tay 2 năm một lần. Khoảng thời gian này sẽ xem xét lịch sử mua hàng trong 2 năm qua và nếu họ tìm một mặt hàng, mặt hàng đó sẽ được lọc khỏi các đề xuất.

1. Chọn **Tiếp theo**

### <a name="add-required-data"></a>Thêm dữ liệu bắt buộc

1. Chọn **Thêm dữ liệu** cho **Lịch sử giao dịch khách hàng** và chọn thực thể cung cấp thông tin lịch sử giao dịch/mua hàng như được mô tả trong [điều kiện tiên quyết](#prerequisites).

1. Ánh xạ các trường ngữ nghĩa với các thuộc tính trong thực thể lịch sử mua hàng của bạn và chọn **Tiếp theo**. Để biết mô tả về các trường, hãy xem [điều kiện tiên quyết](#prerequisites).
   > [!div class="mx-imgBorder"]
   > ![Xác định mối quan hệ của thực thể](media/product-recommendation-purchasehistorymapping.PNG "Trang lịch sử mua hàng hiển thị các thuộc tính ngữ nghĩa được ánh xạ tới các trường trong thực thể lịch sử mua hàng đã chọn")

1. Nếu các trường không được điền, hãy định cấu hình mối quan hệ từ thực thể lịch sử mua hàng của bạn với thực thể *Khách hàng*.
    1. Chọn **Thực thể lịch sử mua hàng**.
    1. Chọn **Trường** xác định khách hàng trong thực thể lịch sử mua hàng. Trường đó cần liên quan đến ID khách hàng chính của thực thể *Khách hàng*.
    1. Chọn **Thực thể khách hàng** khớp với thực thể khách hàng chính của bạn.
    1. Nhập tên mô tả mối quan hệ.
       > [!div class="mx-imgBorder"]
       > ![Trang lịch sử mua hàng hiển thị việc tạo mối quan hệ với khách hàng](media/model-purchase-join.png "Trang lịch sử mua hàng hiển thị việc tạo mối quan hệ với khách hàng")

1. Chọn **Lưu**.

1. Chọn **Tiếp theo**.

### <a name="set-schedule-and-review-configuration"></a>Đặt lịch và xem xét cấu hình

1. Đặt tần số để đào tạo lại mô hình của bạn. Thiết đặt này rất quan trọng để cập nhật tính chính xác của các dự đoán khi dữ liệu mới được nhập vào Customer Insights. Hầu hết các doanh nghiệp đều có thể đào tạo lại một lần mỗi tháng và có dự đoán chính xác cao.

1. Chọn **Tiếp theo**.

1. Xem lại cấu hình. Bạn có thể quay lại bất kỳ phần nào của cấu hình dự đoán bằng cách chọn **Chỉnh sửa** bên dưới giá trị hiển thị. Hoặc bạn có thể chọn một bước cấu hình từ chỉ báo tiến trình.

1. Nếu tất cả giá trị được đặt cấu hình chính xác, hãy chọn **Lưu và chạy** để bắt đầu quá trình dự đoán. Trên tab **Dự đoán của tôi**, bạn có thể xem trạng thái dự đoán. Quá trình này có thể mất vài giờ mới hoàn thành, tùy thuộc vào lượng dữ liệu dùng trong dự đoán.

## <a name="review-a-prediction-status-and-results"></a>Xem lại trạng thái dự đoán và kết quả

1. Chuyển đến tab **Dự đoán của tôi** trên **Thông tin** > **Dự đoán**.
   > [!div class="mx-imgBorder"]
   > ![Xem trang Dự đoán của tôi](media/product-recommendation-mypredictions.PNG "Xem trang Dự đoán của tôi")

1. Chọn dự đoán bạn muốn xem lại.
   - **Tên dự đoán:** Tên của dự đoán được cung cấp khi tạo.
   - **Loại dự đoán:** Loại mô hình dùng cho dự đoán
   - **Thực thể đầu ra:** Tên của thực thể để lưu trữ đầu ra của dự đoán. Bạn có thể tìm thấy thực thể có tên này trên **Dữ liệu** > **Thực thể**.
   - **Trường dự đoán:** Trường này chỉ được điền cho một số loại dự đoán và không được sử dụng trong dự đoán rời đi.
   - **Trạng thái:** Trạng thái hiện tại của lần chạy dự đoán.
        - **Xếp hàng đợi:"** Dự đoán hiện đang chờ quá trình khác chạy.
        - **Làm mới:** Dự đoán hiện đang chạy giai đoạn "điểm số" của quá trình để tạo ra các kết quả sẽ chuyển đến thực thể đầu ra.
        - **Không thành công:** dự đoán không thành công. Chọn **Nhật ký** để biết thêm chi tiết.
        - **Thành công:** dự đoán đã thành công. Chọn **Xem** bên dưới các hình elip dọc để xem xét dự đoán
   - **Đã chỉnh sửa:** Ngày thay đổi cấu hình của dự đoán.
   - **Làm mới lần gần đây nhất** Ngày dự đoán làm mới kết quả trong thực thể đầu ra.

1. Chọn các hình elip dọc bên cạnh dự đoán bạn muốn xem lại kết quả rồi chọn **Xem**.
   > [!div class="mx-imgBorder"]
   > ![Xem các tùy chọn trong menu hình elip dọc để dự đoán bao gồm chỉnh sửa, làm mới, xem, ghi nhật ký và xóa](media/product-recommendation-verticalellipses.PNG "Xem các tùy chọn trong menu hình elip dọc để dự đoán bao gồm chỉnh sửa, làm mới, xem, ghi nhật ký và xóa")

1. Có 3 phần dữ liệu chính trong trang kết quả:
    1. **Hiệu suất mô hình đào tạo:** A, B hoặc C là các điểm số có thể có. Điểm số này cho biết hiệu suất của dự đoán và có thể giúp bạn ra quyết định sử dụng kết quả được lưu trữ trong thực thể đầu ra.
        - Điểm số được xác định dựa trên các quy tắc sau:
            - **A** Mô hình sẽ được xem xét có chất lượng **A** nếu chỉ số "Thành công @ K" cao hơn đường cơ sở ít nhất 10%. 
            - **B** Mô hình sẽ được xem xét có chất lượng **B** nếu chỉ số "Thành công @ K" cao hơn 0 đến 10% so với đường cơ sở.
            - **C** Mô hình sẽ được xem xét có chất lượng **C** nếu chỉ số "Thành công @ K" thấp hơn so với đường cơ sở.
               
               > [!div class="mx-imgBorder"]
               > ![Xem kết quả hiệu suất của mô hình](media/product-recommendation-modelperformance.PNG "Xem kết quả hiệu suất của mô hình")
            - **Đường cơ sở**: Mô hình lấy các sản phẩm được đề xuất nhiều nhất theo số lượng mua của tất cả các khách hàng và sử dụng các quy tắc đã học do mô hình xác định để tạo một tập hợp các đề xuất cho khách hàng. Sau đó, các dự đoán được so sánh với các sản phẩm hàng đầu, được tính bằng số lượng khách hàng đã mua sản phẩm. Nếu khách hàng có ít nhất một sản phẩm trong các sản phẩm được đề xuất cũng có trong các sản phẩm được mua nhiều nhất, thì chúng được coi là một phần của đường cơ sở. Nếu có 10 khách hàng trong số này đã mua sản phẩm được đề xuất trong tổng số 100 khách hàng, thì mức cơ bản sẽ là 10%.
            - **Thành công @ K**: Sử dụng tập hợp xác thực khoảng thời gian của các giao dịch, các đề xuất được tạo cho tất cả khách hàng và được so sánh với tập hợp xác thực của các giao dịch. Ví dụ: trong khoảng thời gian 12 tháng, tháng 12 có thể được dành làm tập dữ liệu xác thực. Nếu mô hình dự đoán ít nhất một thứ bạn sẽ mua trong tháng 12 dựa trên những gì đã học được từ 11 tháng trước, thì khách hàng sẽ tăng chỉ số "Thành công @ K".
    
    1. **Các sản phẩm được đề xuất nhiều nhất (có kiểm đếm):** 5 sản phẩm hàng đầu được dự đoán cho khách hàng của bạn.
       > [!div class="mx-imgBorder"]
       > ![Biểu đồ hiển thị 5 sản phẩm được đề xuất hàng đầu](media/product-recommendation-topproducts.PNG "Biểu đồ hiển thị 5 sản phẩm được đề xuất hàng đầu")
    
    1. **Đề xuất sản phẩm có độ tin cậy cao:** Một mẫu đề xuất được cung cấp cho khách hàng của bạn mà mô hình đó tin rằng khách hàng có thể mua.
       > [!div class="mx-imgBorder"]
       > ![Danh sách hiển thị các đề xuất có độ tin cậy cao cho một nhóm khách hàng cá nhân được chọn](media/product-recommendation-highconfidence.PNG "Danh sách hiển thị các đề xuất có độ tin cậy cao cho một nhóm khách hàng cá nhân được chọn")

## <a name="fix-a-failed-prediction"></a>Khắc phục một dự đoán không thành công

1. Chuyển đến tab **Dự đoán của tôi** trên **Thông tin** > **Dự đoán**.

1. Chọn một dự đoán mà bạn muốn xem nhật ký lỗi rồi chọn **Nhật ký**.

1. Xem lại tất cả lỗi. Có một số loại lỗi có thể xảy ra và chúng mô tả nguyên nhân gây ra lỗi. Ví dụ: một lỗi không đủ dữ liệu để dự đoán chính xác thường được giải quyết bằng cách tải thêm dữ liệu vào Customer Insights.

## <a name="refresh-a-prediction"></a>Làm mới một dự đoán

Các dự đoán tự động làm mới trên cùng một [lịch làm mới dữ liệu của bạn](system.md#schedule-tab) như được định cấu hình trong chế độ cài đặt.

1. Chuyển đến tab **Dự đoán của tôi** trên **Thông tin** > **Dự đoán**.

1. Chọn các hình elip dọc bên cạnh dự đoán bạn muốn làm mới.

1. Chọn **Làm mới**.

## <a name="delete-a-prediction"></a>Xóa dự đoán

Việc xóa dự đoán cũng xóa thực thể đầu ra của nó.

1. Chuyển đến tab **Dự đoán của tôi** trên **Thông tin** > **Dự đoán**.

1. Chọn các hình elip dọc bên cạnh dự đoán bạn muốn xóa.

1. Chọn **Xóa**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]