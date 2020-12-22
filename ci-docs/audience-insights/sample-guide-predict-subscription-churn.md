---
title: Hướng dẫn mẫu dự đoán rời bỏ đăng ký
description: Sử dụng hướng dẫn mẫu này để thử mô hình dự đoán rời bỏ đăng ký dùng ngay.
ms.date: 11/19/2020
ms.reviewer: digranad
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 2537cfb5dde0d1ce1af16f585f0bf91d15ea1870
ms.sourcegitcommit: a6e7df90d61450e00886753eb5db116f2f35bb6c
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 12/01/2020
ms.locfileid: "4654006"
---
# <a name="subscription-churn-prediction-preview-sample-guide"></a>Hướng dẫn mẫu dự đoán rời bỏ đăng ký (bản xem trước)

Chúng tôi hướng dẫn bạn thông qua một ví dụ toàn diện về dự đoán rời bỏ đăng ký bằng cách sử dụng dữ liệu mẫu được cung cấp bên dưới. 

## <a name="scenario"></a>Kịch bản

Contoso là công ty sản xuất cà phê và máy pha cà phê chất lượng cao, họ bán thông qua trang web Contoso Coffee của mình. Gần đây, họ đã bắt đầu kinh doanh dịch vụ đăng ký cho khách hàng của mình để uống cà phê thường xuyên. Mục tiêu của họ là hiểu, những khách hàng đã đăng ký nào có thể hủy đăng ký của họ trong vài tháng tới. Biết khách hàng nào **có khả năng rời bỏ**, có thể giúp họ tiết kiệm các nỗ lực tiếp thị bằng cách tập trung vào việc giữ chân họ.

## <a name="prerequisites"></a>Điều kiện tiên quyết

- Ít nhất [Quyền của người đóng góp](permissions.md) trong Customer Insights.
- Chúng tôi khuyên bạn nên thực hiện các bước sau [trong một môi trường mới](manage-environments.md).

## <a name="task-1---ingest-data"></a>Nhiệm vụ 1 - Nhập dữ liệu

Đặc biệt, hãy xem lại các bài viết [về nhập dữ liệu](data-sources.md) và [nhập nguồn dữ liệu bằng trình kết nối Power Query](connect-power-query.md). Thông tin sau đây giả định rằng bạn đã quen với việc nhập dữ liệu nói chung. 

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Nhập dữ liệu khách hàng từ nền tảng Thương mại điện tử

1. Tạo nguồn dữ liệu có tên **Thương mại điện tử**, chọn tùy chọn nhập và chọn trình kết nối **Văn bản/CSV**.

1. Nhập URL cho các liên hệ Thương mại điện tử https://aka.ms/ciadclasscontacts.

1. Trong khi chỉnh sửa dữ liệu, hãy chọn **Chuyển đổi** và sau đó **Sử dụng hàng đầu tiên làm tiêu đề**.

1. Cập nhật kiểu dữ liệu cho các cột được liệt kê bên dưới:

   - **DateOfBirth**: Ngày
   - **CreatedOn**: Ngày/Giờ/Vùng

   [!div class="mx-imgBorder"]
   ![Chuyển đổi DoB thành Ngày](media/ecommerce-dob-date.PNG "chuyển đổi ngày sinh thành ngày")

1. Trong trường "Tên" ở ngăn bên phải, hãy đổi tên nguồn dữ liệu của bạn từ **Truy vấn** thành **eCommerceContacts**.

1. Lưu nguồn dữ liệu.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Nhập dữ liệu khách hàng từ lược đồ khách hàng thân thiết

1. Tạo nguồn dữ liệu có tên **LoyaltyScheme**, chọn tùy chọn nhập và chọn trình kết nối **Văn bản/CSV**.

1. Nhập URL cho các liên hệ Thương mại điện tử https://aka.ms/ciadclasscustomerloyalty.

1. Trong khi chỉnh sửa dữ liệu, hãy chọn **Chuyển đổi** và sau đó **Sử dụng hàng đầu tiên làm tiêu đề**.

1. Cập nhật kiểu dữ liệu cho các cột được liệt kê bên dưới:

   - **DateOfBirth**: Ngày
   - **RewardsPoints**: Số nguyên
   - **CreatedOn**: Ngày/Giờ

1. Trong trường "Tên" ở ngăn bên phải, hãy đổi tên nguồn dữ liệu của bạn từ **Truy vấn** thành **loyCustomers**.

1. Lưu nguồn dữ liệu.

### <a name="ingest-subscription-information"></a>Nhập thông tin đăng ký

1. Tạo nguồn dữ liệu có tên **SubscriptionHistory**, chọn tùy chọn nhập và chọn trình kết nối **Văn bản/CSV**.

1. Nhập URL cho các liên hệ Thương mại điện tử https://aka.ms/ciadchurnsubscriptionhistory.

1. Trong khi chỉnh sửa dữ liệu, hãy chọn **Chuyển đổi** và sau đó **Sử dụng hàng đầu tiên làm tiêu đề**.

1. Cập nhật kiểu dữ liệu cho các cột được liệt kê bên dưới:

   - **SubscriptioID**: Số nguyên
   - **SubscriptionAmount**: Đơn vị tiền tệ
   - **SubscriptionEndDate**: Ngày/Giờ
   - **SubscriptionStartDate**: Ngày/Giờ
   - **TransactionDate**: Ngày/Giờ
   - **IsRecurring**: True/False
   - **Is_auto_renew**: True/False
   - **RecurringFrequencyInMonths**: Số nguyên

1. Trong trường "Tên" ở ngăn bên phải, hãy đổi tên nguồn dữ liệu của bạn từ **Truy vấn** thành **SubscriptionHistory**.

1. Lưu nguồn dữ liệu.

### <a name="ingest-customer-data-from-website-reviews"></a>Nhập dữ liệu khách hàng từ các bài đánh giá trang web

1. Tạo nguồn dữ liệu có tên **Trang web**, chọn tùy chọn nhập và chọn trình kết nối **Văn bản/CSV**.

1. Nhập URL cho các liên hệ Thương mại điện tử https://aka.ms/ciadclasswebsite.

1. Trong khi chỉnh sửa dữ liệu, hãy chọn **Chuyển đổi** và sau đó **Sử dụng hàng đầu tiên làm tiêu đề**.

1. Cập nhật kiểu dữ liệu cho các cột được liệt kê bên dưới:

   - **ReviewRating**: Số nguyên
   - **ReviewDate**: Ngày

1. Trong trường "Tên" ở ngăn bên phải, hãy đổi tên nguồn dữ liệu của bạn từ **Truy vấn** thành **webReviews**.

## <a name="task-2---data-unification"></a>Nhiệm vụ 2 - Hợp nhất dữ liệu

Sau khi nhập dữ liệu, bây giờ chúng ta bắt đầu quy trình **Ánh xạ, So khớp, Hợp nhất** để tạo hồ sơ khách hàng hợp nhất. Để biết thêm thông tin, hãy xem [Hợp nhất dữ liệu](data-unification.md).

### <a name="map"></a>Bản đồ

1. Sau khi nhập dữ liệu, hãy ánh xạ các địa chỉ liên hệ từ dữ liệu Thương mại điện tử và Mức độ trung thành thành các loại dữ liệu phổ biến. Chuyển đến **Dữ liệu** > **Hợp nhất** > **Ánh xạ**.

1. Chọn các thực thể đại diện cho hồ sơ khách hàng – **eCommerceContacts** và **loyCustomers**. 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="hợp nhất nguồn dữ liệu thương mại điện tử và khách hàng thân thiết.":::

1. Chọn **ContactId** làm khóa chính cho **eCommerceContacts** và **LoyaltyID** làm khóa chính cho **loyCustomers**.

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="Hợp nhất LoyaltyId làm khóa chính.":::

### <a name="match"></a>So khớp

1. Đi đến tab **So khớp** và chọn **Đặt thứ tự**.

1. Trong danh sách thả xuống **Chính**, chọn **eCommerceContacts: eCommerce** là nguồn chính và bao gồm tất cả các bản ghi.

1. Trong danh sách thả xuống **Thực thể 2**, chọn **loyCustomers : LoyaltyScheme** và bao gồm tất cả các bản ghi.

   :::image type="content" source="media/unify-match-order.PNG" alt-text="Hợp nhất so khớp thương mại điện tử và khách hàng thân thiết.":::

1. Chọn **Tạo quy tắc mới**

1. Thêm điều kiện đầu tiên của bạn bằng FullName.

   * Đối với eCommerceContacts, hãy chọn **FullName** trong danh sách thả xuống.
   * Đối với loyCustomers, hãy chọn **FullName** trong danh sách thả xuống.
   * Chọn danh sách thả xuống **Chuẩn hóa** và chọn **Loại (Điện thoại, Tên, Địa chỉ, ...)**.
   * Đặt **Mức độ chính xác**: **Cơ bản** và **Giá trị**: **Cao**.

1. Nhập tên **FullName, Email** cho quy tắc mới.

   * Thêm điều kiện thứ hai cho địa chỉ email bằng cách chọn **Thêm điều kiện**
   * Đối với thực thể eCommerceContacts, hãy chọn **Email** trong danh sách thả xuống.
   * Đối với thực thể loyCustomers, hãy chọn **Email** trong danh sách thả xuống. 
   * Để trống trường Chuẩn hóa. 
   * Đặt **Mức độ chính xác**: **Cơ bản** và **Giá trị**: **Cao**.

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="Hợp nhất quy tắc so khớp cho tên và email.":::

7. Chọn **Lưu** và **Chạy**.

### <a name="merge"></a>Hợp nhất

1. Đi đến tab **Hợp nhất**.

1. Trên thực thể **ContactId** cho **loyCustomers**, thay đổi tên hiển thị thành **ContactIdLOYALTY** để phân biệt nó với các ID khác đã nhập.

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="đổi tên contactid từ id khách hàng thân thiết.":::

1. Chọn **Lưu** và **Chạy** để bắt đầu quy trình Hợp nhất.


## <a name="task-3---configure-the-subscription-churn-prediction"></a>Nhiệm vụ 3 - Định cấu hình dự đoán rời bỏ đăng ký

Với hồ sơ khách hàng hợp nhất đã có, giờ đây chúng tôi có thể chạy dự đoán rời bỏ đăng ký. Để biết các bước chi tiết, hãy xem bài viết [Dự đoán rời bỏ đăng ký (bản xem trước)](predict-subscription-churn.md). 

1. Đi đến **Thông tin** > **Khám phá** và chọn để sử dụng **Mô hình khách hàng rời đi**.

1. Chọn tùy chọn **Đăng ký** và chọn **Bắt đầu**.

1. Đặt tên cho mô hình **Dự đoán rời bỏ đăng ký OOB** và thực thể đầu ra **OOBSubscriptionChurnPrediction**.

1. Xác định hai điều kiện cho mô hình khách hàng rời đi:

   * **Số ngày kể từ khi đăng ký kết thúc**: **ít nhất 60** ngày. Nếu khách hàng không gia hạn gói đăng ký của họ trong khoảng thời gian này sau khi gói đăng ký kết thúc, thì họ sẽ được xem là đã rời đi. 

   * **Định nghĩa về tỷ lệ rời đi**: **tối thiểu 93** ngày. Khoảng thời gian mà mô hình dự đoán những khách hàng có thể rời đi. Bạn càng dự đoán xa thì kết quả càng thiếu chính xác.

     :::image type="content" source="media/model-subs-levers.PNG" alt-text="Chọn mô hình thúc đẩy khoảng thời gian dự đoán và định nghĩa về tỷ lệ rời đi.":::

1. Chọn **Thêm dữ liệu bắt buộc** và chọn **Thêm dữ liệu** cho lịch sử đăng ký.

1. Thêm thực thể **Đăng ký: SubscriptionHistory** và ánh xạ các trường từ thương mại điện tử đến các trường tương ứng theo yêu cầu của mô hình.

1. Tham gia thực thể **Đăng ký: SubscriptionHistory** với **eCommerceContacts: eCommerce**, đặt tên cho mối quan hệ **eCommerceSubscription**.

   :::image type="content" source="media/model-subscription-join.PNG" alt-text="Tham gia các thực thể thương mại điện tử.":::

1. Trong Hoạt động của khách hàng, thêm thực thể **webReviews: Website** và ánh xạ các trường từ webReviews với các trường tương ứng được yêu cầu theo mô hình. 
   - Khóa chính: ReviewId
   - Dấu thời gian: ReviewDate
   - Sự kiện: ReviewRating

1. Định cấu hình một hoạt động để đánh giá trang web. Chọn hoạt động **Đánh giá** và tham gia thực thể **webReviews: Website** với **eCommerceContacts : eCommerce**.

1. Chọn **Tiếp theo** để đặt lịch trình mô hình.

   Mô hình cần đào tạo thường xuyên để học các mẫu mới khi có dữ liệu mới được nhập vào. Đối với ví dụ này, hãy chọn **Hàng tháng**.

1. Sau khi xem xét tất cả các chi tiết, hãy chọn **Lưu và chạy**.

## <a name="task-4---review-model-results-and-explanations"></a>Nhiệm vụ 4 - Xem xét kết quả và giải thích mô hình

Để mô hình hoàn thành việc đào tạo và chấm điểm dữ liệu. Bây giờ bạn có thể xem lại giải thích mô hình rời bỏ đăng ký. Để biết thêm thông tin, hãy xem [Xem lại dự đoán trạng thái và kết quả](predict-subscription-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a>Nhiệm vụ 5 - Tạo một phân khúc khách hàng có nguy cơ rời bỏ cao

Việc chạy mô hình sản xuất sẽ tạo ra một thực thể mới mà bạn có thể thấy trong **Dữ liệu** > **Thực thể**.   

Bạn có thể tạo một phân khúc mới dựa trên thực thể được tạo bởi mô hình.

1.  Đi đến **Phân khúc**. Chọn **Mới** và chọn **Tạo từ** > **Thông tin**. 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Tạo một phân khúc với đầu ra mô hình.":::

1. Chọn điểm cuối **OOBSubscriptionChurnPrediction** và xác định phân khúc: 
   - Trường: ChurnScore
   - Toán tử: lớn hơn
   - Giá trị: 0.6
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Thiết lập phân khúc rời bỏ đăng ký.":::

Giờ đây, bạn có một phân khúc được cập nhật động để xác định những khách hàng có nguy cơ rời bỏ cao cho doanh nghiệp đăng ký này.

Để biết thêm thông tin, hãy xem [Tạo và quản lý phân khúc](segments.md).
