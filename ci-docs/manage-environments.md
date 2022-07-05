---
title: 'Cách thực hiện: Quản lý môi trường'
description: Tìm hiểu cách quản lý môi trường Thông tin chi tiết về khách hàng hiện tại với tư cách là quản trị viên. "
ms.date: 05/31/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: fc3b3f404cf0ac84c782778414494289c803babe
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 06/29/2022
ms.locfileid: "9083070"
---
# <a name="how-to-manage-environments"></a>Cách thực hiện: Quản lý môi trường

Quản trị viên [tạo ra](create-environment.md) và quản lý môi trường. Họ có thể thay đổi một số cài đặt trong môi trường hiện có. Doanh nghiệp, loại, khu vực, tùy chọn lưu trữ và Dataverse cài đặt được cố định sau khi tạo môi trường. Nếu bạn muốn thay đổi các cài đặt này, hãy đặt lại môi trường hoặc tạo môi trường mới.

## <a name="edit-an-existing-environment"></a>Chỉnh sửa môi trường hiện có

Bạn có thể chỉnh sửa một số thông tin của các môi trường hiện có.

1. Chọn bộ chọn **Môi trường** trong tiêu đề của ứng dụng.

1. Chọn biểu tượng **Chỉnh sửa**.

   :::image type="content" source="media/edit-environment.png" alt-text="Biểu tượng để chỉnh sửa cài đặt môi trường.":::

1. Trong hộp **Chỉnh sửa môi trường**, bạn có thể cập nhật thiết đặt môi trường.

Để bắt đầu với một môi trường trong lành, hãy xem [Tạo một môi trường mới](create-environment.md).

## <a name="change-the-owner-of-an-environment"></a>Thay đổi chủ sở hữu của một môi trường

Một số người dùng có thể có quyền quản trị nhưng chỉ một người dùng là chủ sở hữu của một môi trường. Theo mặc định, quản trị viên là người tạo môi trường ban đầu. Với tư cách là quản trị viên của một môi trường, bạn có thể chỉ định quyền sở hữu cho người dùng khác với quyền quản trị viên.

1. Chọn bộ chọn **Môi trường** trong tiêu đề của ứng dụng.

1. Chọn biểu tượng **Chỉnh sửa**.

1. Bên trong **Chỉnh sửa môi trường** hộp, đi đến **Thông tin cơ bản** bươc.

1. Bên trong **Thay đổi chủ sở hữu của môi trường**, chọn chủ sở hữu mới của môi trường.  

1. Lựa chọn **Xem lại và kết thúc**, sau đó **Cập nhật** để áp dụng các thay đổi.

## <a name="claim-ownership-of-an-environment"></a>Yêu cầu quyền sở hữu môi trường

Nếu tài khoản người dùng của chủ sở hữu bị xóa hoặc bị tạm ngưng, môi trường sẽ không có chủ sở hữu. Mọi người dùng quản trị đều có thể xác nhận quyền sở hữu và trở thành chủ sở hữu mới. Họ có thể tiếp tục sở hữu môi trường hoặc [thay đổi quyền sở hữu cho một quản trị viên khác](#change-the-owner-of-an-environment).

Để xác nhận quyền sở hữu, hãy chọn **Lấy quyền sở hữu** nút hiển thị ở đầu mỗi trang trong Thông tin chi tiết về khách hàng khi chủ sở hữu ban đầu rời tổ chức.

## <a name="reset-an-existing-environment-preview"></a>Đặt lại môi trường hiện có (Xem trước)

Là chủ sở hữu của môi trường, bạn có thể đặt lại môi trường về trạng thái trống nếu bạn muốn xóa tất cả các cấu hình và xóa dữ liệu đã nhập.

1. Chọn bộ chọn **Môi trường** trong tiêu đề của ứng dụng.

1. Chọn môi trường bạn muốn đặt lại và chọn dấu ba chấm dọc (&vellip;).

1. Chọn tùy chọn **Đặt lại**.

   :::image type="content" source="media/reset-environment.png" alt-text="Kiểm soát để thiết lập lại môi trường.":::

1. Chọn xem bạn có muốn đặt lại toàn bộ môi trường, mọi thứ ngoại trừ nguồn dữ liệu hay bất kỳ thứ gì được định cấu hình trên hồ sơ khách hàng hợp nhất hay không.

1. Để xác nhận, hãy nhập tên môi trường và chọn **Cài lại**.

## <a name="delete-an-existing-environment"></a>Xóa môi trường hiện có

Với tư cách là chủ sở hữu của một môi trường, bạn có thể xóa một môi trường mà bạn quản lý.

1. Chọn bộ chọn **Môi trường** trong tiêu đề của ứng dụng.

1. Chọn môi trường bạn muốn đặt lại và chọn dấu ba chấm dọc (&vellip;). 

1. Chọn tùy chọn **Xóa**.

   :::image type="content" source="media/delete-environment.png" alt-text="Kiểm soát để xóa môi trường.":::

1. Để xác nhận thao tác xóa, hãy nhập tên môi trường rồi chọn **Xóa**.

> [!IMPORTANT]
> Xóa môi trường không xóa kết nối với Dataverse Môi trường. Nếu bạn định kết nối giống nhau Dataverse sang môi trường Thông tin chi tiết về khách hàng mới trong tương lai, bạn phải xóa kết nối đó Tìm hiểu cách [loại bỏ một kết nối hiện có với một Dataverse Môi trường](customer-insights-dataverse.md#remove-an-existing-connection-to-a-dataverse-environment).

[!INCLUDE [footer-include](includes/footer-banner.md)]
