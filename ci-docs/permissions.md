---
title: Quản lý quyền của người dùng
description: Tìm hiểu về quyền và vai trò của người dùng.
ms.date: 02/09/2022
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
ms.openlocfilehash: 74c7ff7cda8431c04dd34713becefa7e346331b4
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 05/11/2022
ms.locfileid: "8740929"
---
# <a name="user-permissions"></a>Quyền người dùng

Các **Quyền** là nơi bạn sẽ thiết lập vai trò và quyền sử dụng Thông tin chi tiết về khách hàng.

Bạn cần có quyền của quản trị viên để xem trang. Để truy cập trang quyền, hãy truy cập **Quản trị viên** > **Bảo vệ** > **Người dùng**.

Có ba loại vai trò:

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
- Hoàn thành ***Hợp nhất dữ liệu** dẫn đến thực thể hồ sơ khách hàng hợp nhất.
- Xác định **Các mối quan hệ** và **Hoạt động**.
- Tạo phân khúc bằng cách sử dụng trang **Phân khúc**.
- Tạo các giá trị đo sử dụng trang **Giá trị đo**.
- Quản lý cấu hình và làm phong phú hồ sơ khách hàng từ trang **Làm phong phú** (chỉ dành cho nội dung phong phú của bên thứ nhất).
- Quản lý và tạo các nội dung xuất dựa trên các kết nối được chia sẻ với người đóng góp. [Tìm hiểu thêm về cách quản trị viên cho phép người đóng góp sử dụng kết nối để xuất](connections.md#allow-contributors-to-use-a-connection-for-exports).

## <a name="admin"></a>Quản trị viên

- Tất cả các quyền có sẵn cho Cộng tác viên.
- Thay đổi cài đặt trên trang **Hệ thống**, bao gồm ngôn ngữ làm việc và lịch trình làm mới cho các quy trình hệ thống của bạn.
- Xem và thêm quyền bằng cách sử dụng trang **Quyền**.
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
- [Đặt lại và xóa](manage-environments.md#reset-an-existing-environment) môi trường.

## <a name="assign-roles-and-permissions"></a>Gán vai trò và quyền

1. Đi đến **Quản trị viên** > **Bảo vệ** > ** Người dùng ***.

1. Chọn **Thêm người dùng** để mở ngăn **Thêm/chỉnh sửa quyền**.

1. Sử dụng trường **Tìm kiếm** để tìm người dùng hoặc nhóm Azure Active Directory có quyền mà bạn muốn điều chỉnh. Chọn một **Vai trò** để chỉ định cho người dùng hoặc nhóm đó.

1. Chọn **Lưu**. Môi trường hiện tại sẽ tự động được chia sẻ với người dùng hoặc các thành viên của nhóm có quyền bạn đã thay đổi. Người dùng có thể truy cập ứng dụng Customer Insights và làm việc theo vai trò được chỉ định.

## <a name="view-current-permissions"></a>Xem các quyền hiện tại

Đi đến **Quản trị viên** > **Bảo vệ** > **Người dùng** để xem những nhiệm vụ vai trò nào hiện đang hoạt động.

- Cột **Loại** chỉ định một người dùng, nhóm hoặc ứng dụng. Hệ thống hỗ trợ người dùng cá nhân và nhóm.
- Vai trò được chỉ định theo cột **Vai trò**.
- Chọn tiêu đề cột bất kỳ để sắp xếp kết quả theo giá trị của cột đó.
- Sử dụng trường **Tìm kiếm** ở đầu trang để xác định vị trí của người dùng cụ thể.


[!INCLUDE [footer-include](includes/footer-banner.md)]
