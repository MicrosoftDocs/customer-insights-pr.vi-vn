---
title: Tạo môi trường trong Customer Insights
description: Các bước để tạo môi trường với đăng ký được cấp phép cho Dynamics 365 Customer Insights.
ms.date: 04/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: c64ac94a7e0e743d3c13e32e394cc5d409420622
ms.sourcegitcommit: c00441bc60b978e25f930b06c9d97b46fe462538
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 05/05/2022
ms.locfileid: "8712928"
---
# <a name="create-an-environment-in-customer-insights"></a>Tạo môi trường trong Thông tin chi tiết về khách hàng

Bài viết này giải thích cách tạo môi trường mới sau khi tổ chức của bạn đã mua gói đăng ký Dynamics 365 Customer Insights. 

Các tổ chức có thể tạo nhiều môi trường cho mọi giấy phép Thông tin chi tiết về khách hàng. Nếu tổ chức của bạn mua nhiều giấy phép, [liên hệ với nhóm hỗ trợ của chúng tôi](https://go.microsoft.com/fwlink/?linkid=2079641) để tăng số lượng môi trường có sẵn. Để biết thêm thông tin về dung lượng và dung lượng bổ sung, hãy xem lại [Hướng dẫn cấp phép Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

> [!NOTE]
> Nếu bạn đang muốn dùng thử dịch vụ, hãy xem [Thiết lập môi trường dùng thử](trial-signup.md).

## <a name="create-a-new-environment"></a>Tạo môi trường mới

Sau khi mua giấy phép đăng ký cho Customer Insights, quản trị viên toàn cầu của Microsoft 365 người thuê nhận được một email mời họ tạo môi trường. Đi tới [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start) để bắt đầu. 

Trải nghiệm có hướng dẫn giúp bạn thực hiện các bước để thu thập tất cả thông tin cần thiết cho một môi trường mới. Bạn cần [quyền quản trị viên](permissions.md) trong Thông tin chi tiết về khách hàng để tạo hoặc quản lý môi trường.

1. Mở bộ chọn môi trường và chọn **+ Mới**.
  
   :::image type="content" source="media/environment-picker.png" alt-text="Chọn bộ chọn môi trường.":::

1. Thực hiện theo kinh nghiệm được hướng dẫn được nêu trong các phần sau.

### <a name="step-1-provide-environment-information"></a>Bước 1: Cung cấp thông tin môi trường

Trong bước **Thông tin cơ bản**, chọn xem bạn muốn tạo một môi trường từ đầu hay [sao chép dữ liệu từ môi trường khác](manage-environments.md#copy-the-environment-configuration).

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Hộp thoại để tạo môi trường Customer Insights mới.":::

Cung cấp các chi tiết sau đây:
   - **Tên**: Tên cho môi trường này. Trường này đã được điền nếu bạn sao chép một môi trường hiện có, nhưng bạn có thể thay đổi trường này.
   - **Chọn doanh nghiệp của bạn**: Chọn đối tượng chính cho môi trường mới. Bạn có thể làm việc với người tiêu dùng cá nhân (B2C) hoặc [tài khoản kinh doanh](work-with-business-accounts.md) (B2B).
   - **Loại**: Chọn xem bạn muốn tạo môi trường sản xuất hay hộp cát. Môi trường hộp cát không cho phép làm mới dữ liệu theo lịch trình và dành cho việc triển khai và thử nghiệm trước. Môi trường hộp cát sử dụng cùng một đối tượng chính như môi trường sản xuất hiện được chọn.
   - **Vùng**: Vùng triển khai và lưu trư dịch vụ.

### <a name="step-2-configure-data-storage"></a>Bước 2: Đặt cấu hình lưu trữ dữ liệu

Bên trong **Lưu trữ dữ liệu** chọn nơi lưu trữ dữ liệu Thông tin chi tiết về khách hàng.

Bạn sẽ có hai lựa chọn: **Bộ nhớ Customer Insights** (một kho dữ liệu Azure do nhóm Customer Insights quản lý) và **Azure Data Lake Storage** (Azure Data Lake Storage của riêng bạn). Tùy chọn mặc định là lưu trữ trong Customer Insights.

:::image type="content" source="media/data-storage-environment.png" alt-text="Chọn Azure Data Lake Storage để lưu trữ dữ liệu của bạn.":::

Bằng cách lưu dữ liệu vào Azure Data Lake Storage, bạn đồng ý rằng dữ liệu sẽ được chuyển đến và lưu trữ ở vị trí địa lý thích hợp cho tài khoản lưu trữ Azure đó. Vị trí này có thể khác với nơi dữ liệu được lưu trữ trong Dynamics 365 Customer Insights. Hãy tìm hiểu thêm tại [Trung tâm tin cậy Microsoft](https://www.microsoft.com/trust-center).

> [!NOTE]
> Customer Insights hiện hỗ trợ:  
> - Tài khoản Azure Data Lake Storage từ cùng một vùng Azure mà bạn đã chọn khi tạo môi trường.
> - Azure Data Lake Storage tài khoản Gen2 và có *không gian tên phân cấp* đã được kích hoạt. Tài khoản lưu trữ Azure Data Lake Gen1 không được hỗ trợ.

Đối với tùy chọn Azure Data Lake Storage, bạn có thể chọn giữa tùy chọn dựa trên nguồn lực và tùy chọn dựa trên đăng ký để xác thực. Để biết thêm thông tin, hãy xem [Kết nối với một tài khoản Azure Data Lake Storage bằng cách sử dụng một dịch vụ Azure chính](connect-service-principal.md). Một vùng chứa có tên`customerinsights` phải tồn tại trên tài khoản lưu trữ.

Khi quá trình hệ thống như nhập dữ liệu hoàn tất, hệ thống sẽ tạo các thư mục tương ứng trong tài khoản lưu trữ mà bạn đã chỉ định. Tệp dữ liệu và tệp *model.json* được tạo và thêm vào các thư mục dựa trên tên quy trình.

Nếu bạn tạo nhiều môi trường Customer Insights và chọn lưu các thực thể đầu ra từ các môi trường đó vào tài khoản lưu trữ của mình, thì Customer Insights sẽ tạo các thư mục riêng biệt cho từng môi trường với `ci_environmentID` trong bộ chứa.

### <a name="step-3-connect-to-microsoft-dataverse"></a>Bước 3: Kết nối với Microsoft Dataverse
   
Bước **Microsoft Dataverse** cho phép bạn kết nối Customer Insights với môi trường Dataverse.

Cung cấp của riêng bạn Microsoft Dataverse môi trường để chia sẻ dữ liệu (hồ sơ và thông tin chi tiết) với các ứng dụng kinh doanh dựa trên Dataverse, như Dynamics 365 Marketing hoặc các ứng dụng theo hướng mô hình trong Power Apps. Để trống trường này nếu bạn không có Dataverse môi trường và chúng tôi sẽ cung cấp một môi trường cho bạn.

Đang kết nối với của bạn Dataverse môi trường cũng cho phép bạn [nhập dữ liệu từ tại chỗ nguồn dữ liệu bằng cách sử dụng Power Platform luồng dữ liệu và các cổng](data-sources.md#add-data-from-on-premises-data-sources).

> [!IMPORTANT]
> 1. Thông tin chi tiết về khách hàng và Dataverse phải ở trong cùng một khu vực để cho phép chia sẻ dữ liệu.
> 1. Bạn phải có vai trò quản trị viên toàn cầu trong Dataverse môi trường. Xác minh nếu điều này [Dataverse môi trường được liên kết](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) vào các nhóm bảo mật nhất định và đảm bảo rằng bạn được thêm vào các nhóm bảo mật đó.
> 1. Không có môi trường Thông tin chi tiết về khách hàng hiện tại nào được liên kết với môi trường đó Dataverse môi trường. Học cách [loại bỏ một kết nối hiện có với một Dataverse môi trường](manage-environments.md#remove-an-existing-connection-to-a-dataverse-environment).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="chia sẻ dữ liệu với Microsoft Dataverse tự động bật cho các phiên bản mới thuần.":::

Để biết thêm thông tin về cách bật chia sẻ dữ liệu với Microsoft Dataverse từ của riêng bạn Azure Data Lake Storage, xem [Kết nối với Microsoft Dataverse](manage-environments.md#connect-to-microsoft-dataverse).

Customer Insights không hỗ trợ các tình huống chia sẻ dữ liệu sau:
- Nếu bạn bật chia sẻ dữ liệu với Dataverse, bạn sẽ không thể [tạo các giá trị được dự đoán hoặc bị thiếu trong một thực thể](predictions.md).

### <a name="step-4-finalize-the-settings"></a>Bước 4: Hoàn tất thiết đặt

Trong bước **Đánh giá**, xem tất cả thiết đặt đã được chỉ định. Khi mọi thứ đã hoàn tất, hãy chọn **Tạo** để thiết lập môi trường. 

Bạn cũng có thể thay đổi hầu hết các thiết đặt sau này. Để biết thêm thông tin, hãy xem [Quản lý môi trường](manage-environments.md).

## <a name="work-with-your-new-environment"></a>Làm việc với môi trường mới của bạn

Xem lại các bài viết sau để giúp bạn bắt đầu định cấu hình Customer Insights: 

- [Thêm người dùng khác và gán quyền](permissions.md).
- [Nhập các nguồn dữ liệu của bạn](data-sources.md) và chạy chúng thông qua [quá trình hợp nhất dữ liệu](data-unification.md) để có được [hồ sơ khách hàng hợp nhất](customer-profiles.md).
- [Tăng cường hồ sơ khách hàng hợp nhất](enrichment-hub.md) hoặc [chạy các mô hình dự đoán](predictions-overview.md).
- [Tạo phân khúc](segments.md) để nhóm khách hàng và [giá trị đo](measures.md) để xem lại KPI.
- [Thiết lập kết nối](connections.md) và [xuất](export-destinations.md) để xử lý tập hợp con của dữ liệu trong các ứng dụng khác.
