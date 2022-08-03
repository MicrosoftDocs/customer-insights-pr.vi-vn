---
title: Ánh xạ ngữ nghĩa (bản xem trước)
description: Tổng quan về ánh xạ ngữ nghĩa và cách sử dụng chúng.
ms.date: 12/01/2021
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-semantic-mapping
- customerInsights
ms.openlocfilehash: 7c9588ac7a132ca6f43cf26ea3a744109a0dd2b8
ms.sourcegitcommit: ad74ace653db9a25fce4343adef7db1c9b0d8904
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 07/21/2022
ms.locfileid: "9183657"
---
# <a name="semantic-mappings-preview"></a>Ánh xạ ngữ nghĩa (bản xem trước)

Ánh xạ ngữ nghĩa cho phép bạn ánh xạ dữ liệu không hoạt động của mình tới các lược đồ được xác định trước. Các lược đồ này giúp Thông tin chi tiết về khách hàng hiểu rõ hơn về các thuộc tính dữ liệu của bạn. Ánh xạ ngữ nghĩa và dữ liệu được cung cấp cho phép các tính năng và thông tin chi tiết mới trong Thông tin chi tiết về khách hàng. Để ánh xạ dữ liệu hoạt động của bạn vào lược đồ, hãy xem lại tài liệu [hoạt động](activities.md).

**Ánh xạ ngữ nghĩa hiện được bật cho các môi trường dựa trên tài khoản doanh nghiệp**. *ContactProfile* là loại ánh xạ ngữ nghĩa duy nhất hiện có trong Thông tin chi tiết về khách hàng.

## <a name="define-a-contactprofile-semantic-entity-mapping"></a>Xác định ánh xạ thực thể ngữ nghĩa ContactProfile

1. Đi đến **Dữ liệu** > **Ánh xạ ngữ nghĩa (xem trước)**.

1. Chọn **Thêm ánh xạ ngữ nghĩa** để bắt đầu trải nghiệm có hướng dẫn.

1. Trong bước **Dữ liệu thực thể**, hãy đặt giá trị cho các trường sau:

   - **Tên ánh xạ thực thể ngữ nghĩa** : Tên cho ánh xạ thực thể ngữ nghĩa của bạn.
   - **Thực thể nguồn** : Thực thể bao gồm dữ liệu liên hệ.
   - **Khóa chính** : Trường xác định duy nhất một bản ghi liên hệ. Nó không nên chứa bất kỳ giá trị trùng lặp, giá trị trống hoặc giá trị thiếu nào.

   :::image type="content" source="media/Semantic_Mapping_Wizard1.png" alt-text="Thiết lập ánh xạ thực thể ngữ nghĩa bằng tên, thực thể nguồn và khóa chính.":::

1. Chọn **Tiếp theo**.

1. Trong bước **Mối quan hệ**, đặt cấu hình chi tiết để kết nối dữ liệu liên hệ của bạn với dữ liệu tài khoản tương ứng. Bước này trực quan hóa kết nối giữa các thực thể.  

   Có hai loại đường dẫn mối quan hệ có thể được thực hiện: **Mối quan hệ trực tiếp** và **Mối quan hệ gián tiếp**. Để biết thêm thông tin, hãy xem [đường dẫn mối quan hệ gián tiếp và trực tiếp](relationships.md#relationship-paths).

   1. Lựa chọn **Thêm mối quan hệ** để định cấu hình mối quan hệ.
   1. Chọn thuộc tính từ thực thể nguồn kết nối thực thể liên hệ của bạn với một thực thể khác.
   1. Chọn thực thể để kết nối với thực thể liên hệ. Chọn một thực thể từ **Các thực thể tài khoản** hoặc là **Thực thể trung gian** tiết diện. Nếu bạn chọn một thực thể trung gian, hãy xác định mối quan hệ thứ hai để kết nối với thực thể tài khoản mục tiêu của bạn.

      :::image type="content" source="media/Semantic_Mapping_Wizard2.png" alt-text="Chọn thực thể Tài khoản hoặc thực thể Trung gian.":::

   1. Cung cấp **Tên mối quan hệ**. Nếu mối quan hệ giữa các thực thể của bạn đã tồn tại, thì tên mối quan hệ ở chế độ chỉ đọc. Nếu không có mối quan hệ nào tồn tại, một mối quan hệ mới sẽ được tạo với tên bạn cung cấp.
   1. Chọn **Áp dụng** để hoàn thành quá trình đặt cấu hình mối quan hệ.

   > [!NOTE]
   > Bạn có thể đặt cấu hình nhiều mối quan hệ hơn giữa thực thể liên hệ và các thực thể tài khoản khác với các thực thể trung gian.
   
     :::image type="content" source="media/Semantic_Mapping_Wizard4.png" alt-text="Minh họa các mối quan hệ khác nhau kết nối các thực thể liên hệ với các thực thể tài khoản.":::

1. Chọn **Tiếp theo**.

1. Trong bước **Đặt loại ngữ nghĩa**, chọn một **Loại ngữ nghĩa**. Hiện tại, có một **Loại ngữ nghĩa** gọi là *ContactProfile*.

1. Ánh xạ id liên hệ của bạn với *ContactProfile* loại ngữ nghĩa **ID liên hệ**. Theo tùy chọn, ánh xạ các trường khác như tên, họ, giới tính hoặc email.

   :::image type="content" source="media/Semantic_Mapping_Wizard5.png" alt-text="Ánh xạ các thuộc tính dữ liệu liên hệ của bạn với các trường bắt buộc và tùy chọn được cung cấp.":::

1. Chọn **Tiếp theo**.

1. Bên trong **Kiểm tra lại** bước, xem lại cấu hình của ánh xạ ngữ nghĩa. Để thực hiện các thay đổi, hãy chọn **Chỉnh sửa** cho phần tương ứng.

1. Chọn **Lưu.**

1. Để xử lý ánh xạ ngữ nghĩa, hãy chọn **Chạy**. Hoặc chọn **Đóng** để lưu ánh xạ ngữ nghĩa của bạn mà không cần xử lý nó. Để chạy nó sau, hãy chọn ánh xạ ngữ nghĩa và chọn **Làm mới**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="manage-existing-semantic-mappings"></a>Quản lý ánh xạ ngữ nghĩa hiện có

Đi đến **Dữ liệu** > **Ánh xạ ngữ nghĩa (xem trước)** để xem các ánh xạ ngữ nghĩa đã lưu của bạn, thực thể nguồn, loại ngữ nghĩa, loại ánh xạ và trạng thái của chúng.

:::image type="content" source="media/semantic-mapping-options.png" alt-text="Các tùy chọn để quản lý ánh xạ ngữ nghĩa.":::

Chọn ánh xạ ngữ nghĩa để xem các hành động có sẵn.
- **Chỉnh sửa** cấu hình hiện tại. Chọn **Lưu** và **Chạy** để thay đổi.
- **Làm mới** ánh xạ ngữ nghĩa để bao gồm dữ liệu mới nhất. Việc làm mới bất kỳ ánh xạ ngữ nghĩa nào đã cho sẽ làm mới tất cả các ánh xạ ngữ nghĩa cùng loại.
- **Đổi tên** ánh xạ ngữ nghĩa. Chọn **Lưu.**
- **Xóa bỏ** ánh xạ ngữ nghĩa. Để xóa nhiều ánh xạ ngữ nghĩa cùng một lúc, hãy chọn ánh xạ ngữ nghĩa và biểu tượng xóa. Chọn **Xóa** để xác nhận thao tác xóa.

## <a name="use-a-contactprofile-semantic-entity-mapping-to-create-contact-level-activities"></a>Sử dụng ánh xạ thực thể ngữ nghĩa ContactProfile để tạo các hoạt động cấp liên hệ

Sau khi tạo một *ContactProfile* ánh xạ thực thể ngữ nghĩa, bạn có thể nắm bắt các hoạt động của các liên hệ. Nó cho phép bạn xem trong dòng thời gian hoạt động cho tài khoản mà người liên hệ chịu trách nhiệm cho mỗi hoạt động. Hầu hết các bước tuân theo cấu hình lập bản đồ hoạt động điển hình.

   > [!NOTE]
   > Để các hoạt động cấp liên hệ hoạt động, bạn phải có cả hai **ID tài khoản** và **ID liên hệ** các thuộc tính cho mỗi bản ghi trong dữ liệu hoạt động của bạn.

1. [Xác định một *ContactProfile* ánh xạ thực thể ngữ nghĩa](#define-a-contactprofile-semantic-entity-mapping) và chạy ánh xạ ngữ nghĩa.

1. Đi đến **Dữ liệu** > **Các hoạt động**.

1. Lựa chọn **Thêm hoạt động** để tạo một hoạt động mới.

1. Đặt tên cho hoạt động, chọn thực thể hoạt động nguồn và chọn khóa chính của thực thể hoạt động.

1. Bên trong **Các mối quan hệ**, tạo mối quan hệ gián tiếp giữa dữ liệu nguồn hoạt động của bạn với các tài khoản, sử dụng dữ liệu liên hệ của bạn làm thực thể trung gian. Để biết thêm thông tin, hãy xem [các con đường quan hệ trực tiếp và gián tiếp](relationships.md#relationship-paths).
   - Mối quan hệ mẫu cho một hoạt động được gọi là *Mua hàng*:
      - **Dữ liệu hoạt động nguồn mua hàng** > **Dữ liệu liên hệ** trên thuộc tính **ID liên hệ**
      - **Dữ liệu liên hệ** > **Dữ liệu tài khoản** trên thuộc tính **ID tài khoản**

   :::image type="content" source="media/Contact_Activities1.png" alt-text="Thiết lập mối quan hệ mẫu.":::

1. Sau khi thiết lập các mối quan hệ, hãy chọn **Tiếp theo** và hoàn thành cấu hình lập bản đồ hoạt động của bạn. Để biết các bước chi tiết về tạo hoạt động, hãy xem [xác định một hoạt động](activities.md).

1. Chạy bản đồ hoạt động của bạn.

1. Sau khi ánh xạ hoạt động cấp liên hệ chạy, hãy chọn **Khách hàng**. Các hoạt động cấp liên hệ hiển thị trên dòng thời gian của khách hàng của bạn.

   :::image type="content" source="media/Contact_Activities2.png" alt-text="Kết quả cuối cùng sau khi định cấu hình các hoạt động liên hệ":::

### <a name="contact-level-activity-timeline-filtering"></a>Lọc dòng thời gian hoạt động cấp liên hệ

Tiến trình hoạt động cho khách hàng của bạn bao gồm ID hoặc tên của họ, tùy thuộc vào *ContactProfile* cấu hình, cho các hoạt động mà họ đã thực hiện. Lọc các hoạt động theo các liên hệ trong dòng thời gian để xem các liên hệ cụ thể mà bạn quan tâm. Để xem tất cả các hoạt động không được chỉ định cho một số liên lạc cụ thể, hãy chọn **Các hoạt động không được ánh xạ tới một Liên hệ**.

:::image type="content" source="media/Contact_Activities3.png" alt-text="Các tùy chọn lọc có sẵn cho các hoạt động cấp Liên hệ.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
