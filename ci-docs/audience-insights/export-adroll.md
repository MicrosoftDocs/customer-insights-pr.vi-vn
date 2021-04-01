---
title: Xuất dữ liệu Customer Insights sang AdRoll
description: Tìm hiểu cách định cấu hình kết nối với AdRoll.
ms.date: 02/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6fedd549c2e7de362f36e3fb23d363200bb92a04
ms.sourcegitcommit: d24e52150fe5a4fab45128e12d6a03637771d9b9
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 03/19/2021
ms.locfileid: "5697100"
---
# <a name="connector-for-adroll-preview"></a>Trình kết nối cho AdRoll (xem trước)

Xuất phân khúc hồ sơ khách hàng hợp nhất sang AdRoll và sử dụng các phân khúc đó để quảng cáo. 

## <a name="prerequisites"></a>Điều kiện tiên quyết

-   Bạn có một [tài khoản AdRoll](https://www.adroll.com/) và thông tin đăng nhập tương ứng của quản trị viên.
-   Bạn có [các phân đoạn được định cấu hình](segments.md) trong thông tin chi tiết về đối tượng.
-   Hồ sơ khách hàng hợp nhất trong các phân đoạn đã xuất chứa các trường đại diện cho địa chỉ email.

## <a name="connect-to-adroll"></a>Kết nối với AdRoll

1. Đi tới **Quản trị viên** > **Đích xuất**.

1. Trong **AdRoll**, chọn **Thiết lập**.

1. Trong trường **Tên hiển thị**, hãy đặt cho đích xuất một cái tên dễ nhận biết.

   :::image type="content" source="media/AdRoll_config.PNG" alt-text="Ngăn cấu hình cho kết nối AdRoll.":::

1. Chọn **Tôi đồng ý** để xác nhận **Quyền riêng tư về dữ liệu và sự tuân thủ**.

1. Chọn **Kết nối** để khởi tạo kết nối với AdRoll.

1. Chọn **Xác thực bằng AdRoll** và cung cấp thông tin đăng nhập quản trị viên cho AdRoll. 

1. Chọn **Thêm chính bạn là người dùng xuất** và cung cấp thông tin xác thực Customer Insights.

1. Nhập **ID nhà quảng cáo AdRoll** [AdRoll có thể quảng cáo](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).

1. Chọn **Tiếp** để định cấu hình xuất.

## <a name="configure-the-connector"></a>Đặt cấu hình trình kết nối

1. Trong phần **So khớp dữ liệu**, trong trường **Email**, chọn trường trong hồ sơ khách hàng hợp nhất trình bày địa chỉ email của khách hàng. Bắt buộc phải xuất các phân khúc sang AdRoll.

1. Chọn phân khúc mà bạn muốn xuất. Chọn một phân khúc có ít nhất 100 thành viên. Bạn không thể xuất các phân khúc nhỏ hơn. Ngoài ra, kích thước tối đa của một phân khúc để xuất là 250.000 thành viên cho mỗi lần xuất. 

1. Chọn **Lưu**.

## <a name="export-the-data"></a>Xuất dữ liệu

Bạn có thể [xuất dữ liệu theo nhu cầu](export-destinations.md). Mỗi lần [làm mới theo lịch](system.md#schedule-tab), tác vụ xuất cũng sẽ chạy.

## <a name="known-limitations"></a>Các giới hạn đã biết

- Bạn có thể xuất tối đa 250.000 hồ sơ cho mỗi lần xuất sang AdRoll.
- Bạn không thể xuất các phân khúc có ít hơn 100 hồ sơ sang AdRoll. 
- Việc xuất sang AdRoll bị giới hạn ở các phân khúc.
- Có thể mất tới 10 phút để hoàn tất việc xuất tối đa 250.000 hồ sơ sang AdRoll. 
- Số lượng hồ sơ mà bạn có thể xuất sang AdRoll phụ thuộc và giới hạn vào hợp đồng của bạn với AdRoll.

## <a name="data-privacy-and-compliance"></a>Quyền riêng tư về dữ liệu và sự tuân thủ

Khi bật Dynamics 365 Customer Insights để truyền dữ liệu sang AdRoll, bạn cho phép truyền dữ liệu ra ngoài ranh giới tuân thủ của Dynamics 365 Customer Insights, bao gồm cả dữ liệu nhạy cảm như Dữ liệu cá nhân. Microsoft sẽ chuyển những dữ liệu đó theo chỉ dẫn của bạn, nhưng bạn có trách nhiệm đảm bảo rằng AdRoll đáp ứng mọi nghĩa vụ về quyền riêng tư hoặc bảo mật mà bạn có thể có. Để biết thêm thông tin, hãy xem [Tuyên bố về Quyền riêng tư của Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Quản trị viên Dynamics 365 Customer Insights của bạn có thể xóa đích xuất này bất cứ lúc nào để ngừng sử dụng chức năng này.
