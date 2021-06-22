---
title: Mối quan hệ giữa các thực thể và đường dẫn thực thể
description: Tạo và quản lý mối quan hệ giữa các thực thể từ nhiều nguồn dữ liệu.
ms.date: 06/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: d5b9566ec88096fec31d8e164a51598159ec26d4
ms.sourcegitcommit: ece48f80a7b470fb33cd36e3096b4f1e9190433a
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 06/03/2021
ms.locfileid: "6171190"
---
# <a name="relationships-between-entities"></a><span data-ttu-id="47b46-103">Mối quan hệ giữa các thực thể</span><span class="sxs-lookup"><span data-stu-id="47b46-103">Relationships between entities</span></span>

<span data-ttu-id="47b46-104">Mối quan hệ kết nối các thực thể và xác định một biểu đồ dữ liệu của bạn khi các thực thể có cùng một khóa ngoại, mã định danh chung.</span><span class="sxs-lookup"><span data-stu-id="47b46-104">Relationships connect entities and define a graph of your data when entities share a common identifier, a foreign key.</span></span> <span data-ttu-id="47b46-105">Khóa ngoại này có thể được tham chiếu từ thực thể này sang thực thể khác.</span><span class="sxs-lookup"><span data-stu-id="47b46-105">This foreign key can be referenced from one entity to another.</span></span> <span data-ttu-id="47b46-106">Các thực thể được kết nối cho phép bạn xác định các phân khúc và giá trị đo dựa trên nhiều nguồn dữ liệu.</span><span class="sxs-lookup"><span data-stu-id="47b46-106">Connected entities enable the definition of segments and measures based on multiple data sources.</span></span>

<span data-ttu-id="47b46-107">Có 3 loại mối quan hệ:</span><span class="sxs-lookup"><span data-stu-id="47b46-107">There are three types of relationships:</span></span> 
- <span data-ttu-id="47b46-108">Mối quan hệ hệ thống không thể chỉnh sửa, do hệ thống tạo trong quá trình hợp nhất dữ liệu</span><span class="sxs-lookup"><span data-stu-id="47b46-108">Non-editable system relationships, created by the system as part of the data unification process</span></span>
- <span data-ttu-id="47b46-109">Mối quan hệ kế thừa không thể chỉnh sửa, được tạo tự động từ quá trình nhập nguồn dữ liệu</span><span class="sxs-lookup"><span data-stu-id="47b46-109">Non-editable inherited relationships, which are created automatically from ingesting data sources</span></span> 
- <span data-ttu-id="47b46-110">Mối quan hệ tùy chỉnh có thể chỉnh sửa, do người dùng tạo và đặt cấu hình</span><span class="sxs-lookup"><span data-stu-id="47b46-110">Editable custom relationships, created and configured by users</span></span>

## <a name="non-editable-system-relationships"></a><span data-ttu-id="47b46-111">Mối quan hệ hệ thống không thể chỉnh sửa</span><span class="sxs-lookup"><span data-stu-id="47b46-111">Non-editable system relationships</span></span>

<span data-ttu-id="47b46-112">Trong quá trình hợp nhất dữ liệu, các mối quan hệ hệ thống được tạo tự động dựa trên tính năng kết hợp thông minh.</span><span class="sxs-lookup"><span data-stu-id="47b46-112">During data unification, system relationships are created automatically based on intelligent matching.</span></span> <span data-ttu-id="47b46-113">Các mối quan hệ này giúp liên kết bản ghi hồ sơ khách hàng với bản ghi tương ứng.</span><span class="sxs-lookup"><span data-stu-id="47b46-113">These relationships help relate the customer profile records with corresponding records.</span></span> <span data-ttu-id="47b46-114">Sơ đồ sau minh họa quá trình tạo ra 3 mối quan hệ dựa trên hệ thống.</span><span class="sxs-lookup"><span data-stu-id="47b46-114">The following diagram illustrates the creation of three system-based relationships.</span></span> <span data-ttu-id="47b46-115">Thực thể khách hàng được kết hợp với các thực thể khác để tạo ra thực thể *Customer* hợp nhất.</span><span class="sxs-lookup"><span data-stu-id="47b46-115">The customer entity is matched with other entities to produce the unified *Customer* entity.</span></span>

:::image type="content" source="media/relationships-entities-merge.png" alt-text="Sơ đồ với các đường dẫn mối quan hệ cho thực thể khách hàng với 3 mối quan hệ 1-n.":::

- <span data-ttu-id="47b46-117">**Mối quan hệ *CustomerToContact*** được tạo giữa thực thể *Customer* và *Contact*.</span><span class="sxs-lookup"><span data-stu-id="47b46-117">***CustomerToContact* relationship** was created between the *Customer* entity and the *Contact* entity.</span></span> <span data-ttu-id="47b46-118">Thực thể *Customer* lấy trường khóa **Contact_contactID** để liên kết với trường khóa **contactID** của thực thể *Contact*.</span><span class="sxs-lookup"><span data-stu-id="47b46-118">The *Customer* entity gets the key field **Contact_contactID** to relate to the *Contact* entity key field **contactID**.</span></span>
- <span data-ttu-id="47b46-119">**Mối quan hệ *CustomerToAccount*** được tạo giữa thực thể *Customer* và thực thể *Account*.</span><span class="sxs-lookup"><span data-stu-id="47b46-119">***CustomerToAccount* relationship** was created between the *Customer* entity and the *Account* entity.</span></span> <span data-ttu-id="47b46-120">Thực thể *Customer* lấy trường khóa **Account_accountID** để liên kết với trường khóa **accountID** của thực thể *Account*.</span><span class="sxs-lookup"><span data-stu-id="47b46-120">The *Customer* entity gets the key field **Account_accountID** to relate to the *Account* entity key field **accountID**.</span></span>
- <span data-ttu-id="47b46-121">**Mối quan hệ *CustomerToWebAccount*** được tạo giữa thực thể *Customer* và thực thể *WebAccount*.</span><span class="sxs-lookup"><span data-stu-id="47b46-121">***CustomerToWebAccount* relationship** was created between the *Customer* entity and the *WebAccount* entity.</span></span> <span data-ttu-id="47b46-122">Thực thể *Customer* lấy trường khóa **WebAccount_webaccountID** để liên kết với trường khóa **webaccountID** của thực thể *WebAccount*.</span><span class="sxs-lookup"><span data-stu-id="47b46-122">The *Customer* entity gets the key field **WebAccount_webaccountID** to relate to the *WebAccount* entity key field **webaccountID**.</span></span>

## <a name="non-editable-inherited-relationships"></a><span data-ttu-id="47b46-123">Mối quan hệ kế thừa không thể chỉnh sửa</span><span class="sxs-lookup"><span data-stu-id="47b46-123">Non-editable inherited relationships</span></span>

<span data-ttu-id="47b46-124">Trong quá trình nhập dữ liệu, hệ thống sẽ kiểm tra nguồn dữ liệu để tìm các mối quan hệ hiện có.</span><span class="sxs-lookup"><span data-stu-id="47b46-124">During the data ingestion process, the system checks data sources for existing relationships.</span></span> <span data-ttu-id="47b46-125">Nếu không có mối quan hệ nào tồn tại, hệ thống sẽ tự động tạo.</span><span class="sxs-lookup"><span data-stu-id="47b46-125">If no relationship exists, the system automatically creates them.</span></span> <span data-ttu-id="47b46-126">Các mối quan hệ này cũng dùng trong các quy trình xuôi tuyến.</span><span class="sxs-lookup"><span data-stu-id="47b46-126">These relationships are also used in downstream processes.</span></span>

## <a name="create-a-custom-relationship"></a><span data-ttu-id="47b46-127">Tạo mối quan hệ tùy chỉnh</span><span class="sxs-lookup"><span data-stu-id="47b46-127">Create a custom relationship</span></span>

<span data-ttu-id="47b46-128">Mối quan hệ bao gồm một *thực thể nguồn* chứa khóa ngoại và một *thực thể đích* mà khóa ngoại của thực thể nguồn trỏ đến.</span><span class="sxs-lookup"><span data-stu-id="47b46-128">Relationship consists of a *source entity* containing the foreign key and a *target entity* that the source entity's foreign key points to.</span></span> 

1. <span data-ttu-id="47b46-129">Trong thông tin chuyên sâu về đối tượng, hãy chuyển đến **Dữ liệu** > **Mối quan hệ**.</span><span class="sxs-lookup"><span data-stu-id="47b46-129">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="47b46-130">Chọn **Mối quan hệ mới**.</span><span class="sxs-lookup"><span data-stu-id="47b46-130">Select **New relationship**.</span></span>

3. <span data-ttu-id="47b46-131">Trong ngăn **Mối quan hệ mới**, hãy cung cấp các thông tin sau:</span><span class="sxs-lookup"><span data-stu-id="47b46-131">In the **New relationship** pane, provide the following information:</span></span>

   :::image type="content" source="media/relationship-add.png" alt-text="Ngăn bên Mối quan hệ mới với các trường nhập dữ liệu trống.":::

   - <span data-ttu-id="47b46-133">**Tên mối quan hệ**: Tên phản ánh mục đích của mối quan hệ.</span><span class="sxs-lookup"><span data-stu-id="47b46-133">**Relationship name**: Name that reflects the purpose of the relationship.</span></span> <span data-ttu-id="47b46-134">Ví dụ: CustomerToSupportCase.</span><span class="sxs-lookup"><span data-stu-id="47b46-134">Example: CustomerToSupportCase.</span></span>
   - <span data-ttu-id="47b46-135">**Mô tả**: Mô tả về mối quan hệ.</span><span class="sxs-lookup"><span data-stu-id="47b46-135">**Description**: Description of the relationship.</span></span>
   - <span data-ttu-id="47b46-136">**Thực thể nguồn**: Thực thể dùng làm nguồn trong mối quan hệ.</span><span class="sxs-lookup"><span data-stu-id="47b46-136">**Source entity**: Entity that is used as a source in the relationship.</span></span> <span data-ttu-id="47b46-137">Ví dụ: SupportCase.</span><span class="sxs-lookup"><span data-stu-id="47b46-137">Example: SupportCase.</span></span>
   - <span data-ttu-id="47b46-138">**Thực thể đích**: Thực thể dùng làm đích trong mối quan hệ.</span><span class="sxs-lookup"><span data-stu-id="47b46-138">**Target entity**: Entity that is used as a target in the relationship.</span></span> <span data-ttu-id="47b46-139">Ví dụ: Customer.</span><span class="sxs-lookup"><span data-stu-id="47b46-139">Example: Customer.</span></span>
   - <span data-ttu-id="47b46-140">**Lượng số nguồn**: Chỉ định lượng số của thực thể nguồn.</span><span class="sxs-lookup"><span data-stu-id="47b46-140">**Source cardinality**: Specify the cardinality of the source entity.</span></span> <span data-ttu-id="47b46-141">Lượng số mô tả số phần tử có thể có trong một tập hợp.</span><span class="sxs-lookup"><span data-stu-id="47b46-141">Cardinality describes the number of possible elements in a set.</span></span> <span data-ttu-id="47b46-142">Lượng số nguồn luôn liên quan đến lượng số đích.</span><span class="sxs-lookup"><span data-stu-id="47b46-142">It always relates to the target cardinality.</span></span> <span data-ttu-id="47b46-143">Bạn có thể chọn giữa **Một** và **Nhiều**.</span><span class="sxs-lookup"><span data-stu-id="47b46-143">You can choose between **One** and **Many**.</span></span> <span data-ttu-id="47b46-144">Chỉ hỗ trợ các mối quan hệ nhiều-một và một-một.</span><span class="sxs-lookup"><span data-stu-id="47b46-144">Only many-to-one and one-to-one relationships are supported.</span></span>  
     - <span data-ttu-id="47b46-145">Nhiều-một: Nhiều bản ghi nguồn có thể liên kết với một bản ghi đích.</span><span class="sxs-lookup"><span data-stu-id="47b46-145">Many-to-one: Multiple source records can relate to one target record.</span></span> <span data-ttu-id="47b46-146">Ví dụ: Nhiều trường hợp hỗ trợ từ một khách hàng.</span><span class="sxs-lookup"><span data-stu-id="47b46-146">Example: Multiple support cases from a single customer.</span></span>
     - <span data-ttu-id="47b46-147">Một-một: Một bản ghi nguồn liên kết với một bản ghi đích.</span><span class="sxs-lookup"><span data-stu-id="47b46-147">One-to-one: A single source record relates to a one target record.</span></span> <span data-ttu-id="47b46-148">Ví dụ: Một ID khách hàng thân thiết cho một khách hàng.</span><span class="sxs-lookup"><span data-stu-id="47b46-148">Example: One loyalty ID for a single customer.</span></span>

     > [!NOTE]
     > <span data-ttu-id="47b46-149">Bạn có thể tạo mối quan hệ nhiều-nhiều bằng cách sử dụng 2 mối quan hệ nhiều-một và một thực thể liên kết, kết nối thực thể nguồn và thực thể đích.</span><span class="sxs-lookup"><span data-stu-id="47b46-149">Many-to-many relationships can be created using two many-to-one relationships and a linking entity, which connects the source entity and the target entity.</span></span>

   - <span data-ttu-id="47b46-150">**Lượng số đích**: Chọn lượng số của các bản ghi thực thể đích.</span><span class="sxs-lookup"><span data-stu-id="47b46-150">**Target cardinality**: Select the cardinality of the target entity records.</span></span> 
   - <span data-ttu-id="47b46-151">**Trường khóa nguồn**: Trường khóa ngoại trong thực thể nguồn.</span><span class="sxs-lookup"><span data-stu-id="47b46-151">**Source key field**: The foreign key field in the source entity.</span></span> <span data-ttu-id="47b46-152">Ví dụ: SupportCase có thể sử dụng CaseID làm trường khóa ngoại.</span><span class="sxs-lookup"><span data-stu-id="47b46-152">Example: SupportCase could use CaseID as a foreign key field.</span></span>
   - <span data-ttu-id="47b46-153">**Trường khóa đích**: Trường khóa của thực thể đích.</span><span class="sxs-lookup"><span data-stu-id="47b46-153">**Target key field**: The key field of the target entity.</span></span> <span data-ttu-id="47b46-154">Ví dụ: Thực thể Customer có thể sử dụng trường khóa **CustomerID**.</span><span class="sxs-lookup"><span data-stu-id="47b46-154">Example Customer could use the **CustomerID** key field.</span></span>

4. <span data-ttu-id="47b46-155">Chọn **Lưu** để tạo mối quan hệ tùy chỉnh.</span><span class="sxs-lookup"><span data-stu-id="47b46-155">Select **Save** to create the custom relationship.</span></span>

## <a name="view-relationships"></a><span data-ttu-id="47b46-156">Xem mối quan hệ</span><span class="sxs-lookup"><span data-stu-id="47b46-156">View relationships</span></span>

<span data-ttu-id="47b46-157">Trang Mối quan hệ liệt kê tất cả các mối quan hệ đã được tạo.</span><span class="sxs-lookup"><span data-stu-id="47b46-157">The Relationships page lists all the relationships that have been created.</span></span> <span data-ttu-id="47b46-158">Mỗi hàng đại diện cho một mối quan hệ, cũng bao gồm thông tin chi tiết về thực thể nguồn, thực thể đích và lượng số.</span><span class="sxs-lookup"><span data-stu-id="47b46-158">Each row represents a relationship, which also includes details about the source entity, the target entity, and the cardinality.</span></span> 

:::image type="content" source="media/relationships-list.png" alt-text="Danh sách các mối quan hệ và tùy chọn trong thanh tác vụ của trang Mối quan hệ.":::

<span data-ttu-id="47b46-160">Trang này cung cấp một bộ tùy chọn cho các mối quan hệ hiện có và mới:</span><span class="sxs-lookup"><span data-stu-id="47b46-160">This page offers a set of options for existing and new relationships:</span></span> 
- <span data-ttu-id="47b46-161">**Mối quan hệ mới**: [Tạo mối quan hệ tùy chỉnh](#create-a-custom-relationship).</span><span class="sxs-lookup"><span data-stu-id="47b46-161">**New Relationship**: [Create a custom relationship](#create-a-custom-relationship).</span></span>
- <span data-ttu-id="47b46-162">**Trình hiển thị**: [Khám phá trình hiển thị mối quan hệ](#explore-the-relationship-visualizer) để xem sơ đồ mạng lưới của các mối quan hệ hiện có và lượng số của chúng.</span><span class="sxs-lookup"><span data-stu-id="47b46-162">**Visualizer**: [Explore the relationship visualizer](#explore-the-relationship-visualizer) to see a network diagram of the existing relationships and their cardinality.</span></span>
- <span data-ttu-id="47b46-163">**Lọc theo**: Chọn loại mối quan hệ để hiển thị trong danh sách.</span><span class="sxs-lookup"><span data-stu-id="47b46-163">**Filter by**: Choose the type of relationships to show in the list.</span></span>
- <span data-ttu-id="47b46-164">**Tìm kiếm mối quan hệ**: Sử dụng chức năng tìm kiếm dựa trên văn bản trên các thuộc tính của mối quan hệ.</span><span class="sxs-lookup"><span data-stu-id="47b46-164">**Search relationships**: Use a text-based search on properties of the relationships.</span></span>

### <a name="explore-the-relationship-visualizer"></a><span data-ttu-id="47b46-165">Khám phá trình hiển thị mối quan hệ</span><span class="sxs-lookup"><span data-stu-id="47b46-165">Explore the relationship visualizer</span></span>

<span data-ttu-id="47b46-166">Trình hiển thị mối quan hệ hiển thị sơ đồ mạng lưới của các mối quan hệ hiện có giữa các thực thể được kết nối và lượng số của chúng.</span><span class="sxs-lookup"><span data-stu-id="47b46-166">The relationship visualizer shows a network diagram of the existing relationships between connected entities and their cardinality.</span></span>

<span data-ttu-id="47b46-167">Để tùy chỉnh dạng xem này, bạn có thể thay đổi vị trí của các hộp bằng cách kéo chúng trên canvas.</span><span class="sxs-lookup"><span data-stu-id="47b46-167">To customize the view, you can change the position of the boxes by dragging them on the canvas.</span></span>

:::image type="content" source="media/relationship-visualizer.png" alt-text="Ảnh chụp màn hình sơ đồ mạng lưới của trình hiển thị mối quan hệ với các kết nối giữa các thực thể liên quan.":::

<span data-ttu-id="47b46-169">Các tùy chọn có thể dùng:</span><span class="sxs-lookup"><span data-stu-id="47b46-169">Available options:</span></span> 
- <span data-ttu-id="47b46-170">**Xuất dưới dạng hình ảnh**: Lưu dạng xem hiện tại dưới dạng tệp hình ảnh.</span><span class="sxs-lookup"><span data-stu-id="47b46-170">**Export as image**: Save the current view as an image file.</span></span>
- <span data-ttu-id="47b46-171">**Thay đổi thành bố cục ngang/dọc**: Thay đổi hướng của các thực thể và mối quan hệ.</span><span class="sxs-lookup"><span data-stu-id="47b46-171">**Change to horizontal/vertical layout**: Change the alignment of the entities and relationships.</span></span>
- <span data-ttu-id="47b46-172">**Chỉnh sửa**: Cập nhật các thuộc tính của mối quan hệ tùy chỉnh trong ngăn chỉnh sửa và lưu các thay đổi.</span><span class="sxs-lookup"><span data-stu-id="47b46-172">**Edit**: Update properties of custom relationships in the edit pane and save changes.</span></span>

## <a name="manage-existing-relationships"></a><span data-ttu-id="47b46-173">Quản lý mối quan hệ hiện có</span><span class="sxs-lookup"><span data-stu-id="47b46-173">Manage existing relationships</span></span> 

<span data-ttu-id="47b46-174">Trên trang Mối quan hệ, mỗi mối quan hệ được thể hiện bằng một hàng.</span><span class="sxs-lookup"><span data-stu-id="47b46-174">On the Relationships page, each relationship is represented by a row.</span></span> 

<span data-ttu-id="47b46-175">Chọn một mối quan hệ rồi chọn một trong các tùy chọn sau:</span><span class="sxs-lookup"><span data-stu-id="47b46-175">Select a relationship and choose one of the following options:</span></span> 
 
- <span data-ttu-id="47b46-176">**Chỉnh sửa**: Cập nhật các thuộc tính của mối quan hệ tùy chỉnh trong ngăn chỉnh sửa và lưu các thay đổi.</span><span class="sxs-lookup"><span data-stu-id="47b46-176">**Edit**: Update properties of custom relationships in the edit pane and save changes.</span></span>
- <span data-ttu-id="47b46-177">**Xóa**: Xóa mối quan hệ tùy chỉnh.</span><span class="sxs-lookup"><span data-stu-id="47b46-177">**Delete**: Delete custom relationships.</span></span>
- <span data-ttu-id="47b46-178">**Xem**: Xem mối quan hệ do hệ thống tạo và mối quan hệ kế thừa.</span><span class="sxs-lookup"><span data-stu-id="47b46-178">**View**: View system-created and inherited relationships.</span></span> 

## <a name="next-step"></a><span data-ttu-id="47b46-179">Bước tiếp theo</span><span class="sxs-lookup"><span data-stu-id="47b46-179">Next step</span></span>

<span data-ttu-id="47b46-180">Các mối quan hệ tùy chỉnh và hệ thống dùng để [tạo phân khúc](segments.md) dựa trên nhiều nguồn dữ liệu không còn lưu trữ theo dạng silo.</span><span class="sxs-lookup"><span data-stu-id="47b46-180">System and custom relationships are used to [create segments](segments.md) based on multiple data sources that are no longer siloed.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
