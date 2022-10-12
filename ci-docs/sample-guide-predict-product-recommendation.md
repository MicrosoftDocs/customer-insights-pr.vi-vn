---
title: Hướng dẫn mẫu dự đoán đề xuất sản phẩm
description: Sử dụng hướng dẫn mẫu này để thử mô hình dự đoán đề xuất sản phẩm dùng ngay.
ms.date: 09/19/2022
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
ms.openlocfilehash: 2b42a89e3f4ec8cf4f0769128b8536973365f1cb
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610170"
---
# <a name="product-recommendation-prediction-sample-guide"></a>Hướng dẫn mẫu dự đoán đề xuất sản phẩm

Hướng dẫn này sẽ hướng dẫn bạn qua một ví dụ từ đầu đến cuối về đề xuất sản phẩm dự đoán bằng cách sử dụng dữ liệu mẫu. Chúng tôi khuyên bạn nên thử dự đoán này [trong một môi trường mới](manage-environments.md).

## <a name="scenario"></a>Kịch bản

Contoso là công ty sản xuất cà phê và máy pha cà phê chất lượng cao. Họ bán sản phẩm thông qua trang web Contoso Coffee của họ. Mục tiêu là hiểu họ nên giới thiệu sản phẩm nào cho khách hàng định kỳ của họ. Biết khách hàng là ai hơn **có khả năng mua** có thể giúp họ tiết kiệm các nỗ lực tiếp thị bằng cách tập trung vào các mặt hàng cụ thể.

## <a name="prerequisites"></a>Điều kiện tiên quyết

- Ít nhất [Quyền của người đóng góp](permissions.md) trong Customer Insights.

## <a name="task-1---ingest-data"></a>Nhiệm vụ 1 - Nhập dữ liệu

Xem lại các bài báo [về việc nhập dữ liệu](data-sources.md) và [kết nối với một Power Query nguồn dữ liệu](connect-power-query.md). Thông tin sau đây giả định rằng bạn đã quen với việc nhập dữ liệu nói chung.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Nhập dữ liệu khách hàng từ nền tảng Thương mại điện tử

1. Tạo Power Query nguồn dữ liệu có tên **Thương mại điện tử** và chọn **Văn bản / CSV** kết nối.

1. Nhập URL cho địa chỉ liên hệ Thương mại điện tử:https://aka.ms/ciadclasscontacts.

1. Trong khi chỉnh sửa dữ liệu, hãy chọn **Biến đổi** và sau đó **Sử dụng hàng đầu tiên làm tiêu đề**.

1. Cập nhật kiểu dữ liệu cho các cột được liệt kê bên dưới:
   - **DateOfBirth**: Ngày
   - **CreatedOn**: Ngày/Giờ/Vùng

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Chuyển đổi ngày sinh thành ngày.":::

1. Bên trong **Tên** trên ngăn bên phải, đổi tên nguồn dữ liệu của bạn thành **eCommerceContacts**.

1. **Lưu** nguồn dữ liệu.

### <a name="ingest-online-purchase-data"></a>Nhập dữ liệu mua hàng trực tuyến

1. Thêm một tập hợp dữ liệu khác vào cùng một nguồn dữ liệu **Thương mại điện tử**. Chọn lại trình kết nối **Văn bản/CSV**.

1. Nhập URL cho dữ liệu mua hàng trực tuyến https://aka.ms/ciadclassonline.

1. Trong khi chỉnh sửa dữ liệu, hãy chọn **Biến đổi** và sau đó **Sử dụng hàng đầu tiên làm tiêu đề**.

1. Cập nhật kiểu dữ liệu cho các cột được liệt kê bên dưới:
   - **PurchasedOn**: Ngày/Giờ
   - **TotalPrice**: Tiền tệ

1. Bên trong **Tên** trong khung bên, đổi tên nguồn dữ liệu của bạn thành **eCommercePurchases**.

1. **Lưu** nguồn dữ liệu.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Nhập dữ liệu khách hàng từ lược đồ khách hàng thân thiết

1. Tạo nguồn dữ liệu có tên **Kế hoạch trung thành** và chọn **Văn bản / CSV** kết nối.

1. Nhập URL cho khách hàng trung thành https://aka.ms/ciadclasscustomerloyalty.

1. Trong khi chỉnh sửa dữ liệu, hãy chọn **Biến đổi** và sau đó **Sử dụng hàng đầu tiên làm tiêu đề**.

1. Cập nhật kiểu dữ liệu cho các cột được liệt kê bên dưới:
   - **DateOfBirth**: Ngày
   - **RewardsPoints**: Số nguyên
   - **CreatedOn**: Ngày/Giờ

1. Bên trong **Tên** trên ngăn bên phải, đổi tên nguồn dữ liệu của bạn thành **loyCustomers**.

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

## <a name="task-4---configure-product-recommendation-prediction"></a>Nhiệm vụ 4 - Định cấu hình dự đoán đề xuất sản phẩm

Với các hồ sơ khách hàng hợp nhất tại chỗ và hoạt động đã được tạo, hãy chạy đề xuất sản phẩm dự đoán.

1. Đi đến **Sự thông minh** > **Phỏng đoán**.

1. Trên **Tạo ra** tab, chọn **Sử dụng mô hình** trên **Đề xuất sản phẩm (xem trước)** ngói.

1. Chọn **Bắt đầu**.

1. Đặt tên cho mô hình **Dự đoán Mô hình Đề xuất Sản phẩm OOB** và thực thể đầu ra **OOBProductRecommendationModelPrediction**.

1. Chọn **Tiếp theo**.

1. Xác định tùy chọn mô hình:
   - **Số lượng sản phẩm** :**5** để xác định số lượng sản phẩm bạn muốn giới thiệu cho khách hàng của mình.
   - **Các giao dịch mua lặp lại dự kiến** :**Đúng** để đưa các sản phẩm đã mua trước đó vào đề xuất.
   - **Cửa sổ nhìn lại:** **365 ngày** để xác định xem mô hình sẽ nhìn lại bao xa trước khi đề xuất sản phẩm một lần nữa.

   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Tùy chọn mô hình cho mô hình đề xuất sản phẩm.":::

1. Chọn **Tiếp theo**.

1. Bên trong **Thêm lịch sử mua hàng** bước, chọn **Thêm dữ liệu**.

1. Lựa chọn **SalesOrderLine** và thực thể eCommercePurchases và chọn **Tiếp theo**. Dữ liệu cần thiết được tự động điền vào từ hoạt động. Lựa chọn **Tiết kiệm** và sau đó **Tiếp theo**.

1. Bỏ qua **Thêm thông tin sản phẩm** và **Bộ lọc sản phẩm** bởi vì chúng tôi không có dữ liệu thông tin sản phẩm.

1. Bên trong **Cập nhật dữ liệu** bước, chọn **Hàng tháng** cho lịch trình mô hình.

1. Chọn **Tiếp theo**.

1. Sau khi xem lại tất cả thông tin chi tiết, hãy chọn **Lưu và chạy**.

## <a name="task-5---review-model-results-and-explanations"></a>Nhiệm vụ 5 - Xem xét kết quả và giải thích mô hình

Để mô hình hoàn thành việc đào tạo và chấm điểm dữ liệu. Xem lại [giải thích mô hình đề xuất sản phẩm](predict-transactional-churn.md#view-prediction-results).

## <a name="task-6---create-a-segment-of-high-purchased-products"></a>Nhiệm vụ 6 - Tạo phân khúc sản phẩm được mua nhiều

Việc chạy mô hình sẽ tạo một thực thể mới, được liệt kê trên phần **Dữ liệu** > **Thực thể**. Bạn có thể tạo một phân khúc mới dựa trên thực thể được tạo bởi mô hình.

1. Trên trang kết quả, hãy chọn **Tạo phân khúc**.

1. Tạo quy tắc bằng cách sử dụng **OOBProductRecommendationModelPrediction** thực thể và xác định phân đoạn:
   - **Đồng ruộng** : ID sản phẩm
   - **Giá trị** : Chọn ba ID sản phẩm hàng đầu

1. Lựa chọn **Tiết kiệm** và **Chạy** phân khúc.

Giờ đây, bạn có một phân đoạn được cập nhật động, xác định những khách hàng có thể quan tâm đến việc mua năm sản phẩm được đề xuất nhiều nhất. Để biết thêm thông tin, hãy xem [Tạo và quản lý phân khúc](segments.md).

> [!TIP]
> Bạn cũng có thể tạo phân đoạn cho mô hình dự đoán từ **Phân đoạn** trang bằng cách chọn **Mới** và lựa chọn **Tạo từ** > **Sự thông minh**. Để biết thêm thông tin, hãy xem [Tạo một phân đoạn mới với các phân đoạn nhanh chóng](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
