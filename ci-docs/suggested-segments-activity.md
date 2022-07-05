---
title: Các phân đoạn được đề xuất dựa trên hoạt động (xem trước)
description: Tìm ra các phân khúc mới mẻ và thú vị dựa trên hoạt động của khách hàng nhờ vào cơ chế máy học.
ms.date: 05/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
searchScope:
- ci-segment-suggestions
- customerInsights
ms.openlocfilehash: e98aea3b3f3a2c4788346deab1b7ad7d1167110d
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 06/29/2022
ms.locfileid: "9054366"
---
# <a name="suggested-segments-based-on-activity-data-preview"></a>Các phân khúc được đề xuất dựa trên dữ liệu hoạt động (bản xem trước)

Khám phá các phân khúc khách hàng thú vị dựa trên dữ liệu hoạt động của khách hàng có trong Customer Insights. Ví dụ về dữ liệu hoạt động là giao dịch, thời lượng cuộc gọi hỗ trợ, quá trình mua hoặc trả hàng. Để đề xuất các phân khúc, dữ liệu hoạt động sẽ được phân tích theo lần truy cập gần đây, tần suất và giá trị tiền tệ (hoặc thời lượng). Ngoài ra, bạn có thể tạo [các phân khúc được đề xuất để cải thiện thước đo hoặc hiểu rõ hơn yếu tố ảnh hưởng đến thuộc tính](suggested-segments.md).

:::image type="content" source="media/suggested-segments-tab.png" alt-text="Tab phân khúc được đề xuất hiển thị các đề xuất cho các phân khúc dựa trên hoạt động và thuộc tính.":::

## <a name="categorize-customers-by-activity"></a>Phân loại khách hàng theo hoạt động

Với [dữ liệu hoạt động](activities.md) có sẵn trong Customer Insights, chúng tôi có thể tạo các đề xuất đại diện cho các nhóm khách hàng:

- những khách hàng tích cực nhất 
- những khách hàng đã mua hàng nhiều nhất 
- những khách hàng tạo ra nhiều doanh thu nhất 
- những khách hàng không hoạt động gần đây 
- những khách hàng thường xuyên tương tác với doanh nghiệp của bạn  

Nếu bạn có một doanh nghiệp bán lẻ, bạn có thể tìm ra những khách hàng nào tạo ra nhiều doanh thu nhất và tặng phiếu giảm giá cho họ. Hoặc bạn có thể xác định những khách hàng không thường xuyên mua hàng và đề nghị họ tham gia chương trình phần thưởng để họ ghé thăm doanh nghiệp của bạn thường xuyên hơn.
Giả sử bạn đang kinh doanh trong lĩnh vực chăm sóc sức khỏe, cung cấp dịch vụ chăm sóc sức khỏe cộng đồng và mục tiêu của bạn là giảm thiểu chi phí cho mỗi bệnh nhân. Bạn có thể giảm số lần tái khám của bệnh nhân bằng cách đưa ra dịch vụ chăm sóc tốt nhất có thể trong những lần khám bệnh ít ỏi đó. Trong trường hợp này, mục tiêu của bạn là giảm tần suất khám bệnh và chi phí tái khám cho bệnh nhân. Hoặc bạn có thể xác định các phân khúc bệnh nhân có cuộc hẹn thường xuyên và chi phí tái khám cao và phân tích những trường hợp này để cải thiện việc điều trị cho từng cá nhân. 

## <a name="required-data"></a>Dữ liệu bắt buộc

Đề xuất được tạo dựa trên dữ liệu đầu vào đã chọn. 

- Hồ sơ khách hàng: Tất cả khách hàng hoặc thành viên của một phân khúc cụ thể. 

- Khoảng thời gian: Tháng trước, năm trước hoặc bất kỳ khung thời gian tùy chỉnh nào.

- Loại hoạt động: mua hàng, giao dịch bán lẻ, giao dịch trực tuyến, các trường hợp hỗ trợ khách hàng, gói đăng ký, v.v.  

- Thực thể trong Customer Insights có chứa dữ liệu hoạt động: Thực thể UnifiedActivity hoặc thực thể cho một hoạt động cụ thể. 

- Các yếu tố bao gồm: Lần truy cập gần đây, tần suất hoặc yếu tố tiền tệ, tùy thuộc vào yêu cầu kinh doanh của bạn.

## <a name="generate-suggested-segments"></a>Tạo các phân đoạn được đề xuất

1. Đi đến **Phân khúc**.

1. Chọn tab **Gợi ý (xem trước)**.

1. Chọn **Tìm đề xuất mới** và chọn **Xem hoặc dự đoán hành vi của khách hàng**. Chọn **Bắt đầu** để chạy trải nghiệm đã hướng dẫn.

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="Bước đầu tiên của trình hướng dẫn cấu hình cho phân khúc đã đề xuất dựa trên hoạt động.":::

1. Cung cấp dữ liệu đầu vào được yêu cầu và tiếp tục chọn **Tiếp theo**.

   - Chọn khách hàng: Bao gồm tất cả khách hàng hoặc khách hàng trong một phân khúc cụ thể.
   - Chọn hoạt động: Chọn loại hoạt động và các thực thể mô tả hoạt động.
   - Tùy chọn: Đặt khoảng thời gian cần xem xét, các yếu tố cho đề xuất và lập bản đồ các thuộc tính.

1. Xem xét lại dữ liệu đầu vào của bạn và chọn **Chạy** để chạy mô hình và tạo đề xuất.

1. Tùy thuộc vào số lượng hồ sơ khách hàng và các hoạt động đã chọn, thời gian chạy có thể lên đến vài phút. 

Sau khi tạo các đề xuất, bạn có thể lọc chúng theo thứ mục hoặc giá trị mà bạn quan tâm nhất. 

## <a name="view-details-of-a-suggested-segment"></a>Xem chi tiết về phân khúc được gợi ý

Sau khi bạn tạo các đề xuất, các đề xuất này sẽ xuất hiện trên mục **Phân khúc** > **Đề xuất (xem trước)** trong phần **Đề xuất dựa trên hoạt động**.

:::image type="content" source="media/suggested-segments-details.png" alt-text="Ngăn bên được mở rộng hiển thị dữ liệu chi tiết của phân khúc đã đề xuất.":::

Chọn **Xem đề xuất** trên một phân khúc đã đề xuất để xem chi tiết. Ngăn bên thể hiện các chi tiết như phạm vi của từng yếu tố so với nhóm mục tiêu. Ngăn này cũng làm nổi bật số lượng thành viên tiềm năng trong phân khúc và tỷ lệ phần trăm tương ứng trên tổng số khách hàng. Nếu bạn muốn giữ đề xuất dưới dạng một phân khúc, hãy chọn **Tạo phân khúc**.    

## <a name="save-a-suggestion-as-a-segment"></a>Lưu đề xuất làm phân đoạn

1. Đi đến **Phân đoạn** > **Gợi ý (xem trước)**.

1. Chọn phân khúc bạn muốn lưu. 

1. Trong ngăn bên, hãy chọn **Tạo phân khúc**. 

1. Sau khi lưu phân khúc, phân khúc đó sẽ hiển thị trên danh sách các phân khúc trong tab **Tất cả các phân khúc**. Bây giờ, bạn có thể [làm mới hoặc xóa phân khúc đó giống như bất kỳ phân khúc nào khác](segments.md). Bạn không thể chỉnh sửa chi tiết phân khúc. Tuy nhiên, bạn có thể thay đổi tiêu chí đầu vào cho các đề xuất và tạo các đề xuất khác nhau.

## <a name="refresh-or-edit-a-set-of-suggestions"></a>Làm mới hoặc chỉnh sửa một tập hợp các đề xuất

1. Chuyển tới **Phân khúc** > **Đề xuất (xem trước)** và tìm kiếm phân khúc trong phần **Đề xuất dựa trên hoạt động**.

1. Chọn **Làm mới đề xuất** để làm mới các đề xuất trong khi vẫn giữ các thuộc tính đã định cấu hình. Hoặc chọn **Chỉnh sửa đề xuất** để sửa đổi các thuộc tính đã định cấu hình. Hệ thống sẽ chạy lại quy trình, tạo các đề xuất phân khúc dựa trên dữ liệu mới nhất và thay thế các đề xuất hiện tại.

[!INCLUDE [footer-include](includes/footer-banner.md)]
