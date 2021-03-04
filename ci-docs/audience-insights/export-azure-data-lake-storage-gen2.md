---
title: Xuất dữ liệu Customer Insights sang Azure Data Lake Storage thế hệ 2
description: Tìm hiểu cách định cấu hình kết nối với Azure Data Lake Storage thế hệ 2.
ms.date: 02/04/2021
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b00c3d6178150cbc93fe800779f094809d4dc67b
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477205"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a>Trình kết nối cho Azure Data Lake Storage thế hệ 2 (bản xem trước)

Lưu trữ dữ liệu Customer Insights của bạn trong Azure Data Lake Storage thế hệ 2 hoặc sử dụng kho lưu trữ đó để chuyển dữ liệu của bạn sang các ứng dụng khác.

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a>Định cấu hình trình kết nối cho Azure Data Lake Storage thế hệ 2

1. Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Quản trị viên** > **Nơi xuất đích**.

1. Trong **Azure Data Lake Storage thế hệ 2**, chọn **Thiết lập**.

1. Trong trường **Tên hiển thị**, hãy đặt tên cho vị trí để dễ nhận diện.

1. Nhập **Tên tài khoản**, **Khóa tài khoản** và **Bộ chứa** cho Azure Data Lake Storage Thế hệ 2 của bạn.
    - Để tìm hiểu cách tạo tài khoản lưu trữ để sử dụng với Azure Data Lake Storage thế hệ 2, hãy xem [Tạo tài khoản lưu trữ](https://docs.microsoft.com/azure/storage/blobs/create-data-lake-storage-account). 
    - Để tìm hiểu thêm về cách tìm tên tài khoản lưu trữ Azure Data Lake thế hệ 2 và khóa tài khoản, hãy xem [Quản lý cài đặt tài khoản lưu trữ trong cổng Azure](https://docs.microsoft.com/azure/storage/common/storage-account-manage).

1. Chọn **Tiếp theo**.

1. Chọn ô cạnh mỗi thực thể mà bạn muốn xuất sang vị trí này.

1. Chọn **Lưu**.

## <a name="export-the-data"></a>Xuất dữ liệu

Bạn có thể [xuất dữ liệu theo nhu cầu](export-destinations.md#export-data-on-demand). Mỗi lần [làm mới theo lịch](system.md#schedule-tab), tác vụ xuất cũng sẽ chạy.
