---
title: Chạy mẫu SDK web
description: Tìm hiểu cách cá nhân hóa và chạy mẫu SDK web.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 545f4a7e9660e339dee1070ad727d5d398eb6254
ms.sourcegitcommit: 693458e13e4b4d94b6205093559912f6a4dc4a1c
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 10/06/2021
ms.locfileid: "7606291"
---
# <a name="run-the-web-sdk-sample-for-dynamics-365-customer-insights-engagement-insights-capability"></a>Chạy mẫu SDK web cho chức năng thông tin chuyên sâu về tương tác của Dynamics 365 Customer Insights

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Thư viện SDK web của chức năng thông tin chuyên sâu về tương tác là một thư viện JavaScript với mã mẫu mà bạn có thể sử dụng trên trang web của mình.

## <a name="prerequisites"></a>Điều kiện tiên quyết

- Tải [Visual Studio Code](https://code.visualstudio.com/).
- [Cài đặt tiện ích mở rộng Máy chủ trực tiếp](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) trong Visual Studio Code và làm quen với cách chạy Máy chủ trực tiếp.
- Bạn phải có một [không gian làm việc thông tin chi tiết về mức độ tương tác](create-workspace.md).

## <a name="run-sample"></a>Chạy mẫu

1. [Tải xuống mẫu SDK web](https://download.pi.dynamics.com/sdk/EngagementInsightsSamples/ei_websdk_sample.zip).

1. Giải nén tệp nén `ei_websdk_sample.zip`.

1. Mở thư mục đã giải nén trong Visual Studio Code.

1. Chuyển đến cổng thông tin chi tiết về mức độ tương tác cho không gian làm việc. Chọn **Quản trị viên** > **Không gian làm việc** rồi chọn **Hướng dẫn cài đặt**. Làm theo tùy chọn đầu tiên rồi chọn **Sao chép mã** để sao chép đoạn mã JavaScript.

1. Trong tệp `ei_websdk_sample.html`, dán đoạn mã mà bạn đã sao chép vào dòng sau:

   - <-- DÁN ĐOẠN MÃ JAVASCRIPT TỪ CỔNG THÔNG TIN CHI TIẾT VỀ MỨC ĐỘ TƯƠNG TÁC VÀO ĐÂY, BÊN DƯỚI DÒNG NÀY -->

1. Mở tệp `ei_websdk_sample.html` bằng Máy chủ trực tiếp trong Visual Studio Code bằng cách chọn **Đưa vào thực hiện** từ thanh trạng thái.

1. Khi mở trang, một sự kiện xem sẽ được gửi tự động. Nhấp vào bất kỳ nút nào trên trang sẽ gửi các sự kiện hành động. Nút **Theo dõi sự kiện** cũng sẽ gửi các sự kiện tùy chỉnh. Chọn **Chuyển đến Bing** sẽ gửi một sự kiện hành động trước khi điều hướng đến trang web Bing.

1. Xem các sự kiện đang diễn ra khi bạn điều hướng đến không gian làm việc của mình. Không gian làm việc này được liên kết với khóa thu thập dữ liệu được nhập ở Bước 4.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
