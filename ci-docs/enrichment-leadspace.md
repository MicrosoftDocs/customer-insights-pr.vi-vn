---
title: Làm phong phú hồ sơ công ty với Leadspace (xem trước)
description: Thông tin chung về dịch vụ tăng cường dữ liệu của bên thứ ba Leadspace.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 3f23fe7177f931db3e3179970915d0cd3c736f87
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196236"
---
# <a name="enrich-company-profiles-with-leadspace-preview"></a>Làm phong phú hồ sơ công ty với Leadspace (xem trước)

Leadspace là một công ty khoa học dữ liệu cung cấp Nền tảng dữ liệu khách hàng B2B. Nó cho phép các môi trường có hồ sơ khách hàng hợp nhất dựa trên các tài khoản để làm phong phú thêm dữ liệu của họ. Làm phong phú *Hồ sơ khách hàng* với các thuộc tính như vị trí, ngành hoặc quy mô công ty. Làm phong phú *Hồ sơ liên hệ* với các thuộc tính như chức danh, chân dung hoặc xác minh email.

## <a name="prerequisites"></a>Điều kiện tiên quyết

- Giấy phép Leadspace đang hoạt động.
- [Hồ sơ khách hàng hợp nhất](customer-profiles.md) dựa trên tài khoản.
- Một không gian dẫn [sự liên quan](connections.md) Là [đã cấu hình](#configure-the-connection-for-leadspace) bởi một quản trị viên. Liên hệ trực tiếp với [Leadspace](https://www.leadspace.com/leadspace-microsoft-dynamics-365/) để biết thông tin chi tiết về sản phẩm của họ.

## <a name="configure-the-connection-for-leadspace"></a>Định cấu hình kết nối cho Leadspace

Bạn phải là một [người quản lý](permissions.md#admin) trong Thông tin chi tiết về khách hàng và có "khóa vĩnh viễn" (gọi tắt là **Mã thông báo Leadspace**).

1. Lựa chọn **Thêm kết nối** khi định cấu hình phần bổ sung hoặc đi đến **Quản trị viên** > **Kết nối** và chọn **Cài đặt** trên ô Leadspace.

   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Trang cấu hình kết nối cho Leadspace.":::

1. Nhập tên cho kết nối và mã thông báo Leadspace hợp lệ.

1. Xem xét và chấp thuận [Quyền riêng tư dữ liệu và sự tuân thủ](#data-privacy-and-compliance) bằng cách chọn **Tôi đồng ý**.

1. Lựa chọn **Kiểm chứng** để xác thực cấu hình và sau đó chọn **Tiết kiệm**.

### <a name="data-privacy-and-compliance"></a>Quyền riêng tư về dữ liệu và sự tuân thủ

Khi bật Dynamics 365 Customer Insights để truyền dữ liệu tới Leadspace, bạn cho phép truyền dữ liệu ra ngoài phạm vi tuân thủ cho Dynamics 365 Customer Insights, bao gồm dữ liệu có khả năng là thông tin nhạy cảm, chẳng hạn như Dữ liệu cá nhân. Microsoft sẽ truyền những dữ liệu đó theo chỉ dẫn của bạn, nhưng bạn có trách nhiệm đảm bảo rằng Leadspace đáp ứng mọi nghĩa vụ về quyền riêng tư hoặc bảo mật mà bạn có thể có. Để biết thêm thông tin, hãy xem [Tuyên bố về Quyền riêng tư của Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Quản trị viên Dynamics 365 Customer Insights của bạn có thể loại bỏ dịch vụ tăng cường này bất kỳ lúc nào để ngừng sử dụng tính năng đó.

## <a name="configure-the-enrichment"></a>Đặt cấu hình dữ liệu tăng cường

1. Đi đến **Dữ liệu** > **Tăng cường** rồi chọn tab **Khám phá**.

1. Lựa chọn **Làm phong phú dữ liệu của tôi** trên **Dữ liệu công ty** từ ô Leadspace.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Ảnh chụp màn hình của ngăn xếp Leadspace.":::

1. Xem lại tổng quan và sau đó chọn **Tiếp theo**.

1. Chọn kết nối. Liên hệ với quản trị viên nếu không có kết nối.

1. Chọn **Tiếp theo**.

1. Chọn **Tập dữ liệu khách hàng** và chọn hồ sơ hoặc phân đoạn bạn muốn làm phong phú thêm với dữ liệu công ty từ Leadspace. Các *khách hàng* thực thể làm phong phú tất cả hồ sơ khách hàng của bạn trong khi một phân khúc chỉ làm phong phú thêm hồ sơ khách hàng có trong phân khúc đó.

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Ảnh chụp màn hình khi chọn tập dữ liệu khách hàng.":::

1. Xác định loại trường nào từ cấu hình hợp nhất của bạn để sử dụng để đối sánh: địa chỉ chính và / hoặc địa chỉ phụ. Bạn có thể chỉ định kiểu ánh xạ trường cho cả hai địa chỉ và tăng cường dữ liệu hồ sơ cho cả hai địa chỉ một cách riêng biệt. Ví dụ: đối với địa chỉ nhà riêng và địa chỉ doanh nghiệp. Chọn **Tiếp theo**.

1. Ánh xạ các trường của bạn với dữ liệu công ty từ Leadspace. Trường **Tên công ty** là bắt buộc. Để có độ chính xác so khớp cao hơn, có thể thêm tối đa 2 trường khác, **Trang web công ty** và **Vị trí công ty**.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Ngăn ánh xạ trường Leadspace.":::

1. Chọn **Tiếp** để hoàn thành quá trình ánh xạ trường.

1. Chọn hộp kiểm nếu bạn có *Hồ sơ liên hệ* mà bạn muốn làm phong phú. Thông tin chi tiết về khách hàng sẽ tự động ánh xạ các trường bắt buộc.

   :::image type="content" source="media/enrichment-leadspace-contacts.png" alt-text="Làm phong phú hồ sơ liên hệ Leadspace.":::

1. Chọn **Tiếp theo**.

1. Cung cấp một **Tên** để làm giàu và **Tên thực thể đầu ra**.

1. Chọn **Lưu dữ liệu tăng cường** sau khi xem xét các lựa chọn của bạn.

1. Lựa chọn **Chạy** để bắt đầu quá trình làm giàu hoặc đóng để quay lại **Làm giàu** trang.

## <a name="view-enrichment-results"></a>Xem kết quả bổ sung

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Để biết thêm thông tin, hãy xem [API Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).

## <a name="next-steps"></a>Các bước tiếp theo

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
