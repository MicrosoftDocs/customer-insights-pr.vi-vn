---
title: Tăng cường với HERE Technologies tăng cường của bên thứ ba
description: Thông tin chung về tăng cường của bên thứ ba HERE Technologies.
ms.date: 12/10/2020
ms.reviewer: jodahl
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 258e37de9d9685d9ebc30b3c6b8d238d583431b4
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269540"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="372f5-103">Tăng cường hồ sơ khách hàng với HERE Technologies (bản xem trước)</span><span class="sxs-lookup"><span data-stu-id="372f5-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="372f5-104">HERE Technologies là một công ty nền tảng vị trí cung cấp dữ liệu và dịch vụ tập trung vào vị trí.</span><span class="sxs-lookup"><span data-stu-id="372f5-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="372f5-105">Với các dịch vụ làm giàu dữ liệu của HERE Technologies, bạn có thể xây dựng kiến thức vị trí chính xác hơn về khách hàng của mình bằng cách chuẩn hóa địa chỉ, trích xuất vĩ độ và kinh độ, v.v.</span><span class="sxs-lookup"><span data-stu-id="372f5-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="372f5-106">Điều kiện tiên quyết</span><span class="sxs-lookup"><span data-stu-id="372f5-106">Prerequisites</span></span>

<span data-ttu-id="372f5-107">Để định cấu hình tính năng tăng cường HERE Technologies, bạn phải đáp ứng các điều kiện tiên quyết sau:</span><span class="sxs-lookup"><span data-stu-id="372f5-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="372f5-108">Bạn có gói đăng ký HERE Technologies hoạt động.</span><span class="sxs-lookup"><span data-stu-id="372f5-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="372f5-109">Để nhận gói đăng ký, bạn có thể [đăng ký tại đây](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) hoặc [liên hệ trực tiếp với HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you).</span><span class="sxs-lookup"><span data-stu-id="372f5-109">To get a subscription, you can [sign-up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="372f5-110">Tìm hiểu thêm về tính năng Tăng cường vị trí HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="372f5-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="372f5-111">Bạn có khóa API HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="372f5-111">You have the HERE Technologies API key.</span></span>

- <span data-ttu-id="372f5-112">Bạn có quyền [Quản trị viên](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="372f5-112">You have [Administrator](permissions.md#administrator) permissions.</span></span>

## <a name="configuration"></a><span data-ttu-id="372f5-113">Cấu hình</span><span class="sxs-lookup"><span data-stu-id="372f5-113">Configuration</span></span>

1. <span data-ttu-id="372f5-114">Chuyển tới **Dữ liệu** > **Nội dung phong phú**.</span><span class="sxs-lookup"><span data-stu-id="372f5-114">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="372f5-115">Chọn **Tăng cường dữ liệu của tôi** trên lát HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="372f5-115">Select **Enrich my data** on the HERE Technologies tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="372f5-116">![lát HERE Technologies](media/HERE-tile.png "lát HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="372f5-116">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="372f5-117">Nhập **khóa API HERE Technologies** hiện hoạt.</span><span class="sxs-lookup"><span data-stu-id="372f5-117">Enter an active **HERE Technologies API key**.</span></span> <span data-ttu-id="372f5-118">Xem lại và đồng ý với **Quyền riêng tư và tuân thủ dữ liệu** bằng cách đánh dấu ô **Tôi đồng ý**.</span><span class="sxs-lookup"><span data-stu-id="372f5-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> 

1. <span data-ttu-id="372f5-119">Xác nhận cả hai đầu vào bằng cách chọn **Kết nối với HERE**.</span><span class="sxs-lookup"><span data-stu-id="372f5-119">Confirm both inputs by selecting **Connect to HERE**.</span></span>

1.  <span data-ttu-id="372f5-120">Chọn **Thêm dữ liệu** và chọn **Tập dữ liệu khách hàng** bạn muốn làm phong phú bằng dữ liệu vị trí từ HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="372f5-120">Select **Add data** and choose the **Customer data set** you want to enrich with location data from HERE Technologies.</span></span> <span data-ttu-id="372f5-121">Bạn có thể chọn thực thể **khách hàng** để làm phong phú tất cả hồ sơ khách hàng của bạn hoặc chọn một thực thể phân khúc để chỉ làm phong phú thêm hồ sơ khách hàng có trong phân khúc đó.</span><span class="sxs-lookup"><span data-stu-id="372f5-121">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Ảnh chụp màn hình khi chọn tập dữ liệu khách hàng.":::

1. <span data-ttu-id="372f5-123">Chọn xem bạn có muốn ánh xạ các trường với địa chỉ chính và/hoặc phụ không.</span><span class="sxs-lookup"><span data-stu-id="372f5-123">Choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="372f5-124">Bạn có thể chỉ định ánh xạ trường cho cả hai địa chỉ (ví dụ: địa chỉ nhà riêng và địa chỉ doanh nghiệp) và tăng cường hồ sơ cho cả hai địa chỉ một cách riêng biệt.</span><span class="sxs-lookup"><span data-stu-id="372f5-124">You can specify a field mapping for both addresses (for example, a home and a business address) and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="372f5-125">Chọn **Tiếp theo**.</span><span class="sxs-lookup"><span data-stu-id="372f5-125">Select **Next**.</span></span>

1. <span data-ttu-id="372f5-126">Xác định trường nào từ hồ sơ hợp nhất của bạn sẽ được sử dụng để tìm kiếm dữ liệu vị trí phù hợp từ HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="372f5-126">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="372f5-127">Các trường **Đường 1** và **Mã zip/bưu chính** là bắt buộc cho địa chỉ chính và/hoặc phụ đã chọn.</span><span class="sxs-lookup"><span data-stu-id="372f5-127">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="372f5-128">Để có độ chính xác so khớp cao hơn, có thể thêm nhiều trường khác.</span><span class="sxs-lookup"><span data-stu-id="372f5-128">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="372f5-129">![Trang cấu hình tăng cường HERE Technologies](media/enrichment-HERE-configuration.png "Trang cấu hình tăng cường HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="372f5-129">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="372f5-130">Chọn **Áp dụng** để hoàn thành ánh xạ trường.</span><span class="sxs-lookup"><span data-stu-id="372f5-130">Select **Apply** to complete the field mapping.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="372f5-131">Kết quả làm phong phú</span><span class="sxs-lookup"><span data-stu-id="372f5-131">Enrichment results</span></span>

<span data-ttu-id="372f5-132">Để bắt đầu quá trình tăng cường, hãy chọn **Chạy** từ thanh lệnh.</span><span class="sxs-lookup"><span data-stu-id="372f5-132">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="372f5-133">Bạn cũng có thể để hệ thống chạy quá trình tăng cường tự động như một phần của [làm mới theo lịch trình](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="372f5-133">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="372f5-134">Thời gian xử lý sẽ phụ thuộc vào kích thước dữ liệu khách hàng của bạn và thời gian phản hồi API từ HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="372f5-134">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="372f5-135">Sau khi quá trình tăng cường hoàn tất, bạn có thể xem lại dữ liệu hồ sơ khách hàng mới được bổ sung trong **Nội dung tăng cường của tôi**.</span><span class="sxs-lookup"><span data-stu-id="372f5-135">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="372f5-136">Ngoài ra, bạn sẽ tìm thấy thời gian của lần cập nhật gần nhất và số lượng hồ sơ được tăng cường.</span><span class="sxs-lookup"><span data-stu-id="372f5-136">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="372f5-137">Bạn có thể truy cập dạng xem chi tiết của từng hồ sơ được làm phong phú bằng cách chọn **Xem dữ liệu được làm phong phú**.</span><span class="sxs-lookup"><span data-stu-id="372f5-137">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="372f5-138">Các bước tiếp theo</span><span class="sxs-lookup"><span data-stu-id="372f5-138">Next steps</span></span>

<span data-ttu-id="372f5-139">Xây dựng dựa trên dữ liệu khách hàng phong phú của bạn.</span><span class="sxs-lookup"><span data-stu-id="372f5-139">Build on top of your enriched customer data.</span></span> <span data-ttu-id="372f5-140">Tạo [phân khúc](segments.md), [biện pháp](measures.md) và [xuất dữ liệu](export-destinations.md) để cung cấp trải nghiệm cá nhân cho khách hàng của bạn.</span><span class="sxs-lookup"><span data-stu-id="372f5-140">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="372f5-141">Quyền riêng tư về dữ liệu và tuân thủ</span><span class="sxs-lookup"><span data-stu-id="372f5-141">Data privacy and compliance</span></span>

<span data-ttu-id="372f5-142">Khi bật Dynamics 365 Customer Insights để truyền dữ liệu tới HERE Technologies, bạn cho phép chuyển dữ liệu ra bên ngoài ranh giới tuân thủ cho Dynamics 365 Customer Insights, bao gồm dữ liệu nhạy cảm tiềm ẩn như Dữ liệu cá nhân.</span><span class="sxs-lookup"><span data-stu-id="372f5-142">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="372f5-143">Microsoft sẽ chuyển những dữ liệu đó theo chỉ dẫn của bạn, nhưng bạn có trách nhiệm đảm bảo rằng HERE Technologies đáp ứng mọi nghĩa vụ về quyền riêng tư hoặc bảo mật mà bạn có thể có.</span><span class="sxs-lookup"><span data-stu-id="372f5-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="372f5-144">Để biết thêm thông tin, hãy xem [Tuyên bố về Quyền riêng tư của Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="372f5-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="372f5-145">Quản trị viên Dynamics 365 Customer Insights của bạn có thể xóa tính năng tăng cường này bất kỳ lúc nào để ngừng sử dụng chức năng này.</span><span class="sxs-lookup"><span data-stu-id="372f5-145">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]