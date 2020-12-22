---
title: Xuất dữ liệu Customer Insights sang Dynamics 365 Marketing
description: Tìm hiểu cách đặt cấu hình kết nối với Dynamics 365 Marketing.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 163387779b64bd78ef08e2d96a5f1c9615062f28
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643799"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a><span data-ttu-id="db341-103">Tác nhân kết nối dành cho Dynamics 365 Marketing (xem trước)</span><span class="sxs-lookup"><span data-stu-id="db341-103">Connector for Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="db341-104">Dùng [các phân đoạn](segments.md) để tạo chiến dịch và liên hệ với các nhóm khách hàng cụ thể với Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="db341-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="db341-105">Để biết thêm thông tin, hãy xem [Sử dụng phân khúc từ Dynamics 365 Customer Insights với Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="db341-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite"></a><span data-ttu-id="db341-106">Điều kiện tiên quyết</span><span class="sxs-lookup"><span data-stu-id="db341-106">Prerequisite</span></span>

<span data-ttu-id="db341-107">Bản ghi liên hệ [từ Dynamics 365 Marketing được nhập Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="db341-107">Contact records [from Dynamics 365 Marketing ingested Common Data Service](connect-power-query.md).</span></span>

## <a name="configure-the-connector-for-marketing"></a><span data-ttu-id="db341-108">Đặt cấu hình tác nhân kết nối dành cho Marketing</span><span class="sxs-lookup"><span data-stu-id="db341-108">Configure the connector for Marketing</span></span>

1. <span data-ttu-id="db341-109">Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Quản trị viên** > **Nơi xuất đích**.</span><span class="sxs-lookup"><span data-stu-id="db341-109">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="db341-110">Trong phần **Dynamics 365 Marketing**, chọn **Thiết lập**.</span><span class="sxs-lookup"><span data-stu-id="db341-110">Under **Dynamics 365 Marketing**, select **Set up**.</span></span>

1. <span data-ttu-id="db341-111">Trong trường **Tên hiển thị**, hãy đặt cho đích xuất một cái tên dễ nhận biết.</span><span class="sxs-lookup"><span data-stu-id="db341-111">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="db341-112">Nhập URL Marketing của tổ chức bạn vào trường **Địa chỉ máy chủ**.</span><span class="sxs-lookup"><span data-stu-id="db341-112">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="db341-113">Trong phần **Tài khoản quản trị viên máy chủ**, chọn **Đăng nhập** rồi chọn tài khoản Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="db341-113">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="db341-114">Ánh xạ trường ID khách hàng với ID liên hệ Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="db341-114">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="db341-115">Chọn **Tiếp theo**.</span><span class="sxs-lookup"><span data-stu-id="db341-115">Select **Next**.</span></span>

1. <span data-ttu-id="db341-116">Chọn một hoặc nhiều phân khúc.</span><span class="sxs-lookup"><span data-stu-id="db341-116">Choose one or more segments.</span></span>

1. <span data-ttu-id="db341-117">Chọn **Lưu**.</span><span class="sxs-lookup"><span data-stu-id="db341-117">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="db341-118">Xuất dữ liệu</span><span class="sxs-lookup"><span data-stu-id="db341-118">Export the data</span></span>

<span data-ttu-id="db341-119">Bạn có thể [xuất dữ liệu theo nhu cầu](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="db341-119">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="db341-120">Mỗi lần [làm mới theo lịch](system.md#schedule-tab), tác vụ xuất cũng sẽ chạy.</span><span class="sxs-lookup"><span data-stu-id="db341-120">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
