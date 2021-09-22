---
title: Bắt đầu với SDK Android
description: Tìm hiểu cách cá nhân hóa và chạy SDK Android
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 77e63929bbcc7ecff34a3839af525b76ec3c7f21173ddc5f8f2d69f11c25c441
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036944"
---
# <a name="get-started-with-the-android-sdk"></a>Bắt đầu với SDK Android

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Hướng dẫn này sẽ giúp bạn thực hiện quá trình trang bị cho ứng dụng Android bằng SDK thông tin chuyên sâu về tương tác Dynamics 365 Customer Insights. Bạn sẽ bắt đầu thấy các sự kiện trong cổng thông tin của mình sau 5 phút hoặc sớm hơn.

## <a name="configuration-options"></a>Tùy chọn cấu hình
Các tùy chọn cấu hình sau có thể được chuyển tới SDK:

- **ingestionKey**: Khóa thu thập dữ liệu được sử dụng để gửi các sự kiện đến không gian làm việc của bạn.

## <a name="prerequisites"></a>Điều kiện tiên quyết

- Android Studio

- Cấp độ API Android tối thiểu: 16 (Jelly Bean)

- Khóa thu thập dữ liệu (xem phần bên dưới để biết hướng dẫn về cách lấy)

## <a name="step-1-integrate-the-sdk-into-your-application"></a>Bước 1. Tích hợp SDK vào ứng dụng của bạn
Bắt đầu quá trình bằng cách chọn một không gian làm việc, chọn nền tảng di động Android và tải xuống SDK Android.

- Sử dụng trình chuyển đổi không gian làm việc trong ngăn điều hướng bên trái để chọn không gian làm việc của bạn.

- Nếu bạn hiện không có không gian làm việc, hãy chọn **Không gian làm việc mới** và làm theo các bước để tạo [không gian làm việc mới](create-workspace.md).

## <a name="step-2-configure-the-sdk"></a>Bước 2. Định cấu hình SDK

1. Sau khi tạo không gian làm việc, hãy chuyển đến **Quản trị viên** > **Không gian làm việc** rồi chọn **Hướng dẫn cài đặt**. 

1. Tải xuống [thông tin chuyên sâu về tương tác SDK Android](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-android-sdk.zip) và đặt tệp `eiandroidsdk-debug.aar` vào thư mục `libs`.

1. Mở tệp `build.gradle` cấp độ dự án của bạn và thêm các đoạn mã sau:
    ```gradle
    dependencies {
        implementation(name: 'eiandroidsdk-debug', ext: 'aar')
        api 'com.google.code.gson:gson:2.8.1'
    }

    repositories {
        flatDir {
            dirs 'libs'
        }
    }
    ```

1. Thiết lập cấu hình SDK thông tin chuyên sâu về tương tác thông qua tệp `AndroidManifest.xml` trong thư mục `manifests`. 
1. Sao chép đoạn mã XML từ **Hướng dẫn cài đặt**. `Your-Ingestion-Key` sẽ được tự động điền.

   > [!NOTE]
   > Bạn không cần phải thay thế phần `${applicationId}`. Phần này sẽ được tự động điền.
   

   ```xml
   <application>
   ...
       <provider
           android:authorities="${applicationId}.com.microsoft.engagementinsights.AnalyticsContentProvider"
           android:name="com.microsoft.engagementinsights.AnalyticsContentProvider" />
       <meta-data
           android:name="com.microsoft.engagementinsights.ingestionKey"
           android:value="Your-Ingestion-Key" />
       <meta-data
           android:name="com.microsoft.engagementinsights.autoCapture"
           android:value="true" />
   ...
   </application>
   ```

1. Bật hoặc tắt tính năng thu nạp tự động sự kiện `View` bằng cách đặt trường `autoCapture` ở trên thành `true` hoặc `false`.

1. (Không bắt buộc) Các cấu hình khác bao gồm việc thiết lập URL trình thu thập điểm cuối. Cấu hình này có thể được thêm vào siêu dữ liệu khóa thu thập trong `AndroidManifest.xml`:
    ```xml
        <meta-data
            android:name="com.microsoft.engagementinsights.endpointUrl"
            android:value="https://some-endpoint-url.com" />
    ```

## <a name="step-3-initialize-the-sdk-from-mainactivity"></a>Bước 3. Khởi tạo SDK từ MainActivity 

Sau khi khởi tạo SDK, bạn có thể làm việc với các sự kiện và thuộc tính của sự kiện đó trong môi trường MainActivity.

    
Java:
```java
Analytics analytics = new Analytics();
```

Kotlin:
```kotlin
var analytics = Analytics()
```

### <a name="set-property-for-all-events-optional"></a>Đặt thuộc tính cho tất cả các sự kiện (không bắt buộc)
    
Java:
```java
analytics.setProperty("year", 2021);
```

Kotlin:
```kotlin
analytics.setProperty("year", 2021)
```

Thuộc tính sự kiện ngữ cảnh gồm các loại sau:
- Chuỗi
- Ngày
- Kép
- Dài
- Boolean
- UUID

### <a name="track-an-event"></a>Theo dõi sự kiện

Java:
```java
Event event = new Event("video");
event.setProperty("duration", 320);
event.setProperty("ad_shown", true);
analytics.trackEvent(event);
```

Kotlin:
```kotlin
var event = Event("video")
event.setProperty("duration", 320)
event.setProperty("ad_shown", true)
analytics.trackEvent(event)
```

### <a name="set-user-details-for-your-event-optional"></a>Đặt chi tiết người dùng cho sự kiện của bạn (không bắt buộc)

SDK cho phép bạn xác định thông tin người dùng có thể được gửi trong mọi sự kiện. Bạn có thể chỉ định thông tin người dùng bằng cách gọi API `setUser(user: User)` cấp độ `Analytics`.

Java:
```java
User user = new User();
user.setName("testuser");
user.setEmail("abc@xyz.com");
analytics.setUser(user);
```

Kotlin:
```kotlin
var user = User()
user.name = "testuser"
user.email = "abc@xyz.com"
analytics.setUser(user)
```

Lớp dữ liệu `User` chứa các thuộc tính chuỗi sau:

- **localId**: ID cục bộ của người dùng.
- **authId**: ID người dùng đã xác thực.
- **authType**: Loại xác thực được sử dụng để lấy ID người dùng xác thực.
- **name**: Tên người dùng.
- **email**: Địa chỉ email của người dùng.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
