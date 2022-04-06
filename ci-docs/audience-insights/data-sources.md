---
title: Sử dụng nguồn dữ liệu để nhập dữ liệu
description: Tìm hiểu cách nhập dữ liệu từ nhiều nguồn khác nhau.
ms.date: 03/18/2022
ms.subservice: audience-insights
ms.topic: overview
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: 9cf97c3e30d7501ba1f188a0e25a1a103299aa7f
ms.sourcegitcommit: a8e99cf8b23ccc00d76c1dee22afd808a160a5c8
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 03/22/2022
ms.locfileid: "8464100"
---
# <a name="data-sources-overview"></a>Tổng quan về nguồn dữ liệu



Khả năng thông tin chi tiết về đối tượng trong Dynamics 365 Customer Insights kết nối với dữ liệu từ nhiều nguồn. Kết nối với nguồn dữ liệu thường được gọi là quá trình *nhập dữ liệu*. Sau khi nhập dữ liệu, bạn có thể [thống nhất](data-unification.md) và thực hiện hành động trên nó.

## <a name="add-a-data-source"></a>Thêm nguồn dữ liệu

Tham khảo các bài viết chi tiết để biết cách thêm nguồn dữ liệu, tùy thuộc vào tùy chọn bạn chọn.

Bạn có thể thêm các nguồn dữ liệu sau:

- [Qua hàng chục Power Query đầu nối](connect-power-query.md)
- [Từ thư mục Common Data Model](connect-common-data-model.md)
- [Từ kho lưu trữ Microsoft Dataverse của riêng bạn](connect-dataverse-managed-lake.md)
- [Từ một Azure Synapse Analytics cơ sở dữ liệu](connect-synapse.md)

> [!NOTE]
> Nếu bạn đang sử dụng phiên bản dùng thử, phần phương pháp nhập bao gồm **Thư viện dữ liệu Thông tin chi tiết về khách hàng** Lựa chọn. Chọn tùy chọn này để chọn một tập dữ liệu mẫu có sẵn cho các ngành khác nhau. Để biết thêm thông tin, hãy xem [Dynamics 365 Customer Insights sự thử nghiệm](../trial-signup.md).

## <a name="add-data-from-on-premises-data-sources"></a>Thêm dữ liệu từ nguồn dữ liệu tại chỗ

Việc nhập dữ liệu từ nguồn dữ liệu tại chỗ trong thông tin chuyên sâu về đối tượng được hỗ trợ dựa trên luồng dữ liệu Microsoft Power Platform. Bạn có thể bật Luồng dữ liệu trong Thông tin chi tiết về khách hàng bằng cách [cung cấp Microsoft Dataverse URL môi trường](create-environment.md) khi thiết lập môi trường.

Nguồn dữ liệu được tạo sau khi liên kết Dataverse môi trường sử dụng Thông tin chi tiết về khách hàng [Power Platform luồng dữ liệu](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) theo mặc định. Luồng dữ liệu hỗ trợ kết nối tại chỗ bằng cách sử dụng cổng dữ liệu. Bạn có thể xóa và tạo lại các nguồn dữ liệu đã tồn tại trước Dataverse môi trường được liên kết [sử dụng cổng dữ liệu tại chỗ](/data-integration/gateway/service-gateway-app).

Cổng dữ liệu từ một môi trường Power BI hoặc Power Apps hiện có sẽ hiển thị và bạn có thể sử dụng lại trong Customer Insights. Trang nguồn dữ liệu hiển thị các liên kết đi đến môi trường Microsoft Power Platform nơi bạn có thể xem và định cấu hình cổng dữ liệu tại chỗ.

> [!IMPORTANT]
> Đảm bảo rằng các cổng của bạn được cập nhật lên phiên bản mới nhất. Bạn có thể cài đặt bản cập nhật và định cấu hình lại cổng từ lời nhắc hiển thị trực tiếp trên màn hình cổng hoặc [tải xuống phiên bản mới nhất](https://powerapps.microsoft.com/downloads/). Nếu bạn không sử dụng phiên bản cổng mới nhất, quá trình làm mới luồng dữ liệu không thành công với các thông báo lỗi như **Từ khóa không được hỗ trợ: thuộc tính cấu hình. Tên thông số: từ khóa**.

## <a name="review-ingested-data"></a>Xem lại dữ liệu đã nhập
Nếu môi trường của bạn chứa Power Platform luồng dữ liệu, **Nguồn dữ liệu** trang liệt kê ba phần: 
- **Được chia sẻ** : Nguồn dữ liệu có thể được quản lý bởi tất cả các quản trị viên Thông tin chi tiết về khách hàng. Power BI luồng dữ liệu, tài khoản lưu trữ của riêng bạn và đính kèm vào Dataverse hồ dữ liệu được quản lý là những ví dụ về các nguồn dữ liệu được chia sẻ.
- **Do tôi quản lý** :Power Platform luồng dữ liệu được tạo và chỉ bạn mới có thể quản lý. Các quản trị viên Thông tin chi tiết khác về khách hàng chỉ có thể xem các luồng dữ liệu này nhưng không thể chỉnh sửa, làm mới hoặc xóa chúng.
- **Do người khác quản lý** :Power Platform luồng dữ liệu do quản trị viên khác tạo. Bạn chỉ có thể xem chúng. Nó liệt kê chủ sở hữu của luồng dữ liệu cần liên hệ để được hỗ trợ.
> [!NOTE]
> Tất cả các thực thể có thể được xem và sử dụng bởi những người dùng khác. Ngữ cảnh của người dùng chỉ áp dụng cho các nguồn dữ liệu chứ không áp dụng cho các thực thể là kết quả của các luồng dữ liệu này.

Nếu không Power Platform luồng dữ liệu được sử dụng, bạn sẽ không thấy bất kỳ nhóm hoặc phần nào. Các **Nguồn dữ liệu** trang chỉ chứa danh sách tất cả các nguồn dữ liệu.

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
