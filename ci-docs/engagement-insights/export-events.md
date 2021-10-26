---
title: Xuất các sự kiện đã tinh chỉnh
description: Cách xuất các sự kiện đã tinh chỉnh và các sự kiện cơ sở.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 7881f8f63134170a7f76e3c75dcfc5fa8930754b
ms.sourcegitcommit: 693458e13e4b4d94b6205093559912f6a4dc4a1c
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 10/06/2021
ms.locfileid: "7606290"
---
# <a name="export-events"></a>Xuất sự kiện

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Sự kiện đại diện cho hành vi của người dùng. Sự kiện ghi lại khi người dùng xem một trang (xem sự kiện) hoặc tương tác với nội dung (sự kiện hành động). Khi bạn có thể quyết định thuộc tính nào của dữ liệu mà bạn muốn hiển thị trong báo cáo, chế độ xem dữ liệu ảo này được gọi là *sự kiện đã tinh chỉnh*. Để biết thêm thông tin, hãy xem [Tạo và chỉnh sửa sự kiện](refined-events.md).

- Bạn có thể xuất các sự kiện và sự kiện đã tinh chỉnh sang bộ nhớ ngoài. 
- Nội dung xuất là luồng dữ liệu chuyển tiếp. Bạn không thể nạp lại luồng. 
- Nội dung xuất có các lược đồ cố định. Nếu bạn thêm các thuộc tính tùy chỉnh vào một sự kiện, các thuộc tính này sẽ không được thêm. Bạn sẽ cần tạo một bản xuất mới.

## <a name="prerequisites"></a>Điều kiện tiên quyết

Trước khi thiết lập nội dung xuất, bạn cần có quyền truy cập và đăng ký hoạt động đối với cổng thông tin Azure. Bạn sẽ cần thông tin tài khoản lưu trữ trong quá trình xuất. 

### <a name="create-an-azure-data-lake-storage-gen-2-accounts"></a>Tạo tài khoản thế hệ 2 của Azure Data Lake Storage

1. Đăng nhập vào cổng thông tin Azure và [tạo một tài khoản lưu trữ mới](/azure/storage/common/storage-account-create). 

1. Đảm bảo rằng bạn bật **Vùng tên phân cấp** trên tab **Nâng cao**. 

   :::image type="content" source="media/enable-hierarchical-namespace.png" alt-text="Bật vùng tên phân cấp trên tab nâng cao.":::

1. Sau khi triển khai, hãy chuyển đến tài khoản lưu trữ mới tạo. Trong ngăn điều hướng, hãy chọn **Cài đặt** > **Khóa truy cập**. 

1. Sao chép **Tên tài khoản** và **Khóa** để sử dụng khi tạo một bản xuất mới.
   :::image type="content" source="media/storage-account-access-keys.png" alt-text="Khóa truy cập trong tài khoản lưu trữ.":::

## <a name="export-events"></a>Xuất sự kiện

Có hai cách để mở hộp thoại **Xuất sự kiện**: 
- Chuyển đến **Dữ liệu** > **Nội dung xuất** và chọn **Bản xuất mới**.
- Đi đến **Dữ liệu** > **Sự kiện**, chọn **Thêm [...]** bên cạnh sự kiện bạn muốn xuất rồi chọn **Xuất** từ menu thả xuống. 

:::image type="content" source="media/new-export.png" alt-text="Tạo xuất mới.":::

Bạn được hướng dẫn qua các bước để tạo bản xuất:

1. Nhập **Tên xuất** rồi chọn **Tiếp**.

1. Trong danh sách thả xuống của phần **Lựa chọn sự kiện**, chọn sự kiện cơ sở và sự kiện tinh chỉnh để xuất. 

1. Trong phần **Cấu trúc tệp**, chọn nhịp (hàng giờ hoặc hàng ngày) để tạo tệp mới trong bộ nhớ đích, rồi chọn **Tiếp**. Các sự kiện được xuất liên tục khi được tạo.

1. Trong hộp thoại **Chọn định dạng**, chọn định dạng cho bản xuất. Chọn trong các định dạng **Common Data Model**, **CSV** và **JSON**. Để sử dụng bản xuất với các ứng dụng Dynamics 365 khác, chúng tôi khuyên bạn nên chọn định dạng **Common Data Model**.

1. Trong hộp thoại **Chọn đích đến**, chỉ định vị trí Azure Data Lake Storage thế hệ 2.
    1. **Tên tài khoản ADLS thế hệ 2** là tên của tài khoản lưu trữ mà bạn muốn lưu bản xuất. 
    1. **Đường dẫn thư mục** xác định nơi bản xuất nên được lưu trữ trong hệ thống tệp và cấu trúc thư mục của tài khoản lưu trữ.
    1. **Khóa chia sẻ** có sẵn từ cổng thông tin Azure cho tài khoản lưu trữ.

1. Xem lại và xác nhận lựa chọn để hoàn tất.

## <a name="view-and-manage-exports"></a>Xem và quản lý nội dung xuất

Khi bạn đã thiết lập bản xuất, hãy chuyển đến **Dữ liệu** > **Nội dung xuất** để xem. Lựa chọn **Thêm [...]** cho mọi bản xuất hiện có để chỉnh sửa hoặc xóa.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
