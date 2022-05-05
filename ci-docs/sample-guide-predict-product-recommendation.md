---
title: Hướng dẫn mẫu dự đoán đề xuất sản phẩm
description: Sử dụng hướng dẫn mẫu này để thử mô hình dự đoán đề xuất sản phẩm dùng ngay.
ms.date: 02/10/2021
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
ms.openlocfilehash: 1115bab13bdca4a308a8d9eb5a1dc270801d16be
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 04/27/2022
ms.locfileid: "8644102"
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

1. Nhập URL cho các liên hệ Thương mại điện tử https://aka.ms/ciadclasscontacts.

1. Trong khi chỉnh sửa dữ liệu, hãy chọn **Chuyển đổi** rồi chọn **Dùng hàng đầu tiên làm tiêu đề**.

1. Cập nhật kiểu dữ liệu cho các cột được liệt kê bên dưới:
   - **DateOfBirth**: Ngày
   - **CreatedOn**: Ngày/Giờ/Vùng

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Chuyển đổi ngày sinh thành ngày.":::

5. Trong trường "Tên" ở ngăn bên phải, hãy đổi tên nguồn dữ liệu của bạn từ **Truy vấn** thành **eCommerceContacts**.

6. **Lưu** nguồn dữ liệu.

### <a name="ingest-online-purchase-data"></a>Nhập dữ liệu mua hàng trực tuyến

1. Thêm một tập hợp dữ liệu khác vào cùng một nguồn dữ liệu **Thương mại điện tử**. Chọn lại trình kết nối **Văn bản/CSV**.

1. Nhập URL cho dữ liệu **Mua hàng trực tuyến** https://aka.ms/ciadclassonline.

1. Trong khi chỉnh sửa dữ liệu, hãy chọn **Chuyển đổi** rồi chọn **Dùng hàng đầu tiên làm tiêu đề**.

1. Cập nhật kiểu dữ liệu cho các cột được liệt kê bên dưới:
   - **PurchasedOn**: Ngày/Giờ
   - **TotalPrice**: Tiền tệ

1. Trong trường **Tên** ở ngăn bên, hãy đổi tên nguồn dữ liệu của bạn từ **Truy vấn** thành **eCommercePurchases**.

1. **Lưu** nguồn dữ liệu.


### <a name="ingest-customer-data-from-loyalty-schema"></a>Nhập dữ liệu khách hàng từ lược đồ khách hàng thân thiết

1. Tạo nguồn dữ liệu có tên **LoyaltyScheme**, chọn tùy chọn nhập và chọn trình kết nối **Văn bản/CSV**.

1. Nhập URL cho các liên hệ Thương mại điện tử https://aka.ms/ciadclasscustomerloyalty.

1. Trong khi chỉnh sửa dữ liệu, hãy chọn **Chuyển đổi** rồi chọn **Dùng hàng đầu tiên làm tiêu đề**.

1. Cập nhật kiểu dữ liệu cho các cột được liệt kê bên dưới:
   - **DateOfBirth**: Ngày
   - **RewardsPoints**: Số nguyên
   - **CreatedOn**: Ngày/Giờ

1. Trong trường **Tên** ở ngăn bên phải, hãy đổi tên nguồn dữ liệu của bạn từ **Truy vấn** thành **loyCustomers**.

1. **Lưu** nguồn dữ liệu.

## <a name="task-2---data-unification"></a>Nhiệm vụ 2 - Hợp nhất dữ liệu

Sau khi nhập dữ liệu, bây giờ, chúng ta sẽ bắt đầu quá trình hợp nhất dữ liệu để tạo hồ sơ khách hàng hợp nhất. Để biết thêm thông tin, hãy xem [Hợp nhất dữ liệu](data-unification.md).

### <a name="map"></a>Bản đồ

1. Sau khi nhập dữ liệu, hãy ánh xạ các địa chỉ liên hệ từ dữ liệu Thương mại điện tử và Mức độ trung thành thành các loại dữ liệu phổ biến. Chuyển đến **Dữ liệu** > **Hợp nhất** > **Ánh xạ**.

2. Chọn các thực thể đại diện cho hồ sơ khách hàng – **eCommerceContacts** và **loyCustomers**.

   ![hợp nhất nguồn dữ liệu thương mại điện tử và khách hàng thân thiết.](media/unify-ecommerce-loyalty.png)

3. Chọn **ContactId** làm khóa chính cho **eCommerceContacts** và **LoyaltyID** làm khóa chính cho **loyCustomers**.

   ![Hợp nhất LoyaltyId làm khóa chính.](media/unify-loyaltyid.png)

### <a name="match"></a>Kết quả khớp

1. Đi đến tab **So khớp** và chọn **Đặt thứ tự**.

2. Trong danh sách thả xuống **Chính**, chọn **eCommerceContacts: eCommerce** là nguồn chính và bao gồm tất cả các bản ghi.

3. Trong danh sách thả xuống **Thực thể 2**, chọn **loyCustomers: LoyaltyScheme** và bao gồm tất cả các bản ghi.

   ![Hợp nhất so khớp thương mại điện tử và khách hàng thân thiết.](media/unify-match-order.png)

4. Chọn **Tạo quy tắc mới**

5. Thêm điều kiện đầu tiên của bạn bằng FullName.

   - Đối với eCommerceContacts, chọn **FullName** trong danh sách thả xuống.
   - Đối với loyCustomers, chọn **FullName** trong danh sách thả xuống.
   - Chọn danh sách thả xuống **Chuẩn hóa** rồi chọn **Loại (Số điện thoại, Tên, Địa chỉ,...)**.
   - Đặt **Mức độ chính xác**: **Cơ bản** và **Giá trị**: **Cao**.

6. Nhập tên **FullName, Email** cho quy tắc mới.

   - Thêm điều kiện thứ hai cho địa chỉ email bằng cách chọn **Thêm điều kiện**
   - Đối với thực thể eCommerceContacts, chọn **EMail** trong danh sách thả xuống.
   - Đối với thực thể loyCustomers, chọn **EMail** trong danh sách thả xuống.
   - Để trống trường Chuẩn hóa.
   - Đặt **Mức độ chính xác**: **Cơ bản** và **Giá trị**: **Cao**.

   ![Hợp nhất quy tắc so khớp cho tên và email.](media/unify-match-rule.png)

7. Chọn **Lưu** và **Chạy**.

### <a name="merge"></a>Hợp nhất

1. Đi đến tab **Hợp nhất**.

1. Trên thực thể **ContactId** cho **loyCustomers**, thay đổi tên hiển thị thành **ContactIdLOYALTY** để phân biệt nó với các ID khác đã nhập.

   ![đổi tên contactid từ id khách hàng thân thiết.](media/unify-merge-contactid.png)

1. Chọn **Lưu** và **Chạy** để bắt đầu quy trình Hợp nhất.

## <a name="task-3---configure-product-recommendation-prediction"></a>Nhiệm vụ 3 - Định cấu hình dự đoán đề xuất sản phẩm

Với hồ sơ khách hàng hợp nhất đã có, giờ đây chúng tôi có thể chạy dự đoán khả năng rời bỏ đăng ký.

1. Đi đến **Thông tin** > **Dự đoán**, chọn **Đề xuất sản phẩm**.

1. Chọn **Bắt đầu**.

1. Đặt tên cho mô hình **Dự đoán Mô hình Đề xuất Sản phẩm OOB** và thực thể đầu ra **OOBProductRecommendationModelPrediction**.

1. Xác định ba điều kiện cho mô hình:

   - **Số lượng sản phẩm**: Đặt giá trị này thành **5**. Cài đặt này xác định số lượng sản phẩm bạn muốn giới thiệu cho khách hàng của mình.

   - **Lặp lại giao dịch mua dự kiến**: Chọn **Có** để cho biết rằng bạn muốn đưa sản phẩm vào phần đề xuất mà khách hàng của bạn đã mua hàng trước đó.

   - **Khoảng thời gian xem lại:** Chọn ít nhất **365 ngày**. Cài đặt này xác định khoảng thời gian mô hình sẽ xem xét hoạt động của khách hàng để dùng làm thông tin đề xuất cho họ.
   
   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Tùy chọn mô hình cho mô hình đề xuất sản phẩm.":::

1. Chọn **Dữ liệu bắt buộc** và chọn **Thêm dữ liệu** cho lịch sử giao dịch.

1. Thêm thực thể **eCommercePurchases: eCommerce** và ánh xạ các trường từ thương mại điện tử đến các trường tương ứng theo yêu cầu của mô hình.

1. Tham gia thực thể **eCommercePurchases: eCommerce** với **eCommerceContacts: eCommerce**.

   ![Tham gia các thực thể thương mại điện tử.](media/model-purchase-join.png)

1. Chọn **Tiếp theo** để đặt lịch trình mô hình.

   Mô hình cần đào tạo thường xuyên để học các mẫu mới khi có dữ liệu mới được nhập vào. Đối với ví dụ này, hãy chọn **Hàng tháng**.

1. Sau khi xem lại tất cả thông tin chi tiết, hãy chọn **Lưu và chạy**.


## <a name="task-4---review-model-results-and-explanations"></a>Nhiệm vụ 4 - Xem xét kết quả và giải thích mô hình

Để mô hình hoàn thành việc đào tạo và chấm điểm dữ liệu. Bây giờ bạn có thể xem lại giải thích về mô hình đề xuất sản phẩm. Để biết thêm thông tin, hãy xem [Xem lại dự đoán trạng thái và kết quả](predict-subscription-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-purchased-products"></a>Nhiệm vụ 5 - Tạo phân khúc sản phẩm được mua nhiều

Việc chạy mô hình sản xuất sẽ tạo ra một thực thể mới mà bạn có thể thấy trong **Dữ liệu** > **Thực thể**.

Bạn có thể tạo một phân khúc mới dựa trên thực thể được tạo bởi mô hình.

1. Đi đến **Phân khúc**. Chọn **Mới** rồi chọn **Tạo từ** > **Thông tin**.

   ![Tạo một phân khúc với đầu ra mô hình.](media/segment-intelligence.png)

1. Chọn điểm cuối **OOBProductRecommendationModelPrediction** và xác định phân khúc:

   - Trường: ID sản phẩm
   - Toán tử: Giá trị
   - Giá trị: Chọn ba ID sản phẩm hàng đầu

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="Tạo một phân khúc từ kết quả mô hình.":::

Giờ đây, bạn có một phân khúc được cập nhật tự động, xác định những khách hàng sẵn sàng mua ba sản phẩm được đề xuất nhiều nhất 

Để biết thêm thông tin, hãy xem [Tạo và quản lý phân khúc](segments.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]
