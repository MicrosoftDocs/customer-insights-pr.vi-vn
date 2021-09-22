---
title: Nhận biết các sự kiện web từ những khách truy cập đã xác thực trước đó với tính năng chưa xác định thành xác định
description: Tính năng chưa xác định thành xác định cho phép bạn liên kết các sự kiện trên trang web với những khách truy cập đã xác thực trước đó.
ms.reviewer: mhart
ms.author: mkisel
author: mkisel11
ms.date: 7/15/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: overview
ms.manager: shellyha
ms.openlocfilehash: d1bbc3315b55e2ee233dc672456e0c27e4ad0fbd5937af09cc790c96ee274000
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036809"
---
# <a name="recognize-web-events-from-previously-authenticated-visitors"></a>Nhận biết các sự kiện web từ những khách truy cập đã xác thực trước đó

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Tính năng **chưa xác định thành xác định** trong chức năng thông tin chi tiết về mức độ tương tác cho phép liên kết các sự kiện trên một trang web với khách truy cập đã xác thực trước đó. Nếu tính năng bị tắt, những khách truy cập đã xác thực trong lần truy cập trước đó và sau đó rời đi sẽ không được xác định nếu không xác thực lại khi quay lại. 

Ví dụ: một người đã truy cập một trang web vào tuần trước, đăng nhập vào tài khoản người dùng của họ trên trang web và duyệt qua danh mục sản phẩm. Người đó quay lại vào tuần sau để duyệt thêm các sản phẩm mà không cần đăng nhập vào tài khoản của họ. Chủ sở hữu trang web sử dụng tính năng **chưa xác định thành xác định** sẽ biết rằng cùng một người đã quay lại và những gì họ đã làm trên trang web. Điều này cho phép báo cáo và phân tích chính xác hơn các hoạt động của trang web.

## <a name="enable-unknown-to-known"></a>Đã bật tính năng chưa xác định thành xác định

Bạn cần phải là [quản trị viên không gian làm việc](user-roles.md) để bật tính năng này. 

1. Trong thông tin chi tiết về mức độ tương tác, hãy đi tới **Quản trị viên** > **Không gian làm việc**. 
2. Chọn tab **Cài đặt**.
3. Trong phần **Chưa xác định thành xác định**, đặt nút chuyển đổi thành **Đã bật**.

![Đã bật tính năng chưa xác định thành xác định](media/U2Ktoggle.png "Đã bật tính năng chưa xác định thành xác định")

## <a name="adding-javascript-code-to-your-sites-tracking-snippet"></a>Thêm mã JavaScript vào đoạn mã theo dõi của trang web của bạn

Một trang web có thể ghi lại **user authId** với mẫu JavaScript sau bằng cách sử dụng [SDK web thông tin chi tiết về mức độ tương tác](advanced-SDK-implementation.md). Để tính năng **chưa xác định thành xác định** hoạt động, bạn cần ghi lại authId *và* bật userMapping:True trong đoạn mã JavaScript của bạn như trong mẫu bên dưới.

```
[…]
window, document
{
src:"https://download.pi.dynamics.com/sdk/web/mspi-0.min.js",
name:"myproject",
cfg:{
ingestionKey:<paste your ingestion key>",
autoCapture:{
view:true,
click:true
},
userMapping: true
},
user:{
authId: getLoggedInUserId()*,
email: getLoggedInUserEmail()*,
authType: "MSA",
name: "Alex Jensen"
}
[…]
```

[!INCLUDE[footer-include](../includes/footer-banner.md)]
