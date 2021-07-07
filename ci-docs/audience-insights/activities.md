---
title: Hoạt động của khách hàng
description: Xác định các hoạt động của khách hàng và xem chúng trong dòng thời gian của khách hàng.
ms.date: 04/07/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: 342aeb33f652d5d60cd25e13969766954bf56370
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304952"
---
# <a name="customer-activities"></a><span data-ttu-id="5d6a6-103">Hoạt động của khách hàng</span><span class="sxs-lookup"><span data-stu-id="5d6a6-103">Customer activities</span></span>

<span data-ttu-id="5d6a6-104">Kết hợp các hoạt động của khách hàng từ [những nguồn dữ liệu khác nhau](data-sources.md) trong Dynamics 365 Customer Insights để tạo dòng thời gian liệt kê các hoạt động theo thứ tự thời gian.</span><span class="sxs-lookup"><span data-stu-id="5d6a6-104">Combine customer activities from [various data sources](data-sources.md) in Dynamics 365 Customer Insights to create a timeline that lists the activities chronologically.</span></span> <span data-ttu-id="5d6a6-105">Bao gồm dòng thời gian trong các ứng dụng Dynamics 365 với giải pháp [phần bổ trợ Thẻ khách hàng](customer-card-add-in.md) hoặc trong một bảng điều khiển Power BI.</span><span class="sxs-lookup"><span data-stu-id="5d6a6-105">Include the timeline in Dynamics 365 apps with the [Customer Card add-in](customer-card-add-in.md) solution, or in a Power BI dashboard.</span></span>

## <a name="define-an-activity"></a><span data-ttu-id="5d6a6-106">Xác định hoạt động</span><span class="sxs-lookup"><span data-stu-id="5d6a6-106">Define an activity</span></span>

<span data-ttu-id="5d6a6-107">Nguồn dữ liệu của bạn có thể bao gồm các thực thể có dữ liệu giao dịch và hoạt động từ nhiều nguồn dữ liệu.</span><span class="sxs-lookup"><span data-stu-id="5d6a6-107">Your data sources can include entities with transactional and activity data from multiple data sources.</span></span> <span data-ttu-id="5d6a6-108">Xác định các thực thể này và chọn các hoạt động bạn muốn xem trên dòng thời gian của khách hàng.</span><span class="sxs-lookup"><span data-stu-id="5d6a6-108">Identify these entities and select the activities you want to view on the customer's timeline.</span></span> <span data-ttu-id="5d6a6-109">Chọn thực thể bao gồm hoạt động mục tiêu hoặc hoạt động của bạn.</span><span class="sxs-lookup"><span data-stu-id="5d6a6-109">Choose the entity that includes your target activity or activities.</span></span>

> [!NOTE]
> <span data-ttu-id="5d6a6-110">Một thực thể phải có ít nhất một thuộc tính loại **Ngày** để được đưa vào dòng thời gian của khách hàng và bạn không thể thêm các thực thể mà không có trường **Ngày**.</span><span class="sxs-lookup"><span data-stu-id="5d6a6-110">An entity must have at least one attribute of type **Date** to be included in a customer timeline and you can't add entities without **Date** fields.</span></span> <span data-ttu-id="5d6a6-111">Kiểm soát **Thêm hoạt động** bị vô hiệu hóa nếu không tìm thấy thực thể đó.</span><span class="sxs-lookup"><span data-stu-id="5d6a6-111">The **Add activity** control is disabled if no such entity is found.</span></span>

1. <span data-ttu-id="5d6a6-112">Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Dữ liệu** > **Hoạt động**.</span><span class="sxs-lookup"><span data-stu-id="5d6a6-112">In audience insights, go to **Data** > **Activities**.</span></span>

1. <span data-ttu-id="5d6a6-113">Chọn **Thêm hoạt động** để bắt đầu trải nghiệm có hướng dẫn cho quá trình thiết lập hoạt động.</span><span class="sxs-lookup"><span data-stu-id="5d6a6-113">Select **Add activity** to start the guided experience for the activity setup process.</span></span>

1. <span data-ttu-id="5d6a6-114">Trong bước **Dữ liệu hoạt động**, hãy đặt giá trị cho các trường sau:</span><span class="sxs-lookup"><span data-stu-id="5d6a6-114">In the **Activity data** step, set the values for the following fields:</span></span>

   - <span data-ttu-id="5d6a6-115">**Tên hoạt động**: Chọn tên cho hoạt động của bạn.</span><span class="sxs-lookup"><span data-stu-id="5d6a6-115">**Activity name**: Select a name for your activity.</span></span>
   - <span data-ttu-id="5d6a6-116">**Thực thể**: Chọn một thực thể bao gồm dữ liệu giao dịch hoặc hoạt động.</span><span class="sxs-lookup"><span data-stu-id="5d6a6-116">**Entity**: Select an entity that includes transactional or activity data.</span></span>
   - <span data-ttu-id="5d6a6-117">**Khóa chính**: Chọn trường xác định duy nhất một bản ghi.</span><span class="sxs-lookup"><span data-stu-id="5d6a6-117">**Primary key**: Select the field that uniquely identifies a record.</span></span> <span data-ttu-id="5d6a6-118">Nó không nên chứa bất kỳ giá trị trùng lặp, giá trị trống hoặc giá trị thiếu nào.</span><span class="sxs-lookup"><span data-stu-id="5d6a6-118">It shouldn't contain any duplicate values, empty values, or missing values.</span></span>

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Thiết lập dữ liệu hoạt động với tên, thực thể và khóa chính.":::

1. <span data-ttu-id="5d6a6-120">Chọn **Tiếp** để chuyển sang bước tiếp theo.</span><span class="sxs-lookup"><span data-stu-id="5d6a6-120">Select **Next** to go to the next step.</span></span>

1. <span data-ttu-id="5d6a6-121">Trong bước **Mối quan hệ**, hãy đặt cấu hình thông tin chi tiết để kết nối dữ liệu hoạt động của bạn với khách hàng tương ứng.</span><span class="sxs-lookup"><span data-stu-id="5d6a6-121">In the **Relationship** step, configure the details to connect your activity data to its corresponding customer.</span></span> <span data-ttu-id="5d6a6-122">Bước này trực quan hóa kết nối giữa các thực thể.</span><span class="sxs-lookup"><span data-stu-id="5d6a6-122">This step visualizes the connection between entities.</span></span>  

   - <span data-ttu-id="5d6a6-123">**Đầu tiên**: Trường ngoại trong thực thể hoạt động của bạn sẽ được dùng để thiết lập mối quan hệ với một thực thể khác.</span><span class="sxs-lookup"><span data-stu-id="5d6a6-123">**First**: Foreign field in your activity entity that will be used to establish a relationship with another entity.</span></span>
   - <span data-ttu-id="5d6a6-124">**Thứ hai**: Thực thể khách hàng nguồn tương ứng mà thực thể hoạt động của bạn sẽ có mối quan hệ.</span><span class="sxs-lookup"><span data-stu-id="5d6a6-124">**Second**: Corresponding source customer entity with which your activity entity will be in relationship.</span></span> <span data-ttu-id="5d6a6-125">Bạn chỉ có thể liên kết với các thực thể khách hàng nguồn được dùng trong quá trình hợp nhất dữ liệu.</span><span class="sxs-lookup"><span data-stu-id="5d6a6-125">You can only relate to source customer entities that are used in the data unification process.</span></span>
   - <span data-ttu-id="5d6a6-126">**Thứ ba** : Nếu mối quan hệ giữa thực thể hoạt động này và thực thể khách hàng nguồn được chọn đã tồn tại, thì tên mối quan hệ sẽ ở chế độ chỉ đọc.</span><span class="sxs-lookup"><span data-stu-id="5d6a6-126">**Third**: If a relationship between this activity entity and the selected source customer entity already exists, the relationship name will be in read-only mode.</span></span> <span data-ttu-id="5d6a6-127">Nếu không có mối quan hệ nào như vậy tồn tại, một mối quan hệ mới sẽ được tạo theo tên mà bạn cung cấp trong hộp này.</span><span class="sxs-lookup"><span data-stu-id="5d6a6-127">If no such relationship exists, a new relationship will be created with the name you provide in this box.</span></span>

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Xác định mối quan hệ của thực thể.":::

1. <span data-ttu-id="5d6a6-129">Chọn **Tiếp** để chuyển sang bước tiếp theo.</span><span class="sxs-lookup"><span data-stu-id="5d6a6-129">Select **Next** to go to the next step.</span></span> 

1. <span data-ttu-id="5d6a6-130">Trong bước **Hợp nhất hoạt động**, hãy chọn sự kiện hoạt động và thời gian bắt đầu hoạt động của bạn.</span><span class="sxs-lookup"><span data-stu-id="5d6a6-130">In the **Activity unification** step, choose the activity event and the start time of your activity.</span></span> 
   - <span data-ttu-id="5d6a6-131">**Trường bắt buộc**</span><span class="sxs-lookup"><span data-stu-id="5d6a6-131">**Required fields**</span></span>
      - <span data-ttu-id="5d6a6-132">**Hoạt động của sự kiện**: Trường về sự kiện cho hoạt động này.</span><span class="sxs-lookup"><span data-stu-id="5d6a6-132">**Event activity**: Field that is the event for this activity.</span></span>
      - <span data-ttu-id="5d6a6-133">**Dấu thời gian**: Trường đại diện cho thời gian bắt đầu hoạt động của bạn.</span><span class="sxs-lookup"><span data-stu-id="5d6a6-133">**Timestamp**: Field that represents the start time of your activity.</span></span>

   - <span data-ttu-id="5d6a6-134">**Trường tùy chọn**</span><span class="sxs-lookup"><span data-stu-id="5d6a6-134">**Optional fields**</span></span>
      - <span data-ttu-id="5d6a6-135">**Chi tiết bổ sung**: Trường có thông tin liên quan cho hoạt động này.</span><span class="sxs-lookup"><span data-stu-id="5d6a6-135">**Additional detail**: Field with relevant information for this activity.</span></span>
      - <span data-ttu-id="5d6a6-136">**Biểu tượng**: Biểu tượng thể hiện rõ nhất loại hoạt động này.</span><span class="sxs-lookup"><span data-stu-id="5d6a6-136">**Icon**: Icon that best represents this activity type.</span></span>
      - <span data-ttu-id="5d6a6-137">**Địa chỉ web**: Trường chứa URL có thông tin về hoạt động này.</span><span class="sxs-lookup"><span data-stu-id="5d6a6-137">**Web address**: Field containing a URL with information about this activity.</span></span> <span data-ttu-id="5d6a6-138">Ví dụ: hệ thống giao dịch lấy nguồn từ hoạt động này.</span><span class="sxs-lookup"><span data-stu-id="5d6a6-138">For example, the transactional system that sources this activity.</span></span> <span data-ttu-id="5d6a6-139">URL này có thể là bất kỳ trường nào từ nguồn dữ liệu hoặc được xây dựng làm một trường mới bằng cách chuyển đổi Power Query.</span><span class="sxs-lookup"><span data-stu-id="5d6a6-139">This URL can be any field from the data source, or it can be constructed as a new field using a Power Query transformation.</span></span> <span data-ttu-id="5d6a6-140">Dữ liệu URL sẽ được lưu trữ trong thực thể *Hoạt động đã hợp nhất*. Dữ liệu này có thể được dùng ở hạ nguồn bằng cách sử dụng [API](apis.md).</span><span class="sxs-lookup"><span data-stu-id="5d6a6-140">The URL data will be stored in the *Unified Activity* entity, which can be consumed downstream using [APIs](apis.md).</span></span>
   
   :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="Chỉ định dữ liệu hoạt động của khách hàng trong thực thể Hoạt động đã hợp nhất.":::

1. <span data-ttu-id="5d6a6-142">Chọn **Tiếp** để chuyển sang bước tiếp theo.</span><span class="sxs-lookup"><span data-stu-id="5d6a6-142">Select **Next** to move to the next step.</span></span> <span data-ttu-id="5d6a6-143">Bạn có thể chọn **Kết thúc và xem xét** để lưu hoạt động ngay bây giờ khi loại hoạt động được đặt thành **Khác**.</span><span class="sxs-lookup"><span data-stu-id="5d6a6-143">You can select **Finish and review** to save the activity now with the activity type set to **Other**.</span></span> 

1. <span data-ttu-id="5d6a6-144">Trong bước **Loại hoạt động**, hãy chọn loại hoạt động và tùy ý chọn nếu bạn muốn ánh xạ theo ngữ nghĩa một số loại hoạt động để sử dụng trong các khu vực khác của Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="5d6a6-144">In the **Activity Type** step, choose the activity type and optionally select if you want to semantically map some of the activity types for use in other areas of Customer Insights.</span></span> <span data-ttu-id="5d6a6-145">Hiện tại, *Đăng ký* và các loại hoạt động *SalesOrderLine* có thể được ánh xạ theo ngữ nghĩa sau khi bạn đồng ý ánh xạ các trường.</span><span class="sxs-lookup"><span data-stu-id="5d6a6-145">Currently, *Subscription* and *SalesOrderLine* activity types can be semantically mapped after agreeing to map the fields.</span></span> <span data-ttu-id="5d6a6-146">Nếu một loại hoạt động không phù hợp với hoạt động mới, bạn có thể chọn *Khác* hoặc *Tạo mới* cho một loại hoạt động tùy chỉnh.</span><span class="sxs-lookup"><span data-stu-id="5d6a6-146">If an activity type isn't relevant for the new activity, you can choose *Other* or *Create new* for a custom activity type.</span></span>

1. <span data-ttu-id="5d6a6-147">Chọn **Tiếp** để chuyển sang bước tiếp theo.</span><span class="sxs-lookup"><span data-stu-id="5d6a6-147">Select **Next** to move to the next step.</span></span> 

1. <span data-ttu-id="5d6a6-148">Trong bước **Xem lại**, hãy xác minh lựa chọn của bạn.</span><span class="sxs-lookup"><span data-stu-id="5d6a6-148">In the **Review** step, verify your selections.</span></span> <span data-ttu-id="5d6a6-149">Quay lại bất kỳ bước nào trước đó và cập nhật thông tin nếu cần.</span><span class="sxs-lookup"><span data-stu-id="5d6a6-149">Go back to any of the previous steps and update the information if necessary.</span></span>

   :::image type="content" source="media/Activity_Wizard5.PNG" alt-text="Xem lại các trường được chỉ định cho một hoạt động.":::
   
1. <span data-ttu-id="5d6a6-151">Chọn **Lưu hoạt động** để áp dụng các thay đổi của bạn và chọn **Xong** để quay lại **Dữ liệu** > **Hoạt động**.</span><span class="sxs-lookup"><span data-stu-id="5d6a6-151">Select **Save activity** to apply your changes and select **Done** to go back to **Data** > **Activities**.</span></span> <span data-ttu-id="5d6a6-152">Tại đây, bạn sẽ thấy những hoạt động nào được thiết lập để hiển thị trong dòng thời gian.</span><span class="sxs-lookup"><span data-stu-id="5d6a6-152">Here you see which activities are set to show in the timeline.</span></span> 

1. <span data-ttu-id="5d6a6-153">Trên trang **Hoạt động**, hãy chọn **Chạy** để xử lý hoạt động.</span><span class="sxs-lookup"><span data-stu-id="5d6a6-153">On the **Activities** page, select **Run** to process the activity.</span></span> 

> [!TIP]
> <span data-ttu-id="5d6a6-154">Có [6 loại trạng thái](system.md#status-types) cho các nhiệm vụ/quy trình.</span><span class="sxs-lookup"><span data-stu-id="5d6a6-154">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="5d6a6-155">Ngoài ra, hầu hết các quy trình [phụ thuộc vào các quá trình hạ nguồn khác](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="5d6a6-155">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="5d6a6-156">Bạn có thể chọn trạng thái của một quy trình để xem chi tiết về tiến trình của toàn bộ công việc.</span><span class="sxs-lookup"><span data-stu-id="5d6a6-156">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="5d6a6-157">Sau khi chọn **Xem chi tiết** đối với một trong các tác vụ của công việc, bạn sẽ tìm thấy thông tin bổ sung: thời gian xử lý, ngày xử lý gần nhất và tất cả các lỗi và cảnh báo liên quan đến tác vụ.</span><span class="sxs-lookup"><span data-stu-id="5d6a6-157">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>


## <a name="manage-existing-activities"></a><span data-ttu-id="5d6a6-158">Quản lý các hoạt động hiện có</span><span class="sxs-lookup"><span data-stu-id="5d6a6-158">Manage existing activities</span></span>

<span data-ttu-id="5d6a6-159">Trên **Dữ liệu** > **Hoạt động**, bạn có thể xem và quản lý tất cả các hoạt động mà mình đã lưu.</span><span class="sxs-lookup"><span data-stu-id="5d6a6-159">On **Data** > **Activities**, you can view all your saved activities, and manage them.</span></span> <span data-ttu-id="5d6a6-160">Mỗi hoạt động được thể hiện bằng một hàng cũng bao gồm thông tin chi tiết về nguồn, thực thể và loại hoạt động.</span><span class="sxs-lookup"><span data-stu-id="5d6a6-160">Each activity is represented by a row that also includes details about the source, the entity, and the activity type.</span></span>

<span data-ttu-id="5d6a6-161">Các hành động sau đây khả dụng khi bạn chọn một hoạt động.</span><span class="sxs-lookup"><span data-stu-id="5d6a6-161">The following actions are available when you select an activity.</span></span> 

- <span data-ttu-id="5d6a6-162">**Chỉnh sửa**: Mở hoạt động được thiết lập ở bước đánh giá.</span><span class="sxs-lookup"><span data-stu-id="5d6a6-162">**Edit**: Opens the activity setup on the review step.</span></span> <span data-ttu-id="5d6a6-163">Bạn có thể thay đổi bất kỳ hoặc tất cả cấu hình hiện tại từ bước này.</span><span class="sxs-lookup"><span data-stu-id="5d6a6-163">You can change any or all of the current configuration from this step.</span></span> <span data-ttu-id="5d6a6-164">Sau khi thay đổi cấu hình, hãy chọn **Lưu hoạt động** rồi chọn **Chạy** để xử lý các thay đổi.</span><span class="sxs-lookup"><span data-stu-id="5d6a6-164">After changing the configuration, select **Save activity** and then select **Run** to process the changes.</span></span>

- <span data-ttu-id="5d6a6-165">**Đổi tên**: Mở hộp thoại nơi bạn có thể nhập tên khác cho hoạt động đã chọn.</span><span class="sxs-lookup"><span data-stu-id="5d6a6-165">**Rename**: Opens a dialog where you can enter a different name for the selected activity.</span></span> <span data-ttu-id="5d6a6-166">Chọn **Lưu** để áp dụng thay đổi.</span><span class="sxs-lookup"><span data-stu-id="5d6a6-166">Select **Save** to apply your changes.</span></span>

- <span data-ttu-id="5d6a6-167">**Xóa**: Mở hộp thoại để xác nhận việc xóa hoạt động đã chọn.</span><span class="sxs-lookup"><span data-stu-id="5d6a6-167">**Delete**: Opens a dialog to confirm the deletion of the selected activity.</span></span> <span data-ttu-id="5d6a6-168">Bạn cũng có thể xóa nhiều hoạt động cùng một lúc bằng cách chọn các hoạt động rồi chọn biểu tượng xóa.</span><span class="sxs-lookup"><span data-stu-id="5d6a6-168">You can also delete more than one activity at once by selecting the activities and then selecting the delete icon.</span></span> <span data-ttu-id="5d6a6-169">Chọn **Xoá** để xác nhận tác vụ xoá của bạn.</span><span class="sxs-lookup"><span data-stu-id="5d6a6-169">Select **Delete** to confirm the deletion.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
