---
title: Ánh xạ ngữ nghĩa (Bản xem trước)
description: Tổng quan về ánh xạ ngữ nghĩa và cách sử dụng chúng.
ms.date: 09/28/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
ms.openlocfilehash: b0884b8b6a2c5abe4b3967d1b57d11a3a6d65c5b
ms.sourcegitcommit: 5d82e5b808517e0e99fdfdd7e4a4422a5b8ebd5c
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 10/11/2021
ms.locfileid: "7622962"
---
# <a name="semantic-mappings"></a>Ánh xạ ngữ nghĩa

Ánh xạ ngữ nghĩa cho phép bạn ánh xạ dữ liệu không hoạt động của mình tới các lược đồ được xác định trước. Các lược đồ này giúp thông tin chuyên sâu về đối tượng hiểu rõ hơn về các thuộc tính dữ liệu của bạn. Ánh xạ ngữ nghĩa và dữ liệu được cung cấp cho phép thông tin chuyên sâu và tính năng mới trong thông tin chuyên sâu về đối tượng. Để ánh xạ dữ liệu hoạt động của bạn vào lược đồ, hãy xem lại tài liệu [hoạt động](activities.md).

**Ánh xạ ngữ nghĩa hiện được bật cho các môi trường dựa trên tài khoản doanh nghiệp**. *ContactProfile* là loại ánh xạ ngữ nghĩa duy nhất hiện có trong thông tin chuyên sâu về đối tượng.

## <a name="define-a-contactprofile-semantic-entity-mapping"></a>Xác định ánh xạ thực thể ngữ nghĩa ContactProfile

1. Trong thông tin chuyên sâu về đối tượng, hãy chuyển đến **Dữ liệu** > **Ánh xạ ngữ nghĩa (bản xem trước)**.

1. Chọn **Thêm ánh xạ ngữ nghĩa** để bắt đầu trải nghiệm có hướng dẫn.

1. Trong bước **Dữ liệu thực thể**, hãy đặt giá trị cho các trường sau:

   - **Tên ánh xạ thực thể ngữ nghĩa**: Cung cấp tên cho ánh xạ thực thể ngữ nghĩa của bạn.
   - **Thực thể nguồn**: Chọn một thực thể bao gồm dữ liệu liên hệ.
   - **Khóa chính**: Chọn trường xác định duy nhất một bản ghi liên hệ. Nó không nên chứa bất kỳ giá trị trùng lặp, giá trị trống hoặc giá trị thiếu nào.

   :::image type="content" source="media/Semantic_Mapping_Wizard1.png" alt-text="Thiết lập ánh xạ thực thể ngữ nghĩa bằng tên, thực thể nguồn và khóa chính.":::

1. Chọn **Tiếp** để tiếp tục.

1. Trong bước **Mối quan hệ**, đặt cấu hình chi tiết để kết nối dữ liệu liên hệ của bạn với dữ liệu tài khoản tương ứng. Bước này trực quan hóa kết nối giữa các thực thể.  

   Có hai loại đường dẫn mối quan hệ có thể được thực hiện: **Mối quan hệ trực tiếp** và **Mối quan hệ gián tiếp**. Để biết thêm thông tin, hãy xem [đường dẫn mối quan hệ gián tiếp và trực tiếp](relationships.md#relationship-paths).

   1. Chọn **Thêm mối quan hệ** để đặt cấu hình mối quan hệ.
   1. Chọn thuộc tính từ thực thể nguồn kết nối thực thể liên hệ của bạn với một thực thể khác.
   1. Chọn thực thể để kết nối với thực thể liên hệ. Bạn có thể chọn thực thể từ **Thực thể tài khoản** hoặc **Thực thể trung gian**. Nếu bạn chọn một thực thể trung gian, bạn cần xác định mối quan hệ thứ hai để kết nối với thực thể tài khoản mục tiêu của mình.

      :::image type="content" source="media/Semantic_Mapping_Wizard2.png" alt-text="Chọn thực thể Tài khoản hoặc thực thể Trung gian.":::

   1. Cung cấp **Tên mối quan hệ**. Nếu mối quan hệ giữa các thực thể của bạn đã tồn tại, thì tên mối quan hệ ở chế độ chỉ đọc. Nếu không có mối quan hệ nào tồn tại, một mối quan hệ mới sẽ được tạo với tên bạn cung cấp.
   1. Chọn **Áp dụng** để hoàn thành quá trình đặt cấu hình mối quan hệ.

   > [!NOTE]
   > Bạn có thể đặt cấu hình nhiều mối quan hệ hơn giữa thực thể liên hệ và các thực thể tài khoản khác với các thực thể trung gian.
   >  :::image type="content" source="media/Semantic_Mapping_Wizard4.png" alt-text="Minh họa các mối quan hệ khác nhau kết nối các thực thể liên hệ với các thực thể tài khoản.":::

1. Chọn **Tiếp** khi bạn hoàn thành cấu hình mối quan hệ.

1. Trong bước **Đặt loại ngữ nghĩa**, chọn một **Loại ngữ nghĩa**. Hiện tại, có một **Loại ngữ nghĩa** gọi là *ContactProfile*.

1. Ánh xạ dữ liệu của bạn đến loại ngữ nghĩa *ContactProfile* **Semantic type** cho trường được hiển thị.
   - Trường bắt buộc: ID liên hệ
   - Trường tùy chọn: Họ, tên, ngày sinh, giới tính, email chính và số điện thoại chính

   :::image type="content" source="media/Semantic_Mapping_Wizard5.png" alt-text="Ánh xạ các thuộc tính dữ liệu liên hệ của bạn với các trường bắt buộc và tùy chọn được cung cấp.":::

1. Chọn **Tiếp** để tiếp tục.

1. Trong bước **Xem lại**, hãy xem cấu hình của ánh xạ ngữ nghĩa. Chọn **Chỉnh sửa** cho phần tương ứng để thay đổi.

1. Chọn **Lưu** để lưu **Ánh xạ ngữ nghĩa** mới của bạn.

1. Sau khi lưu, bạn có thể chọn quy trình **Chạy** ánh xạ ngữ nghĩa hoặc chọn **Đóng** để lưu ánh xạ ngữ nghĩa mà không xử lý.

1. Để chạy ánh xạ ngữ nghĩa vào lúc khác, hãy chọn ánh xạ ngữ nghĩa rồi chọn **Làm mới**.

> [!TIP]
> Có [6 loại trạng thái](system.md#status-types) cho các nhiệm vụ/quy trình. Ngoài ra, hầu hết các quy trình [phụ thuộc vào các quá trình hạ nguồn khác](system.md#refresh-policies). Bạn có thể chọn trạng thái của một quy trình để xem chi tiết về tiến trình của toàn bộ công việc. Sau khi chọn **Xem chi tiết** đối với một trong các tác vụ của công việc, bạn sẽ tìm thấy thông tin bổ sung: thời gian xử lý, ngày xử lý gần nhất và tất cả các lỗi và cảnh báo liên quan đến tác vụ.

## <a name="manage-existing-semantic-mappings"></a>Quản lý ánh xạ ngữ nghĩa hiện có

Trên **Dữ liệu** > **Ánh xạ ngữ nghĩa (bản xem trước)**, bạn có thể xem tất cả ánh xạ đã lưu và quản lý chúng. Mỗi ánh xạ ngữ nghĩa được biểu diễn bằng một hàng riêng biệt. Bạn sẽ tìm thấy thông tin chi tiết về thực thể nguồn, kiểu ngữ nghĩa, kiểu ánh xạ và trạng thái của nó.

:::image type="content" source="media/semantic-mapping-options.png" alt-text="Các tùy chọn để quản lý ánh xạ ngữ nghĩa.":::

- **Chỉnh sửa**: Mở cấu hình ánh xạ ngữ nghĩa đã thiết lập trong bước xem lại. Bạn có thể thay đổi cấu hình hiện tại. Chọn **Lưu** và **Chạy** để thay đổi.

- **Làm mới**: Làm mới ánh xạ ngữ nghĩa đã chọn với dữ liệu cập nhật nhất từ các thực thể nằm trong cấu hình của nó. Việc làm mới bất kỳ ánh xạ ngữ nghĩa nào đã cho sẽ làm mới tất cả các ánh xạ ngữ nghĩa cùng loại.

- **Đổi tên**: Mở hộp thoại trong đó bạn có thể nhập một tên khác cho ánh xạ ngữ nghĩa đã chọn. Chọn **Lưu** để áp dụng thay đổi.

- **Xóa**: Mở hộp thoại để xác nhận việc xóa ánh xạ ngữ nghĩa đã chọn. Bạn cũng có thể xóa nhiều ánh xạ ngữ nghĩa cùng một lúc bằng cách chọn ánh xạ ngữ nghĩa và biểu tượng xóa. Chọn **Xóa** để xác nhận thao tác xóa.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
