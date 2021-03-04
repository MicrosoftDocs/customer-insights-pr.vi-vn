---
title: Tăng cường hồ sơ công ty bằng chức năng tăng cường của bên thứ ba Leadspace
description: Thông tin chung về tăng cường của bên thứ ba Leadspace.
ms.date: 11/24/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 12eed91a7ca4ef7fde0d53cca4a1dfd398b4634f
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269448"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="36836-103">Làm phong phú hồ sơ công ty bằng Leadspace (xem trước)</span><span class="sxs-lookup"><span data-stu-id="36836-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="36836-104">Leadspace là công ty khoa học dữ liệu cung cấp Nền tảng dữ liệu khách hàng B2B.</span><span class="sxs-lookup"><span data-stu-id="36836-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="36836-105">Nó cho phép khách hàng có hồ sơ khách hàng hợp nhất cho các công ty để làm phong phú dữ liệu của họ.</span><span class="sxs-lookup"><span data-stu-id="36836-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="36836-106">Tăng cường bao gồm các thuộc tính bổ sung như kích cỡ công ty, vị trí, ngành và các thông tin khác.</span><span class="sxs-lookup"><span data-stu-id="36836-106">Enrichments include additional attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="36836-107">Điều kiện tiên quyết</span><span class="sxs-lookup"><span data-stu-id="36836-107">Prerequisites</span></span>

<span data-ttu-id="36836-108">Để đặt cấu hình Leadspace, phải đáp ứng các điều kiện tiên quyết sau đây:</span><span class="sxs-lookup"><span data-stu-id="36836-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="36836-109">Bạn có giấy phép Leadspace hiện hoạt và "khóa vĩnh viễn" (được gọi là **Mã thông báo Leadspace**).</span><span class="sxs-lookup"><span data-stu-id="36836-109">You have an active Leadspace license and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="36836-110">Liên hệ trực tiếp với [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) để biết chi tiết về sản phẩm của họ.</span><span class="sxs-lookup"><span data-stu-id="36836-110">Contact directly [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) for details about their product.</span></span>
- <span data-ttu-id="36836-111">Bạn có quyền [Quản trị viên](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="36836-111">You have [Administrator](permissions.md#administrator) permissions.</span></span>
- <span data-ttu-id="36836-112">Bạn có [hồ sơ khách hàng hợp nhất](customer-profiles.md) cho các công ty.</span><span class="sxs-lookup"><span data-stu-id="36836-112">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>

## <a name="configuration"></a><span data-ttu-id="36836-113">Cấu hình</span><span class="sxs-lookup"><span data-stu-id="36836-113">Configuration</span></span>

1. <span data-ttu-id="36836-114">Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Dữ liệu** > **Tăng cường**.</span><span class="sxs-lookup"><span data-stu-id="36836-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="36836-115">Chọn **Tăng cường dữ liệu của tôi** trên ngăn xếp Leadspace.</span><span class="sxs-lookup"><span data-stu-id="36836-115">Select **Enrich my data** on the Leadspace tile.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="Ảnh chụp màn hình của ngăn xếp Leadspace.":::

1. <span data-ttu-id="36836-117">Chọn **Bắt đầu** và sau đó nhập một **Mã thông báo Leadspace** hiện hoạt (khóa vĩnh viễn).</span><span class="sxs-lookup"><span data-stu-id="36836-117">Select **Get Started** and then enter an active **Leadspace token** (perpetual key).</span></span> <span data-ttu-id="36836-118">Xem lại và đồng ý với **Quyền riêng tư và tuân thủ dữ liệu** bằng cách đánh dấu ô **Tôi đồng ý**.</span><span class="sxs-lookup"><span data-stu-id="36836-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="36836-119">Xác nhận cả hai đầu vào bằng cách chọn **Kết nối với Leadspace**.</span><span class="sxs-lookup"><span data-stu-id="36836-119">Confirm both inputs by selecting **Connect to Leadspace**.</span></span>

1. <span data-ttu-id="36836-120">Chọn **Ánh xạ dữ liệu** và chọn tập dữ liệu bạn muốn làm phong phú bằng dữ liệu công ty từ Leadspace.</span><span class="sxs-lookup"><span data-stu-id="36836-120">Select **Map data** and choose the data set you want to enrich with company data from Leadspace.</span></span> <span data-ttu-id="36836-121">Bạn có thể chọn thực thể *khách hàng* để làm phong phú tất cả hồ sơ khách hàng của bạn hoặc chọn một thực thể phân khúc để chỉ làm phong phú thêm hồ sơ khách hàng có trong phân khúc đó.</span><span class="sxs-lookup"><span data-stu-id="36836-121">You can select the *Customer* entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

   :::image type="content" source="media/enrichment-leadspace-select-segment.png" alt-text="Chọn giữa hồ sơ khách hàng và làm phong phú phân khúc.":::

1. <span data-ttu-id="36836-123">Nhấp vào **Tiếp theo** và xác định trường trong hồ sơ hợp nhất sẽ được dùng để tìm kiếm dữ liệu công ty phù hợp từ Leadspace.</span><span class="sxs-lookup"><span data-stu-id="36836-123">Click **Next** and define which fields from your unified profiles should be used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="36836-124">Trường **Tên công ty** là bắt buộc.</span><span class="sxs-lookup"><span data-stu-id="36836-124">The **Name of company** field is required.</span></span> <span data-ttu-id="36836-125">Để có độ chính xác so khớp cao hơn, có thể thêm tối đa 2 trường khác, **Trang web công ty** và **Vị trí công ty**.</span><span class="sxs-lookup"><span data-stu-id="36836-125">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Ngăn ánh xạ trường Leadspace.":::
   
1. <span data-ttu-id="36836-127">Chọn **Áp dụng** để hoàn thành ánh xạ trường.</span><span class="sxs-lookup"><span data-stu-id="36836-127">Select **Apply** to complete the field mapping.</span></span>

1. <span data-ttu-id="36836-128">Chọn **Chạy** để làm phong phú hồ sơ công ty.</span><span class="sxs-lookup"><span data-stu-id="36836-128">Select **Run** to enrich the company profiles.</span></span> <span data-ttu-id="36836-129">Thời gian tăng cường phụ thuộc vào số lượng hồ sơ khách hàng hợp nhất.</span><span class="sxs-lookup"><span data-stu-id="36836-129">How long an enrichment takes depends on the number of unified customer profiles.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="36836-130">Kết quả làm phong phú</span><span class="sxs-lookup"><span data-stu-id="36836-130">Enrichment results</span></span>

<span data-ttu-id="36836-131">Sau khi làm mới hồ sơ phong phú, bạn có thể xem lại dữ liệu công ty được làm mới gần đây trong phần [Nội dung phong phú của tôi](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="36836-131">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="36836-132">Bạn có thể tìm thấy thời điểm cập nhật gần đây nhất và số lượng hồ sơ phong phú.</span><span class="sxs-lookup"><span data-stu-id="36836-132">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="36836-133">Bạn có thể truy cập dạng xem chi tiết của từng hồ sơ được làm phong phú bằng cách chọn **Xem dữ liệu được làm phong phú**.</span><span class="sxs-lookup"><span data-stu-id="36836-133">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="36836-134">Để biết thêm thông tin, hãy xem [API Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span><span class="sxs-lookup"><span data-stu-id="36836-134">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="36836-135">Các bước tiếp theo</span><span class="sxs-lookup"><span data-stu-id="36836-135">Next steps</span></span>

<span data-ttu-id="36836-136">Xây dựng dựa trên dữ liệu khách hàng phong phú của bạn.</span><span class="sxs-lookup"><span data-stu-id="36836-136">Build on top of your enriched customer data.</span></span> <span data-ttu-id="36836-137">Tạo [phân khúc](segments.md), [biện pháp](measures.md) và [xuất dữ liệu](export-destinations.md) để cung cấp trải nghiệm cá nhân cho khách hàng của bạn.</span><span class="sxs-lookup"><span data-stu-id="36836-137">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="36836-138">Quyền riêng tư về dữ liệu và tuân thủ</span><span class="sxs-lookup"><span data-stu-id="36836-138">Data privacy and compliance</span></span>

<span data-ttu-id="36836-139">Khi bật Dynamics 365 Customer Insights để truyền dữ liệu tới Leadspace, bạn cho phép chuyển dữ liệu ra bên ngoài ranh giới tuân thủ cho Dynamics 365 Customer Insights, bao gồm dữ liệu nhạy cảm tiềm ẩn như Dữ liệu cá nhân.</span><span class="sxs-lookup"><span data-stu-id="36836-139">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="36836-140">Microsoft sẽ chuyển những dữ liệu đó theo chỉ dẫn của bạn, nhưng bạn có trách nhiệm đảm bảo rằng Leadspace đáp ứng mọi nghĩa vụ về quyền riêng tư hoặc bảo mật mà bạn có thể có.</span><span class="sxs-lookup"><span data-stu-id="36836-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="36836-141">Để biết thêm thông tin, hãy xem [Tuyên bố về Quyền riêng tư của Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="36836-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="36836-142">Quản trị viên Dynamics 365 Customer Insights của bạn có thể xóa tính năng tăng cường này bất kỳ lúc nào để ngừng sử dụng chức năng này.</span><span class="sxs-lookup"><span data-stu-id="36836-142">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]