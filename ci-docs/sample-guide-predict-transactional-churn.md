---
title: Hướng dẫn mẫu dự đoán rời bỏ giao dịch
description: Sử dụng hướng dẫn mẫu này để thử mô hình dự đoán rời bỏ giao dịch dùng ngay.
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0ccc32b6e5e96adf6f2fa8c6d52960a07d1513f3
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609711"
---
# <a name="transactional-churn-prediction-sample-guide"></a>Hướng dẫn mẫu dự đoán rời bỏ giao dịch

Hướng dẫn này sẽ giải thích cho bạn một ví dụ từ đầu đến cuối về churn giao dịch dự đoán bằng cách sử dụng dữ liệu mẫu. Chúng tôi khuyên bạn nên thử dự đoán này [trong một môi trường mới](manage-environments.md).

## <a name="scenario"></a>Kịch bản

Contoso là công ty sản xuất cà phê và máy pha cà phê chất lượng cao. Họ bán sản phẩm thông qua trang web Contoso Coffee của họ. Mục tiêu là biết những khách hàng nào thường mua sản phẩm của họ một cách thường xuyên, sẽ không còn là khách hàng tích cực trong 60 ngày tới. Biết khách hàng nào **có khả năng rời bỏ**, có thể giúp họ tiết kiệm các nỗ lực tiếp thị bằng cách tập trung vào việc giữ chân họ.

## <a name="prerequisites"></a>Điều kiện tiên quyết

- Tối thiểu [Quyền của cộng tác viên](permissions.md).

## <a name="task-1---ingest-data"></a>Nhiệm vụ 1 - Nhập dữ liệu

Xem lại các bài báo [về việc nhập dữ liệu](data-sources.md) và [kết nối với một Power Query nguồn dữ liệu](connect-power-query.md). Thông tin sau đây giả định rằng bạn đã quen với việc nhập dữ liệu nói chung.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Nhập dữ liệu khách hàng từ nền tảng Thương mại điện tử

1. Tạo nguồn dữ liệu có tên **Thương mại điện tử** và chọn **Văn bản / CSV** kết nối.

1. Nhập URL cho các liên hệ Thương mại điện tử https://aka.ms/ciadclasscontacts.

1. Trong khi chỉnh sửa dữ liệu, hãy chọn **Biến đổi** và sau đó **Sử dụng hàng đầu tiên làm tiêu đề**.

1. Cập nhật kiểu dữ liệu cho các cột được liệt kê bên dưới:

   - **DateOfBirth**: Ngày
   - **CreatedOn**: Ngày/Giờ/Vùng

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Chuyển đổi DoB thành Ngày.":::

1. Bên trong **Tên** trên ngăn bên phải, đổi tên nguồn dữ liệu của bạn thành **eCommerceContacts**

1. Lưu nguồn dữ liệu.

### <a name="ingest-online-purchase-data"></a>Nhập dữ liệu mua hàng trực tuyến

1. Thêm một tập hợp dữ liệu khác vào cùng một nguồn dữ liệu **Thương mại điện tử**. Chọn lại trình kết nối **Văn bản/CSV**.

1. Nhập URL cho dữ liệu mua hàng trực tuyến https://aka.ms/ciadclassonline.

1. Trong khi chỉnh sửa dữ liệu, hãy chọn **Biến đổi** và sau đó **Sử dụng hàng đầu tiên làm tiêu đề**.

1. Cập nhật kiểu dữ liệu cho các cột được liệt kê bên dưới:

   - **PurchasedOn**: Ngày/Giờ
   - **TotalPrice**: Tiền tệ

1. Bên trong **Tên** trên ngăn bên phải, đổi tên nguồn dữ liệu của bạn thành **eCommercePurchases**.

1. Lưu nguồn dữ liệu.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Nhập dữ liệu khách hàng từ lược đồ khách hàng thân thiết

1. Tạo nguồn dữ liệu có tên **Kế hoạch trung thành** và chọn **Văn bản / CSV** kết nối.

1. Nhập URL cho các liên hệ Thương mại điện tử https://aka.ms/ciadclasscustomerloyalty.

1. Trong khi chỉnh sửa dữ liệu, hãy chọn **Biến đổi** và sau đó **Sử dụng hàng đầu tiên làm tiêu đề**.

1. Cập nhật kiểu dữ liệu cho các cột được liệt kê bên dưới:

   - **DateOfBirth**: Ngày
   - **RewardsPoints**: Số nguyên
   - **CreatedOn**: Ngày/Giờ

1. Bên trong **Tên** trên ngăn bên phải, đổi tên nguồn dữ liệu của bạn thành **loyCustomers**.

1. Lưu nguồn dữ liệu.

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

## <a name="task-4---configure-transaction-churn-prediction"></a>Nhiệm vụ 4 - Định cấu hình dự đoán rời bỏ giao dịch

Với hồ sơ khách hàng hợp nhất tại chỗ và hoạt động, hãy chạy giao dịch churn dự đoán.

1. Đi đến **Sự thông minh** > **Phỏng đoán**.

1. Trên **Tạo ra** tab, chọn **Sử dụng mô hình** trên **Mô hình churn khách hàng**.

1. Lựa chọn **Giao dịch** cho kiểu churn và sau đó **Bắt đầu**.

1. Đặt tên cho mô hình **Dự đoán rời bỏ giao dịch thương mại điện tử OOB** và thực thể đầu ra **OOBeCommerceChurnPrediction**.

1. Chọn **Tiếp theo**.

1. Xác định tùy chọn mô hình:

   - **dự đoán cửa sổ** :**60** ngày để xác định khoảng cách trong tương lai mà chúng tôi muốn dự đoán thời gian nghỉ của khách hàng.

   - **Định nghĩa Churn** :**60** số ngày để cho biết khoảng thời gian không mua hàng mà sau đó khách hàng được coi là bỏ qua.

     :::image type="content" source="media/model-levers.PNG" alt-text="Chọn tùy chọn mô hình dự đoán Cửa sổ và Định nghĩa Churn.":::

1. Chọn **Tiếp theo**.

1. Chọn **Lịch sử mua hàng (bắt buộc)** và chọn **Thêm dữ liệu** cho lịch sử mua hàng.

1. Lựa chọn **SalesOrderLine** và thực thể eCommercePurchases và chọn **Tiếp theo**. Dữ liệu cần thiết được tự động điền vào từ hoạt động. Lựa chọn **Tiết kiệm** và sau đó **Tiếp theo**.

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="Tham gia các thực thể thương mại điện tử.":::

1. Bỏ qua **Dữ liệu bổ sung (tùy chọn)** bươc.

1. Bên trong **Cập nhật dữ liệu** bước, chọn **Hàng tháng** cho lịch trình mô hình.

1. Sau khi xem lại tất cả thông tin chi tiết, hãy chọn **Lưu và chạy**.

## <a name="task-5---review-model-results-and-explanations"></a>Nhiệm vụ 5 - Xem xét kết quả và giải thích mô hình

Để mô hình hoàn thành việc đào tạo và chấm điểm dữ liệu. Xem lại các giải thích mô hình churn. Để biết thêm thông tin, hãy xem [Xem kết quả dự đoán](predict-transactional-churn.md#view-prediction-results).

## <a name="task-6---create-a-segment-of-high-churn-risk-customers"></a>Nhiệm vụ 6 - Tạo một phân khúc khách hàng có nguy cơ rời bỏ cao

Việc chạy mô hình sản xuất sẽ tạo ra một thực thể mới, được liệt kê trên **Dữ liệu** > **Thực thể**. Bạn có thể tạo một phân khúc mới dựa trên thực thể được tạo bởi mô hình.

1. Trên trang kết quả, hãy chọn **Tạo phân khúc**.

1. Tạo quy tắc bằng cách sử dụng **OOBeCommerceChurnPrediction** thực thể và xác định phân đoạn:
   - **Đồng ruộng** : ChurnScore
   - **Nhà điều hành** : lớn hơn
   - **Giá trị** : 0,6

1. Lựa chọn **Tiết kiệm** và **Chạy** phân khúc.

Giờ đây, bạn có một phân đoạn được cập nhật động để xác định những khách hàng có nguy cơ bỏ trốn cao. Để biết thêm thông tin, hãy xem [Tạo và quản lý phân khúc](segments.md).

> [!TIP]
> Bạn cũng có thể tạo phân đoạn cho mô hình dự đoán từ **Phân đoạn** trang bằng cách chọn **Mới** và lựa chọn **Tạo từ** > **Sự thông minh**. Để biết thêm thông tin, hãy xem [Tạo một phân đoạn mới với các phân đoạn nhanh chóng](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
