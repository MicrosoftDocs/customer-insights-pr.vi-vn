---
title: Tự dùng cái của bạn đi Azure Data Lake Storage Tài khoản Gen2
author: mukeshpo
description: Tìm hiểu về các yêu cầu để sử dụng của riêng bạn Azure Data Lake Storage tài khoản để lưu trữ dữ liệu Thông tin chi tiết về khách hàng.
ms.author: mukeshpo
ms.date: 06/08/2022
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.reviewer: mhart
ms.openlocfilehash: d2ff49c324c5c5c28213f362ff330d441fcb6052
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246227"
---
# <a name="use-your-own-azure-data-lake-storage-gen2-account"></a>Tự dùng cái của bạn đi Azure Data Lake Storage Tài khoản Gen2

Dynamics 365 Customer Insights cung cấp cho bạn tùy chọn để lưu trữ tất cả dữ liệu của bạn trong [Azure Data Lake Storage Thế hệ 2](/azure/storage/blobs/data-lake-storage-introduction).

Bằng cách lưu dữ liệu vào Data Lake Storage, bạn đồng ý rằng dữ liệu sẽ được chuyển đến và lưu trữ ở vị trí địa lý thích hợp cho tài khoản lưu trữ Azure đó. Để biết thêm thông tin, hãy xem [Trung tâm tin cậy của Microsoft](https://www.microsoft.com/trust-center).

Quản trị viên trong Thông tin chi tiết về khách hàng có thể [tạo môi trường](create-environment.md) và [chỉ định tùy chọn lưu trữ dữ liệu](create-environment.md#step-2-configure-data-storage) trong quá trình.

## <a name="prerequisites-to-use-your-storage-account"></a>Điều kiện tiên quyết để sử dụng tài khoản lưu trữ của bạn

- Azure Data Lake Storage tài khoản phải ở trong cùng khu vực Azure mà bạn đã chọn khi tạo môi trường Thông tin chi tiết về khách hàng. Bạn có thể kiểm tra khu vực của môi trường Thông tin chi tiết về khách hàng trong **Quản trị viên** > **Hệ thống** > **Về**.
- Bộ nhớ Data Lake phải là Gen2 và có [không gian tên phân cấp được bật](/azure/storage/blobs/create-data-lake-storage-account). Tài khoản bộ nhớ Gen1 không được hỗ trợ.
- Một vùng chứa có tên`customerinsights` phải tồn tại trên tài khoản lưu trữ. Bạn phải tạo nó trước khi sử dụng Bộ nhớ Data Lake của riêng mình trong Thông tin chi tiết về khách hàng. Quản trị viên thiết lập môi trường Thông tin chi tiết về khách hàng cần có vai trò Người đóng góp dữ liệu Blob lưu trữ hoặc Chủ sở hữu dữ liệu Blob lưu trữ trên tài khoản lưu trữ hoặc`customerinsights` thùng đựng hàng. Để biết thêm thông tin về cách chỉ định quyền trong tài khoản lưu trữ, hãy xem [Tạo tài khoản lưu trữ](/azure/storage/common/storage-account-create?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&tabs=azure-portal).

## <a name="connect-customer-insights-with-your-storage-account"></a>Kết nối Thông tin chi tiết về khách hàng với tài khoản lưu trữ của bạn

Khi bạn tạo một môi trường mới, hãy đảm bảo rằng tài khoản Data Lake Storage tồn tại và đáp ứng tất cả các điều kiện tiên quyết.

1. Bên trong **Lưu trữ dữ liệu** bước trong quá trình tạo môi trường, thiết lập **Lưu dữ liệu đầu ra** đến **Azure Data Lake Storage Gen2**.
1. Chọn cách **Kết nối bộ nhớ của bạn**. Bạn có thể chọn giữa tùy chọn dựa trên tài nguyên và tùy chọn dựa trên đăng ký để xác thực. Để biết thêm thông tin, hãy xem [Kết nối với một Azure Data Lake Storage tài khoản bằng cách sử dụng Dịch vụ Azure chính](connect-service-principal.md).
   - Vì **Đăng ký Azure**, chọn **Đăng ký**, **tài nguyên**, và **Tài khoản lưu trữ** có chứa`customerinsights` thùng đựng hàng.
   - Vì **Chìa khóa tài khoản**, cung cấp **Tên tài khoản** và **Chìa khóa tài khoản** cho tài khoản Data Lake Storage. Sử dụng phương pháp xác thực này ngụ ý rằng bạn được thông báo nếu tổ chức của bạn xoay các khóa. Bạn phải [cập nhật cấu hình môi trường](manage-environments.md#edit-an-existing-environment) với phím mới khi nó được xoay.
1. Chọn nếu bạn muốn sử dụng Azure Private Link để kết nối với tài khoản lưu trữ và [tạo kết nối với Liên kết riêng tư](security-overview.md#set-up-an-azure-private-link) với quy trình hai bước.

Khi quá trình hệ thống như nhập dữ liệu hoàn tất, hệ thống sẽ tạo các thư mục tương ứng trong tài khoản lưu trữ. Tệp dữ liệu và tệp *model.json* được tạo và thêm vào các thư mục dựa trên tên quy trình.

Nếu bạn tạo nhiều môi trường Customer Insights và chọn lưu các thực thể đầu ra từ các môi trường đó vào tài khoản lưu trữ của mình, thì Customer Insights sẽ tạo các thư mục riêng biệt cho từng môi trường với `ci_environmentID` trong bộ chứa.
