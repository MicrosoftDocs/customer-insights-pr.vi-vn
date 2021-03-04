---
title: Trộn các thực thể trong hợp nhất dữ liệu
description: Trộn các thực thể để tạo hồ sơ khách hàng hợp nhất.
ms.date: 04/16/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 5d5ff4c6f091d1b50d0f6c8366bbe4f0e6428dac
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268528"
---
# <a name="merge-entities"></a><span data-ttu-id="2422b-103">Hợp nhất thực thể</span><span class="sxs-lookup"><span data-stu-id="2422b-103">Merge entities</span></span>

<span data-ttu-id="2422b-104">Giai đoạn hợp nhất là giai đoạn cuối cùng trong quy trình hợp nhất dữ liệu.</span><span class="sxs-lookup"><span data-stu-id="2422b-104">The merge phase is the last phase in the data unification process.</span></span> <span data-ttu-id="2422b-105">Mục đích của nó là đối chiếu dữ liệu xung đột.</span><span class="sxs-lookup"><span data-stu-id="2422b-105">Its purpose is reconciling conflicting data.</span></span> <span data-ttu-id="2422b-106">Ví dụ về dữ liệu xung đột có thể bao gồm tên khách hàng được tìm thấy trong hai bộ dữ liệu của bạn nhưng hiển thị hơi khác nhau trong mỗi dữ liệu ("Grant Marshall" so với "Grant Marshal") hoặc số điện thoại khác nhau ở định dạng (617-803-091X so với 617803091X).</span><span class="sxs-lookup"><span data-stu-id="2422b-106">Examples of conflicting data could include a customer name found in two of your datasets but that shows up a little differently in each ("Grant Marshall" versus "Grant Marshal"), or a phone number that differs in format (617-803-091X versus 617803091X).</span></span> <span data-ttu-id="2422b-107">Việc hợp nhất các điểm dữ liệu xung đột đó được thực hiện trên cơ sở từng thuộc tính.</span><span class="sxs-lookup"><span data-stu-id="2422b-107">Merging those conflicting data points is done on an attribute-by-attribute basis.</span></span>

<span data-ttu-id="2422b-108">Sau khi hoàn thành [giai đoạn so khớp](match-entities.md), bạn có thể bắt đầu giai đoạn hợp nhất bằng cách chọn lát **Hợp nhất** trên trang **Hợp nhất**.</span><span class="sxs-lookup"><span data-stu-id="2422b-108">After completing the [match phase](match-entities.md), you start the merge phase by selecting the **Merge** tile on the **Unify** page.</span></span>

## <a name="review-system-recommendations"></a><span data-ttu-id="2422b-109">Xem lại đề xuất hệ thống</span><span class="sxs-lookup"><span data-stu-id="2422b-109">Review system recommendations</span></span>

<span data-ttu-id="2422b-110">Trên trang **Hợp nhất**, bạn có thể chọn và loại trừ các thuộc tính được hợp nhất trong thực thể hồ sơ khách hàng đã hợp nhất của bạn (kết quả của quá trình cấu hình).</span><span class="sxs-lookup"><span data-stu-id="2422b-110">On the **Merge** page, you choose and exclude attributes to merge within your unified customer profile entity (the result of the configuration process).</span></span> <span data-ttu-id="2422b-111">Một số thuộc tính được hệ thống tự động hợp nhất.</span><span class="sxs-lookup"><span data-stu-id="2422b-111">Some attributes are automatically merged by the system.</span></span>

### <a name="view-merged-attributes"></a><span data-ttu-id="2422b-112">Xem thuộc tính đã hợp nhất</span><span class="sxs-lookup"><span data-stu-id="2422b-112">View merged attributes</span></span>

<span data-ttu-id="2422b-113">Để xem các thuộc tính được bao gồm trong một trong các thuộc tính được hợp nhất tự động của bạn, hãy chọn thuộc tính được hợp nhất đó.</span><span class="sxs-lookup"><span data-stu-id="2422b-113">To view the attributes that are included in one of your automatically merged attributes, select that merged attribute.</span></span> <span data-ttu-id="2422b-114">Hai thuộc tính cấu thành thuộc tính được hợp nhất đó sẽ hiển thị trong hai hàng mới bên dưới thuộc tính được hợp nhất.</span><span class="sxs-lookup"><span data-stu-id="2422b-114">The two attributes that compose that merged attribute display in two new rows beneath the merged attribute.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="2422b-115">![Chọn thuộc tính đã hợp nhất](media/configure-data-merge-profile-attributes.png "Chọn thuộc tính đã hợp nhất")</span><span class="sxs-lookup"><span data-stu-id="2422b-115">![Select merged attribute](media/configure-data-merge-profile-attributes.png "Select merged attribute")</span></span>

### <a name="separate-merged-attributes"></a><span data-ttu-id="2422b-116">Tách thuộc tính đã hợp nhất</span><span class="sxs-lookup"><span data-stu-id="2422b-116">Separate merged attributes</span></span>

<span data-ttu-id="2422b-117">Để tách hoặc hủy hợp nhất tách bất kỳ thuộc tính được hợp nhất tự động nào, hãy tìm thuộc tính đó trong bảng **Thuộc tính hồ sơ**.</span><span class="sxs-lookup"><span data-stu-id="2422b-117">To separate or unmerge any of the automatically merged attributes, find the attribute in the **Profile attributes** table.</span></span>

1. <span data-ttu-id="2422b-118">Chọn nút dấu chấm lửng (...).</span><span class="sxs-lookup"><span data-stu-id="2422b-118">Select the ellipsis (...) button.</span></span>
  
2. <span data-ttu-id="2422b-119">Trong danh sách thả xuống, chọn **Tách các trường**.</span><span class="sxs-lookup"><span data-stu-id="2422b-119">In the dropdown list, select **Separate fields**.</span></span>

### <a name="remove-merged-attributes"></a><span data-ttu-id="2422b-120">Xóa thuộc tính đã hợp nhất</span><span class="sxs-lookup"><span data-stu-id="2422b-120">Remove merged attributes</span></span>

<span data-ttu-id="2422b-121">Để loại trừ một thuộc tính khỏi thực thể hồ sơ khách hàng cuối cùng, hãy tìm thuộc tính đó trong bảng **Thuộc tính hồ sơ**.</span><span class="sxs-lookup"><span data-stu-id="2422b-121">To exclude an attribute from the final customer profile entity, find it in the **Profile attributes** table.</span></span>

1. <span data-ttu-id="2422b-122">Chọn nút dấu chấm lửng (...).</span><span class="sxs-lookup"><span data-stu-id="2422b-122">Select the ellipsis (...) button.</span></span>
  
2. <span data-ttu-id="2422b-123">Trong danh sách thả xuống, chọn **Không hợp nhất**.</span><span class="sxs-lookup"><span data-stu-id="2422b-123">In the dropdown list, select **Don't merge**.</span></span>

   <span data-ttu-id="2422b-124">Thuộc tính được chuyển đến phần **Xóa khỏi hồ sơ khách hàng**.</span><span class="sxs-lookup"><span data-stu-id="2422b-124">The attribute is moved to the **Removed from customer record** section.</span></span>

## <a name="manually-add-a-merged-attribute"></a><span data-ttu-id="2422b-125">Thêm thủ công một thuộc tính hợp nhất</span><span class="sxs-lookup"><span data-stu-id="2422b-125">Manually add a merged attribute</span></span>

<span data-ttu-id="2422b-126">Để thêm một thuộc tính được hợp nhất, hãy đi đến trang **Hợp nhất**.</span><span class="sxs-lookup"><span data-stu-id="2422b-126">To add a merged attribute, go to the **Merge** page.</span></span>

1. <span data-ttu-id="2422b-127">Chọn **Thêm thuộc tính đã hợp nhất**.</span><span class="sxs-lookup"><span data-stu-id="2422b-127">Select **Add merged attribute**.</span></span>

2. <span data-ttu-id="2422b-128">Cung cấp một **Tên** để xác định thuộc tính đó trên trang **Hợp nhất** vào lúc khác.</span><span class="sxs-lookup"><span data-stu-id="2422b-128">Provide a **Name** to identify it on the **Merge** page later.</span></span>

3. <span data-ttu-id="2422b-129">Hoặc bạn có thể cung cấp một **Tên hiển thị** để xuất hiện trong thực thể Hồ sơ khách hàng hợp nhất.</span><span class="sxs-lookup"><span data-stu-id="2422b-129">Optionally, provide a **Display name** to appear in the unified Customer Profile entity.</span></span>

4. <span data-ttu-id="2422b-130">Cấu hình **Chọn các thuộc tính trùng lặp** để chọn các thuộc tính mà bạn muốn hợp nhất từ các thực thể phù hợp.</span><span class="sxs-lookup"><span data-stu-id="2422b-130">Configure **Select duplicate attributes** to select the attributes that you want to merge from the matched entities.</span></span> <span data-ttu-id="2422b-131">Bạn cũng có thể tìm kiếm các thuộc tính.</span><span class="sxs-lookup"><span data-stu-id="2422b-131">You can also search for attributes.</span></span>

5. <span data-ttu-id="2422b-132">Đặt **Xếp hạng theo mức độ quan trọng** để ưu tiên một thuộc tính so với các thuộc tính khác.</span><span class="sxs-lookup"><span data-stu-id="2422b-132">Set the **Rank by importance** to prioritize one attribute above the others.</span></span> <span data-ttu-id="2422b-133">Ví dụ: nếu thực thể *WebAccountCSV* bao gồm dữ liệu chính xác nhất về thuộc tín *Tên đầy đủ*, thì bạn có thể ưu tiên thực thể này so với *ContactCSV* bằng việc chọn *WebAccountCSV*.</span><span class="sxs-lookup"><span data-stu-id="2422b-133">For example, if the *WebAccountCSV* entity includes the most accurate data about the *Full Names* attribute, you could prioritize this entity over *ContactCSV* by selecting *WebAccountCSV*.</span></span> <span data-ttu-id="2422b-134">Kết quả là *WebAccountCSV* chuyển sang ưu tiên hàng đầu, trong khi *ContactCSV* chuyển sang ưu tiên thứ hai khi kéo các giá trị cho thuộc tính *Họ và tên*.</span><span class="sxs-lookup"><span data-stu-id="2422b-134">As a result, *WebAccountCSV* moves to first priority, while *ContactCSV* moves to second priority when pulling values for the *Full Name* attribute.</span></span>

## <a name="run-your-merge"></a><span data-ttu-id="2422b-135">Chạy hợp nhất của bạn</span><span class="sxs-lookup"><span data-stu-id="2422b-135">Run your merge</span></span>

<span data-ttu-id="2422b-136">Cho dù bạn hợp nhất thủ công các thuộc tính hay để hệ thống hợp nhất chúng, bạn luôn có thể chạy hợp nhất.</span><span class="sxs-lookup"><span data-stu-id="2422b-136">Whether you manually merge attributes or let the system merge them, you can always run your merge.</span></span> <span data-ttu-id="2422b-137">Chọn **Chạy** trên trang **Hợp nhất** để bắt đầu quy trình.</span><span class="sxs-lookup"><span data-stu-id="2422b-137">Select **Run** on the **Merge** page to start the process.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="2422b-138">![Lưu và chạy hợp nhất dữ liệu](media/configure-data-merge-save-run.png "Lưu và chạy hợp nhất dữ liệu")</span><span class="sxs-lookup"><span data-stu-id="2422b-138">![Data merge Save and Run](media/configure-data-merge-save-run.png "Data merge Save and Run")</span></span>

<span data-ttu-id="2422b-139">Để thực hiện các thay đổi bổ sung và chạy lại bước này, bạn có thể hủy hợp nhất đang thực hiện.</span><span class="sxs-lookup"><span data-stu-id="2422b-139">To make additional changes and rerun the step, you can cancel an in-progress merge.</span></span> <span data-ttu-id="2422b-140">Chọn **Đang làm mới ...** rồi chọn **Hủy công việc**  trong ngăn bên xuất hiện.</span><span class="sxs-lookup"><span data-stu-id="2422b-140">Select **Refreshing ...** and select **Cancel job**  in the side pane that appears.</span></span>

<span data-ttu-id="2422b-141">Sau khi văn bản **Đang làm mới ...** thay đổi thành **Thành công**, quá trình hợp nhất đã hoàn tất và đã giải quyết mẫu thuẫn trong dữ liệu theo các chính sách bạn đã xác định.</span><span class="sxs-lookup"><span data-stu-id="2422b-141">After the **Refreshing ...** text changes to **Successful**, merge has completed and resolved contradictions in your data according to the policies you defined.</span></span> <span data-ttu-id="2422b-142">Các thuộc tính được hợp nhất và chưa được hợp nhất được bao gồm trong thực thể hồ sơ hợp nhất.</span><span class="sxs-lookup"><span data-stu-id="2422b-142">Merged and unmerged attributes are included in the unified profile entity.</span></span> <span data-ttu-id="2422b-143">Các thuộc tính bị loại trừ chưa được bao gồm trong thực thể hồ sơ hợp nhất.</span><span class="sxs-lookup"><span data-stu-id="2422b-143">Excluded attributes aren't included in the unified profile entity.</span></span>

<span data-ttu-id="2422b-144">Nếu đó không phải là lần đầu tiên bạn thực hiện hợp nhất thành công, tất cả các quy trình hạ nguồn, bao gồm làm giàu, phân đoạn và các biện pháp sẽ tự động chạy lại.</span><span class="sxs-lookup"><span data-stu-id="2422b-144">If it wasn't the first time you ran a merge successfully, all downstream processes, including enrichment, segmentation, and measures will rerun automatically.</span></span> <span data-ttu-id="2422b-145">Sau khi tất cả các quy trình hạ nguồn đã được chạy lại, hồ sơ khách hàng phản ánh bất kỳ thay đổi nào bạn đã thực hiện.</span><span class="sxs-lookup"><span data-stu-id="2422b-145">After all downstream processes have been rerun, the customer profiles reflect any changes you made.</span></span>

> [!TIP]
> <span data-ttu-id="2422b-146">Có [6 loại trạng thái](system.md#status-types) cho các nhiệm vụ/quy trình.</span><span class="sxs-lookup"><span data-stu-id="2422b-146">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="2422b-147">Ngoài ra, hầu hết các quy trình [phụ thuộc vào các quá trình hạ nguồn khác](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="2422b-147">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="2422b-148">Bạn có thể chọn trạng thái của một quy trình để xem chi tiết về tiến trình của toàn bộ công việc.</span><span class="sxs-lookup"><span data-stu-id="2422b-148">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="2422b-149">Sau khi chọn **Xem chi tiết** đối với một trong các tác vụ của công việc, bạn sẽ tìm thấy thông tin bổ sung: thời gian xử lý, ngày xử lý gần nhất và tất cả các lỗi và cảnh báo liên quan đến tác vụ.</span><span class="sxs-lookup"><span data-stu-id="2422b-149">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="2422b-150">Bước tiếp theo</span><span class="sxs-lookup"><span data-stu-id="2422b-150">Next Step</span></span>

<span data-ttu-id="2422b-151">Đặt cấu hình [hoạt động](activities.md), [nội dung phong phú](enrichment-microsoft-graph.md) hoặc [mối quan hệ](relationships.md) để hiểu thêm về khách hàng của bạn.</span><span class="sxs-lookup"><span data-stu-id="2422b-151">Configure [activities](activities.md), [enrichment](enrichment-microsoft-graph.md), or [relationships](relationships.md) to gain more insights about your customers.</span></span>

<span data-ttu-id="2422b-152">Nếu bạn đã định cấu hình các hoạt động, nội dung phong phú hoặc các mối quan hệ hoặc nếu bạn đã xác định các phân khúc, chúng sẽ được xử lý tự động để sử dụng dữ liệu khách hàng mới nhất.</span><span class="sxs-lookup"><span data-stu-id="2422b-152">If you already configured activities, enrichment, or relationships, or if you defined segments, they'll be processed automatically to use the latest customer data.</span></span>




[!INCLUDE[footer-include](../includes/footer-banner.md)]