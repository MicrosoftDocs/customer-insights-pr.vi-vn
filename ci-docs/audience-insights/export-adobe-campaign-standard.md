---
title: Xuất dữ liệu Customer Insights sang Adobe Campaign Standard
description: Tìm hiểu cách sử dụng phân đoạn thông tin chi tiết về đối tượng trong Adobe Campaign Standard.
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: a5d0154c3d7c473dcba03fac0847bafcf97de2f2
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596341"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a><span data-ttu-id="92c2a-103">Sử dụng phân đoạn Customer Insights trong Adobe Campaign Standard (xem trước)</span><span class="sxs-lookup"><span data-stu-id="92c2a-103">Use Customer Insights segments in Adobe Campaign Standard (preview)</span></span>

<span data-ttu-id="92c2a-104">Là người dùng thông tin chi tiết đối tượng trong Dynamics 365 Customer Insights, bạn có thể đã tạo các phân khúc để chiến dịch tiếp thị trở nên hiệu quả hơn bằng cách nhắm mục tiêu các đối tượng phù hợp.</span><span class="sxs-lookup"><span data-stu-id="92c2a-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="92c2a-105">Để sử dụng phân khúc từ thông tin chi tiết đối tượng trong Nền tảng trải nghiệm Adobe và các ứng dụng như Adobe Campaign Standard, bạn cần làm theo một vài bước nêu trong bài viết này.</span><span class="sxs-lookup"><span data-stu-id="92c2a-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/ACS-flow.png" alt-text="Sơ đồ quy trình các bước nêu trong bài viết này.":::

## <a name="prerequisites"></a><span data-ttu-id="92c2a-107">Điều kiện tiên quyết</span><span class="sxs-lookup"><span data-stu-id="92c2a-107">Prerequisites</span></span>

-   <span data-ttu-id="92c2a-108">Giấy phép Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="92c2a-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="92c2a-109">Giấy phép Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="92c2a-109">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="92c2a-110">Tài khoản lưu trữ Azure Blob</span><span class="sxs-lookup"><span data-stu-id="92c2a-110">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="92c2a-111">Tổng quan Chiến dịch</span><span class="sxs-lookup"><span data-stu-id="92c2a-111">Campaign Overview</span></span>

<span data-ttu-id="92c2a-112">Để hiểu rõ hơn về cách bạn có thể sử dụng các phân khúc từ thông tin chi tiết về đối tượng trong Nền tảng trải nghiệm Adobe, hãy xem một chiến dịch mẫu giả tưởng.</span><span class="sxs-lookup"><span data-stu-id="92c2a-112">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="92c2a-113">Giả sử rằng công ty của bạn cung cấp dịch vụ dựa trên đăng ký hàng tháng cho khách hàng của bạn ở Hoa Kỳ.</span><span class="sxs-lookup"><span data-stu-id="92c2a-113">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="92c2a-114">Bạn muốn xác định những khách hàng có đăng ký sẽ đến hạn gia hạn trong 8 ngày tới nhưng chưa gia hạn đăng ký của họ.</span><span class="sxs-lookup"><span data-stu-id="92c2a-114">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="92c2a-115">Để giữ chân những khách hàng này, bạn nên gửi khuyến mại cho họ qua email, sử dụng Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="92c2a-115">To keep these customers, you want to send them a promotional offer via email, using Adobe Campaign Standard.</span></span>

<span data-ttu-id="92c2a-116">Trong ví dụ này, chúng tôi muốn chạy chiến dịch email quảng cáo một lần.</span><span class="sxs-lookup"><span data-stu-id="92c2a-116">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="92c2a-117">Bài viết này không đề cập đến trường hợp sử dụng của việc chạy chiến dịch nhiều lần.</span><span class="sxs-lookup"><span data-stu-id="92c2a-117">This article doesn’t cover the use-case of running the campaign more than once.</span></span> <span data-ttu-id="92c2a-118">Tuy nhiên, thông tin chi tiết về đối tượng và Adobe Campaign Standard cũng có thể được định cấu hình để hoạt động cho một kịch bản chiến dịch lặp lại.</span><span class="sxs-lookup"><span data-stu-id="92c2a-118">However, audience insights and Adobe Campaign Standard can be configured to work for a recurring campaign scenario too.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="92c2a-119">Xác định đối tượng mục tiêu của bạn</span><span class="sxs-lookup"><span data-stu-id="92c2a-119">Identify your target audience</span></span>

<span data-ttu-id="92c2a-120">Trong kịch bản của chúng tôi, chúng tôi giả định rằng địa chỉ email của khách hàng có sẵn trong thông tin chi tiết về đối tượng và các sở thích khuyến mại của họ đã được phân tích để xác định các thành viên của phân khúc.</span><span class="sxs-lookup"><span data-stu-id="92c2a-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="92c2a-121">[Phân khúc bạn đã xác định trong thông tin chi tiết về đối tượng](segments.md) được gọi là **ChurnProneCustomers** và bạn dự định gửi những khách hàng này ưu đãi qua email.</span><span class="sxs-lookup"><span data-stu-id="92c2a-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Ảnh chụp màn hình của trang phân khúc đã tạo phân khúc ChurnProneCustomers.":::

<span data-ttu-id="92c2a-123">Email ưu đãi mà bạn muốn gửi sẽ chứa tên, họ, và ngày kết thúc đăng ký của khách hàng.</span><span class="sxs-lookup"><span data-stu-id="92c2a-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="92c2a-124">Email đó thông báo cho khách hàng về khoản chiết khấu mà họ sẽ nhận được nếu họ gia hạn đăng ký trước khi nó kết thúc.</span><span class="sxs-lookup"><span data-stu-id="92c2a-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="92c2a-125">Xuất đối tượng mục tiêu của bạn</span><span class="sxs-lookup"><span data-stu-id="92c2a-125">Export your target audience</span></span>

<span data-ttu-id="92c2a-126">Với đối tượng mục tiêu đã được xác định, chúng tôi có thể định cấu hình xuất từ thông tin chi tiết về đối tượng sang tài khoản Lưu trữ Azure Blob.</span><span class="sxs-lookup"><span data-stu-id="92c2a-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="92c2a-127">Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Quản trị viên** > **Nơi xuất đích**.</span><span class="sxs-lookup"><span data-stu-id="92c2a-127">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="92c2a-128">Trong ngăn xếp **Adobe Campaign**, chọn **Thiết lập**.</span><span class="sxs-lookup"><span data-stu-id="92c2a-128">In the **Adobe Campaign** tile, select **Set up**.</span></span>

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Ngăn xếp cấu hình cho Adobe Campaign Standard.":::

1. <span data-ttu-id="92c2a-130">Cung cấp **Tên hiển thị** cho đích xuất mới này rồi nhập **Tên tài khoản**, **Khóa tài khoản** và **Vùng chứa** của tài khoản Lưu trữ Azure Blob nơi bạn muốn xuất phân khúc.</span><span class="sxs-lookup"><span data-stu-id="92c2a-130">Provide a **Display name** for this new export destination and then enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Ảnh chụp màn hình cấu hình tài khoản lưu trữ. "::: 

   - <span data-ttu-id="92c2a-132">Để biết cách tìm tên tài khoản và mã tài khoản Azure Blob Storage, hãy xem [Quản lý tùy chọn cài đặt của tài khoản lưu trữ trong cổng Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="92c2a-132">To learn more about how to find the Azure Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="92c2a-133">Để tìm hiểu cách tạo bộ chứa, hãy xem [Tạo bộ chứa](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="92c2a-133">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="92c2a-134">Chọn **Tiếp theo**.</span><span class="sxs-lookup"><span data-stu-id="92c2a-134">Select **Next**.</span></span>

1. <span data-ttu-id="92c2a-135">Chọn phân khúc mà bạn muốn xuất.</span><span class="sxs-lookup"><span data-stu-id="92c2a-135">Choose the segment that you want to export.</span></span> <span data-ttu-id="92c2a-136">Trong ví dụ này, phân khúc đó là **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="92c2a-136">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Ảnh chụp màn hình giao diện người dùng chọn phân phúc đã chọn phân khúc ChurnProneCustomers.":::

1. <span data-ttu-id="92c2a-138">Chọn **Tiếp theo**.</span><span class="sxs-lookup"><span data-stu-id="92c2a-138">Select **Next**.</span></span>

1. <span data-ttu-id="92c2a-139">Bây giờ, chúng ta sẽ lập bản đồ trường **Nguồn** từ phân khúc thông tin chi tiết đối tượng đến tên trường **Đích** trong sơ đồ hồ sơ Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="92c2a-139">Now we map the **Source** fields from the audience insights segment to the **Target** field names in the Adobe Campaign Standard profile schema.</span></span>

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Ánh xạ trường cho trình kết nối Adobe Campaign Standard.":::

   <span data-ttu-id="92c2a-141">Nếu bạn muốn thêm nhiều thuộc tính, hãy chọn **Thêm thuộc tính**.</span><span class="sxs-lookup"><span data-stu-id="92c2a-141">If you want to add more attributes, select **Add attribute**.</span></span> <span data-ttu-id="92c2a-142">Tên mục tiêu có thể khác với tên trường nguồn để bạn vẫn có thể ánh xạ đầu ra của phân khúc từ thông tin chi tiết về đối tượng sang Adobe Campaign Standard nếu các trường không có cùng tên trong hai hệ thống.</span><span class="sxs-lookup"><span data-stu-id="92c2a-142">The target name can be different from the source field name so you can still map segment output from audience insights to Adobe Campaign Standard if the fields don’t have the same name in the two systems.</span></span>

   > [!NOTE]
   > <span data-ttu-id="92c2a-143">Địa chỉ email được sử dụng làm trường nhận dạng, nhưng bạn có thể sử dụng bất kỳ số nhận dạng nào khác từ đối tượng của bạn thông tin chi tiết về hồ sơ khách hàng để ánh xạ dữ liệu tới Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="92c2a-143">Email address is used as an identity field but you can use any other identifier from your audience insights customer profile to map data to Adobe Campaign Standard.</span></span>

1. <span data-ttu-id="92c2a-144">Chọn **Lưu**.</span><span class="sxs-lookup"><span data-stu-id="92c2a-144">Select **Save**.</span></span>

<span data-ttu-id="92c2a-145">Sau khi lưu đích xuất, bạn sẽ tìm thấy trên **Quản trị** > **Xuất** > **Đích xuất**.</span><span class="sxs-lookup"><span data-stu-id="92c2a-145">After saving the export destination, you find it on **Admin** > **Exports** > **My export destinations**.</span></span>

:::image type="content" source="media/export-destination-adobe-campaign-standard.png" alt-text="Ảnh chụp màn hình với danh sách các mục xuất và phân khúc mẫu được đánh dấu.":::

<span data-ttu-id="92c2a-147">Bây giờ, bạn có thể [xuất phân khúc theo yêu cầu](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="92c2a-147">You can now [export the segment on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="92c2a-148">Mỗi lần [làm mới theo lịch](system.md), tác vụ xuất cũng sẽ chạy.</span><span class="sxs-lookup"><span data-stu-id="92c2a-148">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="92c2a-149">Đảm bảo rằng số lượng bản ghi trong phân khúc đã xuất nằm trong giới hạn cho phép của giấy phép Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="92c2a-149">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="92c2a-150">Dữ liệu đã xuất được lưu trữ trong vùng chứa Azure Blob mà bạn đã định cấu hình ở trên.</span><span class="sxs-lookup"><span data-stu-id="92c2a-150">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="92c2a-151">Đường dẫn thư mục sau được tạo tự động trong vùng chứa của bạn:</span><span class="sxs-lookup"><span data-stu-id="92c2a-151">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="92c2a-152">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span><span class="sxs-lookup"><span data-stu-id="92c2a-152">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span></span>

<span data-ttu-id="92c2a-153">Ví dụ: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span><span class="sxs-lookup"><span data-stu-id="92c2a-153">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span></span>

## <a name="configure-adobe-campaign-standard"></a><span data-ttu-id="92c2a-154">Đặt cấu hình Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="92c2a-154">Configure Adobe Campaign Standard</span></span>

<span data-ttu-id="92c2a-155">Khi một phân khúc từ thông tin chi tiết về đối tượng được xuất, phân khúc đó chứa các cột bạn đã chọn trong khi xác định đích xuất ở bước trước.</span><span class="sxs-lookup"><span data-stu-id="92c2a-155">When a segment from audience insights is exported, it contains the columns you selected while defining the export destination in the previous step.</span></span> <span data-ttu-id="92c2a-156">Dữ liệu này có thể được dùng để [tạo hồ sơ trong Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span><span class="sxs-lookup"><span data-stu-id="92c2a-156">This data can be used to [create profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span></span>

<span data-ttu-id="92c2a-157">Để sử dụng phân khúc trong Adobe Campaign Standard, chúng ta cần mở rộng sơ đồ hồ sơ trong Adobe Campaign Standard để bao gồm hai trường bổ sung.</span><span class="sxs-lookup"><span data-stu-id="92c2a-157">To use the segment in Adobe Campaign Standard, we need to extend the profile schema in Adobe Campaign Standard to include two additional fields.</span></span> <span data-ttu-id="92c2a-158">Tìm hiểu cách [mở rộng tài nguyên hồ sơ](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) với các trường mới trong Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="92c2a-158">Learn how to [extend the profile resource](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) with new fields in Adobe Campaign Standard.</span></span>

<span data-ttu-id="92c2a-159">Trong ví dụ của chúng tôi các trường này là *Tên phân khúc và ngày phân khúc (tùy chọn).*</span><span class="sxs-lookup"><span data-stu-id="92c2a-159">In our example, these fields are *Segment Name and Segment Date (optional).*</span></span>

<span data-ttu-id="92c2a-160">Chúng tôi sẽ sử dụng các trường này để xác định những hồ sơ trong Adobe Campaign Standard mà chúng tôi muốn nhắm mục tiêu cho chiến dịch này.</span><span class="sxs-lookup"><span data-stu-id="92c2a-160">We will use these fields to identify the profiles in Adobe Campaign Standard we want to target for this campaign.</span></span>

<span data-ttu-id="92c2a-161">Nếu không có bản ghi nào khác trong Adobe Campaign Standard, ngoài những gì bạn sẽ nhập, bạn có thể bỏ qua bước này.</span><span class="sxs-lookup"><span data-stu-id="92c2a-161">If there are no other records in Adobe Campaign Standard, other than what you are going to import, you can skip this step.</span></span>

## <a name="import-data-into-adobe-campaign-standard"></a><span data-ttu-id="92c2a-162">Nhập dữ liệu vào Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="92c2a-162">Import data into Adobe Campaign Standard</span></span>

<span data-ttu-id="92c2a-163">Bây giờ mọi thứ đã sẵn sàng, chúng tôi cần nhập dữ liệu đối tượng đã chuẩn bị từ thông tin chi tiết về đối tượng vào Adobe Campaign Standard để tạo hồ sơ.</span><span class="sxs-lookup"><span data-stu-id="92c2a-163">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Campaign Standard to create profiles.</span></span> <span data-ttu-id="92c2a-164">Tìm hiểu [cách nhập hồ sơ trong Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) bằng quy trình làm việc.</span><span class="sxs-lookup"><span data-stu-id="92c2a-164">Learn [how to import profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) using a workflow.</span></span>

<span data-ttu-id="92c2a-165">Quy trình nhập trong hình ảnh bên dưới đã được định cấu hình để chạy 8 giờ một lần và tìm kiếm các phân khúc thông tin chi tiết về đối tượng được xuất (tệp .csv trong Azure Blob Storage).</span><span class="sxs-lookup"><span data-stu-id="92c2a-165">The import workflow in the image below has been configured to run every 8 hours and looks for exported audience insights segments (.csv file in Azure Blob Storage).</span></span> <span data-ttu-id="92c2a-166">Dòng công việc trích xuất nội dung tệp .csv theo thứ tự cột được chỉ định.</span><span class="sxs-lookup"><span data-stu-id="92c2a-166">The workflow extracts the .csv file content in a specified column order.</span></span> <span data-ttu-id="92c2a-167">Quy trình làm việc này đã được xây dựng để thực hiện xử lý lỗi cơ bản và đảm bảo rằng mỗi bản ghi đều có địa chỉ email trước khi cung cấp dữ liệu trong Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="92c2a-167">This workflow has been built to perform basic error handling and ensure that each record has an email address before hydrating the data in Adobe Campaign Standard.</span></span> <span data-ttu-id="92c2a-168">Dòng công việc cũng trích xuất tên phân khúc từ tên tệp trước khi bổ sung vào dữ liệu Hồ sơ ACS.</span><span class="sxs-lookup"><span data-stu-id="92c2a-168">The workflow also extracts the segment name from the filename before upserting into ACS Profile data.</span></span>

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Ảnh chụp màn hình quy trình nhập trong giao diện người dùng Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a><span data-ttu-id="92c2a-170">Truy xuất đối tượng trong Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="92c2a-170">Retrieve the audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="92c2a-171">Sau khi dữ liệu được nhập vào Adobe Campaign Standard, bạn [có thể tạo quy trình là việc](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) và [truy vấn](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) khách hàng dựa trên *Tên phân khúc* và *Ngày phân khúc* để chọn các hồ sơ đã được xác định cho chiến dịch mẫu của chúng tôi.</span><span class="sxs-lookup"><span data-stu-id="92c2a-171">Once the data is imported into Adobe Campaign Standard, you [can create a workflow](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) and [query](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) the customers based on the *Segment Name* and *Segment Date* to select profiles that were identified for our sample campaign.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="92c2a-172">Tạo và gửi email bằng Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="92c2a-172">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="92c2a-173">Tạo nội dung email rồi [thử nghiệm và gửi](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) email của bạn.</span><span class="sxs-lookup"><span data-stu-id="92c2a-173">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Email mẫu với đề nghị gia hạn từ Adobe Campaign Standard.":::