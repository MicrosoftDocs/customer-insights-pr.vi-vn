---
title: Tìm và lọc hồ sơ khách hàng
description: Nhanh chóng tìm thông tin về hồ sơ khách hàng thống nhất và lọc các thuộc tính được chỉ định.
ms.date: 04/16/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 1842ad333c23bb155abc89167556163ae79cdd34
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407336"
---
# <a name="customer-profiles-search--filter-index"></a><span data-ttu-id="26011-103">Hồ sơ khách hàng: Chỉ mục tìm kiếm và lọc</span><span class="sxs-lookup"><span data-stu-id="26011-103">Customer profiles: Search & filter index</span></span>

<span data-ttu-id="26011-104">Kết quả của việc thống nhất dữ liệu khách hàng của bạn là một thực thể Hồ sơ khách hàng cung cấp một cái nhìn tổng hợp vào toàn bộ cơ sở khách hàng của bạn.</span><span class="sxs-lookup"><span data-stu-id="26011-104">The result of unifying your customer data is a Customer Profile entity that provides a unified view into your total customer base.</span></span> <span data-ttu-id="26011-105">Để nhanh chóng [tìm thông tin về một khách hàng hoặc một nhóm khách hàng cụ thể](customer-profiles.md), bạn có thể đặt cấu hình khả năng **Tìm kiếm** và **Bộ lọc** trên trang **Khách hàng**.</span><span class="sxs-lookup"><span data-stu-id="26011-105">To quickly [find information on a specific customer or group of customers](customer-profiles.md), you can configure the **Search** and **Filter** capabilities on the **Customers** page.</span></span> <span data-ttu-id="26011-106">Đọc để tìm hiểu cách quản trị viên có thể chỉnh sửa các thuộc tính trên trang **Tìm kiếm và lọc chỉ mục**, trong đó có sẵn cho người dùng để tìm kiếm và lọc.</span><span class="sxs-lookup"><span data-stu-id="26011-106">Read on to learn how admins can edit the attributes on the **Search & filter index** page, which are available to users for searching and filtering.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="26011-107">![Bộ lọc tìm kiếm](media/search-filter.png "Bộ lọc tìm kiếm")</span><span class="sxs-lookup"><span data-stu-id="26011-107">![Search filter](media/search-filter.png "Search filter")</span></span>

## <a name="add-fields-and-specify-attributes"></a><span data-ttu-id="26011-108">Thêm trường và chỉ định thuộc tính</span><span class="sxs-lookup"><span data-stu-id="26011-108">Add fields and specify attributes</span></span>

<span data-ttu-id="26011-109">Nếu đó là lần đầu tiên bạn xác định các thuộc tính có thể tìm kiếm với tư cách là quản trị viên, trước tiên, bạn cần xác định các trường được lập chỉ mục.</span><span class="sxs-lookup"><span data-stu-id="26011-109">If it's the first time you define searchable attributes as an administrator, you need to define indexed fields first.</span></span> <span data-ttu-id="26011-110">Chúng tôi khuyên bạn nên chọn tất cả các thuộc tính mà người dùng có thể tìm kiếm và lọc trên trang **Khách hàng**.</span><span class="sxs-lookup"><span data-stu-id="26011-110">We suggest you choose all the attributes by which users can search and filter customers on the **Customers** page.</span></span> <span data-ttu-id="26011-111">Bạn chỉ có thể chỉ định các thuộc tính tồn tại trong thực thể hồ sơ khách hàng mà bạn đã tạo trong quá trình thống nhất dữ liệu.</span><span class="sxs-lookup"><span data-stu-id="26011-111">You can only specify attributes that exist in the Customer Profile entity that you created during the data unification process.</span></span>

1. <span data-ttu-id="26011-112">Mở trang **Khách hàng** rồi chọn **Tìm kiếm & lọc chỉ mục**.</span><span class="sxs-lookup"><span data-stu-id="26011-112">Open the **Customers** page and select **Search & filter index**.</span></span>

> [!NOTE]
> <span data-ttu-id="26011-113">Chúng tôi đã tạo cấu hình chỉ mục tìm kiếm mặc định trên các thuộc tính khả dụng trong thực thể Khách hàng từ các loại ngữ nghĩa sau như xác định trên trang Bản đồ.</span><span class="sxs-lookup"><span data-stu-id="26011-113">We create a default search index configuration on the available attributes in the Customer entity from the following semantic types as defined on the Map page.</span></span>
> - <span data-ttu-id="26011-114">Tên, Họ, Tên đệm và Tên đầy đủ của một người</span><span class="sxs-lookup"><span data-stu-id="26011-114">Person First name, Last name, Middle name, Full Name</span></span>
> - <span data-ttu-id="26011-115">Tên tổ chức</span><span class="sxs-lookup"><span data-stu-id="26011-115">Organization Name</span></span>
> - <span data-ttu-id="26011-116">Địa chỉ email</span><span class="sxs-lookup"><span data-stu-id="26011-116">Email address</span></span>
> - <span data-ttu-id="26011-117">Số điện thoại</span><span class="sxs-lookup"><span data-stu-id="26011-117">Phone number</span></span>
> - <span data-ttu-id="26011-118">Thông tin vị trí</span><span class="sxs-lookup"><span data-stu-id="26011-118">Location information</span></span>

2. <span data-ttu-id="26011-119">Chọn **+ Thêm** để chỉ định trường lập chỉ mục.</span><span class="sxs-lookup"><span data-stu-id="26011-119">Select **+ Add** to specify the indexed fields.</span></span>

3. <span data-ttu-id="26011-120">Chọn các thuộc tính trong danh sách mà bạn muốn thêm dưới dạng các trường đã lập chỉ mục.</span><span class="sxs-lookup"><span data-stu-id="26011-120">Select the attributes in the list you want to add as indexed fields.</span></span> <span data-ttu-id="26011-121">Bạn luôn có thể thêm các thuộc tính bằng cách chọn **Thêm**.</span><span class="sxs-lookup"><span data-stu-id="26011-121">You can always add more attributes by selecting **Add**.</span></span> <span data-ttu-id="26011-122">Bạn cũng có thể xóa bất kỳ thuộc tính nào đã chọn bằng cách chọn biểu tượng **Loại bỏ**.</span><span class="sxs-lookup"><span data-stu-id="26011-122">You can also remove any selected attributes by selecting the **Remove** symbol.</span></span>

## <a name="explore-the-indexed-customer-fields-table"></a><span data-ttu-id="26011-123">Khám phá bảng trường khách hàng đã lập chỉ mục</span><span class="sxs-lookup"><span data-stu-id="26011-123">Explore the Indexed customer fields table</span></span>

<span data-ttu-id="26011-124">Các thông tin sau đây được trình bày trong bảng.</span><span class="sxs-lookup"><span data-stu-id="26011-124">The following information is presented in the table.</span></span>

- <span data-ttu-id="26011-125">**Tên**: Biểu thị tên của thuộc tính khi nó xuất hiện trong thực thể hồ sơ khách hàng.</span><span class="sxs-lookup"><span data-stu-id="26011-125">**Name**: Represents the attribute's name as it appears in the Customer Profile entity.</span></span>
- <span data-ttu-id="26011-126">**Loại dữ liệu**: Chỉ định loại dữ liệu là một chuỗi, số hoặc một ngày.</span><span class="sxs-lookup"><span data-stu-id="26011-126">**Data type**: Specifies whether the data type is a string, a number, or a date.</span></span>
- <span data-ttu-id="26011-127">**Bao gồm trong tìm kiếm** Cho biết liệu một thuộc tính có thể dùng để tìm kiếm khách hàng trên trang **Khách hàng** bằng trường **Tìm kiếm** hay không.</span><span class="sxs-lookup"><span data-stu-id="26011-127">**Included in search**: Specifies whether this attribute can be used for searching customers on the **Customers** page using the **Search** field.</span></span>
- <span data-ttu-id="26011-128">**Thêm bộ lọc**: Kiểm soát để xác định cách các thuộc tính này có thể được sử dụng để lọc trên trang **Khách hàng**.</span><span class="sxs-lookup"><span data-stu-id="26011-128">**Add Filter**: Control to define how this attribute can be used for filtering on the **Customers** page.</span></span>

## <a name="editing-filtering-options-for-a-given-attribute"></a><span data-ttu-id="26011-129">Chỉnh sửa các tùy chọn lọc cho một thuộc tính nhất định</span><span class="sxs-lookup"><span data-stu-id="26011-129">Editing filtering options for a given attribute</span></span>

<span data-ttu-id="26011-130">Menu **Bộ lọc** trên trang **Khách hàng** có thể bao gồm một số mức thuộc tính khác nhau (ví dụ: các nhóm tuổi khác nhau để lọc khách hàng).</span><span class="sxs-lookup"><span data-stu-id="26011-130">The **Filter** menu on the **Customers** page can include a varying number of attribute levels (for example, different age groups to filter customers by).</span></span>

1. <span data-ttu-id="26011-131">Chọn **Thêm bộ lọc** cho một thuộc tính nhất định trên trang **Tìm kiếm và lọc chỉ mục**.</span><span class="sxs-lookup"><span data-stu-id="26011-131">Select **Add Filter** for a given attribute on the **Search & filter index** page.</span></span> <span data-ttu-id="26011-132">Bạn có thể xác định số lượng kết quả và thứ tự mà chúng sẽ được tổ chức.</span><span class="sxs-lookup"><span data-stu-id="26011-132">You can define the number of results and the order in which they'll be organized.</span></span> <span data-ttu-id="26011-133">Tùy thuộc vào loại dữ liệu của thuộc tính, một trong các ngăn sau xuất hiện.</span><span class="sxs-lookup"><span data-stu-id="26011-133">Depending on the attribute's data type, one of the following panes appears.</span></span>

- <span data-ttu-id="26011-134">Thuộc tính loại chuỗi: Cho biết số kết quả mong muốn trên bảng điều khiển **Tùy chọn Bộ lọc chuỗi** và chính sách thứ tự mà họ sẽ tổ chức.</span><span class="sxs-lookup"><span data-stu-id="26011-134">String-type attributes: Specify the number of desired results on the **String filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="26011-135">Thuộc tính loại số: Cho biết khoảng thời gian trên bảng điều khiển **Tùy chọn Bộ lọc số** và chính sách thứ tự mà họ sẽ tổ chức.</span><span class="sxs-lookup"><span data-stu-id="26011-135">Numerical-type attributes: Specify the intervals included on the **Number filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="26011-136">Thuộc tính loại ngày: Cho biết khoảng thời gian trên bảng điều khiển **Tùy chọn Bộ lọc ngày** và chính sách thứ tự mà họ sẽ tổ chức.</span><span class="sxs-lookup"><span data-stu-id="26011-136">Date-type attributes:  Specify the intervals included on the **Date filter options** pane and the order policy by which they'll be organized.</span></span>

2. <span data-ttu-id="26011-137">Chọn **Lưu** để áp dụng thay đổi.</span><span class="sxs-lookup"><span data-stu-id="26011-137">Select **Save** to apply your changes.</span></span>

3. <span data-ttu-id="26011-138">Chọn **Chạy** sau khi bạn đã sẵn sàng áp dụng cài đặt của mình.</span><span class="sxs-lookup"><span data-stu-id="26011-138">Select **Run** once you're ready to apply your settings.</span></span>
