---
title: Xuất dữ liệu Customer Insights sang Trình quản lý quảng cáo Facebook
description: Tìm hiểu cách đặt cấu hình kết nối và xuất sang Facebook Ads Manager.
ms.date: 04/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ca32906a98bc734639fb369d6f5a92e8888fd850
ms.sourcegitcommit: 6d5dd572f75ba4c0303ec77c3b74e4318d52705c
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 04/16/2021
ms.locfileid: "5906836"
---
# <a name="export-segments-list-to-facebook-ads-manager-preview"></a>Xuất danh sách phân khúc sang Facebook Ads Manager (bản xem trước)

Xuất phân khúc hồ sơ khách hàng hợp nhất sang Trình quản lý quảng cáo Facebook để tạo chiến dịch trên Facebook và Instagram.

## <a name="prerequisites-for-connection"></a>Điều kiện tiên quyết để kết nối

- Bạn cần có một [**Tài khoản quảng cáo Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) có chứa [**Tài khoản kinh doanh Facebook**](https://business.facebook.com/).
- Bạn cần phải là một quản trị viên trên [**Tài khoản quảng cáo Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).

## <a name="known-limitations"></a>Các giới hạn đã biết

- Lên đến 10 triệu hồ sơ khách hàng cho mỗi lần xuất sang Facebook Ads Manager.
- Chỉ có thể xuất các phân khúc sang Facebook.
- Chỉ tạo hoặc cập nhật đối tượng tùy chỉnh thuộc loại *danh sách khách hàng* trong Facebook.
- Có thể mất đến 90 phút để hoàn tất quá trình xuất phân khúc với tổng số 10 triệu hồ sơ.

## <a name="set-up-connection-to-facebook-ads-manager"></a>Thiết lập kết nối với Facebook Ads Manager

Quản trị viên phải đặt cấu hình kết nối với dịch vụ và cho phép những người đóng góp sử dụng kết nối này thì người dùng mới có thể tạo nội dung xuất.

1. Đi đến **Quản trị viên** > **Kết nối**.

1. Chọn **Thêm kết nối** rồi chọn **Facebook Ads Manager** để đặt cấu hình kết nối.

1. Đặt tên dễ nhận biết cho kết nối trong trường **Tên hiển thị**. Tên và loại kết nối mô tả kết nối này. Bạn nên chọn một tên giải thích mục đích và mục tiêu của kết nối.

1. Chọn người có thể sử dụng kết nối này. Nếu bạn không thực hiện hành động nào, giá trị mặc định sẽ là **Quản trị viên**. Để biết thêm thông tin, hãy xem [Cho phép người đóng góp sử dụng một kết nối cho các lần xuất](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Xác thực với Facebook Ads: 

   1. Chọn **Tiếp tục với Facebook** để đăng nhập vào Tài khoản quảng cáo Facebook.

   1. Cho phép quyền **ads_management** sau khi xác thực với Facebook.

   1. Chọn **Tài khoản quảng cáo Facebook** mà bạn muốn làm việc.

   1. Chọn **Đối tượng tùy chỉnh hiện có** từ danh sách thả xuống hoặc tạo **Đối tượng tùy chỉnh mới**. Để biết thêm thông tin, hãy xem [**Đối tượng trong Trình quản lý quảng cáo Facebook**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).
      > [!NOTE]
      > Bạn chỉ có thể tạo hoặc cập nhật đối tượng tùy chỉnh thuộc loại *danh sách khách hàng* trên Facebook qua lần xuất này. Trong một số trường hợp, bạn thấy các đối tượng tùy chỉnh thuộc loại khác nhau trong danh sách thả xuống. Việc chọn một loại khác với *danh sách khách hàng* sẽ dẫn đến việc xuất không thành công. 

1. Xem lại **Quyền riêng tư về dữ liệu và sự tuân thủ** rồi chọn **Tôi đồng ý**.

1. Chọn **Lưu** để hoàn thành kết nối.

## <a name="configure-an-export"></a>Đặt cấu hình xuất

Bạn có thể đặt cấu hình lần xuất này nếu bạn có quyền truy cập vào kết nối thuộc loại này. Để biết thêm thông tin, hãy xem [Các quyền cần thiết để đặt cấu hình xuất](export-destinations.md#set-up-a-new-export).

1. Đi tới **Dữ liệu** > **Nội dung xuất**.

1. Để tạo một nội dung xuất mới, hãy chọn **Thêm đích**. 

1. Trong **Kết nối để xuất**, hãy chọn một kết nối từ phần **Facebook Ads Manager**. Nếu bạn không thấy tên phần này, tức là không có kết nối nào thuộc loại này dành cho bạn.

1. Trong **Chọn trường mã định danh chính của bạn**, chọn **Email**, **Tên và địa chỉ** hoặc **Điện thoại** để gửi đến Trình quản lý quảng cáo Facebook. 

1. Đặt tên dễ nhận biết cho kết nối trong trường **Tên hiển thị**.

1. Ánh xạ các thuộc tính tương ứng từ thực thể khách hàng hợp nhất của bạn cho khóa định danh đã chọn.
   > [MẸO] Cơ hội tốt nhất để có kết quả khớp là khi bạn chọn **Email** làm mã định danh chính. Thêm mã định danh bổ sung có thể cải thiện kết quả khớp.

1. Chọn **Thêm thuộc tính** để ánh xạ thêm các thuộc tính cho mục đích gửi đến Facebook Ads Manager. Các thuộc tính từ Facebook Ads Manager đang ánh xạ tới các tên thân thiện với người dùng sau đây: **FN** = **Tên**, **LN** = **Họ**, **FI** = **Chữ cái đầu tiên của tên**, **PHONE** = **Số điện thoại**, **GEN** = **Giới tính**, **DOB** = **Ngày sinh**, **ST** = **Tiểu bang**, **CT** = **Thành phố**, **ZIP** = **Mã bưu chính/Mã zip**, **COUNTRY** = **Quốc gia/Khu vực**

1. Chọn phân khúc mà bạn muốn xuất.

1. Chọn **Lưu**.

Việc lưu một nội dung xuất sẽ không chạy nội dung xuất đó ngay lập tức.

Nội dung xuất chạy trong mỗi lần [làm mới theo lịch trình](system.md#schedule-tab). Bạn cũng có thể [xuất dữ liệu theo yêu cầu](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Quyền riêng tư về dữ liệu và sự tuân thủ

Khi bật Dynamics 365 Customer Insights để truyền dữ liệu tới Trình quản lý quảng cáo Facebook, bạn cho phép chuyển dữ liệu ra bên ngoài ranh giới tuân thủ cho Dynamics 365 Customer Insights, bao gồm dữ liệu nhạy cảm tiềm ẩn như Dữ liệu cá nhân. Microsoft sẽ chuyển những dữ liệu đó theo chỉ dẫn của bạn, nhưng bạn có trách nhiệm đảm bảo rằng Quảng cáo Facebook đáp ứng mọi nghĩa vụ về quyền riêng tư hoặc bảo mật mà bạn có thể có. Để biết thêm thông tin, hãy xem [Tuyên bố về Quyền riêng tư của Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Quản trị viên Dynamics 365 Customer Insights của bạn có thể xóa đích xuất này bất cứ lúc nào để ngừng sử dụng chức năng này.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
