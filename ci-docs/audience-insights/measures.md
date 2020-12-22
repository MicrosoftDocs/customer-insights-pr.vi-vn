---
title: Tạo và chỉnh sửa các giá trị đo
description: Xác định các chỉ số đo lường liên quan đến khách hàng để phân tích và phản ánh hiệu suất của các lĩnh vực kinh doanh nhất định.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 0e214a6eb66abd27f7292db3ce2c2a6e16a8ff33
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407332"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="4301a-103">Xác định và quản lý các biện pháp</span><span class="sxs-lookup"><span data-stu-id="4301a-103">Define and manage measures</span></span>

<span data-ttu-id="4301a-104">**Giá trị đo** đại diện cho các chỉ số đo lường hiệu suất chính (KPI) phản ánh hiệu suất và tình trạng của các lĩnh vực kinh doanh cụ thể.</span><span class="sxs-lookup"><span data-stu-id="4301a-104">**Measures** represent key performance indicators (KPIs) that reflect the performance and health of specific business areas.</span></span> <span data-ttu-id="4301a-105">Thông tin chi tiết về đối tượng cung cấp trải nghiệm trực quan để xây dựng các loại giá trị đo khác nhau, sử dụng trình tạo truy vấn không yêu cầu bạn viết mã hoặc xác thực các giá trị đo của mình theo cách thủ công.</span><span class="sxs-lookup"><span data-stu-id="4301a-105">Audience insights provides an intuitive experience for building different types of measures, using a query builder that doesn't require you to code or validate your measures manually.</span></span> <span data-ttu-id="4301a-106">Bạn có thể theo dõi các giá trị đo công việc trên **Trang chủ**, xem các giá trị đo cho khách hàng cụ thể trên **Thẻ khách hàng** và sử dụng các giá trị đo để xác định phân khúc khách hàng trên trang **Phân khúc**.</span><span class="sxs-lookup"><span data-stu-id="4301a-106">You can track your business measures on the **Home** page, see measures for specific customers on the **Customer Card**, and use measures to define customer segments on the **Segments** page.</span></span>

## <a name="create-a-measure"></a><span data-ttu-id="4301a-107">Tạo giá trị đo</span><span class="sxs-lookup"><span data-stu-id="4301a-107">Create a measure</span></span>

<span data-ttu-id="4301a-108">Phần này hướng dẫn bạn tạo một giá trị đo từ đầu.</span><span class="sxs-lookup"><span data-stu-id="4301a-108">This section walks you through creating a measure from scratch.</span></span> <span data-ttu-id="4301a-109">Bạn có thể xây dựng các giá trị đo với dữ liệu từ nhiều nguồn dữ liệu được kết nối thông qua thực thể Khách hàng.</span><span class="sxs-lookup"><span data-stu-id="4301a-109">You can build measures with data from multiple data sources that are connected through the Customer entity.</span></span> <span data-ttu-id="4301a-110">Một số [giới hạn dịch vụ](service-limits.md) được áp dụng.</span><span class="sxs-lookup"><span data-stu-id="4301a-110">Some [service limits](service-limits.md) apply.</span></span>

1. <span data-ttu-id="4301a-111">Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Giá trị đo**.</span><span class="sxs-lookup"><span data-stu-id="4301a-111">In audience insights, go to **Measures**.</span></span>

2. <span data-ttu-id="4301a-112">Chọn **Giá trị đo mới**.</span><span class="sxs-lookup"><span data-stu-id="4301a-112">Select **New measure**.</span></span>

3. <span data-ttu-id="4301a-113">Chọn giá trị **Loại**:</span><span class="sxs-lookup"><span data-stu-id="4301a-113">Choose the measure **Type**:</span></span>

   - <span data-ttu-id="4301a-114">**Thuộc tính khách hàng**: Một trường duy nhất cho mỗi khách hàng phản ánh điểm số, giá trị hoặc trạng thái cho khách hàng.</span><span class="sxs-lookup"><span data-stu-id="4301a-114">**Customer attribute**: A single field per customer that reflects a score, value, or state for the customer.</span></span> <span data-ttu-id="4301a-115">Các thuộc tính khách hàng được tạo như các thuộc tính trong một thực thể mới do hệ thống tạo ra được gọi là **Giá trị đo Khách hàng**.</span><span class="sxs-lookup"><span data-stu-id="4301a-115">Customer attributes are created as attributes in a new system-generated entity called **Customer_Measure**.</span></span>

   - <span data-ttu-id="4301a-116">**Giá trị đo khách hàng**: Thông tin chi tiết về hành vi của khách hàng được phân tích theo các chỉ số đã chọn.</span><span class="sxs-lookup"><span data-stu-id="4301a-116">**Customer measure**: Insights on customer behavior with breakdown by selected dimensions.</span></span> <span data-ttu-id="4301a-117">Một thực thể mới được tạo cho mỗi giá trị đo, có khả năng có nhiều hồ sơ cho mỗi khách hàng.</span><span class="sxs-lookup"><span data-stu-id="4301a-117">A new entity is generated for each measure, potentially with multiple records per customer.</span></span>

   - <span data-ttu-id="4301a-118">**Giá trị đo công việc**: Theo dõi hiệu suất kinh doanh và tình trạng của doanh nghiệp.</span><span class="sxs-lookup"><span data-stu-id="4301a-118">**Business measure**: Tracks your business performance and health of the business.</span></span> <span data-ttu-id="4301a-119">Các giá trị đo công việc có thể có hai đầu ra khác nhau: đầu ra số hiển thị trên **Trang chủ** hoặc một thực thể mới mà bạn tìm thấy trên trang **Các thực thể**.</span><span class="sxs-lookup"><span data-stu-id="4301a-119">Business measures can have two different outputs: a numeric output that shows on the **Home** page or a new entity that you find on the **Entities** page.</span></span>

4. <span data-ttu-id="4301a-120">Cung cấp một **Tên** và một **Tên hiển thị** hiển thị, sau đó chọn **Tiếp theo**.</span><span class="sxs-lookup"><span data-stu-id="4301a-120">Provide a **Name** and an optional **Display name**, then select **Next**.</span></span>

5. <span data-ttu-id="4301a-121">Trong phần **Thực thể**, chọn thực thể đầu tiên từ danh sách thả xuống.</span><span class="sxs-lookup"><span data-stu-id="4301a-121">In the **Entities** section, select the first entity from the drop-down list.</span></span> <span data-ttu-id="4301a-122">Tại thời điểm này, bạn nên quyết định xem có cần thực thể bổ sung như là một phần của định nghĩa giá trị đo của bạn hay không.</span><span class="sxs-lookup"><span data-stu-id="4301a-122">At this point, you should decide whether additional entities are needed as part of your measure definition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="4301a-123">![Định nghĩa số liệu đo lường](media/measure-definition.png "Định nghĩa số liệu đo lường")</span><span class="sxs-lookup"><span data-stu-id="4301a-123">![Measure definition](media/measure-definition.png "Measure definition")</span></span>

   <span data-ttu-id="4301a-124">Để thêm các thực thể khác, chọn **Thêm thực thể** và chọn thực thể bạn muốn dùng cho giá trị đo đó.</span><span class="sxs-lookup"><span data-stu-id="4301a-124">To add more entities, select **Add entity** and select entities you want to use for the measure.</span></span>

   > [!NOTE]
   > <span data-ttu-id="4301a-125">Bạn chỉ có thể chọn các thực thể có mối quan hệ với thực thể bắt đầu của bạn.</span><span class="sxs-lookup"><span data-stu-id="4301a-125">You can select only entities that have relationships to your starting entity.</span></span> <span data-ttu-id="4301a-126">Để biết thêm thông tin định nghĩa mối quan hệ, hãy xem [Mối quan hệ](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="4301a-126">For more information about defining relationships, see [Relationships](relationships.md).</span></span>

6. <span data-ttu-id="4301a-127">Hoặc bạn có thể cấu hình các biến.</span><span class="sxs-lookup"><span data-stu-id="4301a-127">Optionally, you can configure variables.</span></span> <span data-ttu-id="4301a-128">Trong phần **Biến**, chọn **Biến mới**.</span><span class="sxs-lookup"><span data-stu-id="4301a-128">In the **Variables** section, select **New variable**.</span></span>

   <span data-ttu-id="4301a-129">Các biến là các tính toán được thực hiện trên mỗi bản ghi đã chọn của bạn.</span><span class="sxs-lookup"><span data-stu-id="4301a-129">Variables are calculations that are made on each of your selected records.</span></span> <span data-ttu-id="4301a-130">Ví dụ: tổng hợp điểm bán hàng (POS) và bán hàng trực tuyến cho mỗi hồ sơ của khách hàng của bạn.</span><span class="sxs-lookup"><span data-stu-id="4301a-130">For example, summing point-of-sale (POS) and online sales for each of your customers' records.</span></span>

7. <span data-ttu-id="4301a-131">Cung cấp **Tên** cho biến.</span><span class="sxs-lookup"><span data-stu-id="4301a-131">Provide a **Name** for the variable.</span></span>

8. <span data-ttu-id="4301a-132">Trong khu vực **Biểu thức**, chọn một trường để bắt đầu tính toán.</span><span class="sxs-lookup"><span data-stu-id="4301a-132">In the **Expression** area, choose a field to begin your calculation with.</span></span>

9. <span data-ttu-id="4301a-133">Nhập một biểu thức trong khu vực **Biểu thức** trong khi chọn nhiều trường được đưa vào tính toán của bạn.</span><span class="sxs-lookup"><span data-stu-id="4301a-133">Type an expression in the **Expression** area while choosing more fields to be included in your calculation.</span></span>

   > [!NOTE]
   > <span data-ttu-id="4301a-134">Hiện tại, chỉ có biểu thức số học được hỗ trợ.</span><span class="sxs-lookup"><span data-stu-id="4301a-134">Currently, only arithmetic expressions are supported.</span></span> <span data-ttu-id="4301a-135">Ngoài ra, tính toán biến không được hỗ trợ cho các thực thể từ [đường dẫn thực thể](relationships.md) khác.</span><span class="sxs-lookup"><span data-stu-id="4301a-135">Additionally, variable calculation isn't supported for entities from different [entity paths](relationships.md).</span></span>

10. <span data-ttu-id="4301a-136">Chọn **Xong**.</span><span class="sxs-lookup"><span data-stu-id="4301a-136">Select **Done**.</span></span>

11. <span data-ttu-id="4301a-137">Trong phần **Định nghĩa số liệu đo lường**, bạn sẽ xác định cách các thực thể được chọn và các biến được tính toán được tổng hợp trong một thực thể hoặc thuộc tính đo lường mới.</span><span class="sxs-lookup"><span data-stu-id="4301a-137">In the **Measure definition** section, you'll define how your chosen entities and calculated variables are aggregated in a new measure entity or attribute.</span></span>

12. <span data-ttu-id="4301a-138">Chọn **Kích thước mới**.</span><span class="sxs-lookup"><span data-stu-id="4301a-138">Select **New dimension**.</span></span> <span data-ttu-id="4301a-139">Bạn có thể coi một kích thước là một hàm *nhóm theo*.</span><span class="sxs-lookup"><span data-stu-id="4301a-139">You can think of a dimension as a *group by* function.</span></span> <span data-ttu-id="4301a-140">Đầu ra dữ liệu của thực thể hoặc thuộc tính Giá trị đo sẽ được nhóm theo tất cả kích thước bạn xác định.</span><span class="sxs-lookup"><span data-stu-id="4301a-140">The data output of your Measure entity or attribute will be grouped by all of your defined dimensions.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="4301a-141">![Chọn chu kỳ tổng hợp](media/measures-businessreport-measure-definition2.png "Chọn chu kỳ tổng hợp")</span><span class="sxs-lookup"><span data-stu-id="4301a-141">![Choose aggregate cycle](media/measures-businessreport-measure-definition2.png "Choose aggregate cycle")</span></span>

    <span data-ttu-id="4301a-142">Chọn hoặc nhập thông tin sau đây như một phần định nghĩa của kích thước của bạn:</span><span class="sxs-lookup"><span data-stu-id="4301a-142">Select or enter the following information as part of your dimension's definition:</span></span>

    - <span data-ttu-id="4301a-143">**Thực thể**: Nếu bạn xác định thực thể Giá trị đo, nó sẽ bao gồm ít nhất một thuộc tính.</span><span class="sxs-lookup"><span data-stu-id="4301a-143">**Entity**: If you define a Measure entity, it should include at least one attribute.</span></span> <span data-ttu-id="4301a-144">Nếu bạn xác định thuộc tính Giá trị đo, nó sẽ chỉ bao gồm một thuộc tính theo mặc định.</span><span class="sxs-lookup"><span data-stu-id="4301a-144">If you define a Measure attribute, it will include only one attribute by default.</span></span> <span data-ttu-id="4301a-145">Lựa chọn này là về việc chọn thực thể bao gồm thuộc tính đó.</span><span class="sxs-lookup"><span data-stu-id="4301a-145">This selection is about choosing the entity that includes that attribute.</span></span>
    - <span data-ttu-id="4301a-146">**Trường**: Chọn thuộc tính cụ thể được bao gồm trong thực thể hoặc thuộc tính Giá trị đo.</span><span class="sxs-lookup"><span data-stu-id="4301a-146">**Field**: Choose the specific attribute to be included either in your Measure entity or attribute.</span></span>
    - <span data-ttu-id="4301a-147">**Bộ chứa**: Chọn xem bạn muốn tổng hợp dữ liệu hàng ngày, hàng tháng hoặc hàng năm.</span><span class="sxs-lookup"><span data-stu-id="4301a-147">**Bucket**: Choose whether you want to aggregate data on a daily, monthly, or annual basis.</span></span> <span data-ttu-id="4301a-148">Đó chỉ là lựa chọn bắt buộc nếu bạn đã chọn thuộc tính loại Ngày.</span><span class="sxs-lookup"><span data-stu-id="4301a-148">It's a required selection only if you've selected a Date type attribute.</span></span>
    - <span data-ttu-id="4301a-149">**Dưới dạng**: Xác định tên của trường mới của bạn.</span><span class="sxs-lookup"><span data-stu-id="4301a-149">**As**: Defines the name of your new field.</span></span>
    - <span data-ttu-id="4301a-150">**Tên hiển thị**: Xác định tên hiển thị của trường của bạn.</span><span class="sxs-lookup"><span data-stu-id="4301a-150">**Display name**: Defines the display name of your field.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4301a-151">Giá trị đo công việc của bạn sẽ được lưu dưới dạng một thực thể số đơn và sẽ xuất hiện trên **Trang chủ** trừ khi bạn thêm nhiều kích thước vào số đo của bạn.</span><span class="sxs-lookup"><span data-stu-id="4301a-151">Your business measure will be saved as a single-number entity and will appear on the **Home** page unless you add more dimensions to your measure.</span></span> <span data-ttu-id="4301a-152">Sau khi thêm nhiều kích thước, giá trị đo sẽ *không* hiện lên trên **Trang chủ**.</span><span class="sxs-lookup"><span data-stu-id="4301a-152">After adding more dimensions, the measure will *not* show up on the **Home** page.</span></span>

13. <span data-ttu-id="4301a-153">Bạn cũng có thể thêm các hàm tổng hợp.</span><span class="sxs-lookup"><span data-stu-id="4301a-153">Optionally, add aggregation functions.</span></span> <span data-ttu-id="4301a-154">Bất kỳ tổng hợp nào bạn tạo sẽ dẫn đến trong một giá trị mới trong thực thể hoặc thuộc tính Giá trị đo.</span><span class="sxs-lookup"><span data-stu-id="4301a-154">Any aggregation that you create results in a new value within your Measures entity or attribute.</span></span> <span data-ttu-id="4301a-155">Các hàm tổng hợp được hỗ trợ là: **Min**, **Max**, **Average**, **Median**, **Sum**, **Count Unique**, **First** (lấy bản ghi đầu tiên của giá trị chỉ số) và **Last** (lấy bản ghi cuối cùng được thêm vào giá trị chỉ số).</span><span class="sxs-lookup"><span data-stu-id="4301a-155">Supported aggregation functions are: **Min**, **Max**, **Average**, **Median**, **Sum**, **Count Unique**, **First** (takes the first record of a dimension value), and **Last** (takes the last record added to a dimension value).</span></span>

14. <span data-ttu-id="4301a-156">Chọn **Lưu** để áp dụng các thay đổi cho giá trị đo.</span><span class="sxs-lookup"><span data-stu-id="4301a-156">Select **Save** to apply your changes to the measure.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="4301a-157">Quản lý các giá trị đo của bạn</span><span class="sxs-lookup"><span data-stu-id="4301a-157">Manage your measures</span></span>

<span data-ttu-id="4301a-158">Sau khi tạo ít nhất một giá trị đo, bạn sẽ thấy danh sách các giá trị đo trên trang **Giá trị đo**.</span><span class="sxs-lookup"><span data-stu-id="4301a-158">After creating at least one measure, you'll see a list of measures on the **Measures** page.</span></span>

<span data-ttu-id="4301a-159">Bạn sẽ tìm thấy thông tin về loại giá trị đo, người tạo, ngày và giờ tạo, ngày và giờ chỉnh sửa cuối cùng, trạng thái (cho dù giá trị đo đó đang hoạt động, không hoạt động hay lỗi) và ngày và giờ làm mới lần cuối.</span><span class="sxs-lookup"><span data-stu-id="4301a-159">You'll find information about the measure type, the creator, creation date and time, last edit date and time, status (whether the measure is active, inactive, or failed), and last refresh date and time.</span></span> <span data-ttu-id="4301a-160">Khi bạn chọn một giá trị đo từ danh sách, bạn có thể thấy bản xem trước của đầu ra.</span><span class="sxs-lookup"><span data-stu-id="4301a-160">When you select a measure from the list, you can see a preview of its output.</span></span>

<span data-ttu-id="4301a-161">Để làm mới tất cả các giá trị đo của bạn cùng một lúc, hãy chọn **Làm mới tất cả** mà không chọn một giá trị đo cụ thể.</span><span class="sxs-lookup"><span data-stu-id="4301a-161">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="4301a-162">![Các hành động để quản lý các giá trị đo đơn lẻ](media/measure-actions.png "Các hành động để quản lý các giá trị đo đơn lẻ")</span><span class="sxs-lookup"><span data-stu-id="4301a-162">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="4301a-163">Hoặc, chọn một giá trị đo từ danh sách và thực hiện một trong các hành động sau:</span><span class="sxs-lookup"><span data-stu-id="4301a-163">Alternatively, select a measure from the list and perform one of the following actions:</span></span>

- <span data-ttu-id="4301a-164">Chọn tên giá trị đo để xem chi tiết về giá trị đo đó.</span><span class="sxs-lookup"><span data-stu-id="4301a-164">Select the measure name to see its details.</span></span>
- <span data-ttu-id="4301a-165">**Chỉnh sửa** cấu hình của giá trị đo.</span><span class="sxs-lookup"><span data-stu-id="4301a-165">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="4301a-166">**Đổi tên** giá trị đo.</span><span class="sxs-lookup"><span data-stu-id="4301a-166">**Rename** the measure.</span></span>
- <span data-ttu-id="4301a-167">**Xóa** giá trị đo.</span><span class="sxs-lookup"><span data-stu-id="4301a-167">**Delete** the measure.</span></span>
- <span data-ttu-id="4301a-168">Chọn dấu chấm lửng (...) rồi sau đó **Làm mới** để bắt đầu quá trình làm mới cho giá trị đo.</span><span class="sxs-lookup"><span data-stu-id="4301a-168">Select the ellipsis (...) and then **Refresh** to start the refresh process for the measure.</span></span>
- <span data-ttu-id="4301a-169">Chọn dấu chấm lửng (...) và sau đó **Tải xuống** để tải tệp .CSV của giá trị đo.</span><span class="sxs-lookup"><span data-stu-id="4301a-169">Select the ellipsis (...) and then **Download** to get a .CSV file of the measure.</span></span>

> [!TIP]
> <span data-ttu-id="4301a-170">Có [6 loại trạng thái](system.md#status-types) cho các nhiệm vụ/quy trình.</span><span class="sxs-lookup"><span data-stu-id="4301a-170">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="4301a-171">Ngoài ra, hầu hết các quy trình [phụ thuộc vào các quá trình hạ nguồn khác](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="4301a-171">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="4301a-172">Bạn có thể chọn trạng thái của một quy trình để xem chi tiết về tiến trình của toàn bộ công việc.</span><span class="sxs-lookup"><span data-stu-id="4301a-172">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="4301a-173">Sau khi chọn **Xem chi tiết** đối với một trong các tác vụ của công việc, bạn sẽ tìm thấy thông tin bổ sung: thời gian xử lý, ngày xử lý gần nhất và tất cả các lỗi và cảnh báo liên quan đến tác vụ.</span><span class="sxs-lookup"><span data-stu-id="4301a-173">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="4301a-174">Bước tiếp theo</span><span class="sxs-lookup"><span data-stu-id="4301a-174">Next step</span></span>

<span data-ttu-id="4301a-175">Bạn có thể sử dụng các giá trị đo hiện có để tạo phân khúc khách hàng đầu tiên của mình trên trang **Phân khúc**.</span><span class="sxs-lookup"><span data-stu-id="4301a-175">You cam use existing measures to create your first customer segment on the **Segments** page.</span></span> <span data-ttu-id="4301a-176">Để biết thêm thông tin, hãy xem [Phân khúc](segments.md).</span><span class="sxs-lookup"><span data-stu-id="4301a-176">For more information, see [Segments](segments.md).</span></span>
