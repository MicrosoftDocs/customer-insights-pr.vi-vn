---
title: Bắt đầu với chức năng thông tin chuyên sâu về tương tác
description: Tổng quan về các nguồn lực trợ giúp để bắt đầu nhanh chóng.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 12/21/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 5ee1567cea834670a16aaa3253912b7957ce26b3
ms.sourcegitcommit: 86739a3f238162fc96837270b5d184e648fab15c
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 08/20/2021
ms.locfileid: "7405384"
---
# <a name="get-started-with-dynamics-365-customer-insights-engagement-insights-capability-public-preview"></a>Bắt đầu với chức năng thông tin chuyên sâu về tương tác của Dynamics 365 Customer Insights (bản xem trước công khai)

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Chức năng thông tin chuyên sâu về tương tác cho phép bạn thu thập và đo lường hành vi của khách hàng trên trang web của mình. Chức năng này tích hợp với chức năng thông tin chuyên sâu về đối tượng để bạn có thể xem các phân tích hành vi theo thời gian thực cùng với các báo cáo hồ sơ khách hàng. Các liên kết trong bài viết này giúp bạn nhanh chóng đặt cấu hình và thiết lập môi trường của mình.

## <a name="step-1-review-prerequisites"></a>Bước 1: Xem lại các điều kiện tiên quyết

Trước tiên, bạn phải có một tài khoản người dùng Microsoft Azure Active Directory đang hoạt động. Sau đó, hãy đọc các bài viết sau trước khi thiết lập không gian làm việc của thông tin chuyên sâu về tương tác.

- Xem lại và đồng ý với [các Điều khoản dịch vụ](terms-of-service.md) của Microsoft.  
- Đọc bài viết [Quản lý cookie và sự đồng ý của người dùng](user-consent-storage.md). Sau khi xem lại bài viết này, hãy đánh giá xem bạn có cần cập nhật thông báo về sự đồng ý của người dùng hay không. Nếu trước đây không có cookie "không cần thiết", bạn có thể cần cập nhật chính sách trang web của mình.
- Xem lại [bảng thuật ngữ](glossary.md) để được giới thiệu nhanh về các thuật ngữ và khái niệm chính.

## <a name="step-2-explore-engagement-insights"></a>Bước 2: Khám phá thông tin chuyên sâu về tương tác

Trong lần đầu tiên truy cập thông tin chuyên sâu về tương tác, bạn có thể đặt cấu hình cài đặt, xem lại chính sách và khám phá sản phẩm.

1. Đăng nhập vào [cổng thông tin về chức năng thông tin chuyên sâu về tương tác](https://pi.dynamics.com) bằng tài khoản người dùng Microsoft Azure Active Directory của bạn. (Đây có thể là tài khoản trường học hoặc cơ quan của bạn.)

1. Chọn khu vực của bạn và sử dụng hộp kiểm để cho biết bạn có muốn chọn tham gia nhận các bản cập nhật và ưu đãi qua email hay không.

1. Xem lại **Điều khoản sử dụng thông tin chuyên sâu về tương tác (xem trước)** và **Tuyên bố về quyền riêng tư** rồi chọn **Khám phá bản demo** để chấp nhận các điều khoản.

1. Khám phá sản phẩm bằng cách sử dụng một bộ dữ liệu mẫu.

##  <a name="step-3-set-up-a-workspace-and-add-code-to-your-website"></a>Bước 3: Thiết lập không gian làm việc và thêm mã vào trang web của bạn

Không gian làm việc là nơi bạn có thể xem hoạt động của người dùng trong thời gian thực, lưu trữ và quản lý các báo cáo. Thêm mã vào trang web của bạn để bắt đầu thu thập *sự kiện*, dữ liệu hoạt động đến từ người dùng.

1. [Tạo không gian làm việc](create-workspace.md) và thêm thành viên.

1. [Thêm mã vào trang web](instrument-website.md) hoặc [ứng dụng dành cho thiết bị di động](developer-resources.md#capture-events-from-mobile-apps) để xem hoạt động của người dùng đến không gian làm việc của bạn.

1. Xem [báo cáo theo thời gian thực](view-reports.md) hiển thị người dùng đang hoạt động theo trình duyệt, thiết bị, hệ điều hành, vị trí và ngôn ngữ. Bạn cũng có thể tạo [báo cáo tùy chỉnh](custom-reports.md) để tạo hình ảnh trực quan của riêng bạn.
    
## <a name="step-4-export-data-to-other-channels"></a>Bước 4: Xuất dữ liệu sang các kênh khác

Bạn có thể tạo *sự kiện tinh chỉnh* (chế độ xem ảo) trong dữ liệu phân tích trang web của mình. Sau đó lọc và xuất dữ liệu sang Azure Data Lake Storage. Bạn có thể nhập dữ liệu đã xuất dưới dạng nguồn dữ liệu. Để biết thêm thông tin: hãy xem [Tạo mối liên kết giữa thông tin chi tiết về đối tượng và thông tin chi tiết về mức độ tương tác](integrate-audience-insights-engagement-insights.md).

1. [Tạo các sự kiện tinh chỉnh](refined-events.md) để xuất.

1. [Xuất dữ liệu](export-events.md) sang Data Lake Storage.

1. Tìm hiểu cách [xóa và xuất dữ liệu sự kiện có chứa thông tin cá nhân](delete-export-personal-data.md).
 
## <a name="step-5-stay-connected"></a>Bước 5: Duy trì kết nối

Chúng tôi đánh giá cao sự tham gia tích cực của bạn và dự định xem xét tất cả các phản hồi liên quan trong việc phát triển các bản phát hành trong tương lai. Chia sẻ phản hồi của bạn và báo cáo sự cố bằng một trong các kênh sau:
- [Cộng đồng](https://go.microsoft.com/fwlink/?linkid=2141648)
- [Đóng góp ý kiến phản hồi](https://go.microsoft.com/fwlink/?linkid=2143222)
- [Yêu cầu hỗ trợ](https://go.microsoft.com/fwlink/?linkid=2145734) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
