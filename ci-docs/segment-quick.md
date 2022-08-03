---
title: Tạo các phân đoạn đơn giản với các phân đoạn nhanh chóng
description: Tạo các phân khúc khách hàng đơn giản để phân nhóm dựa trên các thuộc tính khác nhau.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-segments
- ci-segment-builder
- ci-segment-details
- customerInsights
ms.openlocfilehash: 98260371a17ff8a05912cc1bc08c67fbe9755727
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 07/18/2022
ms.locfileid: "9171169"
---
# <a name="create-simple-segments-with-quick-segments"></a>Tạo các phân đoạn đơn giản với các phân đoạn nhanh chóng

Phân khúc nhanh cho phép bạn tạo nhanh các phân khúc đơn giản với một toán tử để có thông tin chi tiết nhanh chóng hơn. Phân khúc nhanh chỉ được hỗ trợ trong các môi trường cho **khách hàng cá nhân**.

## <a name="create-a-new-segment-with-quick-segments"></a>Tạo một phân đoạn mới với các phân đoạn nhanh chóng

1. Đi đến **Phân khúc**.

1. Lựa chọn **Mới** > **Tạo từ**.
   - Chọn **Hồ sơ** để xây dựng phân khúc dựa trên thực thể *khách hàng hợp nhất*.
   - Chọn tùy chọn **Giá trị đo** để tạo một phân khúc xoay quanh các giá trị đo mà bạn đã tạo trước đó.
   - Chọn tùy chọn **Thông tin** để xây dựng một phân khúc xung quanh một trong các thực thể đầu ra mà bạn tạo bằng một trong hai chức năng **Dự đoán** hoặc **Mô hình tùy chỉnh**.

1. Trong hộp thoại **Phân khúc nhanh mới**, hãy chọn một thuộc tính từ mục thả xuống **Trường**. Dựa trên lựa chọn của bạn, hệ thống cung cấp các giá trị khác nhau.
   - Đối với các trường phân loại, 10 số lượng khách hàng hàng đầu sẽ hiển thị. Chọn **Giá trị** rồi chọn **Xem lại**.
   - Đối với thuộc tính số, hệ thống hiển thị giá trị thuộc tính nào thuộc phân vị của mỗi khách hàng. Chọn một **Toán tử** và một **Giá trị**, sau đó chọn **Xem lại**.

1. Hệ thống cung cấp một **Kích thước phân đoạn ước tính**. Chọn tạo phân đoạn bạn đã xác định hay quay lại để chọn một trường khác.

   :::image type="content" source="media/quick-segment-name.png" alt-text="Tên và ước tính cho một phân khúc nhanh.":::

1. Cung cấp một **Tên** và **Tên thực thể đầu ra** cho phân khúc của bạn. Tùy chọn, thêm [thẻ](work-with-tags-columns.md#manage-tags).

1. Chọn **Lưu** để tạo phân khúc. Các **Phân đoạn** hiển thị trang.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="next-steps"></a>Các bước tiếp theo

[Xuất một phân khúc](export-destinations.md) và khám phá [Tích hợp thẻ khách hàng](customer-card-add-in.md) để sử dụng các phân khúc trong các ứng dụng khác.

[!INCLUDE [footer-include](includes/footer-banner.md)]
