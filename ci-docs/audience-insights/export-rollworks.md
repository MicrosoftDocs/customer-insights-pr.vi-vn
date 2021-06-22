---
title: Xuất dữ liệu Customer Insights sang RollWorks
description: Tìm hiểu cách đặt cấu hình kết nối và xuất sang RollWorks.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: dce5d51ca4587b4d7a0644cc701c1826854882b5
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124115"
---
# <a name="export-segments-to-rollworks-preview"></a><span data-ttu-id="4a148-103">Xuất phân khúc sang RollWorks (xem trước)</span><span class="sxs-lookup"><span data-stu-id="4a148-103">Export segments to RollWorks (preview)</span></span>

<span data-ttu-id="4a148-104">Xuất các phân khúc hồ sơ khách hàng hợp nhất sang RollWorks và sử dụng chúng cho quảng cáo.</span><span class="sxs-lookup"><span data-stu-id="4a148-104">Export segments of unified customer profiles to RollWorks and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="4a148-105">Điều kiện tiên quyết để kết nối</span><span class="sxs-lookup"><span data-stu-id="4a148-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="4a148-106">Bạn có một [Tài khoản RollWorks](https://www.rollworks.com/) và thông tin xác thực tương ứng của quản trị viên.</span><span class="sxs-lookup"><span data-stu-id="4a148-106">You have an [RollWorks account](https://www.rollworks.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="4a148-107">Bạn có [các phân khúc được định cấu hình](segments.md) trong thông tin chuyên sâu về đối tượng.</span><span class="sxs-lookup"><span data-stu-id="4a148-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="4a148-108">Hồ sơ khách hàng hợp nhất trong các phân khúc đã xuất chứa các trường đại diện cho địa chỉ email.</span><span class="sxs-lookup"><span data-stu-id="4a148-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="4a148-109">Các giới hạn đã biết</span><span class="sxs-lookup"><span data-stu-id="4a148-109">Known limitations</span></span>

- <span data-ttu-id="4a148-110">Bạn có thể xuất tối đa 250.000 hồ sơ trong mỗi lần xuất sang RollWorks.</span><span class="sxs-lookup"><span data-stu-id="4a148-110">You can export up to 250'000 profiles in per export to RollWorks.</span></span>
- <span data-ttu-id="4a148-111">Bạn không thể xuất các phân khúc có ít hơn 100 hồ sơ sang RollWorks.</span><span class="sxs-lookup"><span data-stu-id="4a148-111">You can't export segments with fewer than 100 profiles to RollWorks.</span></span> 
- <span data-ttu-id="4a148-112">Bạn chỉ xuất được phân khúc sang RollWorks.</span><span class="sxs-lookup"><span data-stu-id="4a148-112">Exporting to RollWorks is limited to segments.</span></span>
- <span data-ttu-id="4a148-113">Có thể mất tới 10 phút để hoàn thành quá trình xuất tối đa 250.000 hồ sơ sang RollWorks.</span><span class="sxs-lookup"><span data-stu-id="4a148-113">Exporting up to 250'000 profiles to RollWorks can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="4a148-114">Số lượng hồ sơ mà bạn có thể xuất sang RollWorks phụ thuộc và bị giới hạn theo hợp đồng của bạn với RollWorks.</span><span class="sxs-lookup"><span data-stu-id="4a148-114">The number of profiles that you can export to RollWorks is dependent and limited on your contract with RollWorks.</span></span>

## <a name="set-up-connection-to-rollworks"></a><span data-ttu-id="4a148-115">Thiết lập kết nối với RollWorks</span><span class="sxs-lookup"><span data-stu-id="4a148-115">Set up connection to RollWorks</span></span>

1. <span data-ttu-id="4a148-116">Đi đến **Quản trị viên** > **Kết nối**.</span><span class="sxs-lookup"><span data-stu-id="4a148-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="4a148-117">Chọn **Thêm kết nối** rồi chọn **RollWorks** để đặt cấu hình kết nối.</span><span class="sxs-lookup"><span data-stu-id="4a148-117">Select **Add connection** and choose **RollWorks** to configure the connection.</span></span>

1. <span data-ttu-id="4a148-118">Đặt tên dễ nhận biết cho kết nối trong trường **Tên hiển thị**.</span><span class="sxs-lookup"><span data-stu-id="4a148-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="4a148-119">Tên và loại kết nối mô tả kết nối này.</span><span class="sxs-lookup"><span data-stu-id="4a148-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="4a148-120">Bạn nên chọn một tên giải thích mục đích và mục tiêu của kết nối.</span><span class="sxs-lookup"><span data-stu-id="4a148-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="4a148-121">Chọn người có thể sử dụng kết nối này.</span><span class="sxs-lookup"><span data-stu-id="4a148-121">Choose who can use this connection.</span></span> <span data-ttu-id="4a148-122">Nếu bạn không thực hiện hành động nào, giá trị mặc định sẽ là Quản trị viên.</span><span class="sxs-lookup"><span data-stu-id="4a148-122">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="4a148-123">Để biết thêm thông tin, hãy xem [Cho phép người đóng góp sử dụng một kết nối cho các lần xuất](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="4a148-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="4a148-124">Chọn **Tôi đồng ý** để xác nhận **Quyền riêng tư về dữ liệu và sự tuân thủ**.</span><span class="sxs-lookup"><span data-stu-id="4a148-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="4a148-125">Chọn **Kết nối** để khởi tạo kết nối với RollWorks.</span><span class="sxs-lookup"><span data-stu-id="4a148-125">Select **Connect** to initialize the connection to RollWorks.</span></span>

1. <span data-ttu-id="4a148-126">Chọn **Xác thực với RollWorks** và cung cấp thông tin xác thực quản trị viên của bạn cho RollWorks.</span><span class="sxs-lookup"><span data-stu-id="4a148-126">Select **Authenticate with RollWorks** and provide your admin credentials for RollWorks.</span></span>

1. <span data-ttu-id="4a148-127">Chọn **Thêm chính bạn là người dùng xuất** và cung cấp thông tin xác thực Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="4a148-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="4a148-128">Chọn **Lưu** để hoàn thành kết nối.</span><span class="sxs-lookup"><span data-stu-id="4a148-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="4a148-129">Đặt cấu hình xuất</span><span class="sxs-lookup"><span data-stu-id="4a148-129">Configure an export</span></span>

<span data-ttu-id="4a148-130">Bạn có thể đặt cấu hình lần xuất này nếu bạn có quyền truy cập vào kết nối thuộc loại này.</span><span class="sxs-lookup"><span data-stu-id="4a148-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="4a148-131">Để biết thêm thông tin, hãy xem [Các quyền cần thiết để đặt cấu hình xuất](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="4a148-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="4a148-132">Đi tới **Dữ liệu** > **Nội dung xuất**.</span><span class="sxs-lookup"><span data-stu-id="4a148-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="4a148-133">Để tạo một nội dung xuất mới, hãy chọn **Thêm đích**.</span><span class="sxs-lookup"><span data-stu-id="4a148-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="4a148-134">Trong trường **Kết nối để xuất**, hãy chọn một kết nối từ phần RollWorks.</span><span class="sxs-lookup"><span data-stu-id="4a148-134">In the **Connection for export** field, choose a connection from the RollWorks section.</span></span> <span data-ttu-id="4a148-135">Nếu bạn không thấy tên phần này, tức là không có kết nối nào thuộc loại này dành cho bạn.</span><span class="sxs-lookup"><span data-stu-id="4a148-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="4a148-136">Nhập **ID nhà quảng cáo RollWorks** của bạn [Có thể quảng cáo trên RollWorks](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="4a148-136">Enter your **RollWorks Advertiser ID** [RollWorks Advertisable](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span></span>

3. <span data-ttu-id="4a148-137">Trong phần **So khớp dữ liệu**, trong trường **Email**, chọn trường trong hồ sơ khách hàng hợp nhất trình bày địa chỉ email của khách hàng.</span><span class="sxs-lookup"><span data-stu-id="4a148-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="4a148-138">Bạn phải xuất các phân khúc sang RollWorks.</span><span class="sxs-lookup"><span data-stu-id="4a148-138">It's required to export segments to RollWorks.</span></span>

1. <span data-ttu-id="4a148-139">Chọn phân khúc mà bạn muốn xuất.</span><span class="sxs-lookup"><span data-stu-id="4a148-139">Select the segments you want to export.</span></span> <span data-ttu-id="4a148-140">Chọn một phân khúc có ít nhất 100 thành viên.</span><span class="sxs-lookup"><span data-stu-id="4a148-140">Select a segment with a least 100 members.</span></span> <span data-ttu-id="4a148-141">Bạn không thể xuất các phân khúc nhỏ hơn.</span><span class="sxs-lookup"><span data-stu-id="4a148-141">You can't export smaller segments.</span></span> <span data-ttu-id="4a148-142">Ngoài ra, kích thước tối đa của một phân khúc để xuất là 250.000 thành viên cho mỗi lần xuất.</span><span class="sxs-lookup"><span data-stu-id="4a148-142">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="4a148-143">Chọn **Lưu**.</span><span class="sxs-lookup"><span data-stu-id="4a148-143">Select **Save**.</span></span>

<span data-ttu-id="4a148-144">Việc lưu một nội dung xuất sẽ không chạy nội dung xuất đó ngay lập tức.</span><span class="sxs-lookup"><span data-stu-id="4a148-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="4a148-145">Nội dung xuất chạy trong mỗi lần [làm mới theo lịch trình](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="4a148-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="4a148-146">Bạn cũng có thể [xuất dữ liệu theo yêu cầu](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="4a148-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="4a148-147">Quyền riêng tư về dữ liệu và sự tuân thủ</span><span class="sxs-lookup"><span data-stu-id="4a148-147">Data privacy and compliance</span></span>

<span data-ttu-id="4a148-148">Khi bật Dynamics 365 Customer Insights để truyền dữ liệu đến RollWorks, bạn cho phép chuyển dữ liệu ra bên ngoài ranh giới tuân thủ của Dynamics 365 Customer Insights, bao gồm cả dữ liệu có thể nhạy cảm như Dữ liệu cá nhân.</span><span class="sxs-lookup"><span data-stu-id="4a148-148">When you enable Dynamics 365 Customer Insights to transmit data to RollWorks, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="4a148-149">Microsoft sẽ chuyển những dữ liệu đó theo chỉ dẫn của bạn, nhưng bạn có trách nhiệm đảm bảo rằng RollWorks đáp ứng mọi nghĩa vụ về quyền riêng tư hoặc bảo mật mà bạn có thể có.</span><span class="sxs-lookup"><span data-stu-id="4a148-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that RollWorks meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="4a148-150">Để biết thêm thông tin, hãy xem [Tuyên bố về Quyền riêng tư của Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="4a148-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="4a148-151">Quản trị viên Dynamics 365 Customer Insights của bạn có thể xóa đích xuất này bất cứ lúc nào để ngừng việc sử dụng chức năng này.</span><span class="sxs-lookup"><span data-stu-id="4a148-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
