---
title: Trang chủ trong thông tin chi tiết về đối tượng
description: Bắt đầu khám phá ứng dụng trên trang chủ.
ms.date: 09/30/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: bd16966eabb126d9c9945ededc53273df02c3369
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407319"
---
# <a name="create-a-new-environment"></a>Tạo môi trường mới

## <a name="create-a-trial-environment"></a>Tạo môi trường dùng thử

Bạn có thể đăng ký dùng thử trên [trang đăng ký dùng thử](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights). 

> [!NOTE]
> Các bản dùng thử sẽ hết hạn sau 30 ngày.

1. Chọn tùy chọn **Đăng ký dùng thử miễn phí** và chọn **Đăng ký ngay**.

1. Cung cấp địa chỉ email cơ quan hoặc trường học, cho chúng tôi biết thêm về bản thân bạn rồi chọn **Tiếp**.

1. Cung cấp **Tên** cho môi trường mới của bạn. 

1. Chọn loại bản dùng thử.

1. Chọn **Khu vực** cho môi trường của bạn.

1. Theo tùy chọn, đối với quản trị viên của tổ chức Dynamics 365: Chọn **Thiết đặt nâng cao** và cung cấp URL của tổ chức của bạn để sử dụng các tính năng dự đoán như khách hàng rời đi.

1. Chọn **Tạo**. 

Sau khi môi trường được tạo, bạn sẽ thấy môi trường **Demo** cho phép bạn khám phá ứng dụng với dữ liệu hư cấu. Bạn có thể thay đổi dữ liệu mẫu để phù hợp với ngành của mình. Chọn biểu tượng **Thiết đặt** trong tiêu đề và chọn **Thiết đặt demo**. Ngoài ra, bạn có thể thay đổi chủ đề trực quan. 

Bạn [chuyển sang môi trường](#change-between-environments) mình đã tạo trong quá trình đăng ký để làm việc với dữ liệu của riêng bạn.

## <a name="create-a-new-production-or-sandbox-environment"></a>Tạo môi trường sản xuất hoặc hộp cát mới

Trong môi trường của bạn, hãy chọn biểu tượng **Thiết đặt** trong tiêu đề và chọn **Môi trường mới**.

Làm theo các bước như thể bạn [tạo môi trường thử nghiệm](#create-a-trial-environment). Bạn nhận được một tùy chọn bổ sung khi chọn **Thiết đặt nâng cao** để lưu trữ dữ liệu trong Azure Data Lake của riêng bạn. Cung cấp tên tài khoản và khóa tài khoản để thiết lập kết nối với Azure Data Lake của bạn. Theo mặc định, dữ liệu được lưu trữ trong kho dữ liệu được quản lý của Customer Insights.

> [!IMPORTANT]
> Bằng cách lưu dữ liệu vào Azure Data Lake Storage, bạn đồng ý rằng dữ liệu sẽ được chuyển đến và lưu trữ ở vị trí địa lý thích hợp cho tài khoản lưu trữ Azure đó. Vị trí này có thể khác với nơi dữ liệu được lưu trữ trong Dynamics 365 Customer Insights. [Hãy tìm hiểu thêm tại Trung tâm tin cậy Microsoft.](https://www.microsoft.com/trust-center)

## <a name="explore-the-home-page"></a>Khám phá trang chủ

Bạn có thể [truy cập môi trường Customer Insights](https://home.ci.ai.dynamics.com/) trên URL sau:[https://home.ci.ai.dynamics.com/](https://home.ci.ai.dynamics.com/).
**Trang chủ** hiển thị tổng quan về cơ sở khách hàng của bạn và các chỉ số chính để theo dõi tình trạng kinh doanh của bạn.

> [!div class="mx-imgBorder"] 
> ![Thông tin chuyên sâu trên Trang chủ](media/home-page-insights.png "Thông tin chuyên sâu trên Trang chủ")

Trong **Các phân đoạn gần đây**, bạn thấy các nhóm khách hàng dựa trên các thuộc tính nhân khẩu học, hành vi hoặc giao dịch mà bạn đã xác định. [Tạo phân khúc](segments.md) giúp bạn nhắm mục tiêu tốt hơn các hoạt động kinh doanh.

**Giá trị đo gần đây** hiển thị ô xếp có [các giá trị đo](measures.md). Giá trị đo là các chỉ số đo lường hiệu suất chính (KPI) mà bạn đã xác định. Ví dụ: khả năng khách hàng rời đi trung bình hoặc chi tiêu trực tuyến trung bình cho mỗi khách hàng.

Phần **Tăng cường gần đây** liệt kê kết quả của các lần chạy bổ sung đã hoàn thành gần đây. Tăng cường sẽ thêm thông tin về cơ sở khách hàng của bạn. Ví dụ: bằng cách hiểu sở thích và thương hiệu mà họ quan tâm. Có thể mở khóa thông tin này bằng khả năng [làm phong phú](enrichment-microsoft-graph.md), sau khi hoàn thành các giai đoạn [sơ đồ](map-entities.md), [khớp](match-entities.md) và [hợp nhất](merge-entities.md).

## <a name="change-between-environments"></a>Thay đổi giữa các môi trường

Khi đã thiết lập và đặt cấu hình [nguồn dữ liệu](data-sources.md), bạn nên chuyển từ môi trường demo sang môi trường trực tiếp. Sử dụng môi trường sản xuất cho phép bạn làm việc với dữ liệu khách hàng của riêng mình. Chọn kiểm soát **Môi trường** ở góc trên bên phải của trang để thay đổi môi trường.

> [!div class="mx-imgBorder"] 
> ![Chuyển đổi môi trường](media/home-page-environment-switcher.png "Chuyển đổi môi trường")

Quản trị viên có thể tạo và quản lý [nhiều môi trường](manage-environments.md). Việc duy trì nhiều môi trường có thể hữu ích nếu chẳng hạn, tổ chức của bạn hoạt động trên phạm vi quốc tế và bạn cần tách biệt dữ liệu và thông tin chi tiết theo nhiều cách khác nhau.

## <a name="next-step"></a>Bước tiếp theo

Để xem thông tin chi tiết của bạn trên trang chủ, trước tiên, bạn cần [thêm nguồn dữ liệu](data-sources.md) và [hợp nhất](data-unification.md) dữ liệu để xây dựng hồ sơ khách hàng.
