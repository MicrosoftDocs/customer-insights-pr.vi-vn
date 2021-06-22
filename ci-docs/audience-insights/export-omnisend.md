---
title: Xuất dữ liệu Customer Insights sang Omnisend
description: Tìm hiểu cách đặt cấu hình kết nối và xuất sang Omnisend.
ms.date: 05/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8bd692819fa8451ded5e74191ee717f81f87425d
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124571"
---
# <a name="export-segments-to-omnisend-preview"></a><span data-ttu-id="d6778-103">Xuất phân khúc sang Omnisend (xem trước)</span><span class="sxs-lookup"><span data-stu-id="d6778-103">Export segments to Omnisend (preview)</span></span>

<span data-ttu-id="d6778-104">Xuất các phân khúc hồ sơ khách hàng hợp nhất sang Omnisend để dùng cho các hoạt động tiếp thị.</span><span class="sxs-lookup"><span data-stu-id="d6778-104">Export segments of unified customer profiles to Omnisend and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d6778-105">Điều kiện tiên quyết</span><span class="sxs-lookup"><span data-stu-id="d6778-105">Prerequisites</span></span>

-   <span data-ttu-id="d6778-106">Bạn có một [tài khoản Omnisend](https://www.omnisend.com/) và thông tin xác thực tương ứng của quản trị viên.</span><span class="sxs-lookup"><span data-stu-id="d6778-106">You have an [Omnisend account](https://www.omnisend.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="d6778-107">Bạn có [các phân khúc đã đặt cấu hình](segments.md) trong thông tin chuyên sâu về đối tượng.</span><span class="sxs-lookup"><span data-stu-id="d6778-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="d6778-108">Hồ sơ khách hàng hợp nhất trong các phân khúc đã xuất chứa các trường đại diện cho địa chỉ email.</span><span class="sxs-lookup"><span data-stu-id="d6778-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="d6778-109">Các giới hạn đã biết</span><span class="sxs-lookup"><span data-stu-id="d6778-109">Known limitations</span></span>

- <span data-ttu-id="d6778-110">Bạn có thể xuất tối đa 1 triệu hồ sơ trong mỗi lần xuất sang Omnisend và có thể mất tới 4 giờ để hoàn tất.</span><span class="sxs-lookup"><span data-stu-id="d6778-110">You can export up to 1 million profiles per export to Omnisend and it can take up to 4 hours to complete.</span></span>
- <span data-ttu-id="d6778-111">Bạn chỉ xuất được phân khúc sang Omnisend.</span><span class="sxs-lookup"><span data-stu-id="d6778-111">Exporting to Omnisend is limited to segments.</span></span>
- <span data-ttu-id="d6778-112">Số lượng hồ sơ mà bạn có thể xuất sang Omnisend tùy thuộc vào hợp đồng của bạn với Omnisend.</span><span class="sxs-lookup"><span data-stu-id="d6778-112">The number of profiles that you can export to Omnisend depends on your contract with Omnisend.</span></span>

## <a name="set-up-connection-to-omnisend"></a><span data-ttu-id="d6778-113">Thiết lập kết nối với Omnisend</span><span class="sxs-lookup"><span data-stu-id="d6778-113">Set up connection to Omnisend</span></span>

1. <span data-ttu-id="d6778-114">Đi đến **Quản trị viên** > **Kết nối**.</span><span class="sxs-lookup"><span data-stu-id="d6778-114">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="d6778-115">Chọn **Thêm kết nối** rồi chọn **Omnisend** để đặt cấu hình kết nối.</span><span class="sxs-lookup"><span data-stu-id="d6778-115">Select **Add connection** and choose **Omnisend** to configure the connection.</span></span>

1. <span data-ttu-id="d6778-116">Đặt tên dễ nhận biết cho kết nối trong trường **Tên hiển thị**.</span><span class="sxs-lookup"><span data-stu-id="d6778-116">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="d6778-117">Tên và loại kết nối mô tả kết nối này.</span><span class="sxs-lookup"><span data-stu-id="d6778-117">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="d6778-118">Bạn nên chọn một tên giải thích mục đích và mục tiêu của kết nối.</span><span class="sxs-lookup"><span data-stu-id="d6778-118">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="d6778-119">Chọn người có thể sử dụng kết nối này.</span><span class="sxs-lookup"><span data-stu-id="d6778-119">Choose who can use this connection.</span></span> <span data-ttu-id="d6778-120">Theo mặc định, giá trị này là quản trị viên.</span><span class="sxs-lookup"><span data-stu-id="d6778-120">By default it's only administrators.</span></span> <span data-ttu-id="d6778-121">Để biết thêm thông tin, hãy xem [Cho phép người đóng góp sử dụng một kết nối cho các lần xuất](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="d6778-121">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="d6778-122">Nhập [khóa API Omnisend](https://support.omnisend.com/en/articles/1061890-generating-api-key) của bạn.</span><span class="sxs-lookup"><span data-stu-id="d6778-122">Enter your [Omnisend API key](https://support.omnisend.com/en/articles/1061890-generating-api-key).</span></span>

1. <span data-ttu-id="d6778-123">Chọn **Tôi đồng ý** để xác nhận **Quyền riêng tư về dữ liệu và sự tuân thủ**.</span><span class="sxs-lookup"><span data-stu-id="d6778-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="d6778-124">Chọn **Kết nối** để khởi tạo kết nối với Omnisend.</span><span class="sxs-lookup"><span data-stu-id="d6778-124">Select **Connect** to initialize the connection to Omnisend.</span></span>

1. <span data-ttu-id="d6778-125">Chọn **Thêm chính bạn là người dùng xuất** và cung cấp thông tin xác thực Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="d6778-125">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="d6778-126">Chọn **Lưu** để hoàn thành kết nối.</span><span class="sxs-lookup"><span data-stu-id="d6778-126">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="d6778-127">Đặt cấu hình xuất</span><span class="sxs-lookup"><span data-stu-id="d6778-127">Configure an export</span></span>

<span data-ttu-id="d6778-128">Bạn có thể đặt cấu hình lần xuất này nếu bạn có quyền truy cập vào kết nối thuộc loại này.</span><span class="sxs-lookup"><span data-stu-id="d6778-128">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="d6778-129">Để biết thêm thông tin, hãy xem [Các quyền cần thiết để đặt cấu hình xuất](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="d6778-129">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="d6778-130">Đi tới **Dữ liệu** > **Nội dung xuất**.</span><span class="sxs-lookup"><span data-stu-id="d6778-130">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="d6778-131">Để tạo một nội dung xuất mới, hãy chọn **Thêm đích**.</span><span class="sxs-lookup"><span data-stu-id="d6778-131">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="d6778-132">Trong trường **Kết nối để xuất**, hãy chọn một kết nối từ phần Omnisend.</span><span class="sxs-lookup"><span data-stu-id="d6778-132">In the **Connection for export** field, choose a connection from the Omnisend section.</span></span> <span data-ttu-id="d6778-133">Nếu bạn không thấy tên phần này, tức là không có kết nối nào thuộc loại này dành cho bạn.</span><span class="sxs-lookup"><span data-stu-id="d6778-133">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="d6778-134">Trong phần **So khớp dữ liệu**, trong trường **Email**, chọn trường trong hồ sơ khách hàng hợp nhất trình bày địa chỉ email của khách hàng.</span><span class="sxs-lookup"><span data-stu-id="d6778-134">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="d6778-135">Bạn phải xuất các phân khúc sang Omnisend.</span><span class="sxs-lookup"><span data-stu-id="d6778-135">It's required to export segments to Omnisend.</span></span> <span data-ttu-id="d6778-136">Bạn có thể tùy ý xuất Tên, Họ, Địa chỉ, Quốc gia/Khu vực, Tiểu bang, Thành phố và Mã bưu chính để tạo thêm nhiều email được cá nhân hóa.</span><span class="sxs-lookup"><span data-stu-id="d6778-136">Optionally, you can export First name, Last name, Address, Country/Region, State, City, and Post Code to create more personalized emails.</span></span> <span data-ttu-id="d6778-137">Chọn **Thêm thuộc tính** để ánh xạ những trường này.</span><span class="sxs-lookup"><span data-stu-id="d6778-137">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="d6778-138">Chọn **Lưu**.</span><span class="sxs-lookup"><span data-stu-id="d6778-138">Select **Save**.</span></span>

<span data-ttu-id="d6778-139">Việc lưu một nội dung xuất sẽ không chạy nội dung xuất đó ngay lập tức.</span><span class="sxs-lookup"><span data-stu-id="d6778-139">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="d6778-140">Nội dung xuất chạy trong mỗi lần [làm mới theo lịch trình](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="d6778-140">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="d6778-141">Bạn cũng có thể [xuất dữ liệu theo yêu cầu](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="d6778-141">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="d6778-142">Quyền riêng tư về dữ liệu và sự tuân thủ</span><span class="sxs-lookup"><span data-stu-id="d6778-142">Data privacy and compliance</span></span>

<span data-ttu-id="d6778-143">Khi bật Dynamics 365 Customer Insights để truyền dữ liệu đến Omnisend, bạn cho phép chuyển dữ liệu ra bên ngoài ranh giới tuân thủ của Dynamics 365 Customer Insights, bao gồm cả dữ liệu có thể nhạy cảm như Dữ liệu cá nhân.</span><span class="sxs-lookup"><span data-stu-id="d6778-143">When you enable Dynamics 365 Customer Insights to transmit data to Ommisend, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="d6778-144">Microsoft sẽ chuyển những dữ liệu đó theo chỉ dẫn của bạn, nhưng bạn có trách nhiệm đảm bảo rằng Omnisend đáp ứng mọi nghĩa vụ về quyền riêng tư hoặc bảo mật mà bạn có thể có.</span><span class="sxs-lookup"><span data-stu-id="d6778-144">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Omnisend meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="d6778-145">Để biết thêm thông tin, hãy xem [Tuyên bố về Quyền riêng tư của Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="d6778-145">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="d6778-146">Quản trị viên Dynamics 365 Customer Insights của bạn có thể xóa đích xuất này bất cứ lúc nào để ngừng việc sử dụng chức năng này.</span><span class="sxs-lookup"><span data-stu-id="d6778-146">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
