---
title: Xuất dữ liệu Customer Insights sang Trình quản lý quảng cáo Facebook
description: Tìm hiểu cách định cấu hình kết nối tới Trình quản lý quảng cáo Facebook.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c839f9dc7e403412c0e3d936392d45a43bc63545
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270000"
---
# <a name="connector-for-facebook-ads-manager-preview"></a>Trình kết nối cho Trình quản lý quảng cáo Facebook (bản xem trước)

Xuất phân khúc hồ sơ khách hàng hợp nhất sang Trình quản lý quảng cáo Facebook để tạo chiến dịch trên Facebook và Instagram.

## <a name="prerequisites"></a>Điều kiện tiên quyết

- Bạn cần có [**Tài khoản quảng cáo Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) bao gồm [**Tài khoản doanh nghiệp Facebook**](https://business.facebook.com/).
- Bạn cần phải là một quản trị viên trên [**Tài khoản quảng cáo Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).

## <a name="connect-to-facebook-ads-manager"></a>Kết nối với Trình quản lý quảng cáo Facebook

1. Đi tới **Quản trị viên** > **Đích xuất**.

1. Trong **Trình quản lý quảng cáo Facebook**, chọn **Thiết lập**.

1. Trong trường **Tên hiển thị**, hãy đặt cho đích xuất một cái tên dễ nhận biết.

1. Chọn **Tiếp tục với Facebook** để đăng nhập vào Tài khoản quảng cáo Facebook.

1. Cho phép quyền **ads_management** sau khi xác thực với Facebook.

1. Chọn **Tài khoản quảng cáo Facebook** mà bạn muốn làm việc.

1. Chọn **Đối tượng tùy chỉnh hiện có** từ danh sách thả xuống hoặc tạo **Đối tượng tùy chỉnh mới**. Để biết thêm thông tin, hãy xem [**Đối tượng trong Trình quản lý quảng cáo Facebook**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).

1. Chọn **Tôi đồng ý** để xác nhận **Quyền riêng tư về dữ liệu và sự tuân thủ**.

1. Chọn **Tiếp** để định cấu hình xuất.

## <a name="configure-the-connector"></a>Đặt cấu hình trình kết nối

1. Trong **Chọn trường mã định danh chính của bạn**, chọn **Email**, **Tên và địa chỉ** hoặc **Điện thoại** để gửi đến Trình quản lý quảng cáo Facebook.

1. Ánh xạ các thuộc tính tương ứng từ thực thể khách hàng hợp nhất của bạn cho khóa định danh đã chọn.
   > [MẸO] Cơ hội tốt nhất để có kết quả khớp là khi bạn chọn **Email** làm mã định danh chính. Thêm mã định danh bổ sung có thể cải thiện kết quả khớp.

1. Chọn **Thêm thuộc tính** để ánh xạ các thuộc tính bổ sung để gửi đến Trình quản lý quảng cáo Facebook. Các thuộc tính từ Trình quản lý quảng cáo Facebook đang ánh xạ tới các tên thân thiện với người dùng sau: **FN** = **Tên**, **LN** = **Họ**, **FI** = **Chữ cái đầu**, **PHONE** = **Điện thoại**, **GEN** = **Giới tính**, **DOB** = **Ngày sinh**, **ST** = **Tiểu bang**, **CT** = **Thành phố**, **ZIP** = **Mã bưu chính/Mã zip**, **COUNTRY** = **Quốc gia/Khu vực**

1. Chọn phân khúc mà bạn muốn xuất.

1. Chọn **Lưu**.

## <a name="export-the-data"></a>Xuất dữ liệu

Bạn có thể [xuất dữ liệu theo nhu cầu](export-destinations.md). Mỗi lần [làm mới theo lịch](system.md#schedule-tab), tác vụ xuất cũng sẽ chạy.

## <a name="known-limitations"></a>Các giới hạn đã biết

- Lên đến 10 triệu hồ sơ khách hàng cho mỗi lần xuất sang Facebook Ads Manager 
- Xuất sang Facebook Ads Manager bị giới hạn ở các phân đoạn
- Quá trình xuất phân đoạn với tổng số 10 triệu hồ sơ có thể mất đến 90 phút để hoàn tất

## <a name="data-privacy-and-compliance"></a>Quyền riêng tư về dữ liệu và sự tuân thủ

Khi bật Dynamics 365 Customer Insights để truyền dữ liệu tới Trình quản lý quảng cáo Facebook, bạn cho phép chuyển dữ liệu ra bên ngoài ranh giới tuân thủ cho Dynamics 365 Customer Insights, bao gồm dữ liệu nhạy cảm tiềm ẩn như Dữ liệu cá nhân. Microsoft sẽ chuyển những dữ liệu đó theo chỉ dẫn của bạn, nhưng bạn có trách nhiệm đảm bảo rằng Quảng cáo Facebook đáp ứng mọi nghĩa vụ về quyền riêng tư hoặc bảo mật mà bạn có thể có. Để biết thêm thông tin, hãy xem [Tuyên bố về Quyền riêng tư của Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Quản trị viên Dynamics 365 Customer Insights của bạn có thể xóa đích xuất này bất cứ lúc nào để ngừng sử dụng chức năng này.


[!INCLUDE[footer-include](../includes/footer-banner.md)]