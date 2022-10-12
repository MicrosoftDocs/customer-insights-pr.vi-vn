---
title: Hướng dẫn mẫu về dự đoán Giá trị trọn đời của khách hàng (CLV)
description: Sử dụng hướng dẫn mẫu này để thử mô hình dự đoán giá trị trọn đời của khách hàng.
ms.date: 09/15/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: fec43b279326daa17fb179181f5e310c99d48bb7
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609664"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a>Hướng dẫn mẫu về dự đoán Giá trị trọn đời của khách hàng (CLV)

Hướng dẫn này sẽ hướng dẫn bạn một ví dụ tổng thể về giá trị lâu dài của Khách hàng (CLV) dự đoán trong Thông tin chi tiết về khách hàng bằng cách sử dụng dữ liệu mẫu. Chúng tôi khuyên bạn nên thử dự đoán này [trong một môi trường mới](manage-environments.md).

## <a name="scenario"></a>Kịch bản

Contoso là công ty sản xuất cà phê và máy pha cà phê chất lượng cao. Họ bán sản phẩm thông qua trang web Contoso Coffee của họ. Công ty muốn tìm hiểu giá trị (doanh thu) mà khách hàng của họ có thể tạo ra trong 12 tháng tới. Nếu biết được giá trị kỳ vọng của khách hàng trong 12 tháng tới, họ có thể hướng nỗ lực tiếp thị đến những khách hàng có giá trị cao.

## <a name="prerequisites"></a>Điều kiện tiên quyết

- Tối thiểu [Quyền của cộng tác viên](permissions.md).

## <a name="task-1---ingest-data"></a>Nhiệm vụ 1 - Nhập dữ liệu

Xem lại các bài báo [về việc nhập dữ liệu](data-sources.md) và [kết nối với một Power Query nguồn dữ liệu](connect-power-query.md). Thông tin sau đây giả định rằng bạn đã quen với việc nhập dữ liệu nói chung.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Nhập dữ liệu khách hàng từ nền tảng Thương mại điện tử

1. Tạo Power Query nguồn dữ liệu có tên **Thương mại điện tử** và chọn **Văn bản / CSV** kết nối.

1. Nhập URL cho các liên hệ Thương mại điện tử https://aka.ms/ciadclasscontacts.

1. Trong khi chỉnh sửa dữ liệu, hãy chọn **Biến đổi** và sau đó **Sử dụng hàng đầu tiên làm tiêu đề**.

1. Cập nhật kiểu dữ liệu cho các cột được liệt kê bên dưới:
   - **DateOfBirth**: Ngày
   - **CreatedOn**: Ngày/Giờ/Vùng

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Chuyển đổi ngày sinh thành ngày.":::

1. Bên trong **Tên** trên ngăn bên phải, đổi tên nguồn dữ liệu của bạn thành **eCommerceContacts**

1. **Lưu** nguồn dữ liệu.

### <a name="ingest-online-purchase-data"></a>Nhập dữ liệu mua hàng trực tuyến

1. Thêm một tập hợp dữ liệu khác vào cùng một nguồn dữ liệu **Thương mại điện tử**. Chọn lại trình kết nối **Văn bản/CSV**.

1. Nhập URL cho dữ liệu **Mua hàng trực tuyến** https://aka.ms/ciadclassonline.

1. Trong khi chỉnh sửa dữ liệu, hãy chọn **Biến đổi** và sau đó **Sử dụng hàng đầu tiên làm tiêu đề**.

1. Cập nhật kiểu dữ liệu cho các cột được liệt kê bên dưới:
   - **PurchasedOn**: Ngày/Giờ
   - **TotalPrice**: Tiền tệ

1. Bên trong **Tên** trong khung bên, đổi tên nguồn dữ liệu của bạn thành **eCommercePurchases**.

1. **Lưu** nguồn dữ liệu.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Nhập dữ liệu khách hàng từ lược đồ khách hàng thân thiết

1. Tạo nguồn dữ liệu có tên **Kế hoạch trung thành** và chọn **Văn bản / CSV** kết nối.

1. Nhập URL cho khách hàng thân thiết https://aka.ms/ciadclasscustomerloyalty.

1. Trong khi chỉnh sửa dữ liệu, hãy chọn **Biến đổi** và sau đó **Sử dụng hàng đầu tiên làm tiêu đề**.

1. Cập nhật kiểu dữ liệu cho các cột được liệt kê bên dưới:
   - **DateOfBirth**: Ngày
   - **RewardsPoints**: Số nguyên
   - **CreatedOn**: Ngày/Giờ

1. Bên trong **Tên** trên ngăn bên phải, đổi tên nguồn dữ liệu của bạn thành **loyCustomers**.

1. **Lưu** nguồn dữ liệu.

### <a name="ingest-customer-data-from-website-reviews"></a>Nhập dữ liệu khách hàng từ các bài đánh giá trang web

1. Tạo nguồn dữ liệu có tên **Trang mạng** và chọn **Văn bản / CSV** kết nối.

1. Nhập URL để xem lại trang web https://aka.ms/CI-ILT/WebReviews.

1. Trong khi chỉnh sửa dữ liệu, hãy chọn **Biến đổi** và sau đó **Sử dụng hàng đầu tiên làm tiêu đề**.

1. Cập nhật kiểu dữ liệu cho các cột được liệt kê bên dưới:
   - **ReviewRating**: Số thập phân
   - **ReviewDate**: Ngày

1. Bên trong **Tên** trên ngăn bên phải, đổi tên nguồn dữ liệu của bạn thành **Nhận xét**.

1. **Lưu** nguồn dữ liệu.

## <a name="task-2---data-unification"></a>Nhiệm vụ 2 - Hợp nhất dữ liệu

Xem lại bài báo [về hợp nhất dữ liệu](data-unification.md). Thông tin sau đây giả định rằng bạn đã quen với việc hợp nhất dữ liệu nói chung.

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---create-transaction-history-activity"></a>Nhiệm vụ 3 - Tạo hoạt động lịch sử giao dịch

Xem lại bài báo [về các hoạt động của khách hàng](activities.md). Thông tin sau đây giả định rằng bạn đã quen với việc tạo các hoạt động nói chung.

1. Tạo một hoạt động được gọi là **eCommercePurchases** với *eCommercePurchases: eCommerce* thực thể và khóa chính của nó, **PurchaseId**.

1. Tạo mối quan hệ giữa *eCommercePurchases: eCommerce* và *eCommerceLiên hệ: eCommerce* với **ID liên hệ** làm khóa ngoại để kết nối hai thực thể.

1. Lựa chọn **Tổng giá** cho **EventActivity** và **Đã mua** cho **TimeStamp**.

1. Lựa chọn **SalesOrderLine** cho **Loại hoạt động** và lập bản đồ ngữ nghĩa dữ liệu hoạt động.

1. Chạy hoạt động.

1. Thêm một hoạt động khác và ánh xạ tên các trường của nó vào các trường tương ứng:
   - **Thực thể hoạt động** : Nhận xét: Trang web
   - **Khóa chính** : ReviewId
   - **Dấu thời gian** : ReviewDate
   - **Hoạt động sự kiện** : ActivityTypeDisplay
   - **Chi tiết bổ sung** : Đánh giá
   - **Loại hoạt động** : Kiểm tra lại

1. Chạy hoạt động.

## <a name="task-4---configure-customer-lifetime-value-prediction"></a>Nhiệm vụ 4 - Định cấu hình dự đoán giá trị trọn đời của khách hàng

Với hồ sơ khách hàng hợp nhất tại chỗ và hoạt động được tạo, hãy chạy giá trị lâu dài của khách hàng (CLV) dự đoán. Để biết các bước chi tiết, hãy xem [Giá trị lâu dài của khách hàng dự đoán](predict-customer-lifetime-value.md).

1. Đi đến **Sự thông minh** > **Phỏng đoán**.

1. Trên **Tạo ra** tab, chọn **Sử dụng mô hình** trên **Giá trị lâu dài của khách hàng** ngói.

1. Chọn **Bắt đầu**.

1. Đặt tên cho mô hình là **OOB eCommerce CLV Prediction** và thực thể đầu ra là **OOBeCommerceCLVPrediction**.

1. Xác định tùy chọn mô hình:
   - **dự đoán khoảng thời gian** :**12 tháng hoặc 1 năm** để xác định khoảng cách trong tương lai để dự đoán CLV.
   - **Khách hàng năng động** :**Để mô hình tính toán khoảng thời gian mua hàng** là khung thời gian mà khách hàng phải có ít nhất một giao dịch để được coi là đang hoạt động.
   - **Khách hàng giá trị cao** : xác định thủ công những khách hàng có giá trị cao là **30% khách hàng tích cực hàng đầu**.

    :::image type="content" source="media/clv-model-preferences.png" alt-text="Bước chọn Tùy chọn trong trải nghiệm có hướng dẫn cho mô hình CLV.":::

1. Chọn **Tiếp theo**.

1. Trong bước **Dữ liệu bắt buộc**, hãy chọn **Thêm dữ liệu** để cung cấp dữ liệu giao dịch trước đây.

    :::image type="content" source="media/clv-model-required.png" alt-text="Thêm bước dữ liệu bắt buộc trong trải nghiệm được hướng dẫn cho mô hình CLV.":::

1. Lựa chọn **SalesOrderLine** và thực thể eCommercePurchases và chọn **Tiếp theo**. Dữ liệu cần thiết được tự động điền vào từ hoạt động. Lựa chọn **Tiết kiệm** và sau đó **Tiếp theo**.

1. Các **Dữ liệu bổ sung (tùy chọn)** cho phép bạn thêm nhiều dữ liệu hoạt động của khách hàng để có thêm thông tin chi tiết về các tương tác của khách hàng. Đối với ví dụ này, hãy chọn **Thêm dữ liệu** và thêm hoạt động đánh giá web.

1. Chọn **Tiếp theo**.

1. Bên trong **Cập nhật dữ liệu** bước, chọn **Hàng tháng** cho lịch trình mô hình.

1. Chọn **Tiếp theo**.

1. Sau khi xem lại tất cả thông tin chi tiết, hãy chọn **Lưu và chạy**.

## <a name="task-5---review-model-results-and-explanations"></a>Nhiệm vụ 5 - Xem xét kết quả và giải thích mô hình

Để mô hình hoàn thành việc đào tạo và chấm điểm dữ liệu. Xem lại [Kết quả và giải thích mô hình CLV](predict-customer-lifetime-value.md#view-prediction-results).

## <a name="task-6---create-a-segment-of-high-value-customers"></a>Nhiệm vụ 6 - Tạo phân khúc khách hàng có giá trị cao

Việc chạy mô hình sẽ tạo một thực thể mới, được liệt kê trên phần **Dữ liệu** > **Thực thể**. Bạn có thể tạo phân khúc khách hàng mới dựa trên thực thể do mô hình tạo.

1. Trên trang kết quả, hãy chọn **Tạo phân khúc**.

1. Tạo quy tắc bằng cách sử dụng **OOBeCommerceCLVPrediction** thực thể và xác định phân đoạn:
   - **Đồng ruộng** : CLVScore
   - **Nhà điều hành** : lớn hơn
   - **Giá trị** : 1500

1. Lựa chọn **Tiết kiệm** và **Chạy** phân khúc.

Giờ đây, bạn có một phân khúc xác định những khách hàng được dự đoán sẽ tạo ra doanh thu hơn $1500 trong 12 tháng tới. Phân khúc này sẽ được cập nhật động nếu bạn nhập thêm dữ liệu. Để biết thêm thông tin, hãy xem [Tạo và quản lý phân khúc](segments.md).

> [!TIP]
> Bạn cũng có thể tạo phân đoạn cho mô hình dự đoán từ **Phân đoạn** trang bằng cách chọn **Mới** và lựa chọn **Tạo từ** > **Sự thông minh**. Để biết thêm thông tin, hãy xem [Tạo một phân đoạn mới với các phân đoạn nhanh chóng](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
