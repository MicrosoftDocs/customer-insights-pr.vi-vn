---
title: Chạy mẫu SDK web
description: Tìm hiểu cách cá nhân hóa và chạy mẫu SDK web.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 10/30/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 97e50a51231bcf05f3e381397f0cf41e49afc10e3c3674d7c709c8f521979e12
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036629"
---
# <a name="run-the-web-sdk-sample-for-dynamics-365-customer-insights-engagement-insights-capability"></a>Chạy mẫu SDK web cho chức năng thông tin chuyên sâu về tương tác của Dynamics 365 Customer Insights

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Thư viện SDK web của chức năng thông tin chuyên sâu về tương tác là một thư viện JavaScript với mã mẫu mà bạn có thể sử dụng trên trang web của mình.

## <a name="prerequisites"></a>Điều kiện tiên quyết

- Tải [Visual Studio Code](https://code.visualstudio.com/).
- [Cài đặt tiện ích mở rộng Máy chủ trực tiếp](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) trong Visual Studio Code và làm quen với cách chạy Máy chủ trực tiếp.
- Bạn cần phải có [khóa thu thập dữ liệu](instrument-website.md).

## <a name="run-sample"></a>Chạy mẫu

1. [Tải xuống mẫu SDK web](https://download.pi.dynamics.com/sdk/EngagementInsightsSamples/ei_websdk_sample.zip).

1. Giải nén tệp nén `ei_websdk_sample.zip`.

1. Mở thư mục đã giải nén trong Visual Studio Code.

1. Trong tệp `ei_websdk_sample.html`, thay thế chuỗi "INGESTION_KEY" bằng khóa thu thập dữ liệu của bạn từ cổng thông tin chuyên sâu về tương tác và chuỗi "NAME" bằng tên chung mà bạn muốn SDK được khởi tạo. Đảm bảo rằng bạn thay thế tất cả các lần xuất hiện.

1. Mở tệp `ei_websdk_sample.html` bằng Máy chủ trực tiếp trong Visual Studio Code bằng cách chọn **Đưa vào thực hiện** từ thanh trạng thái.

1. Khi mở trang, một sự kiện xem sẽ được gửi tự động. Nhấp vào bất kỳ nút nào trên trang sẽ gửi các sự kiện hành động. Nút **Theo dõi sự kiện** cũng sẽ gửi các sự kiện tùy chỉnh. Chọn **Chuyển đến Bing** sẽ gửi một sự kiện hành động trước khi điều hướng đến trang web Bing.

1. Xem các sự kiện đang diễn ra khi bạn điều hướng đến không gian làm việc của mình. Không gian làm việc này được liên kết với khóa thu thập dữ liệu được nhập ở Bước 4.


[!INCLUDE[footer-include](../includes/footer-banner.md)]