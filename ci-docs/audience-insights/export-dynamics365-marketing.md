---
title: Xuất dữ liệu Customer Insights sang Dynamics 365 Marketing
description: Tìm hiểu cách đặt cấu hình kết nối với Dynamics 365 Marketing.
ms.date: 02/01/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: a06920b8ff25d7102ccd14ae68cf42fe91fa1ee6
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269080"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a><span data-ttu-id="bd33f-103">Tác nhân kết nối dành cho Dynamics 365 Marketing (xem trước)</span><span class="sxs-lookup"><span data-stu-id="bd33f-103">Connector for Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="bd33f-104">Dùng [các phân đoạn](segments.md) để tạo chiến dịch và liên hệ với các nhóm khách hàng cụ thể với Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="bd33f-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="bd33f-105">Để biết thêm thông tin, hãy xem [Sử dụng phân khúc từ Dynamics 365 Customer Insights với Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="bd33f-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite"></a><span data-ttu-id="bd33f-106">Điều kiện tiên quyết</span><span class="sxs-lookup"><span data-stu-id="bd33f-106">Prerequisite</span></span>

- <span data-ttu-id="bd33f-107">Hồ sơ liên hệ phải có trong Dynamics 365 Marketing trước khi bạn có thể xuất một phân đoạn từ Customer Insights sang Marketing.</span><span class="sxs-lookup"><span data-stu-id="bd33f-107">Contact records must be present in Dynamics 365 Marketing before you can export a segment from Customer Insights to Marketing.</span></span> <span data-ttu-id="bd33f-108">Đọc thêm về cách nhập liên hệ vào [Dynamics 365 Marketing bằng Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="bd33f-108">Read more on how to ingest contacts in [Dynamics 365 Marketing using Common Data Services](connect-power-query.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="bd33f-109">Việc xuất các phân đoạn từ thông tin chi tiết về đối tượng sang Marketing sẽ không tạo hồ sơ liên hệ mới trong các phiên bản Marketing.</span><span class="sxs-lookup"><span data-stu-id="bd33f-109">Exporting segments from audience insights to Marketing will not create new contact records in the Marketing instances.</span></span> <span data-ttu-id="bd33f-110">Các bản ghi liên hệ từ Marketing phải được nhập vào thông tin chi tiết về đối tượng và được sử dụng làm nguồn dữ liệu.</span><span class="sxs-lookup"><span data-stu-id="bd33f-110">The contact records from Marketing must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="bd33f-111">Chúng cũng cần được đưa vào thực thể Khách hàng hợp nhất để ánh xạ ID khách hàng với ID liên hệ trước khi có thể xuất phân đoạn.</span><span class="sxs-lookup"><span data-stu-id="bd33f-111">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="configure-the-connector-for-marketing"></a><span data-ttu-id="bd33f-112">Đặt cấu hình tác nhân kết nối dành cho Marketing</span><span class="sxs-lookup"><span data-stu-id="bd33f-112">Configure the connector for Marketing</span></span>

1. <span data-ttu-id="bd33f-113">Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Quản trị viên** > **Nơi xuất đích**.</span><span class="sxs-lookup"><span data-stu-id="bd33f-113">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="bd33f-114">Trong phần **Dynamics 365 Marketing**, chọn **Thiết lập**.</span><span class="sxs-lookup"><span data-stu-id="bd33f-114">Under **Dynamics 365 Marketing**, select **Set up**.</span></span>

1. <span data-ttu-id="bd33f-115">Trong trường **Tên hiển thị**, hãy đặt cho đích xuất một cái tên dễ nhận biết.</span><span class="sxs-lookup"><span data-stu-id="bd33f-115">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="bd33f-116">Nhập URL Marketing của tổ chức bạn vào trường **Địa chỉ máy chủ**.</span><span class="sxs-lookup"><span data-stu-id="bd33f-116">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="bd33f-117">Trong phần **Tài khoản quản trị viên máy chủ**, chọn **Đăng nhập** rồi chọn tài khoản Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="bd33f-117">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="bd33f-118">Ánh xạ trường ID khách hàng với ID liên hệ Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="bd33f-118">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="bd33f-119">Chọn **Tiếp theo**.</span><span class="sxs-lookup"><span data-stu-id="bd33f-119">Select **Next**.</span></span>

1. <span data-ttu-id="bd33f-120">Chọn một hoặc nhiều phân khúc.</span><span class="sxs-lookup"><span data-stu-id="bd33f-120">Choose one or more segments.</span></span>

1. <span data-ttu-id="bd33f-121">Chọn **Lưu**.</span><span class="sxs-lookup"><span data-stu-id="bd33f-121">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="bd33f-122">Xuất dữ liệu</span><span class="sxs-lookup"><span data-stu-id="bd33f-122">Export the data</span></span>

<span data-ttu-id="bd33f-123">Bạn có thể [xuất dữ liệu theo nhu cầu](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="bd33f-123">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="bd33f-124">Mỗi lần [làm mới theo lịch](system.md#schedule-tab), tác vụ xuất cũng sẽ chạy.</span><span class="sxs-lookup"><span data-stu-id="bd33f-124">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]