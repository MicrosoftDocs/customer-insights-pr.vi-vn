---
title: Trình kết nối Power BI (xem trước)
description: Tìm hiểu về cách dùng trình kết nối Dynamics 365 Customer Insights trong Power BI.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 656a695b8b3f1ec2b5fbaad69feba7f1f0b73dee
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196696"
---
# <a name="power-bi-connector-preview"></a>Trình kết nối Power BI (xem trước)

Tạo hình ảnh trực quan cho dữ liệu của bạn với Microsoft Power BI Máy tính để bàn. Tạo thông tin chi tiết bổ sung và xây dựng báo cáo với dữ liệu khách hàng hợp nhất của bạn.

## <a name="prerequisites"></a>Điều kiện tiên quyết

- Hồ sơ khách hàng hợp nhất.
- Phiên bản mới nhất của [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) được cài đặt trên máy tính của bạn. [Tìm hiểu thêm về Power BI Desktop](/power-bi/desktop-what-is-desktop).

## <a name="configure-the-connector-for-power-bi"></a>Đặt cấu hình trình kết nối cho Power BI

1. Trong Power BI Desktop, chọn **Tệp** > **Nhận dữ liệu**.

1. Chọn **Xem thêm** và tìm kiếm **Dynamics 365 Customer Insights**

1. Chọn **Kết nối**.

1. **Đăng nhập** bằng cùng tài khoản tổ chức bạn dùng cho Customer Insights rồi chọn **Kết nối**.
   > [!NOTE]
   > Tài khoản bạn chỉ ra trong bước này được sử dụng để tìm nạp dữ liệu từ Customer Insights và không cần giống với tài khoản bạn đã đăng nhập vào Power BI. Để đặt lại tài khoản được sử dụng để tìm nạp dữ liệu, hãy mở Power BI và đi đến **Tệp** > **Tùy chọn** > **Cài đặt** > **Cài đặt nguồn dữ liệu**. Trong danh sách nguồn dữ liệu, hãy chọn **Đăng nhập Dynamics 365 Customer Insights** và chọn **Xóa quyền**.  

1. Bên trong **Hoa tiêu** hộp thoại, xem danh sách tất cả các môi trường bạn có quyền truy cập. Mở rộng môi trường và mở bất kỳ thư mục nào (thực thể, đo lường, phân đoạn, tăng cường). Ví dụ: mở thư mục **Thực thể** để xem tất cả các thực thể bạn có thể nhập.

   :::image type="content" source="media/power-bi-navigator.png" alt-text="Trình điều hướng trình kết nối Power BI.":::

1. Chọn hộp kiểm bên cạnh các thực thể để bao gồm và **Tải**. Bạn có thể chọn nhiều thực thể ngay từ nhiều môi trường.

   Hộp thoại đang tải hiển thị trong khi các thực thể của bạn được tải. Khi tất cả các thực thể bạn đã chọn đã tải xong, hãy sử dụng các khả năng của Power BI để trực quan hóa dữ liệu.

## <a name="large-data-sets"></a>Tập hợp dữ liệu lớn

Trình kết nối Customer Insights cho Power BI được thiết kế để hoạt động cho các tập hợp dữ liệu có chứa tới 1 triệu hồ sơ khách hàng. Việc nhập các tập dữ liệu lớn hơn có thể hoạt động, nhưng mất nhiều thời gian và có thể hết thời gian vì Power BI những hạn chế. Để biết thêm thông tin, hãy xem [Power BI: Đề xuất cho tập hợp dữ liệu lớn](/power-bi/admin/service-premium-what-is#large-datasets).

### <a name="work-with-a-subset-of-data"></a>Làm việc với một tập hợp con dữ liệu

Cân nhắc làm việc với một tập hợp con dữ liệu của bạn. Ví dụ, tạo [phân đoạn](segments.md) thay vì xuất tất cả hồ sơ khách hàng sang Power BI.

## <a name="troubleshooting"></a>Khắc phục sự cố

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a>Môi trường Customer Insights không hiển thị trong Power BI

Môi trường có nhiều hơn một [mối quan hệ](relationships.md) được xác định giữa hai thực thể giống nhau trong Thông tin chi tiết về khách hàng sẽ không có sẵn trong Power BI kết nối.

Xác định và loại bỏ các mối quan hệ trùng lặp.

1. Đi đến **Dữ liệu** > **Các mối quan hệ** về môi trường bạn đang bỏ lỡ Power BI.
1. Xác định các mối quan hệ trùng lặp:
   - Kiểm tra xem có nhiều hơn một mối quan hệ được xác định giữa hai thực thể giống nhau hay không.
   - Kiểm tra xem có mối quan hệ nào được tạo ra giữa hai thực thể đều được bao gồm trong quá trình hợp nhất hay không. Có một mối quan hệ ngầm được xác định giữa tất cả các thực thể có trong quá trình hợp nhất.
1. Loại bỏ bất kỳ mối quan hệ trùng lặp nào được xác định.

Sau khi loại bỏ các mối quan hệ trùng lặp, hãy thử định cấu hình trình kết nối Power BI lần nữa.

### <a name="errors-on-date-fields-when-loading-entities-in-power-bi-desktop"></a>Lỗi trên trường ngày khi tải các thực thể trong Power BI Desktop

Khi tải các thực thể chứa các trường có định dạng ngày tháng như MM / DD / YYYY, bạn có thể gặp phải lỗi do định dạng ngôn ngữ không khớp. Sự không phù hợp này xảy ra khi Power BI Desktop tệp được đặt thành ngôn ngữ khác ngoài tiếng Anh (Hoa Kỳ), vì các trường ngày trong Thông tin chi tiết về khách hàng được lưu ở định dạng Hoa Kỳ.

Tệp Power BI Desktop có một cài đặt ngôn ngữ duy nhất, được áp dụng khi truy xuất dữ liệu. Để sửa lỗi ngày tháng, [đặt ngôn ngữ của tệp .BPI](/power-bi/fundamentals/supported-languages-countries-regions#choose-the-language-or-locale-of-power-bi-desktop) sang tiếng Anh (Hoa Kỳ).

[!INCLUDE [footer-include](includes/footer-banner.md)]
