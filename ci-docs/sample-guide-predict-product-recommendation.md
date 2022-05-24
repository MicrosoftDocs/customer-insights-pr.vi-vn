---
title: Hướng dẫn mẫu dự đoán đề xuất sản phẩm
description: Sử dụng hướng dẫn mẫu này để thử mô hình dự đoán đề xuất sản phẩm dùng ngay.
ms.date: 05/16/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-predictions
- ci-create-prediction
- customerInsights
ms.openlocfilehash: cc72cce15fa0c9e92dbf202c803e99514c9ce2b1
ms.sourcegitcommit: 82f417cfb0a16600e9f552d7a21d598cc8f5a267
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 05/16/2022
ms.locfileid: "8762712"
---
# <a name="product-recommendation-prediction-sample-guide"></a>Hướng dẫn mẫu dự đoán đề xuất sản phẩm

Chúng tôi hướng dẫn bạn thông qua một ví dụ toàn diện về dự đoán đề xuất sản phẩm bằng cách sử dụng dữ liệu mẫu được cung cấp bên dưới.

## <a name="scenario"></a>Kịch bản

Contoso là công ty sản xuất cà phê và máy pha cà phê chất lượng cao, họ bán thông qua trang web Contoso Coffee của mình. Mục tiêu là hiểu họ nên giới thiệu sản phẩm nào cho khách hàng định kỳ của họ. Biết khách hàng **có khả năng mua** sản phẩm nào hơn, có thể giúp họ tiết kiệm nỗ lực tiếp thị bằng cách tập trung vào các mặt hàng cụ thể.

## <a name="prerequisites"></a>Điều kiện tiên quyết

- Ít nhất [Quyền của người đóng góp](permissions.md) trong Customer Insights.
- Chúng tôi khuyên bạn nên thực hiện các bước sau [trong một môi trường mới](manage-environments.md).

## <a name="task-1---ingest-data"></a>Nhiệm vụ 1 - Nhập dữ liệu

Xem lại các bài báo [về việc nhập dữ liệu](data-sources.md) và [nhập nguồn dữ liệu bằng cách sử dụng Power Query đầu nối](connect-power-query.md) đặc biệt. Thông tin sau đây giả định rằng bạn đã quen với việc nhập dữ liệu nói chung.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Nhập dữ liệu khách hàng từ nền tảng Thương mại điện tử

1. Tạo nguồn dữ liệu có tên **Thương mại điện tử**, chọn tùy chọn nhập và chọn trình kết nối **Văn bản/CSV**.

1. Nhập URL cho địa chỉ liên hệ Thương mại điện tử: [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).

1. Trong khi chỉnh sửa dữ liệu, hãy chọn **Chuyển đổi** rồi chọn **Dùng hàng đầu tiên làm tiêu đề**.

1. Cập nhật kiểu dữ liệu cho các cột được liệt kê bên dưới:
   - **DateOfBirth**: Ngày
   - **CreatedOn**: Ngày/Giờ/Vùng

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Chuyển đổi ngày sinh thành ngày.":::

1. Trong trường "Tên" ở ngăn bên phải, hãy đổi tên nguồn dữ liệu của bạn từ **Truy vấn** thành **eCommerceContacts**.

1. **Lưu** nguồn dữ liệu.

### <a name="ingest-online-purchase-data"></a>Nhập dữ liệu mua hàng trực tuyến

1. Thêm một tập hợp dữ liệu khác vào cùng một nguồn dữ liệu **Thương mại điện tử**. Chọn lại trình kết nối **Văn bản/CSV**.

1. Nhập URL cho **Mua hàng trực tuyến** dữ liệu [https://aka.ms/ciadclassonline](https://aka.ms/ciadclassonline).

1. Trong khi chỉnh sửa dữ liệu, hãy chọn **Chuyển đổi** rồi chọn **Dùng hàng đầu tiên làm tiêu đề**.

1. Cập nhật kiểu dữ liệu cho các cột được liệt kê bên dưới:
   - **PurchasedOn**: Ngày/Giờ
   - **TotalPrice**: Tiền tệ

1. Trong trường **Tên** ở ngăn bên, hãy đổi tên nguồn dữ liệu của bạn từ **Truy vấn** thành **eCommercePurchases**.

1. **Lưu** nguồn dữ liệu.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Nhập dữ liệu khách hàng từ lược đồ khách hàng thân thiết

1. Tạo nguồn dữ liệu có tên **LoyaltyScheme**, chọn tùy chọn nhập và chọn trình kết nối **Văn bản/CSV**.

1. Nhập URL cho các liên hệ Thương mại điện tử [https://aka.ms/ciadclasscustomerloyalty](https://aka.ms/ciadclasscustomerloyalty).

1. Trong khi chỉnh sửa dữ liệu, hãy chọn **Chuyển đổi** rồi chọn **Dùng hàng đầu tiên làm tiêu đề**.

1. Cập nhật kiểu dữ liệu cho các cột được liệt kê bên dưới:
   - **DateOfBirth**: Ngày
   - **RewardsPoints**: Số nguyên
   - **CreatedOn**: Ngày/Giờ

1. Trong trường **Tên** ở ngăn bên phải, hãy đổi tên nguồn dữ liệu của bạn từ **Truy vấn** thành **loyCustomers**.

1. **Lưu** nguồn dữ liệu.

## <a name="task-2---data-unification"></a>Nhiệm vụ 2 - Hợp nhất dữ liệu

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-product-recommendation-prediction"></a>Nhiệm vụ 3 - Định cấu hình dự đoán đề xuất sản phẩm

Với hồ sơ khách hàng thống nhất đã có, giờ đây chúng tôi có thể chạy đề xuất sản phẩm dự đoán.

1. Đi đến **Thông tin** > **Dự đoán**, chọn **Đề xuất sản phẩm**.

1. Chọn **Bắt đầu**.

1. Đặt tên cho mô hình **Dự đoán Mô hình Đề xuất Sản phẩm OOB** và thực thể đầu ra **OOBProductRecommendationModelPrediction**.

1. Xác định ba điều kiện cho mô hình:

   - **Số lượng sản phẩm**: Đặt giá trị này thành **5**. Cài đặt này xác định số lượng sản phẩm bạn muốn giới thiệu cho khách hàng của mình.

   - **Lặp lại giao dịch mua dự kiến**: Chọn **Có** để cho biết rằng bạn muốn đưa sản phẩm vào phần đề xuất mà khách hàng của bạn đã mua hàng trước đó.

   - **Khoảng thời gian xem lại:** Chọn ít nhất **365 ngày**. Cài đặt này xác định khoảng thời gian mô hình sẽ xem xét hoạt động của khách hàng để dùng làm thông tin đề xuất cho họ.

   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Tùy chọn mô hình cho mô hình đề xuất sản phẩm.":::

1. Bên trong **Thêm dữ liệu bắt buộc** bước, chọn **Thêm dữ liệu**.

1. Bên trong **Thêm dữ liệu** ngăn, chọn **SalesOrderLine** với tư cách là thực thể lịch sử mua hàng. Tại thời điểm này, nó có thể chưa được định cấu hình. Mở liên kết trong ngăn để tạo hoạt động theo các bước sau:
   1. Nhập một **Tên hoạt động** và lựa chọn *eCommercePurchases: eCommerce* như **Thực thể hoạt động**. Các **Khóa chính** Là *PurchaseId*.
   1. Xác định và đặt tên cho mối quan hệ với *eCommerceContacts: thực thể thương mại điện tử* và lựa chọn **ContactId** làm khóa ngoại.
   1. Để hợp nhất Hoạt động, hãy đặt **Hoạt động sự kiện** như *Tổng giá* và Dấu thời gian cho *Đã mua*. Bạn có thể chỉ định nhiều trường hơn như được nêu trong [Hoạt động của khách hàng](activities.md).
   1. Vì **Loại hoạt động**, chọn *SalesOrderLine*. Lập bản đồ các trường hoạt động sau:
      - ID dòng đặt hàng: PurchaseId
      - ID đặt hàng: PurchaseId
      - Dữ liệu đặt hàng: PurchasedOn
      - ID sản phẩm: ProductId
      - Số lượng: Tổng giá
   1. Xem lại và kết thúc hoạt động trước khi quay lại cấu hình mô hình.

1. Quay lại **Chọn các hoạt động** bước, chọn hoạt động mới được tạo trong **Các hoạt động** tiết diện. Lựa chọn **Kế tiếp** và ánh xạ thuộc tính đã được điền. Lựa chọn **Cứu**.

1. Trong hướng dẫn mẫu này, chúng tôi bỏ qua **Thêm thông tin sản phẩm** và **Bộ lọc sản phẩm** đặt vì chúng tôi không có dữ liệu thông tin sản phẩm.

1. Bên trong **Cập nhật dữ liệu** bước, thiết lập lịch trình mô hình.

   Mô hình cần đào tạo thường xuyên để học các mẫu mới khi có dữ liệu mới được nhập vào. Đối với ví dụ này, hãy chọn **Hàng tháng**.

1. Sau khi xem lại tất cả thông tin chi tiết, hãy chọn **Lưu và chạy**. Sẽ mất vài phút để chạy mô hình lần đầu tiên.

## <a name="task-4---review-model-results-and-explanations"></a>Nhiệm vụ 4 - Xem xét kết quả và giải thích mô hình

Để mô hình hoàn thành việc đào tạo và chấm điểm dữ liệu. Bây giờ bạn có thể xem lại giải thích về mô hình đề xuất sản phẩm. Để biết thêm thông tin, hãy xem [Xem lại dự đoán trạng thái và kết quả](predict-transactional-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-purchased-products"></a>Nhiệm vụ 5 - Tạo phân khúc sản phẩm được mua nhiều

Việc chạy mô hình sản xuất sẽ tạo ra một thực thể mới mà bạn có thể thấy trong **Dữ liệu** > **Thực thể**.

Bạn có thể tạo một phân khúc mới dựa trên thực thể được tạo bởi mô hình.

1. Đi đến **Phân khúc**. Lựa chọn **Mới mẻ** và lựa chọn **Tạo từ Trí tuệ**.

   ![Tạo một phân khúc với đầu ra mô hình.](media/segment-intelligence.png)

1. Chọn điểm cuối **OOBProductRecommendationModelPrediction** và xác định phân khúc:

   - Trường: ID sản phẩm
   - Giá trị: Chọn ba ID sản phẩm hàng đầu

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="Tạo một phân khúc từ kết quả mô hình.":::

Giờ đây, bạn có một phân đoạn được cập nhật động, xác định những khách hàng có thể quan tâm đến việc mua ba sản phẩm được đề xuất nhiều nhất.

Để biết thêm thông tin, hãy xem [Tạo và quản lý phân khúc](segments.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
