---
title: Xuất dữ liệu Thông tin chi tiết về khách hàng sang InMobi
description: Tìm hiểu cách định cấu hình kết nối và xuất sang InMobi.
ms.date: 06/27/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8261c8adfe231792e70fc85432237cf73d5cd5a7
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 06/29/2022
ms.locfileid: "9059622"
---
# <a name="export-segment-list-and-other-data-to-inmobi-preview"></a>Xuất danh sách phân đoạn và dữ liệu khác sang InMobi (xem trước)

Xuất danh sách phân đoạn hoặc dữ liệu khác từ phiên bản Thông tin chi tiết về khách hàng của bạn sang [InMobi](https://www.inmobi.com/).

## <a name="prerequisites"></a>Điều kiện tiên quyết

1. Bạn có một [Tài khoản InMobi](https://www.inmobi.com/) và thông tin đăng nhập quản trị viên.
1. Bạn có tên tài khoản lưu trữ Azure Blob và khóa tài khoản tương ứng. Để biết thêm thông tin, hãy xem [Quản lý cài đặt tài khoản lưu trữ trong cổng Azure](/azure/storage/common/storage-account-manage). Có một vùng chứa trong tài khoản lưu trữ để xuất dữ liệu inMobi sang. Để biết thêm thông tin, hãy xem [Tạo một thùng chứa](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).
1. InMobi sẽ tạo kết nối trực tiếp đến Bộ nhớ Blob của bạn và định cấu hình nhập dữ liệu tự động của bạn vào InMobi. Liên hệ với đại diện InMobi của bạn để bắt đầu quá trình.

## <a name="known-limitations"></a>Các hạn chế đã biết

1. Đối với Azure Blob Storage, bạn có thể chọn giữa [Hiệu suất tiêu chuẩn và Bậc hiệu suất cao cấp](/azure/storage/blobs/storage-blob-performance-tiers). Nếu bạn chọn bậc Hiệu suất cao cấp, hãy chọn [các blob khối cao cấp làm loại tài khoản](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-the-connection-to-azure-blob-storage-and-configure-an-export"></a>Thiết lập kết nối với Azure Blob Storage và định cấu hình xuất

1. Làm theo hướng dẫn để [thiết lập kết nối với Azure Blob Storage của bạn](export-azure-blob-storage.md).
2. Làm theo hướng dẫn để [định cấu hình xuất](export-azure-blob-storage.md#configure-an-export).

[!INCLUDE [footer-include](includes/footer-banner.md)]
