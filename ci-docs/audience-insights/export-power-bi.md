---
title: Trình kết nối Power BI
description: Tìm hiểu về cách dùng trình kết nối Dynamics 365 Customer Insights trong Power BI.
ms.date: 09/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: e43e2f9dbc84ebfbf2154990a752740f973296cb
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596065"
---
# <a name="connector-for-power-bi-preview"></a><span data-ttu-id="94632-103">Trình kết nối cho Power BI (xem trước)</span><span class="sxs-lookup"><span data-stu-id="94632-103">Connector for Power BI (preview)</span></span>

<span data-ttu-id="94632-104">Tạo trực quan hóa cho dữ liệu của bạn với Power BI Desktop.</span><span class="sxs-lookup"><span data-stu-id="94632-104">Create visualizations for your data with the Power BI Desktop.</span></span> <span data-ttu-id="94632-105">Tạo thông tin chi tiết bổ sung và xây dựng báo cáo với dữ liệu khách hàng hợp nhất của bạn.</span><span class="sxs-lookup"><span data-stu-id="94632-105">Generate additional insights and build reports with your unified customer data.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="94632-106">Điều kiện tiên quyết</span><span class="sxs-lookup"><span data-stu-id="94632-106">Prerequisites</span></span>

- <span data-ttu-id="94632-107">Bạn có hồ sơ khách hàng hợp nhất.</span><span class="sxs-lookup"><span data-stu-id="94632-107">You have unified customer profiles.</span></span>
- <span data-ttu-id="94632-108">Phiên bản mới nhất của [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) được cài đặt trên máy tính của bạn.</span><span class="sxs-lookup"><span data-stu-id="94632-108">The latest version of [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) is installed on your computer.</span></span> <span data-ttu-id="94632-109">[Tìm hiểu thêm về Power BI Desktop](/power-bi/desktop-what-is-desktop).</span><span class="sxs-lookup"><span data-stu-id="94632-109">[Learn more about Power BI Desktop](/power-bi/desktop-what-is-desktop).</span></span>

## <a name="configure-the-connector-for-power-bi"></a><span data-ttu-id="94632-110">Đặt cấu hình trình kết nối cho Power BI</span><span class="sxs-lookup"><span data-stu-id="94632-110">Configure the connector for Power BI</span></span>

1. <span data-ttu-id="94632-111">Trong Power BI Desktop, chọn **Tệp** > **Nhận dữ liệu**.</span><span class="sxs-lookup"><span data-stu-id="94632-111">In Power BI Desktop, select **File** > **Get Data**.</span></span>

1. <span data-ttu-id="94632-112">Chọn **Xem thêm** và tìm kiếm **Dynamics 365 Customer Insights**</span><span class="sxs-lookup"><span data-stu-id="94632-112">Select **See more** and search for **Dynamics 365 Customer Insights**</span></span>

1. <span data-ttu-id="94632-113">Chọn **Kết nối**.</span><span class="sxs-lookup"><span data-stu-id="94632-113">Select **Connect**.</span></span>

1. <span data-ttu-id="94632-114">**Đăng nhập** bằng cùng tài khoản tổ chức bạn dùng cho Customer Insights rồi chọn **Kết nối**.</span><span class="sxs-lookup"><span data-stu-id="94632-114">**Sign in** with the same organizational account you use for Customer Insights and select **Connect**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="94632-115">Tài khoản bạn chỉ ra trong bước này được sử dụng để tìm nạp dữ liệu từ Customer Insights và không cần giống với tài khoản bạn đã đăng nhập vào Power BI.</span><span class="sxs-lookup"><span data-stu-id="94632-115">The account you indicate in this step is used to fetch data from Customer Insights and doesn't need to be the same you are signed in to Power BI.</span></span> <span data-ttu-id="94632-116">Để đặt lại tài khoản được sử dụng để tìm nạp dữ liệu, hãy mở Power BI và đi đến **Tệp** > **Tùy chọn** > **Cài đặt** > **Cài đặt nguồn dữ liệu**.</span><span class="sxs-lookup"><span data-stu-id="94632-116">To reset the account that is used for data fetching, open Power BI and go to **File** > **Options** > **Settings** > **Data source settings**.</span></span> <span data-ttu-id="94632-117">Trong danh sách nguồn dữ liệu, hãy chọn **Đăng nhập Dynamics 365 Customer Insights** và chọn **Xóa quyền**.</span><span class="sxs-lookup"><span data-stu-id="94632-117">In the list of data sources, select **Dynamics 365 Customer Insights Login** and select **Clear permissions**.</span></span>  

1. <span data-ttu-id="94632-118">Trong hộp thoại **Trình điều hướng**.</span><span class="sxs-lookup"><span data-stu-id="94632-118">In the **Navigator** dialog box.</span></span> <span data-ttu-id="94632-119">bạn sẽ thấy danh sách tất cả các môi trường mà bạn có quyền truy cập.</span><span class="sxs-lookup"><span data-stu-id="94632-119">you see the list of all environments you have access to.</span></span> <span data-ttu-id="94632-120">Mở rộng môi trường và mở bất kỳ thư mục nào (thực thể, đo lường, phân đoạn, tăng cường).</span><span class="sxs-lookup"><span data-stu-id="94632-120">Expand an environment and open any of the folders (entities, measures, segments, enrichments).</span></span> <span data-ttu-id="94632-121">Ví dụ: mở thư mục **Thực thể** để xem tất cả các thực thể bạn có thể nhập.</span><span class="sxs-lookup"><span data-stu-id="94632-121">For example, open the **Entities** folder, to see all entities you can import.</span></span>

   <span data-ttu-id="94632-122">![Trình điều hướng trình kết nối Power BI](media/power-bi-navigator.png "Trình điều hướng trình kết nối Power BI")</span><span class="sxs-lookup"><span data-stu-id="94632-122">![Power BI Connector Navigator](media/power-bi-navigator.png "Power BI Connector Navigator")</span></span>

1. <span data-ttu-id="94632-123">Chọn hộp kiểm bên cạnh các thực thể để bao gồm và **Tải**.</span><span class="sxs-lookup"><span data-stu-id="94632-123">Select the check boxes next to the entities to include and **Load**.</span></span> <span data-ttu-id="94632-124">Bạn có thể chọn nhiều thực thể ngay từ nhiều môi trường.</span><span class="sxs-lookup"><span data-stu-id="94632-124">You can select multiple entities from multiple environments.</span></span>

1. <span data-ttu-id="94632-125">Bạn sẽ thấy hộp thoại tải trong khi các thực thể của bạn được tải.</span><span class="sxs-lookup"><span data-stu-id="94632-125">You'll see a loading dialog box while your entities are loaded.</span></span> <span data-ttu-id="94632-126">Khi tất cả các thực thể mà bạn chọn đã tải xong, bạn có thể sử dụng các khả năng của Power BI để trực quan hóa dữ liệu.</span><span class="sxs-lookup"><span data-stu-id="94632-126">Once all of your selected entities have loaded, you can use the capabilities of Power BI to visualize the data.</span></span>

## <a name="large-data-sets"></a><span data-ttu-id="94632-127">Tập hợp dữ liệu lớn</span><span class="sxs-lookup"><span data-stu-id="94632-127">Large data sets</span></span>

<span data-ttu-id="94632-128">Trình kết nối Customer Insights cho Power BI được thiết kế để hoạt động cho các tập hợp dữ liệu có chứa tới 1 triệu hồ sơ khách hàng.</span><span class="sxs-lookup"><span data-stu-id="94632-128">The Customer Insights connector for Power BI is designed to work for data sets that contain up to 1 million customer profiles.</span></span> <span data-ttu-id="94632-129">Việc nhập các tập hợp dữ liệu lớn hơn có thể hiệu quả, nhưng mất nhiều thời gian.</span><span class="sxs-lookup"><span data-stu-id="94632-129">Importing larger data sets may work, but it takes a long time.</span></span> <span data-ttu-id="94632-130">Ngoài ra, quá trình này có thể hết thời gian chờ vì những hạn chế của Power BI.</span><span class="sxs-lookup"><span data-stu-id="94632-130">Additionally, the process could run into a time-out because of Power BI limitations.</span></span> <span data-ttu-id="94632-131">Để biết thêm thông tin, hãy xem [Power BI: Đề xuất cho tập hợp dữ liệu lớn](/power-bi/admin/service-premium-what-is#large-datasets).</span><span class="sxs-lookup"><span data-stu-id="94632-131">For more information, see [Power BI: Recommendations for large data sets](/power-bi/admin/service-premium-what-is#large-datasets).</span></span> 

### <a name="work-with-a-subset-of-data"></a><span data-ttu-id="94632-132">Làm việc với một tập hợp con dữ liệu</span><span class="sxs-lookup"><span data-stu-id="94632-132">Work with a subset of data</span></span>

<span data-ttu-id="94632-133">Cân nhắc làm việc với một tập hợp con dữ liệu của bạn.</span><span class="sxs-lookup"><span data-stu-id="94632-133">Consider working with a subset of your data.</span></span> <span data-ttu-id="94632-134">Ví dụ: bạn có thể tạo [phân đoạn](segments.md) thay vì xuất tất cả hồ sơ khách hàng sang Power BI.</span><span class="sxs-lookup"><span data-stu-id="94632-134">For example, you can create [segments](segments.md) instead of exporting all customer records to Power BI.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="94632-135">Khắc phục sự cố</span><span class="sxs-lookup"><span data-stu-id="94632-135">Troubleshooting</span></span>

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a><span data-ttu-id="94632-136">Môi trường Customer Insights không hiển thị trong Power BI</span><span class="sxs-lookup"><span data-stu-id="94632-136">Customer Insights environment doesn't show in Power BI</span></span>

<span data-ttu-id="94632-137">Môi trường có nhiều hơn một [mối quan hệ](relationships.md) được xác định giữa hai thực thể giống nhau trong thông tin chi tiết về đối tượng sẽ không có sẵn trong trình kết nối Power BI.</span><span class="sxs-lookup"><span data-stu-id="94632-137">Environments that have more than one [relationship](relationships.md) defined between two identical entities in audience insights will not be available in the Power BI connector.</span></span>

<span data-ttu-id="94632-138">Bạn có thể xác định và loại bỏ các mối quan hệ trùng lặp.</span><span class="sxs-lookup"><span data-stu-id="94632-138">You can identify and remove the duplicated relationships.</span></span>

1. <span data-ttu-id="94632-139">Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Dữ liệu** > **Các mối quan hệ** trên môi trường bạn đang thiếu trong Power BI.</span><span class="sxs-lookup"><span data-stu-id="94632-139">In audience insights, go to **Data** > **Relationships** on the environment you're missing in Power BI.</span></span>
2. <span data-ttu-id="94632-140">Xác định các mối quan hệ trùng lặp:</span><span class="sxs-lookup"><span data-stu-id="94632-140">Identify duplicated relationships:</span></span>
   - <span data-ttu-id="94632-141">Kiểm tra xem có nhiều hơn một mối quan hệ được xác định giữa hai thực thể giống nhau hay không.</span><span class="sxs-lookup"><span data-stu-id="94632-141">Check if there is more than one relationship defined between the same two entities.</span></span>
   - <span data-ttu-id="94632-142">Kiểm tra xem có mối quan hệ nào được tạo ra giữa hai thực thể đều được bao gồm trong quá trình hợp nhất hay không.</span><span class="sxs-lookup"><span data-stu-id="94632-142">Check if there is a relationship created between two entities that are both included in the unification process.</span></span> <span data-ttu-id="94632-143">Có một mối quan hệ ngầm được xác định giữa tất cả các thực thể có trong quá trình hợp nhất.</span><span class="sxs-lookup"><span data-stu-id="94632-143">There is an implicit relationship defined between all entities included in the unification process.</span></span>
3. <span data-ttu-id="94632-144">Loại bỏ bất kỳ mối quan hệ trùng lặp nào được xác định.</span><span class="sxs-lookup"><span data-stu-id="94632-144">Remove any duplicate relationships identified.</span></span>

<span data-ttu-id="94632-145">Sau khi loại bỏ các mối quan hệ trùng lặp, hãy thử định cấu hình trình kết nối Power BI lần nữa.</span><span class="sxs-lookup"><span data-stu-id="94632-145">After removal of the duplicated relationships, try to configure the Power BI connector again.</span></span> <span data-ttu-id="94632-146">Môi trường sẽ có sẵn ngay.</span><span class="sxs-lookup"><span data-stu-id="94632-146">The environment should be available now.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]