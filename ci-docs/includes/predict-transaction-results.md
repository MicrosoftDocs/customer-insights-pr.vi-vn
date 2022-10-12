---
ms.openlocfilehash: a67714de5aae80a0080c0e631ae6f8986eb2a003
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 09/30/2022
ms.locfileid: "9611139"
---
- **Hiệu suất mô hình đào tạo** : Điểm A, B hoặc C cho biết hiệu suất của dự đoán và có thể giúp bạn đưa ra quyết định sử dụng kết quả được lưu trữ trong thực thể đầu ra.

  Điểm được xác định dựa trên các quy tắc sau:
  - **A** khi mô hình dự đoán chính xác ít nhất 50% tổng số dự đoán và khi tỷ lệ dự đoán chính xác cho khách hàng đã dự đoán lớn hơn tỷ lệ cơ sở ít nhất 10%.
  - **B** khi mô hình dự đoán chính xác ít nhất 50% tổng số dự đoán và khi tỷ lệ dự đoán chính xác cho khách hàng đã rời đi lớn hơn tỷ lệ cơ sở tối đa 10%.
  - **C** khi mô hình dự đoán chính xác ít hơn 50% tổng số dự đoán hoặc khi phần trăm dự đoán chính xác cho khách hàng đã dự đoán nhỏ hơn đường cơ sở.
  - **Đường cơ sở** lấy đầu vào cửa sổ thời gian dự đoán cho mô hình (ví dụ: một năm) và tạo các phần thời gian khác nhau bằng cách chia nó cho 2 cho đến khi nó đạt đến một tháng hoặc ít hơn. Nó sử dụng các phân số này để tạo quy tắc công việc cho những khách hàng chưa mua hàng trong khung thời gian này. Những khách hàng này được coi là đã rời đi. Quy tắc kinh doanh dựa trên thời gian với khả năng dự đoán cao nhất ai có khả năng bỏ trốn được chọn làm mô hình cơ sở.

- **Khả năng rời khỏi (số lượng khách hàng)**: Các nhóm khách hàng dựa trên rủi ro rời khỏi dự đoán. Tùy ý, [tạo phân khúc khách hàng](../prediction-based-segment.md) với nguy cơ churn cao. Những phân khúc này giúp hiểu được điểm cắt nên dành cho các thành phần phân khúc.

- **Các yếu tố có ảnh hưởng nhất**: Có nhiều yếu tố được xem xét khi tạo dự đoán. Mỗi yếu tố có tầm quan trọng được tính toán cho các dự đoán tổng hợp mà một mô hình tạo ra. Sử dụng các yếu tố này để giúp xác thực kết quả dự đoán của bạn. Hoặc sử dụng thông tin này sau để [tạo phân đoạn](../prediction-based-segment.md) điều đó có thể giúp ảnh hưởng đến rủi ro churn cho khách hàng.