---
title: Xuất dữ liệu Customer Insights sang Microsoft Advertising
description: Tìm hiểu cách đặt cấu hình kết nối và xuất sang Microsoft Advertising.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c2ac92de2718cf7f0622b407bf198a7a7e50a37b
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124570"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a><span data-ttu-id="d1edc-103">Xuất phân khúc sang Microsoft Advertising (xem trước)</span><span class="sxs-lookup"><span data-stu-id="d1edc-103">Export segments to Microsoft Advertising (preview)</span></span>

<span data-ttu-id="d1edc-104">Xuất phân khúc Customer Insights sang Microsoft Advertising để tạo đối tượng Customer Match.</span><span class="sxs-lookup"><span data-stu-id="d1edc-104">Export Customer Insights segments to Microsoft Advertising to create Customer Match audiences.</span></span> <span data-ttu-id="d1edc-105">Sử dụng những đối tượng này cho chiến dịch quảng cáo của bạn.</span><span class="sxs-lookup"><span data-stu-id="d1edc-105">Use these audiences for your ad campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d1edc-106">Điều kiện tiên quyết</span><span class="sxs-lookup"><span data-stu-id="d1edc-106">Prerequisites</span></span>

-   <span data-ttu-id="d1edc-107">Một [tài khoản Microsoft Advertising](https://ads.microsoft.com/) và thông tin xác thực tương ứng của quản trị viên.</span><span class="sxs-lookup"><span data-stu-id="d1edc-107">An [Microsoft Advertising account](https://ads.microsoft.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="d1edc-108">Bạn đã chấp nhận điều khoản sử dụng của Customer Match.</span><span class="sxs-lookup"><span data-stu-id="d1edc-108">You've accepted the Customer Match terms of use.</span></span> 
-   <span data-ttu-id="d1edc-109">[Các phân khúc đã đặt cấu hình](segments.md) trong thông tin chuyên sâu về đối tượng.</span><span class="sxs-lookup"><span data-stu-id="d1edc-109">[Configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="d1edc-110">Hồ sơ khách hàng hợp nhất trong các phân khúc đã xuất chứa trường có địa chỉ email.</span><span class="sxs-lookup"><span data-stu-id="d1edc-110">Unified customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="d1edc-111">Các giới hạn đã biết</span><span class="sxs-lookup"><span data-stu-id="d1edc-111">Known limitations</span></span>

- <span data-ttu-id="d1edc-112">Bạn có thể xuất tối đa 500 nghìn hồ sơ trong mỗi lần xuất sang Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="d1edc-112">You can export up to 500 K profiles per export to Microsoft Advertising.</span></span>
- <span data-ttu-id="d1edc-113">Bạn chỉ xuất được phân khúc sang Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="d1edc-113">Exporting to Microsoft Advertising is limited to segments.</span></span>
- <span data-ttu-id="d1edc-114">Có thể mất tới 10 phút để hoàn thành quá trình xuất tối đa 500 nghìn hồ sơ sang Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="d1edc-114">Exporting up to 500 K profiles to Microsoft Advertising can take up to 10 minutes to complete.</span></span> 


## <a name="set-up-the-connection-to-microsoft-advertising"></a><span data-ttu-id="d1edc-115">Thiết lập kết nối với Microsoft Advertising</span><span class="sxs-lookup"><span data-stu-id="d1edc-115">Set up the connection to Microsoft Advertising</span></span>

1. <span data-ttu-id="d1edc-116">Đi đến **Quản trị viên** > **Kết nối**.</span><span class="sxs-lookup"><span data-stu-id="d1edc-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="d1edc-117">Chọn **Thêm kết nối** rồi chọn **Microsoft Advertising** để đặt cấu hình kết nối.</span><span class="sxs-lookup"><span data-stu-id="d1edc-117">Select **Add connection** and choose **Microsoft Advertising** to configure the connection.</span></span>

1. <span data-ttu-id="d1edc-118">Đặt tên dễ nhận biết cho kết nối trong trường **Tên hiển thị**.</span><span class="sxs-lookup"><span data-stu-id="d1edc-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="d1edc-119">Tên và loại kết nối mô tả kết nối này.</span><span class="sxs-lookup"><span data-stu-id="d1edc-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="d1edc-120">Bạn nên chọn một tên giải thích mục đích và mục tiêu của kết nối.</span><span class="sxs-lookup"><span data-stu-id="d1edc-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="d1edc-121">Chọn người có thể sử dụng kết nối này.</span><span class="sxs-lookup"><span data-stu-id="d1edc-121">Choose who can use this connection.</span></span> <span data-ttu-id="d1edc-122">Giá trị mặc định là quản trị viên.</span><span class="sxs-lookup"><span data-stu-id="d1edc-122">The default is administrators.</span></span> <span data-ttu-id="d1edc-123">Để biết thêm thông tin, hãy xem [Cho phép người đóng góp sử dụng một kết nối cho các lần xuất](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="d1edc-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="d1edc-124">Chọn **Tôi đồng ý** để xác nhận **Quyền riêng tư về dữ liệu và sự tuân thủ**.</span><span class="sxs-lookup"><span data-stu-id="d1edc-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="d1edc-125">Chọn **Kết nối** để khởi tạo kết nối với Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="d1edc-125">Select **Connect** to initialize the connection to Microsoft Advertising.</span></span>

1. <span data-ttu-id="d1edc-126">Chọn **Xác thực với Microsoft Advertising** và cung cấp thông tin xác thực quản trị viên của bạn cho Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="d1edc-126">Select **Authenticate with Microsoft Advertising** and provide your admin credentials for Microsoft Advertising.</span></span>

1. <span data-ttu-id="d1edc-127">Chọn **Thêm chính bạn là người dùng xuất** và cung cấp thông tin xác thực Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="d1edc-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="d1edc-128">Chọn **Lưu** để hoàn thành kết nối.</span><span class="sxs-lookup"><span data-stu-id="d1edc-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="d1edc-129">Đặt cấu hình xuất</span><span class="sxs-lookup"><span data-stu-id="d1edc-129">Configure an export</span></span>

<span data-ttu-id="d1edc-130">Bạn có thể đặt cấu hình lần xuất này nếu bạn có quyền truy cập vào kết nối thuộc loại này.</span><span class="sxs-lookup"><span data-stu-id="d1edc-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="d1edc-131">Để biết thêm thông tin, hãy xem [Các quyền cần thiết để đặt cấu hình xuất](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="d1edc-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="d1edc-132">Đi tới **Dữ liệu** > **Nội dung xuất**.</span><span class="sxs-lookup"><span data-stu-id="d1edc-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="d1edc-133">Để tạo một nội dung xuất mới, hãy chọn **Thêm đích**.</span><span class="sxs-lookup"><span data-stu-id="d1edc-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="d1edc-134">Trong trường **Kết nối để xuất**, hãy chọn một kết nối từ phần Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="d1edc-134">In the **Connection for export** field, choose a connection from the Microsoft Advertising section.</span></span> <span data-ttu-id="d1edc-135">Nếu bạn không thấy tên phần này, tức là không có kết nối nào thuộc loại này dành cho bạn.</span><span class="sxs-lookup"><span data-stu-id="d1edc-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="d1edc-136">Chọn phân khúc để xuất.</span><span class="sxs-lookup"><span data-stu-id="d1edc-136">Select the segments to export.</span></span> <span data-ttu-id="d1edc-137">Các đối tượng Customer Match trong Microsoft Advertising được tạo tự động với tên của các phân khúc mà bạn đã chọn để xuất.</span><span class="sxs-lookup"><span data-stu-id="d1edc-137">The Customer Match audiences in Microsoft Advertising are automatically created with the name of the segments selected for export.</span></span> <span data-ttu-id="d1edc-138">Mỗi phân khúc sẽ cho ra một đối tượng Customer Match riêng biệt.</span><span class="sxs-lookup"><span data-stu-id="d1edc-138">Each segment will result in a separate Customer Match audience.</span></span> 

1. <span data-ttu-id="d1edc-139">Nhập **ID tài khoản và ID khách hàng Microsoft Advertising**.</span><span class="sxs-lookup"><span data-stu-id="d1edc-139">Enter your **Microsoft Advertising Customer ID and Account ID**.</span></span> <span data-ttu-id="d1edc-140">Bạn có thể tìm thấy ID khách hàng (`cid`) và ID tài khoản (`aid`) trong các tham số của URL khi bạn đăng nhập vào Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="d1edc-140">You can find the Customer ID (`cid`) and Account ID (`aid`) in the parameters of the URL when you're signed in Microsoft Advertising.</span></span>

1. <span data-ttu-id="d1edc-141">Trong phần **So khớp dữ liệu**, trong trường **Email**, hãy chọn trường có địa chỉ email của khách hàng trong hồ sơ khách hàng hợp nhất của bạn.</span><span class="sxs-lookup"><span data-stu-id="d1edc-141">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile with a customer's email address.</span></span> <span data-ttu-id="d1edc-142">Bạn phải xuất các phân khúc sang Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="d1edc-142">It's required to export segments to Microsoft Advertising.</span></span>

1. <span data-ttu-id="d1edc-143">Chọn **Lưu**.</span><span class="sxs-lookup"><span data-stu-id="d1edc-143">Select **Save**.</span></span>

<span data-ttu-id="d1edc-144">Việc lưu một nội dung xuất sẽ không chạy nội dung xuất đó ngay lập tức.</span><span class="sxs-lookup"><span data-stu-id="d1edc-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="d1edc-145">Nội dung xuất chạy trong mỗi lần [làm mới theo lịch trình](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="d1edc-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="d1edc-146">Bạn cũng có thể [xuất dữ liệu theo yêu cầu](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="d1edc-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="d1edc-147">Quyền riêng tư về dữ liệu và sự tuân thủ</span><span class="sxs-lookup"><span data-stu-id="d1edc-147">Data privacy and compliance</span></span>

<span data-ttu-id="d1edc-148">Khi bật Dynamics 365 Customer Insights để truyền dữ liệu đến Microsoft Advertising, bạn cho phép chuyển dữ liệu ra bên ngoài ranh giới tuân thủ của Dynamics 365 Customer Insights, bao gồm cả dữ liệu có thể nhạy cảm như Dữ liệu cá nhân.</span><span class="sxs-lookup"><span data-stu-id="d1edc-148">When you enable Dynamics 365 Customer Insights to transmit data to Microsoft Advertising, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="d1edc-149">Microsoft sẽ chuyển những dữ liệu đó theo chỉ dẫn của bạn, nhưng bạn có trách nhiệm đảm bảo rằng Microsoft Advertising đáp ứng mọi nghĩa vụ về quyền riêng tư hoặc bảo mật mà bạn có thể có.</span><span class="sxs-lookup"><span data-stu-id="d1edc-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Microsoft Advertising meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="d1edc-150">Để biết thêm thông tin, hãy xem [Tuyên bố về Quyền riêng tư của Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="d1edc-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="d1edc-151">Quản trị viên Dynamics 365 Customer Insights của bạn có thể xóa đích xuất này bất cứ lúc nào để ngừng việc sử dụng chức năng này.</span><span class="sxs-lookup"><span data-stu-id="d1edc-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to stop use of this functionality.</span></span>
