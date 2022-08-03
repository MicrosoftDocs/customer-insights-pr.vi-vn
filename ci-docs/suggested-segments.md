---
title: Các phân đoạn được đề xuất dựa trên các thước đo (xem trước)
description: Hãy để máy học giúp bạn tìm các phân khúc mới và thú vị dựa trên các thuộc tính của khách hàng.
ms.date: 10/15/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
searchScope:
- ci-segment-suggestions
- customerInsights
ms.openlocfilehash: e3f504827029afa12c65ec6f065a62606aaa823f
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170983"
---
# <a name="suggested-segments-based-on-measures-preview"></a>Các phân đoạn được đề xuất dựa trên các thước đo (xem trước)

Khám phá các phân khúc khách hàng thú vị của bạn với sự trợ giúp của mô hình AI. Tính năng được hỗ trợ bởi máy học này đề xuất các phân khúc dựa trên các phép đo hoặc thuộc tính khách hàng. Nó có thể giúp cải thiện các Chỉ số Hiệu suất Chính (KPI) của bạn hoặc hiểu rõ hơn về ảnh hưởng của các thuộc tính trong ngữ cảnh của các thuộc tính khác.

> [!NOTE]
> Tính năng phân đoạn được đề xuất sử dụng các phương tiện tự động để đánh giá dữ liệu và đưa ra dự đoán dựa trên dữ liệu đó. Do đó, nó có khả năng được sử dụng như một phương pháp lập hồ sơ, vì thuật ngữ đó được xác định bởi Quy định chung về bảo vệ dữ liệu ("GDPR"). Việc bạn sử dụng tính năng này để xử lý dữ liệu có thể tuân theo GDPR hoặc các luật hoặc quy định khác. Bạn có trách nhiệm đảm bảo rằng việc sử dụng Dynamics 365 Customer Insights, bao gồm tính năng này, tuân thủ tất cả các luật và quy định hiện hành, bao gồm các luật liên quan đến quyền riêng tư, dữ liệu cá nhân, dữ liệu sinh trắc học, bảo vệ dữ liệu và bảo mật thông tin liên lạc.

:::image type="content" source="media/suggested-segments.png" alt-text="Trang phân khúc được gợi ý hiển thị thông tin chi tiết của gợi ý trong ngăn bên.":::

## <a name="suggested-segments-to-improve-your-kpis"></a>Các phân khúc được đề xuất để cải thiện KPI của bạn

Nếu bạn dùng [các biện pháp được tạo ra](measures.md) để giúp theo dõi KPI của bạn, tạo các phân đoạn để xem các ảnh hưởng đến KPI. Bạn có thể sử dụng thông tin này để chạy một chiến dịch được nhắm mục tiêu cao.

Ví dụ: bạn theo dõi một số đo được gọi là *TotalSpendPerCustomer*. Là một doanh nghiệp, bạn muốn thấy con số này tăng lên. Chọn thước đo làm thuộc tính chính, chọn các thuộc tính mà bạn muốn đánh giá mức độ ảnh hưởng. Giả sử đó là *cấp thành viên*, *thời hạn thành viên* và *nghề nghiệp*. Sau đó, Customer Insights có thể đề xuất một phân đoạn cho bạn biết ai là người có ảnh hưởng lớn nhất của biện pháp đó. Ví dụ: *Kế toán* là thành viên *Vàng* và những người đã làm việc với doanh nghiệp của bạn trong *ít nhất 5 năm* là người có ảnh hưởng lớn nhất đến *TotalSpendPerCustomer*. Bạn sẽ nhận được quy mô phân đoạn ước tính cho mọi đề xuất. Bạn có thể sử dụng thông tin này để tạo chiến dịch cho các đối tượng được nhắm mục tiêu.

## <a name="understand-what-influences-a-customer-attribute"></a>Hiểu điều gì ảnh hưởng đến thuộc tính khách hàng

Bạn có thể chọn thuộc tính khách hàng thay vì một số đo làm thuộc tính chính. Dựa trên lựa chọn của bạn về các thuộc tính ảnh hưởng, mô hình AI tạo ra một loạt các đề xuất cho thấy những thuộc tính đã chọn ảnh hưởng như thế nào đến thuộc tính chính.

Ví dụ: bạn chọn *Thành viên thưởng (Có/Không)* là thuộc tính chính. *Thâm niên*, *Nghề nghiệp* và *Số lượng phiếu hỗ trợ* được đặt làm các thuộc tính ảnh hưởng khác. Mô hình AI có thể đề xuất các phân đoạn cho thấy hầu hết các chuyên gia CNTT có thâm niên trên 2 năm là thành viên thưởng. Một gợi ý khác có thể làm nổi bật rằng kế toán có thâm niên trên 1 năm và ít hơn 3 phiếu hỗ trợ là thành viên thưởng.

## <a name="artificial-intelligence-usage"></a>Sử dụng trí tuệ nhân tạo

Thuật toán cây quyết định đề xuất các phân đoạn thú vị dựa trên thuộc tính chính và thuộc tính ảnh hưởng. Các đề xuất dựa trên các quy tắc hoặc mẫu đã được thuật toán AI chọn ra. Chỉ các phân đoạn khác biệt đáng kể so với quần thể trung bình mới được hiển thị dưới dạng đề xuất. So sánh với quần thể trung bình dựa trên thước đo đã chọn hoặc thuộc tính chính.

### <a name="responsible-ai"></a>AI có trách nhiệm

Với các phân đoạn được đề xuất, bạn chọn các thuộc tính để tạo phân đoạn mới và xử lý dữ liệu bạn chọn. Khi chọn các thuộc tính, bao gồm các thuộc tính nhạy cảm như chủng tộc, khuynh hướng tình dục hoặc giới tính, bạn phải đảm bảo rằng bạn có thể và cần xử lý dữ liệu đó. Bạn có trách nhiệm tuân thủ mọi luật áp dụng cho tổ chức của mình và tuân thủ các nguyên tắc cũng như chính sách quyền riêng tư của tổ chức bạn.

### <a name="different-results-for-primary-attributes-with-categorical-and-numeric-values"></a>Các kết quả khác nhau cho thuộc tính chính có giá trị phân loại và số

Đề xuất phân đoạn sẽ khác nếu bạn chọn thuộc tính số hoặc thuộc tính phân loại làm thuộc tính chính. Giá trị trong thuộc tính phân loại chứa hai hoặc nhiều phân loại hoặc loại. Thuộc tính số chứa dữ liệu định lượng và có giá trị đo lường liên quan đến nó.

Với thuộc tính số như *thu nhập hàng năm* hoặc *thời hạn thành viên* là thuộc tính chính, hệ thống đề xuất các phân đoạn có giá trị trung bình cao hơn hoặc thấp hơn thuộc tính số khi so sánh với tất cả khách hàng.

Một thuộc tính phân loại như *sự hài lòng của khách hàng* dưới dạng thuộc tính chính dẫn đến các phân đoạn được đề xuất có tỷ lệ phần trăm khách hàng thuộc một danh mục cụ thể cao hơn hoặc thấp hơn khi so sánh với phần trăm của tất cả khách hàng thuộc cùng một danh mục đó. Ví dụ: *sự hài lòng của khách hàng* được chọn làm thuộc tính chính và bao gồm ba danh mục (*Thấp*, *Trung bình* và *Cao*). Đối với mỗi danh mục, các phân khúc sẽ được đề xuất có tỷ lệ khách hàng thuộc danh mục đó cao hơn hoặc thấp hơn so với tỷ lệ của tất cả khách hàng trong cùng danh mục. Nếu 22% trong số tất cả khách hàng có mức độ hài lòng *Cao* thì chỉ những phân khúc có tỷ lệ khách hàng với mức độ hài lòng *Cao* cao hơn hoặc thấp hơn 22% mới được gợi ý cho danh mục đó. Tương tự, các phân đoạn sẽ được đề xuất cho từng danh mục khác (*Thấp* và *Trung bình*) nếu chúng có ý nghĩa thống kê.

> [!NOTE]
> Hiện tại, chúng tôi chỉ hỗ trợ các thuộc tính phân loại chính có tối đa 10 danh mục. Nếu bạn muốn xem các đề xuất phân đoạn dựa trên thuộc tính chính có hơn 10 danh mục, chúng tôi khuyên bạn nên nhóm một số danh mục để giảm số lượng danh mục xuống còn 10 danh mục trở xuống. Giới hạn này chỉ áp dụng cho các thuộc tính chính. Để ảnh hưởng đến các thuộc tính phân loại, chúng tôi hiện hỗ trợ tối đa 100 danh mục.

## <a name="generate-suggested-segments"></a>Tạo các phân đoạn được đề xuất

1. Đi đến **Phân đoạn** và chọn **Gợi ý (xem trước)** chuyển hướng.

1. Lựa chọn **Tìm đề xuất mới** và lựa chọn **Cải thiện thước đo / chỉ số**. Lựa chọn **Bắt đầu**.

   :::image type="content" source="media/suggested-segments-measure.png" alt-text="Chọn biện pháp cải thiện trên các phân đoạn được đề xuất.":::

1. Chọn thuộc tính hoặc đo lường khách hàng làm thuộc tính chính và chọn **Tiếp theo**.

1. Chọn các thuộc tính ảnh hưởng và chọn **Chạy**.

   > [!TIP]
   > Việc chọn nhiều thuộc tính ảnh hưởng giúp cải thiện cơ hội đánh giá cách chúng ảnh hưởng đến thuộc tính chính. Không bao gồm các thuộc tính không có ảnh hưởng đến thuộc tính chính. Ví dụ: nếu tất cả khách hàng của bạn đến từ một quốc gia cụ thể, đừng bao gồm thuộc tính *quốc gia* vì nó sẽ không có bất kỳ tác động nào đến đầu ra.

Tùy thuộc vào số lượng hồ sơ khách hàng và các thuộc tính đã chọn, có thể mất vài phút để xử lý các thuộc tính đã chọn.

## <a name="manage-suggested-segments"></a>Quản lý các phân đoạn được đề xuất

Đi đến **Phân đoạn** và chọn **Gợi ý (xem trước)** chuyển hướng. bên trong **Đề xuất phân đoạn dựa trên thuộc tính**, chọn một phân đoạn được đề xuất để xem các hành động có sẵn.

- **Lượt xem** chi tiết phân đoạn được đề xuất và các giá trị hoặc quy tắc thuộc tính mà mô hình AI đã học được.
- **Lưu dưới dạng phân đoạn** đề xuất dưới dạng một phân đoạn. Nó hiển thị trên **Tất cả các phân đoạn** tab và có thể là [làm mới, chỉnh sửa hoặc xóa](segments.md).
- **Chỉnh sửa thuộc tính** và sửa đổi các thuộc tính đã định cấu hình sẽ thay thế các đề xuất hiện tại.
- **Làm mới đề xuất** để làm mới các đề xuất trong khi vẫn giữ các thuộc tính đã định cấu hình.

## <a name="limitations"></a>Giới hạn

1. Kích thước phân đoạn ước tính không khớp: Nếu bạn chọn thuộc tính chính chứa các giá trị trống, thì thuộc tính này có thể ảnh hưởng đến kích thước phân đoạn ước tính trong đề xuất phân đoạn. Khi lưu phân đoạn như vậy, kích thước phân đoạn thực tế có thể khác với ước tính ban đầu.

2. Thuộc tính chính kiểu boolean không hoạt động: Hiện tại, chúng tôi chỉ hỗ trợ các kiểu dữ liệu chuỗi và số làm thuộc tính chính.

3. Các phân đoạn được đề xuất không đủ khác biệt: Hãy nhớ rằng các thuộc tính đã chọn và sự phân bổ giá trị của các thuộc tính đó ảnh hưởng đến kết quả. Bạn có thể thay đổi các thuộc tính ảnh hưởng hoặc thậm chí là thuộc tính chính của mình để nhận được các kết quả khác nhau.

[!INCLUDE [footer-include](includes/footer-banner.md)]