---
title: Tạo và quản lý các giá trị đo
description: Xác định các giá trị đo để phân tích và phản ánh tình hình hoạt động của doanh nghiệp bạn.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: a83caf2428f3dbd9791b9f746d00d370362a508c
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304836"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="9bfc4-103">Xác định và quản lý các biện pháp</span><span class="sxs-lookup"><span data-stu-id="9bfc4-103">Define and manage measures</span></span>

<span data-ttu-id="9bfc4-104">Giá trị đo giúp bạn hiểu rõ hơn về hành vi của khách hàng và hiệu quả kinh doanh.</span><span class="sxs-lookup"><span data-stu-id="9bfc4-104">Measures help you to better understand customer behaviors and business performance.</span></span> <span data-ttu-id="9bfc4-105">Giá trị đo xem xét các giá trị có liên quan từ [hồ sơ hợp nhất](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="9bfc4-105">They look at relevant values from [unified profiles](data-unification.md).</span></span> <span data-ttu-id="9bfc4-106">Ví dụ: một doanh nghiệp muốn xem *tổng mức chi tiêu của mỗi khách hàng* để nắm được lịch sử mua hàng của một khách hàng cá nhân hoặc đo lường *tổng doanh số của công ty* để nắm được tổng doanh thu của toàn bộ doanh nghiệp.</span><span class="sxs-lookup"><span data-stu-id="9bfc4-106">For example, a business wants to see the *total spend per customer* to understand an individual customer’s purchase history or measure *total sales of the company* to understand the aggregate-level revenue in the whole business.</span></span>  

<span data-ttu-id="9bfc4-107">Các giá trị đo được tạo bằng cách sử dụng trình tạo giá trị đo, một nền tảng truy vấn dữ liệu với các toán tử khác nhau và các tùy chọn ánh xạ đơn giản.</span><span class="sxs-lookup"><span data-stu-id="9bfc4-107">Measures are created using the measure builder, a data query platform with various operators and simple mapping options.</span></span> <span data-ttu-id="9bfc4-108">Nó cho phép bạn lọc dữ liệu, nhóm kết quả, phát hiện [đường dẫn mối quan hệ thực thể](relationships.md) và xem trước đầu ra.</span><span class="sxs-lookup"><span data-stu-id="9bfc4-108">It lets you filter the data, group results, detect [entity relationship paths](relationships.md), and preview the output.</span></span>

<span data-ttu-id="9bfc4-109">Hãy sử dụng trình tạo giá trị đo để lập kế hoạch hoạt động kinh doanh bằng cách truy vấn dữ liệu khách hàng và trích xuất thông tin chi tiết.</span><span class="sxs-lookup"><span data-stu-id="9bfc4-109">Use the measure builder to plan business activities by querying customer data and extract insights.</span></span> <span data-ttu-id="9bfc4-110">Ví dụ: tạo một giá trị đo *tổng chi tiêu mỗi khách hàng* và *tổng lợi nhuận trên mỗi khách hàng* giúp xác định nhóm khách hàng có mức chi tiêu cao nhưng lợi nhuận thu về cao.</span><span class="sxs-lookup"><span data-stu-id="9bfc4-110">For example, creating a measure of *total spend per customer* and *total return per customer* helps identify a group of customers with high spend yet high return.</span></span> <span data-ttu-id="9bfc4-111">Bạn có thể [tạo một phân đoạn](segments.md) để thúc đẩy các hành động tốt nhất tiếp theo.</span><span class="sxs-lookup"><span data-stu-id="9bfc4-111">You can [create a segment](segments.md) to drive next best actions.</span></span> 

## <a name="build-your-own-measure-from-scratch"></a><span data-ttu-id="9bfc4-112">Tạo giá trị đo của riêng bạn từ đầu</span><span class="sxs-lookup"><span data-stu-id="9bfc4-112">Build your own measure from scratch</span></span>

<span data-ttu-id="9bfc4-113">Phần này sẽ hướng dẫn bạn cách tạo một giá trị đo mới từ đầu.</span><span class="sxs-lookup"><span data-stu-id="9bfc4-113">This section walks you through creating a new measure from scratch.</span></span> <span data-ttu-id="9bfc4-114">Bạn có thể tạo một giá trị đo với các thuộc tính dữ liệu từ các thực thể dữ liệu có mối quan hệ được thiết lập để kết nối với thực thể Khách hàng.</span><span class="sxs-lookup"><span data-stu-id="9bfc4-114">You can build a measure with data attributes from data entities that have a relationship set up to connect with the Customer entity.</span></span> 

1. <span data-ttu-id="9bfc4-115">Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Giá trị đo**.</span><span class="sxs-lookup"><span data-stu-id="9bfc4-115">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="9bfc4-116">Chọn **Mới** rồi chọn **Tạo giá trị đo riêng**.</span><span class="sxs-lookup"><span data-stu-id="9bfc4-116">Select **New** and choose **Build your own**.</span></span>

1. <span data-ttu-id="9bfc4-117">Chọn **Chỉnh sửa tên** và cung cấp một **Tên** cho giá trị đo.</span><span class="sxs-lookup"><span data-stu-id="9bfc4-117">Select **Edit name** and provide a **Name** for the measure.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="9bfc4-118">Nếu cấu hình giá trị đo mới của bạn chỉ có hai trường, ví dụ: CustomerID và một phép tính thì kết quả đầu ra sẽ được thêm vào thực thể do hệ thống tạo ra có tên là Customer_Measure dưới dạng một cột mới.</span><span class="sxs-lookup"><span data-stu-id="9bfc4-118">If your new measure configuration has only two fields—for example, CustomerID and one calculation—the output will be added as a new column to the system-generated entity called Customer_Measure.</span></span> <span data-ttu-id="9bfc4-119">Và bạn sẽ có thể thấy giá trị của giá trị đo trong hồ sơ khách hàng hợp nhất.</span><span class="sxs-lookup"><span data-stu-id="9bfc4-119">And you will be able to see the measure’s value in the unified customer profile.</span></span> <span data-ttu-id="9bfc4-120">Các giá trị đo khác sẽ tạo ra các thực thể của riêng chúng.</span><span class="sxs-lookup"><span data-stu-id="9bfc4-120">Other measures will generate their own entities.</span></span>

1. <span data-ttu-id="9bfc4-121">Trong vùng cấu hình, hãy chọn hàm tổng hợp từ menu thả xuống **Chọn hàm**.</span><span class="sxs-lookup"><span data-stu-id="9bfc4-121">In the configuration area, choose the aggregation function from the **Select Function** dropdown menu.</span></span> <span data-ttu-id="9bfc4-122">Các hàm tổng hợp bao gồm:</span><span class="sxs-lookup"><span data-stu-id="9bfc4-122">Aggregation functions include:</span></span> 
   - <span data-ttu-id="9bfc4-123">**Sum**</span><span class="sxs-lookup"><span data-stu-id="9bfc4-123">**Sum**</span></span>
   - <span data-ttu-id="9bfc4-124">**Trung bình**</span><span class="sxs-lookup"><span data-stu-id="9bfc4-124">**Average**</span></span>
   - <span data-ttu-id="9bfc4-125">**Đếm**</span><span class="sxs-lookup"><span data-stu-id="9bfc4-125">**Count**</span></span>
   - <span data-ttu-id="9bfc4-126">**Số đếm Duy nhất**</span><span class="sxs-lookup"><span data-stu-id="9bfc4-126">**Count Unique**</span></span>
   - <span data-ttu-id="9bfc4-127">**Tối đa**</span><span class="sxs-lookup"><span data-stu-id="9bfc4-127">**Max**</span></span>
   - <span data-ttu-id="9bfc4-128">**Min**</span><span class="sxs-lookup"><span data-stu-id="9bfc4-128">**Min**</span></span>
   - <span data-ttu-id="9bfc4-129">**Đầu tiên**: lấy giá trị đầu tiên của bản ghi dữ liệu</span><span class="sxs-lookup"><span data-stu-id="9bfc4-129">**First**: takes the first value of the data record</span></span>
   - <span data-ttu-id="9bfc4-130">**Cuối cùng**: lấy giá trị cuối cùng đã được thêm vào bản ghi dữ liệu</span><span class="sxs-lookup"><span data-stu-id="9bfc4-130">**Last**: takes the last value that was added to the data record</span></span>

   :::image type="content" source="media/measure-operators.png" alt-text="Các toán tử để tính toán giá trị đo.":::

1. <span data-ttu-id="9bfc4-132">Chọn **Thêm thuộc tính** để chọn dữ liệu bạn cần để tạo giá trị đo này.</span><span class="sxs-lookup"><span data-stu-id="9bfc4-132">Select **Add attribute** to select the data you need to create this measure.</span></span>
   
   1. <span data-ttu-id="9bfc4-133">Chọn thẻ **Thuộc tính**.</span><span class="sxs-lookup"><span data-stu-id="9bfc4-133">Select the **Attributes** tab.</span></span> 
   1. <span data-ttu-id="9bfc4-134">Thực thể dữ liệu: Chọn thực thể bao gồm thuộc tính bạn muốn đo.</span><span class="sxs-lookup"><span data-stu-id="9bfc4-134">Data entity: Choose the entity that includes the attribute you want to measure.</span></span> 
   1. <span data-ttu-id="9bfc4-135">Thuộc tính dữ liệu: Chọn thuộc tính bạn muốn sử dụng trong hàm tổng hợp để tính toán giá trị đo.</span><span class="sxs-lookup"><span data-stu-id="9bfc4-135">Data attribute: Choose the attribute you want to use in the aggregation function to calculate the measure.</span></span> <span data-ttu-id="9bfc4-136">Mỗi lần, bạn chỉ có thể chọn một thuộc tính.</span><span class="sxs-lookup"><span data-stu-id="9bfc4-136">You can only select one attribute at a time.</span></span>
   1. <span data-ttu-id="9bfc4-137">Bạn cũng có thể chọn một thuộc tính dữ liệu từ một giá trị đo hiện có bằng cách chọn thẻ **Giá trị đo**. Hoặc bạn có thể tìm kiếm một thực thể hoặc tên giá trị đo.</span><span class="sxs-lookup"><span data-stu-id="9bfc4-137">You can also select a data attribute from an existing measure by selecting the **Measures** tab. Or, you can search for an entity or measure name.</span></span> 
   1. <span data-ttu-id="9bfc4-138">Chọn **Thêm** để thêm thuộc tính đã chọn vào giá trị đo.</span><span class="sxs-lookup"><span data-stu-id="9bfc4-138">Select **Add** to add the selected attribute to the measure.</span></span>

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Chọn một thuộc tính để sử dụng trong tính toán.":::

1. <span data-ttu-id="9bfc4-140">Để xây dựng các giá trị đo phức tạp hơn, bạn có thể thêm nhiều thuộc tính hơn hoặc sử dụng các toán tử toán học trên hàm đo lường của mình.</span><span class="sxs-lookup"><span data-stu-id="9bfc4-140">To build more complex measures, you can add more attributes or use math operators on your measure function.</span></span>

   :::image type="content" source="media/measure-math-operators.png" alt-text="Tạo một giá trị đo phức tạp với các toán tử toán học.":::

1. <span data-ttu-id="9bfc4-142">Để thêm bộ lọc, hãy chọn **Bộ lọc** trong vùng cấu hình.</span><span class="sxs-lookup"><span data-stu-id="9bfc4-142">To add filters, select the **Filter** in the configuration area.</span></span> 
  
   1. <span data-ttu-id="9bfc4-143">Trong phần **Thêm thuộc tính** của ngăn **Bộ lọc**, chọn thuộc tính bạn muốn sử dụng để tạo bộ lọc.</span><span class="sxs-lookup"><span data-stu-id="9bfc4-143">In the **Add attribute** section of the **Filters** pane, select the attribute you want to use to create filters.</span></span>
   1. <span data-ttu-id="9bfc4-144">Đặt toán tử bộ lọc để xác định bộ lọc cho mọi thuộc tính đã chọn.</span><span class="sxs-lookup"><span data-stu-id="9bfc4-144">Set the filter operators to define the filter for every selected attribute.</span></span>
   1. <span data-ttu-id="9bfc4-145">Chọn **Áp dụng** để thêm các bộ lọc vào giá trị đo.</span><span class="sxs-lookup"><span data-stu-id="9bfc4-145">Select **Apply** to add the filters to the measure.</span></span>

1. <span data-ttu-id="9bfc4-146">Để thêm các thứ nguyên, hãy chọn **Thứ nguyên** trong vùng cấu hình.</span><span class="sxs-lookup"><span data-stu-id="9bfc4-146">To add dimensions, select **Dimension** in the configuration area.</span></span> <span data-ttu-id="9bfc4-147">Thứ nguyên sẽ hiển thị dưới dạng cột trong thực thể đầu ra giá trị đo.</span><span class="sxs-lookup"><span data-stu-id="9bfc4-147">Dimensions will show as columns in the measure output entity.</span></span>
 
   1. <span data-ttu-id="9bfc4-148">Chọn **Chỉnh sửa thứ nguyên** để thêm các thuộc tính dữ liệu mà bạn muốn nhóm các giá trị đo lường.</span><span class="sxs-lookup"><span data-stu-id="9bfc4-148">Select **Edit dimensions** to add data attributes you want to group the measure values by.</span></span> <span data-ttu-id="9bfc4-149">Ví dụ: thành phố hoặc giới tính.</span><span class="sxs-lookup"><span data-stu-id="9bfc4-149">For example, city or gender.</span></span> <span data-ttu-id="9bfc4-150">Theo mặc định, thứ nguyên *ID khách hàng* được chọn để tạo *giá trị đo cấp khách hàng*.</span><span class="sxs-lookup"><span data-stu-id="9bfc4-150">By default, the *CustomerID* dimension is selected to create *customer-level measures*.</span></span> <span data-ttu-id="9bfc4-151">Bạn có thể xóa thứ nguyên mặc định nếu muốn tạo *giá trị đo cấp doanh nghiệp*.</span><span class="sxs-lookup"><span data-stu-id="9bfc4-151">You can remove the default dimension if you want to create *business-level measures*.</span></span>
   1. <span data-ttu-id="9bfc4-152">Chọn **Xong** để thêm các thứ nguyên vào giá trị đo.</span><span class="sxs-lookup"><span data-stu-id="9bfc4-152">Select **Done** to add the dimensions to the measure.</span></span>

1. <span data-ttu-id="9bfc4-153">Nếu có các giá trị trong dữ liệu của bạn mà bạn cần thay thế bằng một số nguyên, chẳng hạn như thay thế *null* bằng *0*, hãy chọn **Quy tắc**.</span><span class="sxs-lookup"><span data-stu-id="9bfc4-153">If there are values in your data that you need to replace with an integer—for example, replace *null* with *0*—select **Rules**.</span></span> <span data-ttu-id="9bfc4-154">Định cấu hình quy tắc và đảm bảo rằng bạn chỉ chọn các số nguyên làm giá trị thay thế.</span><span class="sxs-lookup"><span data-stu-id="9bfc4-154">Configure the rule and make sure that you choose only whole numbers as replacements.</span></span>

1. <span data-ttu-id="9bfc4-155">Nếu có nhiều đường dẫn giữa thực thể dữ liệu bạn đã ánh xạ và thực thể *Khách hàng*,bạn phải chọn một trong các [đường dẫn mối quan hệ thực thể](relationships.md) đã xác định.</span><span class="sxs-lookup"><span data-stu-id="9bfc4-155">If there are multiple paths between the data entity you mapped and the *Customer* entity, you have to choose one of the identified [entity relationship paths](relationships.md).</span></span> <span data-ttu-id="9bfc4-156">Kết quả giá trị đo có thể khác nhau tùy thuộc vào đường dẫn đã chọn.</span><span class="sxs-lookup"><span data-stu-id="9bfc4-156">Measure results can vary depending on the selected path.</span></span> 
   
   1. <span data-ttu-id="9bfc4-157">Chọn **Tùy chọn dữ liệu** và chọn đường dẫn thực thể sẽ được sử dụng để xác định giá trị đo của bạn.</span><span class="sxs-lookup"><span data-stu-id="9bfc4-157">Select **Data preferences** and choose the entity path that should be used to identify your measure.</span></span> <span data-ttu-id="9bfc4-158">Nếu chỉ có một đường dẫn đến thực thể *Khách hàng*, điều khiển này sẽ không hiển thị.</span><span class="sxs-lookup"><span data-stu-id="9bfc4-158">If there's only a single path to the *Customer* entity, this control won't show.</span></span>
   1. <span data-ttu-id="9bfc4-159">Chọn **Xong** để áp dụng lựa chọn của bạn.</span><span class="sxs-lookup"><span data-stu-id="9bfc4-159">Select **Done** to apply your selection.</span></span> 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Chọn đường dẫn thực thể cho giá trị đo đó.":::

1. <span data-ttu-id="9bfc4-161">Để thêm các phép tính khác cho giá trị đo đó, hãy chọn **Tính toán mới**.</span><span class="sxs-lookup"><span data-stu-id="9bfc4-161">To add more calculations for the measure, select **New calculation**.</span></span> <span data-ttu-id="9bfc4-162">Bạn chỉ có thể sử dụng các thực thể trên cùng một đường dẫn thực thể cho các phép tính mới.</span><span class="sxs-lookup"><span data-stu-id="9bfc4-162">You can only use entities on the same entity path for new calculations.</span></span> <span data-ttu-id="9bfc4-163">Các phép tính khác sẽ hiển thị dưới dạng cột mới trong thực thể đầu ra giá trị đo.</span><span class="sxs-lookup"><span data-stu-id="9bfc4-163">More calculations will show as new columns in the measure output entity.</span></span>

1. <span data-ttu-id="9bfc4-164">Chọn **...** trên phép tính để **Nhân bản**, **Đổi tên** hoặc **Xóa** phép tính khỏi giá trị đo.</span><span class="sxs-lookup"><span data-stu-id="9bfc4-164">Select **...** on the calculation to **Duplicate**, **Rename**, or **Remove** a calculation from a measure.</span></span>

1. <span data-ttu-id="9bfc4-165">Trong ngăn **Xem trước**, bạn sẽ thấy giản đồ dữ liệu của thực thể đầu ra giá trị đo, bao gồm các bộ lọc và thứ nguyên.</span><span class="sxs-lookup"><span data-stu-id="9bfc4-165">In the **Preview** area, you'll see the data schema of the measure output entity, including filters and dimensions.</span></span> <span data-ttu-id="9bfc4-166">Bản xem trước phản ứng tự động với các thay đổi trong cấu hình.</span><span class="sxs-lookup"><span data-stu-id="9bfc4-166">The preview reacts dynamically to changes in the configuration.</span></span>

1. <span data-ttu-id="9bfc4-167">Chọn **Chạy** để tính toán kết quả cho giá trị đo đã định cấu hình.</span><span class="sxs-lookup"><span data-stu-id="9bfc4-167">Select **Run** to calculate results for the configured measure.</span></span> <span data-ttu-id="9bfc4-168">Chọn **Lưu và đóng** nếu bạn muốn giữ cấu hình hiện tại và chạy giá trị đo sau.</span><span class="sxs-lookup"><span data-stu-id="9bfc4-168">Select **Save and close** if you want to keep the current configuration and run the measure later.</span></span>

1. <span data-ttu-id="9bfc4-169">Đi đến **Giá trị đo** để xem số đo mới được tạo trong danh sách.</span><span class="sxs-lookup"><span data-stu-id="9bfc4-169">Go to **Measures** to see the newly created measure in the list.</span></span>

## <a name="use-a-template-to-build-a-measure"></a><span data-ttu-id="9bfc4-170">Sử dụng mẫu để tạo giá trị đo</span><span class="sxs-lookup"><span data-stu-id="9bfc4-170">Use a template to build a measure</span></span>

<span data-ttu-id="9bfc4-171">Bạn có thể sử dụng các mẫu định sẵn có chứa các giá trị đo thường dùng để tạo giá trị đo.</span><span class="sxs-lookup"><span data-stu-id="9bfc4-171">You can use predefined templates of commonly used measures to create them.</span></span> <span data-ttu-id="9bfc4-172">Mô tả chi tiết về các mẫu và trải nghiệm có hướng dẫn sẽ giúp bạn tạo giá trị đo hiệu quả.</span><span class="sxs-lookup"><span data-stu-id="9bfc4-172">Detailed descriptions of the templates and a guided experience help you with efficient measure creation.</span></span> <span data-ttu-id="9bfc4-173">Các mẫu xây dựng dựa trên dữ liệu được ánh xạ từ thực thể *Hoạt động được hợp nhất*.</span><span class="sxs-lookup"><span data-stu-id="9bfc4-173">Templates build on mapped data from the *Unified Activity* entity.</span></span> <span data-ttu-id="9bfc4-174">Vì vậy, hãy đảm bảo rằng bạn đã định cấu hình [hoạt động của khách hàng](activities.md) trước khi tạo giá trị đo từ một mẫu.</span><span class="sxs-lookup"><span data-stu-id="9bfc4-174">So make sure you have configured [customer activities](activities.md) before you create a measure from a template.</span></span>

<span data-ttu-id="9bfc4-175">Các mẫu giá trị đo sẵn có:</span><span class="sxs-lookup"><span data-stu-id="9bfc4-175">Available measure templates:</span></span> 
- <span data-ttu-id="9bfc4-176">Giá trị giao dịch trung bình (ATV)</span><span class="sxs-lookup"><span data-stu-id="9bfc4-176">Average transaction value (ATV)</span></span>
- <span data-ttu-id="9bfc4-177">Tổng giá trị giao dịch</span><span class="sxs-lookup"><span data-stu-id="9bfc4-177">Total transaction value</span></span>
- <span data-ttu-id="9bfc4-178">Doanh thu trung bình hàng ngày</span><span class="sxs-lookup"><span data-stu-id="9bfc4-178">Average daily revenue</span></span>
- <span data-ttu-id="9bfc4-179">Doanh thu trung bình hàng năm</span><span class="sxs-lookup"><span data-stu-id="9bfc4-179">Average yearly revenue</span></span>
- <span data-ttu-id="9bfc4-180">Số lượng giao dịch</span><span class="sxs-lookup"><span data-stu-id="9bfc4-180">Transaction count</span></span>
- <span data-ttu-id="9bfc4-181">Điểm khách hàng thân thiết kiếm được</span><span class="sxs-lookup"><span data-stu-id="9bfc4-181">Loyalty points earned</span></span>
- <span data-ttu-id="9bfc4-182">Điểm khách hàng thân thiết đã quy đổi</span><span class="sxs-lookup"><span data-stu-id="9bfc4-182">Loyalty points redeemed</span></span>
- <span data-ttu-id="9bfc4-183">Số dư điểm khách hàng thân thiết</span><span class="sxs-lookup"><span data-stu-id="9bfc4-183">Loyalty points balance</span></span>
- <span data-ttu-id="9bfc4-184">Quãng thời gian khách hàng hoạt động</span><span class="sxs-lookup"><span data-stu-id="9bfc4-184">Active customer lifespan</span></span>
- <span data-ttu-id="9bfc4-185">Thời lượng là thành viên khách hàng thân thiết</span><span class="sxs-lookup"><span data-stu-id="9bfc4-185">Loyalty membership duration</span></span>
- <span data-ttu-id="9bfc4-186">Thời gian kể từ giao dịch mua gần nhất</span><span class="sxs-lookup"><span data-stu-id="9bfc4-186">Time since last purchase</span></span>

<span data-ttu-id="9bfc4-187">Quy trình sau đây phác thảo các bước để tạo giá trị đo mới bằng cách sử dụng một mẫu.</span><span class="sxs-lookup"><span data-stu-id="9bfc4-187">The following procedure outlines the steps to build a new measure using a template.</span></span>

1. <span data-ttu-id="9bfc4-188">Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Giá trị đo**.</span><span class="sxs-lookup"><span data-stu-id="9bfc4-188">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="9bfc4-189">Chọn **Mới** rồi chọn **Chọn một mẫu**.</span><span class="sxs-lookup"><span data-stu-id="9bfc4-189">Select **New** and select **Choose a template**.</span></span>

   :::image type="content" source="media/measure-use-template.png" alt-text="Ảnh chụp màn hình của menu thả xuống khi tạo một giá trị đo mới được tô sáng trên mẫu.":::

1. <span data-ttu-id="9bfc4-191">Tìm mẫu phù hợp với nhu cầu của bạn rồi chọn **Chọn mẫu**.</span><span class="sxs-lookup"><span data-stu-id="9bfc4-191">Find the template that fits your need and select **Choose template**.</span></span>

1. <span data-ttu-id="9bfc4-192">Xem lại dữ liệu bắt buộc rồi chọn **Bắt đầu** nếu bạn có sẵn tất cả dữ liệu.</span><span class="sxs-lookup"><span data-stu-id="9bfc4-192">Review the required data and select **Get started** if you have all the data in place.</span></span>

1. <span data-ttu-id="9bfc4-193">Trong ngăn **Chỉnh sửa tên**, hãy đặt tên cho giá trị đo của bạn và thực thể đầu ra.</span><span class="sxs-lookup"><span data-stu-id="9bfc4-193">In the **Edit name** pane, set the name for your measure and the output entity.</span></span> 

1. <span data-ttu-id="9bfc4-194">Chọn **Xong**.</span><span class="sxs-lookup"><span data-stu-id="9bfc4-194">Select **Done**.</span></span>

1. <span data-ttu-id="9bfc4-195">Trong phần **Đặt khoảng thời gian**, hãy xác định khung thời gian của dữ liệu sẽ sử dụng.</span><span class="sxs-lookup"><span data-stu-id="9bfc4-195">In the **Set time period** section, define the time frame of the data to use.</span></span> <span data-ttu-id="9bfc4-196">Chọn **Mọi lúc** nếu bạn muốn giá trị đo mới bao quát toàn bộ tập dữ liệu hoặc chọn **Khoảng thời gian cụ thể** nếu muốn giá trị đo tập trung vào một khoảng thời gian.</span><span class="sxs-lookup"><span data-stu-id="9bfc4-196">Choose if you want the new measure to cover the entire dataset by selecting **All time**, or if you want the measure to focus on a **Specific time period**.</span></span>

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Ảnh chụp màn hình về phần khoảng thời gian khi định cấu hình giá trị đo từ một mẫu.":::

1. <span data-ttu-id="9bfc4-198">Trong phần tiếp theo, hãy chọn **Thêm dữ liệu** để chọn các hoạt động rồi ánh xạ dữ liệu tương ứng từ thực thể *Hoạt động được hợp nhất*.</span><span class="sxs-lookup"><span data-stu-id="9bfc4-198">In the next section, select **Add data** to choose the activities and map the corresponding data from your *Unified Activity* entity.</span></span>

    1. <span data-ttu-id="9bfc4-199">Bước 1/2: Trong mục **Loại hoạt động**, hãy chọn loại thực thể mà bạn muốn sử dụng.</span><span class="sxs-lookup"><span data-stu-id="9bfc4-199">Step 1 of 2: Under **Activity type**, choose the type of the entity you want to use.</span></span> <span data-ttu-id="9bfc4-200">Đối với **Hoạt động**, hãy chọn các thực thể mà bạn muốn ánh xạ.</span><span class="sxs-lookup"><span data-stu-id="9bfc4-200">For **Activities**, select the entities you want to map.</span></span>
    1. <span data-ttu-id="9bfc4-201">Bước 2/2: Chọn thuộc tính từ *Hoạt động được hợp nhất* cho thành phần theo yêu cầu của công thức.</span><span class="sxs-lookup"><span data-stu-id="9bfc4-201">Step 2 of 2: Choose the attribute from the *Unified Activity* entity for the component required by the formula.</span></span> <span data-ttu-id="9bfc4-202">Ví dụ: đối với giá trị giao dịch Trung bình, đó là thuộc tính đại diện cho Giá trị giao dịch.</span><span class="sxs-lookup"><span data-stu-id="9bfc4-202">For example, for Average transaction value, it's the attribute representing the Transaction value.</span></span> <span data-ttu-id="9bfc4-203">Đối với **Dấu thời gian hoạt động**, hãy chọn thuộc tính từ thực thể Hoạt động được hợp nhất đại diện cho ngày và giờ của hoạt động.</span><span class="sxs-lookup"><span data-stu-id="9bfc4-203">For **Activity timestamp**, choose the attribute from the Unified Activity entity that represents the date and time of the activity.</span></span>
   
1. <span data-ttu-id="9bfc4-204">Khi ánh xạ dữ liệu thành công, bạn có thể thấy trạng thái là **Hoàn thành** cũng như tên của các hoạt động và thuộc tính được ánh xạ.</span><span class="sxs-lookup"><span data-stu-id="9bfc4-204">Once the data mapping is successful, you can see the status as **Complete** and the name of the mapped activities and attributes.</span></span>

   :::image type="content" source="media/measure-template-configured.png" alt-text="Ảnh chụp màn hình về cấu hình mẫu giá trị đo đã hoàn thành.":::

1. <span data-ttu-id="9bfc4-206">Bây giờ, bạn có thể chọn **Chạy** để tính toán kết quả của giá trị đo.</span><span class="sxs-lookup"><span data-stu-id="9bfc4-206">You can now select **Run** to calculate the results of the measure.</span></span> <span data-ttu-id="9bfc4-207">Để tinh chỉnh giá trị đo về sau, hãy chọn **Lưu bản nháp**.</span><span class="sxs-lookup"><span data-stu-id="9bfc4-207">To refine it later, select **Save draft**.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="9bfc4-208">Quản lý các giá trị đo của bạn</span><span class="sxs-lookup"><span data-stu-id="9bfc4-208">Manage your measures</span></span>

<span data-ttu-id="9bfc4-209">Bạn có thể tìm thấy danh sách các giá trị đo trên trang **Giá trị đo**.</span><span class="sxs-lookup"><span data-stu-id="9bfc4-209">You can find the list of measures on the **Measures** page.</span></span>

<span data-ttu-id="9bfc4-210">Bạn sẽ tìm thấy thông tin về loại giá trị đo, người tạo, ngày tạo, trạng thái và tình trạng.</span><span class="sxs-lookup"><span data-stu-id="9bfc4-210">You'll find information about the measure type, the creator, creation date, status, and state.</span></span> <span data-ttu-id="9bfc4-211">Khi chọn một giá trị đo từ danh sách, bạn có thể xem trước kết quả đầu ra và tải xuống tệp CSV.</span><span class="sxs-lookup"><span data-stu-id="9bfc4-211">When you select a measure from the list, you can preview the output and download a CSV file.</span></span>

<span data-ttu-id="9bfc4-212">Để làm mới tất cả các giá trị đo của bạn cùng một lúc, hãy chọn **Làm mới tất cả** mà không chọn một giá trị đo cụ thể.</span><span class="sxs-lookup"><span data-stu-id="9bfc4-212">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="9bfc4-213">![Các hành động để quản lý các giá trị đo đơn lẻ.](media/measure-actions.png "Các hành động để quản lý các giá trị đo đơn lẻ.")</span><span class="sxs-lookup"><span data-stu-id="9bfc4-213">![Actions to manage single measures.](media/measure-actions.png "Actions to manage single measures.")</span></span>

<span data-ttu-id="9bfc4-214">Chọn một giá trị đo từ danh sách cho các tùy chọn sau:</span><span class="sxs-lookup"><span data-stu-id="9bfc4-214">Select a measure from the list for the following options:</span></span>

- <span data-ttu-id="9bfc4-215">Chọn tên giá trị đo để xem chi tiết về giá trị đo đó.</span><span class="sxs-lookup"><span data-stu-id="9bfc4-215">Select the measure name to see its details.</span></span>
- <span data-ttu-id="9bfc4-216">**Chỉnh sửa** cấu hình của giá trị đo.</span><span class="sxs-lookup"><span data-stu-id="9bfc4-216">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="9bfc4-217">**Làm mới** giá trị đo dựa trên dữ liệu mới nhất.</span><span class="sxs-lookup"><span data-stu-id="9bfc4-217">**Refresh** the measure based on the latest data.</span></span>
- <span data-ttu-id="9bfc4-218">**Đổi tên** giá trị đo.</span><span class="sxs-lookup"><span data-stu-id="9bfc4-218">**Rename** the measure.</span></span>
- <span data-ttu-id="9bfc4-219">**Xóa** giá trị đo.</span><span class="sxs-lookup"><span data-stu-id="9bfc4-219">**Delete** the measure.</span></span>
- <span data-ttu-id="9bfc4-220">**Kích hoạt** hoặc **hủy kích hoạt**.</span><span class="sxs-lookup"><span data-stu-id="9bfc4-220">**Activate** or **Deactivate**.</span></span> <span data-ttu-id="9bfc4-221">Các giá trị đo không hoạt động sẽ không được làm mới trong [quá trình làm mới theo lịch trình](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="9bfc4-221">Inactive measures won't get refreshed during a [scheduled refresh](system.md#schedule-tab).</span></span>

> [!TIP]
> <span data-ttu-id="9bfc4-222">Có [6 loại trạng thái](system.md#status-types) cho các nhiệm vụ/quy trình.</span><span class="sxs-lookup"><span data-stu-id="9bfc4-222">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="9bfc4-223">Ngoài ra, hầu hết các quy trình [phụ thuộc vào các quá trình hạ nguồn khác](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="9bfc4-223">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="9bfc4-224">Bạn có thể chọn trạng thái của một quy trình để xem chi tiết về tiến trình của toàn bộ công việc.</span><span class="sxs-lookup"><span data-stu-id="9bfc4-224">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="9bfc4-225">Sau khi chọn **Xem chi tiết** đối với một trong các nhiệm vụ của công việc, bạn sẽ tìm thấy thông tin bổ sung như: thời gian xử lý, ngày xử lý cuối cùng và tất cả các lỗi cũng như cảnh báo liên quan đến nhiệm vụ.</span><span class="sxs-lookup"><span data-stu-id="9bfc4-225">After selecting **See details** for one of the job's tasks, you'll find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="9bfc4-226">Bước tiếp theo</span><span class="sxs-lookup"><span data-stu-id="9bfc4-226">Next step</span></span>

<span data-ttu-id="9bfc4-227">Bạn có thể sử dụng các giá trị đo hiện có để tạo [một phân khúc khách hàng](segments.md).</span><span class="sxs-lookup"><span data-stu-id="9bfc4-227">You can use existing measures to create [a customer segment](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
