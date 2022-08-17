---
title: Xuất dữ liệu sang Azure Synapse Analytics (xem trước)
description: Tìm hiểu cách định cấu hình kết nối tới Azure Synapse Analytics.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 0e953cfff12df433d033717d58b28c2834468916
ms.sourcegitcommit: 086f75136132d561cd78a4c2cb1e1933e2301f32
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 08/11/2022
ms.locfileid: "9259870"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>Xuất dữ liệu sang Azure Synapse Analytics (xem trước)

Azure Synapse là một dịch vụ phân tích giúp tăng tốc thời gian để hiểu rõ hơn về các kho dữ liệu và hệ thống dữ liệu lớn. Bạn có thể nhập và sử dụng dữ liệu Customer Insights của mình trong [Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Điều kiện tiên quyết

> [!NOTE]
> Đảm bảo bạn đặt tất cả các phép **gán vai trò** giống như mô tả.

- Trong Thông tin chi tiết về khách hàng,Azure Active Directory (AD) tài khoản người dùng phải có [Vai trò quản trị viên](permissions.md#add-users).

Trong Azure:

- Đăng ký Azure hiện hoạt.

- Nếu sử dụng một Azure Data Lake Storage Tài khoản Gen2, [dịch vụ chính cho Thông tin chi tiết về khách hàng](connect-service-principal.md) có **Người đóng góp dữ liệu khối lưu trữ** quyền. Bạn **cần bật** [vùng tên phân cấp](/azure/storage/blobs/data-lake-storage-namespace) trên Data Lake Storage Thế hệ 2.

- Trên nhóm tài nguyên, nơi Azure Synapse không gian làm việc được đặt, *dịch vụ chính* và *Azure AD người dùng có quyền quản trị trong Thông tin chi tiết về khách hàng* ít nhất phải được chỉ định **Người đọc**[sự cho phép](/azure/role-based-access-control/role-assignments-portal).

- Các *Azure AD người dùng có quyền quản trị trong Thông tin chi tiết về khách hàng* có **Người đóng góp dữ liệu khối lưu trữ** quyền trên Azure Data Lake Storage Tài khoản Gen2 nơi dữ liệu được đặt và liên kết với Azure Synapse không gian làm việc. Tìm hiểu thêm về [cách sử dụng cổng thông tin Azure để gắn vai trò Azure nhằm truy cập vào dữ liệu blob và dữ liệu hàng đợi](/azure/storage/common/storage-auth-aad-rbac-portal) cũng như [quyền Người đóng góp dữ liệu Storage Blob](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Các *[Azure Synapse không gian làm việc được quản lý danh tính](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* có **Người đóng góp dữ liệu khối lưu trữ** quyền trên Azure Data Lake Storage Tài khoản Gen2 nơi dữ liệu được đặt và liên kết với Azure Synapse không gian làm việc. Tìm hiểu thêm về [cách sử dụng cổng thông tin Azure để gắn vai trò Azure nhằm truy cập vào dữ liệu blob và dữ liệu hàng đợi](/azure/storage/common/storage-auth-aad-rbac-portal) cũng như [quyền Người đóng góp dữ liệu Storage Blob](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Trên Azure Synapse không gian làm việc, *dịch vụ chính cho Thông tin chi tiết về khách hàng* có **Quản trị viên Synapse**[vai trò được giao](/azure/synapse-analytics/security/how-to-set-up-access-control).

- Nếu môi trường Thông tin chi tiết về khách hàng của bạn lưu trữ dữ liệu trong [riêng Azure Data Lake Storage](own-data-lake-storage.md), người dùng thiết lập kết nối với Azure Synapse Analytics cần ít nhất là cài sẵn **Người đọc** trên tài khoản Data Lake Storage. Để biết thêm thông tin, hãy xem [Vai trò Assign Azure bằng cách sử dụng cổng thông tin Azure](/azure/role-based-access-control/role-assignments-portal).

## <a name="set-up-connection-to-azure-synapse"></a>Thiết lập kết nối với Azure Synapse

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Đi đến **Quản trị viên** > **Kết nối**.

1. Lựa chọn **Thêm kết nối** và lựa chọn **Azure Synapse Analytics**.

1. Đặt tên dễ nhận biết cho kết nối trong trường **Tên hiển thị**. Tên và loại kết nối mô tả kết nối này. Bạn nên chọn một tên giải thích mục đích và mục tiêu của kết nối.

1. Chọn người có thể sử dụng kết nối này. Theo mặc định, giá trị này là quản trị viên. Để biết thêm thông tin, hãy xem [Cho phép người đóng góp sử dụng một kết nối cho các lần xuất](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Chọn hoặc tìm kiếm gói đăng ký nơi bạn muốn sử dụng dữ liệu Customer Insights. Ngay sau khi chọn gói đăng ký, bạn cũng có thể chọn **Không gian làm việc**, **Tài khoản lưu trữ** và **Bộ chứa**.

1. Xem lại [quyền riêng tư và tuân thủ dữ liệu](connections.md#data-privacy-and-compliance) và chọn **tôi đồng ý**.

1. Chọn **Lưu** để hoàn thành kết nối.

## <a name="configure-an-export"></a>Định cấu hình xuất

[!INCLUDE [export-permission-include](includes/export-permission.md)] Để định cấu hình xuất với kết nối được chia sẻ, bạn cần ít nhất **Người đóng góp** quyền trong Thông tin chi tiết về khách hàng.

1. Đi tới **Dữ liệu** > **Nội dung xuất**.

1. Lựa chọn **Thêm xuất khẩu**.

1. Bên trong **Kết nối để xuất** trường, chọn một kết nối từ Azure Synapse Analytics tiết diện. Liên hệ với quản trị viên nếu không có kết nối.

1. Đặt một **Tên hiển thị** dễ nhận biết cho việc xuất dữ liệu và **Tên cơ sở dữ liệu** của bạn. Việc xuất sẽ tạo ra một [Azure Synapse cơ sở dữ liệu hồ](/azure/synapse-analytics/database-designer/concepts-lake-database) trong không gian làm việc được xác định trong kết nối.

1. Chọn thực thể bạn muốn xuất sang Azure Synapse Analytics.
   > [!NOTE]
   > Nguồn dữ liệu dựa trên [Thư mục Common Data Model](connect-common-data-model.md) không được hỗ trợ.

1. Chọn **Lưu.**

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Để truy vấn dữ liệu đã được xuất sang Synapse Analytics, bạn cần **Bộ đọc dữ liệu khối lưu trữ** quyền truy cập vào bộ nhớ đích trên không gian làm việc của các tệp xuất.

## <a name="update-an-export"></a>Cập nhật việc xuất dữ liệu

1. Đi tới **Dữ liệu** > **Nội dung xuất**.

1. Chọn **Chỉnh sửa** quá trình xuất bạn muốn cập nhật.

   - **Thêm** hoặc **Xóa** các thực thể đã chọn. Nếu bạn bỏ chọn các thực thể, những thực thể này sẽ không bị xóa khỏi cơ sở dữ liệu Synapse Analytics. Tuy nhiên, các thực thể đã xóa trong cơ sở dữ liệu đó sẽ không được cập nhật trong những lần làm mới dữ liệu tiếp theo.

   - Việc **thay đổi Tên cơ sở dữ liệu** tạo ra cơ sở dữ liệu Synapse Analytics mới. Cơ sở dữ liệu có tên đã được định cấu hình trước đó sẽ không nhận được bất kỳ bản cập nhật nào trong các lần làm mới tiếp theo.

[!INCLUDE [footer-include](includes/footer-banner.md)]
