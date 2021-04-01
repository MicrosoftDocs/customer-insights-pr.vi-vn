---
title: Xuất dữ liệu Customer Insights sang Autopilot
description: Tìm hiểu cách định cấu hình kết nối với Autopilot.
ms.date: 12/08/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d039c4afd84eaad942d214d4e6fb8ef7b1ec72a
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596157"
---
# <a name="connector-for-autopilot-preview"></a><span data-ttu-id="fc5ea-103">Trình kết nối cho Autopilot (bản xem trước)</span><span class="sxs-lookup"><span data-stu-id="fc5ea-103">Connector for Autopilot (preview)</span></span>

<span data-ttu-id="fc5ea-104">Xuất phân đoạn hồ sơ khách hàng hợp nhất sang Autopilot và sử dụng chúng cho các chiến dịch và tiếp thị qua email trong Autopilot.</span><span class="sxs-lookup"><span data-stu-id="fc5ea-104">Export segments of unified customer profiles to Autopilot and use them for email marketing in Autopilot.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="fc5ea-105">Điều kiện tiên quyết</span><span class="sxs-lookup"><span data-stu-id="fc5ea-105">Prerequisites</span></span>

-   <span data-ttu-id="fc5ea-106">Bạn có một [Tài khoản Autopilot](https://www.autopilothq.com/) và thông tin đăng nhập quản trị viên tương ứng.</span><span class="sxs-lookup"><span data-stu-id="fc5ea-106">You have an [Autopilot account](https://www.autopilothq.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="fc5ea-107">Bạn có [các phân đoạn được định cấu hình](segments.md) trong thông tin chi tiết về đối tượng.</span><span class="sxs-lookup"><span data-stu-id="fc5ea-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="fc5ea-108">Hồ sơ khách hàng hợp nhất trong các phân đoạn đã xuất chứa các trường đại diện cho địa chỉ email.</span><span class="sxs-lookup"><span data-stu-id="fc5ea-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-autopilot"></a><span data-ttu-id="fc5ea-109">Kết nối với AutoPilot</span><span class="sxs-lookup"><span data-stu-id="fc5ea-109">Connect to Autopilot</span></span>

1. <span data-ttu-id="fc5ea-110">Đi tới **Quản trị viên** > **Đích xuất**.</span><span class="sxs-lookup"><span data-stu-id="fc5ea-110">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="fc5ea-111">Trong **Autopilot**, chọn **Thiết lập**.</span><span class="sxs-lookup"><span data-stu-id="fc5ea-111">Under **Autopilot**, select **Set up**.</span></span>

1. <span data-ttu-id="fc5ea-112">Trong trường **Tên hiển thị**, hãy đặt cho đích xuất một cái tên dễ nhận biết.</span><span class="sxs-lookup"><span data-stu-id="fc5ea-112">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/export-autopilot.PNG" alt-text="Ngăn cấu hình cho kết nối Autopilot.":::

1. <span data-ttu-id="fc5ea-114">Nhập **Khóa API Autopilot** [Khóa API Autopilot](https://autopilot.docs.apiary.io/#).</span><span class="sxs-lookup"><span data-stu-id="fc5ea-114">Enter your **Autopilot API key** [Autopilot API key](https://autopilot.docs.apiary.io/#).</span></span>

1. <span data-ttu-id="fc5ea-115">Chọn **Tôi đồng ý** để xác nhận **Quyền riêng tư về dữ liệu và sự tuân thủ**.</span><span class="sxs-lookup"><span data-stu-id="fc5ea-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="fc5ea-116">Chọn **Kết nối** để khởi tạo kết nối với Autopilot.</span><span class="sxs-lookup"><span data-stu-id="fc5ea-116">Select **Connect** to initialize the connection to Autopilot.</span></span>

1. <span data-ttu-id="fc5ea-117">Chọn **Thêm chính bạn là người dùng xuất** và cung cấp thông tin xác thực Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="fc5ea-117">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="fc5ea-118">Chọn **Tiếp** để định cấu hình xuất.</span><span class="sxs-lookup"><span data-stu-id="fc5ea-118">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="fc5ea-119">Đặt cấu hình trình kết nối</span><span class="sxs-lookup"><span data-stu-id="fc5ea-119">Configure the connector</span></span>

1. <span data-ttu-id="fc5ea-120">Trong phần **So khớp dữ liệu**, trong trường **Email**, chọn trường trong hồ sơ khách hàng hợp nhất trình bày địa chỉ email của khách hàng.</span><span class="sxs-lookup"><span data-stu-id="fc5ea-120">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="fc5ea-121">Lặp lại các bước tương tự cho các trường tùy chọn khác như **Tên**, **Họ**.</span><span class="sxs-lookup"><span data-stu-id="fc5ea-121">Repeat the same steps for other optional fields such as **First name**, **Last name**.</span></span>

1. <span data-ttu-id="fc5ea-122">Chọn phân khúc mà bạn muốn xuất.</span><span class="sxs-lookup"><span data-stu-id="fc5ea-122">Select the segments you want to export.</span></span> <span data-ttu-id="fc5ea-123">Chúng tôi **khuyên bạn không nên xuất tổng cộng hơn 100.000 hồ sơ khách hàng** tới Autopilot.</span><span class="sxs-lookup"><span data-stu-id="fc5ea-123">We strongly **recommend to not export more than 100'000 customer profiles in total** to Autopilot.</span></span> 

1. <span data-ttu-id="fc5ea-124">Chọn **Lưu**.</span><span class="sxs-lookup"><span data-stu-id="fc5ea-124">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="fc5ea-125">Xuất dữ liệu</span><span class="sxs-lookup"><span data-stu-id="fc5ea-125">Export the data</span></span>

<span data-ttu-id="fc5ea-126">Bạn có thể [xuất dữ liệu theo nhu cầu](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="fc5ea-126">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="fc5ea-127">Mỗi lần [làm mới theo lịch](system.md#schedule-tab), tác vụ xuất cũng sẽ chạy.</span><span class="sxs-lookup"><span data-stu-id="fc5ea-127">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="fc5ea-128">Các giới hạn đã biết</span><span class="sxs-lookup"><span data-stu-id="fc5ea-128">Known limitations</span></span>

- <span data-ttu-id="fc5ea-129">Bạn có thể xuất tổng cộng tối đa 100.000 hồ sơ khách hàng sang Autopilot.</span><span class="sxs-lookup"><span data-stu-id="fc5ea-129">You can export up to 100'000 profiles in total to Autopilot.</span></span>
- <span data-ttu-id="fc5ea-130">Việc xuất sang Autopilot bị giới hạn ở các phân đoạn.</span><span class="sxs-lookup"><span data-stu-id="fc5ea-130">Exporting to Autopilot is limited to segments.</span></span>
- <span data-ttu-id="fc5ea-131">Có thể mất tới vài giờ để hoàn thành việc xuất lên đến 100.000 hồ sơ sang Autopilot.</span><span class="sxs-lookup"><span data-stu-id="fc5ea-131">Exporting up to 100'000 profiles to Autopilot can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="fc5ea-132">Số lượng hồ sơ mà bạn có thể xuất sang Autopilot phụ thuộc vào giới hạn đối với hợp đồng của bạn với Autopilot.</span><span class="sxs-lookup"><span data-stu-id="fc5ea-132">The number of profiles that you can export to Autopilot is dependent and limited on your contract with Autopilot.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="fc5ea-133">Quyền riêng tư về dữ liệu và sự tuân thủ</span><span class="sxs-lookup"><span data-stu-id="fc5ea-133">Data privacy and compliance</span></span>

<span data-ttu-id="fc5ea-134">Khi bật Dynamics 365 Customer Insights để truyền dữ liệu tới Autopilot, bạn cho phép chuyển dữ liệu ra bên ngoài ranh giới tuân thủ cho Dynamics 365 Customer Insights, bao gồm dữ liệu nhạy cảm tiềm ẩn như Dữ liệu cá nhân.</span><span class="sxs-lookup"><span data-stu-id="fc5ea-134">When you enable Dynamics 365 Customer Insights to transmit data to Autopilot, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="fc5ea-135">Microsoft sẽ chuyển những dữ liệu đó theo chỉ dẫn của bạn, nhưng bạn có trách nhiệm đảm bảo rằng Autopilot đáp ứng mọi nghĩa vụ về quyền riêng tư hoặc bảo mật mà bạn có thể có.</span><span class="sxs-lookup"><span data-stu-id="fc5ea-135">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Autopilot meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="fc5ea-136">Để biết thêm thông tin, hãy xem [Tuyên bố về Quyền riêng tư của Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="fc5ea-136">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="fc5ea-137">Quản trị viên Dynamics 365 Customer Insights của bạn có thể xóa đích xuất này bất cứ lúc nào để ngừng sử dụng chức năng này.</span><span class="sxs-lookup"><span data-stu-id="fc5ea-137">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]