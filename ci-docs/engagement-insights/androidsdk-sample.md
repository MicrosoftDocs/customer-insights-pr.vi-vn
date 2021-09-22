---
title: Mẫu SDK Android
description: Dự án mẫu để tìm hiểu về SDK Android
author: britl
ms.reviewer: m-hartmann
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: ba51961bc7f9555d7dba5b6a21c8636011438d75cba87bc132b896841c467a33
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035852"
---
# <a name="run-the-android-sdk-sample"></a>Chạy mẫu SDK Android

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Mẫu dự án Android này giúp bạn hiểu cách SDK hoạt động trong một ứng dụng. Bạn không phải viết mã. Bạn chỉ cần thêm khóa thu thập dữ liệu là đã có thể xem các sự kiện trong không gian làm việc của mình ngay lập tức.

## <a name="prerequisites"></a>Điều kiện tiên quyết

- [Android Studio](https://developer.android.com/studio)
- [Khóa thu thập dữ liệu](get-started-android.md)

## <a name="download-the-android-sdk-sample"></a>Tải xuống mẫu SDK Android

1. [Tải xuống mẫu SDK Android thông tin chuyên sâu về mức độ tương tác](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-android-sample.zip).
1. Giải nén tệp nén `ei-android-sample.zip`.
1. Mở thư mục đã giải nén trong Android Studio.
1. Bên trong tệp `AndroidManifest.xml`, thay thế chuỗi `"Your-Ingestion-Key"` bằng khóa thu thập dữ liệu không gian làm việc của bạn từ thông tin chuyên sâu về mức độ tương tác trong phần **Quản trị viên** > **Không gian làm việc** > **Hướng dẫn cài đặt**. 

   > [!NOTE]
   > Bạn không cần phải thay thế phần `${applicationId}`. Phần này sẽ được tự động điền.

   ```xml
   <application>
   ...
       <provider
           android:authorities="${applicationId}.com.microsoft.engagementinsights.eiandroidsdk.AnalyticsContentProvider"
           android:name="microsoft.dynamics.engagementinsights.eiandroidsdk.AnalyticsContentProvider" />
       <meta-data
           android:name="com.microsoft.engagementinsights.ingestionKey"
           android:value="Your-Ingestion-Key" />
       <meta-data
           android:name="com.microsoft.engagementinsights.autoCapture"
           android:value="true" />
   ...
   </application>
   ```

1. Chọn **Chạy** để bắt đầu dự án mẫu.
1. Xem các sự kiện trong không gian làm việc của bạn.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
