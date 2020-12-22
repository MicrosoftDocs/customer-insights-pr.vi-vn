---
title: Tăng cường hồ sơ công ty bằng chức năng tăng cường của bên thứ ba Leadspace
description: Thông tin chung về tăng cường của bên thứ ba Leadspace.
ms.date: 11/24/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 1b5c6e46e8e424df83e855d81fc4dd7ecb394e3c
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668749"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="5196e-103">Làm phong phú hồ sơ công ty bằng Leadspace (xem trước)</span><span class="sxs-lookup"><span data-stu-id="5196e-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="5196e-104">Leadspace là công ty khoa học dữ liệu cung cấp Nền tảng dữ liệu khách hàng B2B.</span><span class="sxs-lookup"><span data-stu-id="5196e-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="5196e-105">Nó cho phép khách hàng có hồ sơ khách hàng hợp nhất cho các công ty để làm phong phú dữ liệu của họ.</span><span class="sxs-lookup"><span data-stu-id="5196e-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="5196e-106">Tăng cường bao gồm các thuộc tính bổ sung như kích cỡ công ty, vị trí, ngành và các thông tin khác.</span><span class="sxs-lookup"><span data-stu-id="5196e-106">Enrichments include additional attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5196e-107">Điều kiện tiên quyết</span><span class="sxs-lookup"><span data-stu-id="5196e-107">Prerequisites</span></span>

<span data-ttu-id="5196e-108">Để đặt cấu hình Leadspace, phải đáp ứng các điều kiện tiên quyết sau đây:</span><span class="sxs-lookup"><span data-stu-id="5196e-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="5196e-109">Bạn có giấy phép Leadspace hiện hoạt và "khóa vĩnh viễn" (được gọi là **Mã thông báo Leadspace**).</span><span class="sxs-lookup"><span data-stu-id="5196e-109">You have an active Leadspace license and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="5196e-110">Liên hệ trực tiếp với [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) để biết chi tiết về sản phẩm của họ.</span><span class="sxs-lookup"><span data-stu-id="5196e-110">Contact directly [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) for details about their product.</span></span>
- <span data-ttu-id="5196e-111">Bạn có quyền [Quản trị viên](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="5196e-111">You have [Administrator](permissions.md#administrator) permissions.</span></span>
- <span data-ttu-id="5196e-112">Bạn có [hồ sơ khách hàng hợp nhất](customer-profiles.md) cho các công ty.</span><span class="sxs-lookup"><span data-stu-id="5196e-112">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>

## <a name="configuration"></a><span data-ttu-id="5196e-113">Cấu hình</span><span class="sxs-lookup"><span data-stu-id="5196e-113">Configuration</span></span>

1. <span data-ttu-id="5196e-114">Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Dữ liệu** > **Tăng cường**.</span><span class="sxs-lookup"><span data-stu-id="5196e-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="5196e-115">Chọn **Tăng cường dữ liệu của tôi** trên ngăn xếp Leadspace.</span><span class="sxs-lookup"><span data-stu-id="5196e-115">Select **Enrich my data** on the Leadspace tile.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="Ảnh chụp màn hình của ngăn xếp Leadspace.":::

1. <span data-ttu-id="5196e-117">Chọn **Bắt đầu** và sau đó nhập một **Mã thông báo Leadspace** hiện hoạt (khóa vĩnh viễn).</span><span class="sxs-lookup"><span data-stu-id="5196e-117">Select **Get Started** and then enter an active **Leadspace token** (perpetual key).</span></span> <span data-ttu-id="5196e-118">Xem lại và đồng ý với **Quyền riêng tư và tuân thủ dữ liệu** bằng cách đánh dấu ô **Tôi đồng ý**.</span><span class="sxs-lookup"><span data-stu-id="5196e-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="5196e-119">Xác nhận cả hai đầu vào bằng cách chọn **Kết nối với Leadspace**.</span><span class="sxs-lookup"><span data-stu-id="5196e-119">Confirm both inputs by selecting **Connect to Leadspace**.</span></span>

1. <span data-ttu-id="5196e-120">Chọn **Dữ liệu bản đồ** và xác định trường nào từ hồ sơ hợp nhất của bạn sẽ được sử dụng để tìm kiếm dữ liệu công ty phù hợp từ Leadspace.</span><span class="sxs-lookup"><span data-stu-id="5196e-120">Select **Map data** and define which fields from your unified profiles should be used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="5196e-121">Trường **Tên công ty** là bắt buộc.</span><span class="sxs-lookup"><span data-stu-id="5196e-121">The **Name of company** field is required.</span></span> <span data-ttu-id="5196e-122">Để có độ chính xác so khớp cao hơn, có thể thêm tối đa 2 trường khác, **Trang web công ty** và **Vị trí công ty**.</span><span class="sxs-lookup"><span data-stu-id="5196e-122">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Ngăn ánh xạ trường Leadspace.":::
   
1. <span data-ttu-id="5196e-124">Chọn **Áp dụng** để hoàn thành ánh xạ trường.</span><span class="sxs-lookup"><span data-stu-id="5196e-124">Select **Apply** to complete the field mapping.</span></span>

1. <span data-ttu-id="5196e-125">Chọn **Chạy** để làm phong phú hồ sơ công ty.</span><span class="sxs-lookup"><span data-stu-id="5196e-125">Select **Run** to enrich the company profiles.</span></span> <span data-ttu-id="5196e-126">Thời gian tăng cường phụ thuộc vào số lượng hồ sơ khách hàng hợp nhất.</span><span class="sxs-lookup"><span data-stu-id="5196e-126">How long an enrichment takes depends on the number of unified customer profiles.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="5196e-127">Kết quả làm phong phú</span><span class="sxs-lookup"><span data-stu-id="5196e-127">Enrichment results</span></span>

<span data-ttu-id="5196e-128">Sau khi làm mới hồ sơ phong phú, bạn có thể xem lại dữ liệu công ty được làm mới gần đây trong phần [Nội dung phong phú của tôi](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="5196e-128">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="5196e-129">Bạn có thể tìm thấy thời điểm cập nhật gần đây nhất và số lượng hồ sơ phong phú.</span><span class="sxs-lookup"><span data-stu-id="5196e-129">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="5196e-130">Bạn có thể truy cập dạng xem chi tiết của từng hồ sơ được làm phong phú bằng cách chọn **Xem dữ liệu được làm phong phú**.</span><span class="sxs-lookup"><span data-stu-id="5196e-130">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="5196e-131">Để biết thêm thông tin, hãy xem [API Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span><span class="sxs-lookup"><span data-stu-id="5196e-131">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="5196e-132">Các bước tiếp theo</span><span class="sxs-lookup"><span data-stu-id="5196e-132">Next steps</span></span>

<span data-ttu-id="5196e-133">Xây dựng dựa trên dữ liệu khách hàng phong phú của bạn.</span><span class="sxs-lookup"><span data-stu-id="5196e-133">Build on top of your enriched customer data.</span></span> <span data-ttu-id="5196e-134">Tạo [phân khúc](segments.md), [biện pháp](measures.md) và [xuất dữ liệu](export-destinations.md) để cung cấp trải nghiệm cá nhân cho khách hàng của bạn.</span><span class="sxs-lookup"><span data-stu-id="5196e-134">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="5196e-135">Quyền riêng tư về dữ liệu và tuân thủ</span><span class="sxs-lookup"><span data-stu-id="5196e-135">Data privacy and compliance</span></span>

<span data-ttu-id="5196e-136">Khi bật Dynamics 365 Customer Insights để truyền dữ liệu tới Leadspace, bạn cho phép chuyển dữ liệu ra bên ngoài ranh giới tuân thủ cho Dynamics 365 Customer Insights, bao gồm dữ liệu nhạy cảm tiềm ẩn như Dữ liệu cá nhân.</span><span class="sxs-lookup"><span data-stu-id="5196e-136">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="5196e-137">Microsoft sẽ chuyển những dữ liệu đó theo chỉ dẫn của bạn, nhưng bạn có trách nhiệm đảm bảo rằng Leadspace đáp ứng mọi nghĩa vụ về quyền riêng tư hoặc bảo mật mà bạn có thể có.</span><span class="sxs-lookup"><span data-stu-id="5196e-137">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="5196e-138">Để biết thêm thông tin, hãy xem [Tuyên bố về Quyền riêng tư của Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="5196e-138">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="5196e-139">Quản trị viên Dynamics 365 Customer Insights của bạn có thể xóa tính năng tăng cường này bất kỳ lúc nào để ngừng sử dụng chức năng này.</span><span class="sxs-lookup"><span data-stu-id="5196e-139">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>