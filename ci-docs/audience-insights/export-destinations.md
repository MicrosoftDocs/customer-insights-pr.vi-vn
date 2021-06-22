---
title: Xuất dữ liệu từ Customer Insights
description: Quản lý nội dung xuất để chia sẻ dữ liệu.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6e7793fa99f8431d9d420529b39e0b5b5dbf6748
ms.sourcegitcommit: 0689e7ed4265855d1f76745d68af390f8f4af8a0
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 06/14/2021
ms.locfileid: "6253066"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="87eb7-103">Tổng quan về trang Nội dung xuất (xem trước)</span><span class="sxs-lookup"><span data-stu-id="87eb7-103">Exports (preview) overview</span></span>

<span data-ttu-id="87eb7-104">Trang **Nội dung xuất** hiển thị cho bạn tất cả các nội dung xuất đã đặt cấu hình.</span><span class="sxs-lookup"><span data-stu-id="87eb7-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="87eb7-105">Nội dung xuất chia sẻ dữ liệu cụ thể với các ứng dụng khác nhau.</span><span class="sxs-lookup"><span data-stu-id="87eb7-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="87eb7-106">Chúng có thể bao gồm các thực thể hoặc hồ sơ khách hàng, lược đồ và thông tin chi tiết ánh xạ.</span><span class="sxs-lookup"><span data-stu-id="87eb7-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="87eb7-107">Mỗi nội dung xuất yêu cầu một [kết nối, do quản trị viên thiết lập, để quản lý hoạt động xác thực và truy cập](connections.md).</span><span class="sxs-lookup"><span data-stu-id="87eb7-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

<span data-ttu-id="87eb7-108">Đi đến **Dữ liệu** > **Nội dung xuất** để xem trang nội dung xuất.</span><span class="sxs-lookup"><span data-stu-id="87eb7-108">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="87eb7-109">Tất cả các vai trò người dùng đều có quyền truy cập để xem các nội dung xuất đã đặt cấu hình.</span><span class="sxs-lookup"><span data-stu-id="87eb7-109">All user roles have access to view configured exports.</span></span> <span data-ttu-id="87eb7-110">Sử dụng trường tìm kiếm trong thanh lệnh để tìm các nội dung xuất theo tên, tên kết nối hoặc loại kết nối.</span><span class="sxs-lookup"><span data-stu-id="87eb7-110">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="87eb7-111">Thiết lập một nội dung xuất mới</span><span class="sxs-lookup"><span data-stu-id="87eb7-111">Set up a new export</span></span>

<span data-ttu-id="87eb7-112">Để thiết lập hoặc chỉnh sửa một nội dung xuất, bạn cần có sẵn các kết nối.</span><span class="sxs-lookup"><span data-stu-id="87eb7-112">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="87eb7-113">Kết nối phụ thuộc vào [vai trò người dùng](permissions.md) của bạn:</span><span class="sxs-lookup"><span data-stu-id="87eb7-113">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="87eb7-114">Quản trị viên có quyền truy cập vào tất cả các kết nối.</span><span class="sxs-lookup"><span data-stu-id="87eb7-114">Administrators have access to all connections.</span></span> <span data-ttu-id="87eb7-115">Họ cũng có thể tạo kết nối mới khi thiết lập nội dung xuất.</span><span class="sxs-lookup"><span data-stu-id="87eb7-115">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="87eb7-116">Những người đóng góp có thể có quyền truy cập vào các kết nối cụ thể.</span><span class="sxs-lookup"><span data-stu-id="87eb7-116">Contributors can have access to specific connections.</span></span> <span data-ttu-id="87eb7-117">Họ có thể đặt cấu hình và chia sẻ kết nối hay không là tùy thuộc vào quản trị viên.</span><span class="sxs-lookup"><span data-stu-id="87eb7-117">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="87eb7-118">Danh sách nội dung xuất cho người đóng góp biết họ có thể chỉnh sửa hay chỉ được xem nội dung xuất trong cột **Quyền của bạn**.</span><span class="sxs-lookup"><span data-stu-id="87eb7-118">The exports list shows contributors whether they can edit or only view an export in the **Your permissions** column.</span></span> <span data-ttu-id="87eb7-119">Để biết thêm thông tin, hãy xem [Cho phép người đóng góp sử dụng một kết nối cho các lần xuất](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="87eb7-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="87eb7-120">Người xem chỉ có thể xem các nội dung xuất hiện có nhưng không thể tạo chúng.</span><span class="sxs-lookup"><span data-stu-id="87eb7-120">Viewers can only view existing exports but not create them.</span></span>

### <a name="define-a-new-export"></a><span data-ttu-id="87eb7-121">Xác định nội dung xuất mới</span><span class="sxs-lookup"><span data-stu-id="87eb7-121">Define a new export</span></span>

1. <span data-ttu-id="87eb7-122">Đi tới **Dữ liệu** > **Nội dung xuất**.</span><span class="sxs-lookup"><span data-stu-id="87eb7-122">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="87eb7-123">Chọn **Thêm nội dung xuất** để tạo nội dung xuất mới.</span><span class="sxs-lookup"><span data-stu-id="87eb7-123">Select **Add export** to create a new export.</span></span>

1. <span data-ttu-id="87eb7-124">Trong ngăn **Thiết lập nội dung xuất**, hãy chọn kết nối để sử dụng.</span><span class="sxs-lookup"><span data-stu-id="87eb7-124">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="87eb7-125">[Kết nối](connections.md) do quản trị viên quản lý.</span><span class="sxs-lookup"><span data-stu-id="87eb7-125">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="87eb7-126">Cung cấp các thông tin chi tiết được yêu cầu rồi chọn **Lưu** để tạo nội dung xuất.</span><span class="sxs-lookup"><span data-stu-id="87eb7-126">Provide the required details and select **Save** to create the export.</span></span>

### <a name="define-a-new-export-based-on-an-existing-export"></a><span data-ttu-id="87eb7-127">Xác định nội dung xuất mới dựa trên nội dung xuất hiện có</span><span class="sxs-lookup"><span data-stu-id="87eb7-127">Define a new export based on an existing export</span></span>

1. <span data-ttu-id="87eb7-128">Đi tới **Dữ liệu** > **Nội dung xuất**.</span><span class="sxs-lookup"><span data-stu-id="87eb7-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="87eb7-129">Trong danh sách nội dung xuất, hãy chọn nội dung xuất bạn muốn sao chép.</span><span class="sxs-lookup"><span data-stu-id="87eb7-129">In the list of exports, select the export you want to duplicate.</span></span>

1. <span data-ttu-id="87eb7-130">Chọn **Tạo bản sao** trên thanh lệnh để mở ngăn **Thiết lập nội dung xuất** với thông tin chi tiết về nội dung xuất đã chọn.</span><span class="sxs-lookup"><span data-stu-id="87eb7-130">Select **Create duplicate** in the command bar to open the **Set up export** pane with the details of the selected export.</span></span>

1. <span data-ttu-id="87eb7-131">Xem lại và điều chỉnh nội dung xuất rồi chọn **Lưu** để tạo nội dung xuất mới.</span><span class="sxs-lookup"><span data-stu-id="87eb7-131">Review and adapt the export and select **Save** to create a new export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="87eb7-132">Chỉnh sửa nội dung xuất</span><span class="sxs-lookup"><span data-stu-id="87eb7-132">Edit an export</span></span>

1. <span data-ttu-id="87eb7-133">Đi tới **Dữ liệu** > **Nội dung xuất**.</span><span class="sxs-lookup"><span data-stu-id="87eb7-133">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="87eb7-134">Trong danh sách nội dung xuất, hãy chọn nội dung xuất bạn muốn chỉnh sửa.</span><span class="sxs-lookup"><span data-stu-id="87eb7-134">In the list of exports, select the export you want to edit.</span></span>

1. <span data-ttu-id="87eb7-135">Chọn **Chỉnh sửa** trên thanh lệnh.</span><span class="sxs-lookup"><span data-stu-id="87eb7-135">Select **Edit** in the command bar.</span></span>

1. <span data-ttu-id="87eb7-136">Thay đổi các giá trị mà bạn muốn cập nhật rồi chọn **Lưu**.</span><span class="sxs-lookup"><span data-stu-id="87eb7-136">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="87eb7-137">Xem nội dung xuất và thông tin chi tiết về nội dung xuất</span><span class="sxs-lookup"><span data-stu-id="87eb7-137">View exports and export details</span></span>

<span data-ttu-id="87eb7-138">Sau khi tạo đích xuất, các đích xuất đã tạo sẽ có trong phần **Dữ liệu** > **Nội dung xuất**.</span><span class="sxs-lookup"><span data-stu-id="87eb7-138">After creating export destinations, they're listed on **Data** > **Exports**.</span></span> <span data-ttu-id="87eb7-139">Tất cả người dùng có thể xem dữ liệu nào được chia sẻ và trạng thái mới nhất của dữ liệu đó.</span><span class="sxs-lookup"><span data-stu-id="87eb7-139">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="87eb7-140">Đi tới **Dữ liệu** > **Nội dung xuất**.</span><span class="sxs-lookup"><span data-stu-id="87eb7-140">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="87eb7-141">Người dùng không có quyền chỉnh sửa hãy chọn **Xem** thay vì **Chỉnh sửa** để xem thông tin chi tiết về nội dung xuất.</span><span class="sxs-lookup"><span data-stu-id="87eb7-141">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="87eb7-142">Ngăn bên hiển thị cấu hình của nội dung xuất.</span><span class="sxs-lookup"><span data-stu-id="87eb7-142">The side pane shows the configuration of an export.</span></span> <span data-ttu-id="87eb7-143">Nếu không có quyền chỉnh sửa, bạn không thể thay đổi giá trị.</span><span class="sxs-lookup"><span data-stu-id="87eb7-143">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="87eb7-144">Chọn **Đóng** để quay lại trang nội dung xuất.</span><span class="sxs-lookup"><span data-stu-id="87eb7-144">Select **Close** to return to the exports page.</span></span>

## <a name="schedule-and-run-exports"></a><span data-ttu-id="87eb7-145">Lên lịch và chạy nội dung xuất</span><span class="sxs-lookup"><span data-stu-id="87eb7-145">Schedule and run exports</span></span>

<span data-ttu-id="87eb7-146">Mỗi nội dung xuất bạn đặt cấu hình đều có lịch làm mới.</span><span class="sxs-lookup"><span data-stu-id="87eb7-146">Each export you configure has a refresh schedule.</span></span> <span data-ttu-id="87eb7-147">Trong quá trình làm mới, hệ thống sẽ tìm dữ liệu mới hoặc dữ liệu cập nhật để đưa vào nội dung xuất.</span><span class="sxs-lookup"><span data-stu-id="87eb7-147">During a refresh, the system looks for new or updated data to include in an export.</span></span> <span data-ttu-id="87eb7-148">Theo mặc định, các nội dung xuất được chạy trong mỗi lần [làm mới hệ thống theo lịch](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="87eb7-148">By default, exports are run as part of every [scheduled system refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="87eb7-149">Bạn có thể tùy chỉnh lịch làm mới hoặc tắt đi để chạy nội dung xuất theo cách thủ công.</span><span class="sxs-lookup"><span data-stu-id="87eb7-149">You can customize the refresh schedule or turn it off to run exports manually.</span></span>

<span data-ttu-id="87eb7-150">Lịch xuất phụ thuộc vào trạng thái môi trường của bạn.</span><span class="sxs-lookup"><span data-stu-id="87eb7-150">Export schedules depend on the state of your environment.</span></span> <span data-ttu-id="87eb7-151">Nếu hệ thống đang cập nhật [các phần phụ thuộc](system.md#refresh-policies) khi quá trình xuất theo lịch bắt đầu, thì trước tiên, hệ thống sẽ hoàn thành các phần phụ thuộc rồi mới chạy nội dung xuất.</span><span class="sxs-lookup"><span data-stu-id="87eb7-151">If there are updates on [dependencies](system.md#refresh-policies) in progress when a scheduled export should start, the system will first complete the dependencies and then run the export.</span></span> <span data-ttu-id="87eb7-152">Bạn có thể biết thời điểm gần đây nhất mà nội dung xuất được làm mới trong cột **Đã làm mới**.</span><span class="sxs-lookup"><span data-stu-id="87eb7-152">You can see when an export was last refreshed in column **Refreshed**.</span></span>

### <a name="schedule-exports"></a><span data-ttu-id="87eb7-153">Lên lịch nội dung xuất</span><span class="sxs-lookup"><span data-stu-id="87eb7-153">Schedule exports</span></span>

<span data-ttu-id="87eb7-154">Bạn có thể xác định lịch làm mới tùy chỉnh cho từng nội dung xuất hoặc một vài nội dung xuất cùng lúc.</span><span class="sxs-lookup"><span data-stu-id="87eb7-154">You can define custom refresh schedules for individual exports or several exports at once.</span></span> <span data-ttu-id="87eb7-155">Lịch trình hiện tại được xác định có trong cột **Lịch trình** của danh sách nội dung xuất.</span><span class="sxs-lookup"><span data-stu-id="87eb7-155">The currently defined schedule is listed in the **Schedule** column of the export list.</span></span> <span data-ttu-id="87eb7-156">Quyền thay đổi lịch trình tương tự như [chỉnh sửa và xác định nội dung xuất](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="87eb7-156">The permission to change the schedule is the same as for [editing and defining exports](export-destinations.md#set-up-a-new-export).</span></span> 

1. <span data-ttu-id="87eb7-157">Đi tới **Dữ liệu** > **Nội dung xuất**.</span><span class="sxs-lookup"><span data-stu-id="87eb7-157">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="87eb7-158">Chọn nội dung xuất bạn muốn lên lịch.</span><span class="sxs-lookup"><span data-stu-id="87eb7-158">Select the export you want to schedule.</span></span>

1. <span data-ttu-id="87eb7-159">Chọn **Lên lịch** trên thanh lệnh.</span><span class="sxs-lookup"><span data-stu-id="87eb7-159">Select **Schedule** in the command bar.</span></span>

1. <span data-ttu-id="87eb7-160">Trong ngăn **Lên lịch xuất**, đặt tùy chọn **Lên lịch chạy** thành **Bật** để tự động chạy nội dung xuất.</span><span class="sxs-lookup"><span data-stu-id="87eb7-160">In the **Schedule export** pane, set the **Schedule run** to **On** to run the export automatically.</span></span> <span data-ttu-id="87eb7-161">Đặt thành **Tắt** để làm mới nội dung xuất theo cách thủ công.</span><span class="sxs-lookup"><span data-stu-id="87eb7-161">Set it to **Off** to refresh it manually.</span></span>

1. <span data-ttu-id="87eb7-162">Đối với nội dung xuất được làm mới tự động, hãy chọn một giá trị **Lặp lại** rồi chỉ định thông tin chi tiết.</span><span class="sxs-lookup"><span data-stu-id="87eb7-162">For automatically refreshed exports, choose a **Recurrence** value and specify the details for it.</span></span> <span data-ttu-id="87eb7-163">Thời gian đã xác định sẽ được áp dụng cho tất cả các trường hợp lặp lại.</span><span class="sxs-lookup"><span data-stu-id="87eb7-163">The time defined applies to all instances of a recurrence.</span></span> <span data-ttu-id="87eb7-164">Đây là thời gian mà một nội dung xuất sẽ bắt đầu làm mới.</span><span class="sxs-lookup"><span data-stu-id="87eb7-164">It's the time when an export should start refreshing.</span></span>

1. <span data-ttu-id="87eb7-165">Áp dụng và kích hoạt các thay đổi bằng cách chọn **Lưu**.</span><span class="sxs-lookup"><span data-stu-id="87eb7-165">Apply and activate your changes by selecting **Save**.</span></span>

<span data-ttu-id="87eb7-166">Khi chỉnh sửa lịch trình cho một số nội dung xuất, bạn cần thực hiện lựa chọn trong phần **Giữ hoặc ghi đè lịch trình**:</span><span class="sxs-lookup"><span data-stu-id="87eb7-166">When editing the schedule for several exports, you need to make a selection under **Keep or override schedules**:</span></span>
- <span data-ttu-id="87eb7-167">**Giữ lịch trình riêng**: Duy trì lịch trình đã xác định từ trước cho các nội dung xuất đã chọn và chỉ tắt hoặc bật.</span><span class="sxs-lookup"><span data-stu-id="87eb7-167">**Keep individual schedules**: Persist the previously defined schedule for the selected exports and only disable or enable them.</span></span>
- <span data-ttu-id="87eb7-168">**Xác định lịch trình mới cho tất cả nội dung xuất đã chọn**: Ghi đè lên lịch trình hiện có của các nội dung xuất đã chọn.</span><span class="sxs-lookup"><span data-stu-id="87eb7-168">**Define new schedule for all selected exports**: Override the existing schedules of the selected exports.</span></span>

### <a name="run-exports-on-demand"></a><span data-ttu-id="87eb7-169">Chạy nội dung xuất theo yêu cầu</span><span class="sxs-lookup"><span data-stu-id="87eb7-169">Run exports on demand</span></span>

<span data-ttu-id="87eb7-170">Để xuất dữ liệu mà không cần đợi làm mới theo lịch trình, hãy đi đến **Dữ liệu** > **Nội dung xuất**.</span><span class="sxs-lookup"><span data-stu-id="87eb7-170">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span>

- <span data-ttu-id="87eb7-171">Để chạy tất cả các nội dung xuất, hãy chọn **Chạy tất cả** trong thanh lệnh.</span><span class="sxs-lookup"><span data-stu-id="87eb7-171">To run all exports, select **Run all** in the command bar.</span></span> <span data-ttu-id="87eb7-172">Thao tác này sẽ chỉ chạy các nội dung xuất có lịch trình hiện hoạt.</span><span class="sxs-lookup"><span data-stu-id="87eb7-172">This action will only run exports that have an active schedule.</span></span>
- <span data-ttu-id="87eb7-173">Để chạy một nội dung xuất, hãy chọn nội dung xuất đó trong danh sách rồi chọn **Chạy** trên thanh lệnh.</span><span class="sxs-lookup"><span data-stu-id="87eb7-173">To run a single export, select it in the list and select **Run** in the command bar.</span></span> <span data-ttu-id="87eb7-174">Đó là cách bạn chạy nội dung xuất không có lịch trình hiện hoạt.</span><span class="sxs-lookup"><span data-stu-id="87eb7-174">That's how you run exports with no active schedule.</span></span> 

## <a name="remove-an-export"></a><span data-ttu-id="87eb7-175">Loại bỏ một nội dung xuất</span><span class="sxs-lookup"><span data-stu-id="87eb7-175">Remove an Export</span></span>

1. <span data-ttu-id="87eb7-176">Đi tới **Dữ liệu** > **Nội dung xuất**.</span><span class="sxs-lookup"><span data-stu-id="87eb7-176">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="87eb7-177">Chọn nội dung xuất mà bạn muốn loại bỏ.</span><span class="sxs-lookup"><span data-stu-id="87eb7-177">Select the export you want to remove.</span></span>

1. <span data-ttu-id="87eb7-178">Chọn **Loại bỏ** trên thanh lệnh.</span><span class="sxs-lookup"><span data-stu-id="87eb7-178">Select **Remove** in the command bar.</span></span>

1. <span data-ttu-id="87eb7-179">Xác nhận việc xóa bằng cách chọn **Xóa** trên màn hình xác nhận.</span><span class="sxs-lookup"><span data-stu-id="87eb7-179">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
