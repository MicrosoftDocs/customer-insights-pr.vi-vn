---
title: Phân tích cảm xúc cho phản hồi của khách hàng
description: Tìm hiểu cách sử dụng mô hình phân tích tình cảm trên phản hồi của khách hàng trong Dynamics 365 Customer Insights.
ms.date: 12/23/2021
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: b06613b00a512a31479f9d30d539a010e17d33ba
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 02/16/2022
ms.locfileid: "8231491"
---
# <a name="analyze-sentiment-in-customer-feedback-preview"></a>Phân tích tình cảm trong phản hồi của khách hàng (Xem trước)

Ngày nay, khách hàng mong đợi những sản phẩm, dịch vụ và trải nghiệm chất lượng cao. Đặc biệt là những khách hàng đã chia sẻ phản hồi của họ. Rất khó khăn cho các tổ chức khi phân tích khối lượng dữ liệu ngày càng tăng mà không làm giảm độ chính xác và chi phí lao động cao hơn. Dynamics 365 Customer Insights đưa ra mô hình phân tích tình cảm cho phản hồi của khách hàng cho phép các tổ chức phân tích dữ liệu của họ chính xác hơn và với chi phí thấp hơn.

Phân tích tình cảm cho phép bạn tổng hợp tình cảm của khách hàng và xác định các khía cạnh kinh doanh là cơ hội để cải thiện. Tính năng Thông tin chi tiết về khách hàng này giúp bạn hiểu những gì hoạt động tốt và những gì bạn cần giải quyết. Tập trung vào các lĩnh vực kinh doanh có tác động và có liên quan nhất để cải thiện trải nghiệm cho khách hàng của bạn. Cuối cùng, nó có thể giúp bạn thúc đẩy các hành động kinh doanh mang lại trải nghiệm mang lại sự hài lòng và lòng trung thành cao của khách hàng.

## <a name="overview"></a>Tổng quan

Tính năng phân tích tình cảm tạo ra hai thông tin chi tiết có được trên mỗi ID khách hàng. Điểm tình cảm (từ -5 đến 5) và danh sách các khía cạnh kinh doanh áp dụng (lĩnh vực kinh doanh) cùng nhau giúp bạn hiểu rõ hơn về phản hồi của khách hàng. 

Thông tin này có thể giúp bạn đạt được các kết quả sau: 
- Xem tổng quan về tình cảm của khách hàng đối với thương hiệu hoặc tổ chức
- Xác định những khách hàng có tâm lý tiêu cực để tập trung vào các chiến dịch và mức độ tương tác của bạn và tối ưu hóa để thu được lợi nhuận cao hơn  
- Xác định các khía cạnh kinh doanh với các vấn đề được khách hàng chỉ ra  
- Phân khúc khách hàng dựa trên cảm tính của họ để chạy các chiến dịch được cá nhân hóa với các nỗ lực bán hàng, tiếp thị và hỗ trợ được nhắm mục tiêu
- Tối ưu hóa hoạt động kinh doanh bằng cách giải quyết các lĩnh vực quan tâm hoặc cơ hội đã được khách hàng đề cập
- Ghi nhận các khía cạnh kinh doanh đang hoạt động tốt và thưởng cho những khách hàng hài lòng thông qua các chương trình khuyến mãi và khách hàng thân thiết

Để đảm bảo rằng bạn có thể tin tưởng vào kết quả của các mô hình, chúng tôi cung cấp thông tin minh bạch về cách các mô hình đưa ra quyết định. Bạn sẽ nhận được danh sách các từ ảnh hưởng đến quyết định của các mô hình trong việc chỉ định một điểm số cảm xúc cụ thể hoặc khía cạnh kinh doanh cho các nhận xét phản hồi.  

Chúng tôi sử dụng hai **Các mô hình Xử lý Ngôn ngữ Tự nhiên (NLP)** : Đầu tiên chỉ định cho mỗi nhận xét phản hồi một điểm tình cảm. Mô hình thứ hai liên kết mỗi phản hồi với tất cả các khía cạnh kinh doanh có thể áp dụng. Các mô hình được đào tạo dựa trên dữ liệu công khai từ các nguồn trên mạng xã hội, bán lẻ, nhà hàng, sản phẩm tiêu dùng và ngành công nghiệp ô tô.    
  
Các khía cạnh kinh doanh được xác định trước để mô hình liên kết với dữ liệu phản hồi bao gồm:
-   Quản lý tài khoản
-   Thanh toán
-   Hỗ trợ khách hàng
-   Nhận hàng tại cửa hàng
-   Vận chuyển và lấy kiện hàng
-   Đặt hàng trước
-   Giá
-   Quyền riêng tư và bảo mật
-   Khuyến mãi và phần thưởng
-   Biên lai và bảo hành
-   Đổi trả hàng
-   Độ chính xác thực hiện
-   Chất lượng trang web/ứng dụng

> [!NOTE]
> Hiện tại, chúng tôi chỉ hỗ trợ phân tích cảm tính trên phản hồi của khách hàng bằng tiếng Anh. Nhiều ngôn ngữ hơn sẽ được hỗ trợ trong tương lai. Nếu phản hồi bằng các ngôn ngữ khác được tải lên, mô hình sẽ vẫn trả về kết quả. Tuy nhiên, những kết quả này sẽ không chính xác. 

## <a name="prerequisites"></a>Điều kiện tiên quyết

Phân tích tình cảm dựa trên dữ liệu phản hồi bằng văn bản đã trải qua [quá trình hợp nhất dữ liệu](data-unification.md). Chúng tôi thực sự khuyên bạn nên [định cấu hình các thực thể dữ liệu phản hồi của bạn dưới dạng các thực thể hoạt động kiểu ngữ nghĩa](map-entities.md#select-primary-key-and-semantic-type-for-attributes) (Loại phản hồi) trước. 

Để định cấu hình mô hình phân tích tình cảm, bạn cần ít nhất [Quyền của cộng tác viên](permissions.md).

Thông tin chi tiết về khách hàng có thể xử lý tới 10 triệu bản ghi phản hồi cho một lần chạy mô hình. Mô hình có thể phân tích các bình luận phản hồi lên đến 128 từ. Nếu một bình luận phản hồi dài hơn, bản phân tích chỉ xem xét 128 từ đầu tiên.

### <a name="data-requirements"></a>Các yêu cầu về dữ liệu
  
Các thuộc tính dữ liệu sau là bắt buộc:
- ID khách hàng hợp nhất (UCID) để khớp các bản ghi dữ liệu phản hồi văn bản với một khách hàng cá nhân. ID này là kết quả của [quá trình hợp nhất dữ liệu](data-unification.md).
- ID Phản hồi
- Dấu thời gian phản hồi
- Văn bản phản hồi   

> [!TIP]
> Phân tích cảm xúc yêu cầu phản hồi bằng văn bản của khách hàng của bạn. Hiện chỉ có thể định cấu hình một thực thể phản hồi. Nếu có nhiều thực thể phản hồi, bạn có thể kết hợp chúng trong Power Query trước khi quá trình nhập dữ liệu bắt đầu.

## <a name="configure-a-sentiment-analysis"></a>Định cấu hình phân tích tình cảm 

1. Trong Customer Insights, chuyển đến phần **Thông tin** > **Dự đoán**.

1. Trên **Phân tích tâm lý khách hàng** gạch, chọn **Sử dụng mô hình**.

1. Bên trong **Phân tích tâm lý khách hàng (xem trước)** ngăn, chọn **Bắt đầu**.

1. Bên trong **Tên mô hình** bước, cung cấp một **Tên** cho phân tích của bạn. 

1. Cung cấp **Tên thực thể đầu ra khía cạnh kinh doanh** và **Tên thực thể đầu ra điểm tình cảm**, sau đó chọn **Tiếp theo**.

1. Bên trong **Dữ liệu bắt buộc** bước, chọn **Thêm dữ liệu**.

   :::image type="content" source="media/sentiment-add-data.png" alt-text="Thêm luồng dữ liệu trong mô hình phân tích tình cảm.":::

1. Bên trong **Thêm dữ liệu** ngăn, chọn loại ngữ nghĩa **Nhận xét** khỏi danh sách.

   :::image type="content" source="media/sentiment-add-feedback-activities.png" alt-text="Bước cấu hình để lựa chọn các hoạt động phản hồi để phân tích tình cảm.":::

1. Chọn các hoạt động để sử dụng cho phân tích tình cảm này, sau đó chọn **Tiếp theo**.
 
1. Ánh xạ các thuộc tính trong dữ liệu của bạn với các thuộc tính mô hình. Lựa chọn **Tiết kiệm** để áp dụng các lựa chọn của bạn. 

1. Bạn thấy trạng thái của ánh xạ dữ liệu. Chọn **Tiếp** để tiếp tục. 

1. Bên trong **Xem lại chi tiết mô hình của bạn** bước, xác thực cấu hình phân tích tình cảm của bạn. Bạn có thể quay lại bất kỳ phần nào của cấu hình dự đoán. Lựa chọn **Lưu và chạy** để bắt đầu phân tích. 

   :::image type="content" source="media/sentiment-model-review-config.png" alt-text="Xem lại bước cho mô hình tình cảm hiển thị tất cả các mục đã định cấu hình.":::

1. Lựa chọn **Xong** để rời khỏi trải nghiệm cấu hình. Quá trình này có thể mất vài giờ để hoàn thành tùy thuộc vào lượng dữ liệu được sử dụng. 

## <a name="review-analysis-status"></a>Xem xét trạng thái phân tích

1.  Đi đến **Thông tin** > **Dự đoán** và chọn tab **Dự đoán của tôi**.
2.  Chọn dự đoán bạn muốn xem lại.
- **Tên dự đoán**: Tên của dự đoán được cung cấp khi tạo.
- **dự đoán loại** : Loại mô hình được sử dụng cho dự đoán.
- **Thực thể đầu ra**: Tên của thực thể để lưu trữ đầu ra của dự đoán. Chuyển đến **Dữ liệu** > **Thực thể** để tìm thực thể có tên này.
- **Trường dự đoán**: Trường này chỉ được điền cho một số loại dự đoán và không được sử dụng trong dự đoán giá trị trọn đời của khách hàng.
- **Trạng thái**: Trạng thái chạy dự đoán.
  - **Đã xếp hàng**: Dự đoán đang đợi các quy trình khác hoàn tất.
  - **Làm mới**: Dự đoán hiện đang chạy để tạo ra kết quả sẽ chuyển vào thực thể đầu ra.
  - **Thất bại**: Chạy dự đoán không thành công. Xem lại nhật ký để biết thêm chi tiết.
  - **Đã thành công**: Dự đoán đã thành công. Chọn Dạng xem dưới dấu ba chấm dọc để xem lại kết quả dự đoán.
- **Đã chỉnh sửa**: Ngày thay đổi cấu hình của dự đoán.
- **Làm mới lần cuối** : Ngày dự đoán đã làm mới kết quả trong thực thể đầu ra.

## <a name="manage-sentiment-analysis"></a>Quản lý phân tích tình cảm

Bạn có thể tối ưu hóa, khắc phục sự cố, làm mới hoặc xóa dự đoán. Hãy xem lại báo cáo khả năng sử dụng dữ liệu đầu vào để tìm hiểu cách giúp dự đoán nhanh hơn và đáng tin cậy hơn. Để biết thêm thông tin, hãy xem phần [Quản lý dự đoán](manage-predictions.md).

## <a name="review-analysis-results"></a>Xem xét kết quả phân tích
 
1. Đi đến **Thông tin** > **Dự đoán** và chọn tab **Dự đoán của tôi**. 
1. Chọn tên của dự đoán mà bạn muốn xem xét kết quả. Trong trường hợp này, hãy chọn phân tích tình cảm mà bạn muốn xem xét. 

### <a name="summary-tab"></a>Tab Tóm tắt

Có bốn phần dữ liệu chính trong trang kết quả. 

- **Điểm tình cảm trung bình** : Giúp bạn hiểu được cảm xúc chung của tất cả khách hàng. Điểm tình cảm được nhóm thành ba loại: 
  1.    Tiêu cực (-5> 2)
  2.    Trung tính (-1> 1)
  3.    Tích cực (2> 5) 
  
  :::image type="content" source="media/overall-customer-sentiment.png" alt-text="Đại diện trực quan về tình cảm tổng thể của khách hàng.":::

- **Phân bổ khách hàng theo điểm tình cảm** : Khách hàng được phân loại thành các nhóm tiêu cực, trung tính và tích cực dựa trên điểm số cảm xúc của họ. Di chuột qua các thanh trong biểu đồ để xem số lượng khách hàng và điểm tình cảm trung bình trong mỗi nhóm. Dữ liệu này có thể giúp bạn [tạo phân khúc khách hàng](segments.md) dựa trên điểm tình cảm của họ.  

  :::image type="content" source="media/distribution-customer-sentiment.png" alt-text="Biểu đồ thanh thể hiện tình cảm của khách hàng trên ba nhóm tình cảm.":::

- **Điểm tình cảm trung bình theo thời gian** : Tâm lý khách hàng có thể thay đổi theo thời gian. Chúng tôi cung cấp các xu hướng về tình cảm của khách hàng trong phạm vi thời gian của dữ liệu của bạn. Chế độ xem này có thể giúp bạn đánh giá tác động của các chương trình khuyến mại theo mùa, ra mắt sản phẩm hoặc các biện pháp can thiệp có giới hạn thời gian khác đối với tình cảm của khách hàng. Xem biểu đồ bằng cách chọn năm quan tâm từ menu thả xuống. 

  :::image type="content" source="media/sentiment-score-over-time.png" alt-text="Biểu đồ lịch sử với điểm tình cảm theo thời gian được biểu thị dưới dạng một đường.":::
 
- **Tình cảm trên các khía cạnh kinh doanh** : Bảng này liệt kê tình cảm trung bình trên các khía cạnh kinh doanh. Nó có thể giúp bạn đánh giá khía cạnh nào của doanh nghiệp bạn đã làm hài lòng khách hàng hoặc khía cạnh nào cần được quan tâm nhiều hơn. Các bản ghi phản hồi không phù hợp với bất kỳ khía cạnh kinh doanh được hỗ trợ nào được phân loại theo **Khác**. Bảng được sắp xếp theo thứ tự bảng chữ cái theo mặc định. Bạn có thể sửa đổi cách sắp xếp bằng cách chọn tiêu đề bảng.

  :::image type="content" source="media/sentiment-across-business-aspects.png" alt-text="Danh sách các khía cạnh kinh doanh với giá trị tình cảm liên quan và số lượng khách hàng đề cập đến nó.":::
 
  Chọn tên của một khía cạnh kinh doanh để xem thông tin bổ sung về cách một khía cạnh kinh doanh được xác định bởi mô hình. Có hai phần trong ngăn này: 

  - **Những từ có ảnh hưởng** : Hiển thị các từ hàng đầu ảnh hưởng đến việc xác định khía cạnh kinh doanh của mô hình AI trong phản hồi của khách hàng. 
    **Hiển thị các từ xúc phạm** : Cho phép bạn đưa các từ xúc phạm vào danh sách từ dữ liệu phản hồi ban đầu của khách hàng. Theo mặc định, nó bị tắt.  Mặt nạ từ xúc phạm được hỗ trợ bởi một mô hình AI và có thể không phát hiện tất cả các từ xúc phạm. Chúng tôi tiếp tục lặp lại và đào tạo bộ phân loại để có hiệu suất tối ưu. Nếu bạn phát hiện một từ xúc phạm không được lọc như mong đợi, hãy cho chúng tôi biết. 
    
    :::image type="content" source="media/offensive-words-sentiment.png" alt-text="Danh sách các từ có ảnh hưởng với nút chuyển đổi để hiển thị hoặc ẩn các từ xúc phạm.":::
 
  - **Phản hồi mẫu** : Hiển thị các bản ghi phản hồi thực tế trong dữ liệu của bạn. Các từ được mã hóa màu tùy theo ảnh hưởng của chúng đối với việc xác định một khía cạnh kinh doanh. 


### <a name="influential-words-analysis-tab"></a>Tab phân tích các từ có ảnh hưởng

Có ba phần thông tin bổ sung giải thích cách hoạt động của mô hình tình cảm.
  
1. **Những từ hàng đầu góp phần tạo nên tình cảm tích cực** : Hiển thị các từ hàng đầu ảnh hưởng đến việc xác định cảm xúc tích cực trong phản hồi của khách hàng trong mô hình AI.  
2. **Những từ hàng đầu góp phần vào tình cảm tiêu cực** : Hiển thị các từ hàng đầu ảnh hưởng đến việc xác định cảm xúc tiêu cực của mô hình AI trong phản hồi của khách hàng.  
3. **Phản hồi mẫu** : Hiển thị các bản ghi phản hồi thực tế, một bản ghi có cảm xúc tiêu cực và một bản ghi có tình cảm tích cực. Các từ trong hồ sơ phản hồi được đánh dấu tùy theo đóng góp của chúng vào điểm số cảm xúc được chỉ định. Những từ đóng góp vào điểm tình cảm tích cực được đánh dấu bằng màu xanh lá cây. Các từ góp phần vào điểm tiêu cực được tô màu đỏ.
   Lựa chọn **Xem thêm** để tải thêm các mẫu phản hồi cung cấp thêm thông tin và bối cảnh về cách hoạt động của mô hình cảm tính.
   
   :::image type="content" source="media/sentiment-feedback-samples.png" alt-text="Ví dụ về phân tích tình cảm trên phản hồi của khách hàng.":::
 
**Hiển thị các từ xúc phạm** : Cho phép bạn đưa các từ xúc phạm vào danh sách từ dữ liệu phản hồi ban đầu của khách hàng. Theo mặc định, nó bị tắt.  Mặt nạ từ xúc phạm được hỗ trợ bởi một mô hình AI và có thể không phát hiện tất cả các từ xúc phạm. Chúng tôi tiếp tục lặp lại và đào tạo bộ phân loại để có hiệu suất tối ưu. Nếu bạn phát hiện một từ xúc phạm không được lọc như mong đợi, hãy cho chúng tôi biết. 

## <a name="act-on-analysis-results"></a>Hành động dựa trên kết quả phân tích

Bạn có thể dễ dàng bắt đầu tạo các phân khúc khách hàng mới từ trang kết quả phân tích tình cảm bằng cách chọn **Tạo phân đoạn** ở đầu trang kết quả mô hình.

:::image type="content" source="media/create-segment-model.png" alt-text="Thanh lệnh với các tùy chọn trên các mô hình dự đoán.":::
 
## <a name="potential-bias"></a>Sự thiên vị tiềm ẩn

Như với bất kỳ tính năng nào sử dụng trí thông minh nhân tạo dự đoán, bạn nên biết về sự thiên vị tiềm ẩn trong dữ liệu bạn sử dụng để dự đoán tâm lý khách hàng. Ví dụ: nếu bạn chỉ thu thập phản hồi bằng kỹ thuật số, bạn có thể bỏ lỡ phản hồi từ những khách hàng chủ yếu giao dịch trực tiếp với bạn, điều này có thể ảnh hưởng đến kết quả đầu ra của tính năng.

Vì tính năng này sử dụng các phương tiện tự động để đánh giá dữ liệu và đưa ra dự đoán dựa trên dữ liệu đó, do đó, tính năng này có khả năng được sử dụng như một phương pháp lập hồ sơ, vì thuật ngữ đó được xác định bởi Quy định chung về bảo vệ dữ liệu ("GDPR"). Việc bạn sử dụng tính năng này để xử lý dữ liệu có thể tuân theo GDPR hoặc các luật hoặc quy định khác. Bạn có trách nhiệm đảm bảo rằng việc sử dụng Dynamics 365 Customer Insights, bao gồm cả phân tích tình cảm, tuân thủ tất cả các luật và quy định hiện hành, bao gồm các luật liên quan đến quyền riêng tư, dữ liệu cá nhân, dữ liệu sinh trắc học, bảo vệ dữ liệu và bảo mật thông tin liên lạc.

[!INCLUDE[footer-include](../includes/footer-banner.md)]

