---
title: Tăng cường các hồ sơ khách hàng với dữ liệu vị trí từ Azure Maps
description: Thông tin chung về dịch vụ tăng cường dữ liệu của bên thứ nhất Azure Maps.
ms.date: 08/31/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 6d43dc2ca82c034fbd396d92637e7aea8179df77
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755380"
---
# <a name="enrichment-of-customer-profiles-with-azure-maps-preview"></a>Tăng cường dữ liệu hồ sơ khách hàng bằng Azure Maps (bản xem trước)

Azure Maps cung cấp dữ liệu và dịch vụ tập trung vào vị trí để mang lại trải nghiệm dựa trên dữ liệu không gian địa lý với thông tin vị trí tích hợp sẵn. Dịch vụ tăng cường dữ liệu Azure Maps cải thiện độ chính xác của thông tin vị trí về khách hàng của bạn. Dịch vụ này mang lại các khả năng như chuẩn hóa địa chỉ và trích xuất vĩ độ cũng như kinh độ cho Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Điều kiện tiên quyết

Để đặt cấu hình dịch vụ tăng cường dữ liệu Azure Maps, bạn phải đáp ứng các điều kiện tiên quyết sau:

- Bạn phải có đăng ký Azure Maps hiện hoạt. Để có gói đăng ký, bạn có thể [đăng ký hoặc nhận bản dùng thử miễn phí](https://azure.microsoft.com/services/azure-maps/).

- [Kết nối](connections.md) Azure Maps có sẵn *hoặc* bạn có quyền [quản trị viên](permissions.md#admin) và một khóa API Azure Maps đang hoạt động.

## <a name="configure-the-enrichment"></a>Đặt cấu hình dữ liệu tăng cường

1. Chuyển tới **Dữ liệu** > **Dữ liệu tăng cường**. 

1. Trên ngăn xếp **Vị trí**, hãy chọn **Tăng cường dữ liệu của tôi**.

   :::image type="content" source="media/azure-maps-tile.png" alt-text="Ngăn xếp Azure Maps.":::

1. Chọn một [kết nối](connections.md) từ danh sách thả xuống. Liên hệ với quản trị viên nếu không có kết nối Azure Maps. Nếu bạn là quản trị viên, bạn có thể [đặt cấu hình kết nối cho Azure Maps](#configure-the-connection-for-azure-maps). 

1. Chọn **Tiếp theo** để xác nhận lựa chọn.

1. Chọn **Tập dữ liệu khách hàng** bạn muốn tăng cường với dữ liệu vị trí từ Azure Maps. Bạn có thể chọn thực thể **Khách hàng** để tăng cường dữ liệu cho tất cả hồ sơ khách hàng hợp nhất của bạn hoặc chọn một thực thể phân khúc để chỉ tăng cường dữ liệu cho hồ sơ khách hàng có trong phân khúc đó.

    :::image type="content" source="media/enrichment-azure-maps-configuration-customer-data-set.png" alt-text="Ảnh chụp màn hình khi chọn tập dữ liệu khách hàng.":::

1. Chọn xem bạn có muốn ánh xạ các trường tới địa chỉ chính và/hoặc địa chỉ phụ hay không. Bạn có thể chỉ định ánh xạ trường cho cả hai địa chỉ và tăng cường hồ sơ cho cả hai địa chỉ một cách riêng biệt&mdash;ví dụ: đối với địa chỉ nhà riêng và địa chỉ doanh nghiệp. Chọn **Tiếp theo**.

1. Xác định trường nào từ hồ sơ hợp nhất của bạn sẽ sử dụng để tìm kiếm dữ liệu vị trí phù hợp từ Azure Maps. Các trường **Đường 1** và **Mã ZIP/Mã bưu điện** là bắt buộc cho địa chỉ chính hoặc phụ đã chọn. Để có độ chính xác đối sánh cao hơn, bạn có thể thêm nhiều trường hơn.

   :::image type="content" source="media/enrichment-azure-maps-configuration.png" alt-text="Trang cấu hình tăng cường Azure Maps.":::

1. Chọn **Tiếp** để hoàn thành quá trình ánh xạ trường.

1. Đánh giá xem bạn có muốn sửa đổi **Thiết đặt nâng cao** không. Các cài đặt này được cung cấp để mang lại sự linh hoạt tối đa để xử lý các trường hợp sử dụng nâng cao, nhưng các giá trị mặc định sẽ phù hợp trong hầu hết các trường hợp:
   - **Loại địa chỉ**: Hành vi mặc định là việc bổ sung sẽ trả về địa chỉ phù hợp nhất ngay cả khi nó chưa hoàn chỉnh. Để chỉ nhận được địa chỉ đầy đủ&mdash;ví dụ: địa chỉ bao gồm số nhà&mdash;xóa tất cả các hộp kiểm ngoại trừ **Địa chỉ dạng điểm**. 
   - **Ngôn ngữ**: Theo mặc định, các địa chỉ được trả về bằng ngôn ngữ cho vùng mà địa chỉ đã được xác định là thuộc về. Để áp dụng ngôn ngữ địa chỉ được chuẩn hóa, hãy chọn ngôn ngữ từ menu thả xuống. Ví dụ: chọn **Tiếng Anh** sẽ trả về **Copenhagen, Đan Mạch** thay vì **København, Đan Mạch**.

1. Đặt tên cho dữ liệu tăng cường.

1. Xem lại các lựa chọn của bạn, sau đó chọn **Lưu dữ liệu tăng cường**.

## <a name="configure-the-connection-for-azure-maps"></a>Đặt cấu hình kết nối cho Azure Maps

Bạn cần phải là quản trị viên trong Thông tin chi tiết về khách hàng để định cấu hình kết nối. Chọn **Thêm kết nối** khi đặt cấu hình dữ liệu tăng cường hoặc đi đến **Quản trị viên** > **Kết nối** rồi chọn **Thiết lập** trên ngăn xếp Azure Maps.

1. Trong hộp **Tên hiển thị**, nhập tên cho kết nối.

1. Cung cấp khóa API Azure Maps hợp lệ.

1. Xem lại và đồng ý với **Quyền riêng tư về dữ liệu và tuân thủ** bằng cách đánh dấu vào hộp kiểm **Tôi đồng ý**

1. Chọn **Xác minh** để xác thực cấu hình.

1. Sau khi hoàn thành xác minh, hãy chọn **Lưu**.

:::image type="content" source="media/enrichment-azure-maps-connection.png" alt-text="Trang cấu hình kết nối Azure Maps.":::

## <a name="enrichment-results"></a>Kết quả tăng cường

Để bắt đầu quá trình tăng cường, hãy chọn **Chạy** từ thanh lệnh. Bạn cũng có thể để hệ thống chạy quá trình tăng cường tự động như một phần của [làm mới theo lịch trình](system.md#schedule-tab). Thời gian xử lý sẽ phụ thuộc vào kích thước dữ liệu khách hàng của bạn và thời gian phản hồi API.

Sau khi quá trình tăng cường hoàn tất, bạn có thể xem xét dữ liệu hồ sơ khách hàng mới được bổ sung trong **Dữ liệu tăng cường của tôi**. Ngoài ra, bạn sẽ tìm thấy thời gian của lần cập nhật gần nhất và số lượng hồ sơ được tăng cường.

Bạn có thể truy cập dạng xem chi tiết của từng hồ sơ được tăng cường dữ liệu bằng cách chọn **Xem dữ liệu tăng cường**.

## <a name="next-steps"></a>Các bước tiếp theo

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Quyền riêng tư về dữ liệu và sự tuân thủ

Khi bật Dynamics 365 Customer Insights để truyền dữ liệu tới Azure Maps, bạn cho phép truyền dữ liệu ra ngoài phạm vi tuân thủ cho Dynamics 365 Customer Insights, bao gồm dữ liệu có khả năng là thông tin nhạy cảm, chẳng hạn như Dữ liệu cá nhân. Microsoft sẽ chuyển những dữ liệu đó theo chỉ dẫn của bạn, nhưng bạn có trách nhiệm đảm bảo rằng Azure Maps đáp ứng mọi nghĩa vụ về quyền riêng tư hoặc bảo mật mà bạn có thể có. Để biết thêm thông tin, hãy chuyển đến phần [Điều khoản về quyền riêng tư của Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Quản trị viên Dynamics 365 Customer Insights của bạn có thể xóa tính năng tăng cường này bất kỳ lúc nào để ngừng sử dụng chức năng này.

[!INCLUDE [footer-include](includes/footer-banner.md)]
