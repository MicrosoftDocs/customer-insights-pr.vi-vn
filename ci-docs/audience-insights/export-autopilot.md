---
title: Xuất dữ liệu Customer Insights sang Autopilot
description: Tìm hiểu cách đặt cấu hình kết nối và xuất sang Autopilot.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e320a48d5b7c35b530e3a38567b226b804879e4e
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760169"
---
# <a name="export-segments-to-autopilot-preview"></a><span data-ttu-id="3305b-103">Xuất phân khúc sang Autopilot (bản xem trước)</span><span class="sxs-lookup"><span data-stu-id="3305b-103">Export segments to Autopilot (preview)</span></span>

<span data-ttu-id="3305b-104">Xuất phân đoạn hồ sơ khách hàng hợp nhất sang Autopilot và sử dụng chúng cho các chiến dịch và tiếp thị qua email trong Autopilot.</span><span class="sxs-lookup"><span data-stu-id="3305b-104">Export segments of unified customer profiles to Autopilot and use them for email marketing in Autopilot.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="3305b-105">Điều kiện tiên quyết để kết nối</span><span class="sxs-lookup"><span data-stu-id="3305b-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="3305b-106">Bạn có một [Tài khoản Autopilot](https://www.autopilothq.com/) và thông tin đăng nhập quản trị viên tương ứng.</span><span class="sxs-lookup"><span data-stu-id="3305b-106">You have an [Autopilot account](https://www.autopilothq.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="3305b-107">Bạn có [các phân đoạn được định cấu hình](segments.md) trong thông tin chi tiết về đối tượng.</span><span class="sxs-lookup"><span data-stu-id="3305b-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="3305b-108">Hồ sơ khách hàng hợp nhất trong các phân đoạn đã xuất chứa các trường đại diện cho địa chỉ email.</span><span class="sxs-lookup"><span data-stu-id="3305b-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="3305b-109">Các giới hạn đã biết</span><span class="sxs-lookup"><span data-stu-id="3305b-109">Known limitations</span></span>

- <span data-ttu-id="3305b-110">Bạn có thể xuất tổng cộng tối đa 100.000 hồ sơ khách hàng sang Autopilot.</span><span class="sxs-lookup"><span data-stu-id="3305b-110">You can export up to 100'000 profiles in total to Autopilot.</span></span>
- <span data-ttu-id="3305b-111">Việc xuất sang Autopilot bị giới hạn ở các phân đoạn.</span><span class="sxs-lookup"><span data-stu-id="3305b-111">Exporting to Autopilot is limited to segments.</span></span>
- <span data-ttu-id="3305b-112">Có thể mất tới vài giờ để hoàn thành việc xuất lên đến 100.000 hồ sơ sang Autopilot.</span><span class="sxs-lookup"><span data-stu-id="3305b-112">Exporting up to 100'000 profiles to Autopilot can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="3305b-113">Số lượng hồ sơ mà bạn có thể xuất sang Autopilot phụ thuộc vào giới hạn đối với hợp đồng của bạn với Autopilot.</span><span class="sxs-lookup"><span data-stu-id="3305b-113">The number of profiles that you can export to Autopilot is dependent and limited on your contract with Autopilot.</span></span>

## <a name="set-up-connection-to-autopilot"></a><span data-ttu-id="3305b-114">Thiết lập kết nối với Autopilot</span><span class="sxs-lookup"><span data-stu-id="3305b-114">Set up connection to Autopilot</span></span>

1. <span data-ttu-id="3305b-115">Đi đến **Quản trị viên** > **Kết nối**.</span><span class="sxs-lookup"><span data-stu-id="3305b-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="3305b-116">Chọn **Thêm kết nối** rồi chọn **Autopilot** để đặt cấu hình kết nối.</span><span class="sxs-lookup"><span data-stu-id="3305b-116">Select **Add connection** and choose **Autopilot** to configure the connection.</span></span>

1. <span data-ttu-id="3305b-117">Đặt tên dễ nhận biết cho kết nối trong trường **Tên hiển thị**.</span><span class="sxs-lookup"><span data-stu-id="3305b-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="3305b-118">Tên và loại kết nối mô tả kết nối này.</span><span class="sxs-lookup"><span data-stu-id="3305b-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="3305b-119">Bạn nên chọn một tên giải thích mục đích và mục tiêu của kết nối.</span><span class="sxs-lookup"><span data-stu-id="3305b-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="3305b-120">Chọn người có thể sử dụng kết nối này.</span><span class="sxs-lookup"><span data-stu-id="3305b-120">Choose who can use this connection.</span></span> <span data-ttu-id="3305b-121">Nếu bạn không thực hiện hành động nào, giá trị mặc định sẽ là Quản trị viên.</span><span class="sxs-lookup"><span data-stu-id="3305b-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="3305b-122">Để biết thêm thông tin, hãy xem [Cho phép người đóng góp sử dụng một kết nối cho các lần xuất](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="3305b-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

3. <span data-ttu-id="3305b-123">Nhập [khóa API Autopilot](https://autopilot.docs.apiary.io/#).</span><span class="sxs-lookup"><span data-stu-id="3305b-123">Enter your [Autopilot API key](https://autopilot.docs.apiary.io/#).</span></span>

1. <span data-ttu-id="3305b-124">Chọn **Tôi đồng ý** để xác nhận **Quyền riêng tư về dữ liệu và sự tuân thủ**.</span><span class="sxs-lookup"><span data-stu-id="3305b-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="3305b-125">Chọn **Kết nối** để khởi tạo kết nối với Autopilot.</span><span class="sxs-lookup"><span data-stu-id="3305b-125">Select **Connect** to initialize the connection to Autopilot.</span></span>

1. <span data-ttu-id="3305b-126">Chọn **Thêm chính bạn là người dùng xuất** và cung cấp thông tin xác thực Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="3305b-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="3305b-127">Chọn **Lưu** để hoàn thành kết nối.</span><span class="sxs-lookup"><span data-stu-id="3305b-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="3305b-128">Đặt cấu hình xuất</span><span class="sxs-lookup"><span data-stu-id="3305b-128">Configure an export</span></span>

<span data-ttu-id="3305b-129">Bạn có thể đặt cấu hình lần xuất này nếu bạn có quyền truy cập vào kết nối thuộc loại này.</span><span class="sxs-lookup"><span data-stu-id="3305b-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="3305b-130">Để biết thêm thông tin, hãy xem [Các quyền cần thiết để đặt cấu hình xuất](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="3305b-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="3305b-131">Đi tới **Dữ liệu** > **Nội dung xuất**.</span><span class="sxs-lookup"><span data-stu-id="3305b-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="3305b-132">Để tạo một nội dung xuất mới, hãy chọn **Thêm đích**.</span><span class="sxs-lookup"><span data-stu-id="3305b-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="3305b-133">Trong trường **Kết nối để xuất**, hãy chọn một kết nối từ phần Autopilot.</span><span class="sxs-lookup"><span data-stu-id="3305b-133">In the **Connection for export** field, choose a connection from the Autopilot section.</span></span> <span data-ttu-id="3305b-134">Nếu bạn không thấy tên phần này, tức là không có kết nối nào thuộc loại này dành cho bạn.</span><span class="sxs-lookup"><span data-stu-id="3305b-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

3. <span data-ttu-id="3305b-135">Trong phần **So khớp dữ liệu**, trong trường **Email**, chọn trường trong hồ sơ khách hàng hợp nhất trình bày địa chỉ email của khách hàng.</span><span class="sxs-lookup"><span data-stu-id="3305b-135">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="3305b-136">Lặp lại các bước tương tự cho các trường tùy chọn khác như **Tên**, **Họ**.</span><span class="sxs-lookup"><span data-stu-id="3305b-136">Repeat the same steps for other optional fields such as **First name**, **Last name**.</span></span>

1. <span data-ttu-id="3305b-137">Chọn phân khúc mà bạn muốn xuất.</span><span class="sxs-lookup"><span data-stu-id="3305b-137">Select the segments you want to export.</span></span> <span data-ttu-id="3305b-138">Chúng tôi **khuyên bạn không nên xuất tổng cộng hơn 100.000 hồ sơ khách hàng** tới Autopilot.</span><span class="sxs-lookup"><span data-stu-id="3305b-138">We strongly **recommend to not export more than 100'000 customer profiles in total** to Autopilot.</span></span> 

1. <span data-ttu-id="3305b-139">Chọn **Lưu**.</span><span class="sxs-lookup"><span data-stu-id="3305b-139">Select **Save**.</span></span>

<span data-ttu-id="3305b-140">Việc lưu một nội dung xuất sẽ không chạy nội dung xuất đó ngay lập tức.</span><span class="sxs-lookup"><span data-stu-id="3305b-140">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="3305b-141">Nội dung xuất chạy trong mỗi lần [làm mới theo lịch trình](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="3305b-141">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="3305b-142">Bạn cũng có thể [xuất dữ liệu theo yêu cầu](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="3305b-142">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="3305b-143">Quyền riêng tư về dữ liệu và sự tuân thủ</span><span class="sxs-lookup"><span data-stu-id="3305b-143">Data privacy and compliance</span></span>

<span data-ttu-id="3305b-144">Khi bật Dynamics 365 Customer Insights để truyền dữ liệu tới Autopilot, bạn cho phép chuyển dữ liệu ra bên ngoài ranh giới tuân thủ cho Dynamics 365 Customer Insights, bao gồm dữ liệu nhạy cảm tiềm ẩn như Dữ liệu cá nhân.</span><span class="sxs-lookup"><span data-stu-id="3305b-144">When you enable Dynamics 365 Customer Insights to transmit data to Autopilot, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="3305b-145">Microsoft sẽ chuyển những dữ liệu đó theo chỉ dẫn của bạn, nhưng bạn có trách nhiệm đảm bảo rằng Autopilot đáp ứng mọi nghĩa vụ về quyền riêng tư hoặc bảo mật mà bạn có thể có.</span><span class="sxs-lookup"><span data-stu-id="3305b-145">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Autopilot meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="3305b-146">Để biết thêm thông tin, hãy xem [Tuyên bố về Quyền riêng tư của Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="3305b-146">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="3305b-147">Quản trị viên Dynamics 365 Customer Insights của bạn có thể xóa đích xuất này bất cứ lúc nào để ngừng sử dụng chức năng này.</span><span class="sxs-lookup"><span data-stu-id="3305b-147">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
