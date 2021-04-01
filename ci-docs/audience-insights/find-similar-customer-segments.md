---
title: Tìm khách hàng tương tự với AI
description: Tìm phân khúc khách hàng tương tự nhờ trí tuệ nhân tạo.
ms.date: 06/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: f588f45ed11efffbb335003642a4b92810153017
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596801"
---
# <a name="similar-customers-preview"></a><span data-ttu-id="8ed83-103">Khách hàng tương tự (xem trước)</span><span class="sxs-lookup"><span data-stu-id="8ed83-103">Similar Customers (preview)</span></span>

<span data-ttu-id="8ed83-104">Tính năng này cho phép bạn tìm thấy những khách hàng tương tự trong cơ sở khách hàng của mình bằng cách sử dụng trí tuệ nhân tạo.</span><span class="sxs-lookup"><span data-stu-id="8ed83-104">This feature lets you find similar customers in your customer base using artificial intelligence.</span></span> <span data-ttu-id="8ed83-105">Bạn cần phải có ít nhất một phân khúc được tạo để sử dụng tính năng này.</span><span class="sxs-lookup"><span data-stu-id="8ed83-105">You need to have at least one segment created to use this feature.</span></span> <span data-ttu-id="8ed83-106">Mở rộng các tiêu chí của một phân đoạn hiện có sẽ giúp tìm kiếm các khách hàng tương tự với phân khúc đó.</span><span class="sxs-lookup"><span data-stu-id="8ed83-106">Expanding the criteria of an existing segment help find customers that are similar to that segment.</span></span>

> [!NOTE]
> <span data-ttu-id="8ed83-107">*Tìm khách hàng tương tự* sử dụng các phương tiện tự động để đánh giá dữ liệu và đưa ra dự đoán dựa trên dữ liệu đó và do đó có khả năng được sử dụng làm phương pháp lập hồ sơ, theo định nghĩa về thuật ngữ đó trong Quy định chung về bảo vệ dữ liệu ("GDPR").</span><span class="sxs-lookup"><span data-stu-id="8ed83-107">*Find similar customers* uses automated means to evaluate data and make predictions based on that data, and therefore has the capability to be used as a method of profiling, as that term is defined by the General Data Protection Regulation (“GDPR”).</span></span> <span data-ttu-id="8ed83-108">Việc khách hàng sử dụng tính năng này để xử lý dữ liệu phải tuân theo GDPR hoặc các luật/quy định khác.</span><span class="sxs-lookup"><span data-stu-id="8ed83-108">Customer’s use of this feature to process data may be subject to GDPR or other laws or regulations.</span></span> <span data-ttu-id="8ed83-109">Bạn có trách nhiệm đảm bảo rằng việc sử dụng Dynamics 365 Customer Insights, bao gồm các dự đoán, tuân thủ tất cả các luật và quy định hiện hành, bao gồm các luật liên quan đến quyền riêng tư, dữ liệu cá nhân, dữ liệu sinh trắc học, bảo vệ dữ liệu và bảo mật thông tin liên lạc.</span><span class="sxs-lookup"><span data-stu-id="8ed83-109">You are responsible for ensuring that your use of Dynamics 365 Customer Insights, including predictions, complies with all applicable laws and regulations, including laws related to privacy, personal data, biometric data, data protection, and confidentiality of communications.</span></span>

## <a name="finding-similar-customers"></a><span data-ttu-id="8ed83-110">Tìm khách hàng tương tự</span><span class="sxs-lookup"><span data-stu-id="8ed83-110">Finding similar customers</span></span>

1. <span data-ttu-id="8ed83-111">Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Phân đoạn** và chọn phân đoạn bạn muốn làm cơ sở cho phân đoạn mới của mình.</span><span class="sxs-lookup"><span data-stu-id="8ed83-111">In audience insights, go to **Segments** and select the segment you want to base your new segment on.</span></span> <span data-ttu-id="8ed83-112">Đó là *phân khúc nguồn* của bạn.</span><span class="sxs-lookup"><span data-stu-id="8ed83-112">That's your *source segment*.</span></span>

1. <span data-ttu-id="8ed83-113">Trên thanh hành động, chọn **Tìm khách hàng tương tự**.</span><span class="sxs-lookup"><span data-stu-id="8ed83-113">In the action bar, select **Find similar customers**.</span></span>

1. <span data-ttu-id="8ed83-114">Xem lại tên được gợi ý cho phân khúc mới của bạn và đổi tên nếu cần.</span><span class="sxs-lookup"><span data-stu-id="8ed83-114">Review the suggested name for your new segment and change it if necessary.</span></span>

1. <span data-ttu-id="8ed83-115">Xem lại các trường xác định phân khúc mới của bạn.</span><span class="sxs-lookup"><span data-stu-id="8ed83-115">Review the fields that define your new segment.</span></span> <span data-ttu-id="8ed83-116">Các trường này xác định cơ sở mà hệ thống sẽ cố gắng tìm khách hàng tương tự với phân khúc nguồn của bạn.</span><span class="sxs-lookup"><span data-stu-id="8ed83-116">These fields define the basis on which the system will try to find similar customers to your source segment.</span></span> <span data-ttu-id="8ed83-117">Hệ thống sẽ chọn các trường được đề xuất theo mặc định.</span><span class="sxs-lookup"><span data-stu-id="8ed83-117">The system will select recommended fields by default.</span></span>
  <span data-ttu-id="8ed83-118">Các trường có thể làm giảm đáng kể hiệu suất mô hình sẽ tự động bị loại trừ:</span><span class="sxs-lookup"><span data-stu-id="8ed83-118">Fields that can significantly reduce the model performance are automatically excluded:</span></span>
  
   - <span data-ttu-id="8ed83-119">Các trường có các kiểu dữ liệu sau: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType</span><span class="sxs-lookup"><span data-stu-id="8ed83-119">Fields with the following data types: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType</span></span>
   - <span data-ttu-id="8ed83-120">Các trường có lượng số (số thành phần trong một trường) ít hơn 2 hoặc nhiều hơn 30</span><span class="sxs-lookup"><span data-stu-id="8ed83-120">Fields with a cardinality (the number of elements in a field) of less than 2 or more than 30</span></span>

1. <span data-ttu-id="8ed83-121">Chọn xem bạn muốn thêm **Tất cả khách hàng** hay chỉ khách hàng trong **Phân khúc cụ thể hiện có** vào phân khúc mới của mình.</span><span class="sxs-lookup"><span data-stu-id="8ed83-121">Choose if you want to include **All customers** or only customers in a **Specific existing segment** in your new segment.</span></span>

1. <span data-ttu-id="8ed83-122">Loại trừ khách hàng trong phân khúc nguồn của bạn bằng cách chọn hộp kiểm **Loại trừ tất cả mọi người trong phân khúc nguồn**.</span><span class="sxs-lookup"><span data-stu-id="8ed83-122">Exclude customers in your source segment by selecting the **Exclude everyone in source segment** checkbox.</span></span>

1. <span data-ttu-id="8ed83-123">Theo mặc định, hệ thống gợi ý chỉ nên bao gồm 20% kích thước đối tượng mục tiêu trong đầu ra của bạn.</span><span class="sxs-lookup"><span data-stu-id="8ed83-123">By default, the system suggests including only 20% of the target audience size in your output.</span></span> <span data-ttu-id="8ed83-124">Chỉnh sửa ngưỡng này nếu cần.</span><span class="sxs-lookup"><span data-stu-id="8ed83-124">Edit this threshold as needed.</span></span> <span data-ttu-id="8ed83-125">Tăng ngưỡng sẽ làm giảm độ chính xác.</span><span class="sxs-lookup"><span data-stu-id="8ed83-125">Increasing the threshold will reduce the precision.</span></span>

1. <span data-ttu-id="8ed83-126">Lựa chọn **Chạy** ở dưới cùng của trang để bắt đầu nhiệm vụ phân loại nhị phân (một phương thức máy học) để phân tích tập dữ liệu.</span><span class="sxs-lookup"><span data-stu-id="8ed83-126">Select **Run** at the bottom of the page to start a binary classification task (a method of machine learning) which analyzes the dataset.</span></span>

## <a name="view-the-similar-segment"></a><span data-ttu-id="8ed83-127">Xem phân khúc tương tự</span><span class="sxs-lookup"><span data-stu-id="8ed83-127">View the similar segment</span></span>

<span data-ttu-id="8ed83-128">Sau khi xử lý phân khúc tương tự, bạn sẽ tìm thấy phân khúc mới được liệt kê trên trang **Phân khúc**.</span><span class="sxs-lookup"><span data-stu-id="8ed83-128">After processing the similar segment, you'll find the new segment listed on the **Segments** page.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="8ed83-129">![Phân khúc khách hàng tương tự](media/expanded-segment.png "Phân khúc khách hàng tương tự")</span><span class="sxs-lookup"><span data-stu-id="8ed83-129">![Similar customers segment](media/expanded-segment.png "Similar customers segment")</span></span>

<span data-ttu-id="8ed83-130">Chọn **Xem** trên thành hành động để mở chi tiết phân khúc.</span><span class="sxs-lookup"><span data-stu-id="8ed83-130">Select **View** in the action bar to open the segment detail.</span></span> <span data-ttu-id="8ed83-131">Dạng xem này chứa thông tin về phân phối kết quả trên [điểm tương đồng](#about-similarity-scores).</span><span class="sxs-lookup"><span data-stu-id="8ed83-131">This view contains information about the result distribution across [similarity scores](#about-similarity-scores).</span></span> <span data-ttu-id="8ed83-132">Bạn cũng sẽ tìm thấy các giá trị điểm tương đồng trong **Xem trước thành phần phân khúc**.</span><span class="sxs-lookup"><span data-stu-id="8ed83-132">You'll also find the similarity score values in the **Segment members preview**.</span></span>

## <a name="use-the-output-of-a-similar-segment"></a><span data-ttu-id="8ed83-133">Sử dụng đầu ra của phân khúc tương tự</span><span class="sxs-lookup"><span data-stu-id="8ed83-133">Use the output of a similar segment</span></span>

<span data-ttu-id="8ed83-134">Bạn có thể [làm việc với đầu ra của phân khúc tương tự](segments.md) như với các phân khúc khác.</span><span class="sxs-lookup"><span data-stu-id="8ed83-134">You can [work with the output of a similar segment](segments.md) as you do with other segments.</span></span> <span data-ttu-id="8ed83-135">Ví dụ: xuất phân khúc hoặc xây dựng một giá trị đo.</span><span class="sxs-lookup"><span data-stu-id="8ed83-135">For example, export the segment or build a measure.</span></span>

## <a name="refresh-and-edit-a-similar-segment"></a><span data-ttu-id="8ed83-136">Làm mới và chỉnh sửa phân khúc tương tự</span><span class="sxs-lookup"><span data-stu-id="8ed83-136">Refresh and edit a similar segment</span></span>

<span data-ttu-id="8ed83-137">Để làm mới phân khúc tương tự, hãy chọn phân khúc đó trên trang **Phân khúc** rồi chọn **Làm mới** trên thanh hành động.</span><span class="sxs-lookup"><span data-stu-id="8ed83-137">To refresh a similar segment, select it on the **Segments** page and select **Refresh** in the action bar.</span></span>

<span data-ttu-id="8ed83-138">Thao tác chỉnh sửa phân khúc tương tự sẽ xử lý lại dữ liệu của bạn.</span><span class="sxs-lookup"><span data-stu-id="8ed83-138">Editing a similar segment will reprocess your data.</span></span> <span data-ttu-id="8ed83-139">Phân khúc đã tạo trước đó được cập nhật dữ liệu làm mới.</span><span class="sxs-lookup"><span data-stu-id="8ed83-139">The previously created segment gets updated with refreshed data.</span></span>    
<span data-ttu-id="8ed83-140">Để chỉnh sửa phân khúc tương tự, hãy chọn phân khúc đó trên trang **Phân khúc** rồi chọn **Chỉnh sửa** trên thanh hành động.</span><span class="sxs-lookup"><span data-stu-id="8ed83-140">To edit a similar segment, select it on the **Segments** page and select **Edit** in the action bar.</span></span> <span data-ttu-id="8ed83-141">Áp dụng thay đổi của bạn và chọn **Chạy** để bắt đầu xử lý.</span><span class="sxs-lookup"><span data-stu-id="8ed83-141">Apply your changes and select **Run** to start the processing.</span></span>

## <a name="delete-a-similar-segment"></a><span data-ttu-id="8ed83-142">Xóa phân khúc tương tự</span><span class="sxs-lookup"><span data-stu-id="8ed83-142">Delete a similar segment</span></span>

<span data-ttu-id="8ed83-143">Chọn phân khúc trên trang **Phân khúc** rồi chọn **Xóa** trên thanh hành động.</span><span class="sxs-lookup"><span data-stu-id="8ed83-143">Select the segment on the **Segments** page and select **Delete** in the action bar.</span></span> <span data-ttu-id="8ed83-144">Sau đó, xác nhận xóa.</span><span class="sxs-lookup"><span data-stu-id="8ed83-144">Then, confirm your deletion.</span></span>

## <a name="about-similarity-scores"></a><span data-ttu-id="8ed83-145">Giới thiệu về điểm tương đồng</span><span class="sxs-lookup"><span data-stu-id="8ed83-145">About similarity scores</span></span>

<span data-ttu-id="8ed83-146">Mô hình học trên máy phân loại nhị phân gán một điểm số cho khách hàng trong phân khúc tương tự.</span><span class="sxs-lookup"><span data-stu-id="8ed83-146">The binary classification machine learning model assigns a score to customers in the similar segment.</span></span> <span data-ttu-id="8ed83-147">Điểm số dựa trên sự tương đồng với khách hàng trong phân khúc nguồn.</span><span class="sxs-lookup"><span data-stu-id="8ed83-147">The score is based on the similarity to customers in the source segment.</span></span>

- <span data-ttu-id="8ed83-148">Điểm tương đồng dưới 0,55 có nghĩa khách hàng được hệ thống phân loại là *không giống* với khách hàng trong phân khúc nguồn</span><span class="sxs-lookup"><span data-stu-id="8ed83-148">Similarity scores below 0.55 are customers the system classified as *not similar* to customers in the source segment</span></span>
- <span data-ttu-id="8ed83-149">Điểm tương đồng trong khoảng 0,55 – 0,7 được phân loại là *có phần giống*</span><span class="sxs-lookup"><span data-stu-id="8ed83-149">Similarity scores between 0.55 – 0.7 are classified as *somewhat similar*</span></span>
- <span data-ttu-id="8ed83-150">Điểm tương đồng trong khoảng 0,7 – 0,85 được phân loại là *giống*</span><span class="sxs-lookup"><span data-stu-id="8ed83-150">Similarity scores between 0.7 – 0.85 are classified as *similar*</span></span>
- <span data-ttu-id="8ed83-151">Điểm tương đồng trong khoảng 0,85 – 1 là các khách hàng được hệ thống phân loại là *rất giống*</span><span class="sxs-lookup"><span data-stu-id="8ed83-151">Similarity scores between 0.85 – 1 are customers the system classified as *very similar*</span></span>

<span data-ttu-id="8ed83-152">Khách hàng có điểm tương tự dưới 0,4 không được bao gồm trong đầu ra mô hình.</span><span class="sxs-lookup"><span data-stu-id="8ed83-152">Customers with similarity scores below 0.4 aren't included in the model output.</span></span> <span data-ttu-id="8ed83-153">Hệ thống nhận định họ không đủ tương tự với phân khúc nguồn.</span><span class="sxs-lookup"><span data-stu-id="8ed83-153">The system doesn't consider them similar enough to the source segment.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]