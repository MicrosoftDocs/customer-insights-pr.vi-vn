---
title: Xuất dữ liệu Customer Insights sang Dynamics 365 Sales
description: Tìm hiểu cách đặt cấu hình kết nối với Dynamics 365 Sales.
ms.date: 02/01/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0013c4e6a96401d6cdbea55ed38f85f5e10dcc56
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269034"
---
# <a name="connector-for-dynamics-365-sales-preview"></a><span data-ttu-id="4f863-103">Tác nhân kết nối dành cho Dynamics 365 Sales (xem trước)</span><span class="sxs-lookup"><span data-stu-id="4f863-103">Connector for Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="4f863-104">Sử dụng dữ liệu khách hàng của bạn để tạo danh sách khách hàng tiếp thị, theo dõi quy trình làm việc và gửi thư quảng cáo với Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="4f863-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite"></a><span data-ttu-id="4f863-105">Điều kiện tiên quyết</span><span class="sxs-lookup"><span data-stu-id="4f863-105">Prerequisite</span></span>

1. <span data-ttu-id="4f863-106">Hồ sơ liên hệ phải có trong Dynamics 365 Sales trước khi bạn có thể xuất một phân đoạn từ Customer Insights sang Sales.</span><span class="sxs-lookup"><span data-stu-id="4f863-106">Contact records must be present in Dynamics 365 Sales before you can export a segment from Customer Insights to Sales.</span></span> <span data-ttu-id="4f863-107">Đọc thêm về cách nhập liên hệ vào [Dynamics 365 Sales bằng Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="4f863-107">Read more on how to ingest contacts in [Dynamics 365 Sales using Common Data Services](connect-power-query.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="4f863-108">Việc xuất các phân đoạn từ thông tin chi tiết về đối tượng sang Sales sẽ không tạo hồ sơ liên hệ mới trong các phiên bản Sales.</span><span class="sxs-lookup"><span data-stu-id="4f863-108">Exporting segments from audience insights to Sales will not create new contact records in the Sales instances.</span></span> <span data-ttu-id="4f863-109">Các bản ghi liên hệ từ Sales phải được nhập vào thông tin chi tiết về đối tượng và được sử dụng làm nguồn dữ liệu.</span><span class="sxs-lookup"><span data-stu-id="4f863-109">The contact records from Sales must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="4f863-110">Chúng cũng cần được đưa vào thực thể Khách hàng hợp nhất để ánh xạ ID khách hàng với ID liên hệ trước khi có thể xuất phân đoạn.</span><span class="sxs-lookup"><span data-stu-id="4f863-110">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="configure-the-connector-for-sales"></a><span data-ttu-id="4f863-111">Đặt cấu hình tác nhân kết nối dành cho Sales</span><span class="sxs-lookup"><span data-stu-id="4f863-111">Configure the connector for Sales</span></span>

1. <span data-ttu-id="4f863-112">Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Quản trị viên** > **Nơi xuất đích**.</span><span class="sxs-lookup"><span data-stu-id="4f863-112">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="4f863-113">Trong phần **Dynamics 365 Sales**, chọn **Thiết lập**.</span><span class="sxs-lookup"><span data-stu-id="4f863-113">Under **Dynamics 365 Sales**, select **Set up**.</span></span>

1. <span data-ttu-id="4f863-114">Trong trường **Tên hiển thị**, hãy đặt cho đích xuất một cái tên dễ nhận biết.</span><span class="sxs-lookup"><span data-stu-id="4f863-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="4f863-115">Nhập URL Sales của tổ chức bạn vào trường **Địa chỉ máy chủ**.</span><span class="sxs-lookup"><span data-stu-id="4f863-115">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="4f863-116">Trong phần **Tài khoản quản trị viên máy chủ**, chọn **Đăng nhập** rồi chọn tài khoản Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="4f863-116">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="4f863-117">Ánh xạ trường ID khách hàng với ID liên hệ Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="4f863-117">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="4f863-118">Chọn **Tiếp theo**.</span><span class="sxs-lookup"><span data-stu-id="4f863-118">Select **Next**.</span></span>

1. <span data-ttu-id="4f863-119">Chọn một hoặc nhiều phân khúc.</span><span class="sxs-lookup"><span data-stu-id="4f863-119">Choose one or more segments.</span></span>

1. <span data-ttu-id="4f863-120">Chọn **Lưu**.</span><span class="sxs-lookup"><span data-stu-id="4f863-120">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="4f863-121">Xuất dữ liệu</span><span class="sxs-lookup"><span data-stu-id="4f863-121">Export the data</span></span>

<span data-ttu-id="4f863-122">Bạn có thể [xuất dữ liệu theo nhu cầu](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="4f863-122">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="4f863-123">Mỗi lần [làm mới theo lịch](system.md#schedule-tab), tác vụ xuất cũng sẽ chạy.</span><span class="sxs-lookup"><span data-stu-id="4f863-123">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]