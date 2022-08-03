---
title: Bot Teams dành cho Dynamics 365 Customer Insights (bản xem trước)
description: Tra cứu hồ sơ khách hàng hợp nhất trong Microsoft Teams với sự giúp đỡ của một bot.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: d140ae72578b48091a41005c4acafe03bac540da
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195868"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a>Bot Teams dành cho Dynamics 365 Customer Insights (bản xem trước)

Kết nối với Microsoft Teams để cho phép bot tra cứu hồ sơ khách hàng hợp nhất trong các kênh Teams.

:::image type="content" source="media/teams-bot.png" alt-text="Teams bot hiển thị hồ sơ khách hàng":::

## <a name="prerequisites"></a>Điều kiện tiên quyết

- Ít nhất một [Đã thêm nguồn dữ liệu](data-sources.md).
- Đã hoàn thành [quy trình hợp nhất](data-unification.md).
- Các trường được thêm vào [tìm kiếm và lọc chỉ mục](search-filter-index.md).
- Customer Insights và Teams thuộc cùng một tổ chức.
- Môi trường của bạn có đối tượng mục tiêu chính được đặt thành các khách hàng cá nhân. Tài khoản doanh nghiệp không được hỗ trợ.


> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElj]

## <a name="configure-the-bot"></a>Đặt cấu hình bot

1. Đi đến **Quản trị viên** > **Kết nối**.
1. Trên lát Microsoft Teams, chọn **Thiết lập**.
1. Bạn sẽ được chuyển đến vùng **Ứng dụng** trong Teams. Bạn cũng có thể mở Teams rồi chọn **Ứng dụng** ở góc dưới bên trái hoặc [tải trực tiếp từ AppSource](https://go.microsoft.com/fwlink/?linkid=2124104).
1. Tìm **Customer Insights** rồi chọn ứng dụng này.
1. Chọn **Thêm**.
1. đăng nhập vào Thông tin chi tiết về khách hàng trong Nhóm. Một thông báo chào mừng hiển thị.

## <a name="things-you-can-do-with-the-bot"></a>Những điều bạn có thể làm với bot

Bot mang đến các chức năng tra cứu đối với hồ sơ khách hàng hợp nhất.

- đi vào **Tìm kiếm** theo sau là tên, địa chỉ email hoặc bất kỳ trường nào khác trên hồ sơ khách hàng hợp nhất được thêm vào chỉ mục tìm kiếm & lọc.

  Bạn sẽ nhận được một thẻ có tối đa 15 trường từ kết quả hồ sơ khách hàng trả về. Khi có nhiều kết quả khớp, hệ thống sẽ trả về một danh sách mà bạn có thể chọn hồ sơ. Để tra cứu một kết hợp chính xác, hãy thêm cụm từ tìm kiếm trong dấu ngoặc kép.

- Nếu tổ chức của bạn duy trì nhiều môi trường Thông tin chi tiết về khách hàng trong cùng một tổ chức, hãy nhập **switchinstance** để chọn môi trường bạn muốn kết nối với bot.

- Nhập **trợ giúp** để xem danh sách các lệnh có thể dùng cho bot.  

[!INCLUDE [footer-include](includes/footer-banner.md)]