---
title: Thêm mã vào trang web của bạn
description: Cách thêm đoạn mã để ghi lại các sự kiện Dynamics 365 Customer Insights trên trang web của bạn.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 09/27/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 99e1c04877993a9cd81912e3d400402aab06a7de
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 02/16/2022
ms.locfileid: "8231060"
---
# <a name="install-the-web-sdk-on-a-website"></a>Cài đặt SDK web trên một trang web

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Bài viết này mô tả cách quản trị viên cài đặt bộ công cụ phát triển phần mềm web (SDK) trên một trang web. Bạn sẽ bắt đầu xem các sự kiện trong không gian làm việc của mình ngay sau khi trang bị cho trang web của bạn. Để biết thêm thông tin, hãy xem [Quản lý không gian làm việc và môi trường](manage-environments-workspaces.md). Để thu nạp các sự kiện trong ứng dụng dành cho thiết bị di động, hãy xem [Tổng quan về nguồn lực dành cho nhà phát triển](developer-resources.md).


### <a name="prerequisites"></a>Điều kiện tiên quyết

* Bạn phải có quyền quản trị viên đối với không gian làm việc để lưu trữ dữ liệu.
* Trang web hoặc dự án của bạn phải được lưu trữ trực tuyến để gửi dữ liệu hoạt động. Dữ liệu được gửi từ một tệp cục bộ sẽ không được máy chủ chấp nhận.


## <a name="add-web-sdk-to-your-website"></a>Thêm SDK web vào trang web của bạn

Chuyển đến **Quản trị viên** > **Không gian làm việc** và rồi chọn **Hướng dẫn cài đặt**. Có hai tùy chọn cài đặt SDK web. Tùy chọn đầu là sử dụng liên kết tải xuống và tùy chọn thứ hai là cài đặt gói trình quản lý gói nút (NPM).

### <a name="option-1-using-the-download-link"></a>Tùy chọn 1: Sử dụng liên kết tải xuống

1. Chọn **Sao chép mã** để sao chép đoạn mã. Theo mặc định, khóa thu thập dữ liệu cho không gian làm việc của bạn được nhúng vào đoạn mã.
  :::image type="content" source="media/copy-code.png" alt-text="Ảnh chụp màn hình của trang đoạn mã.":::

1. Thêm mã đã sao chép vào trang web của bạn, gần <head> thẻ và trước bất kỳ tập lệnh nào khác hoặc các thẻ CSS.
1. Phát hành trang web đã cập nhật của bạn và đợi vài phút để nắm bắt lưu lượng truy cập web đến.
1. Để xem dữ liệu của bạn, hãy chọn không gian làm việc từ trình chuyển đổi không gian làm việc trong ngăn điều hướng. Sau đó, chọn một trong các báo cáo trong phần **Khám phá**.

### <a name="option-2-using-the-npm-package-recommended-for-javascript-based-web-apps"></a>Tùy chọn 2: Sử dụng gói NPM (được khuyến nghị cho Ứng dụng web dựa trên JavaScript)

1. Truy cập vào [trang web NPM](https://www.npmjs.com/package/engagementinsights-web) của chúng tôi và làm theo hướng dẫn để cài đặt và thiết lập gói NPM của SDK.
1. Phát hành trang web đã cập nhật của bạn và đợi vài phút để nắm bắt lưu lượng truy cập web đến.
1. Để xem dữ liệu của bạn, hãy chọn không gian làm việc từ trình chuyển đổi không gian làm việc trong ngăn điều hướng. Sau đó, chọn một trong các báo cáo trong phần **Khám phá**.

## <a name="configuration-options"></a>Tùy chọn cấu hình

Bạn có thể thay đổi các tùy chọn cấu hình sau trong đoạn mã:

- **ingestionKey**: Khóa thu thập dữ liệu được sử dụng để gửi các sự kiện đến không gian làm việc của bạn. Bạn có thể thay đổi khóa thu thập dữ liệu để gửi các sự kiện đến một không gian làm việc khác. Khóa nhập là duy nhất cho mỗi không gian làm việc.
- **autoCapture**: Chỉ định lượt xem trang và tương tác với trang web có được ghi lại hay không. Có hai tùy chọn:
    - **lượt xem**: Đặt thành *đúng* để nắm bắt lượt xem trang. Lượt xem trang được ghi lại dưới dạng *Lượt xem* [sự kiện](glossary.md#event), một loại [sự kiện cơ sở](glossary.md#base-event).
    - **lượt nhấp chuột**: Đặt thành *đúng* để nắm bắt các tương tác của khách truy cập trên trang web. Lượt tương tác được ghi lại dưới dạng *sự kiện* [Hành động](glossary.md#event), một loại [sự kiện cơ sở](glossary.md#base-event).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
