---
title: Hướng dẫn mẫu dự đoán đề xuất sản phẩm
description: Sử dụng hướng dẫn mẫu này để thử mô hình dự đoán đề xuất sản phẩm dùng ngay.
ms.date: 02/10/2021
ms.reviewer: digranad
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0ee873d9b7caa5f891cb2d5b8c665dec90ad0e59
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270546"
---
# <a name="product-recommendation-prediction-preview-sample-guide"></a><span data-ttu-id="160ef-103">Hướng dẫn mẫu dự đoán đề xuất sản phẩm (bản xem trước)</span><span class="sxs-lookup"><span data-stu-id="160ef-103">Product recommendation prediction (preview) sample guide</span></span>

<span data-ttu-id="160ef-104">Chúng tôi hướng dẫn bạn thông qua một ví dụ toàn diện về dự đoán đề xuất sản phẩm bằng cách sử dụng dữ liệu mẫu được cung cấp bên dưới.</span><span class="sxs-lookup"><span data-stu-id="160ef-104">We'll walk you through an end to end example of product recommendation prediction using the sample data provided below.</span></span>

## <a name="scenario"></a><span data-ttu-id="160ef-105">Kịch bản</span><span class="sxs-lookup"><span data-stu-id="160ef-105">Scenario</span></span>

<span data-ttu-id="160ef-106">Contoso là công ty sản xuất cà phê và máy pha cà phê chất lượng cao, họ bán thông qua trang web Contoso Coffee của mình.</span><span class="sxs-lookup"><span data-stu-id="160ef-106">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="160ef-107">Mục tiêu là hiểu họ nên giới thiệu sản phẩm nào cho khách hàng định kỳ của họ.</span><span class="sxs-lookup"><span data-stu-id="160ef-107">Their goal is to understand which products should they recommend to their recurring customers.</span></span> <span data-ttu-id="160ef-108">Biết khách hàng **có khả năng mua** sản phẩm nào hơn, có thể giúp họ tiết kiệm nỗ lực tiếp thị bằng cách tập trung vào các mặt hàng cụ thể.</span><span class="sxs-lookup"><span data-stu-id="160ef-108">Knowing what customers are more **likely to purchase**, can help them save marketing efforts by focusing on specific items.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="160ef-109">Điều kiện tiên quyết</span><span class="sxs-lookup"><span data-stu-id="160ef-109">Prerequisites</span></span>

- <span data-ttu-id="160ef-110">Ít nhất [Quyền của người đóng góp](permissions.md) trong Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="160ef-110">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="160ef-111">Chúng tôi khuyên bạn nên thực hiện các bước sau [trong một môi trường mới](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="160ef-111">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="160ef-112">Nhiệm vụ 1 - Nhập dữ liệu</span><span class="sxs-lookup"><span data-stu-id="160ef-112">Task 1 - Ingest data</span></span>

<span data-ttu-id="160ef-113">Đặc biệt, hãy xem lại các bài viết [về nhập dữ liệu](data-sources.md) và [nhập nguồn dữ liệu bằng trình kết nối Power Query](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="160ef-113">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="160ef-114">Thông tin sau đây giả định rằng bạn đã quen với việc nhập dữ liệu nói chung.</span><span class="sxs-lookup"><span data-stu-id="160ef-114">The following information assumes you familiarized with ingesting data in general.</span></span>

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="160ef-115">Nhập dữ liệu khách hàng từ nền tảng Thương mại điện tử</span><span class="sxs-lookup"><span data-stu-id="160ef-115">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="160ef-116">Tạo nguồn dữ liệu có tên **Thương mại điện tử**, chọn tùy chọn nhập và chọn trình kết nối **Văn bản/CSV**.</span><span class="sxs-lookup"><span data-stu-id="160ef-116">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="160ef-117">Nhập URL cho các liên hệ Thương mại điện tử https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="160ef-117">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="160ef-118">Trong khi chỉnh sửa dữ liệu, hãy chọn **Chuyển đổi** và sau đó **Sử dụng hàng đầu tiên làm tiêu đề**.</span><span class="sxs-lookup"><span data-stu-id="160ef-118">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="160ef-119">Cập nhật kiểu dữ liệu cho các cột được liệt kê bên dưới:</span><span class="sxs-lookup"><span data-stu-id="160ef-119">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="160ef-120">**DateOfBirth**: Ngày</span><span class="sxs-lookup"><span data-stu-id="160ef-120">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="160ef-121">**CreatedOn**: Ngày/Giờ/Vùng</span><span class="sxs-lookup"><span data-stu-id="160ef-121">**CreatedOn**: Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Chuyển đổi ngày sinh thành ngày.":::

5. <span data-ttu-id="160ef-123">Trong trường "Tên" ở ngăn bên phải, hãy đổi tên nguồn dữ liệu của bạn từ **Truy vấn** thành **eCommerceContacts**.</span><span class="sxs-lookup"><span data-stu-id="160ef-123">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

6. <span data-ttu-id="160ef-124">**Lưu** nguồn dữ liệu.</span><span class="sxs-lookup"><span data-stu-id="160ef-124">**Save** the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="160ef-125">Nhập dữ liệu mua hàng trực tuyến</span><span class="sxs-lookup"><span data-stu-id="160ef-125">Ingest online purchase data</span></span>

1. <span data-ttu-id="160ef-126">Thêm một tập hợp dữ liệu khác vào cùng một nguồn dữ liệu **Thương mại điện tử**.</span><span class="sxs-lookup"><span data-stu-id="160ef-126">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="160ef-127">Chọn lại trình kết nối **Văn bản/CSV**.</span><span class="sxs-lookup"><span data-stu-id="160ef-127">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="160ef-128">Nhập URL cho dữ liệu **Mua hàng trực tuyến** https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="160ef-128">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="160ef-129">Trong khi chỉnh sửa dữ liệu, hãy chọn **Chuyển đổi** và sau đó **Sử dụng hàng đầu tiên làm tiêu đề**.</span><span class="sxs-lookup"><span data-stu-id="160ef-129">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="160ef-130">Cập nhật kiểu dữ liệu cho các cột được liệt kê bên dưới:</span><span class="sxs-lookup"><span data-stu-id="160ef-130">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="160ef-131">**PurchasedOn**: Ngày/Giờ</span><span class="sxs-lookup"><span data-stu-id="160ef-131">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="160ef-132">**TotalPrice**: Tiền tệ</span><span class="sxs-lookup"><span data-stu-id="160ef-132">**TotalPrice**: Currency</span></span>

1. <span data-ttu-id="160ef-133">Trong trường **Tên** ở ngăn bên, hãy đổi tên nguồn dữ liệu của bạn từ **Truy vấn** thành **eCommercePurchases**.</span><span class="sxs-lookup"><span data-stu-id="160ef-133">In the **Name** field on the side pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="160ef-134">Lưu nguồn dữ liệu.</span><span class="sxs-lookup"><span data-stu-id="160ef-134">Save the data source.</span></span>


### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="160ef-135">Nhập dữ liệu khách hàng từ lược đồ khách hàng thân thiết</span><span class="sxs-lookup"><span data-stu-id="160ef-135">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="160ef-136">Tạo nguồn dữ liệu có tên **LoyaltyScheme**, chọn tùy chọn nhập và chọn trình kết nối **Văn bản/CSV**.</span><span class="sxs-lookup"><span data-stu-id="160ef-136">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="160ef-137">Nhập URL cho các liên hệ Thương mại điện tử https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="160ef-137">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="160ef-138">Trong khi chỉnh sửa dữ liệu, hãy chọn **Chuyển đổi** và sau đó **Sử dụng hàng đầu tiên làm tiêu đề**.</span><span class="sxs-lookup"><span data-stu-id="160ef-138">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="160ef-139">Cập nhật kiểu dữ liệu cho các cột được liệt kê bên dưới:</span><span class="sxs-lookup"><span data-stu-id="160ef-139">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="160ef-140">**DateOfBirth**: Ngày</span><span class="sxs-lookup"><span data-stu-id="160ef-140">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="160ef-141">**RewardsPoints**: Số nguyên</span><span class="sxs-lookup"><span data-stu-id="160ef-141">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="160ef-142">**CreatedOn**: Ngày/Giờ</span><span class="sxs-lookup"><span data-stu-id="160ef-142">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="160ef-143">Trong trường **Tên** ở ngăn bên phải, hãy đổi tên nguồn dữ liệu của bạn từ **Truy vấn** thành **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="160ef-143">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="160ef-144">Lưu nguồn dữ liệu.</span><span class="sxs-lookup"><span data-stu-id="160ef-144">Save the data source.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="160ef-145">Nhiệm vụ 2 - Hợp nhất dữ liệu</span><span class="sxs-lookup"><span data-stu-id="160ef-145">Task 2 - Data unification</span></span>

<span data-ttu-id="160ef-146">Sau khi nhập dữ liệu, bây giờ chúng ta bắt đầu quy trình **Ánh xạ, So khớp, Hợp nhất** để tạo hồ sơ khách hàng hợp nhất.</span><span class="sxs-lookup"><span data-stu-id="160ef-146">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="160ef-147">Để biết thêm thông tin, hãy xem [Hợp nhất dữ liệu](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="160ef-147">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="160ef-148">Bản đồ</span><span class="sxs-lookup"><span data-stu-id="160ef-148">Map</span></span>

1. <span data-ttu-id="160ef-149">Sau khi nhập dữ liệu, hãy ánh xạ các địa chỉ liên hệ từ dữ liệu Thương mại điện tử và Mức độ trung thành thành các loại dữ liệu phổ biến.</span><span class="sxs-lookup"><span data-stu-id="160ef-149">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="160ef-150">Chuyển đến **Dữ liệu** > **Hợp nhất** > **Ánh xạ**.</span><span class="sxs-lookup"><span data-stu-id="160ef-150">Go to **Data** > **Unify** > **Map**.</span></span>

2. <span data-ttu-id="160ef-151">Chọn các thực thể đại diện cho hồ sơ khách hàng – **eCommerceContacts** và **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="160ef-151">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span>

   ![hợp nhất nguồn dữ liệu thương mại điện tử và khách hàng thân thiết.](media/unify-ecommerce-loyalty.png)

3. <span data-ttu-id="160ef-153">Chọn **ContactId** làm khóa chính cho **eCommerceContacts** và **LoyaltyID** làm khóa chính cho **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="160ef-153">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   ![Hợp nhất LoyaltyId làm khóa chính.](media/unify-loyaltyid.png)

### <a name="match"></a><span data-ttu-id="160ef-155">So khớp</span><span class="sxs-lookup"><span data-stu-id="160ef-155">Match</span></span>

1. <span data-ttu-id="160ef-156">Đi đến tab **So khớp** và chọn **Đặt thứ tự**.</span><span class="sxs-lookup"><span data-stu-id="160ef-156">Go to the **Match** tab and select **Set Order**.</span></span>

2. <span data-ttu-id="160ef-157">Trong danh sách thả xuống **Chính**, chọn **eCommerceContacts: eCommerce** là nguồn chính và bao gồm tất cả các bản ghi.</span><span class="sxs-lookup"><span data-stu-id="160ef-157">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

3. <span data-ttu-id="160ef-158">Trong danh sách thả xuống **Thực thể 2**, chọn **loyCustomers : LoyaltyScheme** và bao gồm tất cả các bản ghi.</span><span class="sxs-lookup"><span data-stu-id="160ef-158">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   ![Hợp nhất so khớp thương mại điện tử và khách hàng thân thiết.](media/unify-match-order.png)

4. <span data-ttu-id="160ef-160">Chọn **Tạo quy tắc mới**</span><span class="sxs-lookup"><span data-stu-id="160ef-160">Select **Create a new rule**</span></span>

5. <span data-ttu-id="160ef-161">Thêm điều kiện đầu tiên của bạn bằng FullName.</span><span class="sxs-lookup"><span data-stu-id="160ef-161">Add your first condition using FullName.</span></span>

   - <span data-ttu-id="160ef-162">Đối với eCommerceContacts, hãy chọn **FullName** trong danh sách thả xuống.</span><span class="sxs-lookup"><span data-stu-id="160ef-162">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="160ef-163">Đối với loyCustomers, hãy chọn **FullName** trong danh sách thả xuống.</span><span class="sxs-lookup"><span data-stu-id="160ef-163">For loyCustomers select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="160ef-164">Chọn danh sách thả xuống **Chuẩn hóa** và chọn **Loại (Điện thoại, Tên, Địa chỉ, ...)**.</span><span class="sxs-lookup"><span data-stu-id="160ef-164">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   - <span data-ttu-id="160ef-165">Đặt **Mức độ chính xác**: **Cơ bản** và **Giá trị**: **Cao**.</span><span class="sxs-lookup"><span data-stu-id="160ef-165">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

6. <span data-ttu-id="160ef-166">Nhập tên **FullName, Email** cho quy tắc mới.</span><span class="sxs-lookup"><span data-stu-id="160ef-166">Enter the name **FullName, Email** for the new rule.</span></span>

   - <span data-ttu-id="160ef-167">Thêm điều kiện thứ hai cho địa chỉ email bằng cách chọn **Thêm điều kiện**</span><span class="sxs-lookup"><span data-stu-id="160ef-167">Add a second condition for email address by selecting **Add Condition**</span></span>
   - <span data-ttu-id="160ef-168">Đối với thực thể eCommerceContacts, hãy chọn **Email** trong danh sách thả xuống.</span><span class="sxs-lookup"><span data-stu-id="160ef-168">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   - <span data-ttu-id="160ef-169">Đối với thực thể loyCustomers, hãy chọn **Email** trong danh sách thả xuống.</span><span class="sxs-lookup"><span data-stu-id="160ef-169">For entity loyCustomers, choose **EMail** in the drop-down.</span></span>
   - <span data-ttu-id="160ef-170">Để trống trường Chuẩn hóa.</span><span class="sxs-lookup"><span data-stu-id="160ef-170">Leave Normalize blank.</span></span>
   - <span data-ttu-id="160ef-171">Đặt **Mức độ chính xác**: **Cơ bản** và **Giá trị**: **Cao**.</span><span class="sxs-lookup"><span data-stu-id="160ef-171">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   ![Hợp nhất quy tắc so khớp cho tên và email.](media/unify-match-rule.png)

7. <span data-ttu-id="160ef-173">Chọn **Lưu** và **Chạy**.</span><span class="sxs-lookup"><span data-stu-id="160ef-173">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="160ef-174">Hợp nhất</span><span class="sxs-lookup"><span data-stu-id="160ef-174">Merge</span></span>

1. <span data-ttu-id="160ef-175">Đi đến tab **Hợp nhất**.</span><span class="sxs-lookup"><span data-stu-id="160ef-175">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="160ef-176">Trên thực thể **ContactId** cho **loyCustomers**, thay đổi tên hiển thị thành **ContactIdLOYALTY** để phân biệt nó với các ID khác đã nhập.</span><span class="sxs-lookup"><span data-stu-id="160ef-176">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   ![đổi tên contactid từ id khách hàng thân thiết.](media/unify-merge-contactid.png)

1. <span data-ttu-id="160ef-178">Chọn **Lưu** và **Chạy** để bắt đầu quy trình Hợp nhất.</span><span class="sxs-lookup"><span data-stu-id="160ef-178">Select **Save** and **Run** to start the Merge Process.</span></span>

## <a name="task-3---configure-product-recommendation-prediction"></a><span data-ttu-id="160ef-179">Nhiệm vụ 3 - Định cấu hình dự đoán đề xuất sản phẩm</span><span class="sxs-lookup"><span data-stu-id="160ef-179">Task 3 - Configure product recommendation prediction</span></span>

<span data-ttu-id="160ef-180">Với hồ sơ khách hàng hợp nhất đã có, giờ đây chúng tôi có thể chạy dự đoán rời bỏ đăng ký.</span><span class="sxs-lookup"><span data-stu-id="160ef-180">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span>

1. <span data-ttu-id="160ef-181">Đi đến **Thông tin** > **Dự đoán**, chọn **Đề xuất sản phẩm**.</span><span class="sxs-lookup"><span data-stu-id="160ef-181">Go to **Intelligence** > **Prediction** choose **Product recommendation**.</span></span>

1. <span data-ttu-id="160ef-182">Chọn **Bắt đầu**.</span><span class="sxs-lookup"><span data-stu-id="160ef-182">Select **Get started**.</span></span>

1. <span data-ttu-id="160ef-183">Đặt tên cho mô hình **Dự đoán Mô hình Đề xuất Sản phẩm OOB** và thực thể đầu ra **OOBProductRecommendationModelPrediction**.</span><span class="sxs-lookup"><span data-stu-id="160ef-183">Name the model **OOB Product Recommendation Model Prediction** and the output entity **OOBProductRecommendationModelPrediction**.</span></span>

1. <span data-ttu-id="160ef-184">Xác định ba điều kiện cho mô hình:</span><span class="sxs-lookup"><span data-stu-id="160ef-184">Define three conditions for the model:</span></span>

   - <span data-ttu-id="160ef-185">**Số lượng sản phẩm**: Đặt giá trị này thành **5**.</span><span class="sxs-lookup"><span data-stu-id="160ef-185">**Number of products**: Set this value to **5**.</span></span> <span data-ttu-id="160ef-186">Cài đặt này xác định số lượng sản phẩm bạn muốn giới thiệu cho khách hàng của mình.</span><span class="sxs-lookup"><span data-stu-id="160ef-186">This setting defines how many products you want to recommend to your customers.</span></span>

   - <span data-ttu-id="160ef-187">**Đề xuất sản phẩm khách hàng đã mua gần đây?**: Chọn **Có** để cho biết rằng bạn muốn đưa sản phẩm vào phần giới thiệu mà khách hàng của bạn đã mua trước đó.</span><span class="sxs-lookup"><span data-stu-id="160ef-187">**Suggest products customers have recently purchased?**: Select **Yes** to indicate that you want to include products in the recommendation that your customers have purchased before.</span></span>

   - <span data-ttu-id="160ef-188">**Khoảng thời gian xem lại:** Chọn ít nhất **365 ngày**.</span><span class="sxs-lookup"><span data-stu-id="160ef-188">**Look back window:** Select at least **365 days**.</span></span> <span data-ttu-id="160ef-189">Cài đặt này xác định khoảng thời gian mô hình sẽ xem xét hoạt động của khách hàng để dùng làm thông tin đề xuất cho họ.</span><span class="sxs-lookup"><span data-stu-id="160ef-189">This setting defines how far the model will look back at the customer's activity to use it as input to their recommendations.</span></span>
   
   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Tùy chọn mô hình cho mô hình đề xuất sản phẩm.":::

1. <span data-ttu-id="160ef-191">Chọn **Dữ liệu bắt buộc** và chọn **Thêm dữ liệu** cho lịch sử giao dịch.</span><span class="sxs-lookup"><span data-stu-id="160ef-191">Select **Required data** and select **Add data** for purchase history.</span></span>

1. <span data-ttu-id="160ef-192">Thêm thực thể **eCommercePurchases: eCommerce** và ánh xạ các trường từ thương mại điện tử đến các trường tương ứng theo yêu cầu của mô hình.</span><span class="sxs-lookup"><span data-stu-id="160ef-192">Add the **eCommercePurchases : eCommerce** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="160ef-193">Tham gia thực thể **eCommercePurchases: eCommerce** với **eCommerceContacts: eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="160ef-193">Join the **eCommercePurchases : eCommerce** entity with **eCommerceContacts : eCommerce**.</span></span>

   ![Tham gia các thực thể thương mại điện tử.](media/model-purchase-join.png)

1. <span data-ttu-id="160ef-195">Chọn **Tiếp theo** để đặt lịch trình mô hình.</span><span class="sxs-lookup"><span data-stu-id="160ef-195">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="160ef-196">Mô hình cần đào tạo thường xuyên để học các mẫu mới khi có dữ liệu mới được nhập vào.</span><span class="sxs-lookup"><span data-stu-id="160ef-196">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="160ef-197">Đối với ví dụ này, hãy chọn **Hàng tháng**.</span><span class="sxs-lookup"><span data-stu-id="160ef-197">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="160ef-198">Sau khi xem xét tất cả các chi tiết, hãy chọn **Lưu và chạy**.</span><span class="sxs-lookup"><span data-stu-id="160ef-198">After reviewing all the details, select **Save and Run**.</span></span>


## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="160ef-199">Nhiệm vụ 4 - Xem xét kết quả và giải thích mô hình</span><span class="sxs-lookup"><span data-stu-id="160ef-199">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="160ef-200">Để mô hình hoàn thành việc đào tạo và chấm điểm dữ liệu.</span><span class="sxs-lookup"><span data-stu-id="160ef-200">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="160ef-201">Bây giờ bạn có thể xem lại giải thích về mô hình đề xuất sản phẩm.</span><span class="sxs-lookup"><span data-stu-id="160ef-201">You can now review the product recommendation model explanations.</span></span> <span data-ttu-id="160ef-202">Để biết thêm thông tin, hãy xem [Xem lại dự đoán trạng thái và kết quả](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="160ef-202">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-purchased-products"></a><span data-ttu-id="160ef-203">Nhiệm vụ 5 - Tạo phân khúc sản phẩm được mua nhiều</span><span class="sxs-lookup"><span data-stu-id="160ef-203">Task 5 - Create a segment of high purchased products</span></span>

<span data-ttu-id="160ef-204">Việc chạy mô hình sản xuất sẽ tạo ra một thực thể mới mà bạn có thể thấy trong **Dữ liệu** > **Thực thể**.</span><span class="sxs-lookup"><span data-stu-id="160ef-204">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>

<span data-ttu-id="160ef-205">Bạn có thể tạo một phân khúc mới dựa trên thực thể được tạo bởi mô hình.</span><span class="sxs-lookup"><span data-stu-id="160ef-205">You can create a new segment based on the entity created by the model.</span></span>

1. <span data-ttu-id="160ef-206">Đi đến **Phân khúc**.</span><span class="sxs-lookup"><span data-stu-id="160ef-206">Go to **Segments**.</span></span> <span data-ttu-id="160ef-207">Chọn **Mới** và chọn **Tạo từ** > **Thông tin**.</span><span class="sxs-lookup"><span data-stu-id="160ef-207">Select **New** and choose **Create from** > **Intelligence**.</span></span>

   ![Tạo một phân khúc với đầu ra mô hình.](media/segment-intelligence.png)

1. <span data-ttu-id="160ef-209">Chọn điểm cuối **OOBProductRecommendationModelPrediction** và xác định phân khúc:</span><span class="sxs-lookup"><span data-stu-id="160ef-209">Select the **OOBProductRecommendationModelPrediction** endpoint and define the segment:</span></span>

   - <span data-ttu-id="160ef-210">Trường: ID sản phẩm</span><span class="sxs-lookup"><span data-stu-id="160ef-210">Field: ProductID</span></span>
   - <span data-ttu-id="160ef-211">Toán tử: Giá trị</span><span class="sxs-lookup"><span data-stu-id="160ef-211">Operator: Value</span></span>
   - <span data-ttu-id="160ef-212">Giá trị: Chọn ba ID sản phẩm hàng đầu</span><span class="sxs-lookup"><span data-stu-id="160ef-212">Value: Select the top three product IDs</span></span>

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="Tạo một phân đoạn từ kết quả mô hình.":::

<span data-ttu-id="160ef-214">Giờ đây, bạn có một phân khúc được cập nhật tự động, xác định những khách hàng sẵn sàng mua ba sản phẩm được đề xuất nhiều nhất</span><span class="sxs-lookup"><span data-stu-id="160ef-214">You now have a segment that is dynamically updated which identifies the customers who are more willing to purchase the three most recommended products</span></span> 

<span data-ttu-id="160ef-215">Để biết thêm thông tin, hãy xem [Tạo và quản lý phân khúc](segments.md).</span><span class="sxs-lookup"><span data-stu-id="160ef-215">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]