---
title: Xuất dữ liệu Customer Insights sang Mailchimp
description: Tìm hiểu cách đặt cấu hình kết nối và xuất sang Mailchimp.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 7922a6a69f863caae5401549ed6f88a61aa77d39
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124253"
---
# <a name="export-segments-to-mailchimp-preview"></a><span data-ttu-id="ec3b5-103">Xuất phân khúc sang Mailchimp (xem trước)</span><span class="sxs-lookup"><span data-stu-id="ec3b5-103">Export segments to Mailchimp (preview)</span></span>

<span data-ttu-id="ec3b5-104">Xuất phân khúc hồ sơ khách hàng hợp nhất sang Mailchimp để tạo bản tin và chiến dịch email.</span><span class="sxs-lookup"><span data-stu-id="ec3b5-104">Export segments of unified customer profiles to Mailchimp to create newsletters and email campaigns.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="ec3b5-105">Điều kiện tiên quyết để kết nối</span><span class="sxs-lookup"><span data-stu-id="ec3b5-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="ec3b5-106">Bạn có một [Tài khoản Mailchimp](https://mailchimp.com/) và thông tin đăng nhập quản trị viên tương ứng.</span><span class="sxs-lookup"><span data-stu-id="ec3b5-106">You have a [Mailchimp account](https://mailchimp.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="ec3b5-107">Có đối tượng hiện có trong Mailchimp và các ID tương ứng.</span><span class="sxs-lookup"><span data-stu-id="ec3b5-107">There are existing audiences in Mailchimp and the corresponding IDs.</span></span> <span data-ttu-id="ec3b5-108">Để biết thêm thông tin, hãy xem [Đối tượng Mailchimp](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="ec3b5-108">For more information, see [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>
-   <span data-ttu-id="ec3b5-109">Bạn có [các phân khúc được định cấu hình](segments.md)</span><span class="sxs-lookup"><span data-stu-id="ec3b5-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="ec3b5-110">Hồ sơ khách hàng hợp nhất trong các phân khúc đã xuất chứa các trường đại diện cho địa chỉ email.</span><span class="sxs-lookup"><span data-stu-id="ec3b5-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="ec3b5-111">Các giới hạn đã biết</span><span class="sxs-lookup"><span data-stu-id="ec3b5-111">Known limitations</span></span>

- <span data-ttu-id="ec3b5-112">Lên đến 1 triệu hồ sơ mỗi lần xuất sang Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="ec3b5-112">Up to 1 million profiles per export to Mailchimp.</span></span>
- <span data-ttu-id="ec3b5-113">Bạn chỉ xuất được phân khúc sang Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="ec3b5-113">Exporting to Mailchimp is limited to segments.</span></span>
- <span data-ttu-id="ec3b5-114">Quá trình xuất phân khúc với 1 triệu hồ sơ có thể mất đến ba giờ.</span><span class="sxs-lookup"><span data-stu-id="ec3b5-114">Exporting segments with 1 million profiles can take up to three hours.</span></span> 
- <span data-ttu-id="ec3b5-115">Số lượng hồ sơ mà bạn có thể xuất sang Mailchimp phụ thuộc và giới hạn vào hợp đồng của bạn với Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="ec3b5-115">The number of profiles that you can export to Mailchimp is dependent and limited on your contract with Mailchimp.</span></span>

## <a name="set-up-connection-to-mailchimp"></a><span data-ttu-id="ec3b5-116">Thiết lập kết nối với Mailchimp</span><span class="sxs-lookup"><span data-stu-id="ec3b5-116">Set up connection to Mailchimp</span></span>

1. <span data-ttu-id="ec3b5-117">Đi đến **Quản trị viên** > **Kết nối**.</span><span class="sxs-lookup"><span data-stu-id="ec3b5-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="ec3b5-118">Chọn **Thêm kết nối** rồi chọn **Autopilot** để đặt cấu hình kết nối.</span><span class="sxs-lookup"><span data-stu-id="ec3b5-118">Select **Add connection** and choose **Autopilot** to configure the connection.</span></span>

1. <span data-ttu-id="ec3b5-119">Đặt tên dễ nhận biết cho kết nối trong trường **Tên hiển thị**.</span><span class="sxs-lookup"><span data-stu-id="ec3b5-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="ec3b5-120">Tên và loại kết nối mô tả kết nối này.</span><span class="sxs-lookup"><span data-stu-id="ec3b5-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="ec3b5-121">Bạn nên chọn một tên giải thích mục đích và mục tiêu của kết nối.</span><span class="sxs-lookup"><span data-stu-id="ec3b5-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="ec3b5-122">Chọn người có thể sử dụng kết nối này.</span><span class="sxs-lookup"><span data-stu-id="ec3b5-122">Choose who can use this connection.</span></span> <span data-ttu-id="ec3b5-123">Nếu bạn không thực hiện hành động nào, giá trị mặc định sẽ là Quản trị viên.</span><span class="sxs-lookup"><span data-stu-id="ec3b5-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="ec3b5-124">Để biết thêm thông tin, hãy xem [Cho phép người đóng góp sử dụng một kết nối cho các lần xuất](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="ec3b5-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="ec3b5-125">Chọn **Tôi đồng ý** để xác nhận **Quyền riêng tư về dữ liệu và sự tuân thủ**.</span><span class="sxs-lookup"><span data-stu-id="ec3b5-125">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="ec3b5-126">Chọn **Kết nối** để khởi tạo kết nối với Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="ec3b5-126">Select **Connect** to initialize the connection to Mailchimp.</span></span>

1. <span data-ttu-id="ec3b5-127">Chọn **Xác thực bằng Mailchimp** và cung cấp thông tin đăng nhập Mailchimp của bạn.</span><span class="sxs-lookup"><span data-stu-id="ec3b5-127">Select **Authenticate with Mailchimp** and provide your Mailchimp credentials.</span></span>

1. <span data-ttu-id="ec3b5-128">Chọn **Thêm chính bạn là người dùng xuất** và cung cấp thông tin xác thực Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="ec3b5-128">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="ec3b5-129">Chọn **Lưu** để hoàn thành kết nối.</span><span class="sxs-lookup"><span data-stu-id="ec3b5-129">Select **Save** to complete the connection.</span></span> 

## <a name="configure-the-connector"></a><span data-ttu-id="ec3b5-130">Đặt cấu hình trình kết nối</span><span class="sxs-lookup"><span data-stu-id="ec3b5-130">Configure the connector</span></span>

<span data-ttu-id="ec3b5-131">Bạn có thể đặt cấu hình lần xuất này nếu bạn có quyền truy cập vào kết nối thuộc loại này.</span><span class="sxs-lookup"><span data-stu-id="ec3b5-131">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="ec3b5-132">Để biết thêm thông tin, hãy xem [Các quyền cần thiết để đặt cấu hình xuất](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="ec3b5-132">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="ec3b5-133">Đi tới **Dữ liệu**> **Nội dung xuất**.</span><span class="sxs-lookup"><span data-stu-id="ec3b5-133">Go to **Data**> **Exports**.</span></span>

1. <span data-ttu-id="ec3b5-134">Để tạo một nội dung xuất mới, hãy chọn **Thêm đích**.</span><span class="sxs-lookup"><span data-stu-id="ec3b5-134">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="ec3b5-135">Trong trường **Kết nối để xuất**, hãy chọn một kết nối từ phần Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="ec3b5-135">In the **Connection for export** field, choose a connection from the Mailchimp section.</span></span> <span data-ttu-id="ec3b5-136">Nếu bạn không thấy tên phần này, tức là không có kết nối nào thuộc loại này dành cho bạn.</span><span class="sxs-lookup"><span data-stu-id="ec3b5-136">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="ec3b5-137">Nhập **[ID đối tượng Mailchimp](https://mailchimp.com/help/find-audience-id/)** của bạn</span><span class="sxs-lookup"><span data-stu-id="ec3b5-137">Enter your **[Mailchimp audience ID](https://mailchimp.com/help/find-audience-id/)**</span></span>

3. <span data-ttu-id="ec3b5-138">Trong phần **So khớp dữ liệu**, trong trường **Email**, chọn trường trong hồ sơ khách hàng hợp nhất trình bày địa chỉ email của khách hàng.</span><span class="sxs-lookup"><span data-stu-id="ec3b5-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="ec3b5-139">Bạn có thể tùy ý xuất **Tên** và **Họ** để tạo nhiều email được cá nhân hóa hơn.</span><span class="sxs-lookup"><span data-stu-id="ec3b5-139">Optionally, you can export **First name** and **Last name** to create more personalized emails.</span></span> <span data-ttu-id="ec3b5-140">Chọn **Thêm thuộc tính** để ánh xạ những trường này.</span><span class="sxs-lookup"><span data-stu-id="ec3b5-140">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="ec3b5-141">Chọn phân khúc mà bạn muốn xuất.</span><span class="sxs-lookup"><span data-stu-id="ec3b5-141">Select the segments you want to export.</span></span> <span data-ttu-id="ec3b5-142">Bạn có thể xuất tổng cộng tối đa 1 triệu hồ sơ khách hàng sang Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="ec3b5-142">You can export up to 1 million customer profiles in total to Mailchimp.</span></span>

1. <span data-ttu-id="ec3b5-143">Chọn **Lưu**.</span><span class="sxs-lookup"><span data-stu-id="ec3b5-143">Select **Save**.</span></span>

<span data-ttu-id="ec3b5-144">Việc lưu một nội dung xuất sẽ không chạy nội dung xuất đó ngay lập tức.</span><span class="sxs-lookup"><span data-stu-id="ec3b5-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="ec3b5-145">Nội dung xuất chạy trong mỗi lần [làm mới theo lịch trình](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="ec3b5-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="ec3b5-146">Bạn cũng có thể [xuất dữ liệu theo yêu cầu](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="ec3b5-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="ec3b5-147">Quyền riêng tư về dữ liệu và sự tuân thủ</span><span class="sxs-lookup"><span data-stu-id="ec3b5-147">Data privacy and compliance</span></span>

<span data-ttu-id="ec3b5-148">Khi bật Dynamics 365 Customer Insights để truyền dữ liệu tới Mailchimp, bạn cho phép chuyển dữ liệu ra bên ngoài ranh giới tuân thủ cho Dynamics 365 Customer Insights, bao gồm dữ liệu nhạy cảm tiềm ẩn như Dữ liệu cá nhân.</span><span class="sxs-lookup"><span data-stu-id="ec3b5-148">When you enable Dynamics 365 Customer Insights to transmit data to Mailchimp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="ec3b5-149">Microsoft sẽ chuyển những dữ liệu đó theo chỉ dẫn của bạn, nhưng bạn có trách nhiệm đảm bảo rằng Mailchimp đáp ứng mọi nghĩa vụ về quyền riêng tư hoặc bảo mật mà bạn có thể có.</span><span class="sxs-lookup"><span data-stu-id="ec3b5-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Mailchimp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="ec3b5-150">Để biết thêm thông tin, hãy xem [Tuyên bố về Quyền riêng tư của Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="ec3b5-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="ec3b5-151">Quản trị viên Dynamics 365 Customer Insights của bạn có thể xóa đích xuất này bất cứ lúc nào để ngừng việc sử dụng chức năng này.</span><span class="sxs-lookup"><span data-stu-id="ec3b5-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
