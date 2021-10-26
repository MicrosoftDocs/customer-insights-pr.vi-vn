---
title: Giới thiệu về báo cáo tùy chỉnh
description: Tìm hiểu cách tạo và tùy chỉnh báo cáo.
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 3fa801bfc8b0aee65c21b90de2423a3d5d5e4e26
ms.sourcegitcommit: d9965f4bfc09391698a34042f6b44367e53819e3
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 09/30/2021
ms.locfileid: "7582904"
---
# <a name="create-and-edit-custom-reports"></a>Tạo và chỉnh sửa báo cáo tùy chỉnh

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Ngoài các báo cáo dùng ngay (OOB), bạn có thể tạo lập báo cáo tùy chỉnh với các phần trực quan hóa bằng biểu đồ và bảng để hiểu hành vi của người dùng. Bài viết này giải thích cách tạo báo cáo với dữ liệu bạn cần bằng cách sử dụng hình ảnh trực quan dạng bảng và biểu đồ. Để biết thông tin về các báo cáo OOB, hãy xem [Xem báo cáo](view-reports.md).

## <a name="create-a-custom-report"></a>Tạo một báo cáo tùy chỉnh

1. Chuyển đến **Phân tích** > **Tùy chỉnh** để truy cập vào danh sách báo cáo tùy chỉnh.

1. Chọn **Báo cáo mới** để bắt đầu tạo báo cáo tùy chỉnh.

   :::image type="content" source="media/new-custom-report.png" alt-text="Báo cáo tùy chỉnh mới.":::

1. Xác định loại báo cáo bạn muốn tạo:

    - Chọn **Thêm hình ảnh** trong thanh lệnh để tạo hình ảnh trực quan dạng bảng theo mặc định.
    - Hoặc chọn hình ảnh trực quan dạng cột, thanh, dòng, khu vực, biểu đồ tròn, biểu đồ dạng vòng hoặc bảng từ ngăn **Trình chỉnh sửa báo cáo**.

1. Trong phần **Dữ liệu** của ngăn **Trình chỉnh sửa hình ảnh trực quan**, hãy chọn một trong các tùy chọn có sẵn (ví dụ: lượt xem trang) từ trình đơn thả xuống **Số liệu**. Bạn cũng có thể thêm **Thứ nguyên** (ví dụ: quốc gia) để hiển thị trên hình ảnh. Để biết thêm thông tin, hãy xem [Xem và tạo chỉ số](metrics.md) và [Xem và tạo thứ nguyên](dimensions.md).

   :::image type="content" source="media/page-views.png" alt-text="Chọn chỉ số cho báo cáo của bạn.":::

1. Chọn phần **Thiết kế** của ngăn **Trình chỉnh sửa hình ảnh trực quan** để thêm **Văn bản tiêu đề** rồi bật và tắt **Tiêu đề**.  Bạn cũng có thể thay đổi kiểu hình ảnh trực quan bằng cách chọn một biểu đồ khác, chẳng hạn như **biểu đồ tròn**.

1. Để thay đổi kích thước và vị trí của hình ảnh trực quan:
   - Chọn hình ảnh trực quan rồi kéo một trong các góc hoặc đường viền để điều chỉnh kích thước của hình ảnh đó.
   - Chọn hình ảnh trực quan và di chuyển đến một vị trí mới. Bạn cũng có thể sử dụng các phím mũi tên để thay đổi vị trí.
1. Để thêm hình ảnh trực quan khác, hãy chọn **Thêm hình ảnh trực quan** trên thanh lệnh.
1. Sau khi thêm các hình ảnh trực quan bạn muốn cho báo cáo, hãy chọn **Lưu** trong thanh lệnh.

1. Đặt tên cho báo cáo tùy chỉnh và chọn **Lưu** để tạo báo cáo.
 
## <a name="filter-a-custom-report"></a>Lọc báo cáo tùy chỉnh

Bạn có thể chọn khung thời gian hoặc phạm vi ngày trong báo cáo tùy chỉnh để tập trung vào một giá trị hoặc khoảng thời gian.

Để chọn khung thời gian, ở góc trên bên phải của chế độ xem báo cáo, hãy chọn một giá trị từ danh sách thả xuống của báo cáo. Bạn cũng có thể chọn một **Phạm vi ngày cố định*.

:::image type="content" source="media/filter-time-date-range.png" alt-text="Lọc theo thời gian hoặc phạm vi ngày.":::

Đối với hầu hết các báo cáo, hãy chọn **+ Thêm điều kiện**, để chọn thứ nguyên hoặc phân khúc để lọc báo cáo. Để biết thêm thông tin, hãy xem [Xem và tạo phân khúc](segments.md).

## <a name="edit-a-custom-report"></a>Chỉnh sửa báo cáo tùy chỉnh

1. Chuyển đến **Phân tích** > **Tùy chỉnh** để truy cập vào danh sách báo cáo tùy chỉnh.

1. Trong danh sách báo cáo tùy chỉnh, hãy chọn **Thêm [...]** 

1. Lựa chọn **Chỉnh sửa tên** để thay đổi tên của báo cáo.

1. Chọn tên của báo cáo rồi sử dụng tùy chọn **+ Thêm hình ảnh trực quan** và **Chỉnh sửa** để thêm, xóa, đặt lại vị trí hoặc thay đổi kích thước của các hình ảnh trực quan.

1. Để thay đổi các thuộc tính của hình ảnh trực quan, hãy chọn hình ảnh trực quan, chọn **...** và sau đó chọn **Chỉnh sửa hình ảnh trực quan**.

   :::image type="content" source="media/edit-visual-control.png" alt-text="Chỉnh sửa thuộc tính biểu đồ cho các báo cáo tùy chỉnh.":::

1. Sau khi chỉnh sửa báo cáo, hãy chọn **Lưu** để áp dụng các thay đổi. 

## <a name="delete-a-custom-report"></a>Xóa báo cáo tùy chỉnh

1. Chuyển đến **Phân tích** > **Tùy chỉnh** để truy cập vào danh sách báo cáo tùy chỉnh.

1. Trong danh sách báo cáo tùy chỉnh, hãy chọn **...**

1. Chọn **Xóa** để xóa báo cáo.

1. Xác nhận việc xóa của bạn để xóa báo cáo vĩnh viễn.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
