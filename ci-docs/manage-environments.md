---
title: Quản lý môi trường
description: Tìm hiểu cách quản lý môi trường Thông tin chi tiết về khách hàng hiện tại với tư cách là quản trị viên. "
ms.date: 08/15/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: 8b4a88bdb75c6e638a76c39d18647681ad4556d7
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304315"
---
# <a name="manage-environments"></a>Quản lý môi trường

Quản trị viên [tạo ra](create-environment.md) và quản lý môi trường. Họ có thể thay đổi một số cài đặt trong môi trường hiện có. Doanh nghiệp, loại, khu vực, tùy chọn lưu trữ và Dataverse cài đặt được cố định sau khi tạo môi trường. Nếu bạn muốn thay đổi các cài đặt này, [thiết lập lại môi trường](#reset-an-existing-environment-preview) hoặc [tạo ra một môi trường mới](create-environment.md).

## <a name="edit-an-existing-environment"></a>Chỉnh sửa môi trường hiện có

Chỉnh sửa chi tiết của môi trường hiện có như tên hoặc thiết lập môi trường mặc định.

1. Chọn bộ chọn **Môi trường** trong tiêu đề của ứng dụng.

1. Chọn biểu tượng **Chỉnh sửa**.

   :::image type="content" source="media/edit-environment.png" alt-text="Biểu tượng để chỉnh sửa cài đặt môi trường.":::

1. Bên trong **Chỉnh sửa môi trường**, cập nhật cài đặt môi trường.

1. Lựa chọn **Xem lại và kết thúc**, sau đó **Cập nhật** để áp dụng các thay đổi.

## <a name="change-the-owner-of-an-environment"></a>Thay đổi chủ sở hữu của một môi trường

Một số người dùng có thể có quyền quản trị nhưng chỉ một người dùng là chủ sở hữu của môi trường. Theo mặc định, quản trị viên là người tạo môi trường ban đầu. Với tư cách là quản trị viên của một môi trường, bạn có thể chỉ định quyền sở hữu cho người dùng khác với quyền quản trị viên.

1. Chọn bộ chọn **Môi trường** trong tiêu đề của ứng dụng.

1. Chọn biểu tượng **Chỉnh sửa**.

1. Bên trong **Chỉnh sửa môi trường** ngăn, chuyển đến **Thông tin cơ bản** bươc.

1. Bên trong **Thay đổi chủ sở hữu của môi trường**, chọn chủ sở hữu mới của môi trường.  

1. Lựa chọn **Xem lại và kết thúc**, sau đó **Cập nhật** để áp dụng các thay đổi.

## <a name="claim-ownership-of-an-environment"></a>Yêu cầu quyền sở hữu môi trường

Nếu tài khoản người dùng của chủ sở hữu bị xóa hoặc bị tạm ngưng, môi trường sẽ không có chủ sở hữu. Bất kỳ người dùng quản trị nào cũng có thể xác nhận quyền sở hữu và trở thành chủ sở hữu mới. Quản trị viên chủ sở hữu có thể tiếp tục sở hữu môi trường hoặc [thay đổi quyền sở hữu cho một quản trị viên khác](#change-the-owner-of-an-environment).

Để xác nhận quyền sở hữu, hãy chọn **Lấy quyền sở hữu** nút hiển thị ở đầu mỗi trang trong Thông tin chi tiết về khách hàng khi chủ sở hữu ban đầu rời tổ chức.

## <a name="reset-an-existing-environment-preview"></a>Đặt lại môi trường hiện có (xem trước)

Với tư cách là chủ sở hữu của môi trường, hãy đặt lại môi trường về trạng thái trống nếu bạn muốn xóa tất cả các cấu hình và xóa dữ liệu đã nhập.

1. Chọn bộ chọn **Môi trường** trong tiêu đề của ứng dụng.

1. Chọn môi trường bạn muốn đặt lại và chọn dấu ba chấm dọc (&vellip;).

1. Chọn **Đặt lại (xem trước)**.

   :::image type="content" source="media/reset-environment.png" alt-text="Kiểm soát để thiết lập lại môi trường.":::

1. Chọn xem bạn có muốn đặt lại toàn bộ môi trường, mọi thứ ngoại trừ nguồn dữ liệu hay bất kỳ thứ gì được định cấu hình trên hồ sơ khách hàng hợp nhất hay không.

1. Để xác nhận, hãy nhập tên môi trường và chọn **Cài lại**.

## <a name="delete-an-existing-environment"></a>Xóa môi trường hiện có

Là chủ sở hữu của một môi trường, bạn có thể xóa nó.

> [!IMPORTANT]
> Xóa môi trường không xóa kết nối với Dataverse Môi trường. Nếu bạn dự định kết nối giống nhau Dataverse sang môi trường Thông tin chi tiết về khách hàng mới trong tương lai, bạn phải [loại bỏ kết nối đó với Dataverse Môi trường](customer-insights-dataverse.md#remove-an-existing-connection-to-a-dataverse-environment).

1. Chọn bộ chọn **Môi trường** trong tiêu đề của ứng dụng.

1. Chọn môi trường bạn muốn xóa và chọn dấu chấm lửng dọc (&vellip;). 

1. Chọn **Xóa bỏ**.

   :::image type="content" source="media/delete-environment.png" alt-text="Kiểm soát để xóa môi trường.":::

1. Để xác nhận thao tác xóa, hãy nhập tên môi trường rồi chọn **Xóa**.

[!INCLUDE [footer-include](includes/footer-banner.md)]
