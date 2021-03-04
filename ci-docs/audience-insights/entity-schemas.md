---
title: Lược đồ thực thể Customer Insights trong Common Data Model
description: Làm việc với các thực thể trong Common Data Model.
ms.date: 04/17/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 9e7a6e944d37d25f4c25846644278b39b3ddd08e
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269310"
---
# <a name="entity-schemas-in-common-data-model"></a>Lược đồ thực thể trong Common Data Model

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

[Common Data Model](https://docs.microsoft.com/common-data-model/) là một thông số khai báo, đồng thời là định nghĩa của các thực thể tiêu chuẩn, đại diện cho những khái niệm và hoạt động thông dụng trên các ứng dụng năng suất và kinh doanh. Mô hình này cũng mở rộng cho cả dữ liệu phân tích và dữ liệu quan sát. Common Data Model cung cấp các thực thể kinh doanh rõ ràng, theo cấu trúc và có thể mở rộng—chẳng hạn như Tài khoản, Đơn vị kinh doanh, Trường hợp, Người liên hệ, Khách hàng tiềm năng, Cơ hội và Sản phẩm—cũng như các hình thức tương tác với đối tác, người lao động và khách hàng— chẳng hạn như các thỏa thuận ở cấp độ dịch vụ và các hoạt động. Bất cứ ai cũng có thể xây dựng và mở rộng định nghĩa Common Data Model để nắm bắt thêm các ý tưởng kinh doanh cụ thể.

Đây là mô hình dữ liệu chung cung cấp định nghĩa thống nhất về dữ liệu, nhờ đó cho phép các ứng dụng và trình tích hợp dữ liệu dễ dàng cộng tác hơn. Common Data Model bao gồm một hệ thống siêu dữ liệu phong phú với các thực thể, mối quan hệ, cấp bậc, xu hướng và nhiều dữ liệu tiêu chuẩn khác. Mô hình này bắt nguồn từ ứng dụng Dynamics 365 và là nguồn mở trên GitHub với hơn 260 thực thể tiêu chuẩn. Một hệ thống rộng lớn gồm các đối tác nội bộ lẫn bên ngoài sẽ đóng góp các khái niệm cụ thể theo ngành cho Common Data Model.

Ngày nay, nhiều hệ thống và nền tảng đã áp dụng Common Data Model, trong đó có các luồng dữ liệu Power BI và các dịch vụ dữ liệu của Azure. Mô hình này cũng đã được hỗ trợ trong Common Data Service, Dynamics 365, Power Apps, Power BI, và sắp tới là các dịch vụ dữ liệu của Azure, trực tiếp đóng góp giá trị vào [Sáng kiến dữ liệu mở](https://www.microsoft.com/open-data-initiative).

## <a name="customer-insights-entity-schemas"></a>Lược đồ thực thể Customer Insights

Để mang đến cái nhìn toàn cảnh về khách hàng cũng như đưa các mô hình Customer Insights vào sử dụng trong Common Data Model cho khả năng mở rộng, chúng tôi đã phát hành lược đồ thực thể sau đây:

| Thực thể | Mô tả |
|---------|---------|
|[CustomerActivity](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customeractivity) | Hoạt động được thực hiện bởi một người dùng có giá trị quan sát đối với doanh nghiệp. |
|[CustomerProfile](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile) | Cá nhân hoặc tổ chức đã thực hiện hoặc có tiềm năng tham gia vào các hoạt động kinh doanh. |
|[Định nghĩa số liệu đo lường](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/measuredefinition) | Cách xác định KPI được phân chia theo 0 hoặc nhiều chiều (chẳng hạn như Số người dùng hoạt động hàng tháng, Tổng chi tiêu của khách hàng, Chi phí sở hữu khách hàng bình quân) |
|[Segment](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segment) | Xác định một nhóm gồm các thành viên với đặc điểm chung. |
|[SegmentMembership](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segmentmembership) | Thành viên tham gia vào một phân đoan nhất định. |

Để biết thêm thông tin, hãy xem tài liệu về [Lược đồ thực thể Customer Insights trong Common Data Model](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/overview).

## <a name="view-entities-using-the-common-data-model-entity-navigator"></a>Xem các thực thể bằng Bộ điều hướng thực thể Common Data Model

Bạn có thể xem các thực thể trong [Bộ điều hướng thực thể Common Data Model](https://microsoft.github.io/CDM/). Chọn nút **Tải từ GitHub!** rồi điều hướng đến **foundationCommon** > **crmCommon** > **solutions** > **customerInsights**. Tại đây, bạn sẽ thấy danh sách các thực thể Customer Insights và định nghĩa của chúng.
> [!div class="mx-imgBorder"]
> ![Bộ điều hướng thực thể CDM hiển thị thực thể CustomerActivity](media/CDM-entity-navigator.png "Bộ điều hướng thực thể CDM hiển thị thực thể CustomerActivity")


[!INCLUDE[footer-include](../includes/footer-banner.md)]