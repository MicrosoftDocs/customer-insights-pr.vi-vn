---
title: Xuất dữ liệu Customer Insights sang AdRoll
description: Tìm hiểu cách đặt cấu hình kết nối và xuất sang AdRoll.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: dbebc3ee3978ca6ee9d1ad1c15c226479876709f
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124391"
---
# <a name="export-segments-to-adroll-preview"></a><span data-ttu-id="81de6-103">Xuất phân khúc sang AdRoll (xem trước)</span><span class="sxs-lookup"><span data-stu-id="81de6-103">Export segments to AdRoll (preview)</span></span>

<span data-ttu-id="81de6-104">Xuất phân khúc hồ sơ khách hàng hợp nhất sang AdRoll và sử dụng các phân khúc đó để quảng cáo.</span><span class="sxs-lookup"><span data-stu-id="81de6-104">Export segments of unified customer profiles to AdRoll and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="81de6-105">Điều kiện tiên quyết để kết nối</span><span class="sxs-lookup"><span data-stu-id="81de6-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="81de6-106">Bạn có một [tài khoản AdRoll](https://www.adroll.com/) và thông tin đăng nhập tương ứng của quản trị viên.</span><span class="sxs-lookup"><span data-stu-id="81de6-106">You have an [AdRoll account](https://www.adroll.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="81de6-107">Bạn có [các phân khúc được định cấu hình](segments.md) trong thông tin chuyên sâu về đối tượng.</span><span class="sxs-lookup"><span data-stu-id="81de6-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="81de6-108">Hồ sơ khách hàng hợp nhất trong các phân khúc đã xuất chứa các trường đại diện cho địa chỉ email.</span><span class="sxs-lookup"><span data-stu-id="81de6-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="81de6-109">Các giới hạn đã biết</span><span class="sxs-lookup"><span data-stu-id="81de6-109">Known limitations</span></span>

- <span data-ttu-id="81de6-110">Bạn có thể xuất tối đa 250.000 hồ sơ cho mỗi lần xuất sang AdRoll.</span><span class="sxs-lookup"><span data-stu-id="81de6-110">You can export up to 250'000 profiles in per export to AdRoll.</span></span>
- <span data-ttu-id="81de6-111">Bạn không thể xuất các phân khúc có ít hơn 100 hồ sơ sang AdRoll.</span><span class="sxs-lookup"><span data-stu-id="81de6-111">You can't export segments with fewer than 100 profiles to AdRoll.</span></span> 
- <span data-ttu-id="81de6-112">Bạn chỉ xuất được phân khúc sang AdRoll.</span><span class="sxs-lookup"><span data-stu-id="81de6-112">Exporting to AdRoll is limited to segments.</span></span>
- <span data-ttu-id="81de6-113">Có thể mất tới 10 phút để hoàn tất việc xuất tối đa 250.000 hồ sơ sang AdRoll.</span><span class="sxs-lookup"><span data-stu-id="81de6-113">Exporting up to 250'000 profiles to AdRoll can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="81de6-114">Số lượng hồ sơ mà bạn có thể xuất sang AdRoll phụ thuộc và giới hạn vào hợp đồng của bạn với AdRoll.</span><span class="sxs-lookup"><span data-stu-id="81de6-114">The number of profiles that you can export to AdRoll is dependent and limited on your contract with AdRoll.</span></span>

## <a name="set-up-connection-to-adroll"></a><span data-ttu-id="81de6-115">Thiết lập kết nối với AdRoll</span><span class="sxs-lookup"><span data-stu-id="81de6-115">Set up connection to AdRoll</span></span>

1. <span data-ttu-id="81de6-116">Đi đến **Quản trị viên** > **Kết nối**.</span><span class="sxs-lookup"><span data-stu-id="81de6-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="81de6-117">Chọn **Thêm kết nối** rồi chọn **AdRoll** để đặt cấu hình kết nối.</span><span class="sxs-lookup"><span data-stu-id="81de6-117">Select **Add connection** and choose **AdRoll** to configure the connection.</span></span>

1. <span data-ttu-id="81de6-118">Đặt tên dễ nhận biết cho kết nối trong trường **Tên hiển thị**.</span><span class="sxs-lookup"><span data-stu-id="81de6-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="81de6-119">Tên và loại kết nối mô tả kết nối này.</span><span class="sxs-lookup"><span data-stu-id="81de6-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="81de6-120">Bạn nên chọn một tên giải thích mục đích và mục tiêu của kết nối.</span><span class="sxs-lookup"><span data-stu-id="81de6-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="81de6-121">Chọn người có thể sử dụng kết nối này.</span><span class="sxs-lookup"><span data-stu-id="81de6-121">Choose who can use this connection.</span></span> <span data-ttu-id="81de6-122">Nếu bạn không thực hiện hành động nào, giá trị mặc định sẽ là Quản trị viên.</span><span class="sxs-lookup"><span data-stu-id="81de6-122">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="81de6-123">Để biết thêm thông tin, hãy xem [Cho phép người đóng góp sử dụng một kết nối cho các lần xuất](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="81de6-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="81de6-124">Chọn **Tôi đồng ý** để xác nhận **Quyền riêng tư về dữ liệu và sự tuân thủ**.</span><span class="sxs-lookup"><span data-stu-id="81de6-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="81de6-125">Chọn **Kết nối** để khởi tạo kết nối với AdRoll.</span><span class="sxs-lookup"><span data-stu-id="81de6-125">Select **Connect** to initialize the connection to AdRoll.</span></span>

1. <span data-ttu-id="81de6-126">Chọn **Xác thực bằng AdRoll** và cung cấp thông tin đăng nhập quản trị viên cho AdRoll.</span><span class="sxs-lookup"><span data-stu-id="81de6-126">Select **Authenticate with AdRoll** and provide your admin credentials for AdRoll.</span></span> 

1. <span data-ttu-id="81de6-127">Chọn **Thêm chính bạn là người dùng xuất** và cung cấp thông tin xác thực Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="81de6-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="81de6-128">Chọn **Lưu** để hoàn thành kết nối.</span><span class="sxs-lookup"><span data-stu-id="81de6-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="81de6-129">Đặt cấu hình xuất</span><span class="sxs-lookup"><span data-stu-id="81de6-129">Configure an export</span></span>

<span data-ttu-id="81de6-130">Bạn có thể đặt cấu hình lần xuất này nếu bạn có quyền truy cập vào kết nối thuộc loại này.</span><span class="sxs-lookup"><span data-stu-id="81de6-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="81de6-131">Để biết thêm thông tin, hãy xem [Các quyền cần thiết để đặt cấu hình xuất](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="81de6-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="81de6-132">Đi tới **Dữ liệu** > **Nội dung xuất**.</span><span class="sxs-lookup"><span data-stu-id="81de6-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="81de6-133">Để tạo một nội dung xuất mới, hãy chọn **Thêm đích**.</span><span class="sxs-lookup"><span data-stu-id="81de6-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="81de6-134">Trong trường **Kết nối để xuất**, hãy chọn một kết nối từ phần AdRoll.</span><span class="sxs-lookup"><span data-stu-id="81de6-134">In the **Connection for export** field, choose a connection from the AdRoll section.</span></span> <span data-ttu-id="81de6-135">Nếu bạn không thấy tên phần này, tức là không có kết nối nào thuộc loại này dành cho bạn.</span><span class="sxs-lookup"><span data-stu-id="81de6-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="81de6-136">Nhập **ID nhà quảng cáo AdRoll** của bạn Để biết thêm thông tin, hãy xem [Hồ sơ nhà quảng cáo AdRoll](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="81de6-136">Enter your **AdRoll Advertiser ID** For more information, see [AdRoll Advertiser Profiles](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span></span>

3. <span data-ttu-id="81de6-137">Trong phần **So khớp dữ liệu**, trong trường **Email**, chọn trường trong hồ sơ khách hàng hợp nhất trình bày địa chỉ email của khách hàng.</span><span class="sxs-lookup"><span data-stu-id="81de6-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="81de6-138">Bắt buộc phải xuất các phân khúc sang AdRoll.</span><span class="sxs-lookup"><span data-stu-id="81de6-138">It's required to export segments to AdRoll.</span></span>

1. <span data-ttu-id="81de6-139">Chọn phân khúc mà bạn muốn xuất.</span><span class="sxs-lookup"><span data-stu-id="81de6-139">Select the segments you want to export.</span></span> <span data-ttu-id="81de6-140">Chọn một phân khúc có ít nhất 100 thành viên.</span><span class="sxs-lookup"><span data-stu-id="81de6-140">Select a segment with a least 100 members.</span></span> <span data-ttu-id="81de6-141">Bạn không thể xuất các phân khúc nhỏ hơn.</span><span class="sxs-lookup"><span data-stu-id="81de6-141">You can't export smaller segments.</span></span> <span data-ttu-id="81de6-142">Ngoài ra, kích thước tối đa của một phân khúc để xuất là 250.000 thành viên cho mỗi lần xuất.</span><span class="sxs-lookup"><span data-stu-id="81de6-142">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="81de6-143">Chọn **Lưu**.</span><span class="sxs-lookup"><span data-stu-id="81de6-143">Select **Save**.</span></span>

<span data-ttu-id="81de6-144">Việc lưu một nội dung xuất sẽ không chạy nội dung xuất đó ngay lập tức.</span><span class="sxs-lookup"><span data-stu-id="81de6-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="81de6-145">Nội dung xuất chạy trong mỗi lần [làm mới theo lịch trình](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="81de6-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="81de6-146">Bạn cũng có thể [xuất dữ liệu theo yêu cầu](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="81de6-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="81de6-147">Quyền riêng tư về dữ liệu và sự tuân thủ</span><span class="sxs-lookup"><span data-stu-id="81de6-147">Data privacy and compliance</span></span>

<span data-ttu-id="81de6-148">Khi bật Dynamics 365 Customer Insights để truyền dữ liệu sang AdRoll, bạn cho phép truyền dữ liệu ra ngoài ranh giới tuân thủ của Dynamics 365 Customer Insights, bao gồm cả dữ liệu nhạy cảm như Dữ liệu cá nhân.</span><span class="sxs-lookup"><span data-stu-id="81de6-148">When you enable Dynamics 365 Customer Insights to transmit data to AdRoll, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="81de6-149">Microsoft sẽ chuyển những dữ liệu đó theo chỉ dẫn của bạn, nhưng bạn có trách nhiệm đảm bảo rằng AdRoll đáp ứng mọi nghĩa vụ về quyền riêng tư hoặc bảo mật mà bạn có thể có.</span><span class="sxs-lookup"><span data-stu-id="81de6-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that AdRoll meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="81de6-150">Để biết thêm thông tin, hãy xem [Tuyên bố về Quyền riêng tư của Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="81de6-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="81de6-151">Quản trị viên Dynamics 365 Customer Insights của bạn có thể xóa đích xuất này bất cứ lúc nào để ngừng việc sử dụng chức năng này.</span><span class="sxs-lookup"><span data-stu-id="81de6-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
