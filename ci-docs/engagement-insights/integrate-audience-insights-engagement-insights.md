---
title: Tạo mối liên kết giữa thông tin chi tiết về đối tượng và thông tin chi tiết về mức độ tương tác
description: Tạo liên kết hoạt động giữa thông tin chi tiết về đối tượng và thông tin chi tiết về mức độ tương tác để cho phép chia sẻ dữ liệu theo hai chiều.
ms.date: 09/08/2021
ms.service: customer-insights
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 8d93a49a29c29103e189a6d4a42294c18dc28abd
ms.sourcegitcommit: f1e3cc51ea4cf68210eaf0210ad6e14b15ac4fe8
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 09/27/2021
ms.locfileid: "7559044"
---
# <a name="create-a-link-between-audience-insights-and-engagement-insights"></a>Tạo mối liên kết giữa thông tin chi tiết về đối tượng và thông tin chi tiết về mức độ tương tác

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Việc tích hợp giữa thông tin chi tiết về mức độ tương tác và thông tin chi tiết về đối tượng liên kết các môi trường từ cả hai khả năng và cho phép chia sẻ dữ liệu hai chiều.

Sử dụng hồ sơ và phân khúc hợp nhất từ thông tin chi tiết về đối tượng để có thêm tùy chọn phân tích trong thông tin chi tiết về mức độ tương tác. Xuất các sự kiện có giá trị kinh doanh cao từ thông tin chi tiết về mức độ tương tác. Sử dụng các sự kiện này để thêm dữ liệu vào hồ sơ hợp nhất trong thông tin chi tiết về đối tượng.

## <a name="prerequisites"></a>Điều kiện tiên quyết

- Hồ sơ thông tin chi tiết về đối tượng phải được lưu trữ trong tài khoản Azure Data Lake Storage mà bạn sở hữu hoặc trong một kho dữ liệu được quản lý [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro.md). 
- Môi trường thông tin chi tiết về đối tượng của bạn phải có môi trường Dataverse. Và nếu môi trường đó cũng đang sử dụng Dataverse để lưu trữ dữ liệu, hãy đảm bảo rằng bạn kiểm tra tùy chọn **Bật tính năng chia sẻ dữ liệu** trong thông tin chi tiết về đối tượng. Để biết thêm thông tin: hãy xem [Tạo và đặt cấu hình môi trường trả phí trong thông tin chi tiết về đối tượng](../audience-insights/get-started-paid.md).
- Bạn cần quyền của quản trị viên cho cả môi trường thông tin chi tiết về mức độ tương tác và thông tin chi tiết về đối tượng.
- Các môi trường liên kết phải trong cùng một vùng địa lý.

> [!NOTE]
> - Nếu đăng ký thông tin chi tiết về đối tượng của bạn là bản dùng thử, sử dụng kho dữ liệu được quản lý nội bộ về thông tin chi tiết về đối tượng, hãy liên hệ [pirequest@microsoft.com](mailto:pirequest@microsoft.com) để được hỗ trợ. 
> - Nếu môi trường thông tin chi tiết về đối tượng của bạn sử dụng Azure Data Lake Storage để lưu trữ dữ liệu, bạn cần thêm tên dịch vụ chính Azure thông tin chi tiết về mức độ tương tác vào tài khoản lưu trữ của mình. Để biết chi tiết, hãy truy cập [Kết nối với một tài khoản Azure Data Lake Storage bằng tên dịch vụ chính Azure để có thông tin chi tiết về đối tượng](../audience-insights/connect-service-principal.md). 


## <a name="create-an-environment-link"></a>Tạo liên kết môi trường

Bạn có thể tạo liên kết môi trường bằng cách cập nhật cài đặt **Quản trị viên** > **Môi trường** trong thông tin chi tiết về mức độ tương tác.

**Để thiết lập liên kết hiện hoạt giữa thông tin chi tiết về đối tượng và thông tin chi tiết về mức độ tương tác**

1. Trên trang **Quản trị viên môi trường**, chọn tab **Môi trường liên kết**.

    :::image type="content" source="media/integrate1.png" alt-text="Thiết lập môi trường.":::

1. Chọn **Thiết lập môi trường** ở góc trên bên trái hoặc ở cuối màn hình.

     :::image type="content" source="media/integrate2.png" alt-text="Chọn môi trường thông tin chi tiết về đối tượng.":::

1. Chọn môi trường thông tin chi tiết về đối tượng, sau đó chọn ***Tiếp theo** để kết thúc. Bây giờ bạn có thể chọn tính năng tùy chọn cho các môi trường được liên kết.
 
## <a name="enable-audience-insights-unified-profiles-attributes-and-segments"></a>Bật các phân khúc và thuộc tính hồ sơ hợp nhất thông tin chi tiết về đối tượng

Sau khi liên kết các môi trường, bạn có thể chọn tính năng tùy chọn cho các môi trường được liên kết. Những tính năng này cho phép các thuộc tính và phân khúc hồ sơ hợp nhất từ thông tin chi tiết về đối tượng để phân tích tương tác trên dữ liệu khách hàng.

> [!IMPORTANT]
> Để phân khúc thông tin chi tiết về đối tượng hiển thị trong thông tin chi tiết về mức độ tương tác, trước tiên bạn phải [chạy các quy trình hợp nhất và xuôi dòng](../audience-insights/merge-entities.md). Các quy trình xuôi dòng rất quan trọng vì chúng tạo ra một bảng duy nhất chuẩn bị cho các phân khúc thông tin chi tiết về đối tượng được chia sẻ với thông tin chi tiết về mức độ tương tác. (Nếu quá trình làm mới hệ thống được lên lịch, nó sẽ tự động bao gồm các quy trình xuôi dòng.)

**Để phân tích dữ liệu web trong thông tin chi tiết về mức độ tương tác**

1. Trên trang **Quản trị viên môi trường**, bật chuyển đổi **Chia sẻ dữ liệu từ thông tin chi tiết về đối tượng với thông tin chi tiết về mức độ tương tác**, sau đó chọn **Tiếp theo**.

    :::image type="content" source="media/integrate4.png" alt-text="Chọn tính năng.":::

1. Chọn các thuộc tính của cấu hình hợp nhất sẽ trở thành thứ nguyên trong thông tin chi tiết về mức độ tương tác. (Không phải tất cả các thuộc tính đều là thứ nguyên hữu ích. Ví dụ: có khả năng bạn không cần **Tên** hoặc **Họ** dưới dạng thuộc tính cho phân tích sự kiện trên trang web.)

    :::image type="content" source="media/integrate5.png" alt-text="Lựa chọn các chiều.":::

   >[!NOTE]
   > Tất cả các thuộc tính hồ sơ thông tin chi tiết về đối tượng đại diện cho số nhận dạng (chẳng hạn như **ID** và **ID thay thế**) được lọc ra khỏi các thuộc tính có sẵn và trở thành thứ nguyên trong thông tin chi tiết về mức độ tương tác.

1. Khi bạn chọn xong các thuộc tính, hãy chọn **Tiếp theo**.
1. Thêm người dùng có thể xem thứ nguyên và phân khúc hồ sơ thông tin chi tiết về đối tượng trong thông tin chi tiết về mức độ tương tác.

    :::image type="content" source="media/integrate6.png" alt-text="Quản lý quyền truy cập vào dữ liệu khách hàng.":::

   > [!IMPORTANT]
   > Nếu bạn không thêm người dùng một cách rõ ràng trong bước này, dữ liệu sẽ bị ẩn với người dùng trong thông tin chi tiết về mức độ tương tác.
   > Để phân khúc thông tin chi tiết về đối tượng hiển thị trong thông tin chi tiết về mức độ tương tác, trước tiên bạn phải [chạy các quy trình hợp nhất và xuôi dòng](../audience-insights/merge-entities.md). Các quy trình xuôi dòng rất quan trọng vì chúng tạo ra một bảng duy nhất chuẩn bị cho các phân khúc thông tin chi tiết về đối tượng được chia sẻ với thông tin chi tiết về mức độ tương tác. (Nếu quá trình làm mới hệ thống được lên lịch, nó sẽ tự động bao gồm các quy trình xuôi dòng.)

1. Xem lại lựa chọn của bạn, sau đó chọn **Kết thúc**.

    :::image type="content" source="media/integrate7.png" alt-text="Xem lại cài đặt dữ liệu khách hàng.":::

## <a name="export-refined-events-to-audience-insights"></a>Xuất các sự kiện tinh chỉnh với thông tin chi tiết về đối tượng

Sau khi tạo liên kết giữa các môi trường, bạn có thể xuất các sự kiện đã tinh chỉnh từ thông tin chi tiết về mức độ tương tác sang thông tin chi tiết về đối tượng và nhập chúng dưới dạng nguồn dữ liệu mới. 

Để biết thêm thông tin, hãy truy cập [Tích hợp dữ liệu web từ thông tin chi tiết về mức độ tương tác với thông tin chi tiết về đối tượng](../audience-insights/integrate-engagement-insights.md).

<!--
## Share engagement insights refined events with audience insights

After you create a link between environments, a new option becomes available for you to share [refined events](refined-events.md) with audience insights.

Consider the following when creating refined events for audience insights: 

- Provide a meaningful name for the refined event. It will be used as an activity name in audience insights.
- Select at least the following properties to create an activity in audience insights: 
    - Signal.Action.Name indicates the activity details.
    - Signal.User.Id maps with the customer ID.
    - Signal.View.Uri is a web address as a basis for segments or measures.
    - Signal.Export.Id is a primary key for events.
    - Signal.Timestamp determines the date and time for the activity.

To share refined events:

1. From the engagement insights menu, select **Data** and then select the **Events** tab.
2. On the **Action** menu, select **Share as activity**.

    :::image type="content" source="media/integrate8.png" alt-text="Data shared events settings.":::

3. You can view and stop actively shared events on the **Export and Sharing** tab.
4. -- per Michael K, we need a mock here (Mukesh needs to update to reflect what happens in AUI once a user shares a refined event (i.e. no longer AUI, data wrangler needs to go discover data in the storage, the shared event is available as a DS and entity, correct?)

### Attach refined events shared as activities to unified profiles in audience insights

You can bring customer web activity data from engagement insights into audience insights. In addition to transactional, demographic, or behavioral data, you can view activities on the web in unified customer profiles. You can then use these profiles to get insights such as segments, measures, and predictions for audience activation.

Follow the steps in [data unification](../audience-insights/data-unification.md) to map, match, and merge website authentication information to unified profiles in audience insights.

You can also share refined events that are now available in audience insights, identified as data sources and entities. 

Next, you can relate event data from engagement insights as unified activities in customer profiles.

### Relate refined event data as an activity of a customer profile

After unifying the data, you can configure the activity for the customer profile. For more information, go to [Customer activities](../audience-insights/activities.md).

:::image type="content" source="media/web-event-activity.png" alt-text="Activities page with expanded Edit activity pane.":::

Next, configure the new activity by using mapping elements: 

- **Primary Key**: Signal.Export.Id, a unique ID that is available for every event record in engagement insights. This property is automatically generated.

- **Timestamp**: Signal.Timestamp in the event property.

- **Event**: Signal.Name, the event name that you want to track.

- **Web address**: Signal.View.Uri that refers to the URI of the page that created the event.

- **Details**: Signal.Action.Name to represent the information to associate with the event. The selected property in this case indicates that the event is for email promotion.

- **Activity type**: In this example, we choose the existing activity type WebLog. This selection is a useful filter option to run prediction models or create segments based on this activity type.

- **Set up relationship**: This important setting ties the activity to existing customer profiles. **Signal.User.Id** is the identifier configured in the SDK to be collected. It relates to the user ID in other data sources that are configured in audience insights. 

This example configures the relationship between Signal.User.Id and RetailCustomers:CustomerRetailId, which is the primary key that was identified in the map step of the data unification process.

After processing the activities, you can review customer records and open a customer card to see activities from engagement insights in the timeline. 

> [!TIP]
> To find a customer ID that has an engagement insights activity, go to **Entities** and preview the data for the UnifiedActivity entity. **ActivityTypeDisplay = WebLog** contains the engagement insights activity configured in the preceding example. Copy the customer ID for one of those records and search<!--note from editor: Edit okay? I couldn't quite follow this.-- > for that ID on the **Customers** page.

--> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
