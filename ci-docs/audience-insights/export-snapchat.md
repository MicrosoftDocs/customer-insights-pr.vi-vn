---
title: Xuất dữ liệu Customer Insights sang Snapchat
description: Tìm hiểu cách đặt cấu hình kết nối và xuất sang Snapchat.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d3dae7f0fef1fc3792c90c8ac0d3b037f5c0923d
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760665"
---
# <a name="export-segment-lists-to-snapchat-preview"></a><span data-ttu-id="f7b53-103">Xuất danh sách phân khúc sang Snapchat (bản xem trước)</span><span class="sxs-lookup"><span data-stu-id="f7b53-103">Export segment lists to Snapchat (preview)</span></span>

<span data-ttu-id="f7b53-104">Xuất các phân khúc hồ sơ khách hàng hợp nhất sang Snapchat và sử dụng chúng cho quảng cáo.</span><span class="sxs-lookup"><span data-stu-id="f7b53-104">Export segments of unified customer profiles to Snapchat and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="f7b53-105">Điều kiện tiên quyết để kết nối</span><span class="sxs-lookup"><span data-stu-id="f7b53-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="f7b53-106">Bạn có một [Tài khoản Snapchat Business](https://business.snapchat.com/), một [Tài khoản Snapchat Ads](https://ads.snapchat.com/) và thông tin xác thực tương ứng của quản trị viên.</span><span class="sxs-lookup"><span data-stu-id="f7b53-106">You have a [Snapchat Business account](https://business.snapchat.com/), a [Snapchat Ads account](https://ads.snapchat.com/), and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="f7b53-107">Bạn có [các phân đoạn được định cấu hình](segments.md) trong thông tin chi tiết về đối tượng.</span><span class="sxs-lookup"><span data-stu-id="f7b53-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="f7b53-108">Hồ sơ khách hàng hợp nhất trong các phân đoạn đã xuất chứa các trường đại diện cho địa chỉ email.</span><span class="sxs-lookup"><span data-stu-id="f7b53-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="f7b53-109">Các giới hạn đã biết</span><span class="sxs-lookup"><span data-stu-id="f7b53-109">Known limitations</span></span>

- <span data-ttu-id="f7b53-110">Chỉ được xuất các phân khúc sang Snapchat.</span><span class="sxs-lookup"><span data-stu-id="f7b53-110">Exporting to Snapchat is limited to segments.</span></span>
- <span data-ttu-id="f7b53-111">Có thể mất tới 15 phút để hoàn thành quá trình xuất tối đa 1 triệu hồ sơ sang Snapchat.</span><span class="sxs-lookup"><span data-stu-id="f7b53-111">Exporting up to 1 million profiles to Snapchat can take up to 15 minutes to complete.</span></span> 

## <a name="set-up-connection-to-snapchat"></a><span data-ttu-id="f7b53-112">Thiết lập kết nối với Snapchat</span><span class="sxs-lookup"><span data-stu-id="f7b53-112">Set up connection to Snapchat</span></span>

1. <span data-ttu-id="f7b53-113">Đi đến **Quản trị viên** > **Kết nối**.</span><span class="sxs-lookup"><span data-stu-id="f7b53-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="f7b53-114">Chọn **Thêm kết nối** rồi chọn **Snapchat** để đặt cấu hình kết nối.</span><span class="sxs-lookup"><span data-stu-id="f7b53-114">Select **Add connection** and choose **Snapchat** to configure the connection.</span></span>

1. <span data-ttu-id="f7b53-115">Đặt tên dễ nhận biết cho kết nối trong trường **Tên hiển thị**.</span><span class="sxs-lookup"><span data-stu-id="f7b53-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="f7b53-116">Tên và loại kết nối mô tả kết nối này.</span><span class="sxs-lookup"><span data-stu-id="f7b53-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="f7b53-117">Bạn nên chọn một tên giải thích mục đích và mục tiêu của kết nối.</span><span class="sxs-lookup"><span data-stu-id="f7b53-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="f7b53-118">Chọn người có thể sử dụng kết nối này.</span><span class="sxs-lookup"><span data-stu-id="f7b53-118">Choose who can use this connection.</span></span> <span data-ttu-id="f7b53-119">Nếu bạn không thực hiện hành động nào, giá trị mặc định sẽ là Quản trị viên.</span><span class="sxs-lookup"><span data-stu-id="f7b53-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="f7b53-120">Để biết thêm thông tin, hãy xem [Cho phép người đóng góp sử dụng một kết nối cho các lần xuất](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="f7b53-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="f7b53-121">Chọn **Tôi đồng ý** để xác nhận **Quyền riêng tư về dữ liệu và sự tuân thủ**.</span><span class="sxs-lookup"><span data-stu-id="f7b53-121">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="f7b53-122">Chọn **Kết nối** để khởi tạo kết nối với Snapchat.</span><span class="sxs-lookup"><span data-stu-id="f7b53-122">Select **Connect** to initialize the connection to Snapchat.</span></span>

1. <span data-ttu-id="f7b53-123">Chọn **Xác thực với Snapchat** và cung cấp thông tin xác thực quản trị viên của bạn cho Snapchat.</span><span class="sxs-lookup"><span data-stu-id="f7b53-123">Select **Authenticate with Snapchat** and provide your admin credentials for Snapchat.</span></span> 

1. <span data-ttu-id="f7b53-124">Chọn **Thêm chính bạn là người dùng xuất** và cung cấp thông tin xác thực Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="f7b53-124">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="f7b53-125">Chọn **Lưu** để hoàn thành kết nối.</span><span class="sxs-lookup"><span data-stu-id="f7b53-125">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="f7b53-126">Đặt cấu hình xuất</span><span class="sxs-lookup"><span data-stu-id="f7b53-126">Configure an export</span></span>

<span data-ttu-id="f7b53-127">Bạn có thể đặt cấu hình lần xuất này nếu bạn có quyền truy cập vào kết nối thuộc loại này.</span><span class="sxs-lookup"><span data-stu-id="f7b53-127">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="f7b53-128">Để biết thêm thông tin, hãy xem [Các quyền cần thiết để đặt cấu hình xuất](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="f7b53-128">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="f7b53-129">Đi tới **Dữ liệu** > **Nội dung xuất**.</span><span class="sxs-lookup"><span data-stu-id="f7b53-129">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="f7b53-130">Để tạo một nội dung xuất mới, hãy chọn **Thêm đích**.</span><span class="sxs-lookup"><span data-stu-id="f7b53-130">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="f7b53-131">Trong trường **Kết nối để xuất**, hãy chọn một kết nối từ phần Snapchat.</span><span class="sxs-lookup"><span data-stu-id="f7b53-131">In the **Connection for export** field, choose a connection from the Snapchat section.</span></span> <span data-ttu-id="f7b53-132">Nếu bạn không thấy tên phần này, tức là không có kết nối nào thuộc loại này dành cho bạn.</span><span class="sxs-lookup"><span data-stu-id="f7b53-132">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="f7b53-133">Nhập [**ID đối tượng Snapchat**](https://businesshelp.snapchat.com/s/article/custom-audiences).</span><span class="sxs-lookup"><span data-stu-id="f7b53-133">Enter the [**Snapchat Audience ID**](https://businesshelp.snapchat.com/s/article/custom-audiences).</span></span>

1. <span data-ttu-id="f7b53-134">Trong phần **So khớp dữ liệu**, trong trường **Email**, chọn trường trong hồ sơ khách hàng hợp nhất trình bày địa chỉ email của khách hàng.</span><span class="sxs-lookup"><span data-stu-id="f7b53-134">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="f7b53-135">Bạn phải xuất các phân khúc sang Snapchat.</span><span class="sxs-lookup"><span data-stu-id="f7b53-135">It's required to export segments to Snapchat.</span></span>

1. <span data-ttu-id="f7b53-136">Chọn phân khúc mà bạn muốn xuất.</span><span class="sxs-lookup"><span data-stu-id="f7b53-136">Select the segments you want to export.</span></span> 

1. <span data-ttu-id="f7b53-137">Chọn **Lưu**.</span><span class="sxs-lookup"><span data-stu-id="f7b53-137">Select **Save**.</span></span>

<span data-ttu-id="f7b53-138">Việc lưu một nội dung xuất sẽ không chạy nội dung xuất đó ngay lập tức.</span><span class="sxs-lookup"><span data-stu-id="f7b53-138">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="f7b53-139">Nội dung xuất chạy trong mỗi lần [làm mới theo lịch trình](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="f7b53-139">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="f7b53-140">Bạn cũng có thể [xuất dữ liệu theo yêu cầu](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="f7b53-140">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="f7b53-141">Quyền riêng tư về dữ liệu và sự tuân thủ</span><span class="sxs-lookup"><span data-stu-id="f7b53-141">Data privacy and compliance</span></span>

<span data-ttu-id="f7b53-142">Khi bật Dynamics 365 Customer Insights để truyền dữ liệu đến Snapchat, bạn cho phép chuyển dữ liệu ra bên ngoài ranh giới tuân thủ của Dynamics 365 Customer Insights, bao gồm cả dữ liệu có thể nhạy cảm như Dữ liệu cá nhân.</span><span class="sxs-lookup"><span data-stu-id="f7b53-142">When you enable Dynamics 365 Customer Insights to transmit data to Snapchat, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="f7b53-143">Microsoft sẽ chuyển những dữ liệu đó theo chỉ dẫn của bạn, nhưng bạn có trách nhiệm đảm bảo rằng Snapchat đáp ứng mọi nghĩa vụ về quyền riêng tư hoặc bảo mật mà bạn có thể có.</span><span class="sxs-lookup"><span data-stu-id="f7b53-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Snapchat meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="f7b53-144">Để biết thêm thông tin, hãy xem [Tuyên bố về Quyền riêng tư của Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="f7b53-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="f7b53-145">Quản trị viên Dynamics 365 Customer Insights của bạn có thể xóa đích xuất này bất cứ lúc nào để ngừng sử dụng chức năng này.</span><span class="sxs-lookup"><span data-stu-id="f7b53-145">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
