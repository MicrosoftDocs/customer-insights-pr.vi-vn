---
title: Cách thực hiện - Tạo môi trường mới
description: Các bước tạo môi trường với for Dynamics 365 Customer Insights.
ms.date: 05/31/2022
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
ms.openlocfilehash: 6dfaa09cd80498e9a4e4dea6a07ce6e9d29105e2
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011637"
---
# <a name="how-to-create-a-new-environment"></a>Cách thực hiện: Tạo môi trường mới

Sau [mua giấy phép đăng ký cho Dynamics 365 Customer Insights](paid-license.md), quản trị viên toàn cầu của Microsoft 365 người thuê nhận được một email mời họ tạo môi trường. Đi tới [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start) để bắt đầu. Trong trường hợp này, bạn có thể truy cập trực tiếp vào [Bước 1: Cung cấp thông tin cơ bản](#step-1-provide-basic-information).

Sau khi môi trường đầu tiên được tạo, quản trị viên toàn cầu của Microsoft 365 người thuê có thể [thêm người dùng hình thành tổ chức của họ với tư cách là quản trị viên](permissions.md). Về sau, những quản trị viên này có thể quản lý người dùng và môi trường. Nếu tổ chức của bạn mua nhiều giấy phép cho Thông tin chi tiết về khách hàng, [liên hệ với nhóm hỗ trợ của chúng tôi](https://go.microsoft.com/fwlink/?linkid=2079641) để tăng số lượng môi trường có sẵn. Để biết thêm thông tin về dung lượng và dung lượng bổ sung, hãy xem lại [Hướng dẫn cấp phép Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

> [!TIP]
> Nếu bạn đang muốn dùng thử dịch vụ, hãy xem [Thiết lập môi trường dùng thử](trial-signup.md).

## <a name="prerequisites"></a>Điều kiện tiên quyết

Bạn cần [quyền quản trị viên](permissions.md) trong Thông tin chi tiết về khách hàng để tạo hoặc quản lý môi trường.

## <a name="start-the-environment-creation-process"></a>Bắt đầu quá trình tạo môi trường

1. Mở bộ chọn môi trường và chọn **+ Mới**.
  
   :::image type="content" source="media/environment-picker.png" alt-text="Chọn bộ chọn môi trường.":::

1. Thực hiện theo kinh nghiệm được hướng dẫn được nêu trong các phần sau để cung cấp tất cả thông tin cần thiết cho một môi trường mới. Nếu bạn đã định cấu hình một môi trường trước đó, bạn cũng có thể [sao chép cấu hình](#copy-the-environment-configuration).

## <a name="step-1-provide-basic-information"></a>Bước 1: Cung cấp thông tin cơ bản

Trong bước **Thông tin cơ bản**, chọn xem bạn muốn tạo một môi trường từ đầu hay [sao chép dữ liệu từ môi trường khác](#copy-the-environment-configuration).

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Hộp thoại để tạo môi trường Customer Insights mới.":::

Cung cấp các chi tiết sau đây:

- **Tên**: Tên cho môi trường này. Trường này đã được điền nếu bạn sao chép một môi trường hiện có, nhưng bạn có thể thay đổi trường này.
- **Chọn doanh nghiệp của bạn**: Chọn đối tượng chính cho môi trường mới. Bạn có thể làm việc với người tiêu dùng cá nhân (B2C) hoặc [tài khoản kinh doanh](work-with-business-accounts.md) (B2B). Nếu tổ chức của bạn chủ yếu kinh doanh với các cá nhân, chẳng hạn như cửa hàng bán lẻ hoặc quán cà phê, hãy chọn người tiêu dùng cá nhân. Trong trường hợp đối tượng chính của bạn là các công ty khác, chẳng hạn như nhà sản xuất ô tô hoặc công ty giấy, hãy chọn tài khoản doanh nghiệp.
- **Loại**: Chọn xem bạn muốn tạo môi trường sản xuất hay hộp cát. Môi trường hộp cát không cho phép làm mới dữ liệu theo lịch trình và dành cho việc triển khai và thử nghiệm trước. Môi trường hộp cát sử dụng cùng một đối tượng chính như môi trường sản xuất hiện được chọn.
- **Vùng**: Vùng triển khai và lưu trư dịch vụ. Đến [Tự dùng cái của bạn đi Azure Data Lake Storage tài khoản](own-data-lake-storage.md) hoặc [kết nối với một hiện tại Microsoft Dataverse cơ quan](customer-insights-dataverse.md), môi trường Thông tin chi tiết về khách hàng phải trong cùng một khu vực.

## <a name="step-2-configure-data-storage"></a>Bước 2: Đặt cấu hình lưu trữ dữ liệu

Bên trong **Lưu trữ dữ liệu** chọn nơi lưu trữ dữ liệu Thông tin chi tiết về khách hàng.

Có hai tùy chọn bạn có thể chọn:

- **Lưu trữ thông tin chi tiết về khách hàng** : Bộ nhớ dữ liệu do nhóm Thông tin chi tiết về khách hàng quản lý. Đây là tùy chọn mặc định và trừ khi có các yêu cầu cụ thể để lưu trữ dữ liệu trong tài khoản lưu trữ của riêng bạn, chúng tôi khuyên bạn nên sử dụng tùy chọn này.
- **Azure Data Lake Storage**: Chỉ định của riêng bạn Azure Data Lake Storage tài khoản để lưu trữ dữ liệu để bạn có toàn quyền kiểm soát nơi dữ liệu được lưu trữ. Để biết thêm thông tin, hãy xem [Tự dùng cái của bạn đi Azure Data Lake Storage tài khoản](own-data-lake-storage.md).

:::image type="content" source="media/data-storage-environment.png" alt-text="Chọn tùy chọn ưu tiên để lưu trữ dữ liệu của bạn.":::

## <a name="step-3-connect-to-microsoft-dataverse"></a>Bước 3: Kết nối với Microsoft Dataverse

Bước **Microsoft Dataverse** cho phép bạn kết nối Customer Insights với môi trường Dataverse. Chia sẻ dữ liệu với Dataverse để sử dụng nó với các ứng dụng kinh doanh dựa trên Dataverse, như Dynamics 365 Marketing hoặc các ứng dụng theo hướng mô hình trong Power Apps.


Để trống trường này nếu bạn không có Dataverse môi trường và chúng tôi sẽ tạo một môi trường cho bạn.

Để biết thêm thông tin, hãy xem [Làm việc với dữ liệu Thông tin chi tiết về khách hàng trong Microsoft Dataverse](customer-insights-dataverse.md).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="chia sẻ dữ liệu với Microsoft Dataverse tự động bật cho môi trường mới thuần.":::

### <a name="step-4-finalize-the-settings"></a>Bước 4: Hoàn tất thiết đặt

Bên trong **Kiểm tra lại** đi qua tất cả các cài đặt được chỉ định. Khi mọi thứ đã hoàn tất, hãy chọn **Tạo** để thiết lập môi trường.

Bạn có thể thay đổi một số cài đặt sau. Để biết thêm thông tin, hãy xem [Quản lý môi trường](manage-environments.md).

## <a name="work-with-your-new-environment"></a>Làm việc với môi trường mới của bạn

Xem lại các bài viết sau để giúp bạn bắt đầu định cấu hình Customer Insights:

- [Thêm người dùng khác và gán quyền](permissions.md).
- [Nhập các nguồn dữ liệu của bạn](data-sources.md) và chạy chúng thông qua [quá trình hợp nhất dữ liệu](data-unification.md) để có được [hồ sơ khách hàng hợp nhất](customer-profiles.md).
- [Tăng cường hồ sơ khách hàng hợp nhất](enrichment-hub.md) hoặc [chạy các mô hình dự đoán](predictions-overview.md).
- [Tạo phân khúc](segments.md) để nhóm khách hàng và [giá trị đo](measures.md) để xem lại KPI.
- [Thiết lập kết nối](connections.md) và [xuất](export-destinations.md) để xử lý tập hợp con của dữ liệu trong các ứng dụng khác.

## <a name="copy-the-environment-configuration"></a>Sao chép cấu hình môi trường

Với tư cách là quản trị viên, bạn có thể chọn sao chép cấu hình từ môi trường hiện có khi tạo môi trường mới.

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Ảnh chụp màn hình của các tùy chọn cài đặt trong cài đặt môi trường.":::

Bạn sẽ nhìn thấy danh sách tất cả các môi trường có sẵn trong tổ chức, nơi bạn có thể sao chép dữ liệu từ đó.

Các thiết đặt cấu hình sau được sao chép:

- Nguồn dữ liệu được nhập qua Power Query
- Cấu hình hợp nhất dữ liệu
- Phân khúc
- Measures
- Quan hệ
- Hoạt động
- Chỉ mục tìm kiếm và lọc
- Nội dung xuất
- Làm mới lịch biểu
- Nội dung tăng cường
- Dự đoán người mẫu
- Chỉ định vai trò

## <a name="set-up-a-copied-environment"></a>Thiết lập môi trường sao chép

Khi bạn sao chép cấu hình môi trường, bạn phải trải qua một số bước bổ sung để xác nhận thông tin đăng nhập:

- Hồ sơ khách hàng. Đầu tiên, xác thực và nhập các nguồn dữ liệu của bạn và chạy hợp nhất dữ liệu để tạo lại hồ sơ khách hàng.
- Thông tin xác thực nguồn dữ liệu. Bạn phải cung cấp thông tin đăng nhập cho mỗi nguồn dữ liệu để xác thực và làm mới nguồn dữ liệu theo cách thủ công.
- Nguồn dữ liệu từ thư mục Mô hình Dữ liệu Chung và Dataverse. Bạn phải tạo các nguồn dữ liệu đó theo cách thủ công với cùng tên như trong môi trường nguồn.
- Bí mật kết nối được sử dụng để xuất khẩu và làm giàu. Bạn phải xác thực lại các kết nối và sau đó kích hoạt lại tính năng bổ sung và xuất khẩu.

Bạn sẽ thấy thông báo xác nhận khi môi trường sao chép đã được tạo. Chọn **Chuyển đến nguồn dữ liệu** để xem danh sách các nguồn dữ liệu.

Tất cả nguồn dữ liệu sẽ hiển thị trạng thái **Đã yêu cầu thông tin đăng nhập**. Chỉnh sửa nguồn dữ liệu và nhập thông tin đăng nhập để làm mới những nguồn dữ liệu đó.

:::image type="content" source="media/data-sources-copied.png" alt-text="Danh sách các nguồn dữ liệu đã được sao chép và cần xác thực.":::

Sau khi làm mới nguồn dữ liệu, hãy chuyển đến **Dữ liệu** > **Hợp nhất**. Tại đây, bạn sẽ tìm thấy các thiết đặt từ môi trường nguồn. Chỉnh sửa chúng khi cần hoặc chọn **Chạy** để bắt đầu quá trình hợp nhất dữ liệu và tạo ra thực thể khách hàng hợp nhất.

Khi quá trình hợp nhất dữ liệu hoàn tất, hãy chuyển đến **Biện pháp** và **Phân khúc** để đồng thời làm mới những dữ liệu này.

Trước khi bạn kích hoạt lại tính năng xuất và bổ sung, hãy chuyển đến **Quản trị viên** > **Kết nối** để xác thực lại các kết nối trong môi trường mới của bạn.

[!INCLUDE [footer-include](includes/footer-banner.md)]
