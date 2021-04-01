---
title: Mối quan hệ giữa các thực thể và đường dẫn thực thể
description: Tạo và quản lý mối quan hệ giữa các thực thể từ nhiều nguồn dữ liệu.
ms.date: 04/14/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: c25bfcb8e2a8223498dd1a5e8cfb3712a40ab85e
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595238"
---
# <a name="relationships-between-entities"></a>Các mối quan hệ giữa các thực thể

Mối quan hệ giúp bạn kết nối các thực thể và tạo một biểu đồ dữ liệu khi các thực thể có chung mã định danh (khóa ngoại) có thể được tham chiếu từ thực thể này sang thực thể khác. Các thực thể được kết nối cho phép bạn xác định các phân đoạn và giá trị đo dựa trên nhiều nguồn dữ liệu.

Có hai loại mối quan hệ. Mối quan hệ hệ thống không thể chỉnh sửa, được tạo tự động và mối quan hệ tùy chỉnh được tạo và định cấu hình bởi người dùng.

Trong quá trình khớp và hợp nhất, các mối quan hệ hệ thống được tạo ở phía sau dựa trên tính năng khớp thông minh. Các mối quan hệ này giúp liên kết bản ghi Hồ sơ khách hàng với bản ghi của các thực thể tương ứng khác. Sơ đồ sau minh họa việc tạo ba mối quan hệ hệ thống khi thực thể khách hàng được khớp với các thực thể bổ sung để tạo ra thực thể Hồ sơ khách hàng cuối cùng.

> [!div class="mx-imgBorder"]
> ![Tạo mối quan hệ](media/relationships-entities-merge.png "Tạo mối quan hệ")

- **Mối quan hệ *CustomerToContact*** được tạo giữa thực thể khách hàng và thực thể Người liên hệ. Thực thể Khách hàng có được trường khóa **Contact_contactId** để liên kết với trường khóa của thực thể Liên hệ **contactId**.
- **Mối quan hệ *CustomerToAccount*** được tạo giữa thực thể Khách hàng và thực thể Tài khoản. Thực thể Khách hàng có được trường khóa **Account_accountId** để liên kết với trường khóa của thực thể Tài khoản **accountId**.
- **Mối quan hệ *CustomerToWebAccount*** được tạo giữa thực thể Khách hàng và thực thể WebAccount. Thực thể Khách hàng có được trường khóa **WebAccount_webaccountId** để liên kết với trường khóa của thực thể WebAccount **webaccountId**.

## <a name="create-a-relationship"></a>Tạo một mối quan hệ

Xác định các mối quan hệ tùy chỉnh trên trang **Mối quan hệ**. Mỗi mối quan hệ bao gồm một thực thể Nguồn (thực thể giữ khóa ngoại) và thực thể Đích (thực thể mà khóa ngoại của thực thể nguồn trỏ đến).

1. Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Dữ liệu** > **Mối quan hệ**.

2. Chọn **Mối quan hệ mới**.

3. Trong ngăn **Thêm mối quan hệ**, hãy cung cấp các thông tin sau:

   > [!div class="mx-imgBorder"]
   > ![Nhập chi tiết mối quan hệ](media/relationships-add.png "Nhập chi tiết mối quan hệ")

   - **Tên mối quan hệ**: Tên phản ánh mục đích của mối quan hệ (ví dụ: **Tài khoản WebLogs**).
   - **Mô tả**: Mô tả về mối quan hệ.
   - **Thực thể nguồn**: Chọn thực thể được sử dụng làm nguồn trong mối quan hệ (ví dụ: WebLog).
   - **Lượng số**: Chọn lượng số của các bản ghi thực thể nguồn. Ví dụ: "nhiều" có nghĩa là nhiều bản ghi Weblog được liên kết với một WebAccount.
   - **Trường khóa nguồn**: Đại diện cho trường khóa ngoại trong thực thể nguồn. Ví dụ: WebLog có trường khóa ngoại **accountId**.
   - **Thực thể đích**: Chọn thực thể được sử dụng làm đích trong mối quan hệ (ví dụ: WebAccount).
   - **Lượng số đích**: Chọn lượng số của các bản ghi thực thể đích. Ví dụ: "một" có nghĩa là nhiều bản ghi Weblog được liên kết với một WebAccount.
   - **Trường khóa mục tiêu**: Trường này đại diện cho trường khóa của thực thể đích. Ví dụ: WebAccount có trường khóa ngoại **accountId**.

> [!NOTE]
> Chỉ hỗ trợ các mối quan hệ nhiều-một và một-một. Mối quan hệ nhiều-nhiều có thể được tạo bằng hai mối quan hệ nhiều-một và một thực thể liên kết (thực thể được sử dụng để kết nối thực thể nguồn và thực thể đích).

## <a name="delete-a-relationship"></a>Xóa mối quan hệ

1. Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Dữ liệu** > **Mối quan hệ**.

2. Chọn hộp kiểm tương ứng với mối quan hệ bạn muốn xóa.

3. Chọn **Xóa** ở đầu bảng **Mối quan hệ**.

4. Xác nhận tác vụ xóa của bạn.

## <a name="next-step"></a>Bước tiếp theo

Mối quan hệ hệ thống và tùy chỉnh được sử dụng để tạo các phân đoạn dựa trên nhiều nguồn dữ liệu không còn tồn tại. Để biết thêm thông tin, hãy xem [Phân khúc](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]