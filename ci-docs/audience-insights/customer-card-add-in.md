---
title: Cài đặt và đặt cấu hình phần bổ trợ Thẻ khách hàng
description: Cài đặt và đặt cấu hình Phần bổ trợ Thẻ Khách hàng cho Dynamics 365 Customer Insights.
ms.date: 01/20/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: a6d5b49380ed129cf147698a16f5f3f597bf7fbc
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268070"
---
# <a name="customer-card-add-in-preview"></a>Trình bổ sung thẻ khách hàng (xem trước)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Nhận thông tin toàn diện về khách hàng ngay trong ứng dụng Dynamics 365. Xem nhân khẩu học, thông tin chi tiết và dòng thời gian hoạt động qua Trình bổ trợ thẻ khách hàng.

## <a name="prerequisites"></a>Điều kiện tiên quyết

- Ứng dụng Dynamics 365 (chẳng hạn như Trung tâm bán hàng hoặc Trung tâm Dịch vụ Khách hàng), phiên bản 9.0 trở lên với Giao diện Hợp nhất được bật.
- Hồ sơ khách hàng [được nhập từ ứng dụng Dynamics 365 bằng cách sử dụng Common Data Service](connect-power-query.md).
- Người dùng phần bổ trợ Thẻ khách hàng cần được [thêm làm người dùng](permissions.md) trong thông tin chi tiết về đối tượng.
- [Khả năng tìm kiếm và lọc đã định cấu hình](search-filter-index.md).
- Kiểm soát nhân khẩu học: Các trường nhân khẩu học (chẳng hạn như tuổi hoặc giới tính) có sẵn trong hồ sơ khách hàng hợp nhất.
- Điều khiển tăng cường: Yêu cầu dữ liệu [tăng cường](enrichment-hub.md) hiện hoạt áp dụng cho hồ sơ khách hàng.
- Kiểm soát thông tin: Yêu cầu có dữ liệu được tạo bằng Azure Machine Learning ([Dự đoán](predictions.md) hoặc [Mô hình khách hàng](custom-models.md))
- Kiểm soát đo lường: Yêu cầu [các biện pháp được đặt cấu hình](measures.md).
- Kiểm soát dòng thời gian: Yêu cầu [các hoạt động được đặt cấu hình](activities.md).

## <a name="install-the-customer-card-add-in"></a>Cài đặt phần bổ trợ Thẻ khách hàng

Phần bổ trợ Thẻ khách hàng là một giải pháp cho các ứng dụng gắn kết khách hàng trong Dynamics 365. Để cài đặt giải pháp, hãy chuyển đến AppSource và tìm kiếm **Thẻ khách hàng Dynamics**. Chọn [Trình bổ sung thẻ khách hàng trên AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) và chọn **Tải ngay**.

Bạn có thể cần phải đăng nhập bằng thông tin đăng nhập quản trị viên của mình cho ứng dụng Dynamics 365 để cài đặt giải pháp.

Có thể mất một chút thời gian để cài đặt giải pháp vào môi trường của bạn.

## <a name="configure-the-customer-card-add-in"></a>Đặt cấu hình Trình bổ trợ thẻ khách hàng

1. Là quản trị viên, hãy đi tới phần **Cài đặt** trong ứng dụng hướng mô hình trong Dynamics 365 và chọn **Giải pháp**.

1. Chọn liên kết **Tên hiển thị** cho giải pháp Trình bổ trợ thẻ khách hàng **Dynamics 365 Customer Insights (Xem trước)**.

   > [!div class="mx-imgBorder"]
   > ![Chọn tên hiển thị](media/select-display-name.png "Chọn tên hiển thị")

1. Chọn **Đăng nhập** và nhập thông tin xác thực cho tài khoản quản trị viên bạn sử dụng để đặt cấu hình Customer Insights.

   > [!NOTE]
   > Kiểm tra để đảm bảo trình chặn cửa sổ bật lên trong trình duyệt không chặn cửa sổ xác thực khi bạn chọn nút **Đăng nhập**.

1. Chọn môi trường bạn muốn lấy dữ liệu từ đó.

1. Xác định ánh xạ trường tới các bản ghi trong ứng dụng Dynamics 365.
   - Để ánh xạ với một liên hệ, hãy chọn trường trong thực thể Khách hàng khớp với ID của thực thể liên hệ của bạn.
   - Để ánh xạ với một tài khoản, hãy chọn trường trong thực thể Khách hàng khớp với ID của thực thể tài khoản của bạn.

   > [!div class="mx-imgBorder"]
   > ![Trường ID người liên hệ](media/contact-id-field.png "Trường ID người liên hệ")

1. Chọn **Lưu cấu hình** để lưu cài đặt.

1. Tiếp theo, bạn cần chỉ định vai trò bảo mật trong Dynamics 365 để người dùng có thể tùy chỉnh và xem thẻ khách hàng. Trong Dynamics 365, hãy chuyển tới **Cài đặt** > **Bảo mật** > **Người dùng**. Chọn người dùng để chỉnh sửa vai trò người dùng và chọn **Quản lý vai trò**.

1. Gán vai trò **Người tùy chỉnh thẻ Customer Insights** cho những người dùng sẽ tùy chỉnh nội dung hiển thị trên thẻ cho toàn bộ tổ chức.

## <a name="add-customer-card-controls-to-forms"></a>Thêm kiểm soát Thẻ khách hàng vào biểu mẫu
  
1. Để thêm các điều khiển Thẻ khách hàng vào biểu mẫu Liên hệ của bạn, hãy chuyển tới **Cài đặt** > **Tùy chỉnh** trong Dynamics 365.

1. Chọn **Tùy chỉnh hệ thống**.

1. Duyệt đến thực thể **Người liên hệ**, mở rộng thực thể này rồi chọn **Biểu mẫu**.

1. Chọn biểu mẫu người liên hệ mà bạn muốn thêm điều khiển Thẻ khách hàng.

    > [!div class="mx-imgBorder"]
    > ![Chọn biểu mẫu người liên hệ](media/contact-active-forms.png "Chọn biểu mẫu người liên hệ")

1. Để thêm một điều khiển, trong công cụ biên tập biểu mẫu, hãy kéo trường bất kỳ từ **Field Explorer** tới vị trí bạn muốn điều khiển xuất hiện.

1. Chọn trường trên biểu mẫu mà bạn vừa thêm, sau đó chọn **Thay đổi thuộc tính**.

1. Truy cập tab **Kiểm soát** và chọn **Thêm kiểm soát**. Chọn một trong các điều khiển tùy chỉnh có sẵn và chọn **Thêm**.

1. Trong hộp thoại **Thuộc tính trường**, bỏ chọn hộp **Hiển thị nhãn trên biểu mẫu**.

1. Chọn tùy chọn **Web** cho điều khiển. Đối với điều khiển Tăng cường, hãy chọn loại tăng cường mà bạn muốn hiển thị bằng cách định cấu hình trường **enrichmentType**. Thêm điều khiển làm phong phú riêng biệt cho từng loại làm phong phú.

1. Chọn **Lưu** và **Xuất bản** để xuất bản biểu mẫu liên hệ đã cập nhật.

1. Chuyển đến biểu mẫu liên hệ đã phát hành. Bạn sẽ thấy điều khiển mới được thêm vào. Bạn có thể cần phải đăng nhập trong lần đầu tiên bạn sử dụng.

1. Để tùy chỉnh nội dung bạn muốn hiển thị trên điều khiển tùy chỉnh, hãy chọn nút chỉnh sửa ở góc trên bên phải.

## <a name="upgrade-customer-card-add-in"></a>Nâng cấp phần bổ trợ Thẻ Khách hàng
Phần bổ trợ Thẻ Khách hàng không tự động nâng cấp. Để nâng cấp lên phiên bản mới nhất, hãy làm theo quy trình này trong ứng dụng Dynamics 365 đã cài đặt Phần bổ trợ.

1. Trong ứng dụng Dynamics 365, hãy chuyển đến **Cài đặt** > **Tùy chỉnh** và chọn **Các giải pháp**.

1. Trong bảng phần bổ trợ, hãy tìm **CustomerInsightsCustomerCard** và chọn hàng.

1. Chọn **Áp dụng nâng cấp giải pháp** trong thanh tác vụ.

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Nâng cấp giải pháp trong khu vực Tùy chỉnh của ứng dụng Dynamics 365":::

1. Sau khi bắt đầu quá trình nâng cấp, bạn sẽ thấy chỉ báo tải cho đến khi quá trình nâng cấp hoàn tất. Nếu không có phiên bản mới hơn, bản nâng cấp sẽ hiển thị thông báo lỗi.


[!INCLUDE[footer-include](../includes/footer-banner.md)]