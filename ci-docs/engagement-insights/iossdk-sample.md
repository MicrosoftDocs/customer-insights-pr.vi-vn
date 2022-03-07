---
title: Chạy mẫu SDK iOS
description: Dự án mẫu để tìm hiểu về SDK iOS
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 06/23/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: bbe4ba648952a8081af4c8f2610276809fa5efeb
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 02/16/2022
ms.locfileid: "8232868"
---
# <a name="run-the-ios-sdk-sample"></a>Chạy mẫu SDK iOS

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Mẫu dự án iOS này giúp bạn hiểu cách SDK hoạt động trong một ứng dụng. Bạn không phải viết mã. Bạn chỉ cần thêm khóa thu thập dữ liệu là đã có thể xem các sự kiện trong không gian làm việc của mình ngay lập tức.

## <a name="prerequisites"></a>Điều kiện tiên quyết

- [Phiên bản Xcode 9 trở lên](https://developer.apple.com/xcode/downloads/)
- [Khóa thu thập dữ liệu](get-started-ios.md)

## <a name="download-the-ios-sdk-sample"></a>Tải xuống mẫu SDK iOS

1. [Tải xuống mẫu SDK iOS thông tin chuyên sâu về tương tác.](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-ios-sample.zip).
1. Giải nén tệp nén `ei-ios-sample.zip`.
1. Mở dự án ứng dụng mẫu trong Xcode.
1. Trong tệp `EIConfig.plist`, hãy thay thế chuỗi `“YOUR-INGESTION-KEY”` trong trường `ingestionKey` bằng khóa thu thập dữ liệu không gian làm việc của bạn từ thông tin chuyên sâu về tương tác trong phần **Quản trị viên** > **Không gian làm việc** > **Hướng dẫn cài đặt**.
1. Chọn **Chạy** để bắt đầu dự án mẫu.
1. Xem các sự kiện trong không gian làm việc của bạn.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
