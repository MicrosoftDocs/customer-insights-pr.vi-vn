---
title: Xuất dữ liệu từ Customer Insights
description: Quản lý nội dung xuất để chia sẻ dữ liệu.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c1078ed0ba259a6e9cde3c7ede3570890ae48e67
ms.sourcegitcommit: 33a8e21b3bf6521bdb8346f81f79fce88091ddfd
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 05/10/2021
ms.locfileid: "6016662"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="51e90-103">Tổng quan về trang Nội dung xuất (bản xem trước)</span><span class="sxs-lookup"><span data-stu-id="51e90-103">Exports (preview) overview</span></span>

<span data-ttu-id="51e90-104">Trang **Nội dung xuất** hiển thị cho bạn tất cả các nội dung xuất đã đặt cấu hình.</span><span class="sxs-lookup"><span data-stu-id="51e90-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="51e90-105">Nội dung xuất chia sẻ dữ liệu cụ thể với các ứng dụng khác nhau.</span><span class="sxs-lookup"><span data-stu-id="51e90-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="51e90-106">Chúng có thể bao gồm các thực thể hoặc hồ sơ khách hàng, lược đồ và thông tin chi tiết ánh xạ.</span><span class="sxs-lookup"><span data-stu-id="51e90-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="51e90-107">Mỗi nội dung xuất yêu cầu một [kết nối, do quản trị viên thiết lập, để quản lý hoạt động xác thực và truy cập](connections.md).</span><span class="sxs-lookup"><span data-stu-id="51e90-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

<span data-ttu-id="51e90-108">Đi đến **Dữ liệu** > **Nội dung xuất** để xem trang nội dung xuất.</span><span class="sxs-lookup"><span data-stu-id="51e90-108">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="51e90-109">Tất cả các vai trò người dùng đều có quyền truy cập để xem các nội dung xuất đã đặt cấu hình.</span><span class="sxs-lookup"><span data-stu-id="51e90-109">All user roles have access to view configured exports.</span></span> <span data-ttu-id="51e90-110">Sử dụng trường tìm kiếm trong thanh lệnh để tìm các nội dung xuất theo tên, tên kết nối hoặc loại kết nối.</span><span class="sxs-lookup"><span data-stu-id="51e90-110">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="51e90-111">Thiết lập một nội dung xuất mới</span><span class="sxs-lookup"><span data-stu-id="51e90-111">Set up a new export</span></span>

<span data-ttu-id="51e90-112">Để thiết lập hoặc chỉnh sửa một nội dung xuất, bạn cần có sẵn các kết nối.</span><span class="sxs-lookup"><span data-stu-id="51e90-112">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="51e90-113">Kết nối phụ thuộc vào [vai trò người dùng](permissions.md) của bạn:</span><span class="sxs-lookup"><span data-stu-id="51e90-113">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="51e90-114">Quản trị viên có quyền truy cập vào tất cả các kết nối.</span><span class="sxs-lookup"><span data-stu-id="51e90-114">Administrators have access to all connections.</span></span> <span data-ttu-id="51e90-115">Họ cũng có thể tạo kết nối mới khi thiết lập nội dung xuất.</span><span class="sxs-lookup"><span data-stu-id="51e90-115">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="51e90-116">Những người đóng góp có thể có quyền truy cập vào các kết nối cụ thể.</span><span class="sxs-lookup"><span data-stu-id="51e90-116">Contributors can have access to specific connections.</span></span> <span data-ttu-id="51e90-117">Họ có thể đặt cấu hình và chia sẻ kết nối hay không là tùy thuộc vào quản trị viên.</span><span class="sxs-lookup"><span data-stu-id="51e90-117">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="51e90-118">Để biết thêm thông tin, hãy xem [Cho phép người đóng góp sử dụng một kết nối cho các lần xuất](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="51e90-118">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="51e90-119">Người xem chỉ có thể xem các nội dung xuất hiện có nhưng không thể tạo chúng.</span><span class="sxs-lookup"><span data-stu-id="51e90-119">Viewers can only view existing exports but not create them.</span></span>

1. <span data-ttu-id="51e90-120">Đi tới **Dữ liệu** > **Nội dung xuất**.</span><span class="sxs-lookup"><span data-stu-id="51e90-120">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="51e90-121">Chọn **Thêm nội dung xuất** để tạo một đích xuất mới.</span><span class="sxs-lookup"><span data-stu-id="51e90-121">Select **Add export** to create a new export destination.</span></span>

1. <span data-ttu-id="51e90-122">Trong ngăn **Thiết lập nội dung xuất**, hãy chọn kết nối để sử dụng.</span><span class="sxs-lookup"><span data-stu-id="51e90-122">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="51e90-123">[Kết nối](connections.md) do quản trị viên quản lý.</span><span class="sxs-lookup"><span data-stu-id="51e90-123">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="51e90-124">Cung cấp các thông tin chi tiết được yêu cầu rồi chọn **Lưu** để tạo nội dung xuất.</span><span class="sxs-lookup"><span data-stu-id="51e90-124">Provide the required details and select **Save** to create the export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="51e90-125">Chỉnh sửa nội dung xuất</span><span class="sxs-lookup"><span data-stu-id="51e90-125">Edit an export</span></span>

1. <span data-ttu-id="51e90-126">Chọn dấu ba chấm dọc cạnh đích xuất bạn muốn chỉnh sửa.</span><span class="sxs-lookup"><span data-stu-id="51e90-126">Select the vertical ellipsis for the export destination you want to edit.</span></span>

1. <span data-ttu-id="51e90-127">Chọn **Chỉnh sửa** từ menu thả xuống.</span><span class="sxs-lookup"><span data-stu-id="51e90-127">Select **Edit** from the drop-down menu.</span></span>

1. <span data-ttu-id="51e90-128">Thay đổi các giá trị mà bạn muốn cập nhật rồi chọn **Lưu**.</span><span class="sxs-lookup"><span data-stu-id="51e90-128">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="51e90-129">Xem Nội dung xuất và thông tin chi tiết về nội dung xuất</span><span class="sxs-lookup"><span data-stu-id="51e90-129">View Exports and export details</span></span>

<span data-ttu-id="51e90-130">Sau khi tạo đích xuất, chúng được liệt kê trên **Dữ liệu** > **Nội dung xuất**.</span><span class="sxs-lookup"><span data-stu-id="51e90-130">After creating export destinations, they are listed on **Data** > **Exports**.</span></span> <span data-ttu-id="51e90-131">Tất cả người dùng có thể xem dữ liệu nào được chia sẻ và trạng thái mới nhất của dữ liệu đó.</span><span class="sxs-lookup"><span data-stu-id="51e90-131">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="51e90-132">Đi tới **Dữ liệu** > **Nội dung xuất**.</span><span class="sxs-lookup"><span data-stu-id="51e90-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="51e90-133">Người dùng không có quyền chỉnh sửa hãy chọn **Xem** thay vì **Chỉnh sửa** để xem thông tin chi tiết về nội dung xuất.</span><span class="sxs-lookup"><span data-stu-id="51e90-133">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="51e90-134">Ngăn bên này hiển thị việc thiết lập nội dung xuất này.</span><span class="sxs-lookup"><span data-stu-id="51e90-134">This side pane shows the set up of this export.</span></span> <span data-ttu-id="51e90-135">Nếu không có quyền chỉnh sửa, bạn không thể thay đổi giá trị.</span><span class="sxs-lookup"><span data-stu-id="51e90-135">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="51e90-136">Chọn **Đóng** để quay lại trang nội dung xuất.</span><span class="sxs-lookup"><span data-stu-id="51e90-136">Select **Close** to return to the exports page.</span></span>

## <a name="run-exports-on-demand"></a><span data-ttu-id="51e90-137">Chạy nội dung xuất theo yêu cầu</span><span class="sxs-lookup"><span data-stu-id="51e90-137">Run exports on demand</span></span>

<span data-ttu-id="51e90-138">Sau khi đặt cấu hình nội dung xuất, nó sẽ chạy trong mỗi [lần làm mới theo lịch trình](system.md#schedule-tab) miễn là có kết nối đang hoạt động.</span><span class="sxs-lookup"><span data-stu-id="51e90-138">After configuring an export, it will run with every [scheduled refresh](system.md#schedule-tab) as long as it has a working connection.</span></span>

<span data-ttu-id="51e90-139">Để xuất dữ liệu mà không cần đợi làm mới theo lịch trình, hãy đi đến **Dữ liệu** > **Nội dung xuất**.</span><span class="sxs-lookup"><span data-stu-id="51e90-139">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span> <span data-ttu-id="51e90-140">Bạn có hai tùy chọn:</span><span class="sxs-lookup"><span data-stu-id="51e90-140">You have two options:</span></span>

- <span data-ttu-id="51e90-141">Để chạy tất cả các nội dung xuất, hãy chọn **Chạy tất cả** trong thanh lệnh.</span><span class="sxs-lookup"><span data-stu-id="51e90-141">To run all exports, select **Run all** in the command bar.</span></span> 
- <span data-ttu-id="51e90-142">Để chạy một nội dung xuất, hãy chọn dấu chấm lửng (...) trên một mục danh sách rồi chọn **Chạy**.</span><span class="sxs-lookup"><span data-stu-id="51e90-142">To run a single export, select the ellipsis (...) on a list item and then choose **Run**.</span></span>

## <a name="remove-an-export"></a><span data-ttu-id="51e90-143">Loại bỏ một nội dung xuất</span><span class="sxs-lookup"><span data-stu-id="51e90-143">Remove an Export</span></span>

1. <span data-ttu-id="51e90-144">Đi tới **Dữ liệu** > **Nội dung xuất**.</span><span class="sxs-lookup"><span data-stu-id="51e90-144">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="51e90-145">Chọn dấu ba chấm dọc cho Nội dung xuất mà bạn muốn loại bỏ.</span><span class="sxs-lookup"><span data-stu-id="51e90-145">Select the vertical ellipsis for the Export you want to remove.</span></span>

1. <span data-ttu-id="51e90-146">Chọn **Xóa** trong menu thả xuống.</span><span class="sxs-lookup"><span data-stu-id="51e90-146">Select **Remove** from the dropdown menu.</span></span>

1. <span data-ttu-id="51e90-147">Xác nhận việc xóa bằng cách chọn **Xóa** trên màn hình xác nhận.</span><span class="sxs-lookup"><span data-stu-id="51e90-147">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
