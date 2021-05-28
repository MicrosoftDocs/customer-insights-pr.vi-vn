---
title: Tăng cường hồ sơ khách hàng hợp nhất
description: Sử dụng các khả năng để tăng cường dữ liệu khách hàng của bạn.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: c8e4a7247ccf575a62440038180010916b09d51b
ms.sourcegitcommit: f9e2fa3f11ecf11a5d9cccc376fdeb1ecea54880
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 04/28/2021
ms.locfileid: "5954513"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="9b872-103">Làm phong phú hồ sơ khách hàng (Xem trước)</span><span class="sxs-lookup"><span data-stu-id="9b872-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="9b872-104">Sử dụng dữ liệu từ các nguồn như Microsoft và các đối tác khác để làm phong phú dữ liệu khách hàng của bạn.</span><span class="sxs-lookup"><span data-stu-id="9b872-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Trang trung tâm làm phong phú":::

<span data-ttu-id="9b872-106">Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Dữ liệu** > **Tăng cường** để làm việc với các tùy chọn tăng cường.</span><span class="sxs-lookup"><span data-stu-id="9b872-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>    
<span data-ttu-id="9b872-107">Bạn cần có quyền của Người đóng góp hoặc Quản trị viên để tạo hoặc chỉnh sửa phần nội dung phong phú.</span><span class="sxs-lookup"><span data-stu-id="9b872-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="9b872-108">Để biết thêm thông tin, hãy xem [Quyền](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="9b872-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="9b872-109">Trên tab **Khám phá**, bạn sẽ tìm thấy những nội dung phong phú sau:</span><span class="sxs-lookup"><span data-stu-id="9b872-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="9b872-110">[Thương hiệu](enrichment-microsoft.md) do Microsoft cung cấp</span><span class="sxs-lookup"><span data-stu-id="9b872-110">[Brands](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="9b872-111">[Sở thích](enrichment-microsoft.md) do Microsoft cung cấp</span><span class="sxs-lookup"><span data-stu-id="9b872-111">[Interests](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="9b872-112">[Địa chỉ nâng cao](enrichment-enhanced-addresses.md) do Microsoft cung cấp</span><span class="sxs-lookup"><span data-stu-id="9b872-112">[Enhanced addresses](enrichment-enhanced-addresses.md) provided by Microsoft</span></span>
- <span data-ttu-id="9b872-113">[Dữ liệu công ty](enrichment-leadspace.md) do Leadspace cung cấp</span><span class="sxs-lookup"><span data-stu-id="9b872-113">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="9b872-114">[Dữ liệu nhân khẩu học](enrichment-experian.md) do Experian cung cấp</span><span class="sxs-lookup"><span data-stu-id="9b872-114">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="9b872-115">[Dữ liệu vị trí](enrichment-here.md) do HERE Technologies cung cấp</span><span class="sxs-lookup"><span data-stu-id="9b872-115">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="9b872-116">[Dữ liệu tùy chỉnh](enrichment-SFTP-custom-import.md) thông qua Secure File Transfer Protocol (SFTP)</span><span class="sxs-lookup"><span data-stu-id="9b872-116">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="9b872-117">Trên tab **Nội dung phong phú**, bạn có thể xem các nội dung phong phú mình đã đặt cấu hình và chỉnh sửa thuộc tính.</span><span class="sxs-lookup"><span data-stu-id="9b872-117">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="9b872-118">Quản lý nội dung phong phú hiện có</span><span class="sxs-lookup"><span data-stu-id="9b872-118">Manage existing enrichments</span></span>

<span data-ttu-id="9b872-119">Chuyển đến **Nội dung phong phú của tôi** để xem tất cả nội dung phong phú được cấu hình.</span><span class="sxs-lookup"><span data-stu-id="9b872-119">Go to the **My enrichments** to see all configured enrichments.</span></span> <span data-ttu-id="9b872-120">Mỗi nội dung phong phú được biểu thị bằng một hàng bao gồm thông tin bổ sung về nội dung phong phú đó.</span><span class="sxs-lookup"><span data-stu-id="9b872-120">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="9b872-121">Chọn nội dung phong phú để xem các tùy chọn có sẵn.</span><span class="sxs-lookup"><span data-stu-id="9b872-121">Select an enrichment to see the available options.</span></span> <span data-ttu-id="9b872-122">Bạn cũng có thể chọn dấu chấm lửng (...) trên một mục danh sách để xem các tùy chọn.</span><span class="sxs-lookup"><span data-stu-id="9b872-122">You can also select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Các tùy chọn quản lý nội dung phong phú trong danh sách nội dung phong phú":::

- <span data-ttu-id="9b872-124">**Xem** thông tin chi tiết về nội dung phong phú với một số hồ sơ khách hàng phong phú.</span><span class="sxs-lookup"><span data-stu-id="9b872-124">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="9b872-125">**Chỉnh sửa** cấu hình nội dung phong phú.</span><span class="sxs-lookup"><span data-stu-id="9b872-125">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="9b872-126">**Chạy** sự nội dung tăng cường để cập nhật hồ sơ khách hàng với dữ liệu mới nhất.</span><span class="sxs-lookup"><span data-stu-id="9b872-126">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="9b872-127">**Vô hiệu hóa** nội dung phong phú hiện có để nội dung đó không làm mới tự động với mỗi lần làm mới theo lịch.</span><span class="sxs-lookup"><span data-stu-id="9b872-127">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="9b872-128">Dữ liệu từ lần làm mới thành công gần nhất sẽ tiếp tục hiển thị.</span><span class="sxs-lookup"><span data-stu-id="9b872-128">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="9b872-129">**Kích hoạt** nội dung phong phú không hoạt động để khởi động lại tính năng làm mới tự động với mỗi lần làm mới theo lịch.</span><span class="sxs-lookup"><span data-stu-id="9b872-129">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="9b872-130">**Xóa** nội dung tăng cường.</span><span class="sxs-lookup"><span data-stu-id="9b872-130">**Delete** an enrichment.</span></span>

<span data-ttu-id="9b872-131">Bạn có thể chạy hoặc hủy kích hoạt nhiều nội dung tăng cường cùng một lúc bằng cách chọn trong danh sách.</span><span class="sxs-lookup"><span data-stu-id="9b872-131">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="9b872-132">Xem và chỉnh sửa các tùy chọn hiện không thực hiện được dưới dạng hành động hàng loạt và tính năng này chỉ hoạt động với một nội dung phong phú mỗi lần.</span><span class="sxs-lookup"><span data-stu-id="9b872-132">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>

## <a name="enrichments-and-connections"></a><span data-ttu-id="9b872-133">Nội dung bổ sung và kết nối</span><span class="sxs-lookup"><span data-stu-id="9b872-133">Enrichments and connections</span></span>

<span data-ttu-id="9b872-134">Các nội dung bổ sung của bên thứ ba được đặt cấu hình bằng cách sử dụng [kết nối](connections.md) do quản trị viên thiết lập bằng thông tin xác thực và cho phép chuyển dữ liệu.</span><span class="sxs-lookup"><span data-stu-id="9b872-134">Third-party enrichments are configured using [connections](connections.md), which an administrator sets up with credentials and provides consent for data transfers.</span></span> <span data-ttu-id="9b872-135">Quản trị viên và người đóng góp có thể dùng kết nối để đặt cấu hình nội dung bổ sung.</span><span class="sxs-lookup"><span data-stu-id="9b872-135">The connection can be used by administrators and contributors to configure enrichments.</span></span>  

## <a name="multiple-enrichments-of-the-same-type"></a><span data-ttu-id="9b872-136">Nhiều nội dung bổ sung thuộc cùng loại</span><span class="sxs-lookup"><span data-stu-id="9b872-136">Multiple enrichments of the same type</span></span>

<span data-ttu-id="9b872-137">Thực thể cần bổ sung sẽ được chỉ định trong quá trình đặt cấu hình nội dung bổ sung. Nhờ đó, bạn có thể chỉ cần bổ sung một tập hợp con các cấu hình của mình.</span><span class="sxs-lookup"><span data-stu-id="9b872-137">The entity to be enriched is specified during the enrichment configuration, which allows you to enrich only a subset of your profiles.</span></span> <span data-ttu-id="9b872-138">Ví dụ: chỉ bổ sung dữ liệu cho một phân khúc cụ thể.</span><span class="sxs-lookup"><span data-stu-id="9b872-138">For exmaple, enrich data only for a specific segment.</span></span> <span data-ttu-id="9b872-139">Bạn có thể đặt cấu hình một số nội dung bổ sung thuộc cùng loại và sử dụng lại cùng một kết nối.</span><span class="sxs-lookup"><span data-stu-id="9b872-139">You can configure several enrichments of the same type and reuse the same connection.</span></span> <span data-ttu-id="9b872-140">Một số nội dung bổ sung sẽ có giới hạn về số lượng nội dung bổ sung thuộc cùng loại có thể được tạo ra.</span><span class="sxs-lookup"><span data-stu-id="9b872-140">Some enrichments will have limits to the number of enrichments of the same type that can be created.</span></span> <span data-ttu-id="9b872-141">Bạn có thể xem các giới hạn và việc sử dụng hiện tại trên trang **Nội dung bổ sung**.</span><span class="sxs-lookup"><span data-stu-id="9b872-141">The limits and current use can be seen on the **Enrichment** page.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
