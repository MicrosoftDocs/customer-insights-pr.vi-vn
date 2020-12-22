---
title: Hoạt động của khách hàng
description: Xác định các hoạt động của khách hàng và xem chúng trong dòng thời gian của khách hàng.
ms.date: 10/13/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: adkuppa
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 1c95cba333266a73959de0a3afe1c8677130a3ec
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667255"
---
# <a name="customer-activities"></a><span data-ttu-id="d20a2-103">Hoạt động của khách hàng</span><span class="sxs-lookup"><span data-stu-id="d20a2-103">Customer activities</span></span>

<span data-ttu-id="d20a2-104">Kết hợp các hoạt động của khách hàng từ [nhiều nguồn dữ liệu khác nhau](data-sources.md) trong Dynamics 365 Customer Insights để tạo dòng thời gian của khách hàng liệt kê các hoạt động theo thứ tự thời gian.</span><span class="sxs-lookup"><span data-stu-id="d20a2-104">Combine customer activities from [various data sources](data-sources.md) in Dynamics 365 Customer Insights to create a customer timeline that lists the activities in chronological order.</span></span> <span data-ttu-id="d20a2-105">Bạn có thể bao gồm tiến trình trong các ứng dụng tương tác với khách hàng trong Dynamics 365 thông qua [Phần bổ trợ Thẻ khách hàng](customer-card-add-in.md) hoặc trong bảng điều khiển Power BI.</span><span class="sxs-lookup"><span data-stu-id="d20a2-105">You can include the timeline in customer engagement apps in Dynamics 365 via the [Customer Card add-in](customer-card-add-in.md), or in a Power BI dashboard.</span></span>

## <a name="define-an-activity"></a><span data-ttu-id="d20a2-106">Xác định hoạt động</span><span class="sxs-lookup"><span data-stu-id="d20a2-106">Define an activity</span></span>

<span data-ttu-id="d20a2-107">Nguồn dữ liệu của bạn bao gồm các thực thể có dữ liệu giao dịch và hoạt động từ nhiều nguồn dữ liệu.</span><span class="sxs-lookup"><span data-stu-id="d20a2-107">Your data sources include entities with transactional and activity data from multiple data sources.</span></span> <span data-ttu-id="d20a2-108">Xác định các thực thể này và chọn các hoạt động bạn muốn xem trên dòng thời gian của khách hàng.</span><span class="sxs-lookup"><span data-stu-id="d20a2-108">Identify these entities and select the activities you want to view on the customer's timeline.</span></span> <span data-ttu-id="d20a2-109">Chọn thực thể bao gồm hoạt động mục tiêu hoặc hoạt động của bạn.</span><span class="sxs-lookup"><span data-stu-id="d20a2-109">Choose the entity that includes your target activity or activities.</span></span>

1. <span data-ttu-id="d20a2-110">Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Dữ liệu** > **Hoạt động**.</span><span class="sxs-lookup"><span data-stu-id="d20a2-110">In audience insights, go to **Data** > **Activities**.</span></span>

1. <span data-ttu-id="d20a2-111">Chọn **Thêm hoạt động**.</span><span class="sxs-lookup"><span data-stu-id="d20a2-111">Select **Add activity**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="d20a2-112">Một thực thể phải có ít nhất một thuộc tính loại **Ngày** để được đưa vào dòng thời gian của khách hàng và bạn không thể thêm các thực thể mà không có trường **Ngày**.</span><span class="sxs-lookup"><span data-stu-id="d20a2-112">An entity must have at least one attribute of type **Date** to be included in a customer timeline and you can't add entities without **Date** fields.</span></span> <span data-ttu-id="d20a2-113">Kiểm soát **Thêm hoạt động** bị vô hiệu hóa nếu không tìm thấy thực thể đó.</span><span class="sxs-lookup"><span data-stu-id="d20a2-113">The **Add activity** control is disabled if no such entity is found.</span></span>

1. <span data-ttu-id="d20a2-114">Trong ngăn **Thêm hoạt động**, đặt các giá trị cho các trường sau:</span><span class="sxs-lookup"><span data-stu-id="d20a2-114">In the **Add activity** pane, set the values for the following fields:</span></span>

   - <span data-ttu-id="d20a2-115">**Thực thể**: Chọn một thực thể bao gồm dữ liệu giao dịch hoặc hoạt động.</span><span class="sxs-lookup"><span data-stu-id="d20a2-115">**Entity**: Select an entity that includes transactional or activity data.</span></span>
   - <span data-ttu-id="d20a2-116">**Khóa chính**: Chọn trường xác định duy nhất một bản ghi.</span><span class="sxs-lookup"><span data-stu-id="d20a2-116">**Primary key**: Select the field that uniquely identifies a record.</span></span> <span data-ttu-id="d20a2-117">Nó không nên chứa bất kỳ giá trị trùng lặp, giá trị trống hoặc giá trị thiếu nào.</span><span class="sxs-lookup"><span data-stu-id="d20a2-117">It shouldn't contain any duplicate values, empty values, or missing values.</span></span>
   - <span data-ttu-id="d20a2-118">**Dấu thời gian**: Chọn trường đại diện cho thời gian bắt đầu hoạt động của bạn.</span><span class="sxs-lookup"><span data-stu-id="d20a2-118">**Timestamp**: Select the field that represents the start time of your activity.</span></span>
   - <span data-ttu-id="d20a2-119">**Biến cố**: Chọn trường là sự kiện cho hoạt động.</span><span class="sxs-lookup"><span data-stu-id="d20a2-119">**Event**: Select the field that is the event for the activity.</span></span>
   - <span data-ttu-id="d20a2-120">**Địa chỉ web**: Chọn trường đại diện cho một URL cung cấp thông tin bổ sung về hoạt động này.</span><span class="sxs-lookup"><span data-stu-id="d20a2-120">**Web address**: Select the field that represents a URL providing additional information about this activity.</span></span> <span data-ttu-id="d20a2-121">Ví dụ: hệ thống giao dịch lấy nguồn từ hoạt động này.</span><span class="sxs-lookup"><span data-stu-id="d20a2-121">For example, the transactional system that sources this activity.</span></span> <span data-ttu-id="d20a2-122">URL này có thể là bất kỳ trường nào từ nguồn dữ liệu hoặc được xây dựng làm một trường mới bằng cách chuyển đổi Power Query.</span><span class="sxs-lookup"><span data-stu-id="d20a2-122">This URL can be any field from the data source, or it can be constructed as a new field using a Power Query transformation.</span></span> <span data-ttu-id="d20a2-123">Dữ liệu URL này sẽ được lưu trữ trong thực thể Hoạt động hợp nhất, có thể được dùng xuôi dòng bằng API.</span><span class="sxs-lookup"><span data-stu-id="d20a2-123">This URL data will be stored in the Unified Activity entity, which can be consumed downstream using APIs.</span></span>
   - <span data-ttu-id="d20a2-124">**Chi tiết**: Hoặc chọn trường được thêm vào để biết thêm chi tiết.</span><span class="sxs-lookup"><span data-stu-id="d20a2-124">**Details**: Optionally, select the field that is added for additional details.</span></span>
   - <span data-ttu-id="d20a2-125">**Biểu tượng**: Hoặc chọn biểu tượng đại diện cho hoạt động này.</span><span class="sxs-lookup"><span data-stu-id="d20a2-125">**Icon**: Optionally, select the icon that represents this activity.</span></span>
   - <span data-ttu-id="d20a2-126">**Loại hoạt động**: Xác định tham chiếu loại hoạt động cho Common Data Model mô tả chính xác nhất định nghĩa ngữ nghĩa của hoạt động.</span><span class="sxs-lookup"><span data-stu-id="d20a2-126">**Activity Type**: Define the activity type reference to Common Data Model that best describes the semantic definition of the activity.</span></span>

1. <span data-ttu-id="d20a2-127">Trong phần **Thiết lập mối quan hệ**, đặt cấu hình chi tiết để kết nối dữ liệu hoạt động của bạn với khách hàng tương ứng.</span><span class="sxs-lookup"><span data-stu-id="d20a2-127">In the **Set up relationship** section, configure the details to connect your activity data to its corresponding customer.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d20a2-128">![Xác định mối quan hệ của thực thể](media/activities-entities-define.png "Xác định mối quan hệ của thực thể")</span><span class="sxs-lookup"><span data-stu-id="d20a2-128">![Define the entity relationship](media/activities-entities-define.png "Define the entity relationship")</span></span>

    - <span data-ttu-id="d20a2-129">**Trường thực thể hoạt động**: Chọn trường trong thực thể hoạt động của bạn sẽ được sử dụng để thiết lập mối quan hệ với thực thể khác.</span><span class="sxs-lookup"><span data-stu-id="d20a2-129">**Activity entity field**: Select the field in your activity entity that will be used to establish a relationship with another entity.</span></span>
    - <span data-ttu-id="d20a2-130">**Thực thể khách hàng**: Chọn thực thể khách hàng nguồn tương ứng mà thực thể hoạt động của bạn sẽ có mối quan hệ.</span><span class="sxs-lookup"><span data-stu-id="d20a2-130">**Customer entity**: Select the corresponding source customer entity with which your activity entity will be in relationship.</span></span> <span data-ttu-id="d20a2-131">Bạn chỉ có thể liên quan đến những thực thể khách hàng nguồn được sử dụng trong quy trình hợp nhất dữ liệu.</span><span class="sxs-lookup"><span data-stu-id="d20a2-131">You can relate to only those source customer entities that are used in the data unification process.</span></span>
    - <span data-ttu-id="d20a2-132">**Trường thực thể khách hàng**: Trường này hiển thị khóa chính của thực thể khách hàng nguồn như được chọn trong quy trình bản đồ.</span><span class="sxs-lookup"><span data-stu-id="d20a2-132">**Customer entity field**: This field shows the primary key of the source customer entity as selected in the map process.</span></span> <span data-ttu-id="d20a2-133">Trường khóa chính này trong thực thể khách hàng nguồn được sử dụng để thiết lập mối quan hệ với thực thể hoạt động.</span><span class="sxs-lookup"><span data-stu-id="d20a2-133">This primary key field in the source customer entity is used to establish a relationship with the activity entity.</span></span>
    - <span data-ttu-id="d20a2-134">**Tên**: Nếu mối quan hệ giữa thực thể hoạt động này và thực thể khách hàng nguồn được chọn đã tồn tại, thì tên mối quan hệ sẽ ở chế độ chỉ đọc.</span><span class="sxs-lookup"><span data-stu-id="d20a2-134">**Name**: If a relationship between this activity entity and the selected source customer entity already exists, the relationship name will be in read-only mode.</span></span> <span data-ttu-id="d20a2-135">Nếu không có mối quan hệ như vậy tồn tại, một mối quan hệ mới sẽ được tạo ra với tên được cung cấp ở đây.</span><span class="sxs-lookup"><span data-stu-id="d20a2-135">If there no such relationship exists, a new relationship will be created with the name provided here.</span></span>

1. <span data-ttu-id="d20a2-136">Chọn **Lưu** để áp dụng thay đổi.</span><span class="sxs-lookup"><span data-stu-id="d20a2-136">Select **Save** to apply your changes.</span></span>

1. <span data-ttu-id="d20a2-137">Trên trang **Hoạt động**, chọn **Chạy**.</span><span class="sxs-lookup"><span data-stu-id="d20a2-137">On the **Activities** page, select **Run**.</span></span>

> [!TIP]
> <span data-ttu-id="d20a2-138">Có [6 loại trạng thái](system.md#status-types) cho các nhiệm vụ/quy trình.</span><span class="sxs-lookup"><span data-stu-id="d20a2-138">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="d20a2-139">Ngoài ra, hầu hết các quy trình [phụ thuộc vào các quá trình hạ nguồn khác](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="d20a2-139">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="d20a2-140">Bạn có thể chọn trạng thái của một quy trình để xem chi tiết về tiến trình của toàn bộ công việc.</span><span class="sxs-lookup"><span data-stu-id="d20a2-140">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="d20a2-141">Sau khi chọn **Xem chi tiết** đối với một trong các tác vụ của công việc, bạn sẽ tìm thấy thông tin bổ sung: thời gian xử lý, ngày xử lý gần nhất và tất cả các lỗi và cảnh báo liên quan đến tác vụ.</span><span class="sxs-lookup"><span data-stu-id="d20a2-141">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="edit-an-activity"></a><span data-ttu-id="d20a2-142">Chỉnh sửa hoạt động</span><span class="sxs-lookup"><span data-stu-id="d20a2-142">Edit an activity</span></span>

1. <span data-ttu-id="d20a2-143">Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Dữ liệu** > **Hoạt động**.</span><span class="sxs-lookup"><span data-stu-id="d20a2-143">In audience insights, go to **Data** > **Activities**.</span></span>

2. <span data-ttu-id="d20a2-144">Chọn thực thể hoạt động bạn muốn chỉnh sửa và chọn **Chỉnh sửa**.</span><span class="sxs-lookup"><span data-stu-id="d20a2-144">Select the activity entity you want to edit and select **Edit**.</span></span> <span data-ttu-id="d20a2-145">Hoặc, bạn có thể di chuột qua hàng thực thể và chọn biểu tượng **Chỉnh sửa**.</span><span class="sxs-lookup"><span data-stu-id="d20a2-145">Or, you can hover over the entity row and select the **Edit** icon.</span></span>

3. <span data-ttu-id="d20a2-146">Bấm vào biểu tượng **Chỉnh sửa**.</span><span class="sxs-lookup"><span data-stu-id="d20a2-146">Click on the **Edit** icon.</span></span>

4. <span data-ttu-id="d20a2-147">Trong ngăn **Chỉnh sửa hoạt động**, cập nhật các giá trị và chọn **Lưu**.</span><span class="sxs-lookup"><span data-stu-id="d20a2-147">In the **Edit activity** pane, update the values and select **Save**.</span></span>

5. <span data-ttu-id="d20a2-148">Trên trang **Hoạt động**, chọn **Chạy**.</span><span class="sxs-lookup"><span data-stu-id="d20a2-148">On the **Activities** page, select **Run**.</span></span>

## <a name="delete-an-activity"></a><span data-ttu-id="d20a2-149">Xóa hoạt động</span><span class="sxs-lookup"><span data-stu-id="d20a2-149">Delete an activity</span></span>

1. <span data-ttu-id="d20a2-150">Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Dữ liệu** > **Hoạt động**.</span><span class="sxs-lookup"><span data-stu-id="d20a2-150">In audience insights, go to **Data** > **Activities**.</span></span>

2. <span data-ttu-id="d20a2-151">Chọn thực thể hoạt động bạn muốn xóa và chọn **Xóa**.</span><span class="sxs-lookup"><span data-stu-id="d20a2-151">Select the activity entity you want to remove and select **Delete**.</span></span> <span data-ttu-id="d20a2-152">Hoặc, bạn có thể di chuột qua hàng thực thể và chọn biểu tượng **Xóa**.</span><span class="sxs-lookup"><span data-stu-id="d20a2-152">Or, you can hover over the entity row and select the **Delete** icon.</span></span> <span data-ttu-id="d20a2-153">Ngoài ra, bạn có thể chọn nhiều thực thể hoạt động sẽ bị xóa cùng một lúc.</span><span class="sxs-lookup"><span data-stu-id="d20a2-153">Additionally, you can select multiple activity entities to be deleted at once.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d20a2-154">![Chỉnh sửa hoặc xóa mối quan hệ thực thể](media/activities-entities-edit-delete.png "Chỉnh sửa hoặc xóa mối quan hệ thực thể")</span><span class="sxs-lookup"><span data-stu-id="d20a2-154">![Edit or delete the entity relationship](media/activities-entities-edit-delete.png "Edit or delete the entity relationship")</span></span>

3. <span data-ttu-id="d20a2-155">Chọn biểu tượng **Xóa**.</span><span class="sxs-lookup"><span data-stu-id="d20a2-155">Select on the **Delete** icon.</span></span>

4. <span data-ttu-id="d20a2-156">Xác nhận tác vụ xóa của bạn.</span><span class="sxs-lookup"><span data-stu-id="d20a2-156">Confirm your deletion.</span></span>
