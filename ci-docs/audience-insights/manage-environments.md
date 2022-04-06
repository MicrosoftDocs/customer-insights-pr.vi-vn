---
title: Tạo và quản lý môi trường
description: Tìm hiểu cách đăng ký dịch vụ và cách quản lý môi trường.
ms.date: 03/28/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: adkuppa
ms.author: adkuppa
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: ba29bcd173e615e544bd10e69043f310c009eb47
ms.sourcegitcommit: ae02ac950810242e2505d7d371b80210dc8a0777
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 03/29/2022
ms.locfileid: "8492030"
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

Cung cấp của riêng bạn Microsoft Dataverse môi trường để chia sẻ dữ liệu (hồ sơ và thông tin chi tiết) với các ứng dụng kinh doanh dựa trên Dataverse, như Dynamics 365 Marketing hoặc các ứng dụng theo mô hình trong Power Apps.

Để sử dụng [mô hình dự đoán sẵn dùng](predictions-overview.md#out-of-box-models), đặt cấu hình chia sẻ dữ liệu với Dataverse. Hoặc bạn có thể bật tính năng nhập dữ liệu từ các nguồn dữ liệu tại chỗ, cung cấp URL môi trường Microsoft Dataverse mà tổ chức của bạn quản lý.

Cho phép chia sẻ dữ liệu với Microsoft Dataverse bằng cách chọn hộp kiểm chia sẻ dữ liệu sẽ kích hoạt một lần làm mới toàn bộ các nguồn dữ liệu của bạn và tất cả các quy trình khác.

> [!IMPORTANT]
> 1. Thông tin chi tiết về khách hàng và Dataverse phải ở trong cùng một khu vực để có thể chia sẻ dữ liệu.
> 1. Bạn phải có vai trò quản trị viên toàn cầu trong Dataverse Môi trường. Xác minh nếu điều này [Dataverse môi trường được liên kết](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) vào các nhóm bảo mật nhất định và đảm bảo rằng bạn được thêm vào các nhóm bảo mật đó.
> 1. Không có môi trường Thông tin chi tiết về khách hàng hiện tại nào được liên kết với môi trường đó Dataverse Môi trường. Học cách [loại bỏ một kết nối hiện có với một Dataverse Môi trường](#remove-an-existing-connection-to-a-dataverse-environment).

:::image type="content" source="media/dataverse-enable-datasharing.png" alt-text="Các tùy chọn cấu hình để bật tính năng chia sẻ dữ liệu với Microsoft Dataverse.":::

### <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Bật chia sẻ dữ liệu với Dataverse từ của riêng bạn Azure Data Lake Storage (Xem trước)

Nếu môi trường của bạn được định cấu hình để sử dụng Azure Data Lake Storage để lưu trữ dữ liệu Thông tin chi tiết về khách hàng, cho phép chia sẻ dữ liệu với Microsoft Dataverse cần một số cấu hình bổ sung.

1. Tạo hai nhóm bảo mật trên đăng ký Azure của bạn - một **Người đọc** nhóm an ninh và một **Người đóng góp** nhóm bảo mật và thiết lập Microsoft Dataverse dịch vụ với tư cách là chủ sở hữu cho cả hai nhóm bảo mật.
2. Quản lý Danh sách kiểm soát truy cập (ACL) trên vùng chứa CustomerInsights trong tài khoản lưu trữ của bạn thông qua các nhóm bảo mật này. Thêm Microsoft Dataverse dịch vụ và bất kỳ Dataverse các ứng dụng kinh doanh dựa trên cơ sở như Dynamics 365 Marketing cho **Người đọc** nhóm an ninh với **chỉ đọc** quyền. Thêm vào *chỉ một* ứng dụng Thông tin chi tiết về khách hàng cho **Người đóng góp** nhóm bảo mật để cấp cho cả hai **đọc và viết** quyền để viết tiểu sử và thông tin chi tiết.
   
#### <a name="prerequisites"></a>Điều kiện tiên quyết

Để thực thi các tập lệnh PowerShell, bạn cần nhập ba mô-đun sau. 

1. Cài đặt phiên bản mới nhất của [Azure Active Directory PowerShell cho đồ thị](/powershell/azure/active-directory/install-adv2).
   1. Trên PC, chọn phím Windows trên bàn phím và tìm kiếm **Windows PowerShell** và chọn **Chạy với tư cách quản trị viên**.
   1. Trong cửa sổ PowerShell mở ra, hãy nhập `Install-Module AzureAD`.
2. Nhập ba mô-đun.
    1. Trong cửa sổ PowerShell, hãy nhập`Install-Module -Name Az.Accounts` và làm theo các bước. 
    1. Lặp lại cho`Install-Module -Name Az.Resources` và `Install-Module -Name Az.Storage`.

#### <a name="configuration-steps"></a>Các bước cấu hình

1. Tải xuống hai tập lệnh PowerShell bạn cần để chạy từ kỹ sư của chúng tôi [GitHub repo](https://github.com/trin-msft/byol).
    1. `CreateSecurityGroups.ps1`
       - Bạn cần *quản trị viên thuê nhà* quyền để chạy tập lệnh PowerShell này. 
       - Tập lệnh PowerShell này tạo hai nhóm bảo mật trên đăng ký Azure của bạn. Một cho nhóm Người đọc và một cho nhóm Cộng tác viên và sẽ tạo Microsoft Dataverse dịch vụ với tư cách là chủ sở hữu cho cả hai nhóm bảo mật này.
       - Thực thi tập lệnh PowerShell này trong Windows PowerShell bằng cách cung cấp ID đăng ký Azure chứa Azure Data Lake Storage. Mở tập lệnh PowerShell trong trình chỉnh sửa để xem xét thông tin bổ sung và logic được triển khai.
       - Lưu cả hai giá trị ID nhóm bảo mật được tạo bởi tập lệnh này vì chúng tôi sẽ sử dụng chúng trong`ByolSetup.ps1` kịch bản.
       
        > [!NOTE]
        > Đối tượng thuê của bạn có thể tắt tính năng tạo nhóm bảo mật. Trong trường hợp đó, cần thiết lập thủ công và Azure AD quản trị viên sẽ phải [cho phép tạo nhóm bảo mật](/azure/active-directory/enterprise-users/groups-self-service-management).

    2. `ByolSetup.ps1`
        - Bạn cần *Chủ sở hữu dữ liệu khối lưu trữ* quyền ở cấp tài khoản lưu trữ / vùng chứa để chạy tập lệnh này hoặc tập lệnh này sẽ tạo một tập lệnh cho bạn. Nhiệm vụ của bạn có thể được xóa theo cách thủ công sau khi chạy thành công tập lệnh.
        - Tập lệnh PowerShell này thêm điều khiển truy cập dựa trên tole bắt buộc (RBAC) cho Microsoft Dataverse dịch vụ và bất kỳ Dataverse ứng dụng kinh doanh dựa trên cơ sở. Nó cũng cập nhật Danh sách kiểm soát truy cập (ACL) trên vùng chứa CustomerInsights cho các nhóm bảo mật được tạo bằng`CreateSecurityGroups.ps1` kịch bản. Nhóm Cộng tác viên sẽ có *rwx* quyền và nhóm độc giả sẽ có *rx* chỉ sự cho phép.
        - Thực thi tập lệnh PowerShell này trong Windows PowerShell bằng cách cung cấp ID đăng ký Azure chứa Azure Data Lake Storage, tên tài khoản lưu trữ, tên nhóm tài nguyên và các giá trị id nhóm bảo mật Reader và Contributor. Mở tập lệnh PowerShell trong trình chỉnh sửa để xem xét thông tin bổ sung và logic được triển khai.
        - Sao chép chuỗi đầu ra sau khi chạy thành công tập lệnh. Chuỗi đầu ra trông giống như sau:`https: //DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`
        
2. Nhập chuỗi đầu ra được sao chép từ bên trên vào **Định danh quyền** trường của bước cấu hình môi trường cho Microsoft Dataverse.

:::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Tùy chọn cấu hình để cho phép chia sẻ dữ liệu từ của riêng bạn Azure Data Lake Storage với Microsoft Dataverse .":::

Customer Insights không hỗ trợ các tình huống chia sẻ dữ liệu sau:
- Nếu bạn bật chia sẻ dữ liệu với Dataverse, bạn sẽ không thể [tạo các giá trị được dự đoán hoặc bị thiếu trong một thực thể](predictions.md).
- Nếu bạn bật chia sẻ dữ liệu với Dataverse, bạn sẽ không thể xem bất kỳ báo cáo nhúng PowerBI tùy chọn nào trong môi trường Thông tin chi tiết về khách hàng của mình.

### <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>Xóa kết nối hiện có với một Dataverse Môi trường

Khi kết nối với một Dataverse môi trường, thông báo lỗi **Tổ chức CDS này đã được đính kèm với một phiên bản Thông tin chi tiết về khách hàng khác** có nghĩa là Dataverse môi trường đã được sử dụng trong môi trường Thông tin chi tiết về khách hàng. Bạn có thể xóa kết nối hiện có với tư cách là quản trị viên toàn cầu trên Dataverse Môi trường. Có thể mất vài giờ để điền các thay đổi.

1. Truy cập [Power Apps](https://make.powerapps.com).
1. Chọn môi trường từ bộ chọn môi trường.
1. Đi đến **Các giải pháp**
1. Gỡ cài đặt hoặc xóa giải pháp có tên **Dynamics 365 Customer Insights Bổ trợ Thẻ khách hàng (Xem trước)**.

HOẶC 

1. Mở của bạn Dataverse Môi trường.
1. Đi đến **Cài đặt nâng cao** > **Các giải pháp**.
1. Gỡ cài đặt **CustomerInsightsCustomerCard** giải pháp.

## <a name="copy-the-environment-configuration"></a>Sao chép cấu hình môi trường

Với tư cách là quản trị viên, bạn có thể chọn sao chép cấu hình từ môi trường hiện có khi tạo môi trường mới. 

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

## <a name="set-up-a-copied-environment"></a>Thiết lập môi trường sao chép

Khi bạn sao chép cấu hình môi trường, dữ liệu sau là *không phải* đã sao chép:

- Hồ sơ khách hàng.
- Thông tin xác thực nguồn dữ liệu. Bạn sẽ phải cung cấp thông tin đăng nhập cho mỗi nguồn dữ liệu và làm mới các nguồn dữ liệu theo cách thủ công.
- Nguồn dữ liệu từ thư mục Common Data Model và kho dữ liệu Dataverse được quản lý. Bạn sẽ phải tạo các nguồn dữ liệu đó theo cách thủ công có cùng tên như trong môi trường nguồn.
- Bí mật kết nối được sử dụng để xuất khẩu và làm giàu. Bạn phải xác thực lại các kết nối và sau đó kích hoạt lại tính năng bổ sung và xuất khẩu. 

Khi bạn sao chép một môi trường, bạn sẽ thấy một thông báo xác nhận rằng môi trường mới đã được tạo. Chọn **Chuyển đến nguồn dữ liệu** để xem danh sách các nguồn dữ liệu.

Tất cả nguồn dữ liệu sẽ hiển thị trạng thái **Đã yêu cầu thông tin đăng nhập**. Chỉnh sửa nguồn dữ liệu và nhập thông tin đăng nhập để làm mới những nguồn dữ liệu đó.

:::image type="content" source="media/data-sources-copied.png" alt-text="Danh sách các nguồn dữ liệu đã được sao chép và cần xác thực.":::

Sau khi làm mới nguồn dữ liệu, hãy chuyển đến **Dữ liệu** > **Hợp nhất**. Tại đây, bạn sẽ tìm thấy các thiết đặt từ môi trường nguồn. Chỉnh sửa chúng khi cần hoặc chọn **Chạy** để bắt đầu quá trình hợp nhất dữ liệu và tạo ra thực thể khách hàng hợp nhất.

Khi quá trình hợp nhất dữ liệu hoàn tất, hãy chuyển đến **Biện pháp** và **Phân khúc** để đồng thời làm mới những dữ liệu này.

Trước khi bạn kích hoạt lại tính năng xuất và bổ sung, hãy chuyển đến **quản trị viên** > **Kết nối** để xác thực lại các kết nối trong môi trường mới của bạn.

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

> [!NOTE]
> Xóa một môi trường không xóa liên kết đến một Dataverse môi trường. Tìm hiểu cách [loại bỏ một kết nối hiện có với một Dataverse Môi trường](#remove-an-existing-connection-to-a-dataverse-environment).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
