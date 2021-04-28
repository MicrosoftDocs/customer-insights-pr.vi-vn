---
title: Xuất dữ liệu Customer Insights sang Azure Data Lake Storage thế hệ 2
description: Tìm hiểu cách định cấu hình kết nối với Azure Data Lake Storage thế hệ 2.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: f431b707e1d65ffe47f8b3aa1c52abaa964e871a
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760077"
---
# <a name="set-up-the-connection-to-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="686ea-103">Thiết lập kết nối với Azure Data Lake Storage Thế hệ 2 (bản xem trước)</span><span class="sxs-lookup"><span data-stu-id="686ea-103">Set up the connection to Azure Data Lake Storage Gen2 (preview)</span></span>

1. <span data-ttu-id="686ea-104">Đi đến **Quản trị viên** > **Kết nối**.</span><span class="sxs-lookup"><span data-stu-id="686ea-104">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="686ea-105">Chọn **Thêm kết nối** rồi chọn **Azure Data Lake Thế hệ 2** để đặt cấu hình kết nối.</span><span class="sxs-lookup"><span data-stu-id="686ea-105">Select **Add connection** and choose **Azure Data Lake Gen 2** to configure the connection.</span></span>

1. <span data-ttu-id="686ea-106">Đặt tên dễ nhận biết cho kết nối trong trường **Tên hiển thị**.</span><span class="sxs-lookup"><span data-stu-id="686ea-106">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="686ea-107">Tên và loại kết nối mô tả kết nối này.</span><span class="sxs-lookup"><span data-stu-id="686ea-107">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="686ea-108">Bạn nên chọn một tên giải thích mục đích và mục tiêu của kết nối.</span><span class="sxs-lookup"><span data-stu-id="686ea-108">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="686ea-109">Chọn người có thể sử dụng kết nối này.</span><span class="sxs-lookup"><span data-stu-id="686ea-109">Choose who can use this connection.</span></span> <span data-ttu-id="686ea-110">Nếu bạn không thực hiện hành động nào, giá trị mặc định sẽ là Quản trị viên.</span><span class="sxs-lookup"><span data-stu-id="686ea-110">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="686ea-111">Để biết thêm thông tin, hãy xem [Cho phép người đóng góp sử dụng một kết nối cho các lần xuất](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="686ea-111">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="686ea-112">Nhập **Tên tài khoản**, **Khóa tài khoản** và **Bộ chứa** cho Azure Data Lake Storage Thế hệ 2 của bạn.</span><span class="sxs-lookup"><span data-stu-id="686ea-112">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="686ea-113">Để tìm hiểu cách tạo tài khoản lưu trữ để sử dụng với Azure Data Lake Storage thế hệ 2, hãy xem [Tạo tài khoản lưu trữ](/azure/storage/blobs/create-data-lake-storage-account).</span><span class="sxs-lookup"><span data-stu-id="686ea-113">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="686ea-114">Để tìm hiểu thêm về tên tài khoản lưu trữ Azure Data Lake Thế hệ 2 và khóa tài khoản, hãy xem [Quản lý các thiết đặt tài khoản lưu trữ trong cổng thông tin Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="686ea-114">To learn more about Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="686ea-115">Chọn **Lưu** để hoàn thành kết nối.</span><span class="sxs-lookup"><span data-stu-id="686ea-115">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="686ea-116">Đặt cấu hình xuất</span><span class="sxs-lookup"><span data-stu-id="686ea-116">Configure an export</span></span>

<span data-ttu-id="686ea-117">Bạn có thể đặt cấu hình lần xuất này nếu bạn có quyền truy cập vào kết nối thuộc loại này.</span><span class="sxs-lookup"><span data-stu-id="686ea-117">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="686ea-118">Để biết thêm thông tin, hãy xem [Các quyền cần thiết để đặt cấu hình xuất](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="686ea-118">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="686ea-119">Đi tới **Dữ liệu** > **Nội dung xuất**.</span><span class="sxs-lookup"><span data-stu-id="686ea-119">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="686ea-120">Để tạo nội dung xuất mới, hãy chọn **Thêm nội dung xuất**.</span><span class="sxs-lookup"><span data-stu-id="686ea-120">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="686ea-121">Trong trường **Kết nối để xuất**, hãy chọn một kết nối từ phần **Azure Data Lake**.</span><span class="sxs-lookup"><span data-stu-id="686ea-121">In the **Connection for export** field, choose a connection from the **Azure Data Lake** section.</span></span> <span data-ttu-id="686ea-122">Nếu bạn không thấy tên phần này, tức là không có kết nối nào thuộc loại này dành cho bạn.</span><span class="sxs-lookup"><span data-stu-id="686ea-122">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="686ea-123">Chọn ô cạnh mỗi thực thể mà bạn muốn xuất sang vị trí này.</span><span class="sxs-lookup"><span data-stu-id="686ea-123">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="686ea-124">Chọn **Lưu**.</span><span class="sxs-lookup"><span data-stu-id="686ea-124">Select **Save**.</span></span>

<span data-ttu-id="686ea-125">Việc lưu một nội dung xuất sẽ không chạy nội dung xuất đó ngay lập tức.</span><span class="sxs-lookup"><span data-stu-id="686ea-125">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="686ea-126">Nội dung xuất chạy trong mỗi lần [làm mới theo lịch trình](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="686ea-126">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="686ea-127">Bạn cũng có thể [xuất dữ liệu theo yêu cầu](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="686ea-127">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

<span data-ttu-id="686ea-128">Dữ liệu đã xuất được lưu trữ trong bộ lưu trữ Azure Data Lake Thế hệ 2 mà bạn đã đặt cấu hình.</span><span class="sxs-lookup"><span data-stu-id="686ea-128">Exported data is stored in the Azure Data Lake Gen 2 storage container you configured.</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
