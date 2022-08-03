---
title: Giao dịch churn dự đoán (có video)
description: Dự đoán xem khách hàng có nguy cơ không mua sản phẩm hoặc dịch vụ của bạn nữa không.
ms.date: 01/13/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: b8216b5a739964fdfff8cad7e6d6d7ce3f5308b5
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 07/18/2022
ms.locfileid: "9171121"
---
# <a name="transaction-churn-prediction"></a>Dự đoán khách hàng rời khỏi giao dịch

Dự đoán Khả năng rời bỏ giao dịch giúp dự đoán liệu khách hàng sẽ không còn mua sản phẩm hoặc dịch vụ của bạn nữa trong một khoảng thời gian nhất định hay không. Bạn có thể tạo dự đoán rời bỏ mới trên **Thông tin** > **Dự đoán**. Chọn **Dự đoán của tôi** để xem các dự đoán khác mà bạn đã tạo. 

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6Eg]

Đối với các môi trường dựa trên tài khoản doanh nghiệp, chúng ta có thể dự đoán tỷ lệ rời khỏi giao dịch cho một tài khoản, ngoài ra còn có thông tin khác như danh mục sản phẩm. Việc thêm thông số có thể giúp tìm hiểu khả năng tài khoản "Contoso" sẽ dừng mua danh mục sản phẩm "văn phòng phẩm". Ngoài ra, đối với tài khoản doanh nghiệp, chúng ta cũng có thể sử dụng AI để tạo danh sách những lý do tại sao một tài khoản có thể rời khỏi đối với một danh mục hoặc cấp thông tin thứ hai.

> [!TIP]
> Hãy thử hướng dẫn churn giao dịch dự đoán bằng cách sử dụng dữ liệu mẫu: [Hướng dẫn mẫu churn dự đoán giao dịch](sample-guide-predict-transactional-churn.md).

## <a name="prerequisites"></a>Điều kiện tiên quyết

# <a name="individual-consumers-b-to-c"></a>[Người tiêu dùng cá nhân (B2C)](#tab/b2c)

- Ít nhất [Quyền của người đóng góp](permissions.md) trong Customer Insights.
- Kiến thức kinh doanh để hiểu ý nghĩa của việc rời đi với doanh nghiệp bạn. Chúng tôi hỗ trợ các định nghĩa rời bỏ dựa trên thời gian, có nghĩa là một khách hàng được coi là đã rời bỏ sau một khoảng thời gian không mua hàng.
- Dữ liệu về các giao dịch/mua hàng của bạn và lịch sử của chúng:
    - Định danh giao dịch để phân biệt mua hàng/giao dịch.
    - Định danh khách hàng để so khớp các giao dịch với khách hàng của bạn.
    - Ngày sự kiện giao dịch, xác định ngày giao dịch diễn ra.
    - Lược đồ dữ liệu ngữ nghĩa cho mua hàng/giao dịch yêu cầu thông tin sau:
        - **ID giao dịch**: Mã định danh duy nhất của một giao dịch mua hàng.
        - **Ngày giao dịch**: Ngày mua hoặc giao dịch.
        - **Giá trị của giao dịch**: Giá trị tiền tệ/số của giao dịch/mặt hàng.
        - (Không bắt buộc) **ID sản phẩm duy nhất**: ID của sản phẩm hoặc dịch vụ được mua nếu dữ liệu của bạn ở cấp mục hàng.
        - (Không bắt buộc) **Liệu giao dịch này có phải mục trả lại hay không**: Trường true/false cho biết liệu giao dịch có phải là mục trả lại hay không. Nếu **Giá trị của giao dịch** là âm, chúng tôi cũng sẽ sử dụng thông tin này để suy ra lợi nhuận.
- (Tùy chọn) Dữ liệu về các hoạt động của khách hàng:
    - Mã định danh hoạt động để phân biệt các hoạt động cùng loại.
    - Mã định danh khách hàng để khớp hoạt động với khách hàng.
    - Thông tin hoạt động chứa tên và ngày của hoạt động.
    - Lược đồ dữ liệu ngữ nghĩa cho hoạt động của khách hàng bao gồm:
        - **Khóa chính:** Mã định danh duy nhất cho một hoạt động. Ví dụ: một lượt truy cập trang web hoặc hồ sơ sử dụng cho thấy khách hàng đã thử một mẫu sản phẩm của bạn.
        - **Dấu thời gian:** Ngày và giờ của sự kiện do khóa chính xác định.
        - **Sự kiện:** Tên của sự kiện bạn muốn sử dụng. Ví dụ: trường có tên "UserAction" trong cửa hàng tạp hóa có thể được khách hàng sử dụng phiếu giảm giá.
        - **Chi tiết:** Thông tin chi tiết về sự kiện. Ví dụ: trường có tên "CouponValue" trong cửa hàng tạp hóa có thể là giá trị tiền tệ của phiếu giảm giá.

# <a name="business-accounts-b-to-b"></a>[Tài khoản doanh nghiệp (B2B)](#tab/b2b)

- Ít nhất [Quyền của người đóng góp](permissions.md) trong Customer Insights.
- Kiến thức kinh doanh để hiểu ý nghĩa của việc rời đi với doanh nghiệp bạn. Chúng tôi hỗ trợ các định nghĩa rời bỏ dựa trên thời gian, có nghĩa là một khách hàng được coi là đã rời bỏ sau một khoảng thời gian không mua hàng.
- Dữ liệu về các giao dịch/mua hàng của bạn và lịch sử của chúng:
    - Định danh giao dịch để phân biệt mua hàng/giao dịch.
    - Định danh khách hàng để so khớp các giao dịch với khách hàng của bạn.
    - Ngày sự kiện giao dịch, xác định ngày giao dịch diễn ra.
    - Lược đồ dữ liệu ngữ nghĩa cho mua hàng/giao dịch yêu cầu thông tin sau:
        - **ID giao dịch**: Mã định danh duy nhất của một giao dịch mua hàng.
        - **Ngày giao dịch**: Ngày mua hoặc giao dịch.
        - **Giá trị của giao dịch**: Giá trị tiền tệ/số của giao dịch/mặt hàng.
        - (Không bắt buộc) **ID sản phẩm duy nhất**: ID của sản phẩm hoặc dịch vụ được mua nếu dữ liệu của bạn ở cấp mục hàng.
        - (Không bắt buộc) **Liệu giao dịch này có phải mục trả lại hay không**: Trường true/false cho biết liệu giao dịch có phải là mục trả lại hay không. Nếu **Giá trị của giao dịch** là âm, chúng tôi cũng sẽ sử dụng thông tin này để suy ra lợi nhuận.
- (Tùy chọn) Dữ liệu về các hoạt động của khách hàng:
    - Mã định danh hoạt động để phân biệt các hoạt động cùng loại.
    - Mã định danh khách hàng để khớp hoạt động với khách hàng.
    - Thông tin hoạt động chứa tên và ngày của hoạt động.
    - Lược đồ dữ liệu ngữ nghĩa cho hoạt động của khách hàng bao gồm:
        - **Khóa chính:** Mã định danh duy nhất cho một hoạt động. Ví dụ: một lượt truy cập trang web hoặc hồ sơ sử dụng cho thấy khách hàng đã thử một mẫu sản phẩm của bạn.
        - **Dấu thời gian:** Ngày và giờ của sự kiện do khóa chính xác định.
        - **Sự kiện:** Tên của sự kiện bạn muốn sử dụng. Ví dụ: trường có tên "UserAction" trong cửa hàng tạp hóa có thể được khách hàng sử dụng phiếu giảm giá.
        - **Chi tiết:** Thông tin chi tiết về sự kiện. Ví dụ: trường có tên "CouponValue" trong cửa hàng tạp hóa có thể là giá trị tiền tệ của phiếu giảm giá.
- (Không bắt buộc) Dữ liệu về khách hàng của bạn:
    - Dữ liệu này nên căn chỉnh theo các thuộc tính tĩnh hơn để đảm bảo mô hình hoạt động tốt nhất.
    - Lược đồ dữ liệu ngữ nghĩa cho dữ liệu khách hàng bao gồm:
        - **ID khách hàng:** Mã định danh duy nhất của khách hàng.
        - **Ngày tạo:** Ngày đầu tiên khách hàng được thêm.
        - **Tiểu bang hoặc Tỉnh:** Vị trí tiểu bang hoặc tỉnh của khách hàng.
        - **Quốc gia:** Quốc gia của khách hàng.
        - **Ngành:** Loại ngành của khách hàng. Ví dụ: trường có tên là "Ngành" trong máy rang cà phê có thể cho biết khách hàng có phải thuộc ngành bán lẻ không.
        - **Phân loại:** Việc phân loại khách hàng cho doanh nghiệp của bạn. Ví dụ: trường có tên "ValueSegment" là máy rang cà phê có thể là bậc của khách hàng dựa trên quy mô khách hàng.

---

- Đặc điểm dữ liệu được đề xuất:
    - Đủ dữ liệu lịch sử: Dữ liệu giao dịch cho ít nhất gấp đôi khoảng thời gian đã chọn. Tốt hơn là lịch sử giao dịch từ hai đến ba năm. 
    - Nhiều giao dịch mua trên mỗi khách hàng: Lý tưởng là tối thiểu hai giao dịch trở lên trên mỗi khách hàng.
    - Số lượng khách hàng: Tối thiểu 10 hồ sơ khách hàng, tốt nhất là 1.000 khách hàng. Mô hình sẽ không thành công nếu dưới 10 khách hàng và không đủ dữ liệu lịch sử.
    - Tính đầy đủ của dữ liệu: Ít hơn 20% giá trị bị thiếu trong trường dữ liệu của thực thể được cung cấp.

> [!NOTE]
> Đối với doanh nghiệp có tần suất mua hàng của khách hàng cao (vài tuần một lần), bạn nên chọn khoảng thời gian dự đoán ngắn hơn và xác định rủi ro khách hàng ngừng giao dịch. Đối với tần suất mua hàng thấp (vài tháng một lần hoặc một năm một lần), hãy chọn khoảng thời gian dự đoán dài hơn và xác định rủi ro khách hàng ngừng giao dịch.

## <a name="create-a-transaction-churn-prediction"></a>Dự đoán tỷ lệ rời khỏi giao dịch

1. Trong Customer Insights, chuyển đến phần **Thông tin** > **Dự đoán**.

1. Chọn **Mô hình churn khách hàng** gạch và chọn **Sử dụng mô hình này**.

1. Trong ngăn **Mô hình khách hàng rời đi**, chọn **Giao dịch** rồi chọn **Bắt đầu**.

:::image type="content" source="media/select-transaction-churn.PNG" alt-text="Ảnh chụp màn hình tùy chọn giao dịch đã chọn trong ngăn mô hình Khách hàng rời khỏi.":::
 
### <a name="name-model"></a>Đặt tên mô hình

1. Cung cấp tên cho mô hình để phân biệt với các mô hình khác.

1. Cung cấp tên cho thực thể đầu ra chỉ bằng chữ cái và chữ số, không có khoảng trắng. Đó là tên mà thực thể mô hình sẽ sử dụng. 

1. Chọn **Tiếp theo**.

### <a name="define-customer-churn"></a>Xác định khách hàng rời đi

1. Đặt **Cửa sổ dự đoán**. Ví dụ: dự đoán nguy cơ khách hàng rời đi trong 90 ngày tới để phù hợp với nỗ lực duy trì hoạt động tiếp thị của bạn. Việc dự đoán rủi ro rời đi trong một khoảng thời gian dài hơn hoặc ngắn hơn có thể gây khó khăn hơn cho việc giải quyết các yếu tố trong hồ sơ rủi ro rời đi của bạn, nhưng nó phụ thuộc vào yêu cầu kinh doanh cụ thể của bạn.
   >[!TIP]
   > Bạn có thể chọn **Lưu bản nháp** bất kỳ lúc nào để lưu dự đoán dưới dạng bản nháp. Bạn sẽ tìm thấy dự đoán nháp trong tab **Dự đoán của tôi** để tiếp tục.

1. Nhập số ngày để xác định thời gian gián đoạn trong **Định nghĩa Churn** đồng ruộng. Ví dụ: nếu khách hàng không mua hàng nào trong 30 ngày qua, họ có thể được coi là đã bỏ qua doanh nghiệp của bạn. 

1. Chọn **Tiếp** để tiếp tục.

### <a name="add-required-data"></a>Thêm dữ liệu bắt buộc

1. Chọn **Thêm dữ liệu** và chọn loại hoạt động trong ngăn bên có chứa thông tin lịch sử giao dịch hoặc mua hàng được yêu cầu.

1. Dưới **Chọn các hoạt động**, chọn các hoạt động cụ thể từ loại hoạt động đã chọn mà bạn muốn tính toán tập trung vào.

   :::image type="content" source="media/transaction-churn-select-activity.PNG" alt-text="Ngăn bên hiển thị việc chọn các hoạt động cụ thể theo loại ngữ nghĩa.":::

   Nếu bạn chưa ánh xạ hoạt động tới một loại ngữ nghĩa, hãy chọn **Chỉnh sửa** để làm vậy. Trải nghiệm được hướng dẫn để ánh xạ các hoạt động ngữ nghĩa sẽ mở ra. Ánh xạ dữ liệu của bạn đến các trường tương ứng trong loại hoạt động đã chọn.

1. Ánh xạ các thuộc tính ngữ nghĩa đến các trường được yêu cầu để chạy mô hình. Nếu các trường bên dưới chưa điền, hãy đặt cấu hình mối quan hệ từ thực thể nhật ký mua hàng cho thực thể *Khách hàng*. Chọn **Lưu.**

1. Bên trong **Thêm dữ liệu bắt buộc** bước, chọn **Tiếp theo** để tiếp tục nếu bạn không muốn thêm các hoạt động khác.


# <a name="individual-consumers-b-to-c"></a>[Người tiêu dùng cá nhân (B2C)](#tab/b2c)

### <a name="add-additional-data-optional"></a>Thêm dữ liệu bổ sung (tùy chọn)

Định cấu hình mối quan hệ từ thực thể hoạt động khách hàng của bạn thành thực thể *Khách hàng*.

1. Chọn trường xác định khách hàng trong bảng hoạt động của khách hàng. Nó có thể liên quan trực tiếp đến ID khách hàng chính của thực thể *Khách hàng* của bạn.

1. Chọn thực thể là thực thể *Khách hàng* chính của bạn.

1. Nhập tên mô tả mối quan hệ.

#### <a name="customer-activities"></a>Hoạt động của khách hàng

1. Theo tùy chọn, chọn **Thêm dữ liệu** cho **Hoạt động của khách hàng**.

1. Chọn loại hoạt động ngữ nghĩa chứa dữ liệu mà bạn muốn sử dụng, sau đó chọn một hoặc nhiều hoạt động trong phần **Hoạt động**.

1. Chọn loại hoạt động phù hợp với loại hoạt động khách hàng mà bạn đang đặt cấu hình. Chọn **Tạo mới** và chọn một loại hoạt động có sẵn hoặc tạo một loại mới.

1. Chọn **Tiếp**, sau đó chọn **Lưu**.

1. Nếu bạn có bất kỳ hoạt động khách hàng nào khác mà bạn muốn bao gồm, hãy lặp lại các bước ở trên.

# <a name="business-accounts-b-to-b"></a>[Tài khoản doanh nghiệp (B2B)](#tab/b2b)

### <a name="select-prediction-level"></a>Chọn mức dự đoán

Hầu hết các dự đoán được tạo ở cấp độ khách hàng. Trong một số tình huống, điều đó có thể không đủ chi tiết để giải quyết nhu cầu kinh doanh của bạn. Ví dụ: bạn có thể sử dụng tính năng này để dự đoán tỷ lệ rời khỏi cho một nhánh hoặc khách hàng, chứ không phải cho tổng thể khách hàng.

1. Để tạo dự đoán ở cấp độ cụ thể hơn là khách hàng, hãy chọn **Chọn thực thể cho cấp phụ**. Nếu tùy chọn không có sẵn, hãy đảm bảo rằng bạn đã hoàn thành phần trước.

1. Mở rộng các thực thể bạn muốn chọn cấp phụ hoặc sử dụng hộp bộ lọc tìm kiếm để lọc các tùy chọn đã chọn.

1. Chọn thuộc tính bạn muốn sử dụng làm cấp phụ, sau đó chọn **Thêm**.

1. Chọn **Tiếp theo**.

> [!NOTE]
> Các thực thể có sẵn trong phần này được hiển thị vì chúng có mối quan hệ với thực thể bạn đã chọn trong phần trước. Nếu bạn không thấy thực thể bạn muốn thêm, hãy đảm bảo rằng thực thể đó có mối quan hệ hợp lệ trong phần **Mối quan hệ**. Chỉ các mối quan hệ một-một và nhiều-một mới hợp lệ cho cấu hình này.

### <a name="add-additional-data-optional"></a>Thêm dữ liệu bổ sung (tùy chọn)

Định cấu hình mối quan hệ từ thực thể hoạt động khách hàng của bạn thành thực thể *Khách hàng*.

1. Chọn trường xác định khách hàng trong bảng hoạt động của khách hàng. Nó có thể liên quan trực tiếp đến ID khách hàng chính của thực thể *Khách hàng* của bạn.

1. Chọn thực thể là thực thể *Khách hàng* chính của bạn.

1. Nhập tên mô tả mối quan hệ.

#### <a name="customer-activities"></a>Hoạt động của khách hàng

1. Theo tùy chọn, chọn **Thêm dữ liệu** cho **Hoạt động của khách hàng**.

1. Chọn loại hoạt động ngữ nghĩa chứa dữ liệu mà bạn muốn sử dụng, sau đó chọn một hoặc nhiều hoạt động trong phần **Hoạt động**.

1. Chọn loại hoạt động phù hợp với loại hoạt động khách hàng mà bạn đang đặt cấu hình. Chọn **Tạo mới** và chọn một loại hoạt động có sẵn hoặc tạo một loại mới.

1. Chọn **Tiếp**, sau đó chọn **Lưu**.

1. Nếu bạn có bất kỳ hoạt động khách hàng nào khác mà bạn muốn bao gồm, hãy lặp lại các bước ở trên.

#### <a name="customers-data"></a>Dữ liệu khách hàng

1. Chọn **Thêm dữ liệu** cho **Dữ liệu khách hàng** (không bắt buộc).

1. Ánh xạ các thuộc tính ngữ nghĩa cho các trường trong dữ liệu khách hàng của riêng bạn như đã xác định. Dữ liệu trong các trường được sử dụng không nên thay đổi thường xuyên để đảm bảo mô hình hoạt động tốt nhất. Ví dụ: thao tác chọn trường "Phân loại" thay đổi hàng tháng sẽ chỉ có giá trị cuối cùng được dùng trong dự đoán, mặc dù trước đó giá trị này có thể không áp dụng cho khách hàng khi tạo mẫu dự đoán.

1. Chọn **Tiếp theo**.

### <a name="provide-an-optional-list-of-benchmark-accounts"></a>Cung cấp danh sách tùy chọn các tài khoản điểm chuẩn

Thêm danh sách các tài khoản và khách hàng doanh nghiệp mà bạn muốn dùng làm điểm chuẩn. Bạn sẽ nhận được [thông tin chi tiết về các tài khoản điểm chuẩn](#review-a-prediction-status-and-results) bao gồm điểm số rời khỏi và hầu hết các tính năng có ảnh hưởng tác động đến dự đoán rời khỏi.

1. Chọn **+ Thêm khách hàng**.

1. Chọn những khách hàng làm tiêu chuẩn.

1. Chọn **Tiếp** để tiếp tục.

---

### <a name="set-schedule-and-review-configuration"></a>Đặt lịch và xem xét cấu hình

1. Đặt tần số để đào tạo lại mô hình của bạn. Cài đặt này rất quan trọng để cập nhật độ chính xác của các dự đoán vì dữ liệu mới được nhập vào thông tin chuyên sâu về đối tượng. Hầu hết các doanh nghiệp đều có thể đào tạo lại một lần mỗi tháng và có dự đoán chính xác cao.

1. Chọn **Tiếp theo**.

1. Xem lại cấu hình dự đoán. Bạn có thể quay lại các bước trước bằng cách chọn **Chỉnh sửa** dưới giá trị hiển thị. Hoặc bạn có thể chọn một bước cấu hình từ chỉ báo tiến trình.

1. Nếu tất cả giá trị được đặt cấu hình chính xác, hãy chọn **Lưu và chạy** để bắt đầu quá trình dự đoán. Trên tab **Dự đoán của tôi**, bạn có thể xem trạng thái dự đoán. Quá trình này có thể mất vài giờ mới hoàn thành, tùy thuộc vào lượng dữ liệu dùng trong dự đoán.

## <a name="review-a-prediction-status-and-results"></a>Xem lại trạng thái dự đoán và kết quả

1. Đi đến **Thông tin** > **Dự đoán** và chọn tab **Dự đoán của tôi**.

1. Chọn dự đoán bạn muốn xem lại.
   - **Tên dự đoán**: Tên của dự đoán được cung cấp khi tạo.
   - **Loại dự đoán**: Loại mô hình được sử dụng cho dự đoán
   - **Thực thể đầu ra**: Tên của thực thể để lưu trữ đầu ra của dự đoán. Bạn có thể tìm thấy thực thể có tên này trên **Dữ liệu** > **Thực thể**.
     Trong thực thể đầu ra, *ChurnScore* là xác suất dự đoán về khả năng khách hàng ngừng sử dụng gói đăng ký và *IsChurn* là một nhãn nhị phân dựa trên *ChurnScore* với ngưỡng 0,5. Ngưỡng mặc định có thể không hoạt động trong trường hợp của bạn. [Tạo một phân khúc mới](segments.md#create-a-segment) với ngưỡng bạn muốn.
     Không phải khách hàng nào cũng nhất thiết phải là khách hàng hiện hoạt. Một số khách hàng có thể không có bất kỳ hoạt động nào trong một thời gian dài và được coi là đã ngừng giao dịch, dựa trên sự xác định của bạn về khách hàng ngừng giao dịch. Việc dự đoán rủi ro rời khỏi đối với những khách hàng đã rời khỏi sẽ không hữu ích vì họ không phải là đối tượng quan tâm.
   - **Trường được dự đoán**: Trường này chỉ được điền đối với một số loại dự báo và không được dùng trong dự đoán rời khỏi.
   - **Trạng thái**: Trạng thái chạy dự đoán.
        - **Đã xếp hàng**: Dự đoán đang chờ các quy trình khác chạy.
        - **Làm mới**: Dự đoán đang chạy để tạo ra kết quả sẽ chuyển vào thực thể đầu ra.
        - **Thất bại**: Chạy dự đoán không thành công. [Xem lại nhật ký](manage-predictions.md#troubleshoot-a-failed-prediction) để biết thêm chi tiết.
        - **Đã thành công**: Dự đoán đã thành công. Chọn **Xem** bên dưới các hình elip dọc để xem xét dự đoán
   - **Đã chỉnh sửa**: Ngày thay đổi cấu hình của dự đoán.
   - **Làm mới lần gần đây nhất**: Ngày dự đoán làm mới kết quả trong thực thể đầu ra.

1. Chọn các hình elip dọc bên cạnh dự đoán bạn muốn xem lại kết quả rồi chọn **Xem**.

   :::image type="content" source="media/model-subs-view.PNG" alt-text="Kiểm soát dạng xem để xem kết quả của dự đoán.":::

# <a name="individual-consumers-b-to-c"></a>[Người tiêu dùng cá nhân (B2C)](#tab/b2c)

1. Có 3 phần dữ liệu chính trong trang kết quả:
   - **Hiệu suất mô hình đào tạo**: A, B hoặc C là các điểm số có thể. Điểm số này cho biết hiệu suất của dự đoán và có thể giúp bạn ra quyết định sử dụng kết quả được lưu trữ trong thực thể đầu ra. Điểm số được xác định dựa trên các quy tắc sau: 
        - **A** khi mô hình dự đoán chính xác ít nhất 50% tổng số dự đoán và khi tỷ lệ dự đoán chính xác cho khách hàng đã dự đoán lớn hơn tỷ lệ cơ sở ít nhất 10%.
            
        - **B** khi mô hình dự đoán chính xác ít nhất 50% tổng số dự đoán và khi tỷ lệ dự đoán chính xác cho khách hàng đã rời đi lớn hơn tỷ lệ cơ sở tối đa 10%.
            
        - **C** khi mô hình dự đoán chính xác dưới 50% tổng số dự đoán hoặc khi tỷ lệ dự đoán chính xác cho khách hàng đã rời đi nhỏ hơn tỷ lệ cơ sở.
               
        - **Đường cơ sở** lấy đầu vào cửa sổ thời gian dự đoán cho mô hình (ví dụ: 1 năm) và mô hình tạo ra các phần thời gian khác nhau bằng cách chia nó cho 2 cho đến khi đạt một tháng hoặc ít hơn. Nó sử dụng các phân số này để tạo quy tắc công việc cho những khách hàng chưa mua hàng trong khung thời gian này. Những khách hàng này được coi là đã rời đi. Quy tắc công việc dựa trên thời gian với khả năng dự đoán cao nhất ai có khả năng rời đi được chọn làm mô hình cơ sở.
            
    - **Khả năng rời khỏi (số lượng khách hàng)**: Các nhóm khách hàng dựa trên rủi ro rời khỏi dự đoán. Dữ liệu này có thể giúp bạn về sau này nếu muốn tạo phân khúc khách hàng có khả năng rời bỏ cao. Những phân khúc này giúp hiểu được điểm cắt nên dành cho các thành phần phân khúc.
       
    - **Các yếu tố có ảnh hưởng nhất**: Có nhiều yếu tố được xem xét khi tạo dự đoán. Mỗi yếu tố có tầm quan trọng được tính toán cho các dự đoán tổng hợp mà một mô hình tạo ra. Bạn có thể sử dụng các yếu tố này để giúp xác thực kết quả dự đoán hoặc sử dụng thông tin này sau để [tạo phân khúc](segments.md) có thể giúp ảnh hưởng đến rủi ro rời khách hàng rời khỏi.


# <a name="business-accounts-b-to-b"></a>[Tài khoản doanh nghiệp (B2B)](#tab/b2b)

1. Có 3 phần dữ liệu chính trong trang kết quả:
   - **Hiệu suất mô hình đào tạo**: A, B hoặc C là các điểm số có thể. Điểm số này cho biết hiệu suất của dự đoán và có thể giúp bạn ra quyết định sử dụng kết quả được lưu trữ trong thực thể đầu ra. Điểm số được xác định dựa trên các quy tắc sau: 
        - **A** khi mô hình dự đoán chính xác ít nhất 50% tổng số dự đoán và khi tỷ lệ dự đoán chính xác cho khách hàng đã dự đoán lớn hơn tỷ lệ cơ sở ít nhất 10%.
            
        - **B** khi mô hình dự đoán chính xác ít nhất 50% tổng số dự đoán và khi tỷ lệ dự đoán chính xác cho khách hàng đã rời đi lớn hơn tỷ lệ cơ sở tối đa 10%.
            
        - **C** khi mô hình dự đoán chính xác dưới 50% tổng số dự đoán hoặc khi tỷ lệ dự đoán chính xác cho khách hàng đã rời đi nhỏ hơn tỷ lệ cơ sở.
               
        - **Đường cơ sở** lấy đầu vào cửa sổ thời gian dự đoán cho mô hình (ví dụ: 1 năm) và mô hình tạo ra các phần thời gian khác nhau bằng cách chia nó cho 2 cho đến khi đạt một tháng hoặc ít hơn. Nó sử dụng các phân số này để tạo quy tắc công việc cho những khách hàng chưa mua hàng trong khung thời gian này. Những khách hàng này được coi là đã rời đi. Quy tắc công việc dựa trên thời gian với khả năng dự đoán cao nhất ai có khả năng rời đi được chọn làm mô hình cơ sở.
            
    - **Khả năng rời khỏi (số lượng khách hàng)**: Các nhóm khách hàng dựa trên rủi ro rời khỏi dự đoán. Dữ liệu này có thể giúp bạn về sau này nếu muốn tạo phân khúc khách hàng có khả năng rời bỏ cao. Những phân khúc này giúp hiểu được điểm cắt nên dành cho các thành phần phân khúc.
       
    - **Các yếu tố có ảnh hưởng nhất**: Có nhiều yếu tố được xem xét khi tạo dự đoán. Mỗi yếu tố có tầm quan trọng được tính toán cho các dự đoán tổng hợp mà một mô hình tạo ra. Bạn có thể sử dụng các yếu tố này để giúp xác thực kết quả dự đoán hoặc sử dụng thông tin này sau để [tạo phân khúc](segments.md) có thể giúp ảnh hưởng đến rủi ro rời khách hàng rời khỏi.


1. Đối với tài khoản doanh nghiệp, bạn sẽ tìm thấy một ngăn thông tin **Phân tích tính năng có ảnh hưởng**. Nó chứa bốn phần dữ liệu:

    - Mục được chọn trong ngăn bên phải xác định nội dung trên trang này. Chọn một mục từ **Khách hàng hàng đầu** hoặc **Khách hàng điểm chuẩn**. Cả hai danh sách được sắp xếp theo giá trị giảm dần của điểm số, cho dù điểm số chỉ dành cho khách hàng hay điểm số kết hợp cho khách hàng và một cấp độ thứ cấp như danh mục sản phẩm.
        
        - **Khách hàng hàng đầu**: Danh sách 10 khách hàng có nguy cơ rời khỏi cao nhất và nguy cơ rời khỏi thấp nhất dựa trên điểm số rời khỏi của họ. 
        - **Khách hàng điểm chuẩn**: Danh sách tối đa 10 khách hàng đã được chọn trong khi đặt cấu hình mô hình.
 
    - **Điểm rời khỏi:** Hiển thị điểm số rời khỏi cho mục đã chọn trong ngăn bên phải.
    
    - **Phân bổ rủi ro rời khỏi:** Cho biết khả năng phân bổ rủi ro rời khỏi giữa các khách hàng và phần trăm khách hàng được chọn. 
    
    - **Các tính năng hàng đầu làm tăng và giảm rủi ro rời khỏi:** Đối với mục đã chọn trong ngăn bên phải, 5 tính năng hàng đầu làm tăng và giảm nguy cơ rời khỏi sẽ được liệt kê. Đối với mỗi tính năng có ảnh hưởng, bạn sẽ tìm thấy giá trị của tính năng cho mặt hàng đó và ảnh hưởng của nó đối với điểm số rời khỏi. Giá trị trung bình của từng đối tính năng trên các phân khúc khách hàng có tỷ lệ rời khỏi thấp, trung bình và cao cũng được hiển thị. Nó giúp ngữ cảnh hóa tốt hơn các giá trị của các tính năng có ảnh hưởng hàng đầu đối với mặt hàng đã chọn và so sánh nó với các phân khúc khách hàng có khả năng rời khỏi thấp, trung bình và cao.

       - Thấp: các tài khoản hoặc kết hợp tài khoản và mức phụ với điểm số rời khỏi từ 0 đến 0,33
       - Thấp: các tài khoản hoặc kết hợp tài khoản và mức phụ với điểm số rời khỏi từ 0,33 đến 0,66
       - Cao: các tài khoản hoặc kết hợp tài khoản và mức phụ với điểm số rời khỏi lớn hơn 0,66
    
       Khi bạn dự đoán tỷ lệ rời khỏi ở cấp tài khoản, tất cả các tài khoản đều được xem xét để tính các giá trị tính năng trung bình cho các phân khúc rời khỏi. Đối với các dự đoán rời khỏi ở cấp phụ cho mọi tài khoản, việc tạo ra các phân khúc rời khỏi phụ thuộc vào cấp phụ của mặt hàng được chọn trong ngăn bên. Ví dụ: nếu một mặt hàng có danh mục sản phẩm thứ cấp = đồ dùng văn phòng, thì chỉ những mặt hàng có đồ dùng văn phòng làm danh mục sản phẩm mới được xem xét khi tính giá trị tính năng trung bình cho các phân khúc rời khỏi. Logic này được áp dụng để đảm bảo so sánh công bằng giữa các giá trị tính năng của mặt hàng với giá trị trung bình trên các phân khúc rời khỏi thấp, trung bình và cao.

       Trong một số trường hợp, giá trị trung bình của các phân khúc rời khỏi thấp, trung bình hoặc cao bị trống hoặc không có sẵn vì không có mặt hàng nào thuộc về các phân khúc rời khỏi tương ứng dựa trên định nghĩa nói trên.
       
       > [!NOTE]
       > Phần diễn giải các giá trị dưới các cột trung bình thấp, trung bình và cao sẽ khác nhau đối với các tính năng phân loại như quốc gia hoặc ngành. Vì khái niệm của giá trị tính năng "trung bình" không áp dụng cho tính năng phân loại, các giá trị trong các cột này là tỷ lệ khách hàng ở các phân khúc rời khỏi thấp, trung bình hoặc cao có cùng giá trị tính năng phân loại so với mục được chọn trong bảng điều khiển bên.

---

## <a name="manage-predictions"></a>Quản lý dự đoán

Bạn có thể tối ưu hóa, khắc phục sự cố, làm mới hoặc xóa dự đoán. Hãy xem lại báo cáo khả năng sử dụng dữ liệu đầu vào để tìm hiểu cách giúp dự đoán nhanh hơn và đáng tin cậy hơn. Để biết thêm thông tin, hãy chuyển đến phần [Quản lý dự báo](manage-predictions.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
