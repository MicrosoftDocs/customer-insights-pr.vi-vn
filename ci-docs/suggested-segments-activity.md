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
ms.openlocfilehash: df4f5f4b5c9a3ad66d57a6b349e18a0d714aff62
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170615"
---
# <a name="suggested-segments-based-on-activity-preview"></a>Các phân đoạn được đề xuất dựa trên hoạt động (xem trước)

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
Nếu bạn cung cấp dịch vụ chăm sóc sức khỏe cộng đồng và mục tiêu của bạn là giảm thiểu chi phí cho từng bệnh nhân, bạn có thể cố gắng giảm số lần khám bệnh định kỳ bằng cách cung cấp dịch vụ chăm sóc tốt nhất có thể với số lần khám bệnh càng ít càng tốt. Trong trường hợp này, mục tiêu của bạn là giảm tần suất khám bệnh và chi phí tái khám cho bệnh nhân. Hoặc bạn có thể xác định các phân khúc bệnh nhân có cuộc hẹn thường xuyên và chi phí tái khám cao và phân tích những trường hợp này để cải thiện việc điều trị cho từng cá nhân.

## <a name="required-data"></a>Dữ liệu bắt buộc

Đề xuất được tạo dựa trên dữ liệu đầu vào đã chọn.

- Hồ sơ khách hàng: Tất cả khách hàng hoặc thành viên của một phân khúc cụ thể.

- Khoảng thời gian: Tháng trước, năm trước hoặc bất kỳ khung thời gian tùy chỉnh nào.

- Loại hoạt động: mua hàng, giao dịch bán lẻ, giao dịch trực tuyến, các trường hợp hỗ trợ khách hàng, gói đăng ký, v.v.  

- Thực thể trong Customer Insights có chứa dữ liệu hoạt động: Thực thể UnifiedActivity hoặc thực thể cho một hoạt động cụ thể.

- Các yếu tố bao gồm: Lần truy cập gần đây, tần suất hoặc yếu tố tiền tệ, tùy thuộc vào yêu cầu kinh doanh của bạn.

## <a name="generate-suggested-segments"></a>Tạo các phân đoạn được đề xuất

1. Đi đến **Phân đoạn** và chọn **Gợi ý (xem trước)** chuyển hướng.

1. Chọn **Tìm đề xuất mới** và chọn **Xem hoặc dự đoán hành vi của khách hàng**. Lựa chọn **Bắt đầu**.

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="Bước đầu tiên của trình hướng dẫn cấu hình cho phân khúc đã đề xuất dựa trên hoạt động.":::

1. Cung cấp dữ liệu đầu vào được yêu cầu và chọn **Tiếp theo**.

   - Chọn khách hàng: Bao gồm tất cả khách hàng hoặc khách hàng trong một phân khúc cụ thể.
   - Chọn hoạt động: Chọn loại hoạt động và các thực thể mô tả hoạt động.
   - Tùy chọn: Đặt khoảng thời gian cần xem xét, các yếu tố cho đề xuất và lập bản đồ các thuộc tính.

1. Xem xét lại dữ liệu đầu vào của bạn và chọn **Chạy** để chạy mô hình và tạo đề xuất.

Tùy thuộc vào số lượng hồ sơ khách hàng và các hoạt động đã chọn, thời gian chạy có thể lên đến vài phút.

Sau khi tạo các đề xuất, bạn có thể lọc chúng theo thứ mục hoặc giá trị mà bạn quan tâm nhất.

## <a name="manage-suggested-segments"></a>Quản lý các phân đoạn được đề xuất

Đi đến **Phân đoạn** và chọn **Gợi ý (xem trước)** chuyển hướng. bên trong **Đề xuất dựa trên hoạt động**, chọn một phân đoạn được đề xuất để xem các hành động có sẵn.

- **Xem đề xuất** để xem chi tiết của phân khúc đó như phạm vi của từng thứ nguyên so với nhóm mục tiêu. Ngăn này cũng làm nổi bật số lượng thành viên tiềm năng trong phân khúc và tỷ lệ phần trăm tương ứng trên tổng số khách hàng.
- **Tạo phân đoạn** để lưu đề xuất dưới dạng phân đoạn. Nó hiển thị trên **Tất cả các phân đoạn** tab và có thể là [làm mới hoặc xóa](segments.md). Bạn không thể chỉnh sửa chi tiết phân khúc. Tuy nhiên, bạn có thể thay đổi tiêu chí đầu vào cho các đề xuất và tạo các đề xuất khác nhau.
- **Chỉnh sửa đề xuất** để sửa đổi các thuộc tính đã định cấu hình sẽ thay thế các đề xuất hiện tại.
- **Làm mới đề xuất** để làm mới các đề xuất trong khi vẫn giữ các thuộc tính đã định cấu hình.

[!INCLUDE [footer-include](includes/footer-banner.md)]
