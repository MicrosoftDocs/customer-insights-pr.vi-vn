---
title: Tăng cường dữ liệu hồ sơ khách hàng hợp nhất
description: Sử dụng các khả năng để tăng cường dữ liệu khách hàng của bạn.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: c35e73b366fcd5db2ba5a757295ddda6db30efa0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305274"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="2e630-103">Tăng cường dữ liệu hồ sơ khách hàng (bản xem trước)</span><span class="sxs-lookup"><span data-stu-id="2e630-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="2e630-104">Sử dụng dữ liệu từ các nguồn như Microsoft và các đối tác khác để tăng cường dữ liệu khách hàng của bạn.</span><span class="sxs-lookup"><span data-stu-id="2e630-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Trang trung tâm tăng cường":::

<span data-ttu-id="2e630-106">Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Dữ liệu** > **Tăng cường** để làm việc với các tùy chọn tăng cường.</span><span class="sxs-lookup"><span data-stu-id="2e630-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>  

<span data-ttu-id="2e630-107">Bạn cần có quyền của Người đóng góp hoặc Quản trị viên để tạo hoặc chỉnh sửa phần dữ liệu tăng cường.</span><span class="sxs-lookup"><span data-stu-id="2e630-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="2e630-108">Để biết thêm thông tin, hãy xem [Quyền](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="2e630-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="2e630-109">Trên tab **Khám phá**, bạn sẽ tìm thấy những dữ liệu tăng cường sau:</span><span class="sxs-lookup"><span data-stu-id="2e630-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="2e630-110">[Thương hiệu](enrichment-microsoft.md) do Microsoft cung cấp</span><span class="sxs-lookup"><span data-stu-id="2e630-110">[Brands](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="2e630-111">[Sở thích](enrichment-microsoft.md) do Microsoft cung cấp</span><span class="sxs-lookup"><span data-stu-id="2e630-111">[Interests](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="2e630-112">[Địa chỉ nâng cao](enrichment-enhanced-addresses.md) do Microsoft cung cấp</span><span class="sxs-lookup"><span data-stu-id="2e630-112">[Enhanced addresses](enrichment-enhanced-addresses.md) provided by Microsoft</span></span>
- <span data-ttu-id="2e630-113">[Dữ liệu công ty](enrichment-leadspace.md) do Leadspace cung cấp</span><span class="sxs-lookup"><span data-stu-id="2e630-113">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="2e630-114">[Dữ liệu nhân khẩu học](enrichment-experian.md) do Experian cung cấp</span><span class="sxs-lookup"><span data-stu-id="2e630-114">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="2e630-115">[Dữ liệu vị trí](enrichment-here.md) do HERE Technologies cung cấp</span><span class="sxs-lookup"><span data-stu-id="2e630-115">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="2e630-116">[Dữ liệu tùy chỉnh](enrichment-SFTP-custom-import.md) thông qua Secure File Transfer Protocol (SFTP)</span><span class="sxs-lookup"><span data-stu-id="2e630-116">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="2e630-117">Trên tab **Dữ liệu tăng cường của tôi**, bạn có thể xem thông tin bổ sung mà mình đã định cấu hình và chỉnh sửa thuộc tính.</span><span class="sxs-lookup"><span data-stu-id="2e630-117">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="2e630-118">Quản lý dữ liệu tăng cường hiện có</span><span class="sxs-lookup"><span data-stu-id="2e630-118">Manage existing enrichments</span></span>

<span data-ttu-id="2e630-119">Đi đến tab **Dữ liệu tăng cường của tôi** để xem tất cả thông tin bổ sung đã định cấu hình.</span><span class="sxs-lookup"><span data-stu-id="2e630-119">Go to the **My enrichments** tab to see all configured enrichments.</span></span> <span data-ttu-id="2e630-120">Mỗi dữ liệu tăng cường được biểu thị bằng một hàng bao gồm thông tin bổ sung về dữ liệu tăng cường đó.</span><span class="sxs-lookup"><span data-stu-id="2e630-120">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="2e630-121">Chọn dữ liệu tăng cường để xem các tùy chọn có sẵn.</span><span class="sxs-lookup"><span data-stu-id="2e630-121">Select an enrichment to see the available options.</span></span> <span data-ttu-id="2e630-122">Bạn cũng có thể chọn dấu chấm lửng (...) trên một mục danh sách để xem các tùy chọn.</span><span class="sxs-lookup"><span data-stu-id="2e630-122">You can also select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Các tùy chọn quản lý dữ liệu tăng cường trong danh sách dữ liệu tăng cường":::

- <span data-ttu-id="2e630-124">**Xem** thông tin chi tiết về dữ liệu tăng cường với số hồ sơ khách hàng được tăng cường.</span><span class="sxs-lookup"><span data-stu-id="2e630-124">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="2e630-125">**Chỉnh sửa** cấu hình dữ liệu tăng cường.</span><span class="sxs-lookup"><span data-stu-id="2e630-125">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="2e630-126">**Chạy** sự dữ liệu tăng cường để cập nhật hồ sơ khách hàng với dữ liệu mới nhất.</span><span class="sxs-lookup"><span data-stu-id="2e630-126">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="2e630-127">**Vô hiệu hóa** dữ liệu tăng cường hiện có để thông tin đó không làm mới tự động với mỗi lần làm mới theo lịch.</span><span class="sxs-lookup"><span data-stu-id="2e630-127">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="2e630-128">Dữ liệu từ lần làm mới thành công gần nhất sẽ tiếp tục hiển thị.</span><span class="sxs-lookup"><span data-stu-id="2e630-128">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="2e630-129">**Kích hoạt** dữ liệu tăng cường không hoạt động để khởi động lại tính năng làm mới tự động với mỗi lần làm mới theo lịch.</span><span class="sxs-lookup"><span data-stu-id="2e630-129">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="2e630-130">**Xóa** dữ liệu tăng cường.</span><span class="sxs-lookup"><span data-stu-id="2e630-130">**Delete** an enrichment.</span></span>

<span data-ttu-id="2e630-131">Bạn có thể chạy hoặc hủy kích hoạt nhiều dữ liệu tăng cường cùng một lúc bằng cách chọn trong danh sách.</span><span class="sxs-lookup"><span data-stu-id="2e630-131">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="2e630-132">Xem và chỉnh sửa các tùy chọn hiện không thực hiện được dưới dạng hành động hàng loạt và tính năng này chỉ hoạt động với một dữ liệu tăng cường mỗi lần.</span><span class="sxs-lookup"><span data-stu-id="2e630-132">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>

## <a name="enrichments-and-connections"></a><span data-ttu-id="2e630-133">Dữ liệu tăng cường và kết nối</span><span class="sxs-lookup"><span data-stu-id="2e630-133">Enrichments and connections</span></span>

<span data-ttu-id="2e630-134">Các dữ liệu tăng cường của bên thứ ba được định cấu hình bằng cách sử dụng [kết nối](connections.md) do quản trị viên thiết lập bằng thông tin xác thực và cho phép truyền dữ liệu.</span><span class="sxs-lookup"><span data-stu-id="2e630-134">Third-party enrichments are configured using [connections](connections.md), which an administrator sets up with credentials and provides consent for data transfers.</span></span> <span data-ttu-id="2e630-135">Quản trị viên và người đóng góp có thể dùng kết nối để định cấu hình dữ liệu tăng cường.</span><span class="sxs-lookup"><span data-stu-id="2e630-135">The connection can be used by administrators and contributors to configure enrichments.</span></span>  

## <a name="multiple-enrichments-of-the-same-type"></a><span data-ttu-id="2e630-136">Nhiều dữ liệu tăng cường thuộc cùng loại</span><span class="sxs-lookup"><span data-stu-id="2e630-136">Multiple enrichments of the same type</span></span>

<span data-ttu-id="2e630-137">Thực thể cần tăng cường sẽ được chỉ định trong quá trình định cấu hình dữ liệu tăng cường. Nhờ đó, bạn có thể chỉ cần tăng cường một tập hợp con các cấu hình của mình.</span><span class="sxs-lookup"><span data-stu-id="2e630-137">The entity to be enriched is specified during the enrichment configuration, which allows you to enrich only a subset of your profiles.</span></span> <span data-ttu-id="2e630-138">Ví dụ: chỉ tăng cường dữ liệu cho một phân khúc cụ thể.</span><span class="sxs-lookup"><span data-stu-id="2e630-138">For example, enrich data only for a specific segment.</span></span> <span data-ttu-id="2e630-139">Bạn có thể định cấu hình một số dữ liệu tăng cường thuộc cùng loại và sử dụng lại cùng một kết nối.</span><span class="sxs-lookup"><span data-stu-id="2e630-139">You can configure several enrichments of the same type and reuse the same connection.</span></span> <span data-ttu-id="2e630-140">Một số dữ liệu tăng cường sẽ có giới hạn về số lượng dữ liệu tăng cường thuộc cùng loại có thể được tạo ra.</span><span class="sxs-lookup"><span data-stu-id="2e630-140">Some enrichments will have limits to the number of enrichments of the same type that can be created.</span></span> <span data-ttu-id="2e630-141">Bạn có thể xem các giới hạn và việc sử dụng hiện tại trên trang **Dữ liệu tăng cường**.</span><span class="sxs-lookup"><span data-stu-id="2e630-141">The limits and current use can be seen on the **Enrichment** page.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
