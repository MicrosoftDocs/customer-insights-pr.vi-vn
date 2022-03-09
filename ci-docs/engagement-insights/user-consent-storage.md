---
title: Quản lý cookie và sự chấp thuận của người dùng để lưu trữ dữ liệu người dùng trong Dynamics 365 Customer Insights
description: Hiểu cách sử dụng cookie và sự đồng ý của người dùng để xác định khách truy cập trang web.
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 09/27/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 018263220d4628690e9f0beb8453e58b0356d099
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 02/16/2022
ms.locfileid: "8229011"
---
# <a name="manage-cookies-and-user-consent"></a>Quản lý cookie và sự đồng ý của người dùng

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Chức năng thông tin chi tiết về tương tác Dynamics 365 Customer Insights sử dụng cookie và (`localStorage`) khóa để xác định khách truy cập trang web.

Cookie là các tệp nhỏ lưu trữ các bit thông tin về tương tác của người dùng với trang web. Cookie được lưu trữ trong các trình duyệt web. Khi người dùng truy cập trang web đã lưu trữ cookie, trình duyệt sẽ gửi thông tin đó đến máy chủ, máy chủ sẽ trả về thông tin duy nhất cho người dùng. Đây là công nghệ cho phép, ví dụ: một giỏ hàng trực tuyến giữ các mặt hàng đã chọn trong đó ngay cả khi người dùng điều hướng khỏi trang web.

## <a name="user-consent"></a>Sự đồng ý của người dùng

[Quy định Chung về Bảo vệ Dữ liệu (GDPR)](/dynamics365/get-started/gdpr/) là một quy định của Liên minh Châu Âu (EU) đặt ra cách các tổ chức phải xử lý quyền riêng tư và bảo mật của người dùng. Cookie thường lưu trữ hoặc thu thập "dữ liệu cá nhân", chẳng hạn như số nhận dạng trực tuyến, được quy định trong GDPR. Nếu doanh nghiệp của bạn sử dụng và/hoặc bán cho các chủ thể dữ liệu ở Liên minh Châu Âu, thì GDPR sẽ ảnh hưởng đến bạn. [Tìm hiểu thêm về cách Microsoft có thể giúp bạn tuân thủ GDPR](https://www.microsoft.com/trust-center/privacy/gdpr-faqs).

Để cho phép SDK thông tin chuyên sâu về tương tác lưu trữ cookie hoặc thông tin nhạy cảm khác, bạn phải xác định xem người dùng của mình có đồng ý hay không. Điều này diễn ra khi khởi chạy SDK bằng cách đặt một trường `userConsent` trong cấu hình.

Nếu bạn cho biết rằng không có sự đồng ý của người dùng, SDK sẽ không lưu trữ bất kỳ dữ liệu nào và sẽ không gửi các sự kiện có thể được sử dụng để theo dõi hành vi của người dùng. Mọi dữ liệu đã lưu trữ trước đó sẽ bị xóa khỏi trình duyệt.

Nếu không có giá trị đồng ý của người dùng nào được chỉ định, SDK sẽ cho rằng người dùng đã đồng ý. Điều này có nghĩa là nếu bạn (với tư cách là khách hàng của chúng tôi) không chỉ định giá trị cho sự đồng ý của người dùng trong SDK, thì dữ liệu sẽ được thu thập. Tuy nhiên, nếu bạn chỉ định rằng giá trị cho sự đồng ý của người dùng cần phải là "đúng", thì dữ liệu sẽ không được thu thập nếu người dùng từ chối hoặc không đưa ra được sự đồng ý rõ ràng.

Dưới đây là đoạn mã để khởi chạy SDK web với sự chấp thuận của người dùng:
```js
<script>
  (function(a,t,i){var e="MSEI";var s="Analytics";var o=e+"queue";a[o]=a[o]||[];var r=a[e]||function(n){var t={};t[s]={};function e(e){while(e.length){var r=e.pop();t[s][r]=function(e){return function(){a[o].push([e,n,arguments])}}(r)}}var r="track";var i="set";e([r+"Event",r+"View",r+"Action",i+"Property",i+"User","initialize","teardown"]);return t}(i.name);var n=i.name;if(!a[e]){a[n]=r[s];a[o].push(["new",n]);setTimeout(function(){var e="script";var r=t.createElement(e);r.async=1;r.src=i.src;var n=t.getElementsByTagName(e)[0];n.parentNode.insertBefore(r,n)},1)}else{a[n]=new r[s]}if(i.user){a[n].setUser(i.user)}if(i.props){for(var c in i.props){a[n].setProperty(c,i.props[c])}}a[n].initialize(i.cfg)})(window,document,{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
    name:"EiJS",
    cfg:{
      ingestionKey:"YOUR-INGESTIONKEY",
      autoCapture:{
        view:true,
        click:true
      },
      userConsent: true
    }
  });
</script>
```

## <a name="visitor-data-storage-in-engagement-insights-capability"></a>Lưu trữ dữ liệu khách truy cập trong chức năng thông tin chuyên sâu về tương tác

### <a name="cookies"></a>Cookie

- _msei
    - Lưu trữ ID người dùng ẩn danh. Cookie này được đặt trong miền khách hàng và sẽ hết hạn sau 365 ngày.

### <a name="local-storage"></a>Lưu trữ cục bộ

Chức năng thông tin chi tiết về tương tác cũng tận dụng (`localStorage`) khóa để theo dõi dữ liệu không nhạy cảm. Dữ liệu này được lưu trữ đầy đủ trong chính trình duyệt, không có lưu lượng truy cập nào được gửi đến hoặc từ máy chủ của bạn.

- *EISession.Id*
    - Lưu trữ thông tin về phiên người dùng đang diễn ra, chẳng hạn như ID phiên, thời điểm bắt đầu và khi hết hạn.
- *EISession.Previous*
    - Lưu trữ URL của trang đã truy cập trước đó trong phiên hiện tại.

Các khóa trong bộ nhớ cục bộ không tự động hết hạn và chúng sẽ được đặt lại trong phiên SDK tiếp theo.

## <a name="deleting-cookies"></a>Xóa cookie

Khách hàng của bạn có thể cookie và khóa lưu trữ cục bộ theo cách thủ công bất kỳ lúc nào thông qua cài đặt trình duyệt của họ.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
