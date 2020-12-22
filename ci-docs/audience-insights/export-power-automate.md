---
title: Trình kết nối Power Automate | Microsoft Docs
description: Tạo dòng trong Microsoft Power Automate từ Dynamics 365 Customer Insights.
ms.date: 08/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: ffe92414365b0b777691a4a2d585100e4fbea591
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407289"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="fd767-103">Trình kết nối Power Automate (xem trước)</span><span class="sxs-lookup"><span data-stu-id="fd767-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="fd767-104">Kích hoạt các sự kiện cụ thể xảy ra tự động khi dữ liệu của bạn thay đổi và quản lý các dòng phức tạp hơn trực tiếp trong [Power Automate](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="fd767-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="fd767-105">Trình kích hoạt Power Automate</span><span class="sxs-lookup"><span data-stu-id="fd767-105">Power Automate triggers</span></span>

<span data-ttu-id="fd767-106">Bạn có thể sử dụng nhiều trình kích hoạt cho phép bạn tạo các quy trình để tự động hóa tác vụ lặp lại, chẳng hạn như thông báo hoặc hành động nâng cao hơn.</span><span class="sxs-lookup"><span data-stu-id="fd767-106">You can use a variety of triggers that allow you to create flows to automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="fd767-107">Kích hoạt khi làm mới nguồn dữ liệu không thành công.</span><span class="sxs-lookup"><span data-stu-id="fd767-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="fd767-108">Kích hoạt khi làm mới nguồn dữ liệu thành công.</span><span class="sxs-lookup"><span data-stu-id="fd767-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="fd767-109">Kích hoạt khi ngưỡng vượt quá trên một phân khúc.</span><span class="sxs-lookup"><span data-stu-id="fd767-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="fd767-110">Kích hoạt bị giới hạn để vượt quá ngưỡng.</span><span class="sxs-lookup"><span data-stu-id="fd767-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="fd767-111">Kích hoạt khi ngưỡng vượt quá trên một giá trị đo kinh doanh.</span><span class="sxs-lookup"><span data-stu-id="fd767-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="fd767-112">Kích hoạt bị giới hạn vượt quá ngưỡng.</span><span class="sxs-lookup"><span data-stu-id="fd767-112">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="fd767-113">Kích hoạt khi hoàn thành quá trình làm mới đầy đủ (nguồn dữ liệu, phân đoạn, đo lường...).</span><span class="sxs-lookup"><span data-stu-id="fd767-113">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="fd767-114">Kích hoạt khi hoàn tất quá trình làm mới quy trình hợp nhất (ánh xạ, khớp, hợp nhất).</span><span class="sxs-lookup"><span data-stu-id="fd767-114">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="fd767-115">[Đặt cấu hình trình kích hoạt trong Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span><span class="sxs-lookup"><span data-stu-id="fd767-115">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="fd767-116">Hành động Power Automate</span><span class="sxs-lookup"><span data-stu-id="fd767-116">Power Automate actions</span></span>
<span data-ttu-id="fd767-117">Trình kết nối Power Automate cung cấp các hành động khác ngoài trình kích hoạt có sẵn.</span><span class="sxs-lookup"><span data-stu-id="fd767-117">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="fd767-118">Để biết thêm thông tin, xem [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="fd767-118">For more information, see the [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow-in-audience-insights"></a><span data-ttu-id="fd767-119">Tạo quy trình Power Automate trong thông tin chi tiết về đối tượng</span><span class="sxs-lookup"><span data-stu-id="fd767-119">Create a Power Automate flow in audience insights</span></span>

1. <span data-ttu-id="fd767-120">Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Quản trị viên** > **Hệ thống**.</span><span class="sxs-lookup"><span data-stu-id="fd767-120">In audience insights, go to **Admin** > **System**.</span></span>

1. <span data-ttu-id="fd767-121">Trên trang **Hệ thống**, hãy chọn tab **Trạng thái**.</span><span class="sxs-lookup"><span data-stu-id="fd767-121">On the **System** page, select the **Status** tab.</span></span>

1. <span data-ttu-id="fd767-122">Trong phần **Nguồn dữ liệu**, hãy chọn **Dòng** rồi chọn **Tạo một dòng** từ danh sách thả xuống.</span><span class="sxs-lookup"><span data-stu-id="fd767-122">In the **Data Sources** section, select **Flows** and select **Create a flow** from the dropdown list.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="fd767-123">![Trình kết nối Power Automate hiển thị hành động Tạo dòng](media/power-automate-connector-create-flow.png "Trình kết nối Power Automate hiển thị hành động Tạo dòng")</span><span class="sxs-lookup"><span data-stu-id="fd767-123">![Power Automate connector showing Create a Flow action](media/power-automate-connector-create-flow.png "Power Automate connector showing Create a Flow action")</span></span>

1. <span data-ttu-id="fd767-124">Trong Power Automate, hãy chọn một trong các trình kích hoạt có sẵn để tạo dòng ưa thích của bạn.</span><span class="sxs-lookup"><span data-stu-id="fd767-124">In Power Automate, select one of the available triggers to create your preferred flow.</span></span> <span data-ttu-id="fd767-125">Nếu bạn đang tạo dòng đầu tiên của mình, bạn cần xác thực bằng trình kết nối Power Automate trước tiên.</span><span class="sxs-lookup"><span data-stu-id="fd767-125">If you're creating your first flow, you'll need to authenticate with the Power Automate connector first.</span></span>
