---
title: Nhập dữ liệu từ Azure Synapse Analytics
description: Sử dụng cơ sở dữ liệu trong Azure Synapse với tư cách là nguồn dữ liệu trong Dynamics 365 Customer Insights.
ms.date: 02/24/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 163bef897880f0497bf00e90fd095621a2d14378
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 02/25/2022
ms.locfileid: "8356058"
---
# <a name="connect-an-azure-synapse-data-source-preview"></a>Kết nối một Azure Synapse nguồn dữ liệu (xem trước)

Azure Synapse Analytics là một dịch vụ phân tích doanh nghiệp giúp tăng tốc thời gian để hiểu rõ hơn về các kho dữ liệu và hệ thống dữ liệu lớn. Azure Synapse Analytics tập hợp những công nghệ SQL tốt nhất được sử dụng trong kho dữ liệu doanh nghiệp, công nghệ Spark được sử dụng cho dữ liệu lớn, Data Explorer để phân tích nhật ký và chuỗi thời gian, Đường ống để tích hợp dữ liệu và ETL / ELT, đồng thời tích hợp sâu với các dịch vụ Azure khác như Power BI,Cosmos DB và AzureML.

Để biết thêm thông tin, hãy xem [Azure Synapse Tổng quat](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Điều kiện tiên quyết

Cần đáp ứng các điều kiện tiên quyết sau để định cấu hình kết nối từ Customer Insights sang Azure Synapse.

> [!IMPORTANT]
> Đảm bảo bạn đặt tất cả các phép **gán vai trò** giống như mô tả.  

## <a name="prerequisites-in-customer-insights"></a>Các điều kiện tiên quyết trong Customer Insights

* Bạn có một **Người quản lý** vai trò trong Thông tin chi tiết về khách hàng. Tìm hiểu thêm về [quyền người dùng trong thông tin chuyên sâu về đối tượng](permissions.md#assign-roles-and-permissions).

Trong Azure: 

- Đăng ký Azure hiện hoạt.

- Nếu bạn sử dụng một tài khoản Azure Data Lake Storage Thế hệ 2 mới, *tên dịch vụ chính cho thông tin chuyên sâu về đối tượng* cần được cấp quyền **Người đóng góp dữ liệu Storage Blob**. Học nhiều hơn về [kết nối với một Azure Data Lake Storage với một người phụ trách dịch vụ để có thông tin chi tiết về khán giả](connect-service-principal.md). Bạn **cần bật** [vùng tên phân cấp](/azure/storage/blobs/data-lake-storage-namespace) trên Data Lake Storage Thế hệ 2.

- Trên nhóm nguồn lực có đặt không gian làm việc Azure Synapse, *tên dịch vụ chính* và *người dùng thông tin chuyên sâu về đối tượng* cần được gán quyền **Người đọc**. Để biết thêm thông tin, hãy xem [Vai trò Assign Azure bằng cách sử dụng cổng thông tin Azure](/azure/role-based-access-control/role-assignments-portal).

- *Người dùng* cần được cấp quyền **Người đóng góp dữ liệu Storage Blob** trên tài khoản Azure Data Lake Storage Thế hệ 2 nơi đặt dữ liệu và liên kết với không gian làm việc Azure Synapse. Tìm hiểu thêm về [cách sử dụng cổng thông tin Azure để gắn vai trò Azure nhằm truy cập vào dữ liệu blob và dữ liệu hàng đợi](/azure/storage/common/storage-auth-aad-rbac-portal) cũng như [quyền Người đóng góp dữ liệu Storage Blob](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- *[Danh tính có quản lý trong không gian làm việc Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* cần được cấp quyền **Người đóng góp dữ liệu Storage Blob** trên tài khoản Azure Data Lake Storage Thế hệ 2, nơi đặt và liên kết dữ liệu với không gian làm việc Azure Synapse. Tìm hiểu thêm về [cách sử dụng cổng thông tin Azure để gắn vai trò Azure nhằm truy cập vào dữ liệu blob và dữ liệu hàng đợi](/azure/storage/common/storage-auth-aad-rbac-portal) cũng như [quyền Người đóng góp dữ liệu Storage Blob](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Trên không gian làm việc Azure Synapse, *tên dịch vụ chính cho thông tin chuyên sâu về đối tượng* cần được gán vai trò **Quản trị viên Synapse**. Để biết thêm thông tin, hãy xem [Cách thiết lập trạng thái kiểm soát truy cập cho không gian làm việc Synapse của bạn](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="connect-to-data-lake-databases-in-azure-synapse-analytics"></a>Kết nối với cơ sở dữ liệu hồ dữ liệu trong Azure Synapse Analytics

1. Chuyển tới **Dữ liệu** > **Nguồn dữ liệu**.

1. Chọn **Thêm nguồn dữ liệu**.

1. Chọn **Azure Synapse Analytics (Xem trước)** phương pháp.

1. Cung cấp một **Tên** cho nguồn dữ liệu và chọn **Tiếp theo** để tạo nguồn dữ liệu. 

1. Chọn một [kết nối có sẵn](connections.md) đến Azure Synapse Analytics hoặc tạo một cái mới.

1. Chọn một **Cơ sở dữ liệu hồ** từ không gian làm việc được kết nối trong Azure Synapse Analytics kết nối và chọn **Tiếp theo**.

1. Chọn các thực thể để nhập từ cơ sở dữ liệu được kết nối. 

1. Theo tùy chọn, hãy chọn các thực thể dữ liệu để cho phép lập hồ sơ dữ liệu. 

1. Lựa chọn **Tiết kiệm** để áp dụng lựa chọn của bạn và bắt đầu nhập dữ liệu từ nguồn dữ liệu mới tạo của bạn được liên kết với các bảng cơ sở dữ liệu Lake trong Azure Synapse Analytics.
