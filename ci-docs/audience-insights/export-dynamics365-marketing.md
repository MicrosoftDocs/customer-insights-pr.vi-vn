---
title: Xuất dữ liệu Customer Insights sang Dynamics 365 Marketing
description: Tìm hiểu cách đặt cấu hình kết nối và xuất sang Dynamics 365 Marketing.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 195bee789dc043057b47c12c8d93e6d53edb59cd
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976826"
---
# <a name="use-segments-in-dynamics-365-marketing-preview"></a><span data-ttu-id="abc9b-103">Sử dụng các phân khúc trong Dynamics 365 Marketing (bản xem trước)</span><span class="sxs-lookup"><span data-stu-id="abc9b-103">Use segments in Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="abc9b-104">Dùng [các phân đoạn](segments.md) để tạo chiến dịch và liên hệ với các nhóm khách hàng cụ thể với Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="abc9b-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="abc9b-105">Để biết thêm thông tin, hãy xem [Sử dụng phân khúc từ Dynamics 365 Customer Insights với Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="abc9b-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite-for-a-connection"></a><span data-ttu-id="abc9b-106">Điều kiện tiên quyết để kết nối</span><span class="sxs-lookup"><span data-stu-id="abc9b-106">Prerequisite for a connection</span></span>

- <span data-ttu-id="abc9b-107">Hồ sơ liên hệ phải có trong Dynamics 365 Marketing trước khi bạn có thể xuất một phân đoạn từ Customer Insights sang Marketing.</span><span class="sxs-lookup"><span data-stu-id="abc9b-107">Contact records must be present in Dynamics 365 Marketing before you can export a segment from Customer Insights to Marketing.</span></span> <span data-ttu-id="abc9b-108">Đọc thêm về cách nhập liên hệ vào [Dynamics 365 Marketing bằng Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="abc9b-108">Read more on how to ingest contacts in [Dynamics 365 Marketing using Common Data Services](connect-power-query.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="abc9b-109">Việc xuất các phân đoạn từ thông tin chi tiết về đối tượng sang Marketing sẽ không tạo hồ sơ liên hệ mới trong các phiên bản Marketing.</span><span class="sxs-lookup"><span data-stu-id="abc9b-109">Exporting segments from audience insights to Marketing will not create new contact records in the Marketing instances.</span></span> <span data-ttu-id="abc9b-110">Các bản ghi liên hệ từ Marketing phải được nhập vào thông tin chi tiết về đối tượng và được sử dụng làm nguồn dữ liệu.</span><span class="sxs-lookup"><span data-stu-id="abc9b-110">The contact records from Marketing must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="abc9b-111">Chúng cũng cần được đưa vào thực thể Khách hàng hợp nhất để ánh xạ ID khách hàng với ID liên hệ trước khi có thể xuất phân đoạn.</span><span class="sxs-lookup"><span data-stu-id="abc9b-111">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="set-up-connection-to-marketing"></a><span data-ttu-id="abc9b-112">Thiết lập kết nối với Marketing</span><span class="sxs-lookup"><span data-stu-id="abc9b-112">Set up connection to Marketing</span></span>

1. <span data-ttu-id="abc9b-113">Đi đến **Quản trị viên** > **Kết nối**.</span><span class="sxs-lookup"><span data-stu-id="abc9b-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="abc9b-114">Chọn **Thêm kết nối** rồi chọn **Dynamics 365 Marketing** để đặt cấu hình kết nối.</span><span class="sxs-lookup"><span data-stu-id="abc9b-114">Select **Add connection** and choose **Dynamics 365 Marketing** to configure the connection.</span></span>

1. <span data-ttu-id="abc9b-115">Đặt tên dễ nhận biết cho kết nối trong trường **Tên hiển thị**.</span><span class="sxs-lookup"><span data-stu-id="abc9b-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="abc9b-116">Tên và loại kết nối mô tả kết nối này.</span><span class="sxs-lookup"><span data-stu-id="abc9b-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="abc9b-117">Bạn nên chọn một tên giải thích mục đích và mục tiêu của kết nối.</span><span class="sxs-lookup"><span data-stu-id="abc9b-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="abc9b-118">Chọn người có thể sử dụng kết nối này.</span><span class="sxs-lookup"><span data-stu-id="abc9b-118">Choose who can use this connection.</span></span> <span data-ttu-id="abc9b-119">Nếu bạn không thực hiện hành động nào, giá trị mặc định sẽ là Quản trị viên.</span><span class="sxs-lookup"><span data-stu-id="abc9b-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="abc9b-120">Để biết thêm thông tin, hãy xem [Cho phép người đóng góp sử dụng một kết nối cho các lần xuất](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="abc9b-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="abc9b-121">Nhập URL Marketing của tổ chức bạn vào trường **Địa chỉ máy chủ**.</span><span class="sxs-lookup"><span data-stu-id="abc9b-121">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="abc9b-122">Trong phần **Tài khoản quản trị viên máy chủ**, chọn **Đăng nhập** rồi chọn tài khoản Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="abc9b-122">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="abc9b-123">Ánh xạ trường ID khách hàng với ID liên hệ Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="abc9b-123">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="abc9b-124">Chọn **Lưu** để hoàn thành kết nối.</span><span class="sxs-lookup"><span data-stu-id="abc9b-124">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="abc9b-125">Đặt cấu hình xuất</span><span class="sxs-lookup"><span data-stu-id="abc9b-125">Configure an export</span></span>

<span data-ttu-id="abc9b-126">Bạn có thể đặt cấu hình lần xuất này nếu bạn có quyền truy cập vào kết nối thuộc loại này.</span><span class="sxs-lookup"><span data-stu-id="abc9b-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="abc9b-127">Để biết thêm thông tin, hãy xem [Các quyền cần thiết để đặt cấu hình xuất](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="abc9b-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="abc9b-128">Đi tới **Dữ liệu** > **Nội dung xuất**.</span><span class="sxs-lookup"><span data-stu-id="abc9b-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="abc9b-129">Để tạo một nội dung xuất mới, hãy chọn **Thêm đích**.</span><span class="sxs-lookup"><span data-stu-id="abc9b-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="abc9b-130">Trong trường **Kết nối để xuất**, hãy chọn một kết nối từ phần Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="abc9b-130">In the **Connection for export** field, choose a connection from the Dynamics 365 Marketing section.</span></span> <span data-ttu-id="abc9b-131">Nếu bạn không thấy tên phần này, tức là không có kết nối nào thuộc loại này dành cho bạn.</span><span class="sxs-lookup"><span data-stu-id="abc9b-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="abc9b-132">Chọn một hoặc nhiều phân khúc.</span><span class="sxs-lookup"><span data-stu-id="abc9b-132">Choose one or more segments.</span></span>

1. <span data-ttu-id="abc9b-133">Chọn **Lưu**.</span><span class="sxs-lookup"><span data-stu-id="abc9b-133">Select **Save**.</span></span>

<span data-ttu-id="abc9b-134">Việc lưu một nội dung xuất sẽ không chạy nội dung xuất đó ngay lập tức.</span><span class="sxs-lookup"><span data-stu-id="abc9b-134">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="abc9b-135">Nội dung xuất chạy trong mỗi lần [làm mới theo lịch trình](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="abc9b-135">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="abc9b-136">Bạn cũng có thể [xuất dữ liệu theo yêu cầu](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="abc9b-136">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
