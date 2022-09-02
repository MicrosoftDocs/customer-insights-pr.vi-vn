---
title: Yêu cầu theo Quyền của chủ thể dữ liệu (DSR) phù hợp với GDPR | Microsoft Docs
description: Trả lời Quyền của chủ thể dữ liệu đối với Dynamics 365 Customer Insights.
ms.date: 08/31/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 49251fb46957c4d7ec205b93c9547a3cd380eb11
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387137"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Yêu cầu theo Quyền của chủ thể dữ liệu (DSR) phù hợp với GDPR

Quy định Chung về Bảo vệ Dữ liệu (GDPR) của Liên minh Châu Âu đã có hiệu lực kể từ ngày 25 tháng 5 năm 2018. Quy định này cung cấp các quyền quan trọng cho các cá nhân liên quan đến dữ liệu của họ. GDPR là quy định về việc bảo vệ và cho phép các quyền riêng tư của các cá nhân. Đọc thêm về cam kết của Microsoft đối với bảo mật và tuân thủ tại [Trung tâm tin cậy của Microsoft](https://www.microsoft.com/trust-center).

Chúng tôi cam kết giúp khách hàng của mình đáp ứng các yêu cầu về GDPR của họ. Nó bao gồm quyền xóa hoặc xuất dữ liệu bao gồm thông tin cá nhân như ID người dùng, số điện thoại và địa chỉ email. Quản trị viên có thể thực hiện các yêu cầu của người dùng để xóa hoặc xuất dữ liệu cá nhân.

## <a name="responding-to-gdpr-data-subject-delete-requests-for-customer-insights"></a>Đáp ứng yêu cầu xóa chủ đề dữ liệu GDPR đối với Thông tin chi tiết về khách hàng

"Quyền xóa" dữ liệu cá nhân khỏi dữ liệu khách hàng của tổ chức là sự bảo vệ chính trong Quy định Chung về Bảo vệ Dữ liệu (GDPR). Việc xóa dữ liệu cá nhân bao gồm xóa tất cả dữ liệu cá nhân và nhật ký do hệ thống tạo, ngoại trừ thông tin nhật ký kiểm tra.

### <a name="manage-data-subject-delete-requests"></a>Quản lý yêu cầu xóa của chủ thể dữ liệu

Thông tin chi tiết về khách hàng cung cấp các trải nghiệm trong sản phẩm sau để xóa dữ liệu cá nhân cho một khách hàng hoặc người dùng cụ thể:

- **Quản lý yêu cầu xóa đối với dữ liệu khách hàng**: Dữ liệu khách hàng trong Customer Insights được nhập từ các nguồn dữ liệu ban đầu bên ngoài Customer Insights. Trước tiên, hãy thực hiện các yêu cầu xóa GDPR trong nguồn dữ liệu gốc.
- **Quản lý yêu cầu xóa đối với dữ liệu người dùng Customer Insights**: Dữ liệu cho người dùng được tạo bởi Customer Insights. Thực hiện tất cả các yêu cầu xóa GDPR trong Thông tin chi tiết về khách hàng.

#### <a name="manage-requests-to-delete-customer-data"></a>Quản lý yêu cầu xóa dữ liệu khách hàng

Với tư cách là quản trị viên Customer Insights, hãy xóa dữ liệu khách hàng Customer Insights đã bị xóa trong nguồn dữ liệu. Xác minh rằng các yêu cầu xóa GDPR đã được thực hiện trong nguồn dữ liệu ban đầu.

1. Đăng nhập vào Dynamics 365 Customer Insights.

1. Chuyển tới **Dữ liệu** > **Nguồn dữ liệu**.

1. Đối với từng nguồn dữ liệu trong danh sách chứa dữ liệu khách hàng đã xóa:
   1. Chọn nguồn dữ liệu rồi chọn **Làm mới**.
   1. Kiểm tra trạng thái nguồn dữ liệu trong **Trạng thái**. Một dấu kiểm có nghĩa là làm mới đã thành công. Một tam giác cảnh báo có nghĩa là đã có vấn đề. Nếu hình tam giác cảnh báo được hiển thị, hãy liên hệ với D365CI@microsoft.com.

   :::image type="content" source="media/gdpr-data-sources.png" alt-text="Xử lý yêu cầu xóa dữ liệu khách hàng theo GDPR.":::

1. Sau khi làm mới nguồn dữ liệu thành công, hãy chạy quá trình làm mới xuôi dòng. Đặc biệt, nếu bạn không lập lịch làm mới đầy đủ định kỳ Thông tin chi tiết về khách hàng.

   > [!IMPORTANT]
   > Các phân đoạn tĩnh không được bao gồm trong quá trình làm mới hoàn toàn hoặc chạy làm mới xuống dòng sau khi có yêu cầu xóa. Để đảm bảo rằng dữ liệu khách hàng cũng bị xóa khỏi các phân đoạn tĩnh, hãy tạo lại các phân đoạn tĩnh bằng dữ liệu nguồn được làm mới.

#### <a name="manage-delete-requests-for-user-data"></a>Quản lý yêu cầu xóa dữ liệu người dùng

Với tư cách là quản trị viên Customer Insights, hãy xóa dữ liệu người dùng của Customer Insights.

1. Đăng nhập vào Dynamics 365 Customer Insights.

1. Đi đến **Quản trị viên** > **Bảo vệ** > và chọn **Người dùng** chuyển hướng.

1. Chọn hộp kiểm cho những người dùng bạn muốn xóa.

1. Chọn **Loại bỏ**.

1. Xác nhận tác vụ xóa này.

## <a name="responding-to-gdpr-data-subject-export-requests"></a>Trả lời yêu cầu xuất của chủ thể dữ liệu theo GDPR

Quyền chuyển đổi dữ liệu cho phép chủ thể dữ liệu yêu cầu lấy bản sao dữ liệu cá nhân của họ ở định dạng điện tử ("định dạng có cấu trúc, thường dùng, có thể đọc được bằng máy và có thể tương tác") có thể được truyền đến đơn vị kiểm soát dữ liệu khác.

### <a name="manage-export-and-view-requests"></a>Quản lý các yêu cầu xuất và xem

Quản lý các yêu cầu xuất dữ liệu khách hàng hoặc người dùng.

#### <a name="export-customer-data-tenant-admin"></a>Xuất dữ liệu khách hàng (quản trị viên đối tượng thuê)

Với tư cách là quản trị viên đối tượng thuê, hãy xuất dữ liệu khách hàng.

1. Gửi email tới D365CI@microsoft.com cho biết địa chỉ email của khách hàng trong yêu cầu. Nhóm Customer Insights sẽ gửi email đến địa chỉ email quản trị viên đối tượng thuê đã đăng ký, yêu cầu xác nhận để xuất dữ liệu.
2. Hãy xác minh để xuất dữ liệu cho khách hàng yêu cầu.
3. Nhận dữ liệu được xuất thông qua địa chỉ email quản trị viên đối tượng thuê.

#### <a name="export-user-data-tenant-admin"></a>Xuất dữ liệu người dùng (quản trị viên đối tượng thuê)

Với tư cách là quản trị viên đối tượng thuê, hãy xuất dữ liệu người dùng.

1. Gửi email tới D365CI@microsoft.com cho biết địa chỉ email của người dùng trong yêu cầu. Nhóm Thông tin chi tiết về khách hàng sẽ gửi email đến địa chỉ email quản trị của người thuê đã đăng ký, yêu cầu xác nhận để xuất dữ liệu.
1. Hãy xác minh để xuất dữ liệu cho người dùng yêu cầu.
1. Nhận dữ liệu được xuất thông qua địa chỉ email quản trị viên đối tượng thuê.

## <a name="data-deletion-handling-in-dynamics-365-customer-insights"></a>Xử lý xóa dữ liệu trong Dynamics 365 Customer Insights

Dữ liệu bị xóa (phân vùng dữ liệu và ảnh chụp nhanh dữ liệu) nếu phân vùng dữ liệu và ảnh chụp nhanh dữ liệu không hoạt động trong hơn 30 ngày, có nghĩa là chúng đã được thay thế bằng phân vùng dữ liệu mới và ảnh chụp nhanh thông qua việc làm mới nguồn dữ liệu.

Không phải tất cả dữ liệu và ảnh chụp nhanh đều bị xóa. Phân vùng dữ liệu gần đây nhất và ảnh chụp nhanh dữ liệu đang hoạt động vì chúng được sử dụng trong Thông tin chi tiết về khách hàng. Đối với dữ liệu gần đây nhất, không quan trọng nếu các nguồn dữ liệu không được làm mới trong vòng 30 ngày qua.

[!INCLUDE [footer-include](includes/footer-banner.md)]
