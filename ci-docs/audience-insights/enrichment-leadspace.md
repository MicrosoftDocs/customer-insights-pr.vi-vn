---
title: Tăng cường hồ sơ công ty bằng chức năng tăng cường của bên thứ ba Leadspace
description: Thông tin chung về tăng cường của bên thứ ba Leadspace.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: ccf4f661ecffb281556a4545b1f26ee809c697cd
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 04/14/2021
ms.locfileid: "5895939"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a>Làm phong phú hồ sơ công ty bằng Leadspace (xem trước)

Leadspace là công ty khoa học dữ liệu cung cấp Nền tảng dữ liệu khách hàng B2B. Nó cho phép khách hàng có hồ sơ khách hàng hợp nhất cho các công ty để làm phong phú dữ liệu của họ. Nội dung bổ sung bao gồm nhiều thuộc tính hơn như quy mô công ty, vị trí, ngành, v.v..

## <a name="prerequisites"></a>Điều kiện tiên quyết

Để đặt cấu hình Leadspace, phải đáp ứng các điều kiện tiên quyết sau đây:

- Bạn có một giấy phép Leadspace hiện hoạt.
- Bạn có [hồ sơ khách hàng hợp nhất](customer-profiles.md) cho các công ty.
- Một kết nối Leadspace đã được quản trị viên đặt cấu hình hoặc bạn có quyền của [quản trị viên](permissions.md#administrator) và “khóa vĩnh viễn” (còn gọi là **Mã thông báo Leadspace**). Liên hệ trực tiếp với [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) để biết thông tin chi tiết về sản phẩm của họ.

## <a name="configure-the-enrichment"></a>Đặt cấu hình nội dung bổ sung

1. Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Dữ liệu** > **Tăng cường**.

1. Chọn **Làm phong phú dữ liệu của tôi** trên ngăn xếp Leadspace rồi chọn **Bắt đầu**.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Ảnh chụp màn hình của ngăn xếp Leadspace.":::

1. Chọn một [kết nối](connections.md) từ danh sách thả xuống. Liên hệ với quản trị viên nếu không có kết nối. Nếu là quản trị viên, bạn có thể tạo kết nối bằng cách chọn **Thêm kết nối** rồi chọn **Leadspace**. 

1. Chọn **Kết nối với Leadspace** để xác nhận kết nối.

1. Chọn **Tiếp** rồi chọn **Tập hợp dữ liệu khách hàng** mà bạn muốn bổ sung thêm dữ liệu công ty từ Leadspace. Bạn có thể chọn thực thể **khách hàng** để làm phong phú tất cả hồ sơ khách hàng của bạn hoặc chọn một thực thể phân khúc để chỉ làm phong phú thêm hồ sơ khách hàng có trong phân khúc đó.

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Ảnh chụp màn hình khi chọn tập dữ liệu khách hàng.":::

1. Chọn **Tiếp** và xác định loại trường nào từ hồ sơ hợp nhất của bạn sẽ được sử dụng để khớp dữ liệu công ty học phù hợp từ Leadspace. Trường **Tên công ty** là bắt buộc. Để có độ chính xác so khớp cao hơn, có thể thêm tối đa 2 trường khác, **Trang web công ty** và **Vị trí công ty**.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Ngăn ánh xạ trường Leadspace.":::

1. Chọn **Tiếp** để hoàn thành quá trình ánh xạ trường.

1. Đặt tên cho nội dung bổ sung rồi chọn **Lưu nội dung bổ sung** sau khi xem xét các lựa chọn của bạn.


## <a name="configure-the-connection-for-leadspace"></a>Đặt cấu hình kết nối cho Leadspace 

Bạn cần phải là quản trị viên thì mới có thể đặt cấu hình kết nối. Chọn **Thêm kết nối** khi đặt cấu hình nội dung bổ sung *hoặc* đi đến **Quản trị viên** > **Kết nối** rồi chọn **Thiết lập** trên ngăn xếp Leadspace.

1. Chọn **Bắt đầu** 

1. Nhập tên cho kết nối trong hộp **Tên hiển thị**.

1. Cung cấp một mã thông báo Leadspace hợp lệ.

1. Xem lại và đồng ý với **Quyền riêng tư về dữ liệu và tuân thủ** bằng cách đánh dấu vào hộp kiểm **Tôi đồng ý**

1. Chọn **Xác minh** để xác thực cấu hình.

1. Sau khi hoàn thành xác minh, hãy chọn **Lưu**.
   
   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Trang cấu hình kết nối cho Leadspace.":::

## <a name="enrichment-results"></a>Kết quả làm phong phú

Sau khi làm mới hồ sơ phong phú, bạn có thể xem lại dữ liệu công ty được làm mới gần đây trong phần [Nội dung phong phú của tôi](enrichment-hub.md). Bạn có thể tìm thấy thời điểm cập nhật gần đây nhất và số lượng hồ sơ phong phú.

Bạn có thể truy cập dạng xem chi tiết của từng hồ sơ được làm phong phú bằng cách chọn **Xem dữ liệu được làm phong phú**.

Để biết thêm thông tin, hãy xem [API Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).

## <a name="next-steps"></a>Các bước tiếp theo

Xây dựng dựa trên dữ liệu khách hàng phong phú của bạn. Tạo [phân khúc](segments.md), [biện pháp](measures.md) và [xuất dữ liệu](export-destinations.md) để cung cấp trải nghiệm cá nhân cho khách hàng của bạn.

## <a name="data-privacy-and-compliance"></a>Quyền riêng tư về dữ liệu và tuân thủ

Khi bật Dynamics 365 Customer Insights để truyền dữ liệu tới Leadspace, bạn cho phép chuyển dữ liệu ra bên ngoài ranh giới tuân thủ cho Dynamics 365 Customer Insights, bao gồm dữ liệu nhạy cảm tiềm ẩn như Dữ liệu cá nhân. Microsoft sẽ chuyển những dữ liệu đó theo chỉ dẫn của bạn, nhưng bạn có trách nhiệm đảm bảo rằng Leadspace đáp ứng mọi nghĩa vụ về quyền riêng tư hoặc bảo mật mà bạn có thể có. Để biết thêm thông tin, hãy xem [Tuyên bố về Quyền riêng tư của Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Quản trị viên Dynamics 365 Customer Insights của bạn có thể xóa tính năng tăng cường này bất kỳ lúc nào để ngừng sử dụng chức năng này.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
