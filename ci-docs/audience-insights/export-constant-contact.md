---
title: Xuất dữ liệu Customer Insights sang Constant Contact
description: Tìm hiểu cách đặt cấu hình kết nối và xuất sang Constant Contact.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3a9372cc4ffa4fb112a96b1286aee9dc35059a50
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760666"
---
# <a name="export-segment-lists-to-constant-contact-preview"></a><span data-ttu-id="6b74b-103">Xuất danh sách phân khúc sang Constant Contact (bản xem trước)</span><span class="sxs-lookup"><span data-stu-id="6b74b-103">Export segment lists to Constant Contact (preview)</span></span>

<span data-ttu-id="6b74b-104">Xuất các phân khúc hồ sơ khách hàng hợp nhất sang Constant Contact và sử dụng chúng cho các hoạt động tiếp thị.</span><span class="sxs-lookup"><span data-stu-id="6b74b-104">Export segments of unified customer profiles to Constant Contact and use them for marketing activities.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="6b74b-105">Điều kiện tiên quyết để kết nối</span><span class="sxs-lookup"><span data-stu-id="6b74b-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="6b74b-106">Bạn có một [Tài khoản Constant Contact](https://www.constantcontact.com/account-home) và thông tin xác thực tương ứng của quản trị viên.</span><span class="sxs-lookup"><span data-stu-id="6b74b-106">You have an [Constant Contact account](https://www.constantcontact.com/account-home) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="6b74b-107">Bạn có [các phân đoạn được định cấu hình](segments.md) trong thông tin chi tiết về đối tượng.</span><span class="sxs-lookup"><span data-stu-id="6b74b-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="6b74b-108">Hồ sơ khách hàng hợp nhất trong các phân đoạn đã xuất chứa các trường đại diện cho địa chỉ email.</span><span class="sxs-lookup"><span data-stu-id="6b74b-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="6b74b-109">Các giới hạn đã biết</span><span class="sxs-lookup"><span data-stu-id="6b74b-109">Known limitations</span></span>

- <span data-ttu-id="6b74b-110">Bạn có thể xuất tối đa 1 triệu hồ sơ trong mỗi lần xuất sang Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="6b74b-110">You can export up to 1 million profiles per export to Constant Contact.</span></span>
- <span data-ttu-id="6b74b-111">Chỉ được xuất các phân khúc sang Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="6b74b-111">Exporting to Constant Contact is limited to segments.</span></span>
- <span data-ttu-id="6b74b-112">Có thể mất tới 1 giờ để hoàn thành quá trình xuất tối đa 1 triệu hồ sơ sang Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="6b74b-112">Exporting up to 1 million profiles to Constant Contact can take up to 1 hour to complete.</span></span> 
- <span data-ttu-id="6b74b-113">Số lượng hồ sơ mà bạn có thể xuất sang Constant Contact phụ thuộc và bị giới hạn theo hợp đồng của bạn với Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="6b74b-113">The number of profiles that you can export to Constant Contact is dependent and limited on your contract with Constant Contact.</span></span>

## <a name="set-up-connection-to-constant-contact"></a><span data-ttu-id="6b74b-114">Thiết lập kết nối với Constant Contact</span><span class="sxs-lookup"><span data-stu-id="6b74b-114">Set up connection to Constant Contact</span></span>

1. <span data-ttu-id="6b74b-115">Đi đến **Quản trị viên** > **Kết nối**.</span><span class="sxs-lookup"><span data-stu-id="6b74b-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="6b74b-116">Chọn **Thêm kết nối** rồi chọn **Constant Contact** để đặt cấu hình kết nối.</span><span class="sxs-lookup"><span data-stu-id="6b74b-116">Select **Add connection** and choose **Constant Contact** to configure the connection.</span></span>

1. <span data-ttu-id="6b74b-117">Đặt tên dễ nhận biết cho kết nối trong trường **Tên hiển thị**.</span><span class="sxs-lookup"><span data-stu-id="6b74b-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="6b74b-118">Tên và loại kết nối mô tả kết nối này.</span><span class="sxs-lookup"><span data-stu-id="6b74b-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="6b74b-119">Bạn nên chọn một tên giải thích mục đích và mục tiêu của kết nối.</span><span class="sxs-lookup"><span data-stu-id="6b74b-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="6b74b-120">Chọn người có thể sử dụng kết nối này.</span><span class="sxs-lookup"><span data-stu-id="6b74b-120">Choose who can use this connection.</span></span> <span data-ttu-id="6b74b-121">Nếu bạn không thực hiện hành động nào, giá trị mặc định sẽ là Quản trị viên.</span><span class="sxs-lookup"><span data-stu-id="6b74b-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="6b74b-122">Để biết thêm thông tin, hãy xem [Cho phép người đóng góp sử dụng một kết nối cho các lần xuất](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="6b74b-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="6b74b-123">Chọn **Tôi đồng ý** để xác nhận **Quyền riêng tư về dữ liệu và sự tuân thủ**.</span><span class="sxs-lookup"><span data-stu-id="6b74b-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="6b74b-124">Chọn **Kết nối** để khởi tạo kết nối với Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="6b74b-124">Select **Connect** to initialize the connection to Constant Contact.</span></span>

1. <span data-ttu-id="6b74b-125">Chọn **Xác thực với AdRoll** và cung cấp thông tin xác thực quản trị viên của bạn cho Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="6b74b-125">Select **Authenticate with AdRoll** and provide your admin credentials for Constant Contact.</span></span> 

1. <span data-ttu-id="6b74b-126">Chọn **Thêm chính bạn là người dùng xuất** và cung cấp thông tin xác thực Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="6b74b-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="6b74b-127">Chọn **Lưu** để hoàn thành kết nối.</span><span class="sxs-lookup"><span data-stu-id="6b74b-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="6b74b-128">Đặt cấu hình xuất</span><span class="sxs-lookup"><span data-stu-id="6b74b-128">Configure an export</span></span>

<span data-ttu-id="6b74b-129">Bạn có thể đặt cấu hình lần xuất này nếu bạn có quyền truy cập vào kết nối thuộc loại này.</span><span class="sxs-lookup"><span data-stu-id="6b74b-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="6b74b-130">Để biết thêm thông tin, hãy xem [Các quyền cần thiết để đặt cấu hình xuất](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="6b74b-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="6b74b-131">Đi tới **Dữ liệu** > **Nội dung xuất**.</span><span class="sxs-lookup"><span data-stu-id="6b74b-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="6b74b-132">Để tạo một nội dung xuất mới, hãy chọn **Thêm đích**.</span><span class="sxs-lookup"><span data-stu-id="6b74b-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="6b74b-133">Trong trường **Kết nối để xuất**, hãy chọn một kết nối từ phần Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="6b74b-133">In the **Connection for export** field, choose a connection from the Constant Contact section.</span></span> <span data-ttu-id="6b74b-134">Nếu bạn không thấy tên phần này, tức là không có kết nối nào thuộc loại này dành cho bạn.</span><span class="sxs-lookup"><span data-stu-id="6b74b-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="6b74b-135">Nhập [**ID danh sách Constant Contact**](https://app.constantcontact.com/pages/contacts/ui#lists).</span><span class="sxs-lookup"><span data-stu-id="6b74b-135">Enter your [**Constant Contact List ID**](https://app.constantcontact.com/pages/contacts/ui#lists).</span></span> <span data-ttu-id="6b74b-136">Mở một danh sách trong Constant Contact để tìm ID danh sách trong URL.</span><span class="sxs-lookup"><span data-stu-id="6b74b-136">Open a list in Constant Contact to find the list ID in the URL.</span></span>

1. <span data-ttu-id="6b74b-137">Trong phần **So khớp dữ liệu**, trong trường **Email**, chọn trường trong hồ sơ khách hàng hợp nhất trình bày địa chỉ email của khách hàng.</span><span class="sxs-lookup"><span data-stu-id="6b74b-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="6b74b-138">Bạn phải xuất các phân khúc sang Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="6b74b-138">It's required to export segments to Constant Contact.</span></span>

1. <span data-ttu-id="6b74b-139">Theo tùy chọn, bạn có thể xuất Tên và Họ dưới dạng trường bổ sung để tạo thêm email cá nhân hóa.</span><span class="sxs-lookup"><span data-stu-id="6b74b-139">Optionally, you can export First name and Last name as additional fields to create more personalized emails.</span></span> <span data-ttu-id="6b74b-140">Chọn **Thêm thuộc tính** để ánh xạ những trường này.</span><span class="sxs-lookup"><span data-stu-id="6b74b-140">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="6b74b-141">Chọn phân khúc mà bạn muốn xuất.</span><span class="sxs-lookup"><span data-stu-id="6b74b-141">Select the segments you want to export.</span></span>

1. <span data-ttu-id="6b74b-142">Chọn **Lưu**.</span><span class="sxs-lookup"><span data-stu-id="6b74b-142">Select **Save**.</span></span>

<span data-ttu-id="6b74b-143">Việc lưu một nội dung xuất sẽ không chạy nội dung xuất đó ngay lập tức.</span><span class="sxs-lookup"><span data-stu-id="6b74b-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="6b74b-144">Nội dung xuất chạy trong mỗi lần [làm mới theo lịch trình](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="6b74b-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="6b74b-145">Bạn cũng có thể [xuất dữ liệu theo yêu cầu](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="6b74b-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="6b74b-146">Quyền riêng tư về dữ liệu và sự tuân thủ</span><span class="sxs-lookup"><span data-stu-id="6b74b-146">Data privacy and compliance</span></span>

<span data-ttu-id="6b74b-147">Khi bật Dynamics 365 Customer Insights để truyền dữ liệu đến Constant Contact, bạn cho phép chuyển dữ liệu ra bên ngoài ranh giới tuân thủ của Dynamics 365 Customer Insights, bao gồm cả dữ liệu có thể nhạy cảm như Dữ liệu cá nhân.</span><span class="sxs-lookup"><span data-stu-id="6b74b-147">When you enable Dynamics 365 Customer Insights to transmit data to Constant Contact, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="6b74b-148">Microsoft sẽ chuyển những dữ liệu đó theo chỉ dẫn của bạn, nhưng bạn có trách nhiệm đảm bảo rằng Constant Contact đáp ứng mọi nghĩa vụ về quyền riêng tư hoặc bảo mật mà bạn có thể có.</span><span class="sxs-lookup"><span data-stu-id="6b74b-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Constant Contact meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="6b74b-149">Để biết thêm thông tin, hãy xem [Tuyên bố về Quyền riêng tư của Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="6b74b-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="6b74b-150">Quản trị viên Dynamics 365 Customer Insights của bạn có thể xóa đích xuất này bất cứ lúc nào để ngừng sử dụng chức năng này.</span><span class="sxs-lookup"><span data-stu-id="6b74b-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
