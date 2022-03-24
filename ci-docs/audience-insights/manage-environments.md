---
title: Tạo và quản lý môi trường
description: Tìm hiểu cách đăng ký dịch vụ và cách quản lý môi trường.
ms.date: 02/09/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: 4f4e5a8415f6c2128b0480edf67f317124eeeba9
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376902"
---
# <a name="manage-environments"></a>Quản lý môi trường

## <a name="switch-environments"></a>Chuyển đổi môi trường

Chọn kiểm soát **Môi trường** ở góc trên bên phải của trang để thay đổi môi trường.

:::image type="content" source="media/home-page-environment-switcher.png" alt-text="Ảnh chụp màn hình của điều khiển để chuyển đổi môi trường.":::

Quản trị viên có thể [tạo](create-environment.md) và quản lý môi trường.

## <a name="edit-an-existing-environment"></a>Chỉnh sửa môi trường hiện có

Bạn có thể chỉnh sửa một số thông tin của các môi trường hiện có.

1.  Chọn bộ chọn **Môi trường** trong tiêu đề của ứng dụng.

2.  Chọn biểu tượng **Chỉnh sửa**.

3. Trong hộp **Chỉnh sửa môi trường**, bạn có thể cập nhật thiết đặt môi trường.

Để biết thêm thông tin về thiết đặt môi trường, hãy xem [Tạo môi trường mới](create-environment.md).

## <a name="connect-to-microsoft-dataverse"></a>Kết nối với Microsoft Dataverse
   
Bước **Microsoft Dataverse** cho phép bạn kết nối Customer Insights với môi trường Dataverse.

Để sử dụng [mô hình dự đoán sẵn dùng](predictions-overview.md#out-of-box-models), đặt cấu hình chia sẻ dữ liệu với Dataverse. Hoặc bạn có thể bật tính năng nhập dữ liệu từ các nguồn dữ liệu tại chỗ, cung cấp URL môi trường Microsoft Dataverse mà tổ chức của bạn quản lý.

> [!IMPORTANT]
> Thông tin chi tiết về khách hàng và Dataverse phải ở trong cùng một khu vực để cho phép chia sẻ dữ liệu.

:::image type="content" source="media/dataverse-provisioning.png" alt-text="Các tùy chọn cấu hình để bật tính năng chia sẻ dữ liệu với Microsoft Dataverse.":::

> [!NOTE]
> Customer Insights không hỗ trợ các tình huống chia sẻ dữ liệu sau:
> - Nếu bạn lưu tất cả dữ liệu vào Azure Data Lake Storage của mình, bạn sẽ không thể bật chia sẻ dữ liệu với kho dữ liệu Dataverse được quản lý.
> - Nếu bạn bật chia sẻ dữ liệu với Dataverse, bạn sẽ không thể [tạo các giá trị được dự đoán hoặc bị thiếu trong một thực thể](predictions.md).

## <a name="copy-the-environment-configuration"></a>Sao chép cấu hình môi trường

Khi bạn tạo một môi trường mới, bạn có thể chọn sao chép cấu hình từ một môi trường hiện có. 

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Ảnh chụp màn hình của các tùy chọn cài đặt trong cài đặt môi trường.":::

Bạn sẽ nhìn thấy danh sách tất cả các môi trường có sẵn trong tổ chức, nơi bạn có thể sao chép dữ liệu từ đó.

Các thiết đặt cấu hình sau được sao chép:

- Nguồn dữ liệu được nhập/thu nạp
- Cấu hình hợp nhất dữ liệu (Bản đồ, kết hợp, hợp nhất)
- Phân khúc
- Biện pháp
- Mối quan hệ
- Hoạt động
- Chỉ mục tìm kiếm & lọc
- Đích xuất
- Làm mới theo lịch trình
- Nội dung tăng cường
- Quản lý mô hình
- Chỉ định vai trò

Dữ liệu sau *không* được sao chép:

- Hồ sơ khách hàng.
- Thông tin xác thực nguồn dữ liệu. Bạn sẽ phải cung cấp thông tin đăng nhập cho mỗi nguồn dữ liệu và làm mới các nguồn dữ liệu theo cách thủ công.

- Nguồn dữ liệu từ thư mục Common Data Model và kho dữ liệu Dataverse được quản lý. Bạn sẽ phải tạo các nguồn dữ liệu đó theo cách thủ công có cùng tên như trong môi trường nguồn.

Khi bạn sao chép một môi trường, bạn sẽ thấy một thông báo xác nhận rằng môi trường mới đã được tạo. Chọn **Chuyển đến nguồn dữ liệu** để xem danh sách các nguồn dữ liệu.

Tất cả nguồn dữ liệu sẽ hiển thị trạng thái **Đã yêu cầu thông tin đăng nhập**. Chỉnh sửa nguồn dữ liệu và nhập thông tin đăng nhập để làm mới những nguồn dữ liệu đó.

:::image type="content" source="media/data-sources-copied.png" alt-text="Danh sách các nguồn dữ liệu đã được sao chép và cần xác thực.":::

Sau khi làm mới nguồn dữ liệu, hãy chuyển đến **Dữ liệu** > **Hợp nhất**. Tại đây, bạn sẽ tìm thấy các thiết đặt từ môi trường nguồn. Chỉnh sửa chúng khi cần hoặc chọn **Chạy** để bắt đầu quá trình hợp nhất dữ liệu và tạo ra thực thể khách hàng hợp nhất.

Khi quá trình hợp nhất dữ liệu hoàn tất, hãy chuyển đến **Biện pháp** và **Phân khúc** để đồng thời làm mới những dữ liệu này.

## <a name="change-the-owner-of-an-environment"></a>Thay đổi chủ sở hữu của một môi trường

Mặc dù một số người dùng có thể có quyền quản trị trong Thông tin chi tiết về khách hàng, nhưng chỉ một người dùng là chủ sở hữu của môi trường. Theo mặc định, quản trị viên là người tạo môi trường ban đầu. Với tư cách là quản trị viên của một môi trường, bạn có thể chỉ định quyền sở hữu cho người dùng khác với quyền quản trị viên.

1. Chọn bộ chọn **Môi trường** trong tiêu đề của ứng dụng.

1. Chọn biểu tượng **Chỉnh sửa**.

1. Bên trong **Chỉnh sửa môi trường** hộp, đi đến **Thông tin cơ bản** bươc chân.

1. Bên trong **Thay đổi chủ sở hữu của môi trường**, chọn chủ sở hữu mới của môi trường.  

1. Lựa chọn **Xem lại và kết thúc**, sau đó **Cập nhật** để áp dụng các thay đổi. 

## <a name="claim-ownership-of-an-environment"></a>Yêu cầu quyền sở hữu môi trường

Nếu chủ sở hữu của một môi trường rời khỏi tổ chức hoặc tài khoản người dùng của họ bị xóa, thì môi trường đó sẽ không có chủ sở hữu. Người dùng có quyền quản trị có thể xác nhận quyền sở hữu và trở thành chủ sở hữu mới. Họ có thể tiếp tục sở hữu môi trường hoặc [thay đổi quyền sở hữu thành quản trị viên khác](#change-the-owner-of-an-environment). 

Để xác nhận quyền sở hữu, hãy chọn **Lấy quyền sở hữu** nút hiển thị ở đầu mỗi trang trong Thông tin chi tiết về khách hàng khi chủ sở hữu ban đầu rời tổ chức.

## <a name="reset-an-existing-environment"></a>Đặt lại môi trường hiện có

Là chủ sở hữu của môi trường, bạn có thể đặt lại môi trường về trạng thái trống nếu bạn muốn xóa tất cả các cấu hình và xóa dữ liệu đã nhập.

1.  Chọn bộ chọn **Môi trường** trong tiêu đề của ứng dụng. 

2.  Chọn môi trường bạn muốn đặt lại và chọn dấu chấm lửng (**...**). 

3. Chọn tùy chọn **Đặt lại**. 

4.  Để xác nhận việc xóa, hãy nhập tên môi trường và chọn **Đặt lại**.

## <a name="delete-an-existing-environment"></a>Xóa môi trường hiện có

Với tư cách là chủ sở hữu của một môi trường, bạn có thể xóa một môi trường mà bạn quản lý.

1.  Chọn bộ chọn **Môi trường** trong tiêu đề của ứng dụng.

2.  Chọn môi trường bạn muốn đặt lại và chọn dấu chấm lửng (**...**). 

3. Chọn tùy chọn **Xóa**. 

4.  Để xác nhận thao tác xóa, hãy nhập tên môi trường rồi chọn **Xóa**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
