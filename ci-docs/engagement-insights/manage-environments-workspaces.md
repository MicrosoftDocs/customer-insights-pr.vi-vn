---
title: Quản lý môi trường và không gian làm việc
description: Cách tạo, đổi tên và xóa không gian làm việc cũng như môi trường.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 279af24358a1d6ea2b4cc75d5496042af73a7cae
ms.sourcegitcommit: 53b133a716c73cb71e8bcbedc6273cec70ceba6c
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 10/15/2021
ms.locfileid: "7645472"
---
# <a name="manage-environments-and-workspaces"></a>Quản lý môi trường và không gian làm việc

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

## <a name="overview"></a>Tổng quan

Chủ đề này thảo luận về cách quản lý không gian làm việc và môi trường sau khi được tạo. 

- *Không gian làm việc* là không gian để lưu trữ cũng như quản lý các sự kiện và báo cáo. Đó là nơi bạn có thể xem hoạt động của người dùng trong thời gian thực. Khi tạo không gian làm việc, bạn có thể chọn loại dữ liệu để gửi đến không gian làm việc. Hiện tại, dữ liệu web và ứng dụng dành cho thiết bị di động đều được hỗ trợ. Để biết thêm thông tin, hãy xem [Tạo không gian làm việc và thêm thành viên](create-workspace.md).

- *Môi trường* là không gian mà bạn quản lý không gian làm việc và kết nối của mình. Để biết thêm thông tin, hãy xem [Tạo môi trường mới](create-new-environment.md).

## <a name="manage-an-existing-workspace"></a>Quản lý không gian làm việc hiện có

Bạn có thể duy trì nhiều không gian làm việc đồng thời trong một môi trường. [Vai trò](user-roles.md) của bạn xác định cách bạn có thể làm việc trong đó. 

 - Bạn cần phải là quản trị viên môi trường hoặc quản trị viên không gian làm việc để quản lý không gian làm việc.
 - Với vai trò là quản trị viên không gian làm việc, bạn có thể đổi tên hoặc xóa không gian làm việc hiện có. 

:::image type="content" source="media/workspace-edit.png" alt-text="Trung tâm quản trị không gian làm việc.":::

### <a name="edit-a-workspace-name"></a>Chỉnh sửa tên không gian làm việc

1. Chuyển đến **Quản trị viên** > **Không gian làm việc** và chọn **Cài đặt**.

1. Trong hộp **Tên không gian làm việc**, hãy nhập tên mới.

1. Chọn **Lưu** để áp dụng thay đổi.

### <a name="delete-a-workspace"></a>Xóa không gian làm việc

Thao tác xóa không gian làm việc sẽ xóa vĩnh viễn tất cả nội dung, dữ liệu, thiết đặt và quyền của không gian đó. Không thể hoàn tác điều này.

1. Chuyển đến **Quản trị viên** > **Không gian làm việc** và chọn **Cài đặt**.

1. Chọn **Xóa không gian làm việc**. 

1. Trong hộp thoại **Xóa không gian làm việc**, nhập **XÁC NHẬN XÓA** bằng chữ hoa. 

1. Chọn **Xóa** để xóa vĩnh viễn không gian làm việc.

### <a name="manage-workspace-members"></a>Quản lý thành viên của không gian làm việc

1. Chuyển đến **Quản trị viên** > **Không gian làm việc** và chọn **Thành viên**.

1. Chọn **Thêm thành viên** để cấp quyền truy cập và [chỉ định vai trò](user-roles.md). Hiện nay, chỉ có sẵn **Quản trị viên không gian làm việc**.

1. Chọn **Thêm thành viên** để thêm họ vào không gian làm việc của bạn.

## <a name="manage-an-existing-environment"></a>Quản lý môi trường hiện có

Là quản trị viên môi trường, bạn có thể truy cập vào môi trường tư ngăn điều hướng bên trái. Bạn có thể đặt cấu hình cài đặt môi trường, quản trị viên môi trường khác và không gian làm việc. Chọn các tab để di chuyển giữa các khu vực khác nhau trong trung tâm quản trị.

:::image type="content" source="media/environment-edit.png" alt-text="Trung tâm quản trị môi trường.":::

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

1. Trong hộp thoại **Xóa không gian làm việc**, nhập **XÁC NHẬN XÓA** bằng chữ hoa. 

1. Chọn **Xóa** để xóa vĩnh viễn môi trường.

## <a name="manage-connections"></a>Quản lý kết nối

Thiết lập kết nối với thông tin chi tiết về đối tượng cho phép bạn xem báo cáo trong thông tin chi tiết về tương tác dựa trên hồ sơ khách hàng thống nhất. 

Để biết thêm thông tin: hãy xem [Tạo mối liên kết giữa thông tin chi tiết về đối tượng và thông tin chi tiết về mức độ tương tác](integrate-audience-insights-engagement-insights.md).

## <a name="manage-personal-data"></a>Quản lý dữ liệu cá nhân

Để bảo vệ dữ liệu cá nhân của khách hàng, bạn có thể xóa hoặc xuất dữ liệu nhận dạng người dùng cuối.

Để biết thêm thông tin, hãy xem phần [Xóa và xuất dữ liệu sự kiện có chứa thông tin cá nhân](delete-export-personal-data.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
