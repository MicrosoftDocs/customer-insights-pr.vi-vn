---
title: Trình kết nối Power BI
description: Tìm hiểu về cách dùng trình kết nối Dynamics 365 Customer Insights trong Power BI.
ms.date: 09/21/2020
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d497ca779a337c512a7254524f597cff226bcb45
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407294"
---
# <a name="connector-for-power-bi-preview"></a>Trình kết nối cho Power BI (xem trước)

Tạo trực quan hóa cho dữ liệu của bạn với Power BI Desktop. Tạo thông tin chi tiết bổ sung và xây dựng báo cáo với dữ liệu khách hàng hợp nhất của bạn.

## <a name="prerequisites"></a>Điều kiện tiên quyết

- Bạn có hồ sơ khách hàng hợp nhất.
- Phiên bản mới nhất của [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) được cài đặt trên máy tính của bạn. [Tìm hiểu thêm về Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).

## <a name="configure-the-connector-for-power-bi"></a>Đặt cấu hình trình kết nối cho Power BI

1. Trong Power BI Desktop, chọn **Tệp** > **Nhận dữ liệu**.

1. Chọn **Xem thêm** và tìm kiếm **Dynamics 365 Customer Insights**

1. Chọn kết quả và chọn **Kết nối**.

1. **Đăng nhập** bằng cùng tài khoản tổ chức bạn dùng cho Customer Insights rồi chọn **Kết nối**.
   > [!NOTE]
   > Tài khoản bạn chỉ ra trong bước này được sử dụng để tìm nạp dữ liệu từ Customer Insights và không cần giống với tài khoản bạn đã đăng nhập vào Power BI. Để đặt lại tài khoản được sử dụng để tìm nạp dữ liệu, hãy mở Power BI và đi đến **Tệp** > **Tùy chọn** > **Cài đặt** > **Cài đặt nguồn dữ liệu**. Trong danh sách nguồn dữ liệu, hãy chọn **Đăng nhập Dynamics 365 Customer Insights** và chọn **Xóa quyền**.  

1. Trong hộp thoại **Trình điều hướng**. bạn sẽ thấy danh sách tất cả các môi trường mà bạn có quyền truy cập. Mở rộng môi trường và mở bất kỳ thư mục nào (thực thể, đo lường, phân đoạn, tăng cường). Ví dụ: mở thư mục **Thực thể** để xem tất cả các thực thể bạn có thể nhập.

   ![Trình điều hướng trình kết nối Power BI](media/power-bi-navigator.png "Trình điều hướng trình kết nối Power BI")

1. Chọn hộp kiểm bên cạnh các thực thể để bao gồm và **Tải**. Bạn có thể chọn nhiều thực thể ngay từ nhiều môi trường.

1. Bạn sẽ thấy hộp thoại tải trong khi các thực thể của bạn được tải. Khi tất cả các thực thể mà bạn chọn đã tải xong, bạn có thể sử dụng các khả năng của Power BI để trực quan hóa dữ liệu.

## <a name="large-data-sets"></a>Tập hợp dữ liệu lớn

Trình kết nối Customer Insights cho Power BI được thiết kế để hoạt động cho các tập hợp dữ liệu có chứa tới 1 triệu hồ sơ khách hàng. Việc nhập các tập hợp dữ liệu lớn hơn có thể hiệu quả, nhưng mất nhiều thời gian. Ngoài ra, quá trình này có thể hết thời gian chờ vì những hạn chế của Power BI. Để biết thêm thông tin, hãy xem [Power BI: Đề xuất cho tập hợp dữ liệu lớn](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets). 

### <a name="work-with-a-subset-of-data"></a>Làm việc với một tập hợp con dữ liệu

Cân nhắc làm việc với một tập hợp con dữ liệu của bạn. Ví dụ: bạn có thể tạo [phân đoạn](segments.md) thay vì xuất tất cả hồ sơ khách hàng sang Power BI.
