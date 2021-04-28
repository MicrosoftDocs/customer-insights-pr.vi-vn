---
title: Xuất dữ liệu từ Customer Insights
description: Quản lý nội dung xuất để chia sẻ dữ liệu.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 354ce9ef30fe918975d06290430996c84f8bd3f7
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896169"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="9f580-103">Tổng quan về trang Nội dung xuất (bản xem trước)</span><span class="sxs-lookup"><span data-stu-id="9f580-103">Exports (preview) overview</span></span>

<span data-ttu-id="9f580-104">Trang **Nội dung xuất** hiển thị cho bạn tất cả các nội dung xuất đã đặt cấu hình.</span><span class="sxs-lookup"><span data-stu-id="9f580-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="9f580-105">Nội dung xuất chia sẻ dữ liệu cụ thể với các ứng dụng khác nhau.</span><span class="sxs-lookup"><span data-stu-id="9f580-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="9f580-106">Chúng có thể bao gồm các thực thể hoặc hồ sơ khách hàng, lược đồ và thông tin chi tiết ánh xạ.</span><span class="sxs-lookup"><span data-stu-id="9f580-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="9f580-107">Mỗi nội dung xuất yêu cầu một [kết nối, do quản trị viên thiết lập, để quản lý hoạt động xác thực và truy cập](connections.md).</span><span class="sxs-lookup"><span data-stu-id="9f580-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

> [!NOTE]
> <span data-ttu-id="9f580-108">Cho đến tháng 3 năm 2021, các nội dung xuất đã tự động tạo kết nối với dịch vụ tương ứng.</span><span class="sxs-lookup"><span data-stu-id="9f580-108">Until March 2021, exports created a connection to the corresponding service automatically.</span></span> <span data-ttu-id="9f580-109">Hiện tại, cần có một [kết nối, do quản trị viên tạo và chia sẻ](connections.md) thì bạn mới có thể tạo các nội dung xuất.</span><span class="sxs-lookup"><span data-stu-id="9f580-109">Exports now require a [connection, created and shared by an administrator](connections.md) before you can create them.</span></span>

<span data-ttu-id="9f580-110">Đi đến **Dữ liệu** > **Nội dung xuất** để xem trang nội dung xuất.</span><span class="sxs-lookup"><span data-stu-id="9f580-110">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="9f580-111">Tất cả các vai trò người dùng đều có quyền truy cập để xem các nội dung xuất đã đặt cấu hình.</span><span class="sxs-lookup"><span data-stu-id="9f580-111">All user roles have access to view configured exports.</span></span> <span data-ttu-id="9f580-112">Sử dụng trường tìm kiếm trong thanh lệnh để tìm các nội dung xuất theo tên, tên kết nối hoặc loại kết nối.</span><span class="sxs-lookup"><span data-stu-id="9f580-112">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="9f580-113">Thiết lập một nội dung xuất mới</span><span class="sxs-lookup"><span data-stu-id="9f580-113">Set up a new export</span></span>

<span data-ttu-id="9f580-114">Để thiết lập hoặc chỉnh sửa một nội dung xuất, bạn cần có sẵn các kết nối.</span><span class="sxs-lookup"><span data-stu-id="9f580-114">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="9f580-115">Kết nối phụ thuộc vào [vai trò người dùng](permissions.md) của bạn:</span><span class="sxs-lookup"><span data-stu-id="9f580-115">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="9f580-116">Quản trị viên có quyền truy cập vào tất cả các kết nối.</span><span class="sxs-lookup"><span data-stu-id="9f580-116">Administrators have access to all connections.</span></span> <span data-ttu-id="9f580-117">Họ cũng có thể tạo kết nối mới khi thiết lập nội dung xuất.</span><span class="sxs-lookup"><span data-stu-id="9f580-117">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="9f580-118">Những người đóng góp có thể có quyền truy cập vào các kết nối cụ thể.</span><span class="sxs-lookup"><span data-stu-id="9f580-118">Contributors can have access to specific connections.</span></span> <span data-ttu-id="9f580-119">Họ có thể đặt cấu hình và chia sẻ kết nối hay không là tùy thuộc vào quản trị viên.</span><span class="sxs-lookup"><span data-stu-id="9f580-119">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="9f580-120">Để biết thêm thông tin, hãy xem [Cho phép người đóng góp sử dụng một kết nối cho các lần xuất](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="9f580-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="9f580-121">Người xem chỉ có thể xem các nội dung xuất hiện có nhưng không thể tạo chúng.</span><span class="sxs-lookup"><span data-stu-id="9f580-121">Viewers can only view existing exports but not create them.</span></span>

1. <span data-ttu-id="9f580-122">Đi tới **Dữ liệu** > **Nội dung xuất**.</span><span class="sxs-lookup"><span data-stu-id="9f580-122">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="9f580-123">Chọn **Thêm nội dung xuất** để tạo một đích xuất mới.</span><span class="sxs-lookup"><span data-stu-id="9f580-123">Select **Add export** to create a new export destination.</span></span>

1. <span data-ttu-id="9f580-124">Trong ngăn **Thiết lập nội dung xuất**, hãy chọn kết nối để sử dụng.</span><span class="sxs-lookup"><span data-stu-id="9f580-124">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="9f580-125">[Kết nối](connections.md) do quản trị viên quản lý.</span><span class="sxs-lookup"><span data-stu-id="9f580-125">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="9f580-126">Cung cấp các thông tin chi tiết được yêu cầu rồi chọn **Lưu** để tạo nội dung xuất.</span><span class="sxs-lookup"><span data-stu-id="9f580-126">Provide the required details and select **Save** to create the export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="9f580-127">Chỉnh sửa nội dung xuất</span><span class="sxs-lookup"><span data-stu-id="9f580-127">Edit an export</span></span>

1. <span data-ttu-id="9f580-128">Chọn dấu ba chấm dọc cạnh đích xuất bạn muốn chỉnh sửa.</span><span class="sxs-lookup"><span data-stu-id="9f580-128">Select the vertical ellipsis for the export destination you want to edit.</span></span>

1. <span data-ttu-id="9f580-129">Chọn **Chỉnh sửa** từ menu thả xuống.</span><span class="sxs-lookup"><span data-stu-id="9f580-129">Select **Edit** from the drop-down menu.</span></span>

1. <span data-ttu-id="9f580-130">Thay đổi các giá trị mà bạn muốn cập nhật rồi chọn **Lưu**.</span><span class="sxs-lookup"><span data-stu-id="9f580-130">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="9f580-131">Xem Nội dung xuất và thông tin chi tiết về nội dung xuất</span><span class="sxs-lookup"><span data-stu-id="9f580-131">View Exports and export details</span></span>

<span data-ttu-id="9f580-132">Sau khi tạo đích xuất, chúng được liệt kê trên **Dữ liệu** > **Nội dung xuất**.</span><span class="sxs-lookup"><span data-stu-id="9f580-132">After creating export destinations, they are listed on **Data** > **Exports**.</span></span> <span data-ttu-id="9f580-133">Tất cả người dùng có thể xem dữ liệu nào được chia sẻ và trạng thái mới nhất của dữ liệu đó.</span><span class="sxs-lookup"><span data-stu-id="9f580-133">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="9f580-134">Đi tới **Dữ liệu** > **Nội dung xuất**.</span><span class="sxs-lookup"><span data-stu-id="9f580-134">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="9f580-135">Người dùng không có quyền chỉnh sửa hãy chọn **Xem** thay vì **Chỉnh sửa** để xem thông tin chi tiết về nội dung xuất.</span><span class="sxs-lookup"><span data-stu-id="9f580-135">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="9f580-136">Ngăn bên này hiển thị việc thiết lập nội dung xuất này.</span><span class="sxs-lookup"><span data-stu-id="9f580-136">This side pane shows the set up of this export.</span></span> <span data-ttu-id="9f580-137">Nếu không có quyền chỉnh sửa, bạn không thể thay đổi giá trị.</span><span class="sxs-lookup"><span data-stu-id="9f580-137">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="9f580-138">Chọn **Đóng** để quay lại trang nội dung xuất.</span><span class="sxs-lookup"><span data-stu-id="9f580-138">Select **Close** to return to the exports page.</span></span>

## <a name="run-exports-on-demand"></a><span data-ttu-id="9f580-139">Chạy nội dung xuất theo yêu cầu</span><span class="sxs-lookup"><span data-stu-id="9f580-139">Run exports on demand</span></span>

<span data-ttu-id="9f580-140">Sau khi đặt cấu hình nội dung xuất, nó sẽ chạy trong mỗi [lần làm mới theo lịch trình](system.md#schedule-tab) miễn là có kết nối đang hoạt động.</span><span class="sxs-lookup"><span data-stu-id="9f580-140">After configuring an export, it will run with every [scheduled refresh](system.md#schedule-tab) as long as it has a working connection.</span></span>

<span data-ttu-id="9f580-141">Để xuất dữ liệu mà không cần đợi làm mới theo lịch trình, hãy đi đến **Dữ liệu** > **Nội dung xuất**.</span><span class="sxs-lookup"><span data-stu-id="9f580-141">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span> <span data-ttu-id="9f580-142">Bạn có hai tùy chọn:</span><span class="sxs-lookup"><span data-stu-id="9f580-142">You have two options:</span></span>

- <span data-ttu-id="9f580-143">Để chạy tất cả các nội dung xuất, hãy chọn **Chạy tất cả** trong thanh lệnh.</span><span class="sxs-lookup"><span data-stu-id="9f580-143">To run all exports, select **Run all** in the command bar.</span></span> 
- <span data-ttu-id="9f580-144">Để chạy một nội dung xuất, hãy chọn dấu chấm lửng (...) trên một mục danh sách rồi chọn **Chạy**.</span><span class="sxs-lookup"><span data-stu-id="9f580-144">To run a single export, select the ellipsis (...) on a list item and then choose **Run**.</span></span>

## <a name="remove-an-export"></a><span data-ttu-id="9f580-145">Loại bỏ một nội dung xuất</span><span class="sxs-lookup"><span data-stu-id="9f580-145">Remove an Export</span></span>

1. <span data-ttu-id="9f580-146">Đi tới **Dữ liệu** > **Nội dung xuất**.</span><span class="sxs-lookup"><span data-stu-id="9f580-146">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="9f580-147">Chọn dấu ba chấm dọc cho Nội dung xuất mà bạn muốn loại bỏ.</span><span class="sxs-lookup"><span data-stu-id="9f580-147">Select the vertical ellipsis for the Export you want to remove.</span></span>

1. <span data-ttu-id="9f580-148">Chọn **Xóa** trong menu thả xuống.</span><span class="sxs-lookup"><span data-stu-id="9f580-148">Select **Remove** from the dropdown menu.</span></span>

1. <span data-ttu-id="9f580-149">Xác nhận việc xóa bằng cách chọn **Xóa** trên màn hình xác nhận.</span><span class="sxs-lookup"><span data-stu-id="9f580-149">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
