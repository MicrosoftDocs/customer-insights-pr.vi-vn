---
title: Các phân khúc được đề xuất dựa trên hoạt động.
description: Tìm ra các phân khúc mới mẻ và thú vị dựa trên hoạt động của khách hàng nhờ vào cơ chế máy học.
ms.date: 05/11/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
ms.openlocfilehash: 14d9d4f0df6b5835f21fb63447d05853ee98a757
ms.sourcegitcommit: 8341fa964365c185b65bc4b71fc0c695ea127dc0
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 05/14/2021
ms.locfileid: "6034127"
---
# <a name="suggested-segments-based-on-activity-data-preview"></a><span data-ttu-id="27094-103">Các phân khúc được đề xuất dựa trên dữ liệu hoạt động (bản xem trước)</span><span class="sxs-lookup"><span data-stu-id="27094-103">Suggested segments based on activity data (preview)</span></span>

<span data-ttu-id="27094-104">Khám phá các phân khúc khách hàng thú vị dựa trên dữ liệu hoạt động của khách hàng có trong Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="27094-104">Discover interesting segments of your customers based on customer activity data that is ingested to Customer Insights.</span></span> <span data-ttu-id="27094-105">Ví dụ về dữ liệu hoạt động là giao dịch, thời lượng cuộc gọi hỗ trợ, quá trình mua hoặc trả hàng.</span><span class="sxs-lookup"><span data-stu-id="27094-105">Examples of activity data are transactions, support call duration, purchases, or returns.</span></span> <span data-ttu-id="27094-106">Để đề xuất các phân khúc, dữ liệu hoạt động sẽ được phân tích theo lần truy cập gần đây, tần suất và giá trị tiền tệ (hoặc thời lượng).</span><span class="sxs-lookup"><span data-stu-id="27094-106">To suggest segments, activity data gets analyzed for recency, frequency, and monetary value (or duration).</span></span> <span data-ttu-id="27094-107">Ngoài ra, bạn có thể tạo [các phân khúc được đề xuất để cải thiện thước đo hoặc hiểu rõ hơn yếu tố ảnh hưởng đến thuộc tính](suggested-segments.md).</span><span class="sxs-lookup"><span data-stu-id="27094-107">Alternatively, you can generate [suggested segments to improve a measure or better understand what influences an attribute](suggested-segments.md).</span></span>

:::image type="content" source="media/suggested-segments-tab.png" alt-text="Tab phân khúc được đề xuất hiển thị các đề xuất cho các phân khúc dựa trên hoạt động và thuộc tính.":::

## <a name="categorize-customers-by-activity"></a><span data-ttu-id="27094-109">Phân loại khách hàng theo hoạt động</span><span class="sxs-lookup"><span data-stu-id="27094-109">Categorize customers by activity</span></span>

<span data-ttu-id="27094-110">Với [dữ liệu hoạt động](activities.md) có sẵn trong Customer Insights, chúng tôi có thể tạo các đề xuất đại diện cho các nhóm khách hàng:</span><span class="sxs-lookup"><span data-stu-id="27094-110">With [activity data](activities.md) available in Customer Insights, we can generate suggestions that represent customer groups:</span></span>

- <span data-ttu-id="27094-111">những khách hàng tích cực nhất</span><span class="sxs-lookup"><span data-stu-id="27094-111">most active customers</span></span> 
- <span data-ttu-id="27094-112">những khách hàng đã mua hàng nhiều nhất</span><span class="sxs-lookup"><span data-stu-id="27094-112">customers that have made the most purchases</span></span> 
- <span data-ttu-id="27094-113">những khách hàng tạo ra nhiều doanh thu nhất</span><span class="sxs-lookup"><span data-stu-id="27094-113">customers that generated the most revenue</span></span> 
- <span data-ttu-id="27094-114">những khách hàng không hoạt động gần đây</span><span class="sxs-lookup"><span data-stu-id="27094-114">customers who haven’t been active lately</span></span> 
- <span data-ttu-id="27094-115">những khách hàng thường xuyên tương tác với doanh nghiệp của bạn</span><span class="sxs-lookup"><span data-stu-id="27094-115">customers who frequently interact with your business</span></span>  

<span data-ttu-id="27094-116">Nếu bạn có một doanh nghiệp bán lẻ, bạn có thể tìm ra những khách hàng nào tạo ra nhiều doanh thu nhất và tặng phiếu giảm giá cho họ.</span><span class="sxs-lookup"><span data-stu-id="27094-116">If you have a retail business, you could find out which customers generate the most revenue and reward them with a coupon.</span></span> <span data-ttu-id="27094-117">Hoặc bạn có thể xác định những khách hàng không thường xuyên mua hàng và đề nghị họ tham gia chương trình phần thưởng để họ ghé thăm doanh nghiệp của bạn thường xuyên hơn.</span><span class="sxs-lookup"><span data-stu-id="27094-117">Or you can identify occasional customers and offer them to join a rewards program so they visit your business more often.</span></span>
<span data-ttu-id="27094-118">Giả sử bạn đang kinh doanh trong lĩnh vực chăm sóc sức khỏe, cung cấp dịch vụ chăm sóc sức khỏe cộng đồng và mục tiêu của bạn là giảm thiểu chi phí cho mỗi bệnh nhân.</span><span class="sxs-lookup"><span data-stu-id="27094-118">If you're in the healthcare business providing public healthcare and your goal is to minimize the expenses for individual patients.</span></span> <span data-ttu-id="27094-119">Bạn có thể giảm số lần tái khám của bệnh nhân bằng cách đưa ra dịch vụ chăm sóc tốt nhất có thể trong những lần khám bệnh ít ỏi đó.</span><span class="sxs-lookup"><span data-stu-id="27094-119">A way to do so could be to reduce recurring visits by providing best possible care in as few visits as possible.</span></span> <span data-ttu-id="27094-120">Trong trường hợp này, mục tiêu của bạn là giảm tần suất khám bệnh và chi phí tái khám cho bệnh nhân.</span><span class="sxs-lookup"><span data-stu-id="27094-120">In this case, your goal is to keep the visit frequency low and minimize recurring cost for the patients.</span></span> <span data-ttu-id="27094-121">Hoặc bạn có thể xác định các phân khúc bệnh nhân có cuộc hẹn thường xuyên và chi phí tái khám cao và phân tích những trường hợp này để cải thiện việc điều trị cho từng cá nhân.</span><span class="sxs-lookup"><span data-stu-id="27094-121">Or you can identify segments of patients who have frequent appointments and high recurring costs and analyze these cases to improve the treatment of the individual.</span></span> 

## <a name="required-data"></a><span data-ttu-id="27094-122">Dữ liệu bắt buộc</span><span class="sxs-lookup"><span data-stu-id="27094-122">Required data</span></span>

<span data-ttu-id="27094-123">Đề xuất được tạo dựa trên dữ liệu đầu vào đã chọn.</span><span class="sxs-lookup"><span data-stu-id="27094-123">Suggestions are generated based on the selected input data.</span></span> 

- <span data-ttu-id="27094-124">Hồ sơ khách hàng: Tất cả khách hàng hoặc thành viên của một phân khúc cụ thể.</span><span class="sxs-lookup"><span data-stu-id="27094-124">Customer profiles: All customers or members of a specific segment.</span></span> 

- <span data-ttu-id="27094-125">Khoảng thời gian: Tháng trước, năm trước hoặc bất kỳ khung thời gian tùy chỉnh nào.</span><span class="sxs-lookup"><span data-stu-id="27094-125">Time period: Last month, last year, or any custom time frame.</span></span>

- <span data-ttu-id="27094-126">Loại hoạt động: mua hàng, giao dịch bán lẻ, giao dịch trực tuyến, các trường hợp hỗ trợ khách hàng, gói đăng ký, v.v.</span><span class="sxs-lookup"><span data-stu-id="27094-126">Activity type: purchases, retail transactions, online transactions, customer support cases, subscriptions, and so on.</span></span>  

- <span data-ttu-id="27094-127">Thực thể trong Customer Insights có chứa dữ liệu hoạt động: Thực thể UnifiedActivity hoặc thực thể cho một hoạt động cụ thể.</span><span class="sxs-lookup"><span data-stu-id="27094-127">Entity in Customer Insights that contains the activity data: The UnifiedActivity entity or the entity for a specific activity.</span></span> 

- <span data-ttu-id="27094-128">Các yếu tố bao gồm: Lần truy cập gần đây, tần suất hoặc yếu tố tiền tệ, tùy thuộc vào yêu cầu kinh doanh của bạn.</span><span class="sxs-lookup"><span data-stu-id="27094-128">Dimensions to include: Recency, frequency, or monetary dimension, depending on your business requirements.</span></span>

## <a name="generate-suggested-segments"></a><span data-ttu-id="27094-129">Tạo các phân đoạn được đề xuất</span><span class="sxs-lookup"><span data-stu-id="27094-129">Generate suggested segments</span></span>

1. <span data-ttu-id="27094-130">Đi đến **Phân khúc**.</span><span class="sxs-lookup"><span data-stu-id="27094-130">Go to **Segments**.</span></span>

1. <span data-ttu-id="27094-131">Chọn tab **Gợi ý (xem trước)**.</span><span class="sxs-lookup"><span data-stu-id="27094-131">Select the **Suggestions (preview)** tab.</span></span>

1. <span data-ttu-id="27094-132">Chọn **Tìm đề xuất mới** và chọn **Xem hoặc dự đoán hành vi của khách hàng**.</span><span class="sxs-lookup"><span data-stu-id="27094-132">Select **Find new suggestions** and choose **See or anticipate customer behavior**.</span></span> <span data-ttu-id="27094-133">Chọn **Bắt đầu** để chạy trải nghiệm đã hướng dẫn.</span><span class="sxs-lookup"><span data-stu-id="27094-133">Select **Start** to run the guided experience.</span></span>

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="Bước đầu tiên của trình hướng dẫn cấu hình cho phân khúc đã đề xuất dựa trên hoạt động.":::

1. <span data-ttu-id="27094-135">Cung cấp dữ liệu đầu vào được yêu cầu và tiếp tục chọn **Tiếp theo**.</span><span class="sxs-lookup"><span data-stu-id="27094-135">Provide the required input data and select **Next** proceed.</span></span>

   - <span data-ttu-id="27094-136">Chọn khách hàng: Bao gồm tất cả khách hàng hoặc khách hàng trong một phân khúc cụ thể.</span><span class="sxs-lookup"><span data-stu-id="27094-136">Choose customers: Include all customers or a specific segment.</span></span>
   - <span data-ttu-id="27094-137">Chọn hoạt động: Chọn loại hoạt động và các thực thể mô tả hoạt động.</span><span class="sxs-lookup"><span data-stu-id="27094-137">Choose activity: Select the activity type and the entities that describe the activity.</span></span>
   - <span data-ttu-id="27094-138">Tùy chọn: Đặt khoảng thời gian cần xem xét, các yếu tố cho đề xuất và lập bản đồ các thuộc tính.</span><span class="sxs-lookup"><span data-stu-id="27094-138">Preferences: Set the time period to consider, the factors for suggestions, and map the attributes.</span></span>

1. <span data-ttu-id="27094-139">Xem xét lại dữ liệu đầu vào của bạn và chọn **Chạy** để chạy mô hình và tạo đề xuất.</span><span class="sxs-lookup"><span data-stu-id="27094-139">Review your input and select **Run** to run the model and generate suggestions.</span></span>

1. <span data-ttu-id="27094-140">Tùy thuộc vào số lượng hồ sơ khách hàng và các hoạt động đã chọn, thời gian chạy có thể lên đến vài phút.</span><span class="sxs-lookup"><span data-stu-id="27094-140">Depending on the number of customer profiles and selected activities, it can take a few minutes to complete.</span></span> 

<span data-ttu-id="27094-141">Sau khi tạo các đề xuất, bạn có thể lọc chúng theo thứ mục hoặc giá trị mà bạn quan tâm nhất.</span><span class="sxs-lookup"><span data-stu-id="27094-141">After generating the suggestions, you can filter them by the dimension or value you're most interested in.</span></span> 

## <a name="view-details-of-a-suggested-segment"></a><span data-ttu-id="27094-142">Xem chi tiết về phân khúc được gợi ý</span><span class="sxs-lookup"><span data-stu-id="27094-142">View details of a suggested segment</span></span>

<span data-ttu-id="27094-143">Sau khi bạn tạo các đề xuất, các đề xuất này sẽ xuất hiện trên mục **Phân khúc** > **Đề xuất (xem trước)** trong phần **Đề xuất dựa trên hoạt động**.</span><span class="sxs-lookup"><span data-stu-id="27094-143">Once the suggestions are generated, you'll find them listed on **Segments** > **Suggestions (preview)** in the **Activity-based suggestions** section.</span></span>

:::image type="content" source="media/suggested-segments-details.png" alt-text="Ngăn bên được mở rộng hiển thị dữ liệu chi tiết của phân khúc đã đề xuất.":::

<span data-ttu-id="27094-145">Chọn **Xem đề xuất** trên một phân khúc đã đề xuất để xem chi tiết.</span><span class="sxs-lookup"><span data-stu-id="27094-145">Select **See suggestion** on a suggested segment to view the details of that segment.</span></span> <span data-ttu-id="27094-146">Ngăn bên thể hiện các chi tiết như phạm vi của từng yếu tố so với nhóm mục tiêu.</span><span class="sxs-lookup"><span data-stu-id="27094-146">The side pane provides details like the extent of each dimension in comparison to the target group.</span></span> <span data-ttu-id="27094-147">Ngăn này cũng làm nổi bật số lượng thành viên tiềm năng trong phân khúc và tỷ lệ phần trăm tương ứng trên tổng số khách hàng.</span><span class="sxs-lookup"><span data-stu-id="27094-147">It also highlights the number of potential members in the segment and the corresponding percentage of the total customers.</span></span> <span data-ttu-id="27094-148">Nếu bạn muốn giữ đề xuất dưới dạng một phân khúc, hãy chọn **Tạo phân khúc**.</span><span class="sxs-lookup"><span data-stu-id="27094-148">If you want to keep the suggestion as a segment, select **Create segment**.</span></span>    

## <a name="save-a-suggestion-as-a-segment"></a><span data-ttu-id="27094-149">Lưu đề xuất làm phân đoạn</span><span class="sxs-lookup"><span data-stu-id="27094-149">Save a suggestion as a segment</span></span>

1. <span data-ttu-id="27094-150">Đi đến **Phân đoạn** > **Gợi ý (xem trước)**.</span><span class="sxs-lookup"><span data-stu-id="27094-150">Go to **Segments** > **Suggestions (preview)**.</span></span>

1. <span data-ttu-id="27094-151">Chọn phân khúc bạn muốn lưu.</span><span class="sxs-lookup"><span data-stu-id="27094-151">Select the segment you want to save.</span></span> 

1. <span data-ttu-id="27094-152">Trong ngăn bên, hãy chọn **Tạo phân khúc**.</span><span class="sxs-lookup"><span data-stu-id="27094-152">In the side pane, select **Create segment**.</span></span> 

1. <span data-ttu-id="27094-153">Sau khi lưu phân khúc, phân khúc đó sẽ hiển thị trên danh sách các phân khúc trong tab **Tất cả các phân khúc**. Bây giờ, bạn có thể [làm mới hoặc xóa phân khúc đó giống như bất kỳ phân khúc nào khác](segments.md).</span><span class="sxs-lookup"><span data-stu-id="27094-153">After saving the segment, it will show in the list of segments on the **All segments** tab. It can now be [refreshed or deleted like any other segment](segments.md).</span></span> <span data-ttu-id="27094-154">Bạn không thể chỉnh sửa chi tiết phân khúc.</span><span class="sxs-lookup"><span data-stu-id="27094-154">You can't edit the segment details.</span></span> <span data-ttu-id="27094-155">Tuy nhiên, bạn có thể thay đổi tiêu chí đầu vào cho các đề xuất và tạo các đề xuất khác nhau.</span><span class="sxs-lookup"><span data-stu-id="27094-155">However, you can change the input criteria for the suggestions and generate different suggestions.</span></span>

## <a name="refresh-or-edit-a-set-of-suggestions"></a><span data-ttu-id="27094-156">Làm mới hoặc chỉnh sửa một tập hợp các đề xuất</span><span class="sxs-lookup"><span data-stu-id="27094-156">Refresh or edit a set of suggestions</span></span>

1. <span data-ttu-id="27094-157">Chuyển tới **Phân khúc** > **Đề xuất (xem trước)** và tìm kiếm phân khúc trong phần **Đề xuất dựa trên hoạt động**.</span><span class="sxs-lookup"><span data-stu-id="27094-157">Go to **Segments** > **Suggestions (preview)** and look for the segment in the **Activity-based suggestions** section.</span></span>

1. <span data-ttu-id="27094-158">Chọn **Làm mới đề xuất** để làm mới các đề xuất trong khi vẫn giữ các thuộc tính đã định cấu hình.</span><span class="sxs-lookup"><span data-stu-id="27094-158">Select **Refresh suggestions** to refresh the suggestions while keeping configured attributes.</span></span> <span data-ttu-id="27094-159">Hoặc chọn **Chỉnh sửa đề xuất** để sửa đổi các thuộc tính đã định cấu hình.</span><span class="sxs-lookup"><span data-stu-id="27094-159">Or select **Edit suggestions** to modify the configured attributes.</span></span> <span data-ttu-id="27094-160">Hệ thống sẽ chạy lại quy trình, tạo các đề xuất phân khúc dựa trên dữ liệu mới nhất và thay thế các đề xuất hiện tại.</span><span class="sxs-lookup"><span data-stu-id="27094-160">The system will rerun the process, generate segment suggestions based on the latest data, and replace the current suggestions.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
