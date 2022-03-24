---
title: Tăng cường dữ liệu hồ sơ công ty bằng dịch vụ tăng cường dữ liệu của bên thứ ba Leadspace
description: Thông tin chung về dịch vụ tăng cường dữ liệu của bên thứ ba Leadspace.
ms.date: 09/30/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 0db0c984f6bf9f7ded0704b6fa0caf39c7dace3a
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376810"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a>Tăng cường dữ liệu hồ sơ công ty bằng Leadspace (bản xem trước)

Leadspace là một công ty khoa học dữ liệu cung cấp Nền tảng dữ liệu khách hàng B2B. Nó cho phép các môi trường có hồ sơ khách hàng hợp nhất dựa trên các tài khoản để làm phong phú thêm dữ liệu của họ. Làm phong phú *Hồ sơ khách hàng* với các thuộc tính như vị trí, ngành hoặc quy mô công ty. Làm phong phú *Hồ sơ liên hệ* với các thuộc tính như chức danh, chân dung hoặc xác minh email.

## <a name="prerequisites"></a>Điều kiện tiên quyết

Để định cấu hình Leadspace, phải đáp ứng các điều kiện tiên quyết sau đây:

- Bạn có một giấy phép Leadspace hiện hoạt.
- Bạn có [hồ sơ khách hàng hợp nhất](customer-profiles.md) dựa trên tài khoản.
- Một kết nối Leadspace đã được quản trị viên định cấu hình hoặc bạn có quyền của [quản trị viên](permissions.md#admin) và “khóa vĩnh viễn” (còn gọi là **Mã thông báo Leadspace**). Liên hệ trực tiếp với [Leadspace](https://www.leadspace.com/leadspace-microsoft-dynamics-365/) để biết thông tin chi tiết về sản phẩm của họ.

## <a name="configure-the-enrichment"></a>Định cấu hình tăng cường

1. Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Dữ liệu** > **Tăng cường**.

1. Chọn **Tăng cường dữ liệu của tôi** trên ngăn xếp Leadspace rồi chọn **Bắt đầu**.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Ảnh chụp màn hình của ngăn xếp Leadspace.":::

1. Chọn một [kết nối](connections.md) từ danh sách thả xuống. Liên hệ với quản trị viên nếu không có kết nối. Nếu là quản trị viên, bạn có thể tạo kết nối bằng cách chọn **Thêm kết nối** rồi chọn **Leadspace**. 

1. Chọn **Kết nối với Leadspace** để xác nhận kết nối.

1. Chọn **Tiếp** rồi chọn **Tập hợp dữ liệu khách hàng** mà bạn muốn tăng cường bằng dữ liệu công ty từ Leadspace. ữBạn có thể chọn thực thể **Khách hàng** để tăng cường dữ liệu cho tất cả hồ sơ khách hàng của bạn hoặc chọn một thực thể phân khúc để chỉ tăng cường dữ liệu cho hồ sơ khách hàng có trong phân khúc đó.

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Ảnh chụp màn hình khi chọn tập dữ liệu khách hàng.":::

1. Chọn **Tiếp** và xác định loại trường nào từ hồ sơ hợp nhất của bạn sẽ được sử dụng để khớp dữ liệu công ty học phù hợp từ Leadspace. Trường **Tên công ty** là bắt buộc. Để có độ chính xác so khớp cao hơn, có thể thêm tối đa 2 trường khác, **Trang web công ty** và **Vị trí công ty**.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Ngăn ánh xạ trường Leadspace.":::

1. Chọn **Tiếp** để hoàn thành quá trình ánh xạ trường.

1. Chọn hộp kiểm nếu bạn có *Hồ sơ liên hệ* mà bạn muốn làm phong phú. Thông tin chi tiết về đối tượng sẽ tự động ánh xạ các trường bắt buộc.

   :::image type="content" source="media/enrichment-leadspace-contacts.png" alt-text="Làm phong phú hồ sơ liên hệ Leadspace.":::
 
1. Đặt tên cho dữ liệu tăng cường rồi chọn **Lưu dữ liệu tăng cường** sau khi xem xét các lựa chọn của bạn.


## <a name="configure-the-connection-for-leadspace"></a>Định cấu hình kết nối cho Leadspace 

Bạn cần phải là quản trị viên thì mới có thể định cấu hình kết nối. Chọn **Thêm kết nối** khi định cấu hình dữ liệu tăng cường *hoặc* đi đến **Quản trị viên** > **Kết nối** rồi chọn **Thiết lập** trên ngăn xếp Leadspace.

1. Chọn **Bắt đầu**. 

1. Nhập tên cho kết nối trong hộp **Tên hiển thị**.

1. Cung cấp một mã thông báo Leadspace hợp lệ.

1. Xem xét và chấp thuận **Quyền riêng tư dữ liệu và sự tuân thủ** bằng cách chọn **Tôi đồng ý**.

1. Chọn **Xác minh** để xác thực cấu hình.

1. Sau khi hoàn thành xác minh, hãy chọn **Lưu**.
   
   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Trang cấu hình kết nối cho Leadspace.":::

## <a name="enrichment-results"></a>Kết quả tăng cường

Sau khi làm mới dữ liệu tăng cường, bạn có thể xem xét dữ liệu công ty mới được bổ sung trong phần [Dữ liệu tăng cường của tôi](enrichment-hub.md). Bạn có thể tìm thấy thời điểm cập nhật gần đây nhất và số lượng hồ sơ tăng cường.

Bạn có thể truy cập dạng xem chi tiết của từng hồ sơ được tăng cường dữ liệu bằng cách chọn **Xem dữ liệu tăng cường**.

Để biết thêm thông tin, hãy xem [API Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).

## <a name="next-steps"></a>Các bước tiếp theo


[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Quyền riêng tư về dữ liệu và sự tuân thủ

Khi bật Dynamics 365 Customer Insights để truyền dữ liệu tới Leadspace, bạn cho phép truyền dữ liệu ra ngoài phạm vi tuân thủ cho Dynamics 365 Customer Insights, bao gồm dữ liệu có khả năng là thông tin nhạy cảm, chẳng hạn như Dữ liệu cá nhân. Microsoft sẽ truyền những dữ liệu đó theo chỉ dẫn của bạn, nhưng bạn có trách nhiệm đảm bảo rằng Leadspace đáp ứng mọi nghĩa vụ về quyền riêng tư hoặc bảo mật mà bạn có thể có. Để biết thêm thông tin, hãy xem [Tuyên bố về Quyền riêng tư của Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Quản trị viên Dynamics 365 Customer Insights của bạn có thể loại bỏ dịch vụ tăng cường này bất kỳ lúc nào để ngừng sử dụng tính năng đó.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
