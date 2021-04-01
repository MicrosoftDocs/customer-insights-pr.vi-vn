---
title: Trình kết nối Power BI
description: Tìm hiểu về cách dùng trình kết nối Dynamics 365 Customer Insights trong Power BI.
ms.date: 09/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: e43e2f9dbc84ebfbf2154990a752740f973296cb
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596065"
---
# <a name="connector-for-power-bi-preview"></a>Trình kết nối cho Power BI (xem trước)

Tạo trực quan hóa cho dữ liệu của bạn với Power BI Desktop. Tạo thông tin chi tiết bổ sung và xây dựng báo cáo với dữ liệu khách hàng hợp nhất của bạn.

## <a name="prerequisites"></a>Điều kiện tiên quyết

- Bạn có hồ sơ khách hàng hợp nhất.
- Phiên bản mới nhất của [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) được cài đặt trên máy tính của bạn. [Tìm hiểu thêm về Power BI Desktop](/power-bi/desktop-what-is-desktop).

## <a name="configure-the-connector-for-power-bi"></a>Đặt cấu hình trình kết nối cho Power BI

1. Trong Power BI Desktop, chọn **Tệp** > **Nhận dữ liệu**.

1. Chọn **Xem thêm** và tìm kiếm **Dynamics 365 Customer Insights**

1. Chọn **Kết nối**.

1. **Đăng nhập** bằng cùng tài khoản tổ chức bạn dùng cho Customer Insights rồi chọn **Kết nối**.
   > [!NOTE]
   > Tài khoản bạn chỉ ra trong bước này được sử dụng để tìm nạp dữ liệu từ Customer Insights và không cần giống với tài khoản bạn đã đăng nhập vào Power BI. Để đặt lại tài khoản được sử dụng để tìm nạp dữ liệu, hãy mở Power BI và đi đến **Tệp** > **Tùy chọn** > **Cài đặt** > **Cài đặt nguồn dữ liệu**. Trong danh sách nguồn dữ liệu, hãy chọn **Đăng nhập Dynamics 365 Customer Insights** và chọn **Xóa quyền**.  

1. Trong hộp thoại **Trình điều hướng**. bạn sẽ thấy danh sách tất cả các môi trường mà bạn có quyền truy cập. Mở rộng môi trường và mở bất kỳ thư mục nào (thực thể, đo lường, phân đoạn, tăng cường). Ví dụ: mở thư mục **Thực thể** để xem tất cả các thực thể bạn có thể nhập.

   ![Trình điều hướng trình kết nối Power BI](media/power-bi-navigator.png "Trình điều hướng trình kết nối Power BI")

1. Chọn hộp kiểm bên cạnh các thực thể để bao gồm và **Tải**. Bạn có thể chọn nhiều thực thể ngay từ nhiều môi trường.

1. Bạn sẽ thấy hộp thoại tải trong khi các thực thể của bạn được tải. Khi tất cả các thực thể mà bạn chọn đã tải xong, bạn có thể sử dụng các khả năng của Power BI để trực quan hóa dữ liệu.

## <a name="large-data-sets"></a>Tập hợp dữ liệu lớn

Trình kết nối Customer Insights cho Power BI được thiết kế để hoạt động cho các tập hợp dữ liệu có chứa tới 1 triệu hồ sơ khách hàng. Việc nhập các tập hợp dữ liệu lớn hơn có thể hiệu quả, nhưng mất nhiều thời gian. Ngoài ra, quá trình này có thể hết thời gian chờ vì những hạn chế của Power BI. Để biết thêm thông tin, hãy xem [Power BI: Đề xuất cho tập hợp dữ liệu lớn](/power-bi/admin/service-premium-what-is#large-datasets). 

### <a name="work-with-a-subset-of-data"></a>Làm việc với một tập hợp con dữ liệu

Cân nhắc làm việc với một tập hợp con dữ liệu của bạn. Ví dụ: bạn có thể tạo [phân đoạn](segments.md) thay vì xuất tất cả hồ sơ khách hàng sang Power BI.

## <a name="troubleshooting"></a>Khắc phục sự cố

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a>Môi trường Customer Insights không hiển thị trong Power BI

Môi trường có nhiều hơn một [mối quan hệ](relationships.md) được xác định giữa hai thực thể giống nhau trong thông tin chi tiết về đối tượng sẽ không có sẵn trong trình kết nối Power BI.

Bạn có thể xác định và loại bỏ các mối quan hệ trùng lặp.

1. Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Dữ liệu** > **Các mối quan hệ** trên môi trường bạn đang thiếu trong Power BI.
2. Xác định các mối quan hệ trùng lặp:
   - Kiểm tra xem có nhiều hơn một mối quan hệ được xác định giữa hai thực thể giống nhau hay không.
   - Kiểm tra xem có mối quan hệ nào được tạo ra giữa hai thực thể đều được bao gồm trong quá trình hợp nhất hay không. Có một mối quan hệ ngầm được xác định giữa tất cả các thực thể có trong quá trình hợp nhất.
3. Loại bỏ bất kỳ mối quan hệ trùng lặp nào được xác định.

Sau khi loại bỏ các mối quan hệ trùng lặp, hãy thử định cấu hình trình kết nối Power BI lần nữa. Môi trường sẽ có sẵn ngay.

[!INCLUDE[footer-include](../includes/footer-banner.md)]