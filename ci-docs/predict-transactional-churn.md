---
title: Giao dịch churn dự đoán (có video)
description: Dự đoán xem khách hàng có nguy cơ không mua sản phẩm hoặc dịch vụ của bạn nữa không.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: fd8df0f0a168ddfab9e8ad3af9e1f1fc0bc1b7a2
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610538"
---
# <a name="predict-transaction-churn"></a>Dự đoán khách hàng rời khỏi giao dịch

Dự đoán Khả năng rời bỏ giao dịch giúp dự đoán liệu khách hàng sẽ không còn mua sản phẩm hoặc dịch vụ của bạn nữa trong một khoảng thời gian nhất định hay không.

Bạn phải có kiến thức kinh doanh để hiểu churn có ý nghĩa như thế nào đối với doanh nghiệp của bạn. Chúng tôi hỗ trợ các định nghĩa rời bỏ dựa trên thời gian, có nghĩa là một khách hàng được coi là đã rời bỏ sau một khoảng thời gian không mua hàng.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6Eg]

Đối với các môi trường dựa trên tài khoản doanh nghiệp, chúng ta có thể dự đoán tỷ lệ rời khỏi giao dịch cho một tài khoản, ngoài ra còn có thông tin khác như danh mục sản phẩm. Ví dụ: thêm thứ nguyên có thể giúp xác định khả năng tài khoản "Contoso" ngừng mua danh mục sản phẩm "văn phòng phẩm". Ngoài ra, đối với tài khoản doanh nghiệp, chúng ta cũng có thể sử dụng AI để tạo danh sách những lý do tại sao một tài khoản có thể rời khỏi đối với một danh mục hoặc cấp thông tin thứ hai.

> [!TIP]
> Hãy thử giao dịch churn dự đoán bằng cách sử dụng dữ liệu mẫu: [Hướng dẫn mẫu churn dự đoán giao dịch](sample-guide-predict-transactional-churn.md).

## <a name="prerequisites"></a>Điều kiện tiên quyết

- Tối thiểu [Quyền của cộng tác viên](permissions.md).
- Ít nhất 10 hồ sơ khách hàng, tốt nhất là hơn 1.000 khách hàng duy nhất.
- Mã định danh khách hàng, một mã định danh duy nhất để khớp các giao dịch với khách hàng của bạn.
- Dữ liệu giao dịch trong ít nhất gấp đôi khoảng thời gian đã chọn, chẳng hạn như lịch sử giao dịch từ hai đến ba năm. Tốt nhất là ít nhất hai giao dịch cho mỗi khách hàng. Lịch sử giao dịch phải bao gồm:
  - **ID giao dịch** : Định danh duy nhất của một giao dịch mua hoặc giao dịch.
  - **Ngày Giao dịch** : Ngày mua hoặc giao dịch.
  - **Giá trị của giao dịch** : Số lượng tiền tệ hoặc giá trị số của giao dịch.
  - **ID sản phẩm duy nhất** : ID của sản phẩm hoặc dịch vụ đã mua nếu dữ liệu của bạn ở cấp mục hàng.
  - **Liệu giao dịch này có phải là trả lại hay không** : Trường true / false xác định liệu giao dịch có phải là trả lại hay không. Nếu **Giá trị của giao dịch** là số âm, chúng tôi suy ra lợi nhuận.
- Dữ liệu hoạt động của khách hàng:
  - Mã định danh khách hàng, một mã định danh duy nhất để ánh xạ các hoạt động tới khách hàng của bạn.
  - **Khóa chính:** Mã định danh duy nhất cho một hoạt động. Ví dụ: một lượt truy cập trang web hoặc hồ sơ sử dụng cho thấy khách hàng đã thử một mẫu sản phẩm của bạn.
  - **Dấu thời gian:** Ngày và giờ của sự kiện được xác định bởi khóa chính.
  - **Biến cố:** Tên của sự kiện bạn muốn sử dụng. Ví dụ: trường có tên "UserAction" trong cửa hàng tạp hóa có thể được khách hàng sử dụng phiếu giảm giá.
  - **Chi tiết:** Thông tin chi tiết về sự kiện. Ví dụ: trường có tên "CouponValue" trong cửa hàng tạp hóa có thể là giá trị tiền tệ của phiếu giảm giá.
- Dưới 20% giá trị bị thiếu trong trường dữ liệu của thực thể được cung cấp

Đối với tài khoản doanh nghiệp (B-to-B), hãy thêm dữ liệu khách hàng được căn chỉnh theo các thuộc tính tĩnh hơn để đảm bảo mô hình hoạt động tốt nhất:
- **ID khách hàng:** Định danh duy nhất cho một khách hàng.
- **Ngày tạo ra:** Ngày khách hàng được thêm vào ban đầu.
- **Tiểu bang hoặc Tỉnh:** Vị trí tiểu bang hoặc tỉnh của khách hàng.
- **Quốc gia:** Quốc gia của khách hàng.
- **Ngành công nghiệp:** Loại ngành của khách hàng. Ví dụ: trường có tên là "Ngành" trong máy rang cà phê có thể cho biết khách hàng có phải thuộc ngành bán lẻ không.
- **Phân loại:** Phân loại khách hàng cho doanh nghiệp của bạn. Ví dụ: trường có tên "ValueSegment" là máy rang cà phê có thể là bậc của khách hàng dựa trên quy mô khách hàng.

> [!NOTE]
> Đối với doanh nghiệp có tần suất mua hàng của khách hàng cao (vài tuần một lần), bạn nên chọn khoảng thời gian dự đoán ngắn hơn và xác định rủi ro khách hàng ngừng giao dịch. Đối với tần suất mua hàng thấp (vài tháng một lần hoặc một năm một lần), hãy chọn khoảng thời gian dự đoán dài hơn và xác định rủi ro khách hàng ngừng giao dịch.

## <a name="create-a-transaction-churn-prediction"></a>Dự đoán tỷ lệ rời khỏi giao dịch

1. Đi đến **Sự thông minh** > **Phỏng đoán**.

1. Trên **Tạo ra** tab, chọn **Sử dụng mô hình** trên **Mô hình churn khách hàng** ngói.

1. Lựa chọn **Giao dịch** cho kiểu churn và sau đó **Bắt đầu**.

1. **Đặt tên cho mô hình này** và **Tên thực thể đầu ra** để phân biệt chúng với các mô hình hoặc thực thể khác.

1. Chọn **Tiếp theo**.

### <a name="define-customer-churn"></a>Xác định khách hàng rời đi

Lựa chọn **Lưu bản nháp** bất kỳ lúc nào để lưu dự đoán dưới dạng bản nháp. Bản nháp dự đoán hiển thị trong **Dự đoán của tôi** chuyển hướng.

1. Đặt **dự đoán cửa sổ**. Ví dụ: dự đoán nguy cơ khách hàng rời đi trong 90 ngày tới để phù hợp với nỗ lực duy trì hoạt động tiếp thị của bạn. Việc dự đoán rủi ro rời đi trong một khoảng thời gian dài hơn hoặc ngắn hơn có thể gây khó khăn hơn cho việc giải quyết các yếu tố trong hồ sơ rủi ro rời đi của bạn, nhưng nó phụ thuộc vào yêu cầu kinh doanh cụ thể của bạn.

1. Nhập số ngày để xác định thời gian chờ trong **Định nghĩa Churn** đồng ruộng. Ví dụ: nếu khách hàng không mua hàng trong 30 ngày qua, họ có thể được coi là đã bỏ qua doanh nghiệp của bạn.

1. Chọn **Tiếp theo**.

### <a name="add-purchase-history"></a>Thêm lịch sử mua hàng

1. Lựa chọn **Thêm dữ liệu** vì **Lịch sử giao dịch của khách hàng**.

1. Chọn loại hoạt động ngữ nghĩa, **Đơn đặt hàng** hoặc **SalesOrderLine**, chứa thông tin lịch sử giao dịch. Nếu hoạt động chưa được thiết lập, hãy chọn **nơi đây** và tạo ra nó.

1. Dưới **Các hoạt động**, nếu các thuộc tính hoạt động được ánh xạ theo ngữ nghĩa khi hoạt động được tạo, hãy chọn các thuộc tính hoặc thực thể cụ thể mà bạn muốn tính toán tập trung vào. Nếu ánh xạ ngữ nghĩa không xảy ra, hãy chọn **Chỉnh sửa** và lập bản đồ dữ liệu của bạn.

   :::image type="content" source="media/transaction-churn-select-activity.PNG" alt-text="Ngăn bên hiển thị việc chọn các hoạt động cụ thể theo loại ngữ nghĩa.":::

1. Lựa chọn **Tiếp theo** và xem xét các thuộc tính cần thiết cho mô hình này.

1. Chọn **Lưu.**

1. Thêm các hoạt động khác hoặc chọn **Tiếp theo**.

# <a name="individual-consumers-b-to-c"></a>[Người tiêu dùng cá nhân (B2C)](#tab/b2c)

### <a name="add-additional-data-optional"></a>Thêm dữ liệu bổ sung (tùy chọn)

1. Lựa chọn **Thêm dữ liệu** vì **Hoạt động của khách hàng**.

1. Chọn loại hoạt động ngữ nghĩa có chứa dữ liệu bạn muốn sử dụng. Nếu hoạt động chưa được thiết lập, hãy chọn **nơi đây** và tạo ra nó.

1. Dưới **Các hoạt động**, nếu các thuộc tính hoạt động được ánh xạ theo ngữ nghĩa khi hoạt động được tạo, hãy chọn các thuộc tính hoặc thực thể cụ thể mà bạn muốn tính toán tập trung vào. Nếu ánh xạ ngữ nghĩa không xảy ra, hãy chọn **Chỉnh sửa** và lập bản đồ dữ liệu của bạn.

1. Lựa chọn **Tiếp theo** và xem xét các thuộc tính cần thiết cho mô hình này.

1. Chọn **Lưu.**

1. Chọn **Tiếp theo**

# <a name="business-accounts-b-to-b"></a>[Tài khoản doanh nghiệp (B2B)](#tab/b2b)

### <a name="select-prediction-level"></a>Chọn mức dự đoán

Hầu hết các dự đoán được tạo ở cấp độ khách hàng. Trong một số tình huống, điều đó có thể không đủ chi tiết để giải quyết nhu cầu kinh doanh của bạn. Ví dụ: sử dụng tính năng này để dự đoán thời gian nghỉ cho một nhánh của khách hàng, thay vì cho toàn bộ khách hàng.

1. Lựa chọn **Chọn thực thể cho cấp phụ**. Nếu tùy chọn không có sẵn, hãy đảm bảo rằng bạn đã hoàn thành phần trước.

1. Mở rộng các thực thể bạn muốn chọn cấp phụ hoặc sử dụng hộp bộ lọc tìm kiếm để lọc các tùy chọn đã chọn.

1. Chọn thuộc tính bạn muốn sử dụng làm cấp phụ, sau đó chọn **Thêm**.

1. Chọn **Tiếp theo**.

> [!NOTE]
> Các thực thể có sẵn trong phần này được hiển thị vì chúng có mối quan hệ với thực thể bạn đã chọn trong phần trước. Nếu bạn không thấy thực thể bạn muốn thêm, hãy đảm bảo rằng thực thể đó có mối quan hệ hợp lệ trong phần **Mối quan hệ**. Chỉ các mối quan hệ một-một và nhiều-một mới hợp lệ cho cấu hình này.

### <a name="add-additional-data-optional"></a>Thêm dữ liệu bổ sung (tùy chọn)

1. Lựa chọn **Thêm dữ liệu** vì **Hoạt động của khách hàng**.

1. Chọn loại hoạt động ngữ nghĩa có chứa dữ liệu bạn muốn sử dụng. Nếu hoạt động chưa được thiết lập, hãy chọn **nơi đây** và tạo ra nó.

1. Dưới **Các hoạt động**, nếu các thuộc tính hoạt động được ánh xạ theo ngữ nghĩa khi hoạt động được tạo, hãy chọn các thuộc tính hoặc thực thể cụ thể mà bạn muốn tính toán tập trung vào. Nếu ánh xạ ngữ nghĩa không xảy ra, hãy chọn **Chỉnh sửa** và lập bản đồ dữ liệu của bạn.

1. Lựa chọn **Tiếp theo** và xem xét các thuộc tính cần thiết cho mô hình này.

1. Chọn **Lưu.**

1. Chọn **Tiếp theo**

1. Chọn **Thêm dữ liệu** cho **Dữ liệu khách hàng** (không bắt buộc).

1. Ánh xạ các thuộc tính ngữ nghĩa cho các trường trong dữ liệu khách hàng của riêng bạn như đã xác định. Dữ liệu trong các trường được sử dụng không nên thay đổi thường xuyên để đảm bảo mô hình hoạt động tốt nhất. Ví dụ: thao tác chọn trường "Phân loại" thay đổi hàng tháng sẽ chỉ có giá trị cuối cùng được dùng trong dự đoán, mặc dù trước đó giá trị này có thể không áp dụng cho khách hàng khi tạo mẫu dự đoán.

1. Chọn **Tiếp theo**.

### <a name="provide-an-optional-list-of-benchmark-accounts"></a>Cung cấp danh sách tùy chọn các tài khoản điểm chuẩn

Thêm danh sách các tài khoản và khách hàng doanh nghiệp mà bạn muốn dùng làm điểm chuẩn. Các [chi tiết cho các tài khoản điểm chuẩn này](#view-prediction-results) bao gồm điểm số churn của họ và các tính năng có ảnh hưởng nhất đã ảnh hưởng đến việc churn dự đoán của họ.

1. Chọn **+ Thêm khách hàng**.

1. Chọn những khách hàng làm tiêu chuẩn.

1. Chọn **Tiếp theo**.

---

### <a name="set-update-schedule"></a>Đặt lịch trình cập nhật

1. Cho **Cập nhật dữ liệu** chọn tần suất để đào tạo lại mô hình của bạn. Cài đặt này rất quan trọng để cập nhật độ chính xác của các dự đoán khi dữ liệu mới được nhập vào Thông tin chi tiết về khách hàng. Hầu hết các doanh nghiệp đều có thể đào tạo lại một lần mỗi tháng và có dự đoán chính xác cao.

1. Chọn **Tiếp theo**.

### <a name="review-and-run-the-model-configuration"></a>Xem lại và chạy cấu hình mô hình

Các **Xem lại và chạy** bước hiển thị tóm tắt cấu hình và cung cấp cơ hội thực hiện các thay đổi trước khi bạn tạo dự đoán.

1. Lựa chọn **Chỉnh sửa** về bất kỳ bước nào để xem xét và thực hiện bất kỳ thay đổi nào.

1. Nếu bạn hài lòng với lựa chọn của mình, hãy chọn **Lưu và chạy** để bắt đầu chạy mô hình. Chọn **Xong**. Các **Dự đoán của tôi** tab hiển thị trong khi dự đoán đang được tạo. Quá trình này có thể mất vài giờ mới hoàn thành, tùy thuộc vào lượng dữ liệu dùng trong dự đoán.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Xem kết quả dự đoán

1. Đi đến **Sự thông minh** > **Phỏng đoán**.

1. Bên trong **Dự đoán của tôi**, chọn dự đoán bạn muốn xem.

# <a name="individual-consumers-b-to-c"></a>[Người tiêu dùng cá nhân (B2C)](#tab/b2c)

Có 3 phần dữ liệu chính trong trang kết quả:

[!INCLUDE [predict-transaction-results](includes/predict-transaction-results.md)]

# <a name="business-accounts-b-to-b"></a>[Tài khoản doanh nghiệp (B2B)](#tab/b2b)

Có 3 phần dữ liệu chính trong trang kết quả:

[!INCLUDE [predict-transaction-results](includes/predict-transaction-results.md)]

Một **Phân tích tính năng có ảnh hưởng** trang thông tin chứa bốn phần dữ liệu:

- Trong ngăn bên phải, chọn một mục từ **Khách hàng hàng đầu** hoặc **Điểm chuẩn khách hàng**. Cả hai danh sách được sắp xếp theo giá trị giảm dần của điểm số, cho dù điểm số chỉ dành cho khách hàng hay điểm số kết hợp cho khách hàng và một cấp độ thứ cấp như danh mục sản phẩm. Mục được chọn xác định nội dung trên trang này.

  - **Khách hàng hàng đầu**: Danh sách 10 khách hàng có nguy cơ rời khỏi cao nhất và nguy cơ rời khỏi thấp nhất dựa trên điểm số rời khỏi của họ.
  - **Khách hàng điểm chuẩn**: Danh sách tối đa 10 khách hàng đã được chọn trong khi đặt cấu hình mô hình.

- **Điểm rời khỏi:** Hiển thị điểm số rời khỏi cho mục đã chọn trong ngăn bên phải.

- **Phân tán rủi ro:** Cho biết sự phân bổ rủi ro hỗn loạn giữa các khách hàng và phần trăm mà khách hàng đã chọn đang ở trong đó.

- **Các tính năng hàng đầu làm tăng và giảm nguy cơ gián đoạn:** Liệt kê năm tính năng hàng đầu làm tăng và giảm nguy cơ gián đoạn cho mục đã chọn trong ngăn bên phải. Cho biết giá trị của đối tượng địa lý đối với mặt hàng đó và ảnh hưởng của nó đối với điểm số churn cho mọi đối tượng địa lý có ảnh hưởng. Giá trị trung bình của từng đối tính năng trên các phân khúc khách hàng có tỷ lệ rời khỏi thấp, trung bình và cao cũng được hiển thị. Nó giúp ngữ cảnh hóa tốt hơn các giá trị của các tính năng có ảnh hưởng hàng đầu đối với mặt hàng đã chọn và so sánh nó với các phân khúc khách hàng có khả năng rời khỏi thấp, trung bình và cao.

  - Thấp: các tài khoản hoặc sự kết hợp giữa tài khoản và cấp thứ cấp có điểm churn từ 0 đến 0,33.
  - Trung bình: các tài khoản hoặc kết hợp các tài khoản và các cấp thứ cấp có điểm churn từ 0,33 đến 0,66.
  - Cao: tài khoản hoặc tổ hợp tài khoản và cấp phụ có điểm churn lớn hơn 0,66.

  Khi bạn dự đoán tỷ lệ rời khỏi ở cấp tài khoản, tất cả các tài khoản đều được xem xét để tính các giá trị tính năng trung bình cho các phân khúc rời khỏi. Đối với các dự đoán rời khỏi ở cấp phụ cho mọi tài khoản, việc tạo ra các phân khúc rời khỏi phụ thuộc vào cấp phụ của mặt hàng được chọn trong ngăn bên. Ví dụ: nếu một mặt hàng có danh mục sản phẩm cấp hai (đồ dùng văn phòng), thì chỉ những mặt hàng có đồ dùng văn phòng làm danh mục sản phẩm mới được xem xét khi lấy giá trị tính năng trung bình cho các phân đoạn churn. Logic này được áp dụng để đảm bảo so sánh công bằng giữa các giá trị tính năng của mặt hàng với giá trị trung bình trên các phân khúc rời khỏi thấp, trung bình và cao.

  Trong một số trường hợp, giá trị trung bình của các phân khúc rời khỏi thấp, trung bình hoặc cao bị trống hoặc không có sẵn vì không có mặt hàng nào thuộc về các phân khúc rời khỏi tương ứng dựa trên định nghĩa nói trên.

  Phần diễn giải các giá trị dưới các cột trung bình thấp, trung bình và cao sẽ khác nhau đối với các tính năng phân loại như quốc gia hoặc ngành. Vì khái niệm của giá trị tính năng "trung bình" không áp dụng cho tính năng phân loại, các giá trị trong các cột này là tỷ lệ khách hàng ở các phân khúc rời khỏi thấp, trung bình hoặc cao có cùng giá trị tính năng phân loại so với mục được chọn trong bảng điều khiển bên.

---

 > [!NOTE]
 > Trong thực thể đầu ra cho mô hình này, *ChurnScore* hiển thị xác suất dự đoán của sự gián đoạn và *IsChurn* là một nhãn nhị phân dựa trên *ChurnScore* với ngưỡng 0,5. Nếu ngưỡng mặc định này không phù hợp với tình huống của bạn, [tạo một phân khúc mới](segments.md#create-a-segment) với ngưỡng ưa thích của bạn. Không phải khách hàng nào cũng nhất thiết phải là khách hàng hiện hoạt. Một số khách hàng có thể không có bất kỳ hoạt động nào trong một thời gian dài và được coi là đã ngừng giao dịch, dựa trên sự xác định của bạn về khách hàng ngừng giao dịch. Việc dự đoán rủi ro rời khỏi đối với những khách hàng đã rời khỏi sẽ không hữu ích vì họ không phải là đối tượng quan tâm.
>
> Để xem điểm số churn, hãy truy cập **Dữ liệu** > **Thực thể** và xem tab dữ liệu cho thực thể đầu ra mà bạn đã xác định cho mô hình này.

[!INCLUDE [footer-include](includes/footer-banner.md)]
