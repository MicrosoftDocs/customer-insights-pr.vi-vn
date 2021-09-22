---
title: Tạo và sửa đổi các sự kiện được tinh chỉnh
description: Cách tạo và sửa đổi sự kiện tinh chỉnh.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 04/30/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 0344bac5f4d43df853309f43c94d95f962937f77c936ed7305c5de4a08835f04
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034800"
---
# <a name="create-and-modify-refined-events"></a>Tạo và sửa đổi các sự kiện được tinh chỉnh

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]


Sự kiện là dữ liệu đại diện cho hành vi của người dùng, chẳng hạn như hoạt động trên một trang web.

- Sự kiện *cơ sở* ghi lại khi người dùng xem một trang (sự kiện xem) hoặc tương tác với nội dung (sự kiện hành động).
- Sự kiện *tinh chỉnh* là một dạng xem ảo của một sự kiện cơ sở. Bạn xác định các sự kiện tinh chỉnh bằng cách xóa và thêm thuộc tính hoặc bằng cách lọc các sự kiện dựa trên giá trị thuộc tính.

Sử dụng các sự kiện tinh chỉnh để giảm phạm vi của một sự kiện cơ sở cho việc [xuất](export-events.md) hoặc để loại bỏ các thuộc tính không cần thiết khi hiển thị.

## <a name="create-refined-events"></a>Tạo các sự kiện tinh chỉnh

Có ba cách để tạo một sự kiện tinh chỉnh từ một sự kiện cơ sở. 

1. Chuyển đến **Dữ liệu**> **Sự kiện** và chọn một trong các tùy chọn sau:
    - Chọn **Sự kiện mới** rồi chọn **Tạo sự kiện tinh chỉnh**.
    - Chọn một sự kiện cơ sở để mở chế độ xem chi tiết và chọn **Tạo sự kiện tinh chỉnh** từ menu trên cùng.
    - Chọn **Thêm [...]** để mở menu lối tắt cho một sự kiện cơ sở. Sau đó chọn **Tạo sự kiện tinh chỉnh**.
    
    :::image type="content" source="media/create-refined-events-options.png" alt-text="Tùy chọn để tạo các sự kiện tinh chỉnh.":::

1. Trong hộp thoại **Tạo sự kiện tinh chỉnh**, hãy nhập thông tin sau:

- Chọn một sự kiện từ danh sách **Sự kiện cơ sở** thả xuống nếu bạn đang tạo một sự kiện mới.
- Nhập tên trong hộp **Tên hiển thị của sự kiện tinh chỉnh**.
- Theo tùy chọn, hãy cập nhật **Tên thực** được đề xuất mà không sử dụng dấu cách.

3. Chọn **Tạo** để áp dụng cài đặt của bạn.

1. Trong chế độ xem chi tiết về sự kiện tinh chỉnh, hãy chọn **Thêm và xóa thuộc tính** để mở ngăn **Chỉnh sửa thuộc tính**. 

1. Sử dụng các hộp kiểm để chọn các thuộc tính bạn muốn hiển thị và những thuộc tính bạn muốn ẩn. 
   :::image type="content" source="media/edit-properties-refined-events.png" alt-text="Chỉnh sửa thuộc tính cho các sự kiện tinh chỉnh.":::

1. Chọn **Xác nhận** để áp dụng lựa chọn của bạn.

1. Chọn **Lưu** để lưu cấu hình.

## <a name="edit-refined-events"></a>Chỉnh sửa các sự kiện tinh chỉnh

Bạn có thể thay đổi tên và thuộc tính của một sự kiện tinh chỉnh.

### <a name="edit-event-name"></a>Chỉnh sửa tên sự kiện

1. Chuyển đến **Dữ liệu** > **Sự kiện**. 
1. Chọn **Thêm [...]** cho một sự kiện và chọn **Chỉnh sửa tên**.
1. Cập nhật tên sự kiện và chọn **Đổi tên**.

### <a name="edit-selected-properties"></a>Chỉnh sửa thuộc tính đã chọn

1. Chuyển đến **Dữ liệu** > **Sự kiện** và chọn các sự kiện tinh chỉnh để mở chế độ xem chi tiết.
1. Chọn **Thêm và xóa thuộc tính**. 
1. Chỉnh sửa lựa chọn của các hộp kiểm.
1. Chọn **Xác nhận** rồi chọn **Lưu** để áp dụng các thay đổi.

Để biết thông tin về thao tác xuất sự kiện, hãy xem [Xuất sự kiện](export-events.md).
[!INCLUDE[footer-include](../includes/footer-banner.md)]
