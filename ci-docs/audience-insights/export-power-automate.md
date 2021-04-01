---
title: Trình kết nối Power Automate | Microsoft Docs
description: Tạo quy trình trong Microsoft Power Automate từ Dynamics 365 Customer Insights.
ms.date: 01/20/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e973bb11b31c9e70b695ebec8aa2700fdaa5e44f
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597951"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="f8d09-103">Trình kết nối Power Automate (xem trước)</span><span class="sxs-lookup"><span data-stu-id="f8d09-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="f8d09-104">Kích hoạt các sự kiện cụ thể xảy ra tự động khi dữ liệu của bạn thay đổi và quản lý các dòng phức tạp hơn trực tiếp trong [Power Automate](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="f8d09-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="f8d09-105">Trình kích hoạt Power Automate</span><span class="sxs-lookup"><span data-stu-id="f8d09-105">Power Automate triggers</span></span>

<span data-ttu-id="f8d09-106">Sử dụng trình kích hoạt để tạo luồng đám mây và tự động hóa các tác vụ lặp lại, chẳng hạn như thông báo hoặc các hành động nâng cao hơn.</span><span class="sxs-lookup"><span data-stu-id="f8d09-106">Use triggers to create cloud flows and automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="f8d09-107">Kích hoạt khi làm mới nguồn dữ liệu không thành công.</span><span class="sxs-lookup"><span data-stu-id="f8d09-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="f8d09-108">Kích hoạt khi làm mới nguồn dữ liệu thành công.</span><span class="sxs-lookup"><span data-stu-id="f8d09-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="f8d09-109">Kích hoạt khi ngưỡng vượt quá trên một phân khúc.</span><span class="sxs-lookup"><span data-stu-id="f8d09-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="f8d09-110">Kích hoạt bị giới hạn để vượt quá ngưỡng.</span><span class="sxs-lookup"><span data-stu-id="f8d09-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="f8d09-111">Kích hoạt khi ngưỡng vượt quá trên một giá trị đo kinh doanh.</span><span class="sxs-lookup"><span data-stu-id="f8d09-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="f8d09-112">Kích hoạt bị giới hạn vượt quá ngưỡng.</span><span class="sxs-lookup"><span data-stu-id="f8d09-112">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="f8d09-113">Kích hoạt khi hoàn thành quá trình làm mới đầy đủ (nguồn dữ liệu, phân đoạn, đo lường...).</span><span class="sxs-lookup"><span data-stu-id="f8d09-113">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="f8d09-114">Kích hoạt khi hoàn tất quá trình làm mới quy trình hợp nhất (ánh xạ, khớp, hợp nhất).</span><span class="sxs-lookup"><span data-stu-id="f8d09-114">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="f8d09-115">[Đặt cấu hình trình kích hoạt trong Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span><span class="sxs-lookup"><span data-stu-id="f8d09-115">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="f8d09-116">Hành động Power Automate</span><span class="sxs-lookup"><span data-stu-id="f8d09-116">Power Automate actions</span></span>
<span data-ttu-id="f8d09-117">Trình kết nối Power Automate cung cấp các hành động khác ngoài trình kích hoạt có sẵn.</span><span class="sxs-lookup"><span data-stu-id="f8d09-117">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="f8d09-118">Để biết thêm thông tin, xem [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="f8d09-118">For more information, see the [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow"></a><span data-ttu-id="f8d09-119">Tạo một Dòng Power Automate</span><span class="sxs-lookup"><span data-stu-id="f8d09-119">Create a Power Automate flow</span></span>

1. <span data-ttu-id="f8d09-120">Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Quản trị viên** > **Nơi xuất đích**.</span><span class="sxs-lookup"><span data-stu-id="f8d09-120">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="f8d09-121">Trên lát **Power Automate**, chọn **Thiết lập**.</span><span class="sxs-lookup"><span data-stu-id="f8d09-121">On the **Power Automate** tile, select **Set up**.</span></span>

1. <span data-ttu-id="f8d09-122">Trình kết nối Customer Insights (xem trước) trong Power Automate mở ra.</span><span class="sxs-lookup"><span data-stu-id="f8d09-122">The Customer Insights Connector (preview) in Power Automate opens.</span></span> <span data-ttu-id="f8d09-123">**Đăng nhập** vào Power Automate.</span><span class="sxs-lookup"><span data-stu-id="f8d09-123">**Sign in** to Power Automate.</span></span>

1. <span data-ttu-id="f8d09-124">Chọn một trong các trình kích hoạt có sẵn và thêm các bước khác vào quy trình mới của bạn.</span><span class="sxs-lookup"><span data-stu-id="f8d09-124">Choose one of the available triggers and add more steps to your new flow.</span></span> <span data-ttu-id="f8d09-125">Để biết thêm thông tin, hãy xem [Tạo luồng đám mây trong Power Automate](/power-automate/get-started-logic-flow).</span><span class="sxs-lookup"><span data-stu-id="f8d09-125">For more information, see [Create a cloud flow in Power Automate](/power-automate/get-started-logic-flow).</span></span>

<span data-ttu-id="f8d09-126">Ví dụ về cách sử dụng các luồng:</span><span class="sxs-lookup"><span data-stu-id="f8d09-126">Examples how to use flows:</span></span> 
- <span data-ttu-id="f8d09-127">Đăng tin nhắn lên một kênh Microsoft Teams nếu làm mới nguồn dữ liệu không thành công.</span><span class="sxs-lookup"><span data-stu-id="f8d09-127">Post a message to a Microsoft Teams channel if a data source refresh fails.</span></span> 
- <span data-ttu-id="f8d09-128">Gửi email cho chủ sở hữu dữ liệu khi vượt qua ngưỡng trên một phân khúc.</span><span class="sxs-lookup"><span data-stu-id="f8d09-128">Send an email to the data owners when a threshold on a segment is crossed.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]