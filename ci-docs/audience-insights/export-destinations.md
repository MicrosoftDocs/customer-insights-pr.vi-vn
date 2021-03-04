---
title: Nơi xuất đích
description: Xuất dữ liệu và quản lý các điểm đến xuất.
ms.date: 07/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 63caa2ebdd7d637d14ac9c9cc7972095803aee2f
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477159"
---
# <a name="export-destinations-preview-overview"></a>Tổng quan về nơi xuất đích (bản xem trước)

Trang **Đích xuất** cho biết tất cả các vị trí bạn đã thiết lập để xuất dữ liệu sang đó. Bạn cũng có thể thêm điểm đến mới để xuất. Ngoài ra, nó hiển thị các tùy chọn xuất hiện có sẵn. Nhận tổng quan nhanh, mô tả và tìm hiểu những gì bạn có thể làm với mỗi tùy chọn mở rộng. Xuất hồ sơ, số liệu đo lường và phân khúc thống nhất cho các ứng dụng được hỗ trợ phù hợp với doanh nghiệp của bạn.

Chuyển đến **Quản trị** > **Vị trí xuất dữ liệu** để tìm các tùy chọn mở rộng sau:

- [Bổ trợ thẻ khách hàng Dynamics 365](customer-card-add-in.md)
- [Trình kết nối quản lý quảng cáo trên Facebook](export-facebook.md)
- [Trình kết nối Power Automate](export-power-automate.md)
- [Trình kết nối Power Apps](export-power-apps.md)
- [Trình kết nối Power BI](export-power-bi.md)
- [Autopilot](export-autopilot.md)
- [DotDigital](export-dotdigital.md)
- [Dynamics 365 Sales](export-dynamics365-sales.md)
- [Dynamics 365 Marketing](export-dynamics365-marketing.md)
- [Lưu trữ Azure Blob](export-azure-blob-storage.md)
- [Azure Data Lake Storage thế hệ 2](export-azure-data-lake-storage-gen2.md)
- [SendGrid](export-sendgrid.md)
- [Trình kết nối LiveRamp&reg;](export-liveramp.md)
- [Bot dành cho Microsoft Teams](export-teams-bot.md)
- [Mailchimp](export-mailchimp.md)
- [API Customer Insights](apis.md)

## <a name="add-a-new-export-destination"></a>Thêm đích xuất mới

Để thêm các điểm đến xuất, bạn có [quyền quản trị viên](permissions.md). Nếu bạn xuất sang các dịch vụ của Microsoft, chúng tôi sẽ giả định rằng cả hai dịch vụ đều thuộc cùng một tổ chức.

1. Đi tới **Quản trị viên** > **Đích xuất**.

1. Chuyển sang tab **Đích xuất của tôi**.

1. Chọn **Thêm đích** để tạo đích xuất mới.

1. Trong ngăn **Thêm đích**, chọn **Loại** cho đích xuất trong menu thả xuống.

1. Cung cấp thông tin cần thiết rồi chọn **Tiếp** để tạo đích xuất.

Bạn cũng có thể chọn **Thiết lập** trên một lát ở tab **Khám phá**.

## <a name="view-export-destinations"></a>Xem các vị trí xuất dữ liệu

Sau khi tạo các đích xuất, bạn sẽ nhìn thấy chúng trong bảng ở tab **Đích xuất của tôi**. Bảng này có 3 cột:

- **Tên hiển thị**: Là tên mà bạn đã đặt khi tạo vị trí.
- **Kiểu**: Kiểu đích xuất bạn mong muốn khi tạo đích.
- **Ngày tạo**: Là ngày bạn tạo vị trí.

## <a name="edit-an-export-destination"></a>Chỉnh sửa một đích xuất

1. Chọn dấu chấm lửng dọc cạnh đích xuất bạn muốn chỉnh sửa.

   > [!div class="mx-imgBorder"]
   > ![Dấu chấm lửng dọc](media/export-destinations-page-ellipsis.png "Dấu chấm lửng dọc")

1. Chọn **Chỉnh sửa** từ menu thả xuống.

1. Thay đổi các giá trị cần cập nhật rồi chọn **Lưu**.

## <a name="export-data-on-demand"></a>Xuất dữ liệu theo nhu cầu

Sau khi đặt cấu hình tác nhân kết nối cho đích xuất, thì mỗi lần [làm mới theo lịch](system.md#schedule-tab), tác vụ xuất cũng sẽ chạy.

Để xuất dữ liệu mà không cần chờ đến lịch làm mới, hãy đi tới tab **Đích xuất của tôi** trên **Quản trị viên** > **Đích xuất**.

> [!div class="mx-imgBorder"]
> ![Dấu chấm lửng dọc](media/export-destinations-page-ellipsis.png "Dấu chấm lửng dọc")

- Chọn **Xuất** ở phía trên danh sách để chạy tác vụ xuất đồng thời cho mọi đích xuất.
- Chọn dấu chấm lửng (...) cuối mỗi mục trong danh sách rồi chọn tùy chọn **Xuất** để chạy tác vụ xuất cho từng đích xuất.

## <a name="remove-an-export-destination"></a>Xóa một Vị trí xuất dữ liệu

Để xóa vị trí xuất dữ liệu, hãy bắt đầu từ trang **Vị trí xuất dữ liệu**.

1. Chọn dấu chấm lửng dọc cạnh vị trí xuất dữ liệu mà bạn muốn xóa.

   > [!div class="mx-imgBorder"]
   > ![Dấu chấm lửng dọc](media/export-destinations-page-ellipsis.png "Dấu chấm lửng dọc")

2. Chọn **Xóa** trong menu thả xuống.

3. Xác nhận việc xóa bằng cách chọn **Xóa** trên màn hình xác nhận.


[!INCLUDE[footer-include](../includes/footer-banner.md)]