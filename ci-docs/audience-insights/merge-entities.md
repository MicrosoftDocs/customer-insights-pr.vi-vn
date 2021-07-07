---
title: Trộn các thực thể trong hợp nhất dữ liệu
description: Trộn các thực thể để tạo hồ sơ khách hàng hợp nhất.
ms.date: 05/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 86ab3cefa70e5fab4bdb27cde363adee26efee4c
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305685"
---
# <a name="merge-entities"></a><span data-ttu-id="2408a-103">Hợp nhất thực thể</span><span class="sxs-lookup"><span data-stu-id="2408a-103">Merge entities</span></span>

<span data-ttu-id="2408a-104">Giai đoạn hợp nhất là giai đoạn cuối cùng trong quy trình hợp nhất dữ liệu.</span><span class="sxs-lookup"><span data-stu-id="2408a-104">The merge phase is the last phase in the data unification process.</span></span> <span data-ttu-id="2408a-105">Mục đích của nó là đối chiếu dữ liệu xung đột.</span><span class="sxs-lookup"><span data-stu-id="2408a-105">Its purpose is reconciling conflicting data.</span></span> <span data-ttu-id="2408a-106">Ví dụ về dữ liệu xung đột có thể bao gồm tên khách hàng được tìm thấy trong hai bộ dữ liệu của bạn nhưng hiển thị hơi khác nhau trong mỗi dữ liệu ("Grant Marshall" so với "Grant Marshal") hoặc số điện thoại khác nhau ở định dạng (617-803-091X so với 617803091X).</span><span class="sxs-lookup"><span data-stu-id="2408a-106">Examples of conflicting data could include a customer name found in two of your datasets but that shows up a little differently in each ("Grant Marshall" versus "Grant Marshal"), or a phone number that differs in format (617-803-091X versus 617803091X).</span></span> <span data-ttu-id="2408a-107">Việc hợp nhất các điểm dữ liệu xung đột đó được thực hiện trên cơ sở từng thuộc tính.</span><span class="sxs-lookup"><span data-stu-id="2408a-107">Merging those conflicting data points is done on an attribute-by-attribute basis.</span></span>

:::image type="content" source="media/merge-fields-page.png" alt-text="Khi phối trang trong quá trình hợp nhất dữ liệu, một bảng với các trường đã hợp nhất xác định hồ sơ khách hàng hợp nhất sẽ xuất hiện.":::

<span data-ttu-id="2408a-109">Sau khi hoàn thành [giai đoạn so khớp](match-entities.md), bạn có thể bắt đầu giai đoạn hợp nhất bằng cách chọn lát **Hợp nhất** trên trang **Hợp nhất**.</span><span class="sxs-lookup"><span data-stu-id="2408a-109">After completing the [match phase](match-entities.md), you start the merge phase by selecting the **Merge** tile on the **Unify** page.</span></span>

## <a name="review-system-recommendations"></a><span data-ttu-id="2408a-110">Xem lại đề xuất hệ thống</span><span class="sxs-lookup"><span data-stu-id="2408a-110">Review system recommendations</span></span>

<span data-ttu-id="2408a-111">Trong mục **Dữ liệu** > **Hợp nhất** > **Hợp nhất**, bạn chọn và loại trừ các thuộc tính để hợp nhất trong thực thể hồ sơ khách hàng hợp nhất của mình.</span><span class="sxs-lookup"><span data-stu-id="2408a-111">On **Data** > **Unify** > **Merge**, you choose and exclude attributes to merge within your unified customer profile entity.</span></span> <span data-ttu-id="2408a-112">Hồ sơ khách hàng hợp nhất là kết quả của quá trình hợp nhất dữ liệu.</span><span class="sxs-lookup"><span data-stu-id="2408a-112">The unified customer profile is the result of the data unification process.</span></span> <span data-ttu-id="2408a-113">Một số thuộc tính được hệ thống tự động hợp nhất.</span><span class="sxs-lookup"><span data-stu-id="2408a-113">Some attributes are automatically merged by the system.</span></span>

<span data-ttu-id="2408a-114">Để xem các thuộc tính có trong thuộc tính được hợp nhất tự động của bạn, hãy chọn thuộc tính được hợp nhất đó trong tab **Trường khách hàng** của bảng.</span><span class="sxs-lookup"><span data-stu-id="2408a-114">To view the attributes that are included in one of your automatically merged attributes, select that merged attribute in the **Customer fields** tab of the table.</span></span> <span data-ttu-id="2408a-115">Thuộc tính cấu thành thuộc tính được hợp nhất đó sẽ hiển thị trong hai hàng mới bên dưới thuộc tính được hợp nhất.</span><span class="sxs-lookup"><span data-stu-id="2408a-115">The attributes that compose that merged attribute display in two new rows beneath the merged attribute.</span></span>

## <a name="separate-rename-exclude-and-edit-merged-fields"></a><span data-ttu-id="2408a-116">Tách, đổi tên, loại trừ và chỉnh sửa các trường đã hợp nhất</span><span class="sxs-lookup"><span data-stu-id="2408a-116">Separate, rename, exclude, and edit merged fields</span></span>

<span data-ttu-id="2408a-117">Bạn có thể thay đổi cách hệ thống xử lý các thuộc tính đã hợp nhất để tạo hồ sơ khách hàng hợp nhất.</span><span class="sxs-lookup"><span data-stu-id="2408a-117">You can change how the system processes merged attributes to generate the unified customer profile.</span></span> <span data-ttu-id="2408a-118">Chọn **Hiển thị thêm** và chọn những phần bạn muốn thay đổi.</span><span class="sxs-lookup"><span data-stu-id="2408a-118">Select **Show more** and choose what you want to change.</span></span>

:::image type="content" source="media/manage-merged-attributes.png" alt-text="Các tùy chọn trong menu thả xuống Hiển thị thêm để quản lý các thuộc tính đã hợp nhất.":::

<span data-ttu-id="2408a-120">Xem phần sau đây để biết thêm thông tin.</span><span class="sxs-lookup"><span data-stu-id="2408a-120">For more information, see the following sections.</span></span>

## <a name="separate-merged-fields"></a><span data-ttu-id="2408a-121">Tách trường đã hợp nhất</span><span class="sxs-lookup"><span data-stu-id="2408a-121">Separate merged fields</span></span>

<span data-ttu-id="2408a-122">Để tách các trường đã hợp nhất, hãy tìm thuộc tính trong bảng.</span><span class="sxs-lookup"><span data-stu-id="2408a-122">To separate merged fields, find the attribute in the table.</span></span> <span data-ttu-id="2408a-123">Các trường được tách sẽ hiển thị dưới dạng các điểm dữ liệu riêng lẻ trên hồ sơ khách hàng hợp nhất.</span><span class="sxs-lookup"><span data-stu-id="2408a-123">Separated fields show as individual data points on the unified customer profile.</span></span> 

1. <span data-ttu-id="2408a-124">Chọn trường hợp nhất.</span><span class="sxs-lookup"><span data-stu-id="2408a-124">Select the merged field.</span></span>
  
1. <span data-ttu-id="2408a-125">Chọn **Hiển thị thêm** và chọn **Các trường riêng biệt**.</span><span class="sxs-lookup"><span data-stu-id="2408a-125">Select **Show more** and choose **Separate fields**.</span></span>
 
1. <span data-ttu-id="2408a-126">Xác nhận việc tách trường.</span><span class="sxs-lookup"><span data-stu-id="2408a-126">Confirm the separation.</span></span>

1. <span data-ttu-id="2408a-127">Chọn **Lưu** và **Chạy** để thay đổi.</span><span class="sxs-lookup"><span data-stu-id="2408a-127">Select **Save** and **Run** to process the changes.</span></span>

## <a name="rename-merged-fields"></a><span data-ttu-id="2408a-128">Đổi tên các trường đã hợp nhất</span><span class="sxs-lookup"><span data-stu-id="2408a-128">Rename merged fields</span></span>

<span data-ttu-id="2408a-129">Thay đổi tên hiển thị của các thuộc tính đã hợp nhất.</span><span class="sxs-lookup"><span data-stu-id="2408a-129">Change the display name of merged attributes.</span></span> <span data-ttu-id="2408a-130">Bạn không thể thay đổi tên của thực thể đầu ra.</span><span class="sxs-lookup"><span data-stu-id="2408a-130">You can't change the name of the output entity.</span></span>

1. <span data-ttu-id="2408a-131">Chọn trường hợp nhất.</span><span class="sxs-lookup"><span data-stu-id="2408a-131">Select the merged field.</span></span>
  
1. <span data-ttu-id="2408a-132">Chọn **Hiển thị thêm** và chọn **Đổi tên**.</span><span class="sxs-lookup"><span data-stu-id="2408a-132">Select **Show more** and choose **Rename**.</span></span>

1. <span data-ttu-id="2408a-133">Xác nhận tên hiển thị đã thay đổi.</span><span class="sxs-lookup"><span data-stu-id="2408a-133">Confirm the changed display name.</span></span> 

1. <span data-ttu-id="2408a-134">Chọn **Lưu** và **Chạy** để thay đổi.</span><span class="sxs-lookup"><span data-stu-id="2408a-134">Select **Save** and **Run** to process the changes.</span></span>

## <a name="exclude-merged-fields"></a><span data-ttu-id="2408a-135">Các trường đã hợp nhất bị loại trừ</span><span class="sxs-lookup"><span data-stu-id="2408a-135">Exclude merged fields</span></span>

<span data-ttu-id="2408a-136">Loại trừ một thuộc tính khỏi hồ sơ khách hàng hợp nhất.</span><span class="sxs-lookup"><span data-stu-id="2408a-136">Exclude an attribute from the unified customer profile.</span></span> <span data-ttu-id="2408a-137">Nếu trường được sử dụng trong các quy trình khác, ví dụ như trong một phân khúc, hãy xóa trường khỏi các quy trình này trước khi loại trừ trường khỏi hồ sơ khách hàng.</span><span class="sxs-lookup"><span data-stu-id="2408a-137">If the field is used in other processes, for example in a segment, remove it from these processes before excluding it from the customer profile.</span></span> 

1. <span data-ttu-id="2408a-138">Chọn trường hợp nhất.</span><span class="sxs-lookup"><span data-stu-id="2408a-138">Select the merged field.</span></span>
  
1. <span data-ttu-id="2408a-139">Chọn **Hiển thị thêm** và chọn **Loại trừ**.</span><span class="sxs-lookup"><span data-stu-id="2408a-139">Select **Show more** and choose **Exclude**.</span></span>

1. <span data-ttu-id="2408a-140">Xác nhận việc loại trừ.</span><span class="sxs-lookup"><span data-stu-id="2408a-140">Confirm the exclusion.</span></span>

1. <span data-ttu-id="2408a-141">Chọn **Lưu** và **Chạy** để thay đổi.</span><span class="sxs-lookup"><span data-stu-id="2408a-141">Select **Save** and **Run** to process the changes.</span></span> 

<span data-ttu-id="2408a-142">Trên trang **Hợp nhất**, chọn **Các trường bị loại trừ** để xem danh sách tất cả các trường đã loại trừ.</span><span class="sxs-lookup"><span data-stu-id="2408a-142">On the **Merge** page, select **Excluded fields** to see the list of all excluded fields.</span></span> <span data-ttu-id="2408a-143">Bạn có thể thêm lại các trường bị loại trừ trong ngăn này.</span><span class="sxs-lookup"><span data-stu-id="2408a-143">This pane lets you add excluded fields back.</span></span>

## <a name="manually-combine-fields"></a><span data-ttu-id="2408a-144">Các trường kết hợp theo cách thủ công</span><span class="sxs-lookup"><span data-stu-id="2408a-144">Manually combine fields</span></span>

<span data-ttu-id="2408a-145">Chỉ định một thuộc tính đã hợp nhất theo cách thủ công.</span><span class="sxs-lookup"><span data-stu-id="2408a-145">Specify a merged attribute manually.</span></span> 

1. <span data-ttu-id="2408a-146">Trên trang **Hợp nhất**, chọn **Kết hợp các trường**.</span><span class="sxs-lookup"><span data-stu-id="2408a-146">On the **Merge** page, select **Combine fields**.</span></span>

1. <span data-ttu-id="2408a-147">Đặt **Tên** và **Tên trường đầu ra**.</span><span class="sxs-lookup"><span data-stu-id="2408a-147">Provide a **Name** and an **Output field name**.</span></span>

1. <span data-ttu-id="2408a-148">Chọn trường để thêm vào.</span><span class="sxs-lookup"><span data-stu-id="2408a-148">Choose a field to add.</span></span> <span data-ttu-id="2408a-149">Chọn **Thêm trường** để kết hợp nhiều trường.</span><span class="sxs-lookup"><span data-stu-id="2408a-149">Select **Add fields** to combine more fields.</span></span>

1. <span data-ttu-id="2408a-150">Xác nhận việc loại trừ.</span><span class="sxs-lookup"><span data-stu-id="2408a-150">Confirm the exclusion.</span></span>

1. <span data-ttu-id="2408a-151">Chọn **Lưu** và **Chạy** để thay đổi.</span><span class="sxs-lookup"><span data-stu-id="2408a-151">Select **Save** and **Run** to process the changes.</span></span> 

## <a name="change-the-order-of-fields"></a><span data-ttu-id="2408a-152">Thay đổi thứ tự trường</span><span class="sxs-lookup"><span data-stu-id="2408a-152">Change the order of fields</span></span>

<span data-ttu-id="2408a-153">Một số thực thể chứa nhiều chi tiết hơn những thực thể khác.</span><span class="sxs-lookup"><span data-stu-id="2408a-153">Some entities contain more details than others.</span></span> <span data-ttu-id="2408a-154">Nếu một thực thể bao gồm dữ liệu mới nhất về một trường, bạn có thể ưu tiên thực thể này hơn khi hợp nhất các giá trị.</span><span class="sxs-lookup"><span data-stu-id="2408a-154">If an entity includes the latest data about a field, you can prioritize it over other entities when merging values.</span></span>

1. <span data-ttu-id="2408a-155">Chọn trường hợp nhất.</span><span class="sxs-lookup"><span data-stu-id="2408a-155">Select the merged field.</span></span>
  
1. <span data-ttu-id="2408a-156">Chọn **Hiển thị thêm** và chọn **Chỉnh sửa**.</span><span class="sxs-lookup"><span data-stu-id="2408a-156">Select **Show more** and choose **Edit**.</span></span>

1. <span data-ttu-id="2408a-157">Trong ngăn **Kết hợp các trường**, chọn **Di chuyển lên/xuống** để đặt thứ tự hoặc kéo và thả các trường vào vị trí mong muốn.</span><span class="sxs-lookup"><span data-stu-id="2408a-157">In the **Combine fields** pane, select **Move up/down** to set the order or drag and drop them in the desired position.</span></span>

1. <span data-ttu-id="2408a-158">Xác nhận thay đổi.</span><span class="sxs-lookup"><span data-stu-id="2408a-158">Confirm the change.</span></span>

1. <span data-ttu-id="2408a-159">Chọn **Lưu** và **Chạy** để thay đổi.</span><span class="sxs-lookup"><span data-stu-id="2408a-159">Select **Save** and **Run** to process the changes.</span></span>

## <a name="run-your-merge"></a><span data-ttu-id="2408a-160">Chạy hợp nhất của bạn</span><span class="sxs-lookup"><span data-stu-id="2408a-160">Run your merge</span></span>

<span data-ttu-id="2408a-161">Cho dù bạn hợp nhất thủ công các thuộc tính hay để hệ thống hợp nhất chúng, bạn luôn có thể chạy hợp nhất.</span><span class="sxs-lookup"><span data-stu-id="2408a-161">Whether you manually merge attributes or let the system merge them, you can always run your merge.</span></span> <span data-ttu-id="2408a-162">Chọn **Chạy** trên trang **Hợp nhất** để bắt đầu quy trình.</span><span class="sxs-lookup"><span data-stu-id="2408a-162">Select **Run** on the **Merge** page to start the process.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="2408a-163">![Lưu và chạy hợp nhất dữ liệu](media/configure-data-merge-save-run.png "Lưu và chạy hợp nhất dữ liệu")</span><span class="sxs-lookup"><span data-stu-id="2408a-163">![Data merge Save and Run](media/configure-data-merge-save-run.png "Data merge Save and Run")</span></span>

<span data-ttu-id="2408a-164">Chọn **Chỉ chạy Hợp nhất** nếu bạn chỉ muốn xem kết quả đầu ra được phản ánh trong thực thể khách hàng hợp nhất.</span><span class="sxs-lookup"><span data-stu-id="2408a-164">Choose **Run only Merge** if you only want to see the output reflected in the unified customer entity.</span></span> <span data-ttu-id="2408a-165">Các quy trình xuôi dòng sẽ được làm mới như [đã xác định trong lịch trình làm mới](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="2408a-165">Downstream processes will be refreshed as [defined in the refresh schedule](system.md#schedule-tab).</span></span>

<span data-ttu-id="2408a-166">Chọn **Chạy các quy trình Hợp nhất và xuôi dòng** để làm mới hệ thống với các thay đổi của bạn.</span><span class="sxs-lookup"><span data-stu-id="2408a-166">Choose **Run Merge and downstream processes** to refresh the system with your changes.</span></span> <span data-ttu-id="2408a-167">Tất cả các quy trình, bao gồm tăng cường, phân đoạn và đo lường sẽ tự động chạy lại.</span><span class="sxs-lookup"><span data-stu-id="2408a-167">All processes, including enrichment, segments, and measures will rerun automatically.</span></span> <span data-ttu-id="2408a-168">Sau khi tất cả các quy trình xuôi dòng đã hoàn tất, hồ sơ khách hàng hiển thị mọi thay đổi bạn đã thực hiện.</span><span class="sxs-lookup"><span data-stu-id="2408a-168">After all downstream processes have completed, the customer profiles reflect any changes you made.</span></span>

<span data-ttu-id="2408a-169">Để thực hiện thêm nhiều thay đổi và chạy lại bước, bạn có thể hủy quá trình hợp nhất đang diễn ra.</span><span class="sxs-lookup"><span data-stu-id="2408a-169">To make more changes and rerun the step, you can cancel an in-progress merge.</span></span> <span data-ttu-id="2408a-170">Chọn **Đang làm mới ...** rồi chọn **Hủy công việc**  trong ngăn bên xuất hiện.</span><span class="sxs-lookup"><span data-stu-id="2408a-170">Select **Refreshing ...** and select **Cancel job**  in the side pane that appears.</span></span>

> [!TIP]
> <span data-ttu-id="2408a-171">Có [6 loại trạng thái](system.md#status-types) cho các nhiệm vụ/quy trình.</span><span class="sxs-lookup"><span data-stu-id="2408a-171">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="2408a-172">Ngoài ra, hầu hết các quy trình [phụ thuộc vào các quá trình hạ nguồn khác](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="2408a-172">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="2408a-173">Bạn có thể chọn trạng thái của một quy trình để xem chi tiết về tiến trình của toàn bộ công việc.</span><span class="sxs-lookup"><span data-stu-id="2408a-173">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="2408a-174">Sau khi chọn **Xem chi tiết** đối với một trong các tác vụ của công việc, bạn sẽ tìm thấy thông tin bổ sung: thời gian xử lý, ngày xử lý gần nhất và tất cả các lỗi và cảnh báo liên quan đến tác vụ.</span><span class="sxs-lookup"><span data-stu-id="2408a-174">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="2408a-175">Bước tiếp theo</span><span class="sxs-lookup"><span data-stu-id="2408a-175">Next Step</span></span>

<span data-ttu-id="2408a-176">Định cấu hình [hoạt động](activities.md), [nội dung phong phú](enrichment-hub.md) hoặc [mối quan hệ](relationships.md) để hiểu thêm về khách hàng của bạn.</span><span class="sxs-lookup"><span data-stu-id="2408a-176">Configure [activities](activities.md), [enrichment](enrichment-hub.md), or [relationships](relationships.md) to gain more insights about your customers.</span></span>

<span data-ttu-id="2408a-177">Nếu bạn đã định cấu hình các hoạt động, quá trình tăng cường hoặc phân đoạn, những phần này sẽ được xử lý tự động để sử dụng dữ liệu khách hàng mới nhất.</span><span class="sxs-lookup"><span data-stu-id="2408a-177">If you already configured activities, enrichment, or segments, they'll be processed automatically to use the latest customer data.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
