---
title: Xuất dữ liệu Thông tin chi tiết về khách hàng sang Facebook Trình quản lý quảng cáo (chứa video)
description: Tìm hiểu cách định cấu hình kết nối và xuất sang Trình quản lý quảng cáo Facebook.
ms.date: 04/15/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 781cf10e1bb5ddaf82d4a17c7a77e0c43c41a1c2
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 02/16/2022
ms.locfileid: "8226521"
---
# <a name="export-segments-list-to-facebook-ads-manager-preview"></a>Xuất danh sách phân khúc sang Trình quản lý quảng cáo Facebook (bản xem trước)

Xuất phân khúc hồ sơ khách hàng hợp nhất sang Trình quản lý quảng cáo Facebook để tạo chiến dịch trên Facebook và Instagram.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO1aN]

## <a name="prerequisites-for-connection"></a>Điều kiện tiên quyết để kết nối

- Bạn cần có [**Tài khoản quảng cáo Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) bao gồm [**Tài khoản doanh nghiệp trên Facebook**](https://business.facebook.com/).
- Bạn cần phải là quản trị viên trên [**Tài khoản quảng cáo Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).

## <a name="known-limitations"></a>Các hạn chế đã biết

- Lên đến 10 triệu hồ sơ khách hàng/lần xuất sang Trình quản lý quảng cáo Facebook.
- Chỉ có thể xuất các phân khúc sang Facebook.
- Chỉ tạo hoặc cập nhật đối tượng tùy chỉnh thuộc loại *danh sách khách hàng* trong Facebook.
- Quá trình xuất phân khúc với tổng số 10 triệu hồ sơ khách hàng có thể mất đến 90 phút để hoàn thành.

## <a name="set-up-connection-to-facebook-ads-manager"></a>Thiết lập kết nối với Trình quản lý quảng cáo Facebook

Quản trị viên phải định cấu hình kết nối với dịch vụ và cho phép những người đóng góp sử dụng kết nối này thì người dùng mới có thể tạo nội dung xuất.

1. Đi đến **Quản trị viên** > **Kết nối**.

1. Chọn **Thêm kết nối** rồi chọn **Trình quản lý quảng cáo Facebook** để định cấu hình kết nối.

1. Đặt tên dễ nhận biết cho kết nối trong trường **Tên hiển thị**. Tên và loại kết nối mô tả kết nối này. Bạn nên chọn một tên giải thích mục đích và mục tiêu của kết nối.

1. Chọn người có thể sử dụng kết nối này. Nếu bạn không thực hiện hành động nào, giá trị mặc định sẽ là Quản trị viên. Để biết thêm thông tin, hãy xem [Cho phép người đóng góp sử dụng một kết nối cho các lần xuất](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Xác thực với Facebook Ads: 

   1. Chọn **Tiếp tục với Facebook** để đăng nhập vào Tài khoản quảng cáo Facebook của bạn.

   1. Cho phép quyền **ads_management** sau khi xác thực với Facebook.

   1. Chọn **Tài khoản quảng cáo Facebook** mà bạn muốn làm việc.

   1. Chọn một **Đối tượng tùy chỉnh hiện có** từ danh sách thả xuống hoặc tạo một **Đối tượng tùy chỉnh mới**. Để biết thêm thông tin, hãy xem [**Đối tượng trong Trình quản lý quảng cáo Facebook**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).
      > [!NOTE]
      > Bạn chỉ có thể tạo hoặc cập nhật đối tượng tùy chỉnh thuộc loại *danh sách khách hàng* trên Facebook qua lần xuất này. Trong một số trường hợp, bạn sẽ thấy các đối tượng tùy chỉnh thuộc các loại khác nhau trong danh sách thả xuống. Việc chọn một loại khác với *danh sách khách hàng* sẽ dẫn đến việc xuất không thành công. 

1. Xem lại **Quyền riêng tư về dữ liệu và sự tuân thủ** rồi chọn **Tôi đồng ý**.

1. Chọn **Lưu** để hoàn thành kết nối.

## <a name="configure-an-export"></a>Định cấu hình xuất

Bạn có thể định cấu hình lần xuất này nếu bạn có quyền truy cập vào kết nối thuộc loại này. Để biết thêm thông tin, hãy xem [Các quyền cần thiết để định cấu hình xuất](export-destinations.md#set-up-a-new-export).

1. Đi tới **Dữ liệu** > **Nội dung xuất**.

1. Để tạo một nội dung xuất mới, hãy chọn **Thêm đích**. 

1. Trong **Kết nối để xuất**, hãy chọn một kết nối từ phần **Trình quản lý quảng cáo Facebook**. Nếu bạn không thấy tên phần này thì có nghĩa là không có kết nối nào thuộc loại này khả dụng cho bạn.

1. Trong **Chọn trường mã định danh chính của bạn**, chọn **Email**, **Tên và địa chỉ** hoặc **Điện thoại** để gửi đến Trình quản lý quảng cáo Facebook. 

1. Đặt tên dễ nhận biết cho kết nối trong trường **Tên hiển thị**.

1. Ánh xạ các thuộc tính tương ứng từ thực thể khách hàng hợp nhất của bạn cho khóa định danh đã chọn.
   > [!TIP]
   > Cơ hội tốt nhất để có kết quả khớp là khi bạn chọn **Email** làm mã định danh chính. Thêm mã định danh bổ sung có thể cải thiện kết quả khớp.

1. Chọn **Thêm thuộc tính** để ánh xạ thêm các thuộc tính cho mục đích gửi đến Trình quản lý quảng cáo Facebook. Các thuộc tính từ Trình quản lý quảng cáo Facebook đang ánh xạ tới các tên thân thiện với người dùng sau đây: **FN** = **Tên**, **LN** = **Họ**, **FI** = **Chữ cái đầu tiên của tên**, **PHONE** = **Số điện thoại**, **GEN** = **Giới tính**, **DOB** = **Ngày sinh**, **ST** = **Tiểu bang**, **CT** = **Thành phố**, **ZIP** = **Mã bưu chính/Mã ZIP**, **COUNTRY** = **Quốc gia/Khu vực**

1. Chọn phân khúc mà bạn muốn xuất.

1. Chọn **Lưu**.

Việc lưu một nội dung xuất sẽ không chạy nội dung xuất đó ngay lập tức.

Nội dung xuất chạy trong mỗi lần [làm mới theo lịch trình](system.md#schedule-tab). 

Bạn cũng có thể [xuất dữ liệu theo yêu cầu](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Quyền riêng tư về dữ liệu và sự tuân thủ

Khi bật Dynamics 365 Customer Insights để truyền dữ liệu tới Trình quản lý quảng cáo Facebook, bạn cho phép chuyển dữ liệu ra bên ngoài ranh giới tuân thủ cho Dynamics 365 Customer Insights, bao gồm dữ liệu nhạy cảm tiềm ẩn như Dữ liệu cá nhân. Microsoft sẽ chuyển những dữ liệu đó theo chỉ dẫn của bạn, nhưng bạn có trách nhiệm đảm bảo rằng Quảng cáo Facebook đáp ứng mọi nghĩa vụ về quyền riêng tư hoặc bảo mật mà bạn có thể có. Để biết thêm thông tin, hãy xem [Tuyên bố về Quyền riêng tư của Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Quản trị viên Dynamics 365 Customer Insights của bạn có thể xóa đích xuất này bất cứ lúc nào để ngừng việc sử dụng chức năng này.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
