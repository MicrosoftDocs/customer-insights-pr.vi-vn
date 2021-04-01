---
title: Xuất dữ liệu Customer Insights sang Dynamics 365 Marketing
description: Tìm hiểu cách đặt cấu hình kết nối với Dynamics 365 Marketing.
ms.date: 02/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 892aff643872f11307a2c43e5670edab657d7848
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597629"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a>Tác nhân kết nối dành cho Dynamics 365 Marketing (xem trước)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Dùng [các phân đoạn](segments.md) để tạo chiến dịch và liên hệ với các nhóm khách hàng cụ thể với Dynamics 365 Marketing. Để biết thêm thông tin, hãy xem [Sử dụng phân khúc từ Dynamics 365 Customer Insights với Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)

## <a name="prerequisite"></a>Điều kiện tiên quyết

- Hồ sơ liên hệ phải có trong Dynamics 365 Marketing trước khi bạn có thể xuất một phân đoạn từ Customer Insights sang Marketing. Đọc thêm về cách nhập liên hệ vào [Dynamics 365 Marketing bằng Common Data Services](connect-power-query.md).

  > [!NOTE]
  > Việc xuất các phân đoạn từ thông tin chi tiết về đối tượng sang Marketing sẽ không tạo hồ sơ liên hệ mới trong các phiên bản Marketing. Các bản ghi liên hệ từ Marketing phải được nhập vào thông tin chi tiết về đối tượng và được sử dụng làm nguồn dữ liệu. Chúng cũng cần được đưa vào thực thể Khách hàng hợp nhất để ánh xạ ID khách hàng với ID liên hệ trước khi có thể xuất phân đoạn.

## <a name="configure-the-connector-for-marketing"></a>Đặt cấu hình tác nhân kết nối dành cho Marketing

1. Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Quản trị viên** > **Nơi xuất đích**.

1. Trong phần **Dynamics 365 Marketing**, chọn **Thiết lập**.

1. Trong trường **Tên hiển thị**, hãy đặt cho đích xuất một cái tên dễ nhận biết.

1. Nhập URL Marketing của tổ chức bạn vào trường **Địa chỉ máy chủ**.

1. Trong phần **Tài khoản quản trị viên máy chủ**, chọn **Đăng nhập** rồi chọn tài khoản Dynamics 365 Marketing.

1. Ánh xạ trường ID khách hàng với ID liên hệ Dynamics 365.

1. Chọn **Tiếp theo**.

1. Chọn một hoặc nhiều phân khúc.

1. Chọn **Lưu**.

## <a name="export-the-data"></a>Xuất dữ liệu

Bạn có thể [xuất dữ liệu theo nhu cầu](export-destinations.md). Mỗi lần [làm mới theo lịch](system.md#schedule-tab), tác vụ xuất cũng sẽ chạy.


[!INCLUDE[footer-include](../includes/footer-banner.md)]