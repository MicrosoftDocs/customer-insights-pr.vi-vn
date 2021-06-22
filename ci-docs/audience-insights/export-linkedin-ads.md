---
title: Xuất dữ liệu Customer Insights sang LinkedIn Ads
description: Tìm hiểu cách đặt cấu hình kết nối và xuất sang LinkedIn Ads.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 1c7b0c728bc4d4cf6b5aea79396cf0779fbf298d
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124572"
---
# <a name="export-segments-to-linkedin-ads-preview"></a><span data-ttu-id="1b44d-103">Xuất phân khúc sang LinkedIn Ads (xem trước)</span><span class="sxs-lookup"><span data-stu-id="1b44d-103">Export segments to LinkedIn Ads (preview)</span></span>

<span data-ttu-id="1b44d-104">Xuất phân khúc hồ sơ khách hàng hợp nhất sang LinkedIn Ads để tạo đối tượng phù hợp.</span><span class="sxs-lookup"><span data-stu-id="1b44d-104">Export segments of unified customer profiles to LinkedIn Ads to create matched audiences.</span></span> <span data-ttu-id="1b44d-105">Sử dụng đối tượng phù hợp để nhắm mục tiêu công ty và nhắm mục tiêu người liên hệ.</span><span class="sxs-lookup"><span data-stu-id="1b44d-105">Use the matched audiences for company targeting and contact targeting.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1b44d-106">Điều kiện tiên quyết</span><span class="sxs-lookup"><span data-stu-id="1b44d-106">Prerequisites</span></span>

-   <span data-ttu-id="1b44d-107">Bạn có một [tài khoản LinkedIn Campaign Manager](https://business.linkedin.com/marketing-solutions/ads) và thông tin xác thực tương ứng của quản trị viên.</span><span class="sxs-lookup"><span data-stu-id="1b44d-107">You have an [LinkedIn Campaign Manager account](https://business.linkedin.com/marketing-solutions/ads) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="1b44d-108">Bạn có [các phân khúc đã đặt cấu hình](segments.md) trong thông tin chuyên sâu về đối tượng.</span><span class="sxs-lookup"><span data-stu-id="1b44d-108">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="1b44d-109">Hồ sơ khách hàng trong các phân khúc đã xuất chứa trường có địa chỉ email.</span><span class="sxs-lookup"><span data-stu-id="1b44d-109">Customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="1b44d-110">Các giới hạn đã biết</span><span class="sxs-lookup"><span data-stu-id="1b44d-110">Known limitations</span></span>

- <span data-ttu-id="1b44d-111">Bạn có thể xuất tối đa 100 nghìn hồ sơ trong mỗi lần xuất sang LinkedIn Ads.</span><span class="sxs-lookup"><span data-stu-id="1b44d-111">You can export up to 100K profiles per export to LinkedIn Ads.</span></span>
- <span data-ttu-id="1b44d-112">Bạn chỉ xuất được phân khúc sang LinkedIn Ads.</span><span class="sxs-lookup"><span data-stu-id="1b44d-112">Exporting to LinkedIn Ads is limited to segments.</span></span>
- <span data-ttu-id="1b44d-113">Có thể mất tới 10 phút để hoàn thành quá trình xuất tối đa 100 nghìn hồ sơ sang LinkedIn Ads.</span><span class="sxs-lookup"><span data-stu-id="1b44d-113">Exporting up to 100K profiles to LinkedIn Ads can take up to 10 minutes to complete.</span></span> 

## <a name="set-up-the-connection-to-linkedin-ads"></a><span data-ttu-id="1b44d-114">Thiết lập kết nối với LinkedIn Ads</span><span class="sxs-lookup"><span data-stu-id="1b44d-114">Set up the connection to LinkedIn Ads</span></span>

1. <span data-ttu-id="1b44d-115">Trong thông tin chuyên sâu về đối tượng, hãy đi đến **Quản trị viên** > **Kết nối**.</span><span class="sxs-lookup"><span data-stu-id="1b44d-115">In audience insights, go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="1b44d-116">Chọn **Thêm kết nối** rồi chọn **LinkedIn Ads** để đặt cấu hình kết nối.</span><span class="sxs-lookup"><span data-stu-id="1b44d-116">Select **Add connection** and choose **LinkedIn Ads** to configure the connection.</span></span>

1. <span data-ttu-id="1b44d-117">Đặt tên dễ nhận biết cho kết nối trong trường **Tên hiển thị**.</span><span class="sxs-lookup"><span data-stu-id="1b44d-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="1b44d-118">Tên và loại kết nối mô tả kết nối này.</span><span class="sxs-lookup"><span data-stu-id="1b44d-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="1b44d-119">Bạn nên chọn một tên giải thích mục đích và mục tiêu của kết nối.</span><span class="sxs-lookup"><span data-stu-id="1b44d-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="1b44d-120">Chọn người có thể sử dụng kết nối này.</span><span class="sxs-lookup"><span data-stu-id="1b44d-120">Choose who can use this connection.</span></span> <span data-ttu-id="1b44d-121">Nếu bạn không làm gì cả, giá trị mặc định sẽ là quản trị viên.</span><span class="sxs-lookup"><span data-stu-id="1b44d-121">If you take no action, the default is administrators.</span></span> <span data-ttu-id="1b44d-122">Để biết thêm thông tin, hãy xem [Cho phép người đóng góp sử dụng một kết nối cho các lần xuất](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="1b44d-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="1b44d-123">Cung cấp [ID tài khoản LinkedIn Campaign Manager](https://www.linkedin.com/help/lms/answer/a424270) của bạn.</span><span class="sxs-lookup"><span data-stu-id="1b44d-123">Provide your [LinkedIn Campaign Manager Account ID](https://www.linkedin.com/help/lms/answer/a424270).</span></span>

1. <span data-ttu-id="1b44d-124">Chọn **Tôi đồng ý** để xác nhận **Quyền riêng tư về dữ liệu và sự tuân thủ**.</span><span class="sxs-lookup"><span data-stu-id="1b44d-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="1b44d-125">Chọn **Kết nối** để khởi tạo kết nối với Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="1b44d-125">Select **Connect** to initialize the connection to Campaign Monitor.</span></span>

1. <span data-ttu-id="1b44d-126">Chọn **Xác thực với LinkedIn** và cung cấp thông tin xác thực quản trị viên của bạn cho LinkedIn Campaign Manager.</span><span class="sxs-lookup"><span data-stu-id="1b44d-126">Select **Authenticate with LinkedIn** and provide your admin credentials for LinkedIn Campaign Manager.</span></span>

1. <span data-ttu-id="1b44d-127">Chọn **Thêm chính bạn là người dùng xuất** và cung cấp thông tin xác thực Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="1b44d-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="1b44d-128">Chọn **Lưu** để hoàn thành kết nối.</span><span class="sxs-lookup"><span data-stu-id="1b44d-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="1b44d-129">Đặt cấu hình xuất</span><span class="sxs-lookup"><span data-stu-id="1b44d-129">Configure an export</span></span>

<span data-ttu-id="1b44d-130">Bạn có thể đặt cấu hình nội dung xuất nếu có quyền truy cập vào kết nối thuộc loại này.</span><span class="sxs-lookup"><span data-stu-id="1b44d-130">You can configure an export if you have access to a connection of this type.</span></span> <span data-ttu-id="1b44d-131">Để biết thêm thông tin, hãy xem [Các quyền cần thiết để đặt cấu hình xuất](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="1b44d-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="1b44d-132">Đi tới **Dữ liệu** > **Nội dung xuất**.</span><span class="sxs-lookup"><span data-stu-id="1b44d-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="1b44d-133">Để tạo một nội dung xuất mới, hãy chọn **Thêm đích**.</span><span class="sxs-lookup"><span data-stu-id="1b44d-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="1b44d-134">Trong trường **Kết nối để xuất**, hãy chọn một kết nối từ phần LinkedIn Ads.</span><span class="sxs-lookup"><span data-stu-id="1b44d-134">In the **Connection for export** field, choose a connection from the LinkedIn Ads section.</span></span> <span data-ttu-id="1b44d-135">Nếu bạn không thấy tên phần này, tức là không có kết nối nào thuộc loại này dành cho bạn.</span><span class="sxs-lookup"><span data-stu-id="1b44d-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="1b44d-136">Chọn xem bạn muốn xuất dữ liệu để [nhắm mục tiêu người liên hệ](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) hay [nhắm mục tiêu công ty](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) trên LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="1b44d-136">Choose whether you want to export data to do [contact targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) or [company targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) on LinkedIn.</span></span> 

1. <span data-ttu-id="1b44d-137">Trong phần **So khớp dữ liệu**, hãy chọn trường đại diện cho địa chỉ email của khách hàng trong hồ sơ khách hàng hợp nhất của bạn.</span><span class="sxs-lookup"><span data-stu-id="1b44d-137">In the **Data matching** section, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="1b44d-138">Bạn phải xuất các phân khúc sang LinkedIn Ads.</span><span class="sxs-lookup"><span data-stu-id="1b44d-138">It's required to export segments to LinkedIn Ads.</span></span>

1. <span data-ttu-id="1b44d-139">Chọn phân khúc mà bạn muốn xuất.</span><span class="sxs-lookup"><span data-stu-id="1b44d-139">Select the segments you want to export.</span></span> <span data-ttu-id="1b44d-140">Đối tượng phù hợp trong LinkedIn Campaign Manager sẽ được tạo tự động với tên của các phân khúc mà bạn đã chọn để xuất.</span><span class="sxs-lookup"><span data-stu-id="1b44d-140">The matched audiences in LinkedIn Campaign Manager will automatically be created with the name of the segments that you selected to export.</span></span> <span data-ttu-id="1b44d-141">Mỗi phân khúc sẽ cho ra một đối tượng phù hợp riêng biệt.</span><span class="sxs-lookup"><span data-stu-id="1b44d-141">Each segment will result in a separate matched audience.</span></span> 

1. <span data-ttu-id="1b44d-142">Chọn **Lưu**.</span><span class="sxs-lookup"><span data-stu-id="1b44d-142">Select **Save**.</span></span>

<span data-ttu-id="1b44d-143">Việc lưu một nội dung xuất sẽ không chạy nội dung xuất đó ngay lập tức.</span><span class="sxs-lookup"><span data-stu-id="1b44d-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="1b44d-144">Nội dung xuất chạy trong mỗi lần [làm mới theo lịch trình](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="1b44d-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="1b44d-145">Bạn cũng có thể [xuất dữ liệu theo yêu cầu](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="1b44d-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="1b44d-146">Quyền riêng tư về dữ liệu và sự tuân thủ</span><span class="sxs-lookup"><span data-stu-id="1b44d-146">Data privacy and compliance</span></span>

<span data-ttu-id="1b44d-147">Khi bật Dynamics 365 Customer Insights để truyền dữ liệu đến LinkedIn Ads, bạn cho phép chuyển dữ liệu ra bên ngoài ranh giới tuân thủ của Dynamics 365 Customer Insights, bao gồm cả dữ liệu có thể nhạy cảm như Dữ liệu cá nhân.</span><span class="sxs-lookup"><span data-stu-id="1b44d-147">When you enable Dynamics 365 Customer Insights to transmit data to LinkedIn Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="1b44d-148">Microsoft sẽ chuyển những dữ liệu đó theo chỉ dẫn của bạn, nhưng bạn có trách nhiệm đảm bảo rằng LinkedIn Ads đáp ứng mọi nghĩa vụ về quyền riêng tư hoặc bảo mật mà bạn có thể có.</span><span class="sxs-lookup"><span data-stu-id="1b44d-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that LinkedIn Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="1b44d-149">Để biết thêm thông tin, hãy xem [Tuyên bố về Quyền riêng tư của Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="1b44d-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="1b44d-150">Quản trị viên Dynamics 365 Customer Insights của bạn có thể xóa đích xuất này bất cứ lúc nào để ngừng việc sử dụng chức năng này.</span><span class="sxs-lookup"><span data-stu-id="1b44d-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to stop the use of this functionality.</span></span>
