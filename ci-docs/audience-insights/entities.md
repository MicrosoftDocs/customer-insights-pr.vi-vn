---
title: Thực thể và tập hợp dữ liệu
description: Xem dữ liệu trên trang Thực thể.
ms.date: 04/16/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: f81128183b6e20e1078ad38c42c771d343909270
ms.sourcegitcommit: c1841ab91fbef9ead9db0f63fbc669cc3af80c12
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 05/17/2021
ms.locfileid: "6049420"
---
# <a name="entities-in-audience-insights"></a><span data-ttu-id="9f75e-103">Các thực thể trong thông tin chi tiết về đối tượng</span><span class="sxs-lookup"><span data-stu-id="9f75e-103">Entities in audience insights</span></span>

<span data-ttu-id="9f75e-104">Sau khi [định cấu hình nguồn dữ liệu](data-sources.md), hãy truy cập trang **Thực thể** để đánh giá chất lượng của dữ liệu được nhập.</span><span class="sxs-lookup"><span data-stu-id="9f75e-104">After [configuring your data sources](data-sources.md), go to the **Entities** page to evaluate the quality of the ingested data.</span></span> <span data-ttu-id="9f75e-105">Các thực thể được coi là tập hợp dữ liệu.</span><span class="sxs-lookup"><span data-stu-id="9f75e-105">Entities are considered datasets.</span></span> <span data-ttu-id="9f75e-106">Nhiều chức năng của Dynamics 365 Customer Insights được xây dựng liên quan đến những thực thể này.</span><span class="sxs-lookup"><span data-stu-id="9f75e-106">Multiple capabilities of Dynamics 365 Customer Insights are built around these entities.</span></span> <span data-ttu-id="9f75e-107">Việc xem xét chúng một cách chi tiết có thể giúp bạn xác thực đầu ra của những khả năng.</span><span class="sxs-lookup"><span data-stu-id="9f75e-107">Reviewing them closely can help you validate the output of those capabilities.</span></span>

<span data-ttu-id="9f75e-108">Trang **Thực thể** liệt kê các thực thể và bao gồm một số cột:</span><span class="sxs-lookup"><span data-stu-id="9f75e-108">The **Entities** page lists entities and includes several columns:</span></span>

- <span data-ttu-id="9f75e-109">**Tên**: Tên của thực thể dữ liệu của bạn.</span><span class="sxs-lookup"><span data-stu-id="9f75e-109">**Name**: The name of your data entity.</span></span> <span data-ttu-id="9f75e-110">Nếu bạn thấy biểu tượng cảnh báo bên cạnh tên thực thể, điều đó có nghĩa là dữ liệu cho thực thể đó không tải thành công.</span><span class="sxs-lookup"><span data-stu-id="9f75e-110">If you see a warning symbol next to an entity name, it means that the data for that entity didn't load successfully.</span></span>
- <span data-ttu-id="9f75e-111">**Nguồn**: Hiển thị loại nguồn dữ liệu được nhập vào thực thể</span><span class="sxs-lookup"><span data-stu-id="9f75e-111">**Source**: The type of data source that ingested the entity</span></span>
- <span data-ttu-id="9f75e-112">**Người tạo**: Tên của người đã tạo thực thể</span><span class="sxs-lookup"><span data-stu-id="9f75e-112">**Created by**: Name of the person who created the entity</span></span>
- <span data-ttu-id="9f75e-113">**Ngày tạo**: Ngày và giờ tạo thực thể</span><span class="sxs-lookup"><span data-stu-id="9f75e-113">**Created**: Date and time of the entity creation</span></span>
- <span data-ttu-id="9f75e-114">**Người cập nhật**: Tên của người cập nhật thực thể</span><span class="sxs-lookup"><span data-stu-id="9f75e-114">**Updated by**: Name of the person who updated the entity</span></span>
- <span data-ttu-id="9f75e-115">**Cập nhật lần cuối**: Ngày và giờ của bản cập nhật cuối cùng của thực thể</span><span class="sxs-lookup"><span data-stu-id="9f75e-115">**Last updated**: Date and time of the last update of the entity</span></span>
- <span data-ttu-id="9f75e-116">**Làm mới lần cuối**: Ngày và giờ làm mới dữ liệu cuối cùng</span><span class="sxs-lookup"><span data-stu-id="9f75e-116">**Last refresh**: Date and time of the last data refresh</span></span>

## <a name="exploring-a-specific-entitys-data"></a><span data-ttu-id="9f75e-117">Khám phá dữ liệu của một thực thể cụ thể</span><span class="sxs-lookup"><span data-stu-id="9f75e-117">Exploring a specific entity's data</span></span>

<span data-ttu-id="9f75e-118">Chọn một thực thể để khám phá các trường và bản ghi khác nhau được bao gồm trong thực thể đó.</span><span class="sxs-lookup"><span data-stu-id="9f75e-118">Select an entity to explore the different fields and records included within that entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="9f75e-119">![Chọn thực thể](media/data-manager-entities-data.png "Chọn một thực thể")</span><span class="sxs-lookup"><span data-stu-id="9f75e-119">![Select an entity](media/data-manager-entities-data.png "Select an entity")</span></span>

- <span data-ttu-id="9f75e-120">Tab **Dữ liệu** hiển thị một bảng liệt kê chi tiết về các bản ghi riêng lẻ của thực thể.</span><span class="sxs-lookup"><span data-stu-id="9f75e-120">The **Data** tab shows a table listing details about individual records of the entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="9f75e-121">![Bảng trường](media/data-manager-entities-fields.PNG "Bảng trường")</span><span class="sxs-lookup"><span data-stu-id="9f75e-121">![Fields table](media/data-manager-entities-fields.PNG "Fields table")</span></span>

- <span data-ttu-id="9f75e-122">Tab **Thuộc tính** được chọn theo mặc định và hiển thị một bảng để bạn xem xét thông tin chi tiết của thực thể đã chọn, chẳng hạn như tên trường, kiểu dữ liệu và loại thực thể.</span><span class="sxs-lookup"><span data-stu-id="9f75e-122">The **Attributes** tab is selected by default and shows a table to review details for the selected entity, such as field names, data types, and types.</span></span> <span data-ttu-id="9f75e-123">Cột **Loại** hiển thị các loại liên kết Common Data Model được tự động xác định bởi hệ thống hoặc [được ánh xạ thủ công](map-entities.md) bởi người dùng.</span><span class="sxs-lookup"><span data-stu-id="9f75e-123">The **Type** column shows Common Data Model associated types, which are either auto-identified by the system or [manually mapped](map-entities.md) by users.</span></span> <span data-ttu-id="9f75e-124">Đây là các loại ngữ nghĩa có thể khác với các loại dữ liệu của thuộc tính — ví dụ: trường *Email* dưới đây có loại dữ liệu *Văn bản* nhưng kiểu Common Data Model có thể là *Email* hoặc *Địa chỉ email*.</span><span class="sxs-lookup"><span data-stu-id="9f75e-124">These are semantic types that can differ from the attributes' data types—for example, the field *Email* below has a data type *Text* but its (semantic) Common Data Model type might be *Email* or *EmailAddress*.</span></span>

> [!NOTE]
> <span data-ttu-id="9f75e-125">Cả hai bảng chỉ hiển thị một mẫu dữ liệu của thực thể của bạn.</span><span class="sxs-lookup"><span data-stu-id="9f75e-125">Both tables show only a sample of your entity's data.</span></span> <span data-ttu-id="9f75e-126">Để xem tập dữ liệu đầy đủ, hãy đi tới trang **Nguồn dữ liệu**, chọn một thực thể, chọn **Chỉnh sửa**, sau đó xem dữ liệu của thực thể này bằng trình chỉnh sửa Power Query như giải thích trong [Nguồn dữ liệu](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="9f75e-126">To view the full data set, go to the **Data sources** page, select an entity, select **Edit**, and then view this entity's data with the Power Query editor as explained in [Data sources](data-sources.md).</span></span>

<span data-ttu-id="9f75e-127">Để tìm hiểu thêm về dữ liệu được nhập vào thực thể, cột **Tóm tắt** cung cấp cho bạn một số đặc điểm quan trọng của dữ liệu, chẳng hạn như giá trị rỗng, các giá trị còn thiếu, giá trị duy nhất, số lượng và phân phối, như áp dụng cho dữ liệu của bạn.</span><span class="sxs-lookup"><span data-stu-id="9f75e-127">To learn more about the data ingested in the entity, the **Summary** column provides you with some important characteristics of the data, such as nulls, missing values, unique values, counts, and distributions, as applicable to your data.</span></span>

<span data-ttu-id="9f75e-128">Chọn biểu tượng biểu đồ để xem tóm tắt dữ liệu.</span><span class="sxs-lookup"><span data-stu-id="9f75e-128">Select the chart icon to see the summary of the data.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="9f75e-129">![Biểu tượng tóm tắt](media/data-manager-entities-summary.png "Bảng tóm tắt dữ liệu")</span><span class="sxs-lookup"><span data-stu-id="9f75e-129">![Summary symbol](media/data-manager-entities-summary.png "Data summary table")</span></span>

### <a name="next-step"></a><span data-ttu-id="9f75e-130">Bước tiếp theo</span><span class="sxs-lookup"><span data-stu-id="9f75e-130">Next step</span></span>

<span data-ttu-id="9f75e-131">Xem chủ đề [Hợp nhất](data-unification.md) để tìm hiểu cách *ánh xạ*, *so khớp* và *hợp nhất* dữ liệu đã nhập.</span><span class="sxs-lookup"><span data-stu-id="9f75e-131">See the [Unify](data-unification.md) topic to learn how to *map*, *match*, and *merge* the ingested data.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
