---
title: Xuất dữ liệu Customer Insights sang Google Ads
description: Tìm hiểu cách định cấu hình kết nối với Google Ads.
ms.date: 11/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ba7c82e643ea0dc1897e0954e78646932cafffa3
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268988"
---
# <a name="connector-for-google-ads-preview"></a><span data-ttu-id="2f888-103">Trình kết nối cho Google Ads (bản xem trước)</span><span class="sxs-lookup"><span data-stu-id="2f888-103">Connector for Google Ads (preview)</span></span>

<span data-ttu-id="2f888-104">Xuất các phân đoạn hồ sơ khách hàng hợp nhất sang danh sách đối tượng Google Ads và sử dụng chúng để quảng cáo trên Google Tìm kiếm, Gmail, YouTube và Mạng hiển thị của Google.</span><span class="sxs-lookup"><span data-stu-id="2f888-104">Export segments of unified customer profiles to Google Ads audience list and use them to advertise on Google Search, Gmail, YouTube, and Google Display Network.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="2f888-105">Điều kiện tiên quyết</span><span class="sxs-lookup"><span data-stu-id="2f888-105">Prerequisites</span></span>

-   <span data-ttu-id="2f888-106">Bạn có một [Tài khoản Google Ads](https://ads.google.com/) và thông tin đăng nhập quản trị viên tương ứng.</span><span class="sxs-lookup"><span data-stu-id="2f888-106">You have a [Google Ads account](https://ads.google.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="2f888-107">Có đối tượng hiện có trong Google Ads và các ID tương ứng.</span><span class="sxs-lookup"><span data-stu-id="2f888-107">There are existing audiences in Google Ads and the corresponding IDs.</span></span> <span data-ttu-id="2f888-108">Để biết thêm thông tin, hãy xem [Đối tượng Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span><span class="sxs-lookup"><span data-stu-id="2f888-108">For more information, see [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span></span>
-   <span data-ttu-id="2f888-109">Bạn có [các phân đoạn được định cấu hình](segments.md)</span><span class="sxs-lookup"><span data-stu-id="2f888-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="2f888-110">Hồ sơ khách hàng hợp nhất trong các phân đoạn đã xuất chứa các trường đại diện cho địa chỉ email, tên và họ</span><span class="sxs-lookup"><span data-stu-id="2f888-110">Unified customer profiles in the exported segments contain fields representing an email address, first name, and last name</span></span>

## <a name="connect-to-google-ads"></a><span data-ttu-id="2f888-111">Kết nối với Google Ads</span><span class="sxs-lookup"><span data-stu-id="2f888-111">Connect to Google Ads</span></span>

1. <span data-ttu-id="2f888-112">Đi tới **Quản trị viên** > **Đích xuất**.</span><span class="sxs-lookup"><span data-stu-id="2f888-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="2f888-113">Trong **Google Ads**, chọn **Thiết lập**.</span><span class="sxs-lookup"><span data-stu-id="2f888-113">Under **Google Ads**, select **Set up**.</span></span>

1. <span data-ttu-id="2f888-114">Trong trường **Tên hiển thị**, hãy đặt cho đích xuất một cái tên dễ nhận biết.</span><span class="sxs-lookup"><span data-stu-id="2f888-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="2f888-115">Nhập **[ID khách hàng Google Ads](https://support.google.com/google-ads/answer/1704344)**.</span><span class="sxs-lookup"><span data-stu-id="2f888-115">Enter your **[Google Ads customer ID](https://support.google.com/google-ads/answer/1704344)**.</span></span>

1. <span data-ttu-id="2f888-116">Nhập **[Mã thông báo nhà phát triển được Google Ads phê duyệt](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span><span class="sxs-lookup"><span data-stu-id="2f888-116">Enter your **[Google Ads approved developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span></span>

1. <span data-ttu-id="2f888-117">Chọn **Tôi đồng ý** để xác nhận **Quyền riêng tư về dữ liệu và sự tuân thủ**.</span><span class="sxs-lookup"><span data-stu-id="2f888-117">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="2f888-118">Nhập **[ID đối tượng Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** và chọn **Kết nối** để khởi tạo kết nối với Google Ads.</span><span class="sxs-lookup"><span data-stu-id="2f888-118">Enter your **[Google Ads audience ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** and select **Connect** to initialize the connection to Google Ads.</span></span>

1. <span data-ttu-id="2f888-119">Chọn **Xác thực bằng Google Ads** và cung cấp thông tin đăng nhập Google Ads của bạn.</span><span class="sxs-lookup"><span data-stu-id="2f888-119">Select **Authenticate with Google Ads** and provide your Google Ads credentials.</span></span>

1. <span data-ttu-id="2f888-120">Chọn **Thêm chính bạn là người dùng xuất** và cung cấp thông tin xác thực Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="2f888-120">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-segments-googleads.PNG" alt-text="Xuất ảnh chụp màn hình cho kết nối Google Ads":::

1. <span data-ttu-id="2f888-122">Chọn **Tiếp** để định cấu hình xuất.</span><span class="sxs-lookup"><span data-stu-id="2f888-122">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="2f888-123">Đặt cấu hình trình kết nối</span><span class="sxs-lookup"><span data-stu-id="2f888-123">Configure the connector</span></span>

1. <span data-ttu-id="2f888-124">Trong phần **So khớp dữ liệu**, trong trường **Email**, chọn trường trong hồ sơ khách hàng hợp nhất trình bày địa chỉ email của khách hàng.</span><span class="sxs-lookup"><span data-stu-id="2f888-124">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="2f888-125">Lặp lại các bước tương tự cho các trường **Tên** và **Họ**.</span><span class="sxs-lookup"><span data-stu-id="2f888-125">Repeat the same steps for \*\*First name" and **Last name** fields.</span></span>

1. <span data-ttu-id="2f888-126">Chọn phân khúc mà bạn muốn xuất.</span><span class="sxs-lookup"><span data-stu-id="2f888-126">Select the segments you want to export.</span></span> <span data-ttu-id="2f888-127">Bạn có thể xuất tổng cộng tối đa 1 triệu hồ sơ khách hàng sang Google Ads.</span><span class="sxs-lookup"><span data-stu-id="2f888-127">You can export up to 1 million customer profiles in total to Google Ads.</span></span>

1. <span data-ttu-id="2f888-128">Chọn **Lưu**.</span><span class="sxs-lookup"><span data-stu-id="2f888-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="2f888-129">Xuất dữ liệu</span><span class="sxs-lookup"><span data-stu-id="2f888-129">Export the data</span></span>

<span data-ttu-id="2f888-130">Bạn có thể [xuất dữ liệu theo nhu cầu](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="2f888-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="2f888-131">Mỗi lần [làm mới theo lịch](system.md#schedule-tab), tác vụ xuất cũng sẽ chạy.</span><span class="sxs-lookup"><span data-stu-id="2f888-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="2f888-132">Trong Google Ads, bạn hiện có thể tìm thấy các phân đoạn của mình trong [Đối tượng Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en/).</span><span class="sxs-lookup"><span data-stu-id="2f888-132">In Google Ads, you can now find your segments under [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en/).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="2f888-133">Các giới hạn đã biết</span><span class="sxs-lookup"><span data-stu-id="2f888-133">Known limitations</span></span>

- <span data-ttu-id="2f888-134">Lên đến 1 triệu hồ sơ mỗi lần xuất sang Google Ads.</span><span class="sxs-lookup"><span data-stu-id="2f888-134">Up to 1 million profiles per export to Google Ads.</span></span>
- <span data-ttu-id="2f888-135">Việc xuất sang Google Ads bị giới hạn ở các phân đoạn.</span><span class="sxs-lookup"><span data-stu-id="2f888-135">Exporting to Google Ads is limited to segments.</span></span>
- <span data-ttu-id="2f888-136">Việc xuất các phân đoạn với tổng số 1 triệu hồ sơ có thể mất đến 5 phút vì những hạn chế từ phía nhà cung cấp.</span><span class="sxs-lookup"><span data-stu-id="2f888-136">Exporting segments with a total of 1 million profiles can take up to 5 minutes because of limitations on the provider side.</span></span> 
- <span data-ttu-id="2f888-137">Quá trình so khớp trong Google Ads có thể mất đến 48 giờ.</span><span class="sxs-lookup"><span data-stu-id="2f888-137">The matching in Google Ads can take up to 48 hours.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="2f888-138">Quyền riêng tư về dữ liệu và tuân thủ</span><span class="sxs-lookup"><span data-stu-id="2f888-138">Data privacy and compliance</span></span>

<span data-ttu-id="2f888-139">Khi bật Dynamics 365 Customer Insights để truyền dữ liệu tới Google Ads, bạn cho phép chuyển dữ liệu ra bên ngoài ranh giới tuân thủ cho Dynamics 365 Customer Insights, bao gồm dữ liệu nhạy cảm tiềm ẩn như Dữ liệu cá nhân.</span><span class="sxs-lookup"><span data-stu-id="2f888-139">When you enable Dynamics 365 Customer Insights to transmit data to Google Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="2f888-140">Microsoft sẽ chuyển những dữ liệu đó theo chỉ dẫn của bạn, nhưng bạn có trách nhiệm đảm bảo rằng Google Ads đáp ứng mọi nghĩa vụ về quyền riêng tư hoặc bảo mật mà bạn có thể có.</span><span class="sxs-lookup"><span data-stu-id="2f888-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Google Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="2f888-141">Để biết thêm thông tin, hãy xem [Tuyên bố về Quyền riêng tư của Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="2f888-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="2f888-142">Quản trị viên Dynamics 365 Customer Insights của bạn có thể xóa đích xuất này bất cứ lúc nào để ngừng sử dụng chức năng này.</span><span class="sxs-lookup"><span data-stu-id="2f888-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]