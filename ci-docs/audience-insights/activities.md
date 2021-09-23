---
title: Hoạt động của khách hàng
description: Xác định các hoạt động của khách hàng và xem các hoạt động đó theo dòng thời gian trên hồ sơ khách hàng.
ms.date: 09/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
ms.openlocfilehash: c5697df8a7d011c70384c8bc5e4773d7fcc25a62
ms.sourcegitcommit: fecdee73e26816c42d39d160d4d5cfb6c8a91596
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 09/15/2021
ms.locfileid: "7494437"
---
# <a name="customer-activities"></a>Hoạt động của khách hàng

Kết hợp các hoạt động của khách hàng từ [những nguồn dữ liệu khác nhau](data-sources.md) trong Dynamics 365 Customer Insights để tạo dòng thời gian liệt kê các hoạt động theo thứ tự thời gian. Bao gồm dòng thời gian trong các ứng dụng Dynamics 365 với giải pháp [phần bổ trợ Thẻ khách hàng](customer-card-add-in.md) hoặc trong một bảng điều khiển Power BI.

## <a name="define-an-activity"></a>Xác định hoạt động

Nguồn dữ liệu của bạn có thể bao gồm các thực thể có dữ liệu giao dịch và hoạt động từ nhiều nguồn dữ liệu. Xác định các thực thể này và chọn các hoạt động bạn muốn xem trên dòng thời gian của khách hàng. Chọn thực thể bao gồm hoạt động mục tiêu hoặc hoạt động của bạn.

> [!NOTE]
> Một thực thể phải có ít nhất một thuộc tính loại **Ngày** để được đưa vào dòng thời gian của khách hàng và bạn không thể thêm các thực thể mà không có trường **Ngày**. Kiểm soát **Thêm hoạt động** bị vô hiệu hóa nếu không tìm thấy thực thể đó.

1. Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Dữ liệu** > **Hoạt động**.

1. Chọn **Thêm hoạt động** để bắt đầu trải nghiệm có hướng dẫn cho quá trình thiết lập hoạt động.

1. Trong bước **Dữ liệu hoạt động**, hãy đặt giá trị cho các trường sau:

   - **Tên hoạt động**: Chọn tên cho hoạt động của bạn.
   - **Thực thể**: Chọn một thực thể bao gồm dữ liệu giao dịch hoặc hoạt động.
   - **Khóa chính**: Chọn trường xác định duy nhất một bản ghi. Nó không nên chứa bất kỳ giá trị trùng lặp, giá trị trống hoặc giá trị thiếu nào.

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Thiết lập dữ liệu hoạt động với tên, thực thể và khóa chính.":::

1. Chọn **Tiếp** để chuyển sang bước tiếp theo.

1. Trong bước **Mối quan hệ**, hãy đặt cấu hình thông tin chi tiết để kết nối dữ liệu hoạt động của bạn với khách hàng tương ứng. Bước này trực quan hóa kết nối giữa các thực thể.  

   - **Đầu tiên**: Trường ngoại trong thực thể hoạt động của bạn sẽ được dùng để thiết lập mối quan hệ với một thực thể khác.
   - **Thứ hai**: Thực thể khách hàng nguồn tương ứng mà thực thể hoạt động của bạn sẽ có mối quan hệ. Bạn chỉ có thể liên kết với các thực thể khách hàng nguồn được dùng trong quá trình hợp nhất dữ liệu.
   - **Thứ ba** : Nếu mối quan hệ giữa thực thể hoạt động này và thực thể khách hàng nguồn được chọn đã tồn tại, thì tên mối quan hệ sẽ ở chế độ chỉ đọc. Nếu không có mối quan hệ nào như vậy tồn tại, một mối quan hệ mới sẽ được tạo theo tên mà bạn cung cấp trong hộp này.

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Xác định mối quan hệ của thực thể.":::

1. Chọn **Tiếp** để chuyển sang bước tiếp theo. 

1. Trong bước **Hợp nhất hoạt động**, hãy chọn sự kiện hoạt động và thời gian bắt đầu hoạt động của bạn. 
   - **Trường bắt buộc**
      - **Hoạt động của sự kiện**: Trường về sự kiện cho hoạt động này.
      - **Dấu thời gian**: Trường đại diện cho thời gian bắt đầu hoạt động của bạn.

   - **Trường tùy chọn**
      - **Chi tiết bổ sung**: Trường có thông tin liên quan cho hoạt động này.
      - **Biểu tượng**: Biểu tượng thể hiện rõ nhất loại hoạt động này.
      - **Địa chỉ web**: Trường chứa URL có thông tin về hoạt động này. Ví dụ: hệ thống giao dịch lấy nguồn từ hoạt động này. URL này có thể là bất kỳ trường nào từ nguồn dữ liệu hoặc được xây dựng làm một trường mới bằng cách chuyển đổi Power Query. Dữ liệu URL sẽ được lưu trữ trong thực thể *Hoạt động đã hợp nhất*. Dữ liệu này có thể được dùng ở hạ nguồn bằng cách sử dụng [API](apis.md).

   - **Hiển thị trong dòng thời gian**
      - Chọn xem bạn có hiển thị hoạt động này trong dạng xem dòng thời gian trên hồ sơ khách hàng của bạn hay không. Chọn **Có** để hiển thị hoạt động trong dòng thời gian hoặc **Không** để ẩn hoạt động đó.

      :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="Chỉ định dữ liệu hoạt động của khách hàng trong thực thể Hoạt động đã hợp nhất.":::

1. Chọn **Tiếp** để chuyển sang bước tiếp theo. Bạn có thể chọn **Kết thúc và xem xét** để lưu hoạt động ngay bây giờ khi loại hoạt động được đặt thành **Khác**. 

1. Trong bước **Loại hoạt động**, hãy chọn loại hoạt động và tùy ý chọn nếu bạn muốn ánh xạ theo ngữ nghĩa một số loại hoạt động để sử dụng trong các khu vực khác của Customer Insights. Hiện tại, các loại hoạt động *Phản hồi*, *Khách hàng thân thiết*, *SalesOrder*, *SalesOrderLine* và *Đăng ký* có thể được ánh xạ theo ngữ nghĩa sau khi bạn đồng ý ánh xạ các trường. Nếu một loại hoạt động không phù hợp với hoạt động mới, bạn có thể chọn *Khác* hoặc *Tạo mới* cho một loại hoạt động tùy chỉnh.

1. Chọn **Tiếp** để chuyển sang bước tiếp theo. 

1. Trong bước **Xem lại**, hãy xác minh lựa chọn của bạn. Quay lại bất kỳ bước nào trước đó và cập nhật thông tin nếu cần.

   :::image type="content" source="media/Activity_Wizard5.PNG" alt-text="Xem lại các trường được chỉ định cho một hoạt động.":::
   
1. Chọn **Lưu hoạt động** để áp dụng các thay đổi của bạn và chọn **Xong** để quay lại **Dữ liệu** > **Hoạt động**. Tại đây, bạn sẽ thấy những hoạt động nào được thiết lập để hiển thị trong dòng thời gian. 

1. Trên trang **Hoạt động**, hãy chọn **Chạy** để xử lý hoạt động. 

> [!TIP]
> Có [6 loại trạng thái](system.md#status-types) cho các nhiệm vụ/quy trình. Ngoài ra, hầu hết các quy trình [phụ thuộc vào các quá trình hạ nguồn khác](system.md#refresh-policies). Bạn có thể chọn trạng thái của một quy trình để xem chi tiết về tiến trình của toàn bộ công việc. Sau khi chọn **Xem chi tiết** đối với một trong các tác vụ của công việc, bạn sẽ tìm thấy thông tin bổ sung: thời gian xử lý, ngày xử lý gần nhất và tất cả các lỗi và cảnh báo liên quan đến tác vụ.


## <a name="manage-existing-activities"></a>Quản lý các hoạt động hiện có

Trên **Dữ liệu** > **Hoạt động**, bạn có thể xem và quản lý tất cả các hoạt động mà mình đã lưu. Mỗi hoạt động được thể hiện bằng một hàng cũng bao gồm thông tin chi tiết về nguồn, thực thể và loại hoạt động.

Các hành động sau đây khả dụng khi bạn chọn một hoạt động. 

- **Chỉnh sửa**: Mở hoạt động được thiết lập ở bước đánh giá. Bạn có thể thay đổi bất kỳ hoặc tất cả cấu hình hiện tại từ bước này. Sau khi thay đổi cấu hình, hãy chọn **Lưu hoạt động** rồi chọn **Chạy** để xử lý các thay đổi.

- **Đổi tên**: Mở hộp thoại nơi bạn có thể nhập tên khác cho hoạt động đã chọn. Chọn **Lưu** để áp dụng thay đổi.

- **Xóa**: Mở hộp thoại để xác nhận việc xóa hoạt động đã chọn. Bạn cũng có thể xóa nhiều hoạt động cùng một lúc bằng cách chọn các hoạt động rồi chọn biểu tượng xóa. Chọn **Xoá** để xác nhận tác vụ xoá của bạn.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
