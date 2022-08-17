---
title: Làm phong phú hồ sơ khách hàng với dữ liệu vị trí từ Azure Maps (xem trước)
description: Thông tin chung về dịch vụ tăng cường dữ liệu của bên thứ nhất Azure Maps.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: f14b4fc20a9a1d8842f42f9e0e656b3d8dcddcf4
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 08/08/2022
ms.locfileid: "9238068"
---
# <a name="enrich-customer-profiles-with-location-data-from-azure-maps-preview"></a>Làm phong phú hồ sơ khách hàng với dữ liệu vị trí từ Azure Maps (xem trước)

Azure Maps cung cấp dữ liệu và dịch vụ tập trung vào vị trí để mang lại trải nghiệm dựa trên dữ liệu không gian địa lý với thông tin vị trí tích hợp sẵn. Dịch vụ tăng cường dữ liệu Azure Maps cải thiện độ chính xác của thông tin vị trí về khách hàng của bạn. Dịch vụ này mang lại các khả năng như chuẩn hóa địa chỉ và trích xuất vĩ độ cũng như kinh độ cho Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Điều kiện tiên quyết

- Đăng ký Azure Maps đang hoạt động. Để có được một đăng ký, [đăng ký hoặc nhận bản dùng thử miễn phí](https://azure.microsoft.com/services/azure-maps/).

- Bản đồ Azure [sự liên quan](connections.md) Là [đã cấu hình](#configure-the-connection-for-azure-maps) bởi một quản trị viên.

## <a name="configure-the-connection-for-azure-maps"></a>Đặt cấu hình kết nối cho Azure Maps

Bạn phải là một [người quản lý](permissions.md#admin) trong Thông tin chi tiết về khách hàng và có khóa API Azure Maps đang hoạt động.

1. Chọn **Thêm kết nối** khi đặt cấu hình dữ liệu tăng cường hoặc đi đến **Quản trị viên** > **Kết nối** rồi chọn **Thiết lập** trên ngăn xếp Azure Maps.

   :::image type="content" source="media/enrichment-azure-maps-connection.png" alt-text="Trang cấu hình kết nối Azure Maps.":::

1. Nhập tên cho kết nối và khóa API Azure Maps hợp lệ.

1. Xem lại [quyền riêng tư và tuân thủ dữ liệu](connections.md#data-privacy-and-compliance) và chọn **tôi đồng ý**.

1. Lựa chọn **Kiểm chứng** để xác thực cấu hình và sau đó chọn **Tiết kiệm**.

## <a name="configure-the-enrichment"></a>Đặt cấu hình dữ liệu tăng cường

1. Đi đến **Dữ liệu** > **Tăng cường** rồi chọn tab **Khám phá**.

1. Lựa chọn **Làm phong phú dữ liệu của tôi** trên **Địa điểm** từ Microsoft Azure Hình xếp bản đồ.

   :::image type="content" source="media/azure-maps-tile.png" alt-text="Ngăn xếp Azure Maps.":::

1. Xem lại tổng quan và sau đó chọn **Tiếp theo**.

1. Chọn kết nối. Liên hệ với quản trị viên nếu không có kết nối.

1. Chọn **Tiếp theo**.

1. Chọn **Tập dữ liệu khách hàng** và chọn cấu hình hoặc phân đoạn bạn muốn bổ sung thêm dữ liệu từ Microsoft. Các *khách hàng* thực thể làm phong phú tất cả hồ sơ khách hàng của bạn trong khi một phân khúc chỉ làm phong phú thêm hồ sơ khách hàng có trong phân khúc đó.

1. Xác định loại trường nào từ cấu hình hợp nhất của bạn để sử dụng để đối sánh: địa chỉ chính và / hoặc địa chỉ phụ. Bạn có thể chỉ định kiểu ánh xạ trường cho cả hai địa chỉ và tăng cường dữ liệu hồ sơ cho cả hai địa chỉ một cách riêng biệt. Ví dụ: đối với địa chỉ nhà riêng và địa chỉ doanh nghiệp. Chọn **Tiếp theo**.

1. Ánh xạ các trường của bạn với dữ liệu vị trí từ Bản đồ Azure. Các trường **Đường 1** và **Mã zip/bưu chính** là bắt buộc cho địa chỉ chính và/hoặc phụ đã chọn. Để có độ chính xác đối sánh cao hơn, hãy thêm nhiều trường hơn.

   :::image type="content" source="media/enrichment-azure-maps-attributes.png" alt-text="Lập bản đồ thuộc tính Azure Maps.":::

1. Chọn **Tiếp** để hoàn thành quá trình ánh xạ trường.

1. Kiểm tra lại **Cài đặt nâng cao** cung cấp tính linh hoạt tối đa để xử lý các trường hợp sử dụng nâng cao. Tuy nhiên, các giá trị mặc định sau thường không cần thay đổi.

   - **Loại địa chỉ** : Đối sánh địa chỉ tốt nhất trả về ngay cả khi nó không đầy đủ. Để chỉ nhận được địa chỉ đầy đủ&mdash;ví dụ: địa chỉ bao gồm số nhà&mdash;xóa tất cả các hộp kiểm ngoại trừ **Địa chỉ dạng điểm**.
   - **Ngôn ngữ** : Địa chỉ trả về bằng ngôn ngữ dựa trên vùng địa chỉ. Để áp dụng ngôn ngữ địa chỉ được chuẩn hóa, hãy chọn ngôn ngữ từ menu thả xuống. Ví dụ, chọn **Tiếng Anh** trả lại **Copenhagen, Đan Mạch** thay vì **København, Danmark**.
   - **Số lượng kết quả tối đa** : Số lượng kết quả trên mỗi địa chỉ.

1. Chọn **Tiếp theo**.

1. Cung cấp một **Tên** để làm giàu và **Tên thực thể đầu ra**.

1. Chọn **Lưu dữ liệu tăng cường** sau khi xem xét các lựa chọn của bạn.

1. Lựa chọn **Chạy** để bắt đầu quá trình làm giàu hoặc đóng để quay lại **Làm giàu** trang.

## <a name="view-enrichment-results"></a>Xem kết quả bổ sung

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Các **Số lượng khách hàng làm giàu theo lĩnh vực** cung cấp thông tin chi tiết về phạm vi bao phủ của từng trường được bổ sung chi tiết.

## <a name="next-steps"></a>Các bước tiếp theo

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
