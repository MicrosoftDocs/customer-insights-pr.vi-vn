---
title: Tăng cường thông tin bằng dịch vụ cung cấp dữ liệu của bên thứ ba HERE Technologies
description: Thông tin chung về dịch vụ tăng cường dữ liệu của bên thứ ba HERE Technologies.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: b3c1da0f541efb85b2ca9d87a2e3b97bbfb6ca7f
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305320"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="44e3a-103">Tăng cường dữ liệu hồ sơ khách hàng bằng HERE Technologies (bản xem trước)</span><span class="sxs-lookup"><span data-stu-id="44e3a-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="44e3a-104">HERE Technologies là một công ty nền tảng vị trí cung cấp dữ liệu và dịch vụ tập trung vào vị trí.</span><span class="sxs-lookup"><span data-stu-id="44e3a-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="44e3a-105">Với các dịch vụ làm giàu dữ liệu của HERE Technologies, bạn có thể xây dựng kiến thức vị trí chính xác hơn về khách hàng của mình bằng cách chuẩn hóa địa chỉ, trích xuất vĩ độ và kinh độ, v.v.</span><span class="sxs-lookup"><span data-stu-id="44e3a-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="44e3a-106">Điều kiện tiên quyết</span><span class="sxs-lookup"><span data-stu-id="44e3a-106">Prerequisites</span></span>

<span data-ttu-id="44e3a-107">Để định cấu hình dịch vụ tăng cường dữ liệu HERE Technologies, bạn phải đáp ứng các điều kiện tiên quyết sau:</span><span class="sxs-lookup"><span data-stu-id="44e3a-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="44e3a-108">Bạn có gói đăng ký HERE Technologies hoạt động.</span><span class="sxs-lookup"><span data-stu-id="44e3a-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="44e3a-109">Để đăng ký, bạn có thể [thực hiện tại đây](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) hoặc [liên hệ trực tiếp với HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you).</span><span class="sxs-lookup"><span data-stu-id="44e3a-109">To get a subscription, you can [sign up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="44e3a-110">Tìm hiểu thêm về dịch vụ Tăng cường vị trí HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="44e3a-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="44e3a-111">[Kết nối](connections.md) HERE có sẵn *hoặc* bạn có quyền [quản trị viên](permissions.md#administrator) và khóa API HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="44e3a-111">A HERE [connection](connections.md) is available *or* you have [administrator](permissions.md#administrator) permissions and the HERE Technologies API key.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="44e3a-112">Định cấu hình dữ liệu tăng cường</span><span class="sxs-lookup"><span data-stu-id="44e3a-112">Configure the enrichment</span></span>

1. <span data-ttu-id="44e3a-113">Chuyển tới **Dữ liệu** > **Dữ liệu tăng cường**.</span><span class="sxs-lookup"><span data-stu-id="44e3a-113">Go to **Data** > **Enrichment**.</span></span> 

1. <span data-ttu-id="44e3a-114">Chọn **Tăng cường dữ liệu của tôi** trên ngăn xếp HERE Technologies rồi chọn **Bắt đầu**.</span><span class="sxs-lookup"><span data-stu-id="44e3a-114">Select **Enrich my data** on the HERE Technologies tile and select **Get started**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="44e3a-115">![lát HERE Technologies](media/HERE-tile.png "lát HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="44e3a-115">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="44e3a-116">Chọn một [kết nối](connections.md) từ danh sách thả xuống.</span><span class="sxs-lookup"><span data-stu-id="44e3a-116">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="44e3a-117">Liên hệ với quản trị viên nếu không có kết nối.</span><span class="sxs-lookup"><span data-stu-id="44e3a-117">Contact  an administrator if no connection is available.</span></span> <span data-ttu-id="44e3a-118">Nếu là quản trị viên, bạn có thể tạo kết nối bằng cách chọn **Thêm kết nối**.</span><span class="sxs-lookup"><span data-stu-id="44e3a-118">If you are an administrator, you can create a connection by selecting **Add connection**.</span></span> <span data-ttu-id="44e3a-119">Chọn **HERE Technologies** từ danh sách thả xuống.</span><span class="sxs-lookup"><span data-stu-id="44e3a-119">Choose **HERE Technologies** from the dropdown list.</span></span> 

1. <span data-ttu-id="44e3a-120">Chọn **Kết nối với HERE Technologies** để xác nhận lựa chọn.</span><span class="sxs-lookup"><span data-stu-id="44e3a-120">Select **Connect to HERE Technologies** to confirm the selection.</span></span>

1.  <span data-ttu-id="44e3a-121">Chọn **Tiếp** rồi chọn **Tập hợp dữ liệu khách hàng** mà bạn muốn bổ sung thêm dữ liệu vị trí từ HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="44e3a-121">Select **Next** and choose the **Customer data set** you want to enrich with location data from HERE Technologies.</span></span> <span data-ttu-id="44e3a-122">Bạn có thể chọn thực thể **Khách hàng** để tăng cường dữ liệu cho tất cả hồ sơ khách hàng của bạn hoặc chọn một thực thể phân khúc để chỉ tăng cường dữ liệu cho hồ sơ khách hàng có trong phân khúc đó.</span><span class="sxs-lookup"><span data-stu-id="44e3a-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Ảnh chụp màn hình khi chọn tập dữ liệu khách hàng.":::

1. <span data-ttu-id="44e3a-124">Chọn xem bạn có muốn ánh xạ các trường với địa chỉ chính và/hoặc phụ không.</span><span class="sxs-lookup"><span data-stu-id="44e3a-124">Choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="44e3a-125">Bạn có thể chỉ định kiểu ánh xạ trường cho cả hai địa chỉ và tăng cường dữ liệu hồ sơ cho cả hai địa chỉ một cách riêng biệt.</span><span class="sxs-lookup"><span data-stu-id="44e3a-125">You can specify a field mapping for both addresses and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="44e3a-126">Ví dụ: nếu có địa chỉ nhà riêng và địa chỉ doanh nghiệp.</span><span class="sxs-lookup"><span data-stu-id="44e3a-126">For example, if there's a home and a business address.</span></span> <span data-ttu-id="44e3a-127">Chọn **Tiếp theo**.</span><span class="sxs-lookup"><span data-stu-id="44e3a-127">Select **Next**.</span></span>

1. <span data-ttu-id="44e3a-128">Xác định trường nào từ hồ sơ hợp nhất của bạn sẽ được sử dụng để tìm kiếm dữ liệu vị trí phù hợp từ HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="44e3a-128">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="44e3a-129">Các trường **Đường 1** và **Mã zip/bưu chính** là bắt buộc cho địa chỉ chính và/hoặc phụ đã chọn.</span><span class="sxs-lookup"><span data-stu-id="44e3a-129">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="44e3a-130">Để có độ chính xác so khớp cao hơn, có thể thêm nhiều trường khác.</span><span class="sxs-lookup"><span data-stu-id="44e3a-130">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="44e3a-131">![Trang cấu hình tăng cường dữ liệu HERE Technologies](media/enrichment-HERE-configuration.png "Trang cấu hình tăng cường dữ liệu HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="44e3a-131">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="44e3a-132">Chọn **Tiếp** để hoàn thành quá trình ánh xạ trường.</span><span class="sxs-lookup"><span data-stu-id="44e3a-132">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="44e3a-133">Đặt tên cho dữ liệu tăng cường.</span><span class="sxs-lookup"><span data-stu-id="44e3a-133">Provide a name for the enrichment.</span></span> 

1. <span data-ttu-id="44e3a-134">Chọn **Lưu dữ liệu tăng cường** sau khi xem xét các lựa chọn của bạn.</span><span class="sxs-lookup"><span data-stu-id="44e3a-134">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-here-technologies"></a><span data-ttu-id="44e3a-135">Định cấu hình kết nối cho HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="44e3a-135">Configure the connection for HERE Technologies</span></span> 

<span data-ttu-id="44e3a-136">Bạn cần phải là quản trị viên thì mới có thể định cấu hình kết nối.</span><span class="sxs-lookup"><span data-stu-id="44e3a-136">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="44e3a-137">Chọn **Thêm kết nối** khi định cấu hình dữ liệu tăng cường *hoặc* đi đến **Quản trị viên** > **Kết nối** rồi chọn **Thiết lập** trên ngăn xếp HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="44e3a-137">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the HERE Technologies tile.</span></span>

1. <span data-ttu-id="44e3a-138">Nhập tên cho kết nối trong hộp **Tên hiển thị**.</span><span class="sxs-lookup"><span data-stu-id="44e3a-138">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="44e3a-139">Cung cấp khóa API HERE Technologies hợp lệ.</span><span class="sxs-lookup"><span data-stu-id="44e3a-139">Provide a valid HERE Technologies API key.</span></span>

1. <span data-ttu-id="44e3a-140">Xem xét và chấp thuận **Quyền riêng tư dữ liệu và sự tuân thủ** bằng cách chọn **Tôi đồng ý**.</span><span class="sxs-lookup"><span data-stu-id="44e3a-140">Review and provide your consent for **Data privacy and compliance** by selecting **I agree**.</span></span>

1. <span data-ttu-id="44e3a-141">Chọn **Xác minh** để xác thực cấu hình.</span><span class="sxs-lookup"><span data-stu-id="44e3a-141">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="44e3a-142">Sau khi hoàn thành xác minh, hãy chọn **Lưu**.</span><span class="sxs-lookup"><span data-stu-id="44e3a-142">After completing the verification, select **Save**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="44e3a-143">![Trang cấu hình kết nối cho HERE Technologies](media/enrichment-HERE-connection.png "Trang cấu hình kết nối cho HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="44e3a-143">![HERE Technologies connection configuration page](media/enrichment-HERE-connection.png "HERE Technologies connection configuration page")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="44e3a-144">Kết quả tăng cường</span><span class="sxs-lookup"><span data-stu-id="44e3a-144">Enrichment results</span></span>

<span data-ttu-id="44e3a-145">Để bắt đầu quá trình tăng cường, hãy chọn **Chạy** từ thanh lệnh.</span><span class="sxs-lookup"><span data-stu-id="44e3a-145">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="44e3a-146">Bạn cũng có thể để hệ thống chạy quá trình tăng cường tự động như một phần của [làm mới theo lịch trình](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="44e3a-146">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="44e3a-147">Thời gian xử lý sẽ phụ thuộc vào kích thước dữ liệu khách hàng của bạn và thời gian phản hồi API từ HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="44e3a-147">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="44e3a-148">Sau khi quá trình tăng cường hoàn tất, bạn có thể xem xét dữ liệu hồ sơ khách hàng mới được bổ sung trong **Dữ liệu tăng cường của tôi**.</span><span class="sxs-lookup"><span data-stu-id="44e3a-148">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="44e3a-149">Ngoài ra, bạn sẽ tìm thấy thời gian của lần cập nhật gần nhất và số lượng hồ sơ được tăng cường.</span><span class="sxs-lookup"><span data-stu-id="44e3a-149">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="44e3a-150">Bạn có thể truy cập dạng xem chi tiết của từng hồ sơ được tăng cường dữ liệu bằng cách chọn **Xem dữ liệu tăng cường**.</span><span class="sxs-lookup"><span data-stu-id="44e3a-150">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="44e3a-151">Các bước tiếp theo</span><span class="sxs-lookup"><span data-stu-id="44e3a-151">Next steps</span></span>

<span data-ttu-id="44e3a-152">Xây dựng dựa trên dữ liệu khách hàng tăng cường của bạn.</span><span class="sxs-lookup"><span data-stu-id="44e3a-152">Build on top of your enriched customer data.</span></span> <span data-ttu-id="44e3a-153">Tạo [phân khúc](segments.md) và [giá trị đo](measures.md), thậm chí [xuất dữ liệu](export-destinations.md) để cung cấp trải nghiệm được cá nhân hóa cho khách hàng của bạn.</span><span class="sxs-lookup"><span data-stu-id="44e3a-153">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="44e3a-154">Quyền riêng tư về dữ liệu và tuân thủ</span><span class="sxs-lookup"><span data-stu-id="44e3a-154">Data privacy and compliance</span></span>

<span data-ttu-id="44e3a-155">Khi bật Dynamics 365 Customer Insights để truyền dữ liệu tới HERE Technologies, bạn cho phép truyền dữ liệu ra ngoài phạm vi tuân thủ cho Dynamics 365 Customer Insights, bao gồm dữ liệu có khả năng là thông tin nhạy cảm, chẳng hạn như Dữ liệu cá nhân.</span><span class="sxs-lookup"><span data-stu-id="44e3a-155">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="44e3a-156">Microsoft sẽ truyền những dữ liệu đó theo chỉ dẫn của bạn, nhưng bạn có trách nhiệm đảm bảo rằng HERE Technologies đáp ứng mọi nghĩa vụ về quyền riêng tư hoặc bảo mật mà bạn có thể có.</span><span class="sxs-lookup"><span data-stu-id="44e3a-156">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="44e3a-157">Để biết thêm thông tin, hãy xem [Tuyên bố về Quyền riêng tư của Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="44e3a-157">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="44e3a-158">Quản trị viên Dynamics 365 Customer Insights của bạn có thể loại bỏ dịch vụ tăng cường này bất kỳ lúc nào để ngừng sử dụng tính năng đó.</span><span class="sxs-lookup"><span data-stu-id="44e3a-158">Your Dynamics 365 Customer Insights administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
