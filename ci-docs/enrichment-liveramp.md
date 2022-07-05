---
title: Làm phong phú hồ sơ khách hàng với dữ liệu nhận dạng từ LiveRamp (xem trước)
description: Làm phong phú hồ sơ khách hàng với dữ liệu LiveRamp.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 334440493c50448005ec90d0cfac11358d677b73
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082209"
---
# <a name="enrich-customer-profiles-with-identity-data-from-liveramp-preview"></a>Làm phong phú hồ sơ khách hàng với dữ liệu nhận dạng từ LiveRamp (xem trước)

LiveRamp cung cấp giải pháp nhận dạng ngoại tuyến xác định và hợp nhất dữ liệu khách hàng. Bạn có thể ánh xạ các số nhận dạng cá nhân trong dữ liệu khách hàng của mình với biểu đồ nhận dạng AbiliTec và nhận các ID AbiliTec. Sau đó, bạn có thể sử dụng các ID này để thống nhất dữ liệu khách hàng của mình tốt hơn.

## <a name="supported-countriesregions"></a>Quốc gia/khu vực được hỗ trợ

Chúng tôi hiện chỉ hỗ trợ làm phong phú hồ sơ khách hàng bằng dữ liệu LiveRamp ở Hoa Kỳ.

## <a name="prerequisites"></a>Điều kiện tiên quyết

- Đăng ký LiveRamp đang hoạt động. Để nhận đăng ký, hãy liên hệ với nhóm tài khoản LiveRamp của bạn hoặc [dynamics@liveramp.com](mailto:dynamics@liveramp.com) để biết thêm thông tin.

- Đăng ký AbiliTec đang hoạt động với ID khách hàng và bí mật để truy cập API. Để biết thêm thông tin, hãy xem [Trung tâm nhà phát triển API AbiliTec](https://developers.liveramp.com/abilitec-api/).

- Một LiveRamp [sự liên quan](connections.md) Là [đã cấu hình](#configure-the-connection-for-liveramp) bởi một quản trị viên.

## <a name="configure-the-connection-for-liveramp"></a>Định cấu hình kết nối cho LiveRamp

Bạn phải là một [người quản lý](permissions.md#admin) trong Thông tin chi tiết về khách hàng và có ID khách hàng LiveRamp đang hoạt động và bí mật.

1. Lựa chọn **Thêm kết nối** khi định cấu hình phần bổ sung hoặc đi tới **Quản trị viên** > **Kết nối** và chọn **Cài đặt** trên ô LiveRamp.

   :::image type="content" source="media/liveramp-connection.png" alt-text="Ngăn cấu hình để thiết lập kết nối với dịch vụ LiveRamp AbiliTec.":::

1. Nhập tên cho kết nối và ID ứng dụng LiveRamp hợp lệ và bí mật.

1. Xem xét và chấp thuận [Quyền riêng tư dữ liệu và sự tuân thủ](#data-privacy-and-compliance) bằng cách chọn **Tôi đồng ý**.

1. Lựa chọn **Kiểm chứng** để xác thực cấu hình và sau đó chọn **Tiết kiệm**.

### <a name="data-privacy-and-compliance"></a>Quyền riêng tư về dữ liệu và sự tuân thủ

Khi bạn bật Dynamics 365 Customer Insights để truyền dữ liệu tới LiveRamp, bạn cho phép chuyển dữ liệu ra bên ngoài ranh giới tuân thủ đối với Dynamics 365 Customer Insights, bao gồm dữ liệu nhạy cảm tiềm ẩn như Dữ liệu cá nhân. Microsoft sẽ chuyển những dữ liệu đó theo chỉ dẫn của bạn, nhưng bạn có trách nhiệm đảm bảo rằng LiveRamp đáp ứng mọi nghĩa vụ về quyền riêng tư hoặc bảo mật mà bạn có thể có. Để biết thêm thông tin, hãy xem lại [Tuyên bố về Quyền riêng tư của Microsoft](https://go.microsoft.com/fwlink/?linkid=396732). Quản trị viên Dynamics 365 Customer Insights của bạn có thể xóa tính năng tăng cường này bất kỳ lúc nào để ngừng sử dụng chức năng này.

## <a name="configure-the-enrichment"></a>Đặt cấu hình dữ liệu tăng cường

1. Đi đến **Dữ liệu** > **Tăng cường** rồi chọn tab **Khám phá**.

1. Lựa chọn **Làm phong phú dữ liệu của tôi** trên **Xác thực** từ ô LiveRamp.

   :::image type="content" source="media/liveramp-tile.png" alt-text="Ô nhận dạng trong trang tổng quan về bổ sung.":::

1. Xem lại tổng quan và sau đó chọn **Tiếp theo**.

1. Chọn kết nối. Liên hệ với quản trị viên nếu không có sẵn.

1. Chọn **Tiếp theo**.

1. Chọn **Tập dữ liệu khách hàng** và chọn hồ sơ hoặc phân đoạn bạn muốn làm giàu bằng dữ liệu nhận dạng từ LiveRamp. Các *khách hàng* thực thể làm phong phú tất cả hồ sơ khách hàng của bạn trong khi một phân khúc chỉ làm phong phú thêm hồ sơ khách hàng có trong phân khúc đó.

1. Xác định loại trường nào từ hồ sơ hợp nhất của bạn để sử dụng để khớp dữ liệu nhận dạng từ LiveRamp. Ít nhất một trong các trường **Tên và địa chỉ**, **-mail**, hoặc **Điện thoại** bắt buộc. Để có độ chính xác đối sánh cao hơn, hãy thêm các trường khác. Chọn **Tiếp theo**.

1. Ánh xạ các trường của bạn với dữ liệu nhận dạng từ LiveRamp.

   :::image type="content" source="media/liveramp-data-mapping.png" alt-text="Các tùy chọn ánh xạ dữ liệu để làm giàu LiveRamp.":::

1. Chọn **Tiếp** để hoàn thành quá trình ánh xạ trường.

1. Cung cấp một **Tên** để làm giàu và **Tên thực thể đầu ra**.

1. Chọn **Lưu dữ liệu tăng cường** sau khi xem xét các lựa chọn của bạn.

1. Lựa chọn **Chạy** để bắt đầu quá trình làm giàu hoặc đóng để quay lại **Làm giàu** trang.

## <a name="view-enrichment-results"></a>Xem kết quả bổ sung

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Các **Số lượng khách hàng phong phú theo lĩnh vực** cung cấp thông tin chi tiết về phạm vi bao phủ của từng trường được bổ sung chi tiết.

## <a name="next-steps"></a>Các bước tiếp theo

Xây dựng dựa trên dữ liệu khách hàng tăng cường của bạn. Sử dụng ID AbiliTec để hợp nhất hồ sơ khách hàng thành chế độ xem dựa trên người.
[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
