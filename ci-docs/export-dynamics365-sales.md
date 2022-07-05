---
title: Xuất phân đoạn sang Bán hàng Dynamics 365 (xem trước)
description: Tìm hiểu cách đặt cấu hình kết nối và xuất sang Dynamics 365 Sales.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- customerInsights
ms.openlocfilehash: b8e756313ca037dca41cb25587229808f0c584c9
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082398"
---
# <a name="export-segments-to-dynamics-365-sales-preview"></a>Xuất phân đoạn sang Bán hàng Dynamics 365 (xem trước)

Sử dụng dữ liệu khách hàng của bạn để tạo danh sách khách hàng tiếp thị, theo dõi quy trình làm việc và gửi thư quảng cáo với Dynamics 365 Sales.

## <a name="known-limitations"></a>Các hạn chế đã biết

- Xuất khẩu sang Dynamics 365 Sales được giới hạn ở 100'000 thành viên trên mỗi phân khúc.
- Quá trình xuất phân đoạn sang Dynamics 365 Sales có thể mất đến 3 giờ để hoàn tất. 

## <a name="prerequisite-for-connection"></a>Điều kiện tiên quyết để kết nối

1. Hồ sơ liên hệ phải có trong Dynamics 365 Sales trước khi bạn có thể xuất một phân đoạn từ Customer Insights sang Sales. Đọc thêm về cách nhập danh bạ từ [Sử dụng Dynamics 365 Sales Microsoft Dataverse](connect-dataverse-managed-lake.md).

   > [!NOTE]
   > Việc xuất các phân đoạn từ Thông tin chi tiết về khách hàng sang Bán hàng sẽ không tạo hồ sơ liên hệ mới trong các trường hợp Bán hàng. Hồ sơ liên hệ từ Bán hàng phải được nhập trong Thông tin chi tiết về khách hàng và được sử dụng làm nguồn dữ liệu. Chúng cũng cần được đưa vào thực thể Khách hàng hợp nhất để ánh xạ ID khách hàng với ID liên hệ trước khi có thể xuất phân đoạn.

## <a name="set-up-the-connection-to-sales"></a>Thiết lập kết nối với Sales

1. Đi đến **Quản trị viên** > **Kết nối**.

1. Chọn **Thêm kết nối** rồi chọn **Dynamics 365 Sales** để đặt cấu hình kết nối.

1. Đặt tên dễ nhận biết cho kết nối trong trường **Tên hiển thị**. Tên và loại kết nối mô tả kết nối này. Bạn nên chọn một tên giải thích mục đích và mục tiêu của kết nối.

1. Chọn người có thể sử dụng kết nối này. Nếu bạn không thực hiện hành động nào, giá trị mặc định sẽ là Quản trị viên. Để biết thêm thông tin, hãy xem [Cho phép người đóng góp sử dụng một kết nối cho các lần xuất](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Nhập URL Sales của tổ chức bạn vào trường **Địa chỉ máy chủ**.

1. Trong phần **Tài khoản quản trị viên máy chủ**, chọn **Đăng nhập** rồi chọn tài khoản Dynamics 365 Sales.

1. Ánh xạ trường ID khách hàng với ID liên hệ Dynamics 365.

1. Chọn **Lưu** để hoàn thành kết nối. 

## <a name="configure-an-export"></a>Đặt cấu hình xuất

Bạn có thể định cấu hình lần xuất này nếu bạn có quyền truy cập vào kết nối thuộc loại này. Để biết thêm thông tin, hãy xem [Các quyền cần thiết để định cấu hình xuất](export-destinations.md#set-up-a-new-export).

1. Đi tới **Dữ liệu** > **Nội dung xuất**.

1. Để tạo một nội dung xuất mới, hãy chọn **Thêm đích**.

1. Trong trường **Kết nối để xuất**, hãy chọn một kết nối từ phần Dynamics 365 Sales. Nếu bạn không thấy tên phần này, tức là không có kết nối nào thuộc loại này dành cho bạn.

1. Chọn một hoặc nhiều phân khúc.

1. Chọn **Lưu**

Việc lưu một nội dung xuất sẽ không chạy nội dung xuất đó ngay lập tức.

Nội dung xuất chạy trong mỗi lần [làm mới theo lịch trình](system.md#schedule-tab). Bạn cũng có thể [xuất dữ liệu theo yêu cầu](export-destinations.md#run-exports-on-demand). 

[!INCLUDE [footer-include](includes/footer-banner.md)]
