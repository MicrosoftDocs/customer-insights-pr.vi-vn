---
title: Xuất phân đoạn sang Facebook Trình quản lý quảng cáo (xem trước) (chứa video)
description: Tìm hiểu cách định cấu hình kết nối và xuất sang Trình quản lý quảng cáo Facebook.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 01be1a075db0da05dc5536aea8a33093f9a2ea13
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195040"
---
# <a name="export-segments-to-facebook-ads-manager-preview"></a>Xuất phân đoạn sang Facebook Trình quản lý quảng cáo (xem trước)

Xuất phân khúc hồ sơ khách hàng hợp nhất sang Trình quản lý quảng cáo Facebook để tạo chiến dịch trên Facebook và Instagram.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO1aN]

## <a name="prerequisites"></a>Điều kiện tiên quyết

- Một [Facebook Tài khoản quảng cáo](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) bao gồm một [Facebook Tài khoản kinh doanh](https://business.facebook.com/).
- Đặc quyền của quản trị viên trên [Facebook Tài khoản Quảng cáo](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).

## <a name="known-limitations"></a>Các hạn chế đã biết

- Lên đến 10 triệu hồ sơ khách hàng cho mỗi lần xuất sang Facebook Trình quản lý quảng cáo, có thể mất đến 90 phút.
- Chỉ phân đoạn.
- Facebook *danh sách khách hàng* gõ vào [đối tượng tùy chỉnh](https://www.facebook.com/business/help/744354708981227?id=2469097953376494) chỉ có.
  > [!NOTE]
  > Trong một số trường hợp, bạn có thể thấy các đối tượng tùy chỉnh thuộc các loại khác nhau trong danh sách thả xuống. Nếu bạn chọn một loại khác với *danh sách khách hàng*, quá trình xuất không thành công.

## <a name="set-up-connection-to-facebook-ads-manager"></a>Thiết lập kết nối với Trình quản lý quảng cáo Facebook

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Đi đến **Quản trị viên** > **Kết nối**.

1. Lựa chọn **Thêm kết nối** và lựa chọn **Facebook Người quản lý quảng cáo**.

1. Đặt tên dễ nhận biết cho kết nối trong trường **Tên hiển thị**. Tên và loại kết nối mô tả kết nối này. Bạn nên chọn một tên giải thích mục đích và mục tiêu của kết nối.

1. [Cho phép những người đóng góp sử dụng kết nối để xuất](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Xác thực với Facebook Ads:

   1. Chọn **Tiếp tục với Facebook** để đăng nhập vào Tài khoản quảng cáo Facebook của bạn.

   1. Cho phép quyền **ads_management** sau khi xác thực với Facebook.

   1. Chọn **Tài khoản quảng cáo Facebook** mà bạn muốn làm việc.

   1. Chọn một **Đối tượng tùy chỉnh hiện có** từ danh sách thả xuống hoặc tạo một **Đối tượng tùy chỉnh mới**.

1. Xem lại [quyền riêng tư và tuân thủ dữ liệu](connections.md#data-privacy-and-compliance) và chọn **tôi đồng ý**.

1. Chọn **Lưu** để hoàn thành kết nối.

## <a name="configure-an-export"></a>Định cấu hình xuất

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Đi tới **Dữ liệu** > **Nội dung xuất**.

1. Lựa chọn **Thêm xuất khẩu**.

1. Bên trong **Kết nối để xuất**, hãy chọn một kết nối từ Facebook Phần Trình quản lý quảng cáo. Liên hệ với quản trị viên nếu không có kết nối.

1. Nhập tên cho lần xuất.

1. Bên trong **Kết nối dữ liệu** trường, chọn **E-mail**, **và địa chỉ**, hoặc **Điện thoại** gửi đến Facebook Trình quản lý quảng cáo.

1. Ánh xạ các thuộc tính tương ứng từ thực thể khách hàng hợp nhất của bạn cho khóa định danh đã chọn.
   > [!TIP]
   > Cơ hội tốt nhất để có kết quả khớp là khi bạn chọn **Email** làm mã định danh chính. Thêm mã định danh bổ sung có thể cải thiện kết quả khớp.

1. Chọn **Thêm thuộc tính** để ánh xạ thêm các thuộc tính cho mục đích gửi đến Trình quản lý quảng cáo Facebook. Các thuộc tính từ Trình quản lý quảng cáo Facebook đang ánh xạ tới các tên thân thiện với người dùng sau đây: **FN** = **Tên**, **LN** = **Họ**, **FI** = **Chữ cái đầu tiên của tên**, **PHONE** = **Số điện thoại**, **GEN** = **Giới tính**, **DOB** = **Ngày sinh**, **ST** = **Tiểu bang**, **CT** = **Thành phố**, **ZIP** = **Mã bưu chính/Mã ZIP**, **COUNTRY** = **Quốc gia/Khu vực**

1. Chọn phân khúc mà bạn muốn xuất.

1. Chọn **Lưu.**

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
