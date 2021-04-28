---
title: Xuất dữ liệu Customer Insights sang Dynamics 365 Sales
description: Tìm hiểu cách đặt cấu hình kết nối và xuất sang Dynamics 365 Sales.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: fc1a05ba4d21d96aa1a9724d158687bbb86949b6
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759630"
---
# <a name="use-segments-in-dynamics-365-sales-preview"></a><span data-ttu-id="34534-103">Sử dụng các phân khúc trong Dynamics 365 Sales (bản xem trước)</span><span class="sxs-lookup"><span data-stu-id="34534-103">Use segments in Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="34534-104">Sử dụng dữ liệu khách hàng của bạn để tạo danh sách khách hàng tiếp thị, theo dõi quy trình làm việc và gửi thư quảng cáo với Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="34534-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite-for-connection"></a><span data-ttu-id="34534-105">Điều kiện tiên quyết để kết nối</span><span class="sxs-lookup"><span data-stu-id="34534-105">Prerequisite for connection</span></span>

1. <span data-ttu-id="34534-106">Hồ sơ liên hệ phải có trong Dynamics 365 Sales trước khi bạn có thể xuất một phân đoạn từ Customer Insights sang Sales.</span><span class="sxs-lookup"><span data-stu-id="34534-106">Contact records must be present in Dynamics 365 Sales before you can export a segment from Customer Insights to Sales.</span></span> <span data-ttu-id="34534-107">Đọc thêm về cách nhập liên hệ vào [Dynamics 365 Sales bằng Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="34534-107">Read more on how to ingest contacts in [Dynamics 365 Sales using Common Data Services](connect-power-query.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="34534-108">Việc xuất các phân đoạn từ thông tin chi tiết về đối tượng sang Sales sẽ không tạo hồ sơ liên hệ mới trong các phiên bản Sales.</span><span class="sxs-lookup"><span data-stu-id="34534-108">Exporting segments from audience insights to Sales will not create new contact records in the Sales instances.</span></span> <span data-ttu-id="34534-109">Các bản ghi liên hệ từ Sales phải được nhập vào thông tin chi tiết về đối tượng và được sử dụng làm nguồn dữ liệu.</span><span class="sxs-lookup"><span data-stu-id="34534-109">The contact records from Sales must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="34534-110">Chúng cũng cần được đưa vào thực thể Khách hàng hợp nhất để ánh xạ ID khách hàng với ID liên hệ trước khi có thể xuất phân đoạn.</span><span class="sxs-lookup"><span data-stu-id="34534-110">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="set-up-the-connection-to-sales"></a><span data-ttu-id="34534-111">Thiết lập kết nối với Sales</span><span class="sxs-lookup"><span data-stu-id="34534-111">Set up the connection to Sales</span></span>

1. <span data-ttu-id="34534-112">Đi đến **Quản trị viên** > **Kết nối**.</span><span class="sxs-lookup"><span data-stu-id="34534-112">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="34534-113">Chọn **Thêm kết nối** rồi chọn **Dynamics 365 Sales** để đặt cấu hình kết nối.</span><span class="sxs-lookup"><span data-stu-id="34534-113">Select **Add connection** and choose **Dynamics 365 Sales** to configure the connection.</span></span>

1. <span data-ttu-id="34534-114">Đặt tên dễ nhận biết cho kết nối trong trường **Tên hiển thị**.</span><span class="sxs-lookup"><span data-stu-id="34534-114">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="34534-115">Tên và loại kết nối mô tả kết nối này.</span><span class="sxs-lookup"><span data-stu-id="34534-115">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="34534-116">Bạn nên chọn một tên giải thích mục đích và mục tiêu của kết nối.</span><span class="sxs-lookup"><span data-stu-id="34534-116">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="34534-117">Chọn người có thể sử dụng kết nối này.</span><span class="sxs-lookup"><span data-stu-id="34534-117">Choose who can use this connection.</span></span> <span data-ttu-id="34534-118">Nếu bạn không thực hiện hành động nào, giá trị mặc định sẽ là Quản trị viên.</span><span class="sxs-lookup"><span data-stu-id="34534-118">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="34534-119">Để biết thêm thông tin, hãy xem [Cho phép người đóng góp sử dụng một kết nối cho các lần xuất](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="34534-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="34534-120">Nhập URL Sales của tổ chức bạn vào trường **Địa chỉ máy chủ**.</span><span class="sxs-lookup"><span data-stu-id="34534-120">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="34534-121">Trong phần **Tài khoản quản trị viên máy chủ**, chọn **Đăng nhập** rồi chọn tài khoản Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="34534-121">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="34534-122">Ánh xạ trường ID khách hàng với ID liên hệ Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="34534-122">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="34534-123">Chọn **Lưu** để hoàn thành kết nối.</span><span class="sxs-lookup"><span data-stu-id="34534-123">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="34534-124">Đặt cấu hình xuất</span><span class="sxs-lookup"><span data-stu-id="34534-124">Configure an export</span></span>

<span data-ttu-id="34534-125">Bạn có thể đặt cấu hình lần xuất này nếu bạn có quyền truy cập vào kết nối thuộc loại này.</span><span class="sxs-lookup"><span data-stu-id="34534-125">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="34534-126">Để biết thêm thông tin, hãy xem [Các quyền cần thiết để đặt cấu hình xuất](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="34534-126">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="34534-127">Đi tới **Dữ liệu** > **Nội dung xuất**.</span><span class="sxs-lookup"><span data-stu-id="34534-127">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="34534-128">Để tạo một nội dung xuất mới, hãy chọn **Thêm đích**.</span><span class="sxs-lookup"><span data-stu-id="34534-128">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="34534-129">Trong trường **Kết nối để xuất**, hãy chọn một kết nối từ phần Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="34534-129">In the **Connection for export** field, choose a connection from the Dynamics 365 Sales section.</span></span> <span data-ttu-id="34534-130">Nếu bạn không thấy tên phần này, tức là không có kết nối nào thuộc loại này dành cho bạn.</span><span class="sxs-lookup"><span data-stu-id="34534-130">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="34534-131">Chọn một hoặc nhiều phân khúc.</span><span class="sxs-lookup"><span data-stu-id="34534-131">Choose one or more segments.</span></span>

1. <span data-ttu-id="34534-132">Chọn **Lưu**</span><span class="sxs-lookup"><span data-stu-id="34534-132">Select **Save**</span></span>

<span data-ttu-id="34534-133">Việc lưu một nội dung xuất sẽ không chạy nội dung xuất đó ngay lập tức.</span><span class="sxs-lookup"><span data-stu-id="34534-133">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="34534-134">Nội dung xuất chạy trong mỗi lần [làm mới theo lịch trình](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="34534-134">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="34534-135">Bạn cũng có thể [xuất dữ liệu theo yêu cầu](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="34534-135">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
