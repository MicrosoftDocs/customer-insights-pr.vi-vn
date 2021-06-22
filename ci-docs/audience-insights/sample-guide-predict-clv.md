---
title: Hướng dẫn mẫu về dự đoán giá trị trọn đời của khách hàng
description: Sử dụng hướng dẫn mẫu này để thử mô hình dự đoán giá trị trọn đời của khách hàng.
ms.date: 05/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: 73d294a285b4ad706bec7fe925c1daa0b839ddd6
ms.sourcegitcommit: 7b6189e47ed1f87e7ce35d40e4cf7a6730f31ef2
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 06/01/2021
ms.locfileid: "6129971"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a><span data-ttu-id="8cdd7-103">Hướng dẫn mẫu về dự đoán Giá trị trọn đời của khách hàng (CLV)</span><span class="sxs-lookup"><span data-stu-id="8cdd7-103">Customer lifetime value (CLV) prediction sample guide</span></span>

<span data-ttu-id="8cdd7-104">Hướng dẫn này sẽ giải thích cho bạn một ví dụ chi tiết về dự đoán Giá trị trọn đời của khách hàng (CLV) trong Customer Insights bằng cách sử dụng dữ liệu mẫu.</span><span class="sxs-lookup"><span data-stu-id="8cdd7-104">This guide will walk you through an end to end example of Customer lifetime value (CLV) prediction in Customer Insights using sample data.</span></span>

## <a name="scenario"></a><span data-ttu-id="8cdd7-105">Kịch bản</span><span class="sxs-lookup"><span data-stu-id="8cdd7-105">Scenario</span></span>

<span data-ttu-id="8cdd7-106">Contoso là công ty sản xuất cà phê và máy pha cà phê chất lượng cao.</span><span class="sxs-lookup"><span data-stu-id="8cdd7-106">Contoso is a company that produces high-quality coffee and coffee machines.</span></span> <span data-ttu-id="8cdd7-107">Họ bán sản phẩm thông qua trang web Contoso Coffee.</span><span class="sxs-lookup"><span data-stu-id="8cdd7-107">They sell the products through their Contoso Coffee website.</span></span> <span data-ttu-id="8cdd7-108">Công ty muốn tìm hiểu giá trị (doanh thu) mà khách hàng của họ có thể tạo ra trong 12 tháng tới.</span><span class="sxs-lookup"><span data-stu-id="8cdd7-108">The company wants to understand the value (revenue) that their customers can generate in the next 12 months.</span></span> <span data-ttu-id="8cdd7-109">Nếu biết được giá trị kỳ vọng của khách hàng trong 12 tháng tới, họ có thể hướng nỗ lực tiếp thị đến những khách hàng có giá trị cao.</span><span class="sxs-lookup"><span data-stu-id="8cdd7-109">Knowing the expected value of their customers in the next 12 months will help them steer their marketing efforts on high value customers.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8cdd7-110">Điều kiện tiên quyết</span><span class="sxs-lookup"><span data-stu-id="8cdd7-110">Prerequisites</span></span>

- <span data-ttu-id="8cdd7-111">Ít nhất là [quyền Cộng tác viên](permissions.md) trong thông tin chuyên sâu về đối tượng.</span><span class="sxs-lookup"><span data-stu-id="8cdd7-111">At least [Contributor permissions](permissions.md) in audience insights.</span></span>
- <span data-ttu-id="8cdd7-112">Chúng tôi khuyên bạn nên thực hiện các bước sau [trong một môi trường mới](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="8cdd7-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="8cdd7-113">Nhiệm vụ 1 - Nhập dữ liệu</span><span class="sxs-lookup"><span data-stu-id="8cdd7-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="8cdd7-114">Xem lại các bài viết về cách [nhập dữ liệu](data-sources.md) và [nhập nguồn dữ liệu bằng trình kết nối Power Query](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="8cdd7-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md).</span></span> <span data-ttu-id="8cdd7-115">Thông tin sau đây giả định rằng bạn đã quen với việc nhập dữ liệu nói chung.</span><span class="sxs-lookup"><span data-stu-id="8cdd7-115">The following information assumes you familiarized with ingesting data in general.</span></span>

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="8cdd7-116">Nhập dữ liệu khách hàng từ nền tảng Thương mại điện tử</span><span class="sxs-lookup"><span data-stu-id="8cdd7-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="8cdd7-117">Tạo nguồn dữ liệu có tên **Thương mại điện tử**, chọn tùy chọn nhập và chọn trình kết nối **Văn bản/CSV**.</span><span class="sxs-lookup"><span data-stu-id="8cdd7-117">Create a data source named  **eCommerce** , choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="8cdd7-118">Nhập URL cho các liên hệ Thương mại điện tử [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).</span><span class="sxs-lookup"><span data-stu-id="8cdd7-118">Enter the URL for eCommerce contacts [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).</span></span>

1. <span data-ttu-id="8cdd7-119">Trong khi chỉnh sửa dữ liệu, hãy chọn **Chuyển đổi** rồi chọn **Dùng hàng đầu tiên làm tiêu đề**.</span><span class="sxs-lookup"><span data-stu-id="8cdd7-119">While editing the data, select  **Transform**  and then  **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="8cdd7-120">Cập nhật kiểu dữ liệu cho các cột được liệt kê bên dưới:</span><span class="sxs-lookup"><span data-stu-id="8cdd7-120">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="8cdd7-121">**DateOfBirth**: Ngày</span><span class="sxs-lookup"><span data-stu-id="8cdd7-121">**DateOfBirth** : Date</span></span>
   - <span data-ttu-id="8cdd7-122">**CreatedOn**: Ngày/Giờ/Vùng</span><span class="sxs-lookup"><span data-stu-id="8cdd7-122">**CreatedOn** : Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Chuyển đổi ngày sinh thành ngày.":::

1. <span data-ttu-id="8cdd7-124">Trong trường "Tên" ở ngăn bên phải, hãy đổi tên nguồn dữ liệu của bạn từ **Truy vấn** thành **eCommerceContacts**.</span><span class="sxs-lookup"><span data-stu-id="8cdd7-124">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="8cdd7-125">**Lưu** nguồn dữ liệu.</span><span class="sxs-lookup"><span data-stu-id="8cdd7-125">**Save** the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="8cdd7-126">Nhập dữ liệu mua hàng trực tuyến</span><span class="sxs-lookup"><span data-stu-id="8cdd7-126">Ingest online purchase data</span></span>

1. <span data-ttu-id="8cdd7-127">Thêm một tập hợp dữ liệu khác vào cùng một nguồn dữ liệu **Thương mại điện tử**.</span><span class="sxs-lookup"><span data-stu-id="8cdd7-127">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="8cdd7-128">Chọn lại trình kết nối **Văn bản/CSV**.</span><span class="sxs-lookup"><span data-stu-id="8cdd7-128">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="8cdd7-129">Nhập URL cho dữ liệu **Mua hàng trực tuyến** https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="8cdd7-129">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="8cdd7-130">Trong khi chỉnh sửa dữ liệu, hãy chọn **Chuyển đổi** rồi chọn **Dùng hàng đầu tiên làm tiêu đề**.</span><span class="sxs-lookup"><span data-stu-id="8cdd7-130">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="8cdd7-131">Cập nhật kiểu dữ liệu cho các cột được liệt kê bên dưới:</span><span class="sxs-lookup"><span data-stu-id="8cdd7-131">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="8cdd7-132">**PurchasedOn**: Ngày/Giờ</span><span class="sxs-lookup"><span data-stu-id="8cdd7-132">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="8cdd7-133">**TotalPrice**: Tiền tệ</span><span class="sxs-lookup"><span data-stu-id="8cdd7-133">**TotalPrice**: Currency</span></span>

1. <span data-ttu-id="8cdd7-134">Trong trường **Tên** ở ngăn bên, hãy đổi tên nguồn dữ liệu của bạn từ **Truy vấn** thành **eCommercePurchases**.</span><span class="sxs-lookup"><span data-stu-id="8cdd7-134">In the **Name** field on the side pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="8cdd7-135">**Lưu** nguồn dữ liệu.</span><span class="sxs-lookup"><span data-stu-id="8cdd7-135">**Save** the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="8cdd7-136">Nhập dữ liệu khách hàng từ lược đồ khách hàng thân thiết</span><span class="sxs-lookup"><span data-stu-id="8cdd7-136">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="8cdd7-137">Tạo nguồn dữ liệu có tên **LoyaltyScheme**, chọn tùy chọn nhập và chọn trình kết nối **Văn bản/CSV**.</span><span class="sxs-lookup"><span data-stu-id="8cdd7-137">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="8cdd7-138">Nhập URL cho các liên hệ Thương mại điện tử https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="8cdd7-138">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="8cdd7-139">Trong khi chỉnh sửa dữ liệu, hãy chọn **Chuyển đổi** rồi chọn **Dùng hàng đầu tiên làm tiêu đề**.</span><span class="sxs-lookup"><span data-stu-id="8cdd7-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="8cdd7-140">Cập nhật kiểu dữ liệu cho các cột được liệt kê bên dưới:</span><span class="sxs-lookup"><span data-stu-id="8cdd7-140">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="8cdd7-141">**DateOfBirth**: Ngày</span><span class="sxs-lookup"><span data-stu-id="8cdd7-141">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="8cdd7-142">**RewardsPoints**: Số nguyên</span><span class="sxs-lookup"><span data-stu-id="8cdd7-142">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="8cdd7-143">**CreatedOn**: Ngày/Giờ</span><span class="sxs-lookup"><span data-stu-id="8cdd7-143">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="8cdd7-144">Trong trường **Tên** ở ngăn bên phải, hãy đổi tên nguồn dữ liệu của bạn từ **Truy vấn** thành **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="8cdd7-144">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="8cdd7-145">**Lưu** nguồn dữ liệu.</span><span class="sxs-lookup"><span data-stu-id="8cdd7-145">**Save** the data source.</span></span>

### <a name="ingest-customer-data-from-website-reviews"></a><span data-ttu-id="8cdd7-146">Nhập dữ liệu khách hàng từ các bài đánh giá trang web</span><span class="sxs-lookup"><span data-stu-id="8cdd7-146">Ingest customer data from website reviews</span></span>

1. <span data-ttu-id="8cdd7-147">Tạo nguồn dữ liệu có tên **Trang web**, chọn tùy chọn nhập và chọn trình kết nối **Văn bản/CSV**.</span><span class="sxs-lookup"><span data-stu-id="8cdd7-147">Create a data source named **Website**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="8cdd7-148">Nhập URL cho các liên hệ Thương mại điện tử https://aka.ms/CI-ILT/WebReviews.</span><span class="sxs-lookup"><span data-stu-id="8cdd7-148">Enter the URL for eCommerce contacts https://aka.ms/CI-ILT/WebReviews.</span></span>

1. <span data-ttu-id="8cdd7-149">Trong khi chỉnh sửa dữ liệu, hãy chọn **Chuyển đổi** rồi chọn **Dùng hàng đầu tiên làm tiêu đề**.</span><span class="sxs-lookup"><span data-stu-id="8cdd7-149">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="8cdd7-150">Cập nhật kiểu dữ liệu cho các cột được liệt kê bên dưới:</span><span class="sxs-lookup"><span data-stu-id="8cdd7-150">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="8cdd7-151">**ReviewRating**: Số thập phân</span><span class="sxs-lookup"><span data-stu-id="8cdd7-151">**ReviewRating**: Decimal number</span></span>
   - <span data-ttu-id="8cdd7-152">**ReviewDate**: Ngày</span><span class="sxs-lookup"><span data-stu-id="8cdd7-152">**ReviewDate**: Date</span></span>

1. <span data-ttu-id="8cdd7-153">Trong trường "Tên" ở ngăn bên phải, hãy đổi tên nguồn dữ liệu của bạn từ **Truy vấn** thành **Đánh giá**.</span><span class="sxs-lookup"><span data-stu-id="8cdd7-153">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **Reviews**.</span></span>

1. <span data-ttu-id="8cdd7-154">**Lưu** nguồn dữ liệu.</span><span class="sxs-lookup"><span data-stu-id="8cdd7-154">**Save** the data source.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="8cdd7-155">Nhiệm vụ 2 - Hợp nhất dữ liệu</span><span class="sxs-lookup"><span data-stu-id="8cdd7-155">Task 2 - Data unification</span></span>

<span data-ttu-id="8cdd7-156">Sau khi nhập dữ liệu, bây giờ, chúng ta sẽ bắt đầu quá trình hợp nhất dữ liệu để tạo hồ sơ khách hàng hợp nhất.</span><span class="sxs-lookup"><span data-stu-id="8cdd7-156">After ingesting the data, we now begin the data unification process to create a unified customer profile.</span></span> <span data-ttu-id="8cdd7-157">Để biết thêm thông tin, hãy xem [Hợp nhất dữ liệu](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="8cdd7-157">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="8cdd7-158">Bản đồ</span><span class="sxs-lookup"><span data-stu-id="8cdd7-158">Map</span></span>

1. <span data-ttu-id="8cdd7-159">Sau khi nhập dữ liệu, hãy ánh xạ các địa chỉ liên hệ từ dữ liệu Thương mại điện tử và Mức độ trung thành thành các loại dữ liệu phổ biến.</span><span class="sxs-lookup"><span data-stu-id="8cdd7-159">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="8cdd7-160">Chuyển đến **Dữ liệu** > **Hợp nhất** > **Ánh xạ**.</span><span class="sxs-lookup"><span data-stu-id="8cdd7-160">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="8cdd7-161">Chọn các thực thể đại diện cho hồ sơ khách hàng – **eCommerceContacts** và **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="8cdd7-161">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> <span data-ttu-id="8cdd7-162">Sau đó, chọn **Áp dụng**.</span><span class="sxs-lookup"><span data-stu-id="8cdd7-162">Then, select **Apply**.</span></span>

   ![hợp nhất nguồn dữ liệu thương mại điện tử và khách hàng thân thiết.](media/unify-ecommerce-loyalty.png)

1. <span data-ttu-id="8cdd7-164">Chọn **ContactId** làm khóa chính cho **eCommerceContacts** và **LoyaltyID** làm khóa chính cho **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="8cdd7-164">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   ![Hợp nhất LoyaltyId làm khóa chính.](media/unify-loyaltyid.png)

1. <span data-ttu-id="8cdd7-166">Chọn **Lưu**.</span><span class="sxs-lookup"><span data-stu-id="8cdd7-166">Select **Save**.</span></span>

### <a name="match"></a><span data-ttu-id="8cdd7-167">Kết quả khớp</span><span class="sxs-lookup"><span data-stu-id="8cdd7-167">Match</span></span>

1. <span data-ttu-id="8cdd7-168">Đi đến tab **So khớp** và chọn **Đặt thứ tự**.</span><span class="sxs-lookup"><span data-stu-id="8cdd7-168">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="8cdd7-169">Trong danh sách thả xuống **Chính**, chọn **eCommerceContacts: eCommerce** là nguồn chính và bao gồm tất cả các bản ghi.</span><span class="sxs-lookup"><span data-stu-id="8cdd7-169">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="8cdd7-170">Trong danh sách thả xuống **Thực thể 2**, chọn **loyCustomers : LoyaltyScheme** và bao gồm tất cả các bản ghi.</span><span class="sxs-lookup"><span data-stu-id="8cdd7-170">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   ![Hợp nhất so khớp thương mại điện tử và khách hàng thân thiết.](media/unify-match-order.png)

1. <span data-ttu-id="8cdd7-172">Chọn **Thêm quy tắc**</span><span class="sxs-lookup"><span data-stu-id="8cdd7-172">Select **Add rule**</span></span>

1. <span data-ttu-id="8cdd7-173">Thêm điều kiện đầu tiên của bạn bằng FullName.</span><span class="sxs-lookup"><span data-stu-id="8cdd7-173">Add your first condition using FullName.</span></span>

   - <span data-ttu-id="8cdd7-174">Đối với eCommerceContacts, hãy chọn **FullName** trong danh sách thả xuống.</span><span class="sxs-lookup"><span data-stu-id="8cdd7-174">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="8cdd7-175">Đối với loyCustomers, hãy chọn **FullName** trong danh sách thả xuống.</span><span class="sxs-lookup"><span data-stu-id="8cdd7-175">For loyCustomers select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="8cdd7-176">Chọn danh sách thả xuống **Chuẩn hóa** rồi chọn **Loại (Điện thoại, Tên, Địa chỉ, ...)**.</span><span class="sxs-lookup"><span data-stu-id="8cdd7-176">Select the **Normalize** drop-down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   - <span data-ttu-id="8cdd7-177">Đặt **Mức độ chính xác**: **Cơ bản** và **Giá trị**: **Cao**.</span><span class="sxs-lookup"><span data-stu-id="8cdd7-177">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="8cdd7-178">Nhập tên **FullName, Email** cho quy tắc mới.</span><span class="sxs-lookup"><span data-stu-id="8cdd7-178">Enter the name **FullName, Email** for the new rule.</span></span>

   - <span data-ttu-id="8cdd7-179">Thêm điều kiện thứ hai cho địa chỉ email bằng cách chọn **Thêm điều kiện**</span><span class="sxs-lookup"><span data-stu-id="8cdd7-179">Add a second condition for email address by selecting **Add Condition**</span></span>
   - <span data-ttu-id="8cdd7-180">Đối với thực thể eCommerceContacts, hãy chọn **Email** trong danh sách thả xuống.</span><span class="sxs-lookup"><span data-stu-id="8cdd7-180">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   - <span data-ttu-id="8cdd7-181">Đối với thực thể loyCustomers, hãy chọn **Email** trong danh sách thả xuống.</span><span class="sxs-lookup"><span data-stu-id="8cdd7-181">For entity loyCustomers, choose **EMail** in the drop-down.</span></span>
   - <span data-ttu-id="8cdd7-182">Để trống trường Chuẩn hóa.</span><span class="sxs-lookup"><span data-stu-id="8cdd7-182">Leave Normalize blank.</span></span>
   - <span data-ttu-id="8cdd7-183">Đặt **Mức độ chính xác**: **Cơ bản** và **Giá trị**: **Cao**.</span><span class="sxs-lookup"><span data-stu-id="8cdd7-183">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   ![Hợp nhất quy tắc so khớp cho tên và email.](media/unify-match-rule.png)

1. <span data-ttu-id="8cdd7-185">Chọn **Xong**.</span><span class="sxs-lookup"><span data-stu-id="8cdd7-185">Select **Done**.</span></span>

1. <span data-ttu-id="8cdd7-186">Chọn **Lưu** và **Chạy**.</span><span class="sxs-lookup"><span data-stu-id="8cdd7-186">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="8cdd7-187">Hợp nhất</span><span class="sxs-lookup"><span data-stu-id="8cdd7-187">Merge</span></span>

1. <span data-ttu-id="8cdd7-188">Đi đến tab **Hợp nhất**.</span><span class="sxs-lookup"><span data-stu-id="8cdd7-188">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="8cdd7-189">Trên thực thể **ContactId** cho **loyCustomers**, thay đổi tên hiển thị thành **ContactIdLOYALTY** để phân biệt nó với các ID khác đã nhập.</span><span class="sxs-lookup"><span data-stu-id="8cdd7-189">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   ![đổi tên contactid từ id khách hàng thân thiết.](media/unify-merge-contactid.png)

1. <span data-ttu-id="8cdd7-191">Chọn **Lưu** và **Chạy quy trình hợp nhất và xuôi dòng**.</span><span class="sxs-lookup"><span data-stu-id="8cdd7-191">Select **Save** and **Run merge and downstream processes**.</span></span>

## <a name="task-3---configure-customer-lifetime-value-prediction"></a><span data-ttu-id="8cdd7-192">Nhiệm vụ 3 - Đặt cấu hình dự đoán giá trị trọn đời của khách hàng</span><span class="sxs-lookup"><span data-stu-id="8cdd7-192">Task 3 - Configure customer lifetime value prediction</span></span>

<span data-ttu-id="8cdd7-193">Sau khi có hồ sơ khách hàng hợp nhất, bây giờ, chúng ta có thể chạy dự đoán giá trị trọn đời của khách hàng.</span><span class="sxs-lookup"><span data-stu-id="8cdd7-193">With the unified customer profiles in place, we can now run the customer lifetime value prediction.</span></span> <span data-ttu-id="8cdd7-194">Để biết các bước chi tiết, hãy xem bài viết [Dự đoán Giá trị trọn đời của khách hàng (xem trước)](predict-customer-lifetime-value.md).</span><span class="sxs-lookup"><span data-stu-id="8cdd7-194">For detailed steps, see [Customer Lifetime Value prediction (preview)](predict-customer-lifetime-value.md).</span></span>

1. <span data-ttu-id="8cdd7-195">Chuyển đến phần **Thông tin**  > **Dự đoán** rồi chọn **Mô hình giá trị trọn đời của khách hàng**.</span><span class="sxs-lookup"><span data-stu-id="8cdd7-195">Go to  **Intelligence**  > **Predictions**  and select the **Customer lifetime value model**.</span></span>

1. <span data-ttu-id="8cdd7-196">Xem qua thông tin ở ngăn bên rồi chọn **Bắt đầu**.</span><span class="sxs-lookup"><span data-stu-id="8cdd7-196">Go through the information in the side pane and select **Get started**.</span></span>

1. <span data-ttu-id="8cdd7-197">Đặt tên cho mô hình là **OOB eCommerce CLV Prediction** và thực thể đầu ra là **OOBeCommerceCLVPrediction**.</span><span class="sxs-lookup"><span data-stu-id="8cdd7-197">Name the model **OOB eCommerce CLV Prediction** and the output entity  **OOBeCommerceCLVPrediction**.</span></span>

1. <span data-ttu-id="8cdd7-198">Xác định các tùy chọn mô hình cho mô hình CLV:</span><span class="sxs-lookup"><span data-stu-id="8cdd7-198">Define model preferences for the CLV model:</span></span>
   - <span data-ttu-id="8cdd7-199">**Khoảng thời gian dự đoán**: **12 tháng hoặc 1 năm**.</span><span class="sxs-lookup"><span data-stu-id="8cdd7-199">**Prediction time period**: **12 months or 1 year**.</span></span> <span data-ttu-id="8cdd7-200">Tùy chọn thiết đặt này xác định khoảng thời gian trong tương lai để dự đoán giá trị trọn đời của khách hàng.</span><span class="sxs-lookup"><span data-stu-id="8cdd7-200">This setting defines how far into the future to predict customer lifetime value.</span></span>
   - <span data-ttu-id="8cdd7-201">**Khách hàng hiện hoạt**: Chỉ định những khách hàng hiện hoạt có ý nghĩa đối với doanh nghiệp của bạn.</span><span class="sxs-lookup"><span data-stu-id="8cdd7-201">**Active customers**: Specify what active customers mean for your business.</span></span> <span data-ttu-id="8cdd7-202">Đặt khung thời gian trong quá khứ mà khách hàng phải có ít nhất một giao dịch để được coi là hiện hoạt.</span><span class="sxs-lookup"><span data-stu-id="8cdd7-202">Set the historical time frame in which a customer must have had at least one transaction to be considered active.</span></span> <span data-ttu-id="8cdd7-203">Mô hình sẽ chỉ dự đoán CLV cho những khách hàng hiện hoạt.</span><span class="sxs-lookup"><span data-stu-id="8cdd7-203">The model will only predict CLV for active customers.</span></span> <span data-ttu-id="8cdd7-204">Bạn có thể chọn tùy chọn để mô hình tính toán khoảng thời gian dựa trên dữ liệu giao dịch trước đây hoặc cung cấp một khung thời gian cụ thể.</span><span class="sxs-lookup"><span data-stu-id="8cdd7-204">Choose between letting the model calculate the time period based on historical transaction data or provide a specific time frame.</span></span> <span data-ttu-id="8cdd7-205">Trong hướng dẫn mẫu này, chúng ta dùng tùy chọn mặc định là **để mô hình tính toán khoảng thời gian mua hàng**.</span><span class="sxs-lookup"><span data-stu-id="8cdd7-205">In this sample guide, we **let the model calculate purchase interval**, which is the default option.</span></span>
   - <span data-ttu-id="8cdd7-206">**Khách hàng có giá trị cao**: Xác định khách hàng có giá trị cao dưới dạng phân vị phần trăm của những khách hàng chi tiêu nhiều nhất.</span><span class="sxs-lookup"><span data-stu-id="8cdd7-206">**High value customers**: Define high value customers as a percentile of top-paying customers.</span></span> <span data-ttu-id="8cdd7-207">Mô hình sẽ dùng dữ liệu đầu vào này để đưa ra kết quả phù hợp với định nghĩa kinh doanh của bạn về khách hàng có giá trị cao.</span><span class="sxs-lookup"><span data-stu-id="8cdd7-207">The model uses this input to provide results that fit your business definition of high value customers.</span></span> <span data-ttu-id="8cdd7-208">Bạn có thể chọn để mô hình xác định khách hàng có giá trị cao.</span><span class="sxs-lookup"><span data-stu-id="8cdd7-208">You can choose to let the model define high value customers.</span></span> <span data-ttu-id="8cdd7-209">Mô hình sẽ sử dụng quy tắc suy nghiệm để lấy phân vị phần trăm.</span><span class="sxs-lookup"><span data-stu-id="8cdd7-209">It uses a heuristic rule that derives the percentile.</span></span> <span data-ttu-id="8cdd7-210">Bạn cũng có thể xác định khách hàng có giá trị cao dưới dạng phân vị phần trăm của những khách hàng chi tiêu nhiều nhất trong tương lai.</span><span class="sxs-lookup"><span data-stu-id="8cdd7-210">You can also define high value customers as a percentile of top future paying customers.</span></span> <span data-ttu-id="8cdd7-211">Trong hướng dẫn mẫu này, chúng ta xác định theo cách thủ công khách hàng có giá trị cao là **30% khách hàng thanh toán hiện hoạt** rồi chọn **Tiếp theo**.</span><span class="sxs-lookup"><span data-stu-id="8cdd7-211">In this sample guide, we manually define high value customers as **top 30% of active paying customers** and select **Next**.</span></span>

    :::image type="content" source="media/clv-model-preferences.png" alt-text="Bước chọn Tùy chọn trong trải nghiệm có hướng dẫn cho mô hình CLV.":::

1. <span data-ttu-id="8cdd7-213">Trong bước **Dữ liệu bắt buộc**, hãy chọn **Thêm dữ liệu** để cung cấp dữ liệu giao dịch trước đây.</span><span class="sxs-lookup"><span data-stu-id="8cdd7-213">In the **Required Data** step, select **Add data** to provide the transaction history data.</span></span>

1. <span data-ttu-id="8cdd7-214">Thêm thực thể **eCommercePurchases : eCommerce** và ánh xạ các thuộc tính theo yêu cầu của mô hình:</span><span class="sxs-lookup"><span data-stu-id="8cdd7-214">Add the **eCommercePurchases : eCommerce** entity and map the attributes that are required by the model:</span></span>
   - <span data-ttu-id="8cdd7-215">ID giao dịch: eCommerce.eCommercePurchases.PurchaseId</span><span class="sxs-lookup"><span data-stu-id="8cdd7-215">Transaction ID: eCommerce.eCommercePurchases.PurchaseId</span></span>
   - <span data-ttu-id="8cdd7-216">Ngày giao dịch: eCommerce.eCommercePurchases.PurchasedOn</span><span class="sxs-lookup"><span data-stu-id="8cdd7-216">Transaction date: eCommerce.eCommercePurchases.PurchasedOn</span></span>
   - <span data-ttu-id="8cdd7-217">Số tiền giao dịch: eCommerce.eCommercePurchases.TotalPrice</span><span class="sxs-lookup"><span data-stu-id="8cdd7-217">Transaction amount: eCommerce.eCommercePurchases.TotalPrice</span></span>
   - <span data-ttu-id="8cdd7-218">ID sản phẩm: eCommerce.eCommercePurchases.ProductId</span><span class="sxs-lookup"><span data-stu-id="8cdd7-218">Product ID: eCommerce.eCommercePurchases.ProductId</span></span>

1. <span data-ttu-id="8cdd7-219">Chọn **Tiếp theo**.</span><span class="sxs-lookup"><span data-stu-id="8cdd7-219">Select **Next**.</span></span>

1. <span data-ttu-id="8cdd7-220">Thiết lập mối quan hệ giữa thực thể **eCommercePurchases : eCommerce** và **eCommerceContacts : eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="8cdd7-220">Set up the relationship between the **eCommercePurchases : eCommerce** entity and  **eCommerceContacts : eCommerce**.</span></span>

1. <span data-ttu-id="8cdd7-221">Bước **Dữ liệu bổ sung (không bắt buộc)** cho phép bạn bổ sung thêm dữ liệu hoạt động của khách hàng.</span><span class="sxs-lookup"><span data-stu-id="8cdd7-221">The **Additional data (optional)** step allows you to add more customer activity data.</span></span> <span data-ttu-id="8cdd7-222">Dữ liệu này có thể giúp tạo thêm thông tin chuyên sâu về hoạt động tương tác của khách hàng với doanh nghiệp của bạn và có thể hữu ích cho CLV.</span><span class="sxs-lookup"><span data-stu-id="8cdd7-222">This data can help to get more insights for customer interactions with your business, which can contribute to CLV.</span></span> <span data-ttu-id="8cdd7-223">Việc thêm các hoạt động tương tác chính của khách hàng như nhật ký web, nhật ký dịch vụ khách hàng hoặc lịch sử chương trình tặng thưởng có thể cải thiện độ chính xác của dự đoán.</span><span class="sxs-lookup"><span data-stu-id="8cdd7-223">Adding key customer interactions like web logs, customer service logs, or rewards program history can improve the accuracy of predictions.</span></span> <span data-ttu-id="8cdd7-224">Chọn **Thêm dữ liệu** để bổ sung thêm dữ liệu hoạt động của khách hàng.</span><span class="sxs-lookup"><span data-stu-id="8cdd7-224">Select **Add data** to include more customer activity data.</span></span>

1. <span data-ttu-id="8cdd7-225">Thêm thực thể hoạt động của khách hàng và ánh xạ tên các trường của thực thể này đến các trường tương ứng theo yêu cầu của mô hình:</span><span class="sxs-lookup"><span data-stu-id="8cdd7-225">Add the customer activity entity and map its fields names to the corresponding fields required by the model:</span></span>
   - <span data-ttu-id="8cdd7-226">Thực thể hoạt động của khách hàng: Reviews:Website</span><span class="sxs-lookup"><span data-stu-id="8cdd7-226">Customer activity entity: Reviews:Website</span></span>
   - <span data-ttu-id="8cdd7-227">Khóa chính: Website.Reviews.ReviewId</span><span class="sxs-lookup"><span data-stu-id="8cdd7-227">Primary key: Website.Reviews.ReviewId</span></span>
   - <span data-ttu-id="8cdd7-228">Dấu thời gian: Website.Reviews.ReviewDate</span><span class="sxs-lookup"><span data-stu-id="8cdd7-228">Timestamp: Website.Reviews.ReviewDate</span></span>
   - <span data-ttu-id="8cdd7-229">Sự kiện (tên hoạt động): Website.Reviews.ActivityTypeDisplay</span><span class="sxs-lookup"><span data-stu-id="8cdd7-229">Event (activity name): Website.Reviews.ActivityTypeDisplay</span></span>
   - <span data-ttu-id="8cdd7-230">Chi tiết (số lượng hoặc giá trị): Website.Reviews.ReviewRating</span><span class="sxs-lookup"><span data-stu-id="8cdd7-230">Details (amount or value): Website.Reviews.ReviewRating</span></span>

1. <span data-ttu-id="8cdd7-231">Chọn **Tiếp theo** rồi đặt cấu hình hoạt động và mối quan hệ giữa dữ liệu giao dịch và dữ liệu khách hàng:</span><span class="sxs-lookup"><span data-stu-id="8cdd7-231">Select **Next** and configure the activity and the relationship between the transaction data and the customer data:</span></span>  
   - <span data-ttu-id="8cdd7-232">Loại hoạt động: Chọn mục hiện có</span><span class="sxs-lookup"><span data-stu-id="8cdd7-232">Activity type: Choose existing</span></span>
   - <span data-ttu-id="8cdd7-233">Nhãn hoạt động: Đánh giá</span><span class="sxs-lookup"><span data-stu-id="8cdd7-233">Activity label: Review</span></span>
   - <span data-ttu-id="8cdd7-234">Nhãn tương ứng: Website.Reviews.UserId</span><span class="sxs-lookup"><span data-stu-id="8cdd7-234">Corresponding label: Website.Reviews.UserId</span></span>
   - <span data-ttu-id="8cdd7-235">Thực thể khách hàng: eCommerceContacts:eCommerce</span><span class="sxs-lookup"><span data-stu-id="8cdd7-235">Customer entity: eCommerceContacts:eCommerce</span></span>
   - <span data-ttu-id="8cdd7-236">Mối quan hệ: WebsiteReviews</span><span class="sxs-lookup"><span data-stu-id="8cdd7-236">Relationship: WebsiteReviews</span></span>

1. <span data-ttu-id="8cdd7-237">Chọn **Tiếp theo** để đặt lịch trình mô hình.</span><span class="sxs-lookup"><span data-stu-id="8cdd7-237">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="8cdd7-238">Mô hình cần được đào tạo thường xuyên để học các mẫu mới khi có dữ liệu mới được nhập vào.</span><span class="sxs-lookup"><span data-stu-id="8cdd7-238">The model needs to train regularly to learn new patterns when there's new data ingested.</span></span> <span data-ttu-id="8cdd7-239">Đối với ví dụ này, hãy chọn **Hàng tháng**.</span><span class="sxs-lookup"><span data-stu-id="8cdd7-239">For this example, choose **Monthly**.</span></span>

1. <span data-ttu-id="8cdd7-240">Sau khi xem lại tất cả thông tin chi tiết, hãy chọn **Lưu và chạy**.</span><span class="sxs-lookup"><span data-stu-id="8cdd7-240">After reviewing all the details, select  **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="8cdd7-241">Nhiệm vụ 4 - Xem xét kết quả và giải thích mô hình</span><span class="sxs-lookup"><span data-stu-id="8cdd7-241">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="8cdd7-242">Để mô hình hoàn thành việc đào tạo và chấm điểm dữ liệu.</span><span class="sxs-lookup"><span data-stu-id="8cdd7-242">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="8cdd7-243">Tiếp theo, bạn có thể xem xét kết quả và phần giải thích mô hình CLV.</span><span class="sxs-lookup"><span data-stu-id="8cdd7-243">Next, you can review the CLV model results and explanations.</span></span> <span data-ttu-id="8cdd7-244">Để biết thêm thông tin, hãy xem [Xem lại dự đoán trạng thái và kết quả](predict-customer-lifetime-value.md#review-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="8cdd7-244">For more information, see [Review a prediction status and results](predict-customer-lifetime-value.md#review-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-value-customers"></a><span data-ttu-id="8cdd7-245">Nhiệm vụ 5 - Tạo phân khúc khách hàng có giá trị cao</span><span class="sxs-lookup"><span data-stu-id="8cdd7-245">Task 5 - Create a segment of high value customers</span></span>

<span data-ttu-id="8cdd7-246">Việc chạy mô hình sẽ tạo một thực thể mới, được liệt kê trên phần **Dữ liệu** > **Thực thể**.</span><span class="sxs-lookup"><span data-stu-id="8cdd7-246">Running the model creates a new entity, which is listed on **Data** > **Entities**.</span></span> <span data-ttu-id="8cdd7-247">Bạn có thể tạo phân khúc khách hàng mới dựa trên thực thể do mô hình tạo.</span><span class="sxs-lookup"><span data-stu-id="8cdd7-247">You can create a new customer segment based on the entity created by the model.</span></span>

1. <span data-ttu-id="8cdd7-248">Đi đến **Phân khúc**.</span><span class="sxs-lookup"><span data-stu-id="8cdd7-248">Go to **Segments**.</span></span> 

1. <span data-ttu-id="8cdd7-249">Chọn **Mới** rồi chọn **Tạo từ** > **Thông tin**.</span><span class="sxs-lookup"><span data-stu-id="8cdd7-249">Select  **New** and choose **Create from** > **Intelligence**.</span></span>

   ![Tạo một phân khúc với đầu ra mô hình.](media/segment-intelligence.png)

1. <span data-ttu-id="8cdd7-251">Chọn thực thể **OOBeCommerceCLVPrediction** và xác định phân khúc:</span><span class="sxs-lookup"><span data-stu-id="8cdd7-251">Select the  **OOBeCommerceCLVPrediction** entity and define the segment:</span></span>
  - <span data-ttu-id="8cdd7-252">Trường: CLVScore</span><span class="sxs-lookup"><span data-stu-id="8cdd7-252">Field: CLVScore</span></span>
  - <span data-ttu-id="8cdd7-253">Toán tử: lớn hơn</span><span class="sxs-lookup"><span data-stu-id="8cdd7-253">Operator: greater than</span></span>
  - <span data-ttu-id="8cdd7-254">Giá trị: 1500</span><span class="sxs-lookup"><span data-stu-id="8cdd7-254">Value: 1500</span></span>

1. <span data-ttu-id="8cdd7-255">Chọn **Đánh giá** và **Lưu** phân khúc.</span><span class="sxs-lookup"><span data-stu-id="8cdd7-255">Select **Review** and **Save** the segment.</span></span>

<span data-ttu-id="8cdd7-256">Giờ đây, bạn có một phân khúc xác định những khách hàng được dự đoán sẽ tạo ra doanh thu hơn $1500 trong 12 tháng tới.</span><span class="sxs-lookup"><span data-stu-id="8cdd7-256">You now have a segment that identifies customers who are predicted to generate more than $1500 of revenue in the next 12 months.</span></span> <span data-ttu-id="8cdd7-257">Phân khúc này sẽ được cập nhật động nếu bạn nhập thêm dữ liệu.</span><span class="sxs-lookup"><span data-stu-id="8cdd7-257">This segment gets updated dynamically if more data is ingested.</span></span>

<span data-ttu-id="8cdd7-258">Để biết thêm thông tin, hãy xem [Tạo và quản lý phân khúc](segments.md).</span><span class="sxs-lookup"><span data-stu-id="8cdd7-258">For more information, see [Create and manage segments](segments.md).</span></span>
