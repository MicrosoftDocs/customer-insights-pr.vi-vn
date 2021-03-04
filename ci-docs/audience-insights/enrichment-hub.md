---
title: Tăng cường hồ sơ khách hàng hợp nhất
description: Sử dụng các khả năng để tăng cường dữ liệu khách hàng của bạn.
ms.date: 11/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 6b73aa93ec1a98f2b8d20d02e88bc6304f887078
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269494"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="67f74-103">Làm phong phú hồ sơ khách hàng (Xem trước)</span><span class="sxs-lookup"><span data-stu-id="67f74-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="67f74-104">Sử dụng dữ liệu từ các nguồn như Microsoft và các đối tác khác để làm phong phú dữ liệu khách hàng của bạn.</span><span class="sxs-lookup"><span data-stu-id="67f74-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Trang trung tâm làm phong phú":::

<span data-ttu-id="67f74-106">Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Dữ liệu** > **Tăng cường** để làm việc với các tùy chọn tăng cường.</span><span class="sxs-lookup"><span data-stu-id="67f74-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>    
<span data-ttu-id="67f74-107">Bạn cần có quyền của Người đóng góp hoặc Quản trị viên để tạo hoặc chỉnh sửa phần nội dung phong phú.</span><span class="sxs-lookup"><span data-stu-id="67f74-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="67f74-108">Để biết thêm thông tin, hãy xem [Quyền](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="67f74-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="67f74-109">Trên tab **Khám phá**, bạn sẽ tìm thấy những nội dung phong phú sau:</span><span class="sxs-lookup"><span data-stu-id="67f74-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="67f74-110">[Thương hiệu](enrichment-microsoft-graph.md) do Microsoft Graph cung cấp</span><span class="sxs-lookup"><span data-stu-id="67f74-110">[Brands](enrichment-microsoft-graph.md) provided by Microsoft Graph</span></span>
- <span data-ttu-id="67f74-111">[Sở thích](enrichment-microsoft-graph.md) do Microsoft Graph cung cấp</span><span class="sxs-lookup"><span data-stu-id="67f74-111">[Interests](enrichment-microsoft-graph.md) provided by Microsoft Graph</span></span>
- <span data-ttu-id="67f74-112">[Dữ liệu công ty](enrichment-leadspace.md) do Leadspace cung cấp</span><span class="sxs-lookup"><span data-stu-id="67f74-112">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="67f74-113">[Dữ liệu nhân khẩu học](enrichment-experian.md) do Experian cung cấp</span><span class="sxs-lookup"><span data-stu-id="67f74-113">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="67f74-114">[Dữ liệu vị trí](enrichment-here.md) do HERE Technologies cung cấp</span><span class="sxs-lookup"><span data-stu-id="67f74-114">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="67f74-115">[Dữ liệu tùy chỉnh](enrichment-SFTP-custom-import.md) thông qua Secure File Transfer Protocol (SFTP)</span><span class="sxs-lookup"><span data-stu-id="67f74-115">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="67f74-116">Trên tab **Nội dung phong phú**, bạn có thể xem các nội dung phong phú mình đã đặt cấu hình và chỉnh sửa thuộc tính.</span><span class="sxs-lookup"><span data-stu-id="67f74-116">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="67f74-117">Quản lý nội dung phong phú hiện có</span><span class="sxs-lookup"><span data-stu-id="67f74-117">Manage existing enrichments</span></span>

<span data-ttu-id="67f74-118">Chuyển đến **Nội dung phong phú của tôi** để xem tất cả nội dung phong phú được cấu hình.</span><span class="sxs-lookup"><span data-stu-id="67f74-118">Go to the **My enrichments** to see all configured enrichments.</span></span> <span data-ttu-id="67f74-119">Mỗi nội dung phong phú được biểu thị bằng một hàng bao gồm thông tin bổ sung về nội dung phong phú đó.</span><span class="sxs-lookup"><span data-stu-id="67f74-119">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="67f74-120">Chọn nội dung phong phú để xem các tùy chọn có sẵn.</span><span class="sxs-lookup"><span data-stu-id="67f74-120">Select an enrichment to see the available options.</span></span> <span data-ttu-id="67f74-121">Ngoài ra, bạn có thể chọn dấu ba chấm (...) trên mục danh sách để xem các tùy chọn.</span><span class="sxs-lookup"><span data-stu-id="67f74-121">Alternatively, you can select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Các tùy chọn quản lý nội dung phong phú trong danh sách nội dung phong phú":::

- <span data-ttu-id="67f74-123">**Xem** thông tin chi tiết về nội dung phong phú với một số hồ sơ khách hàng phong phú.</span><span class="sxs-lookup"><span data-stu-id="67f74-123">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="67f74-124">**Chỉnh sửa** cấu hình nội dung phong phú.</span><span class="sxs-lookup"><span data-stu-id="67f74-124">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="67f74-125">**Chạy** sự nội dung tăng cường để cập nhật hồ sơ khách hàng với dữ liệu mới nhất.</span><span class="sxs-lookup"><span data-stu-id="67f74-125">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="67f74-126">**Vô hiệu hóa** nội dung phong phú hiện có để nội dung đó không làm mới tự động với mỗi lần làm mới theo lịch.</span><span class="sxs-lookup"><span data-stu-id="67f74-126">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="67f74-127">Dữ liệu từ lần làm mới thành công gần nhất sẽ tiếp tục hiển thị.</span><span class="sxs-lookup"><span data-stu-id="67f74-127">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="67f74-128">**Kích hoạt** nội dung phong phú không hoạt động để khởi động lại tính năng làm mới tự động với mỗi lần làm mới theo lịch.</span><span class="sxs-lookup"><span data-stu-id="67f74-128">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="67f74-129">**Xóa** nội dung tăng cường.</span><span class="sxs-lookup"><span data-stu-id="67f74-129">**Delete** an enrichment.</span></span>

<span data-ttu-id="67f74-130">Bạn có thể chạy hoặc hủy kích hoạt nhiều nội dung tăng cường cùng một lúc bằng cách chọn trong danh sách.</span><span class="sxs-lookup"><span data-stu-id="67f74-130">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="67f74-131">Xem và chỉnh sửa các tùy chọn hiện không thực hiện được dưới dạng hành động hàng loạt và tính năng này chỉ hoạt động với một nội dung phong phú mỗi lần.</span><span class="sxs-lookup"><span data-stu-id="67f74-131">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]