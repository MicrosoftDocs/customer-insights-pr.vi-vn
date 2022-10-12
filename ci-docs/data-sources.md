---
title: Tổng quan về nguồn dữ liệu
description: Tìm hiểu cách nhập hoặc nhập dữ liệu từ nhiều nguồn khác nhau.
ms.date: 09/29/2022
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
ms.openlocfilehash: f89da3cf5b56e367bd673740f80cd82ec0907b28
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610078"
---
# <a name="data-sources-overview"></a>Tổng quan về nguồn dữ liệu

Dynamics 365 Customer Insights cung cấp các kết nối để mang dữ liệu từ nhiều nguồn khác nhau. Kết nối với nguồn dữ liệu thường được gọi là quá trình *nhập dữ liệu*. Sau khi nhập dữ liệu, bạn có thể [thống nhất](data-unification.md), tạo thông tin chi tiết và kích hoạt dữ liệu để xây dựng trải nghiệm được cá nhân hóa.

## <a name="add-or-edit-data-sources"></a>Thêm hoặc chỉnh sửa nguồn dữ liệu

Bạn có thể đính kèm hoặc nhập các nguồn dữ liệu vào Thông tin chi tiết về khách hàng. Các liên kết bên dưới cung cấp hướng dẫn về cách thêm và chỉnh sửa nguồn dữ liệu.

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
> Tất cả các thực thể có thể được xem và sử dụng bởi những người dùng khác. Mặc dù các nguồn dữ liệu thuộc sở hữu của người dùng đã tạo chúng, nhưng mọi người dùng Thông tin chi tiết về khách hàng đều có thể sử dụng các thực thể kết quả từ quá trình nhập dữ liệu.

Nếu môi trường của bạn không sử dụng Power Platform luồng dữ liệu, **Nguồn dữ liệu** trang chỉ chứa danh sách tất cả các nguồn dữ liệu. Không có phần hiển thị.

## <a name="manage-existing-data-sources"></a>Quản lý các nguồn dữ liệu hiện có

Đi đến **Dữ liệu** > **Nguồn dữ liệu** để xem tên của từng nguồn dữ liệu đã nhập, trạng thái của nó và lần cuối cùng dữ liệu được làm mới cho nguồn đó. Bạn có thể sắp xếp danh sách nguồn dữ liệu theo bất kỳ cột nào hoặc sử dụng hộp tìm kiếm để tìm nguồn dữ liệu mà bạn muốn quản lý.

Chọn nguồn dữ liệu để xem các hành động có sẵn.

:::image type="content" source="media/data_sources_showmore.png" alt-text="Nguồn dữ liệu đã thêm.":::

- [**Chỉnh sửa**](#add-or-edit-data-sources) nguồn dữ liệu để thay đổi thuộc tính của nó.
- [**Làm mới**](#refresh-data-sources) nguồn dữ liệu để bao gồm dữ liệu mới nhất.
- [**Làm giàu**](data-sources-enrichment.md) nguồn dữ liệu trước khi thống nhất.
- **Xóa bỏ** nguồn dữ liệu. Nguồn dữ liệu chỉ có thể bị xóa nếu dữ liệu không được sử dụng trong bất kỳ quá trình xử lý nào như hợp nhất, thông tin chi tiết, kích hoạt hoặc xuất.

## <a name="refresh-data-sources"></a>Làm mới nguồn dữ liệu

Nguồn dữ liệu có thể được làm mới theo lịch trình tự động hoặc được làm mới theo cách thủ công theo yêu cầu. [Nguồn dữ liệu tại chỗ](connect-power-query.md#add-data-from-on-premises-data-sources) làm mới lịch biểu của riêng họ được thiết lập trong quá trình nhập dữ liệu. Để biết các mẹo khắc phục sự cố, hãy xem [Khắc phục sự cố PPDF Power Query vấn đề làm mới -based nguồn dữ liệu](connect-power-query.md#troubleshoot-ppdf-power-query-based-data-source-refresh-issues).

Đối với các nguồn dữ liệu được đính kèm, quá trình nhập dữ liệu sẽ sử dụng dữ liệu mới nhất có sẵn từ nguồn dữ liệu đó.

Đi đến **Quản trị viên** > **Hệ thống** > [**Lịch trình**](schedule-refresh.md) để định cấu hình làm mới theo lịch trình của hệ thống đối với các nguồn dữ liệu đã nhập của bạn.

Để làm mới nguồn dữ liệu theo yêu cầu:

1. Chuyển tới **Dữ liệu** > **Nguồn dữ liệu**.

1. Chọn nguồn dữ liệu bạn muốn làm mới và chọn **Làm mới**. Nguồn dữ liệu hiện đã được kích hoạt để làm mới thủ công. Việc làm mới nguồn dữ liệu sẽ cập nhật cả giản đồ thực thể và dữ liệu cho tất cả các thực thể được chỉ định trong nguồn dữ liệu.

1. Chọn trạng thái để mở **Chi tiết tiến độ** ngăn và xem tiến trình. Để hủy công việc, hãy chọn **Hủy bỏ công việc** ở cuối ngăn.

## <a name="corrupt-data-sources"></a>Nguồn dữ liệu bị hỏng

Dữ liệu đang được nhập có thể có các bản ghi bị hỏng, điều này có thể khiến quá trình nhập dữ liệu hoàn tất với lỗi hoặc cảnh báo.

> [!NOTE]
> Nếu quá trình nhập dữ liệu hoàn tất mà có lỗi, quá trình xử lý tiếp theo (chẳng hạn như hợp nhất hoặc tạo hoạt động) sử dụng nguồn dữ liệu này sẽ bị bỏ qua. Nếu quá trình nhập hoàn tất với cảnh báo, quá trình xử lý tiếp theo sẽ tiếp tục nhưng một số bản ghi có thể không được đưa vào.

Những lỗi này có thể được nhìn thấy trong chi tiết nhiệm vụ.

:::image type="content" source="media/corrupt-task-error.png" alt-text="Chi tiết tác vụ hiển thị lỗi dữ liệu bị hỏng.":::

Các bản ghi lỗi được hiển thị trong các thực thể do hệ thống tạo ra.

### <a name="fix-corrupt-data"></a>Sửa dữ liệu bị hỏng

1. Để xem dữ liệu bị hỏng, hãy truy cập **Dữ liệu** > **Thực thể** và tìm kiếm các thực thể bị hỏng trong **Hệ thống** tiết diện. Lược đồ đặt tên của các thực thể bị hỏng: 'DataSourceName_EntityName_corrupt'.

1. Chọn một thực thể bị hỏng và sau đó **Dữ liệu** chuyển hướng.

1. Xác định các trường bị hỏng trong bản ghi và lý do.

   :::image type="content" source="media/corruption-reason.png" alt-text="Lý do tham nhũng." lightbox="media/corruption-reason.png":::

   > [!NOTE]
   > **Dữ liệu** > **Thực thể** chỉ hiển thị một phần của các bản ghi bị hỏng. Để xem tất cả các bản ghi bị hỏng, hãy xuất các tệp vào một vùng chứa trong tài khoản lưu trữ bằng cách sử dụng [Quy trình xuất thông tin chi tiết về khách hàng](export-destinations.md). Nếu bạn đã sử dụng tài khoản lưu trữ của riêng mình, bạn cũng có thể xem thư mục Thông tin chi tiết về khách hàng trong tài khoản lưu trữ của mình.

1. Sửa chữa các dữ liệu bị hỏng. Ví dụ: đối với nguồn dữ liệu Azure Data Lake, [sửa dữ liệu trong Data Lake Storage hoặc cập nhật các loại dữ liệu trong tệp kê khai / model.json](connect-common-data-model.md#common-reasons-for-ingestion-errors-or-corrupt-data). Vì Power Query nguồn dữ liệu, sửa dữ liệu trong tệp nguồn và [sửa kiểu dữ liệu bước chuyển đổi](connect-power-query.md#data-type-does-not-match-data) trên **Power Query - Chỉnh sửa các truy vấn** trang.

Sau lần làm mới tiếp theo của nguồn dữ liệu, các bản ghi đã sửa sẽ được nhập vào Customer Insights và được chuyển cho các quy trình tiếp theo.

Ví dụ: cột "ngày sinh" có loại dữ liệu được đặt là "ngày". Hồ sơ khách hàng có ngày sinh của họ được nhập là "01/01/19777". Hệ thống gắn cờ bản ghi này là bị hỏng. Thay đổi ngày sinh trong hệ thống nguồn thành '1977'. Sau khi tự động làm mới nguồn dữ liệu, trường hiện có định dạng hợp lệ và bản ghi sẽ bị xóa khỏi thực thể bị hỏng.

[!INCLUDE [footer-include](includes/footer-banner.md)]
