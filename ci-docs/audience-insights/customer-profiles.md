---
title: Xem hồ sơ khách hàng
description: Nhận thông tin kết hợp về dữ liệu khách hàng hợp nhất của bạn.
ms.date: 12/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: c9adb4d7db74573d0512ae7a68a0e7ab51c994a0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304630"
---
# <a name="customer-profiles"></a><span data-ttu-id="56d0e-103">Hồ sơ khách hàng</span><span class="sxs-lookup"><span data-stu-id="56d0e-103">Customer profiles</span></span>

<span data-ttu-id="56d0e-104">Trang **Khách hàng** hiển thị thông tin kết hợp về khách hàng của bạn, dựa trên dữ liệu hồ sơ thu thập được từ [tất cả nguồn dữ liệu](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="56d0e-104">The **Customers** page shows a combined view of your customers, based on profile data gathered from [all data sources](data-sources.md).</span></span> <span data-ttu-id="56d0e-105">Hồ sơ khách hàng có sẵn sau khi bạn [tạo thực thể khách hàng thống nhất](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="56d0e-105">Customer profiles are available once you [create the unified Customer entity](data-unification.md).</span></span> <span data-ttu-id="56d0e-106">Hãy chắc chắn rằng bạn hoàn thành quy trình hợp nhất dữ liệu để có được dạng xem phong phú hơn về khách hàng của mình.</span><span class="sxs-lookup"><span data-stu-id="56d0e-106">Make sure you complete the data unification process to get richer views of your customers.</span></span> <span data-ttu-id="56d0e-107">Trang cũng cho phép bạn tìm kiếm khách hàng.</span><span class="sxs-lookup"><span data-stu-id="56d0e-107">The page also lets you search for customers.</span></span>

<span data-ttu-id="56d0e-108">Khách hàng có thể là cá nhân hoặc tổ chức (xem trước).</span><span class="sxs-lookup"><span data-stu-id="56d0e-108">Customers can be individuals or organizations (preview).</span></span> <span data-ttu-id="56d0e-109">Mỗi hồ sơ khách hàng hoặc tổ chức được đại diện bởi một ngăn xếp.</span><span class="sxs-lookup"><span data-stu-id="56d0e-109">Each customer or organization profile is represented by a tile.</span></span> <span data-ttu-id="56d0e-110">Chọn một ngăn xếp để xem thông tin bổ sung về khách hàng hoặc tổ chức cụ thể đó.</span><span class="sxs-lookup"><span data-stu-id="56d0e-110">Select a tile to see additional information on that specific customer or organization.</span></span> <span data-ttu-id="56d0e-111">Sử dụng các điều khiển phân trang ở cuối trang để xem các bản ghi bổ sung.</span><span class="sxs-lookup"><span data-stu-id="56d0e-111">Use the pagination controls at the bottom of the page to see additional records.</span></span>

> [!div class="mx-imgBorder"] 
> <span data-ttu-id="56d0e-112">![Hồ sơ khách hàng B2C](media/profiles-customers.png "Hồ sơ khách hàng B2C")</span><span class="sxs-lookup"><span data-stu-id="56d0e-112">![B2C customer profiles](media/profiles-customers.png "B2C customer profiles")</span></span>

<span data-ttu-id="56d0e-113">Tổ chức (Xem trước)</span><span class="sxs-lookup"><span data-stu-id="56d0e-113">Organizations (Preview)</span></span>
> [!div class="mx-imgBorder"] 
> <span data-ttu-id="56d0e-114">![Hồ sơ khách hàng B2B](media/profile-customers-b2b.png "Hồ sơ khách hàng B2B")</span><span class="sxs-lookup"><span data-stu-id="56d0e-114">![B2B customer profiles](media/profile-customers-b2b.png "B2B customer profiles")</span></span>

> [!NOTE]
> <span data-ttu-id="56d0e-115">Nếu bạn không thể nhìn thấy ngăn xếp khi bạn chọn **Khách hàng** trong điều hướng, quản trị viên của bạn cần phải [xác định ít nhất một thuộc tính có thể tìm kiếm](search-filter-index.md) trên **Chỉ mục tìm kiếm & lọc**.</span><span class="sxs-lookup"><span data-stu-id="56d0e-115">If you can't see the tiles when you select **Customers** in navigation, your administrator needs to [define at least one searchable attribute](search-filter-index.md) on the **Search & filter index**.</span></span>

## <a name="search-for-customers"></a><span data-ttu-id="56d0e-116">Tìm kiếm khách hàng</span><span class="sxs-lookup"><span data-stu-id="56d0e-116">Search for customers</span></span>

<span data-ttu-id="56d0e-117">Tìm kiếm khách hàng bằng cách nhập tên hoặc một số thuộc tính khác vào hộp tìm kiếm.</span><span class="sxs-lookup"><span data-stu-id="56d0e-117">Search for customers by entering a name or some other attribute in the search box.</span></span> <span data-ttu-id="56d0e-118">Tìm kiếm chỉ hoạt động trong thực thể Hồ sơ khách hàng được tạo trong quá trình hợp nhất dữ liệu.</span><span class="sxs-lookup"><span data-stu-id="56d0e-118">The search only works within the Customer Profile entity created during the data unification process.</span></span>

<span data-ttu-id="56d0e-119">Là quản trị viên, bạn có thể định cấu hình các thuộc tính có thể tìm kiếm bằng cách sử dụng trang **Tìm kiếm và lọc chỉ mục**.</span><span class="sxs-lookup"><span data-stu-id="56d0e-119">As an admin, you can configure the searchable attributes using the **Search & filter index** page.</span></span> <span data-ttu-id="56d0e-120">Để biết thêm thông tin, hãy xem [Quản lý tìm kiếm và lọc chỉ mục](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="56d0e-120">For more information, see [Manage search & filter index](search-filter-index.md).</span></span>

## <a name="filter-customers"></a><span data-ttu-id="56d0e-121">Lọc khách hàng</span><span class="sxs-lookup"><span data-stu-id="56d0e-121">Filter customers</span></span>

<span data-ttu-id="56d0e-122">Bạn có thể lọc khách hàng theo các trường thực thể Hồ sơ khách hàng.</span><span class="sxs-lookup"><span data-stu-id="56d0e-122">You can filter customers by the Customer Profile entity fields.</span></span> <span data-ttu-id="56d0e-123">Tương tự như tìm kiếm, trước tiên, quản trị viên của bạn sẽ cần xác định các trường là có thể lọc bằng cách sử dụng trang **Tìm kiếm và lọc chỉ mục**.</span><span class="sxs-lookup"><span data-stu-id="56d0e-123">Similar to search, your admin will first need to define the fields as filterable using the **Search & filter index** page.</span></span>

1. <span data-ttu-id="56d0e-124">Chọn **Bộ lọc** trên trang **Khách hàng**.</span><span class="sxs-lookup"><span data-stu-id="56d0e-124">Select **Filter** on the **Customers** page.</span></span>

2. <span data-ttu-id="56d0e-125">Chọn các hộp bên cạnh các thuộc tính bạn muốn lọc khách hàng.</span><span class="sxs-lookup"><span data-stu-id="56d0e-125">Check the boxes next to the attributes you want to filter customers by.</span></span>

   > [!div class="mx-imgBorder"] 
   > <span data-ttu-id="56d0e-126">![Hồ sơ khách hàng](media/profiles-customers3.png "Hồ sơ khách hàng")</span><span class="sxs-lookup"><span data-stu-id="56d0e-126">![Customer profiles](media/profiles-customers3.png "Customer profiles")</span></span>

3. <span data-ttu-id="56d0e-127">Xóa bộ lọc của bạn bằng cách chọn **Xóa bộ lọc** trên trang **Khách hàng**.</span><span class="sxs-lookup"><span data-stu-id="56d0e-127">Remove your filters by selecting **Clear filters** on the **Customers** page.</span></span>

##  <a name="customer-details-page"></a><span data-ttu-id="56d0e-128">Trang thông tin chi tiết về khách hàng</span><span class="sxs-lookup"><span data-stu-id="56d0e-128">Customer details page</span></span>

<span data-ttu-id="56d0e-129">Chọn bất kỳ ngăn xếp khách hàng nào để mở **Trang thông tin chi tiết về khách hàng**.</span><span class="sxs-lookup"><span data-stu-id="56d0e-129">Select any of the customer tiles to open the **Customer details page**.</span></span> <span data-ttu-id="56d0e-130">Chế độ xem này chứa thông tin hợp nhất cho khách hàng đã chọn.</span><span class="sxs-lookup"><span data-stu-id="56d0e-130">This view contains unified information for the selected customer.</span></span>

<span data-ttu-id="56d0e-131">Thông tin chi tiết về khách hàng bao gồm:</span><span class="sxs-lookup"><span data-stu-id="56d0e-131">Customer details include:</span></span>

-   <span data-ttu-id="56d0e-132">**Ngăn xếp hồ sơ khách hàng**: Ngăn xếp này hiển thị các giá trị khác nhau từ thực thể hồ sơ khách hàng hợp nhất.</span><span class="sxs-lookup"><span data-stu-id="56d0e-132">**Customer profile tile**: This tile shows the different values from the unified customer profile entity.</span></span> <span data-ttu-id="56d0e-133">Những chi tiết này có thể bao gồm địa chỉ email, tên, thành phố, v.v.</span><span class="sxs-lookup"><span data-stu-id="56d0e-133">These details can include email address, name, city, and so on.</span></span> 

-   <span data-ttu-id="56d0e-134">**Sở thích tiềm năng, thương hiệu tiềm năng**: Hiển thị nếu bạn đã định cấu hình phần bổ sung của bên thứ nhất.</span><span class="sxs-lookup"><span data-stu-id="56d0e-134">**Potential interests, potential brands**: Shows if you configured a first-party enrichment.</span></span> <span data-ttu-id="56d0e-135">Nó thể hiện sở thích và mối quan hệ tiềm năng đối với các thương hiệu mà một khách hàng có hồ sơ tương tự như khách hàng này có thể có.</span><span class="sxs-lookup"><span data-stu-id="56d0e-135">It represents potential interests and affinities for brands a customer with a profile similar to this customer might have.</span></span> <span data-ttu-id="56d0e-136">Để biết thêm thông tin, hãy xem [Làm phong phú hồ sơ khách hàng bằng thương hiệu và sở thích](enrichment-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="56d0e-136">For more information, see [Enrich customer profiles with brand and interest affinities](enrichment-microsoft.md).</span></span>

-   <span data-ttu-id="56d0e-137">**Đo lường**: Hiển thị nếu bạn đã định cấu hình một hoặc nhiều loại biện pháp đo lường cụ thể: đo lường thuộc tính khách hàng.</span><span class="sxs-lookup"><span data-stu-id="56d0e-137">**Measures**: Shows if you configured one or more measures of a specific type: customer attribute measures.</span></span> <span data-ttu-id="56d0e-138">Chúng bao gồm các KPI được tính toán xung quanh khách hàng của bạn ở cấp độ khách hàng cá nhân.</span><span class="sxs-lookup"><span data-stu-id="56d0e-138">They include calculated KPIs around your customers on the individual customer level.</span></span> <span data-ttu-id="56d0e-139">Để biết thêm thông tin, hãy xem [Xác định và quản lý các biện pháp](measures.md).</span><span class="sxs-lookup"><span data-stu-id="56d0e-139">For more information, see [Define and manage measures](measures.md).</span></span>

-   <span data-ttu-id="56d0e-140">**Tiến trình hoạt động**: Hiển thị nếu bạn đã định cấu hình các hoạt động.</span><span class="sxs-lookup"><span data-stu-id="56d0e-140">**Activity timeline**: Shows if you have configured activities.</span></span> <span data-ttu-id="56d0e-141">Chế độ xem dòng thời gian chứa các hoạt động được sắp xếp theo thứ tự thời gian của khách hàng này, bắt đầu với hoạt động gần đây nhất.</span><span class="sxs-lookup"><span data-stu-id="56d0e-141">The timeline view contains chronologically sorted activities of this customer, starting with the most recent activity.</span></span> <span data-ttu-id="56d0e-142">Để biết thêm thông tin, hãy xem [Hoạt động của khách hàng](activities.md).</span><span class="sxs-lookup"><span data-stu-id="56d0e-142">For more information, see [Customer activities](activities.md).</span></span>

<span data-ttu-id="56d0e-143">Chọn **Quay lại khách hàng** để quay lại trang tìm kiếm của khách hàng.</span><span class="sxs-lookup"><span data-stu-id="56d0e-143">Select **Back to Customers** to return to the customer search page.</span></span>

## <a name="next-steps"></a><span data-ttu-id="56d0e-144">Các bước tiếp theo</span><span class="sxs-lookup"><span data-stu-id="56d0e-144">Next steps</span></span>

<span data-ttu-id="56d0e-145">[Thêm nhiều nguồn dữ liệu](data-sources.md) hoặc [tạo phân khúc khách hàng](segments.md).</span><span class="sxs-lookup"><span data-stu-id="56d0e-145">[Add more data sources](data-sources.md) or [create customer segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
