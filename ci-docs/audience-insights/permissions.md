---
title: Quản lý quyền của người dùng
description: Tìm hiểu về quyền và vai trò của người dùng.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 8638489dba908d4504278916d2c28454e3ea9e18
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760399"
---
# <a name="user-permissions"></a>Quyền người dùng

Trang **Quyền** là nơi bạn sẽ thiết lập vai trò và quyền sử dụng thông tin chi tiết về đối tượng.

Bạn cần có quyền của quản trị viên để xem trang. Để truy cập trang quyền trong thông tin chi tiết về đối tượng, hãy chuyển đến **Quản trị viên** > **Quyền**.

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
- Hoàn thành các phần *Hợp nhất dữ liệu* (**Ánh xạ**, **So khớp** và **Trộn**) để có thực thể hồ sơ khách hàng hợp nhất.
- Xác định **Các mối quan hệ** và **Hoạt động**.
- Tạo phân khúc bằng cách sử dụng trang **Phân khúc**.
- Tạo các giá trị đo sử dụng trang **Giá trị đo**.
- Quản lý cấu hình và làm phong phú hồ sơ khách hàng từ trang **Làm phong phú** (chỉ dành cho nội dung phong phú của bên thứ nhất).
- Quản lý và tạo các nội dung xuất dựa trên các kết nối được chia sẻ với người đóng góp. [Tìm hiểu thêm về cách quản trị viên cho phép người đóng góp sử dụng kết nối để xuất](connections.md#allow-contributors-to-use-a-connection-for-exports).

## <a name="administrator"></a>Quản trị viên

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

## <a name="assign-roles-and-permissions"></a>Gán vai trò và quyền

1. Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Quản trị** > **Quyền**.

1. Chọn **Thêm người dùng** để mở ngăn **Thêm/chỉnh sửa quyền**.

1. Sử dụng trường **Tìm kiếm** để tìm người dùng hoặc nhóm Azure Active Directory có quyền mà bạn muốn điều chỉnh. Chọn một **Vai trò** để chỉ định cho người dùng hoặc nhóm đó.

1. Chọn **Lưu**. Môi trường hiện tại sẽ tự động được chia sẻ với người dùng hoặc các thành viên của nhóm có quyền bạn đã thay đổi. Người dùng có thể truy cập ứng dụng Customer Insights và làm việc theo vai trò được chỉ định.

## <a name="view-current-permissions"></a>Xem các quyền hiện tại

Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Quản trị viên** > **Quyền** để xem nhiệm vụ nào hiện đang hoạt động.

- Cột **Loại** chỉ định một người dùng, nhóm hoặc ứng dụng. Hệ thống hỗ trợ người dùng cá nhân và nhóm.
- Vai trò được chỉ định theo cột **Vai trò**.
- Chọn tiêu đề cột bất kỳ để sắp xếp kết quả theo giá trị của cột đó.
- Sử dụng trường **Tìm kiếm** ở đầu trang để xác định vị trí của người dùng cụ thể.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
