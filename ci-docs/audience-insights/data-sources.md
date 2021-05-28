---
title: Sử dụng nguồn dữ liệu để nhập dữ liệu
description: Tìm hiểu cách nhập dữ liệu từ nhiều nguồn khác nhau.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 3c0b4690e18285aa37eef481b3cfac951884ead6
ms.sourcegitcommit: fcc94f55dc2dce84eae188d582801dc47696c9cc
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 05/20/2021
ms.locfileid: "6085556"
---
# <a name="data-sources-overview"></a><span data-ttu-id="24547-103">Tổng quan về nguồn dữ liệu</span><span class="sxs-lookup"><span data-stu-id="24547-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="24547-104">Khả năng thông tin chi tiết về đối tượng trong Dynamics 365 Customer Insights kết nối với dữ liệu từ nhiều nguồn.</span><span class="sxs-lookup"><span data-stu-id="24547-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="24547-105">Kết nối với nguồn dữ liệu thường được gọi là quá trình *nhập dữ liệu*.</span><span class="sxs-lookup"><span data-stu-id="24547-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="24547-106">Sau khi nhập dữ liệu, bạn có thể [thống nhất](data-unification.md) và thực hiện hành động trên nó.</span><span class="sxs-lookup"><span data-stu-id="24547-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="24547-107">Thêm nguồn dữ liệu</span><span class="sxs-lookup"><span data-stu-id="24547-107">Add a data source</span></span>

<span data-ttu-id="24547-108">Tham khảo các bài viết chi tiết về cách thêm nguồn dữ liệu, tùy thuộc vào tùy chọn bạn chọn.</span><span class="sxs-lookup"><span data-stu-id="24547-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="24547-109">Bạn có thể thêm nguồn dữ liệu theo ba cách chính:</span><span class="sxs-lookup"><span data-stu-id="24547-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="24547-110">Thông qua hàng chục trình kết nối Power Query</span><span class="sxs-lookup"><span data-stu-id="24547-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="24547-111">Từ thư mục Common Data Model</span><span class="sxs-lookup"><span data-stu-id="24547-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="24547-112">Từ kho lưu trữ Common Data Service của riêng bạn</span><span class="sxs-lookup"><span data-stu-id="24547-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a><span data-ttu-id="24547-113">Thêm dữ liệu từ nguồn dữ liệu tại chỗ</span><span class="sxs-lookup"><span data-stu-id="24547-113">Add data from on-premises data sources</span></span>

<span data-ttu-id="24547-114">Việc nhập dữ liệu từ nguồn dữ liệu tại chỗ trong Audience Insights được hỗ trợ dựa trên luồng dữ liệu Power Platform.</span><span class="sxs-lookup"><span data-stu-id="24547-114">Ingesting data from on-premises data sources in Audience Insights is supported based on Power Platform dataflows.</span></span> <span data-ttu-id="24547-115">Bạn có thể bật luồng dữ liệu trong Customer Insights bằng cách [cung cấp URL môi trường Microsoft Dataverse](manage-environments.md#create-an-environment-in-an-existing-organization) khi thiết lập môi trường.</span><span class="sxs-lookup"><span data-stu-id="24547-115">Dataflows can be enabled in Customer Insights by [providing the Microsoft Dataverse environment URL](manage-environments.md#create-an-environment-in-an-existing-organization) when setting up the environment.</span></span>

<span data-ttu-id="24547-116">Nguồn dữ liệu được tạo sau khi liên kết một môi trường Dataverse với Customer Insights sẽ sử dụng [luồng dữ liệu Power Platform](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) theo mặc định.</span><span class="sxs-lookup"><span data-stu-id="24547-116">Data sources that are created after associating a Dataverse environment with Customer Insights will use [Power Platform dataflows](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) by default.</span></span> <span data-ttu-id="24547-117">Luồng dữ liệu hỗ trợ kết nối tại chỗ bằng cách sử dụng cổng dữ liệu.</span><span class="sxs-lookup"><span data-stu-id="24547-117">Dataflows support on-premises connectivity using the data gateway.</span></span> <span data-ttu-id="24547-118">Loại bỏ và tái tạo các nguồn dữ liệu đã tồn tại trước khi môi trường Dataverse được liên kết để [sử dụng cổng dữ liệu tại chỗ](/powerapps/maker/data-platform/using-dataflows-with-on-premises-data.md).</span><span class="sxs-lookup"><span data-stu-id="24547-118">Remove and recreate data sources that existed before a Dataverse environment was associated to [use the on-premises data gateways](/powerapps/maker/data-platform/using-dataflows-with-on-premises-data.md).</span></span>

<span data-ttu-id="24547-119">Cổng dữ liệu từ một môi trường Power BI hoặc Power Apps hiện có sẽ hiển thị và bạn có thể sử dụng lại trong Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="24547-119">Data gateways from an existing Power BI or Power Apps environment will be visible and you can reuse in Customer Insights.</span></span> <span data-ttu-id="24547-120">Trang nguồn dữ liệu hiển thị các liên kết để chuyển đến môi trường Power Platform nơi bạn có thể xem và đặt cấu hình cổng dữ liệu tại chỗ.</span><span class="sxs-lookup"><span data-stu-id="24547-120">The data sources page shows links to go the Power Platform environment where you can view and configure on-premises data gateways.</span></span>

## <a name="review-ingested-data"></a><span data-ttu-id="24547-121">Xem lại dữ liệu đã nhập</span><span class="sxs-lookup"><span data-stu-id="24547-121">Review ingested data</span></span>

<span data-ttu-id="24547-122">Bạn sẽ thấy tên của mỗi nguồn dữ liệu đã nhập, trạng thái của nó và lần cuối cùng dữ liệu được làm mới cho nguồn đó.</span><span class="sxs-lookup"><span data-stu-id="24547-122">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="24547-123">Bạn có thể sắp xếp danh sách nguồn dữ liệu theo mọi cột.</span><span class="sxs-lookup"><span data-stu-id="24547-123">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="24547-124">![Nguồn dữ liệu đã thêm](media/configure-data-datasource-added.png "Nguồn dữ liệu đã thêm")</span><span class="sxs-lookup"><span data-stu-id="24547-124">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="24547-125">Trạng thái</span><span class="sxs-lookup"><span data-stu-id="24547-125">Status</span></span>  |<span data-ttu-id="24547-126">Nội dung mô tả</span><span class="sxs-lookup"><span data-stu-id="24547-126">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="24547-127">Thành công</span><span class="sxs-lookup"><span data-stu-id="24547-127">Successful</span></span>   |<span data-ttu-id="24547-128">Nguồn dữ liệu đã được nhập thành công nếu thời gian được đề cập trong cột **Làm mới**.</span><span class="sxs-lookup"><span data-stu-id="24547-128">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="24547-129">Chưa bắt đầu</span><span class="sxs-lookup"><span data-stu-id="24547-129">Not started</span></span>   |<span data-ttu-id="24547-130">Nguồn dữ liệu chưa nhập dữ liệu nào hoặc vẫn ở chế độ nháp.</span><span class="sxs-lookup"><span data-stu-id="24547-130">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="24547-131">Làm mới</span><span class="sxs-lookup"><span data-stu-id="24547-131">Refreshing</span></span>    |<span data-ttu-id="24547-132">Đang nhập dữ liệu.</span><span class="sxs-lookup"><span data-stu-id="24547-132">Data ingestion is in progress.</span></span> <span data-ttu-id="24547-133">Bạn có thể hủy thao tác này bằng cách chọn **Ngừng làm mới** trong cột **Hành động**.</span><span class="sxs-lookup"><span data-stu-id="24547-133">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="24547-134">Dừng việc làm mới nguồn dữ liệu sẽ hoàn nguyên nguồn dữ liệu về trạng thái làm mới cuối cùng.</span><span class="sxs-lookup"><span data-stu-id="24547-134">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="24547-135">Không thành công</span><span class="sxs-lookup"><span data-stu-id="24547-135">Failed</span></span>     |<span data-ttu-id="24547-136">Phiên nhập dữ liệu gặp lỗi.</span><span class="sxs-lookup"><span data-stu-id="24547-136">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="24547-137">Chọn giá trị trong cột **Trạng thái** của bất kỳ nguồn dữ liệu nào để xem xét thêm chi tiết.</span><span class="sxs-lookup"><span data-stu-id="24547-137">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="24547-138">Trong ngăn **Chi tiết tiến độ**, hãy mở rộng **Nguồn dữ liệu**.</span><span class="sxs-lookup"><span data-stu-id="24547-138">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="24547-139">Chọn **Xem chi tiết** để xem thêm thông tin về trạng thái làm mới, bao gồm chi tiết lỗi và cập nhật quy trình xuôi dòng.</span><span class="sxs-lookup"><span data-stu-id="24547-139">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="24547-140">Việc tải dữ liệu có thể mất chút thời gian.</span><span class="sxs-lookup"><span data-stu-id="24547-140">Loading data can take some time.</span></span> <span data-ttu-id="24547-141">Sau khi làm mới thành công, dữ liệu đã nhập có thể được xem xét từ trang **Các thực thể**.</span><span class="sxs-lookup"><span data-stu-id="24547-141">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="24547-142">Để biết thêm thông tin, hãy xem [Các thực thể](entities.md).</span><span class="sxs-lookup"><span data-stu-id="24547-142">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="24547-143">Làm mới nguồn dữ liệu</span><span class="sxs-lookup"><span data-stu-id="24547-143">Refresh a data source</span></span>

<span data-ttu-id="24547-144">Nguồn dữ liệu có thể được làm mới theo lịch trình tự động hoặc được làm mới theo cách thủ công theo yêu cầu.</span><span class="sxs-lookup"><span data-stu-id="24547-144">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="24547-145">Đi đến **Quản trị viên** > **Hệ thống** > [**Lịch trình**](system.md#schedule-tab) để định cấu hình làm mới theo lịch của tất cả các nguồn dữ liệu đã nhập của bạn.</span><span class="sxs-lookup"><span data-stu-id="24547-145">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="24547-146">Để làm mới nguồn dữ liệu theo yêu cầu, hãy làm theo các bước sau:</span><span class="sxs-lookup"><span data-stu-id="24547-146">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="24547-147">Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Dữ liệu** > **Nguồn dữ liệu**</span><span class="sxs-lookup"><span data-stu-id="24547-147">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="24547-148">Chọn dấu ba chấm dọc bên cạnh nguồn dữ liệu bạn muốn làm mới và chọn **Làm mới** từ danh sách thả xuống.</span><span class="sxs-lookup"><span data-stu-id="24547-148">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="24547-149">Nguồn dữ liệu hiện đã được kích hoạt để làm mới thủ công.</span><span class="sxs-lookup"><span data-stu-id="24547-149">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="24547-150">Việc làm mới nguồn dữ liệu sẽ cập nhật cả giản đồ thực thể và dữ liệu cho tất cả các thực thể được chỉ định trong nguồn dữ liệu.</span><span class="sxs-lookup"><span data-stu-id="24547-150">Refreshing a data source will update both the entity schema and data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="24547-151">Chọn **Dừng làm mới** nếu bạn muốn hủy quá trình làm mới hiện có và nguồn dữ liệu sẽ hoàn nguyên về trạng thái làm mới cuối cùng.</span><span class="sxs-lookup"><span data-stu-id="24547-151">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="24547-152">Xóa nguồn dữ liệu</span><span class="sxs-lookup"><span data-stu-id="24547-152">Delete a data source</span></span>

1. <span data-ttu-id="24547-153">Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Dữ liệu** > **Nguồn dữ liệu**.</span><span class="sxs-lookup"><span data-stu-id="24547-153">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="24547-154">Chọn dấu chấm lửng dọc bên cạnh nguồn dữ liệu bạn muốn xóa và chọn **Xóa** từ menu thả xuống.</span><span class="sxs-lookup"><span data-stu-id="24547-154">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="24547-155">Xác nhận tác vụ xóa của bạn.</span><span class="sxs-lookup"><span data-stu-id="24547-155">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
