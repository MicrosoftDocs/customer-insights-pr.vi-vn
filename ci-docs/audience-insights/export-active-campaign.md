---
title: Xuất dữ liệu Customer Insights sang ActiveCampaign
description: Tìm hiểu cách định cấu hình kết nối và xuất sang ActiveCampaign.
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d85fa9836618e27f7f3da6ce17c07b4bc89e187
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314695"
---
# <a name="export-segments-to-activecampaign-preview"></a><span data-ttu-id="3f017-103">Xuất phân khúc sang ActiveCampaign (bản xem trước)</span><span class="sxs-lookup"><span data-stu-id="3f017-103">Export segments to ActiveCampaign (preview)</span></span>

<span data-ttu-id="3f017-104">Xuất phân khúc hồ sơ khách hàng hợp nhất sang ActiveCampaign và sử dụng chúng cho các hoạt động tiếp thị.</span><span class="sxs-lookup"><span data-stu-id="3f017-104">Export segments of unified customer profiles to ActiveCampaign and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3f017-105">Điều kiện tiên quyết</span><span class="sxs-lookup"><span data-stu-id="3f017-105">Prerequisites</span></span>

-   <span data-ttu-id="3f017-106">Bạn có một [Tài khoản ActiveCampaign](https://www.activecampaign.com/) và thông tin xác thực tương ứng của quản trị viên.</span><span class="sxs-lookup"><span data-stu-id="3f017-106">You have an [ActiveCampaign account](https://www.activecampaign.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="3f017-107">Bạn có [các phân khúc được định cấu hình](segments.md) trong thông tin chuyên sâu về đối tượng.</span><span class="sxs-lookup"><span data-stu-id="3f017-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="3f017-108">Hồ sơ khách hàng hợp nhất trong các phân khúc đã xuất chứa trường có địa chỉ email.</span><span class="sxs-lookup"><span data-stu-id="3f017-108">Unified customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="3f017-109">Các hạn chế đã biết</span><span class="sxs-lookup"><span data-stu-id="3f017-109">Known limitations</span></span>

- <span data-ttu-id="3f017-110">Bạn có thể xuất đến 1 triệu hồ sơ/lần sang ActiveCampaign và quy trình này có thể mất tối đa 90 phút để hoàn thành.</span><span class="sxs-lookup"><span data-stu-id="3f017-110">You can export up to 1 million profiles per export to ActiveCampaign and it can take up to 90 minutes to complete.</span></span>
- <span data-ttu-id="3f017-111">Việc xuất sang ActiveCampaign bị giới hạn theo phân khúc.</span><span class="sxs-lookup"><span data-stu-id="3f017-111">Exporting to ActiveCampaign is limited to segments.</span></span>
- <span data-ttu-id="3f017-112">Số lượng hồ sơ mà bạn có thể xuất sang ActiveCampaign tùy thuộc vào hợp đồng của bạn với ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="3f017-112">The number of profiles that you can export to ActiveCampaign depends on your contract with ActiveCampaign.</span></span>

## <a name="set-up-connection-to-activecampaign"></a><span data-ttu-id="3f017-113">Thiết lập kết nối với ActiveCampaign</span><span class="sxs-lookup"><span data-stu-id="3f017-113">Set up connection to ActiveCampaign</span></span>

1. <span data-ttu-id="3f017-114">Đi đến **Quản trị viên** > **Kết nối**.</span><span class="sxs-lookup"><span data-stu-id="3f017-114">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="3f017-115">Chọn **Thêm kết nối** rồi chọn **ActiveCampaign** để định cấu hình kết nối.</span><span class="sxs-lookup"><span data-stu-id="3f017-115">Select **Add connection** and choose **ActiveCampaign** to configure the connection.</span></span>

1. <span data-ttu-id="3f017-116">Đặt tên dễ nhận biết cho kết nối trong trường **Tên hiển thị**.</span><span class="sxs-lookup"><span data-stu-id="3f017-116">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="3f017-117">Tên và loại kết nối mô tả kết nối này.</span><span class="sxs-lookup"><span data-stu-id="3f017-117">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="3f017-118">Bạn nên chọn một tên giải thích mục đích và mục tiêu của kết nối.</span><span class="sxs-lookup"><span data-stu-id="3f017-118">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="3f017-119">Chọn người có thể sử dụng kết nối này.</span><span class="sxs-lookup"><span data-stu-id="3f017-119">Choose who can use this connection.</span></span> <span data-ttu-id="3f017-120">Theo mặc định, giá trị này là quản trị viên.</span><span class="sxs-lookup"><span data-stu-id="3f017-120">By default, it's only administrators.</span></span> <span data-ttu-id="3f017-121">Để biết thêm thông tin, hãy xem [Cho phép người đóng góp sử dụng một kết nối cho các lần xuất](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="3f017-121">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="3f017-122">Nhập [Khóa API ActiveCampaign và Tên máy chủ Điểm cuối REST](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key).</span><span class="sxs-lookup"><span data-stu-id="3f017-122">Enter your [ActiveCampaign API Key and REST Endpoint Hostname](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key).</span></span> <span data-ttu-id="3f017-123">Tên máy chủ điểm cuối REST chỉ là tên máy chủ, không có https://.</span><span class="sxs-lookup"><span data-stu-id="3f017-123">The REST Endpoint Hostname is the hostname only, without https://.</span></span> 

1. <span data-ttu-id="3f017-124">Chọn **Tôi đồng ý** để xác nhận **Quyền riêng tư về dữ liệu và sự tuân thủ**.</span><span class="sxs-lookup"><span data-stu-id="3f017-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="3f017-125">Chọn **Kết nối** để khởi tạo kết nối đến ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="3f017-125">Select **Connect** to initialize the connection to ActiveCampaign.</span></span>

1. <span data-ttu-id="3f017-126">Chọn **Thêm chính bạn là người dùng xuất** và cung cấp thông tin xác thực Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="3f017-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="3f017-127">Chọn **Lưu** để hoàn thành kết nối.</span><span class="sxs-lookup"><span data-stu-id="3f017-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="3f017-128">Định cấu hình xuất</span><span class="sxs-lookup"><span data-stu-id="3f017-128">Configure an export</span></span>

<span data-ttu-id="3f017-129">Bạn có thể định cấu hình nội dung xuất nếu có quyền truy cập vào kết nối thuộc loại này.</span><span class="sxs-lookup"><span data-stu-id="3f017-129">You can configure an export if you have access to a connection of this type.</span></span> <span data-ttu-id="3f017-130">Để biết thêm thông tin, hãy xem [Các quyền cần thiết để định cấu hình xuất](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="3f017-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="3f017-131">Đi tới **Dữ liệu** > **Nội dung xuất**.</span><span class="sxs-lookup"><span data-stu-id="3f017-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="3f017-132">Để tạo một nội dung xuất mới, hãy chọn **Thêm đích**.</span><span class="sxs-lookup"><span data-stu-id="3f017-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="3f017-133">Trong trường **Kết nối để xuất**, hãy chọn một kết nối từ phần ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="3f017-133">In the **Connection for export** field, choose a connection from the ActiveCampaign section.</span></span> <span data-ttu-id="3f017-134">Nếu bạn không thấy tên phần này, tức là không có kết nối nào thuộc loại này dành cho bạn.</span><span class="sxs-lookup"><span data-stu-id="3f017-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="3f017-135">Nhập [**ID Danh sách ActiveCampaign**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).</span><span class="sxs-lookup"><span data-stu-id="3f017-135">Enter your [**ActiveCampaign List ID**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).</span></span>    

3. <span data-ttu-id="3f017-136">Trong phần **So khớp dữ liệu**, trong trường **Email**, chọn trường trong hồ sơ khách hàng hợp nhất trình bày địa chỉ email của khách hàng.</span><span class="sxs-lookup"><span data-stu-id="3f017-136">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="3f017-137">Bạn phải xuất phân khúc sang ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="3f017-137">It's required to export segments to ActiveCampaign.</span></span> <span data-ttu-id="3f017-138">Bạn có thể xuất Tên, Họ và Số điện thoại để tạo nhiều email được cá nhân hóa hơn.</span><span class="sxs-lookup"><span data-stu-id="3f017-138">Optionally, you can export First name, Last name, and Phone to create more personalized emails.</span></span> <span data-ttu-id="3f017-139">Chọn Thêm thuộc tính để ánh xạ những trường này.</span><span class="sxs-lookup"><span data-stu-id="3f017-139">Select Add attribute to map these fields.</span></span>

1. <span data-ttu-id="3f017-140">Chọn **Lưu**.</span><span class="sxs-lookup"><span data-stu-id="3f017-140">Select **Save**.</span></span>

<span data-ttu-id="3f017-141">Việc lưu một nội dung xuất sẽ không chạy nội dung xuất đó ngay lập tức.</span><span class="sxs-lookup"><span data-stu-id="3f017-141">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="3f017-142">Nội dung xuất chạy trong mỗi lần [làm mới theo lịch trình](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="3f017-142">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="3f017-143">Bạn cũng có thể [xuất dữ liệu theo yêu cầu](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="3f017-143">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="3f017-144">Quyền riêng tư về dữ liệu và sự tuân thủ</span><span class="sxs-lookup"><span data-stu-id="3f017-144">Data privacy and compliance</span></span>

<span data-ttu-id="3f017-145">Khi bật Dynamics 365 Customer Insights để truyền dữ liệu tới ActiveCampaign, bạn cho phép truyền dữ liệu ra ngoài phạm vi tuân thủ cho Dynamics 365 Customer Insights, bao gồm dữ liệu có khả năng là thông tin nhạy cảm, chẳng hạn như Dữ liệu cá nhân.</span><span class="sxs-lookup"><span data-stu-id="3f017-145">When you enable Dynamics 365 Customer Insights to transmit data to ActiveCampaign, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="3f017-146">Microsoft sẽ truyền những dữ liệu đó theo chỉ dẫn của bạn, nhưng bạn có trách nhiệm đảm bảo rằng ActiveCampaign đáp ứng mọi nghĩa vụ về quyền riêng tư hoặc bảo mật mà bạn có thể có.</span><span class="sxs-lookup"><span data-stu-id="3f017-146">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that ActiveCampaign meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="3f017-147">Để biết thêm thông tin, hãy xem [Tuyên bố về Quyền riêng tư của Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="3f017-147">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="3f017-148">Quản trị viên Dynamics 365 Customer Insights của bạn có thể xóa đích xuất này bất cứ lúc nào để ngừng việc sử dụng chức năng này.</span><span class="sxs-lookup"><span data-stu-id="3f017-148">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
