---
title: Tạo và quản lý phân đoạn
description: Tạo phân đoạn khách hàng để nhóm họ lại dựa trên các đặc điểm khác nhau.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: a1308f07ac3ba7d4b09931bab3d19b6dfaf479ee
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270382"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="0aae3-103">Tạo và quản lý phân đoạn</span><span class="sxs-lookup"><span data-stu-id="0aae3-103">Create and manage segments</span></span>

<span data-ttu-id="0aae3-104">Phân khúc cho phép bạn nhóm khách hàng của mình dựa trên các thuộc tính nhân khẩu học, giao dịch hoặc hành vi.</span><span class="sxs-lookup"><span data-stu-id="0aae3-104">Segments let you group your customers based on demographic, transactional, or behavioral attributes.</span></span> <span data-ttu-id="0aae3-105">Bạn có thể sử dụng các phân khúc để nhắm mục tiêu chiến dịch quảng cáo, hoạt động bán hàng và hành động hỗ trợ khách hàng để đạt được mục tiêu kinh doanh.</span><span class="sxs-lookup"><span data-stu-id="0aae3-105">You can use segments to target promotional campaigns, sales activities, and customer support actions to achieve your business goals.</span></span>

<span data-ttu-id="0aae3-106">Bạn có thể xác định các bộ lọc phức hợp xung quanh thực thể Hồ sơ khách hàng và các thực thể liên quan.</span><span class="sxs-lookup"><span data-stu-id="0aae3-106">You can define complex filters around the Customer Profile entity and its related entities.</span></span> <span data-ttu-id="0aae3-107">Mỗi phân khúc, sau khi xử lý, sẽ tạo một bộ hồ sơ khách hàng mà bạn có thể xuất và hành động.</span><span class="sxs-lookup"><span data-stu-id="0aae3-107">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="0aae3-108">Một số [giới hạn dịch vụ](service-limits.md) được áp dụng.</span><span class="sxs-lookup"><span data-stu-id="0aae3-108">Some [service limits](service-limits.md) apply.</span></span>

<span data-ttu-id="0aae3-109">Trừ khi có quy định khác, tất cả các phân khúc đều là **Phân khúc động**, được làm mới theo lịch trình định kỳ.</span><span class="sxs-lookup"><span data-stu-id="0aae3-109">Unless stated otherwise, all segments are **Dynamic segments**, which are refreshed on a recurring schedule.</span></span>

<span data-ttu-id="0aae3-110">Ví dụ sau minh họa khả năng tạo phân khúc.</span><span class="sxs-lookup"><span data-stu-id="0aae3-110">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="0aae3-111">Chúng tôi đã xác định một phân đoạn cho khách hàng đặt hàng hóa trị giá ít nhất $500 trong 90 ngày qua *và* đã tham gia vào cuộc gọi dịch vụ khách hàng đã báo cáo.</span><span class="sxs-lookup"><span data-stu-id="0aae3-111">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0aae3-112">![Nhiều nhóm](media/segmentation-group1-2.png "Nhiều nhóm")</span><span class="sxs-lookup"><span data-stu-id="0aae3-112">![Multiple groups](media/segmentation-group1-2.png "Multiple groups")</span></span>

## <a name="create-a-new-segment"></a><span data-ttu-id="0aae3-113">Tạo phân đoạn mới</span><span class="sxs-lookup"><span data-stu-id="0aae3-113">Create a new segment</span></span>

<span data-ttu-id="0aae3-114">Các phân khúc được quản lý trên trang **Phân khúc**.</span><span class="sxs-lookup"><span data-stu-id="0aae3-114">Segments are managed on the **Segments** page.</span></span>

1. <span data-ttu-id="0aae3-115">Trong thông tin chi tiết về đối tượng, hãy chuyển đến trang **Phân khúc**.</span><span class="sxs-lookup"><span data-stu-id="0aae3-115">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="0aae3-116">Chọn **Mới** > **Phân đoạn trống**.</span><span class="sxs-lookup"><span data-stu-id="0aae3-116">Select **New** > **Blank segment**.</span></span>

3. <span data-ttu-id="0aae3-117">Trong ngăn **Phân đoạn mới**, chọn loại phân đoạn và cung cấp **Tên**.</span><span class="sxs-lookup"><span data-stu-id="0aae3-117">In the **New segment** pane, choose a segment type and provide a **Name**.</span></span>

   <span data-ttu-id="0aae3-118">Bạn cũng có thể cung cấp tên hiển thị và mô tả nhằm xác định phân đoạn.</span><span class="sxs-lookup"><span data-stu-id="0aae3-118">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

4. <span data-ttu-id="0aae3-119">Chọn **Tiếp theo** để đi đến trang **Trình tạo phân đoạn** và xác định nhóm.</span><span class="sxs-lookup"><span data-stu-id="0aae3-119">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="0aae3-120">Một nhóm là một tập hợp các khách hàng.</span><span class="sxs-lookup"><span data-stu-id="0aae3-120">A group is a set of customers.</span></span>

5. <span data-ttu-id="0aae3-121">Chọn thực thể bao gồm thuộc tính mà bạn muốn tạo phân đoạn.</span><span class="sxs-lookup"><span data-stu-id="0aae3-121">Choose the entity that includes the attribute you want to segment by.</span></span>

6. <span data-ttu-id="0aae3-122">Chọn thuộc tính để tạo phân đoạn.</span><span class="sxs-lookup"><span data-stu-id="0aae3-122">Choose the attribute to segment by.</span></span> <span data-ttu-id="0aae3-123">Thuộc tính này có thể có 1 trong số 4 loại giá trị: số, chuỗi, ngày hoặc Boolean.</span><span class="sxs-lookup"><span data-stu-id="0aae3-123">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

7. <span data-ttu-id="0aae3-124">Chọn một toán tử và một giá trị cho thuộc tính đã chọn.</span><span class="sxs-lookup"><span data-stu-id="0aae3-124">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0aae3-125">![Bộ lọc nhóm tùy chỉnh](media/customer-group-numbers.png "Bộ lọc nhóm khách hàng")</span><span class="sxs-lookup"><span data-stu-id="0aae3-125">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="0aae3-126">Số</span><span class="sxs-lookup"><span data-stu-id="0aae3-126">Number</span></span> |<span data-ttu-id="0aae3-127">Định nghĩa</span><span class="sxs-lookup"><span data-stu-id="0aae3-127">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="0aae3-128">1</span><span class="sxs-lookup"><span data-stu-id="0aae3-128">1</span></span>     |<span data-ttu-id="0aae3-129">Entity</span><span class="sxs-lookup"><span data-stu-id="0aae3-129">Entity</span></span>          |
   |<span data-ttu-id="0aae3-130">2</span><span class="sxs-lookup"><span data-stu-id="0aae3-130">2</span></span>     |<span data-ttu-id="0aae3-131">Đặc điểm</span><span class="sxs-lookup"><span data-stu-id="0aae3-131">Attribute</span></span>          |
   |<span data-ttu-id="0aae3-132">3</span><span class="sxs-lookup"><span data-stu-id="0aae3-132">3</span></span>    |<span data-ttu-id="0aae3-133">Toán tử</span><span class="sxs-lookup"><span data-stu-id="0aae3-133">Operator</span></span>         |
   |<span data-ttu-id="0aae3-134">4</span><span class="sxs-lookup"><span data-stu-id="0aae3-134">4</span></span>    |<span data-ttu-id="0aae3-135">Giá trị</span><span class="sxs-lookup"><span data-stu-id="0aae3-135">Value</span></span>         |

8. <span data-ttu-id="0aae3-136">Nếu thực thể được kết nối với thực thể khách hàng hợp nhất qua [các mối quan hệ](relationships.md), thì bạn cần xác định đường dẫn mối quan hệ để tạo một phân đoạn hợp lệ.</span><span class="sxs-lookup"><span data-stu-id="0aae3-136">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="0aae3-137">Thêm các thực thể từ đường dẫn mối quan hệ cho đến khi bạn có thể chọn thực thể **Khách hàng : CustomerInsights** từ danh sách thả xuống.</span><span class="sxs-lookup"><span data-stu-id="0aae3-137">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="0aae3-138">Sau đó, chọn **Tất cả bản ghi** cho mỗi điều kiện.</span><span class="sxs-lookup"><span data-stu-id="0aae3-138">Then, choose **All records** for each condition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0aae3-139">![Đường dẫn mối quan hệ trong khi tạo phận đoạn](media/segments-multiple-relationships.png "Đường dẫn mối quan hệ trong khi tạo phận đoạn")</span><span class="sxs-lookup"><span data-stu-id="0aae3-139">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

9. <span data-ttu-id="0aae3-140">Chọn **Lưu** để lưu phân đoạn của bạn.</span><span class="sxs-lookup"><span data-stu-id="0aae3-140">Select **Save** to save your segment.</span></span> <span data-ttu-id="0aae3-141">Phân đoạn của bạn sẽ được lưu và xử lý nếu tất cả các yêu cầu được xác thực.</span><span class="sxs-lookup"><span data-stu-id="0aae3-141">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="0aae3-142">Nếu không, nó sẽ được lưu dưới dạng bản nháp.</span><span class="sxs-lookup"><span data-stu-id="0aae3-142">Otherwise, it will be saved as a draft.</span></span>

10. <span data-ttu-id="0aae3-143">Chọn **Quay lại phân khúc** để quay lại trang **Phân khúc**.</span><span class="sxs-lookup"><span data-stu-id="0aae3-143">Select **Back to segments** to go back to the **Segments** page.</span></span>

## <a name="manage-existing-segments"></a><span data-ttu-id="0aae3-144">Quản lý các phân đoạn hiện có</span><span class="sxs-lookup"><span data-stu-id="0aae3-144">Manage existing segments</span></span>

<span data-ttu-id="0aae3-145">Trên trang **Phân đoạn**, bạn có thể xem tất cả các phân đoạn đã lưu và quản lý chúng.</span><span class="sxs-lookup"><span data-stu-id="0aae3-145">On the **Segments** page, you can view all your saved segments and manage them.</span></span>

<span data-ttu-id="0aae3-146">Mỗi phân khúc được đại diện bởi một hàng bao gồm thông tin bổ sung về phân khúc.</span><span class="sxs-lookup"><span data-stu-id="0aae3-146">Each segment is represented by a row that includes additional information about the segment.</span></span>

<span data-ttu-id="0aae3-147">Bạn có thể sắp xếp các phân đoạn trong một cột bằng cách chọn tiêu đề cột.</span><span class="sxs-lookup"><span data-stu-id="0aae3-147">You can sort the segments in a column by selecting the column heading.</span></span>

<span data-ttu-id="0aae3-148">Sử dụng hộp **Tìm kiếm** ở góc trên cùng bên phải để lọc các phân khúc.</span><span class="sxs-lookup"><span data-stu-id="0aae3-148">Use the **Search** box in the top-right corner to filter the segments.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0aae3-149">![Tùy chọn để quản lý phân đoạn hiện có](media/segments-selected-segment.png "Tùy chọn để quản lý phân đoạn hiện có")</span><span class="sxs-lookup"><span data-stu-id="0aae3-149">![Options to manage an existing segment](media/segments-selected-segment.png "Options to manage an existing segment")</span></span>

<span data-ttu-id="0aae3-150">Hành động sau đây khả dụng khi bạn chọn một phân khúc:</span><span class="sxs-lookup"><span data-stu-id="0aae3-150">The following action are available when you select a segment:</span></span>

- <span data-ttu-id="0aae3-151">**Xem** chi tiết phân đoạn, bao gồm xu hướng số lượng thành viên của một bản xem trước thành viên phân đoạn.</span><span class="sxs-lookup"><span data-stu-id="0aae3-151">**View** the segment details, including member count trend a preview of segment members.</span></span>
- <span data-ttu-id="0aae3-152">**Chỉnh sửa** phân đoạn để thay đổi các thuộc tính của phân đoạn đó.</span><span class="sxs-lookup"><span data-stu-id="0aae3-152">**Edit** the segment to change its properties.</span></span>
- <span data-ttu-id="0aae3-153">**Làm mới** phân đoạn để bao gồm dữ liệu mới nhất.</span><span class="sxs-lookup"><span data-stu-id="0aae3-153">**Refresh** the segment to include the latest data.</span></span>
- <span data-ttu-id="0aae3-154">**Bật** hoặc **tắt** phân đoạn.</span><span class="sxs-lookup"><span data-stu-id="0aae3-154">**Activate** or **Deactivate** the segment.</span></span> <span data-ttu-id="0aae3-155">Các phân khúc có thể có hai trạng thái: hiện hoạt hoặc không hoạt động.</span><span class="sxs-lookup"><span data-stu-id="0aae3-155">Segments have two possible states - active or inactive.</span></span> <span data-ttu-id="0aae3-156">Các trạng thái này rất hữu ích khi bạn chỉnh sửa phân khúc.</span><span class="sxs-lookup"><span data-stu-id="0aae3-156">These states come in handy when editing a segment.</span></span> <span data-ttu-id="0aae3-157">Đối với các phân khúc không hoạt động, định nghĩa phân khúc tồn tại nhưng phân khúc chưa chứa bất kỳ khách hàng nào.</span><span class="sxs-lookup"><span data-stu-id="0aae3-157">For inactive segments, the segment definition exists but it doesn't contain any customers yet.</span></span> <span data-ttu-id="0aae3-158">Khi bạn kích hoạt một phân khúc, phân khúc sẽ thay đổi trạng thái từ "không hoạt động" thành "hiện hoạt" và bắt đầu tìm kiếm khách hàng phù hợp với định nghĩa phân khúc.</span><span class="sxs-lookup"><span data-stu-id="0aae3-158">When you activate a segment, its state changes from 'inactive' to 'active" and it starts looking for customers that match the segment definition.</span></span> <span data-ttu-id="0aae3-159">Nếu hoạt động [làm mới theo lịch trình](system.md#schedule-tab) được đặt cấu hình, thì các phân khúc không hoạt động sẽ có **Trạng thái** là **Đã bỏ qua**, biểu thị việc làm mới chưa được thực hiện.</span><span class="sxs-lookup"><span data-stu-id="0aae3-159">If a [scheduled refresh](system.md#schedule-tab) is configured, inactive segments have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.</span></span> <span data-ttu-id="0aae3-160">Khi phân khúc không hoạt động được kích hoạt, mục đó sẽ được làm mới và được đưa vào các lần làm mới theo lịch trình.</span><span class="sxs-lookup"><span data-stu-id="0aae3-160">When an inactive segment is activated, it will refresh and will be included in scheduled refreshes.</span></span>
  <span data-ttu-id="0aae3-161">Ngoài ra, bạn cũng có thể dùng chức năng **Lên lịch sau** trong menu thả xuống **Kích hoạt/Hủy kích hoạt** để xác định ngày giờ kích hoạt và hủy kích hoạt trong tương lai của một phân khúc cụ thể.</span><span class="sxs-lookup"><span data-stu-id="0aae3-161">Alternatively, you can use the **Schedule later** functionality in the **Activate/Deactivate** dropdown to specify a future date and time for activation and deactivation of a particular segment.</span></span>
- <span data-ttu-id="0aae3-162">**Đổi tên** phân đoạn.</span><span class="sxs-lookup"><span data-stu-id="0aae3-162">**Rename** the segment.</span></span>
- <span data-ttu-id="0aae3-163">**Tải xuống** danh sách thành viên dưới dạng tệp .CSV.</span><span class="sxs-lookup"><span data-stu-id="0aae3-163">**Download** the list of members as a .CSV file.</span></span>
- <span data-ttu-id="0aae3-164">Tùy chọn **Thêm vào** sẽ gửi danh sách ID khách hàng trong phân khúc để xử lý trong một ứng dụng khác.</span><span class="sxs-lookup"><span data-stu-id="0aae3-164">**Add to** option sends the list of customer IDs in the segment for processing in another application.</span></span>
- <span data-ttu-id="0aae3-165">**Xóa** phân đoạn.</span><span class="sxs-lookup"><span data-stu-id="0aae3-165">**Delete** the segment.</span></span>

## <a name="refresh-segments"></a><span data-ttu-id="0aae3-166">Làm mới phân đoạn</span><span class="sxs-lookup"><span data-stu-id="0aae3-166">Refresh segments</span></span>

<span data-ttu-id="0aae3-167">Bạn có thể làm mới tất cả phân phúc cùng lúc bằng cách chọn **Làm mới tất cả** trên trang **Phân khúc** hoặc bạn có thể làm mới một hoặc nhiều phân khúc khi chọn và chọn **Làm mới** từ các tùy chọn.</span><span class="sxs-lookup"><span data-stu-id="0aae3-167">You can refresh all segments at once by selecting **Refresh all** on the **Segments** page or you can refresh one or multiple segments when you select them and choose **Refresh** in from the options.</span></span> <span data-ttu-id="0aae3-168">Hoặc, bạn có thể đặt cấu hình làm mới lặp lại trên **Quản trị viên** > **Hệ thống** > **Lịch trình**.</span><span class="sxs-lookup"><span data-stu-id="0aae3-168">Alternatively, you can configure a recurring refresh on **Admin** > **System** > **Schedule**.</span></span>

> [!TIP]
> <span data-ttu-id="0aae3-169">Có [6 loại trạng thái](system.md#status-types) cho các nhiệm vụ/quy trình.</span><span class="sxs-lookup"><span data-stu-id="0aae3-169">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="0aae3-170">Ngoài ra, hầu hết các quy trình [phụ thuộc vào các quá trình hạ nguồn khác](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="0aae3-170">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="0aae3-171">Bạn có thể chọn trạng thái của một quy trình để xem chi tiết về tiến trình của toàn bộ công việc.</span><span class="sxs-lookup"><span data-stu-id="0aae3-171">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="0aae3-172">Sau khi chọn **Xem chi tiết** đối với một trong các tác vụ của công việc, bạn sẽ tìm thấy thông tin bổ sung: thời gian xử lý, ngày xử lý gần nhất và tất cả các lỗi và cảnh báo liên quan đến tác vụ.</span><span class="sxs-lookup"><span data-stu-id="0aae3-172">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="download-and-export-segments"></a><span data-ttu-id="0aae3-173">Tải xuống và xuất phân đoạn</span><span class="sxs-lookup"><span data-stu-id="0aae3-173">Download and export segments</span></span>

<span data-ttu-id="0aae3-174">Bạn có thể tải xuống các phân đoạn của mình vào tệp CSV hoặc xuất chúng sang Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="0aae3-174">You can download your segments to a CSV file or export them to Dynamics 365 Sales.</span></span>

### <a name="download-segments-to-a-csv-file"></a><span data-ttu-id="0aae3-175">Tải xuống các phân đoạn vào tệp CSV</span><span class="sxs-lookup"><span data-stu-id="0aae3-175">Download segments to a CSV file</span></span>

1. <span data-ttu-id="0aae3-176">Trong thông tin chi tiết về đối tượng, hãy chuyển đến trang **Phân khúc**.</span><span class="sxs-lookup"><span data-stu-id="0aae3-176">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="0aae3-177">Chọn dấu chấm lửng trong ngăn xếp của một phân đoạn cụ thể.</span><span class="sxs-lookup"><span data-stu-id="0aae3-177">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="0aae3-178">Chọn **Tải xuống dưới dạng CSV** từ danh sách thả xuống hành động.</span><span class="sxs-lookup"><span data-stu-id="0aae3-178">Select **Download as CSV** from the actions drop-down list.</span></span>

### <a name="export-segments-to-dynamics-365-sales"></a><span data-ttu-id="0aae3-179">Xuất phân đoạn sang Dynamics 365 Sales</span><span class="sxs-lookup"><span data-stu-id="0aae3-179">Export segments to Dynamics 365 Sales</span></span>

<span data-ttu-id="0aae3-180">Trước khi xuất phân đoạn sang Dynamics 365 Sales, quản trị viên cần phải [tạo đích xuất](export-destinations.md) cho Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="0aae3-180">Before exporting segments to Dynamics 365 Sales, an admin needs to [create the export destination](export-destinations.md) for Dynamics 365 Sales.</span></span>

1. <span data-ttu-id="0aae3-181">Trong thông tin chi tiết về đối tượng, hãy chuyển đến trang **Phân khúc**.</span><span class="sxs-lookup"><span data-stu-id="0aae3-181">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="0aae3-182">Chọn dấu chấm lửng trong ngăn xếp của một phân đoạn cụ thể.</span><span class="sxs-lookup"><span data-stu-id="0aae3-182">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="0aae3-183">Chọn **Thêm vào** từ danh sách hành động thả xuống và chọn đích xuất bạn muốn gửi dữ liệu vào.</span><span class="sxs-lookup"><span data-stu-id="0aae3-183">Select **Add to** from the actions drop-down list and select the export destination you want to send the data to.</span></span>

## <a name="draft-mode-for-segments"></a><span data-ttu-id="0aae3-184">Chế độ bản nháp cho phân đoạn</span><span class="sxs-lookup"><span data-stu-id="0aae3-184">Draft mode for segments</span></span>

<span data-ttu-id="0aae3-185">Nếu không đáp ứng tất cả các yêu cầu để xử lý phân đoạn, bạn có thể lưu phân đoạn dưới dạng bản nháp và truy cập từ trang **Phân đoạn**.</span><span class="sxs-lookup"><span data-stu-id="0aae3-185">If not all requirements to process a segment are met, you can save the segment as a draft and access it from the **Segments** page.</span></span>

<span data-ttu-id="0aae3-186">Phân đoạn sẽ được lưu dưới dạng phân đoạn không hoạt động và không bật được cho tới khi có hiệu lực.</span><span class="sxs-lookup"><span data-stu-id="0aae3-186">It will be saved as an inactive segment, and can't be activated it until it's valid.</span></span>

## <a name="add-more-conditions-to-a-group"></a><span data-ttu-id="0aae3-187">Thêm nhiều điều kiện cho một nhóm</span><span class="sxs-lookup"><span data-stu-id="0aae3-187">Add more conditions to a group</span></span>

<span data-ttu-id="0aae3-188">Để thêm nhiều điều kiện vào một nhóm, bạn có thể sử dụng hai toán tử logic:</span><span class="sxs-lookup"><span data-stu-id="0aae3-188">To add more conditions to a group, you can use two logical operators:</span></span>

- <span data-ttu-id="0aae3-189">Toán tử **AND**: Cả hai điều kiện phải được thỏa mãn như một phần của quá trình tạo phân đoạn.</span><span class="sxs-lookup"><span data-stu-id="0aae3-189">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="0aae3-190">Tùy chọn này hữu ích nhất khi bạn xác định các điều kiện trên các thực thể khác nhau.</span><span class="sxs-lookup"><span data-stu-id="0aae3-190">This option is most useful when you define conditions across different entities.</span></span>

- <span data-ttu-id="0aae3-191">Toán tử **OR**: Một trong các điều kiện cần phải được thỏa mãn như một phần của quá trình tạo phân đoạn.</span><span class="sxs-lookup"><span data-stu-id="0aae3-191">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="0aae3-192">Tùy chọn này hữu ích nhất khi bạn xác định nhiều điều kiện cho cùng một thực thể.</span><span class="sxs-lookup"><span data-stu-id="0aae3-192">This option is most useful when you define multiple conditions for the same entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0aae3-193">![Toán tử OR trong đó một trong hai điều kiện cần phải được thỏa mãn](media/segmentation-either-condition.png "Toán tử OR trong đó một trong hai điều kiện cần phải được thỏa mãn")</span><span class="sxs-lookup"><span data-stu-id="0aae3-193">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

<span data-ttu-id="0aae3-194">Hiện tại, có thể lồng một toán tử **OR** trong toán tử **AND** nhưng không phải là ngược lại.</span><span class="sxs-lookup"><span data-stu-id="0aae3-194">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

## <a name="combine-multiple-groups"></a><span data-ttu-id="0aae3-195">Kết hợp nhiều nhóm</span><span class="sxs-lookup"><span data-stu-id="0aae3-195">Combine multiple groups</span></span>

<span data-ttu-id="0aae3-196">Mỗi nhóm tạo một nhóm khách hàng cụ thể.</span><span class="sxs-lookup"><span data-stu-id="0aae3-196">Each group produces a specific set of customers.</span></span> <span data-ttu-id="0aae3-197">Bạn có thể kết hợp các nhóm này để bao gồm các khách hàng cần thiết cho trường hợp công việc của bạn.</span><span class="sxs-lookup"><span data-stu-id="0aae3-197">You can combine these groups to include the customers required for your business case.</span></span>

1. <span data-ttu-id="0aae3-198">Trong thông tin chi tiết về đối tượng, hãy chuyển đến trang **Phân khúc** và chọn một phân khúc.</span><span class="sxs-lookup"><span data-stu-id="0aae3-198">In audience insights, go to the **Segments** page and select a segment.</span></span>

2. <span data-ttu-id="0aae3-199">Chọn **Thêm nhóm**.</span><span class="sxs-lookup"><span data-stu-id="0aae3-199">Select **Add Group**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0aae3-200">![Thêm nhóm khách hàng](media/customer-group-add-group.png "Thêm nhóm khách hàng")</span><span class="sxs-lookup"><span data-stu-id="0aae3-200">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

3. <span data-ttu-id="0aae3-201">Chọn một trong các toán tử tập hợp sau: **Liên hiệp**, **Giao nhau** hoặc **Ngoại trừ**.</span><span class="sxs-lookup"><span data-stu-id="0aae3-201">Select one of the following set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0aae3-202">![Thêm tập hợp nhóm khách hàng](media/customer-group-union.png "Thêm tập hợp nhóm khách hàng")</span><span class="sxs-lookup"><span data-stu-id="0aae3-202">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   <span data-ttu-id="0aae3-203">Chọn một toán tử bộ để xác định nhóm mới.</span><span class="sxs-lookup"><span data-stu-id="0aae3-203">Select a set operator to define a new group.</span></span> <span data-ttu-id="0aae3-204">Lưu các nhóm khác nhau để quyết định dữ liệu gì được giữ lại:</span><span class="sxs-lookup"><span data-stu-id="0aae3-204">Save different groups to determine what data gets retained:</span></span>

   - <span data-ttu-id="0aae3-205">**Hợp nhất** sẽ hợp nhất hai nhóm với nhau.</span><span class="sxs-lookup"><span data-stu-id="0aae3-205">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="0aae3-206">**Giao nhau** sẽ chồng chéo hai nhóm với nhau.</span><span class="sxs-lookup"><span data-stu-id="0aae3-206">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="0aae3-207">Chỉ dữ liệu *là phổ biến* cho cả hai nhóm được giữ lại trong nhóm hợp nhất.</span><span class="sxs-lookup"><span data-stu-id="0aae3-207">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="0aae3-208">**Trừ** kết hợp hai nhóm với nhau.</span><span class="sxs-lookup"><span data-stu-id="0aae3-208">**Except** combines the two groups.</span></span> <span data-ttu-id="0aae3-209">Chỉ dữ liệu trong nhóm A *là không phổ biến* cho dữ liệu trong nhóm B được giữ lại.</span><span class="sxs-lookup"><span data-stu-id="0aae3-209">Only data in group A that *is not common* to data in group B is retained.</span></span>

## <a name="view-processing-history-and-segment-members"></a><span data-ttu-id="0aae3-210">Xem lịch sử xử lý và các thành phần trong phân đoạn</span><span class="sxs-lookup"><span data-stu-id="0aae3-210">View processing history and segment members</span></span>

<span data-ttu-id="0aae3-211">Bạn có thể xem dữ liệu tổng hợp về một phân đoạn bằng cách xem lại chi tiết của phân đoạn đó.</span><span class="sxs-lookup"><span data-stu-id="0aae3-211">You can see consolidated data about a segment by reviewing its details.</span></span>

<span data-ttu-id="0aae3-212">Trên trang **Phân đoạn**, chọn phân đoạn bạn muốn xem lại.</span><span class="sxs-lookup"><span data-stu-id="0aae3-212">On the **Segments** page, select the segment you want to review.</span></span>

<span data-ttu-id="0aae3-213">Phần trên của trang bao gồm một biểu đồ xu hướng nhằm trực quan hóa những thay đổi về số lượng thành phần.</span><span class="sxs-lookup"><span data-stu-id="0aae3-213">The upper part of the page includes a trend graph that visualizes changes in member count.</span></span> <span data-ttu-id="0aae3-214">Di chuột qua các điểm dữ liệu để xem số lượng thành phần trong một ngày cụ thể.</span><span class="sxs-lookup"><span data-stu-id="0aae3-214">Hover over data points to see the member count on a specific date.</span></span>

<span data-ttu-id="0aae3-215">Bạn có thể cập nhật khung thời gian của trực quan hóa.</span><span class="sxs-lookup"><span data-stu-id="0aae3-215">You can update the time frame of the visualization.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0aae3-216">![Khoảng thời gian phân đoạn](media/segment-time-range.png "Khoảng thời gian phân đoạn")</span><span class="sxs-lookup"><span data-stu-id="0aae3-216">![Segment time range](media/segment-time-range.png "Segment time range")</span></span>

<span data-ttu-id="0aae3-217">Phần dưới chứa danh sách các thành phần phân đoạn.</span><span class="sxs-lookup"><span data-stu-id="0aae3-217">The lower part contains a list of the segment members.</span></span>

> [!NOTE]
> <span data-ttu-id="0aae3-218">Các trường xuất hiện trong danh sách này dựa trên các thuộc tính của các thực thể trong phân đoạn của bạn.</span><span class="sxs-lookup"><span data-stu-id="0aae3-218">Fields that appear in this list are based on the attributes of your segment's entities.</span></span>
>
><span data-ttu-id="0aae3-219">Danh sách này là bản xem trước của các thành phần phân đoạn phù hợp và hiển thị 100 bản ghi đầu tiên của phân đoạn, từ đó bạn có thể đánh giá nhanh và xem lại định nghĩa nếu cần.</span><span class="sxs-lookup"><span data-stu-id="0aae3-219">The list is a preview of the matching segment members and shows the first 100 records of your segment so that you can quickly evaluate it and review its definitions if needed.</span></span> <span data-ttu-id="0aae3-220">Để xem tất cả các hồ sơ phù hợp, bạn cần [xuất phân đoạn](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="0aae3-220">To see all matching records, you need to [export the segment](export-destinations.md).</span></span>

## <a name="quick-segments"></a><span data-ttu-id="0aae3-221">Phân đoạn nhanh</span><span class="sxs-lookup"><span data-stu-id="0aae3-221">Quick segments</span></span>

<span data-ttu-id="0aae3-222">Ngoài trình tạo phân khúc, có một đường dẫn khác để tạo phân khúc.</span><span class="sxs-lookup"><span data-stu-id="0aae3-222">In addition to the segment builder, there's another path for creating segments.</span></span> <span data-ttu-id="0aae3-223">Phân khúc nhanh cho phép bạn xây dựng các phân khúc đơn giản (với một toán tử) nhanh chóng và có thông tin chuyên sâu tức thì.</span><span class="sxs-lookup"><span data-stu-id="0aae3-223">Quick segments let you build simple segments with a single operator quickly and with instant insights.</span></span>

1. <span data-ttu-id="0aae3-224">Trên trang **Phân đoạn**, hãy chọn **Mới** > **Tạo nhanh từ**.</span><span class="sxs-lookup"><span data-stu-id="0aae3-224">On the **Segments** page, select **New** > **Quickly create from**.</span></span>

   - <span data-ttu-id="0aae3-225">Chọn **Hồ sơ** để xây dựng phân đoạn dựa trên thực thể Khách hàng hợp nhất.</span><span class="sxs-lookup"><span data-stu-id="0aae3-225">Select the **Profiles** option to build a segment that is based on the unified Customer entity.</span></span>
   - <span data-ttu-id="0aae3-226">Chọn **Số liệu đo lường** để xây dựng phân đoạn xung quanh từng loại số liệu đo lường của Thuộc tính khách hàng mà bạn đã tạo trên trang **Giá trị đo lường**.</span><span class="sxs-lookup"><span data-stu-id="0aae3-226">Select the **Measures** option to build a segment around each of the Customer Attribute type of measures you have previously created on the **Measures** page.</span></span>
   - <span data-ttu-id="0aae3-227">Chọn tùy chọn **Thông tin** để xây dựng một phân đoạn xung quanh một trong các thực thể đầu ra mà bạn tạo bằng một trong hai chức năng **Dự đoán** hoặc **Mô hình tùy chỉnh**.</span><span class="sxs-lookup"><span data-stu-id="0aae3-227">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="0aae3-228">Trong hộp thoại **Phân đoạn nhanh mới**, hãy chọn một thuộc tính từ mục thả xuống **Trường**.</span><span class="sxs-lookup"><span data-stu-id="0aae3-228">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="0aae3-229">Hệ thống sẽ cung cấp thêm một số thông tin chi tiết để giúp bạn tạo các phân đoạn khách hàng tốt hơn.</span><span class="sxs-lookup"><span data-stu-id="0aae3-229">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="0aae3-230">Đối với các trường có phân loại, chúng tôi sẽ hiển thị 10 lượt khách hàng tốt nhất.</span><span class="sxs-lookup"><span data-stu-id="0aae3-230">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="0aae3-231">Chọn **Giá trị** rồi chọn **Xem lại**.</span><span class="sxs-lookup"><span data-stu-id="0aae3-231">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="0aae3-232">Đối với một thuộc tính số, hệ thống sẽ hiển thị giá trị thuộc tính nào nằm trong phần trăm của mỗi khách hàng.</span><span class="sxs-lookup"><span data-stu-id="0aae3-232">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="0aae3-233">Chọn một **Toán tử** và một **Giá trị**, sau đó chọn **Xem lại**.</span><span class="sxs-lookup"><span data-stu-id="0aae3-233">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="0aae3-234">Hệ thống sẽ cung cấp cho bạn một **Kích cỡ phân đoạn ước tính**.</span><span class="sxs-lookup"><span data-stu-id="0aae3-234">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="0aae3-235">Bạn có thể chọn tạo phân đoạn bạn đã xác định hoặc truy cập lại vào phân đoạn đó để có kích cỡ phân đoạn khác.</span><span class="sxs-lookup"><span data-stu-id="0aae3-235">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0aae3-236">![Tên và ước tính cho một phân đoạn nhanh](media/quick-segment-name.png "Tên và ước tính cho một phân đoạn nhanh")</span><span class="sxs-lookup"><span data-stu-id="0aae3-236">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="0aae3-237">Đặt **Tên** cho phân đoạn của bạn.</span><span class="sxs-lookup"><span data-stu-id="0aae3-237">Provide a **Name** for your segment.</span></span> <span data-ttu-id="0aae3-238">Bạn cũng có thể cung cấp **Tên hiển thị**.</span><span class="sxs-lookup"><span data-stu-id="0aae3-238">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="0aae3-239">Chọn **Lưu** để tạo phân đoạn.</span><span class="sxs-lookup"><span data-stu-id="0aae3-239">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="0aae3-240">Sau khi phân đoạn đã xử lý xong, bạn có thể xem nó như bất kỳ phân đoạn nào khác mà bạn đã tạo.</span><span class="sxs-lookup"><span data-stu-id="0aae3-240">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

<span data-ttu-id="0aae3-241">Đối với các tình huống sau, bạn nên sử dụng trình tạo phân đoạn thay vì chức năng phân đoạn được đề xuất:</span><span class="sxs-lookup"><span data-stu-id="0aae3-241">For the following scenarios, we advise using the segment builder rather than the recommended segments capability:</span></span>

- <span data-ttu-id="0aae3-242">Tạo các phân đoạn với các bộ lọc trên các trường phân loại trong đó toán tử không phải là toán tử **Is**</span><span class="sxs-lookup"><span data-stu-id="0aae3-242">Creating segments with filters on categorical fields where the operator is different than the **Is** operator</span></span>
- <span data-ttu-id="0aae3-243">Tạo các phân đoạn với các bộ lọc trên các trường số trong đó toán tử không phải là **Between**, **Greater than** và **Less than**</span><span class="sxs-lookup"><span data-stu-id="0aae3-243">Creating segments with filters on numerical fields where the operator is different than the **Between**, **Greater than**, and **Less than** operators</span></span>
- <span data-ttu-id="0aae3-244">Tạo phân đoạn với các bộ lọc trên các trường loại ngày</span><span class="sxs-lookup"><span data-stu-id="0aae3-244">Creating segments with filters on date type fields</span></span>

## <a name="next-steps"></a><span data-ttu-id="0aae3-245">Bước tiếp theo</span><span class="sxs-lookup"><span data-stu-id="0aae3-245">Next steps</span></span>

<span data-ttu-id="0aae3-246">[Xuất phân đoạn](export-destinations.md) và khám phá [Thẻ khách hàng](customer-card-add-in.md) và [Bộ kết nối](export-power-bi.md) để nắm được thông tin chi tiết ở cấp độ khách hàng.</span><span class="sxs-lookup"><span data-stu-id="0aae3-246">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]