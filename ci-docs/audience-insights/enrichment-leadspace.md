---
title: Tăng cường dữ liệu hồ sơ công ty bằng dịch vụ tăng cường dữ liệu của bên thứ ba Leadspace
description: Thông tin chung về dịch vụ tăng cường dữ liệu của bên thứ ba Leadspace.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 0496d10c994cd077a778a6e745e3774e316765ae
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305228"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="a7e03-103">Tăng cường dữ liệu hồ sơ công ty bằng Leadspace (bản xem trước)</span><span class="sxs-lookup"><span data-stu-id="a7e03-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="a7e03-104">Leadspace là công ty khoa học dữ liệu cung cấp Nền tảng dữ liệu khách hàng B2B.</span><span class="sxs-lookup"><span data-stu-id="a7e03-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="a7e03-105">Công ty này hỗ trợ hồ sơ khách hàng hợp nhất cho các công ty để tăng cường dữ liệu của họ.</span><span class="sxs-lookup"><span data-stu-id="a7e03-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="a7e03-106">Dữ liệu tăng cường bao gồm nhiều thuộc tính hơn như quy mô công ty, vị trí, ngành, v.v..</span><span class="sxs-lookup"><span data-stu-id="a7e03-106">Enrichments include more attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a7e03-107">Điều kiện tiên quyết</span><span class="sxs-lookup"><span data-stu-id="a7e03-107">Prerequisites</span></span>

<span data-ttu-id="a7e03-108">Để định cấu hình Leadspace, phải đáp ứng các điều kiện tiên quyết sau đây:</span><span class="sxs-lookup"><span data-stu-id="a7e03-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="a7e03-109">Bạn có một giấy phép Leadspace hiện hoạt.</span><span class="sxs-lookup"><span data-stu-id="a7e03-109">You have an active Leadspace license.</span></span>
- <span data-ttu-id="a7e03-110">Bạn có [hồ sơ khách hàng hợp nhất](customer-profiles.md) cho các công ty.</span><span class="sxs-lookup"><span data-stu-id="a7e03-110">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>
- <span data-ttu-id="a7e03-111">Một kết nối Leadspace đã được quản trị viên định cấu hình hoặc bạn có quyền của [quản trị viên](permissions.md#administrator) và “khóa vĩnh viễn” (còn gọi là **Mã thông báo Leadspace**).</span><span class="sxs-lookup"><span data-stu-id="a7e03-111">A Leadspace connection has already been configured by an administrator or you have [administrator](permissions.md#administrator) permissions and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="a7e03-112">Liên hệ trực tiếp với [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) để biết thông tin chi tiết về sản phẩm của họ.</span><span class="sxs-lookup"><span data-stu-id="a7e03-112">Contact [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) directly for details about their product.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="a7e03-113">Định cấu hình tăng cường</span><span class="sxs-lookup"><span data-stu-id="a7e03-113">Configure the enrichment</span></span>

1. <span data-ttu-id="a7e03-114">Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Dữ liệu** > **Tăng cường**.</span><span class="sxs-lookup"><span data-stu-id="a7e03-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="a7e03-115">Chọn **Tăng cường dữ liệu của tôi** trên ngăn xếp Leadspace rồi chọn **Bắt đầu**.</span><span class="sxs-lookup"><span data-stu-id="a7e03-115">Select **Enrich my data** on the Leadspace tile and select **Get started**.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="Ảnh chụp màn hình của ngăn xếp Leadspace.":::

1. <span data-ttu-id="a7e03-117">Chọn một [kết nối](connections.md) từ danh sách thả xuống.</span><span class="sxs-lookup"><span data-stu-id="a7e03-117">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="a7e03-118">Liên hệ với quản trị viên nếu không có kết nối.</span><span class="sxs-lookup"><span data-stu-id="a7e03-118">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="a7e03-119">Nếu là quản trị viên, bạn có thể tạo kết nối bằng cách chọn **Thêm kết nối** rồi chọn **Leadspace**.</span><span class="sxs-lookup"><span data-stu-id="a7e03-119">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **Leadspace**.</span></span> 

1. <span data-ttu-id="a7e03-120">Chọn **Kết nối với Leadspace** để xác nhận kết nối.</span><span class="sxs-lookup"><span data-stu-id="a7e03-120">Select **Connect to Leadspace** to confirm the connection.</span></span>

1. <span data-ttu-id="a7e03-121">Chọn **Tiếp** rồi chọn **Tập hợp dữ liệu khách hàng** mà bạn muốn tăng cường bằng dữ liệu công ty từ Leadspace.</span><span class="sxs-lookup"><span data-stu-id="a7e03-121">Select **Next** and choose the **Customer data set** you want to enrich with company data from Leadspace.</span></span> <span data-ttu-id="a7e03-122">ữBạn có thể chọn thực thể **Khách hàng** để tăng cường dữ liệu cho tất cả hồ sơ khách hàng của bạn hoặc chọn một thực thể phân khúc để chỉ tăng cường dữ liệu cho hồ sơ khách hàng có trong phân khúc đó.</span><span class="sxs-lookup"><span data-stu-id="a7e03-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Ảnh chụp màn hình khi chọn tập dữ liệu khách hàng.":::

1. <span data-ttu-id="a7e03-124">Chọn **Tiếp** và xác định loại trường nào từ hồ sơ hợp nhất của bạn sẽ được sử dụng để khớp dữ liệu công ty học phù hợp từ Leadspace.</span><span class="sxs-lookup"><span data-stu-id="a7e03-124">Select **Next** and define which fields from your unified profiles are used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="a7e03-125">Trường **Tên công ty** là bắt buộc.</span><span class="sxs-lookup"><span data-stu-id="a7e03-125">The **Name of company** field is required.</span></span> <span data-ttu-id="a7e03-126">Để có độ chính xác so khớp cao hơn, có thể thêm tối đa 2 trường khác, **Trang web công ty** và **Vị trí công ty**.</span><span class="sxs-lookup"><span data-stu-id="a7e03-126">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Ngăn ánh xạ trường Leadspace.":::

1. <span data-ttu-id="a7e03-128">Chọn **Tiếp** để hoàn thành quá trình ánh xạ trường.</span><span class="sxs-lookup"><span data-stu-id="a7e03-128">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="a7e03-129">Đặt tên cho dữ liệu tăng cường rồi chọn **Lưu dữ liệu tăng cường** sau khi xem xét các lựa chọn của bạn.</span><span class="sxs-lookup"><span data-stu-id="a7e03-129">Provide a name for the enrichment and select **Save enrichment** after reviewing your choices.</span></span>


## <a name="configure-the-connection-for-leadspace"></a><span data-ttu-id="a7e03-130">Định cấu hình kết nối cho Leadspace</span><span class="sxs-lookup"><span data-stu-id="a7e03-130">Configure the connection for Leadspace</span></span> 

<span data-ttu-id="a7e03-131">Bạn cần phải là quản trị viên thì mới có thể định cấu hình kết nối.</span><span class="sxs-lookup"><span data-stu-id="a7e03-131">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="a7e03-132">Chọn **Thêm kết nối** khi định cấu hình dữ liệu tăng cường *hoặc* đi đến **Quản trị viên** > **Kết nối** rồi chọn **Thiết lập** trên ngăn xếp Leadspace.</span><span class="sxs-lookup"><span data-stu-id="a7e03-132">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Leadspace tile.</span></span>

1. <span data-ttu-id="a7e03-133">Chọn **Bắt đầu**.</span><span class="sxs-lookup"><span data-stu-id="a7e03-133">Select **Get Started**.</span></span> 

1. <span data-ttu-id="a7e03-134">Nhập tên cho kết nối trong hộp **Tên hiển thị**.</span><span class="sxs-lookup"><span data-stu-id="a7e03-134">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="a7e03-135">Cung cấp một mã thông báo Leadspace hợp lệ.</span><span class="sxs-lookup"><span data-stu-id="a7e03-135">Provide a valid Leadspace token.</span></span>

1. <span data-ttu-id="a7e03-136">Xem xét và chấp thuận **Quyền riêng tư dữ liệu và sự tuân thủ** bằng cách chọn **Tôi đồng ý**.</span><span class="sxs-lookup"><span data-stu-id="a7e03-136">Review and provide your consent for **Data privacy and compliance** by selecting **I agree**.</span></span>

1. <span data-ttu-id="a7e03-137">Chọn **Xác minh** để xác thực cấu hình.</span><span class="sxs-lookup"><span data-stu-id="a7e03-137">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="a7e03-138">Sau khi hoàn thành xác minh, hãy chọn **Lưu**.</span><span class="sxs-lookup"><span data-stu-id="a7e03-138">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Trang cấu hình kết nối cho Leadspace.":::

## <a name="enrichment-results"></a><span data-ttu-id="a7e03-140">Kết quả tăng cường</span><span class="sxs-lookup"><span data-stu-id="a7e03-140">Enrichment results</span></span>

<span data-ttu-id="a7e03-141">Sau khi làm mới dữ liệu tăng cường, bạn có thể xem xét dữ liệu công ty mới được bổ sung trong phần [Dữ liệu tăng cường của tôi](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="a7e03-141">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="a7e03-142">Bạn có thể tìm thấy thời điểm cập nhật gần đây nhất và số lượng hồ sơ tăng cường.</span><span class="sxs-lookup"><span data-stu-id="a7e03-142">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="a7e03-143">Bạn có thể truy cập dạng xem chi tiết của từng hồ sơ được tăng cường dữ liệu bằng cách chọn **Xem dữ liệu tăng cường**.</span><span class="sxs-lookup"><span data-stu-id="a7e03-143">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="a7e03-144">Để biết thêm thông tin, hãy xem [API Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span><span class="sxs-lookup"><span data-stu-id="a7e03-144">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="a7e03-145">Các bước tiếp theo</span><span class="sxs-lookup"><span data-stu-id="a7e03-145">Next steps</span></span>

<span data-ttu-id="a7e03-146">Xây dựng dựa trên dữ liệu khách hàng tăng cường của bạn.</span><span class="sxs-lookup"><span data-stu-id="a7e03-146">Build on top of your enriched customer data.</span></span> <span data-ttu-id="a7e03-147">Tạo [phân khúc](segments.md) và [giá trị đo](measures.md), thậm chí [xuất dữ liệu](export-destinations.md) để cung cấp trải nghiệm được cá nhân hóa cho khách hàng của bạn.</span><span class="sxs-lookup"><span data-stu-id="a7e03-147">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="a7e03-148">Quyền riêng tư về dữ liệu và tuân thủ</span><span class="sxs-lookup"><span data-stu-id="a7e03-148">Data privacy and compliance</span></span>

<span data-ttu-id="a7e03-149">Khi bật Dynamics 365 Customer Insights để truyền dữ liệu tới Leadspace, bạn cho phép truyền dữ liệu ra ngoài phạm vi tuân thủ cho Dynamics 365 Customer Insights, bao gồm dữ liệu có khả năng là thông tin nhạy cảm, chẳng hạn như Dữ liệu cá nhân.</span><span class="sxs-lookup"><span data-stu-id="a7e03-149">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="a7e03-150">Microsoft sẽ truyền những dữ liệu đó theo chỉ dẫn của bạn, nhưng bạn có trách nhiệm đảm bảo rằng Leadspace đáp ứng mọi nghĩa vụ về quyền riêng tư hoặc bảo mật mà bạn có thể có.</span><span class="sxs-lookup"><span data-stu-id="a7e03-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="a7e03-151">Để biết thêm thông tin, hãy xem [Tuyên bố về Quyền riêng tư của Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="a7e03-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="a7e03-152">Quản trị viên Dynamics 365 Customer Insights của bạn có thể loại bỏ dịch vụ tăng cường này bất kỳ lúc nào để ngừng sử dụng tính năng đó.</span><span class="sxs-lookup"><span data-stu-id="a7e03-152">Your Dynamics 365 Customer Insights administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
