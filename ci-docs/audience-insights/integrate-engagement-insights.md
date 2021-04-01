---
title: Tích hợp dữ liệu web từ thông tin chi tiết về mức độ tương tác với thông tin chi tiết về đối tượng
description: Chuyển thông tin chi tiết về mức độ tương tác trên web của khách hàng thành thông tin chi tiết về đối tượng.
ms.date: 12/17/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 14ebff30d3ec7fc52dca6f86136309a3f454fa27
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597491"
---
# <a name="integrate-web-data-from-engagement-insights-with-audience-insights"></a>Tích hợp dữ liệu web từ thông tin chi tiết về mức độ tương tác với thông tin chi tiết về đối tượng

Khách hàng thường thực hiện các giao dịch trực tuyến hàng ngày của họ bằng các trang web. Khả năng hiểu rõ về mức độ tương tác trong Dynamics 365 Customer Insights là một giải pháp tiện dụng để tích hợp dữ liệu web làm nguồn. Ngoài dữ liệu giao dịch, nhân khẩu học hoặc hành vi, chúng tôi có thể xem các hoạt động trên web trong hồ sơ khách hàng thống nhất. Chúng tôi có thể sử dụng hồ sơ này để có thêm thông tin chi tiết như phân đoạn, giá trị đo hoặc dự đoán nhằm kích hoạt đối tượng.

Bài viết này mô tả các bước để chuyển thông tin chi tiết về mức độ tương tác (dựa vào dữ liệu hoạt động trên web của khách hàng) vào môi trường thông tin chi tiết về đối tượng hiện tại của bạn.

Trong ví dụ này, chúng tôi giả định một môi trường chứa hồ sơ khách hàng hợp nhất. Các hồ sơ được thống nhất với các nguồn từ cuộc khảo sát, doanh số bán lẻ và hệ thống bán vé. Nó cũng cho thấy các hoạt động liên quan của khách hàng. 

Bây giờ, chúng tôi muốn biết liệu một khách hàng có truy cập các thuộc tính web của chúng tôi và hiểu các hoạt động của họ hay không. Các hoạt động bao gồm, ví dụ, các trang web đã truy cập hoặc các trang sản phẩm đã xem từ một liên kết nhận được trong email.

## <a name="prerequisites"></a>Điều kiện tiên quyết

Để tích hợp dữ liệu từ thông tin chi tiết về mức độ tương tác, bạn cần đáp ứng một số điều kiện tiên quyết: 

- Tích hợp SDK thông tin chi tiết về mức độ tương tác với trang web của bạn. Để biết thêm thông tin, hãy xem [Bắt đầu với SDK web](../engagement-insights/instrument-website.md).
- Việc xuất các sự kiện web từ thông tin chi tiết về mức độ tương tác yêu cầu quyền truy cập vào tài khoản lưu trữ ADLS Thế hệ 2 sẽ được dùng để nhập dữ liệu sự kiện trên web vào thông tin chi tiết về đối tượng. Để biết thêm thông tin, hãy xem [Xuất sự kiện](../engagement-insights/export-events.md).

## <a name="configure-refined-events-in-engagement-insights"></a>Định cấu hình các sự kiện đã tinh chỉnh trong thông tin chi tiết về mức độ tương tác

Sau khi quản trị viên tích hợp SDK thông tin chi tiết về mức độ tương tác vào trang web, *sự kiện cơ sở* được thu thập khi người dùng xem một trang web hoặc nhấp vào một nơi nào đó. Các sự kiện cơ sở có xu hướng chứa nhiều chi tiết. Tùy thuộc vào trường hợp sử dụng của bạn, bạn chỉ cần một tập hợp con của dữ liệu trong một sự kiện cơ sở. Thông tin chi tiết về mức độ tương tác cho phép bạn tạo *sự kiện tinh chỉnh* chỉ chứa các thuộc tính của sự kiện cơ sở mà bạn chọn.     

Để biết thêm thông tin, hãy xem [Tạo và sửa đổi các sự kiện đã tinh chỉnh](../engagement-insights/refined-events.md).

Các cân nhắc khi tạo các sự kiện tinh chỉnh: 

- Cung cấp tên có ý nghĩa cho sự kiện đã được tinh chỉnh. Nó được sử dụng làm tên hoạt động trong thông tin chi tiết về đối tượng.
- Chọn tối thiểu các thuộc tính sau để tạo hoạt động trong thông tin chi tiết về đối tượng: 
    - Signal.Action.Name - cho biết chi tiết về hoạt động
    - Signal.User.Id - được dùng để ánh xạ với ID khách hàng
    - Signal.View.Uri - được sử dụng làm địa chỉ web làm cơ sở cho các phân đoạn hoặc giá trị đo
    - Signal.Export.Id - để dùng làm khóa chính cho sự kiện <!-- system generated, do we need to list?-->
    - Signal.Timestamp - để xác định ngày và giờ cho hoạt động

Chọn bộ lọc để tập trung vào các sự kiện và trang quan trọng cho trường hợp sử dụng của bạn. Trong ví dụ này, chúng tôi sẽ sử dụng tên hành động "Quảng cáo qua email".

## <a name="export-the-refined-web-events"></a>Xuất các sự kiện web tinh chỉnh 

Sau khi xác định, sự kiện tinh chỉnh được xác định, bạn phải định cấu hình hoạt động xuất dữ liệu sự kiện sang một Azure Data Lake Storage, có thể được đặt làm nguồn dữ liệu để nhập thông tin chi tiết về đối tượng. Quá trình xuất diễn ra liên tục khi các sự kiện diễn ra từ thuộc tính web.

Để biết thêm thông tin, hãy xem [Xuất sự kiện](../engagement-insights/export-events.md).

## <a name="ingest-event-data-to-audience-insights"></a>Nhập dữ liệu sự kiện vào thông tin chi tiết về đối tượng

Bây giờ, bạn đã xác định sự kiện được tinh chỉnh và định cấu hình hoạt động xuất, chúng tôi chuyển sang nhập dữ liệu vào thông tin chi tiết về đối tượng. Bạn cần tạo nguồn dữ liệu mới dựa trên thư mục Common Data Model. Nhập chi tiết cho tài khoản lưu trữ mà bạn xuất các sự kiện sang. Trong tệp *default.cdm.json*, chọn sự kiện đã tinh chỉnh để nhập và tạo thực thể trong thông tin chi tiết về đối tượng.

Để biết thêm thông tin, hãy xem [Kết nối với thư mục Common Data Model bằng tài khoản Azure Data Lake](connect-common-data-model.md)


## <a name="relate-refined-event-data-as-an-activity-of-a-customer-profile"></a>Liên hệ dữ liệu sự kiện đã tinh chỉnh như một hoạt động của hồ sơ khách hàng

Sau khi hoàn tất quá trình nhập thực thể, bạn có thể định cấu hình hoạt động cho hồ sơ khách hàng.

Để biết thêm thông tin, hãy xem [Hoạt động của khách hàng](activities.md).

:::image type="content" source="media/web-event-activity.png" alt-text="Trang hoạt động với ngăn hoạt động Chỉnh sửa được mở rộng và được điền vào các trường.":::

Định cấu hình hoạt động mới với ánh xạ sau: 

- **Khóa chính:** Signal.Export.Id, một ID duy nhất có sẵn cho mọi bản ghi sự kiện trong thông tin chi tiết về mức độ tương tác. Thuộc tính này được tạo tự động.

- **Dấu thời gian:** Signal.Timestamp trong thuộc tính sự kiện.

- **Sự kiện:** Signal.Name, tên sự kiện bạn muốn theo dõi.

- **Địa chỉ web:** Signal.View.Uri đề cập đến uri của trang đã tạo sự kiện.

- **Chi tiết:** Signal.Action.Name để đại diện cho thông tin liên quan đến sự kiện. Thuộc tính được chọn trong trường hợp này cho biết rằng sự kiện là để quảng cáo qua email.

- **Loại hoạt động:** Trong ví dụ này, chúng tôi chọn loại hoạt động thú vị là WebLog. Lựa chọn này là một tùy chọn bộ lọc hữu ích để chạy mô hình dự đoán hoặc tạo phân đoạn dựa trên loại hoạt động này.

- **Thiết lập mối quan hệ:** Cài đặt quan trọng này liên kết hoạt động với hồ sơ khách hàng hiện tại. **Signal.User.Id** là mã nhận dạng được định cấu hình trong SDK sẽ được thu thập và liên quan đến ID người dùng trong các nguồn dữ liệu khác được định cấu hình trong thông tin chi tiết về đối tượng. Trong ví dụ này, chúng tôi định cấu hình mối quan hệ giữa Signal.User.Id và RetailCustomers: CustomerRetailId, là khóa chính đã được xác định trong bước ánh xạ của quy trình hợp nhất dữ liệu.


Sau khi xử lý các hoạt động, bạn có thể xem lại hồ sơ khách hàng và mở thẻ khách hàng để xem các hoạt động từ thông tin chi tiết về mức độ tương tác trong dòng thời gian. 

> [!TIP]
> Để tìm id khách hàng có hoạt động thông tin chi tiết về mức độ tương tác, hãy truy cập **Thực thể** và xem trước dữ liệu cho thực thể UnifiedActivity. ActivityTypeDisplay = WebLog chứa hoạt động thông tin chi tiết về mức độ tương tác được định cấu hình trong ví dụ trên. Sao chép ID khách hàng cho một trong những bản ghi đó và cho ID đó trên trang **Khách hàng**.

## <a name="next-steps"></a>Bước tiếp theo

Bây giờ bạn có thể tạo [phân đoạn](segments.md), [giá trị đo](measures.md) và [dự đoán](predictions.md) để tạo kết nối có ý nghĩa với khách hàng của bạn.


[!INCLUDE[footer-include](../includes/footer-banner.md)]