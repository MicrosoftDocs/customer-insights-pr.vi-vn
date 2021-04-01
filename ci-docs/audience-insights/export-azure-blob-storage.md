---
title: Xuất dữ liệu Customer Insights sang bộ lưu trữ Azure Blob
description: Tìm hiểu cách đặt cấu hình cho kết nối với bộ lưu trữ Azure Blob.
ms.date: 09/18/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 0986ee5caf5fa079994ca584fb2c4d9294ddb80b
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596203"
---
# <a name="connector-for-azure-blob-storage-preview"></a>Trình kết nối dành cho bộ lưu trữ Azure Blob (xem trước)

Lưu trữ dữ liệu Customer Insights của bạn trong bộ lưu trữ Azure Blob hoặc sử dụng kho lưu trữ đó để chuyển dữ liệu của bạn sang các ứng dụng khác.

## <a name="configure-the-connector-for-azure-blob-storage"></a>Đặt cấu hình trình kết nối dành cho bộ nhớ Azure Blob

1. Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Quản trị viên** > **Nơi xuất đích**.

1. Trong **Bộ lưu trữ Azure Blob**, chọn **Thiết lập**.

1. Nhập **Tên tài khoản**, **Khóa tài khoản** và **Vùng chứa** cho tài khoản bộ lưu trữ Azure Blob.
    - Để biết cách tìm tên tài khoản và mã tài khoản Azure Blob Storage, hãy xem [Quản lý tùy chọn cài đặt của tài khoản lưu trữ trong cổng Azure](/azure/storage/common/storage-account-manage).
    - Để tìm hiểu cách tạo bộ chứa, hãy xem [Tạo bộ chứa](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Trong trường **Tên hiển thị**, hãy đặt tên cho vị trí để dễ nhận diện.

1. Chọn **Tiếp theo**.

1. Chọn ô cạnh mỗi thực thể mà bạn muốn xuất sang vị trí này.

1. Chọn **Lưu**.

Dữ liệu đã xuất sẽ được lưu trữ trong vùng chứa của bộ lưu trữ Azure Blob mà bạn đã đặt cấu hình. Đường dẫn thư mục sau đây sẽ tự động được tạo trong bộ chứa của bạn:

- Đối với thực thể nguồn và thực thể do hệ thống tạo ra: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`
  - Ví dụ: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`
- model.json cho các thực thể đã xuất có ở cấp độ %ExportDestinationName%
  - Ví dụ: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

## <a name="export-the-data"></a>Xuất dữ liệu

Bạn có thể [xuất dữ liệu theo nhu cầu](export-destinations.md#export-data-on-demand). Mỗi lần [làm mới theo lịch](system.md#schedule-tab), tác vụ xuất cũng sẽ chạy.


[!INCLUDE[footer-include](../includes/footer-banner.md)]