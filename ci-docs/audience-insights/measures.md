---
title: Tạo và quản lý các giá trị đo
description: Xác định các giá trị đo để phân tích và phản ánh tình hình hoạt động của doanh nghiệp bạn.
ms.date: 02/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 202ea22d290be04e54ce9676b6b693162354607f
ms.sourcegitcommit: d3eb07dcc72624a2d5cfc95c7ea9faaa2c1b6001
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 03/16/2021
ms.locfileid: "5654758"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="bb0cd-103">Xác định và quản lý các biện pháp</span><span class="sxs-lookup"><span data-stu-id="bb0cd-103">Define and manage measures</span></span>

<span data-ttu-id="bb0cd-104">Các giá trị đo giúp bạn hiểu rõ hơn về hành vi của khách hàng và hiệu suất kinh doanh bằng cách truy xuất các giá trị có liên quan từ [hồ sơ thống nhất](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="bb0cd-104">Measures help you to better understand customer behaviors and business performance by retrieving relevant values from [unified profiles](data-unification.md).</span></span> <span data-ttu-id="bb0cd-105">Ví dụ: một doanh nghiệp muốn xem *tổng chi tiêu mỗi khách hàng* để hiểu lịch sử mua hàng của từng khách hàng.</span><span class="sxs-lookup"><span data-stu-id="bb0cd-105">For example, a business wants to see the *total spend per customer* to understand individual customer’s purchase history.</span></span> <span data-ttu-id="bb0cd-106">Hoặc đo lường *tổng doanh số của công ty* để hiểu tổng doanh thu trong toàn bộ doanh nghiệp.</span><span class="sxs-lookup"><span data-stu-id="bb0cd-106">Or measure *total sales of the company* to understand the aggregate-level revenue in the whole business.</span></span>  

<span data-ttu-id="bb0cd-107">Các giá trị đo được tạo bằng cách sử dụng trình tạo giá trị đo, một nền tảng truy vấn dữ liệu với các toán tử khác nhau và các tùy chọn ánh xạ đơn giản.</span><span class="sxs-lookup"><span data-stu-id="bb0cd-107">Measures are created using the measure builder, a data query platform with various operators and simple mapping options.</span></span> <span data-ttu-id="bb0cd-108">Nó cho phép bạn lọc dữ liệu, nhóm kết quả, phát hiện [đường dẫn mối quan hệ thực thể](relationships.md) và xem trước đầu ra.</span><span class="sxs-lookup"><span data-stu-id="bb0cd-108">It lets you filter the data, group results, detect [entity relationship paths](relationships.md), and preview the output.</span></span>

<span data-ttu-id="bb0cd-109">Hãy sử dụng trình tạo giá trị đo để lập kế hoạch hoạt động kinh doanh bằng cách truy vấn dữ liệu khách hàng và trích xuất thông tin chi tiết.</span><span class="sxs-lookup"><span data-stu-id="bb0cd-109">Use the measure builder to plan business activities by querying customer data and extract insights.</span></span> <span data-ttu-id="bb0cd-110">Ví dụ: tạo một giá trị đo *tổng chi tiêu mỗi khách hàng* và *tổng lợi nhuận trên mỗi khách hàng* giúp xác định nhóm khách hàng có mức chi tiêu cao nhưng lợi nhuận thu về cao.</span><span class="sxs-lookup"><span data-stu-id="bb0cd-110">For example, creating a measure of *total spend per customer* and *total return per customer* helps identify a group of customers with high spend yet high return.</span></span> <span data-ttu-id="bb0cd-111">Bạn có thể [tạo một phân đoạn](segments.md) để thúc đẩy các hành động tốt nhất tiếp theo.</span><span class="sxs-lookup"><span data-stu-id="bb0cd-111">You can [create a segment](segments.md) to drive next best actions.</span></span> 

## <a name="create-a-measure"></a><span data-ttu-id="bb0cd-112">Tạo giá trị đo</span><span class="sxs-lookup"><span data-stu-id="bb0cd-112">Create a measure</span></span>

<span data-ttu-id="bb0cd-113">Phần này sẽ hướng dẫn bạn cách tạo một giá trị đo mới từ đầu.</span><span class="sxs-lookup"><span data-stu-id="bb0cd-113">This section walks you through creating a new measure from scratch.</span></span> <span data-ttu-id="bb0cd-114">Bạn có thể tạo một giá trị đo với các thuộc tính dữ liệu từ các thực thể dữ liệu có mối quan hệ được thiết lập để kết nối với thực thể Khách hàng.</span><span class="sxs-lookup"><span data-stu-id="bb0cd-114">You can build a measure with data attributes from data entities that have a relationship set up to connect with the Customer entity.</span></span> 

1. <span data-ttu-id="bb0cd-115">Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Giá trị đo**.</span><span class="sxs-lookup"><span data-stu-id="bb0cd-115">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="bb0cd-116">Chọn **Mới**.</span><span class="sxs-lookup"><span data-stu-id="bb0cd-116">Select **New**.</span></span>

1. <span data-ttu-id="bb0cd-117">Chọn **Chỉnh sửa tên** và cung cấp một **Tên** cho giá trị đo.</span><span class="sxs-lookup"><span data-stu-id="bb0cd-117">Select **Edit name** and provide a **Name** for the measure.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="bb0cd-118">Nếu cấu hình giá trị đo mới của bạn chỉ có hai trường, ví dụ CustomerID và một phép tính, đầu ra sẽ được thêm dưới dạng một cột mới vào thực thể do hệ thống tạo có tên là Customer_Measure.</span><span class="sxs-lookup"><span data-stu-id="bb0cd-118">If your new measure configuration has only two fields, for exmample, CustomerID and one calculation, the output will be added as a new column to the system generated entity called Customer_Measure.</span></span> <span data-ttu-id="bb0cd-119">Và bạn sẽ có thể thấy giá trị của giá trị đo trong hồ sơ khách hàng hợp nhất.</span><span class="sxs-lookup"><span data-stu-id="bb0cd-119">And you will be able to see the measure’s value in the unified customer profile.</span></span> <span data-ttu-id="bb0cd-120">Các giá trị đo khác sẽ tạo ra các thực thể của riêng chúng.</span><span class="sxs-lookup"><span data-stu-id="bb0cd-120">Other measures will generate their own entities.</span></span>

1. <span data-ttu-id="bb0cd-121">Trong vùng cấu hình, hãy chọn hàm tổng hợp từ menu thả xuống **Chọn hàm**.</span><span class="sxs-lookup"><span data-stu-id="bb0cd-121">In the configuration area, choose the aggregation function from the **Select Function** drop-down menu.</span></span> <span data-ttu-id="bb0cd-122">Các hàm tổng hợp bao gồm:</span><span class="sxs-lookup"><span data-stu-id="bb0cd-122">Aggregation functions include:</span></span> 
   - <span data-ttu-id="bb0cd-123">**Sum**</span><span class="sxs-lookup"><span data-stu-id="bb0cd-123">**Sum**</span></span>
   - <span data-ttu-id="bb0cd-124">**Trung bình**</span><span class="sxs-lookup"><span data-stu-id="bb0cd-124">**Average**</span></span>
   - <span data-ttu-id="bb0cd-125">**Đếm**</span><span class="sxs-lookup"><span data-stu-id="bb0cd-125">**Count**</span></span>
   - <span data-ttu-id="bb0cd-126">**Số đếm Duy nhất**</span><span class="sxs-lookup"><span data-stu-id="bb0cd-126">**Count Unique**</span></span>
   - <span data-ttu-id="bb0cd-127">**Tối đa**</span><span class="sxs-lookup"><span data-stu-id="bb0cd-127">**Max**</span></span>
   - <span data-ttu-id="bb0cd-128">**Min**</span><span class="sxs-lookup"><span data-stu-id="bb0cd-128">**Min**</span></span>
   - <span data-ttu-id="bb0cd-129">**Đầu tiên**: lấy giá trị đầu tiên của bản ghi dữ liệu</span><span class="sxs-lookup"><span data-stu-id="bb0cd-129">**First**: takes the first value of the data record</span></span>
   - <span data-ttu-id="bb0cd-130">**Cuối cùng**: lấy giá trị cuối cùng đã được thêm vào bản ghi dữ liệu</span><span class="sxs-lookup"><span data-stu-id="bb0cd-130">**Last**: takes the last value that was added to the data record</span></span>

   :::image type="content" source="media/measure-operators.png" alt-text="Các toán tử để tính toán giá trị đo.":::

1. <span data-ttu-id="bb0cd-132">Chọn **Thêm thuộc tính** để chọn dữ liệu bạn cần để tạo giá trị đo này.</span><span class="sxs-lookup"><span data-stu-id="bb0cd-132">Select **Add attribute** to select the data you need to create this measure.</span></span>
   
   1. <span data-ttu-id="bb0cd-133">Chọn thẻ **Thuộc tính**.</span><span class="sxs-lookup"><span data-stu-id="bb0cd-133">Select the **Attributes** tab.</span></span> 
   1. <span data-ttu-id="bb0cd-134">Thực thể dữ liệu: Chọn thực thể bao gồm thuộc tính bạn muốn đo.</span><span class="sxs-lookup"><span data-stu-id="bb0cd-134">Data entity: Choose the entity that includes the attribute you want to measure.</span></span> 
   1. <span data-ttu-id="bb0cd-135">Thuộc tính dữ liệu: Chọn thuộc tính bạn muốn sử dụng trong hàm tổng hợp để tính toán giá trị đo.</span><span class="sxs-lookup"><span data-stu-id="bb0cd-135">Data attribute: Choose the attribute you want to use in the aggregation function to calculate the measure.</span></span> <span data-ttu-id="bb0cd-136">Mỗi lần, bạn chỉ có thể chọn một thuộc tính.</span><span class="sxs-lookup"><span data-stu-id="bb0cd-136">You can only select one attribute at a time.</span></span>
   1. <span data-ttu-id="bb0cd-137">Bạn cũng có thể chọn một thuộc tính dữ liệu từ một giá trị đo hiện có bằng cách chọn thẻ **Giá trị đo**. Hoặc, bạn có thể tìm kiếm một thực thể hoặc tên giá trị đo.</span><span class="sxs-lookup"><span data-stu-id="bb0cd-137">You can also select a data attribute from an existing measure by selecting the **Measures** tab. Or, you can search for an entity or measure name.</span></span> 
   1. <span data-ttu-id="bb0cd-138">Chọn **Thêm** để thêm thuộc tính đã chọn vào giá trị đo.</span><span class="sxs-lookup"><span data-stu-id="bb0cd-138">Select **Add** to add the selected attribute to the measure.</span></span>

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Chọn một thuộc tính để sử dụng trong tính toán.":::

1. <span data-ttu-id="bb0cd-140">Để xây dựng các giá trị đo phức tạp hơn, bạn có thể thêm nhiều thuộc tính hơn hoặc sử dụng các toán tử toán học trên hàm đo lường của mình.</span><span class="sxs-lookup"><span data-stu-id="bb0cd-140">To build more complex measures, you can add more attributes or use math operators on your measure function.</span></span>

   :::image type="content" source="media/measure-math-operators.png" alt-text="Tạo một giá trị đo phức tạp với các toán tử toán học.":::

1. <span data-ttu-id="bb0cd-142">Để thêm bộ lọc, hãy chọn **Bộ lọc** trong vùng cấu hình.</span><span class="sxs-lookup"><span data-stu-id="bb0cd-142">To add filters, select the **Filter** in the configuration area.</span></span> 
  
   1. <span data-ttu-id="bb0cd-143">Trong mục **Thêm thuộc tính** của ngăn **Bộ lọc**, hãy chọn thuộc tính bạn muốn sử dụng để tạo bộ lọc.</span><span class="sxs-lookup"><span data-stu-id="bb0cd-143">In **Add attribute** section of the **Filters** pane, select the attribute you want to use to create filters.</span></span>
   1. <span data-ttu-id="bb0cd-144">Đặt toán tử bộ lọc để xác định bộ lọc cho mọi thuộc tính đã chọn.</span><span class="sxs-lookup"><span data-stu-id="bb0cd-144">Set the filter operators to define the filter for every selected attribute.</span></span>
   1. <span data-ttu-id="bb0cd-145">Chọn **Áp dụng** để thêm các bộ lọc vào giá trị đo.</span><span class="sxs-lookup"><span data-stu-id="bb0cd-145">Select **Apply** to add the filters to the measure.</span></span>

1. <span data-ttu-id="bb0cd-146">Để thêm các thứ nguyên, hãy chọn **Thứ nguyên** trong vùng cấu hình.</span><span class="sxs-lookup"><span data-stu-id="bb0cd-146">To add dimensions, select **Dimension** in the configuration area.</span></span> <span data-ttu-id="bb0cd-147">Thứ nguyên sẽ hiển thị dưới dạng cột trong thực thể đầu ra giá trị đo.</span><span class="sxs-lookup"><span data-stu-id="bb0cd-147">Dimensions will show as columns in the measure output entity.</span></span>
   1. <span data-ttu-id="bb0cd-148">Chọn **Chỉnh sửa thứ nguyên** để thêm các thuộc tính dữ liệu mà bạn muốn nhóm các giá trị đo lường.</span><span class="sxs-lookup"><span data-stu-id="bb0cd-148">Select **Edit dimensions** to add data attributes you want to group the measure values by.</span></span> <span data-ttu-id="bb0cd-149">Ví dụ: thành phố hoặc giới tính.</span><span class="sxs-lookup"><span data-stu-id="bb0cd-149">For example, city or gender.</span></span> <span data-ttu-id="bb0cd-150">Theo mặc định, thứ nguyên *ID khách hàng* được chọn để tạo *giá trị đo cấp khách hàng*.</span><span class="sxs-lookup"><span data-stu-id="bb0cd-150">By default, the *CustomerID* dimension is selected to create *customer-level measures*.</span></span> <span data-ttu-id="bb0cd-151">Bạn có thể xóa thứ nguyên mặc định nếu muốn tạo *giá trị đo cấp doanh nghiệp*.</span><span class="sxs-lookup"><span data-stu-id="bb0cd-151">You can remove the default dimension if you want to create *business-level measures*.</span></span>
   1. <span data-ttu-id="bb0cd-152">Chọn **Xong** để thêm các thứ nguyên vào giá trị đo.</span><span class="sxs-lookup"><span data-stu-id="bb0cd-152">Select **Done** to add the dimensions to the measure.</span></span>

1. <span data-ttu-id="bb0cd-153">Nếu có nhiều đường dẫn giữa thực thể dữ liệu bạn đã ánh xạ và thực thể *Khách hàng*,bạn phải chọn một trong các [đường dẫn mối quan hệ thực thể](relationships.md) đã xác định.</span><span class="sxs-lookup"><span data-stu-id="bb0cd-153">If there are multiple paths between the data entity you mapped and the *Customer* entity, you have to choose one of the identified [entity relationship paths](relationships.md).</span></span> <span data-ttu-id="bb0cd-154">Kết quả giá trị đo có thể khác nhau tùy thuộc vào đường dẫn đã chọn.</span><span class="sxs-lookup"><span data-stu-id="bb0cd-154">Measure results can vary depending on the selected path.</span></span> 
   1. <span data-ttu-id="bb0cd-155">Chọn **Tùy chọn dữ liệu** và chọn đường dẫn thực thể sẽ được sử dụng để xác định giá trị đo của bạn.</span><span class="sxs-lookup"><span data-stu-id="bb0cd-155">Select **Data preferences** and choose the entity path that should be used to identify your measure.</span></span> <span data-ttu-id="bb0cd-156">Nếu chỉ có một đường dẫn đến thực thể *Khách hàng*, điều khiển này sẽ không hiển thị.</span><span class="sxs-lookup"><span data-stu-id="bb0cd-156">If there's only a single path to the *Customer* entity, this control won't show.</span></span>
   1. <span data-ttu-id="bb0cd-157">Chọn **Xong** để áp dụng lựa chọn của bạn.</span><span class="sxs-lookup"><span data-stu-id="bb0cd-157">Select **Done** to apply your selection.</span></span> 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Chọn đường dẫn thực thể cho giá trị đo đó.":::

1. <span data-ttu-id="bb0cd-159">Để thêm các phép tính khác cho giá trị đo đó, hãy chọn **Tính toán mới**.</span><span class="sxs-lookup"><span data-stu-id="bb0cd-159">To add more calculations for the measure, select **New calculation**.</span></span> <span data-ttu-id="bb0cd-160">Bạn chỉ có thể sử dụng các thực thể trên cùng một đường dẫn thực thể cho các phép tính mới.</span><span class="sxs-lookup"><span data-stu-id="bb0cd-160">You can only use entities on the same entity path for new calculations.</span></span> <span data-ttu-id="bb0cd-161">Các phép tính khác sẽ hiển thị dưới dạng cột mới trong thực thể đầu ra giá trị đo.</span><span class="sxs-lookup"><span data-stu-id="bb0cd-161">More calculations will show as new columns in the measure output entity.</span></span>

1. <span data-ttu-id="bb0cd-162">Chọn **...** trên phép tính để **Nhân bản**, **Đổi tên** hoặc **Xóa** phép tính khỏi giá trị đo.</span><span class="sxs-lookup"><span data-stu-id="bb0cd-162">Select **...** on the calculation to **Duplicate**, **Rename**, or **Remove** a calculation from a measure.</span></span>

1. <span data-ttu-id="bb0cd-163">Trong ngăn **Xem trước**, bạn sẽ thấy giản đồ dữ liệu của thực thể đầu ra giá trị đo, bao gồm các bộ lọc và thứ nguyên.</span><span class="sxs-lookup"><span data-stu-id="bb0cd-163">In the **Preview** area, you'll see the data schema of the measure output entity, including filters and dimensions.</span></span> <span data-ttu-id="bb0cd-164">Bản xem trước phản ứng tự động với các thay đổi trong cấu hình.</span><span class="sxs-lookup"><span data-stu-id="bb0cd-164">The preview reacts dynamically to changes in the configuration.</span></span>

1. <span data-ttu-id="bb0cd-165">Chọn **Chạy** để tính toán kết quả cho giá trị đo đã định cấu hình.</span><span class="sxs-lookup"><span data-stu-id="bb0cd-165">Select **Run** to calculate results for the configured measure.</span></span> <span data-ttu-id="bb0cd-166">Chọn **Lưu và đóng** nếu bạn muốn giữ cấu hình hiện tại và chạy giá trị đo sau.</span><span class="sxs-lookup"><span data-stu-id="bb0cd-166">Select **Save and close** if you want to keep the current configuration and run the measure later.</span></span>

1. <span data-ttu-id="bb0cd-167">Đi đến **Giá trị đo** để xem số đo mới được tạo trong danh sách.</span><span class="sxs-lookup"><span data-stu-id="bb0cd-167">Go to **Measures** to see the newly created measure in the list.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="bb0cd-168">Quản lý các giá trị đo của bạn</span><span class="sxs-lookup"><span data-stu-id="bb0cd-168">Manage your measures</span></span>

<span data-ttu-id="bb0cd-169">Sau khi [tạo một giá trị đo](#create-a-measure), bạn sẽ thấy danh sách các giá trị đo trên trang **Giá trị đo**.</span><span class="sxs-lookup"><span data-stu-id="bb0cd-169">After [creating a measure](#create-a-measure), you see a list of measures on the **Measures** page.</span></span>

<span data-ttu-id="bb0cd-170">Bạn sẽ tìm thấy thông tin về loại giá trị đo, người tạo, ngày tạo, trạng thái và tình trạng.</span><span class="sxs-lookup"><span data-stu-id="bb0cd-170">You'll find information about the measure type, the creator, creation date, status, and state.</span></span> <span data-ttu-id="bb0cd-171">Khi bạn chọn một giá trị đo từ danh sách, bạn có thể xem trước kết quả đầu ra và tải xuống tệp .CSV.</span><span class="sxs-lookup"><span data-stu-id="bb0cd-171">When you select a measure from the list, you can preview the output and download a .CSV file.</span></span>

<span data-ttu-id="bb0cd-172">Để làm mới tất cả các giá trị đo của bạn cùng một lúc, hãy chọn **Làm mới tất cả** mà không chọn một giá trị đo cụ thể.</span><span class="sxs-lookup"><span data-stu-id="bb0cd-172">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="bb0cd-173">![Các hành động để quản lý các giá trị đo đơn lẻ](media/measure-actions.png "Các hành động để quản lý các giá trị đo đơn lẻ")</span><span class="sxs-lookup"><span data-stu-id="bb0cd-173">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="bb0cd-174">Chọn một giá trị đo từ danh sách cho các tùy chọn sau:</span><span class="sxs-lookup"><span data-stu-id="bb0cd-174">Select a measure from the list for the following options:</span></span>

- <span data-ttu-id="bb0cd-175">Chọn tên giá trị đo để xem chi tiết về giá trị đo đó.</span><span class="sxs-lookup"><span data-stu-id="bb0cd-175">Select the measure name to see its details.</span></span>
- <span data-ttu-id="bb0cd-176">**Chỉnh sửa** cấu hình của giá trị đo.</span><span class="sxs-lookup"><span data-stu-id="bb0cd-176">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="bb0cd-177">**Làm mới** giá trị đo dựa trên dữ liệu mới nhất.</span><span class="sxs-lookup"><span data-stu-id="bb0cd-177">**Refresh** the measure based on the latest data.</span></span>
- <span data-ttu-id="bb0cd-178">**Đổi tên** giá trị đo.</span><span class="sxs-lookup"><span data-stu-id="bb0cd-178">**Rename** the measure.</span></span>
- <span data-ttu-id="bb0cd-179">**Xóa** giá trị đo.</span><span class="sxs-lookup"><span data-stu-id="bb0cd-179">**Delete** the measure.</span></span>
- <span data-ttu-id="bb0cd-180">**Kích hoạt** hoặc **hủy kích hoạt**.</span><span class="sxs-lookup"><span data-stu-id="bb0cd-180">**Activate** or **Deactivate**.</span></span> <span data-ttu-id="bb0cd-181">Các giá trị đo không hoạt động sẽ không được làm mới trong [quá trình làm mới theo lịch trình](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="bb0cd-181">Inactive measures won't get refreshed during a [scheduled refresh](system.md#schedule-tab).</span></span>

> [!TIP]
> <span data-ttu-id="bb0cd-182">Có [6 loại trạng thái](system.md#status-types) cho các nhiệm vụ/quy trình.</span><span class="sxs-lookup"><span data-stu-id="bb0cd-182">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="bb0cd-183">Ngoài ra, hầu hết các quy trình [phụ thuộc vào các quá trình hạ nguồn khác](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="bb0cd-183">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="bb0cd-184">Bạn có thể chọn trạng thái của một quy trình để xem chi tiết về tiến trình của toàn bộ công việc.</span><span class="sxs-lookup"><span data-stu-id="bb0cd-184">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="bb0cd-185">Sau khi chọn **Xem chi tiết** đối với một trong các tác vụ của công việc, bạn sẽ tìm thấy thông tin bổ sung: thời gian xử lý, ngày xử lý gần nhất và tất cả các lỗi và cảnh báo liên quan đến tác vụ.</span><span class="sxs-lookup"><span data-stu-id="bb0cd-185">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="bb0cd-186">Bước tiếp theo</span><span class="sxs-lookup"><span data-stu-id="bb0cd-186">Next step</span></span>

<span data-ttu-id="bb0cd-187">Bạn có thể sử dụng các giá trị hiện có để tạo [một phân khúc khách hàng](segments.md).</span><span class="sxs-lookup"><span data-stu-id="bb0cd-187">You cam use existing measures to create [a customer segment](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]