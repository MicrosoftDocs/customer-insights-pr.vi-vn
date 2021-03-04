---
title: Sử dụng nguồn dữ liệu để nhập dữ liệu
description: Tìm hiểu cách nhập dữ liệu từ nhiều nguồn khác nhau.
ms.date: 11/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 68aa1b56fb634da80a0c64db72f778d57507104d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269724"
---
# <a name="data-sources-overview"></a><span data-ttu-id="fe358-103">Tổng quan về nguồn dữ liệu</span><span class="sxs-lookup"><span data-stu-id="fe358-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="fe358-104">Khả năng thông tin chi tiết về đối tượng trong Dynamics 365 Customer Insights kết nối với dữ liệu từ nhiều nguồn.</span><span class="sxs-lookup"><span data-stu-id="fe358-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="fe358-105">Kết nối với nguồn dữ liệu thường được gọi là quá trình *nhập dữ liệu*.</span><span class="sxs-lookup"><span data-stu-id="fe358-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="fe358-106">Sau khi nhập dữ liệu, bạn có thể [thống nhất](data-unification.md) và thực hiện hành động trên nó.</span><span class="sxs-lookup"><span data-stu-id="fe358-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="fe358-107">Thêm nguồn dữ liệu</span><span class="sxs-lookup"><span data-stu-id="fe358-107">Add a data source</span></span>

<span data-ttu-id="fe358-108">Tham khảo các bài viết chi tiết về cách thêm nguồn dữ liệu, tùy thuộc vào tùy chọn bạn chọn.</span><span class="sxs-lookup"><span data-stu-id="fe358-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="fe358-109">Bạn có thể thêm nguồn dữ liệu theo ba cách chính:</span><span class="sxs-lookup"><span data-stu-id="fe358-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="fe358-110">Thông qua hàng chục trình kết nối Power Query</span><span class="sxs-lookup"><span data-stu-id="fe358-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="fe358-111">Từ thư mục Common Data Model</span><span class="sxs-lookup"><span data-stu-id="fe358-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="fe358-112">Từ kho lưu trữ Common Data Service của riêng bạn</span><span class="sxs-lookup"><span data-stu-id="fe358-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

> [!NOTE]
> <span data-ttu-id="fe358-113">Bạn chưa thể thêm dữ liệu từ nguồn dữ liệu tại chỗ.</span><span class="sxs-lookup"><span data-stu-id="fe358-113">You can't add data from on-premises data sources yet.</span></span>

## <a name="review-ingested-data"></a><span data-ttu-id="fe358-114">Xem lại dữ liệu đã nhập</span><span class="sxs-lookup"><span data-stu-id="fe358-114">Review ingested data</span></span>

<span data-ttu-id="fe358-115">Bạn sẽ thấy tên của mỗi nguồn dữ liệu đã nhập, trạng thái của nó và lần cuối cùng dữ liệu được làm mới cho nguồn đó.</span><span class="sxs-lookup"><span data-stu-id="fe358-115">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="fe358-116">Bạn có thể sắp xếp danh sách nguồn dữ liệu theo mọi cột.</span><span class="sxs-lookup"><span data-stu-id="fe358-116">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="fe358-117">![Nguồn dữ liệu đã thêm](media/configure-data-datasource-added.png "Nguồn dữ liệu đã thêm")</span><span class="sxs-lookup"><span data-stu-id="fe358-117">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="fe358-118">Trạng thái</span><span class="sxs-lookup"><span data-stu-id="fe358-118">Status</span></span>  |<span data-ttu-id="fe358-119">Nội dung mô tả</span><span class="sxs-lookup"><span data-stu-id="fe358-119">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="fe358-120">Thành công</span><span class="sxs-lookup"><span data-stu-id="fe358-120">Successful</span></span>   |<span data-ttu-id="fe358-121">Nguồn dữ liệu đã được nhập thành công nếu thời gian được đề cập trong cột **Làm mới**.</span><span class="sxs-lookup"><span data-stu-id="fe358-121">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="fe358-122">Chưa bắt đầu</span><span class="sxs-lookup"><span data-stu-id="fe358-122">Not started</span></span>   |<span data-ttu-id="fe358-123">Nguồn dữ liệu chưa nhập dữ liệu nào hoặc vẫn ở chế độ nháp.</span><span class="sxs-lookup"><span data-stu-id="fe358-123">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="fe358-124">Làm mới</span><span class="sxs-lookup"><span data-stu-id="fe358-124">Refreshing</span></span>    |<span data-ttu-id="fe358-125">Đang nhập dữ liệu.</span><span class="sxs-lookup"><span data-stu-id="fe358-125">Data ingestion is in progress.</span></span> <span data-ttu-id="fe358-126">Bạn có thể hủy thao tác này bằng cách chọn **Ngừng làm mới** trong cột **Hành động**.</span><span class="sxs-lookup"><span data-stu-id="fe358-126">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="fe358-127">Dừng việc làm mới nguồn dữ liệu sẽ hoàn nguyên nguồn dữ liệu về trạng thái làm mới cuối cùng.</span><span class="sxs-lookup"><span data-stu-id="fe358-127">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="fe358-128">Không thành công</span><span class="sxs-lookup"><span data-stu-id="fe358-128">Failed</span></span>     |<span data-ttu-id="fe358-129">Phiên nhập dữ liệu gặp lỗi.</span><span class="sxs-lookup"><span data-stu-id="fe358-129">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="fe358-130">Chọn giá trị trong cột **Trạng thái** của bất kỳ nguồn dữ liệu nào để xem xét thêm chi tiết.</span><span class="sxs-lookup"><span data-stu-id="fe358-130">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="fe358-131">Trong ngăn **Chi tiết tiến độ**, hãy mở rộng **Nguồn dữ liệu**.</span><span class="sxs-lookup"><span data-stu-id="fe358-131">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="fe358-132">Chọn **Xem chi tiết** để xem thêm thông tin về trạng thái làm mới, bao gồm chi tiết lỗi và cập nhật quy trình xuôi dòng.</span><span class="sxs-lookup"><span data-stu-id="fe358-132">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="fe358-133">Việc tải dữ liệu có thể mất chút thời gian.</span><span class="sxs-lookup"><span data-stu-id="fe358-133">Loading data can take some time.</span></span> <span data-ttu-id="fe358-134">Sau khi làm mới thành công, dữ liệu đã nhập có thể được xem xét từ trang **Các thực thể**.</span><span class="sxs-lookup"><span data-stu-id="fe358-134">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="fe358-135">Để biết thêm thông tin, hãy xem [Các thực thể](entities.md).</span><span class="sxs-lookup"><span data-stu-id="fe358-135">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="fe358-136">Làm mới nguồn dữ liệu</span><span class="sxs-lookup"><span data-stu-id="fe358-136">Refresh a data source</span></span>

<span data-ttu-id="fe358-137">Nguồn dữ liệu có thể được làm mới theo lịch trình tự động hoặc được làm mới theo cách thủ công theo yêu cầu.</span><span class="sxs-lookup"><span data-stu-id="fe358-137">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="fe358-138">Đi đến **Quản trị viên** > **Hệ thống** > [**Lịch trình**](system.md#schedule-tab) để định cấu hình làm mới theo lịch của tất cả các nguồn dữ liệu đã nhập của bạn.</span><span class="sxs-lookup"><span data-stu-id="fe358-138">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="fe358-139">Để làm mới nguồn dữ liệu theo yêu cầu, hãy làm theo các bước sau:</span><span class="sxs-lookup"><span data-stu-id="fe358-139">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="fe358-140">Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Dữ liệu** > **Nguồn dữ liệu**</span><span class="sxs-lookup"><span data-stu-id="fe358-140">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="fe358-141">Chọn dấu ba chấm dọc bên cạnh nguồn dữ liệu bạn muốn làm mới và chọn **Làm mới** từ danh sách thả xuống.</span><span class="sxs-lookup"><span data-stu-id="fe358-141">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="fe358-142">Nguồn dữ liệu hiện đã được kích hoạt để làm mới thủ công.</span><span class="sxs-lookup"><span data-stu-id="fe358-142">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="fe358-143">Làm mới nguồn dữ liệu sẽ cập nhật cả giản đồ thực thể cũng như dữ liệu cho tất cả các thực thể được chỉ định trong nguồn dữ liệu.</span><span class="sxs-lookup"><span data-stu-id="fe358-143">Refreshing a data source will update both the entity schema as well as data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="fe358-144">Chọn **Dừng làm mới** nếu bạn muốn hủy quá trình làm mới hiện có và nguồn dữ liệu sẽ hoàn nguyên về trạng thái làm mới cuối cùng.</span><span class="sxs-lookup"><span data-stu-id="fe358-144">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="fe358-145">Xóa nguồn dữ liệu</span><span class="sxs-lookup"><span data-stu-id="fe358-145">Delete a data source</span></span>

1. <span data-ttu-id="fe358-146">Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Dữ liệu** > **Nguồn dữ liệu**.</span><span class="sxs-lookup"><span data-stu-id="fe358-146">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="fe358-147">Chọn dấu chấm lửng dọc bên cạnh nguồn dữ liệu bạn muốn xóa và chọn **Xóa** từ menu thả xuống.</span><span class="sxs-lookup"><span data-stu-id="fe358-147">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="fe358-148">Xác nhận tác vụ xóa của bạn.</span><span class="sxs-lookup"><span data-stu-id="fe358-148">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]