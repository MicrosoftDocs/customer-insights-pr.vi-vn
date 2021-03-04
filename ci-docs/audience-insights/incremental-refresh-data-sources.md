---
title: Làm mới gia tăng cho các nguồn dữ liệu dựa trên Power Query
description: Làm mới dữ liệu mới và cập nhật cho các nguồn dữ liệu lớn dựa trên Power Query.
ms.date: 09/28/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d4b01be75d25fa0e120904924a193171eefec579
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268574"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a><span data-ttu-id="dcf1f-103">Làm mới gia tăng cho các nguồn dữ liệu dựa trên Power Query</span><span class="sxs-lookup"><span data-stu-id="dcf1f-103">Incremental refresh for data sources based on Power Query</span></span>

<span data-ttu-id="dcf1f-104">Làm mới gia tăng cho các nguồn dữ liệu cung cấp các lợi ích sau:</span><span class="sxs-lookup"><span data-stu-id="dcf1f-104">Incremental refresh for data sources provides the following advantages:</span></span>

- <span data-ttu-id="dcf1f-105">**Làm mới nhanh hơn** - Chỉ dữ liệu đã thay đổi được làm mới.</span><span class="sxs-lookup"><span data-stu-id="dcf1f-105">**Faster refreshes** - Only data that has changed gets refreshed.</span></span> <span data-ttu-id="dcf1f-106">Ví dụ: bạn có thể chỉ làm mới năm ngày qua của bộ dữ liệu lịch sử.</span><span class="sxs-lookup"><span data-stu-id="dcf1f-106">For example, you might refresh only the past five days of a historical dataset.</span></span>
- <span data-ttu-id="dcf1f-107">**Tăng độ tin cậy** - Với các lần làm mới nhỏ hơn, bạn không cần duy trì kết nối với các hệ thống nguồn hay thay đổi trong thời gian dài, giảm nguy cơ xảy ra sự cố kết nối.</span><span class="sxs-lookup"><span data-stu-id="dcf1f-107">**Increased reliability** - With smaller refreshes, you don't need to maintain connections to volatile source systems for as long, reducing the risk of connection issues.</span></span>
- <span data-ttu-id="dcf1f-108">**Giảm tiêu thụ nguồn lực** - Chỉ làm mới một tập hợp con trong tổng số dữ liệu của bạn dẫn đến việc sử dụng nguồn lực máy tính hiệu quả hơn và giảm dấu chân môi trường.</span><span class="sxs-lookup"><span data-stu-id="dcf1f-108">**Reduced resource consumption** - Refreshing only a subset of your total data leads to more efficient use of computing resources and decreases the environmental footprint.</span></span>

## <a name="configure-incremental-refresh"></a><span data-ttu-id="dcf1f-109">Đặt cấu hình làm mới gia tăng</span><span class="sxs-lookup"><span data-stu-id="dcf1f-109">Configure incremental refresh</span></span>

<span data-ttu-id="dcf1f-110">Thông tin chi tiết về đối tượng cho phép làm mới gia tăng các nguồn dữ liệu được nhập thông qua Power Query hỗ trợ nhập tăng dần.</span><span class="sxs-lookup"><span data-stu-id="dcf1f-110">Audience insights allows incremental refresh for data sources imported through Power Query that support incremental ingestion.</span></span> <span data-ttu-id="dcf1f-111">Ví dụ: cơ sở dữ liệu Azure SQL với các trường ngày và thời gian, cho biết thời điểm các bản ghi dữ liệu được cập nhật lần cuối.</span><span class="sxs-lookup"><span data-stu-id="dcf1f-111">For example, Azure SQL databases with date and time fields, which indicate when data records were last updated.</span></span>

1. <span data-ttu-id="dcf1f-112">[Tạo nguồn dữ liệu mới dựa trên Power Query](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="dcf1f-112">[Create a new data source based on Power Query](connect-power-query.md).</span></span>

1. <span data-ttu-id="dcf1f-113">Cung cấp tên cho nguồn dữ liệu.</span><span class="sxs-lookup"><span data-stu-id="dcf1f-113">Provide a name for the data source.</span></span>

1. <span data-ttu-id="dcf1f-114">Chọn nguồn dữ liệu hỗ trợ làm mới tăng dần, chẳng hạn như cơ sở dữ liệu Azure SQL.</span><span class="sxs-lookup"><span data-stu-id="dcf1f-114">Select a data source that supports incremental refresh, such as Azure SQL database.</span></span>

1. <span data-ttu-id="dcf1f-115">Chọn các thực thể hoặc bảng để nhập.</span><span class="sxs-lookup"><span data-stu-id="dcf1f-115">Select the entities or tables to ingest.</span></span>

1. <span data-ttu-id="dcf1f-116">Hoàn thành các bước chuyển đổi và chọn **Tiếp theo**.</span><span class="sxs-lookup"><span data-stu-id="dcf1f-116">Complete the transformation steps and select **Next**.</span></span>

1. <span data-ttu-id="dcf1f-117">Trong hộp thoại **Thiết lập làm mới tăng dần**, chọn **Thiết lập** để mở **Thiết đặt làm mới tăng dần**.</span><span class="sxs-lookup"><span data-stu-id="dcf1f-117">In the **Set up incremental refresh** dialog box, select **Set up** to open the **Incremental refresh settings**.</span></span> <span data-ttu-id="dcf1f-118">Nếu bạn chọn **Bỏ qua**, nguồn dữ liệu sẽ làm mới toàn bộ tập dữ liệu.</span><span class="sxs-lookup"><span data-stu-id="dcf1f-118">If you select **Skip**, the data source will refresh the entire data set.</span></span>
   > [!TIP]
   > <span data-ttu-id="dcf1f-119">Bạn cũng có thể áp dụng làm mới gia tăng sau bằng cách chỉnh sửa nguồn dữ liệu hiện có.</span><span class="sxs-lookup"><span data-stu-id="dcf1f-119">You can also apply incremental refresh later by editing an existing data source.</span></span>

1. <span data-ttu-id="dcf1f-120">Trên **Thiết đặt làm mới tăng dần**, bạn sẽ định cấu hình làm mới tăng dần cho tất cả các thực thể mà bạn đã chọn khi tạo nguồn dữ liệu.</span><span class="sxs-lookup"><span data-stu-id="dcf1f-120">On **Incremental refresh settings**, you'll configure the incremental refresh for all entities that you selected when creating the data source.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="dcf1f-121">![Định cấu hình các thực thể trong nguồn dữ liệu để làm mới tăng dần](media/incremental-refresh-settings.png "Định cấu hình các thực thể trong nguồn dữ liệu để làm mới tăng dần")</span><span class="sxs-lookup"><span data-stu-id="dcf1f-121">![Configure entities in a data source for incremental refresh](media/incremental-refresh-settings.png "Configure entities in a data source for incremental refresh")</span></span>

1. <span data-ttu-id="dcf1f-122">Chọn một thực thể và cung cấp các chi tiết sau:</span><span class="sxs-lookup"><span data-stu-id="dcf1f-122">Select an entity, and provide the following details:</span></span>

   - <span data-ttu-id="dcf1f-123">**Xác định khóa chính**: Chọn khóa chính cho thực thể hoặc bảng.</span><span class="sxs-lookup"><span data-stu-id="dcf1f-123">**Define the primary key**: Select a primary key for the entity or table.</span></span>
   - <span data-ttu-id="dcf1f-124">**Xác định trường "cập nhật lần cuối"**: Trường này sẽ chỉ hiển thị các thuộc tính của loại ngày hoặc thời gian.</span><span class="sxs-lookup"><span data-stu-id="dcf1f-124">**Define the "last updated" field**: This field will only display attributes of type date or time.</span></span> <span data-ttu-id="dcf1f-125">Chọn một thuộc tính cho biết thời điểm các bản ghi được cập nhật lần cuối.</span><span class="sxs-lookup"><span data-stu-id="dcf1f-125">Select an attribute that indicates when the records were last updated.</span></span> <span data-ttu-id="dcf1f-126">Nó sẽ được sử dụng để xác định các bản ghi nằm trong khung thời gian làm mới gia tăng.</span><span class="sxs-lookup"><span data-stu-id="dcf1f-126">It will be used to identify the records that fall within the incremental refresh time frame.</span></span>
   - <span data-ttu-id="dcf1f-127">**Kiểm tra cập nhật mỗi**: Chỉ định khoảng thời gian bạn muốn cho khung thời gian làm mới tăng dần.</span><span class="sxs-lookup"><span data-stu-id="dcf1f-127">**Check for updates every**: Specify how long you want the incremental refresh time frame to be.</span></span>

1. <span data-ttu-id="dcf1f-128">Chọn **Lưu** để hoàn thành việc tạo nguồn dữ liệu.</span><span class="sxs-lookup"><span data-stu-id="dcf1f-128">Select **Save** to complete the creation of the data source.</span></span> <span data-ttu-id="dcf1f-129">Làm mới dữ liệu ban đầu sẽ là một làm mới đầy đủ.</span><span class="sxs-lookup"><span data-stu-id="dcf1f-129">The initial data refresh will be a full refresh.</span></span> <span data-ttu-id="dcf1f-130">Sau đó, làm mới dữ liệu gia tăng xảy ra như được cấu hình ở bước trước.</span><span class="sxs-lookup"><span data-stu-id="dcf1f-130">Afterwards, the incremental data refresh happens as configured in the previous step.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]