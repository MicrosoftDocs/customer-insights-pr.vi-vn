---
title: Hướng dẫn mẫu dự đoán rời bỏ đăng ký
description: Sử dụng hướng dẫn mẫu này để thử mô hình dự đoán rời bỏ đăng ký dùng ngay.
ms.date: 09/19/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-create-prediction
- customerInsights
ms.openlocfilehash: 7e754be9a2cb9450949c6b3667bbd37aa39cf0bf
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610032"
---
# <a name="subscription-churn-prediction-sample-guide"></a>Hướng dẫn mẫu dự đoán rời bỏ đăng ký

Hướng dẫn này sẽ giải thích cho bạn một ví dụ từ đầu đến cuối về churn đăng ký dự đoán bằng cách sử dụng dữ liệu mẫu. Chúng tôi khuyên bạn nên thử dự đoán này [trong một môi trường mới](manage-environments.md).

## <a name="scenario"></a>Kịch bản

Contoso là công ty sản xuất cà phê và máy pha cà phê chất lượng cao. Họ bán sản phẩm thông qua trang web Contoso Coffee của họ. Gần đây, họ đã bắt đầu kinh doanh dịch vụ đăng ký cho khách hàng của mình để uống cà phê thường xuyên. Mục tiêu của họ là hiểu những khách hàng đã đăng ký nào có thể hủy đăng ký của họ trong vài tháng tới. Biết khách hàng của họ là ai **có khả năng khuấy động** có thể giúp họ tiết kiệm các nỗ lực tiếp thị bằng cách tập trung vào việc giữ chân chúng.

## <a name="prerequisites"></a>Điều kiện tiên quyết

- Ít nhất [Quyền của người đóng góp](permissions.md) trong Customer Insights.

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

1. Lưu nguồn dữ liệu.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Nhập dữ liệu khách hàng từ lược đồ khách hàng thân thiết

1. Tạo nguồn dữ liệu có tên **Kế hoạch trung thành** và chọn **Văn bản / CSV** kết nối.

1. Nhập URL cho khách hàng thân thiết https://aka.ms/ciadclasscustomerloyalty.

1. Trong khi chỉnh sửa dữ liệu, hãy chọn **Biến đổi** và sau đó **Sử dụng hàng đầu tiên làm tiêu đề**.

1. Cập nhật kiểu dữ liệu cho các cột được liệt kê bên dưới:
   - **DateOfBirth**: Ngày
   - **RewardsPoints**: Số nguyên
   - **CreatedOn**: Ngày/Giờ

1. Bên trong **Tên** trên ngăn bên phải, đổi tên nguồn dữ liệu của bạn thành **loyCustomers**.

1. Lưu nguồn dữ liệu.

### <a name="ingest-subscription-information"></a>Nhập thông tin đăng ký

1. Tạo nguồn dữ liệu có tên **Đăng ký** và chọn **Văn bản / CSV** kết nối.

1. Nhập URL cho các đăng ký https://aka.ms/ciadchurnsubscriptionhistory.

1. Trong khi chỉnh sửa dữ liệu, hãy chọn **Biến đổi** và sau đó **Sử dụng hàng đầu tiên làm tiêu đề**.

1. Cập nhật kiểu dữ liệu cho các cột được liệt kê bên dưới:
   - **SubscriptioID**: Số nguyên
   - **SubscriptionAmount**: Đơn vị tiền tệ
   - **SubscriptionEndDate**: Ngày/Giờ
   - **SubscriptionStartDate**: Ngày/Giờ
   - **TransactionDate**: Ngày/Giờ
   - **IsRecurring**: True/False
   - **Is_auto_renew**: True/False
   - **RecurringFrequencyInMonths**: Số nguyên

1. Bên trong **Tên** trên ngăn bên phải, đổi tên nguồn dữ liệu của bạn thành **Đăng ký**.

1. Lưu nguồn dữ liệu.

### <a name="ingest-customer-data-from-website-reviews"></a>Nhập dữ liệu khách hàng từ các bài đánh giá trang web

1. Tạo nguồn dữ liệu có tên **Trang mạng** và chọn **Văn bản / CSV** kết nối.

1. Nhập URL để xem lại trang web https://aka.ms/ciadclasswebsite.

1. Trong khi chỉnh sửa dữ liệu, hãy chọn **Biến đổi** và sau đó **Sử dụng hàng đầu tiên làm tiêu đề**.

1. Cập nhật kiểu dữ liệu cho các cột được liệt kê bên dưới:
   - **ReviewRating**: Số nguyên
   - **ReviewDate**: Ngày

1. Bên trong **Tên** trên ngăn bên phải, đổi tên nguồn dữ liệu của bạn thành **webReviews**.

## <a name="task-2---data-unification"></a>Nhiệm vụ 2 - Hợp nhất dữ liệu

Xem lại bài báo [về hợp nhất dữ liệu](data-unification.md). Thông tin sau đây giả định rằng bạn đã quen với việc hợp nhất dữ liệu nói chung.

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---create-transaction-history-activity"></a>Nhiệm vụ 3 - Tạo hoạt động lịch sử giao dịch

Xem lại bài báo [về các hoạt động của khách hàng](activities.md). Thông tin sau đây giả định rằng bạn đã quen với việc tạo các hoạt động nói chung.

1. Tạo một hoạt động được gọi là **Đăng ký** với *Đăng ký* thực thể và khóa chính của nó, **ID khách hàng**.

1. Tạo mối quan hệ giữa *Đăng kýHistory: Đăng ký* và *eCommerceLiên hệ: eCommerce* với **ID khách hàng** làm khóa ngoại để kết nối hai thực thể.

1. Lựa chọn **SubscriptionType** cho **EventActivity** và **Ngày đăng ký** cho **TimeStamp**.

1. Lựa chọn **Đăng ký** cho **Loại hoạt động** và lập bản đồ ngữ nghĩa dữ liệu hoạt động.

1. Chạy hoạt động.

1. Thêm một hoạt động khác và ánh xạ tên các trường của nó vào các trường tương ứng:
   - Thực thể hoạt động của khách hàng: Reviews:Website
   - Khóa chính: Website.Reviews.ReviewId
   - Dấu thời gian: Website.Reviews.ReviewDate
   - Sự kiện (tên hoạt động): Website.Reviews.ActivityTypeDisplay
   - Chi tiết (số lượng hoặc giá trị): Website.Reviews.ReviewRating

1. Chạy hoạt động.

## <a name="task-4---configure-the-subscription-churn-prediction"></a>Nhiệm vụ 4 - Định cấu hình dự đoán rời bỏ đăng ký

Với hồ sơ khách hàng hợp nhất tại chỗ và hoạt động đã được tạo, hãy chạy đăng ký churn dự đoán. Để biết các bước chi tiết, hãy xem [Đăng ký churn dự đoán](predict-subscription-churn.md).

1. Đi đến **Sự thông minh** > **Phỏng đoán**.

1. Trên **Tạo ra** tab, chọn **Sử dụng mô hình** trên **Mô hình churn khách hàng** ngói.

1. Lựa chọn **Đăng ký** cho kiểu churn và sau đó **Bắt đầu**.

1. Đặt tên cho mô hình **Dự đoán rời bỏ đăng ký OOB** và thực thể đầu ra **OOBSubscriptionChurnPrediction**.

1. Xác định tùy chọn mô hình:
   - **Số ngày kể từ khi đăng ký kết thúc** :**60** ngày để cho biết rằng một khách hàng được coi là bỏ cuộc nếu họ không gia hạn đăng ký trong khoảng thời gian này sau khi đăng ký của họ kết thúc.
   - **Số ngày điều tra tương lai để dự đoán tình trạng hỗn loạn** :**93** ngày là khoảng thời gian mà mô hình dự đoán khách hàng nào có thể rời đi. Bạn càng dự đoán xa thì kết quả càng thiếu chính xác.

   :::image type="content" source="media/model-subs-levers.PNG" alt-text="Chọn tùy chọn mô hình và định nghĩa churn.":::

1. Chọn **Tiếp theo**.

1. Bên trong **Dữ liệu bắt buộc** bước, chọn **Thêm dữ liệu** để cung cấp lịch sử đăng ký.

1. Lựa chọn **Đăng ký** và thực thể SubscriptionHistory và chọn **Tiếp theo**. Dữ liệu cần thiết được tự động điền vào từ hoạt động. Chọn **Lưu.**

1. Trong Hoạt động của khách hàng, hãy chọn **Thêm dữ liệu**.

1. Đối với ví dụ này, hãy thêm hoạt động đánh giá web.

1. Chọn **Tiếp theo**.

1. Bên trong **Cập nhật dữ liệu** bước, chọn **Hàng tháng** cho lịch trình mô hình.

1. Sau khi xem lại tất cả thông tin chi tiết, hãy chọn **Lưu và chạy**.

## <a name="task-5---review-model-results-and-explanations"></a>Nhiệm vụ 5 - Xem xét kết quả và giải thích mô hình

Để mô hình hoàn thành việc đào tạo và chấm điểm dữ liệu. Xem lại giải thích mô hình churn đăng ký. Để biết thêm thông tin, hãy xem [Xem kết quả dự đoán](predict-subscription-churn.md#view-prediction-results).

## <a name="task-6---create-a-segment-of-high-churn-risk-customers"></a>Nhiệm vụ 6 - Tạo một phân khúc khách hàng có nguy cơ rời bỏ cao

Việc chạy mô hình sẽ tạo một thực thể mới, được liệt kê trên phần **Dữ liệu** > **Thực thể**. Bạn có thể tạo một phân khúc mới dựa trên thực thể được tạo bởi mô hình.

1. Trên trang kết quả, hãy chọn **Tạo phân khúc**.

1. Tạo quy tắc bằng cách sử dụng **OOBSubscriptionChurnPrediction** thực thể và xác định phân đoạn:
   - **Đồng ruộng** : ChurnScore
   - **Nhà điều hành** : lớn hơn
   - **Giá trị** : 0,6

1. Lựa chọn **Tiết kiệm** và **Chạy** phân khúc.

Giờ đây, bạn có một phân khúc được cập nhật động để xác định những khách hàng có nguy cơ rời bỏ cao cho doanh nghiệp đăng ký này. Để biết thêm thông tin, hãy xem [Tạo và quản lý phân khúc](segments.md).

> [!TIP]
> Bạn cũng có thể tạo phân đoạn cho mô hình dự đoán từ **Phân đoạn** trang bằng cách chọn **Mới** và lựa chọn **Tạo từ** > **Sự thông minh**. Để biết thêm thông tin, hãy xem [Tạo một phân đoạn mới với các phân đoạn nhanh chóng](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
