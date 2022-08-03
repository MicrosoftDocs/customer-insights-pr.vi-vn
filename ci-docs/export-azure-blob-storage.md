---
title: Xuất dữ liệu sang Bộ nhớ Azure Blob (xem trước)
description: Tìm hiểu cách đặt cấu hình kết nối và xuất sang bộ lưu trữ Blob.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 22593ed05f403a40fe494e30f807b57658594f01
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195730"
---
# <a name="export-data-to-an-azure-blob-storage-preview"></a>Xuất dữ liệu sang Bộ nhớ Azure Blob (xem trước)

Lưu trữ dữ liệu Customer Insights của bạn trong bộ lưu trữ Blob hoặc sử dụng bộ lưu trữ đó để chuyển dữ liệu của bạn sang các ứng dụng khác.

## <a name="prerequisites"></a>Điều kiện tiên quyết

- Một [Tài khoản lưu trữ Azure Blob](/azure/storage/blobs/create-data-lake-storage-account) tên và khóa tài khoản. Để tìm tên và khóa, hãy xem [Quản lý cài đặt tài khoản lưu trữ trong cổng Azure](/azure/storage/common/storage-account-manage).
- Một [Hộp chứa Azure Blob Storage](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="known-limitations"></a>Các hạn chế đã biết

- Đối với Azure Blob Storage, hãy chọn giữa [Hiệu suất tiêu chuẩn và Bậc hiệu suất cao cấp](/azure/storage/blobs/storage-blob-performance-tiers). Nếu bạn chọn bậc Hiệu suất cao cấp, hãy chọn [các blob khối cao cấp làm loại tài khoản](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-blob-storage"></a>Thiết lập kết nối với Bộ nhớ Blob

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Đi đến **Quản trị viên** > **Kết nối**.

1. Lựa chọn **Thêm kết nối** và lựa chọn **Lưu trữ Azure Blob**.

1. Đặt tên dễ nhận biết cho kết nối trong trường **Tên hiển thị**. Tên và loại kết nối mô tả kết nối này. Bạn nên chọn một tên giải thích mục đích và mục tiêu của kết nối.

1. Chọn người có thể sử dụng kết nối này. Theo mặc định, giá trị này là quản trị viên. Để biết thêm thông tin, hãy xem [Cho phép người đóng góp sử dụng một kết nối cho các lần xuất](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Nhập **Tên tài khoản**, **Khóa tài khoản** và **Bộ chứa** cho tài khoản Lưu trữ Blob của bạn.

1. Xem lại [quyền riêng tư và tuân thủ dữ liệu](connections.md#data-privacy-and-compliance) và chọn **tôi đồng ý**.

1. Chọn **Lưu** để hoàn thành kết nối.

## <a name="configure-an-export"></a>Định cấu hình xuất

Để định cấu hình xuất này, bạn phải có [sự cho phép](export-destinations.md#set-up-a-new-export) cho loại kết nối này.

> [!IMPORTANT]
> Nếu bạn bật [cài đặt xóa mềm](/azure/storage/blobs/soft-delete-blob-enable) đối với tài khoản Azure Blob Storage, quá trình xuất sẽ không thành công. Tắt tính năng xóa mềm để xuất dữ liệu thành các blob.

1. Đi tới **Dữ liệu** > **Nội dung xuất**.

1. Lựa chọn **Thêm xuất khẩu**.

1. Trong trường **Kết nối để xuất**, hãy chọn một kết nối từ phần Azure Blob Storage. Liên hệ với quản trị viên nếu không có kết nối.

1. Nhập tên cho lần xuất.

1. Nhập tên thư mục cho bộ lưu trữ Blob.

1. Chọn ô cạnh mỗi thực thể mà bạn muốn xuất sang vị trí này.

1. Chọn **Lưu.**

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Dữ liệu đã xuất được lưu trữ trong bộ chứa Lưu trữ Blob mà bạn đã đặt cấu hình. Đường dẫn thư mục sau đây sẽ tự động được tạo trong bộ chứa của bạn:

- Đối với thực thể nguồn và thực thể do hệ thống tạo ra:  
  *%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*  

  Ví dụ: Dynamics365CustomerInsights / CustomerInsights_ abcd1234-4312-11f4-93dc-24f72f43e7d5 /BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv
  
  > [!TIP]
  > Việc xuất các thực thể chứa một lượng lớn dữ liệu có thể dẫn đến nhiều tệp CSV trong cùng một thư mục cho mỗi lần xuất. Việc chia nhỏ xuất khẩu xảy ra vì lý do hiệu suất để giảm thiểu thời gian hoàn thành xuất khẩu.

- Model.json cho các thực thể đã xuất nằm ở *%ExportDestinationName%* mức độ.  
  
  Ví dụ: Dynamics365CustomerInsights / CustomerInsights_ abcd1234-4312-11f4-93dc-24f72f43e7d5 /BlobExport/model.json

[!INCLUDE [footer-include](includes/footer-banner.md)]
