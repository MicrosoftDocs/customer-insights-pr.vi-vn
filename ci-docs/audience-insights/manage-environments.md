---
title: Tạo và quản lý môi trường
description: Tìm hiểu cách đăng ký dịch vụ và cách quản lý môi trường.
ms.date: 06/15/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 904ce68336cba4b7a4d5a37692b72d091400559d
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304906"
---
# <a name="manage-environments"></a>Quản lý môi trường

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Bài viết này giải thích cách tạo một tổ chức mới và cách cung cấp môi trường.

## <a name="sign-up-and-create-an-organization"></a>Đăng ký và tạo một tổ chức

1. Truy cập trang web [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/).

2. Chọn **Bắt đầu**.

3. Chọn kịch bản đăng nhập bạn mong muốn rồi nhấp vào đường liên kết tương ứng.

4. Chấp nhận các điều khoản và điều kiện rồi chọn **Tiếp tục** để bắt đầu tạo tổ chức.

5. Sau khi môi trường được tạo, bạn sẽ được chuyển hướng đến [Customer Insights](https://home.ci.ai.dynamics.com).

6. Sử dụng môi trường demo để khám phá ứng dụng hoặc tạo môi trường mới bằng cách làm theo các bước trong phần tiếp theo.

7. Sau khi xác định các tùy chọn cài đặt cho môi trường, hãy chọn **Tạo**.

8. Bạn sẽ được đăng nhập sau khi tạo thành công môi trường.

## <a name="create-an-environment-in-an-existing-organization"></a>Tạo môi trường trong tổ chức hiện có

Có hai cách để tạo một môi trường mới. Bạn có thể chỉ định một cấu hình hoàn toàn mới hoặc sao chép một số thiết đặt cấu hình từ môi trường hiện có.

> [!NOTE]
> Các tổ chức có thể tạo *hai* môi trường cho mọi giấy phép Customer Insights. Nếu tổ chức của bạn mua nhiều giấy phép, vui lòng [liên hệ với nhóm hỗ trợ của chúng tôi](https://go.microsoft.com/fwlink/?linkid=2079641) để tăng số lượng môi trường khả dụng. Để biết thêm thông tin về nguồn lực và nguồn lực bổ trợ, hãy tải [Hướng dẫn cấp phép Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544) xuống.

Để tạo môi trường:

1. Chọn bộ chọn **Môi trường** trong tiêu đề của ứng dụng.

1. Chọn **Mới**.

   > [!div class="mx-imgBorder"]
   > ![Thiết đặt môi trường.](media/environment-settings-dialog.png)

1. Trong hộp thoại **Tạo môi trường**, chọn **Môi trường mới**.

   Nếu bạn muốn [sao chép dữ liệu từ môi trường hiện tại](#considerations-for-copy-configuration-preview), chọn **Sao chép từ môi trường hiện có**. Bạn sẽ nhìn thấy danh sách tất cả các môi trường có sẵn trong tổ chức, nơi bạn có thể sao chép dữ liệu từ đó.

1. Cung cấp các chi tiết sau đây:
   - **Tên**: Tên cho môi trường này. Trường này đã được điền nếu bạn sao chép một môi trường hiện có, nhưng bạn có thể thay đổi trường này.
   - **Loại**: Chọn xem bạn muốn tạo môi trường sản xuất hay hộp cát.
   - **Vùng**: Vùng triển khai và lưu trư dịch vụ.
   
1. Bạn có thể chọn **Thiết đặt nâng cao**:

   - **Lưu tất cả dữ liệu vào**: Chỉ định nơi bạn muốn lưu trữ dữ liệu đầu ra được tạo từ Customer Insights. Bạn sẽ có hai lựa chọn: **Bộ nhớ Customer Insights** (một Azure Data Lake do nhóm Customer Insights quản lý) và **Azure Data Lake Storage** (Azure Data Lake Storage của riêng bạn). Tùy chọn mặc định là lưu trữ trong Customer Insights.

     > [!NOTE]
     > Bằng việc lưu dữ liệu vào Azure Data Lake Storage, bạn đồng ý rằng dữ liệu sẽ được chuyển sang và lưu trữ tại vị trí địa lý phù hợp cho tài khoản Azure Storage đó. Vị trí này có thể khác với nơi lưu trữ dữ liệu trong Dynamics 365 Customer Insights. [Hãy tìm hiểu thêm tại Trung tâm tin cậy Microsoft.](https://www.microsoft.com/trust-center)
     >
     > Hiện tại, các thực thể đã thu nạp sẽ luôn được lưu trữ trong Customer Insights Managed Data Lake. 
     > 
     > Chúng tôi chỉ hỗ trợ Azure Data Lake Storage tài khoản từ cùng một vùng Azure mà bạn đã chọn khi tạo môi trường. 
     > 
     > Chúng tôi chỉ hỗ trợ tài khoản Azure Data Lake Storage đã bật tính năng không gian tên theo cấp bậc.


   - Đối với tùy chọn Azure Data Lake Storage, bạn có thể chọn giữa tùy chọn dựa trên nguồn lực và tùy chọn dựa trên đăng ký để xác thực. Để biết thêm thông tin, hãy xem [Kết nối thông tin chuyên sâu về đối tượng với tài khoản Azure Data Lake Storage Gen2 có dịch vụ chính Azure](connect-service-principal.md). Tên **Vùng chứa** không thể thay đổi và mặc định là `customerinsights`.
   
   - Nếu bạn muốn sử dụng [dự đoán](predictions.md), hãy định cấu hình tính năng chia sẻ dữ liệu với Microsoft Dataverse hoặc cho phép nhập dữ liệu từ nguồn dữ liệu tại chỗ, cung cấp URL môi trường Microsoft Dataverse trong mục **Định cấu hình chia sẻ dữ liệu với Microsoft Dataverse và cho phép các nguồn lực bổ sung**. Chọn **Bật chia sẻ dữ liệu** để chia sẻ dữ liệu đầu ra của Customer Insights với Microsoft Dataverse Managed Data Lake.

     > [!NOTE]
     > - Chia sẻ dữ liệu với Microsoft Dataverse Managed Data Lake hiện không được hỗ trợ khi bạn lưu tất cả dữ liệu vào Azure Data Lake Storage của riêng mình.
     > - [Dự đoán giá trị bị thiếu trong một thực thể](predictions.md) hiện không được hỗ trợ khi bạn bật chia sẻ dữ liệu với Microsoft Dataverse Managed Data Lake.

     > [!div class="mx-imgBorder"]
     > ![Các tùy chọn cấu hình để bật tính năng chia sẻ dữ liệu với Microsoft Dataverse.](media/datasharing-with-DataverseMDL.png)

   Khi bạn chạy các quy trình, chẳng hạn như nhập dữ liệu hoặc tạo phân khúc, các thư mục tương ứng sẽ được tạo trong tài khoản lưu trữ mà bạn đã chỉ định ở trên. Tệp dữ liệu và tệp model.json sẽ được tạo và thêm vào các thư mục dựa trên tên quy trình.

   Nếu bạn tạo nhiều môi trường Customer Insights và chọn lưu các thực thể đầu ra từ các môi trường đó trong tài khoản lưu trữ của mình, các thư mục riêng biệt sẽ được tạo cho từng môi trường với ci_<environmentid> trong vùng chứa.

### <a name="considerations-for-copy-configuration-preview"></a>Những điều cần cân nhắc đối với cấu hình sao chép (xem trước)

Các thiết đặt cấu hình sau được sao chép:

- Cấu hình tính năng
- Nguồn dữ liệu được nhập/thu nạp
- Cấu hình hợp nhất dữ liệu (Bản đồ, kết hợp, hợp nhất)
- Phân khúc
- Biện pháp
- Mối quan hệ
- Hoạt động
- Chỉ mục tìm kiếm & lọc
- Đích xuất
- Làm mới theo lịch trình
- Nội dung làm phong phú
- Quản lý mô hình
- Chỉ định vai trò

Các thiết đặt sau *không* được sao chép:

- Hồ sơ khách hàng.
- Thông tin xác thực nguồn dữ liệu. Bạn sẽ phải cung cấp thông tin đăng nhập cho mỗi nguồn dữ liệu và làm mới các nguồn dữ liệu theo cách thủ công.
- Nguồn dữ liệu từ thư mục Common Data Model và Dataverse Managed Data Lake. Bạn sẽ phải tạo các nguồn dữ liệu đó theo cách thủ công có cùng tên như trong môi trường nguồn.

Khi bạn sao chép một môi trường, bạn sẽ thấy một thông báo xác nhận rằng môi trường mới đã được tạo. Chọn **Chuyển đến nguồn dữ liệu** để xem danh sách các nguồn dữ liệu.

Tất cả nguồn dữ liệu sẽ hiển thị trạng thái **Đã yêu cầu thông tin đăng nhập**. Chỉnh sửa nguồn dữ liệu và nhập thông tin đăng nhập để làm mới những nguồn dữ liệu đó.

> [!div class="mx-imgBorder"]
> ![Đã sao chép nguồn dữ liệu.](media/data-sources-copied.png)

Sau khi làm mới nguồn dữ liệu, hãy chuyển đến **Dữ liệu** > **Hợp nhất**. Tại đây, bạn sẽ tìm thấy các thiết đặt từ môi trường nguồn. Chỉnh sửa chúng khi cần hoặc chọn **Chạy** để bắt đầu quá trình hợp nhất dữ liệu và tạo ra thực thể khách hàng hợp nhất.

Khi quá trình hợp nhất dữ liệu hoàn tất, hãy chuyển đến **Biện pháp** và **Phân khúc** để đồng thời làm mới những dữ liệu này.

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
   > - [Dự đoán giá trị bị thiếu trong một thực thể](predictions.md) hiện không được hỗ trợ khi bạn bật tính năng chia sẻ dữ liệu với dịch vụ Microsoft Dataverse Managed Data Lake.

   Sau khi bạn bật tính năng chia sẻ dữ liệu với Microsoft Dataverse, một lần làm mới hoàn toàn nguồn dữ liệu của bạn và các quy trình khác sẽ bắt đầu. Nếu các quy trình hiện đang chạy, bạn sẽ không thấy tùy chọn bật tính năng chia sẻ dữ liệu với Microsoft Dataverse. Hãy đợi các quy trình đó hoàn tất hoặc hủy chúng để bật tính năng chia sẻ dữ liệu. 
   
   :::image type="content" source="media/datasharing-with-DataverseMDL.png" alt-text="Các tùy chọn cấu hình để bật tính năng chia sẻ dữ liệu với Microsoft Dataverse.":::
   
   Khi bạn chạy các quy trình, chẳng hạn như nhập dữ liệu hoặc tạo phân khúc, các thư mục tương ứng sẽ được tạo trong tài khoản lưu trữ mà bạn đã chỉ định ở trên. Tệp dữ liệu và tệp model.json sẽ được tạo và thêm vào các thư mục con tương ứng, tùy thuộc vào quá trình bạn chạy.

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
