---
title: Tạo và quản lý phân đoạn
description: Tạo phân đoạn khách hàng để nhóm họ lại dựa trên các đặc điểm khác nhau.
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 550e509a24701fe5fcdeb9d54311872dc954156c
ms.sourcegitcommit: 72603fb39c4d5dbca71128815a2e1692542ea4dc
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 05/19/2021
ms.locfileid: "6064963"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="6f751-103">Tạo và quản lý phân đoạn</span><span class="sxs-lookup"><span data-stu-id="6f751-103">Create and manage segments</span></span>

<span data-ttu-id="6f751-104">Xác định các bộ lọc phức hợp xung quanh thực thể khách hàng hợp nhất và các thực thể có liên quan.</span><span class="sxs-lookup"><span data-stu-id="6f751-104">Define complex filters around the unified customer entity and its related entities.</span></span> <span data-ttu-id="6f751-105">Mỗi phân khúc, sau khi xử lý, sẽ tạo một bộ hồ sơ khách hàng mà bạn có thể xuất và hành động.</span><span class="sxs-lookup"><span data-stu-id="6f751-105">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="6f751-106">Các phân khúc được quản lý trên trang **Phân khúc**.</span><span class="sxs-lookup"><span data-stu-id="6f751-106">Segments are managed on the **Segments** page.</span></span> 

<span data-ttu-id="6f751-107">Ví dụ sau minh họa khả năng tạo phân khúc.</span><span class="sxs-lookup"><span data-stu-id="6f751-107">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="6f751-108">Chúng tôi đã xác định một phân đoạn cho khách hàng đặt hàng hóa trị giá ít nhất $500 trong 90 ngày qua *và* đã tham gia vào cuộc gọi dịch vụ khách hàng đã báo cáo.</span><span class="sxs-lookup"><span data-stu-id="6f751-108">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

:::image type="content" source="media/segmentation-group1-2.png" alt-text="Ảnh chụp màn hình của giao diện người dùng từ trình tạo phân khúc với hai nhóm chỉ định phân khúc khách hàng.":::

## <a name="create-a-new-segment"></a><span data-ttu-id="6f751-110">Tạo phân đoạn mới</span><span class="sxs-lookup"><span data-stu-id="6f751-110">Create a new segment</span></span>

<span data-ttu-id="6f751-111">Có nhiều cách để tạo một phân khúc mới.</span><span class="sxs-lookup"><span data-stu-id="6f751-111">There are multiple ways to create a new segment.</span></span> <span data-ttu-id="6f751-112">Phần này mô tả cách tạo *phân khúc trống* từ đầu.</span><span class="sxs-lookup"><span data-stu-id="6f751-112">This section describes how to create a *blank segment* from scratch.</span></span> <span data-ttu-id="6f751-113">Bạn cũng có thể tạo một *phân khúc nhanh* dựa trên các thực thể hiện có hoặc sử dụng các mô hình máy học để có được *phân khúc đề xuất*.</span><span class="sxs-lookup"><span data-stu-id="6f751-113">You can also create a *quick segment* based on existing entities or make use of machine learning models to get *suggested segments*.</span></span> <span data-ttu-id="6f751-114">Thông tin thêm: [Tổng quan về các phân khúc](segments.md).</span><span class="sxs-lookup"><span data-stu-id="6f751-114">More information: [Segments overview](segments.md).</span></span>

<span data-ttu-id="6f751-115">Trong khi tạo phân khúc, bạn có thể lưu bản nháp.</span><span class="sxs-lookup"><span data-stu-id="6f751-115">While creating a segment, you can save a draft.</span></span> <span data-ttu-id="6f751-116">Bản nháp sẽ được lưu dưới dạng một phân khúc không hoạt động và không thể kích hoạt với cấu hình hợp lệ.</span><span class="sxs-lookup"><span data-stu-id="6f751-116">It will be saved as an inactive segment, and can't be activated it finished with a valid configuration.</span></span>

1. <span data-ttu-id="6f751-117">Truy cập trang **Phân đoạn**.</span><span class="sxs-lookup"><span data-stu-id="6f751-117">Go to the **Segments** page.</span></span>

1. <span data-ttu-id="6f751-118">Chọn **Mới** > **Phân đoạn trống**.</span><span class="sxs-lookup"><span data-stu-id="6f751-118">Select **New** > **Blank segment**.</span></span>

1. <span data-ttu-id="6f751-119">Trong ngăn **Phân khúc mới**, chọn một loại phân khúc:</span><span class="sxs-lookup"><span data-stu-id="6f751-119">In the **New segment** pane, choose a segment type:</span></span>

   - <span data-ttu-id="6f751-120">**Phân khúc động** [làm mới](segments.md#refresh-segments) theo lịch trình định kỳ.</span><span class="sxs-lookup"><span data-stu-id="6f751-120">**Dynamic segments** [refresh](segments.md#refresh-segments) on a recurring schedule.</span></span>
   - <span data-ttu-id="6f751-121">**Phân khúc tĩnh** chạy một lần khi bạn khởi tạo.</span><span class="sxs-lookup"><span data-stu-id="6f751-121">**Static segments** run once when you create it.</span></span>

1. <span data-ttu-id="6f751-122">Đặt **Tên thực thể đầu ra** cho phân khúc.</span><span class="sxs-lookup"><span data-stu-id="6f751-122">Provide an **Output entity name** for the segment.</span></span> <span data-ttu-id="6f751-123">Bạn cũng có thể cung cấp tên hiển thị và mô tả nhằm xác định phân đoạn.</span><span class="sxs-lookup"><span data-stu-id="6f751-123">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

1. <span data-ttu-id="6f751-124">Chọn **Tiếp theo** để đi đến trang **Trình tạo phân đoạn** và xác định nhóm.</span><span class="sxs-lookup"><span data-stu-id="6f751-124">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="6f751-125">Một nhóm là một tập hợp các khách hàng.</span><span class="sxs-lookup"><span data-stu-id="6f751-125">A group is a set of customers.</span></span>

1. <span data-ttu-id="6f751-126">Chọn thực thể bao gồm thuộc tính mà bạn muốn tạo phân đoạn.</span><span class="sxs-lookup"><span data-stu-id="6f751-126">Choose the entity that includes the attribute you want to segment by.</span></span>

1. <span data-ttu-id="6f751-127">Chọn thuộc tính để tạo phân đoạn.</span><span class="sxs-lookup"><span data-stu-id="6f751-127">Choose the attribute to segment by.</span></span> <span data-ttu-id="6f751-128">Thuộc tính này có thể có 1 trong số 4 loại giá trị: số, chuỗi, ngày hoặc Boolean.</span><span class="sxs-lookup"><span data-stu-id="6f751-128">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

1. <span data-ttu-id="6f751-129">Chọn một toán tử và một giá trị cho thuộc tính đã chọn.</span><span class="sxs-lookup"><span data-stu-id="6f751-129">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6f751-130">![Bộ lọc nhóm tùy chỉnh](media/customer-group-numbers.png "Bộ lọc nhóm khách hàng")</span><span class="sxs-lookup"><span data-stu-id="6f751-130">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="6f751-131">Số điện thoại</span><span class="sxs-lookup"><span data-stu-id="6f751-131">Number</span></span> |<span data-ttu-id="6f751-132">Định nghĩa</span><span class="sxs-lookup"><span data-stu-id="6f751-132">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="6f751-133">1</span><span class="sxs-lookup"><span data-stu-id="6f751-133">1</span></span>     |<span data-ttu-id="6f751-134">Thực thể</span><span class="sxs-lookup"><span data-stu-id="6f751-134">Entity</span></span>          |
   |<span data-ttu-id="6f751-135">2</span><span class="sxs-lookup"><span data-stu-id="6f751-135">2</span></span>     |<span data-ttu-id="6f751-136">Thuộc tính</span><span class="sxs-lookup"><span data-stu-id="6f751-136">Attribute</span></span>          |
   |<span data-ttu-id="6f751-137">3</span><span class="sxs-lookup"><span data-stu-id="6f751-137">3</span></span>    |<span data-ttu-id="6f751-138">Toán tử</span><span class="sxs-lookup"><span data-stu-id="6f751-138">Operator</span></span>         |
   |<span data-ttu-id="6f751-139">Tệp 4</span><span class="sxs-lookup"><span data-stu-id="6f751-139">4</span></span>    |<span data-ttu-id="6f751-140">Giá trị</span><span class="sxs-lookup"><span data-stu-id="6f751-140">Value</span></span>         |

   1. <span data-ttu-id="6f751-141">Để thêm nhiều điều kiện vào một nhóm, bạn có thể sử dụng hai toán tử logic:</span><span class="sxs-lookup"><span data-stu-id="6f751-141">To add more conditions to a group, you can use two logical operators:</span></span>

      - <span data-ttu-id="6f751-142">Toán tử **AND**: Cả hai điều kiện phải được thỏa mãn như một phần của quá trình tạo phân đoạn.</span><span class="sxs-lookup"><span data-stu-id="6f751-142">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="6f751-143">Tùy chọn này hữu ích nhất khi bạn xác định các điều kiện trên các thực thể khác nhau.</span><span class="sxs-lookup"><span data-stu-id="6f751-143">This option is most useful when you define conditions across different entities.</span></span>

      - <span data-ttu-id="6f751-144">Toán tử **OR**: Một trong các điều kiện cần phải được thỏa mãn như một phần của quá trình tạo phân đoạn.</span><span class="sxs-lookup"><span data-stu-id="6f751-144">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="6f751-145">Tùy chọn này hữu ích nhất khi bạn xác định nhiều điều kiện cho cùng một thực thể.</span><span class="sxs-lookup"><span data-stu-id="6f751-145">This option is most useful when you define multiple conditions for the same entity.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="6f751-146">![Toán tử OR trong đó một trong hai điều kiện cần phải được thỏa mãn](media/segmentation-either-condition.png "Toán tử OR trong đó một trong hai điều kiện cần phải được thỏa mãn")</span><span class="sxs-lookup"><span data-stu-id="6f751-146">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

      <span data-ttu-id="6f751-147">Hiện tại, có thể lồng một toán tử **OR** trong toán tử **AND** nhưng không phải là ngược lại.</span><span class="sxs-lookup"><span data-stu-id="6f751-147">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

   1. <span data-ttu-id="6f751-148">Mỗi nhóm phù hợp với tập khách hàng.</span><span class="sxs-lookup"><span data-stu-id="6f751-148">Each group matches set of customers.</span></span> <span data-ttu-id="6f751-149">Bạn có thể kết hợp các nhóm để có được những khách hàng cần thiết cho hoạt động kinh doanh của bạn.</span><span class="sxs-lookup"><span data-stu-id="6f751-149">You can combine groups to include the customers required for your business case.</span></span>    
   <span data-ttu-id="6f751-150">Chọn **Thêm nhóm**.</span><span class="sxs-lookup"><span data-stu-id="6f751-150">Select **Add Group**.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="6f751-151">![Thêm nhóm khách hàng](media/customer-group-add-group.png "Thêm nhóm khách hàng")</span><span class="sxs-lookup"><span data-stu-id="6f751-151">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

   1. <span data-ttu-id="6f751-152">Chọn một trong các toán tử đã đặt: **Hợp nhất**, **Giao nhau** hoặc **Ngoại trừ**.</span><span class="sxs-lookup"><span data-stu-id="6f751-152">Select one of the set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6f751-153">![Thêm tập hợp nhóm khách hàng](media/customer-group-union.png "Thêm tập hợp nhóm khách hàng")</span><span class="sxs-lookup"><span data-stu-id="6f751-153">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   - <span data-ttu-id="6f751-154">**Hợp nhất** sẽ hợp nhất hai nhóm với nhau.</span><span class="sxs-lookup"><span data-stu-id="6f751-154">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="6f751-155">**Giao nhau** sẽ chồng chéo hai nhóm với nhau.</span><span class="sxs-lookup"><span data-stu-id="6f751-155">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="6f751-156">Chỉ dữ liệu *là phổ biến* cho cả hai nhóm được giữ lại trong nhóm hợp nhất.</span><span class="sxs-lookup"><span data-stu-id="6f751-156">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="6f751-157">**Trừ** kết hợp hai nhóm với nhau.</span><span class="sxs-lookup"><span data-stu-id="6f751-157">**Except** combines the two groups.</span></span> <span data-ttu-id="6f751-158">Chỉ dữ liệu trong nhóm A *là không phổ biến* cho dữ liệu trong nhóm B được giữ lại.</span><span class="sxs-lookup"><span data-stu-id="6f751-158">Only data in group A that *is not common* to data in group B is retained.</span></span>

1. <span data-ttu-id="6f751-159">Nếu thực thể được kết nối với thực thể khách hàng hợp nhất qua [các mối quan hệ](relationships.md), thì bạn cần xác định đường dẫn mối quan hệ để tạo một phân đoạn hợp lệ.</span><span class="sxs-lookup"><span data-stu-id="6f751-159">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="6f751-160">Thêm các thực thể từ đường dẫn mối quan hệ cho đến khi bạn có thể chọn thực thể **Khách hàng : CustomerInsights** từ danh sách thả xuống.</span><span class="sxs-lookup"><span data-stu-id="6f751-160">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="6f751-161">Sau đó chọn **Tất cả hồ sơ** cho mỗi bước.</span><span class="sxs-lookup"><span data-stu-id="6f751-161">Then, choose **All records** for each step.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6f751-162">![Đường dẫn mối quan hệ trong khi tạo phận đoạn](media/segments-multiple-relationships.png "Đường dẫn mối quan hệ trong khi tạo phận đoạn")</span><span class="sxs-lookup"><span data-stu-id="6f751-162">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

1. <span data-ttu-id="6f751-163">Theo mặc định, các phân khúc tạo một thực thể đầu ra chứa tất cả các thuộc tính của hồ sơ khách hàng phù hợp với các bộ lọc đã xác định.</span><span class="sxs-lookup"><span data-stu-id="6f751-163">By default, segments generate an output entity that contains all attributes of customer profiles which match the defined filters.</span></span> <span data-ttu-id="6f751-164">Nếu một phân khúc dựa trên các thực thể khác với *Khách hàng*, bạn có thể thêm nhiều thuộc tính hơn từ các thực thể này vào thực thể đầu ra.</span><span class="sxs-lookup"><span data-stu-id="6f751-164">If a segment is based on other entities than the *Customer* entity, you can add more attributes from these entities to the output entity.</span></span> <span data-ttu-id="6f751-165">Chọn **Thuộc tính dự án** để chọn các thuộc tính sẽ được thêm vào thực thể đầu ra.</span><span class="sxs-lookup"><span data-stu-id="6f751-165">Select **Project attributes** to choose the attributes that will be appended to the output entity.</span></span>  
  
   <span data-ttu-id="6f751-166">Ví dụ: Một phân khúc dựa trên một thực thể chứa dữ liệu về hoạt động khách hàng, liên quan đến thực thể *Khách hàng*.</span><span class="sxs-lookup"><span data-stu-id="6f751-166">Example: A segment is based on an entity that contains customer activity data which is related to the *Customer* entity.</span></span> <span data-ttu-id="6f751-167">Phân đoạn này tìm kiếm tất cả khách hàng đã gọi điện đến bộ phận trợ giúp trong 60 ngày qua.</span><span class="sxs-lookup"><span data-stu-id="6f751-167">The segment looks for all customers that called the help desk in the last 60 days.</span></span> <span data-ttu-id="6f751-168">Bạn có thể chọn thêm thời lượng cuộc gọi và số lượng cuộc gọi vào tất cả các bản ghi khách hàng phù hợp trong thực thể đầu ra.</span><span class="sxs-lookup"><span data-stu-id="6f751-168">You can choose to append the call duration and the number of calls to all matching customer records in the output entity.</span></span> <span data-ttu-id="6f751-169">Thông tin này có thể hữu ích để gửi một email với các liên kết hữu ích đến các bài báo trợ giúp trực tuyến và Câu hỏi thường gặp cho những khách hàng đã gọi điện thường xuyên.</span><span class="sxs-lookup"><span data-stu-id="6f751-169">This information might be useful to send an email with helpful links to online help articles and FAQs to customers who called frequently.</span></span>

   > [!NOTE]
   > - <span data-ttu-id="6f751-170">Các thuộc tính dự kiến chỉ hoạt động với các thực thể có mối quan hệ một-nhiều với thực thể khách hàng.</span><span class="sxs-lookup"><span data-stu-id="6f751-170">Projected attributes only work for entities that have a one-to-many relationship with the customer entity.</span></span> <span data-ttu-id="6f751-171">Ví dụ: một khách hàng có thể có nhiều gói đăng ký.</span><span class="sxs-lookup"><span data-stu-id="6f751-171">For example, one customer can have multiple subscriptions.</span></span>
   > - <span data-ttu-id="6f751-172">Bạn chỉ có thể chiếu các thuộc tính từ một thực thể được sử dụng trong tất cả các nhóm truy vấn phân khúc mà bạn đang tạo.</span><span class="sxs-lookup"><span data-stu-id="6f751-172">You can only project attributes from an entity that is used in every group of segment query you are building.</span></span>
   > - <span data-ttu-id="6f751-173">Các thuộc tính dự kiến được coi như yếu tố khi sử dụng các toán tử tập hợp.</span><span class="sxs-lookup"><span data-stu-id="6f751-173">Projected attributes are factored in when using set operators.</span></span>

1. <span data-ttu-id="6f751-174">Chọn **Lưu** để lưu phân đoạn của bạn.</span><span class="sxs-lookup"><span data-stu-id="6f751-174">Select **Save** to save your segment.</span></span> <span data-ttu-id="6f751-175">Phân đoạn của bạn sẽ được lưu và xử lý nếu tất cả các yêu cầu được xác thực.</span><span class="sxs-lookup"><span data-stu-id="6f751-175">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="6f751-176">Nếu không, nó sẽ được lưu dưới dạng bản nháp.</span><span class="sxs-lookup"><span data-stu-id="6f751-176">Otherwise, it will be saved as a draft.</span></span>

1. <span data-ttu-id="6f751-177">Chọn **Quay lại phân khúc** để quay lại trang **Phân khúc**.</span><span class="sxs-lookup"><span data-stu-id="6f751-177">Select **Back to segments** to go back to the **Segments** page.</span></span>



## <a name="quick-segments"></a><span data-ttu-id="6f751-178">Phân đoạn nhanh</span><span class="sxs-lookup"><span data-stu-id="6f751-178">Quick segments</span></span>

<span data-ttu-id="6f751-179">Phân khúc nhanh cho phép bạn tạo nhanh các phân khúc đơn giản với một toán tử để có thông tin chi tiết nhanh chóng hơn.</span><span class="sxs-lookup"><span data-stu-id="6f751-179">Quick segments let you build simple segments with a single operator quickly for faster insights.</span></span>

1. <span data-ttu-id="6f751-180">Trên trang **Phân khúc**, chọn **Mới** > **Tạo từ**.</span><span class="sxs-lookup"><span data-stu-id="6f751-180">On the **Segments** page, select **New** > **Create from**.</span></span>

   - <span data-ttu-id="6f751-181">Chọn **Hồ sơ** để xây dựng phân khúc dựa trên thực thể *khách hàng hợp nhất*.</span><span class="sxs-lookup"><span data-stu-id="6f751-181">Select the **Profiles** option to build a segment that is based on the *unified customer* entity.</span></span>
   - <span data-ttu-id="6f751-182">Chọn các tùy chọn **Biện pháp** để xây dựng một phân khúc xung quanh các biện pháp bạn đã tạo trước đó.</span><span class="sxs-lookup"><span data-stu-id="6f751-182">Select the **Measures** option to build a segment around  measures you have previously created.</span></span>
   - <span data-ttu-id="6f751-183">Chọn tùy chọn **Thông tin** để xây dựng một phân đoạn xung quanh một trong các thực thể đầu ra mà bạn tạo bằng một trong hai chức năng **Dự đoán** hoặc **Mô hình tùy chỉnh**.</span><span class="sxs-lookup"><span data-stu-id="6f751-183">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="6f751-184">Trong hộp thoại **Phân đoạn nhanh mới**, hãy chọn một thuộc tính từ mục thả xuống **Trường**.</span><span class="sxs-lookup"><span data-stu-id="6f751-184">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="6f751-185">Hệ thống sẽ cung cấp thêm một số thông tin chi tiết để giúp bạn tạo các phân đoạn khách hàng tốt hơn.</span><span class="sxs-lookup"><span data-stu-id="6f751-185">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="6f751-186">Đối với các trường có phân loại, chúng tôi sẽ hiển thị 10 lượt khách hàng tốt nhất.</span><span class="sxs-lookup"><span data-stu-id="6f751-186">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="6f751-187">Chọn **Giá trị** rồi chọn **Xem lại**.</span><span class="sxs-lookup"><span data-stu-id="6f751-187">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="6f751-188">Đối với một thuộc tính số, hệ thống sẽ hiển thị giá trị thuộc tính nào nằm trong phần trăm của mỗi khách hàng.</span><span class="sxs-lookup"><span data-stu-id="6f751-188">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="6f751-189">Chọn một **Toán tử** và một **Giá trị**, sau đó chọn **Xem lại**.</span><span class="sxs-lookup"><span data-stu-id="6f751-189">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="6f751-190">Hệ thống sẽ cung cấp cho bạn một **Kích cỡ phân đoạn ước tính**.</span><span class="sxs-lookup"><span data-stu-id="6f751-190">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="6f751-191">Bạn có thể chọn tạo phân đoạn bạn đã xác định hoặc truy cập lại vào phân đoạn đó để có kích cỡ phân đoạn khác.</span><span class="sxs-lookup"><span data-stu-id="6f751-191">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="6f751-192">![Tên và ước tính cho một phân đoạn nhanh](media/quick-segment-name.png "Tên và ước tính cho một phân đoạn nhanh")</span><span class="sxs-lookup"><span data-stu-id="6f751-192">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="6f751-193">Đặt **Tên** cho phân đoạn của bạn.</span><span class="sxs-lookup"><span data-stu-id="6f751-193">Provide a **Name** for your segment.</span></span> <span data-ttu-id="6f751-194">Bạn cũng có thể cung cấp **Tên hiển thị**.</span><span class="sxs-lookup"><span data-stu-id="6f751-194">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="6f751-195">Chọn **Lưu** để tạo phân đoạn.</span><span class="sxs-lookup"><span data-stu-id="6f751-195">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="6f751-196">Sau khi phân đoạn đã xử lý xong, bạn có thể xem nó như bất kỳ phân đoạn nào khác mà bạn đã tạo.</span><span class="sxs-lookup"><span data-stu-id="6f751-196">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

## <a name="next-steps"></a><span data-ttu-id="6f751-197">Các bước tiếp theo</span><span class="sxs-lookup"><span data-stu-id="6f751-197">Next steps</span></span>

<span data-ttu-id="6f751-198">[Xuất phân đoạn](export-destinations.md) và khám phá [Thẻ khách hàng](customer-card-add-in.md) và [Bộ kết nối](export-power-bi.md) để nắm được thông tin chi tiết ở cấp độ khách hàng.</span><span class="sxs-lookup"><span data-stu-id="6f751-198">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
