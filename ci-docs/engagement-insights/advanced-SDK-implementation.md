---
title: Tình huống SDK trang web nâng cao
description: Các tình huống nâng cao cần xem xét khi chỉnh sửa trang web của bạn bằng SDK.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 09/27/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: a083d8215f295af0884257a016b62b8c7e4ab2c7
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 02/16/2022
ms.locfileid: "8227224"
---
# <a name="advanced-web-sdk-instrumentation"></a>Thiết bị SDK web nâng cao

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Bài viết này hướng dẫn bạn các tình huống nâng cao để xem xét khi [chỉnh sửa trang web của bạn](instrument-website.md) bằng SDK chức năng thông tin chuyên sâu về tương tác của Dynamics 365 Customer Insights.

## <a name="setting-user-details-for-your-event"></a>Thiết lập chi tiết người dùng cho sự kiện của bạn

SDK cho phép bạn xác định thông tin người dùng có thể được gửi trong mọi sự kiện. Bạn có thể chỉ định chi tiết người dùng trong thuộc tính có tên `user` (dữ liệu kỳ vọng cho thuộc tính này là đối tượng `IUser`), tương tự như `src`, `name` và `cfg` trong cấu hình đoạn mã.

Đối tượng `IUser` đối tượng chứa các thuộc tính chuỗi sau:

- **localId**: ID cục bộ của người dùng.
- **authId**: ID người dùng đã xác thực.
- **authType**: Loại xác thực được sử dụng để nhận ID người dùng đã xác thực.
- **name**: Tên người dùng.
- **email**: Địa chỉ email của người dùng.

Ví dụ sau cho thấy đoạn mã đang gửi thông tin người dùng. Khi bạn thấy các hàm có ký hiệu dấu hoa thị * đứng trước, hãy thay thế hàm đó bằng triển khai tùy chỉnh của bạn:

```
[…]
window, document
{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
    name:"myproject",
    cfg:{
      ingestionKey:<paste your ingestion key>",
      autoCapture:{
        view:true,
        click:true
      }
    },
    user:{
      authId: getLoggedInUserId()*,
      email: getLoggedInUserEmail()*,
      authType: "MSA",
      name: "John Doe"
    }
[…]
```

Bạn cũng có thể chỉ định thông tin người dùng bằng cách gọi API `setUser(user: IUser)`. Phương pháp đo từ xa được gửi sau khi gọi API `setUser` sẽ chứa thông tin người dùng.

## <a name="adding-custom-properties-for-each-event"></a>Thêm thuộc tính tùy chỉnh cho từng sự kiện

SDK cho phép bạn chỉ định thuộc tính tùy chọn có thể được gửi với mọi sự kiện. Bạn có thể chỉ định các thuộc tính tùy chỉnh dưới dạng một đối tượng chứa các cặp khóa-giá trị (giá trị có thể thuộc loại `string | number | boolean`). Bạn có thể thêm đối tượng trong một thuộc tính có tên `props`, tương tự như `src`, `name` và `cfg` trong cấu hình đoạn mã.

Ví dụ sau cho thấy đoạn mã đang gửi thuộc tính tùy chọn:

```
[…]
window, document
{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
    name:"myproject",
    cfg:{
      ingestionKey:<paste your ingestion key>",
      autoCapture:{
        view:true,
        click:true
      }
    },
    props:{
      "key_name_string": "value",
      "key_name_number": 10,
      "key_name_bool": true
    }
[…]
```

Bạn cũng có thể chỉ định từng thuộc tính tùy chỉnh bằng cách gọi API `setProperty(name: string, value: string | number | boolean)`.

## <a name="sending-custom-events"></a>Gửi sự kiện tùy chỉnh

Bạn có thể sử dụng SDK để gửi các sự kiện tùy chỉnh. Bạn phải chỉ định tên cho sự kiện và các thuộc tính sẽ được gửi cùng với sự kiện.

Ví dụ sau cho thấy đoạn mã đang theo dõi sự kiện tùy chỉnh. "NAME" là giá trị trong khóa `name` trong cấu hình đoạn mã. Nó cũng là tên biến trong đối tượng cửa sổ, ở vị trí SDK được tải.

```
window["NAME"].trackEvent({
    name: "event_name",
    properties: {
        "duration": 320,
        "name": "getting_started",
        "ad_shown": true
    }
});
```


[!INCLUDE[footer-include](../includes/footer-banner.md)]
