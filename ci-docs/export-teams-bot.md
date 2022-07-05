---
title: Bot Teams dành cho Dynamics 365 Customer Insights (bản xem trước)
description: Tra cứu hồ sơ khách hàng hợp nhất trong Microsoft Teams với sự giúp đỡ của một bot.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 62a0216de848b5a3a81fdd6ac078feb551fcfec6
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082608"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a>Bot Teams dành cho Dynamics 365 Customer Insights (bản xem trước)

Kết nối với Microsoft Teams để cho phép bot tra cứu hồ sơ khách hàng hợp nhất trong các kênh Teams.

> [!div class="mx-imgBorder"]
> ![Teams bot hiển thị hồ sơ khách hàng.](media/teams-bot.png "Teams bot hiển thị hồ sơ khách hàng")

## <a name="prerequisites"></a>Điều kiện tiên quyết

Để thiết lập và đặt cấu hình cho bot, bạn phải đáp ứng những điều kiện tiên quyết sau đây:

- Đã thêm ít nhất một [nguồn dữ liệu](data-sources.md).
- Đã hoàn thành [quy trình hợp nhất](data-unification.md).
- Đã thêm các trường vào [chỉ mục tìm kiếm và lọc](search-filter-index.md).
- Customer Insights và Teams thuộc cùng một tổ chức.
- Môi trường của bạn có đối tượng mục tiêu chính được đặt thành các khách hàng cá nhân. Tài khoản doanh nghiệp không được hỗ trợ.


> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElj]

## <a name="configure-the-bot"></a>Đặt cấu hình bot

1. Đi đến **Quản trị viên** > **Các điểm đến xuất khẩu**.
1. Trên lát Microsoft Teams, chọn **Thiết lập**.
1. Bạn sẽ được chuyển đến vùng **Ứng dụng** trong Teams. Bạn cũng có thể mở Teams rồi chọn **Ứng dụng** ở góc dưới bên trái hoặc [tải trực tiếp từ AppSource](https://go.microsoft.com/fwlink/?linkid=2124104).
1. Tìm **Customer Insights** rồi chọn ứng dụng này.
1. Chọn **Thêm**.
1. Sau khi đăng nhập vào Customer Insights trong Teams, bạn sẽ thấy thông báo chào mừng và có thể bắt đầu.

## <a name="things-you-can-do-with-the-bot"></a>Những điều bạn có thể làm với bot

Bot mang đến các chức năng tra cứu đối với hồ sơ khách hàng hợp nhất.

- Nhập **tìm kiếm** rồi đến tên, địa chỉ email hoặc bất kỳ trường nào khác trên hồ sơ khách hàng hợp nhất mà đã được thêm vào chỉ mục lọc và tìm kiếm.

  Bạn sẽ nhận được một thẻ có tối đa 15 trường từ kết quả hồ sơ khách hàng trả về. Khi có nhiều kết quả khớp, hệ thống sẽ trả về một danh sách mà bạn có thể chọn hồ sơ. Bạn có thể thêm cụm từ tìm kiếm trong ngoặc kép để tra cứu kết quả khớp hoàn toàn.

- Nếu tổ chức của bạn duy trì nhiều môi trường Customer Insights trong cùng một tổ chức, bạn có thể nhập **switchinstance** để chọn môi trường bạn muốn kết nối với bot.

- Nhập **trợ giúp** để xem danh sách các lệnh có thể dùng cho bot.  


[!INCLUDE [footer-include](includes/footer-banner.md)]