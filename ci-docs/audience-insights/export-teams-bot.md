---
title: Bot dành cho Microsoft Teams
description: Tra cứu hồ sơ khách hàng hợp nhất trong Microsoft Teams với sự giúp đỡ của một bot.
ms.date: 04/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 03299610fd41a7e142e3c9723fad56ce7f90e083
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267978"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a><span data-ttu-id="fb6f2-103">Bot Teams dành cho Dynamics 365 Customer Insights (bản xem trước)</span><span class="sxs-lookup"><span data-stu-id="fb6f2-103">Teams bot for Dynamics 365 Customer Insights (preview)</span></span>

<span data-ttu-id="fb6f2-104">Kết nối với Microsoft Teams để cho phép bot tra cứu hồ sơ khách hàng hợp nhất trong các kênh Teams.</span><span class="sxs-lookup"><span data-stu-id="fb6f2-104">Connect with Microsoft Teams to let a bot look up unified customer profiles in Teams channels.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="fb6f2-105">![Teams bot hiển thị hồ sơ khách hàng](media/teams-bot.png "Teams bot hiển thị hồ sơ khách hàng")</span><span class="sxs-lookup"><span data-stu-id="fb6f2-105">![Teams bot showing a customer record](media/teams-bot.png "Teams bot showing a customer record")</span></span>

## <a name="prerequisites"></a><span data-ttu-id="fb6f2-106">Điều kiện tiên quyết</span><span class="sxs-lookup"><span data-stu-id="fb6f2-106">Prerequisites</span></span>

<span data-ttu-id="fb6f2-107">Để thiết lập và đặt cấu hình cho bot, bạn phải đáp ứng những điều kiện tiên quyết sau đây:</span><span class="sxs-lookup"><span data-stu-id="fb6f2-107">To set up and configure the bot, the following prerequisites must be met:</span></span>

- <span data-ttu-id="fb6f2-108">Đã thêm ít nhất một [nguồn dữ liệu](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="fb6f2-108">There's at least one [data source added](data-sources.md).</span></span>
- <span data-ttu-id="fb6f2-109">Đã hoàn thành [quy trình hợp nhất](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="fb6f2-109">The [unification process](data-unification.md) is complete.</span></span>
- <span data-ttu-id="fb6f2-110">Đã thêm các trường vào [chỉ mục tìm kiếm và lọc](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="fb6f2-110">Fields are added to the [search and filter index](search-filter-index.md).</span></span>
- <span data-ttu-id="fb6f2-111">Customer Insights và Teams thuộc cùng một tổ chức.</span><span class="sxs-lookup"><span data-stu-id="fb6f2-111">Customer Insights and Teams are in the same organization.</span></span>

## <a name="configure-the-bot"></a><span data-ttu-id="fb6f2-112">Đặt cấu hình bot</span><span class="sxs-lookup"><span data-stu-id="fb6f2-112">Configure the bot</span></span>

1. <span data-ttu-id="fb6f2-113">Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Quản trị viên** > **Điểm đến xuất**.</span><span class="sxs-lookup"><span data-stu-id="fb6f2-113">In audience insights, go to **Admin** > **Export Destinations**.</span></span>
1. <span data-ttu-id="fb6f2-114">Trên lát Microsoft Teams, chọn **Thiết lập**.</span><span class="sxs-lookup"><span data-stu-id="fb6f2-114">On the Microsoft Teams tile, select **Set up**.</span></span>
1. <span data-ttu-id="fb6f2-115">Bạn sẽ được chuyển đến vùng **Ứng dụng** trong Teams.</span><span class="sxs-lookup"><span data-stu-id="fb6f2-115">You're redirected to the **Apps** area in Teams.</span></span> <span data-ttu-id="fb6f2-116">Bạn cũng có thể mở Teams rồi chọn **Ứng dụng** ở góc dưới bên trái hoặc [tải trực tiếp từ AppSource](https://go.microsoft.com/fwlink/?linkid=2124104).</span><span class="sxs-lookup"><span data-stu-id="fb6f2-116">You can also open Teams and select **Apps** in the bottom-left corner or [get it from AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) directly.</span></span>
1. <span data-ttu-id="fb6f2-117">Tìm **Customer Insights** rồi chọn ứng dụng này.</span><span class="sxs-lookup"><span data-stu-id="fb6f2-117">Search for **Customer Insights** and select the app.</span></span>
1. <span data-ttu-id="fb6f2-118">Chọn **Thêm**.</span><span class="sxs-lookup"><span data-stu-id="fb6f2-118">Select **Add**.</span></span>
1. <span data-ttu-id="fb6f2-119">Sau khi đăng nhập vào Customer Insights trong Teams, bạn sẽ thấy thông báo chào mừng và có thể bắt đầu.</span><span class="sxs-lookup"><span data-stu-id="fb6f2-119">After signing in to Customer Insights in Teams, you'll see a welcome message and can get started.</span></span>

## <a name="things-you-can-do-with-the-bot"></a><span data-ttu-id="fb6f2-120">Những điều bạn có thể làm với bot</span><span class="sxs-lookup"><span data-stu-id="fb6f2-120">Things you can do with the bot</span></span>

<span data-ttu-id="fb6f2-121">Bot mang đến các chức năng tra cứu đối với hồ sơ khách hàng hợp nhất.</span><span class="sxs-lookup"><span data-stu-id="fb6f2-121">The bot provides lookup capabilities for unified customer profiles.</span></span>

- <span data-ttu-id="fb6f2-122">Nhập **tìm kiếm** rồi đến tên, địa chỉ email hoặc bất kỳ trường nào khác trên hồ sơ khách hàng hợp nhất mà đã được thêm vào chỉ mục lọc và tìm kiếm.</span><span class="sxs-lookup"><span data-stu-id="fb6f2-122">Enter **search** followed by a name, email address, or any other field on the unified customer profile that is added to the search and filter index.</span></span>

  <span data-ttu-id="fb6f2-123">Bạn sẽ nhận được một thẻ có tối đa 15 trường từ kết quả hồ sơ khách hàng trả về.</span><span class="sxs-lookup"><span data-stu-id="fb6f2-123">You'll get a card with up to 15 fields from the resulting customer profile.</span></span> <span data-ttu-id="fb6f2-124">Khi có nhiều kết quả khớp, hệ thống sẽ trả về một danh sách mà bạn có thể chọn hồ sơ.</span><span class="sxs-lookup"><span data-stu-id="fb6f2-124">Multiple matches return a list of results where you can select a profile.</span></span> <span data-ttu-id="fb6f2-125">Bạn có thể thêm cụm từ tìm kiếm trong ngoặc kép để tra cứu kết quả khớp hoàn toàn.</span><span class="sxs-lookup"><span data-stu-id="fb6f2-125">You can add the search term in double quotes to look up an exact match.</span></span>

- <span data-ttu-id="fb6f2-126">Nếu tổ chức của bạn duy trì nhiều môi trường Customer Insights trong cùng một tổ chức, bạn có thể nhập **switchinstance** để chọn môi trường bạn muốn kết nối với bot.</span><span class="sxs-lookup"><span data-stu-id="fb6f2-126">If your organization maintains multiple Customer Insights environments in the same organization, you can enter **switchinstance** to choose which environment you want to connect the bot to.</span></span>

- <span data-ttu-id="fb6f2-127">Nhập **trợ giúp** để xem danh sách các lệnh có thể dùng cho bot.</span><span class="sxs-lookup"><span data-stu-id="fb6f2-127">Enter **help** to see a list of available commands for the bot.</span></span>  


[!INCLUDE[footer-include](../includes/footer-banner.md)]