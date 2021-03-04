---
title: Tăng cường hồ sơ công ty bằng chức năng tăng cường của bên thứ ba Leadspace
description: Thông tin chung về tăng cường của bên thứ ba Leadspace.
ms.date: 11/24/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 12eed91a7ca4ef7fde0d53cca4a1dfd398b4634f
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269448"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a>Làm phong phú hồ sơ công ty bằng Leadspace (xem trước)

Leadspace là công ty khoa học dữ liệu cung cấp Nền tảng dữ liệu khách hàng B2B. Nó cho phép khách hàng có hồ sơ khách hàng hợp nhất cho các công ty để làm phong phú dữ liệu của họ. Tăng cường bao gồm các thuộc tính bổ sung như kích cỡ công ty, vị trí, ngành và các thông tin khác.

## <a name="prerequisites"></a>Điều kiện tiên quyết

Để đặt cấu hình Leadspace, phải đáp ứng các điều kiện tiên quyết sau đây:

- Bạn có giấy phép Leadspace hiện hoạt và "khóa vĩnh viễn" (được gọi là **Mã thông báo Leadspace**). Liên hệ trực tiếp với [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) để biết chi tiết về sản phẩm của họ.
- Bạn có quyền [Quản trị viên](permissions.md#administrator).
- Bạn có [hồ sơ khách hàng hợp nhất](customer-profiles.md) cho các công ty.

## <a name="configuration"></a>Cấu hình

1. Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Dữ liệu** > **Tăng cường**.

1. Chọn **Tăng cường dữ liệu của tôi** trên ngăn xếp Leadspace.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Ảnh chụp màn hình của ngăn xếp Leadspace.":::

1. Chọn **Bắt đầu** và sau đó nhập một **Mã thông báo Leadspace** hiện hoạt (khóa vĩnh viễn). Xem lại và đồng ý với **Quyền riêng tư và tuân thủ dữ liệu** bằng cách đánh dấu ô **Tôi đồng ý**. Xác nhận cả hai đầu vào bằng cách chọn **Kết nối với Leadspace**.

1. Chọn **Ánh xạ dữ liệu** và chọn tập dữ liệu bạn muốn làm phong phú bằng dữ liệu công ty từ Leadspace. Bạn có thể chọn thực thể *khách hàng* để làm phong phú tất cả hồ sơ khách hàng của bạn hoặc chọn một thực thể phân khúc để chỉ làm phong phú thêm hồ sơ khách hàng có trong phân khúc đó.

   :::image type="content" source="media/enrichment-leadspace-select-segment.png" alt-text="Chọn giữa hồ sơ khách hàng và làm phong phú phân khúc.":::

1. Nhấp vào **Tiếp theo** và xác định trường trong hồ sơ hợp nhất sẽ được dùng để tìm kiếm dữ liệu công ty phù hợp từ Leadspace. Trường **Tên công ty** là bắt buộc. Để có độ chính xác so khớp cao hơn, có thể thêm tối đa 2 trường khác, **Trang web công ty** và **Vị trí công ty**.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Ngăn ánh xạ trường Leadspace.":::
   
1. Chọn **Áp dụng** để hoàn thành ánh xạ trường.

1. Chọn **Chạy** để làm phong phú hồ sơ công ty. Thời gian tăng cường phụ thuộc vào số lượng hồ sơ khách hàng hợp nhất.

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