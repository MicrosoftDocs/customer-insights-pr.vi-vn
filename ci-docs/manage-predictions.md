---
title: Quản lý dự đoán
description: Tìm hiểu cách quản lý, khắc phục sự cố và tinh chỉnh dự đoán.
ms.date: 11/01/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: a180f6462452d9830d0daa150a35a9d0acad925a
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082860"
---
# <a name="manage-predictions"></a>Quản lý dự đoán

Bài viết này thảo luận về một số tác vụ mà hầu hết các kịch bản dự đoán đều có.

## <a name="troubleshoot-a-failed-prediction"></a>Khắc phục sự cố dự đoán không thành công

1. Đi đến **Thông tin** > **Dự đoán** và chọn tab **Dự đoán của tôi**.

1. Chọn dấu chấm lửng dọc bên cạnh dự đoán mà bạn muốn xem nhật ký lỗi.

1. Chọn **Nhật ký**.

1. Xem lại tất cả lỗi. Có một số loại lỗi có thể xảy ra và chúng mô tả nguyên nhân gây ra lỗi. Ví dụ: một lỗi không đủ dữ liệu để dự đoán chính xác thường được giải quyết bằng cách tải thêm dữ liệu vào Customer Insights.

## <a name="input-data-usability-report"></a>Báo cáo khả năng sử dụng dữ liệu đầu vào

Báo cáo khả năng sử dụng dữ liệu đầu vào cung cấp một dạng xem tổng hợp về các lỗi và cảnh báo mà các dự đoán có sẵn của bạn có thể đang tạo ra. Báo cáo này cũng đưa ra đề xuất về cách cải thiện hiệu suất của mô hình.

Báo cáo này có sẵn sau khi một mô hình đã hoàn tất quá trình đào tạo. Báo cáo được tạo cho từng mô hình riêng biệt, bất kể quá trình có hoàn tất thành công hay không.

### <a name="view-the-input-data-usability-report"></a>Xem báo cáo khả năng sử dụng dữ liệu đầu vào

Sau khi một mô hình có sẵn đã hoàn thành bước đào tạo, hãy xem báo cáo theo các cách sau:
- Chọn dấu chấm lửng bên cạnh tên mô hình rồi chọn **Báo cáo khả năng sử dụng dữ liệu đầu vào**.
- Chọn trạng thái của một mô hình rồi chọn **Xem báo cáo khả năng sử dụng dữ liệu đầu vào** trong ngăn bên.
- Chọn một trong các mô hình trong danh sách rồi chọn **Báo cáo khả năng sử dụng dữ liệu đầu vào** trên thanh lệnh.
- Mở trang kết quả mô hình rồi chọn **Báo cáo khả năng sử dụng dữ liệu đầu vào** trên thanh lệnh.

### <a name="information-in-the-input-data-usability-report"></a>Thông tin trong báo cáo khả năng sử dụng dữ liệu đầu vào

Các cột sau trong báo cáo chứa thông tin hữu ích để cải thiện dữ liệu cho mô hình.

:::image type="content" source="media/input-data-usability-report.png" alt-text="Ví dụ về một báo cáo khả năng sử dụng dữ liệu đầu vào hiển thị một bảng có lỗi, cảnh báo và đề xuất.":::

- **Tên:** Tên mô tả của lỗi, cảnh báo hoặc khuyến nghị.
- **Bươc:** Giai đoạn mô hình, đào tạo hoặc điểm số, thông tin đề cập đến.
- **Tiểu bang:** Mức độ nghiêm trọng của thông tin (lỗi, cảnh báo, khuyến nghị).
- **Tên cột dọc:** Cột trong một thực thể cần được sửa đổi để cải thiện hiệu suất mô hình.
- **Tên thực thể:** Tên của thực thể cần được sửa đổi để cải thiện hiệu suất của mô hình.
- **Thông tin chi tiết:** Thông tin chi tiết về lỗi, cảnh báo hoặc khuyến nghị.

## <a name="refresh-a-prediction"></a>Làm mới một dự đoán

Các dự đoán sẽ tự động làm mới trên cùng một [trình làm mới dữ liệu](system.md#schedule-tab) như định cấu hình trong thiết đặt. Bạn cũng có thể làm mới chúng theo cách thủ công.

1. Đi đến **Thông tin** > **Dự đoán** và chọn tab **Dự đoán của tôi**.

1. Chọn các hình elip dọc bên cạnh dự đoán bạn muốn làm mới.

1. Chọn **Làm mới**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="delete-a-prediction"></a>Xóa dự đoán

Xóa dự đoán cũng xóa thực thể đầu ra của nó.

1. Đi đến **Thông tin** > **Dự đoán** và chọn tab **Dự đoán của tôi**.

1. Chọn các hình elip dọc bên cạnh dự đoán bạn muốn xóa.

1. Chọn **Xóa**.
