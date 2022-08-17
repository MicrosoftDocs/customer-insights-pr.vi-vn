---
title: Chỉ định quyền của người dùng
description: Tìm hiểu về quyền và vai trò của người dùng.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-permissions
- ci-system-security
- customerInsights
ms.openlocfilehash: a59a672b6f7e1e67c2162ea14bb9860df0d551aa
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245445"
---
# <a name="assign-user-permissions"></a>Chỉ định quyền của người dùng

Quyền truy cập vào Thông tin chi tiết về khách hàng bị hạn chế đối với người dùng trong tổ chức của bạn được quản trị viên thêm vào ứng dụng. Quản trị viên có thể thêm, chỉnh sửa hoặc xóa người dùng. Người dùng có thể là một người dùng, nhóm hoặc ứng dụng. Người dùng có thể có ba loại vai trò:

## <a name="viewer"></a>Người xem

- Khám phá những hiểu biết và phân khúc trong trang **Trang chủ** và **Phân đoạn**.
- Tìm kiếm và lọc hồ sơ khách hàng bằng cách sử dụng trang **Khách hàng**. Các trường phải có thể tìm kiếm được.
- Xem và khám phá trang **nội dung phong phú**.
- Khám phá và xuất các thực thể bằng cách sử dụng trang **Các thực thể**.
- Xem trạng thái của các quy trình hệ thống bằng cách sử dụng trang **Hệ thống**.
- Xem nội dung xuất trong trang **Nội dung xuất**.
- Cài đặt và sử dụng bảng thông tin **Power BI Customer Insights**.

## <a name="contributor"></a>Cộng tác viên

- Tất cả các quyền có sẵn cho Người xem.
- Tải và chuyển đổi dữ liệu bằng cách dùng trang **Nguồn dữ liệu**.
- Hoàn thành **Hợp nhất dữ liệu** dẫn đến thực thể hồ sơ khách hàng hợp nhất.
- Xác định **Các mối quan hệ** và **Hoạt động**.
- Tạo phân khúc bằng cách sử dụng trang **Phân khúc**.
- Tạo các giá trị đo sử dụng trang **Giá trị đo**.
- Quản lý cấu hình và làm phong phú hồ sơ khách hàng từ trang **Làm phong phú** (chỉ dành cho nội dung phong phú của bên thứ nhất).
- Quản lý và tạo xuất dựa trên [kết nối được chia sẻ với những người đóng góp](connections.md#allow-contributors-to-use-a-connection-for-exports).

## <a name="admin"></a>Quản trị viên

- Tất cả các quyền có sẵn cho Cộng tác viên.
- Thay đổi cài đặt trên **Hệ thống**, bao gồm ngôn ngữ làm việc, lịch làm mới cho các quy trình hệ thống của bạn và xuất nhật ký chẩn đoán.
- Thay đổi cài đặt trên **Bảo vệ** trang, bao gồm người dùng, khóa API, liên kết riêng tư và kho khóa.
- Đặt định nghĩa tìm kiếm và lọc cho trang Khách hàng bằng cách dùng trang **Tìm kiếm và lọc chỉ mục** (có sẵn qua trang **Khách hàng**).
- Quản lý và cho phép các kết nối đối với những vai trò người dùng khác trên trang **Kết nối**.
- Quản lý cấu hình và làm phong phú hồ sơ khách hàng từ trang **Nội dung phong phú** (cho tất cả các nội dung phong phú).
- Quản lý và tạo nội dung xuất trên trang **Nội dung xuất**.
- Cài đặt và sử dụng **phần bổ trợ Thẻ khách hàng**.
- Thêm và sử dụng **Trình kết nối Power Apps**.
- Cho phép sử dụng [API Customer Insights](apis.md).
- [Chỉ định quyền sở hữu môi trường](manage-environments.md#change-the-owner-of-an-environment) cho một quản trị viên khác.

## <a name="admin-owner"></a>Quản trị viên (chủ sở hữu)

- Tất cả các quyền có sẵn cho Quản trị viên.
- [Đặt lại và xóa](manage-environments.md#reset-an-existing-environment-preview) môi trường.

## <a name="add-users"></a>Thêm người dùng

1. Đi đến **Quản trị viên** > **Bảo vệ** và chọn **Người dùng** chuyển hướng.

1. Chọn **Thêm người dùng** để mở ngăn **Thêm/chỉnh sửa quyền**.

1. Sử dụng **Tìm kiếm** lĩnh vực để tìm Azure Active Directory người dùng hoặc nhóm bạn muốn thêm. Chọn một **Vai trò** để chỉ định cho người dùng hoặc nhóm đó.

1. Chọn **Lưu.** Môi trường hiện tại được tự động chia sẻ với người dùng hoặc các thành viên của nhóm. Người dùng có thể truy cập ứng dụng Customer Insights và làm việc theo vai trò được chỉ định.

## <a name="view-current-permissions"></a>Xem các quyền hiện tại

Đi đến **Quản trị viên** > **Bảo vệ** và chọn **Người dùng** để xem danh sách những người dùng đang hoạt động và nhiệm vụ của họ. Bạn có thể sắp xếp danh sách người dùng theo bất kỳ cột nào hoặc sử dụng hộp tìm kiếm để tìm một người dùng cụ thể.

## <a name="manage-current-users"></a>Quản lý người dùng hiện tại

Đi đến **Quản trị viên** > **Bảo vệ** và chọn **Người dùng** chuyển hướng. Bạn có thể sắp xếp danh sách người dùng theo bất kỳ cột nào hoặc sử dụng hộp tìm kiếm để tìm người dùng bạn muốn quản lý.

Chọn một người dùng để xem các hành động có sẵn.

- **Chỉnh sửa** để chỉnh sửa vai trò của người dùng trong Thông tin chi tiết về khách hàng. Lựa chọn **Tiết kiệm** để xác nhận thay đổi.
- **Loại bỏ** để xóa người dùng có quyền truy cập vào Thông tin chi tiết về khách hàng. Chọn **Xóa** để xác nhận thao tác xóa.

[!INCLUDE [footer-include](includes/footer-banner.md)]
