---
title: Ánh xạ các thực thể để hợp nhất dữ liệu
description: Ánh xạ dữ liệu để tạo hồ sơ khách hàng hợp nhất.
ms.date: 09/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: e98c7717f7707d43a9fd1fc6f6b0e9c49e4e7ee0
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407326"
---
# <a name="map-entities-and-attributes"></a><span data-ttu-id="d9a7b-103">Ánh xạ thực thể và thuộc tính</span><span class="sxs-lookup"><span data-stu-id="d9a7b-103">Map entities and attributes</span></span>

<span data-ttu-id="d9a7b-104">**Ánh xạ** là giai đoạn đầu tiên trong quy trình hợp nhất dữ liệu của thông tin chi tiết về đối tượng.</span><span class="sxs-lookup"><span data-stu-id="d9a7b-104">**Map** is the first stage in the data unification process of audience insights.</span></span> <span data-ttu-id="d9a7b-105">Ánh xạ bao gồm ba giai đoạn:</span><span class="sxs-lookup"><span data-stu-id="d9a7b-105">Mapping consists of three phases:</span></span>

- <span data-ttu-id="d9a7b-106">*Lựa chọn thực thể*: Xác định các thực thể có thể kết hợp dẫn đến tập dữ liệu có thông tin đầy đủ hơn về khách hàng của bạn.</span><span class="sxs-lookup"><span data-stu-id="d9a7b-106">*Entity selection*: Identify the combinable entities that lead to a dataset with more complete information about your customers.</span></span>
- <span data-ttu-id="d9a7b-107">*Lựa chọn thuộc tính*: Đối với mỗi thực thể, xác định các cột bạn muốn kết hợp và hợp nhất trong giai đoạn *so khớp* và *hợp nhất*.</span><span class="sxs-lookup"><span data-stu-id="d9a7b-107">*Attribute selection*: For each entity, identify the columns you want to combine and reconcile in the *match* and *merge* phases.</span></span> <span data-ttu-id="d9a7b-108">Các cột này có tên là *Thuộc tính*.</span><span class="sxs-lookup"><span data-stu-id="d9a7b-108">These columns are called *Attributes*.</span></span>
- <span data-ttu-id="d9a7b-109">*Khóa chính và lựa chọn kiểu ngữ nghĩa*: Đối với mỗi thực thể, hãy xác định một thuộc tính bạn muốn xác định làm khóa chính cho thực thể đó và đối với mỗi thuộc tính, hãy xác định một loại ngữ nghĩa mô tả tốt nhất thuộc tính đó.</span><span class="sxs-lookup"><span data-stu-id="d9a7b-109">*Primary key and semantic type selection*: For each entity, identify an attribute you want to define as the primary key for that entity, and for each attribute, identify a semantic type that best describes that attribute.</span></span>

<span data-ttu-id="d9a7b-110">Để biết thêm thông tin về quy trình hợp nhất dữ liệu chung, hãy xem [Hợp nhất](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="d9a7b-110">For more information about the general flow of data unification, see [Unify](data-unification.md).</span></span>

## <a name="select-the-first-entities"></a><span data-ttu-id="d9a7b-111">Chọn thực thể đầu tiên</span><span class="sxs-lookup"><span data-stu-id="d9a7b-111">Select the first entities</span></span>

1. <span data-ttu-id="d9a7b-112">Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Dữ liệu** > **Hợp nhất** > **Ánh xạ**.</span><span class="sxs-lookup"><span data-stu-id="d9a7b-112">In audience insights, go to **Data** > **Unify** > **Map**.</span></span>

2. <span data-ttu-id="d9a7b-113">Bắt đầu giai đoạn ánh xạ bằng cách chọn **Chọn thực thể**.</span><span class="sxs-lookup"><span data-stu-id="d9a7b-113">Start the map phase by selecting **Select entities**.</span></span>

3. <span data-ttu-id="d9a7b-114">Chọn các thực thể và thuộc tính bạn muốn sử dụng trong giai đoạn *khớp* và *hợp nhất*.</span><span class="sxs-lookup"><span data-stu-id="d9a7b-114">Select the entities and attributes you want to use in the *match* and *merge* phases.</span></span> <span data-ttu-id="d9a7b-115">Bạn có thể chọn các thuộc tính bắt buộc riêng lẻ từ một thực thể hoặc bao gồm tất cả các thuộc tính từ một thực thể bằng cách chọn hộp kiểm **Bao gồm tất cả các trường** ở cấp thực thể.</span><span class="sxs-lookup"><span data-stu-id="d9a7b-115">You can select the required attributes individually from an entity or include all attributes from an entity by selecting the **Include all fields** checkbox on the entity level.</span></span> <span data-ttu-id="d9a7b-116">Chúng tôi khuyên bạn nên chọn ít nhất hai thực thể để hưởng lợi từ quá trình thống nhất dữ liệu.</span><span class="sxs-lookup"><span data-stu-id="d9a7b-116">We recommend selecting at least two entities to benefit from the data unification process.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d9a7b-117">![Ví dụ về thêm thực thể](media/data-manager-configure-map-add-entities-example.png "Ví dụ về thêm thực thể")</span><span class="sxs-lookup"><span data-stu-id="d9a7b-117">![Add entities example](media/data-manager-configure-map-add-entities-example.png "Add entities example")</span></span>

   <span data-ttu-id="d9a7b-118">Trong ví dụ này, chúng tôi đang thêm thực thể **eCommerceContacts** và **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="d9a7b-118">In this example, we're adding the **eCommerceContacts** and **loyCustomers** entities.</span></span> <span data-ttu-id="d9a7b-119">Bằng cách chọn những thực thể này, bạn có thể có được thông tin chi tiết về khách hàng kinh doanh trực tuyến nào là thành viên của chương trình khách hàng thân thiết.</span><span class="sxs-lookup"><span data-stu-id="d9a7b-119">By choosing these entities, you can derive insights on which of the online business customers are loyalty program members.</span></span>
   
   <span data-ttu-id="d9a7b-120">Bạn có thể tìm kiếm từ khóa trên tất cả các thuộc tính và thực thể để chọn các thuộc tính bắt buộc mà bạn muốn ánh xạ.</span><span class="sxs-lookup"><span data-stu-id="d9a7b-120">You can search on keywords across all attributes and entities to select the required attributes you want to map.</span></span>
   
     > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d9a7b-121">![Ví dụ về trường tìm kiếm](media/data-manager-configure-map-search-fields-example.png "Ví dụ về trường tìm kiếm")</span><span class="sxs-lookup"><span data-stu-id="d9a7b-121">![Search fields example](media/data-manager-configure-map-search-fields-example.png "Search fields example")</span></span>

4. <span data-ttu-id="d9a7b-122">Lựa chọn **Áp dụng** để xác nhận lựa chọn của bạn.</span><span class="sxs-lookup"><span data-stu-id="d9a7b-122">Select **Apply** to confirm your selections.</span></span>

## <a name="select-primary-key-and-semantic-type-for-attributes"></a><span data-ttu-id="d9a7b-123">Chọn khóa chính và loại ngữ nghĩa cho các thuộc tính</span><span class="sxs-lookup"><span data-stu-id="d9a7b-123">Select primary key and semantic type for attributes</span></span>

<span data-ttu-id="d9a7b-124">Sau khi chọn các thực thể của bạn, trang **Bản đồ** sẽ liệt kê các thực thể đã chọn để bạn xem xét.</span><span class="sxs-lookup"><span data-stu-id="d9a7b-124">After selecting your entities, the **Map** page lists the selected entities for your review.</span></span> <span data-ttu-id="d9a7b-125">Xác định khóa chính cho một thực thể và xác định kiểu ngữ nghĩa cho một thuộc tính trong thực thể.</span><span class="sxs-lookup"><span data-stu-id="d9a7b-125">Define the primary key for an entity and identify the semantic type for an attribute in the entity.</span></span>

- <span data-ttu-id="d9a7b-126">**Khóa chính**: Chọn một thuộc tính làm khóa chính cho từng thực thể của bạn.</span><span class="sxs-lookup"><span data-stu-id="d9a7b-126">**Primary key**: Select one attribute as a primary key for each of your entities.</span></span> <span data-ttu-id="d9a7b-127">Để một thuộc tính là khóa chính hợp lệ, thuộc tính đó không được bao gồm các giá trị trùng lặp, giá trị bị thiếu hoặc giá trị rỗng.</span><span class="sxs-lookup"><span data-stu-id="d9a7b-127">For an attribute to be a valid primary key, it shouldn't include duplicate values, missing values, or null values.</span></span> <span data-ttu-id="d9a7b-128">Các thuộc tính kiểu dữ liệu chuỗi, số nguyên và GUID được hỗ trợ làm khóa chính và sẽ được hiển thị trong một trường để bạn chọn.</span><span class="sxs-lookup"><span data-stu-id="d9a7b-128">String, integer, and GUID data type attributes are supported as primary keys and will be displayed in a field for you to select from.</span></span>

- <span data-ttu-id="d9a7b-129">**Loại ngữ nghĩa thuộc tính**: Danh mục các thuộc tính của bạn, chẳng hạn như địa chỉ email hoặc tên.</span><span class="sxs-lookup"><span data-stu-id="d9a7b-129">**Attribute semantic type**: Categories of your attributes, such as email address or name.</span></span> <span data-ttu-id="d9a7b-130">Để sử dụng mô hình trí tuệ nhân tạo cho dự đoán thông minh về ngữ nghĩa, tiết kiệm thời gian và cải thiện độ chính xác, hãy đặt **Ánh xạ thông minh** thành **BẬT**.</span><span class="sxs-lookup"><span data-stu-id="d9a7b-130">To use AI models for smart prediction of semantics, save time and improve accuracy, set **Intelligent mapping** to **ON**.</span></span> <span data-ttu-id="d9a7b-131">Ánh xạ thông minh làm nổi bật các đề xuất ngữ nghĩa dựa trên AI trong trường **Loại**.</span><span class="sxs-lookup"><span data-stu-id="d9a7b-131">Intelligent mapping highlights AI-based semantics recommendation in the **Type** field.</span></span> <span data-ttu-id="d9a7b-132">Nếu bạn đặt nó thành **TẮT**, bạn sẽ thấy các đề xuất ánh xạ thông thường của chúng tôi.</span><span class="sxs-lookup"><span data-stu-id="d9a7b-132">If you set it to **OFF**, you will see our regular mapping recommendations.</span></span> <span data-ttu-id="d9a7b-133">Bạn có thể chọn bất kỳ kiểu ngữ nghĩa nào từ danh sách tùy chọn có sẵn và ghi đè lựa chọn được gợi ý.</span><span class="sxs-lookup"><span data-stu-id="d9a7b-133">You can select any semantic type from the available list of options and override the suggested selection.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d9a7b-134">![Loại thuộc tính và ngữ nghĩa dự đoán](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Loại thuộc tính và ngữ nghĩa dự đoán")</span><span class="sxs-lookup"><span data-stu-id="d9a7b-134">![Attribute type and semantic prediction](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Attribute type and semantic prediction")</span></span>

<span data-ttu-id="d9a7b-135">Cũng có thể thêm một loại ngữ nghĩa tùy chỉnh.</span><span class="sxs-lookup"><span data-stu-id="d9a7b-135">Adding a custom semantic type is also possible.</span></span> <span data-ttu-id="d9a7b-136">Chọn trường loại cho thuộc tính đó và nhập tên loại ngữ nghĩa tùy chỉnh của bạn.</span><span class="sxs-lookup"><span data-stu-id="d9a7b-136">Select the type field for an attribute, and type your custom semantic type name.</span></span> <span data-ttu-id="d9a7b-137">Như vậy, bạn cũng có thể thay đổi các loại thuộc tính được xác định bởi hệ thống.</span><span class="sxs-lookup"><span data-stu-id="d9a7b-137">This way, you can also change the attribute types that were identified by the system.</span></span>

<span data-ttu-id="d9a7b-138">Tất cả các thuộc tính mà một loại ngữ nghĩa được nhận dạng tự động được nhóm lại trong phần **Xem lại các trường được ánh xạ**.</span><span class="sxs-lookup"><span data-stu-id="d9a7b-138">All attributes for which a semantic type is automatically identified are grouped in the **Review mapped fields** section.</span></span> <span data-ttu-id="d9a7b-139">Xem lại các thuộc tính này và các loại ngữ nghĩa của chúng vì chúng sẽ được sử dụng để kết hợp các thực thể của bạn trong bước hợp nhất của hợp nhất dữ liệu.</span><span class="sxs-lookup"><span data-stu-id="d9a7b-139">Review these attributes and their semantic types because they'll be used to combine your entities in the merge step of data unification.</span></span>

<span data-ttu-id="d9a7b-140">Các thuộc tính không được ánh xạ tự động đến một loại ngữ nghĩa được nhóm lại trong phần **Xác định dữ liệu trong các trường chưa được ánh xạ**.</span><span class="sxs-lookup"><span data-stu-id="d9a7b-140">Attributes that aren't automatically mapped to a semantic type are grouped in the **Define the data in the unmapped fields** section.</span></span> <span data-ttu-id="d9a7b-141">Chọn trường loại ngữ nghĩa cho các thuộc tính chưa được ánh xạ hoặc nhập tên loại thuộc tính tùy chỉnh của bạn.</span><span class="sxs-lookup"><span data-stu-id="d9a7b-141">Select the semantic type field for the unmapped attributes, or enter your custom attribute-type name.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d9a7b-142">![Khóa chính và loại thuộc tính](media/data-manager-configure-map-add-attributes.png "Khóa chính và loại thuộc tính")</span><span class="sxs-lookup"><span data-stu-id="d9a7b-142">![Primary key and attribute type](media/data-manager-configure-map-add-attributes.png "Primary key and attribute type")</span></span>

> [!NOTE]
> <span data-ttu-id="d9a7b-143">Một trường nên ánh xạ đến kiểu ngữ nghĩa Person.FullName để điền tên khách hàng vào thẻ khách hàng.</span><span class="sxs-lookup"><span data-stu-id="d9a7b-143">One field should map to the semantic type Person.FullName to populate the customer name in customer card.</span></span> <span data-ttu-id="d9a7b-144">Nếu không, thẻ khách hàng sẽ xuất hiện không tên.</span><span class="sxs-lookup"><span data-stu-id="d9a7b-144">Otherwise, the customer cards will appear nameless.</span></span> 

## <a name="add-and-remove-attributes-and-entities"></a><span data-ttu-id="d9a7b-145">Thêm và xóa các thuộc tính và thực thể</span><span class="sxs-lookup"><span data-stu-id="d9a7b-145">Add and remove attributes and entities</span></span>

1. <span data-ttu-id="d9a7b-146">Trên **Hợp nhất** > **Bản đồ**, chọn **Chỉnh sửa các trường**.</span><span class="sxs-lookup"><span data-stu-id="d9a7b-146">On **Unify** > **Map**, select **Edit fields**.</span></span>

2. <span data-ttu-id="d9a7b-147">Trong ngăn **Chỉnh sửa các trường**, thêm hoặc xóa các thuộc tính và thực thể.</span><span class="sxs-lookup"><span data-stu-id="d9a7b-147">In the **Edit fields** pane, add or remove attributes and entities.</span></span> <span data-ttu-id="d9a7b-148">Sử dụng tìm kiếm hoặc cuộn để tìm và chọn các thuộc tính và thực thể bạn quan tâm.</span><span class="sxs-lookup"><span data-stu-id="d9a7b-148">Use the search or scroll to find and select your attributes and entities of interest.</span></span> <span data-ttu-id="d9a7b-149">Bạn không thể xóa một thuộc tính hoặc một thực thể nếu chúng đã được đối sánh.</span><span class="sxs-lookup"><span data-stu-id="d9a7b-149">You can't remove an attribute or an entity if they've already been matched.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d9a7b-150">![Thêm hoặc loại bỏ thuộc tính](media/configure-data-map-edit.png "Thêm hoặc loại bỏ thuộc tính")</span><span class="sxs-lookup"><span data-stu-id="d9a7b-150">![Add or remove attributes](media/configure-data-map-edit.png "Add or remove attributes")</span></span>

3. <span data-ttu-id="d9a7b-151">Chọn **Áp dụng**.</span><span class="sxs-lookup"><span data-stu-id="d9a7b-151">Select **Apply**.</span></span>

## <a name="add-images-to-profiles"></a><span data-ttu-id="d9a7b-152">Thêm hình ảnh vào hồ sơ</span><span class="sxs-lookup"><span data-stu-id="d9a7b-152">Add images to profiles</span></span>

<span data-ttu-id="d9a7b-153">Nếu một thực thể chứa URL tới logo hoặc hình ảnh hồ sơ sẵn có công khai, bạn có thể thêm chúng vào hồ sơ khách hàng hợp nhất.</span><span class="sxs-lookup"><span data-stu-id="d9a7b-153">If an entity contains URLs to publicly available profile images or logos, you can add them to the unified customer profile.</span></span>

<span data-ttu-id="d9a7b-154">Chọn thực thể và tìm trường có chứa URL tới hình ảnh hồ sơ.</span><span class="sxs-lookup"><span data-stu-id="d9a7b-154">Select the entity and find the field that contains the URL to the profile image.</span></span> <span data-ttu-id="d9a7b-155">Trong trường nhập **Loại**, hãy nhập giá trị sau:</span><span class="sxs-lookup"><span data-stu-id="d9a7b-155">In the **Type** input field, manually enter the following value:</span></span> 
- <span data-ttu-id="d9a7b-156">Đối với một người: Person.ProfileImage</span><span class="sxs-lookup"><span data-stu-id="d9a7b-156">For a person: Person.ProfileImage</span></span>
- <span data-ttu-id="d9a7b-157">Đối với một tổ chức: Organisation.LogoImage</span><span class="sxs-lookup"><span data-stu-id="d9a7b-157">For an organization: Organization.LogoImage</span></span>

<span data-ttu-id="d9a7b-158">Tiếp tục với các bước hợp nhất và đảm bảo thuộc tính chứa URL hình ảnh cũng được thêm vào bước [Hợp nhất](merge-entities.md).</span><span class="sxs-lookup"><span data-stu-id="d9a7b-158">Continue with the unification steps and ensure the attribute that contains the image URL is also added in the [Merge](merge-entities.md) step.</span></span>

## <a name="set-attributes-for-organizations"></a><span data-ttu-id="d9a7b-159">Đặt thuộc tính cho tổ chức</span><span class="sxs-lookup"><span data-stu-id="d9a7b-159">Set attributes for organizations</span></span>

<span data-ttu-id="d9a7b-160">Đối với tổ chức (Xem trước), loại thuộc tính sẽ được ánh xạ tới "Organization.Name"</span><span class="sxs-lookup"><span data-stu-id="d9a7b-160">For organizations (Preview), the attribute type should be mapped to "Organization.Name"</span></span>
> [!div class="mx-imgBorder"]
> <span data-ttu-id="d9a7b-161">![Khóa chính và loại thuộc tính B2B](media/configure-data-map-edit-b2b.png "Khóa chính và loại thuộc tính B2B")</span><span class="sxs-lookup"><span data-stu-id="d9a7b-161">![Primary key and attribute type B2B](media/configure-data-map-edit-b2b.png "Primary key and attribute type B2B")</span></span>

## <a name="next-step"></a><span data-ttu-id="d9a7b-162">Bước tiếp theo</span><span class="sxs-lookup"><span data-stu-id="d9a7b-162">Next step</span></span>

<span data-ttu-id="d9a7b-163">Là một phần của quá trình thống nhất dữ liệu, hãy chuyển đến trang **So khớp**.</span><span class="sxs-lookup"><span data-stu-id="d9a7b-163">As part of the data unification process, go to the **Match** page.</span></span> <span data-ttu-id="d9a7b-164">Truy cập phần [**So khớp**](match-entities.md) để tìm hiểu về giai đoạn này.</span><span class="sxs-lookup"><span data-stu-id="d9a7b-164">Visit [**Match**](match-entities.md) to learn about this phase.</span></span>

> [!TIP]
> <span data-ttu-id="d9a7b-165">Xem video sau: [Bắt đầu: Tạo hồ sơ khách hàng hợp nhất](https://youtu.be/oBfGEhucAxs).</span><span class="sxs-lookup"><span data-stu-id="d9a7b-165">Check out the following video: [Getting Started: Creating a Unified Customer Profile](https://youtu.be/oBfGEhucAxs).</span></span>
