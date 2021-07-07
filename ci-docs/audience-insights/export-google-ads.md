---
title: Xuất dữ liệu Customer Insights sang Google Ads
description: Tìm hiểu cách định cấu hình kết nối và xuất sang Google Ads.
ms.date: 03/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: c23c8b4e6758df08e04bf1e3ae0cba4dee06fe2b
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305366"
---
# <a name="export-segments-to-google-ads-preview"></a><span data-ttu-id="95631-103">Xuất phân khúc sang Google Ads (bản xem trước)</span><span class="sxs-lookup"><span data-stu-id="95631-103">Export segments to Google Ads (preview)</span></span>

<span data-ttu-id="95631-104">Xuất các phân khúc hồ sơ khách hàng hợp nhất sang danh sách đối tượng Google Ads và sử dụng chúng để quảng cáo trên Google Tìm kiếm, Gmail, YouTube và Google Display Network.</span><span class="sxs-lookup"><span data-stu-id="95631-104">Export segments of unified customer profiles to a Google Ads audience list and use them to advertise on Google Search, Gmail, YouTube, and Google Display Network.</span></span> 

## <a name="prerequisites-for-connection"></a><span data-ttu-id="95631-105">Điều kiện tiên quyết để kết nối</span><span class="sxs-lookup"><span data-stu-id="95631-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="95631-106">Bạn có một [Tài khoản Google Ads](https://ads.google.com/) và thông tin đăng nhập quản trị viên tương ứng.</span><span class="sxs-lookup"><span data-stu-id="95631-106">You have a [Google Ads account](https://ads.google.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="95631-107">Bạn có một [Mã thông báo Nhà phát triển Google Ads được chấp thuận](https://developers.google.com/google-ads/api/docs/first-call/dev-token).</span><span class="sxs-lookup"><span data-stu-id="95631-107">You have an [approved Google Ads Developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token).</span></span> 
-   <span data-ttu-id="95631-108">Bạn đáp ứng các yêu cầu của [Chính sách đối sánh khách hàng](https://support.google.com/adspolicy/answer/6299717).</span><span class="sxs-lookup"><span data-stu-id="95631-108">You fulfill the requirements of the [Customer Match Policy](https://support.google.com/adspolicy/answer/6299717).</span></span>
-   <span data-ttu-id="95631-109">Bạn đáp ứng các yêu cầu về [kích thước danh sách tiếp thị lại](https://support.google.com/google-ads/answer/7558048).</span><span class="sxs-lookup"><span data-stu-id="95631-109">You fulfill the requirements of the [remarketing list sizes](https://support.google.com/google-ads/answer/7558048).</span></span>
-   <span data-ttu-id="95631-110">Có đối tượng hiện có trong Google Ads và các ID tương ứng.</span><span class="sxs-lookup"><span data-stu-id="95631-110">There are existing audiences in Google Ads and the corresponding IDs.</span></span> <span data-ttu-id="95631-111">Để biết thêm thông tin, hãy xem [Đối tượng Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span><span class="sxs-lookup"><span data-stu-id="95631-111">For more information, see [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span></span>
-   <span data-ttu-id="95631-112">Bạn có [các phân khúc được định cấu hình](segments.md).</span><span class="sxs-lookup"><span data-stu-id="95631-112">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="95631-113">Hồ sơ khách hàng hợp nhất trong các phân khúc đã xuất chứa các trường đại diện cho địa chỉ email, tên và họ.</span><span class="sxs-lookup"><span data-stu-id="95631-113">Unified customer profiles in the exported segments contain fields representing an email address, first name, and last name.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="95631-114">Các hạn chế đã biết</span><span class="sxs-lookup"><span data-stu-id="95631-114">Known limitations</span></span>

- <span data-ttu-id="95631-115">Lên đến 1 triệu hồ sơ mỗi lần xuất sang Google Ads.</span><span class="sxs-lookup"><span data-stu-id="95631-115">Up to 1 million profiles per export to Google Ads.</span></span>
- <span data-ttu-id="95631-116">Việc xuất sang Google Ads bị giới hạn ở các phân khúc.</span><span class="sxs-lookup"><span data-stu-id="95631-116">Exporting to Google Ads is limited to segments.</span></span>
- <span data-ttu-id="95631-117">Việc xuất các phân khúc với tổng số 1 triệu hồ sơ có thể mất đến 5 phút vì những hạn chế từ phía nhà cung cấp.</span><span class="sxs-lookup"><span data-stu-id="95631-117">Exporting segments with a total of 1 million profiles can take up to 5 minutes because of limitations on the provider side.</span></span> 
- <span data-ttu-id="95631-118">Quá trình so khớp trong Google Ads có thể mất đến 48 giờ.</span><span class="sxs-lookup"><span data-stu-id="95631-118">The matching in Google Ads can take up to 48 hours.</span></span>

## <a name="set-up-connection-to-google-ads"></a><span data-ttu-id="95631-119">Thiết lập kết nối với Google Ads</span><span class="sxs-lookup"><span data-stu-id="95631-119">Set up connection to Google Ads</span></span>

1. <span data-ttu-id="95631-120">Đi đến **Quản trị viên** > **Kết nối**.</span><span class="sxs-lookup"><span data-stu-id="95631-120">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="95631-121">Chọn **Thêm kết nối** rồi chọn **Google Ads** để định cấu hình kết nối.</span><span class="sxs-lookup"><span data-stu-id="95631-121">Select **Add connection** and choose **Google Ads** to configure the connection.</span></span>

1. <span data-ttu-id="95631-122">Đặt tên dễ nhận biết cho kết nối trong trường **Tên hiển thị**.</span><span class="sxs-lookup"><span data-stu-id="95631-122">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="95631-123">Tên và loại kết nối mô tả kết nối này.</span><span class="sxs-lookup"><span data-stu-id="95631-123">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="95631-124">Bạn nên chọn một tên giải thích mục đích và mục tiêu của kết nối.</span><span class="sxs-lookup"><span data-stu-id="95631-124">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="95631-125">Chọn người có thể sử dụng kết nối này.</span><span class="sxs-lookup"><span data-stu-id="95631-125">Choose who can use this connection.</span></span> <span data-ttu-id="95631-126">Nếu bạn không thực hiện hành động nào, giá trị mặc định sẽ là Quản trị viên.</span><span class="sxs-lookup"><span data-stu-id="95631-126">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="95631-127">Để biết thêm thông tin, hãy xem [Cho phép người đóng góp sử dụng một kết nối cho các lần xuất](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="95631-127">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="95631-128">Nhập **[ID khách hàng Google Ads](https://support.google.com/google-ads/answer/1704344)**.</span><span class="sxs-lookup"><span data-stu-id="95631-128">Enter your **[Google Ads customer ID](https://support.google.com/google-ads/answer/1704344)**.</span></span>

1. <span data-ttu-id="95631-129">Nhập **[Mã thông báo nhà phát triển được Google Ads phê duyệt](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span><span class="sxs-lookup"><span data-stu-id="95631-129">Enter your **[Google Ads approved developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span></span>

1. <span data-ttu-id="95631-130">Chọn **Tôi đồng ý** để xác nhận **Quyền riêng tư về dữ liệu và sự tuân thủ**.</span><span class="sxs-lookup"><span data-stu-id="95631-130">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="95631-131">Chọn **Xác thực bằng Google Ads** và cung cấp thông tin đăng nhập Google Ads của bạn.</span><span class="sxs-lookup"><span data-stu-id="95631-131">Select **Authenticate with Google Ads** and provide your Google Ads credentials.</span></span>

1. <span data-ttu-id="95631-132">Chọn **Thêm chính bạn là người dùng xuất** và cung cấp thông tin xác thực Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="95631-132">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="95631-133">Chọn **Lưu** để hoàn thành kết nối.</span><span class="sxs-lookup"><span data-stu-id="95631-133">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="95631-134">Định cấu hình xuất</span><span class="sxs-lookup"><span data-stu-id="95631-134">Configure an export</span></span>

<span data-ttu-id="95631-135">Bạn có thể định cấu hình lần xuất này nếu bạn có quyền truy cập vào kết nối thuộc loại này.</span><span class="sxs-lookup"><span data-stu-id="95631-135">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="95631-136">Để biết thêm thông tin, hãy xem [Các quyền cần thiết để định cấu hình xuất](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="95631-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="95631-137">Đi tới **Dữ liệu** > **Nội dung xuất**.</span><span class="sxs-lookup"><span data-stu-id="95631-137">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="95631-138">Để tạo một nội dung xuất mới, hãy chọn **Thêm đích**.</span><span class="sxs-lookup"><span data-stu-id="95631-138">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="95631-139">Trong trường **Kết nối để xuất**, hãy chọn một kết nối từ phần Google Ads.</span><span class="sxs-lookup"><span data-stu-id="95631-139">In the **Connection for export** field, choose a connection from the Google Ads section.</span></span> <span data-ttu-id="95631-140">Nếu bạn không thấy tên phần này thì có nghĩa là không có kết nối nào thuộc loại này khả dụng cho bạn.</span><span class="sxs-lookup"><span data-stu-id="95631-140">If you don't see this section name, then no connections of this type are available to you.</span></span>

1. <span data-ttu-id="95631-141">Nhập **[ID đối tượng Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** và chọn **Kết nối** để khởi tạo kết nối với Google Ads.</span><span class="sxs-lookup"><span data-stu-id="95631-141">Enter your **[Google Ads audience ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** and select **Connect** to initialize the connection to Google Ads.</span></span>

1. <span data-ttu-id="95631-142">Trong phần **So khớp dữ liệu**, trong trường **Email**, chọn trường trong hồ sơ khách hàng hợp nhất trình bày địa chỉ email của khách hàng.</span><span class="sxs-lookup"><span data-stu-id="95631-142">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="95631-143">Lặp lại các bước tương tự cho các trường **Tên** và **Họ**.</span><span class="sxs-lookup"><span data-stu-id="95631-143">Repeat the same steps for **First name** and **Last name** fields.</span></span>

1. <span data-ttu-id="95631-144">Chọn phân khúc mà bạn muốn xuất.</span><span class="sxs-lookup"><span data-stu-id="95631-144">Select the segments you want to export.</span></span> <span data-ttu-id="95631-145">Bạn có thể xuất tổng cộng tối đa 1 triệu hồ sơ khách hàng sang Google Ads.</span><span class="sxs-lookup"><span data-stu-id="95631-145">You can export up to 1 million customer profiles in total to Google Ads.</span></span>

<span data-ttu-id="95631-146">Việc lưu một nội dung xuất sẽ không chạy nội dung xuất đó ngay lập tức.</span><span class="sxs-lookup"><span data-stu-id="95631-146">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="95631-147">Nội dung xuất chạy trong mỗi lần [làm mới theo lịch trình](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="95631-147">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> 

<span data-ttu-id="95631-148">Bạn cũng có thể [xuất dữ liệu theo yêu cầu](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="95631-148">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="95631-149">Quyền riêng tư về dữ liệu và sự tuân thủ</span><span class="sxs-lookup"><span data-stu-id="95631-149">Data privacy and compliance</span></span>

<span data-ttu-id="95631-150">Khi bật Dynamics 365 Customer Insights để truyền dữ liệu tới Google Ads, bạn cho phép chuyển dữ liệu ra bên ngoài ranh giới tuân thủ cho Dynamics 365 Customer Insights, bao gồm dữ liệu nhạy cảm tiềm ẩn như Dữ liệu cá nhân.</span><span class="sxs-lookup"><span data-stu-id="95631-150">When you enable Dynamics 365 Customer Insights to transmit data to Google Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="95631-151">Microsoft sẽ chuyển những dữ liệu đó theo chỉ dẫn của bạn, nhưng bạn có trách nhiệm đảm bảo rằng Google Ads đáp ứng mọi nghĩa vụ về quyền riêng tư hoặc bảo mật mà bạn có thể có.</span><span class="sxs-lookup"><span data-stu-id="95631-151">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Google Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="95631-152">Để biết thêm thông tin, hãy xem [Tuyên bố về Quyền riêng tư của Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="95631-152">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="95631-153">Quản trị viên Dynamics 365 Customer Insights của bạn có thể xóa đích xuất này bất cứ lúc nào để ngừng việc sử dụng chức năng này.</span><span class="sxs-lookup"><span data-stu-id="95631-153">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
