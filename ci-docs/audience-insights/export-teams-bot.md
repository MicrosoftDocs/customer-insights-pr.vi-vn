---
title: Bot dành cho Microsoft Teams
description: Tra cứu hồ sơ khách hàng hợp nhất trong Microsoft Teams với sự giúp đỡ của một bot.
ms.date: 04/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 45ea23fbefe5f1d44c3961183b76d2cc5c45355e
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407322"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a><span data-ttu-id="6f26d-103">Bot Teams dành cho Dynamics 365 Customer Insights (bản xem trước)</span><span class="sxs-lookup"><span data-stu-id="6f26d-103">Teams bot for Dynamics 365 Customer Insights (preview)</span></span>

<span data-ttu-id="6f26d-104">Kết nối với Microsoft Teams để cho phép bot tra cứu hồ sơ khách hàng hợp nhất trong các kênh Teams.</span><span class="sxs-lookup"><span data-stu-id="6f26d-104">Connect with Microsoft Teams to let a bot look up unified customer profiles in Teams channels.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="6f26d-105">![Teams bot hiển thị hồ sơ khách hàng](media/teams-bot.png "Teams bot hiển thị hồ sơ khách hàng")</span><span class="sxs-lookup"><span data-stu-id="6f26d-105">![Teams bot showing a customer record](media/teams-bot.png "Teams bot showing a customer record")</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6f26d-106">Điều kiện tiên quyết</span><span class="sxs-lookup"><span data-stu-id="6f26d-106">Prerequisites</span></span>

<span data-ttu-id="6f26d-107">Để thiết lập và đặt cấu hình cho bot, bạn phải đáp ứng những điều kiện tiên quyết sau đây:</span><span class="sxs-lookup"><span data-stu-id="6f26d-107">To set up and configure the bot, the following prerequisites must be met:</span></span>

- <span data-ttu-id="6f26d-108">Đã thêm ít nhất một [nguồn dữ liệu](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="6f26d-108">There's at least one [data source added](data-sources.md).</span></span>
- <span data-ttu-id="6f26d-109">Đã hoàn thành [quy trình hợp nhất](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="6f26d-109">The [unification process](data-unification.md) is complete.</span></span>
- <span data-ttu-id="6f26d-110">Đã thêm các trường vào [chỉ mục tìm kiếm và lọc](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="6f26d-110">Fields are added to the [search and filter index](search-filter-index.md).</span></span>
- <span data-ttu-id="6f26d-111">Customer Insights và Teams thuộc cùng một tổ chức.</span><span class="sxs-lookup"><span data-stu-id="6f26d-111">Customer Insights and Teams are in the same organization.</span></span>

## <a name="configure-the-bot"></a><span data-ttu-id="6f26d-112">Đặt cấu hình bot</span><span class="sxs-lookup"><span data-stu-id="6f26d-112">Configure the bot</span></span>

1. <span data-ttu-id="6f26d-113">Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Quản trị viên** > **Điểm đến xuất**.</span><span class="sxs-lookup"><span data-stu-id="6f26d-113">In audience insights, go to **Admin** > **Export Destinations**.</span></span>
1. <span data-ttu-id="6f26d-114">Trên lát Microsoft Teams, chọn **Thiết lập**.</span><span class="sxs-lookup"><span data-stu-id="6f26d-114">On the Microsoft Teams tile, select **Set up**.</span></span>
1. <span data-ttu-id="6f26d-115">Bạn sẽ được chuyển đến vùng **Ứng dụng** trong Teams.</span><span class="sxs-lookup"><span data-stu-id="6f26d-115">You're redirected to the **Apps** area in Teams.</span></span> <span data-ttu-id="6f26d-116">Bạn cũng có thể mở Teams rồi chọn **Ứng dụng** ở góc dưới bên trái hoặc [tải trực tiếp từ AppSource](https://go.microsoft.com/fwlink/?linkid=2124104).</span><span class="sxs-lookup"><span data-stu-id="6f26d-116">You can also open Teams and select **Apps** in the bottom-left corner or [get it from AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) directly.</span></span>
1. <span data-ttu-id="6f26d-117">Tìm **Customer Insights** rồi chọn ứng dụng này.</span><span class="sxs-lookup"><span data-stu-id="6f26d-117">Search for **Customer Insights** and select the app.</span></span>
1. <span data-ttu-id="6f26d-118">Chọn **Thêm**.</span><span class="sxs-lookup"><span data-stu-id="6f26d-118">Select **Add**.</span></span>
1. <span data-ttu-id="6f26d-119">Sau khi đăng nhập vào Customer Insights trong Teams, bạn sẽ thấy thông báo chào mừng và có thể bắt đầu.</span><span class="sxs-lookup"><span data-stu-id="6f26d-119">After signing in to Customer Insights in Teams, you'll see a welcome message and can get started.</span></span>

## <a name="things-you-can-do-with-the-bot"></a><span data-ttu-id="6f26d-120">Những điều bạn có thể làm với bot</span><span class="sxs-lookup"><span data-stu-id="6f26d-120">Things you can do with the bot</span></span>

<span data-ttu-id="6f26d-121">Bot mang đến các chức năng tra cứu đối với hồ sơ khách hàng hợp nhất.</span><span class="sxs-lookup"><span data-stu-id="6f26d-121">The bot provides lookup capabilities for unified customer profiles.</span></span>

- <span data-ttu-id="6f26d-122">Nhập **tìm kiếm** rồi đến tên, địa chỉ email hoặc bất kỳ trường nào khác trên hồ sơ khách hàng hợp nhất mà đã được thêm vào chỉ mục lọc và tìm kiếm.</span><span class="sxs-lookup"><span data-stu-id="6f26d-122">Enter **search** followed by a name, email address, or any other field on the unified customer profile that is added to the search and filter index.</span></span>

  <span data-ttu-id="6f26d-123">Bạn sẽ nhận được một thẻ có tối đa 15 trường từ kết quả hồ sơ khách hàng trả về.</span><span class="sxs-lookup"><span data-stu-id="6f26d-123">You'll get a card with up to 15 fields from the resulting customer profile.</span></span> <span data-ttu-id="6f26d-124">Khi có nhiều kết quả khớp, hệ thống sẽ trả về một danh sách mà bạn có thể chọn hồ sơ.</span><span class="sxs-lookup"><span data-stu-id="6f26d-124">Multiple matches return a list of results where you can select a profile.</span></span> <span data-ttu-id="6f26d-125">Bạn có thể thêm cụm từ tìm kiếm trong ngoặc kép để tra cứu kết quả khớp hoàn toàn.</span><span class="sxs-lookup"><span data-stu-id="6f26d-125">You can add the search term in double quotes to look up an exact match.</span></span>

- <span data-ttu-id="6f26d-126">Nếu tổ chức của bạn duy trì nhiều môi trường Customer Insights trong cùng một tổ chức, bạn có thể nhập **switchinstance** để chọn môi trường bạn muốn kết nối với bot.</span><span class="sxs-lookup"><span data-stu-id="6f26d-126">If your organization maintains multiple Customer Insights environments in the same organization, you can enter **switchinstance** to choose which environment you want to connect the bot to.</span></span>

- <span data-ttu-id="6f26d-127">Nhập **trợ giúp** để xem danh sách các lệnh có thể dùng cho bot.</span><span class="sxs-lookup"><span data-stu-id="6f26d-127">Enter **help** to see a list of available commands for the bot.</span></span>  
