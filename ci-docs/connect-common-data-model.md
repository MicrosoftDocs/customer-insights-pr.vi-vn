---
title: Kết nối với thư mục Common Data Model sử dụng tài khoản Azure Data Lake
description: Làm việc với dữ liệu Common Data Model bằng cách sử dụng Azure Data Lake Storage.
ms.date: 07/27/2022
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- ci-attach-cdm
- customerInsights
ms.openlocfilehash: b237c291bb4dd22ca22ab2cdd8b6293490aa83e1
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245859"
---
# <a name="connect-to-data-in-azure-data-lake-storage"></a>Kết nối với dữ liệu trong Azure Data Lake Storage

Nhập dữ liệu vào Dynamics 365 Customer Insights sử dụng của bạn Azure Data Lake Storage Tài khoản Gen2. Quá trình nhập dữ liệu có thể đầy đủ hoặc tăng dần.

## <a name="prerequisites"></a>Điều kiện tiên quyết

- Hỗ trợ nhập dữ liệu Azure Data Lake Storage *Gen2* tài khoản độc quyền. Bạn không thể sử dụng tài khoản Data Lake Storage Gen1 để nhập dữ liệu.

- Các Azure Data Lake Storage tài khoản phải có [không gian tên phân cấp được bật](/azure/storage/blobs/data-lake-storage-namespace). Dữ liệu phải được lưu trữ ở định dạng thư mục phân cấp xác định thư mục gốc và có các thư mục con cho mỗi thực thể. Các thư mục con có thể có dữ liệu đầy đủ hoặc các thư mục dữ liệu gia tăng.

- Để xác thực bằng dịch vụ chính Azure, hãy đảm bảo rằng dịch vụ chính được định cấu hình trong đối tượng thuê của bạn. Để biết thêm thông tin, hãy xem [Kết nối với một Azure Data Lake Storage Tài khoản Gen2 có gốc dịch vụ Azure](connect-service-principal.md).

- Các Azure Data Lake Storage bạn muốn kết nối và nhập dữ liệu từ đó phải ở trong cùng khu vực Azure với Dynamics 365 Customer Insights Môi trường. Không hỗ trợ kết nối với thư mục Common Data Model từ một kho dữ liệu trong một vùng Azure khác. Để biết vùng Azure của môi trường, hãy truy cập **Quản trị viên** > **Hệ thống** > **Về** trong Thông tin chi tiết về khách hàng.

- Dữ liệu được lưu trữ trong các dịch vụ trực tuyến có thể được lưu trữ ở một vị trí khác với nơi dữ liệu được xử lý hoặc lưu trữ trong Dynamics 365 Customer Insights.Bằng cách nhập hoặc kết nối với dữ liệu được lưu trữ trong các dịch vụ trực tuyến, bạn đồng ý rằng dữ liệu có thể được chuyển đến và lưu trữ bằng Dynamics 365 Customer Insights . [Tìm hiểu thêm tại Trung tâm tin cậy của Microsoft](https://www.microsoft.com/trust-center).

- Nhân viên chính của dịch vụ Thông tin chi tiết về khách hàng phải có một trong các vai trò sau đây để truy cập vào tài khoản lưu trữ. Để biết thêm thông tin, hãy xem [Cấp quyền cho người điều hành dịch vụ để truy cập vào tài khoản lưu trữ](connect-service-principal.md#grant-permissions-to-the-service-principal-to-access-the-storage-account).
  - Bộ đọc dữ liệu khối lưu trữ
  - Chủ sở hữu dữ liệu khối lưu trữ
  - Người đóng góp dữ liệu khối lưu trữ

- Dữ liệu trong Data Lake Storage của bạn phải tuân theo tiêu chuẩn Mô hình Dữ liệu Chung để lưu trữ dữ liệu của bạn và có tệp kê khai mô hình dữ liệu chung để đại diện cho lược đồ của các tệp dữ liệu (* .csv hoặc * .parquet). Tệp kê khai phải cung cấp thông tin chi tiết về các đối tượng như cột đối tượng và kiểu dữ liệu cũng như vị trí tệp dữ liệu và loại tệp. Để biết thêm thông tin, hãy xem [Tệp kê khai Mô hình dữ liệu chung](/common-data-model/sdk/manifest). Nếu tệp kê khai không xuất hiện, người dùng quản trị có quyền truy cập Chủ sở hữu dữ liệu Blob lưu trữ hoặc Người đóng góp dữ liệu Blob lưu trữ có thể xác định giản đồ khi nhập dữ liệu.

## <a name="connect-to-azure-data-lake-storage"></a>Kết nối với Azure Data Lake Storage

1. Chuyển tới **Dữ liệu** > **Nguồn dữ liệu**.

1. Chọn **Thêm nguồn dữ liệu**.

1. Lựa chọn **Lưu trữ hồ dữ liệu Azure**.

   :::image type="content" source="media/data_sources_ADLS.png" alt-text="Hộp thoại để nhập chi tiết kết nối cho Azure Data Lake." lightbox="media/data_sources_ADLS.png":::

1. Nhập **Tên** cho nguồn dữ liệu và một tùy chọn **Sự mô tả**. Tên xác định duy nhất nguồn dữ liệu và được tham chiếu trong các quy trình hạ lưu và không thể thay đổi.

1. Chọn một trong các tùy chọn sau cho **Kết nối bộ nhớ của bạn bằng**. Để biết thêm thông tin, hãy xem [Kết nối Thông tin chi tiết về khách hàng với một Azure Data Lake Storage Tài khoản Gen2 có gốc dịch vụ Azure](connect-service-principal.md).

   - **Tài nguyên Azure** : Nhập **Id tài nguyên** . Theo tùy chọn, nếu bạn muốn nhập dữ liệu từ tài khoản lưu trữ thông qua Liên kết riêng tư Azure, hãy chọn **Bật liên kết riêng tư**. Để biết thêm thông tin, hãy xem [Liên kết riêng tư](security-overview.md#set-up-an-azure-private-link).
   - **Đăng ký Azure** : Chọn **Đăng ký** và sau đó **Nhóm tài nguyên** và **Tài khoản lưu trữ**. Theo tùy chọn, nếu bạn muốn nhập dữ liệu từ tài khoản lưu trữ thông qua Liên kết riêng tư Azure, hãy chọn **Bật liên kết riêng tư**. Để biết thêm thông tin, hãy xem [Liên kết riêng tư](security-overview.md#set-up-an-azure-private-link).
  
   > [!NOTE]
   > Bạn cần một trong các vai trò sau đối với vùng chứa hoặc tài khoản lưu trữ để tạo nguồn dữ liệu:
   >
   >  - Storage Blob Data Reader đủ để đọc từ tài khoản lưu trữ và nhập dữ liệu vào Customer Insights. 
   >  - Người đóng góp hoặc chủ sở hữu dữ liệu Storage Blob là bắt buộc nếu bạn muốn chỉnh sửa tệp kê khai trực tiếp trong Thông tin chi tiết về khách hàng.  
  
1. Chọn tên của **Thùng đựng hàng** chứa dữ liệu và giản đồ (tệp model.json hoặc tệp manifest.json) để nhập dữ liệu từ đó và chọn **Tiếp theo**.
   > [!NOTE]
   > Mọi tệp model.json hoặc manifest.json được liên kết với nguồn dữ liệu khác trong môi trường sẽ không hiển thị trong danh sách. Tuy nhiên, cùng một tệp model.json hoặc manifest.json có thể được sử dụng cho các nguồn dữ liệu trong nhiều môi trường.

1. Để tạo một giản đồ mới, hãy truy cập [Tạo một tệp giản đồ mới](#create-a-new-schema-file).

1. Để sử dụng một lược đồ hiện có, hãy điều hướng đến thư mục chứa tệp model.json hoặc tệp manifest.cdm.json. Bạn có thể tìm kiếm trong một thư mục để tìm tệp.

1. Chọn tệp json và chọn **Tiếp theo**. Một danh sách các thực thể có sẵn sẽ hiển thị.

   :::image type="content" source="media/review-entities.png" alt-text="Hộp thoại danh sách các thực thể để chọn":::

1. Chọn các thực thể bạn muốn đưa vào.

   :::image type="content" source="media/ADLS_required.png" alt-text="Hộp thoại hiển thị Bắt buộc đối với Khóa chính":::

   > [!TIP]
   > Để chỉnh sửa một đối tượng trong giao diện chỉnh sửa JSON, hãy chọn đối tượng và sau đó **Chỉnh sửa tệp lược đồ**. Thực hiện các thay đổi và chọn **Tiết kiệm**.

1. Đối với các thực thể đã chọn yêu cầu nhập tăng dần, **Yêu cầu** hiển thị dưới **Làm mới gia tăng**. Đối với từng thực thể này, hãy xem [Định cấu hình làm mới gia tăng cho các nguồn dữ liệu Azure Data Lake](incremental-refresh-data-sources.md).

1. Đối với các thực thể đã chọn mà khóa chính chưa được xác định, **Yêu cầu** hiển thị dưới **Khóa chính**. Đối với mỗi thực thể sau:
   1. Lựa chọn **Yêu cầu**. Các **Chỉnh sửa thực thể** bảng điều khiển hiển thị.
   1. Chọn **Khóa chính**. Khóa chính là một thuộc tính duy nhất của thực thể. Để một thuộc tính là khóa chính hợp lệ, thuộc tính đó không được bao gồm các giá trị trùng lặp, giá trị bị thiếu hoặc giá trị rỗng. Các thuộc tính kiểu dữ liệu chuỗi, số nguyên và GUID được hỗ trợ làm khóa chính.
   1. Theo tùy chọn, thay đổi mẫu phân vùng.
   1. Lựa chọn **Đóng** để lưu và đóng bảng điều khiển.

1. Chọn số lượng **Thuộc tính** cho mỗi thực thể được bao gồm. Các **Quản lý các thuộc tính** hiển thị trang.

   :::image type="content" source="media/dataprofiling-entities.png" alt-text="Hộp thoại để chọn cấu hình dữ liệu.":::

   1. Tạo các thuộc tính mới, chỉnh sửa hoặc xóa các thuộc tính hiện có. Bạn có thể thay đổi tên, định dạng dữ liệu hoặc thêm một loại ngữ nghĩa.
   1. Để bật phân tích và các khả năng khác, hãy chọn **Lập hồ sơ dữ liệu** cho toàn bộ thực thể hoặc cho các thuộc tính cụ thể. Theo mặc định, không có thực thể nào được bật cho phân tích chất lượng dữ liệu.
   1. Chọn **Xong**.

1. Chọn **Lưu.** Các **Nguồn dữ liệu** trang mở ra hiển thị nguồn dữ liệu mới trong **Làm mới** trạng thái.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Quá trình tải dữ liệu có thể mất một khoảng thời gian. Sau khi làm mới thành công, dữ liệu đã nhập có thể được xem xét từ [**Thực thể**](entities.md) trang.

### <a name="create-a-new-schema-file"></a>Tạo một tệp giản đồ mới

1. Lựa chọn **Tệp lược đồ mới**.

1. Nhập tên cho tệp và chọn **Tiết kiệm**.

1. Lựa chọn **Thực thể mới**. Các **Thực thể mới** bảng điều khiển hiển thị.

1. Nhập tên thực thể và chọn **Vị trí tệp dữ liệu**.
   - **Nhiều tệp .csv hoặc .parquet** : Duyệt đến thư mục gốc, chọn kiểu mẫu và nhập biểu thức.
   - **Tệp .csv hoặc .parquet đơn lẻ** : Duyệt đến tệp .csv hoặc .parquet và chọn nó.

   :::image type="content" source="media/ADLS_new_entity_location.png" alt-text="Hộp thoại để tạo một thực thể mới với vị trí tệp Dữ liệu được đánh dấu.":::

1. Chọn **Lưu.**

   :::image type="content" source="media/ADLS_new_entity_define_attributes.png" alt-text="Hộp thoại để xác định hoặc tự động tạo các thuộc tính.":::

1. Lựa chọn **xác định các thuộc tính** để thêm các thuộc tính theo cách thủ công hoặc chọn **tự động tạo chúng**. Để xác định các thuộc tính, hãy nhập tên, chọn định dạng dữ liệu và kiểu ngữ nghĩa tùy chọn. Đối với các thuộc tính được tạo tự động:

   1. Sau khi các thuộc tính được tạo tự động, hãy chọn **Xem lại các thuộc tính**. Các **Quản lý các thuộc tính** hiển thị trang.

   1. Đảm bảo định dạng dữ liệu chính xác cho từng thuộc tính.

   1. Để bật phân tích và các khả năng khác, hãy chọn **Lập hồ sơ dữ liệu** cho toàn bộ thực thể hoặc cho các thuộc tính cụ thể. Theo mặc định, không có thực thể nào được bật cho phân tích chất lượng dữ liệu.

      :::image type="content" source="media/dataprofiling-entities.png" alt-text="Hộp thoại để chọn cấu hình dữ liệu.":::

   1. Chọn **Xong**. Các **Chọn thực thể** hiển thị trang.

1. Tiếp tục thêm các thực thể và thuộc tính, nếu có.

1. Sau khi tất cả các thực thể đã được thêm, hãy chọn **Bao gồm** để bao gồm các thực thể trong quá trình nhập nguồn dữ liệu.

   :::image type="content" source="media/ADLS_required.png" alt-text="Hộp thoại hiển thị Bắt buộc đối với Khóa chính":::

1. Đối với các thực thể đã chọn yêu cầu nhập tăng dần, **Yêu cầu** hiển thị dưới **Làm mới gia tăng**. Đối với từng thực thể này, hãy xem [Định cấu hình làm mới gia tăng cho các nguồn dữ liệu Azure Data Lake](incremental-refresh-data-sources.md).

1. Đối với các thực thể đã chọn mà khóa chính chưa được xác định, **Yêu cầu** hiển thị dưới **Khóa chính**. Đối với mỗi thực thể sau:
   1. Lựa chọn **Yêu cầu**. Các **Chỉnh sửa thực thể** bảng điều khiển hiển thị.
   1. Chọn **Khóa chính**. Khóa chính là một thuộc tính duy nhất của thực thể. Để một thuộc tính là khóa chính hợp lệ, thuộc tính đó không được bao gồm các giá trị trùng lặp, giá trị bị thiếu hoặc giá trị rỗng. Các thuộc tính kiểu dữ liệu chuỗi, số nguyên và GUID được hỗ trợ làm khóa chính.
   1. Theo tùy chọn, thay đổi mẫu phân vùng.
   1. Lựa chọn **Đóng** để lưu và đóng bảng điều khiển.

1. Chọn **Lưu.** Các **Nguồn dữ liệu** trang mở ra hiển thị nguồn dữ liệu mới trong **Làm mới** trạng thái.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Quá trình tải dữ liệu có thể mất một khoảng thời gian. Sau khi làm mới thành công, dữ liệu đã nhập có thể được xem xét từ [**Thực thể**](entities.md) trang.

## <a name="edit-an-azure-data-lake-storage-data-source"></a>Chỉnh sửa một Azure Data Lake Storage nguồn dữ liệu

Bạn có thể cập nhật *Kết nối với tài khoản lưu trữ bằng* quyền mua. Để biết thêm thông tin, hãy xem [Kết nối Thông tin chi tiết về khách hàng với một Azure Data Lake Storage Tài khoản Gen2 có gốc dịch vụ Azure](connect-service-principal.md). Để kết nối với vùng chứa khác từ tài khoản lưu trữ của bạn hoặc đổi tên tài khoản, hãy [tạo một kết nối mới cho nguồn dữ liệu](#connect-to-azure-data-lake-storage).

1. Chuyển tới **Dữ liệu** > **Nguồn dữ liệu**.

1. Bên cạnh nguồn dữ liệu bạn muốn cập nhật, hãy chọn **Chỉnh sửa**.

   :::image type="content" source="media/data_sources_edit_ADLS.png" alt-text="Hộp thoại để chỉnh sửa Azure Data Lake nguồn dữ liệu.":::

1. Thay đổi bất kỳ thông tin nào sau đây:

   - **Mô tả**
   - **Kết nối bộ nhớ của bạn bằng** và thông tin kết nối. Bạn không thể thay đổi thông tin **Vùng chứa** khi cập nhật kết nối.
      > [!NOTE]
      > Một trong các vai trò sau đây phải được chỉ định cho tài khoản lưu trữ hoặc vùng chứa:
        > - Bộ đọc dữ liệu khối lưu trữ
        > - Chủ sở hữu dữ liệu khối lưu trữ
        > - Người đóng góp dữ liệu khối lưu trữ

   - **Bật liên kết riêng tư** nếu bạn muốn nhập dữ liệu từ tài khoản lưu trữ thông qua Liên kết cá nhân Azure. Để biết thêm thông tin, hãy xem [Liên kết riêng tư](security-overview.md#set-up-an-azure-private-link).

1. Chọn **Tiếp theo**.
1. Thay đổi bất kỳ điều nào sau đây:
   - Điều hướng đến tệp model.json hoặc tệp manifest.json khác với một nhóm thực thể khác từ vùng chứa.
   - Để thêm các thực thể bổ sung để nhập, hãy chọn **Thực thể mới**.
   - Để xóa bất kỳ thực thể nào đã được chọn nếu không có phụ thuộc, hãy chọn thực thể và **Xóa bỏ**.
      > [!IMPORTANT]
      > Nếu có các phần phụ thuộc vào tệp model.json hoặc tệp manifest.json hiện có và tập hợp các thực thể, bạn sẽ thấy thông báo lỗi và không thể chọn tệp model.json hoặc tệp manifest.json khác. Hãy xóa các phần phụ thuộc đó trước khi thay đổi tệp model.json hoặc tệp manifest.json hoặc tạo một nguồn dữ liệu mới với tệp model.json hoặc tệp manifest.json mà bạn muốn sử dụng để tránh xóa các phần phụ thuộc.
   - Để thay đổi vị trí tệp dữ liệu hoặc khóa chính, hãy chọn **Chỉnh sửa**.
   - Để thay đổi dữ liệu nhập gia tăng, hãy xem [Định cấu hình làm mới gia tăng cho các nguồn dữ liệu Azure Data Lake](incremental-refresh-data-sources.md).
   - Chỉ thay đổi tên thực thể để khớp với tên thực thể trong tệp .json.

     > [!NOTE]
     > Luôn giữ tên thực thể trong Thông tin chi tiết về khách hàng giống với tên thực thể bên trong tệp model.json hoặc tệp manifest.json sau khi nhập. Thông tin chi tiết về khách hàng xác thực tất cả các tên thực thể bằng model.json hoặc manifest.json trong mỗi lần làm mới hệ thống. Nếu tên thực thể được thay đổi bên trong Thông tin chi tiết về khách hàng hoặc bên ngoài, thì sẽ xảy ra lỗi vì Thông tin chi tiết về khách hàng không thể tìm thấy tên thực thể mới trong tệp .json. Nếu tên thực thể đã nhập vô tình bị thay đổi, hãy chỉnh sửa tên thực thể trong Thông tin chi tiết về khách hàng để khớp với tên trong tệp .json.

1. Lựa chọn **Thuộc tính** để thêm hoặc thay đổi các thuộc tính hoặc để kích hoạt cấu hình dữ liệu. Sau đó, chọn **Hoàn tất**.

1. Nhấp chuột **Tiết kiệm** để áp dụng các thay đổi của bạn và quay lại **Nguồn dữ liệu** trang.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
