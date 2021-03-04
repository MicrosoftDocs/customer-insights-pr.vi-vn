---
title: Nhập dữ liệu thông qua trình kết nối Power Query
description: Trình kết nối cho nguồn dữ liệu dựa trên Power Query.
ms.date: 09/29/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d51a7efa5fd9f7336d1662500eb804a674738493
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267802"
---
# <a name="connect-to-a-power-query-data-source"></a><span data-ttu-id="6f19e-103">Kết nối với nguồn dữ liệu Power Query</span><span class="sxs-lookup"><span data-stu-id="6f19e-103">Connect to a Power Query data source</span></span>

<span data-ttu-id="6f19e-104">Power Query cung cấp một loạt các trình kết nối để nhập dữ liệu.</span><span class="sxs-lookup"><span data-stu-id="6f19e-104">Power Query offers a broad set of connectors to ingest data.</span></span> <span data-ttu-id="6f19e-105">Hầu hết các trình kết nối này được hỗ trợ bởi Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="6f19e-105">Most of these connectors are supported by Dynamics 365 Customer Insights.</span></span> <span data-ttu-id="6f19e-106">Việc thêm nguồn dữ liệu dựa trên trình kết nối Power Query thường tuân theo các bước được nêu trong phần tiếp theo.</span><span class="sxs-lookup"><span data-stu-id="6f19e-106">Adding data sources based on Power Query connectors generally follows the steps outlined in the next section.</span></span> <span data-ttu-id="6f19e-107">Tuy nhiên, tùy thuộc vào trình kết nối bạn sử dụng, bạn sẽ cần dùng thông tin khác nhau.</span><span class="sxs-lookup"><span data-stu-id="6f19e-107">However, depending on the connector you use, different information is required.</span></span> <span data-ttu-id="6f19e-108">Để biết thêm thông tin, hãy xem tài liệu về các trình kết nối riêng lẻ trong [tham khảo trình kết nối Power Query](https://docs.microsoft.com/power-query/connectors/).</span><span class="sxs-lookup"><span data-stu-id="6f19e-108">For more information, see the documentation about individual connectors in the [Power Query connector reference](https://docs.microsoft.com/power-query/connectors/).</span></span>

## <a name="create-a-new-data-source"></a><span data-ttu-id="6f19e-109">Tạo một nguồn dữ liệu mới</span><span class="sxs-lookup"><span data-stu-id="6f19e-109">Create a new data source</span></span>

1. <span data-ttu-id="6f19e-110">Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Dữ liệu** > **Nguồn dữ liệu**.</span><span class="sxs-lookup"><span data-stu-id="6f19e-110">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="6f19e-111">Chọn **Thêm nguồn dữ liệu**.</span><span class="sxs-lookup"><span data-stu-id="6f19e-111">Select **Add data source**.</span></span>

1. <span data-ttu-id="6f19e-112">Chọn phương thức **Nhập dữ liệu** và chọn **Tiếp theo**.</span><span class="sxs-lookup"><span data-stu-id="6f19e-112">Choose the **Import data** method and select **Next**.</span></span>

1. <span data-ttu-id="6f19e-113">Cung cấp một **Tên** cho nguồn dữ liệu và chọn **Tiếp theo** để tạo nguồn dữ liệu.</span><span class="sxs-lookup"><span data-stu-id="6f19e-113">Provide a **Name** for the data source, and select **Next** to create the data source.</span></span> <span data-ttu-id="6f19e-114">Hướng dẫn về tên:</span><span class="sxs-lookup"><span data-stu-id="6f19e-114">Name guidelines:</span></span> 
   - <span data-ttu-id="6f19e-115">Bắt đầu bằng một chữ cái.</span><span class="sxs-lookup"><span data-stu-id="6f19e-115">Start with a letter.</span></span>
   - <span data-ttu-id="6f19e-116">Chỉ sử dụng chữ cái và số.</span><span class="sxs-lookup"><span data-stu-id="6f19e-116">Use letters and numbers only.</span></span> <span data-ttu-id="6f19e-117">Không được phép nhập ký tự đặc biệt và khoảng trống.</span><span class="sxs-lookup"><span data-stu-id="6f19e-117">Special characters and spaces are not allowed.</span></span>
   - <span data-ttu-id="6f19e-118">Sử dụng từ 3 đến 64 ký tự.</span><span class="sxs-lookup"><span data-stu-id="6f19e-118">Use between 3 and 64 characters.</span></span>

1. <span data-ttu-id="6f19e-119">Chọn một trong các [trình kết nối có sẵn](#available-power-query-data-sources).</span><span class="sxs-lookup"><span data-stu-id="6f19e-119">Choose one of the [available connectors](#available-power-query-data-sources).</span></span> <span data-ttu-id="6f19e-120">Đối với ví dụ này, chúng tôi chọn trình kết nối **Văn bản/CSV**.</span><span class="sxs-lookup"><span data-stu-id="6f19e-120">For this example, we select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="6f19e-121">Nhập các chi tiết được yêu cầu trong **Cài đặt kết nối** cho trình kết nối đã chọn và chọn **Tiếp theo** để xem bản xem trước của dữ liệu.</span><span class="sxs-lookup"><span data-stu-id="6f19e-121">Enter the required details in the **Connection settings** for the selected connector and select **Next** to see a preview of the data.</span></span>

1. <span data-ttu-id="6f19e-122">Chọn **Chuyển đổi dữ liệu**.</span><span class="sxs-lookup"><span data-stu-id="6f19e-122">Select **Transform data**.</span></span> <span data-ttu-id="6f19e-123">Trong bước này, bạn sẽ thêm các thực thể vào nguồn dữ liệu của mình.</span><span class="sxs-lookup"><span data-stu-id="6f19e-123">In this step, you'll add entities to your data source.</span></span> <span data-ttu-id="6f19e-124">Thực thể là tập dữ liệu.</span><span class="sxs-lookup"><span data-stu-id="6f19e-124">Entities are datasets.</span></span> <span data-ttu-id="6f19e-125">Nếu bạn có một cơ sở dữ liệu bao gồm nhiều bộ dữ liệu, mỗi bộ dữ liệu là thực thể riêng của nó.</span><span class="sxs-lookup"><span data-stu-id="6f19e-125">If you have a database that includes multiple datasets, each dataset is its own entity.</span></span>

1. <span data-ttu-id="6f19e-126">Hộp thoại **Power Query - Chỉnh sửa truy vấn** cho phép bạn xem lại và tinh chỉnh dữ liệu.</span><span class="sxs-lookup"><span data-stu-id="6f19e-126">The **Power Query - Edit queries** dialog lets you review and refine the data.</span></span> <span data-ttu-id="6f19e-127">Các thực thể mà các hệ thống được xác định trong nguồn dữ liệu đã chọn của bạn xuất hiện trong ngăn bên trái.</span><span class="sxs-lookup"><span data-stu-id="6f19e-127">The entities that the systems identified in your selected data source appear in the left pane.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6f19e-128">![Hộp thoại Chỉnh sửa truy vấn](media/data-manager-configure-edit-queries.png "Hộp thoại Chỉnh sửa truy vấn")</span><span class="sxs-lookup"><span data-stu-id="6f19e-128">![Edit queries dialog](media/data-manager-configure-edit-queries.png "Edit queries dialog")</span></span>

1. <span data-ttu-id="6f19e-129">Bạn cũng có thể chuyển đổi dữ liệu của bạn.</span><span class="sxs-lookup"><span data-stu-id="6f19e-129">You can also transform your data.</span></span> <span data-ttu-id="6f19e-130">Chọn một thực thể để chỉnh sửa hoặc chuyển đổi.</span><span class="sxs-lookup"><span data-stu-id="6f19e-130">Select an entity to edit or transform.</span></span> <span data-ttu-id="6f19e-131">Sử dụng các tùy chọn trong cửa sổ Power Query để áp dụng các phép biến đổi.</span><span class="sxs-lookup"><span data-stu-id="6f19e-131">Use the options in the Power Query window to apply transformations.</span></span> <span data-ttu-id="6f19e-132">Mỗi chuyển đổi được liệt kê dưới **Các bước đã áp dụng**.</span><span class="sxs-lookup"><span data-stu-id="6f19e-132">Each transformation gets listed under **Applied steps**.</span></span> <span data-ttu-id="6f19e-133">Power Query cung cấp nhiều tùy chọn chuyển đổi được tạo sẵn.</span><span class="sxs-lookup"><span data-stu-id="6f19e-133">Power Query provides numerous pre-built transformation options.</span></span> <span data-ttu-id="6f19e-134">Xem [Chuyển đổi Power Query](https://docs.microsoft.com/power-query/power-query-what-is-power-query#transformations) để biết thêm thông tin.</span><span class="sxs-lookup"><span data-stu-id="6f19e-134">For more information, see [Power Query Transformations](https://docs.microsoft.com/power-query/power-query-what-is-power-query#transformations).</span></span>

1. <span data-ttu-id="6f19e-135">Bạn có thể thêm các thực thể bổ sung vào nguồn dữ liệu của mình bằng cách chọn **Lấy dữ liệu** trong hộp thoại **Chỉnh sửa truy vấn**.</span><span class="sxs-lookup"><span data-stu-id="6f19e-135">You can add additional entities to your data source by selecting **Get data** in the **Edit queries** dialog.</span></span>

   <span data-ttu-id="6f19e-136">Những chuyển đổi này rất được khuyến khích:</span><span class="sxs-lookup"><span data-stu-id="6f19e-136">These transformations are highly recommended:</span></span>

   - <span data-ttu-id="6f19e-137">Nếu bạn đang nhập dữ liệu từ tệp CSV, hàng đầu tiên thường chứa các tiêu đề.</span><span class="sxs-lookup"><span data-stu-id="6f19e-137">If you're ingesting data from a CSV file, the first row often contains headers.</span></span> <span data-ttu-id="6f19e-138">Đi đến **Bảng biến đổi** và chọn **Sử dụng tiêu đề làm hàng đầu tiên**.</span><span class="sxs-lookup"><span data-stu-id="6f19e-138">Go to **Transform table** and select **Use headers as first row**.</span></span>
   - <span data-ttu-id="6f19e-139">Đảm bảo loại dữ liệu được đặt phù hợp.</span><span class="sxs-lookup"><span data-stu-id="6f19e-139">Ensure the data type is set appropriately.</span></span>

1. <span data-ttu-id="6f19e-140">Chọn **Lưu** ở góc dưới bên phải cửa sổ Power Query để lưu mục chuyển đổi của bạn.</span><span class="sxs-lookup"><span data-stu-id="6f19e-140">Select **Save** at the bottom of the Power Query window to save the transformations.</span></span> <span data-ttu-id="6f19e-141">Sau khi lưu, bạn sẽ thấy nguồn dữ liệu của mình trên **Dữ liệu** > **Nguồn dữ liệu**.</span><span class="sxs-lookup"><span data-stu-id="6f19e-141">After saving, you'll find your data source on **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="6f19e-142">Trên trang **Nguồn dữ liệu**, bạn sẽ nhận thấy nguồn dữ liệu mới ở trạng thái **Làm mới**.</span><span class="sxs-lookup"><span data-stu-id="6f19e-142">On the **Data sources** page, you'll notice the new data source is in **Refreshing** status.</span></span>

## <a name="available-power-query-data-sources"></a><span data-ttu-id="6f19e-143">Nguồn dữ liệu Power Query có sẵn</span><span class="sxs-lookup"><span data-stu-id="6f19e-143">Available Power Query data sources</span></span>

<span data-ttu-id="6f19e-144">Xem [tham khảo trình kết nối Power Query](https://docs.microsoft.com/power-query/connectors/) để có danh sách cập nhật các trình kết nối mà bạn có thể chọn để nhập dữ liệu vào Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="6f19e-144">See the [Power Query connector reference](https://docs.microsoft.com/power-query/connectors/) for an up-to-date list of connectors that you can select to import data to Customer Insights.</span></span> 

<span data-ttu-id="6f19e-145">Các trình kết nối có dấu kiểm trong cột **Customer Insights (Luồng dữ liệu)** có sẵn để tạo nguồn dữ liệu mới dựa trên Power Query.</span><span class="sxs-lookup"><span data-stu-id="6f19e-145">Connectors with a checkmark in the **Customer Insights (Dataflows)** column are available to create new data sources based on Power Query.</span></span> <span data-ttu-id="6f19e-146">Xem lại tài liệu về một trình kết nối cụ thể để tìm hiểu thêm về các điều kiện tiên quyết, giới hạn và các chi tiết khác của nó.</span><span class="sxs-lookup"><span data-stu-id="6f19e-146">Review the documentation of a specific connector to learn more about its prerequisites, limitations, and other details.</span></span>

## <a name="edit-power-query-data-sources"></a><span data-ttu-id="6f19e-147">Chỉnh sửa nguồn dữ liệu Power Query</span><span class="sxs-lookup"><span data-stu-id="6f19e-147">Edit Power Query data sources</span></span>

> [!NOTE]
> <span data-ttu-id="6f19e-148">Có thể không thực hiện được thay đổi đối với các nguồn dữ liệu hiện đang được sử dụng trong một trong các quy trình của ứng dụng (*phân khúc*, *so khớp* hoặc *hợp nhất*).</span><span class="sxs-lookup"><span data-stu-id="6f19e-148">It might not be possible to make changes to data sources that are currently being used in one of the app's processes (*segmentation*, *match*, or *merge*, for example).</span></span> 
>
> <span data-ttu-id="6f19e-149">Sử dụng trang **Cài đặt**, bạn có thể theo dõi tiến trình của từng quá trình hoạt động.</span><span class="sxs-lookup"><span data-stu-id="6f19e-149">Using the **Settings** page, you can track the progress of each of the active processes.</span></span> <span data-ttu-id="6f19e-150">Khi một quá trình hoàn tất, bạn có thể quay lại trang **Nguồn dữ liệu** và thực hiện các thay đổi của bạn.</span><span class="sxs-lookup"><span data-stu-id="6f19e-150">When a process completes, you can return to the **Data Sources** page and make your changes.</span></span>

1. <span data-ttu-id="6f19e-151">Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Dữ liệu** > **Nguồn dữ liệu**.</span><span class="sxs-lookup"><span data-stu-id="6f19e-151">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="6f19e-152">Chọn dấu chấm lửng dọc bên cạnh nguồn dữ liệu bạn muốn thay đổi và chọn **Chỉnh sửa** từ menu thả xuống.</span><span class="sxs-lookup"><span data-stu-id="6f19e-152">Select the vertical ellipsis next to the data source you want to change and select **Edit** from the drop-down menu.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6f19e-153">![Tùy chọn chỉnh sửa](media/edit-option-data-sources.png "Tùy chọn chỉnh sửa")</span><span class="sxs-lookup"><span data-stu-id="6f19e-153">![Edit option](media/edit-option-data-sources.png "Edit option")</span></span>

3. <span data-ttu-id="6f19e-154">Áp dụng các thay đổi và chuyển đổi của bạn trong hộp thoại **Power Query - Chỉnh sửa truy vấn** như được mô tả trong phần [Tạo nguồn dữ liệu mới](#create-a-new-data-source).</span><span class="sxs-lookup"><span data-stu-id="6f19e-154">Apply your changes and transformations in the **Power Query - Edit queries** dialog as described in the [Create a new data source](#create-a-new-data-source) section.</span></span>

4. <span data-ttu-id="6f19e-155">Chọn **Lưu** trong Power Query sau khi hoàn tất các chỉnh sửa để lưu các thay đổi của bạn.</span><span class="sxs-lookup"><span data-stu-id="6f19e-155">Select **Save** in Power Query after completing your edits to save your changes.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]