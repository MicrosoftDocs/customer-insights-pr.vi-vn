---
title: Tăng cường hồ sơ công ty bằng chức năng tăng cường của bên thứ ba Leadspace
description: Thông tin chung về tăng cường của bên thứ ba Leadspace.
ms.date: 11/24/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 1b5c6e46e8e424df83e855d81fc4dd7ecb394e3c
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668749"
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

1. Chọn **Dữ liệu bản đồ** và xác định trường nào từ hồ sơ hợp nhất của bạn sẽ được sử dụng để tìm kiếm dữ liệu công ty phù hợp từ Leadspace. Trường **Tên công ty** là bắt buộc. Để có độ chính xác so khớp cao hơn, có thể thêm tối đa 2 trường khác, **Trang web công ty** và **Vị trí công ty**.

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