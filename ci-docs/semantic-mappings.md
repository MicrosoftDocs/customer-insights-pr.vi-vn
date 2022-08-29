---
title: Ánh xạ ngữ nghĩa (bản xem trước)
description: Tổng quan về ánh xạ ngữ nghĩa và cách sử dụng chúng.
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.reviewer: v-wendysmith
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-semantic-mapping
- customerInsights
ms.openlocfilehash: 8780c11c8b091717349f0fd75a36b99c3a63ab49
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303947"
---
# <a name="semantic-mappings-preview"></a>Ánh xạ ngữ nghĩa (bản xem trước)

> [!NOTE]
> Các **Ánh xạ ngữ nghĩa** trang chỉ khả dụng cho môi trường kinh doanh (B-to-B) nơi các hồ sơ liên hệ đã được tạo bằng cách sử dụng trang này. Bạn có thể tiếp tục tạo và quản lý hồ sơ liên hệ cá nhân bằng cách sử dụng **Ánh xạ ngữ nghĩa** trang. Hoặc, [thống nhất dữ liệu liên hệ của bạn](data-unification-contacts.md) để loại bỏ các bản sao, xác định các kết quả trùng khớp giữa các thực thể và tạo một hồ sơ liên hệ thống nhất. Sau đó, bạn có thể sử dụng hồ sơ liên hệ hợp nhất để tạo các hoạt động cấp liên hệ.

Ánh xạ ngữ nghĩa cho phép bạn ánh xạ dữ liệu không hoạt động của mình tới các lược đồ được xác định trước. Các lược đồ này giúp Thông tin chi tiết về khách hàng hiểu rõ hơn về các thuộc tính dữ liệu của bạn. Lập bản đồ ngữ nghĩa và dữ liệu được cung cấp cho phép các tính năng và thông tin chi tiết mới trong Thông tin chi tiết về khách hàng. Để ánh xạ dữ liệu hoạt động của bạn vào lược đồ, hãy xem lại tài liệu [hoạt động](activities.md).

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

[!INCLUDE [footer-include](includes/footer-banner.md)]
