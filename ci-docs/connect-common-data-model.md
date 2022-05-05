---
title: Kết nối dữ liệu Common Data Model với tài khoản Azure Data Lake
description: Làm việc với dữ liệu Common Data Model bằng cách sử dụng Azure Data Lake Storage.
ms.date: 01/25/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- ci-attach-cdm
- customerInsights
ms.openlocfilehash: eeb6b9d97be5f9c0b9f6cbd6dbc6985559a1cd9d
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 04/27/2022
ms.locfileid: "8644046"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a>Kết nối với thư mục Common Data Model sử dụng tài khoản Azure Data Lake

Bài viết này cung cấp thông tin về cách nhập dữ liệu vào Dynamics 365 Customer Insights từ một thư mục Mô hình Dữ liệu Chung bằng cách sử dụng Azure Data Lake Storage Tài khoản Gen2.

## <a name="important-considerations"></a>Những điều quan trọng cần cân nhắc

- Dữ liệu trong Azure Data Lake của bạn phải theo chuẩn Common Data Model. Hiện các định dạng khác chưa được hỗ trợ.

- Nhập dữ liệu chỉ hỗ trợ tài khoản lưu trữ Azure Data Lake *Gen2*. Bạn không thể sử dụng tài khoản lưu trữ Azure Data Lake Gen1 để nhập dữ liệu.

- Tài khoản lưu trữ Azure Data Lake phải có [không gian tên phân cấp được bật](/azure/storage/blobs/data-lake-storage-namespace).

- Để xác thực bằng dịch vụ chính Azure, hãy đảm bảo rằng dịch vụ chính được định cấu hình trong đối tượng thuê của bạn. Để biết thêm thông tin, hãy xem [Kết nối với một Azure Data Lake Storage Tài khoản Gen2 có gốc dịch vụ Azure](connect-service-principal.md).

- Azure Data Lake mà bạn muốn kết nối và nhập dữ liệu phải ở cùng khu vực Azure với môi trường Dynamics 365 Customer Insights. Không hỗ trợ kết nối với thư mục Common Data Model từ một kho dữ liệu trong một vùng Azure khác. Để biết vùng Azure của môi trường, hãy truy cập **Quản trị viên** > **Hệ thống** > **Về** trong Thông tin chi tiết về khách hàng.

- Dữ liệu được lưu trữ trong các dịch vụ trực tuyến có thể được lưu trữ ở một vị trí khác với nơi dữ liệu được xử lý hoặc lưu trữ trong Dynamics 365 Customer Insights.Bằng cách nhập hoặc kết nối với dữ liệu được lưu trữ trong các dịch vụ trực tuyến, bạn đồng ý rằng dữ liệu có thể được chuyển đến và lưu trữ bằng Dynamics 365 Customer Insights . [Tìm hiểu thêm tại Trung tâm Tin cậy của Microsoft](https://www.microsoft.com/trust-center).

## <a name="connect-to-a-common-data-model-folder"></a>Kết nối với thư mục Common Data Model

1. Chuyển tới **Dữ liệu** > **Nguồn dữ liệu**.

1. Chọn **Thêm nguồn dữ liệu**.

1. Lựa chọn **Lưu trữ hồ dữ liệu Azure**, nhập **Tên** cho nguồn dữ liệu, sau đó chọn **Kế tiếp**.

   - Nếu được nhắc, hãy chọn một trong các bộ dữ liệu mẫu liên quan đến ngành của bạn, sau đó chọn **Kế tiếp**. 

1. Bạn có thể chọn giữa sử dụng tùy chọn dựa trên nguồn lực và tùy chọn dựa trên đăng ký để xác thực. Để biết thêm thông tin, hãy xem [Kết nối với một Azure Data Lake Storage Tài khoản Gen2 có gốc dịch vụ Azure](connect-service-principal.md). Nhập **Địa chỉ máy chủ**, lựa chọn **đăng nhập**, sau đó chọn **Kế tiếp**.
   > [!div class="mx-imgBorder"]
   > ![Hộp thoại để nhập chi tiết kết nối mới cho Azure Data Lake.](media/enter-new-storage-details.png)
   > [!NOTE]
   > Bạn cần một trong các vai trò sau đối với vùng chứa hoặc tài khoản lưu trữ được đề cập ở trên để có thể kết nối và tạo nguồn dữ liệu:
   >  - Bộ đọc dữ liệu khối lưu trữ
   >  - Chủ sở hữu dữ liệu khối lưu trữ
   >  - Người đóng góp dữ liệu khối lưu trữ

1. Trong hộp thoại **Chọn thư mục Common Data Model**, chọn tệp model.json hoặc manifest.json để nhập dữ liệu từ đó và chọn **Tiếp theo**.
   > [!NOTE]
   > Mọi tệp model.json hoặc manifest.json được liên kết với nguồn dữ liệu khác trong môi trường sẽ không hiển thị trong danh sách.

1. Bạn sẽ thấy danh sách các thực thể có sẵn trong tệp model.json hoặc tệp manifest.json đã chọn. Xem lại và chọn từ danh sách các thực thể có sẵn, sau đó chọn **Cứu**. Tất cả thực thể đã chọn sẽ được nhập từ nguồn dữ liệu mới.
   > [!div class="mx-imgBorder"]
   > ![Hộp thoại hiển thị danh sách thực thể từ tệp model.json.](media/review-entities.png)

8. Cho biết thực thể dữ liệu nào bạn muốn bật cấu hình dữ liệu, sau đó chọn **Cứu**. Tính năng thu thập dữ liệu cho phép phân tích và các chức năng khác. Bạn có thể chọn toàn bộ thực thể. Thao tác này sẽ chọn tất cả các thuộc tính từ thực thể hoặc chọn một số thuộc tính bạn chọn. Theo mặc định, không có thực thể nào được bật cho phân tích chất lượng dữ liệu.
   > [!div class="mx-imgBorder"]
   > ![Hộp thoại hiển thị phân tích chất lượng dữ liệu.](media/dataprofiling-entities.png)

9. Sau khi bạn lưu các lựa chọn, trang **Nguồn dữ liệu** sẽ mở ra. Lúc này, bạn sẽ thấy kết nối thư mục Common Data Model dưới dạng nguồn dữ liệu.

> [!NOTE]
> Tệp model.json hoặc manifest.json chỉ có thể liên kết với một nguồn dữ liệu trong cùng một môi trường. Tuy nhiên, cùng một tệp model.json hoặc manifest.json có thể được sử dụng cho các nguồn dữ liệu trong nhiều môi trường.

## <a name="edit-a-common-data-model-folder-data-source"></a>Chỉnh sửa nguồn dữ liệu thư mục Common Data Model

Bạn có thể cập nhật khóa truy cập cho tài khoản lưu trữ có chứa thư mục Common Data Model. Bạn cũng có thể thay đổi tệp model.json hoặc tệp manifest.json. Để kết nối với vùng chứa khác từ tài khoản lưu trữ của bạn hoặc đổi tên tài khoản, hãy [tạo một kết nối mới cho nguồn dữ liệu](#connect-to-a-common-data-model-folder).

1. Chuyển tới **Dữ liệu** > **Nguồn dữ liệu**.

2. Cạnh nguồn dữ liệu mà bạn muốn thay đổi, hãy chọn dấu chấm lửng.

3. Nhấp vào tùy chọn **Chỉnh sửa** trong danh sách.

4. Nếu muốn, hãy thay đổi **Mã truy cập** rồi chọn **Tiếp**.

   ![Hộp thoại để chỉnh sửa và cập nhật mã truy cập cho nguồn dữ liệu hiện tại.](media/edit-access-key.png)

5. Theo tùy chọn, bạn có thể cập nhật từ kết nối khóa tài khoản thành kết nối dựa trên tài nguyên hoặc dựa trên đăng ký. Để biết thêm thông tin, hãy xem [Kết nối với một Azure Data Lake Storage Tài khoản Gen2 có gốc dịch vụ Azure](connect-service-principal.md). Bạn không thể thay đổi thông tin **Vùng chứa** khi cập nhật kết nối.
   > [!div class="mx-imgBorder"]

   > ![Hộp thoại để nhập chi tiết kết nối cho Azure Data Lake với tài khoản lưu trữ hiện có.](media/enter-existing-storage-details.png)

   > [!NOTE]
   > Bạn cần một trong các vai trò sau đối với vùng chứa hoặc tài khoản lưu trữ được đề cập ở trên để có thể kết nối và tạo nguồn dữ liệu:
   >  - Bộ đọc dữ liệu khối lưu trữ
   >  - Chủ sở hữu dữ liệu khối lưu trữ
   >  - Người đóng góp dữ liệu khối lưu trữ


6. Tùy chọn, hãy chọn tệp model.json hoặc tệp manifest.json khác với một nhóm thực thể khác từ vùng chứa.

7. Theo tùy chọn, bạn có thể chọn các thực thể bổ sung để nhập. Bạn cũng có thể xóa mọi thực thể đã chọn nếu không có phụ thuộc.

   > [!IMPORTANT]
   > Nếu có các phần phụ thuộc vào tệp model.json hoặc tệp manifest.json hiện có và tập hợp các thực thể, bạn sẽ thấy thông báo lỗi và không thể chọn tệp model.json hoặc tệp manifest.json khác. Hãy xóa các phần phụ thuộc đó trước khi thay đổi tệp model.json hoặc tệp manifest.json hoặc tạo một nguồn dữ liệu mới với tệp model.json hoặc tệp manifest.json mà bạn muốn sử dụng để tránh xóa các phần phụ thuộc.

8. Theo tùy chọn, bạn có thể chọn các thuộc tính hoặc thực thể bổ sung để bật hoặc tắt phân tích chất lượng dữ liệu đã được chọn.   


[!INCLUDE [footer-include](includes/footer-banner.md)]
