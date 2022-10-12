---
title: Kết nối với thư mục Common Data Model sử dụng tài khoản Azure Data Lake
description: Làm việc với dữ liệu Common Data Model bằng cách sử dụng Azure Data Lake Storage.
ms.date: 09/29/2022
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
ms.openlocfilehash: c12603b9ed8a814356a0f8d0137e97afc749b87c
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609974"
---
# <a name="connect-to-data-in-azure-data-lake-storage"></a>Kết nối với dữ liệu trong Azure Data Lake Storage

Nhập dữ liệu vào Dynamics 365 Customer Insights sử dụng của bạn Azure Data Lake Storage Tài khoản Gen2. Quá trình nhập dữ liệu có thể đầy đủ hoặc tăng dần.

## <a name="prerequisites"></a>Điều kiện tiên quyết

- Hỗ trợ nhập dữ liệu Azure Data Lake Storage *Gen2* tài khoản độc quyền. Bạn không thể sử dụng tài khoản Data Lake Storage Gen1 để nhập dữ liệu.

- Các Azure Data Lake Storage tài khoản phải có [không gian tên phân cấp được bật](/azure/storage/blobs/data-lake-storage-namespace). Dữ liệu phải được lưu trữ ở định dạng thư mục phân cấp xác định thư mục gốc và có các thư mục con cho mỗi thực thể. Các thư mục con có thể có đầy đủ dữ liệu hoặc các thư mục dữ liệu gia tăng.

- Để xác thực bằng dịch vụ chính Azure, hãy đảm bảo rằng dịch vụ chính được định cấu hình trong đối tượng thuê của bạn. Để biết thêm thông tin, hãy xem [Kết nối với một Azure Data Lake Storage Tài khoản Gen2 có gốc dịch vụ Azure](connect-service-principal.md).

- Các Azure Data Lake Storage bạn muốn kết nối và nhập dữ liệu từ đó phải ở trong cùng khu vực Azure với Dynamics 365 Customer Insights Môi trường. Không hỗ trợ kết nối với thư mục Common Data Model từ một kho dữ liệu trong một vùng Azure khác. Để biết vùng Azure của môi trường, hãy truy cập **Quản trị viên** > **Hệ thống** > **Về** trong Thông tin chi tiết về khách hàng.

- Dữ liệu được lưu trữ trong các dịch vụ trực tuyến có thể được lưu trữ ở một vị trí khác với nơi dữ liệu được xử lý hoặc lưu trữ trong Dynamics 365 Customer Insights.Bằng cách nhập hoặc kết nối với dữ liệu được lưu trữ trong các dịch vụ trực tuyến, bạn đồng ý rằng dữ liệu có thể được chuyển đến và lưu trữ bằng Dynamics 365 Customer Insights . [Tìm hiểu thêm tại Trung tâm Tin cậy của Microsoft](https://www.microsoft.com/trust-center).

- Nhân viên chính của dịch vụ Thông tin chi tiết về khách hàng phải đảm nhiệm một trong các vai trò sau đây để truy cập vào tài khoản lưu trữ. Để biết thêm thông tin, hãy xem [Cấp quyền cho người quản lý dịch vụ để truy cập vào tài khoản lưu trữ](connect-service-principal.md#grant-permissions-to-the-service-principal-to-access-the-storage-account).
  - Bộ đọc dữ liệu khối lưu trữ
  - Chủ sở hữu dữ liệu khối lưu trữ
  - Người đóng góp dữ liệu khối lưu trữ

- Người dùng thiết lập kết nối nguồn dữ liệu cần ít quyền nhất của Storage Blob Data Contributor trên tài khoản lưu trữ.

- Dữ liệu trong Data Lake Storage của bạn phải tuân theo tiêu chuẩn Mô hình Dữ liệu Chung để lưu trữ dữ liệu của bạn và có tệp kê khai mô hình dữ liệu chung để đại diện cho lược đồ của các tệp dữ liệu (* .csv hoặc * .parquet). Tệp kê khai phải cung cấp thông tin chi tiết về các đối tượng như cột đối tượng và kiểu dữ liệu cũng như vị trí tệp dữ liệu và loại tệp. Để biết thêm thông tin, hãy xem [Tệp kê khai Mô hình dữ liệu chung](/common-data-model/sdk/manifest). Nếu tệp kê khai không xuất hiện, người dùng quản trị có quyền truy cập Chủ sở hữu dữ liệu Blob lưu trữ hoặc Người đóng góp dữ liệu Blob lưu trữ có thể xác định giản đồ khi nhập dữ liệu.

## <a name="recommendations"></a>Đề xuất

Để có hiệu suất tối ưu, Customer Insights khuyến nghị kích thước của phân vùng từ 1 GB trở xuống và số lượng tệp phân vùng trong một thư mục không được vượt quá 1000.

## <a name="connect-to-azure-data-lake-storage"></a>Kết nối với Azure Data Lake Storage

1. Chuyển tới **Dữ liệu** > **Nguồn dữ liệu**.

1. Chọn **Thêm nguồn dữ liệu**.

1. Lựa chọn **Lưu trữ hồ dữ liệu Azure**.

   :::image type="content" source="media/data_sources_ADLS.png" alt-text="Hộp thoại để nhập chi tiết kết nối cho Azure Data Lake." lightbox="media/data_sources_ADLS.png":::

1. Nhập **Tên** cho nguồn dữ liệu và một tùy chọn **Sự mô tả**. Tên xác định duy nhất nguồn dữ liệu và được tham chiếu trong các quy trình hạ lưu và không thể thay đổi.

1. Chọn một trong các tùy chọn sau cho **Kết nối bộ nhớ của bạn bằng**. Để biết thêm thông tin, hãy xem [Kết nối thông tin chi tiết về khách hàng với Azure Data Lake Storage Tài khoản Gen2 có gốc dịch vụ Azure](connect-service-principal.md).

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

1. Để tạo một giản đồ mới, hãy chuyển đến [Tạo một tệp giản đồ mới](#create-a-new-schema-file).

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

   1. Tạo các thuộc tính mới, chỉnh sửa hoặc xóa các thuộc tính hiện có. Bạn có thể thay đổi tên, định dạng dữ liệu hoặc thêm một kiểu ngữ nghĩa.
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

Bạn có thể cập nhật *Kết nối với tài khoản lưu trữ bằng* quyền mua. Để biết thêm thông tin, hãy xem [Kết nối thông tin chi tiết về khách hàng với Azure Data Lake Storage Tài khoản Gen2 có gốc dịch vụ Azure](connect-service-principal.md). Để kết nối với vùng chứa khác từ tài khoản lưu trữ của bạn hoặc đổi tên tài khoản, hãy [tạo một kết nối mới cho nguồn dữ liệu](#connect-to-azure-data-lake-storage).

1. Chuyển tới **Dữ liệu** > **Nguồn dữ liệu**.

1. Bên cạnh nguồn dữ liệu bạn muốn cập nhật, hãy chọn **Chỉnh sửa**.

   :::image type="content" source="media/data_sources_edit_ADLS.png" alt-text="Hộp thoại để chỉnh sửa Azure Data Lake nguồn dữ liệu.":::

1. Thay đổi bất kỳ thông tin nào sau đây:

   - **Mô tả**
   - **Kết nối bộ nhớ của bạn bằng** và thông tin kết nối. Bạn không thể thay đổi thông tin **Vùng chứa** khi cập nhật kết nối.
      > [!NOTE]
      > Một trong các vai trò sau phải được chỉ định cho tài khoản lưu trữ hoặc vùng chứa:
        > - Bộ đọc dữ liệu khối lưu trữ
        > - Chủ sở hữu dữ liệu khối lưu trữ
        > - Người đóng góp dữ liệu khối lưu trữ

   - **Bật liên kết riêng tư** nếu bạn muốn nhập dữ liệu từ tài khoản lưu trữ thông qua Liên kết riêng tư Azure. Để biết thêm thông tin, hãy xem [Liên kết riêng tư](security-overview.md#set-up-an-azure-private-link).

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
     > Luôn giữ tên thực thể trong Thông tin chi tiết về khách hàng giống với tên thực thể bên trong tệp model.json hoặc tệp manifest.json sau khi nhập. Thông tin chi tiết về khách hàng xác thực tất cả các tên thực thể bằng model.json hoặc manifest.json trong mỗi lần làm mới hệ thống. Nếu tên pháp nhân được thay đổi bên trong Thông tin chi tiết về khách hàng hoặc bên ngoài, thì sẽ xảy ra lỗi vì Thông tin chi tiết về khách hàng không thể tìm thấy tên thực thể mới trong tệp .json. Nếu tên thực thể đã nhập vô tình bị thay đổi, hãy chỉnh sửa tên thực thể trong Thông tin chi tiết về khách hàng để khớp với tên trong tệp .json.

1. Lựa chọn **Thuộc tính** để thêm hoặc thay đổi các thuộc tính hoặc để kích hoạt cấu hình dữ liệu. Sau đó, chọn **Hoàn tất**.

1. Nhấp chuột **Tiết kiệm** để áp dụng các thay đổi của bạn và quay lại **Nguồn dữ liệu** trang.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="common-reasons-for-ingestion-errors-or-corrupt-data"></a>Các lý do phổ biến gây ra lỗi nhập hoặc dữ liệu bị hỏng

Trong quá trình nhập dữ liệu, một số lý do phổ biến nhất mà bản ghi có thể bị coi là bị hỏng bao gồm:

- Các kiểu dữ liệu và giá trị trường không khớp giữa tệp nguồn và giản đồ
- Số cột trong tệp nguồn không khớp với lược đồ
- Các trường chứa các ký tự khiến các cột bị lệch so với lược đồ mong đợi. Ví dụ: dấu ngoặc kép được định dạng không chính xác, dấu ngoặc kép không thoát, ký tự dòng mới hoặc ký tự được gắn thẻ.
- Tệp phân vùng bị thiếu
- Nếu có các cột datetime / date / datetimeoffset, thì định dạng của chúng phải được chỉ định trong lược đồ nếu nó không tuân theo định dạng chuẩn.

### <a name="schema-or-data-type-mismatch"></a>Lược đồ hoặc kiểu dữ liệu không khớp

Nếu dữ liệu không tuân theo lược đồ, quá trình nhập sẽ hoàn tất với lỗi. Sửa dữ liệu nguồn hoặc lược đồ và nhập lại dữ liệu.

### <a name="partition-files-are-missing"></a>Tệp phân vùng bị thiếu

- Nếu quá trình nhập thành công mà không có bất kỳ bản ghi nào bị hỏng, nhưng bạn không thể thấy bất kỳ dữ liệu nào, hãy chỉnh sửa tệp model.json hoặc tệp manifest.json của bạn để đảm bảo các phân vùng được chỉ định. Sau đó, [làm mới nguồn dữ liệu](data-sources.md#refresh-data-sources).

- Nếu quá trình nhập dữ liệu xảy ra cùng lúc với nguồn dữ liệu đang được làm mới trong quá trình làm mới theo lịch tự động, thì các tệp phân vùng có thể trống hoặc không có sẵn để Customer Insights xử lý. Để phù hợp với lịch trình làm mới ngược dòng, hãy thay đổi [lịch làm mới hệ thống](schedule-refresh.md) hoặc lịch làm mới cho nguồn dữ liệu. Căn chỉnh thời gian để không phải làm mới tất cả cùng một lúc và cung cấp dữ liệu mới nhất được xử lý trong Thông tin chi tiết về khách hàng.

### <a name="datetime-fields-in-the-wrong-format"></a>Các trường ngày giờ ở định dạng sai

Các trường ngày giờ trong thực thể không ở định dạng ISO 8601 hoặc en-US. Định dạng ngày giờ mặc định trong Thông tin chi tiết về khách hàng là định dạng ở Hoa Kỳ. Tất cả các trường ngày giờ trong một thực thể phải ở cùng một định dạng. Thông tin chi tiết về khách hàng hỗ trợ các định dạng khác được cung cấp các chú thích hoặc đặc điểm được tạo ở cấp nguồn hoặc cấp thực thể trong mô hình hoặc tệp kê khai.json. Ví dụ: 

**Model.json**

   ```json
      "annotations": [
        {
          "name": "ci:CustomTimestampFormat",
          "value": "yyyy-MM-dd'T'HH:mm:ss:SSS"
        },
        {
          "name": "ci:CustomDateFormat",
          "value": "yyyy-MM-dd"
        }
      ]   
   ```

  Trong tệp kê khai.json, định dạng ngày giờ có thể được chỉ định ở cấp thực thể hoặc ở cấp thuộc tính. Ở cấp thực thể, hãy sử dụng "tang vật" trong thực thể ở định dạng * .manifest.cdm.json để xác định định dạng ngày giờ. Ở cấp thuộc tính, hãy sử dụng "applyTraits" trong thuộc tính trong entityname.cdm.json.

**Manifest.json ở cấp thực thể**

```json
"exhibitsTraits": [
    {
        "traitReference": "is.formatted.dateTime",
        "arguments": [
            {
                "name": "format",
                "value": "yyyy-MM-dd'T'HH:mm:ss"
            }
        ]
    },
    {
        "traitReference": "is.formatted.date",
        "arguments": [
            {
                "name": "format",
                "value": "yyyy-MM-dd"
            }
        ]
    }
]
```

**Entity.json ở cấp thuộc tính**

```json
   {
      "name": "PurchasedOn",
      "appliedTraits": [
        {
          "traitReference": "is.formatted.date",
          "arguments" : [
            {
              "name": "format",
              "value": "yyyy-MM-dd"
            }
          ]
        },
        {
          "traitReference": "is.formatted.dateTime",
          "arguments" : [
            {
              "name": "format",
              "value": "yyyy-MM-ddTHH:mm:ss"
            }
          ]
        }
      ],
      "attributeContext": "POSPurchases/attributeContext/POSPurchases/PurchasedOn",
      "dataFormat": "DateTime"
    }
```

[!INCLUDE [footer-include](includes/footer-banner.md)]
