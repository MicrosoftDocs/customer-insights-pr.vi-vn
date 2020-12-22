---
title: Làm mới gia tăng cho các nguồn dữ liệu dựa trên Power Query
description: Làm mới dữ liệu mới và cập nhật cho các nguồn dữ liệu lớn dựa trên Power Query.
ms.date: 09/28/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b7e834f5f2fd1328563139675d7f850008348734
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407324"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a>Làm mới gia tăng cho các nguồn dữ liệu dựa trên Power Query

Làm mới gia tăng cho các nguồn dữ liệu cung cấp các lợi ích sau:

- **Làm mới nhanh hơn** - Chỉ dữ liệu đã thay đổi được làm mới. Ví dụ: bạn có thể chỉ làm mới năm ngày qua của bộ dữ liệu lịch sử.
- **Tăng độ tin cậy** - Với các lần làm mới nhỏ hơn, bạn không cần duy trì kết nối với các hệ thống nguồn hay thay đổi trong thời gian dài, giảm nguy cơ xảy ra sự cố kết nối.
- **Giảm tiêu thụ nguồn lực** - Chỉ làm mới một tập hợp con trong tổng số dữ liệu của bạn dẫn đến việc sử dụng nguồn lực máy tính hiệu quả hơn và giảm dấu chân môi trường.

## <a name="configure-incremental-refresh"></a>Đặt cấu hình làm mới gia tăng

Thông tin chi tiết về đối tượng cho phép làm mới gia tăng các nguồn dữ liệu được nhập thông qua Power Query hỗ trợ nhập tăng dần. Ví dụ: cơ sở dữ liệu Azure SQL với các trường ngày và thời gian, cho biết thời điểm các bản ghi dữ liệu được cập nhật lần cuối.

1. [Tạo nguồn dữ liệu mới dựa trên Power Query](connect-power-query.md).

1. Cung cấp tên cho nguồn dữ liệu.

1. Chọn nguồn dữ liệu hỗ trợ làm mới tăng dần, chẳng hạn như cơ sở dữ liệu Azure SQL.

1. Chọn các thực thể hoặc bảng để nhập.

1. Hoàn thành các bước chuyển đổi và chọn **Tiếp theo**.

1. Trong hộp thoại **Thiết lập làm mới tăng dần**, chọn **Thiết lập** để mở **Thiết đặt làm mới tăng dần**. Nếu bạn chọn **Bỏ qua**, nguồn dữ liệu sẽ làm mới toàn bộ tập dữ liệu.
   > [!TIP]
   > Bạn cũng có thể áp dụng làm mới gia tăng sau bằng cách chỉnh sửa nguồn dữ liệu hiện có.

1. Trên **Thiết đặt làm mới tăng dần**, bạn sẽ định cấu hình làm mới tăng dần cho tất cả các thực thể mà bạn đã chọn khi tạo nguồn dữ liệu.

   > [!div class="mx-imgBorder"]
   > ![Định cấu hình các thực thể trong nguồn dữ liệu để làm mới tăng dần](media/incremental-refresh-settings.png "Định cấu hình các thực thể trong nguồn dữ liệu để làm mới tăng dần")

1. Chọn một thực thể và cung cấp các chi tiết sau:

   - **Xác định khóa chính**: Chọn khóa chính cho thực thể hoặc bảng.
   - **Xác định trường "cập nhật lần cuối"**: Trường này sẽ chỉ hiển thị các thuộc tính của loại ngày hoặc thời gian. Chọn một thuộc tính cho biết thời điểm các bản ghi được cập nhật lần cuối. Nó sẽ được sử dụng để xác định các bản ghi nằm trong khung thời gian làm mới gia tăng.
   - **Kiểm tra cập nhật mỗi**: Chỉ định khoảng thời gian bạn muốn cho khung thời gian làm mới tăng dần.

1. Chọn **Lưu** để hoàn thành việc tạo nguồn dữ liệu. Làm mới dữ liệu ban đầu sẽ là một làm mới đầy đủ. Sau đó, làm mới dữ liệu gia tăng xảy ra như được cấu hình ở bước trước.
