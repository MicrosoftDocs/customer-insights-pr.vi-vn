---
title: Xuất dữ liệu Thông tin chi tiết về khách hàng sang InMobi
description: Tìm hiểu cách định cấu hình kết nối và xuất sang InMobi.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ef486ad6786ef01be977f3d6bda69ce8a2b081c7
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195914"
---
# <a name="export-customer-insights-data-to-inmobi-preview"></a>Xuất dữ liệu Thông tin chi tiết về khách hàng sang InMobi (xem trước)

Xuất danh sách phân đoạn hoặc dữ liệu khác từ phiên bản Thông tin chi tiết về khách hàng của bạn sang [InMobi](https://www.inmobi.com/).

## <a name="prerequisites"></a>Điều kiện tiên quyết

- Một [Tài khoản InMobi](https://www.inmobi.com/) và thông tin đăng nhập quản trị viên.
- Một [Tài khoản lưu trữ Azure Blob](/azure/storage/blobs/create-data-lake-storage-account) tên và khóa tài khoản. Để tìm tên và khóa, hãy xem [Quản lý cài đặt tài khoản lưu trữ trong cổng Azure](/azure/storage/common/storage-account-manage).
- Một [Hộp chứa Azure Blob Storage](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container) để xuất dữ liệu InMobi sang.
- InMobi sẽ tạo kết nối trực tiếp đến Bộ nhớ Blob của bạn và định cấu hình nhập dữ liệu tự động của bạn vào InMobi. Liên hệ với đại diện InMobi của bạn để bắt đầu quá trình.

## <a name="known-limitations"></a>Các hạn chế đã biết

- Đối với Azure Blob Storage, hãy chọn giữa [Hiệu suất tiêu chuẩn và Bậc hiệu suất cao cấp](/azure/storage/blobs/storage-blob-performance-tiers). Nếu bạn chọn bậc Hiệu suất cao cấp, hãy chọn [các blob khối cao cấp làm loại tài khoản](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-azure-blob-storage"></a>Thiết lập kết nối với Azure Blob Storage

[Thiết lập kết nối với Bộ nhớ Azure Blob của bạn](export-azure-blob-storage.md).

## <a name="configure-an-export"></a>Định cấu hình xuất

[Định cấu hình xuất](export-azure-blob-storage.md#configure-an-export).

[!INCLUDE [footer-include](includes/footer-banner.md)]
