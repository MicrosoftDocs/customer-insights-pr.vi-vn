---
title: Quản lý môi trường và không gian làm việc
description: Cách tạo, đổi tên và xóa không gian làm việc cũng như môi trường.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 09/09/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: a5b48db5ae23ea65bf608d67348d493bfdc7678f
ms.sourcegitcommit: 0ceb46c4f57ab49d3a2ebb1c8a816bbafe979e3d
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 09/09/2021
ms.locfileid: "7486065"
---
# <a name="manage-environments-and-workspaces"></a>Quản lý môi trường và không gian làm việc

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

## <a name="overview"></a>Tổng quan

Không gian làm việc là không gian để lưu trữ cũng như quản lý các sự kiện và báo cáo. Đó là nơi bạn có thể xem hoạt động của người dùng trong thời gian thực. Khi tạo không gian làm việc, bạn có thể chọn loại dữ liệu để gửi đến không gian làm việc. Hiện tại, dữ liệu web và ứng dụng dành cho thiết bị di động đều được hỗ trợ.

Môi trường là không gian mà bạn quản lý không gian làm việc và kết nối của mình. Cách bạn sử dụng môi trường phụ thuộc vào tổ chức và trường hợp sử dụng của bạn. Ví dụ, bạn có thể tạo:

-   Một môi trường duy nhất.
-   Môi trường riêng biệt để thử nghiệm và sản xuất.
-   Môi trường riêng biệt cho các nhóm hoặc phòng ban cụ thể trong tổ chức của bạn có chứa các sự kiện liên quan cho từng đối tượng.
-   Môi trường riêng biệt cho các chi nhánh toàn cầu khác nhau của công ty bạn.
-   Kết nối với chức năng thông tin chi tiết về đối tượng của Customer Insights.

## <a name="choose-an-environment-and-create-a-workspace"></a>Chọn môi trường và tạo không gian làm việc 

Mọi không gian làm việc cần phải ở trong một môi trường. Bạn có thể chọn môi trường đã có từ trước hoặc tạo môi trường mới khi tạo không gian làm việc. Sau đó, bạn có thể chọn thêm thành viên của không gian làm việc và bắt đầu thu thập dữ liệu.

**Để tạo không gian làm việc đầu tiên của bạn**

1. Trong thông tin chi tiết về tương tác, hãy chọn **Mới** từ trình chuyển đổi không gian làm việc. 

   :::image type="content" source="media/New-workspace.png" alt-text="Bộ chọn không gian làm việc của trang Customer Insights.":::

1. Chọn một môi trường từ danh sách hoặc chọn **Tạo môi trường mới**.

1. Nhập tên vào **Tên không gian làm việc**. 

1. Chọn loại môi trường bạn muốn tạo, tùy thuộc vào việc bạn muốn đo lường những gì xảy ra trên trang web hay trong ứng dụng dành cho thiết bị di động. 

1. Bạn có thể thêm thành viên và chỉ định cấp độ quyền của họ trong danh sách **Vai trò**. Sau đó chọn **Hoàn thành** để tạo không gian làm việc hoặc **Tiếp theo** để cài đặt mã. 

1. Cài đặt đoạn mã để bắt đầu nhận dữ liệu rồi chọn **Hoàn tất**. 

## <a name="manage-a-workspace"></a>Quản lý không gian làm việc

Bạn có thể duy trì nhiều không gian làm việc đồng thời trong một môi trường. [Vai trò](user-roles.md) của bạn xác định cách bạn có thể làm việc trong đó. 

 - Bạn cần phải là quản trị viên môi trường hoặc quản trị viên không gian làm việc để quản lý không gian làm việc.
 - Với vai trò là quản trị viên không gian làm việc, bạn có thể đổi tên hoặc xóa không gian làm việc hiện có. 

### <a name="edit-a-workspace-name"></a>Chỉnh sửa tên không gian làm việc

1. Chuyển đến **Quản trị viên** > **Không gian làm việc** và chọn **Cài đặt**.

1. Trong hộp **Tên không gian làm việc**, hãy nhập tên mới.

1. Chọn **Lưu** để áp dụng thay đổi.

### <a name="delete-a-workspace"></a>Xóa không gian làm việc

Thao tác xóa không gian làm việc sẽ xóa vĩnh viễn tất cả nội dung, dữ liệu, thiết đặt và quyền của không gian đó. Không thể hoàn tác điều này.

1. Chuyển đến **Quản trị viên** > **Không gian làm việc** và chọn **Cài đặt**.

1. Chọn **Xóa không gian làm việc**. 

1. Trong hộp thoại **Xóa không gian làm việc**, nhập **XÁC NHẬN XÓA**. 

1. Chọn **Xóa** để xóa vĩnh viễn không gian làm việc.

### <a name="manage-workspace-members"></a>Quản lý thành viên của không gian làm việc

1. Chuyển đến **Quản trị viên** > **Không gian làm việc** và chọn **Thành viên**.

1. Chọn **Thêm thành viên** để cấp quyền truy cập và [chỉ định vai trò](user-roles.md). Hiện nay, chỉ có sẵn **Quản trị viên không gian làm việc**.

1. Chọn **Thêm thành viên** để thêm họ vào không gian làm việc của bạn.

## <a name="manage-an-environment"></a>Quản lý môi trường

Là quản trị viên Môi trường, bạn có thể truy cập môi trường từ ngăn điều hướng bên trái. Bạn có thể đặt cấu hình cài đặt môi trường, quản trị viên môi trường khác và không gian làm việc. Chọn các tab để di chuyển giữa các khu vực khác nhau trong trung tâm quản trị.

:::image type="content" source="media/New-environment.png" alt-text="Trung tâm quản trị môi trường.":::

### <a name="create-an-environment"></a>Tạo môi trường

1. Trong bộ chọn không gian làm việc, chọn **+Mới**.

1. Trong trải nghiệm được hướng dẫn, hãy mở menu thả xuống **Môi trường** và chọn **Tạo môi trường mới**. 

1. Cung cấp một **Tên môi trường**.

   :::image type="content" source="media/create-environment.png" alt-text="Bước trong trải nghiệm được hướng dẫn để chỉ định chi tiết môi trường.":::

1. Chọn **Khu vực** và chọn **Tiếp theo**. 

1. Cung cấp tên Không gian làm việc và chọn loại không gian làm việc bạn muốn tạo. 

1.  Theo tùy chọn, thêm thành viên và sao chép đoạn mã để hoàn tất quá trình tạo.

### <a name="rename-an-environment"></a>Đổi tên môi trường

1. Chuyển đến **Quản trị viên** > **Môi trường** và chọn **Cài đặt**.

1. Cập nhật **Tên môi trường** và chọn **Lưu** để áp dụng các thay đổi của bạn.

### <a name="manage-environment-members"></a>Quản lý thành viên môi trường

1. Chuyển đến **Quản trị viên** > **Môi trường** và chọn **Thành viên**.

1. Chọn **Thêm thành viên** để cập nhật thành viên và [chỉ định vai trò](user-roles.md). Hiện nay, chỉ có sẵn **Quản trị viên môi trường**.

1. Chọn **Thêm thành viên** để thêm họ vào môi trường của bạn.

### <a name="delete-an-environment"></a>Xóa môi trường

Quản trị viên môi trường có thể xóa môi trường. Trước khi có thể xóa một môi trường, bạn phải xóa tất cả các không gian làm việc trong đó.

1. Chuyển đến **Quản trị viên** > **Môi trường** và chọn **Cài đặt**.

1. Chọn **Xóa môi trường**. 

1. Trong hộp thoại **Xóa không gian làm việc**, nhập **XÁC NHẬN XÓA**. 

1. Chọn **Xóa** để xóa vĩnh viễn môi trường.

## <a name="manage-connections"></a>Quản lý kết nối

Thiết lập kết nối với thông tin chi tiết về đối tượng cho phép bạn xem báo cáo trong thông tin chi tiết về tương tác dựa trên hồ sơ khách hàng thống nhất. 

Để biết thêm thông tin: hãy xem [Tạo mối liên kết giữa thông tin chi tiết về đối tượng và thông tin chi tiết về mức độ tương tác](integrate-audience-insights-engagement-insights.md).

## <a name="manage-personal-data"></a>Quản lý dữ liệu cá nhân

Để bảo vệ dữ liệu cá nhân của khách hàng, bạn có thể xóa hoặc xuất dữ liệu nhận dạng người dùng cuối.

Để biết thêm thông tin, hãy xem phần [Xóa và xuất dữ liệu sự kiện có chứa thông tin cá nhân](delete-export-personal-data.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
