---
title: Tăng cường với HERE Technologies tăng cường của bên thứ ba
description: Thông tin chung về tăng cường của bên thứ ba HERE Technologies.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 5d1f037377010153045c9255d2d01f98ebf1fdfd
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896077"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a>Tăng cường hồ sơ khách hàng với HERE Technologies (bản xem trước)

HERE Technologies là một công ty nền tảng vị trí cung cấp dữ liệu và dịch vụ tập trung vào vị trí. Với các dịch vụ làm giàu dữ liệu của HERE Technologies, bạn có thể xây dựng kiến thức vị trí chính xác hơn về khách hàng của mình bằng cách chuẩn hóa địa chỉ, trích xuất vĩ độ và kinh độ, v.v.

## <a name="prerequisites"></a>Điều kiện tiên quyết

Để định cấu hình tính năng tăng cường HERE Technologies, bạn phải đáp ứng các điều kiện tiên quyết sau:

- Bạn có gói đăng ký HERE Technologies hoạt động. Để nhận gói đăng ký, bạn có thể [đăng ký tại đây](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) hoặc [liên hệ trực tiếp với HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you). [Tìm hiểu thêm về tính năng Tăng cường vị trí HERE Technologies.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- Có sẵn một [kết nối](connections.md) HERE *hoặc* bạn có quyền của [quản trị viên](permissions.md#administrator) và khóa API HERE Technologies.

## <a name="configure-the-enrichment"></a>Đặt cấu hình nội dung bổ sung

1. Chuyển tới **Dữ liệu** > **Nội dung phong phú**. 

1. Chọn **Làm phong phú dữ liệu của tôi** trên ngăn xếp HERE Technologies rồi chọn **Bắt đầu**.

   > [!div class="mx-imgBorder"]
   > ![lát HERE Technologies](media/HERE-tile.png "lát HERE Technologies")

1. Chọn một [kết nối](connections.md) từ danh sách thả xuống. Liên hệ với quản trị viên nếu không có kết nối. Nếu là quản trị viên, bạn có thể tạo kết nối bằng cách chọn **Thêm kết nối**. Chọn **HERE Technologies** từ danh sách thả xuống. 

1. Chọn **Kết nối với HERE Technologies** để xác nhận lựa chọn.

1.  Chọn **Tiếp** rồi chọn **Tập hợp dữ liệu khách hàng** mà bạn muốn bổ sung thêm dữ liệu vị trí từ HERE Technologies. Bạn có thể chọn thực thể **khách hàng** để làm phong phú tất cả hồ sơ khách hàng của bạn hoặc chọn một thực thể phân khúc để chỉ làm phong phú thêm hồ sơ khách hàng có trong phân khúc đó.

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Ảnh chụp màn hình khi chọn tập dữ liệu khách hàng.":::

1. Chọn xem bạn có muốn ánh xạ các trường với địa chỉ chính và/hoặc phụ không. Bạn có thể chỉ định kiểu ánh xạ trường cho cả hai địa chỉ và bổ sung hồ sơ cho cả hai địa chỉ một cách riêng biệt. Ví dụ: nếu có địa chỉ nhà riêng và địa chỉ doanh nghiệp. Chọn **Tiếp theo**.

1. Xác định trường nào từ hồ sơ hợp nhất của bạn sẽ được sử dụng để tìm kiếm dữ liệu vị trí phù hợp từ HERE Technologies. Các trường **Đường 1** và **Mã zip/bưu chính** là bắt buộc cho địa chỉ chính và/hoặc phụ đã chọn. Để có độ chính xác so khớp cao hơn, có thể thêm nhiều trường khác.

   > [!div class="mx-imgBorder"]
   > ![Trang cấu hình tăng cường HERE Technologies](media/enrichment-HERE-configuration.png "Trang cấu hình tăng cường HERE Technologies")

1. Chọn **Tiếp** để hoàn thành quá trình ánh xạ trường.

1. Đặt tên cho nội dung bổ sung. 

1.Chọn **Lưu nội dung bổ sung** sau khi xem xét các lựa chọn của bạn.

## <a name="configure-the-connection-for-here-technologies"></a>Đặt cấu hình kết nối cho HERE technologies 

Bạn cần phải là quản trị viên thì mới có thể đặt cấu hình kết nối. Chọn **Thêm kết nối** khi đặt cấu hình nội dung bổ sung *hoặc* đi đến **Quản trị viên** > **Kết nối** rồi chọn **Thiết lập** trên ngăn xếp HERE Technologies.

1. Nhập tên cho kết nối trong hộp **Tên hiển thị**.

1. Cung cấp khóa API HERE Technologies hợp lệ.

1. Xem lại và đồng ý với **Quyền riêng tư về dữ liệu và tuân thủ** bằng cách đánh dấu vào hộp kiểm **Tôi đồng ý**

1. Chọn **Xác minh** để xác thực cấu hình.

1. Sau khi hoàn thành xác minh, hãy chọn **Lưu**.

> [!div class="mx-imgBorder"]
   > ![Trang cấu hình kết nối cho HERE Technologies](media/enrichment-HERE-connection.png "Trang cấu hình kết nối cho HERE Technologies")

## <a name="enrichment-results"></a>Kết quả làm phong phú

Để bắt đầu quá trình tăng cường, hãy chọn **Chạy** từ thanh lệnh. Bạn cũng có thể để hệ thống chạy quá trình tăng cường tự động như một phần của [làm mới theo lịch trình](system.md#schedule-tab). Thời gian xử lý sẽ phụ thuộc vào kích thước dữ liệu khách hàng của bạn và thời gian phản hồi API từ HERE Technologies.

Sau khi quá trình tăng cường hoàn tất, bạn có thể xem lại dữ liệu hồ sơ khách hàng mới được bổ sung trong **Nội dung tăng cường của tôi**. Ngoài ra, bạn sẽ tìm thấy thời gian của lần cập nhật gần nhất và số lượng hồ sơ được tăng cường.

Bạn có thể truy cập dạng xem chi tiết của từng hồ sơ được làm phong phú bằng cách chọn **Xem dữ liệu được làm phong phú**.

## <a name="next-steps"></a>Các bước tiếp theo

Xây dựng dựa trên dữ liệu khách hàng phong phú của bạn. Tạo [phân khúc](segments.md), [biện pháp](measures.md) và [xuất dữ liệu](export-destinations.md) để cung cấp trải nghiệm cá nhân cho khách hàng của bạn.

## <a name="data-privacy-and-compliance"></a>Quyền riêng tư về dữ liệu và tuân thủ

Khi bật Dynamics 365 Customer Insights để truyền dữ liệu tới HERE Technologies, bạn cho phép chuyển dữ liệu ra bên ngoài ranh giới tuân thủ cho Dynamics 365 Customer Insights, bao gồm dữ liệu nhạy cảm tiềm ẩn như Dữ liệu cá nhân. Microsoft sẽ chuyển những dữ liệu đó theo chỉ dẫn của bạn, nhưng bạn có trách nhiệm đảm bảo rằng HERE Technologies đáp ứng mọi nghĩa vụ về quyền riêng tư hoặc bảo mật mà bạn có thể có. Để biết thêm thông tin, hãy xem [Tuyên bố về Quyền riêng tư của Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Quản trị viên Dynamics 365 Customer Insights của bạn có thể xóa tính năng tăng cường này bất kỳ lúc nào để ngừng sử dụng chức năng này.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
