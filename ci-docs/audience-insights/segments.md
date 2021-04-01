---
title: Tạo và quản lý phân đoạn
description: Tạo phân đoạn khách hàng để nhóm họ lại dựa trên các đặc điểm khác nhau.
ms.date: 03/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 4a6e8a3216a2c0738d60247054afa9fc18412f55
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597089"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="41cb1-103">Tạo và quản lý phân đoạn</span><span class="sxs-lookup"><span data-stu-id="41cb1-103">Create and manage segments</span></span>

<span data-ttu-id="41cb1-104">Phân khúc cho phép bạn nhóm khách hàng của mình dựa trên các thuộc tính nhân khẩu học, giao dịch hoặc hành vi.</span><span class="sxs-lookup"><span data-stu-id="41cb1-104">Segments let you group your customers based on demographic, transactional, or behavioral attributes.</span></span> <span data-ttu-id="41cb1-105">Bạn có thể sử dụng các phân khúc để nhắm mục tiêu chiến dịch quảng cáo, hoạt động bán hàng và hành động hỗ trợ khách hàng để đạt được mục tiêu kinh doanh.</span><span class="sxs-lookup"><span data-stu-id="41cb1-105">You can use segments to target promotional campaigns, sales activities, and customer support actions to achieve your business goals.</span></span>

<span data-ttu-id="41cb1-106">Bạn có thể xác định các bộ lọc phức hợp xung quanh thực thể Hồ sơ khách hàng và các thực thể liên quan.</span><span class="sxs-lookup"><span data-stu-id="41cb1-106">You can define complex filters around the Customer Profile entity and its related entities.</span></span> <span data-ttu-id="41cb1-107">Mỗi phân khúc, sau khi xử lý, sẽ tạo một bộ hồ sơ khách hàng mà bạn có thể xuất và hành động.</span><span class="sxs-lookup"><span data-stu-id="41cb1-107">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="41cb1-108">Một số [giới hạn dịch vụ](service-limits.md) được áp dụng.</span><span class="sxs-lookup"><span data-stu-id="41cb1-108">Some [service limits](service-limits.md) apply.</span></span>

<span data-ttu-id="41cb1-109">Trừ khi có quy định khác, tất cả các phân khúc đều là **Phân khúc động**, được làm mới theo lịch trình định kỳ.</span><span class="sxs-lookup"><span data-stu-id="41cb1-109">Unless stated otherwise, all segments are **Dynamic segments**, which are refreshed on a recurring schedule.</span></span>

<span data-ttu-id="41cb1-110">Ví dụ sau minh họa khả năng tạo phân khúc.</span><span class="sxs-lookup"><span data-stu-id="41cb1-110">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="41cb1-111">Chúng tôi đã xác định một phân đoạn cho khách hàng đặt hàng hóa trị giá ít nhất $500 trong 90 ngày qua *và* đã tham gia vào cuộc gọi dịch vụ khách hàng đã báo cáo.</span><span class="sxs-lookup"><span data-stu-id="41cb1-111">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="41cb1-112">![Nhiều nhóm](media/segmentation-group1-2.png "Nhiều nhóm")</span><span class="sxs-lookup"><span data-stu-id="41cb1-112">![Multiple groups](media/segmentation-group1-2.png "Multiple groups")</span></span>

## <a name="create-a-new-segment"></a><span data-ttu-id="41cb1-113">Tạo phân đoạn mới</span><span class="sxs-lookup"><span data-stu-id="41cb1-113">Create a new segment</span></span>

<span data-ttu-id="41cb1-114">Các phân khúc được quản lý trên trang **Phân khúc**.</span><span class="sxs-lookup"><span data-stu-id="41cb1-114">Segments are managed on the **Segments** page.</span></span>

1. <span data-ttu-id="41cb1-115">Trong thông tin chi tiết về đối tượng, hãy chuyển đến trang **Phân khúc**.</span><span class="sxs-lookup"><span data-stu-id="41cb1-115">In audience insights, go to the **Segments** page.</span></span>

1. <span data-ttu-id="41cb1-116">Chọn **Mới** > **Phân đoạn trống**.</span><span class="sxs-lookup"><span data-stu-id="41cb1-116">Select **New** > **Blank segment**.</span></span>

1. <span data-ttu-id="41cb1-117">Trong ngăn **Phân đoạn mới**, chọn loại phân đoạn và cung cấp **Tên**.</span><span class="sxs-lookup"><span data-stu-id="41cb1-117">In the **New segment** pane, choose a segment type and provide a **Name**.</span></span>

   <span data-ttu-id="41cb1-118">Bạn cũng có thể cung cấp tên hiển thị và mô tả nhằm xác định phân đoạn.</span><span class="sxs-lookup"><span data-stu-id="41cb1-118">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

1. <span data-ttu-id="41cb1-119">Chọn **Tiếp theo** để đi đến trang **Trình tạo phân đoạn** và xác định nhóm.</span><span class="sxs-lookup"><span data-stu-id="41cb1-119">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="41cb1-120">Một nhóm là một tập hợp các khách hàng.</span><span class="sxs-lookup"><span data-stu-id="41cb1-120">A group is a set of customers.</span></span>

1. <span data-ttu-id="41cb1-121">Chọn thực thể bao gồm thuộc tính mà bạn muốn tạo phân đoạn.</span><span class="sxs-lookup"><span data-stu-id="41cb1-121">Choose the entity that includes the attribute you want to segment by.</span></span>

1. <span data-ttu-id="41cb1-122">Chọn thuộc tính để tạo phân đoạn.</span><span class="sxs-lookup"><span data-stu-id="41cb1-122">Choose the attribute to segment by.</span></span> <span data-ttu-id="41cb1-123">Thuộc tính này có thể có 1 trong số 4 loại giá trị: số, chuỗi, ngày hoặc Boolean.</span><span class="sxs-lookup"><span data-stu-id="41cb1-123">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

1. <span data-ttu-id="41cb1-124">Chọn một toán tử và một giá trị cho thuộc tính đã chọn.</span><span class="sxs-lookup"><span data-stu-id="41cb1-124">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="41cb1-125">![Bộ lọc nhóm tùy chỉnh](media/customer-group-numbers.png "Bộ lọc nhóm khách hàng")</span><span class="sxs-lookup"><span data-stu-id="41cb1-125">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="41cb1-126">Số</span><span class="sxs-lookup"><span data-stu-id="41cb1-126">Number</span></span> |<span data-ttu-id="41cb1-127">Định nghĩa</span><span class="sxs-lookup"><span data-stu-id="41cb1-127">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="41cb1-128">1</span><span class="sxs-lookup"><span data-stu-id="41cb1-128">1</span></span>     |<span data-ttu-id="41cb1-129">Entity</span><span class="sxs-lookup"><span data-stu-id="41cb1-129">Entity</span></span>          |
   |<span data-ttu-id="41cb1-130">2</span><span class="sxs-lookup"><span data-stu-id="41cb1-130">2</span></span>     |<span data-ttu-id="41cb1-131">Đặc điểm</span><span class="sxs-lookup"><span data-stu-id="41cb1-131">Attribute</span></span>          |
   |<span data-ttu-id="41cb1-132">3</span><span class="sxs-lookup"><span data-stu-id="41cb1-132">3</span></span>    |<span data-ttu-id="41cb1-133">Toán tử</span><span class="sxs-lookup"><span data-stu-id="41cb1-133">Operator</span></span>         |
   |<span data-ttu-id="41cb1-134">4</span><span class="sxs-lookup"><span data-stu-id="41cb1-134">4</span></span>    |<span data-ttu-id="41cb1-135">Giá trị</span><span class="sxs-lookup"><span data-stu-id="41cb1-135">Value</span></span>         |

8. <span data-ttu-id="41cb1-136">Nếu thực thể được kết nối với thực thể khách hàng hợp nhất qua [các mối quan hệ](relationships.md), thì bạn cần xác định đường dẫn mối quan hệ để tạo một phân đoạn hợp lệ.</span><span class="sxs-lookup"><span data-stu-id="41cb1-136">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="41cb1-137">Thêm các thực thể từ đường dẫn mối quan hệ cho đến khi bạn có thể chọn thực thể **Khách hàng : CustomerInsights** từ danh sách thả xuống.</span><span class="sxs-lookup"><span data-stu-id="41cb1-137">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="41cb1-138">Sau đó, chọn **Tất cả bản ghi** cho mỗi điều kiện.</span><span class="sxs-lookup"><span data-stu-id="41cb1-138">Then, choose **All records** for each condition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="41cb1-139">![Đường dẫn mối quan hệ trong khi tạo phận đoạn](media/segments-multiple-relationships.png "Đường dẫn mối quan hệ trong khi tạo phận đoạn")</span><span class="sxs-lookup"><span data-stu-id="41cb1-139">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

1. <span data-ttu-id="41cb1-140">Theo mặc định, các phân khúc tạo một thực thể đầu ra chứa tất cả các thuộc tính của hồ sơ khách hàng phù hợp với các bộ lọc đã xác định.</span><span class="sxs-lookup"><span data-stu-id="41cb1-140">By default, segments generate an output entity that contains all attributes of customer profiles which match the defined filters.</span></span> <span data-ttu-id="41cb1-141">Nếu một phân khúc dựa trên các thực thể khác với *Khách hàng*, bạn có thể thêm nhiều thuộc tính hơn từ các thực thể này vào thực thể đầu ra.</span><span class="sxs-lookup"><span data-stu-id="41cb1-141">If a segment is based on other entities than the *Customer* entity, you can add more attributes from these entities to the output entity.</span></span> <span data-ttu-id="41cb1-142">Chọn **Thuộc tính dự án** để chọn các thuộc tính sẽ được thêm vào thực thể đầu ra.</span><span class="sxs-lookup"><span data-stu-id="41cb1-142">Select **Project attributes** to choose the attributes that will be appended to the output entity.</span></span>  

   
   <span data-ttu-id="41cb1-143">Ví dụ: Một phân khúc dựa trên một thực thể chứa dữ liệu về hoạt động khách hàng, liên quan đến thực thể *Khách hàng*.</span><span class="sxs-lookup"><span data-stu-id="41cb1-143">Example: A segment is based on an entity that contains customer activity data which is related to the *Customer* entity.</span></span> <span data-ttu-id="41cb1-144">Phân đoạn này tìm kiếm tất cả khách hàng đã gọi điện đến bộ phận trợ giúp trong 60 ngày qua.</span><span class="sxs-lookup"><span data-stu-id="41cb1-144">The segment looks for all customers that called the help desk in the last 60 days.</span></span> <span data-ttu-id="41cb1-145">Bạn có thể chọn thêm thời lượng cuộc gọi và số lượng cuộc gọi vào tất cả các bản ghi khách hàng phù hợp trong thực thể đầu ra.</span><span class="sxs-lookup"><span data-stu-id="41cb1-145">You can choose to append the call duration and the number of calls to all matching customer records in the output entity.</span></span> <span data-ttu-id="41cb1-146">Thông tin này có thể hữu ích để gửi một email với các liên kết hữu ích đến các bài báo trợ giúp trực tuyến và Câu hỏi thường gặp cho những khách hàng đã gọi điện thường xuyên.</span><span class="sxs-lookup"><span data-stu-id="41cb1-146">This information might be useful to send an email with helpful links to online help articles and FAQs to customers who called frequently.</span></span>

1. <span data-ttu-id="41cb1-147">Chọn **Lưu** để lưu phân đoạn của bạn.</span><span class="sxs-lookup"><span data-stu-id="41cb1-147">Select **Save** to save your segment.</span></span> <span data-ttu-id="41cb1-148">Phân đoạn của bạn sẽ được lưu và xử lý nếu tất cả các yêu cầu được xác thực.</span><span class="sxs-lookup"><span data-stu-id="41cb1-148">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="41cb1-149">Nếu không, nó sẽ được lưu dưới dạng bản nháp.</span><span class="sxs-lookup"><span data-stu-id="41cb1-149">Otherwise, it will be saved as a draft.</span></span>

1. <span data-ttu-id="41cb1-150">Chọn **Quay lại phân khúc** để quay lại trang **Phân khúc**.</span><span class="sxs-lookup"><span data-stu-id="41cb1-150">Select **Back to segments** to go back to the **Segments** page.</span></span>

## <a name="manage-existing-segments"></a><span data-ttu-id="41cb1-151">Quản lý các phân đoạn hiện có</span><span class="sxs-lookup"><span data-stu-id="41cb1-151">Manage existing segments</span></span>

<span data-ttu-id="41cb1-152">Trên trang **Phân đoạn**, bạn có thể xem tất cả các phân đoạn đã lưu và quản lý chúng.</span><span class="sxs-lookup"><span data-stu-id="41cb1-152">On the **Segments** page, you can view all your saved segments and manage them.</span></span>

<span data-ttu-id="41cb1-153">Mỗi phân khúc được đại diện bởi một hàng bao gồm thông tin bổ sung về phân khúc.</span><span class="sxs-lookup"><span data-stu-id="41cb1-153">Each segment is represented by a row that includes additional information about the segment.</span></span>

<span data-ttu-id="41cb1-154">Bạn có thể sắp xếp các phân đoạn trong một cột bằng cách chọn tiêu đề cột.</span><span class="sxs-lookup"><span data-stu-id="41cb1-154">You can sort the segments in a column by selecting the column heading.</span></span>

<span data-ttu-id="41cb1-155">Sử dụng hộp **Tìm kiếm** ở góc trên cùng bên phải để lọc các phân khúc.</span><span class="sxs-lookup"><span data-stu-id="41cb1-155">Use the **Search** box in the top-right corner to filter the segments.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="41cb1-156">![Tùy chọn để quản lý phân đoạn hiện có](media/segments-selected-segment.png "Tùy chọn để quản lý phân đoạn hiện có")</span><span class="sxs-lookup"><span data-stu-id="41cb1-156">![Options to manage an existing segment](media/segments-selected-segment.png "Options to manage an existing segment")</span></span>

<span data-ttu-id="41cb1-157">Hành động sau đây khả dụng khi bạn chọn một phân khúc:</span><span class="sxs-lookup"><span data-stu-id="41cb1-157">The following action are available when you select a segment:</span></span>

- <span data-ttu-id="41cb1-158">**Xem** chi tiết phân đoạn, bao gồm xu hướng số lượng thành viên của một bản xem trước thành viên phân đoạn.</span><span class="sxs-lookup"><span data-stu-id="41cb1-158">**View** the segment details, including member count trend a preview of segment members.</span></span>
- <span data-ttu-id="41cb1-159">**Chỉnh sửa** phân đoạn để thay đổi các thuộc tính của phân đoạn đó.</span><span class="sxs-lookup"><span data-stu-id="41cb1-159">**Edit** the segment to change its properties.</span></span>
- <span data-ttu-id="41cb1-160">**Tạo bản sao** của một phân khúc.</span><span class="sxs-lookup"><span data-stu-id="41cb1-160">**Create duplicate** of a segment.</span></span> <span data-ttu-id="41cb1-161">Bạn có thể chọn chỉnh sửa các thuộc tính của nó ngay lập tức hoặc chỉ cần lưu bản sao.</span><span class="sxs-lookup"><span data-stu-id="41cb1-161">You can choose to edit its properties right away or simply save the duplicate.</span></span>
- <span data-ttu-id="41cb1-162">**Làm mới** phân đoạn để bao gồm dữ liệu mới nhất.</span><span class="sxs-lookup"><span data-stu-id="41cb1-162">**Refresh** the segment to include the latest data.</span></span>
- <span data-ttu-id="41cb1-163">**Bật** hoặc **tắt** phân đoạn.</span><span class="sxs-lookup"><span data-stu-id="41cb1-163">**Activate** or **Deactivate** the segment.</span></span> <span data-ttu-id="41cb1-164">Các phân khúc có thể có hai trạng thái: hiện hoạt hoặc không hoạt động.</span><span class="sxs-lookup"><span data-stu-id="41cb1-164">Segments have two possible states - active or inactive.</span></span> <span data-ttu-id="41cb1-165">Các trạng thái này rất hữu ích khi bạn chỉnh sửa phân khúc.</span><span class="sxs-lookup"><span data-stu-id="41cb1-165">These states come in handy when editing a segment.</span></span> <span data-ttu-id="41cb1-166">Đối với các phân khúc không hoạt động, định nghĩa phân khúc tồn tại nhưng phân khúc chưa chứa bất kỳ khách hàng nào.</span><span class="sxs-lookup"><span data-stu-id="41cb1-166">For inactive segments, the segment definition exists but it doesn't contain any customers yet.</span></span> <span data-ttu-id="41cb1-167">Khi bạn kích hoạt một phân khúc, phân khúc sẽ thay đổi trạng thái từ "không hoạt động" thành "hiện hoạt" và bắt đầu tìm kiếm khách hàng phù hợp với định nghĩa phân khúc.</span><span class="sxs-lookup"><span data-stu-id="41cb1-167">When you activate a segment, its state changes from 'inactive' to 'active" and it starts looking for customers that match the segment definition.</span></span> <span data-ttu-id="41cb1-168">Nếu hoạt động [làm mới theo lịch trình](system.md#schedule-tab) được đặt cấu hình, thì các phân khúc không hoạt động sẽ có **Trạng thái** là **Đã bỏ qua**, biểu thị việc làm mới chưa được thực hiện.</span><span class="sxs-lookup"><span data-stu-id="41cb1-168">If a [scheduled refresh](system.md#schedule-tab) is configured, inactive segments have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.</span></span> <span data-ttu-id="41cb1-169">Khi phân khúc không hoạt động được kích hoạt, mục đó sẽ được làm mới và được đưa vào các lần làm mới theo lịch trình.</span><span class="sxs-lookup"><span data-stu-id="41cb1-169">When an inactive segment is activated, it will refresh and will be included in scheduled refreshes.</span></span>
  <span data-ttu-id="41cb1-170">Ngoài ra, bạn cũng có thể dùng chức năng **Lên lịch sau** trong menu thả xuống **Kích hoạt/Hủy kích hoạt** để xác định ngày giờ kích hoạt và hủy kích hoạt trong tương lai của một phân khúc cụ thể.</span><span class="sxs-lookup"><span data-stu-id="41cb1-170">Alternatively, you can use the **Schedule later** functionality in the **Activate/Deactivate** dropdown to specify a future date and time for activation and deactivation of a particular segment.</span></span>
- <span data-ttu-id="41cb1-171">**Đổi tên** phân đoạn.</span><span class="sxs-lookup"><span data-stu-id="41cb1-171">**Rename** the segment.</span></span>
- <span data-ttu-id="41cb1-172">**Tải xuống** danh sách thành viên dưới dạng tệp .CSV.</span><span class="sxs-lookup"><span data-stu-id="41cb1-172">**Download** the list of members as a .CSV file.</span></span>
- <span data-ttu-id="41cb1-173">Tùy chọn **Thêm vào** sẽ gửi danh sách ID khách hàng trong phân khúc để xử lý trong một ứng dụng khác.</span><span class="sxs-lookup"><span data-stu-id="41cb1-173">**Add to** option sends the list of customer IDs in the segment for processing in another application.</span></span>
- <span data-ttu-id="41cb1-174">**Xóa** phân đoạn.</span><span class="sxs-lookup"><span data-stu-id="41cb1-174">**Delete** the segment.</span></span>

## <a name="refresh-segments"></a><span data-ttu-id="41cb1-175">Làm mới phân đoạn</span><span class="sxs-lookup"><span data-stu-id="41cb1-175">Refresh segments</span></span>

<span data-ttu-id="41cb1-176">Bạn có thể làm mới tất cả phân phúc cùng lúc bằng cách chọn **Làm mới tất cả** trên trang **Phân khúc** hoặc bạn có thể làm mới một hoặc nhiều phân khúc khi chọn và chọn **Làm mới** từ các tùy chọn.</span><span class="sxs-lookup"><span data-stu-id="41cb1-176">You can refresh all segments at once by selecting **Refresh all** on the **Segments** page or you can refresh one or multiple segments when you select them and choose **Refresh** in from the options.</span></span> <span data-ttu-id="41cb1-177">Hoặc, bạn có thể đặt cấu hình làm mới lặp lại trên **Quản trị viên** > **Hệ thống** > **Lịch trình**.</span><span class="sxs-lookup"><span data-stu-id="41cb1-177">Alternatively, you can configure a recurring refresh on **Admin** > **System** > **Schedule**.</span></span>

> [!TIP]
> <span data-ttu-id="41cb1-178">Có [6 loại trạng thái](system.md#status-types) cho các nhiệm vụ/quy trình.</span><span class="sxs-lookup"><span data-stu-id="41cb1-178">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="41cb1-179">Ngoài ra, hầu hết các quy trình [phụ thuộc vào các quá trình hạ nguồn khác](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="41cb1-179">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="41cb1-180">Bạn có thể chọn trạng thái của một quy trình để xem chi tiết về tiến trình của toàn bộ công việc.</span><span class="sxs-lookup"><span data-stu-id="41cb1-180">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="41cb1-181">Sau khi chọn **Xem chi tiết** đối với một trong các tác vụ của công việc, bạn sẽ tìm thấy thông tin bổ sung: thời gian xử lý, ngày xử lý gần nhất và tất cả các lỗi và cảnh báo liên quan đến tác vụ.</span><span class="sxs-lookup"><span data-stu-id="41cb1-181">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="download-and-export-segments"></a><span data-ttu-id="41cb1-182">Tải xuống và xuất phân đoạn</span><span class="sxs-lookup"><span data-stu-id="41cb1-182">Download and export segments</span></span>

<span data-ttu-id="41cb1-183">Bạn có thể tải xuống các phân đoạn của mình vào tệp CSV hoặc xuất chúng sang Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="41cb1-183">You can download your segments to a CSV file or export them to Dynamics 365 Sales.</span></span>

### <a name="download-segments-to-a-csv-file"></a><span data-ttu-id="41cb1-184">Tải xuống các phân đoạn vào tệp CSV</span><span class="sxs-lookup"><span data-stu-id="41cb1-184">Download segments to a CSV file</span></span>

1. <span data-ttu-id="41cb1-185">Trong thông tin chi tiết về đối tượng, hãy chuyển đến trang **Phân khúc**.</span><span class="sxs-lookup"><span data-stu-id="41cb1-185">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="41cb1-186">Chọn dấu chấm lửng trong ngăn xếp của một phân đoạn cụ thể.</span><span class="sxs-lookup"><span data-stu-id="41cb1-186">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="41cb1-187">Chọn **Tải xuống dưới dạng CSV** từ danh sách thả xuống hành động.</span><span class="sxs-lookup"><span data-stu-id="41cb1-187">Select **Download as CSV** from the actions drop-down list.</span></span>

### <a name="export-segments-to-dynamics-365-sales"></a><span data-ttu-id="41cb1-188">Xuất phân đoạn sang Dynamics 365 Sales</span><span class="sxs-lookup"><span data-stu-id="41cb1-188">Export segments to Dynamics 365 Sales</span></span>

<span data-ttu-id="41cb1-189">Trước khi xuất phân đoạn sang Dynamics 365 Sales, quản trị viên cần phải [tạo đích xuất](export-destinations.md) cho Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="41cb1-189">Before exporting segments to Dynamics 365 Sales, an admin needs to [create the export destination](export-destinations.md) for Dynamics 365 Sales.</span></span>

1. <span data-ttu-id="41cb1-190">Trong thông tin chi tiết về đối tượng, hãy chuyển đến trang **Phân khúc**.</span><span class="sxs-lookup"><span data-stu-id="41cb1-190">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="41cb1-191">Chọn dấu chấm lửng trong ngăn xếp của một phân đoạn cụ thể.</span><span class="sxs-lookup"><span data-stu-id="41cb1-191">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="41cb1-192">Chọn **Thêm vào** từ danh sách hành động thả xuống và chọn đích xuất bạn muốn gửi dữ liệu vào.</span><span class="sxs-lookup"><span data-stu-id="41cb1-192">Select **Add to** from the actions drop-down list and select the export destination you want to send the data to.</span></span>

## <a name="draft-mode-for-segments"></a><span data-ttu-id="41cb1-193">Chế độ bản nháp cho phân đoạn</span><span class="sxs-lookup"><span data-stu-id="41cb1-193">Draft mode for segments</span></span>

<span data-ttu-id="41cb1-194">Nếu không đáp ứng tất cả các yêu cầu để xử lý phân đoạn, bạn có thể lưu phân đoạn dưới dạng bản nháp và truy cập từ trang **Phân đoạn**.</span><span class="sxs-lookup"><span data-stu-id="41cb1-194">If not all requirements to process a segment are met, you can save the segment as a draft and access it from the **Segments** page.</span></span>

<span data-ttu-id="41cb1-195">Phân đoạn sẽ được lưu dưới dạng phân đoạn không hoạt động và không bật được cho tới khi có hiệu lực.</span><span class="sxs-lookup"><span data-stu-id="41cb1-195">It will be saved as an inactive segment, and can't be activated it until it's valid.</span></span>

## <a name="add-more-conditions-to-a-group"></a><span data-ttu-id="41cb1-196">Thêm nhiều điều kiện cho một nhóm</span><span class="sxs-lookup"><span data-stu-id="41cb1-196">Add more conditions to a group</span></span>

<span data-ttu-id="41cb1-197">Để thêm nhiều điều kiện vào một nhóm, bạn có thể sử dụng hai toán tử logic:</span><span class="sxs-lookup"><span data-stu-id="41cb1-197">To add more conditions to a group, you can use two logical operators:</span></span>

- <span data-ttu-id="41cb1-198">Toán tử **AND**: Cả hai điều kiện phải được thỏa mãn như một phần của quá trình tạo phân đoạn.</span><span class="sxs-lookup"><span data-stu-id="41cb1-198">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="41cb1-199">Tùy chọn này hữu ích nhất khi bạn xác định các điều kiện trên các thực thể khác nhau.</span><span class="sxs-lookup"><span data-stu-id="41cb1-199">This option is most useful when you define conditions across different entities.</span></span>

- <span data-ttu-id="41cb1-200">Toán tử **OR**: Một trong các điều kiện cần phải được thỏa mãn như một phần của quá trình tạo phân đoạn.</span><span class="sxs-lookup"><span data-stu-id="41cb1-200">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="41cb1-201">Tùy chọn này hữu ích nhất khi bạn xác định nhiều điều kiện cho cùng một thực thể.</span><span class="sxs-lookup"><span data-stu-id="41cb1-201">This option is most useful when you define multiple conditions for the same entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="41cb1-202">![Toán tử OR trong đó một trong hai điều kiện cần phải được thỏa mãn](media/segmentation-either-condition.png "Toán tử OR trong đó một trong hai điều kiện cần phải được thỏa mãn")</span><span class="sxs-lookup"><span data-stu-id="41cb1-202">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

<span data-ttu-id="41cb1-203">Hiện tại, có thể lồng một toán tử **OR** trong toán tử **AND** nhưng không phải là ngược lại.</span><span class="sxs-lookup"><span data-stu-id="41cb1-203">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

## <a name="combine-multiple-groups"></a><span data-ttu-id="41cb1-204">Kết hợp nhiều nhóm</span><span class="sxs-lookup"><span data-stu-id="41cb1-204">Combine multiple groups</span></span>

<span data-ttu-id="41cb1-205">Mỗi nhóm tạo một nhóm khách hàng cụ thể.</span><span class="sxs-lookup"><span data-stu-id="41cb1-205">Each group produces a specific set of customers.</span></span> <span data-ttu-id="41cb1-206">Bạn có thể kết hợp các nhóm này để bao gồm các khách hàng cần thiết cho trường hợp công việc của bạn.</span><span class="sxs-lookup"><span data-stu-id="41cb1-206">You can combine these groups to include the customers required for your business case.</span></span>

1. <span data-ttu-id="41cb1-207">Trong thông tin chi tiết về đối tượng, hãy chuyển đến trang **Phân khúc** và chọn một phân khúc.</span><span class="sxs-lookup"><span data-stu-id="41cb1-207">In audience insights, go to the **Segments** page and select a segment.</span></span>

2. <span data-ttu-id="41cb1-208">Chọn **Thêm nhóm**.</span><span class="sxs-lookup"><span data-stu-id="41cb1-208">Select **Add Group**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="41cb1-209">![Thêm nhóm khách hàng](media/customer-group-add-group.png "Thêm nhóm khách hàng")</span><span class="sxs-lookup"><span data-stu-id="41cb1-209">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

3. <span data-ttu-id="41cb1-210">Chọn một trong các toán tử tập hợp sau: **Liên hiệp**, **Giao nhau** hoặc **Ngoại trừ**.</span><span class="sxs-lookup"><span data-stu-id="41cb1-210">Select one of the following set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="41cb1-211">![Thêm tập hợp nhóm khách hàng](media/customer-group-union.png "Thêm tập hợp nhóm khách hàng")</span><span class="sxs-lookup"><span data-stu-id="41cb1-211">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   <span data-ttu-id="41cb1-212">Chọn một toán tử bộ để xác định nhóm mới.</span><span class="sxs-lookup"><span data-stu-id="41cb1-212">Select a set operator to define a new group.</span></span> <span data-ttu-id="41cb1-213">Lưu các nhóm khác nhau để quyết định dữ liệu gì được giữ lại:</span><span class="sxs-lookup"><span data-stu-id="41cb1-213">Save different groups to determine what data gets retained:</span></span>

   - <span data-ttu-id="41cb1-214">**Hợp nhất** sẽ hợp nhất hai nhóm với nhau.</span><span class="sxs-lookup"><span data-stu-id="41cb1-214">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="41cb1-215">**Giao nhau** sẽ chồng chéo hai nhóm với nhau.</span><span class="sxs-lookup"><span data-stu-id="41cb1-215">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="41cb1-216">Chỉ dữ liệu *là phổ biến* cho cả hai nhóm được giữ lại trong nhóm hợp nhất.</span><span class="sxs-lookup"><span data-stu-id="41cb1-216">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="41cb1-217">**Trừ** kết hợp hai nhóm với nhau.</span><span class="sxs-lookup"><span data-stu-id="41cb1-217">**Except** combines the two groups.</span></span> <span data-ttu-id="41cb1-218">Chỉ dữ liệu trong nhóm A *là không phổ biến* cho dữ liệu trong nhóm B được giữ lại.</span><span class="sxs-lookup"><span data-stu-id="41cb1-218">Only data in group A that *is not common* to data in group B is retained.</span></span>

## <a name="view-processing-history-and-segment-members"></a><span data-ttu-id="41cb1-219">Xem lịch sử xử lý và các thành phần trong phân đoạn</span><span class="sxs-lookup"><span data-stu-id="41cb1-219">View processing history and segment members</span></span>

<span data-ttu-id="41cb1-220">Bạn có thể xem dữ liệu tổng hợp về một phân đoạn bằng cách xem lại chi tiết của phân đoạn đó.</span><span class="sxs-lookup"><span data-stu-id="41cb1-220">You can see consolidated data about a segment by reviewing its details.</span></span>

<span data-ttu-id="41cb1-221">Trên trang **Phân đoạn**, chọn phân đoạn bạn muốn xem lại.</span><span class="sxs-lookup"><span data-stu-id="41cb1-221">On the **Segments** page, select the segment you want to review.</span></span>

<span data-ttu-id="41cb1-222">Phần trên của trang bao gồm một biểu đồ xu hướng nhằm trực quan hóa những thay đổi về số lượng thành phần.</span><span class="sxs-lookup"><span data-stu-id="41cb1-222">The upper part of the page includes a trend graph that visualizes changes in member count.</span></span> <span data-ttu-id="41cb1-223">Di chuột qua các điểm dữ liệu để xem số lượng thành phần trong một ngày cụ thể.</span><span class="sxs-lookup"><span data-stu-id="41cb1-223">Hover over data points to see the member count on a specific date.</span></span>

<span data-ttu-id="41cb1-224">Bạn có thể cập nhật khung thời gian của trực quan hóa.</span><span class="sxs-lookup"><span data-stu-id="41cb1-224">You can update the time frame of the visualization.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="41cb1-225">![Khoảng thời gian phân đoạn](media/segment-time-range.png "Khoảng thời gian phân đoạn")</span><span class="sxs-lookup"><span data-stu-id="41cb1-225">![Segment time range](media/segment-time-range.png "Segment time range")</span></span>

<span data-ttu-id="41cb1-226">Phần dưới chứa danh sách các thành phần phân đoạn.</span><span class="sxs-lookup"><span data-stu-id="41cb1-226">The lower part contains a list of the segment members.</span></span>

> [!NOTE]
> <span data-ttu-id="41cb1-227">Các trường xuất hiện trong danh sách này dựa trên các thuộc tính của các thực thể trong phân đoạn của bạn.</span><span class="sxs-lookup"><span data-stu-id="41cb1-227">Fields that appear in this list are based on the attributes of your segment's entities.</span></span>
>
><span data-ttu-id="41cb1-228">Danh sách này là bản xem trước của các thành phần phân đoạn phù hợp và hiển thị 100 bản ghi đầu tiên của phân đoạn, từ đó bạn có thể đánh giá nhanh và xem lại định nghĩa nếu cần.</span><span class="sxs-lookup"><span data-stu-id="41cb1-228">The list is a preview of the matching segment members and shows the first 100 records of your segment so that you can quickly evaluate it and review its definitions if needed.</span></span> <span data-ttu-id="41cb1-229">Để xem tất cả các hồ sơ phù hợp, bạn cần [xuất phân đoạn](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="41cb1-229">To see all matching records, you need to [export the segment](export-destinations.md).</span></span>

## <a name="quick-segments"></a><span data-ttu-id="41cb1-230">Phân đoạn nhanh</span><span class="sxs-lookup"><span data-stu-id="41cb1-230">Quick segments</span></span>

<span data-ttu-id="41cb1-231">Ngoài trình tạo phân khúc, có một đường dẫn khác để tạo phân khúc.</span><span class="sxs-lookup"><span data-stu-id="41cb1-231">In addition to the segment builder, there's another path for creating segments.</span></span> <span data-ttu-id="41cb1-232">Phân khúc nhanh cho phép bạn xây dựng các phân khúc đơn giản (với một toán tử) nhanh chóng và có thông tin chuyên sâu tức thì.</span><span class="sxs-lookup"><span data-stu-id="41cb1-232">Quick segments let you build simple segments with a single operator quickly and with instant insights.</span></span>

1. <span data-ttu-id="41cb1-233">Trên trang **Phân đoạn**, hãy chọn **Mới** > **Tạo nhanh từ**.</span><span class="sxs-lookup"><span data-stu-id="41cb1-233">On the **Segments** page, select **New** > **Quickly create from**.</span></span>

   - <span data-ttu-id="41cb1-234">Chọn **Hồ sơ** để xây dựng phân đoạn dựa trên thực thể Khách hàng hợp nhất.</span><span class="sxs-lookup"><span data-stu-id="41cb1-234">Select the **Profiles** option to build a segment that is based on the unified Customer entity.</span></span>
   - <span data-ttu-id="41cb1-235">Chọn **Số liệu đo lường** để xây dựng phân đoạn xung quanh từng loại số liệu đo lường của Thuộc tính khách hàng mà bạn đã tạo trên trang **Giá trị đo lường**.</span><span class="sxs-lookup"><span data-stu-id="41cb1-235">Select the **Measures** option to build a segment around each of the Customer Attribute type of measures you have previously created on the **Measures** page.</span></span>
   - <span data-ttu-id="41cb1-236">Chọn tùy chọn **Thông tin** để xây dựng một phân đoạn xung quanh một trong các thực thể đầu ra mà bạn tạo bằng một trong hai chức năng **Dự đoán** hoặc **Mô hình tùy chỉnh**.</span><span class="sxs-lookup"><span data-stu-id="41cb1-236">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="41cb1-237">Trong hộp thoại **Phân đoạn nhanh mới**, hãy chọn một thuộc tính từ mục thả xuống **Trường**.</span><span class="sxs-lookup"><span data-stu-id="41cb1-237">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="41cb1-238">Hệ thống sẽ cung cấp thêm một số thông tin chi tiết để giúp bạn tạo các phân đoạn khách hàng tốt hơn.</span><span class="sxs-lookup"><span data-stu-id="41cb1-238">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="41cb1-239">Đối với các trường có phân loại, chúng tôi sẽ hiển thị 10 lượt khách hàng tốt nhất.</span><span class="sxs-lookup"><span data-stu-id="41cb1-239">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="41cb1-240">Chọn **Giá trị** rồi chọn **Xem lại**.</span><span class="sxs-lookup"><span data-stu-id="41cb1-240">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="41cb1-241">Đối với một thuộc tính số, hệ thống sẽ hiển thị giá trị thuộc tính nào nằm trong phần trăm của mỗi khách hàng.</span><span class="sxs-lookup"><span data-stu-id="41cb1-241">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="41cb1-242">Chọn một **Toán tử** và một **Giá trị**, sau đó chọn **Xem lại**.</span><span class="sxs-lookup"><span data-stu-id="41cb1-242">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="41cb1-243">Hệ thống sẽ cung cấp cho bạn một **Kích cỡ phân đoạn ước tính**.</span><span class="sxs-lookup"><span data-stu-id="41cb1-243">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="41cb1-244">Bạn có thể chọn tạo phân đoạn bạn đã xác định hoặc truy cập lại vào phân đoạn đó để có kích cỡ phân đoạn khác.</span><span class="sxs-lookup"><span data-stu-id="41cb1-244">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="41cb1-245">![Tên và ước tính cho một phân đoạn nhanh](media/quick-segment-name.png "Tên và ước tính cho một phân đoạn nhanh")</span><span class="sxs-lookup"><span data-stu-id="41cb1-245">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="41cb1-246">Đặt **Tên** cho phân đoạn của bạn.</span><span class="sxs-lookup"><span data-stu-id="41cb1-246">Provide a **Name** for your segment.</span></span> <span data-ttu-id="41cb1-247">Bạn cũng có thể cung cấp **Tên hiển thị**.</span><span class="sxs-lookup"><span data-stu-id="41cb1-247">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="41cb1-248">Chọn **Lưu** để tạo phân đoạn.</span><span class="sxs-lookup"><span data-stu-id="41cb1-248">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="41cb1-249">Sau khi phân đoạn đã xử lý xong, bạn có thể xem nó như bất kỳ phân đoạn nào khác mà bạn đã tạo.</span><span class="sxs-lookup"><span data-stu-id="41cb1-249">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

<span data-ttu-id="41cb1-250">Đối với các tình huống sau, bạn nên sử dụng trình tạo phân đoạn thay vì chức năng phân đoạn được đề xuất:</span><span class="sxs-lookup"><span data-stu-id="41cb1-250">For the following scenarios, we advise using the segment builder rather than the recommended segments capability:</span></span>

- <span data-ttu-id="41cb1-251">Tạo các phân đoạn với các bộ lọc trên các trường phân loại trong đó toán tử không phải là toán tử **Is**</span><span class="sxs-lookup"><span data-stu-id="41cb1-251">Creating segments with filters on categorical fields where the operator is different than the **Is** operator</span></span>
- <span data-ttu-id="41cb1-252">Tạo các phân đoạn với các bộ lọc trên các trường số trong đó toán tử không phải là **Between**, **Greater than** và **Less than**</span><span class="sxs-lookup"><span data-stu-id="41cb1-252">Creating segments with filters on numerical fields where the operator is different than the **Between**, **Greater than**, and **Less than** operators</span></span>
- <span data-ttu-id="41cb1-253">Tạo phân đoạn với các bộ lọc trên các trường loại ngày</span><span class="sxs-lookup"><span data-stu-id="41cb1-253">Creating segments with filters on date type fields</span></span>

## <a name="next-steps"></a><span data-ttu-id="41cb1-254">Bước tiếp theo</span><span class="sxs-lookup"><span data-stu-id="41cb1-254">Next steps</span></span>

<span data-ttu-id="41cb1-255">[Xuất phân đoạn](export-destinations.md) và khám phá [Thẻ khách hàng](customer-card-add-in.md) và [Bộ kết nối](export-power-bi.md) để nắm được thông tin chi tiết ở cấp độ khách hàng.</span><span class="sxs-lookup"><span data-stu-id="41cb1-255">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]