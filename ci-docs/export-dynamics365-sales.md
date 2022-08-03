---
title: Xuất phân đoạn sang Dynamics 365 Sales (xem trước)
description: Tìm hiểu cách đặt cấu hình kết nối và xuất sang Dynamics 365 Sales.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- customerInsights
ms.openlocfilehash: c3497f4625cada49ae33c6987e58994a15536f9b
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196007"
---
# <a name="export-segments-to-dynamics-365-sales-preview"></a>Xuất phân đoạn sang Dynamics 365 Sales (xem trước)

Sử dụng dữ liệu khách hàng của bạn để tạo danh sách khách hàng tiếp thị, theo dõi quy trình làm việc và gửi thư quảng cáo với Dynamics 365 Sales.

## <a name="prerequisites"></a>Điều kiện tiên quyết

Hồ sơ liên hệ phải có trong Dynamics 365 Sales trước khi bạn có thể xuất một phân đoạn từ Customer Insights sang Sales. Đọc thêm về cách nhập danh bạ từ [Sử dụng Dynamics 365 Sales Microsoft Dataverse](connect-dataverse-managed-lake.md).

   > [!NOTE]
   > Việc xuất các phân đoạn từ Thông tin chi tiết về khách hàng sang Bán hàng sẽ không tạo hồ sơ liên hệ mới trong các trường hợp Bán hàng. Hồ sơ liên hệ từ Bán hàng phải được nhập trong Thông tin chi tiết về khách hàng và được sử dụng làm nguồn dữ liệu. Chúng cũng cần được đưa vào thực thể Khách hàng hợp nhất để ánh xạ ID khách hàng với ID liên hệ trước khi có thể xuất phân đoạn.

## <a name="known-limitations"></a>Các hạn chế đã biết

Xuất sang Dynamics 365 Sales được giới hạn ở 100.000 cho mỗi phân đoạn, có thể mất tới 3 giờ để hoàn thành.

## <a name="set-up-connection-to-sales"></a>Thiết lập kết nối với Bán hàng

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Đi đến **Quản trị viên** > **Kết nối**.

1. Lựa chọn **Thêm kết nối** và lựa chọn **Bán hàng Dynamics 365**.

1. Đặt tên dễ nhận biết cho kết nối trong trường **Tên hiển thị**. Tên và loại kết nối mô tả kết nối này. Bạn nên chọn một tên giải thích mục đích và mục tiêu của kết nối.

1. Chọn người có thể sử dụng kết nối này. Theo mặc định, giá trị này là quản trị viên. Để biết thêm thông tin, hãy xem [Cho phép người đóng góp sử dụng một kết nối cho các lần xuất](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Nhập URL Sales của tổ chức bạn vào trường **Địa chỉ máy chủ**.

1. Trong phần **Tài khoản quản trị viên máy chủ**, chọn **Đăng nhập** rồi chọn tài khoản Dynamics 365 Sales.

1. Ánh xạ trường ID khách hàng với ID liên hệ Dynamics 365.

1. Xem lại [quyền riêng tư và tuân thủ dữ liệu](connections.md#data-privacy-and-compliance) và chọn **tôi đồng ý**.

1. Chọn **Lưu** để hoàn thành kết nối.

## <a name="configure-an-export"></a>Định cấu hình xuất

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Đi tới **Dữ liệu** > **Nội dung xuất**.

1. Lựa chọn **Thêm xuất khẩu**.

1. Trong trường **Kết nối để xuất**, hãy chọn một kết nối từ phần Dynamics 365 Sales. Liên hệ với quản trị viên nếu không có kết nối.

1. Nhập tên cho lần xuất.

1. Chọn trường ID liên hệ trong thực thể Khách hàng phù hợp với ID liên hệ Dynamics 365.

1. Chọn phân khúc mà bạn muốn xuất.

1. Chọn **Lưu**

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
