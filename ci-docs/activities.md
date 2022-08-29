---
title: Hoạt động liên hệ với khách hàng hoặc doanh nghiệp
description: Xác định các hoạt động liên hệ với khách hàng hoặc doanh nghiệp và xem chúng theo dòng thời gian trên hồ sơ khách hàng.
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.reviewer: v-wendysmith
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-entities
- ci-customer-card
- ci-relationships
- ci-activities
- ci-activities-wizard
- ci-measures
- ci-segment-suggestions
- customerInsights
ms.openlocfilehash: bbb8bc30d079273bc935181c628915bb3c02d982
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304131"
---
# <a name="customer-or-business-contact-activities"></a>Hoạt động liên hệ với khách hàng hoặc doanh nghiệp

Hoạt động của khách hàng là những hành động hoặc sự kiện được thực hiện bởi khách hàng hoặc những người liên hệ kinh doanh. Ví dụ: giao dịch, thời lượng cuộc gọi hỗ trợ, đánh giá trang web, mua hàng hoặc trả hàng. Các hoạt động này được chứa trong một hoặc nhiều nguồn dữ liệu. Với Thông tin chi tiết về khách hàng, hãy củng cố các hoạt động khách hàng của bạn từ những [nguồn dữ liệu](data-sources.md) và liên kết chúng với hồ sơ khách hàng. Các hoạt động này xuất hiện theo thứ tự thời gian trong một dòng thời gian trên hồ sơ khách hàng. Bao gồm tiến trình trong các ứng dụng Dynamics 365 với [Tiện ích bổ sung Thẻ khách hàng](customer-card-add-in.md) dung dịch.

## <a name="define-a-customer-activity"></a>Xác định hoạt động của khách hàng

Một thực thể phải có ít nhất một thuộc tính loại **Ngày** được đưa vào dòng thời gian của khách hàng. Kiểm soát **Thêm hoạt động** bị vô hiệu hóa nếu không tìm thấy thực thể đó.

1. Đi đến **Dữ liệu** > **Các hoạt động**.

1. Lựa chọn **Thêm hoạt động** để bắt đầu trải nghiệm được hướng dẫn.

1. Bên trong **Dữ liệu hoạt động** bước, nhập thông tin sau:

   - **Tên hoạt động**: Chọn tên cho hoạt động của bạn.
   - **Thực thể hoạt động** : Chọn một thực thể bao gồm dữ liệu giao dịch hoặc hoạt động.
   - **Khóa chính**: Chọn trường xác định duy nhất một bản ghi. Nó không nên chứa bất kỳ giá trị trùng lặp, giá trị trống hoặc giá trị thiếu nào.

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Thiết lập dữ liệu hoạt động với tên, thực thể và khóa chính.":::

1. Chọn **Tiếp theo**.

1. Bên trong **Mối quan hệ** bước, chọn **Thêm mối quan hệ** để kết nối dữ liệu hoạt động của bạn với hồ sơ khách hàng tương ứng. Bước này trực quan hóa kết nối giữa các thực thể.  

   - **Khóa ngoại** : Trường nước ngoài trong thực thể hoạt động của bạn sẽ được sử dụng để thiết lập mối quan hệ với một thực thể khác.
   - **Tới tên thực thể** : Thực thể khách hàng nguồn tương ứng mà thực thể hoạt động của bạn sẽ có mối quan hệ. Bạn chỉ có thể liên kết với các thực thể khách hàng nguồn được dùng trong quá trình hợp nhất dữ liệu.
   - **Tên mối quan hệ** : Nếu mối quan hệ giữa thực thể hoạt động này và thực thể khách hàng nguồn đã chọn đã tồn tại, tên mối quan hệ sẽ ở chế độ chỉ đọc. Nếu không có mối quan hệ nào như vậy tồn tại, một mối quan hệ mới sẽ được tạo theo tên mà bạn cung cấp trong hộp này.

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Xác định mối quan hệ của thực thể.":::

   > [!TIP]
   > Trong môi trường B2B, bạn có thể chọn giữa các thực thể tài khoản và các thực thể khác. Nếu bạn chọn một thực thể tài khoản, đường dẫn mối quan hệ sẽ tự động được đặt. Đối với các thực thể khác, bạn phải xác định đường dẫn mối quan hệ trên một hoặc nhiều thực thể trung gian cho đến khi bạn tiếp cận thực thể tài khoản.

1. Lựa chọn **Ứng dụng** để tạo mối quan hệ.

1. Chọn **Tiếp theo**.

1. Trong bước **Hợp nhất hoạt động**, hãy chọn sự kiện hoạt động và thời gian bắt đầu hoạt động của bạn.
   - **Trường bắt buộc**
      - **Hoạt động của sự kiện**: Trường về sự kiện cho hoạt động này.
      - **Dấu thời gian**: Trường đại diện cho thời gian bắt đầu hoạt động của bạn.

   - **Trường tùy chọn**
      - **Chi tiết bổ sung**: Trường có thông tin liên quan cho hoạt động này.
      - **Biểu tượng**: Biểu tượng thể hiện rõ nhất loại hoạt động này.
      - **Địa chỉ web**: Trường chứa URL có thông tin về hoạt động này. Ví dụ: hệ thống giao dịch lấy nguồn từ hoạt động này. URL này có thể là bất kỳ trường nào từ nguồn dữ liệu hoặc nó có thể được tạo thành một trường mới bằng cách sử dụng Power Query sự biến đổi. Dữ liệu URL sẽ được lưu trữ trong thực thể *Hoạt động đã hợp nhất*. Dữ liệu này có thể được dùng ở hạ nguồn bằng cách sử dụng [API](apis.md).

   - **Hiển thị trong dòng thời gian**
      - Chọn xem bạn có hiển thị hoạt động này trong dạng xem dòng thời gian trên hồ sơ khách hàng của bạn hay không. Chọn **Có** để hiển thị hoạt động trong dòng thời gian hoặc **Không** để ẩn hoạt động đó.

      :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="Chỉ định dữ liệu hoạt động của khách hàng trong thực thể Hoạt động đã hợp nhất.":::

1. Lựa chọn **Tiếp theo** để chọn loại hoạt động hoặc chọn **Kết thúc và xem xét** để lưu hoạt động với loại hoạt động được đặt thành **Khác**.

1. Trong bước **Loại hoạt động**, hãy chọn loại hoạt động và tùy ý chọn nếu bạn muốn ánh xạ theo ngữ nghĩa một số loại hoạt động để sử dụng trong các khu vực khác của Customer Insights. Hiện nay, *Nhận xét*, *trung thành*, *đặt hàng*, *·*, và *Đăng ký* các loại hoạt động hỗ trợ ngữ nghĩa sau khi đồng ý lập bản đồ các trường. Nếu một loại hoạt động không phù hợp với hoạt động mới, bạn có thể chọn *Khác* hoặc *Tạo mới* cho một loại hoạt động tùy chỉnh.

1. Chọn **Tiếp theo**.

1. Trong bước **Xem lại**, hãy xác minh lựa chọn của bạn. Quay lại bất kỳ bước nào trước đó và cập nhật thông tin nếu cần.

1. Chọn **Lưu hoạt động** để áp dụng các thay đổi của bạn và chọn **Xong** để quay lại **Dữ liệu** > **Hoạt động**. Hoạt động đã tạo hiển thị.

1. Sau khi tạo tất cả các hoạt động của bạn, hãy chọn **Chạy** để xử lý chúng.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="manage-existing-customer-activities"></a>Quản lý các hoạt động hiện tại của khách hàng

Đi đến **Dữ liệu** > **Các hoạt động** để xem các hoạt động đã lưu của bạn, thực thể nguồn của chúng, loại hoạt động và liệu chúng có được đưa vào dòng thời gian của khách hàng hay không. Bạn có thể sắp xếp danh sách hoạt động theo bất kỳ cột nào hoặc sử dụng hộp tìm kiếm để tìm hoạt động bạn muốn quản lý.

Chọn một hoạt động để xem các hành động có sẵn.

- **Chỉnh sửa** hoạt động để thay đổi cấu hình của nó. Cấu hình sẽ mở ở bước xem xét. Sau khi thay đổi cấu hình, hãy chọn **Lưu hoạt động** rồi chọn **Chạy** để xử lý các thay đổi.
- **Đổi tên** hoạt động. Chọn **Lưu** để áp dụng thay đổi.
- **Xóa bỏ** hoạt động. Để xóa nhiều hoạt động cùng một lúc, hãy chọn các hoạt động và sau đó **Xóa bỏ**. Xác nhận tác vụ xóa này.

## <a name="view-activity-timelines-on-customer-profiles"></a>Xem tiến trình hoạt động trên hồ sơ khách hàng

1. Nếu bạn đã chọn **Hiển thị trong dòng thời gian hoạt động** trong cấu hình hoạt động, hãy chuyển đến **Khách hàng** và chọn hồ sơ khách hàng để xem các hoạt động của khách hàng trong **Dòng thời gian hoạt động** tiết diện.

   :::image type="content" source="media/Activity_Timeline1.PNG" alt-text="Xem các hoạt động đã đặt cấu hình trong Hồ sơ khách hàng.":::

1. Để lọc các hoạt động trong dòng thời gian hoạt động:

   - Chọn một hoặc nhiều biểu tượng hoạt động để tinh chỉnh kết quả của bạn để chỉ bao gồm các loại đã chọn.

     :::image type="content" source="media/Activity_Timeline2.PNG" alt-text="Lọc các hoạt động theo loại bằng cách sử dụng các biểu tượng.":::

   - Lựa chọn **Lọc** để mở bảng điều khiển bộ lọc để định cấu hình bộ lọc dòng thời gian của bạn. Lọc bởi *ActivityType* và / hoặc *Ngày*. Chọn **Áp dụng**.

     :::image type="content" source="media/Activity_Timeline3.PNG" alt-text="Sử dụng bảng điều khiển bộ lọc để đặt cấu hình các điều kiện bộ lọc.":::

> [!NOTE]
> Bộ lọc hoạt động bị xóa khi bạn rời khỏi hồ sơ khách hàng. Bạn phải áp dụng chúng mỗi khi mở hồ sơ khách hàng.

## <a name="define-a-contact-activity"></a>Xác định hoạt động liên hệ

Đối với tài khoản doanh nghiệp (B-to-B), hãy sử dụng *ContactProfile* thực thể để nắm bắt các hoạt động của các liên hệ. Bạn có thể thấy trong dòng thời gian hoạt động cho tài khoản mà người liên hệ chịu trách nhiệm cho từng hoạt động. Hầu hết các bước tuân theo cấu hình lập bản đồ hoạt động của khách hàng.

   > [!NOTE]
   > Để xác định một hoạt động cấp liên hệ, *ContactProfile* thực thể phải được tạo, dưới dạng [hồ sơ liên hệ thống nhất](data-unification-contacts.md) hoặc thông qua [ánh xạ ngữ nghĩa](semantic-mappings.md#define-a-contactprofile-semantic-entity-mapping).
   >
   > Bạn phải có cả hai **ID tài khoản** và **ID liên hệ** thuộc tính cho từng bản ghi trong dữ liệu hoạt động của bạn.
  
1. Đi đến **Dữ liệu** > **Các hoạt động**.

1. Lựa chọn **Thêm hoạt động**.

1. Đặt tên cho hoạt động, chọn thực thể hoạt động nguồn và chọn khóa chính của thực thể hoạt động.

1. Bên trong **Các mối quan hệ**, tạo mối quan hệ gián tiếp giữa dữ liệu nguồn hoạt động của bạn với các tài khoản, sử dụng dữ liệu liên hệ của bạn làm thực thể trung gian. Để biết thêm thông tin, hãy xem [các con đường quan hệ trực tiếp và gián tiếp](relationships.md#relationship-paths).
   - Mối quan hệ mẫu cho một hoạt động được gọi là *Mua hàng*:
      - **Dữ liệu hoạt động nguồn mua hàng** > **Dữ liệu liên hệ** trên thuộc tính **ID liên hệ**
      - **Dữ liệu liên hệ** > **Dữ liệu tài khoản** trên thuộc tính **ID tài khoản**

   :::image type="content" source="media/Contact_Activities1.png" alt-text="Thiết lập mối quan hệ mẫu.":::

1. Sau khi thiết lập các mối quan hệ, hãy chọn **Tiếp theo** và hoàn thành cấu hình lập bản đồ hoạt động của bạn. Để biết các bước chi tiết về tạo hoạt động, hãy xem [xác định một hoạt động của khách hàng](#define-a-customer-activity).

1. Chạy bản đồ hoạt động của bạn.

1. Các hoạt động cấp liên hệ của bạn giờ đây sẽ hiển thị trên dòng thời gian của khách hàng.

   :::image type="content" source="media/Contact_Activities2.png" alt-text="Kết quả cuối cùng sau khi định cấu hình các hoạt động liên hệ":::

## <a name="contact-level-activity-timeline-filtering"></a>Lọc dòng thời gian hoạt động cấp liên hệ

Sau khi định cấu hình ánh xạ hoạt động cấp liên hệ và chạy nó, tiến trình hoạt động cho khách hàng của bạn sẽ được cập nhật. Nó bao gồm ID hoặc tên của họ, tùy thuộc vào *ContactProfile* cấu hình cho các hoạt động mà họ đã thực hiện. Bạn có thể lọc các hoạt động theo các liên hệ trong dòng thời gian để xem các liên hệ cụ thể mà bạn quan tâm. Ngoài ra, bạn có thể xem tất cả các hoạt động không được chỉ định cho một liên hệ cụ thể bằng cách chọn **Các hoạt động không được ánh xạ tới một Liên hệ**.

   :::image type="content" source="media/Contact_Activities3.png" alt-text="Các tùy chọn lọc có sẵn cho các hoạt động cấp Liên hệ.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
