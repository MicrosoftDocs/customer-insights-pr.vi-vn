---
title: Nhập dữ liệu trong thời gian thực (xem trước)
description: Thông tin chung về khả năng thời gian thực trong Thông tin chi tiết về khách hàng.
ms.date: 10/27/2020
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
searchScope:
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: 403cc9dbd3bddcf67f59b5cb0be936af4d268fc2
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195684"
---
# <a name="real-time-data-ingestion-preview"></a>Nhập dữ liệu trong thời gian thực (xem trước)

Chức năng gần thời gian thực cho phép bạn xem, trong vài giây, các tương tác mới nhất mà khách hàng của bạn đã thực hiện với các sản phẩm hoặc dịch vụ của bạn.

[Làm mới theo lịch trình](system.md#schedule-tab) bao gồm số lượng lớn các bản ghi và một số hoạt động phức tạp. Đầu tiên, dữ liệu được lấy từ nguồn dữ liệu. Tiếp theo, dữ liệu được hợp nhất, và sau đó được làm giàu với thông tin bổ sung. Mỗi lần chạy của quá trình này có thể mất vài phút đến vài giờ.

Chức năng thời gian thực cung cấp dữ liệu ngay lập tức để sử dụng, cho đến khi quá trình làm mới theo lịch trình tiếp theo kéo dữ liệu này từ nguồn dữ liệu.

Các cập nhật trong thời gian thực có thời gian hết hạn mà sau đó chúng không còn ghi đè giá trị từ nguồn dữ liệu:

- Cập nhật hồ sơ sẽ được giữ trong bốn giờ
- Các hoạt động sẽ được giữ trong 30 ngày

Các giá trị này là các tham số gọi API mà bạn có thể thay đổi. Các giá trị này nhằm đảm bảo rằng dữ liệu nguồn vẫn là nguồn sự thật của bạn. Nếu bạn muốn các cập nhật trong thời gian thực được đưa vào lâu hơn, bạn cần thêm chúng vào nguồn dữ liệu để chúng được kéo trong lần làm mới theo lịch trình tiếp theo.

## <a name="real-time-update-of-the-unified-customer-profile-fields"></a>Cập nhật theo thời gian thực của các trường hồ sơ khách hàng hợp nhất

Hồ sơ cập nhật sẽ hiển thị trong chế độ xem thẻ khách hàng hoặc bất kỳ hình ảnh trực quan nào khác, trong vòng vài giây.

Bởi vì các hoạt động trong thời gian thực diễn ra sau khi quá hợp nhất dữ liệu đã xảy ra, các hoạt động này chỉ áp dụng cho hồ sơ khách hàng hợp nhất. Do đó, các thay đổi hồ sơ theo thời gian thực sẽ không cập nhật các biện pháp, tư cách thành viên phân đoạn hoặc làm phong phú.

### <a name="limitations"></a>Giới hạn

- Có thể cập nhật nhưng không tạo hoặc xóa hồ sơ khách hàng.
- Tại thời điểm này, không xuất được thông tin cập nhật trong thời gian thực sang các hệ thống bên ngoài, như Power BI.

## <a name="real-time-creation-of-activities"></a>Tạo hoạt động theo thời gian thực

API thời gian thực cho phép bạn xuất bản một hoạt động mới từ hệ thống nguồn của bạn (một bản ghi nguồn riêng lẻ) lên một hồ sơ khách hàng hợp nhất. Hoạt động mới sẽ có sẵn dưới dạng một hoạt động hợp nhất trong dòng thời gian của hồ sơ khách hàng hợp nhất đó trong vài giây. Bạn có thể xem dòng thời gian trong chế độ xem thẻ khách hàng hoặc bất kỳ tích hợp dòng thời gian nào khác mà bạn đã định cấu hình.

> [!NOTE]
>
> - Hoạt động không thể thay đổi được. Hoạt động không thay đổi sau khi được tạo.
> - Hiện tại, các phân đoạn và biện pháp sẽ không cập nhật dựa trên hoạt động mới.
> - Các hoạt động chỉ được thêm thông qua API thời gian thực không phải là một phần của hoạt động xuất và sẽ không hiển thị trong PowerBI.

Có hai cách để kết nối với API thời gian thực:

- [gián tiếp](#connect-via-the-dynamics-365-customer-insights-connector), sử dụng [Dynamics 365 Customer Insights trình kết nối](/connectors/customerinsights/)
- [trực tiếp](#connect-directly-to-the-real-time-api), có mã

Cả hai cách đều có chung các điều kiện tiên quyết sau:

- Môi trường Customer Insights
- Hồ sơ khách hàng hợp nhất
- Các hoạt động đặt đặt cấu hình và chạy
- Quyền của Cộng tác viên hoặc Quản trị viên để xác thực tài khoản của bạn

## <a name="connect-via-the-dynamics-365-customer-insights-connector"></a>Kết nối thông qua trình kết nối Dynamics 365 Customer Insights

API thời gian thực có thể nhập dữ liệu từ một trình kết nối Power Platform chuyên dụng, trình kết nối [Dynamics 365 Customer Insights ](/connectors/customerinsights/) mà không cần phải viết và triển khai bất kỳ mã nào.    
Trình kết nối có thể thực hiện các hành động tương tự trong thời gian thực như API. Bạn cần có giấy phép hợp lệ cho các kết nối cao cấp. Để biết thêm thông tin, hãy xem Câu hỏi thường gặp về cấp phép [Power Apps và Power Automate](/power-platform/admin/powerapps-flow-licensing-faq).

- Power Platform [Power Apps và/hoặc Power Automate](/connectors/)
- Ứng dụng Logic [Azure](/azure/connectors/apis-list)

Để biết chi tiết về việc tạo dòng, hãy xem tài liệu [Power Automate](/power-automate/).

## <a name="connect-directly-to-the-real-time-api"></a>Kết nối trực tiếp với API thời gian thực

Bạn có thể sử dụng các khả năng thời gian thực bằng cách xây dựng quy trình của riêng mình và kết nối trực tiếp với API thời gian thực.    
Bạn có thể đăng một hoạt động ở định dạng của hệ thống nguồn của bạn hoặc ở định dạng UnifiedActivity. Lấy định dạng bằng cách thực hiện cuộc gọi API tới /api/instances/{instanceId}/manage/entities/UnifiedActivity.

Thông tin chi tiết về API này, bao gồm các thông số và phản hồi, có thể được tìm thấy trong phần **EntityData** trên [Tham chiếu API Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Để biết thêm thông tin, hãy xem [Làm việc với API Customer Insights](apis.md).

## <a name="understand-your-real-time-usage-with-telemetry"></a>Tìm hiểu cách sử dụng trong thời gian thực với phương pháp đo từ xa

Xem tổng quan về khối lượng yêu cầu tới API thời gian thực và thông tin về các vấn đề mà hệ thống có thể gặp phải. Bạn có thể [truy cập máy đo từ xa thời gian thực](system.md#api-usage-tab). 


[!INCLUDE [footer-include](includes/footer-banner.md)]
