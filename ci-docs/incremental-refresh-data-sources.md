---
title: Làm mới gia tăng cho Power Query nguồn dữ liệu dựa trên
description: Làm mới dữ liệu mới và cập nhật cho các nguồn dữ liệu lớn dựa trên Power Query.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: 3d21baf9804f300802b066df0183fc8f01abba9a
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 04/27/2022
ms.locfileid: "8644118"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a>Làm mới gia tăng cho các nguồn dữ liệu dựa trên Power Query

Bài viết này thảo luận về cách định cấu hình làm mới gia tăng cho các nguồn dữ liệu dựa trên Power Query.

Làm mới gia tăng cho các nguồn dữ liệu cung cấp các lợi ích sau:

- **Làm mới nhanh hơn** - Chỉ dữ liệu đã thay đổi được làm mới. Ví dụ: bạn có thể chỉ làm mới năm ngày qua của bộ dữ liệu lịch sử.
- **Tăng độ tin cậy** - Với các lần làm mới nhỏ hơn, bạn không cần duy trì kết nối với các hệ thống nguồn hay thay đổi trong thời gian dài, giảm nguy cơ xảy ra sự cố kết nối.
- **Giảm tiêu thụ nguồn lực** - Chỉ làm mới một tập hợp con trong tổng số dữ liệu của bạn dẫn đến việc sử dụng nguồn lực máy tính hiệu quả hơn và giảm dấu chân môi trường.

## <a name="configure-incremental-refresh"></a>Đặt cấu hình chế độ làm mới gia tăng

Thông tin chi tiết về khách hàng cho phép làm mới gia tăng các nguồn dữ liệu được nhập qua Power Query hỗ trợ quá trình nhập tăng dần. Ví dụ: cơ sở dữ liệu Azure SQL với các trường ngày và thời gian, cho biết thời điểm các bản ghi dữ liệu được cập nhật lần cuối.

1. [Tạo nguồn dữ liệu mới dựa trên Power Query](connect-power-query.md).

1. Cung cấp một **Tên** cho nguồn dữ liệu.

1. Chọn nguồn dữ liệu hỗ trợ làm mới gia tăng, chẳng hạn như [Cơ sở dữ liệu Azure SQL](/power-query/connectors/azuresqldatabase).

1. Chọn các thực thể hoặc bảng để nhập.

1. Hoàn thành các bước chuyển đổi và chọn **Tiếp theo**.

1. Trong hộp thoại **Thiết lập làm mới tăng dần**, chọn **Thiết lập** để mở **Thiết đặt làm mới tăng dần**. Nếu bạn chọn **Bỏ qua**, nguồn dữ liệu sẽ làm mới toàn bộ tập dữ liệu.
   > [!TIP]
   > Bạn cũng có thể áp dụng làm mới gia tăng sau bằng cách chỉnh sửa nguồn dữ liệu hiện có.

1. Trên **Thiết đặt làm mới tăng dần**, bạn sẽ định cấu hình làm mới tăng dần cho tất cả các thực thể mà bạn đã chọn khi tạo nguồn dữ liệu.

   :::image type="content" source="media/incremental-refresh-settings.png" alt-text="Định cấu hình các thực thể trong nguồn dữ liệu để làm mới gia tăng.":::

1. Chọn một thực thể và cung cấp các chi tiết sau:

   - **Xác định khóa chính**: Chọn khóa chính cho thực thể hoặc bảng.
   - **Xác định trường "cập nhật lần cuối"**: Trường này sẽ chỉ hiển thị các thuộc tính của loại ngày hoặc thời gian. Chọn một thuộc tính cho biết thời điểm các bản ghi được cập nhật lần cuối. Nó sẽ được sử dụng để xác định các bản ghi nằm trong khung thời gian làm mới gia tăng.
   - **Kiểm tra cập nhật mỗi**: Chỉ định khoảng thời gian bạn muốn cho khung thời gian làm mới tăng dần.

1. Chọn **Lưu** để hoàn thành việc tạo nguồn dữ liệu. Làm mới dữ liệu ban đầu sẽ là một làm mới đầy đủ. Sau đó, làm mới dữ liệu gia tăng xảy ra như được cấu hình ở bước trước.


[!INCLUDE [footer-include](includes/footer-banner.md)]
