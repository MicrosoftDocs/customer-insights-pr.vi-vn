---
title: Tổng quan về nguồn dữ liệu
description: Tìm hiểu cách nhập hoặc nhập dữ liệu từ nhiều nguồn khác nhau.
ms.date: 07/26/2022
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
ms.openlocfilehash: 591353bf1ba2f9ca05ddd137e1cf29dc0b0fba97
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245675"
---
# <a name="data-sources-overview"></a>Tổng quan về nguồn dữ liệu

Dynamics 365 Customer Insights cung cấp các kết nối để mang dữ liệu từ nhiều nguồn khác nhau. Kết nối với nguồn dữ liệu thường được gọi là quá trình *nhập dữ liệu*. Sau khi nhập dữ liệu, bạn có thể [thống nhất](data-unification.md), tạo thông tin chi tiết và kích hoạt dữ liệu để xây dựng trải nghiệm được cá nhân hóa.

## <a name="add-or-edit-data-sources"></a>Thêm hoặc chỉnh sửa nguồn dữ liệu

Bạn có thể đính kèm hoặc nhập nguồn dữ liệu vào Thông tin chi tiết về khách hàng. Các liên kết bên dưới cung cấp hướng dẫn về cách thêm và chỉnh sửa nguồn dữ liệu.

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
- **Do tôi quản lý** :Power Platform luồng dữ liệu chỉ do bạn tạo và quản lý. Các quản trị viên Thông tin chi tiết về khách hàng khác chỉ có thể xem các luồng dữ liệu này nhưng không thể chỉnh sửa, làm mới hoặc xóa chúng.
- **Do người khác quản lý** :Power Platform luồng dữ liệu do quản trị viên khác tạo. Bạn chỉ có thể xem chúng. Nó liệt kê chủ sở hữu của luồng dữ liệu cần liên hệ để được hỗ trợ.
> [!NOTE]
> Tất cả các thực thể có thể được xem và sử dụng bởi những người dùng khác. Mặc dù các nguồn dữ liệu thuộc sở hữu của người dùng đã tạo chúng, nhưng mọi người dùng Thông tin chi tiết về khách hàng đều có thể sử dụng các thực thể kết quả từ quá trình nhập dữ liệu.

Nếu môi trường của bạn không sử dụng Power Platform luồng dữ liệu, **Nguồn dữ liệu** trang chỉ chứa danh sách tất cả các nguồn dữ liệu. Không có phần nào hiển thị.

## <a name="manage-existing-data-sources"></a>Quản lý các nguồn dữ liệu hiện có

Đi đến **Dữ liệu** > **Nguồn dữ liệu** để xem tên của từng nguồn dữ liệu đã nhập, trạng thái của nó và lần cuối cùng dữ liệu được làm mới cho nguồn đó. Bạn có thể sắp xếp danh sách nguồn dữ liệu theo bất kỳ cột nào hoặc sử dụng hộp tìm kiếm để tìm nguồn dữ liệu mà bạn muốn quản lý.

Chọn nguồn dữ liệu để xem các hành động có sẵn.

:::image type="content" source="media/data_sources_showmore.png" alt-text="Nguồn dữ liệu đã thêm.":::

- [**Chỉnh sửa**](#add-or-edit-data-sources) nguồn dữ liệu để thay đổi thuộc tính của nó.
- [**Làm mới**](#refresh-data-sources) nguồn dữ liệu để bao gồm dữ liệu mới nhất.
- [**Làm giàu**](data-sources-enrichment.md) nguồn dữ liệu trước khi thống nhất.
- **Xóa bỏ** nguồn dữ liệu. Nguồn dữ liệu chỉ có thể bị xóa nếu dữ liệu không được sử dụng trong bất kỳ quá trình xử lý nào như hợp nhất, thông tin chi tiết, kích hoạt hoặc xuất.

## <a name="refresh-data-sources"></a>Làm mới nguồn dữ liệu

Nguồn dữ liệu có thể được làm mới theo lịch trình tự động hoặc được làm mới theo cách thủ công theo yêu cầu. [Nguồn dữ liệu tại chỗ](connect-power-query.md#add-data-from-on-premises-data-sources) làm mới lịch biểu của riêng họ được thiết lập trong quá trình nhập dữ liệu. Đối với các nguồn dữ liệu đính kèm, quá trình nhập dữ liệu sẽ sử dụng dữ liệu mới nhất có sẵn từ nguồn dữ liệu đó.

Đi đến **Quản trị viên** > **Hệ thống** > [**Lịch trình**](schedule-refresh.md) để định cấu hình các lần làm mới theo lịch trình của hệ thống đối với các nguồn dữ liệu đã nhập của bạn.

Để làm mới nguồn dữ liệu theo yêu cầu:

1. Chuyển tới **Dữ liệu** > **Nguồn dữ liệu**.

1. Chọn nguồn dữ liệu bạn muốn làm mới và chọn **Làm mới**. Nguồn dữ liệu hiện đã được kích hoạt để làm mới thủ công. Việc làm mới nguồn dữ liệu sẽ cập nhật cả giản đồ thực thể và dữ liệu cho tất cả các thực thể được chỉ định trong nguồn dữ liệu.

1. Chọn trạng thái để mở **Chi tiết tiến độ** ngăn và xem tiến trình. Để hủy công việc, hãy chọn **Hủy bỏ công việc** ở cuối ngăn.

[!INCLUDE [footer-include](includes/footer-banner.md)]
