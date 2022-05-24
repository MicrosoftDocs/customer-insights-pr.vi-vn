---
title: Quản lý các quy tắc đồng ý mặc định trên các phân đoạn
description: Với khả năng quản lý sự đồng ý, bạn có thể tắt hoặc thay đổi các quy tắc đồng ý mặc định nếu tính năng ghi đè được bật.
ms.date: 12/01/2021
ms.topic: how-to
author: anubhav-t
ms.author: antando
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 764eeca9d99c95a34d9bd4c11d79f8b8e90701e2
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755242"
---
# <a name="disable-or-change-default-consent-rules"></a>Tắt hoặc thay đổi các quy tắc đồng ý mặc định

Nếu tổ chức của bạn sử dụng [khả năng quản lý sự đồng ý](consent-management/overview.md) với Dynamics 365 Customer Insights,[quản trị viên có thể thực thi các quy tắc về sự đồng ý](activate-consent.md) cho các phân đoạn. 

Với các quy tắc về sự đồng ý được thực thi trong khu vực phân khúc, mọi phân khúc đều thông báo về trạng thái kiểm tra sự đồng ý và các quy tắc. Nếu cho phép ghi đè, các quy tắc đồng ý mặc định sẽ bị tắt cho các phân đoạn cụ thể. Mọi người tạo ra một phân khúc đều có thể thêm các quy tắc đồng ý khác vào đầu các quy tắc mặc định cho một phân khúc. 

## <a name="for-administrators"></a>Dành cho quản trị viên

:::image type="content" source="consent-management/media/consent-rules-segment.png" alt-text="Trình tạo phân đoạn với các tùy chọn quy tắc đồng ý.":::

**Để hủy kích hoạt các quy tắc đồng ý mặc định:**

1. Bên trong **Quy tắc đồng ý** thông báo, chọn **Xem chi tiết**. 

1. Đặt **Quy tắc đồng ý mặc định** chuyển sang **Tắt**.

**Để thêm các quy tắc đồng ý khác:**

1. Bên trong **Quy tắc đồng ý** thông báo, chọn **Xem chi tiết**. 

1. Lựa chọn **Thêm quy tắc đồng ý** và chọn một quy tắc đồng ý từ **Chọn loại dữ liệu về sự đồng ý** trình đơn thả xuống.

1. Lựa chọn **Cứu** để áp dụng quy tắc mới cho phân đoạn.

## <a name="for-contributors"></a>Đối với những người đóng góp

Để tạo phân đoạn mà không có quy tắc đồng ý được thực thi, bạn phải làm việc với quản trị viên để tắt chúng trên phân đoạn của mình. Tuy nhiên, bạn có thể thêm các quy tắc về sự đồng ý của riêng mình vào các phân đoạn mà bạn sở hữu và quản lý.

Đó là một quy trình ba bước: 
1. [Tạo phân khúc](segments.md) trong Thông tin chi tiết về khách hàng và lưu nó. 

1. Chia sẻ tên phân đoạn với quản trị viên của bạn và yêu cầu họ [cho phép ghi đè cho phân đoạn của bạn](activate-consent.md). 

1. Mở lại các phân đoạn của bạn. Bên trong **Quy tắc đồng ý** thông báo, chọn **Xem chi tiết** và thêm các quy tắc đồng ý mà bạn muốn áp dụng. Sau đó, **Cứu** và **Chạy** phân khúc của bạn.



[!INCLUDE [footer-include](includes/footer-banner.md)] 
