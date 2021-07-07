---
title: Kết nối với các dịch vụ khác từ Customer Insights.
description: Chia sẻ dữ liệu với các dịch vụ khác.
ms.date: 04/09/2021
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 17e04b243e9b3d4375c86f5a890a18be35956835
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304998"
---
# <a name="connections-preview-overview"></a><span data-ttu-id="addd2-103">Tổng quan về kết nối (bản xem trước)</span><span class="sxs-lookup"><span data-stu-id="addd2-103">Connections (preview) overview</span></span>

<span data-ttu-id="addd2-104">Kết nối là chìa khóa để cho phép chia sẻ dữ liệu với và từ Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="addd2-104">Connections are the key to enable data sharing to and from Customer Insights.</span></span> <span data-ttu-id="addd2-105">Mỗi kết nối thiết lập chế độ chia sẻ dữ liệu với một dịch vụ cụ thể.</span><span class="sxs-lookup"><span data-stu-id="addd2-105">Each connection establishes data sharing with a specific service.</span></span> <span data-ttu-id="addd2-106">Kết nối là nền tảng để [đặt cấu hình nội dung bổ sung của bên thứ ba](enrichment-hub.md) và [đặt cấu hình nội dung xuất](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="addd2-106">Connections are the foundation to [configure third-party enrichments](enrichment-hub.md) and [configure exports](export-destinations.md).</span></span> <span data-ttu-id="addd2-107">Một loại kết nối có thể được sử dụng nhiều lần.</span><span class="sxs-lookup"><span data-stu-id="addd2-107">The same connection can be used multiple times.</span></span> <span data-ttu-id="addd2-108">Ví dụ: một kết nối đến Dynamics 365 Marketing hoạt động cho nhiều lần xuất và một kết nối Leadspace có thể được sử dụng cho nhiều nội dung bổ sung.</span><span class="sxs-lookup"><span data-stu-id="addd2-108">For example, one connection to Dynamics 365 Marketing works for multiple exports and one Leadspace connection can be used for several enrichments.</span></span>

<span data-ttu-id="addd2-109">Đi đến **Quản trị viên** > **Kết nối** để tạo và xem các kết nối.</span><span class="sxs-lookup"><span data-stu-id="addd2-109">Go to **Admin** > **Connections** to create and view connections.</span></span>

<span data-ttu-id="addd2-110">Tab **Kết nối** hiển thị cho bạn tất cả các kết nối hiện hoạt.</span><span class="sxs-lookup"><span data-stu-id="addd2-110">The **Connections** tab shows you all active connections.</span></span> <span data-ttu-id="addd2-111">Danh sách hiển thị một hàng cho mỗi kết nối.</span><span class="sxs-lookup"><span data-stu-id="addd2-111">The list shows a row for each connection.</span></span> 

<span data-ttu-id="addd2-112">Xem tổng quan nhanh, nội dung mô tả và tìm hiểu những gì bạn có thể làm với từng tùy chọn khả năng mở rộng trên tab **Khám phá**.</span><span class="sxs-lookup"><span data-stu-id="addd2-112">Get a quick overview, description, and find out what you can do with each extensibility option on the **Discover** tab.</span></span>

### <a name="exports"></a><span data-ttu-id="addd2-113">Nội dung xuất</span><span class="sxs-lookup"><span data-stu-id="addd2-113">Exports</span></span>

<span data-ttu-id="addd2-114">Chỉ quản trị viên là có thể đặt cấu hình các kết nối mới, nhưng họ có thể cấp quyền truy cập cho những người đóng góp để sử dụng các kết nối hiện có.</span><span class="sxs-lookup"><span data-stu-id="addd2-114">Only administrators can configure new connections but they can grant access to contributors to use existing connections.</span></span> <span data-ttu-id="addd2-115">Quản trị viên kiểm soát nơi dữ liệu có thể đến, những người đóng góp xác định tải trọng và tần suất phù hợp với nhu cầu của họ.</span><span class="sxs-lookup"><span data-stu-id="addd2-115">Administrators control where data can go, contributors define the payload and frequency fitting their needs.</span></span> <span data-ttu-id="addd2-116">Để biết thêm thông tin, hãy xem [Cho phép người đóng góp sử dụng một kết nối cho các lần xuất](#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="addd2-116">For more information, see [Allow contributors to use a connection for exports](#allow-contributors-to-use-a-connection-for-exports).</span></span>

### <a name="enrichments"></a><span data-ttu-id="addd2-117">Nội dung tăng cường</span><span class="sxs-lookup"><span data-stu-id="addd2-117">Enrichments</span></span>

<span data-ttu-id="addd2-118">Chỉ quản trị viên là có thể đặt cấu hình các kết nối mới nhưng các kết nối đã tạo luôn có sẵn cho cả quản trị viên và người đóng góp.</span><span class="sxs-lookup"><span data-stu-id="addd2-118">Only administrators can configure new connections but the created connections are always available to both administrators and contributors.</span></span> <span data-ttu-id="addd2-119">Quản trị viên quản lý thông tin xác thực và cho phép chuyển dữ liệu.</span><span class="sxs-lookup"><span data-stu-id="addd2-119">Administrators manage credentials and give consent to data transfers.</span></span> <span data-ttu-id="addd2-120">Sau đó, cả quản trị viên và người đóng góp đều có thể dùng các kết nối cho những nội dung bổ sung.</span><span class="sxs-lookup"><span data-stu-id="addd2-120">The connections can then be used for enrichments by both administrators and contributors.</span></span>

## <a name="add-a-new-connection"></a><span data-ttu-id="addd2-121">Thêm kết nối mới</span><span class="sxs-lookup"><span data-stu-id="addd2-121">Add a new connection</span></span>

<span data-ttu-id="addd2-122">Để thêm kết nối, bạn cần có [quyền của quản trị viên](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="addd2-122">To add connections, you need to have [administrator permissions](permissions.md).</span></span> <span data-ttu-id="addd2-123">Nếu bạn kết nối với các dịch vụ khác của Microsoft, chúng tôi giả định rằng cả hai dịch vụ đều nằm trong cùng một tổ chức.</span><span class="sxs-lookup"><span data-stu-id="addd2-123">If you connect to other Microsoft services, we assume both services are in the same organization.</span></span>

1. <span data-ttu-id="addd2-124">Đi đến **Quản trị viên** > **Kết nối (bản xem trước)**.</span><span class="sxs-lookup"><span data-stu-id="addd2-124">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="addd2-125">Đi đến tab **Kết nối**.</span><span class="sxs-lookup"><span data-stu-id="addd2-125">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="addd2-126">Chọn **Thêm kết nối** để tạo kết nối mới.</span><span class="sxs-lookup"><span data-stu-id="addd2-126">Select **Add connection** to create a new connection.</span></span> <span data-ttu-id="addd2-127">Chọn loại kết nối bạn muốn tạo từ menu thả xuống.</span><span class="sxs-lookup"><span data-stu-id="addd2-127">Choose from the dropdown menu what type of connection you want to create.</span></span>

1. <span data-ttu-id="addd2-128">Trong ngăn **Thiết lập kết nối**, hãy cung cấp thông tin chi tiết được yêu cầu.</span><span class="sxs-lookup"><span data-stu-id="addd2-128">In the **Set up connection** pane, provide the required details.</span></span> 
   1. <span data-ttu-id="addd2-129">**Tên hiển thị** và loại kết nối mô tả một kết nối.</span><span class="sxs-lookup"><span data-stu-id="addd2-129">The **Display name** and the type of the connection describe a connection.</span></span> <span data-ttu-id="addd2-130">Bạn nên chọn một tên giải thích mục đích và mục tiêu của kết nối này.</span><span class="sxs-lookup"><span data-stu-id="addd2-130">We recommend choosing a name that explains the purpose and target of this connection.</span></span>
   1. <span data-ttu-id="addd2-131">Các trường chính xác phụ thuộc vào dịch vụ bạn đang kết nối.</span><span class="sxs-lookup"><span data-stu-id="addd2-131">The exact fields depend on what service you are connecting to.</span></span> <span data-ttu-id="addd2-132">Bạn có thể tìm hiểu về thông tin chi tiết của một loại kết nối cụ thể trong bài viết về dịch vụ mục tiêu.</span><span class="sxs-lookup"><span data-stu-id="addd2-132">You can learn about details of a specific connection type in the article about the target service.</span></span>

1. <span data-ttu-id="addd2-133">Để tạo kết nối, hãy chọn **Lưu**.</span><span class="sxs-lookup"><span data-stu-id="addd2-133">To create the connection, select **Save**.</span></span>

<span data-ttu-id="addd2-134">Bạn cũng có thể chọn **Thiết lập** trên một lát ở tab **Khám phá**.</span><span class="sxs-lookup"><span data-stu-id="addd2-134">You can also select **Set up** on a tile on the **Discover** tab.</span></span>

### <a name="allow-contributors-to-use-a-connection-for-exports"></a><span data-ttu-id="addd2-135">Cho phép người đóng góp sử dụng một kết nối cho các lần xuất</span><span class="sxs-lookup"><span data-stu-id="addd2-135">Allow contributors to use a connection for exports</span></span>

<span data-ttu-id="addd2-136">Khi thiết lập hoặc chỉnh sửa kết nối xuất, bạn hãy chọn người dùng nào được phép sử dụng kết nối cụ thể này để xác định [các nội dung xuất](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="addd2-136">When setting up or editing an export connection, you choose which users are allowed to use this specific connection to define [exports](export-destinations.md).</span></span> <span data-ttu-id="addd2-137">Theo mặc định, một kết nối có sẵn cho người dùng có vai trò quản trị viên.</span><span class="sxs-lookup"><span data-stu-id="addd2-137">By default a connection is available to users with an administrator role.</span></span> <span data-ttu-id="addd2-138">Bạn có thể thay đổi thiết đặt này trong **Chọn người có thể sử dụng kết nối này** và cho phép người dùng có vai trò người đóng góp sử dụng kết nối này.</span><span class="sxs-lookup"><span data-stu-id="addd2-138">You can change this setting under **Choose who can use this connection** and allow users with contributor role to use this connection.</span></span>

- <span data-ttu-id="addd2-139">Những người đóng góp sẽ không thể xem hoặc chỉnh sửa kết nối.</span><span class="sxs-lookup"><span data-stu-id="addd2-139">Contributors won't be able to view or edit the connection.</span></span> <span data-ttu-id="addd2-140">Họ sẽ chỉ thấy tên hiển thị và loại kết nối khi tạo một nội dung xuất.</span><span class="sxs-lookup"><span data-stu-id="addd2-140">They will only see the display name and its type when creating an export.</span></span>
- <span data-ttu-id="addd2-141">Bằng cách chia sẻ kết nối, bạn cho phép những người đóng góp sử dụng kết nối.</span><span class="sxs-lookup"><span data-stu-id="addd2-141">By sharing a connection, you allow contributors to use a connection.</span></span> <span data-ttu-id="addd2-142">Những người đóng góp sẽ thấy các kết nối được chia sẻ khi họ thiết lập chế độ xuất.</span><span class="sxs-lookup"><span data-stu-id="addd2-142">Contributors will see shared connections when they set up exports.</span></span> <span data-ttu-id="addd2-143">Họ có thể quản lý mọi lần xuất sử dụng kết nối cụ thể này.</span><span class="sxs-lookup"><span data-stu-id="addd2-143">They can manage every export that uses this specific connection.</span></span>
- <span data-ttu-id="addd2-144">Bạn có thể thay đổi thiết đặt này trong khi vẫn giữ nội dung xuất đo những người đóng góp xác định.</span><span class="sxs-lookup"><span data-stu-id="addd2-144">You can change this setting while keeping the exports that have already been defined by contributors.</span></span>

## <a name="edit-a-connection"></a><span data-ttu-id="addd2-145">Chỉnh sửa kết nối</span><span class="sxs-lookup"><span data-stu-id="addd2-145">Edit a connection</span></span>

1. <span data-ttu-id="addd2-146">Đi đến **Quản trị viên** > **Kết nối (bản xem trước)**.</span><span class="sxs-lookup"><span data-stu-id="addd2-146">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="addd2-147">Đi đến tab **Kết nối**.</span><span class="sxs-lookup"><span data-stu-id="addd2-147">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="addd2-148">Chọn dấu ba chấm dọc cho kết nối mà bạn muốn chỉnh sửa.</span><span class="sxs-lookup"><span data-stu-id="addd2-148">Select the vertical ellipsis for the connection you want to edit.</span></span>

1. <span data-ttu-id="addd2-149">Chọn **Chỉnh sửa**.</span><span class="sxs-lookup"><span data-stu-id="addd2-149">Select **Edit**.</span></span>

1. <span data-ttu-id="addd2-150">Thay đổi các giá trị mà bạn muốn cập nhật rồi chọn **Lưu**.</span><span class="sxs-lookup"><span data-stu-id="addd2-150">Change the values you want to update and select **Save**.</span></span>

## <a name="remove-a-connection"></a><span data-ttu-id="addd2-151">Loại bỏ kết nối</span><span class="sxs-lookup"><span data-stu-id="addd2-151">Remove a connection</span></span>

<span data-ttu-id="addd2-152">Nếu kết nối mà bạn đang loại bỏ được dùng cho các nội dung bổ sung hoặc nội dung xuất, thì trước tiên, bạn cần gỡ bỏ hoặc loại bỏ các nội dung bổ sung hoặc nội dung xuất đó.</span><span class="sxs-lookup"><span data-stu-id="addd2-152">If the connection you are removing is used by enrichments or exports, you first need to detach or remove them.</span></span> <span data-ttu-id="addd2-153">Hộp thoại loại bỏ sẽ hướng dẫn bạn chuyển đến các nội dung bổ sung hoặc nội dung xuất có liên quan.</span><span class="sxs-lookup"><span data-stu-id="addd2-153">The remove dialog will guide you to the relevant enrichments or exports.</span></span> 

<span data-ttu-id="addd2-154">Các nội dung bổ sung và nội dung xuất đã gỡ bỏ chuyển sang chế độ không hoạt động.</span><span class="sxs-lookup"><span data-stu-id="addd2-154">Detached enrichments and exports become inactive.</span></span> <span data-ttu-id="addd2-155">Bạn hãy kích hoạt lại các nội dung bổ sung và nội dung xuất đã gỡ bỏ bằng cách thêm một kết nối khác vào chúng trên trang [Nội dung bổ sung](enrichment-hub.md) hoặc [Nội dung xuất](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="addd2-155">You reactivate them by adding another connection to them on the [Enrichments](enrichment-hub.md) or [Exports](export-destinations.md) page.</span></span>

1. <span data-ttu-id="addd2-156">Đi đến **Quản trị viên** > **Kết nối (bản xem trước)**.</span><span class="sxs-lookup"><span data-stu-id="addd2-156">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="addd2-157">Đi đến tab **Kết nối**.</span><span class="sxs-lookup"><span data-stu-id="addd2-157">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="addd2-158">Chọn dấu ba chấm dọc cho kết nối mà bạn muốn loại bỏ.</span><span class="sxs-lookup"><span data-stu-id="addd2-158">Select the vertical ellipsis for the connection you want to remove.</span></span>

1. <span data-ttu-id="addd2-159">Chọn **Xóa** trong menu thả xuống.</span><span class="sxs-lookup"><span data-stu-id="addd2-159">Select **Remove** from the dropdown menu.</span></span> <span data-ttu-id="addd2-160">Một hộp thoại xác nhận sẽ xuất hiện.</span><span class="sxs-lookup"><span data-stu-id="addd2-160">A confirmation dialog appears.</span></span>

   1. <span data-ttu-id="addd2-161">Nếu có các nội dung bổ sung hoặc nội dung xuất sử dụng kết nối này, hãy chọn nút để xem những gì đang sử dụng kết nối.</span><span class="sxs-lookup"><span data-stu-id="addd2-161">If there are enrichments or exports using this connection, select the button to see what's using the connection.</span></span>
      - <span data-ttu-id="addd2-162">**Nội dung xuất:** Bạn có thể chọn loại bỏ hoặc ngắt kết nối các nội dung xuất để có thể loại bỏ kết nối.</span><span class="sxs-lookup"><span data-stu-id="addd2-162">**Exports:** You can choose to either remove or disconnect the exports to be able to remove the connection.</span></span> <span data-ttu-id="addd2-163">Để ngắt kết nối nội dung xuất, quản trị viên có thể sử dụng thao tác **Ngắt kết nối**.</span><span class="sxs-lookup"><span data-stu-id="addd2-163">To disconnect an export, administrators can use the **Disconnect** action.</span></span> <span data-ttu-id="addd2-164">Hành động này có thể áp dụng cho từng nội dung xuất và nhiều nội dung xuất đã chọn.</span><span class="sxs-lookup"><span data-stu-id="addd2-164">This action is available for individual and multiple selected exports.</span></span> <span data-ttu-id="addd2-165">Bằng cách ngắt kết nối, bạn vẫn giữ được cấu hình xuất, nhưng cấu hình này sẽ không chạy cho đến khi bạn thêm một kết nối khác.</span><span class="sxs-lookup"><span data-stu-id="addd2-165">By disconnecting you keep the export config, but it won't be run until another connection is added to it.</span></span>
      - <span data-ttu-id="addd2-166">**Phiên tăng cường:** Bạn có thể chọn loại bỏ hoặc vô hiệu hóa các nội dung bổ sung để có thể loại bỏ kết nối.</span><span class="sxs-lookup"><span data-stu-id="addd2-166">**Enrichments:** You can choose to either remove or deactivate the enrichments to be able to remove the connection.</span></span> 
   1. <span data-ttu-id="addd2-167">Khi kết nối không còn thành phần phụ thuộc nữa, hãy quay lại **Quản trị viên** > **Kết nối** và thử loại bỏ kết nối một lần nữa.</span><span class="sxs-lookup"><span data-stu-id="addd2-167">Once the connection has no more dependencies, go back to **Admin** > **Connections** and try removing the connection again.</span></span>

1. <span data-ttu-id="addd2-168">Để xác nhận xóa, hãy chọn **Loại bỏ**.</span><span class="sxs-lookup"><span data-stu-id="addd2-168">To confirm the deletion, select **Remove**.</span></span>

