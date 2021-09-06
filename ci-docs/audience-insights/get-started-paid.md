---
title: Tạo và đặt cấu hình giấy phép trả phí của Customer Insights
description: Các bước để nhận đăng ký có giấy phép cho Dynamics 365 Customer Insights và đặt cấu hình.
ms.date: 07/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: b5f76f4c468b88aaf7037dbd2ee3bed449fbeaa5f645d52278eee05b36b4e328
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034478"
---
# <a name="get-started-with-a-paid-subscription"></a>Bắt đầu với gói đăng ký trả phí

Bài viết này giải thích cách tạo môi trường mới sau khi tổ chức của bạn đã mua gói đăng ký Dynamics 365 Customer Insights. Nếu bạn muốn mua Customer Insights, các tùy chọn liên hệ của chúng tôi được liệt kê trên trang web [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/). 

Nếu bạn đang muốn dùng thử dịch vụ và các tính năng, hãy xem [Thiết lập môi trường dùng thử](get-started-trial.md).

## <a name="create-an-environment-in-an-existing-organization"></a>Tạo môi trường trong tổ chức hiện có

Sau khi mua giấy phép đăng ký cho Customer Insights, quản trị viên toàn cầu của đối tượng thuê Microsoft 365 sẽ nhận được email mời họ tạo môi trường. Đi tới [https://home.ci.dynamics.com/start](https://home.ci.dynamics.com/start) để bắt đầu. 

Customer Insights không được cấp phép cho mỗi người dùng, vì vậy nó sẽ không hiển thị trong khu vực Giấy phép. Nếu bạn đang tìm kiếm giấy phép trong trung tâm quản trị Microsoft 365, hãy truy cập **Sản phẩm của bạn**. 

> [!NOTE]
> Các tổ chức có thể tạo *hai* môi trường cho mọi giấy phép Customer Insights. Nếu tổ chức của bạn mua nhiều giấy phép, vui lòng [liên hệ với nhóm hỗ trợ của chúng tôi](https://go.microsoft.com/fwlink/?linkid=2079641) để tăng số lượng môi trường khả dụng. Để biết thêm thông tin về năng lực và năng lực bổ trợ, hãy tải xuống [Hướng dẫn cấp phép Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

Để tạo môi trường:

1. Trong hộp thoại **Tạo môi trường**, chọn **Môi trường mới**.

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Hộp thoại để tạo môi trường Customer Insights mới.":::

   Chúng tôi khuyên bạn nên bắt đầu thiết lập môi trường từ đầu. Tuy nhiên, nếu bạn là quản trị viên hoặc thành viên của môi trường dùng thử, bạn có thể [sao chép dữ liệu từ một môi trường khác](manage-environments.md#copy-the-environment-configuration), bằng cách chọn **Sao chép từ môi trường hiện có**. Bạn sẽ nhìn thấy danh sách tất cả các môi trường có sẵn trong tổ chức, nơi bạn có thể sao chép dữ liệu từ đó.

1. Cung cấp các chi tiết sau đây:
   - **Tên**: Tên cho môi trường này. Trường này đã được điền nếu bạn sao chép một môi trường hiện có, nhưng bạn có thể thay đổi trường này.
   - **Vùng**: Vùng triển khai và lưu trư dịch vụ.
   - **Loại**: Chọn xem bạn muốn tạo môi trường sản xuất hay hộp cát. Môi trường hộp cát không cho phép làm mới dữ liệu theo lịch trình và dành cho việc triển khai và thử nghiệm trước.
   
1. Bạn có thể chọn **Thiết đặt nâng cao**:

   - **Lưu tất cả dữ liệu vào**: Chỉ định nơi bạn muốn lưu trữ dữ liệu đầu ra được tạo từ Customer Insights. Bạn sẽ có hai lựa chọn: **Bộ nhớ Customer Insights** (một Azure Data Lake do nhóm Customer Insights quản lý) và **Azure Data Lake Storage** (Azure Data Lake Storage của riêng bạn). Tùy chọn mặc định là lưu trữ trong Customer Insights.

     > [!NOTE]
     > Bằng việc lưu dữ liệu vào Azure Data Lake Storage, bạn đồng ý rằng dữ liệu sẽ được chuyển sang và lưu trữ tại vị trí địa lý phù hợp cho tài khoản Azure Storage đó. Vị trí này có thể khác với nơi lưu trữ dữ liệu trong Dynamics 365 Customer Insights. [Hãy tìm hiểu thêm tại Trung tâm tin cậy Microsoft.](https://www.microsoft.com/trust-center)
     >
     > Hiện tại, các thực thể đã thu nạp từ dòng dữ liệu Power BI được lưu trữ trong Microsoft Dataverse Managed Data Lake. 
     > 
     > Chúng tôi chỉ hỗ trợ Azure Data Lake Storage tài khoản từ cùng một vùng Azure mà bạn đã chọn khi tạo môi trường. 
     > 
     > Chúng tôi chỉ hỗ trợ tài khoản Azure Data Lake Storage đã bật tính năng không gian tên theo cấp bậc.


   - Đối với tùy chọn Azure Data Lake Storage, bạn có thể chọn giữa tùy chọn dựa trên nguồn lực và tùy chọn dựa trên đăng ký để xác thực. Để biết thêm thông tin, hãy xem [Kết nối thông tin chuyên sâu về đối tượng với tài khoản Azure Data Lake Storage Gen2 có dịch vụ chính Azure](connect-service-principal.md). Tên **Vùng chứa** không thể thay đổi và mặc định là `customerinsights`.
   
   - Nếu bạn muốn sử dụng [mô hình sẵn dùng](predictions-overview.md#out-of-box-models), hãy định cấu hình tính năng chia sẻ dữ liệu với Microsoft Dataverse hoặc cho phép nhập dữ liệu từ nguồn dữ liệu tại chỗ, cung cấp URL môi trường Microsoft Dataverse trong mục **Định cấu hình chia sẻ dữ liệu với Microsoft Dataverse và cho phép các nguồn lực bổ sung**. Chọn **Bật chia sẻ dữ liệu** để chia sẻ dữ liệu đầu ra của Customer Insights với Microsoft Dataverse Managed Data Lake.

     > [!NOTE]
     > - Chia sẻ dữ liệu với Microsoft Dataverse Managed Data Lake hiện không được hỗ trợ khi bạn lưu tất cả dữ liệu vào Azure Data Lake Storage của riêng mình.
     > - [Dự đoán giá trị bị thiếu trong một thực thể](predictions.md) hiện không được hỗ trợ khi bạn bật tính năng chia sẻ dữ liệu với dịch vụ Microsoft Dataverse Managed Data Lake.

     :::image type="content" source="media/Datasharing-with-DataverseMDL.png" alt-text="Các tùy chọn cấu hình để bật tính năng chia sẻ dữ liệu với Microsoft Dataverse.":::

   Khi các quy trình hệ thống như nhập dữ liệu hoàn tất, hệ thống sẽ tạo các thư mục tương ứng trong tài khoản lưu trữ mà bạn đã chỉ định. Tệp dữ liệu và tệp model.json được tạo và thêm vào các thư mục dựa trên tên quy trình.

   Nếu bạn tạo nhiều môi trường Customer Insights và chọn lưu các thực thể đầu ra từ các môi trường đó trong tài khoản lưu trữ của mình, các thư mục riêng biệt sẽ được tạo cho từng môi trường với ci_<environmentid> trong vùng chứa.

1. Chọn **Tạo** để thiết lập môi trường. 

## <a name="configure-an-environment"></a>Định cấu hình môi trường

Xem lại các bài viết sau để giúp bạn bắt đầu đặt cấu hình Customer Insights. 

- [Thêm người dùng khác và gán quyền](permissions.md).
- [Nhập các nguồn dữ liệu của bạn](data-sources.md) và chạy chúng thông qua [quá trình hợp nhất dữ liệu](data-unification.md) để có được [hồ sơ khách hàng hợp nhất](customer-profiles.md).
- [Tăng cường hồ sơ khách hàng hợp nhất](enrichment-hub.md) hoặc [chạy các mô hình dự đoán](predictions-overview.md).
- Tạo [phân khúc](segments.md) để nhóm khách hàng và [số liệu đo lường](measures.md) đánh giá KPI.
- Thiết lập [kết nối](connections.md) và [xuất](export-destinations.md) để xử lý tập hợp con của dữ liệu trong các ứng dụng khác.
