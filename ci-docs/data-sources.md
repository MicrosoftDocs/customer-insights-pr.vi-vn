---
title: Sử dụng nguồn dữ liệu để nhập dữ liệu
description: Tìm hiểu cách nhập dữ liệu từ nhiều nguồn khác nhau.
ms.date: 05/31/2022
ms.subservice: audience-insights
ms.topic: overview
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: e22977107565a0b28b74f41576a1c7ccc74f6dc1
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011775"
---
# <a name="data-sources-overview"></a>Tổng quan về nguồn dữ liệu

Dynamics 365 Customer Insights cung cấp các kết nối để mang dữ liệu từ nhiều nguồn khác nhau. Kết nối với nguồn dữ liệu thường được gọi là quá trình *nhập dữ liệu*. Sau khi nhập dữ liệu, bạn có thể [thống nhất](data-unification.md), tạo thông tin chi tiết và kích hoạt dữ liệu để xây dựng trải nghiệm được cá nhân hóa.

## <a name="add-data-sources"></a>Thêm nguồn dữ liệu

Bạn có thể đính kèm hoặc nhập nguồn dữ liệu vào Thông tin chi tiết về khách hàng. Các liên kết bên dưới cung cấp hướng dẫn về cách thêm nguồn dữ liệu.

**Đính kèm nguồn dữ liệu**

Nếu bạn đã chuẩn bị dữ liệu ở một trong các dịch vụ dữ liệu Azure của Microsoft, thì Customer Insights có thể dễ dàng kết nối với nguồn dữ liệu mà không cần phải nhập lại dữ liệu. Chọn một trong các tùy chọn sau:
- [Azure Data Lake Storage(tệp csv hoặc tệp parquet trong thư mục Mô hình Dữ liệu Chung)](connect-common-data-model.md)
- [Azure Synapse Analytics(Cơ sở dữ liệu hồ)](connect-synapse.md)
- [Microsoft Dataverse hồ dữ liệu](connect-dataverse-managed-lake.md)

**Nhập và chuyển đổi**

Nếu bạn sử dụng nguồn dữ liệu tại chỗ, Microsoft hoặc dữ liệu của bên thứ ba, hãy nhập và chuyển đổi dữ liệu bằng cách sử dụng Power Query các đầu nối.
- [Power Query đầu nối](connect-power-query.md)

## <a name="review-data-sources"></a>Xem lại các nguồn dữ liệu

Nếu môi trường của bạn được định cấu hình để sử dụng bộ nhớ Thông tin chi tiết về khách hàng và bạn sử dụng các nguồn dữ liệu tại chỗ, bạn sẽ sử dụng Power Platform luồng dữ liệu. Với Power Platform luồng dữ liệu, bạn có thể xem các nguồn dữ liệu được chia sẻ và các nguồn dữ liệu do người khác quản lý. Các **Nguồn dữ liệu** trang liệt kê các nguồn dữ liệu trong ba phần:
- **Được chia sẻ** : Nguồn dữ liệu có thể được quản lý bởi tất cả các quản trị viên Thông tin chi tiết về khách hàng. Power Platform luồng dữ liệu, tài khoản lưu trữ của riêng bạn và đính kèm vào Dataverse hồ dữ liệu được quản lý là những ví dụ về các nguồn dữ liệu được chia sẻ.
- **Do tôi quản lý** :Power Platform luồng dữ liệu chỉ do bạn tạo và quản lý. Các quản trị viên Thông tin chi tiết khác về khách hàng chỉ có thể xem các luồng dữ liệu này nhưng không thể chỉnh sửa, làm mới hoặc xóa chúng.
- **Do người khác quản lý** :Power Platform luồng dữ liệu do quản trị viên khác tạo. Bạn chỉ có thể xem chúng. Nó liệt kê chủ sở hữu của luồng dữ liệu cần liên hệ để được hỗ trợ.
> [!NOTE]
> Tất cả các thực thể có thể được xem và sử dụng bởi những người dùng khác. Mặc dù các nguồn dữ liệu thuộc sở hữu của người dùng đã tạo ra chúng, nhưng các thực thể kết quả từ quá trình nhập dữ liệu có thể được mọi người dùng của Customer Insights sử dụng.

Nếu môi trường của bạn không sử dụng Power Platform luồng dữ liệu, **Nguồn dữ liệu** trang chỉ chứa danh sách tất cả các nguồn dữ liệu. Không có phần hiển thị.

Đi đến **Dữ liệu** > **Nguồn dữ liệu** để xem tên của từng nguồn dữ liệu đã nhập, trạng thái của nó và lần cuối cùng dữ liệu được làm mới cho nguồn đó. Bạn có thể sắp xếp danh sách nguồn dữ liệu theo mọi cột.

:::image type="content" source="media/configure-data-datasource-added.png" alt-text="Nguồn dữ liệu đã thêm.":::

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Quá trình tải dữ liệu có thể mất một khoảng thời gian. Sau khi làm mới thành công, dữ liệu đã nhập có thể được xem xét từ trang **Các thực thể**. Để biết thêm thông tin, hãy xem [Các thực thể](entities.md).

## <a name="refresh-data-sources"></a>Làm mới nguồn dữ liệu

Nguồn dữ liệu có thể được làm mới theo lịch trình tự động hoặc được làm mới theo cách thủ công theo yêu cầu. [Nguồn dữ liệu tại chỗ](connect-power-query.md#add-data-from-on-premises-data-sources) làm mới lịch biểu của riêng họ được thiết lập trong quá trình nhập dữ liệu. Đối với các nguồn dữ liệu đính kèm, quá trình nhập dữ liệu sẽ sử dụng dữ liệu mới nhất có sẵn từ nguồn dữ liệu đó.

Đi đến **Quản trị viên** > **Hệ thống** > [**Lịch trình**](system.md#schedule-tab) để định cấu hình các lần làm mới theo lịch trình của hệ thống đối với các nguồn dữ liệu đã nhập của bạn.

Để làm mới nguồn dữ liệu theo yêu cầu, hãy làm theo các bước sau:

1. Chuyển tới **Dữ liệu** > **Nguồn dữ liệu**.

1. Chọn dấu chấm lửng dọc (&vellip;) bên cạnh nguồn dữ liệu bạn muốn làm mới và chọn **Làm mới** từ danh sách thả xuống. Nguồn dữ liệu hiện đã được kích hoạt để làm mới thủ công. Việc làm mới nguồn dữ liệu sẽ cập nhật cả giản đồ thực thể và dữ liệu cho tất cả các thực thể được chỉ định trong nguồn dữ liệu.

1. Chọn **Dừng làm mới** nếu bạn muốn hủy quá trình làm mới hiện có và nguồn dữ liệu sẽ hoàn nguyên về trạng thái làm mới cuối cùng.

## <a name="delete-a-data-source"></a>Xóa nguồn dữ liệu

Nguồn dữ liệu chỉ có thể bị xóa nếu dữ liệu không được sử dụng trong bất kỳ quá trình xử lý nào như hợp nhất, thông tin chi tiết, kích hoạt hoặc xuất.

1. Chuyển tới **Dữ liệu** > **Nguồn dữ liệu**.

2. Chọn dấu chấm lửng dọc (&vellip;) bên cạnh nguồn dữ liệu bạn muốn xóa và chọn **Xóa bỏ** từ menu thả xuống.

3. Xác nhận tác vụ xóa của bạn.


[!INCLUDE [footer-include](includes/footer-banner.md)]
