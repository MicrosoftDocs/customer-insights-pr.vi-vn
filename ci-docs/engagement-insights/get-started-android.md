---
title: Bắt đầu với SDK Android
description: Tìm hiểu cách cá nhân hóa và chạy SDK Android
author: britl
ms.reviewer: mhart
ms.custom: intro-internal
ms.author: britl
ms.date: 10/19/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: b06822b2c2d6a859bdf808f7800baef43c4ab874
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 02/16/2022
ms.locfileid: "8226195"
---
# <a name="get-started-with-the-android-sdk"></a>Bắt đầu với SDK Android

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Hướng dẫn này sẽ giúp bạn thực hiện quá trình trang bị cho ứng dụng Android bằng SDK thông tin chi tiết về tương tác Dynamics 365 Customer Insights. Bạn sẽ bắt đầu thấy các sự kiện trong cổng thông tin của mình sau 5 phút hoặc sớm hơn.

## <a name="configuration-options"></a>Tùy chọn cấu hình
Các tùy chọn cấu hình sau có thể được chuyển tới SDK:

- **ingestionKey**: Khóa thu thập dữ liệu được sử dụng để gửi các sự kiện đến không gian làm việc của bạn.

## <a name="prerequisites"></a>Điều kiện tiên quyết

- Android Studio

- Cấp độ API Android tối thiểu: 16 (Jelly Bean)

- Khóa thu thập dữ liệu (xem phần bên dưới để biết hướng dẫn về cách lấy)

## <a name="integrate-the-sdk-into-your-application"></a>Tích hợp SDK vào ứng dụng của bạn
Bắt đầu quá trình bằng cách chọn một không gian làm việc, chọn nền tảng di động Android và tải xuống SDK Android.

- Sử dụng trình chuyển đổi không gian làm việc trong ngăn điều hướng bên trái để chọn không gian làm việc của bạn.

- Nếu bạn hiện không có không gian làm việc, hãy chọn **Không gian làm việc mới** và làm theo các bước để tạo [không gian làm việc mới](create-workspace.md).

- Sau khi tạo không gian làm việc, hãy chuyển đến **Quản trị viên** > **Không gian làm việc** rồi chọn **Hướng dẫn cài đặt**.

## <a name="configure-the-sdk"></a>Đặt cấu hình SDK

Sau khi tải xuống SDK, bạn có thể làm việc với SDK đó trong Android Studio để kích hoạt và xác định sự kiện. Có hai cách để làm vậy:
### <a name="option-1-use-jitpack-recommended"></a>Tùy chọn 1: Sử dụng JitPack (khuyến nghị)
1. Thêm kho lưu trữ JitPack vào `build.gradle` gốc của bạn:
    ```gradle
    allprojects {
        repositories {
            ...
            maven { url 'https://jitpack.io' }
        }
    }
    ```

1. Thêm phần phụ thuộc:
    ```gradle
    dependencies {
        implementation 'com.github.microsoft:engagementinsights-sdk-android:v1.0.0'
        api 'com.google.code.gson:gson:2.8.1'
    }
    ```

### <a name="option-2-use-download-link"></a>Tùy chọn 2: Sử dụng liên kết tải xuống
1. Tải xuống [thông tin chi tiết về tương tác SDK Android](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-android-sdk.zip) và đặt tệp `eiandroidsdk-debug.aar` vào thư mục `libs`.

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

## <a name="enable-auto-instrumentation"></a>Bật tính năng tự động trang bị

1. Thêm quyền cho mạng và Internet trong tệp `AndroidManifest.xml` nằm ở thư mục `manifests`.
    ```xml
    <manifest>
        ...
        <uses-permission android:name="android.permission.INTERNET" />
        <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
    ```

1. Thiết lập cấu hình SDK thông tin chi tiết về tương tác thông qua tệp `AndroidManifest.xml`.

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

   >[!NOTE]
   >`Action` sự kiện cần được thêm thủ công.

1. (Không bắt buộc) Các cấu hình khác bao gồm việc thiết lập URL trình thu thập điểm cuối. Chúng có thể được thêm vào trong siêu dữ liệu khóa nhập trong `AndroidManifest.xml`.

   ```xml
        <meta-data
            android:name="com.microsoft.engagementinsights.endpointUrl"
            android:value="https://some-endpoint-url.com" />
   ```

## <a name="implement-custom-events"></a>Triển khai sự kiện tùy chỉnh

Sau khi khởi tạo SDK, bạn có thể làm việc với các sự kiện và thuộc tính của sự kiện đó trong môi trường `MainActivity`.


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

## <a name="set-user-details-for-your-event-optional"></a>Đặt chi tiết người dùng cho sự kiện của bạn (không bắt buộc)

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
