---
title: Xuất dữ liệu sang Azure Data Lake Storage Gen2 (xem trước)
description: Tìm hiểu cách định cấu hình kết nối với Azure Data Lake Storage thế hệ 2.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 55a61e4d9166df7809a64aeb1168a730402aaed6
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196466"
---
# <a name="export-data-to-azure-data-lake-storage-gen2-preview"></a>Xuất dữ liệu sang Azure Data Lake Storage Gen2 (xem trước)

Lưu trữ dữ liệu Customer Insights của bạn trong tài khoản Data Lake Storage thế hệ 2 hoặc sử dụng kho lưu trữ đó để chuyển dữ liệu của bạn sang các ứng dụng khác.

## <a name="prerequisites"></a>Điều kiện tiên quyết

- Một [tài khoản lưu trữ để sử dụng với Azure Data Lake Gen2](/azure/storage/blobs/create-data-lake-storage-account). Để tìm tên và khóa tài khoản lưu trữ, hãy xem [Quản lý cài đặt tài khoản lưu trữ trong cổng Azure](/azure/storage/common/storage-account-manage).
- Một [Hộp chứa Azure Blob Storage](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="known-limitations"></a>Các hạn chế đã biết

- Vì Azure Data Lake Storage Gen2, chọn giữa [Hiệu suất tiêu chuẩn và Bậc hiệu suất cao cấp](/azure/storage/blobs/create-data-lake-storage-account). Nếu bạn chọn bậc Hiệu suất cao cấp, hãy chọn [các blob khối cao cấp làm loại tài khoản](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-azure-data-lake-storage-gen2"></a>Thiết lập kết nối với Azure Data Lake Storage Gen2

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Đi đến **Quản trị viên** > **Kết nối**.

1. Lựa chọn **Thêm kết nối** và lựa chọn **Azure Data Lake thế hệ 2**.

1. Đặt tên dễ nhận biết cho kết nối trong trường **Tên hiển thị**. Tên và loại kết nối mô tả kết nối này. Bạn nên chọn một tên giải thích mục đích và mục tiêu của kết nối.

1. Chọn người có thể sử dụng kết nối này. Theo mặc định, giá trị này là quản trị viên. Để biết thêm thông tin, hãy xem [Cho phép người đóng góp sử dụng một kết nối cho các lần xuất](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Nhập **Tên tài khoản**, **Khóa tài khoản** và **Bộ chứa** cho Azure Data Lake Storage Thế hệ 2 của bạn.

1. Xem lại [quyền riêng tư và tuân thủ dữ liệu](connections.md#data-privacy-and-compliance) và chọn **tôi đồng ý**.

1. Chọn **Lưu** để hoàn thành kết nối.

## <a name="configure-an-export"></a>Định cấu hình xuất

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Đi tới **Dữ liệu** > **Nội dung xuất**.

1. Lựa chọn **Thêm xuất khẩu**.

1. Bên trong **Kết nối để xuất**, chọn một kết nối từ phần Azure Data Lake. Liên hệ với quản trị viên nếu không có kết nối.

1. Nhập tên cho lần xuất.

1. Nhập tên thư mục cho Azure Data Lake Storage Lưu trữ Gen2.

1. Chọn ô cạnh mỗi thực thể mà bạn muốn xuất sang vị trí này.

1. Chọn **Lưu.**

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Dữ liệu đã xuất được lưu trữ trong bộ lưu trữ Azure Data Lake Thế hệ 2 mà bạn đã đặt cấu hình.

> [!TIP]
> Việc xuất các thực thể chứa một lượng lớn dữ liệu có thể dẫn đến nhiều tệp CSV trong cùng một thư mục cho mỗi lần xuất. Việc chia nhỏ xuất khẩu xảy ra vì lý do hiệu suất để giảm thiểu thời gian hoàn thành xuất khẩu.

[!INCLUDE [footer-include](includes/footer-banner.md)]
