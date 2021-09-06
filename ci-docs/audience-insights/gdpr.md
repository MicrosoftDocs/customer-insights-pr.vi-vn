---
title: Yêu cầu theo Quyền của chủ thể dữ liệu (DSR) phù hợp với GDPR | Microsoft Docs
description: Trả lời các yêu cầu về chủ đề dữ liệu cho khả năng thông tin chi tiết về đối tượng Dynamics 365 Customer Insights.
ms.date: 05/14/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 891794321f20954533ec0374b397eaf6b30445c2b0c95f601009912b3c3950a7
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034541"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Yêu cầu theo Quyền của chủ thể dữ liệu (DSR) phù hợp với GDPR

## <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a>Trả lời yêu cầu xóa chủ đề dữ liệu GDPR cho khả năng thông tin chi tiết về đối tượng Dynamics 365 Customer Insights

"Quyền xóa" dữ liệu cá nhân khỏi dữ liệu khách hàng của tổ chức là sự bảo vệ chính trong Quy định Chung về Bảo vệ Dữ liệu (GDPR). Việc xóa dữ liệu cá nhân bao gồm xóa tất cả dữ liệu cá nhân và nhật ký do hệ thống tạo, ngoại trừ thông tin nhật ký kiểm tra.

### <a name="manage-data-subject-delete-requests"></a>Quản lý yêu cầu xóa của chủ thể dữ liệu

Thông tin chi tiết về đối tượng cung cấp những trải nghiệm trong sản phẩm sau để xóa dữ liệu cá nhân cho một khách hàng hoặc người dùng cụ thể:

- **Quản lý yêu cầu xóa đối với dữ liệu khách hàng**: Dữ liệu khách hàng trong Customer Insights được nhập từ các nguồn dữ liệu ban đầu bên ngoài Customer Insights. Tất cả yêu cầu xóa theo GDPR phải được thực hiện trong nguồn dữ liệu gốc.
- **Quản lý yêu cầu xóa đối với dữ liệu người dùng Customer Insights**: Dữ liệu cho người dùng được tạo bởi Customer Insights. Tất cả yêu cầu xóa GDPR phải được thực hiện trong Customer Insights.

#### <a name="manage-delete-requests-for-customer-data"></a>Quản lý yêu cầu xóa dữ liệu khách hàng

Quản trị viên Customer Insights có thể làm theo các bước sau để xóa dữ liệu khách hàng đã bị xóa trong nguồn dữ liệu:

1. Đăng nhập vào Dynamics 365 Customer Insights.
2. Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Dữ liệu** > **Nguồn dữ liệu**
3. Đối với từng nguồn dữ liệu trong danh sách chứa dữ liệu khách hàng đã xóa:
   1. Chọn (...) rồi chọn **Làm mới**.
   2. Kiểm tra trạng thái nguồn dữ liệu trong **Trạng thái**. Một dấu kiểm có nghĩa là làm mới đã thành công. Một tam giác cảnh báo có nghĩa là đã có vấn đề. Nếu hình tam giác cảnh báo được hiển thị, hãy liên hệ với D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![Xử lý yêu cầu xóa dữ liệu khách hàng theo GDPR.](media/gdpr-data-sources.png "Xử lý yêu cầu xóa dữ liệu khách hàng theo GDPR")

#### <a name="manage-delete-requests-for-user-data"></a>Quản lý yêu cầu xóa dữ liệu người dùng

Quản trị viên Customer Insights có thể làm theo các bước sau để xóa dữ liệu người dùng Customer Insights:

1. Đăng nhập vào Dynamics 365 Customer Insights.
2. Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Quản trị** > **Quyền**.
3. Chọn hộp kiểm tương ứng với người dùng bạn muốn xóa.
4. Chọn **Loại bỏ**.

> [!div class="mx-imgBorder"]
> ![Xử lý yêu cầu xóa GDPR đối với dữ liệu người dùng.](media/gdpr-permissions.png "Xử lý yêu cầu xóa dữ liệu người dùng theo GDPR")

## <a name="responding-to-gdpr-data-subject-export-requests"></a>Trả lời yêu cầu xuất của chủ thể dữ liệu theo GDPR

Là một phần trong cam kết của chúng tôi để hợp tác với bạn trên hành trình của bạn theo Quy định chung về bảo vệ dữ liệu (GDPR), chúng tôi đã phát triển tài liệu để giúp bạn chuẩn bị. Tài liệu này mô tả các bước bạn có thể thực hiện ngay hôm nay để hỗ trợ tuân thủ GDPR khi sử dụng thông tin chi tiết về đối tượng.

### <a name="manage-export-and-view-requests"></a>Quản lý các yêu cầu xuất và xem

Quyền chuyển đổi dữ liệu cho phép chủ thể dữ liệu yêu cầu lấy bản sao dữ liệu cá nhân của họ ở định dạng điện tử ("định dạng có cấu trúc, thường dùng, có thể đọc được bằng máy và có thể tương tác") có thể được truyền đến đơn vị kiểm soát dữ liệu khác.

#### <a name="export-customer-data-tenant-admin"></a>Xuất dữ liệu khách hàng (quản trị viên đối tượng thuê)

Quản trị viên đối tượng thuê có thể tuân theo các bước sau để xuất dữ liệu:

1. Gửi email tới D365CI@microsoft.com cho biết địa chỉ email của khách hàng trong yêu cầu. Nhóm Customer Insights sẽ gửi email đến địa chỉ email quản trị viên đối tượng thuê đã đăng ký, yêu cầu xác nhận để xuất dữ liệu.
2. Hãy xác minh để xuất dữ liệu cho khách hàng yêu cầu.
3. Nhận dữ liệu được xuất thông qua địa chỉ email quản trị viên đối tượng thuê.

#### <a name="export-user-data-tenant-admin"></a>Xuất dữ liệu người dùng (quản trị viên đối tượng thuê)

1. Gửi email tới D365CI@microsoft.com cho biết địa chỉ email của người dùng trong yêu cầu. Nhóm Customer Insights sẽ gửi email đến địa chỉ email quản trị viên đối tượng thuê đã đăng ký, yêu cầu xác nhận để xuất dữ liệu.
2. Hãy xác minh để xuất dữ liệu cho người dùng yêu cầu.
3. Nhận dữ liệu được xuất thông qua địa chỉ email quản trị viên đối tượng thuê.


[!INCLUDE[footer-include](../includes/footer-banner.md)]