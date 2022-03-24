---
title: Tăng cường thông tin bằng dịch vụ cung cấp dữ liệu của bên thứ ba HERE Technologies
description: Thông tin chung về dịch vụ tăng cường dữ liệu của bên thứ ba HERE Technologies.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 1cbbad9bfe559bcb15b23894fc7475507aae8add
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376396"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a>Tăng cường dữ liệu hồ sơ khách hàng bằng HERE Technologies (bản xem trước)

HERE Technologies là một công ty nền tảng vị trí cung cấp dữ liệu và dịch vụ tập trung vào vị trí. Với các dịch vụ làm giàu dữ liệu của HERE Technologies, bạn có thể xây dựng kiến thức vị trí chính xác hơn về khách hàng của mình bằng cách chuẩn hóa địa chỉ, trích xuất vĩ độ và kinh độ, v.v.

## <a name="prerequisites"></a>Điều kiện tiên quyết

Để định cấu hình dịch vụ tăng cường dữ liệu HERE Technologies, bạn phải đáp ứng các điều kiện tiên quyết sau:

- Bạn có gói đăng ký HERE Technologies hoạt động. Để đăng ký, bạn có thể [thực hiện tại đây](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) hoặc [liên hệ trực tiếp với HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you). [Tìm hiểu thêm về dịch vụ Tăng cường vị trí HERE Technologies.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- [Kết nối](connections.md) HERE có sẵn *hoặc* bạn có quyền [quản trị viên](permissions.md#admin) và khóa API HERE Technologies.

## <a name="configure-the-enrichment"></a>Định cấu hình dữ liệu tăng cường

1. Chuyển tới **Dữ liệu** > **Dữ liệu tăng cường**. 

1. Chọn **Tăng cường dữ liệu của tôi** trên ngăn xếp HERE Technologies rồi chọn **Bắt đầu**.

   > [!div class="mx-imgBorder"]
   > ![Ngăn xếp HERE Technologies.](media/HERE-tile.png "lát HERE Technologies")

1. Chọn một [kết nối](connections.md) từ danh sách thả xuống. Liên hệ với quản trị viên nếu không có kết nối. Nếu là quản trị viên, bạn có thể tạo kết nối bằng cách chọn **Thêm kết nối**. Chọn **HERE Technologies** từ danh sách thả xuống. 

1. Chọn **Kết nối với HERE Technologies** để xác nhận lựa chọn.

1.  Chọn **Tiếp** rồi chọn **Tập hợp dữ liệu khách hàng** mà bạn muốn bổ sung thêm dữ liệu vị trí từ HERE Technologies. Bạn có thể chọn thực thể **Khách hàng** để tăng cường dữ liệu cho tất cả hồ sơ khách hàng của bạn hoặc chọn một thực thể phân khúc để chỉ tăng cường dữ liệu cho hồ sơ khách hàng có trong phân khúc đó.

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Ảnh chụp màn hình khi chọn tập dữ liệu khách hàng.":::

1. Chọn xem bạn có muốn ánh xạ các trường với địa chỉ chính và/hoặc phụ không. Bạn có thể chỉ định kiểu ánh xạ trường cho cả hai địa chỉ và tăng cường dữ liệu hồ sơ cho cả hai địa chỉ một cách riêng biệt. Ví dụ: nếu có địa chỉ nhà riêng và địa chỉ doanh nghiệp. Chọn **Tiếp theo**.

1. Xác định trường nào từ hồ sơ hợp nhất của bạn sẽ được sử dụng để tìm kiếm dữ liệu vị trí phù hợp từ HERE Technologies. Các trường **Đường 1** và **Mã zip/bưu chính** là bắt buộc cho địa chỉ chính và/hoặc phụ đã chọn. Để có độ chính xác so khớp cao hơn, có thể thêm nhiều trường khác.

   > [!div class="mx-imgBorder"]
   > ![Trang cấu hình tăng cường dữ liệu HERE Technologies.](media/enrichment-HERE-configuration.png "Trang cấu hình tăng cường dữ liệu HERE Technologies")

1. Chọn **Tiếp** để hoàn thành quá trình ánh xạ trường.

1. Đặt tên cho dữ liệu tăng cường. 

1. Chọn **Lưu dữ liệu tăng cường** sau khi xem xét các lựa chọn của bạn.

## <a name="configure-the-connection-for-here-technologies"></a>Định cấu hình kết nối cho HERE Technologies 

Bạn cần phải là quản trị viên thì mới có thể định cấu hình kết nối. Chọn **Thêm kết nối** khi định cấu hình dữ liệu tăng cường *hoặc* đi đến **Quản trị viên** > **Kết nối** rồi chọn **Thiết lập** trên ngăn xếp HERE Technologies.

1. Nhập tên cho kết nối trong hộp **Tên hiển thị**.

1. Cung cấp khóa API HERE Technologies hợp lệ.

1. Xem xét và chấp thuận **Quyền riêng tư dữ liệu và sự tuân thủ** bằng cách chọn **Tôi đồng ý**.

1. Chọn **Xác minh** để xác thực cấu hình.

1. Sau khi hoàn thành xác minh, hãy chọn **Lưu**.

   > [!div class="mx-imgBorder"]
   > ![Trang cấu hình kết nối cho HERE Technologies.](media/enrichment-HERE-connection.png "Trang cấu hình kết nối cho HERE Technologies")

## <a name="enrichment-results"></a>Kết quả tăng cường

Để bắt đầu quá trình tăng cường, hãy chọn **Chạy** từ thanh lệnh. Bạn cũng có thể để hệ thống chạy quá trình tăng cường tự động như một phần của [làm mới theo lịch trình](system.md#schedule-tab). Thời gian xử lý sẽ phụ thuộc vào kích thước dữ liệu khách hàng của bạn và thời gian phản hồi API từ HERE Technologies.

Sau khi quá trình tăng cường hoàn tất, bạn có thể xem xét dữ liệu hồ sơ khách hàng mới được bổ sung trong **Dữ liệu tăng cường của tôi**. Ngoài ra, bạn sẽ tìm thấy thời gian của lần cập nhật gần nhất và số lượng hồ sơ được tăng cường.

Bạn có thể truy cập dạng xem chi tiết của từng hồ sơ được tăng cường dữ liệu bằng cách chọn **Xem dữ liệu tăng cường**.

## <a name="next-steps"></a>Các bước tiếp theo

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Quyền riêng tư về dữ liệu và sự tuân thủ

Khi bật Dynamics 365 Customer Insights để truyền dữ liệu tới HERE Technologies, bạn cho phép truyền dữ liệu ra ngoài phạm vi tuân thủ cho Dynamics 365 Customer Insights, bao gồm dữ liệu có khả năng là thông tin nhạy cảm, chẳng hạn như Dữ liệu cá nhân. Microsoft sẽ truyền những dữ liệu đó theo chỉ dẫn của bạn, nhưng bạn có trách nhiệm đảm bảo rằng HERE Technologies đáp ứng mọi nghĩa vụ về quyền riêng tư hoặc bảo mật mà bạn có thể có. Để biết thêm thông tin, hãy xem [Tuyên bố về Quyền riêng tư của Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Quản trị viên Dynamics 365 Customer Insights của bạn có thể loại bỏ dịch vụ tăng cường này bất kỳ lúc nào để ngừng sử dụng tính năng đó.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
