---
title: Yêu cầu theo Quyền của chủ thể dữ liệu (DSR) phù hợp với GDPR | Microsoft Docs
description: Trả lời các yêu cầu về chủ đề dữ liệu cho khả năng thông tin chi tiết về đối tượng Dynamics 365 Customer Insights.
ms.date: 08/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: e095eb4f8e194f314d7d6baf6fa6a7a319319d2a
ms.sourcegitcommit: 1946d7af0bd2ca216885bec3c5c95009996d9a28
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 02/25/2022
ms.locfileid: "8350295"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Yêu cầu theo Quyền của chủ thể dữ liệu (DSR) phù hợp với GDPR

Quy định Chung về Bảo vệ Dữ liệu (GDPR) của Liên minh Châu Âu đã có hiệu lực kể từ ngày 25 tháng 5 năm 2018. Quy định này cung cấp các quyền quan trọng cho các cá nhân liên quan đến dữ liệu của họ. GDPR là quy định về việc bảo vệ và cho phép các quyền riêng tư của các cá nhân. Bạn có thể đọc thêm về cam kết của Microsoft về vấn đề bảo mật và tuân thủ tại [Trung tâm Tin cậy của Microsoft](https://www.microsoft.com/trust-center).

Chúng tôi cam kết giúp khách hàng của mình đáp ứng các yêu cầu về GDPR của họ. Chức năng này bao gồm quyền xóa và xuất dữ liệu có chứa thông tin cá nhân như ID người dùng, số điện thoại và địa chỉ email. Quản trị viên có thể thực hiện các yêu cầu của người dùng để xóa hoặc xuất dữ liệu cá nhân.

## <a name="audience-insights"></a>Thông tin chi tiết về đối tượng

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a>Trả lời yêu cầu xóa chủ đề dữ liệu GDPR cho khả năng thông tin chi tiết về đối tượng Dynamics 365 Customer Insights

"Quyền xóa" dữ liệu cá nhân khỏi dữ liệu khách hàng của tổ chức là sự bảo vệ chính trong Quy định Chung về Bảo vệ Dữ liệu (GDPR). Việc xóa dữ liệu cá nhân bao gồm xóa tất cả dữ liệu cá nhân và nhật ký do hệ thống tạo, ngoại trừ thông tin nhật ký kiểm tra.

#### <a name="manage-data-subject-delete-requests"></a>Quản lý yêu cầu xóa của chủ thể dữ liệu

Thông tin chi tiết về đối tượng cung cấp những trải nghiệm trong sản phẩm sau để xóa dữ liệu cá nhân cho một khách hàng hoặc người dùng cụ thể:

- **Quản lý yêu cầu xóa đối với dữ liệu khách hàng**: Dữ liệu khách hàng trong Customer Insights được nhập từ các nguồn dữ liệu ban đầu bên ngoài Customer Insights. Tất cả yêu cầu xóa theo GDPR phải được thực hiện trong nguồn dữ liệu gốc.
- **Quản lý yêu cầu xóa đối với dữ liệu người dùng Customer Insights**: Dữ liệu cho người dùng được tạo bởi Customer Insights. Tất cả yêu cầu xóa GDPR phải được thực hiện trong Customer Insights.

##### <a name="manage-requests-to-delete-customer-data"></a>Quản lý yêu cầu xóa dữ liệu khách hàng

Quản trị viên Customer Insights có thể làm theo các bước sau để xóa dữ liệu khách hàng đã bị xóa trong nguồn dữ liệu:

1. Đăng nhập vào Dynamics 365 Customer Insights.
2. Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Dữ liệu** > **Nguồn dữ liệu**
3. Đối với từng nguồn dữ liệu trong danh sách chứa dữ liệu khách hàng đã xóa:
   1. Chọn (...) rồi chọn **Làm mới**.
   2. Kiểm tra trạng thái nguồn dữ liệu trong **Trạng thái**. Một dấu kiểm có nghĩa là làm mới đã thành công. Một tam giác cảnh báo có nghĩa là đã có vấn đề. Nếu hình tam giác cảnh báo được hiển thị, hãy liên hệ với D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![Xử lý yêu cầu xóa dữ liệu khách hàng theo GDPR.](audience-insights/media/gdpr-data-sources.png "Xử lý yêu cầu xóa dữ liệu khách hàng theo GDPR")

##### <a name="manage-delete-requests-for-user-data"></a>Quản lý yêu cầu xóa dữ liệu người dùng

Quản trị viên Customer Insights có thể làm theo các bước sau để xóa dữ liệu người dùng Customer Insights:

1. Đăng nhập vào Dynamics 365 Customer Insights.
2. Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Quản trị** > **Quyền**.
3. Chọn hộp kiểm tương ứng với người dùng bạn muốn xóa.
4. Chọn **Loại bỏ**.

### <a name="responding-to-gdpr-data-subject-export-requests"></a>Trả lời yêu cầu xuất của chủ thể dữ liệu theo GDPR

Là một phần trong cam kết của chúng tôi để hợp tác với bạn trên hành trình của bạn theo Quy định chung về bảo vệ dữ liệu (GDPR), chúng tôi đã phát triển tài liệu để giúp bạn chuẩn bị. Tài liệu này mô tả các bước bạn có thể thực hiện ngay hôm nay để hỗ trợ tuân thủ GDPR khi sử dụng thông tin chi tiết về đối tượng.

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

## <a name="consent-management-preview"></a>Quản lý sự đồng ý (xem trước)

Khả năng quản lý sự đồng ý không trực tiếp thu thập dữ liệu người dùng. Nó chỉ nhập và xử lý dữ liệu về sự đồng ý do người dùng cung cấp trong các ứng dụng khác.

Để xóa dữ liệu về sự đồng ý về những người dùng cụ thể, hãy xóa dữ liệu đó trong các nguồn dữ liệu được nhập vào khả năng quản lý sự đồng ý. Sau khi làm mới nguồn dữ liệu, dữ liệu đã xóa cũng sẽ bị xóa trong Trung tâm đồng ý. Các ứng dụng sử dụng pháp nhân đồng ý cũng sẽ xóa dữ liệu đã bị xóa trên nguồn sau [Làm tươi](audience-insights/system.md#refresh-processes). Chúng tôi khuyên bạn nên nhanh chóng làm mới nguồn dữ liệu sau khi phản hồi yêu cầu chủ thể dữ liệu để xóa dữ liệu của người dùng khỏi tất cả các quy trình và ứng dụng khác.


<!-- ## Engagement insights (preview)

### Deleting and exporting event data containing end user identifiable information

The following sections describe how to delete and export event data that might contain personal data.

To delete or export data:

1. Tag event properties that contain data with personal information.
2. Delete or export data associated with specific values (for example: a specified user ID).

#### Tag and update event properties

Personal data is tagged on an event property level. First, tag the properties being considered for deletion or export.

To tag an event property as containing personal information, follow these steps:

1. Open the workspace containing the event.

1. Go to **Data** > **Events** to see the list of events in the selected workspace.
  
1. Select the event you want to tag.

1. Select **Edit properties** to open the pane listing all properties of the selected event.
     
1. Select **...** and then choose **Edit** to reach the **Update property** dialog.

   ![Edit event.](engagement-insights/media/edit-event.png "Edit event")

1. In the **Update Property** window, choose **...** in the upper right corner, and then choose the **Contains EUII** box. Choose **Update** to save your changes.

   ![Save your changes.](engagement-insights/media/update-property.png "Save your changes")

   > [!NOTE]
   > Every time the event schema changes or you create a new event, it's recommended that you evaluate the associated event properties and tag or untag them as containing personal data, if necessary.

#### Delete or export tagged event data

If all event properties have been tagged appropriately as described in the previous step, an environment admin can issue a deletion request against the tagged event data.

To manage EUII deletion or export requests

1. Go to **Admin** > **Environment** > **Settings**.

1. In the **Manage end user identifiable information (EUII)** section, select **Manage EUII**.

##### Deletion

For deletion, you can enter a list of comma-separated user IDs in the **Delete end user identifiable information (EUII)** section. These IDs will then be compared with all tagged event properties of all projects in the current environment via exact string matching. 

If a property value matches one of the provided IDs, the associated event will be permanently deleted. Due to the irreversibility of this action, you must confirm the deletion after selecting **Delete**.

##### Export

The export process is identical to the deletion process when it comes to defining event property values in the **Export end user identifiable information (EUII)** section. Additionally, you'll need to provide an **Azure blob storage URL** to specify the export destination. The Azure Blob URL must include a [Shared Access Signature (SAS)](/azure/storage/common/storage-sas-overview).

After selecting **Export**, all events of the current team that contain matching tagged properties will be exported in CSV format to the export destination.

### Good practices

* Try to avoid sending any events that contain personal data.
* If you need to send events containing EUII data, limit the number of events and event properties that contain EUII data. Ideally, limit yourself to one such event.
* Make sure that as few people as possible have access to the sent personal data.
* For events containing personal data, make sure that you set one property to emit a unique identifier that can easily be linked to a specific user (for example, a user ID). This makes it easier to segregate data and to export or delete the right data.
* Only tag one property per event as containing personal data. Ideally one that only contains a unique identifier.
* Do not tag properties containing verbose values (for example, an entire request body). Engagement insights capability uses exact string matching when deciding which events to delete or export. -->

[!INCLUDE[footer-include](includes/footer-banner.md)]