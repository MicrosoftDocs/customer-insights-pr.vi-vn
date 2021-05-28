---
title: Xuất dữ liệu Customer Insights sang Azure Blob Storage
description: Tìm hiểu cách đặt cấu hình kết nối và xuất sang bộ lưu trữ Blob.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3c19dc6d4956a33a5bd3cea706f8a154198d487f
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976207"
---
# <a name="export-segment-list-and-other-data-to-azure-blob-storage-preview"></a>Xuất danh sách phân khúc và dữ liệu khác sang Azure Blob Storage (bản xem trước)

Lưu trữ dữ liệu Customer Insights của bạn trong bộ lưu trữ Blob hoặc sử dụng bộ lưu trữ đó để chuyển dữ liệu của bạn sang các ứng dụng khác.

## <a name="set-up-the-connection-to-blob-storage"></a>Thiết lập kết nối với bộ lưu trữ Blob

1. Đi đến **Quản trị viên** > **Kết nối**.

1. Chọn **Thêm kết nối** rồi chọn **Azure Blob Storage** để đặt cấu hình kết nối.

1. Đặt tên dễ nhận biết cho kết nối trong trường **Tên hiển thị**. Tên và loại kết nối mô tả kết nối này. Bạn nên chọn một tên giải thích mục đích và mục tiêu của kết nối.

1. Chọn người có thể sử dụng kết nối này. Nếu bạn không thực hiện hành động nào, giá trị mặc định sẽ là Quản trị viên. Để biết thêm thông tin, hãy xem [Cho phép người đóng góp sử dụng một kết nối cho các lần xuất](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Nhập **Tên tài khoản**, **Khóa tài khoản** và **Bộ chứa** cho tài khoản lưu trữ Blob của bạn.
    - Để tìm hiểu thêm về cách tìm tên tài khoản lưu trữ Blob và khóa tài khoản, hãy xem [Quản lý các thiết đặt tài khoản lưu trữ trong cổng thông tin Azure](/azure/storage/common/storage-account-manage).
    - Để tìm hiểu cách tạo bộ chứa, hãy xem [Tạo bộ chứa](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Chọn **Lưu** để hoàn thành kết nối. 

## <a name="configure-an-export"></a>Đặt cấu hình xuất

Bạn có thể đặt cấu hình lần xuất này nếu bạn có quyền truy cập vào kết nối thuộc loại này. Để biết thêm thông tin, hãy xem [Các quyền cần thiết để đặt cấu hình xuất](export-destinations.md#set-up-a-new-export).

1. Đi tới **Dữ liệu** > **Nội dung xuất**.

1. Để tạo một nội dung xuất mới, hãy chọn **Thêm đích**.

1. Trong trường **Kết nối để xuất**, hãy chọn một kết nối từ phần Azure Blob Storage. Nếu bạn không thấy tên phần này, tức là không có kết nối nào thuộc loại này dành cho bạn.

1. Chọn ô cạnh mỗi thực thể mà bạn muốn xuất sang vị trí này.

1. Chọn **Lưu**.

Việc lưu một nội dung xuất sẽ không chạy nội dung xuất đó ngay lập tức.

Nội dung xuất chạy trong mỗi lần [làm mới theo lịch trình](system.md#schedule-tab).     
Bạn cũng có thể [xuất dữ liệu theo yêu cầu](export-destinations.md#run-exports-on-demand). 

Dữ liệu đã xuất được lưu trữ trong bộ lưu trữ Blob mà bạn đã đặt cấu hình. Đường dẫn thư mục sau đây sẽ tự động được tạo trong bộ chứa của bạn:

- Đối với thực thể nguồn và thực thể do hệ thống tạo ra: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`
  - Ví dụ: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`
- Tệp model.json cho các thực thể đã xuất sẽ ở cấp độ %ExportDestinationName%
  - Ví dụ: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

[!INCLUDE[footer-include](../includes/footer-banner.md)]
