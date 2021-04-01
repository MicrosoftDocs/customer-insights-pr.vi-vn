---
title: Xuất dữ liệu Customer Insights sang Azure Data Lake Storage thế hệ 2
description: Tìm hiểu cách định cấu hình kết nối với Azure Data Lake Storage thế hệ 2.
ms.date: 02/04/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 7c0eef575f745efa6312d7141a6dd96607f9797e
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596670"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a>Trình kết nối cho Azure Data Lake Storage thế hệ 2 (bản xem trước)

Lưu trữ dữ liệu Customer Insights của bạn trong Azure Data Lake Storage thế hệ 2 hoặc sử dụng kho lưu trữ đó để chuyển dữ liệu của bạn sang các ứng dụng khác.

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a>Định cấu hình trình kết nối cho Azure Data Lake Storage thế hệ 2

1. Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Quản trị viên** > **Nơi xuất đích**.

1. Trong **Azure Data Lake Storage thế hệ 2**, chọn **Thiết lập**.

1. Trong trường **Tên hiển thị**, hãy đặt tên cho vị trí để dễ nhận diện.

1. Nhập **Tên tài khoản**, **Khóa tài khoản** và **Bộ chứa** cho Azure Data Lake Storage Thế hệ 2 của bạn.
    - Để tìm hiểu cách tạo tài khoản lưu trữ để sử dụng với Azure Data Lake Storage thế hệ 2, hãy xem [Tạo tài khoản lưu trữ](/azure/storage/blobs/create-data-lake-storage-account). 
    - Để tìm hiểu thêm về cách tìm tên tài khoản lưu trữ Azure Data Lake thế hệ 2 và khóa tài khoản, hãy xem [Quản lý cài đặt tài khoản lưu trữ trong cổng Azure](/azure/storage/common/storage-account-manage).

1. Chọn **Tiếp theo**.

1. Chọn ô cạnh mỗi thực thể mà bạn muốn xuất sang vị trí này.

1. Chọn **Lưu**.

## <a name="export-the-data"></a>Xuất dữ liệu

Bạn có thể [xuất dữ liệu theo nhu cầu](export-destinations.md#export-data-on-demand). Mỗi lần [làm mới theo lịch](system.md#schedule-tab), tác vụ xuất cũng sẽ chạy.