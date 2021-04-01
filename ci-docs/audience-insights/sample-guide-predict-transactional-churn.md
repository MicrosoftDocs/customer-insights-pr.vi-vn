---
title: Hướng dẫn mẫu dự đoán rời bỏ giao dịch
description: Sử dụng hướng dẫn mẫu này để thử mô hình dự đoán rời bỏ giao dịch dùng ngay.
ms.date: 11/19/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: 251bc26246cee16952e8e4cb08e2ed7aa4d18488
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595452"
---
# <a name="transactional-churn-prediction-preview-sample-guide"></a><span data-ttu-id="cbc00-103">Hướng dẫn mẫu dự đoán rời bỏ giao dịch (bản xem trước)</span><span class="sxs-lookup"><span data-stu-id="cbc00-103">Transactional churn prediction (preview) sample guide</span></span>

<span data-ttu-id="cbc00-104">Hướng dẫn này sẽ giải thích cho bạn ví dụ toàn diện về dự đoán rời bỏ giao dịch trong Customer Insights bằng cách sử dụng dữ liệu được cung cấp bên dưới.</span><span class="sxs-lookup"><span data-stu-id="cbc00-104">This guide will walk you through an end to end example of Transactional Churn prediction in Customer Insights using the data provided below.</span></span> <span data-ttu-id="cbc00-105">Tất cả dữ liệu được sử dụng trong hướng dẫn này không phải là dữ liệu khách hàng thực và là một phần của tập dữ liệu Contoso được tìm thấy trong môi trường *Demo* trong Đăng ký Customer Insights của bạn.</span><span class="sxs-lookup"><span data-stu-id="cbc00-105">All data used in this guide is not real customer data and is part of the Contoso dataset found in the *Demo* environment within your Customer Insights Subscription.</span></span>

## <a name="scenario"></a><span data-ttu-id="cbc00-106">Kịch bản</span><span class="sxs-lookup"><span data-stu-id="cbc00-106">Scenario</span></span>

<span data-ttu-id="cbc00-107">Contoso là công ty sản xuất cà phê và máy pha cà phê chất lượng cao, họ bán thông qua trang web Contoso Coffee của mình.</span><span class="sxs-lookup"><span data-stu-id="cbc00-107">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="cbc00-108">Mục tiêu là biết những khách hàng nào thường mua sản phẩm của họ một cách thường xuyên, sẽ không còn là khách hàng tích cực trong 60 ngày tới.</span><span class="sxs-lookup"><span data-stu-id="cbc00-108">Their goal is to know which customers who typically purchase their products on a regular basis, will stop being active customers in the next 60 days.</span></span> <span data-ttu-id="cbc00-109">Biết khách hàng nào **có khả năng rời bỏ**, có thể giúp họ tiết kiệm các nỗ lực tiếp thị bằng cách tập trung vào việc giữ chân họ.</span><span class="sxs-lookup"><span data-stu-id="cbc00-109">Knowing which of their customers is **likely to churn**, can help them save marketing efforts by focusing on keeping them.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="cbc00-110">Điều kiện tiên quyết</span><span class="sxs-lookup"><span data-stu-id="cbc00-110">Prerequisites</span></span>

- <span data-ttu-id="cbc00-111">Ít nhất [Quyền của người đóng góp](permissions.md) trong Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="cbc00-111">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="cbc00-112">Chúng tôi khuyên bạn nên thực hiện các bước sau [trong một môi trường mới](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="cbc00-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="cbc00-113">Nhiệm vụ 1 - Nhập dữ liệu</span><span class="sxs-lookup"><span data-stu-id="cbc00-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="cbc00-114">Đặc biệt, hãy xem lại các bài viết [về nhập dữ liệu](data-sources.md) và [nhập nguồn dữ liệu bằng trình kết nối Power Query](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="cbc00-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="cbc00-115">Thông tin sau đây giả định rằng bạn đã quen với việc nhập dữ liệu nói chung.</span><span class="sxs-lookup"><span data-stu-id="cbc00-115">The following information assumes you familiarized with ingesting data in general.</span></span> 

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="cbc00-116">Nhập dữ liệu khách hàng từ nền tảng Thương mại điện tử</span><span class="sxs-lookup"><span data-stu-id="cbc00-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="cbc00-117">Tạo nguồn dữ liệu có tên **Thương mại điện tử**, chọn tùy chọn nhập và chọn trình kết nối **Văn bản/CSV**.</span><span class="sxs-lookup"><span data-stu-id="cbc00-117">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="cbc00-118">Nhập URL cho các liên hệ Thương mại điện tử https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="cbc00-118">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="cbc00-119">Trong khi chỉnh sửa dữ liệu, hãy chọn **Chuyển đổi** và sau đó **Sử dụng hàng đầu tiên làm tiêu đề**.</span><span class="sxs-lookup"><span data-stu-id="cbc00-119">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="cbc00-120">Cập nhật kiểu dữ liệu cho các cột được liệt kê bên dưới:</span><span class="sxs-lookup"><span data-stu-id="cbc00-120">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="cbc00-121">**DateOfBirth**: Ngày</span><span class="sxs-lookup"><span data-stu-id="cbc00-121">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="cbc00-122">**CreatedOn**: Ngày/Giờ/Vùng</span><span class="sxs-lookup"><span data-stu-id="cbc00-122">**CreatedOn**: Date/Time/Zone</span></span>

   [!div class="mx-imgBorder"]
   <span data-ttu-id="cbc00-123">![Chuyển đổi DoB thành Ngày](media/ecommerce-dob-date.PNG "chuyển đổi ngày sinh thành ngày")</span><span class="sxs-lookup"><span data-stu-id="cbc00-123">![Transform DoB to Date](media/ecommerce-dob-date.PNG "transform date of birth to date")</span></span>

1. <span data-ttu-id="cbc00-124">Trong trường **Tên** ở ngăn bên phải, hãy đổi tên nguồn dữ liệu của bạn từ **Truy vấn** thành **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="cbc00-124">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="cbc00-125">Lưu nguồn dữ liệu.</span><span class="sxs-lookup"><span data-stu-id="cbc00-125">Save the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="cbc00-126">Nhập dữ liệu mua hàng trực tuyến</span><span class="sxs-lookup"><span data-stu-id="cbc00-126">Ingest online purchase data</span></span>

1. <span data-ttu-id="cbc00-127">Thêm một tập hợp dữ liệu khác vào cùng một nguồn dữ liệu **Thương mại điện tử**.</span><span class="sxs-lookup"><span data-stu-id="cbc00-127">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="cbc00-128">Chọn lại trình kết nối **Văn bản/CSV**.</span><span class="sxs-lookup"><span data-stu-id="cbc00-128">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="cbc00-129">Nhập URL cho dữ liệu **Mua hàng trực tuyến** https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="cbc00-129">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="cbc00-130">Trong khi chỉnh sửa dữ liệu, hãy chọn **Chuyển đổi** và sau đó **Sử dụng hàng đầu tiên làm tiêu đề**.</span><span class="sxs-lookup"><span data-stu-id="cbc00-130">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="cbc00-131">Cập nhật kiểu dữ liệu cho các cột được liệt kê bên dưới:</span><span class="sxs-lookup"><span data-stu-id="cbc00-131">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="cbc00-132">**PurchasedOn**: Ngày/Giờ</span><span class="sxs-lookup"><span data-stu-id="cbc00-132">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="cbc00-133">**TotalPrice**: Tiền tệ</span><span class="sxs-lookup"><span data-stu-id="cbc00-133">**TotalPrice**: Currency</span></span>
   
1. <span data-ttu-id="cbc00-134">Trong trường **Tên** ở ngăn bên phải, hãy đổi tên nguồn dữ liệu của bạn từ **Truy vấn** thành **eCommercePurchases**.</span><span class="sxs-lookup"><span data-stu-id="cbc00-134">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="cbc00-135">Lưu nguồn dữ liệu.</span><span class="sxs-lookup"><span data-stu-id="cbc00-135">Save the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="cbc00-136">Nhập dữ liệu khách hàng từ lược đồ khách hàng thân thiết</span><span class="sxs-lookup"><span data-stu-id="cbc00-136">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="cbc00-137">Tạo nguồn dữ liệu có tên **LoyaltyScheme**, chọn tùy chọn nhập và chọn trình kết nối **Văn bản/CSV**.</span><span class="sxs-lookup"><span data-stu-id="cbc00-137">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="cbc00-138">Nhập URL cho các liên hệ Thương mại điện tử https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="cbc00-138">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="cbc00-139">Trong khi chỉnh sửa dữ liệu, hãy chọn **Chuyển đổi** và sau đó **Sử dụng hàng đầu tiên làm tiêu đề**.</span><span class="sxs-lookup"><span data-stu-id="cbc00-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="cbc00-140">Cập nhật kiểu dữ liệu cho các cột được liệt kê bên dưới:</span><span class="sxs-lookup"><span data-stu-id="cbc00-140">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="cbc00-141">**DateOfBirth**: Ngày</span><span class="sxs-lookup"><span data-stu-id="cbc00-141">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="cbc00-142">**RewardsPoints**: Số nguyên</span><span class="sxs-lookup"><span data-stu-id="cbc00-142">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="cbc00-143">**CreatedOn**: Ngày/Giờ</span><span class="sxs-lookup"><span data-stu-id="cbc00-143">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="cbc00-144">Trong trường **Tên** ở ngăn bên phải, hãy đổi tên nguồn dữ liệu của bạn từ **Truy vấn** thành **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="cbc00-144">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="cbc00-145">Lưu nguồn dữ liệu.</span><span class="sxs-lookup"><span data-stu-id="cbc00-145">Save the data source.</span></span>


## <a name="task-2---data-unification"></a><span data-ttu-id="cbc00-146">Nhiệm vụ 2 - Hợp nhất dữ liệu</span><span class="sxs-lookup"><span data-stu-id="cbc00-146">Task 2 - Data unification</span></span>

<span data-ttu-id="cbc00-147">Sau khi nhập dữ liệu, bây giờ chúng ta bắt đầu quy trình **Ánh xạ, So khớp, Hợp nhất** để tạo hồ sơ khách hàng hợp nhất.</span><span class="sxs-lookup"><span data-stu-id="cbc00-147">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="cbc00-148">Để biết thêm thông tin, hãy xem [Hợp nhất dữ liệu](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="cbc00-148">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="cbc00-149">Bản đồ</span><span class="sxs-lookup"><span data-stu-id="cbc00-149">Map</span></span>

1. <span data-ttu-id="cbc00-150">Sau khi nhập dữ liệu, hãy ánh xạ các địa chỉ liên hệ từ dữ liệu Thương mại điện tử và Mức độ trung thành thành các loại dữ liệu phổ biến.</span><span class="sxs-lookup"><span data-stu-id="cbc00-150">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="cbc00-151">Chuyển đến **Dữ liệu** > **Hợp nhất** > **Ánh xạ**.</span><span class="sxs-lookup"><span data-stu-id="cbc00-151">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="cbc00-152">Chọn các thực thể đại diện cho hồ sơ khách hàng – **eCommerceContacts** và **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="cbc00-152">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="hợp nhất nguồn dữ liệu thương mại điện tử và khách hàng thân thiết.":::

1. <span data-ttu-id="cbc00-154">Chọn **ContactId** làm khóa chính cho **eCommerceContacts** và **LoyaltyID** làm khóa chính cho **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="cbc00-154">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="Hợp nhất LoyaltyId làm khóa chính.":::

### <a name="match"></a><span data-ttu-id="cbc00-156">So khớp</span><span class="sxs-lookup"><span data-stu-id="cbc00-156">Match</span></span>

1. <span data-ttu-id="cbc00-157">Đi đến tab **So khớp** và chọn **Đặt thứ tự**.</span><span class="sxs-lookup"><span data-stu-id="cbc00-157">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="cbc00-158">Trong danh sách thả xuống **Chính**, chọn **eCommerceContacts: eCommerce** là nguồn chính và bao gồm tất cả các bản ghi.</span><span class="sxs-lookup"><span data-stu-id="cbc00-158">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="cbc00-159">Trong danh sách thả xuống **Thực thể 2**, chọn **loyCustomers : LoyaltyScheme** và bao gồm tất cả các bản ghi.</span><span class="sxs-lookup"><span data-stu-id="cbc00-159">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   :::image type="content" source="media/unify-match-order.PNG" alt-text="Hợp nhất so khớp thương mại điện tử và khách hàng thân thiết.":::

1. <span data-ttu-id="cbc00-161">Chọn **Tạo quy tắc mới**</span><span class="sxs-lookup"><span data-stu-id="cbc00-161">Select **Create a new rule**</span></span>

1. <span data-ttu-id="cbc00-162">Thêm điều kiện đầu tiên của bạn bằng FullName.</span><span class="sxs-lookup"><span data-stu-id="cbc00-162">Add your first condition using FullName.</span></span>

   * <span data-ttu-id="cbc00-163">Đối với eCommerceContacts, hãy chọn **FullName** trong danh sách thả xuống.</span><span class="sxs-lookup"><span data-stu-id="cbc00-163">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="cbc00-164">Đối với loyCustomers, hãy chọn **FullName** trong danh sách thả xuống.</span><span class="sxs-lookup"><span data-stu-id="cbc00-164">For loyCustomers select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="cbc00-165">Chọn danh sách thả xuống **Chuẩn hóa** và chọn **Loại (Điện thoại, Tên, Địa chỉ, ...)**.</span><span class="sxs-lookup"><span data-stu-id="cbc00-165">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   * <span data-ttu-id="cbc00-166">Đặt **Mức độ chính xác**: **Cơ bản** và **Giá trị**: **Cao**.</span><span class="sxs-lookup"><span data-stu-id="cbc00-166">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="cbc00-167">Nhập tên **FullName, Email** cho quy tắc mới.</span><span class="sxs-lookup"><span data-stu-id="cbc00-167">Enter the name **FullName, Email** for the new rule.</span></span>

   * <span data-ttu-id="cbc00-168">Thêm điều kiện thứ hai cho địa chỉ email bằng cách chọn **Thêm điều kiện**</span><span class="sxs-lookup"><span data-stu-id="cbc00-168">Add a second condition for email address by selecting **Add Condition**</span></span>
   * <span data-ttu-id="cbc00-169">Đối với thực thể eCommerceContacts, hãy chọn **Email** trong danh sách thả xuống.</span><span class="sxs-lookup"><span data-stu-id="cbc00-169">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   * <span data-ttu-id="cbc00-170">Đối với thực thể loyCustomers, hãy chọn **Email** trong danh sách thả xuống.</span><span class="sxs-lookup"><span data-stu-id="cbc00-170">For entity loyCustomers, choose **EMail** in the drop-down.</span></span> 
   * <span data-ttu-id="cbc00-171">Để trống trường Chuẩn hóa.</span><span class="sxs-lookup"><span data-stu-id="cbc00-171">Leave Normalize blank.</span></span> 
   * <span data-ttu-id="cbc00-172">Đặt **Mức độ chính xác**: **Cơ bản** và **Giá trị**: **Cao**.</span><span class="sxs-lookup"><span data-stu-id="cbc00-172">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="Hợp nhất quy tắc so khớp cho tên và email.":::

7. <span data-ttu-id="cbc00-174">Chọn **Lưu** và **Chạy**.</span><span class="sxs-lookup"><span data-stu-id="cbc00-174">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="cbc00-175">Hợp nhất</span><span class="sxs-lookup"><span data-stu-id="cbc00-175">Merge</span></span>

1. <span data-ttu-id="cbc00-176">Đi đến tab **Hợp nhất**.</span><span class="sxs-lookup"><span data-stu-id="cbc00-176">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="cbc00-177">Trên thực thể **ContactId** cho **loyCustomers**, thay đổi tên hiển thị thành **ContactIdLOYALTY** để phân biệt nó với các ID khác đã nhập.</span><span class="sxs-lookup"><span data-stu-id="cbc00-177">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="đổi tên contactid từ id khách hàng thân thiết.":::

1. <span data-ttu-id="cbc00-179">Chọn **Lưu** và **Chạy** để bắt đầu quy trình Hợp nhất.</span><span class="sxs-lookup"><span data-stu-id="cbc00-179">Select **Save** and **Run** to start the Merge Process.</span></span>



## <a name="task-3---configure-transaction-churn-prediction"></a><span data-ttu-id="cbc00-180">Nhiệm vụ 3 - Định cấu hình dự đoán rời bỏ giao dịch</span><span class="sxs-lookup"><span data-stu-id="cbc00-180">Task 3 - Configure transaction churn prediction</span></span>

<span data-ttu-id="cbc00-181">Với hồ sơ khách hàng hợp nhất đã có, giờ đây chúng tôi có thể chạy dự đoán rời bỏ đăng ký.</span><span class="sxs-lookup"><span data-stu-id="cbc00-181">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span> <span data-ttu-id="cbc00-182">Để biết các bước chi tiết, hãy xem bài viết [Dự đoán rời bỏ đăng ký (bản xem trước)](predict-subscription-churn.md).</span><span class="sxs-lookup"><span data-stu-id="cbc00-182">For detailed steps, see the [Subscription churn prediction (preview)](predict-subscription-churn.md) article.</span></span> 

1. <span data-ttu-id="cbc00-183">Đi đến **Thông tin** > **Khám phá** và chọn để sử dụng **Mô hình khách hàng rời đi**.</span><span class="sxs-lookup"><span data-stu-id="cbc00-183">Go to **Intelligence** > **Discover** and select to use the **Customer churn model**.</span></span>

1. <span data-ttu-id="cbc00-184">Chọn tùy chọn **Giao dịch** và chọn **Bắt đầu**.</span><span class="sxs-lookup"><span data-stu-id="cbc00-184">Select the **Transactional** option and select **Get started**.</span></span>

1. <span data-ttu-id="cbc00-185">Đặt tên cho mô hình **Dự đoán rời bỏ giao dịch thương mại điện tử OOB** và thực thể đầu ra **OOBeCommerceChurnPrediction**.</span><span class="sxs-lookup"><span data-stu-id="cbc00-185">Name the model **OOB eCommerce Transaction Churn Prediction** and the output entity **OOBeCommerceChurnPrediction**.</span></span>

1. <span data-ttu-id="cbc00-186">Xác định hai điều kiện cho mô hình khách hàng rời đi:</span><span class="sxs-lookup"><span data-stu-id="cbc00-186">Define two conditions for the churn model:</span></span>

   * <span data-ttu-id="cbc00-187">**Khoảng thời gian dự đoán**: **tối thiểu 60** ngày.</span><span class="sxs-lookup"><span data-stu-id="cbc00-187">**Prediction window**: **at least 60** days.</span></span> <span data-ttu-id="cbc00-188">Cài đặt này xác định chúng ta muốn dự đoán khách hàng rời đi trong tương lai bao xa.</span><span class="sxs-lookup"><span data-stu-id="cbc00-188">This setting defines how far into the future do we want to predict customer churn.</span></span>

   * <span data-ttu-id="cbc00-189">**Định nghĩa về tỷ lệ rời đi**: **tối thiểu 60** ngày.</span><span class="sxs-lookup"><span data-stu-id="cbc00-189">**Churn definition**: **at least 60** days.</span></span> <span data-ttu-id="cbc00-190">Khoảng thời gian không mua hàng mà sau đó khách hàng được coi là rời đi.</span><span class="sxs-lookup"><span data-stu-id="cbc00-190">The duration without purchase after which a customer is considered churned.</span></span>

     :::image type="content" source="media/model-levers.PNG" alt-text="Chọn mô hình thúc đẩy khoảng thời gian dự đoán và định nghĩa về tỷ lệ rời đi.":::

1. <span data-ttu-id="cbc00-192">Chọn **Lịch sử mua hàng (bắt buộc)** và chọn **Thêm dữ liệu** cho lịch sử mua hàng.</span><span class="sxs-lookup"><span data-stu-id="cbc00-192">Select **Purchase History (required)** and select **Add data** for purchase history.</span></span>

1. <span data-ttu-id="cbc00-193">Thêm thực thể **eCommercePurchases: eCommerce** và ánh xạ các trường từ thương mại điện tử đến các trường tương ứng theo yêu cầu của mô hình.</span><span class="sxs-lookup"><span data-stu-id="cbc00-193">Add the **eCommercePurchases : eCommerce** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="cbc00-194">Tham gia thực thể **eCommercePurchases: eCommerce** với **eCommerceContacts: eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="cbc00-194">Join the **eCommercePurchases : eCommerce** entity with **eCommerceContacts : eCommerce**.</span></span>

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="Tham gia các thực thể thương mại điện tử.":::

1. <span data-ttu-id="cbc00-196">Chọn **Tiếp theo** để đặt lịch trình mô hình.</span><span class="sxs-lookup"><span data-stu-id="cbc00-196">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="cbc00-197">Mô hình cần đào tạo thường xuyên để học các mẫu mới khi có dữ liệu mới được nhập vào.</span><span class="sxs-lookup"><span data-stu-id="cbc00-197">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="cbc00-198">Đối với ví dụ này, hãy chọn **Hàng tháng**.</span><span class="sxs-lookup"><span data-stu-id="cbc00-198">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="cbc00-199">Sau khi xem xét tất cả các chi tiết, hãy chọn **Lưu và chạy**.</span><span class="sxs-lookup"><span data-stu-id="cbc00-199">After reviewing all the details, select **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="cbc00-200">Nhiệm vụ 4 - Xem xét kết quả và giải thích mô hình</span><span class="sxs-lookup"><span data-stu-id="cbc00-200">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="cbc00-201">Để mô hình hoàn thành việc đào tạo và chấm điểm dữ liệu.</span><span class="sxs-lookup"><span data-stu-id="cbc00-201">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="cbc00-202">Bây giờ bạn có thể xem lại giải thích mô hình rời bỏ đăng ký.</span><span class="sxs-lookup"><span data-stu-id="cbc00-202">You can now review the subscription churn model explanations.</span></span> <span data-ttu-id="cbc00-203">Để biết thêm thông tin, hãy xem [Xem lại dự đoán trạng thái và kết quả](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="cbc00-203">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a><span data-ttu-id="cbc00-204">Nhiệm vụ 5 - Tạo một phân khúc khách hàng có nguy cơ rời bỏ cao</span><span class="sxs-lookup"><span data-stu-id="cbc00-204">Task 5 - Create a segment of high churn-risk customers</span></span>

<span data-ttu-id="cbc00-205">Việc chạy mô hình sản xuất sẽ tạo ra một thực thể mới mà bạn có thể thấy trong **Dữ liệu** > **Thực thể**.</span><span class="sxs-lookup"><span data-stu-id="cbc00-205">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>   

<span data-ttu-id="cbc00-206">Bạn có thể tạo một phân khúc mới dựa trên thực thể được tạo bởi mô hình.</span><span class="sxs-lookup"><span data-stu-id="cbc00-206">You can create a new segment based on the entity created by the model.</span></span>

1.  <span data-ttu-id="cbc00-207">Đi đến **Phân khúc**.</span><span class="sxs-lookup"><span data-stu-id="cbc00-207">Go to **Segments**.</span></span> <span data-ttu-id="cbc00-208">Chọn **Mới** và chọn **Tạo từ** > **Thông tin**.</span><span class="sxs-lookup"><span data-stu-id="cbc00-208">Select **New** and choose **Create from** > **Intelligence**.</span></span> 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Tạo một phân khúc với đầu ra mô hình.":::

1. <span data-ttu-id="cbc00-210">Chọn điểm cuối **OOBSubscriptionChurnPrediction** và xác định phân khúc:</span><span class="sxs-lookup"><span data-stu-id="cbc00-210">Select the **OOBSubscriptionChurnPrediction** endpoint and define the segment:</span></span> 
   - <span data-ttu-id="cbc00-211">Trường: ChurnScore</span><span class="sxs-lookup"><span data-stu-id="cbc00-211">Field: ChurnScore</span></span>
   - <span data-ttu-id="cbc00-212">Toán tử: lớn hơn</span><span class="sxs-lookup"><span data-stu-id="cbc00-212">Operator: greater than</span></span>
   - <span data-ttu-id="cbc00-213">Giá trị: 0.6</span><span class="sxs-lookup"><span data-stu-id="cbc00-213">Value: 0.6</span></span>
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Thiết lập phân khúc rời bỏ đăng ký.":::

<span data-ttu-id="cbc00-215">Giờ đây, bạn có một phân khúc được cập nhật động để xác định những khách hàng có nguy cơ rời bỏ cao cho doanh nghiệp đăng ký này.</span><span class="sxs-lookup"><span data-stu-id="cbc00-215">You now have a segment that is dynamically updated which identifies high churn-risk customers for this subscription business.</span></span>

<span data-ttu-id="cbc00-216">Để biết thêm thông tin, hãy xem [Tạo và quản lý phân khúc](segments.md).</span><span class="sxs-lookup"><span data-stu-id="cbc00-216">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]