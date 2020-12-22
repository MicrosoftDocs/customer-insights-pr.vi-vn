---
title: Xuất dữ liệu Customer Insights sang Dynamics 365 Sales
description: Tìm hiểu cách đặt cấu hình kết nối với Dynamics 365 Sales.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: af0824e69dfdf620a0ac756e32a9bd3dd85e5151
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643844"
---
# <a name="connector-for-dynamics-365-sales-preview"></a><span data-ttu-id="37bd0-103">Tác nhân kết nối dành cho Dynamics 365 Sales (xem trước)</span><span class="sxs-lookup"><span data-stu-id="37bd0-103">Connector for Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="37bd0-104">Sử dụng dữ liệu khách hàng của bạn để tạo danh sách khách hàng tiếp thị, theo dõi quy trình làm việc và gửi thư quảng cáo với Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="37bd0-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite"></a><span data-ttu-id="37bd0-105">Điều kiện tiên quyết</span><span class="sxs-lookup"><span data-stu-id="37bd0-105">Prerequisite</span></span>

<span data-ttu-id="37bd0-106">Bản ghi liên hệ [từ Dynamics 365 Sales được nhập bằng Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="37bd0-106">Contact records [from Dynamics 365 Sales ingested using Common Data Service](connect-power-query.md).</span></span>

## <a name="configure-the-connector-for-sales"></a><span data-ttu-id="37bd0-107">Đặt cấu hình tác nhân kết nối dành cho Sales</span><span class="sxs-lookup"><span data-stu-id="37bd0-107">Configure the connector for Sales</span></span>

1. <span data-ttu-id="37bd0-108">Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Quản trị viên** > **Nơi xuất đích**.</span><span class="sxs-lookup"><span data-stu-id="37bd0-108">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="37bd0-109">Trong phần **Dynamics 365 Sales**, chọn **Thiết lập**.</span><span class="sxs-lookup"><span data-stu-id="37bd0-109">Under **Dynamics 365 Sales**, select **Set up**.</span></span>

1. <span data-ttu-id="37bd0-110">Trong trường **Tên hiển thị**, hãy đặt cho đích xuất một cái tên dễ nhận biết.</span><span class="sxs-lookup"><span data-stu-id="37bd0-110">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="37bd0-111">Nhập URL Sales của tổ chức bạn vào trường **Địa chỉ máy chủ**.</span><span class="sxs-lookup"><span data-stu-id="37bd0-111">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="37bd0-112">Trong phần **Tài khoản quản trị viên máy chủ**, chọn **Đăng nhập** rồi chọn tài khoản Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="37bd0-112">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="37bd0-113">Ánh xạ trường ID khách hàng với ID liên hệ Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="37bd0-113">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="37bd0-114">Chọn **Tiếp theo**.</span><span class="sxs-lookup"><span data-stu-id="37bd0-114">Select **Next**.</span></span>

1. <span data-ttu-id="37bd0-115">Chọn một hoặc nhiều phân khúc.</span><span class="sxs-lookup"><span data-stu-id="37bd0-115">Choose one or more segments.</span></span>

1. <span data-ttu-id="37bd0-116">Chọn **Lưu**.</span><span class="sxs-lookup"><span data-stu-id="37bd0-116">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="37bd0-117">Xuất dữ liệu</span><span class="sxs-lookup"><span data-stu-id="37bd0-117">Export the data</span></span>

<span data-ttu-id="37bd0-118">Bạn có thể [xuất dữ liệu theo nhu cầu](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="37bd0-118">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="37bd0-119">Mỗi lần [làm mới theo lịch](system.md#schedule-tab), tác vụ xuất cũng sẽ chạy.</span><span class="sxs-lookup"><span data-stu-id="37bd0-119">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
