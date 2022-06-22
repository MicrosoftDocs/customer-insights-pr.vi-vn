---
title: Nhập dữ liệu từ Azure Synapse Analytics
description: Sử dụng cơ sở dữ liệu trong Azure Synapse với tư cách là nguồn dữ liệu trong Dynamics 365 Customer Insights.
ms.date: 03/25/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 6f94cdbcc203fc4518544f7a945bd80e871b36c1
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011453"
---
# <a name="connect-an-azure-synapse-analytics-data-source-preview"></a>Kết nối một Azure Synapse Analytics nguồn dữ liệu (xem trước)

Azure Synapse Analytics là một dịch vụ phân tích doanh nghiệp giúp tăng tốc thời gian để hiểu rõ hơn về các kho dữ liệu và hệ thống dữ liệu lớn. Azure Synapse Analytics tập hợp những công nghệ SQL tốt nhất được sử dụng trong kho dữ liệu doanh nghiệp, công nghệ Spark được sử dụng cho dữ liệu lớn, Data Explorer để phân tích nhật ký và chuỗi thời gian, Đường ống để tích hợp dữ liệu và ETL / ELT, đồng thời tích hợp sâu với các dịch vụ Azure khác như Power BI,Cosmos DB và AzureML.

Để biết thêm thông tin, hãy xem [Azure Synapse tổng quát](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Điều kiện tiên quyết

> [!IMPORTANT]
> Đảm bảo bạn đặt tất cả các phép **gán vai trò** giống như mô tả.  

**Trong thông tin chi tiết về khách hàng**:

* Bạn có một **Người quản lý** vai trò trong Thông tin chi tiết về khách hàng. Học nhiều hơn về [quyền của người dùng trong Thông tin chi tiết về khách hàng](permissions.md#assign-roles-and-permissions).

**Trong Azure**:

- Đăng ký Azure hiện hoạt.

- Nếu sử dụng một cái mới Azure Data Lake Storage Tài khoản Gen2, *dịch vụ chính cho Thông tin chi tiết về khách hàng* nhu cầu **Người đóng góp dữ liệu khối lưu trữ** quyền. Học nhiều hơn về [kết nối với một Azure Data Lake Storage với một dịch vụ chính cho Thông tin chi tiết về khách hàng](connect-service-principal.md). Bạn **cần bật** [vùng tên phân cấp](/azure/storage/blobs/data-lake-storage-namespace) trên Data Lake Storage Thế hệ 2.

- Trên nhóm tài nguyên,Azure Synapse không gian làm việc được đặt, *dịch vụ chính* và *người dùng cho Thông tin chi tiết về khách hàng* ít nhất cần được chỉ định **Người đọc** quyền. Để biết thêm thông tin, hãy xem [Vai trò Assign Azure bằng cách sử dụng cổng thông tin Azure](/azure/role-based-access-control/role-assignments-portal).

- *Người dùng* cần được cấp quyền **Người đóng góp dữ liệu Storage Blob** trên tài khoản Azure Data Lake Storage Thế hệ 2 nơi đặt dữ liệu và liên kết với không gian làm việc Azure Synapse. Tìm hiểu thêm về [cách sử dụng cổng thông tin Azure để gắn vai trò Azure nhằm truy cập vào dữ liệu blob và dữ liệu hàng đợi](/azure/storage/common/storage-auth-aad-rbac-portal) cũng như [quyền Người đóng góp dữ liệu Storage Blob](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- *[Danh tính có quản lý trong không gian làm việc Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* cần được cấp quyền **Người đóng góp dữ liệu Storage Blob** trên tài khoản Azure Data Lake Storage Thế hệ 2, nơi đặt và liên kết dữ liệu với không gian làm việc Azure Synapse. Tìm hiểu thêm về [cách sử dụng cổng thông tin Azure để gắn vai trò Azure nhằm truy cập vào dữ liệu blob và dữ liệu hàng đợi](/azure/storage/common/storage-auth-aad-rbac-portal) cũng như [quyền Người đóng góp dữ liệu Storage Blob](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Trên Azure Synapse không gian làm việc, *dịch vụ chính cho Thông tin chi tiết về khách hàng* nhu cầu **Quản trị viên Synapse** vai trò được giao. Để biết thêm thông tin, hãy xem [Cách thiết lập trạng thái kiểm soát truy cập cho không gian làm việc Synapse của bạn](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="connect-to-the-data-lake-database-in-azure-synapse-analytics"></a>Kết nối với cơ sở dữ liệu hồ dữ liệu trong Azure Synapse Analytics

1. Chuyển tới **Dữ liệu** > **Nguồn dữ liệu**.

1. Chọn **Thêm nguồn dữ liệu**.

1. Chọn **Azure Synapse Analytics (Xem trước)** phương pháp.

   :::image type="content" source="media/data_sources_synapse.png" alt-text="Hộp thoại để kết nối với dữ liệu Synapse Analytics":::
  
1. Nhập **Tên** cho nguồn dữ liệu và một tùy chọn **Sự mô tả**.

1. Chọn một [kết nối có sẵn](connections.md) đến Azure Synapse Analytics hoặc tạo một cái mới.

1. Chọn một **Cơ sở dữ liệu** từ không gian làm việc được kết nối trong Azure Synapse Analytics kết nối và chọn **Tiếp theo**.

1. Chọn các thực thể để nhập từ cơ sở dữ liệu được kết nối và chọn **Tiếp theo**.

1. Theo tùy chọn, hãy chọn các thực thể dữ liệu để cho phép lập hồ sơ dữ liệu.

1. Lựa chọn **Tiết kiệm** để áp dụng lựa chọn của bạn và bắt đầu nhập dữ liệu từ nguồn dữ liệu mới tạo của bạn được liên kết với các bảng cơ sở dữ liệu Lake trong Azure Synapse Analytics. Các **Nguồn dữ liệu** trang mở ra hiển thị nguồn dữ liệu mới trong **Làm mới** trạng thái.
