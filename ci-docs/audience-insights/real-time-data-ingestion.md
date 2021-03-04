---
title: Nhập dữ liệu thời gian thực và các giới hạn
description: Thông tin chung về khả năng thời gian thực trong thông tin chi tiết về đối tượng.
ms.date: 10/27/2020
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7421ed9d2cb399d546815b2d1b0ea5ec51ca6b6d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270306"
---
# <a name="real-time-data-ingestion-preview"></a><span data-ttu-id="16a4c-103">Nhập dữ liệu trong thời gian thực (xem trước)</span><span class="sxs-lookup"><span data-stu-id="16a4c-103">Real-time data ingestion (preview)</span></span>

<span data-ttu-id="16a4c-104">Chức năng gần thời gian thực cho phép bạn xem, trong vài giây, các tương tác mới nhất mà khách hàng của bạn đã thực hiện với các sản phẩm hoặc dịch vụ của bạn.</span><span class="sxs-lookup"><span data-stu-id="16a4c-104">The near real-time functionality lets you see, within seconds, the latest interactions that your customers have made with your products or services.</span></span>

<span data-ttu-id="16a4c-105">[Làm mới theo lịch trình](system.md#schedule-tab) bao gồm số lượng lớn các bản ghi và một số hoạt động phức tạp.</span><span class="sxs-lookup"><span data-stu-id="16a4c-105">[Scheduled refreshes](system.md#schedule-tab) include large numbers of records and several complex operations.</span></span> <span data-ttu-id="16a4c-106">Đầu tiên, dữ liệu được lấy từ nguồn dữ liệu.</span><span class="sxs-lookup"><span data-stu-id="16a4c-106">First, data is pulled from the data source.</span></span> <span data-ttu-id="16a4c-107">Tiếp theo, dữ liệu được hợp nhất, và sau đó được làm giàu với thông tin bổ sung.</span><span class="sxs-lookup"><span data-stu-id="16a4c-107">Next, the data is unified, and then enriched with additional information.</span></span> <span data-ttu-id="16a4c-108">Mỗi lần chạy của quá trình này có thể mất vài phút đến vài giờ.</span><span class="sxs-lookup"><span data-stu-id="16a4c-108">Every run of this process can take minutes to hours.</span></span>

<span data-ttu-id="16a4c-109">Chức năng thời gian thực cung cấp dữ liệu ngay lập tức để sử dụng, cho đến khi quá trình làm mới theo lịch trình tiếp theo kéo dữ liệu này từ nguồn dữ liệu.</span><span class="sxs-lookup"><span data-stu-id="16a4c-109">The real-time functionality provides data immediately for consumption, until the subsequent scheduled refresh pulls this data from the data source.</span></span>

<span data-ttu-id="16a4c-110">Các cập nhật trong thời gian thực có thời gian hết hạn mà sau đó chúng không còn ghi đè giá trị từ nguồn dữ liệu:</span><span class="sxs-lookup"><span data-stu-id="16a4c-110">Real-time updates have an expiration time after which they no longer override the value from the data source:</span></span>

- <span data-ttu-id="16a4c-111">Cập nhật hồ sơ sẽ được lưu giữ trong 4 giờ</span><span class="sxs-lookup"><span data-stu-id="16a4c-111">Profile updates will be kept for 4 hours</span></span>
- <span data-ttu-id="16a4c-112">Các hoạt động sẽ được giữ trong 30 ngày</span><span class="sxs-lookup"><span data-stu-id="16a4c-112">Activities will be kept for 30 days</span></span>

<span data-ttu-id="16a4c-113">Các giá trị này là các tham số gọi API mà bạn có thể thay đổi.</span><span class="sxs-lookup"><span data-stu-id="16a4c-113">These values are API call parameters that you can change.</span></span> <span data-ttu-id="16a4c-114">Các giá trị này nhằm đảm bảo rằng dữ liệu nguồn vẫn là nguồn sự thật của bạn.</span><span class="sxs-lookup"><span data-stu-id="16a4c-114">They aim to ensure that your source data remains your source of truth.</span></span> <span data-ttu-id="16a4c-115">Nếu bạn muốn các cập nhật trong thời gian thực được đưa vào lâu hơn, bạn cần thêm chúng vào nguồn dữ liệu để chúng được kéo trong lần làm mới theo lịch trình tiếp theo.</span><span class="sxs-lookup"><span data-stu-id="16a4c-115">If you want real-time updates to be included for longer, you need to add them to a data source so they get pulled during the next scheduled refresh.</span></span>

## <a name="real-time-update-of-the-unified-customer-profile-fields"></a><span data-ttu-id="16a4c-116">Cập nhật theo thời gian thực của các trường hồ sơ khách hàng hợp nhất</span><span class="sxs-lookup"><span data-stu-id="16a4c-116">Real-time update of the unified customer profile fields</span></span>

<span data-ttu-id="16a4c-117">Hồ sơ cập nhật sẽ hiển thị trong chế độ xem thẻ khách hàng hoặc bất kỳ hình ảnh trực quan nào khác, trong vòng vài giây.</span><span class="sxs-lookup"><span data-stu-id="16a4c-117">Updated profiles will show in the customer card view, or any other visualization, within a few seconds.</span></span>

<span data-ttu-id="16a4c-118">Bởi vì các hoạt động trong thời gian thực diễn ra sau khi quá hợp nhất dữ liệu đã xảy ra, các hoạt động này chỉ áp dụng cho hồ sơ khách hàng hợp nhất.</span><span class="sxs-lookup"><span data-stu-id="16a4c-118">Because real-time operations take place after the data unification has happened, they only apply to the unified customer profiles.</span></span> <span data-ttu-id="16a4c-119">Do đó, các thay đổi hồ sơ theo thời gian thực sẽ không cập nhật các biện pháp, tư cách thành viên phân đoạn hoặc làm phong phú.</span><span class="sxs-lookup"><span data-stu-id="16a4c-119">Consequently, real-time profile changes will not update measures, segment membership, or enrichments.</span></span>

### <a name="limitations"></a><span data-ttu-id="16a4c-120">Giới hạn</span><span class="sxs-lookup"><span data-stu-id="16a4c-120">Limitations</span></span>

- <span data-ttu-id="16a4c-121">Có thể cập nhật nhưng không tạo hoặc xóa hồ sơ khách hàng.</span><span class="sxs-lookup"><span data-stu-id="16a4c-121">Customer profiles can be updated, but not created or deleted.</span></span>
- <span data-ttu-id="16a4c-122">Tại thời điểm này, không xuất được thông tin cập nhật trong thời gian thực sang các hệ thống bên ngoài, như Power BI.</span><span class="sxs-lookup"><span data-stu-id="16a4c-122">Exporting real-time updates to external systems, like Power BI, is not possible at the moment.</span></span>

## <a name="real-time-creation-of-activities"></a><span data-ttu-id="16a4c-123">Tạo hoạt động theo thời gian thực</span><span class="sxs-lookup"><span data-stu-id="16a4c-123">Real-time creation of activities</span></span>

<span data-ttu-id="16a4c-124">API thời gian thực cho phép bạn xuất bản một hoạt động mới từ hệ thống nguồn của bạn (một bản ghi nguồn riêng lẻ) lên một hồ sơ khách hàng hợp nhất.</span><span class="sxs-lookup"><span data-stu-id="16a4c-124">The real-time API lets you publish a new activity from your source system (an individual source record) to a unified customer profile.</span></span> <span data-ttu-id="16a4c-125">Hoạt động mới sẽ có sẵn dưới dạng một hoạt động hợp nhất trong dòng thời gian của hồ sơ khách hàng hợp nhất đó trong vài giây.</span><span class="sxs-lookup"><span data-stu-id="16a4c-125">The new activity will be available as a unified activity in that unified customer profile's timeline within seconds.</span></span> <span data-ttu-id="16a4c-126">Bạn có thể xem dòng thời gian trong chế độ xem thẻ khách hàng hoặc bất kỳ tích hợp dòng thời gian nào khác mà bạn đã định cấu hình.</span><span class="sxs-lookup"><span data-stu-id="16a4c-126">You can see the timeline in the customer card view or any other timeline integration you configured.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="16a4c-127">Hoạt động không thể thay đổi được.</span><span class="sxs-lookup"><span data-stu-id="16a4c-127">Activities are immutable.</span></span> <span data-ttu-id="16a4c-128">Hoạt động không thay đổi sau khi được tạo.</span><span class="sxs-lookup"><span data-stu-id="16a4c-128">They don't change once created.</span></span>
> - <span data-ttu-id="16a4c-129">Hiện tại, các phân đoạn và biện pháp sẽ không cập nhật dựa trên hoạt động mới.</span><span class="sxs-lookup"><span data-stu-id="16a4c-129">Currently, segments and measures won't update based on the new activity.</span></span>
> - <span data-ttu-id="16a4c-130">Các hoạt động chỉ được thêm thông qua API thời gian thực không phải là một phần của hoạt động xuất và sẽ không hiển thị trong PowerBI.</span><span class="sxs-lookup"><span data-stu-id="16a4c-130">Activities added only through the real-time API are not part of exports and won't show up in PowerBI.</span></span>

<span data-ttu-id="16a4c-131">Có hai cách để kết nối với API thời gian thực:</span><span class="sxs-lookup"><span data-stu-id="16a4c-131">There are two ways to connect to the real-time API:</span></span>

- <span data-ttu-id="16a4c-132">[gián tiếp](#connect-via-the-dynamics-365-customer-insights-connector), sử dụng [Dynamics 365 Customer Insights trình kết nối](https://docs.microsoft.com/connectors/customerinsights/)</span><span class="sxs-lookup"><span data-stu-id="16a4c-132">[indirectly](#connect-via-the-dynamics-365-customer-insights-connector), using the [Dynamics 365 Customer Insights connector](https://docs.microsoft.com/connectors/customerinsights/)</span></span>
- <span data-ttu-id="16a4c-133">[trực tiếp](#connect-directly-to-the-real-time-api), có mã</span><span class="sxs-lookup"><span data-stu-id="16a4c-133">[directly](#connect-directly-to-the-real-time-api), with code</span></span>

<span data-ttu-id="16a4c-134">Cả hai cách đều có chung các điều kiện tiên quyết sau:</span><span class="sxs-lookup"><span data-stu-id="16a4c-134">Both ways share the following prerequisites:</span></span>

- <span data-ttu-id="16a4c-135">Môi trường Customer Insights</span><span class="sxs-lookup"><span data-stu-id="16a4c-135">A Customer Insights environment</span></span>
- <span data-ttu-id="16a4c-136">Hồ sơ khách hàng hợp nhất</span><span class="sxs-lookup"><span data-stu-id="16a4c-136">Unified customer profiles</span></span>
- <span data-ttu-id="16a4c-137">Các hoạt động đặt đặt cấu hình và chạy</span><span class="sxs-lookup"><span data-stu-id="16a4c-137">Activities configured and run</span></span>
- <span data-ttu-id="16a4c-138">Quyền của Cộng tác viên hoặc Quản trị viên để xác thực tài khoản của bạn</span><span class="sxs-lookup"><span data-stu-id="16a4c-138">Contributor or Administrator permissions to authenticate your account</span></span>

## <a name="connect-via-the-dynamics-365-customer-insights-connector"></a><span data-ttu-id="16a4c-139">Kết nối thông qua trình kết nối Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="16a4c-139">Connect via the Dynamics 365 Customer Insights connector</span></span>

<span data-ttu-id="16a4c-140">API thời gian thực có thể nhập dữ liệu từ một trình kết nối Power Platform chuyên dụng, trình kết nối [Dynamics 365 Customer Insights ](https://docs.microsoft.com/connectors/customerinsights/) mà không cần phải viết và triển khai bất kỳ mã nào.</span><span class="sxs-lookup"><span data-stu-id="16a4c-140">The real-time API can ingest data from a dedicated Power Platform connector, the [Dynamics 365 Customer Insights connector](https://docs.microsoft.com/connectors/customerinsights/), without the need to write and deploy any code.</span></span>    
<span data-ttu-id="16a4c-141">Trình kết nối có thể thực hiện các hành động tương tự trong thời gian thực như API.</span><span class="sxs-lookup"><span data-stu-id="16a4c-141">The connector can do the same real-time actions as the API.</span></span> <span data-ttu-id="16a4c-142">Bạn cần có giấy phép hợp lệ cho các kết nối cao cấp.</span><span class="sxs-lookup"><span data-stu-id="16a4c-142">You need a valid license for premium connectors.</span></span> <span data-ttu-id="16a4c-143">Để biết thêm thông tin, hãy xem Câu hỏi thường gặp về cấp phép [Power Apps và Power Automate](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq).</span><span class="sxs-lookup"><span data-stu-id="16a4c-143">For more information, see [Power Apps and Power Automate licensing FAQs](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq).</span></span>

- <span data-ttu-id="16a4c-144">Power Platform [Power Apps và/hoặc Power Automate](https://docs.microsoft.com/connectors/)</span><span class="sxs-lookup"><span data-stu-id="16a4c-144">Power Platform [Power Apps and/or Power Automate](https://docs.microsoft.com/connectors/)</span></span>
- <span data-ttu-id="16a4c-145">Ứng dụng Logic [Azure](https://docs.microsoft.com/azure/connectors/apis-list)</span><span class="sxs-lookup"><span data-stu-id="16a4c-145">Azure [Logic Apps](https://docs.microsoft.com/azure/connectors/apis-list)</span></span>

<span data-ttu-id="16a4c-146">Để biết chi tiết về việc tạo dòng, hãy xem tài liệu [Power Automate](https://docs.microsoft.com/power-automate/).</span><span class="sxs-lookup"><span data-stu-id="16a4c-146">For details about creating flows, see the [Power Automate documentation](https://docs.microsoft.com/power-automate/).</span></span>

## <a name="connect-directly-to-the-real-time-api"></a><span data-ttu-id="16a4c-147">Kết nối trực tiếp với API thời gian thực</span><span class="sxs-lookup"><span data-stu-id="16a4c-147">Connect directly to the real-time API</span></span>

<span data-ttu-id="16a4c-148">Bạn có thể sử dụng các khả năng thời gian thực bằng cách xây dựng quy trình của riêng mình và kết nối trực tiếp với API thời gian thực.</span><span class="sxs-lookup"><span data-stu-id="16a4c-148">You can use the real-time capabilities by building your own pipeline and connecting directly to the real-time API.</span></span>    
<span data-ttu-id="16a4c-149">Bạn có thể đăng một hoạt động ở định dạng của hệ thống nguồn của bạn hoặc ở định dạng UnifiedActivity.</span><span class="sxs-lookup"><span data-stu-id="16a4c-149">You can post an activity in the format of your source system or in the UnifiedActivity format.</span></span> <span data-ttu-id="16a4c-150">Lấy định dạng bằng cách thực hiện cuộc gọi API tới /api/instances/{instanceId}/manage/entities/UnifiedActivity.</span><span class="sxs-lookup"><span data-stu-id="16a4c-150">Get the format by making an API call to /api/instances/{instanceId}/manage/entities/UnifiedActivity.</span></span>

<span data-ttu-id="16a4c-151">Thông tin chi tiết về API này, bao gồm các thông số và phản hồi, có thể được tìm thấy trong phần **EntityData** trên [Tham chiếu API Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span><span class="sxs-lookup"><span data-stu-id="16a4c-151">Details of this API, including parameters and responses, can be found in the **EntityData** section on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="16a4c-152">Để biết thêm thông tin, hãy xem [Làm việc với API Customer Insights](apis.md).</span><span class="sxs-lookup"><span data-stu-id="16a4c-152">For more information, see [Work with Customer Insights APIs](apis.md).</span></span>

## <a name="understand-your-real-time-usage-with-telemetry"></a><span data-ttu-id="16a4c-153">Tìm hiểu cách sử dụng trong thời gian thực với phương pháp đo từ xa</span><span class="sxs-lookup"><span data-stu-id="16a4c-153">Understand your real-time usage with telemetry</span></span>

<span data-ttu-id="16a4c-154">Xem tổng quan về khối lượng yêu cầu tới API thời gian thực và thông tin về các vấn đề mà hệ thống có thể gặp phải.</span><span class="sxs-lookup"><span data-stu-id="16a4c-154">Get an overview of the volume of requests to the real-time API and information about issues the system may encounter.</span></span> <span data-ttu-id="16a4c-155">Bạn có thể [truy cập máy đo từ xa thời gian thực](system.md#api-usage-tab).</span><span class="sxs-lookup"><span data-stu-id="16a4c-155">You can [access the real-time telemetry](system.md#api-usage-tab).</span></span> 


[!INCLUDE[footer-include](../includes/footer-banner.md)]