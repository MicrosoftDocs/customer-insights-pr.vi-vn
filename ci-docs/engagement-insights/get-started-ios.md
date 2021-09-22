---
title: Bắt đầu với SDK iOS
description: Tìm hiểu cách cá nhân hóa và chạy SDK iOS
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: de8291fc429ae6433301a47bfdf9a3271b1b77294fd58448c7aa6bd0783edc97
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036899"
---
# <a name="get-started-with-the-ios-sdk"></a>Bắt đầu với SDK iOS

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Hướng dẫn này sẽ giúp bạn thực hiện quá trình trang bị cho ứng dụng iOS bằng SDK thông tin chuyên sâu về tương tác Dynamics 365 Customer Insights. Bạn sẽ bắt đầu thấy các sự kiện trong cổng thông tin của mình sau 5 phút hoặc sớm hơn.

## <a name="configuration-options"></a>Tùy chọn cấu hình

Các tùy chọn cấu hình sau có thể được chuyển tới SDK thông qua tệp `EIConfig.plist` được cung cấp:

- **ingestionKey**: Khóa thu thập dữ liệu được sử dụng để gửi các sự kiện đến dự án của bạn.
- **autocollectAction**: Giá trị Boolean để bật hoặc tắt tính năng tự động trang bị sự kiện hành động.
- **autocollectView**: Giá trị Boolean để bật hoặc tắt tính năng tự động trang bị sự kiện xem.
- **endpointUrl**: URL điểm cuối nơi các sự kiện sẽ được chuyển đến.

## <a name="prerequisites"></a>Điều kiện tiên quyết

- Phiên bản Xcode 9 trở lên
- Phiên bản iOS 8.2 trở lên
- Khóa thu thập dữ liệu (xem hướng dẫn bên dưới về cách lấy)

## <a name="integrate-the-sdk-into-your-application"></a>Tích hợp SDK vào ứng dụng của bạn

Bắt đầu quá trình bằng cách chọn một không gian làm việc, chọn nền tảng di động iOS và tải xuống SDK.

- Sử dụng trình chuyển đổi không gian làm việc trong ngăn điều hướng bên trái để chọn không gian làm việc của bạn.

- Nếu bạn hiện không có không gian làm việc, hãy chọn **Không gian làm việc mới** và làm theo các bước để tạo [không gian làm việc mới](create-workspace.md).

## <a name="configure-the-sdk"></a>Định cấu hình SDK

Sau khi tải xuống SDK, bạn có thể làm việc với SDK đó trong Xcode để kích hoạt và xác định sự kiện.

1. Sau khi tạo không gian làm việc, hãy chuyển đến **Quản trị viên** > **Không gian làm việc** rồi chọn **Hướng dẫn cài đặt**.

1. Tải xuống [thông tin chuyên sâu về tương tác SDK iOS](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-ios-sdk.zip) và đặt tệp `EIObjC.xcframework` vào thư mục `Frameworks`.

1. Nếu `Frameworks` không tồn tại, hãy tạo một thư mục như vậy trong thư mục dự án.

## <a name="enable-auto-instrumentation"></a>Bật tính năng tự động trang bị
 
Bạn có thể dễ dàng kích hoạt tính năng tự động trang bị mà không cần mã hóa. Khi chạy, dự án sẽ tự động theo dõi sự kiện `view` và `action` bằng cách sử dụng khóa thu thập dữ liệu đã định cấu hình. 

1. Cập nhật và đưa tệp `EIConfig.plist` được cung cấp vào thư mục dự án của bạn cho các trường sau:
    - ingestionKey = `"Your-Ingestion-Key"`
    - autocollectView = CÓ
    - autocollectAction = CÓ

2. Sau đó, thêm tệp `EIConfig.plist` vào dự án của bạn trong Xcode. 



Để tắt tính năng tự động trang bị, hãy cập nhật các trường sau trong tệp `EIConfig.plist` vào thư mục dự án của bạn. 

```objectivec
'autocollectView' = NO (to disable)
'autocollectAction' = NO (to disable)
```


## <a name="implement-custom-events"></a>Triển khai sự kiện tùy chỉnh

1. Mở dự án của bạn trong Xcode và chuyển đến cài đặt **Chung**. 
1. Thêm `EIObjC.xcframework` vào dự án trong phần "Khung công việc, Thư viện và Nội dung nhúng".

1. Nhập tệp tiêu đề khung công việc trong AppDelegate.m với đoạn mã sau đây:

    ```objectivec
    #import <EIObjC/EIObjC.h>
    ```

1. Khởi tạo SDK thông tin chuyên sâu về tương tác từ ứng dụng: didFinishLaunchingWithOptions.
1. Sao chép đoạn mã XML từ **Hướng dẫn cài đặt**.

    ```objectivec
    NSError *error = [NSError new];
    id<EIIAnalytics> analytics = [EIAnalyticsProvider analyticsForIngestionKey:nil error:&error];
    ```

1. Theo dõi sự kiện:

    ```objectivec
    EIEvent *event = [EIEvent new];
    event.name = @"video.log";
    [event setLongValue:320 forKey:@"duration"];
    [event setBoolValue:YES forKey:@"ad_shown"];
    [analytics trackEvent:event];
    ```

## <a name="set-user-details-for-your-event"></a>Đặt chi tiết người dùng cho sự kiện của bạn

SDK cho phép bạn xác định thông tin người dùng có thể được gửi trong mọi sự kiện. Bạn có thể chỉ định thông tin người dùng bằng cách gọi API `setUser:(nonnull EIUser *)user` trên SDK.

Chỉ định chi tiết người dùng trên cấp độ `Analytics` có nghĩa là tất cả các phép đo từ xa sẽ có thông tin này. Tuy nhiên, nếu bạn chỉ định ở cấp độ sự kiện bằng cách gọi API `setUser:(nonnull EIUser *)user` trên đối tượng EIEvent, chỉ sự kiện cụ thể đó mới chứa thông tin.

Lớp dữ liệu `EIUser` chứa các thuộc tính NSString sau:

- **localId**: ID cục bộ của người dùng.
- **authId**: ID người dùng đã xác thực.
- **authType**: Loại xác thực được sử dụng để nhận ID người dùng đã xác thực.
- **name**: Tên người dùng.
- **email**: Địa chỉ email của người dùng.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
