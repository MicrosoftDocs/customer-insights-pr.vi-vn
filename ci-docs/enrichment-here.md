---
title: Làm phong phú hồ sơ khách hàng với Công nghệ HERE (xem trước)
description: Thông tin chung về dịch vụ tăng cường dữ liệu của bên thứ ba HERE Technologies.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 86a070342193dd7afda38823d90f4bd28c8b862e
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 08/08/2022
ms.locfileid: "9237884"
---
# <a name="enrich-customer-profiles-with-here-technologies-preview"></a>Làm phong phú hồ sơ khách hàng với Công nghệ HERE (xem trước)

HERE Technologies là một công ty nền tảng vị trí cung cấp dữ liệu và dịch vụ tập trung vào vị trí. Các dịch vụ làm giàu dữ liệu của HERE Technologies cải thiện độ chính xác của thông tin vị trí về khách hàng của bạn. Nó cung cấp chuẩn hóa địa chỉ, trích xuất vĩ độ và kinh độ, v.v.

## <a name="prerequisites"></a>Điều kiện tiên quyết

- Đăng ký HERE Technologies đang hoạt động. Để có được một đăng ký, [đăng ký tại đây](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) hoặc [liên hệ với HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) trực tiếp. [Tìm hiểu thêm về dịch vụ Tăng cường vị trí HERE Technologies.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- ĐÂY [sự liên quan](connections.md) Là [đã cấu hình](#configure-the-connection-for-here-technologies) bởi một quản trị viên.

## <a name="configure-the-connection-for-here-technologies"></a>Định cấu hình kết nối cho HERE Technologies

Bạn phải là một [người quản lý](permissions.md#admin) trong Thông tin chi tiết về khách hàng và có khóa API HERE Technologies đang hoạt động.

1. Lựa chọn **Thêm kết nối** khi định cấu hình phần bổ sung hoặc đi tới **Quản trị viên** > **Kết nối** và chọn **Cài đặt** trên ô HERE Technologies.

1. Nhập tên cho kết nối và khóa API HERE Technologies hợp lệ.

1. Xem lại [quyền riêng tư và tuân thủ dữ liệu](connections.md#data-privacy-and-compliance) và chọn **tôi đồng ý**.

1. Lựa chọn **Kiểm chứng** để xác thực cấu hình và sau đó chọn **Tiết kiệm**.

   :::image type="content" source="media/enrichment-HERE-connection.png" alt-text="Trang cấu hình kết nối cho HERE Technologies.":::

## <a name="configure-the-enrichment"></a>Đặt cấu hình dữ liệu tăng cường

1. Đi đến **Dữ liệu** > **Tăng cường** rồi chọn tab **Khám phá**.

1. Lựa chọn **Làm phong phú dữ liệu của tôi** trên **Địa điểm** từ ô Công nghệ TẠI ĐÂY.

   :::image type="content" source="media/HERE-tile.png" alt-text="Ngăn xếp HERE Technologies.":::

1. Xem lại tổng quan và sau đó chọn **Tiếp theo**.

1. Chọn kết nối. Liên hệ với quản trị viên nếu không có kết nối.

1. Chọn **Tiếp theo**.

1. Chọn **Tập dữ liệu khách hàng** và chọn hồ sơ hoặc phân đoạn bạn muốn làm giàu bằng dữ liệu từ Công nghệ HERE. Các *khách hàng* thực thể làm phong phú tất cả hồ sơ khách hàng của bạn trong khi một phân khúc chỉ làm phong phú thêm hồ sơ khách hàng có trong phân khúc đó.

1. Xác định loại trường nào từ cấu hình hợp nhất của bạn để sử dụng để đối sánh: địa chỉ chính và / hoặc địa chỉ phụ. Bạn có thể chỉ định kiểu ánh xạ trường cho cả hai địa chỉ và tăng cường dữ liệu hồ sơ cho cả hai địa chỉ một cách riêng biệt. Ví dụ: đối với địa chỉ nhà riêng và địa chỉ doanh nghiệp. Chọn **Tiếp theo**.

1. Ánh xạ các trường của bạn với dữ liệu từ Công nghệ HERE. Các trường **Đường 1** và **Mã zip/bưu chính** là bắt buộc cho địa chỉ chính và/hoặc phụ đã chọn. Để có độ chính xác đối sánh cao hơn, hãy thêm nhiều trường hơn.

1. Chọn **Tiếp** để hoàn thành quá trình ánh xạ trường.

1. Cung cấp một **Tên** để làm giàu và **Tên thực thể đầu ra**.

1. Chọn **Lưu dữ liệu tăng cường** sau khi xem xét các lựa chọn của bạn.

1. Lựa chọn **Chạy** để bắt đầu quá trình làm giàu hoặc đóng để quay lại **Làm giàu** trang.

## <a name="view-enrichment-results"></a>Xem kết quả bổ sung

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Các **Số lượng khách hàng làm giàu theo lĩnh vực** cung cấp thông tin chi tiết về phạm vi bao phủ của từng trường được bổ sung chi tiết.

## <a name="next-steps"></a>Các bước tiếp theo

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
