---
title: Tạo môi trường mới
description: Mục đích của một môi trường và cách tạo một môi trường mới.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 10/04/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 5e301b4ff0a7586fb143b154b773791b3bd645b7
ms.sourcegitcommit: 37182127b93b90846cc91fbeb26dd7a18cf5610a
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 10/18/2021
ms.locfileid: "7648143"
---
# <a name="create-a-new-environment"></a>Tạo môi trường mới 

## <a name="overview"></a>Tổng quan

Môi trường là không gian mà bạn quản lý không gian làm việc và kết nối của mình. Cách bạn sử dụng môi trường phụ thuộc vào tổ chức và trường hợp sử dụng của bạn. Ví dụ, bạn có thể tạo:

- Một môi trường duy nhất.
- Môi trường riêng biệt để thử nghiệm và sản xuất.
- Môi trường riêng biệt cho các nhóm hoặc phòng ban cụ thể trong tổ chức của bạn có chứa các sự kiện liên quan cho từng đối tượng.
- Môi trường riêng biệt cho các chi nhánh toàn cầu khác nhau của công ty bạn.
- Kết nối với chức năng thông tin chi tiết về đối tượng của Customer Insights.

## <a name="create-a-new-environment"></a>Tạo môi trường mới

1. Ở phía bên phải của biểu ngữ chính, hãy chọn bộ chọn môi trường, sau đó chọn **+Mới**.

   :::image type="content" source="media/environment-picker.png" alt-text="Chọn bộ chọn môi trường.":::

1. Trong ngăn **Thiết lập**, nhập **Tên môi trường**.

1. Chọn **Loại** của tài khoản, tùy thuộc vào loại gói của bạn.

1. Chọn **Khu vực** và chọn **Tiếp theo**. 

1. Nhập **Tên không gian làm việc**, cho phép bạn thu thập dữ liệu cho trang web hoặc ứng dụng cụ thể. Để biết thêm thông tin, hãy xem [Tạo không gian làm việc](create-workspace.md).

1. Chọn **Loại không gian làm việc** (Web hoặc di động) mà bạn muốn tạo. 

1. Chọn **Hiện thiết đặt nâng cao** để bật hoặc tắt các thiết đặt tùy chọn này:

   - Chuyển **Chưa xác định thành đã xác định** thành "bật" để liên kết các sự kiện web với những người dùng đã xác thực trước đó. Để biết thêm thông tin, hãy xem [Nhận ra các sự kiện web từ những khách truy cập đã được xác thực trước đó](unknown-to-known.md)
   - Chuyển **Lọc lưu lượng bot** thành "bật" để loại bỏ lưu lượng truy cập web của bot cho không gian làm việc này. 

1. Chọn **Hoàn tất** khi bạn hoàn tất. 

1. Cài đặt đoạn mã để bắt đầu nhận dữ liệu, rồi chọn **Kết thúc** để tạo không gian làm việc. Để biết thêm thông tin, hãy xem [Tổng quan về nguồn lực dành cho nhà phát triển](developer-resources.md).

> [!NOTE]
> Giờ đây, bạn có thể thêm thành viên và chỉ định cấp độ quyền của họ từ danh sách **Vai trò**. Để biết thêm thông tin, hãy xem [Vai trò và quyền](user-roles.md). 

Để biết thêm thông tin, hãy xem [Quản lý môi trường và không gian làm việc](manage-environments-workspaces.md).

## <a name="work-with-your-new-environment"></a>Làm việc với môi trường mới của bạn

- [Tạo không gian làm việc](../engagement-insights/create-workspace.md) và thêm thành viên.
- [Thêm mã vào trang web của bạn](../engagement-insights/instrument-website.md) hoặc [ứng dụng dành cho thiết bị di động](../engagement-insights/developer-resources.md#capture-events-from-mobile-apps).
- Xem một [báo cáo theo thời gian thực](../engagement-insights/view-reports.md) hoặc tạo [báo cáo tùy chọn](../engagement-insights/custom-reports.md).
- [Tạo các sự kiện tinh chỉnh](../engagement-insights/refined-events.md) để xuất.
- [Xuất dữ liệu](../engagement-insights/export-events.md) sang Data Lake Storage.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
