---
title: Hướng dẫn mẫu dự đoán rời bỏ đăng ký
description: Sử dụng hướng dẫn mẫu này để thử mô hình dự đoán rời bỏ đăng ký dùng ngay.
ms.date: 11/19/2020
ms.reviewer: digranad
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 2537cfb5dde0d1ce1af16f585f0bf91d15ea1870
ms.sourcegitcommit: a6e7df90d61450e00886753eb5db116f2f35bb6c
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 12/01/2020
ms.locfileid: "4654006"
---
# <a name="subscription-churn-prediction-preview-sample-guide"></a><span data-ttu-id="1e932-103">Hướng dẫn mẫu dự đoán rời bỏ đăng ký (bản xem trước)</span><span class="sxs-lookup"><span data-stu-id="1e932-103">Subscription churn prediction (preview) sample guide</span></span>

<span data-ttu-id="1e932-104">Chúng tôi hướng dẫn bạn thông qua một ví dụ toàn diện về dự đoán rời bỏ đăng ký bằng cách sử dụng dữ liệu mẫu được cung cấp bên dưới.</span><span class="sxs-lookup"><span data-stu-id="1e932-104">We'll walk you through an end to end example of subscription churn prediction using the sample data provided below.</span></span> 

## <a name="scenario"></a><span data-ttu-id="1e932-105">Kịch bản</span><span class="sxs-lookup"><span data-stu-id="1e932-105">Scenario</span></span>

<span data-ttu-id="1e932-106">Contoso là công ty sản xuất cà phê và máy pha cà phê chất lượng cao, họ bán thông qua trang web Contoso Coffee của mình.</span><span class="sxs-lookup"><span data-stu-id="1e932-106">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="1e932-107">Gần đây, họ đã bắt đầu kinh doanh dịch vụ đăng ký cho khách hàng của mình để uống cà phê thường xuyên.</span><span class="sxs-lookup"><span data-stu-id="1e932-107">They recently started a subscription business for their customers to get coffee on a regular basis.</span></span> <span data-ttu-id="1e932-108">Mục tiêu của họ là hiểu, những khách hàng đã đăng ký nào có thể hủy đăng ký của họ trong vài tháng tới.</span><span class="sxs-lookup"><span data-stu-id="1e932-108">Their goal is to understand, which subscribed customers might cancel their subscription in the next few months.</span></span> <span data-ttu-id="1e932-109">Biết khách hàng nào **có khả năng rời bỏ**, có thể giúp họ tiết kiệm các nỗ lực tiếp thị bằng cách tập trung vào việc giữ chân họ.</span><span class="sxs-lookup"><span data-stu-id="1e932-109">Knowing which of their customers is **likely to churn**, can help them save marketing efforts by focusing on keeping them.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1e932-110">Điều kiện tiên quyết</span><span class="sxs-lookup"><span data-stu-id="1e932-110">Prerequisites</span></span>

- <span data-ttu-id="1e932-111">Ít nhất [Quyền của người đóng góp](permissions.md) trong Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="1e932-111">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="1e932-112">Chúng tôi khuyên bạn nên thực hiện các bước sau [trong một môi trường mới](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="1e932-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="1e932-113">Nhiệm vụ 1 - Nhập dữ liệu</span><span class="sxs-lookup"><span data-stu-id="1e932-113">Task 1 - Ingest Data</span></span>

<span data-ttu-id="1e932-114">Đặc biệt, hãy xem lại các bài viết [về nhập dữ liệu](data-sources.md) và [nhập nguồn dữ liệu bằng trình kết nối Power Query](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="1e932-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="1e932-115">Thông tin sau đây giả định rằng bạn đã quen với việc nhập dữ liệu nói chung.</span><span class="sxs-lookup"><span data-stu-id="1e932-115">The following information assumes you familiarized with ingesting data in general.</span></span> 

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="1e932-116">Nhập dữ liệu khách hàng từ nền tảng Thương mại điện tử</span><span class="sxs-lookup"><span data-stu-id="1e932-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="1e932-117">Tạo nguồn dữ liệu có tên **Thương mại điện tử**, chọn tùy chọn nhập và chọn trình kết nối **Văn bản/CSV**.</span><span class="sxs-lookup"><span data-stu-id="1e932-117">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="1e932-118">Nhập URL cho các liên hệ Thương mại điện tử https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="1e932-118">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="1e932-119">Trong khi chỉnh sửa dữ liệu, hãy chọn **Chuyển đổi** và sau đó **Sử dụng hàng đầu tiên làm tiêu đề**.</span><span class="sxs-lookup"><span data-stu-id="1e932-119">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="1e932-120">Cập nhật kiểu dữ liệu cho các cột được liệt kê bên dưới:</span><span class="sxs-lookup"><span data-stu-id="1e932-120">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="1e932-121">**DateOfBirth**: Ngày</span><span class="sxs-lookup"><span data-stu-id="1e932-121">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="1e932-122">**CreatedOn**: Ngày/Giờ/Vùng</span><span class="sxs-lookup"><span data-stu-id="1e932-122">**CreatedOn**: Date/Time/Zone</span></span>

   [!div class="mx-imgBorder"]
   <span data-ttu-id="1e932-123">![Chuyển đổi DoB thành Ngày](media/ecommerce-dob-date.PNG "chuyển đổi ngày sinh thành ngày")</span><span class="sxs-lookup"><span data-stu-id="1e932-123">![Transform DoB to Date](media/ecommerce-dob-date.PNG "transform date of birth to date")</span></span>

1. <span data-ttu-id="1e932-124">Trong trường "Tên" ở ngăn bên phải, hãy đổi tên nguồn dữ liệu của bạn từ **Truy vấn** thành **eCommerceContacts**.</span><span class="sxs-lookup"><span data-stu-id="1e932-124">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="1e932-125">Lưu nguồn dữ liệu.</span><span class="sxs-lookup"><span data-stu-id="1e932-125">Save the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="1e932-126">Nhập dữ liệu khách hàng từ lược đồ khách hàng thân thiết</span><span class="sxs-lookup"><span data-stu-id="1e932-126">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="1e932-127">Tạo nguồn dữ liệu có tên **LoyaltyScheme**, chọn tùy chọn nhập và chọn trình kết nối **Văn bản/CSV**.</span><span class="sxs-lookup"><span data-stu-id="1e932-127">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="1e932-128">Nhập URL cho các liên hệ Thương mại điện tử https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="1e932-128">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="1e932-129">Trong khi chỉnh sửa dữ liệu, hãy chọn **Chuyển đổi** và sau đó **Sử dụng hàng đầu tiên làm tiêu đề**.</span><span class="sxs-lookup"><span data-stu-id="1e932-129">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="1e932-130">Cập nhật kiểu dữ liệu cho các cột được liệt kê bên dưới:</span><span class="sxs-lookup"><span data-stu-id="1e932-130">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="1e932-131">**DateOfBirth**: Ngày</span><span class="sxs-lookup"><span data-stu-id="1e932-131">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="1e932-132">**RewardsPoints**: Số nguyên</span><span class="sxs-lookup"><span data-stu-id="1e932-132">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="1e932-133">**CreatedOn**: Ngày/Giờ</span><span class="sxs-lookup"><span data-stu-id="1e932-133">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="1e932-134">Trong trường "Tên" ở ngăn bên phải, hãy đổi tên nguồn dữ liệu của bạn từ **Truy vấn** thành **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="1e932-134">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="1e932-135">Lưu nguồn dữ liệu.</span><span class="sxs-lookup"><span data-stu-id="1e932-135">Save the data source.</span></span>

### <a name="ingest-subscription-information"></a><span data-ttu-id="1e932-136">Nhập thông tin đăng ký</span><span class="sxs-lookup"><span data-stu-id="1e932-136">Ingest subscription information</span></span>

1. <span data-ttu-id="1e932-137">Tạo nguồn dữ liệu có tên **SubscriptionHistory**, chọn tùy chọn nhập và chọn trình kết nối **Văn bản/CSV**.</span><span class="sxs-lookup"><span data-stu-id="1e932-137">Create a data source named **SubscriptionHistory**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="1e932-138">Nhập URL cho các liên hệ Thương mại điện tử https://aka.ms/ciadchurnsubscriptionhistory.</span><span class="sxs-lookup"><span data-stu-id="1e932-138">Enter the URL for eCommerce contacts https://aka.ms/ciadchurnsubscriptionhistory.</span></span>

1. <span data-ttu-id="1e932-139">Trong khi chỉnh sửa dữ liệu, hãy chọn **Chuyển đổi** và sau đó **Sử dụng hàng đầu tiên làm tiêu đề**.</span><span class="sxs-lookup"><span data-stu-id="1e932-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="1e932-140">Cập nhật kiểu dữ liệu cho các cột được liệt kê bên dưới:</span><span class="sxs-lookup"><span data-stu-id="1e932-140">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="1e932-141">**SubscriptioID**: Số nguyên</span><span class="sxs-lookup"><span data-stu-id="1e932-141">**SubscriptioID**: Whole Number</span></span>
   - <span data-ttu-id="1e932-142">**SubscriptionAmount**: Đơn vị tiền tệ</span><span class="sxs-lookup"><span data-stu-id="1e932-142">**SubscriptionAmount**: Currency</span></span>
   - <span data-ttu-id="1e932-143">**SubscriptionEndDate**: Ngày/Giờ</span><span class="sxs-lookup"><span data-stu-id="1e932-143">**SubscriptionEndDate**: Date/Time</span></span>
   - <span data-ttu-id="1e932-144">**SubscriptionStartDate**: Ngày/Giờ</span><span class="sxs-lookup"><span data-stu-id="1e932-144">**SubscriptionStartDate**: Date/Time</span></span>
   - <span data-ttu-id="1e932-145">**TransactionDate**: Ngày/Giờ</span><span class="sxs-lookup"><span data-stu-id="1e932-145">**TransactionDate**: Date/Time</span></span>
   - <span data-ttu-id="1e932-146">**IsRecurring**: True/False</span><span class="sxs-lookup"><span data-stu-id="1e932-146">**IsRecurring**: True/False</span></span>
   - <span data-ttu-id="1e932-147">**Is_auto_renew**: True/False</span><span class="sxs-lookup"><span data-stu-id="1e932-147">**Is_auto_renew**: True/False</span></span>
   - <span data-ttu-id="1e932-148">**RecurringFrequencyInMonths**: Số nguyên</span><span class="sxs-lookup"><span data-stu-id="1e932-148">**RecurringFrequencyInMonths**: Whole Number</span></span>

1. <span data-ttu-id="1e932-149">Trong trường "Tên" ở ngăn bên phải, hãy đổi tên nguồn dữ liệu của bạn từ **Truy vấn** thành **SubscriptionHistory**.</span><span class="sxs-lookup"><span data-stu-id="1e932-149">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **SubscriptionHistory**.</span></span>

1. <span data-ttu-id="1e932-150">Lưu nguồn dữ liệu.</span><span class="sxs-lookup"><span data-stu-id="1e932-150">Save the data source.</span></span>

### <a name="ingest-customer-data-from-website-reviews"></a><span data-ttu-id="1e932-151">Nhập dữ liệu khách hàng từ các bài đánh giá trang web</span><span class="sxs-lookup"><span data-stu-id="1e932-151">Ingest customer data from website reviews</span></span>

1. <span data-ttu-id="1e932-152">Tạo nguồn dữ liệu có tên **Trang web**, chọn tùy chọn nhập và chọn trình kết nối **Văn bản/CSV**.</span><span class="sxs-lookup"><span data-stu-id="1e932-152">Create a data source named **Website**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="1e932-153">Nhập URL cho các liên hệ Thương mại điện tử https://aka.ms/ciadclasswebsite.</span><span class="sxs-lookup"><span data-stu-id="1e932-153">Enter the URL for eCommerce contacts https://aka.ms/ciadclasswebsite.</span></span>

1. <span data-ttu-id="1e932-154">Trong khi chỉnh sửa dữ liệu, hãy chọn **Chuyển đổi** và sau đó **Sử dụng hàng đầu tiên làm tiêu đề**.</span><span class="sxs-lookup"><span data-stu-id="1e932-154">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="1e932-155">Cập nhật kiểu dữ liệu cho các cột được liệt kê bên dưới:</span><span class="sxs-lookup"><span data-stu-id="1e932-155">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="1e932-156">**ReviewRating**: Số nguyên</span><span class="sxs-lookup"><span data-stu-id="1e932-156">**ReviewRating**: Whole Number</span></span>
   - <span data-ttu-id="1e932-157">**ReviewDate**: Ngày</span><span class="sxs-lookup"><span data-stu-id="1e932-157">**ReviewDate**: Date</span></span>

1. <span data-ttu-id="1e932-158">Trong trường "Tên" ở ngăn bên phải, hãy đổi tên nguồn dữ liệu của bạn từ **Truy vấn** thành **webReviews**.</span><span class="sxs-lookup"><span data-stu-id="1e932-158">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **webReviews**.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="1e932-159">Nhiệm vụ 2 - Hợp nhất dữ liệu</span><span class="sxs-lookup"><span data-stu-id="1e932-159">Task 2 - Data unification</span></span>

<span data-ttu-id="1e932-160">Sau khi nhập dữ liệu, bây giờ chúng ta bắt đầu quy trình **Ánh xạ, So khớp, Hợp nhất** để tạo hồ sơ khách hàng hợp nhất.</span><span class="sxs-lookup"><span data-stu-id="1e932-160">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="1e932-161">Để biết thêm thông tin, hãy xem [Hợp nhất dữ liệu](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="1e932-161">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="1e932-162">Bản đồ</span><span class="sxs-lookup"><span data-stu-id="1e932-162">Map</span></span>

1. <span data-ttu-id="1e932-163">Sau khi nhập dữ liệu, hãy ánh xạ các địa chỉ liên hệ từ dữ liệu Thương mại điện tử và Mức độ trung thành thành các loại dữ liệu phổ biến.</span><span class="sxs-lookup"><span data-stu-id="1e932-163">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="1e932-164">Chuyển đến **Dữ liệu** > **Hợp nhất** > **Ánh xạ**.</span><span class="sxs-lookup"><span data-stu-id="1e932-164">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="1e932-165">Chọn các thực thể đại diện cho hồ sơ khách hàng – **eCommerceContacts** và **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="1e932-165">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="hợp nhất nguồn dữ liệu thương mại điện tử và khách hàng thân thiết.":::

1. <span data-ttu-id="1e932-167">Chọn **ContactId** làm khóa chính cho **eCommerceContacts** và **LoyaltyID** làm khóa chính cho **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="1e932-167">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="Hợp nhất LoyaltyId làm khóa chính.":::

### <a name="match"></a><span data-ttu-id="1e932-169">So khớp</span><span class="sxs-lookup"><span data-stu-id="1e932-169">Match</span></span>

1. <span data-ttu-id="1e932-170">Đi đến tab **So khớp** và chọn **Đặt thứ tự**.</span><span class="sxs-lookup"><span data-stu-id="1e932-170">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="1e932-171">Trong danh sách thả xuống **Chính**, chọn **eCommerceContacts: eCommerce** là nguồn chính và bao gồm tất cả các bản ghi.</span><span class="sxs-lookup"><span data-stu-id="1e932-171">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="1e932-172">Trong danh sách thả xuống **Thực thể 2**, chọn **loyCustomers : LoyaltyScheme** và bao gồm tất cả các bản ghi.</span><span class="sxs-lookup"><span data-stu-id="1e932-172">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   :::image type="content" source="media/unify-match-order.PNG" alt-text="Hợp nhất so khớp thương mại điện tử và khách hàng thân thiết.":::

1. <span data-ttu-id="1e932-174">Chọn **Tạo quy tắc mới**</span><span class="sxs-lookup"><span data-stu-id="1e932-174">Select **Create a new rule**</span></span>

1. <span data-ttu-id="1e932-175">Thêm điều kiện đầu tiên của bạn bằng FullName.</span><span class="sxs-lookup"><span data-stu-id="1e932-175">Add your first condition using FullName.</span></span>

   * <span data-ttu-id="1e932-176">Đối với eCommerceContacts, hãy chọn **FullName** trong danh sách thả xuống.</span><span class="sxs-lookup"><span data-stu-id="1e932-176">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="1e932-177">Đối với loyCustomers, hãy chọn **FullName** trong danh sách thả xuống.</span><span class="sxs-lookup"><span data-stu-id="1e932-177">For loyCustomers select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="1e932-178">Chọn danh sách thả xuống **Chuẩn hóa** và chọn **Loại (Điện thoại, Tên, Địa chỉ, ...)**.</span><span class="sxs-lookup"><span data-stu-id="1e932-178">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   * <span data-ttu-id="1e932-179">Đặt **Mức độ chính xác**: **Cơ bản** và **Giá trị**: **Cao**.</span><span class="sxs-lookup"><span data-stu-id="1e932-179">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="1e932-180">Nhập tên **FullName, Email** cho quy tắc mới.</span><span class="sxs-lookup"><span data-stu-id="1e932-180">Enter the name **FullName, Email** for the new rule.</span></span>

   * <span data-ttu-id="1e932-181">Thêm điều kiện thứ hai cho địa chỉ email bằng cách chọn **Thêm điều kiện**</span><span class="sxs-lookup"><span data-stu-id="1e932-181">Add a second condition for email address by selecting **Add Condition**</span></span>
   * <span data-ttu-id="1e932-182">Đối với thực thể eCommerceContacts, hãy chọn **Email** trong danh sách thả xuống.</span><span class="sxs-lookup"><span data-stu-id="1e932-182">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   * <span data-ttu-id="1e932-183">Đối với thực thể loyCustomers, hãy chọn **Email** trong danh sách thả xuống.</span><span class="sxs-lookup"><span data-stu-id="1e932-183">For entity loyCustomers, choose **EMail** in the drop-down.</span></span> 
   * <span data-ttu-id="1e932-184">Để trống trường Chuẩn hóa.</span><span class="sxs-lookup"><span data-stu-id="1e932-184">Leave Normalize blank.</span></span> 
   * <span data-ttu-id="1e932-185">Đặt **Mức độ chính xác**: **Cơ bản** và **Giá trị**: **Cao**.</span><span class="sxs-lookup"><span data-stu-id="1e932-185">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="Hợp nhất quy tắc so khớp cho tên và email.":::

7. <span data-ttu-id="1e932-187">Chọn **Lưu** và **Chạy**.</span><span class="sxs-lookup"><span data-stu-id="1e932-187">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="1e932-188">Hợp nhất</span><span class="sxs-lookup"><span data-stu-id="1e932-188">Merge</span></span>

1. <span data-ttu-id="1e932-189">Đi đến tab **Hợp nhất**.</span><span class="sxs-lookup"><span data-stu-id="1e932-189">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="1e932-190">Trên thực thể **ContactId** cho **loyCustomers**, thay đổi tên hiển thị thành **ContactIdLOYALTY** để phân biệt nó với các ID khác đã nhập.</span><span class="sxs-lookup"><span data-stu-id="1e932-190">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="đổi tên contactid từ id khách hàng thân thiết.":::

1. <span data-ttu-id="1e932-192">Chọn **Lưu** và **Chạy** để bắt đầu quy trình Hợp nhất.</span><span class="sxs-lookup"><span data-stu-id="1e932-192">Select **Save** and **Run** to start the Merge Process.</span></span>


## <a name="task-3---configure-the-subscription-churn-prediction"></a><span data-ttu-id="1e932-193">Nhiệm vụ 3 - Định cấu hình dự đoán rời bỏ đăng ký</span><span class="sxs-lookup"><span data-stu-id="1e932-193">Task 3 - Configure the subscription churn prediction</span></span>

<span data-ttu-id="1e932-194">Với hồ sơ khách hàng hợp nhất đã có, giờ đây chúng tôi có thể chạy dự đoán rời bỏ đăng ký.</span><span class="sxs-lookup"><span data-stu-id="1e932-194">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span> <span data-ttu-id="1e932-195">Để biết các bước chi tiết, hãy xem bài viết [Dự đoán rời bỏ đăng ký (bản xem trước)](predict-subscription-churn.md).</span><span class="sxs-lookup"><span data-stu-id="1e932-195">For detailed steps, see the [Subscription churn prediction (preview)](predict-subscription-churn.md) article.</span></span> 

1. <span data-ttu-id="1e932-196">Đi đến **Thông tin** > **Khám phá** và chọn để sử dụng **Mô hình khách hàng rời đi**.</span><span class="sxs-lookup"><span data-stu-id="1e932-196">Go to **Intelligence** > **Discover** and select to use the **Customer churn model**.</span></span>

1. <span data-ttu-id="1e932-197">Chọn tùy chọn **Đăng ký** và chọn **Bắt đầu**.</span><span class="sxs-lookup"><span data-stu-id="1e932-197">Select the **Subscription** option and select **Get started**.</span></span>

1. <span data-ttu-id="1e932-198">Đặt tên cho mô hình **Dự đoán rời bỏ đăng ký OOB** và thực thể đầu ra **OOBSubscriptionChurnPrediction**.</span><span class="sxs-lookup"><span data-stu-id="1e932-198">Name the model **OOB Subscription Churn Prediction** and the output entity **OOBSubscriptionChurnPrediction**.</span></span>

1. <span data-ttu-id="1e932-199">Xác định hai điều kiện cho mô hình khách hàng rời đi:</span><span class="sxs-lookup"><span data-stu-id="1e932-199">Define two conditions for the churn model:</span></span>

   * <span data-ttu-id="1e932-200">**Số ngày kể từ khi đăng ký kết thúc**: **ít nhất 60** ngày.</span><span class="sxs-lookup"><span data-stu-id="1e932-200">**Days since subscription ended**: **at least 60** days.</span></span> <span data-ttu-id="1e932-201">Nếu khách hàng không gia hạn gói đăng ký của họ trong khoảng thời gian này sau khi gói đăng ký kết thúc, thì họ sẽ được xem là đã rời đi.</span><span class="sxs-lookup"><span data-stu-id="1e932-201">If a customer doesn't renew the subscription in this period after their subscription ended, they are considered churned.</span></span> 

   * <span data-ttu-id="1e932-202">**Định nghĩa về tỷ lệ rời đi**: **tối thiểu 93** ngày.</span><span class="sxs-lookup"><span data-stu-id="1e932-202">**Churn definition**: **at least 93** days.</span></span> <span data-ttu-id="1e932-203">Khoảng thời gian mà mô hình dự đoán những khách hàng có thể rời đi.</span><span class="sxs-lookup"><span data-stu-id="1e932-203">The duration the model predict which customers might churn.</span></span> <span data-ttu-id="1e932-204">Bạn càng dự đoán xa thì kết quả càng thiếu chính xác.</span><span class="sxs-lookup"><span data-stu-id="1e932-204">The further in the future you look, the less precise the results.</span></span>

     :::image type="content" source="media/model-subs-levers.PNG" alt-text="Chọn mô hình thúc đẩy khoảng thời gian dự đoán và định nghĩa về tỷ lệ rời đi.":::

1. <span data-ttu-id="1e932-206">Chọn **Thêm dữ liệu bắt buộc** và chọn **Thêm dữ liệu** cho lịch sử đăng ký.</span><span class="sxs-lookup"><span data-stu-id="1e932-206">Select **Add required data** and select **Add data** for subscription history.</span></span>

1. <span data-ttu-id="1e932-207">Thêm thực thể **Đăng ký: SubscriptionHistory** và ánh xạ các trường từ thương mại điện tử đến các trường tương ứng theo yêu cầu của mô hình.</span><span class="sxs-lookup"><span data-stu-id="1e932-207">Add the **Subscription : SubscriptionHistory** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="1e932-208">Tham gia thực thể **Đăng ký: SubscriptionHistory** với **eCommerceContacts: eCommerce**, đặt tên cho mối quan hệ **eCommerceSubscription**.</span><span class="sxs-lookup"><span data-stu-id="1e932-208">Join the **Subscription : SubscriptionHistory** entity with **eCommerceContacts : eCommerce**, name the relationship **eCommerceSubscription**.</span></span>

   :::image type="content" source="media/model-subscription-join.PNG" alt-text="Tham gia các thực thể thương mại điện tử.":::

1. <span data-ttu-id="1e932-210">Trong Hoạt động của khách hàng, thêm thực thể **webReviews: Website** và ánh xạ các trường từ webReviews với các trường tương ứng được yêu cầu theo mô hình.</span><span class="sxs-lookup"><span data-stu-id="1e932-210">Under Customer Activities, add the **webReviews : Website** entity and map the fields from webReviews to the corresponding fields required by the model.</span></span> 
   - <span data-ttu-id="1e932-211">Khóa chính: ReviewId</span><span class="sxs-lookup"><span data-stu-id="1e932-211">Primary key: ReviewId</span></span>
   - <span data-ttu-id="1e932-212">Dấu thời gian: ReviewDate</span><span class="sxs-lookup"><span data-stu-id="1e932-212">Timestamp: ReviewDate</span></span>
   - <span data-ttu-id="1e932-213">Sự kiện: ReviewRating</span><span class="sxs-lookup"><span data-stu-id="1e932-213">Event: ReviewRating</span></span>

1. <span data-ttu-id="1e932-214">Định cấu hình một hoạt động để đánh giá trang web.</span><span class="sxs-lookup"><span data-stu-id="1e932-214">Configure an activity for website reviews.</span></span> <span data-ttu-id="1e932-215">Chọn hoạt động **Đánh giá** và tham gia thực thể **webReviews: Website** với **eCommerceContacts : eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="1e932-215">Select the activity **Review** and join the **webReviews : Website** entity with **eCommerceContacts : eCommerce**.</span></span>

1. <span data-ttu-id="1e932-216">Chọn **Tiếp theo** để đặt lịch trình mô hình.</span><span class="sxs-lookup"><span data-stu-id="1e932-216">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="1e932-217">Mô hình cần đào tạo thường xuyên để học các mẫu mới khi có dữ liệu mới được nhập vào.</span><span class="sxs-lookup"><span data-stu-id="1e932-217">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="1e932-218">Đối với ví dụ này, hãy chọn **Hàng tháng**.</span><span class="sxs-lookup"><span data-stu-id="1e932-218">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="1e932-219">Sau khi xem xét tất cả các chi tiết, hãy chọn **Lưu và chạy**.</span><span class="sxs-lookup"><span data-stu-id="1e932-219">After reviewing all the details, select **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="1e932-220">Nhiệm vụ 4 - Xem xét kết quả và giải thích mô hình</span><span class="sxs-lookup"><span data-stu-id="1e932-220">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="1e932-221">Để mô hình hoàn thành việc đào tạo và chấm điểm dữ liệu.</span><span class="sxs-lookup"><span data-stu-id="1e932-221">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="1e932-222">Bây giờ bạn có thể xem lại giải thích mô hình rời bỏ đăng ký.</span><span class="sxs-lookup"><span data-stu-id="1e932-222">You can now review the subscription churn model explanations.</span></span> <span data-ttu-id="1e932-223">Để biết thêm thông tin, hãy xem [Xem lại dự đoán trạng thái và kết quả](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="1e932-223">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a><span data-ttu-id="1e932-224">Nhiệm vụ 5 - Tạo một phân khúc khách hàng có nguy cơ rời bỏ cao</span><span class="sxs-lookup"><span data-stu-id="1e932-224">Task 5 - Create a segment of high churn-risk customers</span></span>

<span data-ttu-id="1e932-225">Việc chạy mô hình sản xuất sẽ tạo ra một thực thể mới mà bạn có thể thấy trong **Dữ liệu** > **Thực thể**.</span><span class="sxs-lookup"><span data-stu-id="1e932-225">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>   

<span data-ttu-id="1e932-226">Bạn có thể tạo một phân khúc mới dựa trên thực thể được tạo bởi mô hình.</span><span class="sxs-lookup"><span data-stu-id="1e932-226">You can create a new segment based on the entity created by the model.</span></span>

1.  <span data-ttu-id="1e932-227">Đi đến **Phân khúc**.</span><span class="sxs-lookup"><span data-stu-id="1e932-227">Go to **Segments**.</span></span> <span data-ttu-id="1e932-228">Chọn **Mới** và chọn **Tạo từ** > **Thông tin**.</span><span class="sxs-lookup"><span data-stu-id="1e932-228">Select **New** and choose **Create from** > **Intelligence**.</span></span> 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Tạo một phân khúc với đầu ra mô hình.":::

1. <span data-ttu-id="1e932-230">Chọn điểm cuối **OOBSubscriptionChurnPrediction** và xác định phân khúc:</span><span class="sxs-lookup"><span data-stu-id="1e932-230">Select the **OOBSubscriptionChurnPrediction** endpoint and define the segment:</span></span> 
   - <span data-ttu-id="1e932-231">Trường: ChurnScore</span><span class="sxs-lookup"><span data-stu-id="1e932-231">Field: ChurnScore</span></span>
   - <span data-ttu-id="1e932-232">Toán tử: lớn hơn</span><span class="sxs-lookup"><span data-stu-id="1e932-232">Operator: greater than</span></span>
   - <span data-ttu-id="1e932-233">Giá trị: 0.6</span><span class="sxs-lookup"><span data-stu-id="1e932-233">Value: 0.6</span></span>
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Thiết lập phân khúc rời bỏ đăng ký.":::

<span data-ttu-id="1e932-235">Giờ đây, bạn có một phân khúc được cập nhật động để xác định những khách hàng có nguy cơ rời bỏ cao cho doanh nghiệp đăng ký này.</span><span class="sxs-lookup"><span data-stu-id="1e932-235">You now have a segment that is dynamically updated which identifies high churn-risk customers for this subscription business.</span></span>

<span data-ttu-id="1e932-236">Để biết thêm thông tin, hãy xem [Tạo và quản lý phân khúc](segments.md).</span><span class="sxs-lookup"><span data-stu-id="1e932-236">For more information, see [Create and manage segments](segments.md).</span></span>
