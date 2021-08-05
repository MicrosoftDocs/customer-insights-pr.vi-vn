---
title: Tạo và quản lý môi trường
description: Tìm hiểu cách đăng ký dịch vụ và cách quản lý môi trường.
ms.date: 07/22/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 2f115269b9d07dd118ec18cc48b55de8aea9b5bb
ms.sourcegitcommit: 98267da3f3eddbdfbc89600a7f54e5e664a8f069
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 07/28/2021
ms.locfileid: "6683499"
---
# <a name="manage-environments"></a>Quản lý môi trường

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

## <a name="switch-environments"></a>Chuyển đổi môi trường

Chọn kiểm soát **Môi trường** ở góc trên bên phải của trang để thay đổi môi trường.

:::image type="content" source="media/home-page-environment-switcher.png" alt-text="Ảnh chụp màn hình của điều khiển để chuyển đổi môi trường.":::

Quản trị viên có thể [tạo](get-started-paid.md) và quản lý môi trường.

## <a name="edit-an-existing-environment"></a>Chỉnh sửa môi trường hiện có

Bạn có thể chỉnh sửa một số thông tin của các môi trường hiện có.

1.  Chọn bộ chọn **Môi trường** trong tiêu đề của ứng dụng.

2.  Chọn biểu tượng **Chỉnh sửa**.

3. Trong hộp **Chỉnh sửa môi trường**, bạn có thể cập nhật **Tên hiển thị** của môi trường, nhưng bạn không thể thay đổi **Khu vực** hoặc **Kiểu**.

4. Nếu một môi trường được định cấu hình để lưu trữ dữ liệu trong Azure Data Lake Storage, bạn có thể cập nhật **Khóa tài khoản**. Tuy nhiên, bạn không thể thay đổi **Tên tài khoản** hoặc tên **Vùng chứa** .

5. Bạn có thể cập nhật từ kết nối dựa trên khóa tài khoản thành kết nối dựa trên nguồn lực hoặc dựa trên đăng ký. Sau khi nâng cấp, bạn không thể hoàn nguyên về khóa tài khoản sau khi cập nhật. Để biết thêm thông tin, hãy xem [Kết nối thông tin chuyên sâu về đối tượng với tài khoản Azure Data Lake Storage Gen2 có dịch vụ chính Azure](connect-service-principal.md). Bạn không thể thay đổi thông tin **Vùng chứa** khi cập nhật kết nối.

6. Bạn có thể tùy ý cung cấp URL môi trường Microsoft Dataverse trong mục **Đặt cấu hình chia sẻ dữ liệu với Microsoft Dataverse và kích hoạt các nguồn lực bổ sung**. Các nguồn lực này bao gồm việc chia sẻ dữ liệu với các ứng dụng và giải pháp dựa trên Microsoft Dataverse, nhập dữ liệu từ nguồn dữ liệu tại chỗ hoặc sử dụng [dự đoán](predictions.md). Chọn **Bật chia sẻ dữ liệu** để chia sẻ dữ liệu đầu ra của Customer Insights với kho dữ liệu được quản lý của Microsoft Dataverse.

   > [!NOTE]
   > - Chia sẻ dữ liệu với Microsoft Dataverse Managed Data Lake hiện không được hỗ trợ khi bạn lưu tất cả dữ liệu vào Azure Data Lake Storage của riêng mình.
   > - [Dự đoán giá trị bị thiếu trong một thực thể](predictions.md) và báo cáo PowerBI Embedded trong thông tin chi tiết về đối tượng (nếu được bật trên môi trường của bạn) hiện không được hỗ trợ khi bạn bật chia sẻ dữ liệu với Microsoft Dataverse Managed Data Lake.

   Sau khi bạn bật tính năng chia sẻ dữ liệu với Microsoft Dataverse, một lần làm mới hoàn toàn nguồn dữ liệu của bạn và các quy trình khác sẽ bắt đầu. Nếu các quy trình hiện đang chạy, bạn sẽ không thấy tùy chọn bật tính năng chia sẻ dữ liệu với Microsoft Dataverse. Hãy đợi các quy trình đó hoàn tất hoặc hủy chúng để bật tính năng chia sẻ dữ liệu. 
   
   :::image type="content" source="media/datasharing-with-DataverseMDL.png" alt-text="Các tùy chọn cấu hình để bật tính năng chia sẻ dữ liệu với Microsoft Dataverse.":::
   
   Khi bạn chạy các quy trình, chẳng hạn như nhập dữ liệu hoặc tạo phân khúc, các thư mục tương ứng sẽ được tạo trong tài khoản lưu trữ mà bạn đã chỉ định ở trên. Tệp dữ liệu và tệp model.json sẽ được tạo và thêm vào các thư mục con tương ứng, tùy thuộc vào quá trình bạn chạy.

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
- Nguồn dữ liệu từ thư mục Common Data Model và Dataverse Managed Data Lake. Bạn sẽ phải tạo các nguồn dữ liệu đó theo cách thủ công có cùng tên như trong môi trường nguồn.

Khi bạn sao chép một môi trường, bạn sẽ thấy một thông báo xác nhận rằng môi trường mới đã được tạo. Chọn **Chuyển đến nguồn dữ liệu** để xem danh sách các nguồn dữ liệu.

Tất cả nguồn dữ liệu sẽ hiển thị trạng thái **Đã yêu cầu thông tin đăng nhập**. Chỉnh sửa nguồn dữ liệu và nhập thông tin đăng nhập để làm mới những nguồn dữ liệu đó.

:::image type="content" source="media/data-sources-copied.png" alt-text="Danh sách các nguồn dữ liệu đã được sao chép và cần xác thực.":::

Sau khi làm mới nguồn dữ liệu, hãy chuyển đến **Dữ liệu** > **Hợp nhất**. Tại đây, bạn sẽ tìm thấy các thiết đặt từ môi trường nguồn. Chỉnh sửa chúng khi cần hoặc chọn **Chạy** để bắt đầu quá trình hợp nhất dữ liệu và tạo ra thực thể khách hàng hợp nhất.

Khi quá trình hợp nhất dữ liệu hoàn tất, hãy chuyển đến **Biện pháp** và **Phân khúc** để đồng thời làm mới những dữ liệu này.

## <a name="reset-an-existing-environment"></a>Đặt lại môi trường hiện có

Là quản trị viên, bạn có thể đặt lại một môi trường về trạng thái trống nếu bạn muốn xóa tất cả các cấu hình và xóa dữ liệu đã nhập.

1.  Chọn bộ chọn **Môi trường** trong tiêu đề của ứng dụng. 

2.  Chọn môi trường bạn muốn đặt lại và chọn dấu chấm lửng (**...**). 

3. Chọn tùy chọn **Đặt lại**. 

4.  Để xác nhận việc xóa, hãy nhập tên môi trường và chọn **Đặt lại**.

## <a name="delete-an-existing-environment"></a>Xóa môi trường hiện có

Với tư cách là quản trị viên, bạn có thể xóa môi trường do mình quản lý.

1.  Chọn bộ chọn **Môi trường** trong tiêu đề của ứng dụng.

2.  Chọn môi trường bạn muốn đặt lại và chọn dấu chấm lửng (**...**). 

3. Chọn tùy chọn **Xóa**. 

4.  Để xác nhận thao tác xóa, hãy nhập tên môi trường rồi chọn **Xóa**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
