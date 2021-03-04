---
title: Thực thể và tập hợp dữ liệu
description: Xem dữ liệu trên trang Thực thể.
ms.date: 04/16/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: e71c69a6207147d8cd65363d51a5fa6bbf896151
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269402"
---
# <a name="entities-in-audience-insights"></a><span data-ttu-id="0a0c2-103">Các thực thể trong thông tin chi tiết về đối tượng</span><span class="sxs-lookup"><span data-stu-id="0a0c2-103">Entities in audience insights</span></span>

<span data-ttu-id="0a0c2-104">Sau khi [định cấu hình nguồn dữ liệu](data-sources.md), hãy truy cập trang **Thực thể** để đánh giá chất lượng của dữ liệu được nhập.</span><span class="sxs-lookup"><span data-stu-id="0a0c2-104">After [configuring your data sources](data-sources.md), go to the **Entities** page to evaluate the quality of the ingested data.</span></span> <span data-ttu-id="0a0c2-105">Các thực thể được coi là tập hợp dữ liệu.</span><span class="sxs-lookup"><span data-stu-id="0a0c2-105">Entities are considered datasets.</span></span> <span data-ttu-id="0a0c2-106">Nhiều chức năng của Dynamics 365 Customer Insights được xây dựng liên quan đến những thực thể này.</span><span class="sxs-lookup"><span data-stu-id="0a0c2-106">Multiple capabilities of Dynamics 365 Customer Insights are built around these entities.</span></span> <span data-ttu-id="0a0c2-107">Việc xem xét chúng một cách chi tiết có thể giúp bạn xác thực đầu ra của những khả năng.</span><span class="sxs-lookup"><span data-stu-id="0a0c2-107">Reviewing them closely can help you validate the output of those capabilities.</span></span>

<span data-ttu-id="0a0c2-108">Trang **Thực thể** liệt kê các thực thể và bao gồm một số cột:</span><span class="sxs-lookup"><span data-stu-id="0a0c2-108">The **Entities** page lists entities and includes several columns:</span></span>

- <span data-ttu-id="0a0c2-109">**Tên**: Tên của thực thể dữ liệu của bạn.</span><span class="sxs-lookup"><span data-stu-id="0a0c2-109">**Name**: The name of your data entity.</span></span> <span data-ttu-id="0a0c2-110">Nếu bạn thấy biểu tượng cảnh báo bên cạnh tên thực thể, điều đó có nghĩa là dữ liệu cho thực thể đó không tải thành công.</span><span class="sxs-lookup"><span data-stu-id="0a0c2-110">If you see a warning symbol next to an entity name, it means that the data for that entity didn't load successfully.</span></span>
- <span data-ttu-id="0a0c2-111">**Nguồn**: Hiển thị loại nguồn dữ liệu được nhập vào thực thể</span><span class="sxs-lookup"><span data-stu-id="0a0c2-111">**Source**: The type of data source that ingested the entity</span></span>
- <span data-ttu-id="0a0c2-112">**Người tạo**: Tên của người đã tạo thực thể</span><span class="sxs-lookup"><span data-stu-id="0a0c2-112">**Created by**: Name of the person who created the entity</span></span>
- <span data-ttu-id="0a0c2-113">**Ngày tạo**: Ngày và giờ tạo thực thể</span><span class="sxs-lookup"><span data-stu-id="0a0c2-113">**Created**: Date and time of the entity creation</span></span>
- <span data-ttu-id="0a0c2-114">**Người cập nhật**: Tên của người cập nhật thực thể</span><span class="sxs-lookup"><span data-stu-id="0a0c2-114">**Updated by**: Name of the person who updated the entity</span></span>
- <span data-ttu-id="0a0c2-115">**Cập nhật lần cuối**: Ngày và giờ của bản cập nhật cuối cùng của thực thể</span><span class="sxs-lookup"><span data-stu-id="0a0c2-115">**Last updated**: Date and time of the last update of the entity</span></span>
- <span data-ttu-id="0a0c2-116">**Làm mới lần cuối**: Ngày và giờ làm mới dữ liệu cuối cùng</span><span class="sxs-lookup"><span data-stu-id="0a0c2-116">**Last refresh**: Date and time of the last data refresh</span></span>

## <a name="exploring-a-specific-entitys-data"></a><span data-ttu-id="0a0c2-117">Khám phá dữ liệu của một thực thể cụ thể</span><span class="sxs-lookup"><span data-stu-id="0a0c2-117">Exploring a specific entity's data</span></span>

<span data-ttu-id="0a0c2-118">Chọn một thực thể để khám phá các trường và bản ghi khác nhau được bao gồm trong thực thể đó.</span><span class="sxs-lookup"><span data-stu-id="0a0c2-118">Select an entity to explore the different fields and records included within that entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0a0c2-119">![Chọn một thực thể](media/data-manager-entities-data.png "Chọn một thực thể")</span><span class="sxs-lookup"><span data-stu-id="0a0c2-119">![Select an entity](media/data-manager-entities-data.png "Select an entity")</span></span>

- <span data-ttu-id="0a0c2-120">Tab **Dữ liệu** được chọn theo mặc định và hiển thị chi tiết danh sách bảng về các bản ghi cá nhân của thực thể.</span><span class="sxs-lookup"><span data-stu-id="0a0c2-120">The **Data** tab is selected by default and shows a table listing details about individual records of the entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0a0c2-121">![Bảng trường](media/data-manager-entities-fields.PNG "Bảng trường")</span><span class="sxs-lookup"><span data-stu-id="0a0c2-121">![Fields table](media/data-manager-entities-fields.PNG "Fields table")</span></span>

- <span data-ttu-id="0a0c2-122">Tab **Trường** hiển thị bảng để đánh giá chi tiết cho thực thể đã chọn, chẳng hạn như tên trường, loại dữ liệu và loại.</span><span class="sxs-lookup"><span data-stu-id="0a0c2-122">The **Fields** tab shows a table to review details for the selected entity, such as field names, data types, and types.</span></span> <span data-ttu-id="0a0c2-123">Cột **Loại** hiển thị các loại liên kết Common Data Model được tự động xác định bởi hệ thống hoặc [được ánh xạ thủ công](map-entities.md) bởi người dùng.</span><span class="sxs-lookup"><span data-stu-id="0a0c2-123">The **Type** column shows Common Data Model associated types, which are either auto-identified by the system or [manually mapped](map-entities.md) by users.</span></span> <span data-ttu-id="0a0c2-124">Đây là các loại ngữ nghĩa có thể khác với các loại dữ liệu của thuộc tính — ví dụ: trường *Email* dưới đây có loại dữ liệu *Văn bản* nhưng kiểu Common Data Model có thể là *Email* hoặc *Địa chỉ email*.</span><span class="sxs-lookup"><span data-stu-id="0a0c2-124">These are semantic types that can differ from the attributes' data types—for example, the field *Email* below has a data type *Text* but its (semantic) Common Data Model type might be *Email* or *EmailAddress*.</span></span>

> [!NOTE]
> <span data-ttu-id="0a0c2-125">Cả hai bảng chỉ hiển thị một mẫu dữ liệu của thực thể của bạn.</span><span class="sxs-lookup"><span data-stu-id="0a0c2-125">Both tables show only a sample of your entity's data.</span></span> <span data-ttu-id="0a0c2-126">Để xem tập dữ liệu đầy đủ, hãy đi tới trang **Nguồn dữ liệu**, chọn một thực thể, chọn **Chỉnh sửa**, sau đó xem dữ liệu của thực thể này bằng trình chỉnh sửa Power Query như giải thích trong [Nguồn dữ liệu](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="0a0c2-126">To view the full data set, go to the **Data sources** page, select an entity, select **Edit**, and then view this entity's data with the Power Query editor as explained in [Data sources](data-sources.md).</span></span>

<span data-ttu-id="0a0c2-127">Để tìm hiểu thêm về dữ liệu được nhập vào thực thể, cột **Tóm tắt** cung cấp cho bạn một số đặc điểm quan trọng của dữ liệu, chẳng hạn như giá trị rỗng, các giá trị còn thiếu, giá trị duy nhất, số lượng và phân phối, như áp dụng cho dữ liệu của bạn.</span><span class="sxs-lookup"><span data-stu-id="0a0c2-127">To learn more about the data ingested in the entity, the **Summary** column provides you with some important characteristics of the data, such as nulls, missing values, unique values, counts, and distributions, as applicable to your data.</span></span>

<span data-ttu-id="0a0c2-128">Chọn biểu tượng biểu đồ để xem tóm tắt dữ liệu.</span><span class="sxs-lookup"><span data-stu-id="0a0c2-128">Select the chart icon to see the summary of the data.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0a0c2-129">![Biểu tượng tóm tắt](media/data-manager-entities-summary.png "Bảng tóm tắt dữ liệu")</span><span class="sxs-lookup"><span data-stu-id="0a0c2-129">![Summary symbol](media/data-manager-entities-summary.png "Data summary table")</span></span>

### <a name="next-step"></a><span data-ttu-id="0a0c2-130">Bước tiếp theo</span><span class="sxs-lookup"><span data-stu-id="0a0c2-130">Next step</span></span>

<span data-ttu-id="0a0c2-131">Xem chủ đề [Hợp nhất](data-unification.md) để tìm hiểu cách *ánh xạ*, *so khớp* và *hợp nhất* dữ liệu đã nhập.</span><span class="sxs-lookup"><span data-stu-id="0a0c2-131">See the [Unify](data-unification.md) topic to learn how to *map*, *match*, and *merge* the ingested data.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]