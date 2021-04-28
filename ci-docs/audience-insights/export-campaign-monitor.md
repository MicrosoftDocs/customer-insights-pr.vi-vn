---
title: Xuất dữ liệu Customer Insights sang Campaign Monitor
description: Tìm hiểu cách đặt cấu hình kết nối và xuất sang Campaign Monitor.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 7fd6af37b40e21d030a1ace0cd5f8fcc7861c3fa
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760667"
---
# <a name="export-segment-lists-to-campaign-monitor-preview"></a><span data-ttu-id="54ea8-103">Xuất danh sách phân khúc sang Campaign Monitor (bản xem trước)</span><span class="sxs-lookup"><span data-stu-id="54ea8-103">Export segment lists to Campaign Monitor (preview)</span></span>

<span data-ttu-id="54ea8-104">Xuất các phân khúc hồ sơ khách hàng hợp nhất sang Campaign Monitor và sử dụng chúng cho các hoạt động tiếp thị.</span><span class="sxs-lookup"><span data-stu-id="54ea8-104">Export segments of unified customer profiles to Campaign Monitor and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="54ea8-105">Điều kiện tiên quyết</span><span class="sxs-lookup"><span data-stu-id="54ea8-105">Prerequisites</span></span>

-   <span data-ttu-id="54ea8-106">Bạn có một [Tài khoản Campaign Monitor](https://www.campaignmonitor.com/) và thông tin xác thực tương ứng của quản trị viên.</span><span class="sxs-lookup"><span data-stu-id="54ea8-106">You have an [Campaign Monitor account](https://www.campaignmonitor.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="54ea8-107">Bạn có [các phân đoạn được định cấu hình](segments.md) trong thông tin chi tiết về đối tượng.</span><span class="sxs-lookup"><span data-stu-id="54ea8-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="54ea8-108">Hồ sơ khách hàng hợp nhất trong các phân đoạn đã xuất chứa các trường đại diện cho địa chỉ email.</span><span class="sxs-lookup"><span data-stu-id="54ea8-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="54ea8-109">Các giới hạn đã biết</span><span class="sxs-lookup"><span data-stu-id="54ea8-109">Known limitations</span></span>

- <span data-ttu-id="54ea8-110">Bạn có thể xuất tối đa 1 triệu hồ sơ trong mỗi lần xuất sang Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="54ea8-110">You can export up to 1 million profiles per export to Campaign Monitor.</span></span>
- <span data-ttu-id="54ea8-111">Chỉ được xuất các phân khúc sang Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="54ea8-111">Exporting to Campaign Monitor is limited to segments.</span></span>
- <span data-ttu-id="54ea8-112">Có thể mất tới 20 phút để hoàn thành quá trình xuất tối đa 1 triệu hồ sơ sang Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="54ea8-112">Exporting up to 1 million profiles to Campaign Monitor can take up to 20 minutes to complete.</span></span> 
- <span data-ttu-id="54ea8-113">Số lượng hồ sơ mà bạn có thể xuất sang Campaign Monitor phụ thuộc và bị giới hạn theo hợp đồng của bạn với Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="54ea8-113">The number of profiles that you can export to Campaign Monitor is dependent and limited on your contract with Campaign Monitor.</span></span>

## <a name="set-up-connection-to-campaign-monitor"></a><span data-ttu-id="54ea8-114">Thiết lập kết nối với Campaign Monitor</span><span class="sxs-lookup"><span data-stu-id="54ea8-114">Set up connection to Campaign Monitor</span></span>

1. <span data-ttu-id="54ea8-115">Đi đến **Quản trị viên** > **Kết nối**.</span><span class="sxs-lookup"><span data-stu-id="54ea8-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="54ea8-116">Chọn **Thêm kết nối** rồi chọn **Campaign Monitor** để đặt cấu hình kết nối.</span><span class="sxs-lookup"><span data-stu-id="54ea8-116">Select **Add connection** and choose **Campaign Monitor** to configure the connection.</span></span>

1. <span data-ttu-id="54ea8-117">Đặt tên dễ nhận biết cho kết nối trong trường **Tên hiển thị**.</span><span class="sxs-lookup"><span data-stu-id="54ea8-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="54ea8-118">Tên và loại kết nối mô tả kết nối này.</span><span class="sxs-lookup"><span data-stu-id="54ea8-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="54ea8-119">Bạn nên chọn một tên giải thích mục đích và mục tiêu của kết nối.</span><span class="sxs-lookup"><span data-stu-id="54ea8-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="54ea8-120">Chọn người có thể sử dụng kết nối này.</span><span class="sxs-lookup"><span data-stu-id="54ea8-120">Choose who can use this connection.</span></span> <span data-ttu-id="54ea8-121">Nếu bạn không thực hiện hành động nào, giá trị mặc định sẽ là Quản trị viên.</span><span class="sxs-lookup"><span data-stu-id="54ea8-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="54ea8-122">Để biết thêm thông tin, hãy xem [Cho phép người đóng góp sử dụng một kết nối cho các lần xuất](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="54ea8-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="54ea8-123">Chọn **Tôi đồng ý** để xác nhận **Quyền riêng tư về dữ liệu và sự tuân thủ**.</span><span class="sxs-lookup"><span data-stu-id="54ea8-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="54ea8-124">Chọn **Kết nối** để khởi tạo kết nối với Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="54ea8-124">Select **Connect** to initialize the connection to Campaign Monitor.</span></span>

1. <span data-ttu-id="54ea8-125">Chọn **Xác thực với Campaign Monitor** và cung cấp thông tin xác thực quản trị viên của bạn cho Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="54ea8-125">Select **Authenticate with Campaign Monitor** and provide your admin credentials for Campaign Monitor.</span></span>

1. <span data-ttu-id="54ea8-126">Chọn **Thêm chính bạn là người dùng xuất** và cung cấp thông tin xác thực Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="54ea8-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="54ea8-127">Chọn **Lưu** để hoàn thành kết nối.</span><span class="sxs-lookup"><span data-stu-id="54ea8-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="54ea8-128">Đặt cấu hình xuất</span><span class="sxs-lookup"><span data-stu-id="54ea8-128">Configure an export</span></span>

<span data-ttu-id="54ea8-129">Bạn có thể đặt cấu hình lần xuất này nếu bạn có quyền truy cập vào kết nối thuộc loại này.</span><span class="sxs-lookup"><span data-stu-id="54ea8-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="54ea8-130">Để biết thêm thông tin, hãy xem [Các quyền cần thiết để đặt cấu hình xuất](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="54ea8-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="54ea8-131">Đi tới **Dữ liệu** > **Nội dung xuất**.</span><span class="sxs-lookup"><span data-stu-id="54ea8-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="54ea8-132">Để tạo một nội dung xuất mới, hãy chọn **Thêm đích**.</span><span class="sxs-lookup"><span data-stu-id="54ea8-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="54ea8-133">Trong trường **Kết nối để xuất**, hãy chọn một kết nối từ phần Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="54ea8-133">In the **Connection for export** field, choose a connection from the Campaign Monitor section.</span></span> <span data-ttu-id="54ea8-134">Nếu bạn không thấy tên phần này, tức là không có kết nối nào thuộc loại này dành cho bạn.</span><span class="sxs-lookup"><span data-stu-id="54ea8-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="54ea8-135">Nhập [**ID danh sách Campaign Monitor**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).</span><span class="sxs-lookup"><span data-stu-id="54ea8-135">Enter your [**Campaign Monitor List ID**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).</span></span>    
   <span data-ttu-id="54ea8-136">[Tạo khóa API](https://www.campaignmonitor.com/api/getting-started/) từ **Cài đặt tài khoản** trong Campaign Monitor trước tiên để xem ID danh sách API.</span><span class="sxs-lookup"><span data-stu-id="54ea8-136">[Generate the API key](https://www.campaignmonitor.com/api/getting-started/) from **Account Settings** in Campaign Monitor first to view the API list ID.</span></span>  

3. <span data-ttu-id="54ea8-137">Trong phần **So khớp dữ liệu**, trong trường **Email**, chọn trường trong hồ sơ khách hàng hợp nhất trình bày địa chỉ email của khách hàng.</span><span class="sxs-lookup"><span data-stu-id="54ea8-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="54ea8-138">Bạn phải xuất các phân khúc sang Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="54ea8-138">It's required to export segments to Campaign Monitor.</span></span>

1. <span data-ttu-id="54ea8-139">Chọn **Lưu**.</span><span class="sxs-lookup"><span data-stu-id="54ea8-139">Select **Save**.</span></span>

<span data-ttu-id="54ea8-140">Việc lưu một nội dung xuất sẽ không chạy nội dung xuất đó ngay lập tức.</span><span class="sxs-lookup"><span data-stu-id="54ea8-140">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="54ea8-141">Nội dung xuất chạy trong mỗi lần [làm mới theo lịch trình](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="54ea8-141">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="54ea8-142">Bạn cũng có thể [xuất dữ liệu theo yêu cầu](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="54ea8-142">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="54ea8-143">Quyền riêng tư về dữ liệu và sự tuân thủ</span><span class="sxs-lookup"><span data-stu-id="54ea8-143">Data privacy and compliance</span></span>

<span data-ttu-id="54ea8-144">Khi bật Dynamics 365 Customer Insights để truyền dữ liệu đến Campaign Monitor, bạn cho phép chuyển dữ liệu ra bên ngoài ranh giới tuân thủ của Dynamics 365 Customer Insights, bao gồm cả dữ liệu có thể nhạy cảm như Dữ liệu cá nhân.</span><span class="sxs-lookup"><span data-stu-id="54ea8-144">When you enable Dynamics 365 Customer Insights to transmit data to Campaign Monitor, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="54ea8-145">Microsoft sẽ chuyển những dữ liệu đó theo chỉ dẫn của bạn, nhưng bạn có trách nhiệm đảm bảo rằng Campaign Monitor đáp ứng mọi nghĩa vụ về quyền riêng tư hoặc bảo mật mà bạn có thể có.</span><span class="sxs-lookup"><span data-stu-id="54ea8-145">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Campaign Monitor meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="54ea8-146">Để biết thêm thông tin, hãy xem [Tuyên bố về Quyền riêng tư của Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="54ea8-146">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="54ea8-147">Quản trị viên Dynamics 365 Customer Insights của bạn có thể xóa đích xuất này bất cứ lúc nào để ngừng sử dụng chức năng này.</span><span class="sxs-lookup"><span data-stu-id="54ea8-147">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
