---
title: Nhập dữ liệu thông qua trình kết nối Power Query
description: Trình kết nối cho nguồn dữ liệu dựa trên Power Query.
ms.date: 09/29/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: b37bb5dfeed2326784ef276a93a04bec626aaf6e
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 07/13/2021
ms.locfileid: "6554723"
---
# <a name="connect-to-a-power-query-data-source"></a>Kết nối với nguồn dữ liệu Power Query

Power Query cung cấp một loạt các trình kết nối để nhập dữ liệu. Hầu hết các trình kết nối này được hỗ trợ bởi Dynamics 365 Customer Insights. Việc thêm nguồn dữ liệu dựa trên trình kết nối Power Query thường tuân theo các bước được nêu trong phần tiếp theo. Tuy nhiên, tùy thuộc vào trình kết nối bạn sử dụng, bạn sẽ cần dùng thông tin khác nhau. Để biết thêm thông tin, hãy xem tài liệu về các trình kết nối riêng lẻ trong [tham khảo trình kết nối Power Query](/power-query/connectors/).

## <a name="create-a-new-data-source"></a>Tạo một nguồn dữ liệu mới

1. Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Dữ liệu** > **Nguồn dữ liệu**.

1. Chọn **Thêm nguồn dữ liệu**.

1. Chọn phương thức **Nhập dữ liệu** và chọn **Tiếp theo**.

1. Cung cấp một **Tên** cho nguồn dữ liệu và chọn **Tiếp theo** để tạo nguồn dữ liệu. Hướng dẫn về tên: 
   - Bắt đầu bằng một chữ cái.
   - Chỉ sử dụng chữ cái và số. Không được phép nhập ký tự đặc biệt và khoảng trống.
   - Sử dụng từ 3 đến 64 ký tự.

1. Chọn một trong các [trình kết nối có sẵn](#available-power-query-data-sources). Đối với ví dụ này, chúng tôi chọn trình kết nối **Văn bản/CSV**.

1. Nhập các chi tiết được yêu cầu trong **Cài đặt kết nối** cho trình kết nối đã chọn và chọn **Tiếp theo** để xem bản xem trước của dữ liệu.

1. Chọn **Chuyển đổi dữ liệu**. Trong bước này, bạn sẽ thêm các thực thể vào nguồn dữ liệu của mình. Thực thể là tập dữ liệu. Nếu bạn có một cơ sở dữ liệu bao gồm nhiều bộ dữ liệu, mỗi bộ dữ liệu là thực thể riêng của nó.

1. Hộp thoại **Power Query - Chỉnh sửa truy vấn** cho phép bạn xem lại và tinh chỉnh dữ liệu. Các thực thể mà các hệ thống được xác định trong nguồn dữ liệu đã chọn của bạn xuất hiện trong ngăn bên trái.

   > [!div class="mx-imgBorder"]
   > ![Hộp thoại Chỉnh sửa truy vấn.](media/data-manager-configure-edit-queries.png "Hộp thoại Chỉnh sửa truy vấn")

1. Bạn cũng có thể chuyển đổi dữ liệu của bạn. Chọn một thực thể để chỉnh sửa hoặc chuyển đổi. Sử dụng các tùy chọn trong cửa sổ Power Query để áp dụng các phép biến đổi. Mỗi chuyển đổi được liệt kê dưới **Các bước đã áp dụng**. Power Query cung cấp nhiều tùy chọn chuyển đổi được tạo sẵn. Xem [Chuyển đổi Power Query](/power-query/power-query-what-is-power-query#transformations) để biết thêm thông tin.

1. Bạn có thể thêm các thực thể bổ sung vào nguồn dữ liệu của mình bằng cách chọn **Lấy dữ liệu** trong hộp thoại **Chỉnh sửa truy vấn**.

   Những chuyển đổi này rất được khuyến khích:

   - Nếu bạn đang nhập dữ liệu từ tệp CSV, hàng đầu tiên thường chứa các tiêu đề. Đi đến **Bảng biến đổi** và chọn **Sử dụng tiêu đề làm hàng đầu tiên**.
   - Đảm bảo loại dữ liệu được đặt phù hợp.

1. Chọn **Lưu** ở góc dưới bên phải cửa sổ Power Query để lưu mục chuyển đổi của bạn. Sau khi lưu, bạn sẽ thấy nguồn dữ liệu của mình trên **Dữ liệu** > **Nguồn dữ liệu**.

1. Trên trang **Nguồn dữ liệu**, bạn sẽ nhận thấy nguồn dữ liệu mới ở trạng thái **Làm mới**.

## <a name="available-power-query-data-sources"></a>Nguồn dữ liệu Power Query có sẵn

Xem [tham khảo trình kết nối Power Query](/power-query/connectors/) để có danh sách cập nhật các trình kết nối mà bạn có thể chọn để nhập dữ liệu vào Customer Insights. 

Các trình kết nối có dấu kiểm trong cột **Customer Insights (Luồng dữ liệu)** có sẵn để tạo nguồn dữ liệu mới dựa trên Power Query. Xem lại tài liệu về một trình kết nối cụ thể để tìm hiểu thêm về các điều kiện tiên quyết, giới hạn và các chi tiết khác của nó.

## <a name="edit-power-query-data-sources"></a>Chỉnh sửa nguồn dữ liệu Power Query

> [!NOTE]
> Có thể không thực hiện được thay đổi đối với các nguồn dữ liệu hiện đang được sử dụng trong một trong các quy trình của ứng dụng (*phân khúc*, *so khớp* hoặc *hợp nhất*). 
>
> Sử dụng trang **Cài đặt**, bạn có thể theo dõi tiến trình của từng quá trình hoạt động. Khi một quá trình hoàn tất, bạn có thể quay lại trang **Nguồn dữ liệu** và thực hiện các thay đổi của bạn.

1. Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Dữ liệu** > **Nguồn dữ liệu**.

2. Chọn dấu 3 chấm dọc bên cạnh nguồn dữ liệu bạn muốn thay đổi và chọn **Chỉnh sửa** từ menu thả xuống.

   > [!div class="mx-imgBorder"]
   > ![Tùy chọn chỉnh sửa.](media/edit-option-data-sources.png "Tùy chọn chỉnh sửa")

3. Áp dụng các thay đổi và chuyển đổi của bạn trong hộp thoại **Power Query - Chỉnh sửa truy vấn** như được mô tả trong phần [Tạo nguồn dữ liệu mới](#create-a-new-data-source).

4. Chọn **Lưu** trong Power Query sau khi hoàn tất các chỉnh sửa để lưu các thay đổi của bạn.


[!INCLUDE[footer-include](../includes/footer-banner.md)]