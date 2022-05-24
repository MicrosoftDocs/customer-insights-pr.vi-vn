---
title: Hướng dẫn mẫu dự đoán rời bỏ giao dịch
description: Sử dụng hướng dẫn mẫu này để thử mô hình dự đoán rời bỏ giao dịch dùng ngay.
ms.date: 05/11/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 3edbf2a471313379c28db874d7f19c3265a23299
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741345"
---
# <a name="transactional-churn-prediction-sample-guide"></a>Hướng dẫn mẫu dự đoán rời bỏ giao dịch

Hướng dẫn này sẽ giải thích cho bạn ví dụ toàn diện về dự đoán rời bỏ giao dịch trong Customer Insights bằng cách sử dụng dữ liệu được cung cấp bên dưới. Tất cả dữ liệu được sử dụng trong hướng dẫn này không phải là dữ liệu khách hàng thực và là một phần của tập dữ liệu Contoso được tìm thấy trong môi trường *Demo* trong Đăng ký Customer Insights của bạn.

## <a name="scenario"></a>Kịch bản

Contoso là công ty sản xuất cà phê và máy pha cà phê chất lượng cao, họ bán thông qua trang web Contoso Coffee của mình. Mục tiêu là biết những khách hàng nào thường mua sản phẩm của họ một cách thường xuyên, sẽ không còn là khách hàng tích cực trong 60 ngày tới. Biết khách hàng nào **có khả năng rời bỏ**, có thể giúp họ tiết kiệm các nỗ lực tiếp thị bằng cách tập trung vào việc giữ chân họ.

## <a name="prerequisites"></a>Điều kiện tiên quyết

- Ít nhất [Quyền của người đóng góp](permissions.md) trong Customer Insights.
- Chúng tôi khuyên bạn nên thực hiện các bước sau [trong một môi trường mới](manage-environments.md).

## <a name="task-1---ingest-data"></a>Nhiệm vụ 1 - Nhập dữ liệu

Xem lại các bài báo [về việc nhập dữ liệu](data-sources.md) và [nhập nguồn dữ liệu bằng cách sử dụng Power Query đầu nối](connect-power-query.md) đặc biệt. Thông tin sau đây giả định rằng bạn đã quen với việc nhập dữ liệu nói chung. 

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Nhập dữ liệu khách hàng từ nền tảng Thương mại điện tử

1. Tạo nguồn dữ liệu có tên **Thương mại điện tử**, chọn tùy chọn nhập và chọn trình kết nối **Văn bản/CSV**.

1. Nhập URL cho các liên hệ Thương mại điện tử https://aka.ms/ciadclasscontacts.

1. Trong khi chỉnh sửa dữ liệu, hãy chọn **Chuyển đổi** rồi chọn **Dùng hàng đầu tiên làm tiêu đề**.

1. Cập nhật kiểu dữ liệu cho các cột được liệt kê bên dưới:

   - **DateOfBirth**: Ngày
   - **CreatedOn**: Ngày/Giờ/Vùng

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Chuyển đổi DoB thành Ngày.":::

1. Trong trường **Tên** ở ngăn bên phải, hãy đổi tên nguồn dữ liệu của bạn từ **Truy vấn** thành **eCommerceContacts**

1. Lưu nguồn dữ liệu.

### <a name="ingest-online-purchase-data"></a>Nhập dữ liệu mua hàng trực tuyến

1. Thêm một tập hợp dữ liệu khác vào cùng một nguồn dữ liệu **Thương mại điện tử**. Chọn lại trình kết nối **Văn bản/CSV**.

1. Nhập URL cho dữ liệu **Mua hàng trực tuyến** https://aka.ms/ciadclassonline.

1. Trong khi chỉnh sửa dữ liệu, hãy chọn **Chuyển đổi** rồi chọn **Dùng hàng đầu tiên làm tiêu đề**.

1. Cập nhật kiểu dữ liệu cho các cột được liệt kê bên dưới:

   - **PurchasedOn**: Ngày/Giờ
   - **TotalPrice**: Tiền tệ
   
1. Trong trường **Tên** ở ngăn bên phải, hãy đổi tên nguồn dữ liệu của bạn từ **Truy vấn** thành **eCommercePurchases**.

1. Lưu nguồn dữ liệu.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Nhập dữ liệu khách hàng từ lược đồ khách hàng thân thiết

1. Tạo nguồn dữ liệu có tên **LoyaltyScheme**, chọn tùy chọn nhập và chọn trình kết nối **Văn bản/CSV**.

1. Nhập URL cho các liên hệ Thương mại điện tử https://aka.ms/ciadclasscustomerloyalty.

1. Trong khi chỉnh sửa dữ liệu, hãy chọn **Chuyển đổi** rồi chọn **Dùng hàng đầu tiên làm tiêu đề**.

1. Cập nhật kiểu dữ liệu cho các cột được liệt kê bên dưới:

   - **DateOfBirth**: Ngày
   - **RewardsPoints**: Số nguyên
   - **CreatedOn**: Ngày/Giờ

1. Trong trường **Tên** ở ngăn bên phải, hãy đổi tên nguồn dữ liệu của bạn từ **Truy vấn** thành **loyCustomers**.

1. Lưu nguồn dữ liệu.

## <a name="task-2---data-unification"></a>Nhiệm vụ 2 - Hợp nhất dữ liệu

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-transaction-churn-prediction"></a>Nhiệm vụ 3 - Định cấu hình dự đoán rời bỏ giao dịch

Với hồ sơ khách hàng hợp nhất đã có, giờ đây chúng tôi có thể chạy giao dịch churn dự đoán. Để biết các bước chi tiết, hãy xem [Giao dịch churn dự đoán](predict-transactional-churn.md) điều. 

1. Đi đến **Thông tin** > **Khám phá** và chọn để sử dụng **Mô hình khách hàng rời đi**.

1. Chọn tùy chọn **Giao dịch** và chọn **Bắt đầu**.

1. Đặt tên cho mô hình **Dự đoán rời bỏ giao dịch thương mại điện tử OOB** và thực thể đầu ra **OOBeCommerceChurnPrediction**.

1. Xác định hai điều kiện cho mô hình khách hàng rời đi:

   * **Khoảng thời gian dự đoán**: **tối thiểu 60** ngày. Cài đặt này xác định chúng ta muốn dự đoán khách hàng rời đi trong tương lai bao xa.

   * **Định nghĩa về tỷ lệ rời đi**: **tối thiểu 60** ngày. Khoảng thời gian không mua hàng mà sau đó khách hàng được coi là rời đi.

     :::image type="content" source="media/model-levers.PNG" alt-text="Chọn mô hình thúc đẩy khoảng thời gian dự đoán và định nghĩa về tỷ lệ rời đi.":::

1. Chọn **Lịch sử mua hàng (bắt buộc)** và chọn **Thêm dữ liệu** cho lịch sử mua hàng.

1. Thêm thực thể **eCommercePurchases: eCommerce** và ánh xạ các trường từ thương mại điện tử đến các trường tương ứng theo yêu cầu của mô hình.

1. Tham gia thực thể **eCommercePurchases: eCommerce** với **eCommerceContacts: eCommerce**.

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="Tham gia các thực thể thương mại điện tử.":::

1. Chọn **Tiếp theo** để đặt lịch trình mô hình.

   Mô hình cần đào tạo thường xuyên để học các mẫu mới khi có dữ liệu mới được nhập vào. Đối với ví dụ này, hãy chọn **Hàng tháng**.

1. Sau khi xem lại tất cả thông tin chi tiết, hãy chọn **Lưu và chạy**.

## <a name="task-4---review-model-results-and-explanations"></a>Nhiệm vụ 4 - Xem xét kết quả và giải thích mô hình

Để mô hình hoàn thành việc đào tạo và chấm điểm dữ liệu. Bây giờ bạn có thể xem lại các giải thích mô hình churn. Để biết thêm thông tin, hãy xem [Xem lại dự đoán trạng thái và kết quả](predict-transactional-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a>Nhiệm vụ 5 - Tạo một phân khúc khách hàng có nguy cơ rời bỏ cao

Việc chạy mô hình sản xuất sẽ tạo ra một thực thể mới mà bạn có thể thấy trong **Dữ liệu** > **Thực thể**.   

Bạn có thể tạo một phân khúc mới dựa trên thực thể được tạo bởi mô hình.

1.  Đi đến **Phân khúc**. Chọn **Mới** rồi chọn **Tạo từ** > **Thông tin**. 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Tạo một phân khúc với đầu ra mô hình.":::

1. Chọn **OOBeCommerceChurnPrediction** endpoint và xác định phân đoạn: 
   - Trường: ChurnScore
   - Toán tử: lớn hơn
   - Giá trị: 0,6

Giờ đây, bạn có một phân đoạn được cập nhật động để xác định những khách hàng có nguy cơ bỏ trốn cao.

Để biết thêm thông tin, hãy xem [Tạo và quản lý phân khúc](segments.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]
