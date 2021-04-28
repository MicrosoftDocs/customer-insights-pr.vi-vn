---
title: Xuất dữ liệu Customer Insights sang Azure Blob Storage
description: Tìm hiểu cách đặt cấu hình kết nối và xuất sang bộ lưu trữ Blob.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 294feff2f77c3756fbadb36c90aab430454f5967
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760261"
---
# <a name="export-segment-list-and-other-data-to-azure-blob-storage-preview"></a><span data-ttu-id="8beae-103">Xuất danh sách phân khúc và dữ liệu khác sang Azure Blob Storage (bản xem trước)</span><span class="sxs-lookup"><span data-stu-id="8beae-103">Export segment list and other data to Azure Blob Storage (preview)</span></span>

<span data-ttu-id="8beae-104">Lưu trữ dữ liệu Customer Insights của bạn trong bộ lưu trữ Blob hoặc sử dụng bộ lưu trữ đó để chuyển dữ liệu của bạn sang các ứng dụng khác.</span><span class="sxs-lookup"><span data-stu-id="8beae-104">Store your Customer Insights data in a Blob storage or use it to transfer your data to other applications.</span></span>

## <a name="set-up-the-connection-to-blob-storage"></a><span data-ttu-id="8beae-105">Thiết lập kết nối với bộ lưu trữ Blob</span><span class="sxs-lookup"><span data-stu-id="8beae-105">Set up the connection to Blob storage</span></span>

1. <span data-ttu-id="8beae-106">Đi đến **Quản trị viên** > **Kết nối**.</span><span class="sxs-lookup"><span data-stu-id="8beae-106">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="8beae-107">Chọn **Thêm kết nối** rồi chọn **Azure Blob Storage** để đặt cấu hình kết nối.</span><span class="sxs-lookup"><span data-stu-id="8beae-107">Select **Add connection** and choose **Azure Blob Storage** to configure the connection.</span></span>

1. <span data-ttu-id="8beae-108">Đặt tên dễ nhận biết cho kết nối trong trường **Tên hiển thị**.</span><span class="sxs-lookup"><span data-stu-id="8beae-108">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="8beae-109">Tên và loại kết nối mô tả kết nối này.</span><span class="sxs-lookup"><span data-stu-id="8beae-109">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="8beae-110">Bạn nên chọn một tên giải thích mục đích và mục tiêu của kết nối.</span><span class="sxs-lookup"><span data-stu-id="8beae-110">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="8beae-111">Chọn người có thể sử dụng kết nối này.</span><span class="sxs-lookup"><span data-stu-id="8beae-111">Choose who can use this connection.</span></span> <span data-ttu-id="8beae-112">Nếu bạn không thực hiện hành động nào, giá trị mặc định sẽ là Quản trị viên.</span><span class="sxs-lookup"><span data-stu-id="8beae-112">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="8beae-113">Để biết thêm thông tin, hãy xem [Cho phép người đóng góp sử dụng một kết nối cho các lần xuất](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="8beae-113">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="8beae-114">Nhập **Tên tài khoản**, **Khóa tài khoản** và **Bộ chứa** cho tài khoản lưu trữ Blob của bạn.</span><span class="sxs-lookup"><span data-stu-id="8beae-114">Enter **Account name**, **Account key**, and **Container** for your Blob storage account.</span></span>
    - <span data-ttu-id="8beae-115">Để tìm hiểu thêm về cách tìm tên tài khoản lưu trữ Blob và khóa tài khoản, hãy xem [Quản lý các thiết đặt tài khoản lưu trữ trong cổng thông tin Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="8beae-115">To learn more about how to find the Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>
    - <span data-ttu-id="8beae-116">Để tìm hiểu cách tạo bộ chứa, hãy xem [Tạo bộ chứa](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="8beae-116">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="8beae-117">Chọn **Lưu** để hoàn thành kết nối.</span><span class="sxs-lookup"><span data-stu-id="8beae-117">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="8beae-118">Đặt cấu hình xuất</span><span class="sxs-lookup"><span data-stu-id="8beae-118">Configure an export</span></span>

<span data-ttu-id="8beae-119">Bạn có thể đặt cấu hình lần xuất này nếu bạn có quyền truy cập vào kết nối thuộc loại này.</span><span class="sxs-lookup"><span data-stu-id="8beae-119">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="8beae-120">Để biết thêm thông tin, hãy xem [Các quyền cần thiết để đặt cấu hình xuất](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="8beae-120">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="8beae-121">Đi tới **Dữ liệu** > **Nội dung xuất**.</span><span class="sxs-lookup"><span data-stu-id="8beae-121">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="8beae-122">Để tạo một nội dung xuất mới, hãy chọn **Thêm đích**.</span><span class="sxs-lookup"><span data-stu-id="8beae-122">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="8beae-123">Trong trường **Kết nối để xuất**, hãy chọn một kết nối từ phần Azure Blob Storage.</span><span class="sxs-lookup"><span data-stu-id="8beae-123">In the **Connection for export** field, choose a connection from the Azure Blob Storage section.</span></span> <span data-ttu-id="8beae-124">Nếu bạn không thấy tên phần này, tức là không có kết nối nào thuộc loại này dành cho bạn.</span><span class="sxs-lookup"><span data-stu-id="8beae-124">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="8beae-125">Chọn ô cạnh mỗi thực thể mà bạn muốn xuất sang vị trí này.</span><span class="sxs-lookup"><span data-stu-id="8beae-125">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="8beae-126">Chọn **Lưu**.</span><span class="sxs-lookup"><span data-stu-id="8beae-126">Select **Save**.</span></span>

<span data-ttu-id="8beae-127">Việc lưu một nội dung xuất sẽ không chạy nội dung xuất đó ngay lập tức.</span><span class="sxs-lookup"><span data-stu-id="8beae-127">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="8beae-128">Nội dung xuất chạy trong mỗi lần [làm mới theo lịch trình](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="8beae-128">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span>     
<span data-ttu-id="8beae-129">Bạn cũng có thể [xuất dữ liệu theo yêu cầu](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="8beae-129">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

<span data-ttu-id="8beae-130">Dữ liệu đã xuất được lưu trữ trong bộ lưu trữ Blob mà bạn đã đặt cấu hình.</span><span class="sxs-lookup"><span data-stu-id="8beae-130">Exported data is stored in the Blob storage container you configured.</span></span> <span data-ttu-id="8beae-131">Đường dẫn thư mục sau đây sẽ tự động được tạo trong bộ chứa của bạn:</span><span class="sxs-lookup"><span data-stu-id="8beae-131">The following folder paths are automatically created in your container:</span></span>

- <span data-ttu-id="8beae-132">Đối với thực thể nguồn và thực thể do hệ thống tạo ra: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span><span class="sxs-lookup"><span data-stu-id="8beae-132">For source entities and entities generated by the system: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span></span>
  - <span data-ttu-id="8beae-133">Ví dụ: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span><span class="sxs-lookup"><span data-stu-id="8beae-133">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span></span>
- <span data-ttu-id="8beae-134">Tệp model.json cho các thực thể đã xuất sẽ ở cấp độ %ExportDestinationName%</span><span class="sxs-lookup"><span data-stu-id="8beae-134">The model.json for the exported entities will be at the %ExportDestinationName% level</span></span>
  - <span data-ttu-id="8beae-135">Ví dụ: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span><span class="sxs-lookup"><span data-stu-id="8beae-135">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
