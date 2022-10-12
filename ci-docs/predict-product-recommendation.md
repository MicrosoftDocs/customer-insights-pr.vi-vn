---
title: Dự đoán đề xuất sản phẩm
description: Dự đoán các sản phẩm mà khách hàng có khả năng mua hoặc tương tác.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: 0057d6796bb60db44d08b58d9e0daaf6e7c90fde
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610308"
---
# <a name="predict-product-recommendations"></a>Dự đoán đề xuất sản phẩm

Mô hình đề xuất sản phẩm tạo ra các bộ đề xuất sản phẩm dự đoán. Các đề xuất dựa trên hành vi mua hàng trước đó và những khách hàng có kiểu mua hàng tương tự. Mô hình này dành cho người tiêu dùng cá nhân (B-to-C).

Bạn phải có kiến thức kinh doanh về các loại sản phẩm khác nhau cho doanh nghiệp của mình và cách khách hàng của bạn tương tác với chúng. Chúng tôi hỗ trợ đề xuất các sản phẩm đã được khách hàng của bạn mua trước đó hoặc đề xuất các sản phẩm mới.

Các đề xuất về sản phẩm có thể tuân theo luật pháp và quy định của địa phương cũng như đáp ứng kỳ vọng của khách hàng. Đây là những yếu tố mà mô hình này không tính đến cụ thể. Vì vậy, **bạn phải xem xét các đề xuất trước khi phân phối chúng cho khách hàng của bạn** để đảm bảo rằng bạn đang tuân thủ mọi luật hoặc quy định hiện hành và mong đợi của khách hàng đối với những gì bạn có thể đề xuất.

Đầu ra của mô hình này cung cấp các đề xuất dựa trên ID sản phẩm. Cơ chế phân phối của bạn phải ánh xạ các ID sản phẩm được dự đoán với nội dung phù hợp để khách hàng của bạn tính đến nội dung bản địa hóa, nội dung hình ảnh và nội dung hoặc hành vi dành riêng cho doanh nghiệp khác.

> [!TIP]
> Hãy thử đề xuất sản phẩm dự đoán bằng cách sử dụng dữ liệu mẫu: [Hướng dẫn mẫu đề xuất sản phẩm dự đoán](sample-guide-predict-product-recommendation.md).

## <a name="prerequisites"></a>Điều kiện tiên quyết

- Ít nhất [Quyền của cộng tác viên](permissions.md)
- Ít nhất 100 khách hàng, tốt nhất là hơn 10.000 khách hàng.
- Mã định danh khách hàng, một mã định danh duy nhất để khớp các giao dịch với một khách hàng cá nhân
- Ít nhất một năm dữ liệu giao dịch, tốt nhất là hai đến ba năm để bao gồm một số tính thời vụ. Tốt nhất, ít nhất ba giao dịch trở lên cho mỗi ID khách hàng. Lịch sử giao dịch phải bao gồm:
  - **ID giao dịch** : Định danh duy nhất của một giao dịch mua hoặc giao dịch.
  - **Ngày Giao dịch** : Ngày mua hoặc giao dịch.
  - **Giá trị của giao dịch** : Giá trị bằng số của giao dịch mua hoặc giao dịch.
  - **ID sản phẩm duy nhất** : ID của sản phẩm hoặc dịch vụ đã mua nếu dữ liệu của bạn ở cấp mục hàng.
  - **Mua hoặc trả lại** : Một giá trị boolean true / false trong đó *thật* xác định rằng một giao dịch là một lợi nhuận. Nếu dữ liệu Mua hàng hoặc Trả lại không được cung cấp trong mô hình và **Giá trị của giao dịch** là số âm, chúng tôi suy ra lợi nhuận.
- Thực thể dữ liệu danh mục sản phẩm để sử dụng làm bộ lọc sản phẩm.

> [!NOTE]
> - Mô hình yêu cầu lịch sử giao dịch của khách hàng của bạn, trong đó giao dịch là bất kỳ dữ liệu nào mô tả tương tác giữa người dùng và sản phẩm. Ví dụ: mua một sản phẩm, tham gia một lớp học hoặc tham dự một sự kiện.
> - Chỉ có thể định cấu hình một thực thể lịch sử giao dịch. Nếu có nhiều thực thể mua hàng, hãy kết hợp chúng trong Power Query trước khi nhập dữ liệu.
> - Nếu đơn hàng và chi tiết đơn hàng là các thực thể khác nhau, hãy liên kết chúng trước khi sử dụng trong mô hình. Mô hình không hoạt động chỉ với ID đơn hàng hoặc ID biên nhận trong một thực thể.

## <a name="create-a-product-recommendation-prediction"></a>Tạo dự đoán đề xuất sản phẩm

Lựa chọn **Lưu bản nháp** bất kỳ lúc nào để lưu dự đoán dưới dạng bản nháp. Bản nháp dự đoán hiển thị trong **Dự đoán của tôi** chuyển hướng.

1. Đi đến **Sự thông minh** > **Phỏng đoán**.

1. Trên **Tạo ra** tab, chọn **Sử dụng mô hình** trên **Đề xuất sản phẩm (xem trước)** ngói.

1. Chọn **Bắt đầu**.

1. **Đặt tên cho mô hình này** và **Tên thực thể đầu ra** để phân biệt chúng với các mô hình hoặc thực thể khác.

1. Chọn **Tiếp theo**.

### <a name="define-product-recommendation-preferences"></a>Xác định tùy chọn đề xuất sản phẩm

1. Đặt **Số lượng sản phẩm** để giới thiệu cho khách hàng. Giá trị này phụ thuộc vào cách phương thức phân phối của bạn điền vào dữ liệu.

1. Chọn xem bạn có muốn đưa các sản phẩm mà khách hàng đã mua trước đó vào **Các giao dịch mua lặp lại dự kiến** đồng ruộng.

1. Đặt **Cửa sổ nhìn lại** với khung thời gian mà người mẫu cân nhắc trước khi giới thiệu lại sản phẩm cho người dùng. Ví dụ: cho biết một khách hàng mua máy tính xách tay hai năm một lần. Mô hình xem xét lịch sử mua hàng trong hai năm qua và nếu tìm thấy một mặt hàng, mặt hàng đó sẽ được lọc khỏi các đề xuất.

1. Chọn **Tiếp theo**

### <a name="add-purchase-history"></a>Thêm lịch sử mua hàng

1. Lựa chọn **Thêm dữ liệu** vì **Lịch sử giao dịch của khách hàng**.

1. Chọn loại hoạt động ngữ nghĩa **SalesOrderLine** chứa thông tin lịch sử giao dịch hoặc mua hàng được yêu cầu. Nếu hoạt động chưa được thiết lập, hãy chọn **nơi đây** và tạo ra nó.

1. Dưới **Các hoạt động**, nếu các thuộc tính hoạt động được ánh xạ theo ngữ nghĩa khi hoạt động được tạo, hãy chọn các thuộc tính hoặc thực thể cụ thể mà bạn muốn tính toán tập trung vào. Nếu ánh xạ ngữ nghĩa không xảy ra, hãy chọn **Chỉnh sửa** và lập bản đồ dữ liệu của bạn.

   :::image type="content" source="media/product-recommendation-select-semantic-activity.PNG" alt-text="Ngăn bên hiển thị việc chọn các hoạt động cụ thể theo loại ngữ nghĩa.":::

1. Lựa chọn **Tiếp theo** và xem xét các thuộc tính cần thiết cho mô hình này.

1. Chọn **Lưu.**

1. Chọn **Tiếp theo**.

### <a name="add-product-information-and-filters"></a>Thêm thông tin sản phẩm và bộ lọc

Đôi khi, chỉ một số sản phẩm là có lợi hoặc phù hợp với loại dự đoán mà bạn đưa ra. Sử dụng bộ lọc sản phẩm để xác định một tập hợp con các sản phẩm có đặc điểm cụ thể để giới thiệu cho khách hàng của bạn. Mô hình sẽ sử dụng tất cả các sản phẩm có sẵn để tìm hiểu các thói quen nhưng chỉ sử dụng các sản phẩm khớp với bộ lọc sản phẩm trong đầu ra của nó.

1. Thêm thực thể danh mục sản phẩm của bạn có chứa thông tin cho từng sản phẩm. Ánh xạ thông tin cần thiết và chọn **Tiết kiệm**.

1. Chọn **Tiếp theo**.

1. Lựa chọn **Bộ lọc sản phẩm**:

   - **Không có bộ lọc**: Sử dụng tất cả các sản phẩm trong phần dự đoán đề xuất về sản phẩm.

   - **Xác định bộ lọc sản phẩm cụ thể**: Sử dụng các sản phẩm cụ thể trong phần dự đoán đề xuất về sản phẩm. Bên trong **Thuộc tính danh mục sản phẩm**, chọn các thuộc tính từ thực thể danh mục sản phẩm mà bạn muốn đưa vào bộ lọc.

     :::image type="content" source="media/product-filters-sidepane.png" alt-text="Ngăn bên hiển thị thuộc tính trong thực thể danh mục sản phẩm để chọn cho bộ lọc sản phẩm.":::

1. Chọn nếu bạn muốn sử dụng bộ lọc sản phẩm **và** hoặc **hoặc** để kết hợp một cách hợp lý lựa chọn các thuộc tính của bạn từ danh mục sản phẩm.

   :::image type="content" source="media/product-filters-sample.png" alt-text="Cấu hình mẫu của bộ lọc sản phẩm kết hợp với các từ nối VÀ hợp lý.":::

1. Chọn **Tiếp theo**.

### <a name="set-update-schedule"></a>Đặt lịch trình cập nhật

1. Chọn tần suất để đào tạo lại mô hình của bạn. Cài đặt này rất quan trọng để cập nhật độ chính xác của các dự đoán khi dữ liệu mới được nhập vào Thông tin chi tiết về khách hàng. Hầu hết các doanh nghiệp đều có thể đào tạo lại một lần mỗi tháng và có dự đoán chính xác cao.

1. Chọn **Tiếp theo**.

### <a name="review-and-run-the-model-configuration"></a>Xem lại và chạy cấu hình mô hình

Các **Xem lại và chạy** bước hiển thị tóm tắt cấu hình và cung cấp cơ hội thực hiện các thay đổi trước khi bạn tạo dự đoán.

1. Lựa chọn **Chỉnh sửa** về bất kỳ bước nào để xem xét và thực hiện bất kỳ thay đổi nào.

1. Nếu bạn hài lòng với lựa chọn của mình, hãy chọn **Lưu và chạy** để bắt đầu chạy mô hình. Chọn **Xong**. Các **Dự đoán của tôi** tab hiển thị trong khi dự đoán đang được tạo. Quá trình này có thể mất vài giờ mới hoàn thành, tùy thuộc vào lượng dữ liệu dùng trong dự đoán.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Xem kết quả dự đoán

1. Đi đến **Sự thông minh** > **Phỏng đoán**.

1. Bên trong **Dự đoán của tôi**, chọn dự đoán bạn muốn xem.

Có năm phần dữ liệu chính trong trang kết quả.

- **Hiệu suất mô hình:** Điểm A, B hoặc C cho biết hiệu suất của dự đoán và có thể giúp bạn đưa ra quyết định sử dụng kết quả được lưu trữ trong thực thể đầu ra.
  
  :::image type="content" source="media/product-recommendation-modelperformance.PNG" alt-text="Hình ảnh về kết quả hoạt động của mô hình với điểm A.":::

  Điểm được xác định dựa trên các quy tắc sau:
  - **Một** khi chỉ số "Thành công @ K" nhiều hơn ít nhất 10% so với đường cơ sở.
  - **B** khi chỉ số "Thành công @ K" cao hơn từ 0% đến 10% so với đường cơ sở.
  - **C** khi chỉ số "Thành công @ K" nhỏ hơn đường cơ sở.
  - **Đường cơ sở** : Các sản phẩm được đề xuất nhiều nhất theo số lượng mua của tất cả các khách hàng + các quy tắc đã học được xác định bởi mô hình = một tập hợp các đề xuất cho khách hàng. Sau đó, các dự đoán được so sánh với các sản phẩm hàng đầu, được tính bằng số lượng khách hàng đã mua sản phẩm. Nếu khách hàng có ít nhất một sản phẩm trong các sản phẩm được đề xuất cũng có trong các sản phẩm được mua nhiều nhất, thì chúng được coi là một phần của đường cơ sở. Ví dụ: nếu 10 khách hàng trong số này đã mua sản phẩm được đề xuất trong tổng số 100 khách hàng, thì mức cơ bản là 10%.
  - **Thành công @ K** : Các đề xuất được tạo cho tất cả khách hàng và được so sánh với tập hợp xác thực về khoảng thời gian của các giao dịch. Ví dụ: trong khoảng thời gian 12 tháng, tháng 12 được đặt làm tập hợp dữ liệu xác thực. Nếu mô hình dự đoán ít nhất một thứ bạn sẽ mua trong tháng 12 dựa trên những gì đã học được từ 11 tháng trước, thì khách hàng sẽ tăng chỉ số "Thành công @ K".

- **Các sản phẩm được đề xuất nhiều nhất (có kiểm đếm):** Năm sản phẩm hàng đầu được dự đoán cho khách hàng của bạn.
  
  :::image type="content" source="media/product-recommendation-topproducts.PNG" alt-text="Biểu đồ hiển thị 5 sản phẩm được đề xuất hàng đầu.":::

- **Các yếu tố đề xuất chính:** Mô hình sử dụng lịch sử giao dịch của khách hàng để đưa ra các đề xuất về sản phẩm. Mô hình học các thói quen dựa trên những giao dịch mua hàng trước đây và tìm ra những điểm tương đồng giữa khách hàng và sản phẩm. Những điểm tương đồng này sau đó được sử dụng để đưa ra các đề xuất về sản phẩm.
  Các yếu tố sau đây có thể ảnh hưởng đến đề xuất sản phẩm do mô hình tạo ra.
  - **Các giao dịch trong quá khứ** : Một sản phẩm được đề xuất dựa trên các mẫu mua trước đây. Ví dụ: mô hình có thể đề xuất *Chuột Surface Arc* nếu ai đó gần đây đã mua *Surface Book 3* và *Bút Surface*. Mô hình học được rằng trước đây, nhiều khách hàng đã mua *Chuột Surface Arc* sau khi mua *Surface Book 3* và *Bút Surface*.
  - **Sự tương đồng của khách hàng**: Trước đây, những khách hàng khác có thói quen mua hàng tương tự đã mua một sản phẩm được đề xuất. Ví dụ: John được đề xuất *Tai nghe Surface 2* bởi vì Jennifer và Brad gần đây đã mua *Tai nghe Surface2*. Mô hình tin rằng John giống Jennifer và Brad vì trước đây họ đã từng có những thói quen mua hàng tương tự.
  - **Sự tương đồng của sản phẩm**: Một sản phẩm được đề xuất tương tự như các sản phẩm khác mà khách hàng đã mua trước đó. Mô hình coi hai sản phẩm là tương tự nhau nếu chúng được mua cùng nhau hoặc được mua bởi những khách hàng tương đồng. Ví dụ: ai đó nhận được đề xuất về *Ổ lưu trữ USB* bởi vì trước đó họ đã mua *Bộ chuyển đổi USB-C sang USB* và mô hình tin rằng *Ổ lưu trữ USB* tương tự như *Bộ chuyển đổi USB-C sang USB* dựa trên các thói quen mua hàng trước đây.

  Mọi đề xuất về sản phẩm đều chịu ảnh hưởng của một hoặc nhiều yếu tố này. Tỷ lệ phần trăm đề xuất (trong đó mỗi yếu tố ảnh hưởng đóng một vai trò) được minh họa trong biểu đồ. Trong ví dụ sau, 100% đề xuất bị ảnh hưởng bởi các giao dịch trước đây, 60% bị ảnh hưởng bởi sự tương đồng của khách hàng và 22% bị ảnh hưởng bởi sự tương đồng của sản phẩm. Di chuột qua các thanh trong biểu đồ để xem chính xác tỷ lệ phần trăm mà các yếu tố ảnh hưởng đã đóng góp.
  
  :::image type="content" source="media/product-recommendation-keyrecommendationfactors.png" alt-text="Các yếu tố khuyến nghị chính mà mô hình học được để đưa ra các đề xuất sản phẩm.":::

- **Thống kê dữ liệu** : Tổng quan về số lượng giao dịch, khách hàng và sản phẩm mà mô hình được xem xét. Thống kê này dựa trên dữ liệu đầu vào được dùng để tìm hiểu các thói quen và đưa ra đề xuất về sản phẩm.

  :::image type="content" source="media/product-recommendation-datastatistics.png" alt-text="Thống kê dữ liệu xung quanh dữ liệu đầu vào được mô hình sử dụng để tìm hiểu các mẫu.":::
  
  Mô hình sử dụng tất cả dữ liệu có sẵn để tìm hiểu các mẫu. Do đó, nếu bạn sử dụng tính năng lọc sản phẩm trong cấu hình mô hình, phần này sẽ hiển thị tổng số sản phẩm mà mô hình đã phân tích để tìm hiểu các mẫu, có thể khác với số lượng sản phẩm phù hợp với tiêu chí lọc đã xác định. Lọc áp dụng trên đầu ra do mô hình tạo ra.

- **Đề xuất sản phẩm mẫu:** Một mẫu đề xuất mà mô hình tin rằng có khả năng được khách hàng mua. Nếu danh mục sản phẩm được thêm vào, ID sản phẩm sẽ được thay thế bằng tên sản phẩm.

  :::image type="content" source="media/product-recommendation-highconfidence.PNG" alt-text="Danh sách hiển thị các đề xuất có độ tin cậy cao cho một nhóm khách hàng cá nhân được chọn.":::

> [!NOTE]
> Trong thực thể đầu ra cho mô hình này, *Ghi bàn* cho thấy thước đo định lượng của khuyến nghị. Mô hình đề xuất các sản phẩm có điểm cao hơn so với các sản phẩm có điểm thấp hơn. Để xem điểm số, hãy truy cập **Dữ liệu** > **Thực thể** và xem tab dữ liệu cho thực thể đầu ra mà bạn đã xác định cho mô hình này.

[!INCLUDE [footer-include](includes/footer-banner.md)]
