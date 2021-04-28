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
ms.openlocfilehash: 0fc13d3ac0a5176637b6fe481dabe0b2aec11649
ms.sourcegitcommit: d89b19b2a3497722b78362aeee688ae7e94915d9
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 04/13/2021
ms.locfileid: "5887920"
---
# <a name="data-sources-overview"></a><span data-ttu-id="7741d-103">Tổng quan về nguồn dữ liệu</span><span class="sxs-lookup"><span data-stu-id="7741d-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="7741d-104">Khả năng thông tin chi tiết về đối tượng trong Dynamics 365 Customer Insights kết nối với dữ liệu từ nhiều nguồn.</span><span class="sxs-lookup"><span data-stu-id="7741d-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="7741d-105">Kết nối với nguồn dữ liệu thường được gọi là quá trình *nhập dữ liệu*.</span><span class="sxs-lookup"><span data-stu-id="7741d-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="7741d-106">Sau khi nhập dữ liệu, bạn có thể [thống nhất](data-unification.md) và thực hiện hành động trên nó.</span><span class="sxs-lookup"><span data-stu-id="7741d-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="7741d-107">Thêm nguồn dữ liệu</span><span class="sxs-lookup"><span data-stu-id="7741d-107">Add a data source</span></span>

<span data-ttu-id="7741d-108">Tham khảo các bài viết chi tiết về cách thêm nguồn dữ liệu, tùy thuộc vào tùy chọn bạn chọn.</span><span class="sxs-lookup"><span data-stu-id="7741d-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="7741d-109">Bạn có thể thêm nguồn dữ liệu theo ba cách chính:</span><span class="sxs-lookup"><span data-stu-id="7741d-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="7741d-110">Thông qua hàng chục trình kết nối Power Query</span><span class="sxs-lookup"><span data-stu-id="7741d-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="7741d-111">Từ thư mục Common Data Model</span><span class="sxs-lookup"><span data-stu-id="7741d-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="7741d-112">Từ kho lưu trữ Common Data Service của riêng bạn</span><span class="sxs-lookup"><span data-stu-id="7741d-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a><span data-ttu-id="7741d-113">Thêm dữ liệu từ nguồn dữ liệu tại chỗ</span><span class="sxs-lookup"><span data-stu-id="7741d-113">Add data from on-premises data sources</span></span>

<span data-ttu-id="7741d-114">Việc nhập dữ liệu từ nguồn dữ liệu tại chỗ trong Audience Insights được hỗ trợ dựa trên luồng dữ liệu Power Platform.</span><span class="sxs-lookup"><span data-stu-id="7741d-114">Ingesting data from on-premises data sources in Audience Insights is supported based on Power Platform dataflows.</span></span> <span data-ttu-id="7741d-115">Bạn có thể bật luồng dữ liệu trong Customer Insights bằng cách [cung cấp URL môi trường Microsoft Dataverse](manage-environments.md#create-an-environment-in-an-existing-organization) khi thiết lập môi trường.</span><span class="sxs-lookup"><span data-stu-id="7741d-115">Dataflows can be enabled in Customer Insights by [providing the Microsoft Dataverse environment URL](manage-environments.md#create-an-environment-in-an-existing-organization) when setting up the environment.</span></span>

<span data-ttu-id="7741d-116">Nguồn dữ liệu được tạo sau khi liên kết một môi trường Dataverse với Customer Insights sẽ sử dụng [luồng dữ liệu Power Platform](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) theo mặc định.</span><span class="sxs-lookup"><span data-stu-id="7741d-116">Data sources that are created after associating a Dataverse environment with Customer Insights will use [Power Platform dataflows](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) by default.</span></span> <span data-ttu-id="7741d-117">Luồng dữ liệu hỗ trợ kết nối tại chỗ bằng cách sử dụng các cổng dữ liệu.</span><span class="sxs-lookup"><span data-stu-id="7741d-117">Dataflows support on-prem connectivity using the data gateways.</span></span> <span data-ttu-id="7741d-118">Loại bỏ và tái tạo các nguồn dữ liệu đã tồn tại trước khi môi trường Dataverse được liên kết để sử dụng cổng dữ liệu tại chỗ.</span><span class="sxs-lookup"><span data-stu-id="7741d-118">Remove and recreate data sources that existed before a Dataverse environment was associated to use the on-premises data gateways.</span></span>

<span data-ttu-id="7741d-119">Cổng dữ liệu từ một môi trường Power BI hoặc Power Apps hiện có sẽ hiển thị và bạn có thể sử dụng lại trong Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="7741d-119">Data gateways from an existing Power BI or Power Apps environment will be visible and you can reuse in Customer Insights.</span></span> <span data-ttu-id="7741d-120">Trang nguồn dữ liệu hiển thị các liên kết để chuyển đến môi trường Power Platform nơi bạn có thể xem và đặt cấu hình cổng dữ liệu tại chỗ.</span><span class="sxs-lookup"><span data-stu-id="7741d-120">The data sources page shows links to go the Power Platform environment where you can view and configure on-premises data gateways.</span></span>

:::image type="content" source="media/data-sources-onpremises-gateways.png" alt-text="Ảnh chụp màn hình của trang nguồn dữ liệu hiển thị các liên kết trỏ đến môi trường Power Platform.":::

## <a name="review-ingested-data"></a><span data-ttu-id="7741d-122">Xem lại dữ liệu đã nhập</span><span class="sxs-lookup"><span data-stu-id="7741d-122">Review ingested data</span></span>

<span data-ttu-id="7741d-123">Bạn sẽ thấy tên của mỗi nguồn dữ liệu đã nhập, trạng thái của nó và lần cuối cùng dữ liệu được làm mới cho nguồn đó.</span><span class="sxs-lookup"><span data-stu-id="7741d-123">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="7741d-124">Bạn có thể sắp xếp danh sách nguồn dữ liệu theo mọi cột.</span><span class="sxs-lookup"><span data-stu-id="7741d-124">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="7741d-125">![Nguồn dữ liệu đã thêm](media/configure-data-datasource-added.png "Nguồn dữ liệu đã thêm")</span><span class="sxs-lookup"><span data-stu-id="7741d-125">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="7741d-126">Trạng thái</span><span class="sxs-lookup"><span data-stu-id="7741d-126">Status</span></span>  |<span data-ttu-id="7741d-127">Nội dung mô tả</span><span class="sxs-lookup"><span data-stu-id="7741d-127">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="7741d-128">Thành công</span><span class="sxs-lookup"><span data-stu-id="7741d-128">Successful</span></span>   |<span data-ttu-id="7741d-129">Nguồn dữ liệu đã được nhập thành công nếu thời gian được đề cập trong cột **Làm mới**.</span><span class="sxs-lookup"><span data-stu-id="7741d-129">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="7741d-130">Chưa bắt đầu</span><span class="sxs-lookup"><span data-stu-id="7741d-130">Not started</span></span>   |<span data-ttu-id="7741d-131">Nguồn dữ liệu chưa nhập dữ liệu nào hoặc vẫn ở chế độ nháp.</span><span class="sxs-lookup"><span data-stu-id="7741d-131">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="7741d-132">Làm mới</span><span class="sxs-lookup"><span data-stu-id="7741d-132">Refreshing</span></span>    |<span data-ttu-id="7741d-133">Đang nhập dữ liệu.</span><span class="sxs-lookup"><span data-stu-id="7741d-133">Data ingestion is in progress.</span></span> <span data-ttu-id="7741d-134">Bạn có thể hủy thao tác này bằng cách chọn **Ngừng làm mới** trong cột **Hành động**.</span><span class="sxs-lookup"><span data-stu-id="7741d-134">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="7741d-135">Dừng việc làm mới nguồn dữ liệu sẽ hoàn nguyên nguồn dữ liệu về trạng thái làm mới cuối cùng.</span><span class="sxs-lookup"><span data-stu-id="7741d-135">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="7741d-136">Không thành công</span><span class="sxs-lookup"><span data-stu-id="7741d-136">Failed</span></span>     |<span data-ttu-id="7741d-137">Phiên nhập dữ liệu gặp lỗi.</span><span class="sxs-lookup"><span data-stu-id="7741d-137">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="7741d-138">Chọn giá trị trong cột **Trạng thái** của bất kỳ nguồn dữ liệu nào để xem xét thêm chi tiết.</span><span class="sxs-lookup"><span data-stu-id="7741d-138">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="7741d-139">Trong ngăn **Chi tiết tiến độ**, hãy mở rộng **Nguồn dữ liệu**.</span><span class="sxs-lookup"><span data-stu-id="7741d-139">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="7741d-140">Chọn **Xem chi tiết** để xem thêm thông tin về trạng thái làm mới, bao gồm chi tiết lỗi và cập nhật quy trình xuôi dòng.</span><span class="sxs-lookup"><span data-stu-id="7741d-140">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="7741d-141">Việc tải dữ liệu có thể mất chút thời gian.</span><span class="sxs-lookup"><span data-stu-id="7741d-141">Loading data can take some time.</span></span> <span data-ttu-id="7741d-142">Sau khi làm mới thành công, dữ liệu đã nhập có thể được xem xét từ trang **Các thực thể**.</span><span class="sxs-lookup"><span data-stu-id="7741d-142">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="7741d-143">Để biết thêm thông tin, hãy xem [Các thực thể](entities.md).</span><span class="sxs-lookup"><span data-stu-id="7741d-143">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="7741d-144">Làm mới nguồn dữ liệu</span><span class="sxs-lookup"><span data-stu-id="7741d-144">Refresh a data source</span></span>

<span data-ttu-id="7741d-145">Nguồn dữ liệu có thể được làm mới theo lịch trình tự động hoặc được làm mới theo cách thủ công theo yêu cầu.</span><span class="sxs-lookup"><span data-stu-id="7741d-145">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="7741d-146">Đi đến **Quản trị viên** > **Hệ thống** > [**Lịch trình**](system.md#schedule-tab) để định cấu hình làm mới theo lịch của tất cả các nguồn dữ liệu đã nhập của bạn.</span><span class="sxs-lookup"><span data-stu-id="7741d-146">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="7741d-147">Để làm mới nguồn dữ liệu theo yêu cầu, hãy làm theo các bước sau:</span><span class="sxs-lookup"><span data-stu-id="7741d-147">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="7741d-148">Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Dữ liệu** > **Nguồn dữ liệu**</span><span class="sxs-lookup"><span data-stu-id="7741d-148">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="7741d-149">Chọn dấu ba chấm dọc bên cạnh nguồn dữ liệu bạn muốn làm mới và chọn **Làm mới** từ danh sách thả xuống.</span><span class="sxs-lookup"><span data-stu-id="7741d-149">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="7741d-150">Nguồn dữ liệu hiện đã được kích hoạt để làm mới thủ công.</span><span class="sxs-lookup"><span data-stu-id="7741d-150">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="7741d-151">Việc làm mới nguồn dữ liệu sẽ cập nhật cả giản đồ thực thể và dữ liệu cho tất cả các thực thể được chỉ định trong nguồn dữ liệu.</span><span class="sxs-lookup"><span data-stu-id="7741d-151">Refreshing a data source will update both the entity schema and data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="7741d-152">Chọn **Dừng làm mới** nếu bạn muốn hủy quá trình làm mới hiện có và nguồn dữ liệu sẽ hoàn nguyên về trạng thái làm mới cuối cùng.</span><span class="sxs-lookup"><span data-stu-id="7741d-152">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="7741d-153">Xóa nguồn dữ liệu</span><span class="sxs-lookup"><span data-stu-id="7741d-153">Delete a data source</span></span>

1. <span data-ttu-id="7741d-154">Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Dữ liệu** > **Nguồn dữ liệu**.</span><span class="sxs-lookup"><span data-stu-id="7741d-154">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="7741d-155">Chọn dấu chấm lửng dọc bên cạnh nguồn dữ liệu bạn muốn xóa và chọn **Xóa** từ menu thả xuống.</span><span class="sxs-lookup"><span data-stu-id="7741d-155">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="7741d-156">Xác nhận tác vụ xóa của bạn.</span><span class="sxs-lookup"><span data-stu-id="7741d-156">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
