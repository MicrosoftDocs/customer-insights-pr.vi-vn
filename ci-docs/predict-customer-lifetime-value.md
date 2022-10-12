---
title: Dự đoán giá trị trọn đời của khách hàng (CLV)
description: Dự đoán doanh thu tiềm năng cho những khách hàng đang hoạt động trong tương lai.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-predictions
- ci-create-prediction
- ci-custom-models
- customerInsights
ms.openlocfilehash: f27462ac327027e50e23387ac9f75a671db9a86d
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610400"
---
# <a name="predict-customer-lifetime-value-clv"></a>Dự đoán giá trị trọn đời của khách hàng (CLV)

Dự đoán giá trị tiềm năng (doanh thu) mà các khách hàng cá nhân đang hoạt động sẽ mang lại cho doanh nghiệp của bạn trong suốt khoảng thời gian xác định trong tương lai. Dự đoán này giúp bạn:

- Xác định những khách hàng có giá trị cao và xử lý thông tin chi tiết này.
- Tạo các phân khúc khách hàng có chiến lược dựa trên giá trị tiềm năng của họ để chạy các chiến dịch được cá nhân hóa với các nỗ lực bán hàng, tiếp thị và hỗ trợ được nhắm mục tiêu.
- Hướng dẫn phát triển sản phẩm bằng cách tập trung vào các tính năng làm tăng giá trị của khách hàng.
- Tối ưu hóa chiến lược bán hàng hoặc tiếp thị và phân bổ ngân sách chính xác hơn cho việc tiếp cận khách hàng.
- Ghi nhận và khen thưởng những khách hàng có giá trị cao thông qua các chương trình phần thưởng hoặc khách hàng thân thiết.

Xác định CLV có ý nghĩa như thế nào đối với doanh nghiệp của bạn. Chúng tôi hỗ trợ CLV dựa trên giao dịch dự đoán. Giá trị dự đoán của khách hàng dựa trên lịch sử giao dịch kinh doanh. Cân nhắc tạo một số mô hình với các tùy chọn đầu vào khác nhau và so sánh kết quả mô hình để xem kịch bản mô hình nào phù hợp nhất với nhu cầu kinh doanh của bạn.

> [!TIP]
> Hãy thử CLV dự đoán bằng cách sử dụng dữ liệu mẫu: [Hướng dẫn mẫu về giá trị lâu dài của khách hàng (CLV) dự đoán](sample-guide-predict-clv.md).

## <a name="prerequisites"></a>Điều kiện tiên quyết

- Ít nhất [Người đóng góp](permissions.md) sự cho phép
- Ít nhất 100 khách hàng duy nhất, tốt nhất là hơn 10.000 khách hàng
- Mã định danh khách hàng, một mã định danh duy nhất để khớp các giao dịch với một khách hàng cá nhân
- Có ít nhất một năm lịch sử giao dịch, tốt nhất là hai đến ba năm. Tốt nhất, ít nhất hai đến ba giao dịch trên mỗi ID khách hàng, tốt nhất là trong nhiều ngày. Lịch sử giao dịch phải bao gồm:
  - **ID giao dịch**: Mã định danh duy nhất của mỗi giao dịch
  - **Ngày Giao dịch** : Dấu ngày hoặc giờ của mỗi giao dịch
  - **Số tiền giao dịch**: Giá trị tiền tệ (ví dụ: doanh thu hoặc biên lợi nhuận) của mỗi giao dịch
  - **Nhãn được chỉ định để trả lại** : Giá trị đúng / sai của Boolean biểu thị liệu giao dịch có phải là trả lại hay không
  - **ID sản phẩm** : ID sản phẩm của sản phẩm tham gia vào giao dịch
- Dữ liệu về hoạt động của khách hàng:
  - **Khóa chính** : Giá trị nhận dạng duy nhất cho một hoạt động
  - **Dấu thời gian** : Ngày và giờ của sự kiện được xác định bởi khóa chính
  - **Sự kiện (tên hoạt động)** : Tên sự kiện bạn muốn sử dụng
  - **Chi tiết (số tiền hoặc giá trị)**: Chi tiết về hoạt động của khách hàng
- Dữ liệu bổ sung như:
  - Hoạt động web: Lịch sử truy cập trang web hoặc lịch sử email
  - Hoạt động dành cho khách hàng thân thiết: Tích lũy điểm thưởng và lịch sử đổi điểm
  - Dịch vụ khách hàng nhật ký: Lịch sử cuộc gọi dịch vụ, khiếu nại hoặc trả hàng
  - Thông tin hồ sơ khách hàng
- Thiếu ít hơn 20% giá trị trong các trường bắt buộc

> [!NOTE]
> Chỉ có thể định cấu hình một thực thể lịch sử giao dịch. Nếu có nhiều thực thể mua hàng hoặc giao dịch, hãy kết hợp chúng trong Power Query trước khi nhập dữ liệu.

## <a name="create-a-customer-lifetime-value-prediction"></a>Tạo dự đoán Giá trị trọn đời của khách hàng

Lựa chọn **Lưu bản nháp** bất kỳ lúc nào để lưu dự đoán dưới dạng bản nháp. Bản nháp dự đoán hiển thị trong **Dự đoán của tôi** chuyển hướng.

1. Đi đến **Sự thông minh** > **Phỏng đoán**.

1. Trên **Tạo ra** tab, chọn **Sử dụng mô hình** trên **Giá trị lâu dài của khách hàng** ngói.

1. Chọn **Bắt đầu**.

1. **Đặt tên cho mô hình này** và **Tên thực thể đầu ra** để phân biệt chúng với các mô hình hoặc thực thể khác.

1. Chọn **Tiếp theo**.

### <a name="define-model-preferences"></a>Xác định các tùy chọn mô hình

1. Đặt một **Khoảng thời gian dự đoán** để xác định khoảng thời gian trong tương lai bạn muốn dự đoán CLV. Theo mặc định, đơn vị được đặt là tháng.

   > [!TIP]
   > Để dự đoán chính xác CLV trong khoảng thời gian đã đặt, cần có một khoảng thời gian dữ liệu lịch sử có thể so sánh được. Ví dụ: nếu bạn muốn dự đoán CLV trong 12 tháng tới, hãy có ít nhất 18-24 tháng dữ liệu lịch sử.

1. Đặt khung thời gian mà khách hàng phải có ít nhất một giao dịch để được coi là đang hoạt động. Mô hình chỉ dự đoán CLV cho **Khách hàng năng động**.
   - **Để mô hình tính toán khoảng thời gian mua hàng (khuyến nghị)** : Mô hình phân tích dữ liệu của bạn và xác định khoảng thời gian dựa trên các giao dịch mua trước đây.
   - **Đặt khoảng thời gian theo cách thủ công** : Khoảng thời gian cho định nghĩa của bạn về một khách hàng đang hoạt động.

1. Xác định phần trăm của **Khách hàng có giá trị cao**.
    - **Tính toán mô hình (khuyến nghị)** : Mô hình sử dụng quy tắc 80/20. Phần trăm khách hàng đã đóng góp vào 80% doanh thu tích lũy cho doanh nghiệp của bạn trong giai đoạn lịch sử được coi là khách hàng có giá trị cao. Thông thường, dưới 30-40% khách hàng đóng góp vào 80% doanh thu tích lũy. Tuy nhiên, con số này có thể thay đổi tùy thuộc vào doanh nghiệp và ngành của bạn.
    - **Phần trăm khách hàng tích cực hàng đầu** : Phân vị cụ thể cho khách hàng có giá trị cao. Ví dụ, nhập **25** để xác định khách hàng có giá trị cao là 25% khách hàng trả tiền hàng đầu trong tương lai.

    Nếu doanh nghiệp của bạn xác định khách hàng có giá trị cao theo một cách khác, [vui lòng chia sẻ với chúng tôi vì chúng tôi rất muốn biết](https://go.microsoft.com/fwlink/?linkid=2074172).

1. Chọn **Tiếp theo**.

### <a name="add-required-data"></a>Thêm dữ liệu bắt buộc

1. Lựa chọn **Thêm dữ liệu** vì **Lịch sử giao dịch của khách hàng**.

1. Chọn loại hoạt động ngữ nghĩa, **Đơn đặt hàng** hoặc **SalesOrderLine**, chứa lịch sử giao dịch. Nếu hoạt động chưa được thiết lập, hãy chọn **nơi đây** và tạo ra nó.

1. Dưới **Các hoạt động**, nếu các thuộc tính hoạt động được ánh xạ theo ngữ nghĩa khi hoạt động được tạo, hãy chọn các thuộc tính hoặc thực thể cụ thể mà bạn muốn tính toán tập trung vào. Nếu ánh xạ ngữ nghĩa không xảy ra, hãy chọn **Chỉnh sửa** và lập bản đồ dữ liệu của bạn.
  
   :::image type="content" source="media/CLV-add-required.PNG" alt-text="Thêm dữ liệu bắt buộc cho mô hình CLV":::

1. Lựa chọn **Tiếp theo** và xem xét các thuộc tính cần thiết cho mô hình này.

1. Chọn **Lưu.**

1. Thêm các hoạt động khác hoặc chọn **Tiếp theo**.

### <a name="add-optional-activity-data"></a>Thêm dữ liệu hoạt động tùy chọn

Dữ liệu phản ánh các tương tác chính của khách hàng (như web, dịch vụ khách hàng và bản ghi sự kiện) bổ sung thêm ngữ cảnh vào hồ sơ giao dịch. Dữ liệu hoạt động khách hàng của bạn có càng nhiều mẫu thì càng cải thiện độ chính xác của các dự đoán.

1. Lựa chọn **Thêm dữ liệu** Dưới **Nâng cao thông tin chi tiết về mô hình với dữ liệu hoạt động bổ sung**.

1. Chọn loại hoạt động phù hợp với loại hoạt động của khách hàng mà bạn đang thêm. Nếu hoạt động chưa được thiết lập, hãy chọn **nơi đây** và tạo ra nó.

1. Dưới **Các hoạt động**, nếu các thuộc tính hoạt động được ánh xạ khi hoạt động được tạo, hãy chọn các thuộc tính hoặc thực thể cụ thể mà bạn muốn tính toán tập trung vào. Nếu ánh xạ không xảy ra, hãy chọn **Chỉnh sửa** và lập bản đồ dữ liệu của bạn.

1. Lựa chọn **Tiếp theo** và xem xét các thuộc tính cần thiết cho mô hình này.

1. Chọn **Lưu.**

1. Chọn **Tiếp theo**.

1. [Thêm dữ liệu khách hàng tùy chọn](#add-optional-customer-data) hoặc chọn **Tiếp theo** và đi đến [Đặt lịch cập nhật](#set-update-schedule).

### <a name="add-optional-customer-data"></a>Thêm dữ liệu khách hàng tùy chọn

Chọn từ 18 thuộc tính hồ sơ khách hàng thường được sử dụng để đưa vào làm đầu vào cho mô hình. Các thuộc tính này có thể dẫn đến các kết quả mô hình được cá nhân hóa, phù hợp và dễ hành động hơn cho các trường hợp sử dụng kinh doanh của bạn.

Ví dụ: Contoso Coffee muốn dự đoán giá trị lâu dài của khách hàng để nhắm mục tiêu những khách hàng có giá trị cao với ưu đãi được cá nhân hóa liên quan đến việc ra mắt máy pha cà phê espresso mới của họ. Contoso sử dụng mô hình CLV và thêm tất cả 18 thuộc tính hồ sơ khách hàng để xem yếu tố nào ảnh hưởng đến những khách hàng có giá trị cao nhất của họ. Họ nhận thấy vị trí của khách hàng là yếu tố ảnh hưởng nhiều nhất đến những khách hàng này.
Với thông tin này, họ tổ chức một sự kiện địa phương để ra mắt máy pha cà phê espresso và hợp tác với các nhà cung cấp địa phương để nhận các ưu đãi cá nhân hóa và trải nghiệm đặc biệt tại sự kiện. Nếu không có thông tin này, Contoso có thể đã chỉ gửi email tiếp thị chung chung và bỏ lỡ cơ hội cá nhân hóa cho phân khúc khách hàng giá trị cao tại địa phương này.

1. Lựa chọn **Thêm dữ liệu** Dưới **Tăng cường thông tin chi tiết hơn nữa về mô hình với dữ liệu khách hàng bổ sung**.

1. Vì **Thực thể**, chọn **Khách hàng: CustomerInsights** để chọn hồ sơ khách hàng hợp nhất ánh xạ tới dữ liệu thuộc tính khách hàng. Vì **ID khách hàng**, chọn **System.Customer.CustomerId**.

1. Ánh xạ nhiều trường hơn nếu dữ liệu có sẵn trong hồ sơ khách hàng hợp nhất của bạn.

   :::image type="content" source="media/clv-optional-customer-profile-mapping.png" alt-text="Ví dụ về các trường được ánh xạ cho dữ liệu hồ sơ khách hàng.":::

1. Chọn **Lưu.**

1. Chọn **Tiếp theo**.

### <a name="set-update-schedule"></a>Đặt lịch trình cập nhật

1. Chọn tần suất đào tạo lại mô hình của bạn dựa trên dữ liệu mới nhất. Cài đặt này rất quan trọng để cập nhật độ chính xác của các dự đoán khi dữ liệu mới được nhập vào Thông tin chi tiết về khách hàng. Hầu hết các doanh nghiệp đều có thể đào tạo lại một lần mỗi tháng và có dự đoán chính xác cao.

1. Chọn **Tiếp theo**.

### <a name="review-and-run-the-model-configuration"></a>Xem lại và chạy cấu hình mô hình

Các **Xem lại và chạy** bước hiển thị tóm tắt cấu hình và cung cấp cơ hội thực hiện các thay đổi trước khi bạn tạo dự đoán.

1. Lựa chọn **Chỉnh sửa** về bất kỳ bước nào để xem xét và thực hiện bất kỳ thay đổi nào.

1. Nếu bạn hài lòng với lựa chọn của mình, hãy chọn **Lưu và chạy** để bắt đầu chạy mô hình. Chọn **Xong**. Các **Dự đoán của tôi** tab hiển thị trong khi dự đoán đang được tạo. Quá trình này có thể mất vài giờ mới hoàn thành, tùy thuộc vào lượng dữ liệu dùng trong dự đoán.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Xem kết quả dự đoán

1. Đi đến **Sự thông minh** > **Phỏng đoán**.

1. Bên trong **Dự đoán của tôi**, chọn dự đoán bạn muốn xem.

Có ba phần dữ liệu chính trong trang kết quả.

- **Hiệu suất mô hình đào tạo** : Điểm A, B hoặc C cho biết hiệu suất của dự đoán và có thể giúp bạn đưa ra quyết định sử dụng kết quả được lưu trữ trong thực thể đầu ra.
  
  :::image type="content" source="media/clv-model-score.png" alt-text="Hình ảnh của hộp thông tin điểm mô hình với điểm A.":::

  Thông tin chi tiết về khách hàng đánh giá mô hình AI hoạt động như thế nào trong việc dự đoán những khách hàng có giá trị cao so với mô hình cơ sở.

  Điểm được xác định dựa trên các quy tắc sau:
  - **A** khi mô hình dự đoán khách hàng có giá trị cao chính xác hơn mô hình cơ sở tối thiểu 5%.
  - **B** khi mô hình dự đoán khách hàng có giá trị cao chính xác hơn mô hình cơ sở từ 0-5%.
  - **C** khi mô hình dự đoán khách hàng có giá trị cao ít chính xác hơn mô hình cơ sở.
  
  Lựa chọn [**Tìm hiểu về điểm số này**](#learn-about-the-score) để mở **Đánh giá mô hình** ngăn hiển thị thêm chi tiết về hiệu suất mô hình AI và mô hình cơ sở. Nó sẽ giúp bạn hiểu rõ hơn về các chỉ số hiệu suất của mô hình cơ bản và cách lấy điểm hiệu suất của mô hình cuối cùng. Mô hình cơ sở sử dụng cách tiếp cận không dựa trên AI để tính toán giá trị trọn đời của khách hàng chủ yếu dựa trên các giao dịch mua trước đây của khách hàng.

- **Giá trị của khách hàng theo phân vị** : Khách hàng có giá trị thấp và giá trị cao hiển thị trong biểu đồ. Di chuột qua các thanh trong biểu đồ để xem số lượng khách hàng trong mỗi nhóm và CLV trung bình của nhóm đó. Tùy ý, [tạo phân khúc khách hàng](prediction-based-segment.md) dựa trên dự đoán CLV của họ.
  
   :::image type="content" source="media/CLV-value-percent.png" alt-text="Giá trị của khách hàng theo phân vị đối với mô hình CLV":::

- **Các yếu tố ảnh hưởng nhất**: Các yếu tố khác nhau được xem xét khi tạo dự đoán CLV của bạn dựa trên dữ liệu đầu vào được cung cấp cho mô hình AI. Mỗi yếu tố có tầm quan trọng được tính toán cho các dự đoán tổng hợp mà một mô hình tạo ra. Sử dụng các yếu tố này để giúp xác thực kết quả dự đoán của bạn. Những yếu tố này cũng cung cấp thêm thông tin chi tiết về các yếu tố có ảnh hưởng nhất góp phần vào việc dự đoán CLV trên tất cả các khách hàng của bạn.
  
   :::image type="content" source="media/CLV-influence-factors.png" alt-text="Các yếu tố ảnh hưởng nhiều nhất đến mô hình CLV":::

### <a name="learn-about-the-score"></a>Tìm hiểu về điểm số

Công thức chuẩn được dùng để tính CLV theo mô hình cơ sở:

 _**CLV cho từng khách hàng** = Mua hàng trung bình hàng tháng của khách hàng trong thời hạn khách hàng đang hoạt động * Số tháng trong khoảng thời gian CLV dự đoán * Tỷ lệ giữ chân tổng thể của tất cả khách hàng_

Mô hình AI được so sánh với mô hình cơ sở dựa trên hai chỉ số hiệu suất của mô hình.
  
- **Tỷ lệ thành công khi dự đoán khách hàng có giá trị cao**

  Xem sự khác biệt trong việc dự đoán khách hàng có giá trị cao bằng cách sử dụng mô hình AI so với mô hình cơ sở. Ví dụ: tỷ lệ thành công 84% có nghĩa là trong số tất cả khách hàng có giá trị cao trong dữ liệu đào tạo, mô hình AI có thể dự đoán chính xác 84%. Sau đó, chúng tôi so sánh tỷ lệ thành công này với tỷ lệ thành công của mô hình cơ sở để báo cáo sự thay đổi tương đối. Giá trị này được sử dụng để gán điểm cho mô hình.

- **Chỉ số lỗi**

  Xem hiệu suất tổng thể của mô hình về sai số trong việc dự đoán các giá trị trong tương lai. Chúng tôi sử dụng chỉ số Lỗi trung bình bình phương (RMSE) tổng thể để đánh giá lỗi này. RMSE là một cách tiêu chuẩn để đo lường lỗi dự đoán dữ liệu định lượng của một mô hình. RMSE của mô hình AI được so sánh với RMSE của mô hình cơ sở và báo cáo sự khác biệt tương đối.

Mô hình AI ưu tiên xếp hạng chính xác khách hàng theo giá trị mà họ mang lại cho doanh nghiệp của bạn. Vì vậy, chỉ tỷ lệ thành công khi dự đoán khách hàng có giá trị cao được dùng để tính điểm cuối cùng của mô hình. Chỉ số RMSE nhạy cảm với các trường hợp ngoại lệ. Trong các tình huống mà bạn có một tỷ lệ nhỏ khách hàng có giá trị mua hàng cực cao, chỉ số RMSE tổng thể có thể không cung cấp bức tranh đầy đủ về hiệu suất của mô hình.

[!INCLUDE [footer-include](includes/footer-banner.md)]
