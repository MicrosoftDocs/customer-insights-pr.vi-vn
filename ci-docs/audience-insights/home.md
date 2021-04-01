---
title: Trang chủ trong thông tin chi tiết về đối tượng
description: Bắt đầu khám phá ứng dụng trên trang chủ.
ms.date: 01/07/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: bf9080c564850bca0c239b7317eed2fc0f77d9f3
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597261"
---
# <a name="create-a-new-environment"></a>Tạo môi trường mới

## <a name="create-a-trial-environment"></a>Tạo môi trường dùng thử

Bạn có thể đăng ký dùng thử trên [trang đăng ký dùng thử](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights). 

> [!NOTE]
> Các bản dùng thử sẽ hết hạn sau 30 ngày.

1. Chọn tùy chọn **Đăng ký dùng thử miễn phí** và chọn **Đăng ký ngay**.

1. Cung cấp địa chỉ email cơ quan hoặc trường học, cho chúng tôi biết thêm về bản thân bạn rồi chọn **Tiếp**.

   :::image type="content" source="media/trial-signup-dialog.png" alt-text="Hộp thoại để đăng ký phiên bản dùng thử":::

1. Cung cấp **Tên** cho môi trường mới của bạn. 

1. Chọn loại bản dùng thử.

1. Chọn **Khu vực** cho môi trường của bạn.

1. Theo tùy chọn, đối với quản trị viên của tổ chức Dynamics 365: Chọn **Thiết đặt nâng cao** và cung cấp URL của tổ chức của bạn để sử dụng các tính năng dự đoán như khách hàng rời đi.

1. Chọn **Tạo**. 

Sau khi môi trường được tạo, bạn sẽ thấy môi trường **Demo** cho phép bạn khám phá ứng dụng với dữ liệu hư cấu. Bạn có thể thay đổi dữ liệu mẫu để phù hợp với ngành của mình. Chọn biểu tượng **Thiết đặt** trong tiêu đề và chọn **Thiết đặt demo**. Ngoài ra, bạn có thể thay đổi chủ đề trực quan. 

Bạn [chuyển sang môi trường](#switch-environments) mình đã tạo trong quá trình đăng ký để làm việc với dữ liệu của riêng bạn.

## <a name="create-a-new-production-or-sandbox-environment"></a>Tạo môi trường sản xuất hoặc hộp cát mới

Trong môi trường của bạn, hãy chọn bộ chọn **Môi trường** trong tiêu đề ứng dụng và chọn **Mới**.

Làm theo các bước như thể bạn [tạo môi trường thử nghiệm](#create-a-trial-environment). Theo mặc định, dữ liệu được lưu trữ trong kho dữ liệu được quản lý của Customer Insights. Bạn nhận được một tùy chọn bổ sung khi chọn **Thiết đặt nâng cao** để lưu trữ dữ liệu trong Azure Data Lake của riêng bạn. Cung cấp tên tài khoản và khóa tài khoản để thiết lập kết nối với Azure Data Lake của bạn. 

> [!IMPORTANT]
> Bằng cách lưu dữ liệu vào Azure Data Lake Storage, bạn đồng ý rằng dữ liệu sẽ được chuyển đến và lưu trữ ở vị trí địa lý thích hợp cho tài khoản lưu trữ Azure đó. Vị trí này có thể khác với nơi dữ liệu được lưu trữ trong Dynamics 365 Customer Insights. [Hãy tìm hiểu thêm tại Trung tâm tin cậy Microsoft.](https://www.microsoft.com/trust-center)

## <a name="explore-the-home-page"></a>Khám phá trang chủ

Bạn có thể [truy cập thông tin chi tiết về đối tượng từ Dynamics 365 Customer Insights](https://home.ci.ai.dynamics.com/) trên URL sau: [https://home.ci.ai.dynamics.com/](https://home.ci.ai.dynamics.com/).
Trang **Trang chủ** hiển thị tổng quan về các phân đoạn, giá trị đo và dữ liệu làm phong phú (nếu được định cấu hình) sau khi hoàn thành các giai đoạn [ánh xạ](map-entities.md), [so khớp](match-entities.md) và [hợp nhất](merge-entities.md).

> [!div class="mx-imgBorder"] 
> ![Thông tin chuyên sâu trên Trang chủ](media/home-page-insights.png "Thông tin chuyên sâu trên Trang chủ")

Trong **Các phân đoạn gần đây**, bạn thấy các nhóm khách hàng dựa trên các thuộc tính nhân khẩu học, hành vi hoặc giao dịch mà bạn đã xác định. [Tạo phân đoạn](segments.md) giúp bạn nhóm cơ sở khách hàng của mình và nhắm mục tiêu tốt hơn các hoạt động kinh doanh của bạn.

**Các biện pháp gần đây** hiển thị các lát với [các chỉ số hiệu suất chính (KPI)](measures.md) mà bạn đã xác định. Ví dụ: khả năng trung bình của một khách hàng ngừng sử dụng hoặc chi tiêu trực tuyến trung bình cho mỗi khách hàng.

Phần **Tăng cường gần đây** liệt kê kết quả của các lần chạy bổ sung đã hoàn thành gần đây. [Làm phong phú](enrichment-hub.md) sẽ thêm thông tin về cơ sở khách hàng của bạn. Ví dụ: bằng cách hiểu sở thích và thương hiệu mà họ quan tâm.

## <a name="switch-environments"></a>Chuyển đổi môi trường

Chọn kiểm soát **Môi trường** ở góc trên bên phải của trang để thay đổi môi trường.

> [!div class="mx-imgBorder"] 
> ![Chuyển đổi môi trường](media/home-page-environment-switcher.png "Chuyển đổi môi trường")

Quản trị viên có thể tạo và quản lý [nhiều môi trường](manage-environments.md). Việc duy trì nhiều môi trường có thể hữu ích nếu chẳng hạn, tổ chức của bạn hoạt động trên phạm vi quốc tế và bạn cần tách biệt dữ liệu và thông tin chi tiết theo nhiều cách khác nhau.

## <a name="next-step"></a>Bước tiếp theo

Để xem thông tin chi tiết của bạn trên trang chủ, trước tiên, bạn cần [thêm nguồn dữ liệu](data-sources.md) và [hợp nhất](data-unification.md) dữ liệu để xây dựng hồ sơ khách hàng.


[!INCLUDE[footer-include](../includes/footer-banner.md)]