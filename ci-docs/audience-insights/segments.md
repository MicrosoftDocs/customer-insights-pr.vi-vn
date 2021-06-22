---
title: Phân khúc trong thông tin chuyên sâu về đối tượng
description: Tổng quan, cách tạo và quản lý phân khúc.
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 6cb7bd62bf0f61e6dc5811b20e5011e4a086c743
ms.sourcegitcommit: 84283d523a891298fca8aaf629d9f9ab2a1bc067
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 05/27/2021
ms.locfileid: "6111413"
---
# <a name="segments-overview"></a><span data-ttu-id="3c418-103">Tổng quan về phân khúc</span><span class="sxs-lookup"><span data-stu-id="3c418-103">Segments overview</span></span>

<span data-ttu-id="3c418-104">Phân khúc cho phép bạn nhóm khách hàng của mình dựa trên các thuộc tính nhân khẩu học, giao dịch hoặc hành vi.</span><span class="sxs-lookup"><span data-stu-id="3c418-104">Segments let you group your customers based on demographic, transactional, or behavioral attributes.</span></span> <span data-ttu-id="3c418-105">Bạn có thể sử dụng các phân khúc để nhắm mục tiêu chiến dịch quảng cáo, hoạt động bán hàng và hành động hỗ trợ khách hàng để đạt được mục tiêu kinh doanh.</span><span class="sxs-lookup"><span data-stu-id="3c418-105">You can use segments to target promotional campaigns, sales activities, and customer support actions to achieve your business goals.</span></span>

<span data-ttu-id="3c418-106">Hồ sơ khách hàng phù hợp với các bộ lọc của định nghĩa phân khúc được gọi là *các thành viên* của một phân khúc.</span><span class="sxs-lookup"><span data-stu-id="3c418-106">Customer profiles that match the filters of a segment definition are referred as *members* of a segment.</span></span> <span data-ttu-id="3c418-107">Một số [giới hạn dịch vụ](service-limits.md) được áp dụng.</span><span class="sxs-lookup"><span data-stu-id="3c418-107">Some [service limits](service-limits.md) apply.</span></span>

## <a name="create-a-new-segment"></a><span data-ttu-id="3c418-108">Tạo phân khúc mới</span><span class="sxs-lookup"><span data-stu-id="3c418-108">Create a new segment</span></span>

<span data-ttu-id="3c418-109">Có nhiều cách để tạo một phân khúc mới:</span><span class="sxs-lookup"><span data-stu-id="3c418-109">There are multiple ways to create a new segment:</span></span> 

- <span data-ttu-id="3c418-110">Phân khúc phức tạp với trình tạo phân khúc: [Phân khúc trống](segment-builder.md#create-a-new-segment)</span><span class="sxs-lookup"><span data-stu-id="3c418-110">Complex segment with segment builder: [Blank segment](segment-builder.md#create-a-new-segment)</span></span>
- <span data-ttu-id="3c418-111">Các phân khúc đơn giản với một toán tử: [Phân khúc nhanh](segment-builder.md#quick-segments)</span><span class="sxs-lookup"><span data-stu-id="3c418-111">Simple segments with one operator: [Quick segment](segment-builder.md#quick-segments)</span></span>
- <span data-ttu-id="3c418-112">Cách tìm khách hàng tương tự dựa trên AI: [Khách hàng tương tự](find-similar-customer-segments.md)</span><span class="sxs-lookup"><span data-stu-id="3c418-112">AI-powered way to find similar customers: [Similar Customers](find-similar-customer-segments.md)</span></span>
- <span data-ttu-id="3c418-113">Đề xuất do AI hỗ trợ dựa trên các biện pháp hoặc thuộc tính: [Các phân khúc được đề xuất nhằm cải thiện các biện pháp](suggested-segments.md)</span><span class="sxs-lookup"><span data-stu-id="3c418-113">AI-powered suggestions based on measures or attributes: [Suggested segments to improve measures](suggested-segments.md)</span></span>
- <span data-ttu-id="3c418-114">Đề xuất dựa trên các hoạt động: [Các phân khúc được đề xuất dựa trên hoạt động của khách hàng](suggested-segments-activity.md)</span><span class="sxs-lookup"><span data-stu-id="3c418-114">Suggestions based on activities: [Suggested segments based on customer activity](suggested-segments-activity.md)</span></span>

## <a name="manage-existing-segments"></a><span data-ttu-id="3c418-115">Quản lý các phân khúc hiện có</span><span class="sxs-lookup"><span data-stu-id="3c418-115">Manage existing segments</span></span>

<span data-ttu-id="3c418-116">Chuyển tới trang **Phân khúc** để xem và quản lý tất cả các phân khúc đã lưu của bạn.</span><span class="sxs-lookup"><span data-stu-id="3c418-116">Go to the **Segments** page, to view all your saved segments and manage them.</span></span>

<span data-ttu-id="3c418-117">Mỗi phân khúc được đại diện bởi một hàng bao gồm thông tin bổ sung về phân khúc.</span><span class="sxs-lookup"><span data-stu-id="3c418-117">Each segment is represented by a row that includes additional information about the segment.</span></span>

:::image type="content" source="media/segments-selected-segment.png" alt-text="Phân khúc đã chọn với danh sách tùy chọn thả xuống và các tùy chọn có sẵn.":::

<span data-ttu-id="3c418-119">Hành động sau đây khả dụng khi bạn chọn một phân khúc:</span><span class="sxs-lookup"><span data-stu-id="3c418-119">The following action are available when you select a segment:</span></span>

- <span data-ttu-id="3c418-120">**Xem** chi tiết phân khúc, bao gồm xu hướng số lượng thành viên của một bản xem trước thành phần phân khúc.</span><span class="sxs-lookup"><span data-stu-id="3c418-120">**View** the segment details, including member count trend a preview of segment members.</span></span>
- <span data-ttu-id="3c418-121">**Chỉnh sửa** phân khúc để thay đổi các thuộc tính của phân khúc đó.</span><span class="sxs-lookup"><span data-stu-id="3c418-121">**Edit** the segment to change its properties.</span></span>
- <span data-ttu-id="3c418-122">**Tạo bản sao** của một phân khúc.</span><span class="sxs-lookup"><span data-stu-id="3c418-122">**Create duplicate** of a segment.</span></span> <span data-ttu-id="3c418-123">Bạn có thể chọn chỉnh sửa các thuộc tính của nó ngay lập tức hoặc chỉ cần lưu bản sao.</span><span class="sxs-lookup"><span data-stu-id="3c418-123">You can choose to edit its properties right away or simply save the duplicate.</span></span>
- <span data-ttu-id="3c418-124">**Làm mới** phân khúc để bao gồm dữ liệu mới nhất.</span><span class="sxs-lookup"><span data-stu-id="3c418-124">**Refresh** the segment to include the latest data.</span></span>
- <span data-ttu-id="3c418-125">**Kích hoạt** hoặc **Hủy kích hoạt** phân khúc.</span><span class="sxs-lookup"><span data-stu-id="3c418-125">**Activate** or **Deactivate** the segment.</span></span> <span data-ttu-id="3c418-126">Các phân khúc có thể có hai trạng thái: hiện hoạt hoặc không hoạt động.</span><span class="sxs-lookup"><span data-stu-id="3c418-126">Segments have two possible states - active or inactive.</span></span> <span data-ttu-id="3c418-127">Các trạng thái này rất hữu ích khi bạn chỉnh sửa phân khúc.</span><span class="sxs-lookup"><span data-stu-id="3c418-127">These states come in handy when editing a segment.</span></span> <span data-ttu-id="3c418-128">Đối với các phân khúc không hoạt động, định nghĩa phân khúc tồn tại nhưng phân khúc chưa chứa bất kỳ khách hàng nào.</span><span class="sxs-lookup"><span data-stu-id="3c418-128">For inactive segments, the segment definition exists but it doesn't contain any customers yet.</span></span> <span data-ttu-id="3c418-129">Khi bạn kích hoạt một phân khúc, phân khúc sẽ thay đổi trạng thái từ "không hoạt động" thành "hiện hoạt" và bắt đầu tìm kiếm khách hàng phù hợp với định nghĩa phân khúc.</span><span class="sxs-lookup"><span data-stu-id="3c418-129">When you activate a segment, its state changes from 'inactive' to 'active" and it starts looking for customers that match the segment definition.</span></span> <span data-ttu-id="3c418-130">Nếu hoạt động [làm mới theo lịch trình](system.md#schedule-tab) được đặt cấu hình, thì các phân khúc không hoạt động sẽ có **Trạng thái** là **Đã bỏ qua**, biểu thị việc làm mới chưa được thực hiện.</span><span class="sxs-lookup"><span data-stu-id="3c418-130">If a [scheduled refresh](system.md#schedule-tab) is configured, inactive segments have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.</span></span> <span data-ttu-id="3c418-131">Khi phân khúc không hoạt động được kích hoạt, mục đó sẽ được làm mới và được đưa vào các lần làm mới theo lịch trình.</span><span class="sxs-lookup"><span data-stu-id="3c418-131">When an inactive segment is activated, it will refresh and will be included in scheduled refreshes.</span></span>
  <span data-ttu-id="3c418-132">Ngoài ra, bạn cũng có thể dùng chức năng **Lên lịch sau** trong menu thả xuống **Kích hoạt/Hủy kích hoạt** để xác định ngày giờ kích hoạt và hủy kích hoạt trong tương lai của một phân khúc cụ thể.</span><span class="sxs-lookup"><span data-stu-id="3c418-132">Alternatively, you can use the **Schedule later** functionality in the **Activate/Deactivate** dropdown to specify a future date and time for activation and deactivation of a particular segment.</span></span>
- <span data-ttu-id="3c418-133">**Đổi tên** phân khúc.</span><span class="sxs-lookup"><span data-stu-id="3c418-133">**Rename** the segment.</span></span>
- <span data-ttu-id="3c418-134">**Tải xuống** danh sách thành viên dưới dạng tệp .CSV.</span><span class="sxs-lookup"><span data-stu-id="3c418-134">**Download** the list of members as a .CSV file.</span></span>
- <span data-ttu-id="3c418-135">**Quản lý nội dung xuất** để xem và quản lý phân khúc liên quan đến nội dung xuất.</span><span class="sxs-lookup"><span data-stu-id="3c418-135">**Manage exports** to see exports related segment and manage them.</span></span> [<span data-ttu-id="3c418-136">Tìm hiểu thêm về nội dung xuất.</span><span class="sxs-lookup"><span data-stu-id="3c418-136">Learn more about exports.</span></span>](export-destinations.md)
- <span data-ttu-id="3c418-137">**Xóa** phân khúc.</span><span class="sxs-lookup"><span data-stu-id="3c418-137">**Delete** the segment.</span></span>

## <a name="refresh-segments"></a><span data-ttu-id="3c418-138">Làm mới phân khúc</span><span class="sxs-lookup"><span data-stu-id="3c418-138">Refresh segments</span></span>

<span data-ttu-id="3c418-139">Bạn có thể làm mới tất cả phân phúc cùng lúc bằng cách chọn **Làm mới tất cả** trên trang **Phân khúc** hoặc bạn có thể làm mới một hoặc nhiều phân khúc khi chọn và chọn **Làm mới** từ các tùy chọn.</span><span class="sxs-lookup"><span data-stu-id="3c418-139">You can refresh all segments at once by selecting **Refresh all** on the **Segments** page or you can refresh one or multiple segments when you select them and choose **Refresh** in from the options.</span></span> <span data-ttu-id="3c418-140">Hoặc, bạn có thể đặt cấu hình làm mới lặp lại trên **Quản trị viên** > **Hệ thống** > **Lịch trình**.</span><span class="sxs-lookup"><span data-stu-id="3c418-140">Alternatively, you can configure a recurring refresh on **Admin** > **System** > **Schedule**.</span></span>

> [!TIP]
> <span data-ttu-id="3c418-141">Có [6 loại trạng thái](system.md#status-types) cho các nhiệm vụ/quy trình.</span><span class="sxs-lookup"><span data-stu-id="3c418-141">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="3c418-142">Ngoài ra, hầu hết các quy trình [phụ thuộc vào các quá trình hạ nguồn khác](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="3c418-142">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="3c418-143">Bạn có thể chọn trạng thái của một quy trình để xem chi tiết về tiến trình của toàn bộ công việc.</span><span class="sxs-lookup"><span data-stu-id="3c418-143">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="3c418-144">Sau khi chọn **Xem chi tiết** đối với một trong các tác vụ của công việc, bạn sẽ tìm thấy thông tin bổ sung: thời gian xử lý, ngày xử lý gần nhất và tất cả các lỗi và cảnh báo liên quan đến tác vụ.</span><span class="sxs-lookup"><span data-stu-id="3c418-144">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="export-segments"></a><span data-ttu-id="3c418-145">Xuất phân khúc</span><span class="sxs-lookup"><span data-stu-id="3c418-145">Export segments</span></span>

<span data-ttu-id="3c418-146">Bạn có thể xuất một phân khúc từ trang phân khúc hoặc [trang nội dung xuất](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="3c418-146">You can export a segment from the segments page or the [exports page](export-destinations.md).</span></span> 

1. <span data-ttu-id="3c418-147">Chuyển đến trang **Phân khúc**.</span><span class="sxs-lookup"><span data-stu-id="3c418-147">Go to the **Segments** page.</span></span>

1. <span data-ttu-id="3c418-148">Chọn **Hiển thị thêm [...]** cho phân khúc bạn muốn xuất.</span><span class="sxs-lookup"><span data-stu-id="3c418-148">Select **Show more [...]** for the segment you want to export.</span></span>

1. <span data-ttu-id="3c418-149">Chọn **Quản lý nội dung xuất** từ danh sách hành động thả xuống.</span><span class="sxs-lookup"><span data-stu-id="3c418-149">Select **Manage exports** from the actions drop-down list.</span></span>

1. <span data-ttu-id="3c418-150">Trang **Nội dung xuất (xem trước) cho phân khúc** sẽ mở ra.</span><span class="sxs-lookup"><span data-stu-id="3c418-150">The page **Exports (preview) for segment** opens.</span></span> <span data-ttu-id="3c418-151">Bạn có thể xem tất cả các nội dung xuất đã đặt cấu hình, được nhóm theo nội dung xuất có chứa hoặc không chứa phân khúc hiện tại.</span><span class="sxs-lookup"><span data-stu-id="3c418-151">You can see all configured exports grouped by by exports that contain the current segment or don't contain it.</span></span>

   1. <span data-ttu-id="3c418-152">Để thêm phân khúc đã chọn vào một nội dung xuất, hãy chọn nội dung xuất trong danh sách rồi chọn **Thêm phân khúc**.</span><span class="sxs-lookup"><span data-stu-id="3c418-152">To add the selected segment to an export, select the export in the list and select **Add segment**.</span></span>

   1. <span data-ttu-id="3c418-153">Để tạo nội dung xuất mới bằng phân khúc đã chọn, hãy chọn **Thêm nội dung xuất**.</span><span class="sxs-lookup"><span data-stu-id="3c418-153">To create a new export with the selected segment, select **Add export**.</span></span> <span data-ttu-id="3c418-154">Để biết thêm thông tin về cách tạo nội dung xuất, hãy xem phần [Thiết lập nội dung xuất mới](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="3c418-154">For more information about creating exports, see [Set up a new export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="3c418-155">Chọn **Quay lại** để quay lại trang chính cho các phân khúc.</span><span class="sxs-lookup"><span data-stu-id="3c418-155">Select **Back** to return to the main page for segments.</span></span>

## <a name="view-processing-history-and-segment-members"></a><span data-ttu-id="3c418-156">Xem lịch sử xử lý và các thành phần phân khúc</span><span class="sxs-lookup"><span data-stu-id="3c418-156">View processing history and segment members</span></span>

<span data-ttu-id="3c418-157">Bạn có thể xem dữ liệu tổng hợp về một phân khúc bằng cách xem lại chi tiết của phân khúc đó.</span><span class="sxs-lookup"><span data-stu-id="3c418-157">You can see consolidated data about a segment by reviewing its details.</span></span>

<span data-ttu-id="3c418-158">Trên trang **Phân khúc**, chọn phân khúc bạn muốn xem lại.</span><span class="sxs-lookup"><span data-stu-id="3c418-158">On the **Segments** page, select the segment you want to review.</span></span>

<span data-ttu-id="3c418-159">Phần trên của trang bao gồm một biểu đồ xu hướng nhằm trực quan hóa những thay đổi về số lượng thành phần.</span><span class="sxs-lookup"><span data-stu-id="3c418-159">The upper part of the page includes a trend graph that visualizes changes in member count.</span></span> <span data-ttu-id="3c418-160">Di chuột qua các điểm dữ liệu để xem số lượng thành phần trong một ngày cụ thể.</span><span class="sxs-lookup"><span data-stu-id="3c418-160">Hover over data points to see the member count on a specific date.</span></span>

<span data-ttu-id="3c418-161">Bạn có thể cập nhật khung thời gian của trực quan hóa.</span><span class="sxs-lookup"><span data-stu-id="3c418-161">You can update the time frame of the visualization.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="3c418-162">![Khoảng thời gian phân khúc](media/segment-time-range.png "Khoảng thời gian phân khúc")</span><span class="sxs-lookup"><span data-stu-id="3c418-162">![Segment time range](media/segment-time-range.png "Segment time range")</span></span>

<span data-ttu-id="3c418-163">Phần dưới chứa danh sách các thành phần phân khúc.</span><span class="sxs-lookup"><span data-stu-id="3c418-163">The lower part contains a list of the segment members.</span></span>

> [!NOTE]
> <span data-ttu-id="3c418-164">Các trường xuất hiện trong danh sách này dựa trên các thuộc tính của các thực thể trong phân khúc của bạn.</span><span class="sxs-lookup"><span data-stu-id="3c418-164">Fields that appear in this list are based on the attributes of your segment's entities.</span></span>
>
><span data-ttu-id="3c418-165">Danh sách này là bản xem trước của các thành phần phân khúc phù hợp và hiển thị 100 bản ghi đầu tiên của phân khúc, từ đó bạn có thể đánh giá nhanh và xem lại định nghĩa nếu cần.</span><span class="sxs-lookup"><span data-stu-id="3c418-165">The list is a preview of the matching segment members and shows the first 100 records of your segment so that you can quickly evaluate it and review its definitions if needed.</span></span> <span data-ttu-id="3c418-166">Để xem tất cả các hồ sơ phù hợp, bạn cần [xuất phân khúc](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="3c418-166">To see all matching records, you need to [export the segment](export-destinations.md).</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)] 
