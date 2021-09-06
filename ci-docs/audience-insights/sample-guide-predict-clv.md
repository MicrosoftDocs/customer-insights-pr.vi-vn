---
title: Hướng dẫn mẫu về dự đoán giá trị trọn đời của khách hàng
description: Sử dụng hướng dẫn mẫu này để thử mô hình dự đoán giá trị trọn đời của khách hàng.
ms.date: 05/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: 705e159f348e876f8a2a0ad3481608c6dd380df3dd74d7e5dba9dd3bebe25e52
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 08/10/2021
ms.locfileid: "7029517"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a>Hướng dẫn mẫu về dự đoán Giá trị trọn đời của khách hàng (CLV)

Hướng dẫn này sẽ giải thích cho bạn một ví dụ chi tiết về dự đoán Giá trị trọn đời của khách hàng (CLV) trong Customer Insights bằng cách sử dụng dữ liệu mẫu.

## <a name="scenario"></a>Kịch bản

Contoso là công ty sản xuất cà phê và máy pha cà phê chất lượng cao. Họ bán sản phẩm thông qua trang web Contoso Coffee. Công ty muốn tìm hiểu giá trị (doanh thu) mà khách hàng của họ có thể tạo ra trong 12 tháng tới. Nếu biết được giá trị kỳ vọng của khách hàng trong 12 tháng tới, họ có thể hướng nỗ lực tiếp thị đến những khách hàng có giá trị cao.

## <a name="prerequisites"></a>Điều kiện tiên quyết

- Ít nhất là [quyền Cộng tác viên](permissions.md) trong thông tin chuyên sâu về đối tượng.
- Chúng tôi khuyên bạn nên thực hiện các bước sau [trong một môi trường mới](manage-environments.md).

## <a name="task-1---ingest-data"></a>Nhiệm vụ 1 - Nhập dữ liệu

Xem lại các bài viết về cách [nhập dữ liệu](data-sources.md) và [nhập nguồn dữ liệu bằng trình kết nối Power Query](connect-power-query.md). Thông tin sau đây giả định rằng bạn đã quen với việc nhập dữ liệu nói chung.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Nhập dữ liệu khách hàng từ nền tảng Thương mại điện tử

1. Tạo nguồn dữ liệu có tên **Thương mại điện tử**, chọn tùy chọn nhập và chọn trình kết nối **Văn bản/CSV**.

1. Nhập URL cho các liên hệ Thương mại điện tử [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).

1. Trong khi chỉnh sửa dữ liệu, hãy chọn **Chuyển đổi** rồi chọn **Dùng hàng đầu tiên làm tiêu đề**.

1. Cập nhật kiểu dữ liệu cho các cột được liệt kê bên dưới:
   - **DateOfBirth**: Ngày
   - **CreatedOn**: Ngày/Giờ/Vùng

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Chuyển đổi ngày sinh thành ngày.":::

1. Trong trường "Tên" ở ngăn bên phải, hãy đổi tên nguồn dữ liệu của bạn từ **Truy vấn** thành **eCommerceContacts**.

1. **Lưu** nguồn dữ liệu.

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

### <a name="ingest-customer-data-from-website-reviews"></a>Nhập dữ liệu khách hàng từ các bài đánh giá trang web

1. Tạo nguồn dữ liệu có tên **Trang web**, chọn tùy chọn nhập và chọn trình kết nối **Văn bản/CSV**.

1. Nhập URL cho các liên hệ Thương mại điện tử https://aka.ms/CI-ILT/WebReviews.

1. Trong khi chỉnh sửa dữ liệu, hãy chọn **Chuyển đổi** rồi chọn **Dùng hàng đầu tiên làm tiêu đề**.

1. Cập nhật kiểu dữ liệu cho các cột được liệt kê bên dưới:

   - **ReviewRating**: Số thập phân
   - **ReviewDate**: Ngày

1. Trong trường "Tên" ở ngăn bên phải, hãy đổi tên nguồn dữ liệu của bạn từ **Truy vấn** thành **Đánh giá**.

1. **Lưu** nguồn dữ liệu.

## <a name="task-2---data-unification"></a>Nhiệm vụ 2 - Hợp nhất dữ liệu

Sau khi nhập dữ liệu, bây giờ, chúng ta sẽ bắt đầu quá trình hợp nhất dữ liệu để tạo hồ sơ khách hàng hợp nhất. Để biết thêm thông tin, hãy xem [Hợp nhất dữ liệu](data-unification.md).

### <a name="map"></a>Bản đồ

1. Sau khi nhập dữ liệu, hãy ánh xạ các địa chỉ liên hệ từ dữ liệu Thương mại điện tử và Mức độ trung thành thành các loại dữ liệu phổ biến. Chuyển đến **Dữ liệu** > **Hợp nhất** > **Ánh xạ**.

1. Chọn các thực thể đại diện cho hồ sơ khách hàng – **eCommerceContacts** và **loyCustomers**. Sau đó, chọn **Áp dụng**.

   ![hợp nhất nguồn dữ liệu thương mại điện tử và khách hàng thân thiết.](media/unify-ecommerce-loyalty.png)

1. Chọn **ContactId** làm khóa chính cho **eCommerceContacts** và **LoyaltyID** làm khóa chính cho **loyCustomers**.

   ![Hợp nhất LoyaltyId làm khóa chính.](media/unify-loyaltyid.png)

1. Chọn **Lưu**.

### <a name="match"></a>Kết quả khớp

1. Đi đến tab **So khớp** và chọn **Đặt thứ tự**.

1. Trong danh sách thả xuống **Chính**, chọn **eCommerceContacts: eCommerce** là nguồn chính và bao gồm tất cả các bản ghi.

1. Trong danh sách thả xuống **Thực thể 2**, chọn **loyCustomers: LoyaltyScheme** và bao gồm tất cả các bản ghi.

   ![Hợp nhất so khớp thương mại điện tử và khách hàng thân thiết.](media/unify-match-order.png)

1. Chọn **Thêm quy tắc**

1. Thêm điều kiện đầu tiên của bạn bằng FullName.

   - Đối với eCommerceContacts, chọn **FullName** trong danh sách thả xuống.
   - Đối với loyCustomers, chọn **FullName** trong danh sách thả xuống.
   - Chọn danh sách thả xuống **Chuẩn hóa** rồi chọn **Loại (Số điện thoại, Tên, Địa chỉ,...)**.
   - Đặt **Mức độ chính xác**: **Cơ bản** và **Giá trị**: **Cao**.

1. Nhập tên **FullName, Email** cho quy tắc mới.

   - Thêm điều kiện thứ hai cho địa chỉ email bằng cách chọn **Thêm điều kiện**
   - Đối với thực thể eCommerceContacts, chọn **EMail** trong danh sách thả xuống.
   - Đối với thực thể loyCustomers, chọn **EMail** trong danh sách thả xuống.
   - Để trống trường Chuẩn hóa.
   - Đặt **Mức độ chính xác**: **Cơ bản** và **Giá trị**: **Cao**.

   ![Hợp nhất quy tắc so khớp cho tên và email.](media/unify-match-rule.png)

1. Chọn **Xong**.

1. Chọn **Lưu** và **Chạy**.

### <a name="merge"></a>Hợp nhất

1. Đi đến tab **Hợp nhất**.

1. Trên thực thể **ContactId** cho **loyCustomers**, thay đổi tên hiển thị thành **ContactIdLOYALTY** để phân biệt nó với các ID khác đã nhập.

   ![đổi tên contactid từ id khách hàng thân thiết.](media/unify-merge-contactid.png)

1. Chọn **Lưu** và **Chạy quy trình hợp nhất và xuôi dòng**.

## <a name="task-3---configure-customer-lifetime-value-prediction"></a>Nhiệm vụ 3 - Định cấu hình dự đoán giá trị trọn đời của khách hàng

Sau khi có hồ sơ khách hàng hợp nhất, bây giờ, chúng ta có thể chạy dự đoán giá trị trọn đời của khách hàng. Để biết các bước chi tiết, hãy xem bài viết [Dự đoán Giá trị trọn đời của khách hàng (xem trước)](predict-customer-lifetime-value.md).

1. Chuyển đến phần **Thông tin**  > **Dự đoán** rồi chọn **Mô hình giá trị trọn đời của khách hàng**.

1. Xem qua thông tin ở ngăn bên rồi chọn **Bắt đầu**.

1. Đặt tên cho mô hình là **OOB eCommerce CLV Prediction** và thực thể đầu ra là **OOBeCommerceCLVPrediction**.

1. Xác định các tùy chọn mô hình cho mô hình CLV:
   - **Khoảng thời gian dự đoán**: **12 tháng hoặc 1 năm**. Tùy chọn thiết đặt này xác định khoảng thời gian trong tương lai để dự đoán giá trị trọn đời của khách hàng.
   - **Khách hàng hiện hoạt**: Chỉ định những khách hàng hiện hoạt có ý nghĩa đối với doanh nghiệp của bạn. Đặt khung thời gian trong quá khứ mà khách hàng phải có ít nhất một giao dịch để được coi là hiện hoạt. Mô hình sẽ chỉ dự đoán CLV cho những khách hàng hiện hoạt. Bạn có thể chọn tùy chọn để mô hình tính toán khoảng thời gian dựa trên dữ liệu giao dịch trước đây hoặc cung cấp một khung thời gian cụ thể. Trong hướng dẫn mẫu này, chúng ta dùng tùy chọn mặc định là **để mô hình tính toán khoảng thời gian mua hàng**.
   - **Khách hàng có giá trị cao**: Xác định khách hàng có giá trị cao dưới dạng phân vị phần trăm của những khách hàng chi tiêu nhiều nhất. Mô hình sẽ dùng dữ liệu đầu vào này để đưa ra kết quả phù hợp với định nghĩa kinh doanh của bạn về khách hàng có giá trị cao. Bạn có thể chọn để mô hình xác định khách hàng có giá trị cao. Mô hình sẽ sử dụng quy tắc suy nghiệm để lấy phân vị phần trăm. Bạn cũng có thể xác định khách hàng có giá trị cao dưới dạng phân vị phần trăm của những khách hàng chi tiêu nhiều nhất trong tương lai. Trong hướng dẫn mẫu này, chúng ta xác định theo cách thủ công khách hàng có giá trị cao là **30% khách hàng thanh toán hiện hoạt** rồi chọn **Tiếp theo**.

    :::image type="content" source="media/clv-model-preferences.png" alt-text="Bước chọn Tùy chọn trong trải nghiệm có hướng dẫn cho mô hình CLV.":::

1. Trong bước **Dữ liệu bắt buộc**, hãy chọn **Thêm dữ liệu** để cung cấp dữ liệu giao dịch trước đây.

1. Thêm thực thể **eCommercePurchases : eCommerce** và ánh xạ các thuộc tính theo yêu cầu của mô hình:
   - ID giao dịch: eCommerce.eCommercePurchases.PurchaseId
   - Ngày giao dịch: eCommerce.eCommercePurchases.PurchasedOn
   - Số tiền giao dịch: eCommerce.eCommercePurchases.TotalPrice
   - ID sản phẩm: eCommerce.eCommercePurchases.ProductId

1. Chọn **Tiếp theo**.

1. Thiết lập mối quan hệ giữa thực thể **eCommercePurchases : eCommerce** và **eCommerceContacts : eCommerce**.

1. Bước **Dữ liệu bổ sung (không bắt buộc)** cho phép bạn bổ sung thêm dữ liệu hoạt động của khách hàng. Dữ liệu này có thể giúp tạo thêm thông tin chuyên sâu về hoạt động tương tác của khách hàng với doanh nghiệp của bạn và có thể hữu ích cho CLV. Việc thêm các hoạt động tương tác chính của khách hàng như nhật ký web, nhật ký dịch vụ khách hàng hoặc lịch sử chương trình tặng thưởng có thể cải thiện độ chính xác của dự đoán. Chọn **Thêm dữ liệu** để bổ sung thêm dữ liệu hoạt động của khách hàng.

1. Thêm thực thể hoạt động của khách hàng và ánh xạ tên các trường của thực thể này đến các trường tương ứng theo yêu cầu của mô hình:
   - Thực thể hoạt động của khách hàng: Reviews:Website
   - Khóa chính: Website.Reviews.ReviewId
   - Dấu thời gian: Website.Reviews.ReviewDate
   - Sự kiện (tên hoạt động): Website.Reviews.ActivityTypeDisplay
   - Chi tiết (số lượng hoặc giá trị): Website.Reviews.ReviewRating

1. Chọn **Tiếp theo** rồi định cấu hình hoạt động và mối quan hệ giữa dữ liệu giao dịch và dữ liệu khách hàng:  
   - Loại hoạt động: Chọn mục hiện có
   - Nhãn hoạt động: Đánh giá
   - Nhãn tương ứng: Website.Reviews.UserId
   - Thực thể khách hàng: eCommerceContacts:eCommerce
   - Mối quan hệ: WebsiteReviews

1. Chọn **Tiếp theo** để đặt lịch trình mô hình.

   Mô hình cần được đào tạo thường xuyên để học các mẫu mới khi có dữ liệu mới được nhập vào. Đối với ví dụ này, hãy chọn **Hàng tháng**.

1. Sau khi xem lại tất cả thông tin chi tiết, hãy chọn **Lưu và chạy**.

## <a name="task-4---review-model-results-and-explanations"></a>Nhiệm vụ 4 - Xem xét kết quả và giải thích mô hình

Để mô hình hoàn thành việc đào tạo và chấm điểm dữ liệu. Tiếp theo, bạn có thể xem xét kết quả và phần giải thích mô hình CLV. Để biết thêm thông tin, hãy xem [Xem lại dự đoán trạng thái và kết quả](predict-customer-lifetime-value.md#review-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-value-customers"></a>Nhiệm vụ 5 - Tạo phân khúc khách hàng có giá trị cao

Việc chạy mô hình sẽ tạo một thực thể mới, được liệt kê trên phần **Dữ liệu** > **Thực thể**. Bạn có thể tạo phân khúc khách hàng mới dựa trên thực thể do mô hình tạo.

1. Đi đến **Phân khúc**. 

1. Chọn **Mới** rồi chọn **Tạo từ** > **Thông tin**.

   ![Tạo một phân khúc với đầu ra mô hình.](media/segment-intelligence.png)

1. Chọn thực thể **OOBeCommerceCLVPrediction** và xác định phân khúc:
  - Trường: CLVScore
  - Toán tử: lớn hơn
  - Giá trị: 1500

1. Chọn **Đánh giá** và **Lưu** phân khúc.

Giờ đây, bạn có một phân khúc xác định những khách hàng được dự đoán sẽ tạo ra doanh thu hơn $1500 trong 12 tháng tới. Phân khúc này sẽ được cập nhật động nếu bạn nhập thêm dữ liệu.

Để biết thêm thông tin, hãy xem [Tạo và quản lý phân khúc](segments.md).
