---
title: Phân tích cảm xúc cho phản hồi của khách hàng (xem trước)
description: Tìm hiểu cách sử dụng mô hình phân tích tình cảm trên phản hồi của khách hàng trong Dynamics 365 Customer Insights.
ms.date: 09/14/2022
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: 61ce9fb18efa6152dddb2e31f4fd0366a31ac2c7
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610492"
---
# <a name="analyze-sentiment-in-customer-feedback-preview"></a>Phân tích tình cảm trong phản hồi của khách hàng (xem trước)

Phân tích cảm xúc cho phép bạn tổng hợp tình cảm của khách hàng và xác định các khía cạnh kinh doanh là cơ hội để cải thiện. Tính năng Thông tin chi tiết về khách hàng này giúp bạn hiểu những gì hoạt động tốt và những gì bạn cần giải quyết. Nó có thể giúp bạn thúc đẩy các hành động kinh doanh mang lại trải nghiệm mang lại sự hài lòng và lòng trung thành cao của khách hàng.

## <a name="overview"></a>Tổng quan

Tính năng phân tích tình cảm tạo ra hai thông tin chi tiết có được trên mỗi ID khách hàng. Điểm tình cảm (từ -5 đến 5) và danh sách các khía cạnh kinh doanh có thể áp dụng (lĩnh vực kinh doanh) cùng nhau giúp bạn hiểu rõ hơn về phản hồi của khách hàng.

Phân tích này giúp bạn:
- Xem tổng quan về tình cảm của khách hàng đối với thương hiệu hoặc tổ chức
- Xác định những khách hàng có tâm lý tiêu cực để tập trung vào các chiến dịch và mức độ tương tác của bạn và tối ưu hóa để thu được lợi nhuận cao hơn  
- Xác định các khía cạnh kinh doanh với các vấn đề được khách hàng chỉ ra  
- Phân khúc khách hàng dựa trên cảm tính của họ để chạy các chiến dịch được cá nhân hóa với các nỗ lực bán hàng, tiếp thị và hỗ trợ được nhắm mục tiêu
- Tối ưu hóa hoạt động kinh doanh bằng cách giải quyết các lĩnh vực quan tâm hoặc cơ hội đã được khách hàng đề cập
- Ghi nhận các khía cạnh kinh doanh đang hoạt động tốt và thưởng cho những khách hàng hài lòng thông qua các chương trình khuyến mãi và khách hàng thân thiết

Mô hình cung cấp danh sách các từ đã ảnh hưởng đến quyết định của mô hình trong việc chỉ định một điểm số cảm xúc cụ thể hoặc khía cạnh kinh doanh cho các nhận xét phản hồi.  

Chúng tôi sử dụng hai **Các mô hình Xử lý Ngôn ngữ Tự nhiên (NLP)** : Đầu tiên chỉ định cho mỗi nhận xét phản hồi một điểm tình cảm. Mô hình thứ hai liên kết mỗi phản hồi với tất cả các khía cạnh kinh doanh có thể áp dụng. Các mô hình được đào tạo dựa trên dữ liệu công khai từ các nguồn trên mạng xã hội, bán lẻ, nhà hàng, sản phẩm tiêu dùng và ngành công nghiệp ô tô.
  
Các khía cạnh nghiệp vụ được xác định trước để mô hình liên kết với dữ liệu phản hồi bao gồm:
- Quản lý tài khoản
- Thanh toán
- Hỗ trợ khách hàng
- Nhận hàng tại cửa hàng
- Vận chuyển và lấy kiện hàng
- Đặt hàng trước
- Giá
- Quyền riêng tư và bảo mật
- Khuyến mãi và phần thưởng
- Biên lai và bảo hành
- Đổi trả hàng
- Độ chính xác thực hiện
- Chất lượng trang web/ứng dụng

> [!NOTE]
> Hiện tại, chúng tôi chỉ hỗ trợ phân tích cảm tính trên phản hồi của khách hàng bằng tiếng Anh. Nhiều ngôn ngữ hơn sẽ được hỗ trợ trong tương lai. Nếu phản hồi bằng các ngôn ngữ khác được tải lên, mô hình sẽ vẫn trả về kết quả. Tuy nhiên, những kết quả này sẽ không chính xác.

## <a name="prerequisites"></a>Điều kiện tiên quyết

- Ít nhất [Quyền của cộng tác viên](permissions.md)
- [Thống nhât](data-unification.md) dữ liệu phản hồi văn bản. Chúng tôi thực sự khuyên bạn nên [định cấu hình các thực thể dữ liệu phản hồi của bạn dưới dạng các thực thể hoạt động kiểu ngữ nghĩa](map-entities.md#select-primary-key-and-semantic-type-for-attributes) (Loại phản hồi).
- ID khách hàng hợp nhất (UCID) từ việc hợp nhất dữ liệu để khớp các bản ghi dữ liệu phản hồi văn bản cho một khách hàng cá nhân.
- ID Phản hồi
- Dấu thời gian phản hồi
- Văn bản phản hồi

Thông tin chi tiết về khách hàng có thể xử lý tới 10 triệu bản ghi phản hồi cho một lần chạy mô hình. Mô hình có thể phân tích các bình luận phản hồi lên đến 128 từ. Nếu một bình luận phản hồi dài hơn, bản phân tích chỉ xem xét 128 từ đầu tiên.

> [!NOTE]
> Chỉ một thực thể phản hồi có thể được định cấu hình. Nếu có nhiều thực thể phản hồi, hãy kết hợp chúng trong Power Query trước khi nhập dữ liệu.

## <a name="configure-a-sentiment-analysis"></a>Định cấu hình phân tích tình cảm

1. Đi đến **Sự thông minh** > **Phỏng đoán**.

1. Trên **Tạo ra** tab, chọn **Sử dụng mô hình** trên **Phân tích tâm lý khách hàng (xem trước)** ngói.

1. Chọn **Bắt đầu**.

1. **Tên** phân tích và cung cấp **Tên thực thể đầu ra khía cạnh kinh doanh** và **Tên thực thể đầu ra điểm tình cảm**.

1. Chọn **Tiếp theo**.

1. Lựa chọn **Thêm dữ liệu** vì **Phản hồi của khách hàng**.

1. Chọn loại hoạt động ngữ nghĩa **Nhận xét** chứa dữ liệu phản hồi. Nếu hoạt động chưa được thiết lập, hãy chọn **nơi đây** và tạo ra nó.

   :::image type="content" source="media/sentiment-add-feedback-activities.png" alt-text="Bước cấu hình để lựa chọn các hoạt động phản hồi để phân tích tình cảm.":::

1. Chọn các hoạt động để sử dụng cho phân tích tình cảm này, sau đó chọn **Tiếp theo**.

1. Ánh xạ các thuộc tính trong dữ liệu của bạn với các thuộc tính mô hình. 

1. Chọn **Lưu.**

1. Chọn **Tiếp theo**. Các **Xem lại và chạy** bước hiển thị tóm tắt cấu hình và cung cấp cơ hội thực hiện các thay đổi trước khi bạn tạo phân tích.

1. Lựa chọn **Chỉnh sửa** về bất kỳ bước nào để xem xét và thực hiện bất kỳ thay đổi nào.

1. Nếu bạn hài lòng với lựa chọn của mình, hãy chọn **Lưu và chạy** để bắt đầu chạy mô hình. Chọn **Xong**. Các **Dự đoán của tôi** tab hiển thị trong khi dự đoán đang được tạo. Quá trình này có thể mất vài giờ mới hoàn thành, tùy thuộc vào lượng dữ liệu dùng trong dự đoán.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-analysis-results"></a>Xem kết quả phân tích

1. Đi đến **Sự thông minh** > **Phỏng đoán**.

1. Trong **Dự đoán của tôi**, chọn dự đoán bạn muốn xem.

Có hai tab kết quả.

### <a name="sumary-tab"></a>Tab tóm tắt

Có bốn phần dữ liệu chính trong trang kết quả.

- **Điểm tình cảm trung bình** : Điểm số cảm xúc giúp bạn hiểu được cảm xúc chung của tất cả khách hàng.
  - **Phủ định** (-5> 2)
  - **Trung tính** (-1> 1)
  - **Tích cực** (2> 5)
  
  :::image type="content" source="media/overall-customer-sentiment.png" alt-text="Đại diện trực quan về tình cảm tổng thể của khách hàng.":::

- **Phân bổ khách hàng theo điểm tình cảm** : Khách hàng được phân loại thành các nhóm tiêu cực, trung lập và tích cực dựa trên điểm số cảm xúc của họ. Di chuột qua các thanh trong biểu đồ để xem số lượng khách hàng và điểm tình cảm trung bình trong mỗi nhóm. Dữ liệu này có thể giúp bạn [tạo phân khúc khách hàng](prediction-based-segment.md) dựa trên điểm tình cảm của họ.  

  :::image type="content" source="media/distribution-customer-sentiment.png" alt-text="Biểu đồ thanh thể hiện tình cảm của khách hàng trên ba nhóm tình cảm.":::

- **Điểm tình cảm trung bình theo thời gian** : Tâm lý khách hàng có thể thay đổi theo thời gian. Chúng tôi cung cấp các xu hướng về tình cảm của khách hàng trong phạm vi thời gian của dữ liệu của bạn. Chế độ xem này giúp bạn đánh giá tác động của các chương trình khuyến mãi theo mùa, ra mắt sản phẩm hoặc các biện pháp can thiệp có giới hạn thời gian khác đối với tình cảm của khách hàng. Xem biểu đồ bằng cách chọn năm quan tâm từ menu thả xuống.

  :::image type="content" source="media/sentiment-score-over-time.png" alt-text="Biểu đồ lịch sử với điểm tình cảm theo thời gian được biểu thị dưới dạng một đường.":::

- **Tình cảm trên các khía cạnh kinh doanh** : Tâm lý trung bình trên các khía cạnh kinh doanh giúp bạn đánh giá khía cạnh nào của doanh nghiệp bạn đã làm hài lòng khách hàng hoặc cần được quan tâm nhiều hơn. Các bản ghi phản hồi không phù hợp với bất kỳ khía cạnh kinh doanh được hỗ trợ nào được phân loại theo **Khác**. Sắp xếp dữ liệu bằng cách chọn bất kỳ cột nào.

  :::image type="content" source="media/sentiment-across-business-aspects.png" alt-text="Danh sách các khía cạnh kinh doanh với giá trị tình cảm liên quan và số lượng khách hàng đề cập đến nó.":::

  Chọn tên của một khía cạnh kinh doanh để xem cách một khía cạnh kinh doanh được xác định bởi mô hình:

  - **Những từ có ảnh hưởng** : Những từ hàng đầu ảnh hưởng đến việc xác định khía cạnh kinh doanh của mô hình AI trong phản hồi của khách hàng.
    **Hiển thị các từ xúc phạm** : Cho phép bạn đưa các từ xúc phạm vào danh sách từ dữ liệu phản hồi ban đầu của khách hàng. Theo mặc định, nó bị tắt.  Mặt nạ từ xúc phạm được hỗ trợ bởi một mô hình AI và có thể không phát hiện tất cả các từ xúc phạm. Nếu bạn phát hiện một từ xúc phạm không được lọc như mong đợi, hãy cho chúng tôi biết.

    :::image type="content" source="media/offensive-words-sentiment.png" alt-text="Danh sách các từ có ảnh hưởng với nút chuyển đổi để hiển thị hoặc ẩn các từ xúc phạm.":::

  - **Phản hồi mẫu** : Bản ghi phản hồi thực tế trong dữ liệu của bạn. Các từ được mã hóa màu tùy theo ảnh hưởng của chúng đối với việc xác định một khía cạnh kinh doanh.

### <a name="influential-words-analysis-tab"></a>Tab phân tích các từ có ảnh hưởng

Có ba phần thông tin bổ sung giải thích cách hoạt động của mô hình tình cảm.
  
- **Những từ hàng đầu góp phần tạo nên tình cảm tích cực** : Những từ hàng đầu ảnh hưởng đến việc xác định tình cảm tích cực của mô hình AI trong phản hồi của khách hàng.  

- **Những từ hàng đầu góp phần vào tình cảm tiêu cực** : Các từ hàng đầu ảnh hưởng đến việc xác định cảm xúc tiêu cực của mô hình AI trong phản hồi của khách hàng.

- **Phản hồi mẫu** : Các bản ghi phản hồi thực tế, một bản ghi lại cảm xúc tiêu cực và một bản ghi lại tình cảm tích cực. Các từ trong hồ sơ phản hồi được đánh dấu tùy theo đóng góp của chúng vào điểm số cảm xúc được chỉ định. Những từ đóng góp vào điểm tình cảm tích cực được đánh dấu bằng màu xanh lá cây. Các từ góp phần vào điểm tiêu cực được tô màu đỏ.
   Lựa chọn **Xem thêm** để tải thêm các mẫu phản hồi.
  
   :::image type="content" source="media/sentiment-feedback-samples.png" alt-text="Ví dụ về phân tích tình cảm trên phản hồi của khách hàng.":::

**Hiển thị các từ xúc phạm** : Cho phép bạn đưa các từ xúc phạm vào danh sách từ dữ liệu phản hồi ban đầu của khách hàng. Theo mặc định, nó bị tắt.  Mặt nạ từ xúc phạm được hỗ trợ bởi một mô hình AI và có thể không phát hiện tất cả các từ xúc phạm. Nếu bạn phát hiện một từ xúc phạm không được lọc như mong đợi, hãy cho chúng tôi biết.

## <a name="act-on-analysis-results"></a>Hành động dựa trên kết quả phân tích

Để tạo các phân khúc khách hàng mới từ kết quả phân tích tình cảm, hãy chọn **Tạo phân đoạn** ở đầu trang kết quả mô hình.

## <a name="potential-bias"></a>Sự thiên vị tiềm ẩn

Như với bất kỳ tính năng nào sử dụng trí thông minh nhân tạo dự đoán, có thể có sự sai lệch tiềm ẩn trong dữ liệu bạn sử dụng để dự đoán tâm lý khách hàng. Ví dụ: nếu bạn chỉ thu thập phản hồi kỹ thuật số, bạn có thể bỏ lỡ phản hồi từ những khách hàng chủ yếu giao dịch trực tiếp với bạn, điều này ảnh hưởng đến kết quả đầu ra của tính năng.

Vì tính năng này sử dụng các phương tiện tự động để đánh giá dữ liệu và đưa ra dự đoán dựa trên dữ liệu đó, do đó, tính năng này có khả năng được sử dụng như một phương pháp lập hồ sơ, vì thuật ngữ đó được xác định bởi Quy định chung về bảo vệ dữ liệu ("GDPR"). Việc bạn sử dụng tính năng này để xử lý dữ liệu có thể tuân theo GDPR hoặc các luật hoặc quy định khác. Bạn có trách nhiệm đảm bảo rằng việc sử dụng Dynamics 365 Customer Insights, bao gồm cả phân tích tình cảm, tuân thủ tất cả các luật và quy định hiện hành, bao gồm các luật liên quan đến quyền riêng tư, dữ liệu cá nhân, dữ liệu sinh trắc học, bảo vệ dữ liệu và bảo mật thông tin liên lạc.

[!INCLUDE [footer-include](includes/footer-banner.md)]

