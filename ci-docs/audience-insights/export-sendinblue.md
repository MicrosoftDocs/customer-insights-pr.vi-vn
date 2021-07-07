---
title: Xuất dữ liệu Customer Insights sang Sendinblue
description: Tìm hiểu cách định cấu hình kết nối và xuất sang Sendinblue.
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 58ca0ae5ad4a3a291f4336984d14fefb23a58ab3
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314694"
---
# <a name="export-segments-to-sendinblue-preview"></a><span data-ttu-id="e0567-103">Xuất phân khúc sang Sendinblue (bản xem trước)</span><span class="sxs-lookup"><span data-stu-id="e0567-103">Export segments to Sendinblue (preview)</span></span>

<span data-ttu-id="e0567-104">Xuất các phân khúc hồ sơ khách hàng hợp nhất để tạo chiến dịch, cung cấp email tiếp thị và sử dụng các nhóm khách hàng cụ thể với Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="e0567-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Sendinblue.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="e0567-105">Điều kiện tiên quyết để kết nối</span><span class="sxs-lookup"><span data-stu-id="e0567-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="e0567-106">Bạn có một [Tài khoản Sendinblue](https://www.sendinblue.com/) và thông tin xác thực tương ứng của quản trị viên.</span><span class="sxs-lookup"><span data-stu-id="e0567-106">You have a [Sendinblue account](https://www.sendinblue.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="e0567-107">Bạn có thể xem các danh sách hiện có trong Sendinblue và ID tương ứng.</span><span class="sxs-lookup"><span data-stu-id="e0567-107">There are existing lists in Sendinblue and the corresponding IDs.</span></span>
-   <span data-ttu-id="e0567-108">Bạn có [các phân khúc được định cấu hình](segments.md).</span><span class="sxs-lookup"><span data-stu-id="e0567-108">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="e0567-109">Hồ sơ khách hàng hợp nhất trong các phân khúc đã xuất chứa các trường đại diện cho địa chỉ email.</span><span class="sxs-lookup"><span data-stu-id="e0567-109">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="e0567-110">Các hạn chế đã biết</span><span class="sxs-lookup"><span data-stu-id="e0567-110">Known limitations</span></span>

- <span data-ttu-id="e0567-111">Lên đến 1 triệu hồ sơ khách hàng/lần xuất sang Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="e0567-111">Up to 1 million profiles per export to Sendinblue.</span></span>
- <span data-ttu-id="e0567-112">Việc xuất sang Sendinblue bị giới hạn theo phân khúc.</span><span class="sxs-lookup"><span data-stu-id="e0567-112">Exporting to Sendinblue is limited to segments.</span></span>
- <span data-ttu-id="e0567-113">Quy trình xuất các phân khúc với tổng số 1 triệu hồ sơ có thể mất đến 90 phút.</span><span class="sxs-lookup"><span data-stu-id="e0567-113">Exporting segments with a total of 1 million profiles can take up to 90 minutes.</span></span> 
- <span data-ttu-id="e0567-114">Số lượng hồ sơ mà bạn có thể xuất sang Sendinblue tùy thuộc vào và bị giới hạn bởi hợp đồng của bạn với Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="e0567-114">The number of profiles that you can export to Sendinblue is dependent and limited on your contract with Sendinblue.</span></span>

## <a name="set-up-connection-to-sendinblue"></a><span data-ttu-id="e0567-115">Thiết lập kết nối đến Sendinblue</span><span class="sxs-lookup"><span data-stu-id="e0567-115">Set up connection to Sendinblue</span></span>

1. <span data-ttu-id="e0567-116">Đi đến **Quản trị viên** > **Kết nối**.</span><span class="sxs-lookup"><span data-stu-id="e0567-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="e0567-117">Chọn **Thêm kết nối** rồi chọn **Sendinblue** để định cấu hình kết nối.</span><span class="sxs-lookup"><span data-stu-id="e0567-117">Select **Add connection** and choose **Sendinblue** to configure the connection.</span></span>

1. <span data-ttu-id="e0567-118">Đặt tên dễ nhận biết cho kết nối trong trường **Tên hiển thị**.</span><span class="sxs-lookup"><span data-stu-id="e0567-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="e0567-119">Tên và loại kết nối mô tả kết nối này.</span><span class="sxs-lookup"><span data-stu-id="e0567-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="e0567-120">Bạn nên chọn một tên giải thích mục đích và mục tiêu của kết nối.</span><span class="sxs-lookup"><span data-stu-id="e0567-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="e0567-121">Chọn người có thể sử dụng kết nối này.</span><span class="sxs-lookup"><span data-stu-id="e0567-121">Choose who can use this connection.</span></span> <span data-ttu-id="e0567-122">Theo mặc định, giá trị này là quản trị viên.</span><span class="sxs-lookup"><span data-stu-id="e0567-122">By default it's only administrators.</span></span> <span data-ttu-id="e0567-123">Để biết thêm thông tin, hãy xem [Cho phép người đóng góp sử dụng một kết nối cho các lần xuất](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="e0567-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="e0567-124">Nhập **[Khóa API SendinBlue](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.</span><span class="sxs-lookup"><span data-stu-id="e0567-124">Enter your **[SendinBlue API key](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.</span></span>

1. <span data-ttu-id="e0567-125">Chọn **Tôi đồng ý** để xác nhận **Quyền riêng tư về dữ liệu và sự tuân thủ** rồi chọn **Kết nối** để khởi tạo kết nối tới Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="e0567-125">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Sendinblue.</span></span>

1. <span data-ttu-id="e0567-126">Chọn **Thêm chính bạn là người dùng xuất** và cung cấp thông tin xác thực Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="e0567-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="e0567-127">Chọn **Lưu** để hoàn thành kết nối.</span><span class="sxs-lookup"><span data-stu-id="e0567-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="e0567-128">Định cấu hình xuất</span><span class="sxs-lookup"><span data-stu-id="e0567-128">Configure an export</span></span>

<span data-ttu-id="e0567-129">Bạn có thể định cấu hình lần xuất này nếu bạn có quyền truy cập vào kết nối thuộc loại này.</span><span class="sxs-lookup"><span data-stu-id="e0567-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="e0567-130">Để biết thêm thông tin, hãy xem [Các quyền cần thiết để định cấu hình xuất](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="e0567-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="e0567-131">Đi tới **Dữ liệu** > **Nội dung xuất**.</span><span class="sxs-lookup"><span data-stu-id="e0567-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e0567-132">Để tạo một nội dung xuất mới, hãy chọn **Thêm đích**.</span><span class="sxs-lookup"><span data-stu-id="e0567-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="e0567-133">Trong trường **Kết nối để xuất**, hãy chọn một kết nối từ phần Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="e0567-133">In the **Connection for export** field, choose a connection from the Sendinblue section.</span></span> <span data-ttu-id="e0567-134">Nếu bạn không thấy tên phần này, tức là không có kết nối nào thuộc loại này dành cho bạn.</span><span class="sxs-lookup"><span data-stu-id="e0567-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="e0567-135">Nhập **ID danh sách Sendinblue**</span><span class="sxs-lookup"><span data-stu-id="e0567-135">Enter your **Sendinblue list ID**</span></span> 

1. <span data-ttu-id="e0567-136">Trong phần **So khớp dữ liệu**, trong trường **Email**, chọn trường trong hồ sơ khách hàng hợp nhất trình bày địa chỉ email của khách hàng.</span><span class="sxs-lookup"><span data-stu-id="e0567-136">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="e0567-137">Bạn có thể xuất **Tên**, **Họ** và **Số điện thoại** để tạo nhiều email được cá nhân hóa hơn.</span><span class="sxs-lookup"><span data-stu-id="e0567-137">Optionally, you can export **First name**, **Last name**, and **Phone**  to create more personalized emails.</span></span> <span data-ttu-id="e0567-138">Chọn **Thêm thuộc tính** để ánh xạ những trường này.</span><span class="sxs-lookup"><span data-stu-id="e0567-138">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="e0567-139">Chọn phân khúc mà bạn muốn xuất.</span><span class="sxs-lookup"><span data-stu-id="e0567-139">Select the segments you want to export.</span></span> 

1. <span data-ttu-id="e0567-140">Chọn **Lưu**.</span><span class="sxs-lookup"><span data-stu-id="e0567-140">Select **Save**.</span></span>

<span data-ttu-id="e0567-141">Việc lưu một nội dung xuất sẽ không chạy nội dung xuất đó ngay lập tức.</span><span class="sxs-lookup"><span data-stu-id="e0567-141">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="e0567-142">Nội dung xuất chạy trong mỗi lần [làm mới theo lịch trình](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="e0567-142">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="e0567-143">Bạn cũng có thể [xuất dữ liệu theo yêu cầu](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="e0567-143">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="e0567-144">Quyền riêng tư về dữ liệu và sự tuân thủ</span><span class="sxs-lookup"><span data-stu-id="e0567-144">Data privacy and compliance</span></span>

<span data-ttu-id="e0567-145">Khi bật Dynamics 365 Customer Insights để truyền dữ liệu tới Sendinblue, bạn cho phép truyền dữ liệu ra ngoài phạm vi tuân thủ cho Dynamics 365 Customer Insights, bao gồm dữ liệu có khả năng là thông tin nhạy cảm, chẳng hạn như Dữ liệu cá nhân.</span><span class="sxs-lookup"><span data-stu-id="e0567-145">When you enable Dynamics 365 Customer Insights to transmit data to Sendinblue, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="e0567-146">Microsoft sẽ truyền những dữ liệu đó theo chỉ dẫn của bạn, nhưng bạn có trách nhiệm đảm bảo rằng Sendinblue đáp ứng mọi nghĩa vụ về quyền riêng tư hoặc bảo mật mà bạn có thể có.</span><span class="sxs-lookup"><span data-stu-id="e0567-146">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Sendinblue meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="e0567-147">Để biết thêm thông tin, hãy xem [Tuyên bố về Quyền riêng tư của Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="e0567-147">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="e0567-148">Quản trị viên Dynamics 365 Customer Insights của bạn có thể xóa đích xuất này bất cứ lúc nào để ngừng việc sử dụng chức năng này.</span><span class="sxs-lookup"><span data-stu-id="e0567-148">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
