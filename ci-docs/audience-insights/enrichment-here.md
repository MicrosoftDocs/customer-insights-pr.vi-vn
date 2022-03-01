---
title: Tăng cường với HERE Technologies tăng cường của bên thứ ba
description: Thông tin chung về tăng cường của bên thứ ba HERE Technologies.
ms.date: 10/27/2020
ms.reviewer: jodahl
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7082fcfec099c3c9436b233c193be23625f6691a
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668704"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a>Tăng cường hồ sơ khách hàng với HERE Technologies (bản xem trước)

HERE Technologies là một công ty nền tảng vị trí cung cấp dữ liệu và dịch vụ tập trung vào vị trí. Với các dịch vụ làm giàu dữ liệu của HERE Technologies, bạn có thể xây dựng kiến thức vị trí chính xác hơn về khách hàng của mình bằng cách chuẩn hóa địa chỉ, trích xuất vĩ độ và kinh độ, v.v.

## <a name="prerequisites"></a>Điều kiện tiên quyết

Để định cấu hình tính năng tăng cường HERE Technologies, bạn phải đáp ứng các điều kiện tiên quyết sau:

- Bạn có gói đăng ký HERE Technologies hoạt động. Để nhận gói đăng ký, bạn có thể [đăng ký tại đây](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) hoặc [liên hệ trực tiếp với HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you). [Tìm hiểu thêm về tính năng Tăng cường vị trí HERE Technologies.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- Bạn có khóa API HERE Technologies.

- Bạn có quyền [Quản trị viên](permissions.md#administrator).

## <a name="configuration"></a>Cấu hình

1. Chuyển tới **Dữ liệu** > **Nội dung phong phú**.

1. Chọn **Tăng cường dữ liệu của tôi** trên lát HERE Technologies.

   > [!div class="mx-imgBorder"]
   > ![lát HERE Technologies](media/HERE-tile.png "lát HERE Technologies")

1. Nhập **khóa API HERE Technologies** hiện hoạt. Xem lại và đồng ý với **Quyền riêng tư và tuân thủ dữ liệu** bằng cách đánh dấu ô **Tôi đồng ý**. 

1. Xác nhận cả hai đầu vào bằng cách chọn **Kết nối với HERE**.

1. Chọn **Thêm dữ liệu** và chọn xem bạn có muốn ánh xạ các trường với địa chỉ chính và/hoặc phụ không. Bạn có thể chỉ định ánh xạ trường cho cả hai địa chỉ (ví dụ: địa chỉ nhà riêng và địa chỉ doanh nghiệp) và tăng cường hồ sơ cho cả hai địa chỉ một cách riêng biệt. Chọn **Tiếp theo**.

1. Xác định trường nào từ hồ sơ hợp nhất của bạn sẽ được sử dụng để tìm kiếm dữ liệu vị trí phù hợp từ HERE Technologies. Các trường **Đường 1** và **Mã zip/bưu chính** là bắt buộc cho địa chỉ chính và/hoặc phụ đã chọn. Để có độ chính xác so khớp cao hơn, có thể thêm nhiều trường khác.

   > [!div class="mx-imgBorder"]
   > ![Trang cấu hình tăng cường HERE Technologies](media/enrichment-HERE-configuration.png "Trang cấu hình tăng cường HERE Technologies")

1. Chọn **Áp dụng** để hoàn thành ánh xạ trường.

## <a name="enrichment-results"></a>Kết quả làm phong phú

Để bắt đầu quá trình tăng cường, hãy chọn **Chạy** từ thanh lệnh. Bạn cũng có thể để hệ thống chạy quá trình tăng cường tự động như một phần của [làm mới theo lịch trình](system.md#schedule-tab). Thời gian xử lý sẽ phụ thuộc vào kích thước dữ liệu khách hàng của bạn và thời gian phản hồi API từ HERE Technologies.

Sau khi quá trình tăng cường hoàn tất, bạn có thể xem lại dữ liệu hồ sơ khách hàng mới được bổ sung trong **Nội dung tăng cường của tôi**. Ngoài ra, bạn sẽ tìm thấy thời gian của lần cập nhật gần nhất và số lượng hồ sơ được tăng cường.

Bạn có thể truy cập dạng xem chi tiết của từng hồ sơ được làm phong phú bằng cách chọn **Xem dữ liệu được làm phong phú**.

## <a name="next-steps"></a>Các bước tiếp theo

Xây dựng dựa trên dữ liệu khách hàng phong phú của bạn. Tạo [phân khúc](segments.md), [biện pháp](measures.md) và [xuất dữ liệu](export-destinations.md) để cung cấp trải nghiệm cá nhân cho khách hàng của bạn.

## <a name="data-privacy-and-compliance"></a>Quyền riêng tư về dữ liệu và tuân thủ

Khi bật Dynamics 365 Customer Insights để truyền dữ liệu tới HERE Technologies, bạn cho phép chuyển dữ liệu ra bên ngoài ranh giới tuân thủ cho Dynamics 365 Customer Insights, bao gồm dữ liệu nhạy cảm tiềm ẩn như Dữ liệu cá nhân. Microsoft sẽ chuyển những dữ liệu đó theo chỉ dẫn của bạn, nhưng bạn có trách nhiệm đảm bảo rằng HERE Technologies đáp ứng mọi nghĩa vụ về quyền riêng tư hoặc bảo mật mà bạn có thể có. Để biết thêm thông tin, hãy xem [Tuyên bố về Quyền riêng tư của Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Quản trị viên Dynamics 365 Customer Insights của bạn có thể xóa tính năng tăng cường này bất kỳ lúc nào để ngừng sử dụng chức năng này.
