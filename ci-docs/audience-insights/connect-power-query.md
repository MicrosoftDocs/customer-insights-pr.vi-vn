---
title: Nhập dữ liệu thông qua Power Query trình kết nối (chứa video)
description: Kết nối cho các nguồn dữ liệu dựa trên Power Query.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: aae49be4364676ecc7a307e60eeca13859f1662a
ms.sourcegitcommit: 9132fdf54070cc551ab878378078e6285852818f
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 12/18/2021
ms.locfileid: "7935004"
---
# <a name="connect-to-a-power-query-data-source"></a>Kết nối với một Power Query nguồn dữ liệu

Power Query cung cấp một loạt các trình kết nối để nhập dữ liệu. Hầu hết các trình kết nối này được hỗ trợ bởi Dynamics 365 Customer Insights. 

Thêm nguồn dữ liệu dựa trên Power Query trình kết nối thường tuân theo các bước được nêu trong phần này. Tuy nhiên, tùy thuộc vào trình kết nối bạn sử dụng, bạn sẽ cần dùng thông tin khác nhau. Để tìm hiểu thêm, hãy xem tài liệu về các trình kết nối riêng lẻ trong [Power Query tham chiếu trình kết nối](/power-query/connectors/).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>Tạo một nguồn dữ liệu mới

1. Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Dữ liệu** > **Nguồn dữ liệu**.

1. Chọn **Thêm nguồn dữ liệu**.

1. Lựa chọn **Microsoft Power Query**, sau đó chọn **Kế tiếp**.

1. Cung cấp một **Tên** cho nguồn dữ liệu và chọn **Tiếp theo** để tạo nguồn dữ liệu.

1. Chọn một trong các [trình kết nối có sẵn](#available-power-query-data-sources). Trong ví dụ này, chúng tôi chọn **Văn bản / CSV** tư nối.

1. Nhập các chi tiết được yêu cầu trong **Cài đặt kết nối** cho trình kết nối đã chọn và chọn **Tiếp theo** để xem bản xem trước của dữ liệu.

1. Chọn **Chuyển đổi dữ liệu**. Trong bước này, bạn sẽ thêm các thực thể vào nguồn dữ liệu của mình. Thực thể là tập dữ liệu. Nếu bạn có một cơ sở dữ liệu bao gồm nhiều bộ dữ liệu, mỗi bộ dữ liệu là thực thể riêng của nó.

1. Các **Power Query - Chỉnh sửa các truy vấn** cho phép bạn xem lại và tinh chỉnh dữ liệu. Các thực thể mà các hệ thống được xác định trong nguồn dữ liệu đã chọn của bạn xuất hiện trong ngăn bên trái.

   > [!div class="mx-imgBorder"]
   > ![Hộp thoại Chỉnh sửa truy vấn.](media/data-manager-configure-edit-queries.png "Hộp thoại Chỉnh sửa truy vấn")

1. Bạn cũng có thể chuyển đổi dữ liệu của bạn. Chọn một thực thể để chỉnh sửa hoặc chuyển đổi. Sử dụng các tùy chọn trong Power Query cửa sổ để áp dụng các phép biến đổi. Mỗi chuyển đổi được liệt kê dưới **Các bước đã áp dụng**. Power Query cung cấp nhiều tùy chọn chuyển đổi được xây dựng trước. Để biết thêm thông tin, hãy xem [Power Query Sự biến đổi](/power-query/power-query-what-is-power-query#transformations).

1. Bạn có thể thêm các thực thể bổ sung vào nguồn dữ liệu của mình bằng cách chọn **Lấy dữ liệu** trong hộp thoại **Chỉnh sửa truy vấn**.

   Chúng tôi khuyên bạn nên sử dụng các biến đổi sau:

   - Nếu bạn đang nhập dữ liệu từ tệp CSV, hàng đầu tiên thường chứa các tiêu đề. Đi đến **Bảng biến đổi** và chọn **Sử dụng tiêu đề làm hàng đầu tiên**.
   - Đảm bảo loại dữ liệu được đặt phù hợp.

1. Lựa chọn **Cứu** ở cuối Power Query cửa sổ để lưu các phép biến đổi. Sau khi lưu, bạn sẽ thấy nguồn dữ liệu của mình trên **Dữ liệu** > **Nguồn dữ liệu**.

1. Trên trang **Nguồn dữ liệu**, bạn sẽ nhận thấy nguồn dữ liệu mới ở trạng thái **Làm mới**.

## <a name="available-power-query-data-sources"></a>Có sẵn Power Query nguồn dữ liệu

Xem [Power Query tham chiếu kết nối](/power-query/connectors/) để biết danh sách các trình kết nối mà bạn có thể sử dụng để nhập dữ liệu vào Thông tin chi tiết về khách hàng. 

Các trình kết nối có dấu kiểm trong **Thông tin chi tiết về khách hàng (Luồng dữ liệu)** cột có sẵn để tạo nguồn dữ liệu mới dựa trên Power Query. Xem lại tài liệu về một trình kết nối cụ thể để tìm hiểu thêm về các điều kiện tiên quyết, giới hạn và các chi tiết khác của nó.

## <a name="edit-power-query-data-sources"></a>Biên tập Power Query nguồn dữ liệu

> [!NOTE]
> Có thể không thực hiện được thay đổi đối với các nguồn dữ liệu hiện đang được sử dụng trong một trong các quy trình của ứng dụng (*phân khúc*, *so khớp* hoặc *hợp nhất*). 
>
> Bên trong **Cài đặt**, bạn có thể theo dõi tiến trình của từng quy trình đang hoạt động. Khi một quá trình hoàn tất, bạn có thể quay lại trang **Nguồn dữ liệu** và thực hiện các thay đổi của bạn.

1. Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Dữ liệu** > **Nguồn dữ liệu**.

2. Chọn dấu 3 chấm dọc bên cạnh nguồn dữ liệu bạn muốn thay đổi và chọn **Chỉnh sửa** từ menu thả xuống.

   > [!div class="mx-imgBorder"]
   > ![Tùy chọn chỉnh sửa.](media/edit-option-data-sources.png "Tùy chọn chỉnh sửa")

   [!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]
   
3. Áp dụng các thay đổi và chuyển đổi của bạn trong **Power Query - Chỉnh sửa các truy vấn** hộp thoại như được mô tả trong [Tạo nguồn dữ liệu mới](#create-a-new-data-source) tiết diện.

4. Lựa chọn **Cứu** trong Power Query sau khi hoàn thành các chỉnh sửa của bạn để lưu các thay đổi của bạn.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
