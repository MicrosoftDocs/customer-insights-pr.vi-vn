---
title: Làm giàu dữ liệu nhận dạng LiveRamp
description: Làm phong phú hồ sơ khách hàng với dữ liệu LiveRamp.
ms.date: 03/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: ee65cb49447df61dd5c298a84ad21bc119ead558
ms.sourcegitcommit: bb1f9e96023490ab340c114f54200ab4dd48da78
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 03/02/2022
ms.locfileid: "8373086"
---
# <a name="enrich-customer-profiles-with-identity-data-from-liveramp-preview"></a>Làm phong phú hồ sơ khách hàng với dữ liệu nhận dạng từ LiveRamp (Xem trước) 

LiveRamp cung cấp giải pháp nhận dạng ngoại tuyến xác định và hợp nhất dữ liệu khách hàng. Bạn có thể ánh xạ các số nhận dạng cá nhân trong dữ liệu khách hàng của mình với biểu đồ nhận dạng AbiliTec và nhận các ID AbiliTec. Sau đó, bạn có thể sử dụng các ID này để thống nhất dữ liệu khách hàng của mình tốt hơn. 

## <a name="prerequisites"></a>Điều kiện tiên quyết 

Để định cấu hình bổ sung, các điều kiện tiên quyết sau phải được đáp ứng: 

- Bạn có một đăng ký LiveRamp đang hoạt động. Để nhận đăng ký, hãy liên hệ với nhóm tài khoản LiveRamp của bạn hoặc [dynamics@liveramp.com](mailto:dynamics@liveramp.com) để biết thêm thông tin.   

- Đăng ký AbiliTec đang hoạt động với ID khách hàng và bí mật để truy cập API. Để biết thêm thông tin, hãy xem [Trung tâm nhà phát triển API AbiliTec](https://developers.liveramp.com/abilitec-api/). 

## <a name="supported-countriesregions"></a>Quốc gia/khu vực được hỗ trợ 

Chúng tôi hiện chỉ hỗ trợ làm phong phú hồ sơ khách hàng bằng dữ liệu LiveRamp ở Hoa Kỳ. 

## <a name="configure-the-enrichment"></a>Đặt cấu hình dữ liệu tăng cường 

1. Đi đến **Dữ liệu** > **Tăng cường** rồi chọn tab **Khám phá**. 

1. Lựa chọn **Làm phong phú dữ liệu của tôi** trên **Xác thực** ngói. 

   :::image type="content" source="media/liveramp-tile.png" alt-text="Ô nhận dạng trong trang tổng quan về bổ sung.":::

1. Chọn một [kết nối](connections.md) từ danh sách thả xuống. Liên hệ với quản trị viên nếu không có kết nối. Nếu bạn là quản trị viên, bạn có thể tạo kết nối bằng cách chọn **Thêm kết nối**. Chọn **LiveRamp** từ danh sách thả xuống. 

1. Lựa chọn **Tiếp theo** và chọn **Tập dữ liệu khách hàng** bạn muốn làm giàu bằng dữ liệu nhận dạng từ LiveRamp. Bạn có thể chọn *Khách hàng* thực thể để làm phong phú thêm tất cả hồ sơ khách hàng của bạn hoặc chọn một *bộ phận* để chỉ làm giàu hồ sơ khách hàng có trong phân khúc đó. 

1. Lựa chọn **Tiếp theo** và xác định loại trường nào từ hồ sơ hợp nhất của bạn sẽ được sử dụng để tìm kiếm dữ liệu nhận dạng phù hợp từ LiveRamp. Ít nhất một trong các trường **Tên và địa chỉ**, **thoại**, hoặc **E-mail** bắt buộc. 

   > [!TIP]
   > Bạn càng ánh xạ nhiều số nhận dạng và trường chính, thì khả năng tỷ lệ đối sánh càng cao 

1. Ánh xạ các trường từ hợp nhất của bạn *Khách hàng* thực thể sẽ được sử dụng để đối sánh với biểu đồ ID AbiliTec của LiveRamp. 

   :::image type="content" source="media/liveramp-data-mapping.png" alt-text="Các tùy chọn ánh xạ dữ liệu để làm giàu LiveRamp.":::

1. Chọn **Tiếp** để hoàn thành quá trình ánh xạ trường. 

1. Cung cấp một **Tên** để làm giàu và **Thực thể đầu ra**. 

1. Chọn **Lưu dữ liệu tăng cường** sau khi xem xét các lựa chọn của bạn. 

## <a name="configure-the-connection-for-liveramp"></a>Định cấu hình kết nối cho LiveRamp 

Bạn cần phải là quản trị viên để [cấu hình kết nối](connections.md). Lựa chọn **Thêm kết nối** khi định cấu hình phần bổ sung hoặc đi đến **quản trị viên** > **Kết nối** và chọn **Thiết lập** trên **LiveRamp** ngói. 

:::image type="content" source="media/liveramp-connection.png" alt-text="Ngăn cấu hình để thiết lập kết nối với dịch vụ LiveRamp AbiliTec.":::

1. Vì **Tên hiển thị**, nhập tên của kết nối. 

1. Cung cấp ID ứng dụng LiveRamp hợp lệ và bí mật. 

1. Xem xét và đồng ý với **Quyền riêng tư và tuân thủ dữ liệu** bằng cách đánh dấu ô **Tôi đồng ý**. 

1. Chọn **Xác minh** để xác thực cấu hình. 

1. Để hoàn tất kết nối, hãy chọn **Tiết kiệm**. 

## <a name="enrichment-results"></a>Kết quả tăng cường 

Để bắt đầu quá trình làm giàu, hãy chọn Chạy từ thanh lệnh. Bạn cũng có thể để hệ thống chạy phần bổ sung tự động như một phần của [làm mới theo lịch trình](system.md#schedule-tab). Thời gian xử lý phụ thuộc vào kích thước dữ liệu khách hàng của bạn. 

Sau khi quá trình bổ sung hoàn tất, bạn có thể xem lại dữ liệu hồ sơ khách hàng mới được bổ sung trong **Sự làm giàu của tôi**. Ngoài ra, bạn sẽ tìm thấy thời gian của lần cập nhật gần nhất và số lượng hồ sơ được tăng cường. 

Bạn có thể truy cập chế độ xem chi tiết của từng hồ sơ được bổ sung chi tiết bằng cách chọn **Xem được phong phú** dữ liệu. 

## <a name="next-steps"></a>Các bước tiếp theo

Xây dựng dựa trên dữ liệu khách hàng tăng cường của bạn. Sử dụng ID AbiliTec để hợp nhất hồ sơ khách hàng thành chế độ xem dựa trên người. 
[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Quyền riêng tư về dữ liệu và sự tuân thủ 

Khi bạn bật Dynamics 365 Customer Insights để truyền dữ liệu tới LiveRamp, bạn cho phép chuyển dữ liệu ra bên ngoài ranh giới tuân thủ đối với Dynamics 365 Customer Insights, bao gồm dữ liệu nhạy cảm tiềm ẩn như Dữ liệu cá nhân. Microsoft sẽ chuyển những dữ liệu đó theo chỉ dẫn của bạn, nhưng bạn có trách nhiệm đảm bảo rằng LiveRamp đáp ứng mọi nghĩa vụ về quyền riêng tư hoặc bảo mật mà bạn có thể có. Để biết thêm thông tin, hãy xem lại [Tuyên bố về Quyền riêng tư của Microsoft](https://go.microsoft.com/fwlink/?linkid=396732). Quản trị viên Dynamics 365 Customer Insights của bạn có thể xóa tính năng tăng cường này bất kỳ lúc nào để ngừng sử dụng chức năng này. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
