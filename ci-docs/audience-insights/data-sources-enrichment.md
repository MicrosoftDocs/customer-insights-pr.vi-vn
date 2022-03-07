---
title: Nguồn dữ liệu làm giàu
description: Làm phong phú nguồn dữ liệu trước khi trải qua quá trình hợp nhất dữ liệu.
ms.date: 03/02/2022
ms.subservice: audience-insights
ms.topic: how-to
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
ms.openlocfilehash: eebaaf18795e80dd1ba16a15a23844d685c94c6e
ms.sourcegitcommit: bb1f9e96023490ab340c114f54200ab4dd48da78
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 03/02/2022
ms.locfileid: "8373085"
---
# <a name="enrichment-for-data-sources-preview"></a>Làm giàu cho nguồn dữ liệu (xem trước)

Sử dụng dữ liệu từ các nguồn như Microsoft và các đối tác khác để làm phong phú thêm dữ liệu khách hàng của bạn trước khi thống nhất dữ liệu. Nguồn dữ liệu làm giàu giúp tạo ra chất lượng và tính hoàn chỉnh của dữ liệu cao hơn có thể giúp đạt được kết quả tốt hơn sau khi bạn thống nhất dữ liệu của mình. Ví dụ: sử dụng định dạng chuẩn hóa và chuẩn hóa cho các địa chỉ sẽ làm tăng chất lượng của kết quả đối sánh. Để biết danh sách các cách làm giàu được hỗ trợ, hãy xem [các tùy chọn làm giàu nguồn dữ liệu được hỗ trợ](#supported-data-source-enrichments).

## <a name="enrich-a-data-source"></a>Làm giàu nguồn dữ liệu

Bạn phải có quyền Người đóng góp hoặc Quản trị viên để tạo hoặc chỉnh sửa các nội dung phong phú. Để biết thêm thông tin, hãy xem [Quyền](permissions.md).  

1. Đi đến **Dữ liệu** > **Hợp nhất**. Chọn đối tượng bạn muốn làm giàu và chọn một thuộc tính làm khóa chính cho đối tượng. Để biết thêm thông tin, hãy xem [Chọn khóa chính](map-entities.md#select-primary-key-and-semantic-type-for-attributes).

1. Chuyển tới **Dữ liệu** > **Nguồn dữ liệu**.
 
1. Chọn dấu ba chấm dọc bên cạnh nguồn dữ liệu mà bạn muốn bổ sung và chọn **Làm giàu**.

   :::image type="content" source="media/data_sources_enrich_discover.png" alt-text="Trang làm giàu nguồn dữ liệu.":::

   Các **Phát hiện** tab hiển thị [các tùy chọn làm giàu nguồn dữ liệu được hỗ trợ](#supported-data-source-enrichments).

1. Lựa chọn **Làm phong phú dữ liệu của tôi** để định cấu hình bổ sung nguồn dữ liệu. Tên thực thể đầu ra được tự động điền.

## <a name="supported-data-source-enrichments"></a>Các cách làm giàu nguồn dữ liệu được hỗ trợ

Các bổ sung sau đây hiện có sẵn cho các nguồn dữ liệu. Xem lại các bước chi tiết của phần bổ sung để tìm hiểu cách định cấu hình nó.

- [Địa chỉ nâng cao](enrichment-enhanced-addresses.md)
- [Dữ liệu nhận dạng từ LiveRamp](enrichment-liveramp.md)

## <a name="manage-existing-data-source-enrichments"></a>Quản lý bổ sung nguồn dữ liệu hiện có

Đi đến tab **Dữ liệu tăng cường của tôi** để xem tất cả thông tin bổ sung đã đặt cấu hình.

Chọn phần tăng cường để xem các tùy chọn có sẵn. Bạn cũng có thể chọn dấu chấm lửng (...) trên một mục danh sách để xem các tùy chọn. Nếu bạn đã đặt cấu hình một số phần tăng cường, bạn có thể sử dụng hộp tìm kiếm để tìm nhanh.

Bạn có thể xem, chỉnh sửa, chạy hoặc xóa phần bổ sung nguồn dữ liệu. Để biết thêm thông tin, hãy xem [Quản lý các nội dung phong phú hiện có](enrichment-hub.md).
