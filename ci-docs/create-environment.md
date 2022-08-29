---
title: Tạo môi trường mới
description: Các bước tạo môi trường trong Dynamics 365 Customer Insights.
ms.date: 08/15/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: 0a45e2fd2bdb7b85883a536f8b42ee650e54db7e
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304299"
---
# <a name="create-a-new-environment"></a>Tạo môi trường mới

Sau [mua giấy phép đăng ký cho Dynamics 365 Customer Insights](paid-license.md), quản trị viên toàn cầu của Microsoft 365 người thuê nhận được một email mời họ tạo môi trường. Đi tới [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start) để bắt đầu. Trong trường hợp này, hãy bắt đầu với [Bước 1: Cung cấp thông tin cơ bản](#step-1-provide-basic-information).

Sau khi môi trường đầu tiên được tạo, quản trị viên toàn cầu của Microsoft 365 người thuê có thể [thêm người dùng từ tổ chức của họ làm quản trị viên](permissions.md). Các quản trị viên này sau đó có thể quản lý người dùng và môi trường. Nếu tổ chức của bạn mua nhiều giấy phép cho Thông tin chi tiết về khách hàng, [liên hệ với nhóm hỗ trợ của chúng tôi](https://go.microsoft.com/fwlink/?linkid=2079641) để tăng số lượng môi trường có sẵn. Để biết thêm thông tin về dung lượng và dung lượng bổ sung, hãy xem lại [Hướng dẫn cấp phép Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544). Khi bạn có khả năng tạo môi trường bổ sung, hãy chuyển đến [Bắt đầu quá trình tạo môi trường](#start-the-environment-creation-process).

> [!TIP]
> Nếu bạn đang muốn dùng thử dịch vụ, hãy xem [Thiết lập môi trường dùng thử](trial-signup.md).

## <a name="prerequisites"></a>Điều kiện tiên quyết

[Quyền của quản trị viên](permissions.md) trong Thông tin chi tiết về khách hàng

## <a name="start-the-environment-creation-process"></a>Bắt đầu quá trình tạo môi trường

1. Mở bộ chọn môi trường và chọn **+ Mới**.
  
   :::image type="content" source="media/environment-picker.png" alt-text="Chọn bộ chọn môi trường.":::

1. Thực hiện theo kinh nghiệm được hướng dẫn được nêu trong các phần sau để cung cấp tất cả thông tin cần thiết cho một môi trường mới.

## <a name="step-1-provide-basic-information"></a>Bước 1: Cung cấp thông tin cơ bản

1. Chọn xem bạn muốn tạo môi trường từ đầu hay sao chép dữ liệu từ môi trường khác. [Sao chép dữ liệu từ môi trường khác](#copy-the-environment-configuration) yêu cầu các bước bổ sung.

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Hộp thoại để tạo môi trường Customer Insights mới.":::

1. Cung cấp các chi tiết sau đây:

   - **Tên** : Đặt tên cho môi trường này. Trường này đã được điền nếu bạn sao chép một môi trường hiện có, nhưng bạn có thể thay đổi trường này.
   - **Chọn doanh nghiệp của bạn** : Đối tượng chính cho môi trường mới: người tiêu dùng cá nhân (B-to-C) hoặc [tài khoản kinh doanh](work-with-business-accounts.md) (B-to-B). Nếu tổ chức của bạn chủ yếu kinh doanh với các cá nhân, chẳng hạn như cửa hàng bán lẻ hoặc quán cà phê, hãy chọn người tiêu dùng cá nhân. Nếu đối tượng chính của bạn là các công ty khác, chẳng hạn như nhà sản xuất ô tô hoặc công ty giấy, hãy chọn tài khoản doanh nghiệp.
   - **Loại hình** Loại môi trường: sản xuất hoặc hộp cát. Môi trường hộp cát không cho phép làm mới dữ liệu theo lịch trình và dành cho việc triển khai và thử nghiệm trước. Môi trường hộp cát sử dụng cùng một đối tượng chính như môi trường sản xuất hiện được chọn.
   - **Vùng đất** : Khu vực mà dịch vụ được triển khai và lưu trữ. Đến [Tự dùng cái của bạn đi Azure Data Lake Storage tài khoản](own-data-lake-storage.md) hoặc [kết nối với một hiện tại Microsoft Dataverse cơ quan](customer-insights-dataverse.md), môi trường Thông tin chi tiết về khách hàng phải trong cùng một khu vực.

1. Chọn **Tiếp theo**.

## <a name="step-2-configure-data-storage"></a>Bước 2: Đặt cấu hình lưu trữ dữ liệu

1. Chọn nơi lưu trữ dữ liệu Thông tin chi tiết về khách hàng:

   - **Lưu trữ thông tin chi tiết về khách hàng** : Lưu trữ dữ liệu được quản lý tự động. Đây là tùy chọn mặc định và trừ khi có các yêu cầu cụ thể để lưu trữ dữ liệu trong tài khoản lưu trữ của riêng bạn, chúng tôi khuyên bạn nên sử dụng tùy chọn này.
   - **Azure Data Lake Storage**: Của riêng bạn Azure Data Lake Storage tài khoản để lưu trữ dữ liệu để bạn có toàn quyền kiểm soát nơi dữ liệu được lưu trữ. Làm theo các bước trong [Tự dùng cái của bạn đi Azure Data Lake Storage tài khoản](own-data-lake-storage.md).

   :::image type="content" source="media/data-storage-environment.png" alt-text="Chọn tùy chọn ưa thích để lưu trữ dữ liệu của bạn.":::

1. Chọn **Tiếp theo**.

## <a name="step-3-connect-to-microsoft-dataverse"></a>Bước 3: Kết nối với Microsoft Dataverse

Nếu bạn có một Dataverse môi trường, kết nối Thông tin chi tiết về khách hàng. Chia sẻ dữ liệu với Dataverse để sử dụng nó với các ứng dụng kinh doanh dựa trên Dataverse, như Dynamics 365 Marketing hoặc các ứng dụng theo hướng mô hình trong Power Apps.

1. Làm theo các bước trong [Làm việc với dữ liệu Thông tin chi tiết về khách hàng trong Microsoft Dataverse](customer-insights-dataverse.md).

   :::image type="content" source="media/dataverse-provisioning.png" alt-text="chia sẻ dữ liệu với Microsoft Dataverse tự động bật cho môi trường mới thuần.":::

1. Chọn **Tiếp theo**.

## <a name="step-4-finalize-the-settings"></a>Bước 4: Hoàn tất thiết đặt

Xem lại các cài đặt đã chỉ định. Khi mọi thứ đã hoàn tất, hãy chọn **Tạo** để thiết lập môi trường.

Để thay đổi một số cài đặt sau này, hãy xem [Quản lý môi trường](manage-environments.md).

## <a name="work-with-your-new-environment"></a>Làm việc với môi trường mới của bạn

Xem lại các bài viết sau để giúp bạn bắt đầu định cấu hình Customer Insights:

- [Thêm người dùng khác và gán quyền](permissions.md).
- [Nhập các nguồn dữ liệu của bạn](data-sources.md) và chạy chúng thông qua [quá trình hợp nhất dữ liệu](data-unification.md) để có được [hồ sơ khách hàng hợp nhất](customer-profiles.md).
- [Tăng cường hồ sơ khách hàng hợp nhất](enrichment-hub.md) hoặc [chạy các mô hình dự đoán](predictions-overview.md).
- [Tạo phân khúc](segments.md) để nhóm khách hàng và [giá trị đo](measures.md) để xem lại KPI.
- [Thiết lập kết nối](connections.md) và [xuất](export-destinations.md) để xử lý tập hợp con của dữ liệu trong các ứng dụng khác.

## <a name="copy-the-environment-configuration"></a>Sao chép cấu hình môi trường

Với tư cách là quản trị viên, nếu bạn chọn sao chép cấu hình từ môi trường hiện có, hãy chọn từ danh sách tất cả các môi trường có sẵn trong tổ chức của bạn.

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Ảnh chụp màn hình của các tùy chọn cài đặt trong cài đặt môi trường.":::

Các thiết đặt cấu hình sau được sao chép:

- Nguồn dữ liệu được nhập qua Power Query
- Cấu hình hợp nhất dữ liệu
- Phân khúc
- Measures
- Quan hệ
- Hoạt động
- Chỉ mục tìm kiếm và lọc
- Nội dung xuất
- Làm mới lịch trình
- Nội dung tăng cường
- Dự đoán người mẫu
- Chỉ định vai trò

### <a name="set-up-a-copied-environment"></a>Thiết lập môi trường sao chép

Khi bạn sao chép cấu hình môi trường, một thông báo xác nhận sẽ hiển thị khi môi trường sao chép đã được tạo. Thực hiện các bước sau để xác nhận thông tin đăng nhập.

1. Chọn **Chuyển đến nguồn dữ liệu** để xem danh sách các nguồn dữ liệu. Tất cả các nguồn dữ liệu hiển thị **Yêu cầu thông tin xác thực** trạng thái.

   :::image type="content" source="media/data-sources-copied.png" alt-text="Danh sách các nguồn dữ liệu đã được sao chép và cần xác thực.":::

1. Chỉnh sửa nguồn dữ liệu và nhập thông tin đăng nhập để làm mới những nguồn dữ liệu đó. Nguồn dữ liệu từ thư mục Mô hình Dữ liệu Chung và Dataverse phải được tạo thủ công với tên giống như trong môi trường nguồn.

1. Sau khi làm mới nguồn dữ liệu, hãy chuyển đến **Dữ liệu** > **Hợp nhất**. Tại đây, bạn sẽ tìm thấy các thiết đặt từ môi trường nguồn. Chỉnh sửa chúng nếu cần hoặc chọn **Thống nhất** > **Hợp nhất hồ sơ khách hàng và sự phụ thuộc** để bắt đầu quá trình hợp nhất dữ liệu và tạo thực thể khách hàng hợp nhất.

   > [!TIP]
   > Đối với tài khoản và danh bạ, hãy chọn **Hợp nhất các tài khoản** > **Hợp nhất hồ sơ và phụ thuộc**.

1. Khi quá trình hợp nhất dữ liệu hoàn tất, hãy chuyển đến **Đo** và **Phân đoạn** để làm mới chúng.

1. Đi đến **Quản trị viên** > **Kết nối** để xác thực lại các kết nối trong môi trường mới của bạn.

1. Đi đến **Dữ liệu** > **Làm giàu** và **Dữ liệu** > **Xuất khẩu** để kích hoạt lại chúng.

[!INCLUDE [footer-include](includes/footer-banner.md)]
