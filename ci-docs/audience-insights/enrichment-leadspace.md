---
title: Tăng cường hồ sơ công ty bằng chức năng tăng cường của bên thứ ba Leadspace
description: Thông tin chung về tăng cường của bên thứ ba Leadspace.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: ccf4f661ecffb281556a4545b1f26ee809c697cd
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 04/14/2021
ms.locfileid: "5895939"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="0b9bc-103">Làm phong phú hồ sơ công ty bằng Leadspace (xem trước)</span><span class="sxs-lookup"><span data-stu-id="0b9bc-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="0b9bc-104">Leadspace là công ty khoa học dữ liệu cung cấp Nền tảng dữ liệu khách hàng B2B.</span><span class="sxs-lookup"><span data-stu-id="0b9bc-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="0b9bc-105">Nó cho phép khách hàng có hồ sơ khách hàng hợp nhất cho các công ty để làm phong phú dữ liệu của họ.</span><span class="sxs-lookup"><span data-stu-id="0b9bc-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="0b9bc-106">Nội dung bổ sung bao gồm nhiều thuộc tính hơn như quy mô công ty, vị trí, ngành, v.v..</span><span class="sxs-lookup"><span data-stu-id="0b9bc-106">Enrichments include more attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0b9bc-107">Điều kiện tiên quyết</span><span class="sxs-lookup"><span data-stu-id="0b9bc-107">Prerequisites</span></span>

<span data-ttu-id="0b9bc-108">Để đặt cấu hình Leadspace, phải đáp ứng các điều kiện tiên quyết sau đây:</span><span class="sxs-lookup"><span data-stu-id="0b9bc-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="0b9bc-109">Bạn có một giấy phép Leadspace hiện hoạt.</span><span class="sxs-lookup"><span data-stu-id="0b9bc-109">You have an active Leadspace license.</span></span>
- <span data-ttu-id="0b9bc-110">Bạn có [hồ sơ khách hàng hợp nhất](customer-profiles.md) cho các công ty.</span><span class="sxs-lookup"><span data-stu-id="0b9bc-110">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>
- <span data-ttu-id="0b9bc-111">Một kết nối Leadspace đã được quản trị viên đặt cấu hình hoặc bạn có quyền của [quản trị viên](permissions.md#administrator) và “khóa vĩnh viễn” (còn gọi là **Mã thông báo Leadspace**).</span><span class="sxs-lookup"><span data-stu-id="0b9bc-111">A Leadspace connection has already been configured by an administrator or you have [administrator](permissions.md#administrator) permissions and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="0b9bc-112">Liên hệ trực tiếp với [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) để biết thông tin chi tiết về sản phẩm của họ.</span><span class="sxs-lookup"><span data-stu-id="0b9bc-112">Contact [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) directly for details about their product.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="0b9bc-113">Đặt cấu hình nội dung bổ sung</span><span class="sxs-lookup"><span data-stu-id="0b9bc-113">Configure the enrichment</span></span>

1. <span data-ttu-id="0b9bc-114">Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Dữ liệu** > **Tăng cường**.</span><span class="sxs-lookup"><span data-stu-id="0b9bc-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="0b9bc-115">Chọn **Làm phong phú dữ liệu của tôi** trên ngăn xếp Leadspace rồi chọn **Bắt đầu**.</span><span class="sxs-lookup"><span data-stu-id="0b9bc-115">Select **Enrich my data** on the Leadspace tile and select **Get started**.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="Ảnh chụp màn hình của ngăn xếp Leadspace.":::

1. <span data-ttu-id="0b9bc-117">Chọn một [kết nối](connections.md) từ danh sách thả xuống.</span><span class="sxs-lookup"><span data-stu-id="0b9bc-117">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="0b9bc-118">Liên hệ với quản trị viên nếu không có kết nối.</span><span class="sxs-lookup"><span data-stu-id="0b9bc-118">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="0b9bc-119">Nếu là quản trị viên, bạn có thể tạo kết nối bằng cách chọn **Thêm kết nối** rồi chọn **Leadspace**.</span><span class="sxs-lookup"><span data-stu-id="0b9bc-119">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **Leadspace**.</span></span> 

1. <span data-ttu-id="0b9bc-120">Chọn **Kết nối với Leadspace** để xác nhận kết nối.</span><span class="sxs-lookup"><span data-stu-id="0b9bc-120">Select **Connect to Leadspace** to confirm the connection.</span></span>

1. <span data-ttu-id="0b9bc-121">Chọn **Tiếp** rồi chọn **Tập hợp dữ liệu khách hàng** mà bạn muốn bổ sung thêm dữ liệu công ty từ Leadspace.</span><span class="sxs-lookup"><span data-stu-id="0b9bc-121">Select **Next** and choose the **Customer data set** you want to enrich with company data from Leadspace.</span></span> <span data-ttu-id="0b9bc-122">Bạn có thể chọn thực thể **khách hàng** để làm phong phú tất cả hồ sơ khách hàng của bạn hoặc chọn một thực thể phân khúc để chỉ làm phong phú thêm hồ sơ khách hàng có trong phân khúc đó.</span><span class="sxs-lookup"><span data-stu-id="0b9bc-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Ảnh chụp màn hình khi chọn tập dữ liệu khách hàng.":::

1. <span data-ttu-id="0b9bc-124">Chọn **Tiếp** và xác định loại trường nào từ hồ sơ hợp nhất của bạn sẽ được sử dụng để khớp dữ liệu công ty học phù hợp từ Leadspace.</span><span class="sxs-lookup"><span data-stu-id="0b9bc-124">Select **Next** and define which fields from your unified profiles are used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="0b9bc-125">Trường **Tên công ty** là bắt buộc.</span><span class="sxs-lookup"><span data-stu-id="0b9bc-125">The **Name of company** field is required.</span></span> <span data-ttu-id="0b9bc-126">Để có độ chính xác so khớp cao hơn, có thể thêm tối đa 2 trường khác, **Trang web công ty** và **Vị trí công ty**.</span><span class="sxs-lookup"><span data-stu-id="0b9bc-126">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Ngăn ánh xạ trường Leadspace.":::

1. <span data-ttu-id="0b9bc-128">Chọn **Tiếp** để hoàn thành quá trình ánh xạ trường.</span><span class="sxs-lookup"><span data-stu-id="0b9bc-128">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="0b9bc-129">Đặt tên cho nội dung bổ sung rồi chọn **Lưu nội dung bổ sung** sau khi xem xét các lựa chọn của bạn.</span><span class="sxs-lookup"><span data-stu-id="0b9bc-129">Provide a name for the enrichment and select **Save enrichment** after reviewing your choices.</span></span>


## <a name="configure-the-connection-for-leadspace"></a><span data-ttu-id="0b9bc-130">Đặt cấu hình kết nối cho Leadspace</span><span class="sxs-lookup"><span data-stu-id="0b9bc-130">Configure the connection for Leadspace</span></span> 

<span data-ttu-id="0b9bc-131">Bạn cần phải là quản trị viên thì mới có thể đặt cấu hình kết nối.</span><span class="sxs-lookup"><span data-stu-id="0b9bc-131">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="0b9bc-132">Chọn **Thêm kết nối** khi đặt cấu hình nội dung bổ sung *hoặc* đi đến **Quản trị viên** > **Kết nối** rồi chọn **Thiết lập** trên ngăn xếp Leadspace.</span><span class="sxs-lookup"><span data-stu-id="0b9bc-132">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Leadspace tile.</span></span>

1. <span data-ttu-id="0b9bc-133">Chọn **Bắt đầu**</span><span class="sxs-lookup"><span data-stu-id="0b9bc-133">Select **Get Started**</span></span> 

1. <span data-ttu-id="0b9bc-134">Nhập tên cho kết nối trong hộp **Tên hiển thị**.</span><span class="sxs-lookup"><span data-stu-id="0b9bc-134">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="0b9bc-135">Cung cấp một mã thông báo Leadspace hợp lệ.</span><span class="sxs-lookup"><span data-stu-id="0b9bc-135">Provide a valid Leadspace token.</span></span>

1. <span data-ttu-id="0b9bc-136">Xem lại và đồng ý với **Quyền riêng tư về dữ liệu và tuân thủ** bằng cách đánh dấu vào hộp kiểm **Tôi đồng ý**</span><span class="sxs-lookup"><span data-stu-id="0b9bc-136">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox</span></span>

1. <span data-ttu-id="0b9bc-137">Chọn **Xác minh** để xác thực cấu hình.</span><span class="sxs-lookup"><span data-stu-id="0b9bc-137">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="0b9bc-138">Sau khi hoàn thành xác minh, hãy chọn **Lưu**.</span><span class="sxs-lookup"><span data-stu-id="0b9bc-138">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Trang cấu hình kết nối cho Leadspace.":::

## <a name="enrichment-results"></a><span data-ttu-id="0b9bc-140">Kết quả làm phong phú</span><span class="sxs-lookup"><span data-stu-id="0b9bc-140">Enrichment results</span></span>

<span data-ttu-id="0b9bc-141">Sau khi làm mới hồ sơ phong phú, bạn có thể xem lại dữ liệu công ty được làm mới gần đây trong phần [Nội dung phong phú của tôi](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="0b9bc-141">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="0b9bc-142">Bạn có thể tìm thấy thời điểm cập nhật gần đây nhất và số lượng hồ sơ phong phú.</span><span class="sxs-lookup"><span data-stu-id="0b9bc-142">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="0b9bc-143">Bạn có thể truy cập dạng xem chi tiết của từng hồ sơ được làm phong phú bằng cách chọn **Xem dữ liệu được làm phong phú**.</span><span class="sxs-lookup"><span data-stu-id="0b9bc-143">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="0b9bc-144">Để biết thêm thông tin, hãy xem [API Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span><span class="sxs-lookup"><span data-stu-id="0b9bc-144">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="0b9bc-145">Các bước tiếp theo</span><span class="sxs-lookup"><span data-stu-id="0b9bc-145">Next steps</span></span>

<span data-ttu-id="0b9bc-146">Xây dựng dựa trên dữ liệu khách hàng phong phú của bạn.</span><span class="sxs-lookup"><span data-stu-id="0b9bc-146">Build on top of your enriched customer data.</span></span> <span data-ttu-id="0b9bc-147">Tạo [phân khúc](segments.md), [biện pháp](measures.md) và [xuất dữ liệu](export-destinations.md) để cung cấp trải nghiệm cá nhân cho khách hàng của bạn.</span><span class="sxs-lookup"><span data-stu-id="0b9bc-147">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="0b9bc-148">Quyền riêng tư về dữ liệu và tuân thủ</span><span class="sxs-lookup"><span data-stu-id="0b9bc-148">Data privacy and compliance</span></span>

<span data-ttu-id="0b9bc-149">Khi bật Dynamics 365 Customer Insights để truyền dữ liệu tới Leadspace, bạn cho phép chuyển dữ liệu ra bên ngoài ranh giới tuân thủ cho Dynamics 365 Customer Insights, bao gồm dữ liệu nhạy cảm tiềm ẩn như Dữ liệu cá nhân.</span><span class="sxs-lookup"><span data-stu-id="0b9bc-149">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="0b9bc-150">Microsoft sẽ chuyển những dữ liệu đó theo chỉ dẫn của bạn, nhưng bạn có trách nhiệm đảm bảo rằng Leadspace đáp ứng mọi nghĩa vụ về quyền riêng tư hoặc bảo mật mà bạn có thể có.</span><span class="sxs-lookup"><span data-stu-id="0b9bc-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="0b9bc-151">Để biết thêm thông tin, hãy xem [Tuyên bố về Quyền riêng tư của Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="0b9bc-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="0b9bc-152">Quản trị viên Dynamics 365 Customer Insights của bạn có thể xóa tính năng tăng cường này bất kỳ lúc nào để ngừng sử dụng chức năng này.</span><span class="sxs-lookup"><span data-stu-id="0b9bc-152">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
