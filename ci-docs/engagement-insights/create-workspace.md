---
title: Tạo không gian làm việc mới
description: Mục đích của không gian làm việc và cách tạo một không gian làm việc mới.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 1f8922703af506974c8b5b24086b61f05a83609d
ms.sourcegitcommit: 31985755c7c973fb1eb540c52fd1451731d2bed2
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 10/22/2021
ms.locfileid: "7673519"
---
# <a name="create-a-new-workspace-and-add-members"></a>Tạo không gian làm việc mới và thêm thành viên

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Không gian làm việc là cách bạn có thể xem hoạt động của người dùng trong thời gian thực để hiểu rõ hơn về đối tượng của mình. Đó là nơi bạn lưu trữ cũng như quản lý các sự kiện và báo cáo.

Khi tạo không gian làm việc, bạn có thể chọn loại dữ liệu để tập trung vào đó. Bạn có thể thêm người dùng hoặc thành viên khác vào không gian làm việc hiện có bất kỳ lúc nào. 

## <a name="create-a-new-workspace"></a>Tạo không gian làm việc mới

Quá trình tạo không gian làm việc bao gồm thiết lập *môi trường* để sắp xếp không gian làm việc của bạn. Môi trường là không gian có thể chứa một hoặc nhiều không gian làm việc. Bạn có thể sử dụng một môi trường để quản lý không gian làm việc và kết nối của mình với khả năng thông tin chi tiết về đối tượng.

1. Lựa chọn **+ Mới** từ trình chuyển đổi không gian làm việc.

   :::image type="content" source="media/new-workspace.png" alt-text="Trang Thông tin chi tiết về khách hàng với chú thích trên ngăn điều hướng và mô tả.":::

1. Trong ngăn **Không gian làm việc**, nhập **Tên không gian làm việc**.

   :::image type="content" source="media/workspace-name.png" alt-text="Nhập tên không gian làm việc.":::

1. Chọn loại nền tảng (web hoặc thiết bị di động) mà bạn muốn đo lường.

1. Chọn **Hiện thiết đặt nâng cao** để bật hoặc tắt các thiết đặt tùy chọn này:

   - Chuyển **Chưa xác định thành đã xác định** thành "bật" để liên kết các sự kiện web với những người dùng đã xác thực trước đó. Để biết thêm thông tin, hãy xem [Nhận ra các sự kiện web từ những khách truy cập đã được xác thực trước đó](unknown-to-known.md)
   - Chuyển **Lọc lưu lượng bot** thành "bật" để loại bỏ lưu lượng truy cập web của bot cho không gian làm việc này. 

1. Chọn **Hoàn tất** khi bạn hoàn tất. 

1. Cài đặt đoạn mã để bắt đầu nhận dữ liệu, rồi chọn **Kết thúc** để tạo không gian làm việc. Để biết thêm thông tin, hãy xem [Tổng quan về nguồn lực dành cho nhà phát triển](developer-resources.md).

> [!NOTE]
> Giờ đây, bạn có thể thêm thành viên và chỉ định cấp độ quyền của họ từ danh sách **Vai trò**. Để biết thêm thông tin, hãy xem [Vai trò và quyền](user-roles.md). 

Để biết thêm thông tin, hãy xem [Quản lý môi trường và không gian làm việc](manage-environments-workspaces.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
