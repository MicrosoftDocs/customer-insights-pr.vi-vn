---
title: Mối quan hệ giữa các thực thể và đường dẫn thực thể
description: Tạo và quản lý mối quan hệ giữa các thực thể từ nhiều nguồn dữ liệu.
ms.date: 04/14/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 295c372bb452e7c40aa950506dc494d4a2de1108
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407335"
---
# <a name="relationships-between-entities"></a><span data-ttu-id="b22a9-103">Các mối quan hệ giữa các thực thể</span><span class="sxs-lookup"><span data-stu-id="b22a9-103">Relationships between entities</span></span>

<span data-ttu-id="b22a9-104">Mối quan hệ giúp bạn kết nối các thực thể và tạo một biểu đồ dữ liệu khi các thực thể có chung mã định danh (khóa ngoại) có thể được tham chiếu từ thực thể này sang thực thể khác.</span><span class="sxs-lookup"><span data-stu-id="b22a9-104">Relationships help you connect entities and generate a graph of your data when entities share a common identifier (foreign key) that can be referenced from one entity to another.</span></span> <span data-ttu-id="b22a9-105">Các thực thể được kết nối cho phép bạn xác định các phân đoạn và giá trị đo dựa trên nhiều nguồn dữ liệu.</span><span class="sxs-lookup"><span data-stu-id="b22a9-105">Connected entities enable you to define segments and measures based on multiple data sources.</span></span>

<span data-ttu-id="b22a9-106">Có hai loại mối quan hệ.</span><span class="sxs-lookup"><span data-stu-id="b22a9-106">There are two types of relationships.</span></span> <span data-ttu-id="b22a9-107">Mối quan hệ hệ thống không thể chỉnh sửa, được tạo tự động và mối quan hệ tùy chỉnh được tạo và định cấu hình bởi người dùng.</span><span class="sxs-lookup"><span data-stu-id="b22a9-107">Non-editable system relationships, which are created automatically, and custom relationships created and configured by users.</span></span>

<span data-ttu-id="b22a9-108">Trong quá trình khớp và hợp nhất, các mối quan hệ hệ thống được tạo ở phía sau dựa trên tính năng khớp thông minh.</span><span class="sxs-lookup"><span data-stu-id="b22a9-108">During the match and merge processes, system relationships are created behind the scenes based on intelligent matching.</span></span> <span data-ttu-id="b22a9-109">Các mối quan hệ này giúp liên kết bản ghi Hồ sơ khách hàng với bản ghi của các thực thể tương ứng khác.</span><span class="sxs-lookup"><span data-stu-id="b22a9-109">These relationships help relate the Customer Profile records with other corresponding entities' records.</span></span> <span data-ttu-id="b22a9-110">Sơ đồ sau minh họa việc tạo ba mối quan hệ hệ thống khi thực thể khách hàng được khớp với các thực thể bổ sung để tạo ra thực thể Hồ sơ khách hàng cuối cùng.</span><span class="sxs-lookup"><span data-stu-id="b22a9-110">The following diagram illustrates the creation of three system relationships when the customer entity is matched with additional entities to produce the final Customer Profile entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b22a9-111">![Tạo mối quan hệ](media/relationships-entities-merge.png "Tạo mối quan hệ")</span><span class="sxs-lookup"><span data-stu-id="b22a9-111">![Relationship creation](media/relationships-entities-merge.png "Relationship creation")</span></span>

- <span data-ttu-id="b22a9-112">**Mối quan hệ *CustomerToContact*** được tạo giữa thực thể khách hàng và thực thể Người liên hệ.</span><span class="sxs-lookup"><span data-stu-id="b22a9-112">***CustomerToContact* relationship** was created between the Customer entity and the Contact entity.</span></span> <span data-ttu-id="b22a9-113">Thực thể Khách hàng có được trường khóa **Contact_contactId** để liên kết với trường khóa của thực thể Liên hệ **contactId**.</span><span class="sxs-lookup"><span data-stu-id="b22a9-113">The Customer entity gets the key field **Contact_contactId** to relate to the Contact entity key field **contactId**.</span></span>
- <span data-ttu-id="b22a9-114">**Mối quan hệ _CustomerToAccount_** được tạo giữa thực thể Khách hàng và thực thể Tài khoản.</span><span class="sxs-lookup"><span data-stu-id="b22a9-114">**_CustomerToAccount_ relationship** was created between the Customer entity and the Account entity.</span></span> <span data-ttu-id="b22a9-115">Thực thể Khách hàng có được trường khóa **Account_accountId** để liên kết với trường khóa của thực thể Tài khoản **accountId**.</span><span class="sxs-lookup"><span data-stu-id="b22a9-115">The Customer entity gets the key field **Account_accountId** to relate to the Account entity key field **accountId**.</span></span>
- <span data-ttu-id="b22a9-116">**Mối quan hệ _CustomerToWebAccount_** được tạo giữa thực thể Khách hàng và thực thể WebAccount.</span><span class="sxs-lookup"><span data-stu-id="b22a9-116">**_CustomerToWebAccount_ relationship** was created between the Customer entity and the WebAccount entity.</span></span> <span data-ttu-id="b22a9-117">Thực thể Khách hàng có được trường khóa **WebAccount_webaccountId** để liên kết với trường khóa của thực thể WebAccount **webaccountId**.</span><span class="sxs-lookup"><span data-stu-id="b22a9-117">The Customer entity gets the key field **WebAccount_webaccountId** to relate to the WebAccount entity key field **webaccountId**.</span></span>

## <a name="create-a-relationship"></a><span data-ttu-id="b22a9-118">Tạo một mối quan hệ</span><span class="sxs-lookup"><span data-stu-id="b22a9-118">Create a relationship</span></span>

<span data-ttu-id="b22a9-119">Xác định các mối quan hệ tùy chỉnh trên trang **Mối quan hệ**.</span><span class="sxs-lookup"><span data-stu-id="b22a9-119">Define custom relationships on the **Relationships** page.</span></span> <span data-ttu-id="b22a9-120">Mỗi mối quan hệ bao gồm một thực thể Nguồn (thực thể giữ khóa ngoại) và thực thể Đích (thực thể mà khóa ngoại của thực thể nguồn trỏ đến).</span><span class="sxs-lookup"><span data-stu-id="b22a9-120">Each relationship consists of a Source entity (the entity that holds the foreign key) and a Target entity (the entity that the source entity's foreign key points to).</span></span>

1. <span data-ttu-id="b22a9-121">Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Dữ liệu** > **Mối quan hệ**.</span><span class="sxs-lookup"><span data-stu-id="b22a9-121">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="b22a9-122">Chọn **Mối quan hệ mới**.</span><span class="sxs-lookup"><span data-stu-id="b22a9-122">Select **New relationship**.</span></span>

3. <span data-ttu-id="b22a9-123">Trong ngăn **Thêm mối quan hệ**, hãy cung cấp các thông tin sau:</span><span class="sxs-lookup"><span data-stu-id="b22a9-123">In the **Add relationship** pane, provide the following information:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b22a9-124">![Nhập chi tiết mối quan hệ](media/relationships-add.png "Nhập chi tiết mối quan hệ")</span><span class="sxs-lookup"><span data-stu-id="b22a9-124">![Enter relationship details](media/relationships-add.png "Enter relationship details")</span></span>

   - <span data-ttu-id="b22a9-125">**Tên mối quan hệ**: Tên phản ánh mục đích của mối quan hệ (ví dụ: **Tài khoản WebLogs**).</span><span class="sxs-lookup"><span data-stu-id="b22a9-125">**Relationship name**: Name that reflects the purpose of the relationship (for example, **AccountWebLogs**).</span></span>
   - <span data-ttu-id="b22a9-126">**Mô tả**: Mô tả về mối quan hệ.</span><span class="sxs-lookup"><span data-stu-id="b22a9-126">**Description**: Description of the relationship.</span></span>
   - <span data-ttu-id="b22a9-127">**Thực thể nguồn**: Chọn thực thể được sử dụng làm nguồn trong mối quan hệ (ví dụ: WebLog).</span><span class="sxs-lookup"><span data-stu-id="b22a9-127">**Source entity**: Select the entity that is used as a source in the relationship (for example, WebLog).</span></span>
   - <span data-ttu-id="b22a9-128">**Lượng số**: Chọn lượng số của các bản ghi thực thể nguồn.</span><span class="sxs-lookup"><span data-stu-id="b22a9-128">**Cardinality**: Select the cardinality of the source entity records.</span></span> <span data-ttu-id="b22a9-129">Ví dụ: "nhiều" có nghĩa là nhiều bản ghi Weblog được liên kết với một WebAccount.</span><span class="sxs-lookup"><span data-stu-id="b22a9-129">For example, "many" means that multiple Weblog records are related to one WebAccount.</span></span>
   - <span data-ttu-id="b22a9-130">**Trường khóa nguồn**: Đại diện cho trường khóa ngoại trong thực thể nguồn.</span><span class="sxs-lookup"><span data-stu-id="b22a9-130">**Source key field**: This represents the foreign key field in the source entity.</span></span> <span data-ttu-id="b22a9-131">Ví dụ: WebLog có trường khóa ngoại **accountId**.</span><span class="sxs-lookup"><span data-stu-id="b22a9-131">For example, WebLog has the **accountId** foreign key field.</span></span>
   - <span data-ttu-id="b22a9-132">**Thực thể đích**: Chọn thực thể được sử dụng làm đích trong mối quan hệ (ví dụ: WebAccount).</span><span class="sxs-lookup"><span data-stu-id="b22a9-132">**Target entity**: Select the entity that is used as a target in the relationship (for example, WebAccount).</span></span>
   - <span data-ttu-id="b22a9-133">**Lượng số đích**: Chọn lượng số của các bản ghi thực thể đích.</span><span class="sxs-lookup"><span data-stu-id="b22a9-133">**Target cardinality**: Select the cardinality of the target entity records.</span></span> <span data-ttu-id="b22a9-134">Ví dụ: "một" có nghĩa là nhiều bản ghi Weblog được liên kết với một WebAccount.</span><span class="sxs-lookup"><span data-stu-id="b22a9-134">For example, "one" means that multiple Weblog records are related to one WebAccount.</span></span>
   - <span data-ttu-id="b22a9-135">**Trường khóa mục tiêu**: Trường này đại diện cho trường khóa của thực thể đích.</span><span class="sxs-lookup"><span data-stu-id="b22a9-135">**Target key field**: This field represents the key field of target entity.</span></span> <span data-ttu-id="b22a9-136">Ví dụ: WebAccount có trường khóa ngoại **accountId**.</span><span class="sxs-lookup"><span data-stu-id="b22a9-136">For example, WebAccount has the **accountId** key field.</span></span>

> [!NOTE]
> <span data-ttu-id="b22a9-137">Chỉ hỗ trợ các mối quan hệ nhiều-một và một-một.</span><span class="sxs-lookup"><span data-stu-id="b22a9-137">Only many-to-one and one-to-one relationships are supported.</span></span> <span data-ttu-id="b22a9-138">Mối quan hệ nhiều-nhiều có thể được tạo bằng hai mối quan hệ nhiều-một và một thực thể liên kết (thực thể được sử dụng để kết nối thực thể nguồn và thực thể đích).</span><span class="sxs-lookup"><span data-stu-id="b22a9-138">Many-to-many relationships can be created using two many-to-one relationships and a link entity (an entity that is used to connect the source entity and the target entity).</span></span>

## <a name="delete-a-relationship"></a><span data-ttu-id="b22a9-139">Xóa mối quan hệ</span><span class="sxs-lookup"><span data-stu-id="b22a9-139">Delete a relationship</span></span>

1. <span data-ttu-id="b22a9-140">Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Dữ liệu** > **Mối quan hệ**.</span><span class="sxs-lookup"><span data-stu-id="b22a9-140">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="b22a9-141">Chọn hộp kiểm tương ứng với mối quan hệ bạn muốn xóa.</span><span class="sxs-lookup"><span data-stu-id="b22a9-141">Select check boxes for the relationships you want to delete.</span></span>

3. <span data-ttu-id="b22a9-142">Chọn **Xóa** ở đầu bảng **Mối quan hệ**.</span><span class="sxs-lookup"><span data-stu-id="b22a9-142">Select **Delete** at the top of the **Relationships** table.</span></span>

4. <span data-ttu-id="b22a9-143">Xác nhận tác vụ xóa của bạn.</span><span class="sxs-lookup"><span data-stu-id="b22a9-143">Confirm your deletion.</span></span>

## <a name="next-step"></a><span data-ttu-id="b22a9-144">Bước tiếp theo</span><span class="sxs-lookup"><span data-stu-id="b22a9-144">Next step</span></span>

<span data-ttu-id="b22a9-145">Mối quan hệ hệ thống và tùy chỉnh được sử dụng để tạo các phân đoạn dựa trên nhiều nguồn dữ liệu không còn tồn tại.</span><span class="sxs-lookup"><span data-stu-id="b22a9-145">System and custom relationships are used to create segments based on multiple data sources that are no longer siloed.</span></span> <span data-ttu-id="b22a9-146">Để biết thêm thông tin, hãy xem [Phân khúc](segments.md).</span><span class="sxs-lookup"><span data-stu-id="b22a9-146">For more information, see [Segments](segments.md).</span></span>
