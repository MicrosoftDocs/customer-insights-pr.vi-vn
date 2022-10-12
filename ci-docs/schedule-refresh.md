---
title: Lên lịch làm mới hệ thống
description: Lên lịch thời gian hệ thống sẽ được làm mới
ms.date: 09/27/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: 4aac02b570357d2086f7a9d7340b0e4837157a0b
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610354"
---
# <a name="schedule-system-refresh"></a>Lên lịch làm mới hệ thống

Lên lịch tự động làm mới tất cả [nguồn dữ liệu đã nhập](data-sources.md). Tự động làm mới giúp đảm bảo rằng cập nhật từ các nguồn dữ liệu được phản ánh trong hồ sơ khách hàng hợp nhất.

> [!NOTE]
> Power Query các nguồn dữ liệu do bạn quản lý làm mới theo lịch trình của riêng chúng. Để lên lịch làm mới những Power Query nguồn dữ liệu, định cấu hình cài đặt làm mới trên nguồn dữ liệu cụ thể đó từ **Nguồn dữ liệu** trang. Căn chỉnh thời gian với lịch trình làm mới dữ liệu ngược dòng để không xảy ra tất cả các lần làm mới cùng một lúc.
> :::image type="content" source="media/PPDF-edit-refresh.png" alt-text="Power Platform Cài đặt làm mới luồng dữ liệu.":::

## <a name="set-system-refresh-schedule"></a>Đặt lịch làm mới hệ thống

1. Đi đến **Quản trị viên** > **Hệ thống** và chọn **Lịch trình** chuyển hướng.

   :::image type="content" source="media/schedule_refresh.png" alt-text="Lên lịch làm mới tab từ trang Hệ thống.":::

1. Trạng thái mặc định cho làm mới theo lịch trình là **Tắt**. Để bật làm mới theo lịch trình, thay chuyển nút ở đầu màn hình thành **Bật**.

1. Chọn tùy chọn làm mới **Hàng tuần** (mặc định) và **Hàng ngày**. Nếu bạn có ý định lên lịch làm mới hàng tuần, hãy chọn một hoặc nhiều ngày mà bạn muốn chạy quy trình làm mới.

1. Đặt **Múi giờ**, sau đó sử dụng mục thả xuống **Thời gian** để đặt thời gian làm mới. Nếu bạn muốn lên lịch nhiều lần làm mới trong một ngày, hãy chọn **Thêm thời gian khác**. Bạn có thể thêm tối đa bốn lần làm mới.

1. Chọn **Lưu** để áp dụng thay đổi.

[!INCLUDE [footer-include](includes/footer-banner.md)]
