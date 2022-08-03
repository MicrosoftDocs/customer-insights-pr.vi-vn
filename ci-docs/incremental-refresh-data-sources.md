---
title: Làm mới gia tăng cho Power Query và nguồn dữ liệu Azure Data Lake
description: Làm mới dữ liệu mới và cập nhật cho các nguồn dữ liệu lớn dựa trên Power Query hoặc các nguồn dữ liệu hồ dữ liệu Azure.
ms.date: 05/30/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: de39743eb8728fac34e417724c5f73bf44309c89
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 07/28/2022
ms.locfileid: "9207163"
---
# <a name="incremental-refresh-for-power-query-and-azure-data-lake-data-sources"></a>Làm mới gia tăng cho Power Query và nguồn dữ liệu Azure Data Lake

Làm mới gia tăng cho các nguồn dữ liệu dựa trên Power Query hoặc Azure Data Lake cung cấp những ưu điểm sau:

- **Làm mới nhanh hơn** - Chỉ dữ liệu đã thay đổi được làm mới. Ví dụ: bạn có thể chỉ làm mới năm ngày qua của bộ dữ liệu lịch sử.
- **Tăng độ tin cậy** - Với các lần làm mới nhỏ hơn, bạn không cần duy trì kết nối với các hệ thống nguồn hay thay đổi trong thời gian dài, giảm nguy cơ xảy ra sự cố kết nối.
- **Giảm tiêu thụ nguồn lực** - Chỉ làm mới một tập hợp con trong tổng số dữ liệu của bạn dẫn đến việc sử dụng nguồn lực máy tính hiệu quả hơn và giảm dấu chân môi trường.

## <a name="configure-incremental-refresh-for-data-sources-based-on-power-query"></a>Định cấu hình làm mới gia tăng cho các nguồn dữ liệu dựa trên Power Query

Thông tin chi tiết về khách hàng cho phép làm mới gia tăng các nguồn dữ liệu được nhập qua Power Query hỗ trợ quá trình nhập tăng dần. Ví dụ: cơ sở dữ liệu Azure SQL với các trường ngày và thời gian, cho biết thời điểm các bản ghi dữ liệu được cập nhật lần cuối.

1. [Tạo nguồn dữ liệu mới dựa trên Power Query](connect-power-query.md).

1. Chọn nguồn dữ liệu hỗ trợ làm mới gia tăng, chẳng hạn như [Cơ sở dữ liệu Azure SQL](/power-query/connectors/azuresqldatabase).

1. Chọn các thực thể hoặc bảng để nhập.

1. Hoàn thành các bước chuyển đổi và chọn **Tiếp theo**.

1. Trong hộp thoại **Thiết lập làm mới tăng dần**, chọn **Thiết lập** để mở **Thiết đặt làm mới tăng dần**. Nếu bạn chọn **Bỏ qua**, nguồn dữ liệu sẽ làm mới toàn bộ tập dữ liệu.
   > [!TIP]
   > Bạn cũng có thể áp dụng làm mới gia tăng sau bằng cách chỉnh sửa nguồn dữ liệu hiện có.

1. Trên **Thiết đặt làm mới tăng dần**, bạn sẽ định cấu hình làm mới tăng dần cho tất cả các thực thể mà bạn đã chọn khi tạo nguồn dữ liệu.

   :::image type="content" source="media/incremental-refresh-settings.png" alt-text="Định cấu hình cài đặt làm mới gia tăng.":::

1. Chọn một thực thể và cung cấp các chi tiết sau:

   - **Xác định khóa chính**: Chọn khóa chính cho thực thể hoặc bảng.
   - **Xác định trường "cập nhật lần cuối"**: Trường này sẽ chỉ hiển thị các thuộc tính của loại ngày hoặc thời gian. Chọn một thuộc tính cho biết thời điểm các bản ghi được cập nhật lần cuối. Nó sẽ được sử dụng để xác định các bản ghi nằm trong khung thời gian làm mới gia tăng.
   - **Kiểm tra cập nhật mỗi**: Chỉ định khoảng thời gian bạn muốn cho khung thời gian làm mới tăng dần.

1. Chọn **Lưu** để hoàn thành việc tạo nguồn dữ liệu. Làm mới dữ liệu ban đầu sẽ là một làm mới đầy đủ. Sau đó, làm mới dữ liệu gia tăng xảy ra như được cấu hình ở bước trước.

## <a name="configure-incremental-refresh-for-azure-data-lake-data-sources"></a>Định cấu hình làm mới gia tăng cho các nguồn dữ liệu Azure Data Lake

Thông tin chi tiết về khách hàng cho phép làm mới gia tăng các nguồn dữ liệu được kết nối với Azure Data Lake Storage. Để sử dụng tính năng nhập và làm mới gia tăng cho một thực thể, hãy định cấu hình thực thể đó khi thêm Azure Data Lake nguồn dữ liệu trở lên khi chỉnh sửa nguồn dữ liệu. Thư mục dữ liệu thực thể phải chứa các thư mục sau:

- **FullData** : Thư mục chứa các tệp dữ liệu chứa các bản ghi ban đầu
- **Dữ liệu tăng dần** : Thư mục với các thư mục phân cấp ngày / giờ trong **yyyy / mm / dd / hh** định dạng có chứa các bản cập nhật gia tăng. **hh** đại diện cho giờ UTC của các bản cập nhật và chứa **Cảnh báo** và **Xóa** thư mục. **Cảnh báo** chứa các tệp dữ liệu với các cập nhật cho các bản ghi hiện có hoặc các bản ghi mới. **Xóa** chứa các tệp dữ liệu với các bản ghi cần loại bỏ.

1. Khi thêm hoặc chỉnh sửa nguồn dữ liệu, hãy điều hướng đến **Thuộc tính** ngăn cho thực thể.

1. Xem lại các thuộc tính. Đảm bảo thuộc tính ngày được tạo hoặc cập nhật lần cuối được thiết lập với *ngày giờ* **Định dạng dữ liệu** và một *Lịch. Ngày* **Loại ngữ nghĩa**. Chỉnh sửa thuộc tính nếu cần và chọn **Xong**.

1. Từ **Chọn thực thể**, chỉnh sửa thực thể. Các **Ăn uống gia tăng** hộp kiểm được chọn.

   :::image type="content" source="media/ADLS_inc_refresh.png" alt-text="Định cấu hình các thực thể trong nguồn dữ liệu để làm mới gia tăng.":::

   1. Duyệt đến thư mục gốc có chứa các tệp .csv hoặc .parquet để có dữ liệu đầy đủ, bổ sung dữ liệu gia tăng và xóa dữ liệu gia tăng.
   1. Nhập phần mở rộng cho toàn bộ dữ liệu và cả hai tệp gia tăng (\. csv hoặc\. sàn gỗ).
   1. Đối với tệp .csv, hãy chọn dấu phân cách cột và nếu bạn muốn hàng đầu tiên của tệp làm tiêu đề cột.
   1. Chọn **Lưu.**

1. Vì **Cập nhật mới nhất**, chọn thuộc tính dấu thời gian ngày.

1. Nếu **Khóa chính** không được chọn, hãy chọn khóa chính. Khóa chính là một thuộc tính duy nhất của thực thể. Để một thuộc tính là khóa chính hợp lệ, thuộc tính đó không được bao gồm các giá trị trùng lặp, giá trị bị thiếu hoặc giá trị rỗng. Các thuộc tính kiểu dữ liệu chuỗi, số nguyên và GUID được hỗ trợ làm khóa chính.

1. Lựa chọn **Đóng** để lưu và đóng ngăn.

1. Tiếp tục thêm hoặc chỉnh sửa nguồn dữ liệu.

[!INCLUDE [footer-include](includes/footer-banner.md)]
