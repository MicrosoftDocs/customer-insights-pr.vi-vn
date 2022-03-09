---
title: Tạo và sửa đổi sự kiện
description: Cách tạo và sửa đổi sự kiện.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: dbafa2231daa82c34ee2ec8292111575e95af675
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 02/16/2022
ms.locfileid: "8228229"
---
# <a name="create-and-modify-events"></a>Tạo và sửa đổi sự kiện

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Sự kiện là dữ liệu đại diện cho hành vi của người dùng, chẳng hạn như hoạt động trên một trang web.

- Sự kiện *cơ sở* ghi lại khi người dùng xem một trang (sự kiện xem) hoặc tương tác với nội dung (sự kiện hành động).
- Sự kiện *tinh chỉnh* là một dạng xem ảo của một sự kiện cơ sở. Bạn xác định các sự kiện tinh chỉnh bằng cách xóa và thêm thuộc tính hoặc bằng cách lọc các sự kiện dựa trên giá trị thuộc tính.

## <a name="prerequisites"></a>Điều kiện tiên quyết

Để nhận sự kiện, trước hết, dữ liệu trang web của bạn phải được kết nối với thông tin chi tiết về mức độ tương tác với một đoạn mã. Để biết thêm thông tin, hãy xem [Cài đặt SDK web trên trang web](instrument-website.md).

 :::image type="content" source="media/new-events-connect-data.png" alt-text="Kết nối dữ liệu của bạn trước tiên.":::

## <a name="create-refined-events"></a>Tạo các sự kiện tinh chỉnh

Sử dụng các sự kiện tinh chỉnh để giảm phạm vi của một sự kiện cơ sở cho việc [xuất](export-events.md) hoặc để loại bỏ các thuộc tính không cần thiết khi hiển thị.

> [!NOTE]
> Khi bạn thêm SDK web vào trang web của mình, bạn có thể xem các sự kiện cơ sở và tạo các sự kiện đã được tinh chỉnh. 

Để xem các sự kiện cơ sở:

1. Chuyển đến phần **Dữ liệu** ở ngăn điều hướng bên trái.

1. Chọn **Sự kiện** để xem danh sách tất cả các sự kiện trong không gian làm việc.

    :::image type="content" source="media/data-events.png" alt-text="Xem sự kiện.":::

Cách tạo một sự kiện đã tinh chỉnh từ một sự kiện cơ sở: 

1. Chuyển đến **Dữ liệu** > **Sự kiện** rồi chọn **+ Sự kiện mới** ở đầu màn hình.

1. Trong hộp thoại **Sự kiện mới**, chọn **Tạo sự kiện tùy chỉnh** rồi chọn **Tiếp**.
   
     :::image type="content" source="media/new-events-wizard.png" alt-text="Trình hướng dẫn sự kiện mới.":::
     
1. Trong hộp thoại **Sự kiện mới**, nhập thông tin sau:

   - Chọn một sự kiện từ trình đơn thả xuống **Sự kiện cơ bản**.
   - Nhập tên trong hộp **Tên hiển thị của sự kiện tinh chỉnh**.
   - Theo tùy chọn, hãy cập nhật **Tên thực** được đề xuất mà không sử dụng dấu cách.

1. Chọn **Tạo** để áp dụng cài đặt của bạn.

Sự kiện đã tinh chỉnh xuất hiện trong danh sách **Sự kiện**.

### <a name="edit-event-name"></a>Chỉnh sửa tên sự kiện

Bạn có thể thay đổi tên và thuộc tính của sự kiện cơ sở hoặc sự kiện tinh chỉnh.

1. Chuyển đến **Dữ liệu** > **Sự kiện**. 

1. Chọn **Thêm [...]** cho một sự kiện và chọn **Chỉnh sửa tên**.
    
     :::image type="content" source="media/create-refined-events-options.png" alt-text="Tùy chọn để tạo các sự kiện tinh chỉnh.":::

3. Cập nhật tên sự kiện và chọn **Đổi tên**.

### <a name="view-the-details-of-a-refined-event"></a>Xem chi tiết của một sự kiện đã được tinh chỉnh:

1. Trong danh sách **Sự kiện**, chọn sự kiện cơ sở hoặc sự kiện tinh chỉnh. 

1. Chọn **Thêm và xóa thuộc tính** ở đầu màn hình để mở ngăn **Chỉnh sửa thuộc tính**. 

     :::image type="content" source="media/add-remove-properties.png" alt-text="Thêm và xóa thuộc tính.":::

1. Sử dụng các hộp kiểm để chọn các thuộc tính bạn muốn hiển thị và những thuộc tính bạn muốn ẩn. 

   :::image type="content" source="media/edit-properties-refined-events.png" alt-text="Chỉnh sửa thuộc tính cho các sự kiện tinh chỉnh.":::

1. Chọn **Xác nhận** để áp dụng lựa chọn của bạn, rồi chọn **Lưu**.


### <a name="edit-selected-properties-for-a-refined-event"></a>Chỉnh sửa các thuộc tính đã chọn cho một sự kiện đã tinh chỉnh

1. Chuyển đến **Dữ liệu** > **Sự kiện** và chọn các sự kiện tinh chỉnh để mở chế độ xem chi tiết.
1. Chọn **Thêm và xóa thuộc tính**. 
1. Chỉnh sửa lựa chọn của các hộp kiểm.
1. Chọn **Xác nhận** rồi chọn **Lưu** để áp dụng các thay đổi.

Để biết thông tin về thao tác xuất sự kiện, hãy xem [Xuất sự kiện](export-events.md).
[!INCLUDE[footer-include](../includes/footer-banner.md)]
