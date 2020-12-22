---
title: Tăng cường với HERE Technologies tăng cường của bên thứ ba
description: Thông tin chung về tăng cường của bên thứ ba HERE Technologies.
ms.date: 10/27/2020
ms.reviewer: jodahl
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7082fcfec099c3c9436b233c193be23625f6691a
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668704"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="e3e14-103">Tăng cường hồ sơ khách hàng với HERE Technologies (bản xem trước)</span><span class="sxs-lookup"><span data-stu-id="e3e14-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="e3e14-104">HERE Technologies là một công ty nền tảng vị trí cung cấp dữ liệu và dịch vụ tập trung vào vị trí.</span><span class="sxs-lookup"><span data-stu-id="e3e14-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="e3e14-105">Với các dịch vụ làm giàu dữ liệu của HERE Technologies, bạn có thể xây dựng kiến thức vị trí chính xác hơn về khách hàng của mình bằng cách chuẩn hóa địa chỉ, trích xuất vĩ độ và kinh độ, v.v.</span><span class="sxs-lookup"><span data-stu-id="e3e14-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e3e14-106">Điều kiện tiên quyết</span><span class="sxs-lookup"><span data-stu-id="e3e14-106">Prerequisites</span></span>

<span data-ttu-id="e3e14-107">Để định cấu hình tính năng tăng cường HERE Technologies, bạn phải đáp ứng các điều kiện tiên quyết sau:</span><span class="sxs-lookup"><span data-stu-id="e3e14-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="e3e14-108">Bạn có gói đăng ký HERE Technologies hoạt động.</span><span class="sxs-lookup"><span data-stu-id="e3e14-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="e3e14-109">Để nhận gói đăng ký, bạn có thể [đăng ký tại đây](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) hoặc [liên hệ trực tiếp với HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you).</span><span class="sxs-lookup"><span data-stu-id="e3e14-109">To get a subscription, you can [sign-up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="e3e14-110">Tìm hiểu thêm về tính năng Tăng cường vị trí HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="e3e14-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="e3e14-111">Bạn có khóa API HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="e3e14-111">You have the HERE Technologies API key.</span></span>

- <span data-ttu-id="e3e14-112">Bạn có quyền [Quản trị viên](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="e3e14-112">You have [Administrator](permissions.md#administrator) permissions.</span></span>

## <a name="configuration"></a><span data-ttu-id="e3e14-113">Cấu hình</span><span class="sxs-lookup"><span data-stu-id="e3e14-113">Configuration</span></span>

1. <span data-ttu-id="e3e14-114">Chuyển tới **Dữ liệu** > **Nội dung phong phú**.</span><span class="sxs-lookup"><span data-stu-id="e3e14-114">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="e3e14-115">Chọn **Tăng cường dữ liệu của tôi** trên lát HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="e3e14-115">Select **Enrich my data** on the HERE Technologies tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e3e14-116">![lát HERE Technologies](media/HERE-tile.png "lát HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="e3e14-116">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="e3e14-117">Nhập **khóa API HERE Technologies** hiện hoạt.</span><span class="sxs-lookup"><span data-stu-id="e3e14-117">Enter an active **HERE Technologies API key**.</span></span> <span data-ttu-id="e3e14-118">Xem lại và đồng ý với **Quyền riêng tư và tuân thủ dữ liệu** bằng cách đánh dấu ô **Tôi đồng ý**.</span><span class="sxs-lookup"><span data-stu-id="e3e14-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> 

1. <span data-ttu-id="e3e14-119">Xác nhận cả hai đầu vào bằng cách chọn **Kết nối với HERE**.</span><span class="sxs-lookup"><span data-stu-id="e3e14-119">Confirm both inputs by selecting **Connect to HERE**.</span></span>

1. <span data-ttu-id="e3e14-120">Chọn **Thêm dữ liệu** và chọn xem bạn có muốn ánh xạ các trường với địa chỉ chính và/hoặc phụ không.</span><span class="sxs-lookup"><span data-stu-id="e3e14-120">Select **Add data** and choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="e3e14-121">Bạn có thể chỉ định ánh xạ trường cho cả hai địa chỉ (ví dụ: địa chỉ nhà riêng và địa chỉ doanh nghiệp) và tăng cường hồ sơ cho cả hai địa chỉ một cách riêng biệt.</span><span class="sxs-lookup"><span data-stu-id="e3e14-121">You can specify a field mapping for both addresses (for example, a home and a business address) and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="e3e14-122">Chọn **Tiếp theo**.</span><span class="sxs-lookup"><span data-stu-id="e3e14-122">Select **Next**.</span></span>

1. <span data-ttu-id="e3e14-123">Xác định trường nào từ hồ sơ hợp nhất của bạn sẽ được sử dụng để tìm kiếm dữ liệu vị trí phù hợp từ HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="e3e14-123">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="e3e14-124">Các trường **Đường 1** và **Mã zip/bưu chính** là bắt buộc cho địa chỉ chính và/hoặc phụ đã chọn.</span><span class="sxs-lookup"><span data-stu-id="e3e14-124">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="e3e14-125">Để có độ chính xác so khớp cao hơn, có thể thêm nhiều trường khác.</span><span class="sxs-lookup"><span data-stu-id="e3e14-125">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e3e14-126">![Trang cấu hình tăng cường HERE Technologies](media/enrichment-HERE-configuration.png "Trang cấu hình tăng cường HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="e3e14-126">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="e3e14-127">Chọn **Áp dụng** để hoàn thành ánh xạ trường.</span><span class="sxs-lookup"><span data-stu-id="e3e14-127">Select **Apply** to complete the field mapping.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="e3e14-128">Kết quả làm phong phú</span><span class="sxs-lookup"><span data-stu-id="e3e14-128">Enrichment results</span></span>

<span data-ttu-id="e3e14-129">Để bắt đầu quá trình tăng cường, hãy chọn **Chạy** từ thanh lệnh.</span><span class="sxs-lookup"><span data-stu-id="e3e14-129">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="e3e14-130">Bạn cũng có thể để hệ thống chạy quá trình tăng cường tự động như một phần của [làm mới theo lịch trình](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="e3e14-130">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="e3e14-131">Thời gian xử lý sẽ phụ thuộc vào kích thước dữ liệu khách hàng của bạn và thời gian phản hồi API từ HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="e3e14-131">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="e3e14-132">Sau khi quá trình tăng cường hoàn tất, bạn có thể xem lại dữ liệu hồ sơ khách hàng mới được bổ sung trong **Nội dung tăng cường của tôi**.</span><span class="sxs-lookup"><span data-stu-id="e3e14-132">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="e3e14-133">Ngoài ra, bạn sẽ tìm thấy thời gian của lần cập nhật gần nhất và số lượng hồ sơ được tăng cường.</span><span class="sxs-lookup"><span data-stu-id="e3e14-133">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="e3e14-134">Bạn có thể truy cập dạng xem chi tiết của từng hồ sơ được làm phong phú bằng cách chọn **Xem dữ liệu được làm phong phú**.</span><span class="sxs-lookup"><span data-stu-id="e3e14-134">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e3e14-135">Các bước tiếp theo</span><span class="sxs-lookup"><span data-stu-id="e3e14-135">Next steps</span></span>

<span data-ttu-id="e3e14-136">Xây dựng dựa trên dữ liệu khách hàng phong phú của bạn.</span><span class="sxs-lookup"><span data-stu-id="e3e14-136">Build on top of your enriched customer data.</span></span> <span data-ttu-id="e3e14-137">Tạo [phân khúc](segments.md), [biện pháp](measures.md) và [xuất dữ liệu](export-destinations.md) để cung cấp trải nghiệm cá nhân cho khách hàng của bạn.</span><span class="sxs-lookup"><span data-stu-id="e3e14-137">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="e3e14-138">Quyền riêng tư về dữ liệu và tuân thủ</span><span class="sxs-lookup"><span data-stu-id="e3e14-138">Data privacy and compliance</span></span>

<span data-ttu-id="e3e14-139">Khi bật Dynamics 365 Customer Insights để truyền dữ liệu tới HERE Technologies, bạn cho phép chuyển dữ liệu ra bên ngoài ranh giới tuân thủ cho Dynamics 365 Customer Insights, bao gồm dữ liệu nhạy cảm tiềm ẩn như Dữ liệu cá nhân.</span><span class="sxs-lookup"><span data-stu-id="e3e14-139">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="e3e14-140">Microsoft sẽ chuyển những dữ liệu đó theo chỉ dẫn của bạn, nhưng bạn có trách nhiệm đảm bảo rằng HERE Technologies đáp ứng mọi nghĩa vụ về quyền riêng tư hoặc bảo mật mà bạn có thể có.</span><span class="sxs-lookup"><span data-stu-id="e3e14-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="e3e14-141">Để biết thêm thông tin, hãy xem [Tuyên bố về Quyền riêng tư của Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="e3e14-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="e3e14-142">Quản trị viên Dynamics 365 Customer Insights của bạn có thể xóa tính năng tăng cường này bất kỳ lúc nào để ngừng sử dụng chức năng này.</span><span class="sxs-lookup"><span data-stu-id="e3e14-142">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>
