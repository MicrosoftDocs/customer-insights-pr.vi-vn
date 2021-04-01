---
title: Hoàn thành dữ liệu từng phần bằng cách sử dụng dự đoán
description: Sử dụng dự đoán để điền vào dữ liệu khách hàng không đầy đủ.
ms.date: 05/05/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 3342328b9eead9bdcb8b41f119a1d0a5823001c8
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595927"
---
# <a name="complete-your-partial-data-with-predictions"></a><span data-ttu-id="e7140-103">Hoàn thành một phần dữ liệu của bạn bằng tính năng dự đoán</span><span class="sxs-lookup"><span data-stu-id="e7140-103">Complete your partial data with predictions</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="e7140-104">Tính năng Dự đoán cho phép bạn dễ dàng tạo các giá trị dự đoán nhằm nâng cao sự hiểu biết của bạn về một khách hàng.</span><span class="sxs-lookup"><span data-stu-id="e7140-104">Predictions lets you easily create predicted values that can enhance your understanding of a customer.</span></span> <span data-ttu-id="e7140-105">Trên trang **Thông tin** > **Dự đoán**, bạn có thể chọn **Dự đoán của tôi** để xem các dự đoán mà bạn đã định cấu hình trong các phần khác của thông tin chi tiết về đối tượng và cho phép bạn tùy chỉnh thêm.</span><span class="sxs-lookup"><span data-stu-id="e7140-105">On the **Intelligence** > **Predictions** page, you can select **My predictions** to see predictions that you've configured in other parts of audience insights, and allow you to further customize them.</span></span>

> [!NOTE]
> <span data-ttu-id="e7140-106">Bạn không thể sử dụng tính năng này nếu môi trường của bạn sử dụng lưu trữ Azure Data Lake Gen 2.</span><span class="sxs-lookup"><span data-stu-id="e7140-106">You can't use this feature if your environment uses Azure Data Lake Gen 2 storage.</span></span>
>
> <span data-ttu-id="e7140-107">Tính năng dự đoán sử dụng phương tiện tự động để đánh giá dữ liệu và đưa ra dự đoán dựa trên dữ liệu đó, do vậy có khả năng được dùng làm phương thức lập hồ sơ, theo định nghĩa về thuật ngữ đó trong Quy định chung về bảo vệ dữ liệu ("GDPR").</span><span class="sxs-lookup"><span data-stu-id="e7140-107">The predictions feature uses automated means to evaluate data and make predictions based on that data, and therefore has the capability to be used as a method of profiling, as that term is defined by the General Data Protection Regulation ("GDPR").</span></span> <span data-ttu-id="e7140-108">Việc khách hàng sử dụng tính năng này để xử lý dữ liệu phải tuân theo GDPR hoặc các luật/quy định khác.</span><span class="sxs-lookup"><span data-stu-id="e7140-108">Customer's use of this feature to process data may be subject to GDPR or other laws or regulations.</span></span> <span data-ttu-id="e7140-109">Bạn có trách nhiệm đảm bảo rằng việc sử dụng Dynamics 365 Customer Insights, bao gồm các dự đoán, tuân thủ tất cả các luật và quy định hiện hành, bao gồm các luật liên quan đến quyền riêng tư, dữ liệu cá nhân, dữ liệu sinh trắc học, bảo vệ dữ liệu và bảo mật thông tin liên lạc.</span><span class="sxs-lookup"><span data-stu-id="e7140-109">You are responsible for ensuring that your use of Dynamics 365 Customer Insights, including predictions, complies with all applicable laws and regulations, including laws related to privacy, personal data, biometric data, data protection, and confidentiality of communications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e7140-110">Điều kiện tiên quyết</span><span class="sxs-lookup"><span data-stu-id="e7140-110">Prerequisites</span></span>

<span data-ttu-id="e7140-111">Trước khi tổ chức của bạn có thể sử dụng tính năng dự đoán, hãy đảm bảo đáp ứng các điều kiện tiên quyết sau đây:</span><span class="sxs-lookup"><span data-stu-id="e7140-111">Before your organization can use the predictions feature, the following prerequisites must be met:</span></span>

1. <span data-ttu-id="e7140-112">Tổ chức của bạn có một phiên bản [được thiết lập trong Common Data Service](/ai-builder/build-model#prerequisites) và nằm trong cùng một tổ chức với Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="e7140-112">Your organization has an instance [set up in the Common Data Service](/ai-builder/build-model#prerequisites) and it's in the same organization as Customer Insights.</span></span>

2. <span data-ttu-id="e7140-113">Môi trường của bạn gắn với phiên bản Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="e7140-113">Your environment is attached to your Common Data Service instance.</span></span>

<span data-ttu-id="e7140-114">Nếu bạn [tạo môi trường đầu tiên](manage-environments.md), hãy đặt cấu hình trong hộp thoại **Tạo môi trường** và chọn **Nâng cao**.</span><span class="sxs-lookup"><span data-stu-id="e7140-114">If you're [creating a new environment](manage-environments.md), configure it in the **Create an environment** dialog and select **Advanced**.</span></span> <span data-ttu-id="e7140-115">Nếu bạn đã tạo một môi trường, hãy đi tới cài đặt của nó và chọn **Nâng cao**.</span><span class="sxs-lookup"><span data-stu-id="e7140-115">If you've already created an environment, go to its settings and select **Advanced**.</span></span> <span data-ttu-id="e7140-116">Dù bằng cách nào, trong phần **Sử dụng dự đoán**, nhập URL phiên bản Common Data Service mà bạn muốn đính kèm môi trường của mình.</span><span class="sxs-lookup"><span data-stu-id="e7140-116">Either way, in the **Use predictions** section, enter the Common Data Service instance URL to which you want to attach your environment.</span></span>

## <a name="create-a-prediction-in-the-customer-entity"></a><span data-ttu-id="e7140-117">Tạo dự đoán trong thực thể Khách hàng</span><span class="sxs-lookup"><span data-stu-id="e7140-117">Create a prediction in the Customer entity</span></span>

1. <span data-ttu-id="e7140-118">Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Dữ liệu** > **Thực thể**.</span><span class="sxs-lookup"><span data-stu-id="e7140-118">In audience insights, go to **Data** > **Entities**.</span></span>

2. <span data-ttu-id="e7140-119">Chọn thực thể **Khách hàng**.</span><span class="sxs-lookup"><span data-stu-id="e7140-119">Select the **Customer** entity.</span></span>

3. <span data-ttu-id="e7140-120">Trong thực thể **Khách hàng: CustomerInsights**, chọn trên tab **Trường**.</span><span class="sxs-lookup"><span data-stu-id="e7140-120">In the **Customer:CustomerInsights** entity, select on the **Fields** tab.</span></span>

4. <span data-ttu-id="e7140-121">Tìm tên thuộc tính bạn muốn dự đoán giá trị, sau đó chọn biểu tượng **Tổng quan** trong cột **Tóm tắt**.</span><span class="sxs-lookup"><span data-stu-id="e7140-121">Find the attribute name you wish to predict values for, then select the **Overview** icon in the **Summary** column.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e7140-122">![Biểu tượng tổng quan](media/intelligence-overviewicon.png "Biểu tượng tổng quan")</span><span class="sxs-lookup"><span data-stu-id="e7140-122">![Overview icon](media/intelligence-overviewicon.png "Overview icon")</span></span>

5. <span data-ttu-id="e7140-123">Nếu có tỷ lệ cao là thiếu giá trị cho thuộc tính của bạn, chọn **Dự đoán các giá trị còn thiếu** để tiếp tục với dự đoán của bạn.</span><span class="sxs-lookup"><span data-stu-id="e7140-123">If there's a high rate of missing values for your attribute, select **Predict missing values** to continue with your prediction.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e7140-124">![Nút hiển thị trạng thái tổng quan với dự đoán các giá trị còn thiếu](media/intelligence-overviewpredictmissingvalues.png "Nút hiển thị trạng thái tổng quan với dự đoán các giá trị còn thiếu")</span><span class="sxs-lookup"><span data-stu-id="e7140-124">![Overview status with predict missing values button shown](media/intelligence-overviewpredictmissingvalues.png "Overview status with predict missing values button shown")</span></span>

6. <span data-ttu-id="e7140-125">Cung cấp **Tên hiển thị** và **Tên thực thể đầu ra** cho kết quả dự đoán.</span><span class="sxs-lookup"><span data-stu-id="e7140-125">Provide a **Display name** and an **Output entity name** for the results of the prediction.</span></span>

7. <span data-ttu-id="e7140-126">Một danh sách các tùy chọn được điền sẵn sẽ hiển thị ở nơi bạn có thể ánh xạ các giá trị vào thể loại được dự đoán.</span><span class="sxs-lookup"><span data-stu-id="e7140-126">A pre-populated list of options will show where you can map the values to a predicted category.</span></span> <span data-ttu-id="e7140-127">Trong trường hợp này, các tùy chọn thể loại duy nhất của bạn sẽ là 0 hoặc 1 khi chúng ánh xạ vào đặc điểm đúng/sai hoặc nhị phân của dự đoán.</span><span class="sxs-lookup"><span data-stu-id="e7140-127">In this case, your only category options will be 0 or 1, as they map to the true/false or binary nature of the prediction.</span></span> <span data-ttu-id="e7140-128">Trong cột Thể loại, ánh xạ các giá trị trường mà bạn muốn phân loại là "0" trong dự đoán cuối cùng vào "0" và các mục bạn muốn phân loại là "1" trong dự đoán cuối cùng vào "1".</span><span class="sxs-lookup"><span data-stu-id="e7140-128">In the Category column, map the field values you'd like to be classified as "0" in the final prediction to "0", and the items you'd like to be classified as "1" in the final prediction to "1".</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e7140-129">![Ví dụ hiển thị các giá trị trường đã ánh xạ vào thể loại](media/intelligence-categorymapping.png "Ví dụ hiển thị các giá trị trường đã ánh xạ vào thể loại")</span><span class="sxs-lookup"><span data-stu-id="e7140-129">![Example showing mapped field values to categories](media/intelligence-categorymapping.png "Example showing mapped field values to categories")</span></span>

8. <span data-ttu-id="e7140-130">Chọn **Xong** và dự đoán sẽ được xử lý.</span><span class="sxs-lookup"><span data-stu-id="e7140-130">Select **Done** and the prediction will be processed.</span></span> <span data-ttu-id="e7140-131">Việc xử lý sẽ mất một lúc, tùy thuộc vào kích thước và độ phức tạp của dữ liệu.</span><span class="sxs-lookup"><span data-stu-id="e7140-131">The processing will take some time, depending on the size and complexity of data.</span></span> <span data-ttu-id="e7140-132">Kết quả sẽ có sẵn trong một thực thể mới dựa trên **Tên thực thể đầu ra** của dự đoán bạn đã tạo.</span><span class="sxs-lookup"><span data-stu-id="e7140-132">Results will be available in a new entity based on the **Output entity name** of the prediction you created.</span></span>

## <a name="create-a-prediction-while-creating-a-segment"></a><span data-ttu-id="e7140-133">Tạo dự đoán trong khi tạo phân đoạn</span><span class="sxs-lookup"><span data-stu-id="e7140-133">Create a prediction while creating a segment</span></span>

<span data-ttu-id="e7140-134">Bạn cũng có thể dự đoán giá trị còn thiếu cho một thuộc tính cụ thể khi tạo phân đoạn.</span><span class="sxs-lookup"><span data-stu-id="e7140-134">Predicting missing values for a specific attribute of choice is also possible when creating a segment.</span></span> <span data-ttu-id="e7140-135">Cụ thể, khi bạn tạo nhanh phân đoạn dựa trên thực thể Khách hàng thống nhất hoặc thực thể Giá trị đo khách hàng.</span><span class="sxs-lookup"><span data-stu-id="e7140-135">Specifically, when you quickly create a segment based on either your unified Customer entity or Customer_Measure entity.</span></span>

<span data-ttu-id="e7140-136">Trong quy trình này, bạn chọn một thuộc tính cụ thể để căn cứ phân đoạn của mình, như Sự hài lòng của khách hàng hoặc Số tiền giao dịch.</span><span class="sxs-lookup"><span data-stu-id="e7140-136">As part of this flow, you'll choose a specific attribute to base your segment on, such as Customer Satisfaction or Purchase Amount.</span></span> <span data-ttu-id="e7140-137">Khi tạo phân đoạn, hệ thống sẽ đề xuất một phương pháp để dự đoán bất kỳ giá trị thiếu nào cho thuộc tính này.</span><span class="sxs-lookup"><span data-stu-id="e7140-137">Upon segment creation, the system will suggest a method for predicting any missing values for this attribute.</span></span>

1. <span data-ttu-id="e7140-138">Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Phân đoạn** và chọn ngăn xếp **Hồ sơ**.</span><span class="sxs-lookup"><span data-stu-id="e7140-138">In audience insights, go to **Segments** and select the **Profiles** tile.</span></span>

2. <span data-ttu-id="e7140-139">Chọn một **Trường** để tạo phân đoạn và chọn một **Toán tử**, sau đó chọn **Xem lại**.</span><span class="sxs-lookup"><span data-stu-id="e7140-139">Choose a **Field** to create a segment on and select an **Operator**, then select **Review**.</span></span>

3. <span data-ttu-id="e7140-140">Cung cấp **Tên** và **Tên hiển thị** cho phân đoạn.</span><span class="sxs-lookup"><span data-stu-id="e7140-140">Provide a **Name** and a **Display name** for the segment.</span></span>

4. <span data-ttu-id="e7140-141">Chọn **Lưu**.</span><span class="sxs-lookup"><span data-stu-id="e7140-141">Select **Save**.</span></span>

5. <span data-ttu-id="e7140-142">Nếu phân đoạn bạn vừa tạo có dữ liệu chưa hoàn chỉnh trong trường nguồn, bạn có thể chọn để dự đoán các giá trị còn thiếu.</span><span class="sxs-lookup"><span data-stu-id="e7140-142">If the segment you created has incomplete data in the source field, you can choose to predict the missing values.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e7140-143">![Nút dự đoán](media/segments-predictoption.png "Nút dự đoán")</span><span class="sxs-lookup"><span data-stu-id="e7140-143">![Prediction button](media/segments-predictoption.png "Prediction button")</span></span>

6. <span data-ttu-id="e7140-144">Cung cấp **Tên hiển thị** và **Tên thực thể đầu ra** cho kết quả dự đoán.</span><span class="sxs-lookup"><span data-stu-id="e7140-144">Provide a **Display name** and an **Output entity name** for the results of the prediction.</span></span>

7. <span data-ttu-id="e7140-145">Chọn **Xong**.</span><span class="sxs-lookup"><span data-stu-id="e7140-145">Select **Done**.</span></span> <span data-ttu-id="e7140-146">Dự đoán của bạn sẽ được tạo ngay trong một thực thể mới với tên bạn cung cấp trong **Tên thực thể đầu ra**.</span><span class="sxs-lookup"><span data-stu-id="e7140-146">Your prediction will be generated shortly in a new entity with the name you provided for the **Output entity name**.</span></span>

## <a name="view-a-prediction"></a><span data-ttu-id="e7140-147">Xem dự đoán</span><span class="sxs-lookup"><span data-stu-id="e7140-147">View a prediction</span></span>

1. <span data-ttu-id="e7140-148">Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Thông tin** > **Dự đoán** > **Dự đoán của tôi**.</span><span class="sxs-lookup"><span data-stu-id="e7140-148">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="e7140-149">Chọn dự đoán bạn muốn xem lại.</span><span class="sxs-lookup"><span data-stu-id="e7140-149">Select the prediction you want to review.</span></span>

3. <span data-ttu-id="e7140-150">Chọn dấu ba chấm trong cột **Hành động** và chọn **Xem**.</span><span class="sxs-lookup"><span data-stu-id="e7140-150">Select the ellipsis in the **Actions** column and choose **View**.</span></span>

4. <span data-ttu-id="e7140-151">Bạn sẽ thấy một số điểm dữ liệu trong dạng xem dự đoán của mình.</span><span class="sxs-lookup"><span data-stu-id="e7140-151">You'll see a number of data points in the view of your prediction.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e7140-152">![Trang dự đoán](media/intelligence-predictionsviewpage.png "Trang dự đoán")</span><span class="sxs-lookup"><span data-stu-id="e7140-152">![Predictions page](media/intelligence-predictionsviewpage.png "Predictions page")</span></span>

   - <span data-ttu-id="e7140-153">**Giá trị dự đoán** cho thấy ánh xạ bạn tạo ra trong giai đoạn ánh xạ giá trị Trường sang Thể loại.</span><span class="sxs-lookup"><span data-stu-id="e7140-153">**Predicted values** shows the mapping you created during the Field value to Category mapping phase.</span></span> <span data-ttu-id="e7140-154">Đó là các giá trị trong tập dữ liệu của bạn đã được ánh xạ tới một thể loại cụ thể.</span><span class="sxs-lookup"><span data-stu-id="e7140-154">These are the values in your dataset that have been mapped to a specific category.</span></span>
   <span data-ttu-id="e7140-155">-**Các yếu tố ảnh hưởng hàng đầu** là các yếu tố trong tập dữ liệu của bạn có nhiều khả năng ảnh hưởng đến độ tin cậy của dự đoán về giá trị Trường được ánh xạ tới một thể loại cụ thể.</span><span class="sxs-lookup"><span data-stu-id="e7140-155">-**Top influencers** are the factors within your dataset that were most likely to influence the prediction's confidence of your Field value being mapped to a specific category.</span></span>
   - <span data-ttu-id="e7140-156">**Hiệu suất** cho biết hiệu quả dự đoán.</span><span class="sxs-lookup"><span data-stu-id="e7140-156">**Performance** indicates how the predictions are doing.</span></span> <span data-ttu-id="e7140-157">Chọn liên kết để tìm hiểu thêm.</span><span class="sxs-lookup"><span data-stu-id="e7140-157">Select the link to learn more.</span></span>
   - <span data-ttu-id="e7140-158">**Xem trước** hiển thị mẫu tập dữ liệu đầu ra từ dự đoán của bạn và khả năng, hoặc độ tin cậy, của giá trị dự đoán trong đó 0 là không chắc chắn và 1 là chắc chắn.</span><span class="sxs-lookup"><span data-stu-id="e7140-158">**Preview** shows samples of the output dataset from your prediction and the likelihood, or our confidence, of the predicted value where 0 is uncertain, and 1 is certain.</span></span>

## <a name="update-a-prediction"></a><span data-ttu-id="e7140-159">Cập nhật dự đoán</span><span class="sxs-lookup"><span data-stu-id="e7140-159">Update a prediction</span></span>

1. <span data-ttu-id="e7140-160">Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Thông tin** > **Dự đoán** > **Dự đoán của tôi**.</span><span class="sxs-lookup"><span data-stu-id="e7140-160">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="e7140-161">Chọn dự đoán bạn muốn cập nhật và chọn biểu tượng **cập nhật**.</span><span class="sxs-lookup"><span data-stu-id="e7140-161">Select the prediction you want to update and select the **Update** icon.</span></span>

3. <span data-ttu-id="e7140-162">Dự đoán sẽ được lên kế hoạch để xử lý.</span><span class="sxs-lookup"><span data-stu-id="e7140-162">The prediction will be scheduled for processing.</span></span> <span data-ttu-id="e7140-163">Bạn có thể xem thời gian cập nhật lần cuối trong cột **cập nhật** của trang **Dự đoán**.</span><span class="sxs-lookup"><span data-stu-id="e7140-163">You can see the time it was last updated in the **Updated** column of the **Predictions** page.</span></span>

## <a name="edit-a-prediction"></a><span data-ttu-id="e7140-164">Chỉnh sửa dự đoán</span><span class="sxs-lookup"><span data-stu-id="e7140-164">Edit a prediction</span></span>

<span data-ttu-id="e7140-165">Sau khi tạo dự đoán, bạn có thể tùy chỉnh mô hình trong AI Builder để tăng hiệu quả của mô hình.</span><span class="sxs-lookup"><span data-stu-id="e7140-165">After you've created a prediction, you can customize the model in the AI Builder to increase the effectiveness of your model.</span></span>  

1. <span data-ttu-id="e7140-166">Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Thông tin** > **Dự đoán** > **Dự đoán của tôi**.</span><span class="sxs-lookup"><span data-stu-id="e7140-166">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="e7140-167">Chọn dự đoán bạn muốn chỉnh sửa.</span><span class="sxs-lookup"><span data-stu-id="e7140-167">Select the prediction you want to edit.</span></span>

3. <span data-ttu-id="e7140-168">Chọn dấu ba chấm trong cột **Hành động** và chọn **Xem**.</span><span class="sxs-lookup"><span data-stu-id="e7140-168">Select the ellipsis in the **Actions** column and choose **View**.</span></span>

4. <span data-ttu-id="e7140-169">Chọn **Tùy chỉnh trong AI Builder**.</span><span class="sxs-lookup"><span data-stu-id="e7140-169">Select **Customize in AI Builder**.</span></span>

5. <span data-ttu-id="e7140-170">Cập nhật mô hình của bạn trong AI Builder.</span><span class="sxs-lookup"><span data-stu-id="e7140-170">Update your model in the AI Builder.</span></span> <span data-ttu-id="e7140-171">[Tìm hiểu thêm về cách quản lý mô hình trong AI Builder](/ai-builder/manage-model#retrain-and-republish-existing-models).</span><span class="sxs-lookup"><span data-stu-id="e7140-171">[Learn more about managing models in the AI builder](/ai-builder/manage-model#retrain-and-republish-existing-models).</span></span>

<span data-ttu-id="e7140-172">Trong lần chạy tiếp theo, dự đoán sẽ sử dụng mô hình cập nhật mà bạn đã tạo.</span><span class="sxs-lookup"><span data-stu-id="e7140-172">The next run of your prediction will use the updated model you've created.</span></span>

> [!NOTE]
> <span data-ttu-id="e7140-173">Các mô hình mới được tạo trong AI Builder sẽ không được hiển thị trong thông tin chi tiết về đối tượng trừ khi mô hình được tạo từ các trải nghiệm được liệt kê ở trên.</span><span class="sxs-lookup"><span data-stu-id="e7140-173">New models created in AI Builder will not be displayed in audience insights unless the model was created from the experiences listed above.</span></span>

## <a name="remove-a-prediction"></a><span data-ttu-id="e7140-174">Loại bỏ dự đoán</span><span class="sxs-lookup"><span data-stu-id="e7140-174">Remove a prediction</span></span>

1. <span data-ttu-id="e7140-175">Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Thông tin** > **Dự đoán** > **Dự đoán của tôi**.</span><span class="sxs-lookup"><span data-stu-id="e7140-175">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="e7140-176">Chọn dự đoán bạn muốn xóa.</span><span class="sxs-lookup"><span data-stu-id="e7140-176">Select the prediction you want to delete.</span></span>

3. <span data-ttu-id="e7140-177">Chọn dấu ba chấm trong cột **Hành động** và chọn **Xóa**.</span><span class="sxs-lookup"><span data-stu-id="e7140-177">Select the ellipsis in the **Actions** column and choose **Delete**.</span></span>

4. <span data-ttu-id="e7140-178">Xác nhận tác vụ xóa này.</span><span class="sxs-lookup"><span data-stu-id="e7140-178">Confirm the deletion.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="e7140-179">Gỡ rối</span><span class="sxs-lookup"><span data-stu-id="e7140-179">Troubleshooting</span></span>

<span data-ttu-id="e7140-180">Nếu không thể hoàn thành quy trình đính kèm Common Data Service do lỗi, bạn có thể cố hoàn thành quy trình theo cách thủ công.</span><span class="sxs-lookup"><span data-stu-id="e7140-180">If you can't complete the attach Common Data Service process due to an error, you can try to complete the process manually.</span></span> <span data-ttu-id="e7140-181">Có hai vấn đề đã biết có thể xảy ra trong quy trình đính kèm:</span><span class="sxs-lookup"><span data-stu-id="e7140-181">There are two known issues that can occur in the attach process:</span></span>

- <span data-ttu-id="e7140-182">Giải pháp Bổ trợ thẻ khách hàng chưa được cài đặt.</span><span class="sxs-lookup"><span data-stu-id="e7140-182">The Customer Card Add-in solution is not installed.</span></span>
    1. <span data-ttu-id="e7140-183">Hoàn thành các hướng dẫn để [cài đặt và đặt cấu hình giải pháp](customer-card-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="e7140-183">Complete the instructions to [install and configure the solution](customer-card-add-in.md).</span></span>

- <span data-ttu-id="e7140-184">Quyền ứng dụng không được cấp.</span><span class="sxs-lookup"><span data-stu-id="e7140-184">App permissions aren't granted.</span></span>
    1. <span data-ttu-id="e7140-185">Truy cập [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="e7140-185">Go to [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).</span></span>
    1. <span data-ttu-id="e7140-186">Chọn **Môi trường**.</span><span class="sxs-lookup"><span data-stu-id="e7140-186">Select **Environments**.</span></span>
    1. <span data-ttu-id="e7140-187">Chọn dấu chấm lửng bên cạnh môi trường bạn muốn thêm quyền và chọn **Cài đặt**.</span><span class="sxs-lookup"><span data-stu-id="e7140-187">Select the ellipsis next to the environment you want to add the permission to and select **Settings**.</span></span>
    1. <span data-ttu-id="e7140-188">Mở rộng **Người dùng + quyền** và chọn **Người dùng**.</span><span class="sxs-lookup"><span data-stu-id="e7140-188">Expand **Users + permissions** and select **Users**.</span></span>
    1. <span data-ttu-id="e7140-189">Chọn **+ Mới** và chọn **Người dùng**.</span><span class="sxs-lookup"><span data-stu-id="e7140-189">Select **+ New** and select **User**.</span></span>
    1. <span data-ttu-id="e7140-190">Chọn **Người dùng ứng dụng** nếu chưa chọn và nhập thông tin sau:</span><span class="sxs-lookup"><span data-stu-id="e7140-190">Select **Application User** if it's not already selected and enter the following information:</span></span>
        - <span data-ttu-id="e7140-191">**Tên người dùng:** cihelp@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="e7140-191">**User Name:** cihelp@microsoft.com</span></span>
        - <span data-ttu-id="e7140-192">**ID ứng dụng:** 38c77d00-5fcb-4cce-9d93-af4738258e3c</span><span class="sxs-lookup"><span data-stu-id="e7140-192">**Application ID:** 38c77d00-5fcb-4cce-9d93-af4738258e3c</span></span>
        - <span data-ttu-id="e7140-193">**Tên:** Khách hàng</span><span class="sxs-lookup"><span data-stu-id="e7140-193">**First Name:** Customer</span></span>
        - <span data-ttu-id="e7140-194">**Họ:** Thông tin chi tiết</span><span class="sxs-lookup"><span data-stu-id="e7140-194">**Last Name:** Insights</span></span>
        - <span data-ttu-id="e7140-195">**Email chính:** cihelp@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="e7140-195">**Primary Email:** cihelp@microsoft.com</span></span>
    1. <span data-ttu-id="e7140-196">Chọn **Lưu & Đóng**.</span><span class="sxs-lookup"><span data-stu-id="e7140-196">Select **Save & Close**.</span></span>
    1. <span data-ttu-id="e7140-197">Chọn người dùng bạn vừa tạo.</span><span class="sxs-lookup"><span data-stu-id="e7140-197">Select the user you just created.</span></span>
    1. <span data-ttu-id="e7140-198">Chọn **Quản lý vai trò** trong thanh menu trên cùng.</span><span class="sxs-lookup"><span data-stu-id="e7140-198">Select **Manage Roles** in the top menu bar.</span></span>
    1. <span data-ttu-id="e7140-199">Chọn **Quản trị viên hệ thống** rồi chọn **OK**.</span><span class="sxs-lookup"><span data-stu-id="e7140-199">Select **System Administrator**, then select **OK**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]