---
title: Xuất dữ liệu Customer Insights sang SendGrid
description: Tìm hiểu cách định cấu hình kết nối với SendGrid.
ms.date: 12/08/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f16d69deb2a0b48270ed04f9b72f03056f20b619
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268758"
---
# <a name="connector-for-sendgrid-preview"></a><span data-ttu-id="cc94f-103">Trình kết nối cho SendGrid (bản xem trước)</span><span class="sxs-lookup"><span data-stu-id="cc94f-103">Connector for SendGrid (preview)</span></span>

<span data-ttu-id="cc94f-104">Xuất phân đoạn hồ sơ khách hàng hợp nhất sang danh sách liên hệ SendGrid và sử dụng chúng cho các chiến dịch và tiếp thị qua email trong SendGrid.</span><span class="sxs-lookup"><span data-stu-id="cc94f-104">Export segments of unified customer profiles to SendGrid contact lists and use them for campaigns and email marketing in SendGrid.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="cc94f-105">Điều kiện tiên quyết</span><span class="sxs-lookup"><span data-stu-id="cc94f-105">Prerequisites</span></span>

-   <span data-ttu-id="cc94f-106">Bạn có một [Tài khoản SendGrid](https://sendgrid.com/) và thông tin đăng nhập quản trị viên tương ứng.</span><span class="sxs-lookup"><span data-stu-id="cc94f-106">You have a [SendGrid account](https://sendgrid.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="cc94f-107">Có danh sách liên hệ hiện có trong SendGrid và các ID tương ứng.</span><span class="sxs-lookup"><span data-stu-id="cc94f-107">There are existing contact lists in SendGrid and the corresponding IDs.</span></span> <span data-ttu-id="cc94f-108">Để biết thêm thông tin, hãy xem [SendGrid - Quản lý liên hệ](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span><span class="sxs-lookup"><span data-stu-id="cc94f-108">For more information, see [SendGrid - Manage contacts](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span></span>
-   <span data-ttu-id="cc94f-109">Bạn có [các phân đoạn được định cấu hình](segments.md) trong thông tin chi tiết về đối tượng.</span><span class="sxs-lookup"><span data-stu-id="cc94f-109">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="cc94f-110">Hồ sơ khách hàng hợp nhất trong các phân đoạn đã xuất chứa các trường đại diện cho địa chỉ email.</span><span class="sxs-lookup"><span data-stu-id="cc94f-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-sendgrid"></a><span data-ttu-id="cc94f-111">Kết nối với SendGrid</span><span class="sxs-lookup"><span data-stu-id="cc94f-111">Connect to SendGrid</span></span>

1. <span data-ttu-id="cc94f-112">Đi tới **Quản trị viên** > **Đích xuất**.</span><span class="sxs-lookup"><span data-stu-id="cc94f-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="cc94f-113">Trong **SendGrid**, chọn **Thiết lập**.</span><span class="sxs-lookup"><span data-stu-id="cc94f-113">Under **SendGrid**, select **Set up**.</span></span>

1. <span data-ttu-id="cc94f-114">Trong trường **Tên hiển thị**, hãy đặt cho đích xuất một cái tên dễ nhận biết.</span><span class="sxs-lookup"><span data-stu-id="cc94f-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/export-sendgrid.PNG" alt-text="Ngăn cấu hình xuất SendGrid.":::

1. <span data-ttu-id="cc94f-116">Nhập **Khóa API SendGrid** [Khóa API SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span><span class="sxs-lookup"><span data-stu-id="cc94f-116">Enter your **SendGrid API key** [SendGrid API key](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span></span>

1. <span data-ttu-id="cc94f-117">Nhập **[ID danh sách SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span><span class="sxs-lookup"><span data-stu-id="cc94f-117">Enter your **[SendGrid list ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span></span>

1. <span data-ttu-id="cc94f-118">Chọn **Tôi đồng ý** để xác nhận **Quyền riêng tư về dữ liệu và sự tuân thủ**.</span><span class="sxs-lookup"><span data-stu-id="cc94f-118">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="cc94f-119">Chọn **Kết nối** để khởi tạo kết nối với SendGrid.</span><span class="sxs-lookup"><span data-stu-id="cc94f-119">Select **Connect** to initialize the connection to SendGrid.</span></span>

1. <span data-ttu-id="cc94f-120">Chọn **Thêm chính bạn là người dùng xuất** và cung cấp thông tin xác thực Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="cc94f-120">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="cc94f-121">Chọn **Tiếp** để định cấu hình xuất.</span><span class="sxs-lookup"><span data-stu-id="cc94f-121">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="cc94f-122">Đặt cấu hình trình kết nối</span><span class="sxs-lookup"><span data-stu-id="cc94f-122">Configure the connector</span></span>

1. <span data-ttu-id="cc94f-123">Trong phần **So khớp dữ liệu**, trong trường **Email**, chọn trường trong hồ sơ khách hàng hợp nhất trình bày địa chỉ email của khách hàng.</span><span class="sxs-lookup"><span data-stu-id="cc94f-123">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="cc94f-124">Lặp lại các bước tương tự cho các trường tùy chọn khác như **Tên**, **Họ**, **Quốc gia/Khu vực**, **Tiểu bang**, **Thành phố** và **Mã bưu điện**.</span><span class="sxs-lookup"><span data-stu-id="cc94f-124">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Country/Region**, **State**, **City**, and **Post code**.</span></span>

1. <span data-ttu-id="cc94f-125">Chọn phân khúc mà bạn muốn xuất.</span><span class="sxs-lookup"><span data-stu-id="cc94f-125">Select the segments you want to export.</span></span> <span data-ttu-id="cc94f-126">Chúng tôi **khuyên bạn không nên xuất tổng cộng hơn 100.000 hồ sơ khách hàng** tới SendGrid.</span><span class="sxs-lookup"><span data-stu-id="cc94f-126">We strongly **recommend to not export more than 100'000 customer profiles in total** to SendGrid.</span></span> 

1. <span data-ttu-id="cc94f-127">Chọn **Lưu**.</span><span class="sxs-lookup"><span data-stu-id="cc94f-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="cc94f-128">Xuất dữ liệu</span><span class="sxs-lookup"><span data-stu-id="cc94f-128">Export the data</span></span>

<span data-ttu-id="cc94f-129">Bạn có thể [xuất dữ liệu theo nhu cầu](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="cc94f-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="cc94f-130">Mỗi lần [làm mới theo lịch](system.md#schedule-tab), tác vụ xuất cũng sẽ chạy.</span><span class="sxs-lookup"><span data-stu-id="cc94f-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="cc94f-131">Các giới hạn đã biết</span><span class="sxs-lookup"><span data-stu-id="cc94f-131">Known limitations</span></span>

- <span data-ttu-id="cc94f-132">Tối đa 100.000 hồ sơ trên SendGrid.</span><span class="sxs-lookup"><span data-stu-id="cc94f-132">Up to 100'000 profiles in total to SendGrid.</span></span>
- <span data-ttu-id="cc94f-133">Việc xuất sang SendGrid bị giới hạn ở các phân đoạn.</span><span class="sxs-lookup"><span data-stu-id="cc94f-133">Exporting to SendGrid is limited to segments.</span></span>
- <span data-ttu-id="cc94f-134">Có thể mất tới vài giờ để hoàn thành việc xuất lên đến 100.000 hồ sơ sang SendGrid.</span><span class="sxs-lookup"><span data-stu-id="cc94f-134">Exporting up to 100'000 profiles to SendGrid can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="cc94f-135">Số lượng hồ sơ mà bạn có thể xuất sang SendGrid còn phụ thuộc vào giới hạn cho hợp đồng của bạn với SendGrid.</span><span class="sxs-lookup"><span data-stu-id="cc94f-135">The number of profiles that you can export to SendGrid is dependent and limited on your contract with SendGrid.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="cc94f-136">Quyền riêng tư về dữ liệu và sự tuân thủ</span><span class="sxs-lookup"><span data-stu-id="cc94f-136">Data privacy and compliance</span></span>

<span data-ttu-id="cc94f-137">Khi bật Dynamics 365 Customer Insights để truyền dữ liệu tới SendGrid, bạn cho phép chuyển dữ liệu ra bên ngoài ranh giới tuân thủ cho Dynamics 365 Customer Insights, bao gồm dữ liệu nhạy cảm tiềm ẩn như Dữ liệu cá nhân.</span><span class="sxs-lookup"><span data-stu-id="cc94f-137">When you enable Dynamics 365 Customer Insights to transmit data to SendGrid, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="cc94f-138">Microsoft sẽ chuyển những dữ liệu đó theo chỉ dẫn của bạn, nhưng bạn có trách nhiệm đảm bảo rằng SendGrid đáp ứng mọi nghĩa vụ về quyền riêng tư hoặc bảo mật mà bạn có thể có.</span><span class="sxs-lookup"><span data-stu-id="cc94f-138">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that SendGrid meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="cc94f-139">Để biết thêm thông tin, hãy xem [Tuyên bố về Quyền riêng tư của Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="cc94f-139">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="cc94f-140">Quản trị viên Dynamics 365 Customer Insights của bạn có thể xóa đích xuất này bất cứ lúc nào để ngừng sử dụng chức năng này.</span><span class="sxs-lookup"><span data-stu-id="cc94f-140">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]