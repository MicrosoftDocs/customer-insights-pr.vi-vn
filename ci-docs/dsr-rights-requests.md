---
title: Yêu cầu theo Quyền của chủ thể dữ liệu (DSR) phù hợp với GDPR | Microsoft Docs
description: Trả lời Quyền của chủ thể dữ liệu đối với Dynamics 365 Customer Insights.
ms.date: 05/23/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 6c6ce49c18de3a09d28138316d893e6842919042
ms.sourcegitcommit: ff0f4b5664d995870c91adb87c7d3780a582efca
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 07/13/2022
ms.locfileid: "9146721"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Yêu cầu theo Quyền của chủ thể dữ liệu (DSR) phù hợp với GDPR

Quy định Chung về Bảo vệ Dữ liệu (GDPR) của Liên minh Châu Âu đã có hiệu lực kể từ ngày 25 tháng 5 năm 2018. Quy định này cung cấp các quyền quan trọng cho các cá nhân liên quan đến dữ liệu của họ. GDPR là quy định về việc bảo vệ và cho phép các quyền riêng tư của các cá nhân. Bạn có thể đọc thêm về cam kết của Microsoft về vấn đề bảo mật và tuân thủ tại [Trung tâm Tin cậy của Microsoft](https://www.microsoft.com/trust-center).

Chúng tôi cam kết giúp khách hàng của mình đáp ứng các yêu cầu về GDPR của họ. Chức năng này bao gồm quyền xóa và xuất dữ liệu có chứa thông tin cá nhân như ID người dùng, số điện thoại và địa chỉ email. Quản trị viên có thể thực hiện các yêu cầu của người dùng để xóa hoặc xuất dữ liệu cá nhân.

## <a name="dynamics-365-customer-insights"></a>Dynamics 365 Customer Insights

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights"></a>Trả lời yêu cầu xóa của chủ thể dữ liệu theo GDPR đối với Dynamics 365 Customer Insights

"Quyền xóa" dữ liệu cá nhân khỏi dữ liệu khách hàng của tổ chức là sự bảo vệ chính trong Quy định Chung về Bảo vệ Dữ liệu (GDPR). Việc xóa dữ liệu cá nhân bao gồm xóa tất cả dữ liệu cá nhân và nhật ký do hệ thống tạo, ngoại trừ thông tin nhật ký kiểm tra.

#### <a name="manage-data-subject-delete-requests"></a>Quản lý yêu cầu xóa của chủ thể dữ liệu

Thông tin chi tiết về khách hàng cung cấp các trải nghiệm trong sản phẩm sau để xóa dữ liệu cá nhân cho một khách hàng hoặc người dùng cụ thể:

- **Quản lý yêu cầu xóa đối với dữ liệu khách hàng**: Dữ liệu khách hàng trong Customer Insights được nhập từ các nguồn dữ liệu ban đầu bên ngoài Customer Insights. Trước tiên, hãy thực hiện các yêu cầu xóa GDPR trong nguồn dữ liệu gốc.
- **Quản lý yêu cầu xóa đối với dữ liệu người dùng Customer Insights**: Dữ liệu cho người dùng được tạo bởi Customer Insights. Tất cả yêu cầu xóa GDPR phải được thực hiện trong Customer Insights.

##### <a name="manage-requests-to-delete-customer-data"></a>Quản lý yêu cầu xóa dữ liệu khách hàng

Quản trị viên Customer Insights có thể làm theo các bước sau để xóa dữ liệu khách hàng đã bị xóa trong nguồn dữ liệu. Đảm bảo rằng yêu cầu xóa đã được thực hiện trong nguồn dữ liệu của bạn trước khi tiếp tục các bước được liệt kê bên dưới. 

1. Đăng nhập vào Dynamics 365 Customer Insights.
1. Đi đến **Dữ liệu** > **Nguồn dữ liệu**
1. Đối với từng nguồn dữ liệu trong danh sách chứa dữ liệu khách hàng đã xóa:
   1. Chọn dấu chấm lửng dọc (&vellip;) và sau đó chọn **Làm mới**.
   1. Kiểm tra trạng thái nguồn dữ liệu trong **Trạng thái**. Một dấu kiểm có nghĩa là làm mới đã thành công. Một tam giác cảnh báo có nghĩa là đã có vấn đề. Nếu hình tam giác cảnh báo được hiển thị, hãy liên hệ với D365CI@microsoft.com.
1. Sau khi làm mới nguồn dữ liệu thành công, hãy chạy quá trình làm mới xuôi dòng. Đặc biệt, nếu bạn không lập lịch làm mới đầy đủ định kỳ Thông tin chi tiết về khách hàng. 

> [!IMPORTANT]
> Các phân đoạn tĩnh không được bao gồm trong quá trình làm mới toàn bộ hoặc chạy làm mới xuống dòng sau khi có yêu cầu xóa. Để đảm bảo rằng dữ liệu khách hàng cũng bị xóa khỏi các phân đoạn tĩnh, hãy tạo lại các phân đoạn tĩnh bằng dữ liệu nguồn được làm mới.

> [!div class="mx-imgBorder"]
> ![Xử lý yêu cầu xóa dữ liệu khách hàng theo GDPR.](media/gdpr-data-sources.png "Xử lý yêu cầu xóa dữ liệu khách hàng theo GDPR")

##### <a name="manage-delete-requests-for-user-data"></a>Quản lý yêu cầu xóa dữ liệu người dùng

Quản trị viên Customer Insights có thể làm theo các bước sau để xóa dữ liệu người dùng Customer Insights:

1. Đăng nhập vào Dynamics 365 Customer Insights.
2. Đi đến **Quản trị viên** > **Bảo vệ** > **Quyền**.
3. Chọn hộp kiểm tương ứng với người dùng bạn muốn xóa.
4. Chọn **Loại bỏ**.

### <a name="responding-to-gdpr-data-subject-export-requests"></a>Trả lời yêu cầu xuất của chủ thể dữ liệu theo GDPR

Là một phần trong cam kết hợp tác với bạn trong hành trình tuân thủ Quy định chung về bảo vệ dữ liệu (GDPR), chúng tôi đã phát triển tài liệu để giúp bạn phản hồi các yêu cầu từ chủ thể dữ liệu.

#### <a name="manage-export-and-view-requests"></a>Quản lý các yêu cầu xuất và xem

Quyền chuyển đổi dữ liệu cho phép chủ thể dữ liệu yêu cầu lấy bản sao dữ liệu cá nhân của họ ở định dạng điện tử ("định dạng có cấu trúc, thường dùng, có thể đọc được bằng máy và có thể tương tác") có thể được truyền đến đơn vị kiểm soát dữ liệu khác.

##### <a name="export-customer-data-tenant-admin"></a>Xuất dữ liệu khách hàng (quản trị viên đối tượng thuê)

Quản trị viên đối tượng thuê có thể tuân theo các bước sau để xuất dữ liệu:

1. Gửi email tới D365CI@microsoft.com cho biết địa chỉ email của khách hàng trong yêu cầu. Nhóm Customer Insights sẽ gửi email đến địa chỉ email quản trị viên đối tượng thuê đã đăng ký, yêu cầu xác nhận để xuất dữ liệu.
2. Hãy xác minh để xuất dữ liệu cho khách hàng yêu cầu.
3. Nhận dữ liệu được xuất thông qua địa chỉ email quản trị viên đối tượng thuê.

##### <a name="export-user-data-tenant-admin"></a>Xuất dữ liệu người dùng (quản trị viên đối tượng thuê)

1. Gửi email tới D365CI@microsoft.com cho biết địa chỉ email của người dùng trong yêu cầu. Nhóm Customer Insights sẽ gửi email đến địa chỉ email quản trị viên đối tượng thuê đã đăng ký, yêu cầu xác nhận để xuất dữ liệu.
2. Hãy xác minh để xuất dữ liệu cho người dùng yêu cầu.
3. Nhận dữ liệu được xuất thông qua địa chỉ email quản trị viên đối tượng thuê.

### <a name="data-deletion-handling-in-dynamics-365-customer-insights"></a>Xử lý xóa dữ liệu trong Dynamics 365 Customer Insights

1. Dữ liệu sẽ bị xóa (phân vùng dữ liệu và ảnh chụp nhanh dữ liệu) nếu phân vùng dữ liệu và ảnh chụp nhanh dữ liệu không hoạt động trong hơn 30 ngày, có nghĩa là chúng đã được thay thế bằng phân vùng dữ liệu mới và ảnh chụp nhanh thông qua việc làm mới nguồn dữ liệu.
2. Không phải tất cả dữ liệu và ảnh chụp nhanh đều bị xóa. Theo định nghĩa, phân vùng dữ liệu và ảnh chụp nhanh dữ liệu gần đây nhất đang hoạt động vì chúng được sử dụng trong Thông tin chi tiết về khách hàng. Đối với dữ liệu gần đây nhất, không quan trọng nếu các nguồn dữ liệu không được làm mới trong vòng 30 ngày qua.

[!INCLUDE [footer-include](includes/footer-banner.md)]
