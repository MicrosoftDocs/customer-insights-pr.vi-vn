---
title: Thông tin chi tiết về phân khúc cho các phân khúc hiện tại
description: Nhận thông tin chi tiết về các phân khúc hiện có để thấy điểm khác biệt và điểm chung.
ms.date: 06/10/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 2856888d6ac64d5daabcc5a234f13bc6f88bb3df
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306100"
---
# <a name="segment-insights-preview"></a><span data-ttu-id="daf9e-103">Thông tin chuyên sâu về phân khúc (xem trước)</span><span class="sxs-lookup"><span data-stu-id="daf9e-103">Segment insights (preview)</span></span>

<span data-ttu-id="daf9e-104">Khám phá thông tin chuyên sâu và chi tiết hơn về các phân khúc hiện có.</span><span class="sxs-lookup"><span data-stu-id="daf9e-104">Discover additional information and insights around your existing segments.</span></span> <span data-ttu-id="daf9e-105">Tìm hiểu xem 2 phân khúc có gì khác hoặc tương tự nhau.</span><span class="sxs-lookup"><span data-stu-id="daf9e-105">Find out what differentiates two segments or what they have in common.</span></span>

## <a name="segment-overlap"></a><span data-ttu-id="daf9e-106">Phân khúc chồng chéo</span><span class="sxs-lookup"><span data-stu-id="daf9e-106">Segment overlap</span></span>

<span data-ttu-id="daf9e-107">Phép phân tích chồng chéo phân khúc sẽ cho biết có bao nhiêu và khách hàng nào xuất hiện ở 2 phân khúc trở lên.</span><span class="sxs-lookup"><span data-stu-id="daf9e-107">Segment overlap analysis shows how many and which customers are common to two or more segments.</span></span> <span data-ttu-id="daf9e-108">Ví dụ: làm thế nào một phân khúc gồm khách hàng thường xuyên lại chồng chéo với phân khúc khác gồm những khách hàng hài lòng với dịch vụ hoặc sản phẩm của bạn.</span><span class="sxs-lookup"><span data-stu-id="daf9e-108">For example, how a segment of frequent customers overlaps with a segment that contains customers that are satisfied with your service or product.</span></span>
<span data-ttu-id="daf9e-109">Bạn cũng có thể phân tính xem sự chồng chéo thay đổi như thế nào đối với các thuộc tính cụ thể.</span><span class="sxs-lookup"><span data-stu-id="daf9e-109">You can also analyze how the overlap changes for specific attributes.</span></span>

### <a name="run-an-overlap-analysis"></a><span data-ttu-id="daf9e-110">Chạy phép phân tích sự chồng chéo</span><span class="sxs-lookup"><span data-stu-id="daf9e-110">Run an overlap analysis</span></span>

1. <span data-ttu-id="daf9e-111">Đi tới **Phân khúc** rồi chọn tab **Thông tin chi tiết (xem trước)**.</span><span class="sxs-lookup"><span data-stu-id="daf9e-111">Go to **Segments** and select the **Insights (preview)** tab.</span></span>

1. <span data-ttu-id="daf9e-112">Chọn **Mới** rồi bấm vào tùy chọn **Chồng chéo** trong ngăn **Chọn loại thông tin chuyên sâu**.</span><span class="sxs-lookup"><span data-stu-id="daf9e-112">Select **New** and choose the **Overlap** option in the **Choose Insight Type** pane.</span></span>

1. <span data-ttu-id="daf9e-113">Chọn các phân khúc bạn quan tâm rồi bấm vào **Tiếp**.</span><span class="sxs-lookup"><span data-stu-id="daf9e-113">Choose the segments of interest and select **Next**.</span></span>

1. <span data-ttu-id="daf9e-114">Không bắt buộc: chọn một hoặc nhiều trường bạn muốn phân tích sự chồng chéo cho từng trường nếu khả thi, sau đó bấm vào **Tiếp**.</span><span class="sxs-lookup"><span data-stu-id="daf9e-114">Optionally, choose one or more fields of interest to analyze overlaps for every possible field value and select **Next**.</span></span>

1. <span data-ttu-id="daf9e-115">Đặt tên cho phép phân tích sự chồng chéo, tên hiển thị (không bắt buộc) và thông tin mô tả.</span><span class="sxs-lookup"><span data-stu-id="daf9e-115">Provide a name for you overlap analysis, an optional display name, and a description.</span></span>

1. <span data-ttu-id="daf9e-116">Chọn **Lưu** để bắt đầu phân tích.</span><span class="sxs-lookup"><span data-stu-id="daf9e-116">Select **Save** to start the analysis.</span></span> <span data-ttu-id="daf9e-117">Phép phân tích sự chồng chéo sẽ sẵn sàng khi trạng thái chuyển từ Đang làm mới sang Thành công.</span><span class="sxs-lookup"><span data-stu-id="daf9e-117">The overlap analysis is ready when the status changes from Refreshing to Successful.</span></span>

### <a name="view-and-optimize-an-overlap-analysis"></a><span data-ttu-id="daf9e-118">Xem và tối ưu hóa phép phân tích sự chồng chéo</span><span class="sxs-lookup"><span data-stu-id="daf9e-118">View and optimize an overlap analysis</span></span>

<span data-ttu-id="daf9e-119">Sau khi hoàn thành phân tích, bạn có thể tìm thấy thống tin chuyên sâu trong mục **Phân khúc** > **Thông tin chuyên sâu (xem trước)**.</span><span class="sxs-lookup"><span data-stu-id="daf9e-119">After completing the analysis, find details on this insight on **Segments** > **Insights (preview)**.</span></span>

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-overlap.png" alt-text="Thông tin chuyên sâu về phân khúc chồng chéo":::

<span data-ttu-id="daf9e-121">Chọn một thông tin chuyên sâu để xem kết quả phân tích:</span><span class="sxs-lookup"><span data-stu-id="daf9e-121">Select an insight to see the analysis results:</span></span>

- <span data-ttu-id="daf9e-122">Số lượng thành viên chồng chéo với phân khúc đã chọn cho phép phân tích.</span><span class="sxs-lookup"><span data-stu-id="daf9e-122">The number of members overlapping the segments selected for analysis.</span></span>
- <span data-ttu-id="daf9e-123">Số lượng thành viên có trong một phân khúc nhưng không có trong các phân khúc còn lại.</span><span class="sxs-lookup"><span data-stu-id="daf9e-123">The number of members included in one of the segments but not in the rest of the segments.</span></span>
- <span data-ttu-id="daf9e-124">Nếu bạn đã chọn các trường trong khi định cấu hình phép phân tích sự chồng chéo, bạn sẽ thấy các trường đó trong tab tương ứng.</span><span class="sxs-lookup"><span data-stu-id="daf9e-124">If you selected fields while configuring the overlap analysis, you'll find them in the corresponding tabs.</span></span> <span data-ttu-id="daf9e-125">Bạn có thể sử dụng danh sách thả xuống của bộ lọc để chọn bất kỳ mức độ quan tâm thuộc tính nào và bảng ở dưới cùng sẽ hiển thị dữ liệu tương ứng.</span><span class="sxs-lookup"><span data-stu-id="daf9e-125">You can use the filter dropdown to select any attribute level of interest and the table at the bottom will show the corresponding data.</span></span>

## <a name="segment-differentiators"></a><span data-ttu-id="daf9e-126">Điểm khác biệt của phân đoạn</span><span class="sxs-lookup"><span data-stu-id="daf9e-126">Segment differentiators</span></span>

<span data-ttu-id="daf9e-127">Bạn có thể dựa vào các nhân tố khác biệt của phân khúc để tìm ra sự khác nhau của một phân khúc so với số khách hàng còn lại hoặc so với một phân khúc khác.</span><span class="sxs-lookup"><span data-stu-id="daf9e-127">Segment differentiators help you find out what differentiates a segment from the rest of your customers or from another segment.</span></span> <span data-ttu-id="daf9e-128">Bạn chỉ cần chọn một phân khúc. Hệ thống sẽ xác định các thuộc tính và phép đo giúp phân biệt phân khúc đã chọn.</span><span class="sxs-lookup"><span data-stu-id="daf9e-128">You just have to select a segment and the system will identify profile attributes and measures that distinguish the selected segment.</span></span>

### <a name="run-a-differentiator-analysis"></a><span data-ttu-id="daf9e-129">Chạy phép phân tích nhân tố khác biệt</span><span class="sxs-lookup"><span data-stu-id="daf9e-129">Run a differentiator analysis</span></span>

1. <span data-ttu-id="daf9e-130">Đi tới **Phân khúc** rồi chọn tab **Thông tin chi tiết (xem trước)**.</span><span class="sxs-lookup"><span data-stu-id="daf9e-130">Go to **Segments** and select the **Insights (preview)** tab.</span></span>

1. <span data-ttu-id="daf9e-131">Chọn **Mới** rồi bấm vào tùy chọn **Chồng chéo** trong ngăn **Chọn loại thông tin chuyên sâu**.</span><span class="sxs-lookup"><span data-stu-id="daf9e-131">Select **New** and choose the **Overlap** option in the **Choose Insight Type** pane.</span></span>

1. <span data-ttu-id="daf9e-132">Chọn phân khúc bạn muốn phân tích làm **Phân khúc chính** rồi chọn **Tiếp**.</span><span class="sxs-lookup"><span data-stu-id="daf9e-132">Choose the segment you want to analyze as **Primary segment** and select **Next**.</span></span>

1. <span data-ttu-id="daf9e-133">Chọn **Tất cả khách hàng** hoặc **Phân khúc phụ** cần so sánh với phân khúc chính rồi bấm vào **Tiếp**.</span><span class="sxs-lookup"><span data-stu-id="daf9e-133">Choose **All customers** or a **Secondary segment** to compare your primary segment with and select **Next**.</span></span>

1. <span data-ttu-id="daf9e-134">Không bắt buộc: Chọn một hoặc nhiều trường bạn muốn tập trung phân tích một số thuộc tính cụ thể, sau đó chọn **Tiếp**.</span><span class="sxs-lookup"><span data-stu-id="daf9e-134">Optionally, choose one or more fields of interest to focus the analysis on specific attributes and select **Next**.</span></span>

1. <span data-ttu-id="daf9e-135">Đặt tên cho phép phân tích sự chồng chéo, tên hiển thị (không bắt buộc) và thông tin mô tả.</span><span class="sxs-lookup"><span data-stu-id="daf9e-135">Provide a name for you overlap analysis, an optional display name, and a description.</span></span>

1. <span data-ttu-id="daf9e-136">Chọn **Lưu** để bắt đầu phân tích.</span><span class="sxs-lookup"><span data-stu-id="daf9e-136">Select **Save** to start the analysis.</span></span> <span data-ttu-id="daf9e-137">Phép phân tích sự chồng chéo sẽ sẵn sàng khi trạng thái chuyển từ Đang làm mới sang Thành công.</span><span class="sxs-lookup"><span data-stu-id="daf9e-137">The overlap analysis is ready when the status changes from Refreshing to Successful.</span></span>

### <a name="view-and-optimize-a-differentiators-analysis"></a><span data-ttu-id="daf9e-138">Xem và tối ưu hóa phép phân tích nhân tố khác biệt</span><span class="sxs-lookup"><span data-stu-id="daf9e-138">View and optimize a differentiators analysis</span></span>

<span data-ttu-id="daf9e-139">Sau khi hoàn thành phân tích, bạn có thể tìm thấy thống tin chuyên sâu trong mục **Phân khúc** > **Thông tin chuyên sâu (xem trước)**.</span><span class="sxs-lookup"><span data-stu-id="daf9e-139">After completing the analysis, find details on this insight on **Segments** > **Insights (preview)**.</span></span>

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-differentiators.png" alt-text="Thông tin chi tiết về nhân tố khác biệt của phân khúc":::

<span data-ttu-id="daf9e-141">Chọn một thông tin chuyên sâu để xem kết quả phân tích.</span><span class="sxs-lookup"><span data-stu-id="daf9e-141">Select an insight to see the analysis results.</span></span> <span data-ttu-id="daf9e-142">Phép phân tích nhân tố khác biệt gồm có 2 tab.</span><span class="sxs-lookup"><span data-stu-id="daf9e-142">A differentiator analysis includes two tabs.</span></span> <span data-ttu-id="daf9e-143">Tab **Thuộc tính** liệt kê các thuộc tính hồ sơ, được coi là nhân tố khác biệt.</span><span class="sxs-lookup"><span data-stu-id="daf9e-143">The **Attributes** tab lists profile attributes considered as differentiators.</span></span> <span data-ttu-id="daf9e-144">Tab **Phép đo** liệt kê các nhân tố khác biệt.</span><span class="sxs-lookup"><span data-stu-id="daf9e-144">The **Measures** tab lists differentiators.</span></span> <span data-ttu-id="daf9e-145">Mỗi tab bao gồm những thông tin sau:</span><span class="sxs-lookup"><span data-stu-id="daf9e-145">Each tab includes the following details:</span></span>

- <span data-ttu-id="daf9e-146">Danh sách xếp hạng các nhân tố khác biệt, được sắp xếp theo điểm chênh lệch.</span><span class="sxs-lookup"><span data-stu-id="daf9e-146">Ranked list of differentiators, sorted by difference score.</span></span>
- <span data-ttu-id="daf9e-147">**Điểm chênh lệch** của từng nhân tố khác biệt.</span><span class="sxs-lookup"><span data-stu-id="daf9e-147">The **Difference score** for each differentiator.</span></span> <span data-ttu-id="daf9e-148">Điểm chênh lệch cho biết mức độ khác biệt của một thuộc tính giữa 2 phân khúc.</span><span class="sxs-lookup"><span data-stu-id="daf9e-148">The difference score represents the degree of difference of an attribute between two segments.</span></span> <span data-ttu-id="daf9e-149">Điểm chênh lệch càng cao thì càng có nhiều thuộc tính khác nhau giữa 2 phân khúc.</span><span class="sxs-lookup"><span data-stu-id="daf9e-149">The higher the difference score, the more the attributes differ between the two segments.</span></span> <span data-ttu-id="daf9e-150">Chọn một điểm số để mở ngăn **Điểm chênh lệch**, chứa giá trị phân phối của thuộc tính đó.</span><span class="sxs-lookup"><span data-stu-id="daf9e-150">Select a score to open the **Difference score** pane with the distributions of values for that attribute.</span></span>

## <a name="manage-segment-insights"></a><span data-ttu-id="daf9e-151">Quản lý thông tin chuyên sâu về phân khúc</span><span class="sxs-lookup"><span data-stu-id="daf9e-151">Manage segment insights</span></span>

<span data-ttu-id="daf9e-152">Từ thanh lệnh, bạn có thể dùng những tùy chọn sau cho thông tin chuyên sâu:</span><span class="sxs-lookup"><span data-stu-id="daf9e-152">You can use the following options on your insights from the command bar:</span></span>

- <span data-ttu-id="daf9e-153">**Quay lại** để trở lại danh sách thông tin chuyên sâu</span><span class="sxs-lookup"><span data-stu-id="daf9e-153">**Back** to return the list of insights</span></span>
- <span data-ttu-id="daf9e-154">**Làm mới** để chạy lại phép phân tích</span><span class="sxs-lookup"><span data-stu-id="daf9e-154">**Refresh** to run the analysis again</span></span>
- <span data-ttu-id="daf9e-155">**Xóa** để xóa thông tin chuyên sâu này</span><span class="sxs-lookup"><span data-stu-id="daf9e-155">**Delete** to remove this insight</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]