---
title: Thêm mã vào trang web của bạn
description: Cách thêm đoạn mã để nắm bắt các sự kiện trên trang web của bạn.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 04/30/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: b5467da775a621c436bd9ddedb272506acc1e2b31dcf7c87feb5dd11e2daae2b
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035120"
---
# <a name="install-the-code-snippet-on-a-website"></a>Cài đặt đoạn mã trên trang web

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Bài viết này mô tả cách quản trị viên cài đặt đoạn mã trên trang web. Bạn sẽ bắt đầu thấy các sự kiện trong không gian làm việc ngay sau khi thêm tập lệnh vào trang web của mình. Để biết thêm thông tin, hãy xem [Quản lý không gian làm việc và môi trường](manage-environments-workspaces.md). Để thu nạp các sự kiện trong ứng dụng dành cho thiết bị di động, hãy xem [Tổng quan về nguồn lực dành cho nhà phát triển](developer-resources.md).


### <a name="prerequisites"></a>Điều kiện tiên quyết

* Bạn phải có quyền quản trị viên đối với không gian làm việc để lưu trữ dữ liệu.
* Trang web hoặc dự án của bạn phải được lưu trữ trực tuyến để gửi dữ liệu hoạt động. Dữ liệu được gửi từ một tệp cục bộ sẽ không được máy chủ chấp nhận.


## <a name="add-code-to-your-website"></a>Thêm mã vào trang web của bạn
1.  Chuyển đến **Quản trị viên** > **Không gian làm việc** và rồi chọn **Hướng dẫn cài đặt**.
1. Chọn **Sao chép mã** để sao chép đoạn mã. Theo mặc định, khóa thu thập dữ liệu cho không gian làm việc của bạn được nhúng vào đoạn mã.
:::image type="content" source="media/copy-code.png" alt-text="Ảnh chụp màn hình của trang đoạn mã.":::
3. Thêm đoạn mã đã sao chép vào trang web của bạn, gần <head> thẻ và trước bất kỳ tập lệnh nào khác hoặc các thẻ CSS.
4.  Phát hành trang web đã cập nhật của bạn và đợi vài phút để nắm bắt lưu lượng truy cập web đến.
5.  Để xem dữ liệu của bạn, hãy chọn không gian làm việc từ trình chuyển đổi không gian làm việc trong ngăn điều hướng. Sau đó, chọn một trong các báo cáo trong phần **Khám phá**.

## <a name="configuration-options"></a>Tùy chọn cấu hình

Bạn có thể thay đổi các tùy chọn cấu hình sau trong đoạn mã:

- **ingestionKey**: Khóa thu thập dữ liệu được sử dụng để gửi các sự kiện đến không gian làm việc của bạn. Bạn có thể thay đổi khóa thu thập dữ liệu để gửi các sự kiện đến một không gian làm việc khác. Khóa nhập là duy nhất cho mỗi không gian làm việc. 
- **autoCapture**: Chỉ định lượt xem trang và tương tác với trang web có được ghi lại hay không. Có hai tùy chọn:
    - **lượt xem**: Đặt thành *đúng* để nắm bắt lượt xem trang. Lượt xem trang được ghi lại dưới dạng *Lượt xem* [sự kiện](glossary.md#event), một loại [sự kiện cơ sở](glossary.md#base-event).
    - **lượt nhấp chuột**: Đặt thành *đúng* để nắm bắt các tương tác của khách truy cập trên trang web. Lượt tương tác được ghi lại dưới dạng *sự kiện* [Hành động](glossary.md#event), một loại [sự kiện cơ sở](glossary.md#base-event).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
