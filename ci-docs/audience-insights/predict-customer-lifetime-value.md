---
title: Dự đoán giá trị trọn đời của khách hàng (CLV)
description: Dự đoán doanh thu tiềm năng cho những khách hàng đang hoạt động trong tương lai.
ms.date: 02/05/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: wameng
manager: shellyha
ms.openlocfilehash: e2f92a64d01a443bcf3c1605621abe045b93ee5e
ms.sourcegitcommit: 6b07c9c3102761be162e4842f3c9fbc19f948a9b
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 05/25/2021
ms.locfileid: "6095536"
---
# <a name="customer-lifetime-value-clv-prediction-preview"></a>Dự đoán Giá trị trọn đời của khách hàng (CLV) (Xem trước)

Dự đoán giá trị tiềm năng (doanh thu) mà các khách hàng cá nhân đang hoạt động sẽ mang lại cho doanh nghiệp của bạn trong suốt khoảng thời gian xác định trong tương lai. Tính năng này có thể giúp bạn đạt được nhiều mục tiêu: 
- Xác định những khách hàng có giá trị cao và xử lý thông tin chi tiết này
- Tạo phân khúc khách hàng chiến lược dựa trên giá trị tiềm năng của họ để chạy các chiến dịch cá nhân hóa với các nỗ lực bán hàng, tiếp thị và hỗ trợ được nhắm mục tiêu
- Hướng dẫn phát triển sản phẩm bằng cách tập trung vào các tính năng làm tăng giá trị khách hàng
- Tối ưu hóa chiến lược bán hàng hoặc tiếp thị và phân bổ ngân sách chính xác hơn để tiếp cận khách hàng
- Ghi nhận và tặng thưởng những khách hàng có giá trị cao thông qua các chương trình phần thưởng hoặc khách hàng thân thiết 

## <a name="prerequisites"></a>Điều kiện tiên quyết

Trước khi bắt đầu, hãy suy nghĩ xem CLV có ý nghĩa như thế nào đối với doanh nghiệp của bạn. Hiện tại, chúng tôi hỗ trợ dự đoán CLV dựa trên giao dịch. Giá trị dự đoán của một khách hàng dựa trên lịch sử giao dịch với doanh nghiệp. Để tạo dự đoán, bạn cần có quyền [Người đóng góp](permissions.md) trở lên.

Vì việc định cấu hình và chạy mô hình CLV không mất nhiều thời gian, hãy cân nhắc tạo một số mô hình với các tùy chọn đầu vào khác nhau và so sánh kết quả của các mô hình để xem kịch bản mô hình nào phù hợp nhất với nhu cầu kinh doanh của bạn.

###  <a name="data-requirements"></a>Các yêu cầu về dữ liệu

Dữ liệu sau đây là bắt buộc và ở những vị trí được đánh dấu là tùy chọn, bạn nên sử dụng để tăng hiệu suất mô hình. Mô hình có thể xử lý càng nhiều dữ liệu, thì dự đoán sẽ càng chính xác. Do đó, bạn nên nhập thêm dữ liệu hoạt động của khách hàng, nếu có.

- Mã nhận dạng khách hàng: Mã định danh duy nhất để khớp các giao dịch với một khách hàng cá nhân

- Lịch sử giao dịch: Bản ghi giao dịch lịch sử với giản đồ dữ liệu ngữ nghĩa bên dưới
    - **ID giao dịch**: Mã định danh duy nhất của mỗi giao dịch
    - **Ngày giao dịch**: Ngày, tốt nhất là dấu thời gian của mỗi giao dịch
    - **Số tiền giao dịch**: Giá trị tiền tệ (ví dụ: doanh thu hoặc biên lợi nhuận) của mỗi giao dịch
    - **Nhãn được gán cho hàng trả lại** (tùy chọn): Giá trị boolean biểu thị liệu giao dịch có phải là trả lại hàng hay không 
    - **ID sản phẩm** (tùy chọn): ID sản phẩm của sản phẩm tham gia vào giao dịch

- Dữ liệu bổ sung (tùy chọn), ví dụ
    - Hoạt động web: lịch sử truy cập trang web, lịch sử email
    - Hoạt động khách hàng thân thiết: tích lũy điểm thưởng và lịch sử đổi điểm
    - Bản ghi dịch vụ khách hàng, cuộc gọi dịch vụ, khiếu nại hoặc lịch sử trả lại
- Dữ liệu về các hoạt động của khách hàng (tùy chọn):
    - Mã định danh hoạt động để phân biệt các hoạt động cùng loại
    - Mã định danh khách hàng để ánh xạ hoạt động với khách hàng
    - Thông tin về hoạt động chứa tên và ngày của hoạt động
    - Lược đồ dữ liệu ngữ nghĩa cho các hoạt động bao gồm: 
        - **Khóa chính**: Mã định danh duy nhất cho một hoạt động
        - **Dấu thời gian**: Ngày và giờ của sự kiện do khóa chính xác định
        - **Sự kiện (tên hoạt động)**: Tên sự kiện bạn muốn sử dụng
        - **Chi tiết (số tiền hoặc giá trị)**: Chi tiết về hoạt động của khách hàng

- Đặc điểm dữ liệu được đề xuất:
    - Đủ dữ liệu lịch sử: Ít nhất một năm dữ liệu giao dịch. Tốt nhất là từ hai đến ba năm dữ liệu giao dịch để dự đoán CLV trong một năm.
    - Nhiều giao dịch mua trên mỗi khách hàng: Lý tưởng là tối thiểu hai đến ba giao dịch trên mỗi ID khách hàng, tốt nhất là trong nhiều ngày.
    - Số lượng khách hàng: Tối thiểu 100 khách hàng duy nhất, tốt nhất là 10.000 khách hàng. Mô hình sẽ không thành công nếu dưới 100 khách hàng và không đủ dữ liệu lịch sử
    - Tính đầy đủ của dữ liệu: Ít hơn 20% giá trị bị thiếu trong trường bắt buộc thuộc dữ liệu đầu vào   

> [!NOTE]
> - Mô hình yêu cầu phải có lịch sử giao dịch của khách hàng. Hiện chỉ có thể đặt cấu hình một thực thể lịch sử giao dịch. Nếu có nhiều thực thể mua hàng/giao dịch, bạn có thể liên kết những thực thể này trong Power Query trước khi nhập dữ liệu.
> - Tuy nhiên, nhằm có thêm dữ liệu hoạt động của khách hàng (tùy chọn), bạn có thể thêm bao nhiêu thực thể hoạt động của khách hàng tùy thích để mô hình xem xét.

## <a name="create-a-customer-lifetime-value-prediction"></a>Tạo dự đoán Giá trị trọn đời của khách hàng

1. Trong thông tin chuyên sâu về đối tượng, hãy chuyển đến **Thông tin** > **Dự đoán**.

1. Chọn ô **Giá trị trọn đời của khách hàng** và chọn **Sử dụng mô hình**. 

1. Trong ngăn **Giá trị trọn đời của khách hàng (xem trước)**, hãy chọn **Bắt đầu**.

1. **Đặt tên cho mô hình này** và **Tên thực thể đầu ra** để phân biệt chúng với các mô hình hoặc thực thể khác.

1. Chọn **Tiếp theo**.

### <a name="define-model-preferences"></a>Xác định các tùy chọn mô hình

1. Đặt một **Khoảng thời gian dự đoán** để xác định khoảng thời gian trong tương lai bạn muốn dự đoán CLV.    
   Theo mặc định, đơn vị được đặt là tháng. Bạn có thể thay đổi thành năm để nhìn xa hơn trong tương lai.

   > [!TIP]
   > Để dự đoán chính xác CLV cho khoảng thời gian bạn đặt, bạn cần một khoảng thời gian dữ liệu lịch sử có thể so sánh được. Ví dụ: nếu bạn muốn dự đoán CLV cho 12 tháng tới, bạn nên có ít nhất 18-24 tháng dữ liệu lịch sử.

1. Chỉ định tầm quan trọng của **Khách hàng đang hoạt động** đối với doanh nghiệp của bạn. Đặt khung thời gian mà khách hàng phải có ít nhất một giao dịch để được coi là đang hoạt động. Mô hình sẽ chỉ dự đoán CLV cho những khách hàng đang hoạt động. 
   - **Để mô hình tính toán khoảng thời gian mua hàng (khuyến nghị)**: Mô hình phân tích dữ liệu của bạn và xác định khoảng thời gian dựa trên các giao dịch mua trước đây.
   - **Đặt khoảng thời gian theo cách thủ công**: Nếu bạn có định nghĩa kinh doanh cụ thể về khách hàng đang hoạt động, hãy chọn tùy chọn này và đặt khoảng thời gian cho phù hợp.

1. Xác định phần trăm của **Khách hàng có giá trị cao** để cho phép mô hình cung cấp kết quả phù hợp với định nghĩa kinh doanh của bạn.
    - **Tính toán mô hình (khuyến nghị)**: Mô hình phân tích dữ liệu của bạn và xác định thế nào là khách hàng có giá trị cao đối với doanh nghiệp của bạn dựa trên lịch sử giao dịch của khách hàng. Mô hình sử dụng quy tắc heuristic (lấy cảm hứng từ quy tắc 80/20 hay nguyên tắc pareto) để tìm tỷ lệ khách hàng có giá trị cao. Phần trăm khách hàng đã đóng góp vào 80% doanh thu tích lũy cho doanh nghiệp của bạn trong giai đoạn lịch sử được coi là khách hàng có giá trị cao. Thông thường, dưới 30-40% khách hàng đóng góp vào 80% doanh thu tích lũy. Tuy nhiên, con số này có thể thay đổi tùy thuộc vào doanh nghiệp và ngành của bạn.    
    - **Phần trăm khách hàng tích cực hàng đầu**: Xác định khách hàng có giá trị cao cho doanh nghiệp của bạn dưới dạng phần trăm khách hàng trả tiền tích cực hàng đầu. Ví dụ: bạn có thể sử dụng tùy chọn này để xác định khách hàng có giá trị cao là 20% khách hàng trả tiền hàng đầu trong tương lai.

    Nếu doanh nghiệp của bạn xác định khách hàng có giá trị cao theo một cách khác, [vui lòng chia sẻ với chúng tôi vì chúng tôi rất muốn biết](https://go.microsoft.com/fwlink/?linkid=2074172).

1. Chọn **Tiếp theo** để tiếp tục bước tiếp theo.

### <a name="add-required-data"></a>Thêm dữ liệu bắt buộc

1. Trong bước **Dữ liệu bắt buộc**, chọn **Thêm dữ liệu** cho **Lịch sử giao dịch khách hàng** và chọn thực thể cung cấp thông tin lịch sử giao dịch như được mô tả trong [điều kiện tiên quyết](#prerequisites).

1. Ánh xạ các trường ngữ nghĩa với các thuộc tính trong thực thể lịch sử mua hàng của bạn và chọn **Tiếp theo**.

   :::image type="content" source="media/clv-add-customer-data-mapping.png" alt-text="Hình ảnh của bước cấu hình để ánh xạ các thuộc tính dữ liệu cho dữ liệu cần thiết.":::
 
1. Nếu các trường bên dưới không được điền, hãy định cấu hình mối quan hệ từ thực thể lịch sử mua hàng của bạn với thực thể *Khách hàng* rồi chọn **Lưu**.
    1. Chọn thực thể lịch sử giao dịch.
    1. Chọn trường xác định khách hàng trong thực thể lịch sử mua hàng. Trường đó cần liên quan đến ID khách hàng chính của thực thể khách hàng.
    1. Chọn một thực thể phù hợp với thực thể tùy chỉnh chính của bạn.
    1. Nhập tên mô tả mối quan hệ.

      :::image type="content" source="media/clv-add-customer-data-relationship.png" alt-text="Hình ảnh của bước cấu hình để xác định mối quan hệ với thực thể khách hàng.":::

1. Chọn **Tiếp theo**.

### <a name="add-optional-data"></a>Thêm dữ liệu tùy chọn

Dữ liệu phản ánh các tương tác chính của khách hàng (như web, dịch vụ khách hàng và bản ghi sự kiện) bổ sung thêm ngữ cảnh vào hồ sơ giao dịch. Dữ liệu hoạt động khách hàng của bạn có càng nhiều mẫu thì càng cải thiện độ chính xác của các dự đoán. 

1. Trong bước **Dữ liệu bổ sung (tùy chọn)**, hãy chọn **Thêm dữ liệu**. Chọn thực thể hoạt động khách hàng cung cấp thông tin hoạt động của khách hàng như được mô tả trong [điều kiện tiên quyết](#prerequisites).

1. Ánh xạ các trường ngữ nghĩa với các thuộc tính trong thực thể hoạt động của khách hàng và chọn **Tiếp theo**.

   :::image type="content" source="media/clv-additional-data-mapping.png" alt-text="Hình ảnh của bước cấu hình để ánh xạ các trường cho dữ liệu bổ sung.":::

1. Chọn loại hoạt động phù hợp với loại hoạt động của khách hàng mà bạn đang thêm. Chọn từ các loại hoạt động hiện có hoặc thêm một loại hoạt động mới.

1. Định cấu hình mối quan hệ từ thực thể hoạt động khách hàng của bạn thành thực thể *Khách hàng*.
    
    1. Chọn trường xác định khách hàng trong bảng hoạt động của khách hàng. Nó có thể liên quan trực tiếp đến ID khách hàng chính của thực thể *Khách hàng* của bạn.
    1. Chọn thực thể *Khách hàng* khớp với thực thể *Khách hàng* chính của bạn.
    1. Nhập tên mô tả mối quan hệ.

   :::image type="content" source="media/clv-additional-data.png" alt-text="Hình ảnh về bước trong quy trình cấu hình để thêm dữ liệu bổ sung và định cấu hình hoạt động với các ví dụ được điền đầy đủ.":::

1. Chọn **Lưu**.    
    Thêm nhiều dữ liệu hơn nếu có các hoạt động khác của khách hàng mà bạn muốn đưa vào.

1. Chọn **Tiếp theo**.

### <a name="set-update-schedule"></a>Đặt lịch trình cập nhật

1. Trong bước **Lịch trình cập nhật dữ liệu**, hãy chọn tần suất đào tạo lại mô hình của bạn dựa trên dữ liệu mới nhất. Cài đặt này rất quan trọng để cập nhật độ chính xác của các dự đoán vì dữ liệu mới được nhập vào thông tin chuyên sâu về đối tượng. Hầu hết các doanh nghiệp đều có thể đào tạo lại một lần mỗi tháng và có dự đoán chính xác cao.

1. Chọn **Tiếp theo**.

### <a name="review-and-run-the-model-configuration"></a>Xem lại và chạy cấu hình mô hình

1. Trong bước **Xem lại chi tiết mô hình của bạn**, hãy xác thực cấu hình của dự đoán. Bạn có thể quay lại bất kỳ phần nào của cấu hình dự đoán bằng cách chọn **Chỉnh sửa** bên dưới giá trị hiển thị. Bạn cũng có thể chọn một bước cấu hình từ chỉ báo tiến trình.

1. Nếu tất cả các giá trị được định cấu hình chính xác, hãy chọn **Lưu và chạy** để bắt đầu chạy mô hình. Trên thẻ **Dự đoán của tôi**, bạn có thể xem trạng thái của quy trình dự đoán. Quá trình này có thể mất vài giờ mới hoàn thành, tùy thuộc vào lượng dữ liệu dùng trong dự đoán.

## <a name="review-prediction-status-and-results"></a>Xem lại trạng thái và kết quả dự đoán

### <a name="review-prediction-status"></a>Xem lại trạng thái dự đoán

1.  Đi đến **Thông tin** > **Dự đoán** và chọn tab **Dự đoán của tôi**.
2.  Chọn dự đoán bạn muốn xem lại.

- **Tên dự đoán**: Tên của dự đoán được cung cấp khi tạo.
- **Loại dự đoán**: Loại mô hình được sử dụng cho dự đoán
- **Thực thể đầu ra**: Tên của thực thể để lưu trữ đầu ra của dự đoán. Chuyển đến **Dữ liệu** > **Thực thể** để tìm thực thể có tên này.
- **Trường dự đoán**: Trường này chỉ được điền cho một số loại dự đoán và không được sử dụng trong dự đoán giá trị trọn đời của khách hàng.
- **Trạng thái**: Trạng thái chạy dự đoán.
    - **Đã xếp hàng**: Dự đoán đang đợi các quy trình khác hoàn tất.
    - **Làm mới**: Dự đoán hiện đang chạy để tạo ra kết quả sẽ chuyển vào thực thể đầu ra.
    - **Thất bại**: Chạy dự đoán không thành công. [Xem lại nhật ký](manage-predictions.md#troubleshoot-a-failed-prediction) để biết thêm chi tiết.
    - **Đã thành công**: Dự đoán đã thành công. Chọn **Dạng xem** dưới dấu ba chấm dọc để xem lại kết quả dự đoán.
- **Đã chỉnh sửa**: Ngày thay đổi cấu hình của dự đoán.
- **Làm mới lần gần đây nhất**: Ngày dự đoán làm mới kết quả trong thực thể đầu ra.

### <a name="review-prediction-results"></a>Xem lại kết quả dự đoán

1. Đi đến **Thông tin** > **Dự đoán** và chọn tab **Dự đoán của tôi**.

1. Chọn dự đoán bạn muốn xem lại kết quả.

Có ba phần dữ liệu chính trong trang kết quả.

- **Hiệu suất mô hình đào tạo**: A, B hoặc C là các điểm khả thi. Điểm này cho biết hiệu suất của dự đoán và có thể giúp bạn đưa ra quyết định sử dụng kết quả được lưu trữ trong thực thể đầu ra. Chọn **Tìm hiểu về điểm số này** để hiểu rõ hơn về các chỉ số hiệu suất của mô hình cơ bản và cách lấy điểm hiệu suất cuối cùng của mô hình.
  
  :::image type="content" source="media/clv-model-score.png" alt-text="Hình ảnh của hộp thông tin điểm mô hình với điểm A.":::

  Sử dụng định nghĩa về khách hàng giá trị cao được cung cấp trong khi định cấu hình dự đoán, hệ thống đánh giá hiệu quả dự đoán khách hàng có giá trị cao của mô hình trí tuệ nhân tạo so với mô hình cơ sở.    

  Điểm được xác định dựa trên các quy tắc sau:
  - **A** khi mô hình dự đoán khách hàng có giá trị cao chính xác hơn mô hình cơ sở tối thiểu 5%.
  - **B** khi mô hình dự đoán khách hàng có giá trị cao chính xác hơn mô hình cơ sở từ 0-5%.
  - **C** khi mô hình dự đoán khách hàng có giá trị cao ít chính xác hơn mô hình cơ sở.

  Ngăn **Xếp hạng mô hình** hiển thị thêm chi tiết về hiệu suất mô hình trí tuệ nhân tạo và mô hình cơ sở. Mô hình cơ sở sử dụng cách tiếp cận không dựa trên AI để tính toán giá trị trọn đời của khách hàng chủ yếu dựa trên các giao dịch mua trước đây của khách hàng.     
  Công thức chuẩn được dùng để tính CLV theo mô hình cơ sở:    

  _**CLV cho mỗi khách hàng** = Giao dịch mua trung bình hàng tháng của khách hàng trong khoảng thời gian khách hàng đang hoạt động * Số tháng trong khoảng thời gian CLV dự đoán * Tỷ lệ giữ chân tổng thể của tất cả khách hàng*_

  Mô hình AI được so sánh với mô hình cơ sở dựa trên hai chỉ số hiệu suất của mô hình.
  
  - **Tỷ lệ thành công khi dự đoán khách hàng có giá trị cao**

    Xem sự khác biệt trong việc dự đoán khách hàng có giá trị cao bằng cách sử dụng mô hình AI so với mô hình cơ sở. Ví dụ: tỷ lệ thành công 84% có nghĩa là trong số tất cả khách hàng có giá trị cao trong dữ liệu đào tạo, mô hình AI có thể dự đoán chính xác 84%. Sau đó, chúng tôi so sánh tỷ lệ thành công này với tỷ lệ thành công của mô hình cơ sở để báo cáo sự thay đổi tương đối. Giá trị này được sử dụng để gán điểm cho mô hình.

  - **Chỉ số lỗi**
    
    Một chỉ số khác cho phép bạn xem xét hiệu suất tổng thể của mô hình về lỗi dự đoán các giá trị trong tương lai. Chúng tôi sử dụng chỉ số Lỗi trung bình bình phương (RMSE) tổng thể để đánh giá lỗi này. RMSE là một cách tiêu chuẩn để đo lường lỗi dự đoán dữ liệu định lượng của một mô hình. RMSE của mô hình AI được so sánh với RMSE của mô hình cơ sở và báo cáo sự khác biệt tương đối.

  Mô hình AI ưu tiên xếp hạng chính xác khách hàng theo giá trị mà họ mang lại cho doanh nghiệp của bạn. Vì vậy, chỉ tỷ lệ thành công khi dự đoán khách hàng có giá trị cao được dùng để tính điểm cuối cùng của mô hình. Chỉ số RMSE nhạy cảm với các trường hợp ngoại lệ. Trong các tình huống mà bạn có một tỷ lệ nhỏ khách hàng có giá trị mua hàng cực cao, chỉ số RMSE tổng thể có thể không cung cấp bức tranh đầy đủ về hiệu suất của mô hình.   

- **Giá trị của khách hàng theo phân vị**: Sử dụng định nghĩa của bạn về khách hàng giá trị cao, khách hàng được nhóm thành giá trị thấp và giá trị cao, dựa trên dự đoán CLV của họ và được hiển thị trong biểu đồ. Bằng cách di chuột qua các thanh trong biểu đồ, bạn có thể thấy số lượng khách hàng trong mỗi nhóm và CLV trung bình của nhóm đó. Dữ liệu này có thể hữu ích nếu bạn muốn [tạo phân khúc khách hàng](segments.md) dựa trên dự đoán CLV của họ.

- **Các yếu tố ảnh hưởng nhất**: Các yếu tố khác nhau được xem xét khi tạo dự đoán CLV của bạn dựa trên dữ liệu đầu vào được cung cấp cho mô hình AI. Mỗi yếu tố có tầm quan trọng được tính toán cho các dự đoán tổng hợp mà một mô hình tạo ra. Bạn có thể sử dụng các yếu tố này để giúp xác nhận kết quả dự đoán. Những yếu tố này cũng cung cấp thêm thông tin chi tiết về các yếu tố có ảnh hưởng nhất góp phần vào việc dự đoán CLV trên tất cả các khách hàng của bạn.

## <a name="manage-predictions"></a>Quản lý dự đoán

Bạn có thể tối ưu hóa, khắc phục sự cố, làm mới hoặc xóa dự đoán. Hãy xem lại báo cáo khả năng sử dụng dữ liệu đầu vào để tìm hiểu cách giúp dự đoán nhanh hơn và đáng tin cậy hơn. Để biết thêm thông tin, hãy xem phần [Quản lý dự đoán](manage-predictions.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
