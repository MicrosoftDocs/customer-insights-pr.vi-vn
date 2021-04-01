---
title: Tìm và lọc hồ sơ khách hàng
description: Nhanh chóng tìm thông tin về hồ sơ khách hàng thống nhất và lọc các thuộc tính được chỉ định.
ms.date: 01/19/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: b6cc0ad1a47a6c00e3bf220271f42870fc53621b
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597169"
---
# <a name="customer-profiles-search--filter-index"></a><span data-ttu-id="0824d-103">Hồ sơ khách hàng: Chỉ mục tìm kiếm và lọc</span><span class="sxs-lookup"><span data-stu-id="0824d-103">Customer profiles: Search & filter index</span></span>

<span data-ttu-id="0824d-104">Kết quả của việc thống nhất dữ liệu khách hàng của bạn là một thực thể Hồ sơ khách hàng cung cấp một cái nhìn tổng hợp vào toàn bộ cơ sở khách hàng của bạn.</span><span class="sxs-lookup"><span data-stu-id="0824d-104">The result of unifying your customer data is a Customer Profile entity that provides a unified view into your total customer base.</span></span> <span data-ttu-id="0824d-105">Để nhanh chóng [tìm thông tin về một khách hàng hoặc một nhóm khách hàng cụ thể](customer-profiles.md), bạn có thể đặt cấu hình khả năng **Tìm kiếm** và **Bộ lọc** trên trang **Khách hàng**.</span><span class="sxs-lookup"><span data-stu-id="0824d-105">To quickly [find information on a specific customer or group of customers](customer-profiles.md), you can configure the **Search** and **Filter** capabilities on the **Customers** page.</span></span> <span data-ttu-id="0824d-106">Đọc để tìm hiểu cách quản trị viên có thể chỉnh sửa các thuộc tính trên trang **Tìm kiếm và lọc chỉ mục**, trong đó có sẵn cho người dùng để tìm kiếm và lọc.</span><span class="sxs-lookup"><span data-stu-id="0824d-106">Read on to learn how admins can edit the attributes on the **Search & filter index** page, which are available to users for searching and filtering.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0824d-107">![Bộ lọc tìm kiếm](media/search-filter.png "Bộ lọc tìm kiếm")</span><span class="sxs-lookup"><span data-stu-id="0824d-107">![Search filter](media/search-filter.png "Search filter")</span></span>

## <a name="add-fields-and-specify-attributes"></a><span data-ttu-id="0824d-108">Thêm trường và chỉ định thuộc tính</span><span class="sxs-lookup"><span data-stu-id="0824d-108">Add fields and specify attributes</span></span>

<span data-ttu-id="0824d-109">Nếu đó là lần đầu tiên bạn xác định các thuộc tính có thể tìm kiếm với tư cách là quản trị viên, trước tiên, bạn cần xác định các trường được lập chỉ mục.</span><span class="sxs-lookup"><span data-stu-id="0824d-109">If it's the first time you define searchable attributes as an administrator, you need to define indexed fields first.</span></span> <span data-ttu-id="0824d-110">Chúng tôi khuyên bạn nên chọn tất cả các thuộc tính mà người dùng có thể tìm kiếm và lọc trên trang **Khách hàng**.</span><span class="sxs-lookup"><span data-stu-id="0824d-110">We suggest you choose all the attributes by which users can search and filter customers on the **Customers** page.</span></span> <span data-ttu-id="0824d-111">Bạn chỉ có thể chỉ định các thuộc tính tồn tại trong thực thể hồ sơ khách hàng mà bạn đã tạo trong quá trình thống nhất dữ liệu.</span><span class="sxs-lookup"><span data-stu-id="0824d-111">You can only specify attributes that exist in the Customer Profile entity that you created during the data unification process.</span></span>

1. <span data-ttu-id="0824d-112">Mở trang **Khách hàng** rồi chọn **Tìm kiếm & lọc chỉ mục**.</span><span class="sxs-lookup"><span data-stu-id="0824d-112">Open the **Customers** page and select **Search & filter index**.</span></span>

2. <span data-ttu-id="0824d-113">Chọn **+ Thêm** để chỉ định trường lập chỉ mục.</span><span class="sxs-lookup"><span data-stu-id="0824d-113">Select **+ Add** to specify the indexed fields.</span></span>

3. <span data-ttu-id="0824d-114">Chọn các thuộc tính trong danh sách mà bạn muốn thêm dưới dạng các trường đã lập chỉ mục.</span><span class="sxs-lookup"><span data-stu-id="0824d-114">Select the attributes in the list you want to add as indexed fields.</span></span> <span data-ttu-id="0824d-115">Bạn luôn có thể thêm các thuộc tính bằng cách chọn **Thêm**.</span><span class="sxs-lookup"><span data-stu-id="0824d-115">You can always add more attributes by selecting **Add**.</span></span> <span data-ttu-id="0824d-116">Bạn cũng có thể xóa bất kỳ thuộc tính nào đã chọn bằng cách chọn biểu tượng **Loại bỏ**.</span><span class="sxs-lookup"><span data-stu-id="0824d-116">You can also remove any selected attributes by selecting the **Remove** symbol.</span></span>

## <a name="explore-the-indexed-customer-fields-table"></a><span data-ttu-id="0824d-117">Khám phá bảng trường khách hàng đã lập chỉ mục</span><span class="sxs-lookup"><span data-stu-id="0824d-117">Explore the Indexed customer fields table</span></span>

<span data-ttu-id="0824d-118">Các thông tin sau đây được trình bày trong bảng.</span><span class="sxs-lookup"><span data-stu-id="0824d-118">The following information is presented in the table.</span></span>

- <span data-ttu-id="0824d-119">**Tên**: Biểu thị tên của thuộc tính khi nó xuất hiện trong thực thể hồ sơ khách hàng.</span><span class="sxs-lookup"><span data-stu-id="0824d-119">**Name**: Represents the attribute's name as it appears in the Customer Profile entity.</span></span>
- <span data-ttu-id="0824d-120">**Loại dữ liệu**: Chỉ định loại dữ liệu là một chuỗi, số hoặc một ngày.</span><span class="sxs-lookup"><span data-stu-id="0824d-120">**Data type**: Specifies whether the data type is a string, a number, or a date.</span></span>
- <span data-ttu-id="0824d-121">**Bao gồm trong tìm kiếm** Cho biết liệu một thuộc tính có thể dùng để tìm kiếm khách hàng trên trang **Khách hàng** bằng trường **Tìm kiếm** hay không.</span><span class="sxs-lookup"><span data-stu-id="0824d-121">**Included in search**: Specifies whether this attribute can be used for searching customers on the **Customers** page using the **Search** field.</span></span>
- <span data-ttu-id="0824d-122">**Thêm bộ lọc**: Kiểm soát để xác định cách các thuộc tính này có thể được sử dụng để lọc trên trang **Khách hàng**.</span><span class="sxs-lookup"><span data-stu-id="0824d-122">**Add Filter**: Control to define how this attribute can be used for filtering on the **Customers** page.</span></span>

## <a name="editing-filtering-options-for-a-given-attribute"></a><span data-ttu-id="0824d-123">Chỉnh sửa các tùy chọn lọc cho một thuộc tính nhất định</span><span class="sxs-lookup"><span data-stu-id="0824d-123">Editing filtering options for a given attribute</span></span>

<span data-ttu-id="0824d-124">Menu **Bộ lọc** trên trang **Khách hàng** có thể bao gồm một số mức thuộc tính khác nhau (ví dụ: các nhóm tuổi khác nhau để lọc khách hàng).</span><span class="sxs-lookup"><span data-stu-id="0824d-124">The **Filter** menu on the **Customers** page can include a varying number of attribute levels (for example, different age groups to filter customers by).</span></span>

1. <span data-ttu-id="0824d-125">Chọn **Thêm bộ lọc** cho một thuộc tính nhất định trên trang **Tìm kiếm và lọc chỉ mục**.</span><span class="sxs-lookup"><span data-stu-id="0824d-125">Select **Add Filter** for a given attribute on the **Search & filter index** page.</span></span> <span data-ttu-id="0824d-126">Bạn có thể xác định số lượng kết quả và thứ tự mà chúng sẽ được tổ chức.</span><span class="sxs-lookup"><span data-stu-id="0824d-126">You can define the number of results and the order in which they'll be organized.</span></span> <span data-ttu-id="0824d-127">Tùy thuộc vào loại dữ liệu của thuộc tính, một trong các ngăn sau xuất hiện.</span><span class="sxs-lookup"><span data-stu-id="0824d-127">Depending on the attribute's data type, one of the following panes appears.</span></span>

- <span data-ttu-id="0824d-128">Thuộc tính loại chuỗi: Cho biết số kết quả mong muốn trên bảng điều khiển **Tùy chọn Bộ lọc chuỗi** và chính sách thứ tự mà họ sẽ tổ chức.</span><span class="sxs-lookup"><span data-stu-id="0824d-128">String-type attributes: Specify the number of desired results on the **String filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="0824d-129">Thuộc tính loại số: Cho biết khoảng thời gian trên bảng điều khiển **Tùy chọn Bộ lọc số** và chính sách thứ tự mà họ sẽ tổ chức.</span><span class="sxs-lookup"><span data-stu-id="0824d-129">Numerical-type attributes: Specify the intervals included on the **Number filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="0824d-130">Thuộc tính loại ngày: Cho biết khoảng thời gian trên bảng điều khiển **Tùy chọn Bộ lọc ngày** và chính sách thứ tự mà họ sẽ tổ chức.</span><span class="sxs-lookup"><span data-stu-id="0824d-130">Date-type attributes:  Specify the intervals included on the **Date filter options** pane and the order policy by which they'll be organized.</span></span>

2. <span data-ttu-id="0824d-131">Chọn **Lưu** để áp dụng thay đổi.</span><span class="sxs-lookup"><span data-stu-id="0824d-131">Select **Save** to apply your changes.</span></span>

3. <span data-ttu-id="0824d-132">Chọn **Chạy** sau khi bạn đã sẵn sàng áp dụng cài đặt của mình.</span><span class="sxs-lookup"><span data-stu-id="0824d-132">Select **Run** once you're ready to apply your settings.</span></span>

## <a name="next-steps"></a><span data-ttu-id="0824d-133">Các bước tiếp theo</span><span class="sxs-lookup"><span data-stu-id="0824d-133">Next steps</span></span>

<span data-ttu-id="0824d-134">Đi đến trang **Khách hàng** để tìm kiếm hồ sơ khách hàng hoặc sử dụng các trường được lập chỉ mục để xem một tập hợp con của tất cả hồ sơ khách hàng.</span><span class="sxs-lookup"><span data-stu-id="0824d-134">Go to the **Customers** page to search for customer profiles or use the indexed fields to see a subset of all customer profiles.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]