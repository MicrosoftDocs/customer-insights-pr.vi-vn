---
title: Phần bổ trợ Thẻ khách hàng cho các ứng dụng Dynamics 365 (có video)
description: Hiển thị dữ liệu hồ sơ khách hàng từ Thông tin chi tiết về khách hàng trong ứng dụng Dynamics 365 với tiện ích bổ sung này.
ms.date: 02/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
searchScope:
- ci-customers-page
- ci-search-filter
- ci-customer-card
- customerInsights
ms.openlocfilehash: 8508880bb3274bb491a314a043a5222d4d381073
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755662"
---
# <a name="customer-card-add-in-preview"></a>Trình bổ sung thẻ khách hàng (xem trước)

Nhận thông tin toàn diện về khách hàng ngay trong ứng dụng Dynamics 365. Với phần bổ trợ Thẻ khách hàng được cài đặt trong ứng dụng Dynamics 365 được hỗ trợ, bạn có thể chọn hiển thị các trường hồ sơ khách hàng, thông tin chi tiết và tiến trình hoạt động. Phần bổ trợ sẽ truy xuất dữ liệu từ Customer Insights mà không ảnh hưởng đến dữ liệu trong ứng dụng Dynamics 365 được kết nối.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN1qv]

## <a name="prerequisites"></a>Điều kiện tiên quyết

- Phần bổ trợ này chỉ hoạt động với các ứng dụng dựa trên mô hình Dynamics 365, chẳng hạn như ứng dụng Sales hoặc Customer Service, phiên bản 9.0 trở lên.
- Để dữ liệu Dynamics 365 của bạn liên kết với hồ sơ khách hàng Customer Insights, chúng tôi khuyên bạn nên [nhập từ ứng dụng Dynamics 365 bằng cách sử dụng Microsoft Dataverse tư nối](connect-power-query.md). Nếu bạn sử dụng một phương pháp khác để nhập địa chỉ liên hệ (hoặc tài khoản) Dynamics 365, bạn cần đảm bảo`contactid` (hoặc`accountid`) trường được đặt là [khóa chính cho nguồn dữ liệu đó trong bước bản đồ của quy trình hợp nhất dữ liệu](map-entities.md#select-primary-key-and-semantic-type-for-attributes).
- Tất cả người dùng Dynamics 365 của Phần bổ trợ Thẻ Khách hàng phải [được thêm vào với tư cách là người dùng](permissions.md) trong Thông tin chi tiết về khách hàng để xem dữ liệu.
- [Các khả năng tìm kiếm và lọc đã định cấu hình](search-filter-index.md) trong Thông tin chi tiết về khách hàng là bắt buộc để tra cứu dữ liệu hoạt động.
- Mỗi kiểm soát bổ trợ dựa trên dữ liệu cụ thể trong Thông tin chi tiết về khách hàng. Một số dữ liệu và điều khiển chỉ có sẵn trong các môi trường thuộc các loại cụ thể. Cấu hình bổ trợ sẽ thông báo cho bạn nếu điều khiển không khả dụng do loại môi trường đã chọn. Tìm hiểu thêm về [trường hợp sử dụng môi trường](work-with-business-accounts.md).
  - **Kiểm soát đo lường**: Yêu cầu [các biện pháp được đặt cấu hình](measures.md) của thuộc tính của loại khách hàng.
  - **Kiểm soát thông minh** : Yêu cầu dữ liệu được tạo bằng cách sử dụng [dự đoán hoặc mô hình tùy chỉnh](predictions-overview.md).
  - **Kiểm soát chi tiết khách hàng**: Tất cả các trường từ hồ sơ đều có sẵn trong hồ sơ khách hàng hợp nhất.
  - **Điều khiển tăng cường**: Yêu cầu dữ liệu [tăng cường](enrichment-hub.md) hiện hoạt áp dụng cho hồ sơ khách hàng. Bổ trợ thẻ hỗ trợ các tính năng bổ sung sau: [Nhãn hiệu](enrichment-microsoft.md) do Microsoft cung cấp, [Sở thích](enrichment-microsoft.md) được cung cấp bởi Microsoft, và [Dữ liệu tham gia văn phòng](enrichment-office.md) do Microsoft cung cấp.
  - **Kiểm soát danh bạ**: Yêu cầu định nghĩa thực thể ngữ nghĩa của các liên hệ kiểu.
  - **Kiểm soát dòng thời gian**: Yêu cầu [các hoạt động được đặt cấu hình](activities.md).

## <a name="install-the-customer-card-add-in"></a>Cài đặt phần bổ trợ Thẻ khách hàng

Phần bổ trợ Thẻ khách hàng là một giải pháp cho các ứng dụng gắn kết khách hàng trong Dynamics 365. Để cài đặt giải pháp, hãy chuyển đến AppSource và tìm kiếm **Thẻ khách hàng Dynamics**. Chọn [Trình bổ sung thẻ khách hàng trên AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) và chọn **Tải ngay**.

Bạn có thể cần phải đăng nhập bằng thông tin đăng nhập quản trị viên của mình cho ứng dụng Dynamics 365 để cài đặt giải pháp. Có thể mất một chút thời gian để cài đặt giải pháp vào môi trường của bạn.

## <a name="configure-the-customer-card-add-in"></a>Đặt cấu hình Trình bổ trợ thẻ khách hàng

1. Là quản trị viên, hãy đi tới phần **Cài đặt** trong ứng dụng hướng mô hình trong Dynamics 365 và chọn **Giải pháp**.

1. Chọn liên kết **Tên hiển thị** cho giải pháp Trình bổ trợ thẻ khách hàng **Dynamics 365 Customer Insights (Xem trước)**.

   > [!div class="mx-imgBorder"]
   > ![Chọn tên hiển thị.](media/select-display-name.png "Chọn tên hiển thị.")

1. Chọn **Đăng nhập** và nhập thông tin xác thực cho tài khoản quản trị viên bạn sử dụng để đặt cấu hình Customer Insights.

   > [!NOTE]
   > Kiểm tra để đảm bảo trình chặn cửa sổ bật lên trong trình duyệt không chặn cửa sổ xác thực khi bạn chọn nút **Đăng nhập**.

1. Chọn môi trường Customer Insights bạn muốn lấy dữ liệu từ đó.

1. Xác định ánh xạ trường tới các bản ghi trong ứng dụng Dynamics 365. Tùy thuộc vào dữ liệu của bạn trong Customer Insights, bạn có thể chọn ánh xạ các đối tượng sau:
   - Để ánh xạ với một liên hệ, hãy chọn trường trong thực thể Khách hàng khớp với ID của thực thể liên hệ của bạn.
   - Để ánh xạ với một tài khoản, hãy chọn trường trong thực thể Khách hàng khớp với ID của thực thể tài khoản của bạn.

   > [!div class="mx-imgBorder"]
   > ![Trường ID người liên hệ.](media/contact-id-field.png "Trường ID liên hệ.")

1. Chọn **Lưu cấu hình** để lưu cài đặt.

1. Tiếp theo, bạn cần chỉ định vai trò bảo mật trong Dynamics 365 để người dùng có thể tùy chỉnh và xem thẻ khách hàng. Trong Dynamics 365, hãy chuyển tới **Cài đặt** > **Bảo mật** > **Người dùng**. Chọn người dùng để chỉnh sửa vai trò người dùng và chọn **Quản lý vai trò**.

1. Gán vai trò **Người tùy chỉnh thẻ Customer Insights** cho những người dùng sẽ tùy chỉnh nội dung hiển thị trên thẻ cho toàn bộ tổ chức.

## <a name="add-customer-card-controls-to-forms"></a>Thêm kiểm soát Thẻ khách hàng vào biểu mẫu

Tùy thuộc vào tình huống của bạn, bạn có thể chọn thêm các điều khiển vào biểu mẫu **Liên hệ** hoặc **Tài khoản**. Nếu môi trường Thông tin chi tiết về khách hàng của bạn dành cho tài khoản doanh nghiệp, chúng tôi khuyên bạn nên thêm các kiểm soát vào biểu mẫu Tài khoản. Trong trường hợp đó, hãy thay thế "liên hệ" trong các bước dưới đây bằng "tài khoản".

1. Để thêm các điều khiển Thẻ khách hàng vào biểu mẫu Liên hệ của bạn, hãy chuyển tới **Cài đặt** > **Tùy chỉnh** trong Dynamics 365.

1. Chọn **Tùy chỉnh hệ thống**.

1. Duyệt đến thực thể **Liên hệ**, mở rộng thực thể này rồi chọn **Biểu mẫu**.

1. Chọn biểu mẫu liên hệ mà bạn muốn thêm điều khiển Thẻ khách hàng.

    > [!div class="mx-imgBorder"]
    > ![Chọn biểu mẫu người liên hệ.](media/contact-active-forms.png "Chọn biểu mẫu Liên hệ.")

1. Để thêm một điều khiển, trong công cụ biên tập biểu mẫu, hãy kéo trường bất kỳ từ **Field Explorer** tới vị trí bạn muốn điều khiển xuất hiện.

1. Chọn trường trên biểu mẫu mà bạn vừa thêm, sau đó chọn **Thay đổi thuộc tính**.

1. Truy cập tab **Kiểm soát** và chọn **Thêm kiểm soát**. Chọn một trong các điều khiển tùy chỉnh có sẵn và chọn **Thêm**.

1. Trong hộp thoại **Thuộc tính trường**, bỏ chọn hộp **Hiển thị nhãn trên biểu mẫu**.

1. Chọn tùy chọn **Web** cho điều khiển. Đối với điều khiển Tăng cường, hãy chọn loại tăng cường mà bạn muốn hiển thị bằng cách định cấu hình trường **enrichmentType**. Thêm điều khiển làm phong phú riêng biệt cho từng loại làm phong phú.

1. Chọn **Lưu** và **Xuất bản** để xuất bản biểu mẫu liên hệ đã cập nhật.

1. Chuyển đến biểu mẫu liên hệ đã phát hành. Bạn sẽ thấy điều khiển mới được thêm vào. Bạn có thể cần phải đăng nhập trong lần đầu tiên bạn sử dụng.

1. Để tùy chỉnh nội dung bạn muốn hiển thị trên điều khiển tùy chỉnh, hãy chọn nút chỉnh sửa ở góc trên bên phải.

## <a name="upgrade-customer-card-add-in"></a>Nâng cấp phần bổ trợ Thẻ Khách hàng

Phần bổ trợ Thẻ Khách hàng không tự động nâng cấp. Để nâng cấp lên phiên bản mới nhất, hãy làm theo các bước sau trong ứng dụng Dynamics 365 đã cài đặt phần bổ trợ.

1. Trong ứng dụng Dynamics 365, hãy chuyển đến **Cài đặt** > **Tùy chỉnh** và chọn **Các giải pháp**.

1. Trong bảng phần bổ trợ, hãy tìm **CustomerInsightsCustomerCard** và chọn hàng.

1. Chọn **Áp dụng nâng cấp giải pháp** trong thanh tác vụ.

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Nâng cấp giải pháp trong khu vực Tùy chỉnh của ứng dụng Dynamics 365.":::

1. Sau khi bắt đầu quá trình nâng cấp, bạn sẽ thấy chỉ báo tải cho đến khi quá trình nâng cấp hoàn tất. Nếu không có phiên bản mới hơn, bản nâng cấp sẽ hiển thị thông báo lỗi.

## <a name="troubleshooting"></a>Gỡ rối

### <a name="controls-from-customer-card-add-in-dont-find-data"></a>Kiểm soát từ Tiện ích bổ sung thẻ khách hàng không tìm thấy dữ liệu

**Vấn đề:**

Ngay cả với các trường ID được định cấu hình chính xác, các điều khiển không thể tìm thấy dữ liệu cho bất kỳ khách hàng nào.  

**Cách giải quyết:**

1. Đảm bảo rằng bạn đã định cấu hình Phần bổ trợ Thẻ theo hướng dẫn: [Định cấu hình bổ trợ Thẻ khách hàng](#configure-the-customer-card-add-in)

1. Xem lại cấu hình nhập dữ liệu. Chỉnh sửa nguồn dữ liệu cho hệ thống Dynamics 365 có chứa GUID ID liên hệ. Nếu GUID ID liên hệ được hiển thị với các ký tự viết hoa trong Power Query trình chỉnh sửa, hãy thử các bước sau:
    1. Chỉnh sửa nguồn dữ liệu để mở nguồn dữ liệu trong Power Query Người biên tập.
    1. Chọn cột ID liên hệ.
    1. Lựa chọn **Biến đổi** trong thanh tiêu đề để xem các hành động khả dụng.
    1. Lựa chọn **chữ thường**. Xác thực nếu GUID trong bảng bây giờ là chữ thường.
    1. Lưu nguồn dữ liệu.
    1. Chạy các quy trình nhập, hợp nhất và hạ nguồn dữ liệu để phổ biến các thay đổi đối với GUID.

Sau khi hệ thống hoàn tất việc làm mới toàn bộ, các điều khiển của Phần bổ trợ Thẻ Khách hàng sẽ hiển thị dữ liệu dự kiến.

[!INCLUDE [footer-include](includes/footer-banner.md)]
