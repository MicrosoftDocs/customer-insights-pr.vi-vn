---
title: Sử dụng nguồn dữ liệu để nhập dữ liệu
description: Tìm hiểu cách nhập dữ liệu từ nhiều nguồn khác nhau.
ms.date: 12/06/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: overview
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
---

# <a name="data-sources-overview"></a>Tổng quan về nguồn dữ liệu



Khả năng thông tin chi tiết về đối tượng trong Dynamics 365 Customer Insights kết nối với dữ liệu từ nhiều nguồn. Kết nối với nguồn dữ liệu thường được gọi là quá trình *nhập dữ liệu*. Sau khi nhập dữ liệu, bạn có thể [thống nhất](data-unification.md) và thực hiện hành động trên nó.

## <a name="add-a-data-source"></a>Thêm nguồn dữ liệu

Tham khảo các bài viết chi tiết để biết cách thêm nguồn dữ liệu, tùy thuộc vào tùy chọn bạn chọn.

Bạn có thể thêm các nguồn dữ liệu sau:

- [Power Query đầu nối](connect-power-query.md)
- [Common Data Model](connect-common-data-model.md)
- [Microsoft Dataverse Hồ](connect-dataverse-managed-lake.md)

> [!NOTE]
> Nếu bạn đang sử dụng phiên bản dùng thử, phần phương pháp nhập bao gồm **Thư viện dữ liệu Thông tin chi tiết về khách hàng** lựa chọn. Chọn tùy chọn này để chọn một tập dữ liệu mẫu có sẵn cho các ngành khác nhau. Để biết thêm thông tin, hãy xem [Dynamics 365 Customer Insights thử nghiệm](../trial-signup.md).

## <a name="add-data-from-on-premises-data-sources"></a>Thêm dữ liệu từ nguồn dữ liệu tại chỗ

Việc nhập dữ liệu từ nguồn dữ liệu tại chỗ trong thông tin chuyên sâu về đối tượng được hỗ trợ dựa trên luồng dữ liệu Microsoft Power Platform. Bạn có thể bật Luồng dữ liệu trong Thông tin chi tiết về khách hàng bằng cách [cung cấp Microsoft Dataverse URL môi trường](create-environment.md) khi thiết lập môi trường.

Nguồn dữ liệu được tạo sau khi liên kết Dataverse môi trường sử dụng Thông tin chi tiết về khách hàng [Power Platform luồng dữ liệu](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) theo mặc định. Luồng dữ liệu hỗ trợ kết nối tại chỗ bằng cách sử dụng cổng dữ liệu. Bạn có thể xóa và tạo lại các nguồn dữ liệu đã tồn tại trước Dataverse môi trường được liên kết [sử dụng cổng dữ liệu tại chỗ](/data-integration/gateway/service-gateway-app).

Cổng dữ liệu từ một môi trường Power BI hoặc Power Apps hiện có sẽ hiển thị và bạn có thể sử dụng lại trong Customer Insights. Trang nguồn dữ liệu hiển thị các liên kết đi đến môi trường Microsoft Power Platform nơi bạn có thể xem và định cấu hình cổng dữ liệu tại chỗ.

## <a name="review-ingested-data"></a>Xem lại dữ liệu đã nhập

Bạn sẽ thấy tên của mỗi nguồn dữ liệu đã nhập, trạng thái của nó và lần cuối cùng dữ liệu được làm mới cho nguồn đó. Bạn có thể sắp xếp danh sách nguồn dữ liệu theo mọi cột.

> [!div class="mx-imgBorder"]
> ![Nguồn dữ liệu đã thêm.](media/configure-data-datasource-added.png "Nguồn dữ liệu đã thêm")

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

Quá trình tải dữ liệu có thể mất một khoảng thời gian. Sau khi làm mới thành công, dữ liệu đã nhập có thể được xem xét từ trang **Các thực thể**. Để biết thêm thông tin, hãy xem [Các thực thể](entities.md).

## <a name="refresh-a-data-source"></a>Làm mới nguồn dữ liệu

Nguồn dữ liệu có thể được làm mới theo lịch trình tự động hoặc được làm mới theo cách thủ công theo yêu cầu. 

Đi đến **Quản trị viên** > **Hệ thống** > [**Lịch trình**](system.md#schedule-tab) để định cấu hình làm mới theo lịch của tất cả các nguồn dữ liệu đã nhập của bạn.

Để làm mới nguồn dữ liệu theo yêu cầu, hãy làm theo các bước sau:

1. Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Dữ liệu** > **Nguồn dữ liệu**.

2. Chọn dấu 3 chấm dọc bên cạnh nguồn dữ liệu bạn muốn làm mới và chọn **Làm mới** từ danh sách thả xuống.

3. Nguồn dữ liệu hiện đã được kích hoạt để làm mới thủ công. Việc làm mới nguồn dữ liệu sẽ cập nhật cả giản đồ thực thể và dữ liệu cho tất cả các thực thể được chỉ định trong nguồn dữ liệu.

4. Chọn **Dừng làm mới** nếu bạn muốn hủy quá trình làm mới hiện có và nguồn dữ liệu sẽ hoàn nguyên về trạng thái làm mới cuối cùng.

## <a name="delete-a-data-source"></a>Xóa nguồn dữ liệu

1. Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Dữ liệu** > **Nguồn dữ liệu**.

2. Chọn dấu 3 chấm dọc bên cạnh nguồn dữ liệu bạn muốn loại bỏ và chọn **Xóa** từ menu thả xuống.

3. Xác nhận tác vụ xóa của bạn.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
