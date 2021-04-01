---
title: Sử dụng nguồn dữ liệu để nhập dữ liệu
description: Tìm hiểu cách nhập dữ liệu từ nhiều nguồn khác nhau.
ms.date: 11/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 780dc61a82d6ed9856a37dc8f164fa946d982bbe
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595973"
---
# <a name="data-sources-overview"></a>Tổng quan về nguồn dữ liệu

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Khả năng thông tin chi tiết về đối tượng trong Dynamics 365 Customer Insights kết nối với dữ liệu từ nhiều nguồn. Kết nối với nguồn dữ liệu thường được gọi là quá trình *nhập dữ liệu*. Sau khi nhập dữ liệu, bạn có thể [thống nhất](data-unification.md) và thực hiện hành động trên nó.

## <a name="add-a-data-source"></a>Thêm nguồn dữ liệu

Tham khảo các bài viết chi tiết về cách thêm nguồn dữ liệu, tùy thuộc vào tùy chọn bạn chọn.

Bạn có thể thêm nguồn dữ liệu theo ba cách chính:

- [Thông qua hàng chục trình kết nối Power Query](connect-power-query.md)
- [Từ thư mục Common Data Model](connect-common-data-model.md)
- [Từ kho lưu trữ Common Data Service của riêng bạn](connect-common-data-service-lake.md)

> [!NOTE]
> Bạn chưa thể thêm dữ liệu từ nguồn dữ liệu tại chỗ.

## <a name="review-ingested-data"></a>Xem lại dữ liệu đã nhập

Bạn sẽ thấy tên của mỗi nguồn dữ liệu đã nhập, trạng thái của nó và lần cuối cùng dữ liệu được làm mới cho nguồn đó. Bạn có thể sắp xếp danh sách nguồn dữ liệu theo mọi cột.

> [!div class="mx-imgBorder"]
> ![Nguồn dữ liệu đã thêm](media/configure-data-datasource-added.png "Nguồn dữ liệu đã thêm")

|Trạng thái  |Nội dung mô tả  |
|---------|---------|
|Thành công   |Nguồn dữ liệu đã được nhập thành công nếu thời gian được đề cập trong cột **Làm mới**.
|Chưa bắt đầu   |Nguồn dữ liệu chưa nhập dữ liệu nào hoặc vẫn ở chế độ nháp.         |
|Làm mới    |Đang nhập dữ liệu. Bạn có thể hủy thao tác này bằng cách chọn **Ngừng làm mới** trong cột **Hành động**. Dừng việc làm mới nguồn dữ liệu sẽ hoàn nguyên nguồn dữ liệu về trạng thái làm mới cuối cùng.       |
|Không thành công     |Phiên nhập dữ liệu gặp lỗi.         |

Chọn giá trị trong cột **Trạng thái** của bất kỳ nguồn dữ liệu nào để xem xét thêm chi tiết. Trong ngăn **Chi tiết tiến độ**, hãy mở rộng **Nguồn dữ liệu**. Chọn **Xem chi tiết** để xem thêm thông tin về trạng thái làm mới, bao gồm chi tiết lỗi và cập nhật quy trình xuôi dòng.

Việc tải dữ liệu có thể mất chút thời gian. Sau khi làm mới thành công, dữ liệu đã nhập có thể được xem xét từ trang **Các thực thể**. Để biết thêm thông tin, hãy xem [Các thực thể](entities.md).

## <a name="refresh-a-data-source"></a>Làm mới nguồn dữ liệu

Nguồn dữ liệu có thể được làm mới theo lịch trình tự động hoặc được làm mới theo cách thủ công theo yêu cầu. 

Đi đến **Quản trị viên** > **Hệ thống** > [**Lịch trình**](system.md#schedule-tab) để định cấu hình làm mới theo lịch của tất cả các nguồn dữ liệu đã nhập của bạn.

Để làm mới nguồn dữ liệu theo yêu cầu, hãy làm theo các bước sau:

1. Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Dữ liệu** > **Nguồn dữ liệu**

2. Chọn dấu ba chấm dọc bên cạnh nguồn dữ liệu bạn muốn làm mới và chọn **Làm mới** từ danh sách thả xuống.

3. Nguồn dữ liệu hiện đã được kích hoạt để làm mới thủ công. Làm mới nguồn dữ liệu sẽ cập nhật cả giản đồ thực thể cũng như dữ liệu cho tất cả các thực thể được chỉ định trong nguồn dữ liệu.

4. Chọn **Dừng làm mới** nếu bạn muốn hủy quá trình làm mới hiện có và nguồn dữ liệu sẽ hoàn nguyên về trạng thái làm mới cuối cùng.

## <a name="delete-a-data-source"></a>Xóa nguồn dữ liệu

1. Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Dữ liệu** > **Nguồn dữ liệu**.

2. Chọn dấu chấm lửng dọc bên cạnh nguồn dữ liệu bạn muốn xóa và chọn **Xóa** từ menu thả xuống.

3. Xác nhận tác vụ xóa của bạn.


[!INCLUDE[footer-include](../includes/footer-banner.md)]