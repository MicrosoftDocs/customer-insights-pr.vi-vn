---
title: Kích hoạt các quy tắc về sự đồng ý cho các phân đoạn
description: Làm theo các bước sau để liên kết dữ liệu về sự đồng ý và kích hoạt tính năng kiểm tra sự đồng ý Dynamics 365 Customer Insights. Quản trị viên cũng có thể tắt kiểm tra sự đồng ý.
ms.date: 11/12/2021
ms.subservice: audience-insights
ms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: bfa03f4b7b56b300a74ebd04721cd64b893879f1
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 04/27/2022
ms.locfileid: "8644001"
---
# <a name="activate-consent-rules"></a>Kích hoạt các quy tắc về sự đồng ý

Các [Trung tâm đồng ý (xem trước)](consent-management/overview.md) giúp bạn hài hòa dữ liệu về sự đồng ý từ nhiều nguồn khác nhau. Sử dụng hợp nhất *Bằng lòng* pháp nhân để áp dụng kiểm tra sự đồng ý mặc định. Sau khi nhập dữ liệu về sự đồng ý vào Trung tâm đồng ý và định cấu hình các quy tắc cho dữ liệu, *Bằng lòng* thực thể được tự động đồng bộ hóa với Dynamics 365 Customer Insights.

## <a name="enable-consent-checks"></a>Bật kiểm tra sự chấp thuận

Với dữ liệu về sự đồng ý được nhập vào Trung tâm đồng ý (bản xem trước) và các quy tắc đã thiết lập, bạn có thể bật tính năng kiểm tra sự đồng ý. 

:::image type="content" source="consent-management/media/enable-consent-checks.png" alt-text="Tab Đồng ý trong cài đặt Thông tin chi tiết về khách hàng với dữ liệu về sự đồng ý đã được kích hoạt.":::

1. Trong Customer Insights, chuyển đến phần **Quản trị** > **Hệ thống**.

1. Chọn **Đồng ý (xem trước)** chuyển hướng.

1. Bên trong **Bật kiểm tra sự đồng ý**, đặt nút chuyển đổi thành **Trên** cho tất cả các khu vực bạn muốn kích hoạt.

1. Chọn **Cho phép ghi đè các quy tắc đồng ý mặc định** hộp kiểm để xóa các kiểm tra đồng ý mặc định được thực thi trên một phân đoạn cụ thể. 

1. Trong menu thả xuống, hãy chọn nơi bạn muốn cho phép ghi đè.     

1. Bên trong **Liên kết sự đồng ý với hồ sơ khách hàng**, hãy chọn thuộc tính được sử dụng làm mã nhận dạng để liên kết dữ liệu về sự đồng ý với dữ liệu của khách hàng. Nó có thể là một số điện thoại hoặc địa chỉ email. 

1. Lựa chọn **Cứu** để áp dụng cài đặt của bạn.

## <a name="disable-consent-checks"></a>Tắt kiểm tra sự đồng ý

Để ngừng sử dụng dữ liệu về sự đồng ý trong Thông tin chi tiết về khách hàng, quản trị viên phải cập nhật cài đặt hệ thống cho phù hợp.

1. Trong Customer Insights, chuyển đến phần **Quản trị** > **Hệ thống**.

1. Chọn **Đồng ý (xem trước)** chuyển hướng.

1. Bên trong **Bật kiểm tra sự đồng ý**, đặt nút chuyển đổi thành **Tắt**.

> [!TIP]
> Để ngừng sử dụng khả năng quản lý sự đồng ý, hãy xem [Cài đặt hệ thống trong Trung tâm đồng ý (xem trước)](consent-management/system-settings.md).
