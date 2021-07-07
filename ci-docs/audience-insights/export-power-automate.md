---
title: Trình kết nối Power Automate | Microsoft Docs
description: Tạo quy trình trong Microsoft Power Automate từ Dynamics 365 Customer Insights.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 57be0a204ef920b7a4bb31cf9a5b3a77f96eca0d
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305090"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="c4cb4-103">Trình kết nối Power Automate (xem trước)</span><span class="sxs-lookup"><span data-stu-id="c4cb4-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="c4cb4-104">Kích hoạt các sự kiện cụ thể xảy ra tự động khi dữ liệu của bạn thay đổi và quản lý các dòng phức tạp hơn trực tiếp trong [Power Automate](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="c4cb4-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="c4cb4-105">Trình kích hoạt Power Automate</span><span class="sxs-lookup"><span data-stu-id="c4cb4-105">Power Automate triggers</span></span>

<span data-ttu-id="c4cb4-106">Sử dụng trình kích hoạt để tạo luồng đám mây và tự động hóa các tác vụ lặp lại, chẳng hạn như thông báo hoặc các hành động nâng cao hơn.</span><span class="sxs-lookup"><span data-stu-id="c4cb4-106">Use triggers to create cloud flows and automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="c4cb4-107">Kích hoạt khi làm mới nguồn dữ liệu không thành công.</span><span class="sxs-lookup"><span data-stu-id="c4cb4-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="c4cb4-108">Kích hoạt khi làm mới nguồn dữ liệu thành công.</span><span class="sxs-lookup"><span data-stu-id="c4cb4-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="c4cb4-109">Kích hoạt khi ngưỡng vượt quá trên một phân khúc.</span><span class="sxs-lookup"><span data-stu-id="c4cb4-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="c4cb4-110">Kích hoạt bị giới hạn để vượt quá ngưỡng.</span><span class="sxs-lookup"><span data-stu-id="c4cb4-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="c4cb4-111">Kích hoạt khi ngưỡng vượt quá trên một giá trị đo kinh doanh.</span><span class="sxs-lookup"><span data-stu-id="c4cb4-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="c4cb4-112">Chỉ hỗ trợ giá trị đo công việc không có kích thước.</span><span class="sxs-lookup"><span data-stu-id="c4cb4-112">Only business measures without a dimension are supported.</span></span> <span data-ttu-id="c4cb4-113">Kích hoạt bị giới hạn để vượt quá ngưỡng.</span><span class="sxs-lookup"><span data-stu-id="c4cb4-113">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="c4cb4-114">Kích hoạt khi hoàn thành quá trình làm mới đầy đủ (nguồn dữ liệu, phân khúc, đo lường,...).</span><span class="sxs-lookup"><span data-stu-id="c4cb4-114">Trigger when a full refresh of (data sources, segments, measures, ...) is completed.</span></span>
- <span data-ttu-id="c4cb4-115">Kích hoạt khi hoàn tất quá trình làm mới quy trình hợp nhất (ánh xạ, khớp, hợp nhất).</span><span class="sxs-lookup"><span data-stu-id="c4cb4-115">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

[<span data-ttu-id="c4cb4-116">Định cấu hình trình kích hoạt trong Power Automate.</span><span class="sxs-lookup"><span data-stu-id="c4cb4-116">Configure your triggers in Power Automate.</span></span>](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a><span data-ttu-id="c4cb4-117">Hành động Power Automate</span><span class="sxs-lookup"><span data-stu-id="c4cb4-117">Power Automate actions</span></span>

<span data-ttu-id="c4cb4-118">Trình kết nối Power Automate cung cấp các hành động khác ngoài trình kích hoạt có sẵn.</span><span class="sxs-lookup"><span data-stu-id="c4cb4-118">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="c4cb4-119">Để biết thêm thông tin, xem [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="c4cb4-119">For more information, see the [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow"></a><span data-ttu-id="c4cb4-120">Tạo một Dòng Power Automate</span><span class="sxs-lookup"><span data-stu-id="c4cb4-120">Create a Power Automate flow</span></span>

1. <span data-ttu-id="c4cb4-121">Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Quản trị viên** > **Nơi xuất đích**.</span><span class="sxs-lookup"><span data-stu-id="c4cb4-121">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="c4cb4-122">Trên lát **Power Automate**, chọn **Thiết lập**.</span><span class="sxs-lookup"><span data-stu-id="c4cb4-122">On the **Power Automate** tile, select **Set up**.</span></span>

1. <span data-ttu-id="c4cb4-123">Trình kết nối Customer Insights (xem trước) trong Power Automate mở ra.</span><span class="sxs-lookup"><span data-stu-id="c4cb4-123">The Customer Insights Connector (preview) in Power Automate opens.</span></span> <span data-ttu-id="c4cb4-124">**Đăng nhập** vào Power Automate.</span><span class="sxs-lookup"><span data-stu-id="c4cb4-124">**Sign in** to Power Automate.</span></span>

1. <span data-ttu-id="c4cb4-125">Chọn một trong các trình kích hoạt có sẵn và thêm các bước khác vào quy trình mới của bạn.</span><span class="sxs-lookup"><span data-stu-id="c4cb4-125">Choose one of the available triggers and add more steps to your new flow.</span></span> <span data-ttu-id="c4cb4-126">Để biết thêm thông tin, hãy xem [Tạo luồng đám mây trong Power Automate](/power-automate/get-started-logic-flow).</span><span class="sxs-lookup"><span data-stu-id="c4cb4-126">For more information, see [Create a cloud flow in Power Automate](/power-automate/get-started-logic-flow).</span></span>

<span data-ttu-id="c4cb4-127">Ví dụ về cách sử dụng các quy trình:</span><span class="sxs-lookup"><span data-stu-id="c4cb4-127">Examples of how to use flows:</span></span> 
- <span data-ttu-id="c4cb4-128">Đăng tin nhắn lên một kênh Microsoft Teams nếu làm mới nguồn dữ liệu không thành công.</span><span class="sxs-lookup"><span data-stu-id="c4cb4-128">Post a message to a Microsoft Teams channel if a data source refresh fails.</span></span> 
- <span data-ttu-id="c4cb4-129">Gửi email cho chủ sở hữu dữ liệu khi vượt qua ngưỡng trên một phân khúc.</span><span class="sxs-lookup"><span data-stu-id="c4cb4-129">Send an email to the data owners when a threshold on a segment is crossed.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]
