---
title: Xuất dữ liệu Customer Insights vào nền tảng trải nghiệm Adobe
description: Tìm hiểu cách sử dụng phân khúc thông tin chi tiết về đối tượng trong Nền tảng trải nghiệm Adobe.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 884f4d30f354bed29909d57be84dce4c8e46965a
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760127"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a><span data-ttu-id="ae116-103">Sử dụng phân khúc Customer Insights trong nền tảng trải nghiệm Adobe (xem trước)</span><span class="sxs-lookup"><span data-stu-id="ae116-103">Use Customer Insights segments in Adobe Experience Platform (preview)</span></span>

<span data-ttu-id="ae116-104">Là người dùng thông tin chi tiết đối tượng trong Dynamics 365 Customer Insights, bạn có thể đã tạo các phân khúc để chiến dịch tiếp thị trở nên hiệu quả hơn bằng cách nhắm mục tiêu các đối tượng phù hợp.</span><span class="sxs-lookup"><span data-stu-id="ae116-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="ae116-105">Để sử dụng phân khúc từ thông tin chi tiết đối tượng trong Nền tảng trải nghiệm Adobe và các ứng dụng như Adobe Campaign Standard, bạn cần làm theo một vài bước nêu trong bài viết này.</span><span class="sxs-lookup"><span data-stu-id="ae116-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/AEP-flow.png" alt-text="Sơ đồ quy trình các bước nêu trong bài viết này.":::

## <a name="prerequisites"></a><span data-ttu-id="ae116-107">Điều kiện tiên quyết</span><span class="sxs-lookup"><span data-stu-id="ae116-107">Prerequisites</span></span>

-   <span data-ttu-id="ae116-108">Giấy phép Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="ae116-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="ae116-109">Giấy phép Nền tảng Trải nghiệm Adobe</span><span class="sxs-lookup"><span data-stu-id="ae116-109">Adobe Experience Platform license</span></span>
-   <span data-ttu-id="ae116-110">Giấy phép Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="ae116-110">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="ae116-111">Tài khoản lưu trữ Azure Blob</span><span class="sxs-lookup"><span data-stu-id="ae116-111">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="ae116-112">Tổng quan Chiến dịch</span><span class="sxs-lookup"><span data-stu-id="ae116-112">Campaign Overview</span></span>

<span data-ttu-id="ae116-113">Để hiểu rõ hơn về cách bạn có thể sử dụng các phân khúc từ thông tin chi tiết về đối tượng trong Nền tảng trải nghiệm Adobe, hãy xem một chiến dịch mẫu giả tưởng.</span><span class="sxs-lookup"><span data-stu-id="ae116-113">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="ae116-114">Giả sử rằng công ty của bạn cung cấp dịch vụ dựa trên đăng ký hàng tháng cho khách hàng của bạn ở Hoa Kỳ.</span><span class="sxs-lookup"><span data-stu-id="ae116-114">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="ae116-115">Bạn muốn xác định những khách hàng có đăng ký sẽ đến hạn gia hạn trong 8 ngày tới nhưng chưa gia hạn đăng ký của họ.</span><span class="sxs-lookup"><span data-stu-id="ae116-115">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="ae116-116">Để giữ chân những khách hàng này, bạn nên gửi khuyến mại cho họ qua email, sử dụng Nền tảng trải nghiệm Adobe.</span><span class="sxs-lookup"><span data-stu-id="ae116-116">To keep these customers, you want to send them a promotional offer via email, using Adobe Experience Platform.</span></span>

<span data-ttu-id="ae116-117">Trong ví dụ này, chúng tôi muốn chạy chiến dịch email quảng cáo một lần.</span><span class="sxs-lookup"><span data-stu-id="ae116-117">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="ae116-118">Bài viết này không đề cập đến trường hợp sử dụng của việc chạy chiến dịch nhiều lần.</span><span class="sxs-lookup"><span data-stu-id="ae116-118">This article doesn’t cover the use-case of running the campaign more than once.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="ae116-119">Xác định đối tượng mục tiêu của bạn</span><span class="sxs-lookup"><span data-stu-id="ae116-119">Identify your target audience</span></span>

<span data-ttu-id="ae116-120">Trong kịch bản của chúng tôi, chúng tôi giả định rằng địa chỉ email của khách hàng có sẵn trong thông tin chi tiết về đối tượng và các sở thích khuyến mại của họ đã được phân tích để xác định các thành viên của phân khúc.</span><span class="sxs-lookup"><span data-stu-id="ae116-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="ae116-121">[Phân khúc bạn đã xác định trong thông tin chi tiết về đối tượng](segments.md) được gọi là **ChurnProneCustomers** và bạn dự định gửi những khách hàng này ưu đãi qua email.</span><span class="sxs-lookup"><span data-stu-id="ae116-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Ảnh chụp màn hình của trang phân khúc đã tạo phân khúc ChurnProneCustomers.":::

<span data-ttu-id="ae116-123">Email ưu đãi mà bạn muốn gửi sẽ chứa tên, họ, và ngày kết thúc đăng ký của khách hàng.</span><span class="sxs-lookup"><span data-stu-id="ae116-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="ae116-124">Email đó thông báo cho khách hàng về khoản chiết khấu mà họ sẽ nhận được nếu họ gia hạn đăng ký trước khi nó kết thúc.</span><span class="sxs-lookup"><span data-stu-id="ae116-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="ae116-125">Xuất đối tượng mục tiêu của bạn</span><span class="sxs-lookup"><span data-stu-id="ae116-125">Export your target audience</span></span>

<span data-ttu-id="ae116-126">Với đối tượng mục tiêu đã được xác định, chúng tôi có thể định cấu hình xuất từ thông tin chi tiết về đối tượng sang tài khoản Lưu trữ Azure Blob.</span><span class="sxs-lookup"><span data-stu-id="ae116-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="ae116-127">Đặt cấu hình kết nối</span><span class="sxs-lookup"><span data-stu-id="ae116-127">Configure a connection</span></span>

1. <span data-ttu-id="ae116-128">Đi đến **Quản trị viên** > **Kết nối**.</span><span class="sxs-lookup"><span data-stu-id="ae116-128">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="ae116-129">Chọn **Thêm kết nối** rồi chọn **Azure Blob Storage** hoặc chọn **Thiết lập** trong ngăn xếp **Azure Blob Storage**:</span><span class="sxs-lookup"><span data-stu-id="ae116-129">Select **Add connection** and choose **Azure Blob Storage** or select **Set up** in the **Azure Blob Storage** tile:</span></span>

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Ngăn xếp cấu hình cho Lưu trữ Azure Blob."::: <span data-ttu-id="ae116-131">để đặt cấu hình kết nối.</span><span class="sxs-lookup"><span data-stu-id="ae116-131">to configure the connection.</span></span>

1. <span data-ttu-id="ae116-132">Đặt tên dễ nhận biết cho kết nối trong trường **Tên hiển thị**.</span><span class="sxs-lookup"><span data-stu-id="ae116-132">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="ae116-133">Tên và loại kết nối mô tả kết nối này.</span><span class="sxs-lookup"><span data-stu-id="ae116-133">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="ae116-134">Bạn nên chọn một tên giải thích mục đích và mục tiêu của kết nối.</span><span class="sxs-lookup"><span data-stu-id="ae116-134">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="ae116-135">Chọn người có thể sử dụng kết nối này.</span><span class="sxs-lookup"><span data-stu-id="ae116-135">Choose who can use this connection.</span></span> <span data-ttu-id="ae116-136">Nếu bạn không thực hiện hành động nào, giá trị mặc định sẽ là Quản trị viên.</span><span class="sxs-lookup"><span data-stu-id="ae116-136">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="ae116-137">Để biết thêm thông tin, hãy xem [Cho phép người đóng góp sử dụng một kết nối cho các lần xuất](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="ae116-137">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="ae116-138">Nhập **Tên tài khoản**, **Khóa tài khoản** và **Bộ chứa** của tài khoản lưu trữ Blog mà bạn muốn xuất phân khúc sang.</span><span class="sxs-lookup"><span data-stu-id="ae116-138">Enter **Account name**, **Account key**, and **Container** for your Blob storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Ảnh chụp màn hình cấu hình tài khoản lưu trữ. "::: 
   
    - <span data-ttu-id="ae116-140">Để tìm hiểu thêm về cách tìm tên tài khoản lưu trữ Blob và khóa tài khoản, hãy xem [Quản lý các thiết đặt tài khoản lưu trữ trong cổng thông tin Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="ae116-140">To learn more about how to find the Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>
    - <span data-ttu-id="ae116-141">Để tìm hiểu cách tạo bộ chứa, hãy xem [Tạo bộ chứa](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="ae116-141">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="ae116-142">Chọn **Lưu** để hoàn thành kết nối.</span><span class="sxs-lookup"><span data-stu-id="ae116-142">Select **Save** to complete the connection.</span></span> 

### <a name="configure-an-export"></a><span data-ttu-id="ae116-143">Đặt cấu hình xuất</span><span class="sxs-lookup"><span data-stu-id="ae116-143">Configure an export</span></span>

<span data-ttu-id="ae116-144">Bạn có thể đặt cấu hình lần xuất này nếu bạn có quyền truy cập vào kết nối thuộc loại này.</span><span class="sxs-lookup"><span data-stu-id="ae116-144">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="ae116-145">Để biết thêm thông tin, hãy xem [Các quyền cần thiết để đặt cấu hình xuất](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="ae116-145">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="ae116-146">Đi tới **Dữ liệu** > **Nội dung xuất**.</span><span class="sxs-lookup"><span data-stu-id="ae116-146">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="ae116-147">Để tạo nội dung xuất mới, hãy chọn **Thêm nội dung xuất**.</span><span class="sxs-lookup"><span data-stu-id="ae116-147">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="ae116-148">Trong trường **Kết nối để xuất**, hãy chọn một kết nối từ phần Azure Blob Storage.</span><span class="sxs-lookup"><span data-stu-id="ae116-148">In the **Connection for export** field, choose a connection from the Azure Blob Storage section.</span></span> <span data-ttu-id="ae116-149">Nếu bạn không thấy tên phần này, tức là không có kết nối nào thuộc loại này dành cho bạn.</span><span class="sxs-lookup"><span data-stu-id="ae116-149">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="ae116-150">Chọn phân khúc mà bạn muốn xuất.</span><span class="sxs-lookup"><span data-stu-id="ae116-150">Choose the segment that you want to export.</span></span> <span data-ttu-id="ae116-151">Trong ví dụ này, phân khúc đó là **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="ae116-151">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Ảnh chụp màn hình giao diện người dùng chọn phân phúc đã chọn phân khúc ChurnProneCustomers.":::

1. <span data-ttu-id="ae116-153">Chọn **Lưu**.</span><span class="sxs-lookup"><span data-stu-id="ae116-153">Select **Save**.</span></span>

<span data-ttu-id="ae116-154">Sau khi lưu đích xuất, bạn sẽ thấy đích này trên **Dữ liệu** > **Nội dung xuất**.</span><span class="sxs-lookup"><span data-stu-id="ae116-154">After saving the export destination, you find it on **Data** > **Exports**.</span></span>

<span data-ttu-id="ae116-155">Bây giờ, bạn có thể [xuất phân khúc theo yêu cầu](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="ae116-155">You can now [export the segment on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="ae116-156">Mỗi lần [làm mới theo lịch](system.md), tác vụ xuất cũng sẽ chạy.</span><span class="sxs-lookup"><span data-stu-id="ae116-156">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="ae116-157">Đảm bảo rằng số lượng bản ghi trong phân khúc đã xuất nằm trong giới hạn cho phép của giấy phép Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="ae116-157">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="ae116-158">Dữ liệu đã xuất được lưu trữ trong vùng chứa Azure Blob mà bạn đã định cấu hình ở trên.</span><span class="sxs-lookup"><span data-stu-id="ae116-158">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="ae116-159">Đường dẫn thư mục sau được tạo tự động trong vùng chứa của bạn:</span><span class="sxs-lookup"><span data-stu-id="ae116-159">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="ae116-160">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span><span class="sxs-lookup"><span data-stu-id="ae116-160">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span></span>

<span data-ttu-id="ae116-161">Ví dụ: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span><span class="sxs-lookup"><span data-stu-id="ae116-161">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span></span>

<span data-ttu-id="ae116-162">*model.json* cho các thực thể đã xuất có ở cấp độ *%ExportDestinationName%*.</span><span class="sxs-lookup"><span data-stu-id="ae116-162">The *model.json* for the exported entities resides at the *%ExportDestinationName%* level.</span></span>

<span data-ttu-id="ae116-163">Ví dụ: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span><span class="sxs-lookup"><span data-stu-id="ae116-163">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span></span>

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a><span data-ttu-id="ae116-164">Xác định mô hình dữ liệu trải nghiệm Experience Data Model (XDM) trong Nền tảng trải nghiệm Adobe</span><span class="sxs-lookup"><span data-stu-id="ae116-164">Define Experience Data Model (XDM) in Adobe Experience Platform</span></span>

<span data-ttu-id="ae116-165">Trước khi dữ liệu đã xuất từ audience insights có thể được dùng với Nền tảng trải nghiệm Adobe, chúng ta cần xác định lược đồ Mô hình dữ liệu trải nghiệm và [định cấu hình dữ liệu cho Hồ sơ khách hàng trong thời gian thực](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span><span class="sxs-lookup"><span data-stu-id="ae116-165">Before the exported data from audience insights can be used within Adobe Experience Platform, we need to define the Experience Data Model schema and [configure the data for the Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span></span>

<span data-ttu-id="ae116-166">Tìm hiểu [XDM là gì](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) và hiểu [thông tin cơ bản về thành phần lược đồ](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span><span class="sxs-lookup"><span data-stu-id="ae116-166">Learn [what XDM is](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) and understand the [basics of schema composition](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span></span>

## <a name="import-data-into-adobe-experience-platform"></a><span data-ttu-id="ae116-167">Nhập dữ liệu vào Nền tảng Trải nghiệm Adobe</span><span class="sxs-lookup"><span data-stu-id="ae116-167">Import data into Adobe Experience Platform</span></span>

<span data-ttu-id="ae116-168">Bây giờ mọi thứ đã sẵn sàng, chúng tôi cần nhập dữ liệu đối tượng đã chuẩn bị từ thông tin chi tiết về đối tượng vào Nền tảng trải nghiệm Adobe.</span><span class="sxs-lookup"><span data-stu-id="ae116-168">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Experience Platform.</span></span>

<span data-ttu-id="ae116-169">Đầu tiên, [tạo kết nối nguồn lưu trữ Azure Blob](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span><span class="sxs-lookup"><span data-stu-id="ae116-169">First, [create an Azure Blob Storage source connection](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span></span>    

<span data-ttu-id="ae116-170">Sau khi xác định kết nối nguồn, hãy [định cấu hình luồng dữ liệu](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) cho kết nối loạt lưu trữ đám mây để nhập kết quả phân khúc từ thông tin chi tiết về đối tượng vào Nền tảng trải nghiệm Adobe.</span><span class="sxs-lookup"><span data-stu-id="ae116-170">After defining the source connection, [configure a dataflow](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) for a cloud storage batch connection to import the segment output from audience insights into Adobe Experience Platform.</span></span>

## <a name="create-an-audience-in-adobe-campaign-standard"></a><span data-ttu-id="ae116-171">Tạo đối tượng trong Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="ae116-171">Create an audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="ae116-172">Để gửi email cho chiến dịch này, chúng tôi sẽ sử dụng Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="ae116-172">To send the email for this campaign, we will use Adobe Campaign Standard.</span></span> <span data-ttu-id="ae116-173">Sau khi nhập dữ liệu vào Nền tảng trải nghiệm Adobe, chúng ta cần [tạo đối tượng](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) trong Adobe Campaign Standard bằng dữ liệu trong Nền tảng trải nghiệm Adobe.</span><span class="sxs-lookup"><span data-stu-id="ae116-173">After importing the data into Adobe Experience Platform, we need to [create an audience](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) in Adobe Campaign Standard using the data in Adobe Experience Platform.</span></span>

<span data-ttu-id="ae116-174">Tìm hiểu cách [sử dụng trình tạo phân phúc](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) trong Adobe Campaign Standard để xác định đối tượng dựa trên dữ liệu trong Nền tảng trải nghiệm Adobe.</span><span class="sxs-lookup"><span data-stu-id="ae116-174">Learn how to [use segment builder](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) in Adobe Campaign Standard to define an audience based on the data in Adobe Experience Platform.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="ae116-175">Tạo và gửi email bằng Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="ae116-175">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="ae116-176">Tạo nội dung email rồi [thử nghiệm và gửi](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) email của bạn.</span><span class="sxs-lookup"><span data-stu-id="ae116-176">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Email mẫu với đề nghị gia hạn từ Adobe Campaign Standard.":::
