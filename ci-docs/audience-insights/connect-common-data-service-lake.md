---
title: Kết nối với các thực thể trong kho do Common Data Service quản lý
description: Nhập dữ liệu từ một kho dữ liệu Common Data Service được quản lý.
ms.date: 09/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: mhart
ms.openlocfilehash: b1cfab40c1edb32f4a7f359e1195cfb1e879a0d5
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596985"
---
# <a name="connect-to-data-in-a-common-data-service-managed-data-lake"></a><span data-ttu-id="4c141-103">Kết nối với dữ liệu trong một kho dữ liệu được quản lý Common Data Service</span><span class="sxs-lookup"><span data-stu-id="4c141-103">Connect to data in a Common Data Service managed data lake</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="4c141-104">Bài viết này cung cấp thông tin về cách khách hàng Dynamics 365 hiện tại có thể nhanh chóng kết nối với các thực thể phân tích của họ trong kho dữ liệu Common Data Service được quản lý.</span><span class="sxs-lookup"><span data-stu-id="4c141-104">This article provides information on how existing Dynamics 365 customers can quickly connect to their analytical entities in the Common Data Service managed lake.</span></span> <span data-ttu-id="4c141-105">Bạn phải là quản trị viên trên tổ chức Common Data Service để tiến hành và xem danh sách các thực thể có trong kho dữ liệu được quản lý.</span><span class="sxs-lookup"><span data-stu-id="4c141-105">You must be an admin on the Common Data Service organization to proceed and see the list of entities available in the managed lake.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="4c141-106">Những điều quan trọng cần cân nhắc</span><span class="sxs-lookup"><span data-stu-id="4c141-106">Important considerations</span></span>

<span data-ttu-id="4c141-107">Dữ liệu lưu trữ trong các dịch vụ trực tuyến như Azure Data Lake Storage có thể được lưu trữ ở địa điểm khác với nơi xử lý hoặc lưu trữ dữ liệu trong Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="4c141-107">Data stored in online services, such as Azure Data Lake Storage, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="4c141-108"> Khi nhập hoặc kết nối với dữ liệu lưu trữ trong các dịch vụ trực tuyến, bạn đồng ý rằng dữ liệu có thể được chuyển sang hoặc lưu trữ bằng Dynamics 365 Customer Insights. [Tìm hiểu thêm trên Trung tâm tin cậy Microsoft.](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="4c141-108"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-service-managed-lake"></a><span data-ttu-id="4c141-109">Kết nối với kho được quản lý Common Data Service</span><span class="sxs-lookup"><span data-stu-id="4c141-109">Connect to a Common Data Service managed lake</span></span>

1. <span data-ttu-id="4c141-110">Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Dữ liệu** > **Nguồn dữ liệu**.</span><span class="sxs-lookup"><span data-stu-id="4c141-110">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="4c141-111">Chọn **Thêm nguồn dữ liệu**.</span><span class="sxs-lookup"><span data-stu-id="4c141-111">Select **Add data source**.</span></span>

3. <span data-ttu-id="4c141-112">Chọn **Kết nối với Common Data Service** rồi chọn **Tiếp theo**.</span><span class="sxs-lookup"><span data-stu-id="4c141-112">Select **Connect to Common Data Service** and select **Next**.</span></span>

4. <span data-ttu-id="4c141-113">Đặt **Tên** cho nguồn dữ liệu rồi chọn **Tiếp**.</span><span class="sxs-lookup"><span data-stu-id="4c141-113">Enter a **Name** for the data source and select **Next**.</span></span> <span data-ttu-id="4c141-114">Hướng dẫn về tên:</span><span class="sxs-lookup"><span data-stu-id="4c141-114">Name guidelines:</span></span> 
   - <span data-ttu-id="4c141-115">Bắt đầu bằng một chữ cái.</span><span class="sxs-lookup"><span data-stu-id="4c141-115">Start with a letter.</span></span>
   - <span data-ttu-id="4c141-116">Chỉ sử dụng chữ cái và số.</span><span class="sxs-lookup"><span data-stu-id="4c141-116">Use letters and numbers only.</span></span> <span data-ttu-id="4c141-117">Không được phép nhập ký tự đặc biệt và khoảng trống.</span><span class="sxs-lookup"><span data-stu-id="4c141-117">Special characters and spaces are not allowed.</span></span>
   - <span data-ttu-id="4c141-118">Sử dụng từ 3 đến 64 ký tự.</span><span class="sxs-lookup"><span data-stu-id="4c141-118">Use between 3 and 64 characters.</span></span>

5. <span data-ttu-id="4c141-119">Cung cấp **Địa chỉ máy chủ** cho tổ chức Common Data Service của bạn rồi chọn **Đăng nhập**.</span><span class="sxs-lookup"><span data-stu-id="4c141-119">Provide the **Server address** for your Common Data Service organization, and select **Sign in**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="4c141-120">![Hộp thoại để nhập địa chỉ máy chủ Common Data Service](media/enter-CDS-org-details.png)</span><span class="sxs-lookup"><span data-stu-id="4c141-120">![Dialog box to enter Common Data Service server address](media/enter-CDS-org-details.png)</span></span>

6. <span data-ttu-id="4c141-121">Chọn các thực thể bạn muốn nhập từ danh sách có sẵn.</span><span class="sxs-lookup"><span data-stu-id="4c141-121">Select the entities you want to ingest from the available list.</span></span>    

   > [!NOTE]
   > <span data-ttu-id="4c141-122">Nếu một số thực thể được chọn, thì chúng có thể được các ứng dụng khác của Dynamics 365 (chẳng hạn như Dynamics 365 Sales Insights hoặc Customer Service Insights) sử dụng.</span><span class="sxs-lookup"><span data-stu-id="4c141-122">If some entities are already selected, they might be used by other Dynamics 365 applications (such as Dynamics 365 Sales Insights or Customer Service Insights).</span></span> <span data-ttu-id="4c141-123">Bạn không thể thay đổi lựa chọn.</span><span class="sxs-lookup"><span data-stu-id="4c141-123">You can't change the selection.</span></span> <span data-ttu-id="4c141-124">Các thực thể này sẽ khả dụng sau khi nguồn dữ liệu được tạo.</span><span class="sxs-lookup"><span data-stu-id="4c141-124">These entities will be available once the data source is created.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="4c141-125">![Hộp thoại hiển thị danh sách các thực thể trong tổ chức Common Data Service](media/select-analytical-entities.png)</span><span class="sxs-lookup"><span data-stu-id="4c141-125">![Dialog box showing a list of entities in the Common Data Service org](media/select-analytical-entities.png)</span></span>

7. <span data-ttu-id="4c141-126">Lưu lựa chọn của bạn để bắt đầu đồng bộ hóa các thực thể được chọn với kho được quản lý Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="4c141-126">Save your selection to start syncing the selected entities to the Common Data Service managed lake.</span></span> <span data-ttu-id="4c141-127">Bạn sẽ tìm thấy kết nối mới được thêm vào trang **Nguồn dữ liệu**.</span><span class="sxs-lookup"><span data-stu-id="4c141-127">You'll find the newly added connection on the **Data sources** page.</span></span> <span data-ttu-id="4c141-128">Thực thể sẽ được xếp hàng để làm mới và hiển thị các thực thể được tính là 0 cho đến khi tất cả các thực thể được đồng bộ hóa.</span><span class="sxs-lookup"><span data-stu-id="4c141-128">It will be queued for refresh and show the entities count as 0 until all the entities are synced.</span></span>

<span data-ttu-id="4c141-129">Chỉ một nguồn dữ liệu của một môi trường có thể đồng thời sử dụng cùng một kho do Common Data Service quản lý.</span><span class="sxs-lookup"><span data-stu-id="4c141-129">Only one data source of an environment can simultaneously use the same Common Data Service managed lake.</span></span>

## <a name="edit-a-common-data-service-managed-lake-data-source"></a><span data-ttu-id="4c141-130">Chỉnh sửa nguồn dữ liệu của kho được quản lý Common Data Service</span><span class="sxs-lookup"><span data-stu-id="4c141-130">Edit a Common Data Service managed lake data source</span></span>

<span data-ttu-id="4c141-131">Bạn chỉ chỉnh sửa lựa chọn thực thể sau khi tạo nguồn dữ liệu.</span><span class="sxs-lookup"><span data-stu-id="4c141-131">You only edit the entity selection after creating the data source.</span></span> <span data-ttu-id="4c141-132">Ví dụ: nếu các thực thể bổ sung được thêm vào Common Data Service và bạn cũng muốn nhập chúng.</span><span class="sxs-lookup"><span data-stu-id="4c141-132">For example, if additional entities were added to Common Data Service and you want to import them too.</span></span>    
<span data-ttu-id="4c141-133">Cách kết nối với Common Data Service khác, [tạo nguồn dữ liệu mới](#connect-to-a-common-data-service-managed-lake).</span><span class="sxs-lookup"><span data-stu-id="4c141-133">To connect to a different Common Data Service, [create a new data source](#connect-to-a-common-data-service-managed-lake).</span></span>

1. <span data-ttu-id="4c141-134">Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Dữ liệu** > **Nguồn dữ liệu**.</span><span class="sxs-lookup"><span data-stu-id="4c141-134">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="4c141-135">Cạnh nguồn dữ liệu mà bạn muốn thay đổi, hãy chọn dấu chấm lửng.</span><span class="sxs-lookup"><span data-stu-id="4c141-135">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="4c141-136">Nhấp vào tùy chọn **Chỉnh sửa** trong danh sách.</span><span class="sxs-lookup"><span data-stu-id="4c141-136">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="4c141-137">Chọn các thực thể bổ sung từ danh sách các thực thể có sẵn rồi chọn **Lưu**.</span><span class="sxs-lookup"><span data-stu-id="4c141-137">Select additional entities from the available list of entities and select **Save**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]