---
title: Xuất dữ liệu Customer Insights sang Mailchimp
description: Tìm hiểu cách định cấu hình kết nối với Mailchimp.
ms.date: 10/26/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 9f86616731c3cc3d26370727103ea9c5d4288c8d
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598227"
---
# <a name="connector-for-mailchimp-preview"></a><span data-ttu-id="9594b-103">Trình kết nối cho Mailchimp (bản xem trước)</span><span class="sxs-lookup"><span data-stu-id="9594b-103">Connector for Mailchimp (preview)</span></span>

<span data-ttu-id="9594b-104">Xuất phân đoạn hồ sơ khách hàng hợp nhất sang Mailchimp để tạo bản tin và chiến dịch email.</span><span class="sxs-lookup"><span data-stu-id="9594b-104">Export segments of unified customer profiles to Mailchimp to create newsletters and email campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9594b-105">Điều kiện tiên quyết</span><span class="sxs-lookup"><span data-stu-id="9594b-105">Prerequisites</span></span>

-   <span data-ttu-id="9594b-106">Bạn có một [Tài khoản Mailchimp](https://mailchimp.com/) và thông tin đăng nhập quản trị viên tương ứng.</span><span class="sxs-lookup"><span data-stu-id="9594b-106">You have a [Mailchimp account](https://mailchimp.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="9594b-107">Có đối tượng hiện có trong Mailchimp và các ID tương ứng.</span><span class="sxs-lookup"><span data-stu-id="9594b-107">There are existing audiences in Mailchimp and the corresponding IDs.</span></span> <span data-ttu-id="9594b-108">Để biết thêm thông tin, hãy xem [Đối tượng Mailchimp](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="9594b-108">For more information, see [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>
-   <span data-ttu-id="9594b-109">Bạn có [các phân đoạn được định cấu hình](segments.md)</span><span class="sxs-lookup"><span data-stu-id="9594b-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="9594b-110">Hồ sơ khách hàng hợp nhất trong các phân đoạn đã xuất chứa các trường đại diện cho địa chỉ email.</span><span class="sxs-lookup"><span data-stu-id="9594b-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-mailchimp"></a><span data-ttu-id="9594b-111">Kết nối với MailChimp</span><span class="sxs-lookup"><span data-stu-id="9594b-111">Connect to Mailchimp</span></span>

1. <span data-ttu-id="9594b-112">Đi tới **Quản trị viên** > **Đích xuất**.</span><span class="sxs-lookup"><span data-stu-id="9594b-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="9594b-113">Trong **Mailchimp**, chọn **Thiết lập**.</span><span class="sxs-lookup"><span data-stu-id="9594b-113">Under **Mailchimp**, select **Set up**.</span></span>

1. <span data-ttu-id="9594b-114">Trong trường **Tên hiển thị**, hãy đặt cho đích xuất một cái tên dễ nhận biết.</span><span class="sxs-lookup"><span data-stu-id="9594b-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="9594b-115">Chọn **Tôi đồng ý** để xác nhận **Quyền riêng tư về dữ liệu và sự tuân thủ**.</span><span class="sxs-lookup"><span data-stu-id="9594b-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="9594b-116">Nhập **[ID đối tượng Mailchimp](https://mailchimp.com/help/find-audience-id/)** và chọn **Kết nối** để khởi tạo kết nối với Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="9594b-116">Enter your **[Mailchimp audience ID](https://mailchimp.com/help/find-audience-id/)** and select **Connect** to initialize the connection to Mailchimp.</span></span>

1. <span data-ttu-id="9594b-117">Chọn **Xác thực bằng Mailchimp** và cung cấp thông tin đăng nhập Mailchimp của bạn.</span><span class="sxs-lookup"><span data-stu-id="9594b-117">Select **Authenticate with Mailchimp** and provide your Mailchimp credentials.</span></span>

1. <span data-ttu-id="9594b-118">Chọn **Thêm chính bạn là người dùng xuất** và cung cấp thông tin xác thực Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="9594b-118">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-connect-mailchimp.png" alt-text="Xuất ảnh chụp màn hình cho kết nối Mailchimp":::

1. <span data-ttu-id="9594b-120">Chọn **Tiếp** để định cấu hình xuất.</span><span class="sxs-lookup"><span data-stu-id="9594b-120">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="9594b-121">Đặt cấu hình trình kết nối</span><span class="sxs-lookup"><span data-stu-id="9594b-121">Configure the connector</span></span>

1. <span data-ttu-id="9594b-122">Trong phần **So khớp dữ liệu**, trong trường **Email**, chọn trường trong hồ sơ khách hàng hợp nhất trình bày địa chỉ email của khách hàng.</span><span class="sxs-lookup"><span data-stu-id="9594b-122">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="9594b-123">Theo tùy chọn, bạn có thể xuất **Tên** và **Họ** dưới dạng trường bổ sung để tạo thêm email cá nhân hóa.</span><span class="sxs-lookup"><span data-stu-id="9594b-123">Optionally, you can export **First name** and **Last name** as additional fields to create more personalized emails.</span></span> <span data-ttu-id="9594b-124">Chọn **Thêm thuộc tính** để ánh xạ những trường này.</span><span class="sxs-lookup"><span data-stu-id="9594b-124">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="9594b-125">Chọn phân khúc mà bạn muốn xuất.</span><span class="sxs-lookup"><span data-stu-id="9594b-125">Select the segments you want to export.</span></span> <span data-ttu-id="9594b-126">Bạn có thể xuất tổng cộng tối đa 1 triệu hồ sơ khách hàng sang Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="9594b-126">You can export up to 1 million customer profiles in total to Mailchimp.</span></span>

   :::image type="content" source="media/export-segments-mailchimp.png" alt-text="Chọn các trường và phân đoạn để xuất sang Mailchimp":::

1. <span data-ttu-id="9594b-128">Chọn **Lưu**.</span><span class="sxs-lookup"><span data-stu-id="9594b-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="9594b-129">Xuất dữ liệu</span><span class="sxs-lookup"><span data-stu-id="9594b-129">Export the data</span></span>

<span data-ttu-id="9594b-130">Bạn có thể [xuất dữ liệu theo nhu cầu](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="9594b-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="9594b-131">Mỗi lần [làm mới theo lịch](system.md#schedule-tab), tác vụ xuất cũng sẽ chạy.</span><span class="sxs-lookup"><span data-stu-id="9594b-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="9594b-132">Trong Mailchimp, bạn hiện có thể tìm thấy các phân đoạn của mình trong [Đối tượng Mailchimp](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="9594b-132">In Mailchimp, you can now find your segments under [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="9594b-133">Các giới hạn đã biết</span><span class="sxs-lookup"><span data-stu-id="9594b-133">Known limitations</span></span>

- <span data-ttu-id="9594b-134">Lên đến 1 triệu hồ sơ mỗi lần xuất sang Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="9594b-134">Up to 1 million profiles per export to Mailchimp.</span></span>
- <span data-ttu-id="9594b-135">Việc xuất sang Mailchimp bị giới hạn ở các phân đoạn.</span><span class="sxs-lookup"><span data-stu-id="9594b-135">Exporting to Mailchimp is limited to segments.</span></span>
- <span data-ttu-id="9594b-136">Việc xuất các phân đoạn với tổng số 1 triệu hồ sơ có thể mất đến 3 giờ do những hạn chế từ phía nhà cung cấp.</span><span class="sxs-lookup"><span data-stu-id="9594b-136">Exporting segments with a total of 1 million profiles can take up to three hours due to limitations on the provider side.</span></span> 
- <span data-ttu-id="9594b-137">Số lượng hồ sơ mà bạn có thể xuất sang Mailchimp phụ thuộc và giới hạn vào hợp đồng của bạn với Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="9594b-137">The number of profiles that you can export to Mailchimp is dependent and limited on your contract with Mailchimp.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="9594b-138">Quyền riêng tư về dữ liệu và tuân thủ</span><span class="sxs-lookup"><span data-stu-id="9594b-138">Data privacy and compliance</span></span>

<span data-ttu-id="9594b-139">Khi bật Dynamics 365 Customer Insights để truyền dữ liệu tới Mailchimp, bạn cho phép chuyển dữ liệu ra bên ngoài ranh giới tuân thủ cho Dynamics 365 Customer Insights, bao gồm dữ liệu nhạy cảm tiềm ẩn như Dữ liệu cá nhân.</span><span class="sxs-lookup"><span data-stu-id="9594b-139">When you enable Dynamics 365 Customer Insights to transmit data to Mailchimp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="9594b-140">Microsoft sẽ chuyển những dữ liệu đó theo chỉ dẫn của bạn, nhưng bạn có trách nhiệm đảm bảo rằng Mailchimp đáp ứng mọi nghĩa vụ về quyền riêng tư hoặc bảo mật mà bạn có thể có.</span><span class="sxs-lookup"><span data-stu-id="9594b-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Mailchimp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="9594b-141">Để biết thêm thông tin, hãy xem [Tuyên bố về Quyền riêng tư của Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="9594b-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="9594b-142">Quản trị viên Dynamics 365 Customer Insights của bạn có thể xóa đích xuất này bất cứ lúc nào để ngừng sử dụng chức năng này.</span><span class="sxs-lookup"><span data-stu-id="9594b-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]