---
title: Xuất dữ liệu Customer Insights sang Azure Synapse Analytics
description: Tìm hiểu cách định cấu hình kết nối tới Azure Synapse Analytics.
ms.date: 04/11/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 8ace9fbee4fbd8822629a39d5902e176f8511cb5
ms.sourcegitcommit: 9f6733b2f2c273748c1e7b77f871e9b4e5a8666e
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 04/11/2022
ms.locfileid: "8560413"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>Xuất dữ liệu sang Azure Synapse Analytics (Xem trước)

Azure Synapse là một dịch vụ phân tích giúp tăng tốc thời gian để hiểu rõ hơn về các kho dữ liệu và hệ thống dữ liệu lớn. Bạn có thể nhập và sử dụng dữ liệu Customer Insights của mình trong [Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Điều kiện tiên quyết

Cần đáp ứng các điều kiện tiên quyết sau để định cấu hình kết nối từ Customer Insights sang Azure Synapse.

> [!NOTE]
> Đảm bảo bạn đặt tất cả các phép **gán vai trò** giống như mô tả.  

## <a name="prerequisites-in-customer-insights"></a>Các điều kiện tiên quyết trong Customer Insights

* Của bạn Azure Active Directory (AD) tài khoản người dùng có một **Người quản lý** vai trò trong Thông tin chi tiết về khách hàng. Tìm hiểu thêm về [thiết lập quyền của người dùng trong phần thông tin chuyên sâu về đối tượng](permissions.md#assign-roles-and-permissions)

Trong Azure: 

- Đăng ký Azure hiện hoạt.

- Nếu sử dụng một cái mới Azure Data Lake Storage Tài khoản Gen2, *dịch vụ chính cho Thông tin chi tiết về khách hàng* nhu cầu **Người đóng góp dữ liệu khối lưu trữ** quyền. Tìm hiểu thêm về [cách kết nối với tài khoản Azure Data Lake Storage Thế hệ 2 với tên dịch vụ chính Azure để có thông tin chuyên sâu về đối tượng](connect-service-principal.md). Bạn **cần bật** [vùng tên phân cấp](/azure/storage/blobs/data-lake-storage-namespace) trên Data Lake Storage Thế hệ 2.

- Trên nhóm tài nguyên, nơi Azure Synapse không gian làm việc được đặt, *dịch vụ chính* và *Azure AD người dùng có quyền quản trị trong Thông tin chi tiết về khách hàng* ít nhất cần được chỉ định **Người đọc** quyền. Để biết thêm thông tin, hãy xem [Vai trò Assign Azure bằng cách sử dụng cổng thông tin Azure](/azure/role-based-access-control/role-assignments-portal).

- Các *Azure AD người dùng có quyền quản trị trong Thông tin chi tiết về khách hàng* nhu cầu **Người đóng góp dữ liệu khối lưu trữ** quyền trên Azure Data Lake Storage Tài khoản Gen2 nơi dữ liệu được đặt và liên kết với Azure Synapse không gian làm việc. Tìm hiểu thêm về [cách sử dụng cổng thông tin Azure để gắn vai trò Azure nhằm truy cập vào dữ liệu blob và dữ liệu hàng đợi](/azure/storage/common/storage-auth-aad-rbac-portal) cũng như [quyền Người đóng góp dữ liệu Storage Blob](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- *[Danh tính có quản lý trong không gian làm việc Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* cần được cấp quyền **Người đóng góp dữ liệu Storage Blob** trên tài khoản Azure Data Lake Storage Thế hệ 2, nơi đặt và liên kết dữ liệu với không gian làm việc Azure Synapse. Tìm hiểu thêm về [cách sử dụng cổng thông tin Azure để gắn vai trò Azure nhằm truy cập vào dữ liệu blob và dữ liệu hàng đợi](/azure/storage/common/storage-auth-aad-rbac-portal) cũng như [quyền Người đóng góp dữ liệu Storage Blob](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Trên Azure Synapse không gian làm việc, *dịch vụ chính cho Thông tin chi tiết về khách hàng* nhu cầu **Quản trị viên Synapse** vai trò được giao. Để biết thêm thông tin, hãy xem [Cách thiết lập trạng thái kiểm soát truy cập cho không gian làm việc Synapse của bạn](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a>Thiết lập kết nối và xuất sang Azure Synapse

### <a name="configure-a-connection"></a>Định cấu hình kết nối

Để tạo kết nối, người quản lý dịch vụ và tài khoản người dùng trong Thông tin chi tiết về khách hàng cần **Người đọc** quyền trên *nhóm tài nguyên* nơi đặt không gian làm việc của Synapse Analytics. Ngoài ra, người quản lý dịch vụ và người dùng trên không gian làm việc Synapse Analytics cần **Quản trị viên Synapse** quyền. 

1. Đi đến **Quản trị viên** > **Kết nối**.

1. Lựa chọn **Thêm kết nối** và lựa chọn **Azure Synapse Analytics** hoặc chọn **Thiết lập** trên **Azure Synapse Analytics** để định cấu hình kết nối.

1. Đặt tên dễ nhận biết cho kết nối trong trường Tên hiển thị. Tên và loại kết nối mô tả kết nối này. Bạn nên chọn một tên giải thích mục đích và mục tiêu của kết nối.

1. Chọn người có thể sử dụng kết nối này. Nếu bạn không thực hiện hành động nào, giá trị mặc định sẽ là Quản trị viên. Để biết thêm thông tin, hãy xem [Cho phép người đóng góp sử dụng một kết nối cho các lần xuất](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Chọn hoặc tìm kiếm gói đăng ký nơi bạn muốn sử dụng dữ liệu Customer Insights. Ngay sau khi chọn gói đăng ký, bạn cũng có thể chọn **Không gian làm việc**, **Tài khoản lưu trữ** và **Bộ chứa**.

1. Để lưu kết nối, hãy chọn **Lưu**.

### <a name="configure-an-export"></a>Đặt cấu hình xuất

Bạn có thể định cấu hình lần xuất này nếu bạn có quyền truy cập vào kết nối thuộc loại này. Để định cấu hình xuất với kết nối được chia sẻ, bạn cần ít nhất **Người đóng góp** quyền trong Thông tin chi tiết về khách hàng. Để biết thêm thông tin, hãy xem [các quyền cần thiết để đặt cấu hình xuất](export-destinations.md#set-up-a-new-export).

1. Đi tới **Dữ liệu** > **Nội dung xuất**.

1. Để tạo nội dung xuất mới, hãy chọn **Thêm nội dung xuất**.

1. Bên trong **Kết nối để xuất** trường, chọn một kết nối từ **Azure Synapse Analytics** tiết diện. Nếu bạn không thấy tên phần này, tức là không có [kết nối](connections.md) nào thuộc loại này dành cho bạn.

1. Đặt một **Tên hiển thị** dễ nhận biết cho việc xuất dữ liệu và **Tên cơ sở dữ liệu** của bạn.

1. Chọn thực thể bạn muốn xuất sang Azure Synapse Analytics.
   > [!NOTE]
   > Nguồn dữ liệu dựa trên [Thư mục Common Data Model](connect-common-data-model.md) không được hỗ trợ.

2. Chọn **Lưu**.

Việc lưu một nội dung xuất sẽ không chạy nội dung xuất đó ngay lập tức.

Nội dung xuất chạy trong mỗi lần [làm mới theo lịch trình](system.md#schedule-tab). Bạn cũng có thể [xuất dữ liệu theo yêu cầu](export-destinations.md#run-exports-on-demand).

Để truy vấn dữ liệu đã được xuất sang Synapse Analytics, bạn cần **Bộ đọc dữ liệu khối lưu trữ** truy cập vào bộ nhớ đích trên không gian làm việc của các tệp xuất. 

### <a name="update-an-export"></a>Cập nhật việc xuất dữ liệu

1. Đi tới **Dữ liệu** > **Nội dung xuất**.

1. Chọn **Chỉnh sửa** quá trình xuất bạn muốn cập nhật.

   - **Thêm** hoặc **Xóa** các thực thể đã chọn. Nếu bạn bỏ chọn các thực thể, những thực thể này sẽ không bị xóa khỏi cơ sở dữ liệu Synapse Analytics. Tuy nhiên, các thực thể đã xóa trong cơ sở dữ liệu đó sẽ không được cập nhật trong những lần làm mới dữ liệu tiếp theo.

   - Việc **thay đổi Tên cơ sở dữ liệu** tạo ra cơ sở dữ liệu Synapse Analytics mới. Cơ sở dữ liệu có tên đã được định cấu hình trước đó sẽ không nhận được bất kỳ bản cập nhật nào trong các lần làm mới tiếp theo.
