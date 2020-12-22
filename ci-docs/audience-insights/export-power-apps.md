---
title: Trình kết nối Power Apps
description: Kết nối với Power Apps và Power Automate.
ms.date: 08/21/2020
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b6ec103e29e218b2f27bfc1193300ea793a6b30b
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407291"
---
# <a name="microsoft-power-apps-connector-preview"></a><span data-ttu-id="20eee-103">Trình kết nối Microsoft Power Apps (xem trước)</span><span class="sxs-lookup"><span data-stu-id="20eee-103">Microsoft Power Apps connector (preview)</span></span>

<span data-ttu-id="20eee-104">Đưa hồ sơ khách hàng hợp nhất vào các ứng dụng được cá nhân hóa của bạn với Power Apps.</span><span class="sxs-lookup"><span data-stu-id="20eee-104">Bring unified customer profiles into your personalized apps with Power Apps.</span></span>

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a><span data-ttu-id="20eee-105">Kết nối Power Apps và Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="20eee-105">Connect Power Apps and Dynamics 365 Customer Insights</span></span>

<span data-ttu-id="20eee-106">Customer Insights là một trong số nhiều [nguồn có sẵn cho dữ liệu trong Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/working-with-data-sources).</span><span class="sxs-lookup"><span data-stu-id="20eee-106">Customer Insights is one of the many [available sources for data in Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/working-with-data-sources).</span></span>

<span data-ttu-id="20eee-107">Tham khảo tài liệu Power Apps để tìm hiểu cách [thêm kết nối dữ liệu tới ứng dụng](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-data-connection).</span><span class="sxs-lookup"><span data-stu-id="20eee-107">Refer to the Power Apps documentation to learn how to [add a data connection to an app](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-data-connection).</span></span> <span data-ttu-id="20eee-108">Ngoài ra, bạn nên xem [cách Power Apps sử dụng đại diện để xử lý tập dữ liệu lớn trong ứng dụng Canvas](https://docs.microsoft.com/powerapps/maker/canvas-apps/delegation-overview).</span><span class="sxs-lookup"><span data-stu-id="20eee-108">We recommend you also review [how Power Apps uses delegation to handle large datasets in Canvas apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/delegation-overview).</span></span>

## <a name="available-entities"></a><span data-ttu-id="20eee-109">Các thực thể sẵn có</span><span class="sxs-lookup"><span data-stu-id="20eee-109">Available entities</span></span>

<span data-ttu-id="20eee-110">Sau khi thêm Customer Insights làm kết nối dữ liệu, bạn có thể chọn các thực thể sau trong Power Apps:</span><span class="sxs-lookup"><span data-stu-id="20eee-110">After adding Customer Insights as a data connection, you can choose the following entities in Power Apps:</span></span>

- <span data-ttu-id="20eee-111">Khách hàng: để sử dụng dữ liệu từ [hồ sơ khách hàng hợp nhất](customer-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="20eee-111">Customer: to use data from the [unified customer profile](customer-profiles.md).</span></span>
- <span data-ttu-id="20eee-112">Hoạt động khách hàng hợp nhất: để hiển thị [dòng thời gian hoạt động](activities.md) trong ứng dụng.</span><span class="sxs-lookup"><span data-stu-id="20eee-112">Unified Customer Activity: to display the [activity timeline](activities.md) on the app.</span></span>

## <a name="limitations"></a><span data-ttu-id="20eee-113">Giới hạn</span><span class="sxs-lookup"><span data-stu-id="20eee-113">Limitations</span></span>

### <a name="retrievable-entities"></a><span data-ttu-id="20eee-114">Các thực thể có thể truy xuất</span><span class="sxs-lookup"><span data-stu-id="20eee-114">Retrievable entities</span></span>

<span data-ttu-id="20eee-115">Bạn chỉ có thể truy xuất các thực thể **Khách hàng**, **UnifiedActivity** và **Phân khúc** thông qua trình kết nối Power Apps.</span><span class="sxs-lookup"><span data-stu-id="20eee-115">You can only retrieve the **Customer**, **UnifiedActivity**, and **Segments** entities through the Power Apps connector.</span></span> <span data-ttu-id="20eee-116">Các thực thể khác được hiển thị vì trình kết nối cơ bản hỗ trợ chúng thông qua trình kích hoạt trong Power Automate.</span><span class="sxs-lookup"><span data-stu-id="20eee-116">Other entities are shown because the underlying connector supports them through triggers in Power Automate.</span></span>  

### <a name="delegation"></a><span data-ttu-id="20eee-117">Đại diện</span><span class="sxs-lookup"><span data-stu-id="20eee-117">Delegation</span></span>

<span data-ttu-id="20eee-118">Ủy quyền hoạt động cho thực thể Khách hàng và thực thể UnifiedActivity.</span><span class="sxs-lookup"><span data-stu-id="20eee-118">Delegation works for the Customer entity and UnifiedActivity entity.</span></span> 

- <span data-ttu-id="20eee-119">Ủy quyền cho thực thể **Khách hàng**: Để sử dụng ủy quyền cho thực thể này, cần lập chỉ mục các trường trong [Chỉ mục tìm kiếm và lọc](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="20eee-119">Delegation for **Customer** entity: To use delegation for this entity, the fields need to be indexed in [Search & filter index](search-filter-index.md).</span></span>  

- <span data-ttu-id="20eee-120">Ủy quyền cho **UnifiedActivity**: Ủy quyền cho thực thể này chỉ hoạt động cho các trường **ActivityId** và **CustomerId**.</span><span class="sxs-lookup"><span data-stu-id="20eee-120">Delegation for **UnifiedActivity**: Delegation for this entity only works for the fields **ActivityId** and **CustomerId**.</span></span>  

- <span data-ttu-id="20eee-121">Để biết thêm thông tin về ủy quyền, hãy xem [Hoạt động và các chức năng có thể ủy quyền Power Apps](https://docs.microsoft.com/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps).</span><span class="sxs-lookup"><span data-stu-id="20eee-121">For more information about delegation, see [Power Apps delegable functions and operations](https://docs.microsoft.com/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps).</span></span> 

## <a name="example-gallery-control"></a><span data-ttu-id="20eee-122">Kiểm soát thư viện ví dụ</span><span class="sxs-lookup"><span data-stu-id="20eee-122">Example gallery control</span></span>

<span data-ttu-id="20eee-123">Ví dụ: bạn thêm hồ sơ khách hàng vào [kiểm soát thư viện](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-gallery).</span><span class="sxs-lookup"><span data-stu-id="20eee-123">For example, you add customer profiles to a [gallery control](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-gallery).</span></span>

1. <span data-ttu-id="20eee-124">Thêm một kiểm soát **Thư viện** vào ứng dụng bạn đang xây dựng.</span><span class="sxs-lookup"><span data-stu-id="20eee-124">Add a **Gallery** control to an app you're building.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="20eee-125">![Thêm một thành phần thư viện](media/connector-powerapps9.png "Thêm một thành phần thư viện")</span><span class="sxs-lookup"><span data-stu-id="20eee-125">![Add a gallery element](media/connector-powerapps9.png "Add a gallery element")</span></span>

1. <span data-ttu-id="20eee-126">Chọn **Khách hàng** làm nguồn dữ liệu cho các mặt hàng.</span><span class="sxs-lookup"><span data-stu-id="20eee-126">Select **Customer** as the data source for items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="20eee-127">![Chọn nguồn dữ liệu](media/choose-datasource-powerapps.png "Chọn nguồn dữ liệu")</span><span class="sxs-lookup"><span data-stu-id="20eee-127">![Select a data source](media/choose-datasource-powerapps.png "Select a data source")</span></span>

1. <span data-ttu-id="20eee-128">Bạn có thể thay đổi bảng dữ liệu ở bên phải để chọn trường cho thực thể Khách hàng hiển thị trên thư viện.</span><span class="sxs-lookup"><span data-stu-id="20eee-128">You can change the data panel on the right to select which field for the Customer entity to show on the gallery.</span></span>

1. <span data-ttu-id="20eee-129">Nếu bạn muốn hiển thị bất kỳ trường nào từ khách hàng đã chọn trên thư viện, hãy điền vào thuộc tính Văn bản của nhãn: **{Name_of_the_gallery}.Đã chọn.{property_name}**</span><span class="sxs-lookup"><span data-stu-id="20eee-129">If you want to show any field from the selected customer on the gallery, fill in the Text property of a label:  **{Name_of_the_gallery}.Selected.{property_name}**</span></span>

    <span data-ttu-id="20eee-130">Ví dụ: Gallery1.Selected.address1_city</span><span class="sxs-lookup"><span data-stu-id="20eee-130">Example: Gallery1.Selected.address1_city</span></span>

1. <span data-ttu-id="20eee-131">Để hiển thị dòng thời gian hợp nhất cho khách hàng, hãy thêm phần tử Thư viện và thuộc tính Items: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**</span><span class="sxs-lookup"><span data-stu-id="20eee-131">To display the unified timeline for a customer, add a Gallery element, and add the Items property: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**</span></span>

    <span data-ttu-id="20eee-132">Ví dụ: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span><span class="sxs-lookup"><span data-stu-id="20eee-132">Example: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span></span>
