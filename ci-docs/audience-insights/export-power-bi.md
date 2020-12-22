---
title: Trình kết nối Power BI
description: Tìm hiểu về cách dùng trình kết nối Dynamics 365 Customer Insights trong Power BI.
ms.date: 09/21/2020
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d497ca779a337c512a7254524f597cff226bcb45
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407294"
---
# <a name="connector-for-power-bi-preview"></a><span data-ttu-id="a5f3c-103">Trình kết nối cho Power BI (xem trước)</span><span class="sxs-lookup"><span data-stu-id="a5f3c-103">Connector for Power BI (preview)</span></span>

<span data-ttu-id="a5f3c-104">Tạo trực quan hóa cho dữ liệu của bạn với Power BI Desktop.</span><span class="sxs-lookup"><span data-stu-id="a5f3c-104">Create visualizations for your data with the Power BI Desktop.</span></span> <span data-ttu-id="a5f3c-105">Tạo thông tin chi tiết bổ sung và xây dựng báo cáo với dữ liệu khách hàng hợp nhất của bạn.</span><span class="sxs-lookup"><span data-stu-id="a5f3c-105">Generate additional insights and build reports with your unified customer data.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a5f3c-106">Điều kiện tiên quyết</span><span class="sxs-lookup"><span data-stu-id="a5f3c-106">Prerequisites</span></span>

- <span data-ttu-id="a5f3c-107">Bạn có hồ sơ khách hàng hợp nhất.</span><span class="sxs-lookup"><span data-stu-id="a5f3c-107">You have unified customer profiles.</span></span>
- <span data-ttu-id="a5f3c-108">Phiên bản mới nhất của [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) được cài đặt trên máy tính của bạn.</span><span class="sxs-lookup"><span data-stu-id="a5f3c-108">The latest version of [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) is installed on your computer.</span></span> <span data-ttu-id="a5f3c-109">[Tìm hiểu thêm về Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).</span><span class="sxs-lookup"><span data-stu-id="a5f3c-109">[Learn more about Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).</span></span>

## <a name="configure-the-connector-for-power-bi"></a><span data-ttu-id="a5f3c-110">Đặt cấu hình trình kết nối cho Power BI</span><span class="sxs-lookup"><span data-stu-id="a5f3c-110">Configure the connector for Power BI</span></span>

1. <span data-ttu-id="a5f3c-111">Trong Power BI Desktop, chọn **Tệp** > **Nhận dữ liệu**.</span><span class="sxs-lookup"><span data-stu-id="a5f3c-111">In Power BI Desktop, select **File** > **Get Data**.</span></span>

1. <span data-ttu-id="a5f3c-112">Chọn **Xem thêm** và tìm kiếm **Dynamics 365 Customer Insights**</span><span class="sxs-lookup"><span data-stu-id="a5f3c-112">Select **See more** and search for **Dynamics 365 Customer Insights**</span></span>

1. <span data-ttu-id="a5f3c-113">Chọn kết quả và chọn **Kết nối**.</span><span class="sxs-lookup"><span data-stu-id="a5f3c-113">Select the result and select **Connect**.</span></span>

1. <span data-ttu-id="a5f3c-114">**Đăng nhập** bằng cùng tài khoản tổ chức bạn dùng cho Customer Insights rồi chọn **Kết nối**.</span><span class="sxs-lookup"><span data-stu-id="a5f3c-114">**Sign in** with the same organizational account you use for Customer Insights and select **Connect**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="a5f3c-115">Tài khoản bạn chỉ ra trong bước này được sử dụng để tìm nạp dữ liệu từ Customer Insights và không cần giống với tài khoản bạn đã đăng nhập vào Power BI.</span><span class="sxs-lookup"><span data-stu-id="a5f3c-115">The account you indicate in this step is used to fetch data from Customer Insights and doesn't need to be the same you are signed in to Power BI.</span></span> <span data-ttu-id="a5f3c-116">Để đặt lại tài khoản được sử dụng để tìm nạp dữ liệu, hãy mở Power BI và đi đến **Tệp** > **Tùy chọn** > **Cài đặt** > **Cài đặt nguồn dữ liệu**.</span><span class="sxs-lookup"><span data-stu-id="a5f3c-116">To reset the account that is used for data fetching, open Power BI and go to **File** > **Options** > **Settings** > **Data source settings**.</span></span> <span data-ttu-id="a5f3c-117">Trong danh sách nguồn dữ liệu, hãy chọn **Đăng nhập Dynamics 365 Customer Insights** và chọn **Xóa quyền**.</span><span class="sxs-lookup"><span data-stu-id="a5f3c-117">In the list of data sources, select **Dynamics 365 Customer Insights Login** and select **Clear permissions**.</span></span>  

1. <span data-ttu-id="a5f3c-118">Trong hộp thoại **Trình điều hướng**.</span><span class="sxs-lookup"><span data-stu-id="a5f3c-118">In the **Navigator** dialog box.</span></span> <span data-ttu-id="a5f3c-119">bạn sẽ thấy danh sách tất cả các môi trường mà bạn có quyền truy cập.</span><span class="sxs-lookup"><span data-stu-id="a5f3c-119">you see the list of all environments you have access to.</span></span> <span data-ttu-id="a5f3c-120">Mở rộng môi trường và mở bất kỳ thư mục nào (thực thể, đo lường, phân đoạn, tăng cường).</span><span class="sxs-lookup"><span data-stu-id="a5f3c-120">Expand an environment and open any of the folders (entities, measures, segments, enrichments).</span></span> <span data-ttu-id="a5f3c-121">Ví dụ: mở thư mục **Thực thể** để xem tất cả các thực thể bạn có thể nhập.</span><span class="sxs-lookup"><span data-stu-id="a5f3c-121">For example, open the **Entities** folder, to see all entities you can import.</span></span>

   <span data-ttu-id="a5f3c-122">![Trình điều hướng trình kết nối Power BI](media/power-bi-navigator.png "Trình điều hướng trình kết nối Power BI")</span><span class="sxs-lookup"><span data-stu-id="a5f3c-122">![Power BI Connector Navigator](media/power-bi-navigator.png "Power BI Connector Navigator")</span></span>

1. <span data-ttu-id="a5f3c-123">Chọn hộp kiểm bên cạnh các thực thể để bao gồm và **Tải**.</span><span class="sxs-lookup"><span data-stu-id="a5f3c-123">Select the check boxes next to the entities to include and **Load**.</span></span> <span data-ttu-id="a5f3c-124">Bạn có thể chọn nhiều thực thể ngay từ nhiều môi trường.</span><span class="sxs-lookup"><span data-stu-id="a5f3c-124">You can select multiple entities from multiple environments.</span></span>

1. <span data-ttu-id="a5f3c-125">Bạn sẽ thấy hộp thoại tải trong khi các thực thể của bạn được tải.</span><span class="sxs-lookup"><span data-stu-id="a5f3c-125">You'll see a loading dialog box while your entities are loaded.</span></span> <span data-ttu-id="a5f3c-126">Khi tất cả các thực thể mà bạn chọn đã tải xong, bạn có thể sử dụng các khả năng của Power BI để trực quan hóa dữ liệu.</span><span class="sxs-lookup"><span data-stu-id="a5f3c-126">Once all of your selected entities have loaded, you can use the capabilities of Power BI to visualize the data.</span></span>

## <a name="large-data-sets"></a><span data-ttu-id="a5f3c-127">Tập hợp dữ liệu lớn</span><span class="sxs-lookup"><span data-stu-id="a5f3c-127">Large data sets</span></span>

<span data-ttu-id="a5f3c-128">Trình kết nối Customer Insights cho Power BI được thiết kế để hoạt động cho các tập hợp dữ liệu có chứa tới 1 triệu hồ sơ khách hàng.</span><span class="sxs-lookup"><span data-stu-id="a5f3c-128">The Customer Insights connector for Power BI is designed to work for data sets that contain up to 1 million customer profiles.</span></span> <span data-ttu-id="a5f3c-129">Việc nhập các tập hợp dữ liệu lớn hơn có thể hiệu quả, nhưng mất nhiều thời gian.</span><span class="sxs-lookup"><span data-stu-id="a5f3c-129">Importing larger data sets may work, but it takes a long time.</span></span> <span data-ttu-id="a5f3c-130">Ngoài ra, quá trình này có thể hết thời gian chờ vì những hạn chế của Power BI.</span><span class="sxs-lookup"><span data-stu-id="a5f3c-130">Additionally, the process could run into a time-out because of Power BI limitations.</span></span> <span data-ttu-id="a5f3c-131">Để biết thêm thông tin, hãy xem [Power BI: Đề xuất cho tập hợp dữ liệu lớn](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span><span class="sxs-lookup"><span data-stu-id="a5f3c-131">For more information, see [Power BI: Recommendations for large data sets](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span></span> 

### <a name="work-with-a-subset-of-data"></a><span data-ttu-id="a5f3c-132">Làm việc với một tập hợp con dữ liệu</span><span class="sxs-lookup"><span data-stu-id="a5f3c-132">Work with a subset of data</span></span>

<span data-ttu-id="a5f3c-133">Cân nhắc làm việc với một tập hợp con dữ liệu của bạn.</span><span class="sxs-lookup"><span data-stu-id="a5f3c-133">Consider working with a subset of your data.</span></span> <span data-ttu-id="a5f3c-134">Ví dụ: bạn có thể tạo [phân đoạn](segments.md) thay vì xuất tất cả hồ sơ khách hàng sang Power BI.</span><span class="sxs-lookup"><span data-stu-id="a5f3c-134">For example, you can create [segments](segments.md) instead of exporting all customer records to Power BI.</span></span>
