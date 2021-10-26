---
title: Xem và tạo thứ nguyên
description: Cách tạo, chỉnh sửa và xóa thứ nguyên.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 136da1e1265c7087d861712d34d011b09cb60ad5
ms.sourcegitcommit: 565637f49cbdd05a82f42784f594c19cac299140
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 10/11/2021
ms.locfileid: "7623658"
---
# <a name="view-and-create-dimensions"></a>Xem và tạo thứ nguyên

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Thứ nguyên là thuộc tính của sự kiện, có thể mô tả, lọc hoặc nhóm dữ liệu. Nếu đang chạy quảng cáo tiếp thị trên trang web của mình, bạn có thể sử dụng các thứ nguyên để sắp xếp khách truy cập theo người dùng mới và người dùng cũ.  

Thông tin chuyên sâu về tương tác bao gồm các thứ nguyên có sẵn (OOB) cho các thuộc tính sự kiện. Ví dụ bao gồm:

- Tên trình duyệt
- Tên trang
- Mẫu thiết bị
- Hệ điều hành
- Quốc gia

## <a name="view-dimensions"></a>Xem thứ nguyên

Thứ nguyên dựa trên các thuộc tính sự kiện hiện có. Khi bạn sử dụng mã theo dõi cho thông tin chuyên sâu về tương tác, thứ nguyên hệ thống sẽ được tạo tự động.

1. Chuyển đến phần **Dữ liệu** ở ngăn điều hướng bên trái. 
1. Chọn **Thứ nguyên** để xem danh sách tất cả các thứ nguyên trong không gian làm việc. 
   > [!NOTE]
   > Các thứ nguyên do hệ thống tạo đều ở chế độ chỉ đọc. Bạn không thể chỉnh sửa các thứ nguyên này. Bạn chỉ có thể tạo và chỉnh sửa thứ nguyên tùy chỉnh.

## <a name="create-a-dimension"></a>Tạo thứ nguyên

Ngoài thứ nguyên do hệ thống tạo, quản trị viên môi trường và không gian làm việc có thể tạo thứ nguyên tùy chỉnh. Thứ nguyên tùy chỉnh dựa trên các thuộc tính mặc định của sự kiện cơ sở hoặc có thể sử dụng [các thuộc tính tùy chỉnh của sự kiện](advanced-SDK-implementation.md).

1. Chuyển đến phần **Dữ liệu** > **Thứ nguyên**.
1. Chọn **Kích thước mới**.

   :::image type="content" source="media/add-dimension.png" alt-text="Thêm thứ nguyên vào sự kiện.":::

1. Trong ngăn **Tạo thứ nguyên**, hãy chọn một thuộc tính để làm cơ sở cho thứ nguyên. Danh sách thuộc tính sẽ hiển thị tất cả các thuộc tính trong không gian làm việc chưa được gán cho một thứ nguyên.
   
   :::image type="content" source="media/create-new-dimension.png" alt-text="Tạo thứ nguyên mới.":::
      
3. Nhập tên trong hộp **Tên hiển thị**. Bạn có thể tùy ý thêm **Mô tả**.
4. Chọn **Tạo** để lưu thứ nguyên. Có thể mất đến một phút trước khi bạn có thể sử dụng thứ nguyên này trong [báo cáo tùy chỉnh](custom-reports.md) hoặc [phân khúc](segments.md). 

## <a name="edit-a-dimension"></a>Chỉnh sửa thứ nguyên

Bạn có thể thay đổi tên và phần mô tả của thứ nguyên. Bạn chỉ có thể chỉnh sửa thứ nguyên do người dùng tạo chứ không thể chỉnh sửa thứ nguyên hệ thống.


1. Chuyển đến phần **Dữ liệu** > **Thứ nguyên**.
1. Chọn thứ nguyên mà bạn muốn xóa.
1. Trong ngăn **Chỉnh sửa thứ nguyên**, hãy cập nhật thứ nguyên.
1. Chọn **Áp dụng** để lưu các thay đổi.

## <a name="delete-a-dimension"></a>Xóa thứ nguyên

Bạn chỉ có thể xóa thứ nguyên do người dùng tạo chứ không thể xóa thứ nguyên hệ thống.

Một khi bạn chọn xóa, thứ nguyên sẽ bị xóa vĩnh viễn. Các báo cáo và phân khúc sử dụng thứ nguyên bị xóa sẽ không hoạt động nữa. 

1. Chuyển đến phần **Dữ liệu** > **Thứ nguyên**.
1. Chọn thứ nguyên mà bạn muốn xóa.
1. Trong ngăn **Chỉnh sửa thứ nguyên**, hãy chọn **Xóa thứ nguyên**.

   :::image type="content" source="media/delete-dimension.png" alt-text="Xóa thứ nguyên khỏi sự kiện.":::

1. Nhập cụm từ **XÁC NHẬN XÓA** (viết hoa toàn bộ) để xác nhận thao tác xóa. 
1. Chọn **Xóa**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
