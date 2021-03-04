---
title: Cài đặt và đặt cấu hình phần bổ trợ Thẻ khách hàng
description: Cài đặt và đặt cấu hình Phần bổ trợ Thẻ Khách hàng cho Dynamics 365 Customer Insights.
ms.date: 01/20/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: a6d5b49380ed129cf147698a16f5f3f597bf7fbc
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268070"
---
# <a name="customer-card-add-in-preview"></a><span data-ttu-id="9c715-103">Trình bổ sung thẻ khách hàng (xem trước)</span><span class="sxs-lookup"><span data-stu-id="9c715-103">Customer Card Add-in (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="9c715-104">Nhận thông tin toàn diện về khách hàng ngay trong ứng dụng Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="9c715-104">Get a 360-degree view of your customers directly in Dynamics 365 apps.</span></span> <span data-ttu-id="9c715-105">Xem nhân khẩu học, thông tin chi tiết và dòng thời gian hoạt động qua Trình bổ trợ thẻ khách hàng.</span><span class="sxs-lookup"><span data-stu-id="9c715-105">View demographics, insights, and activity timelines with the Customer Card Add-in.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9c715-106">Điều kiện tiên quyết</span><span class="sxs-lookup"><span data-stu-id="9c715-106">Prerequisites</span></span>

- <span data-ttu-id="9c715-107">Ứng dụng Dynamics 365 (chẳng hạn như Trung tâm bán hàng hoặc Trung tâm Dịch vụ Khách hàng), phiên bản 9.0 trở lên với Giao diện Hợp nhất được bật.</span><span class="sxs-lookup"><span data-stu-id="9c715-107">Dynamics 365 app (such as Sales Hub or Customer Service Hub), version 9.0 and later with Unified Interface enabled.</span></span>
- <span data-ttu-id="9c715-108">Hồ sơ khách hàng [được nhập từ ứng dụng Dynamics 365 bằng cách sử dụng Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="9c715-108">Customer profiles [ingested from the Dynamics 365 app using Common Data Service](connect-power-query.md).</span></span>
- <span data-ttu-id="9c715-109">Người dùng phần bổ trợ Thẻ khách hàng cần được [thêm làm người dùng](permissions.md) trong thông tin chi tiết về đối tượng.</span><span class="sxs-lookup"><span data-stu-id="9c715-109">Users of the Customer Card Add-in need to be [added as users](permissions.md) in audience insights.</span></span>
- <span data-ttu-id="9c715-110">[Khả năng tìm kiếm và lọc đã định cấu hình](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="9c715-110">[Configured search and filter capabilities](search-filter-index.md).</span></span>
- <span data-ttu-id="9c715-111">Kiểm soát nhân khẩu học: Các trường nhân khẩu học (chẳng hạn như tuổi hoặc giới tính) có sẵn trong hồ sơ khách hàng hợp nhất.</span><span class="sxs-lookup"><span data-stu-id="9c715-111">Demographic control: Demographic fields(such as age or gender) are available in the unified customer profile.</span></span>
- <span data-ttu-id="9c715-112">Điều khiển tăng cường: Yêu cầu dữ liệu [tăng cường](enrichment-hub.md) hiện hoạt áp dụng cho hồ sơ khách hàng.</span><span class="sxs-lookup"><span data-stu-id="9c715-112">Enrichment control: Requires active [enrichments](enrichment-hub.md) applied to customer profiles.</span></span>
- <span data-ttu-id="9c715-113">Kiểm soát thông tin: Yêu cầu có dữ liệu được tạo bằng Azure Machine Learning ([Dự đoán](predictions.md) hoặc [Mô hình khách hàng](custom-models.md))</span><span class="sxs-lookup"><span data-stu-id="9c715-113">Intelligence control: Requires data generated using Azure Machine Learning ([Predictions](predictions.md) or [Custom Models](custom-models.md))</span></span>
- <span data-ttu-id="9c715-114">Kiểm soát đo lường: Yêu cầu [các biện pháp được đặt cấu hình](measures.md).</span><span class="sxs-lookup"><span data-stu-id="9c715-114">Measure control: Requires [configured measures](measures.md).</span></span>
- <span data-ttu-id="9c715-115">Kiểm soát dòng thời gian: Yêu cầu [các hoạt động được đặt cấu hình](activities.md).</span><span class="sxs-lookup"><span data-stu-id="9c715-115">Timeline control: Requires [configured activities](activities.md).</span></span>

## <a name="install-the-customer-card-add-in"></a><span data-ttu-id="9c715-116">Cài đặt phần bổ trợ Thẻ khách hàng</span><span class="sxs-lookup"><span data-stu-id="9c715-116">Install the Customer Card Add-in</span></span>

<span data-ttu-id="9c715-117">Phần bổ trợ Thẻ khách hàng là một giải pháp cho các ứng dụng gắn kết khách hàng trong Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="9c715-117">The Customer Card Add-in is a solution for customer engagement apps in Dynamics 365.</span></span> <span data-ttu-id="9c715-118">Để cài đặt giải pháp, hãy chuyển đến AppSource và tìm kiếm **Thẻ khách hàng Dynamics**.</span><span class="sxs-lookup"><span data-stu-id="9c715-118">To install the solution, go to AppSource and search for **Dynamics Customer Card**.</span></span> <span data-ttu-id="9c715-119">Chọn [Trình bổ sung thẻ khách hàng trên AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) và chọn **Tải ngay**.</span><span class="sxs-lookup"><span data-stu-id="9c715-119">Select the [Customer Card Add-in on AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) and select **Get It Now**.</span></span>

<span data-ttu-id="9c715-120">Bạn có thể cần phải đăng nhập bằng thông tin đăng nhập quản trị viên của mình cho ứng dụng Dynamics 365 để cài đặt giải pháp.</span><span class="sxs-lookup"><span data-stu-id="9c715-120">You may need to sign in with your admin credentials for the Dynamics 365 app to install the solution.</span></span>

<span data-ttu-id="9c715-121">Có thể mất một chút thời gian để cài đặt giải pháp vào môi trường của bạn.</span><span class="sxs-lookup"><span data-stu-id="9c715-121">It can take some time for the solution to be installed to your environment.</span></span>

## <a name="configure-the-customer-card-add-in"></a><span data-ttu-id="9c715-122">Đặt cấu hình Trình bổ trợ thẻ khách hàng</span><span class="sxs-lookup"><span data-stu-id="9c715-122">Configure the Customer Card Add-in</span></span>

1. <span data-ttu-id="9c715-123">Là quản trị viên, hãy đi tới phần **Cài đặt** trong ứng dụng hướng mô hình trong Dynamics 365 và chọn **Giải pháp**.</span><span class="sxs-lookup"><span data-stu-id="9c715-123">As an admin, go to the **Settings** section in Dynamics 365 and select **Solutions**.</span></span>

1. <span data-ttu-id="9c715-124">Chọn liên kết **Tên hiển thị** cho giải pháp Trình bổ trợ thẻ khách hàng **Dynamics 365 Customer Insights (Xem trước)**.</span><span class="sxs-lookup"><span data-stu-id="9c715-124">Select the **Display Name** link for the **Dynamics 365 Customer Insights Customer Card Add-in (Preview)** solution.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9c715-125">![Chọn tên hiển thị](media/select-display-name.png "Chọn tên hiển thị")</span><span class="sxs-lookup"><span data-stu-id="9c715-125">![Select display name](media/select-display-name.png "Select display name")</span></span>

1. <span data-ttu-id="9c715-126">Chọn **Đăng nhập** và nhập thông tin xác thực cho tài khoản quản trị viên bạn sử dụng để đặt cấu hình Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="9c715-126">Select **Sign in** and enter the credentials for the admin account you use to configure Customer Insights.</span></span>

   > [!NOTE]
   > <span data-ttu-id="9c715-127">Kiểm tra để đảm bảo trình chặn cửa sổ bật lên trong trình duyệt không chặn cửa sổ xác thực khi bạn chọn nút **Đăng nhập**.</span><span class="sxs-lookup"><span data-stu-id="9c715-127">Check that the browser pop-up blocker does not block the authentication window when you select the **Sign in** button.</span></span>

1. <span data-ttu-id="9c715-128">Chọn môi trường bạn muốn lấy dữ liệu từ đó.</span><span class="sxs-lookup"><span data-stu-id="9c715-128">Select the environment you want to fetch data from.</span></span>

1. <span data-ttu-id="9c715-129">Xác định ánh xạ trường tới các bản ghi trong ứng dụng Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="9c715-129">Define which the field mapping to records in the Dynamics 365 app.</span></span>
   - <span data-ttu-id="9c715-130">Để ánh xạ với một liên hệ, hãy chọn trường trong thực thể Khách hàng khớp với ID của thực thể liên hệ của bạn.</span><span class="sxs-lookup"><span data-stu-id="9c715-130">To map with a contact, select the field in the Customer entity that matches the ID of your contact entity.</span></span>
   - <span data-ttu-id="9c715-131">Để ánh xạ với một tài khoản, hãy chọn trường trong thực thể Khách hàng khớp với ID của thực thể tài khoản của bạn.</span><span class="sxs-lookup"><span data-stu-id="9c715-131">To map with an account, select the field in the Customer entity that matches the ID of your account entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9c715-132">![Trường ID người liên hệ](media/contact-id-field.png "Trường ID người liên hệ")</span><span class="sxs-lookup"><span data-stu-id="9c715-132">![Contact ID field](media/contact-id-field.png "Contact ID field")</span></span>

1. <span data-ttu-id="9c715-133">Chọn **Lưu cấu hình** để lưu cài đặt.</span><span class="sxs-lookup"><span data-stu-id="9c715-133">Select **Save configuration** to save the settings.</span></span>

1. <span data-ttu-id="9c715-134">Tiếp theo, bạn cần chỉ định vai trò bảo mật trong Dynamics 365 để người dùng có thể tùy chỉnh và xem thẻ khách hàng.</span><span class="sxs-lookup"><span data-stu-id="9c715-134">Next, you need to assign security roles in Dynamics 365 so users can customize and see the customer card.</span></span> <span data-ttu-id="9c715-135">Trong Dynamics 365, hãy chuyển tới **Cài đặt** > **Bảo mật** > **Người dùng**.</span><span class="sxs-lookup"><span data-stu-id="9c715-135">In Dynamics 365, go to **Settings** > **Security** > **Users**.</span></span> <span data-ttu-id="9c715-136">Chọn người dùng để chỉnh sửa vai trò người dùng và chọn **Quản lý vai trò**.</span><span class="sxs-lookup"><span data-stu-id="9c715-136">Select the users to edit user roles and select **Manage roles**.</span></span>

1. <span data-ttu-id="9c715-137">Gán vai trò **Người tùy chỉnh thẻ Customer Insights** cho những người dùng sẽ tùy chỉnh nội dung hiển thị trên thẻ cho toàn bộ tổ chức.</span><span class="sxs-lookup"><span data-stu-id="9c715-137">Assign the **Customer Insights Card Customizer** role to users who will customize the content shown on the card for the whole organization.</span></span>

## <a name="add-customer-card-controls-to-forms"></a><span data-ttu-id="9c715-138">Thêm kiểm soát Thẻ khách hàng vào biểu mẫu</span><span class="sxs-lookup"><span data-stu-id="9c715-138">Add Customer Card controls to forms</span></span>
  
1. <span data-ttu-id="9c715-139">Để thêm các điều khiển Thẻ khách hàng vào biểu mẫu Liên hệ của bạn, hãy chuyển tới **Cài đặt** > **Tùy chỉnh** trong Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="9c715-139">To add the Customer Card controls to your Contact form, go to the **Settings** > **Customizations** in Dynamics 365.</span></span>

1. <span data-ttu-id="9c715-140">Chọn **Tùy chỉnh hệ thống**.</span><span class="sxs-lookup"><span data-stu-id="9c715-140">Select **Customize the System**.</span></span>

1. <span data-ttu-id="9c715-141">Duyệt đến thực thể **Người liên hệ**, mở rộng thực thể này rồi chọn **Biểu mẫu**.</span><span class="sxs-lookup"><span data-stu-id="9c715-141">Browse to the **Contact** entity, expand it and select **Forms**.</span></span>

1. <span data-ttu-id="9c715-142">Chọn biểu mẫu người liên hệ mà bạn muốn thêm điều khiển Thẻ khách hàng.</span><span class="sxs-lookup"><span data-stu-id="9c715-142">Select the contact form to which you want to add the Customer Card controls.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="9c715-143">![Chọn biểu mẫu người liên hệ](media/contact-active-forms.png "Chọn biểu mẫu người liên hệ")</span><span class="sxs-lookup"><span data-stu-id="9c715-143">![Select Contact form](media/contact-active-forms.png "Select Contact form")</span></span>

1. <span data-ttu-id="9c715-144">Để thêm một điều khiển, trong công cụ biên tập biểu mẫu, hãy kéo trường bất kỳ từ **Field Explorer** tới vị trí bạn muốn điều khiển xuất hiện.</span><span class="sxs-lookup"><span data-stu-id="9c715-144">To add a control, in the form editor, drag any field from the **Field Explorer** to where you want the control to appear.</span></span>

1. <span data-ttu-id="9c715-145">Chọn trường trên biểu mẫu mà bạn vừa thêm, sau đó chọn **Thay đổi thuộc tính**.</span><span class="sxs-lookup"><span data-stu-id="9c715-145">Select the field on the form that you just added, and select **Change Properties**.</span></span>

1. <span data-ttu-id="9c715-146">Truy cập tab **Kiểm soát** và chọn **Thêm kiểm soát**.</span><span class="sxs-lookup"><span data-stu-id="9c715-146">Go to the **Controls** tab and select **Add Control**.</span></span> <span data-ttu-id="9c715-147">Chọn một trong các điều khiển tùy chỉnh có sẵn và chọn **Thêm**.</span><span class="sxs-lookup"><span data-stu-id="9c715-147">Choose one of the available custom controls and select **Add**.</span></span>

1. <span data-ttu-id="9c715-148">Trong hộp thoại **Thuộc tính trường**, bỏ chọn hộp **Hiển thị nhãn trên biểu mẫu**.</span><span class="sxs-lookup"><span data-stu-id="9c715-148">In the **Field Properties** dialog, clear the **Display label on the form** check box.</span></span>

1. <span data-ttu-id="9c715-149">Chọn tùy chọn **Web** cho điều khiển.</span><span class="sxs-lookup"><span data-stu-id="9c715-149">Select the **Web** option for the control.</span></span> <span data-ttu-id="9c715-150">Đối với điều khiển Tăng cường, hãy chọn loại tăng cường mà bạn muốn hiển thị bằng cách định cấu hình trường **enrichmentType**.</span><span class="sxs-lookup"><span data-stu-id="9c715-150">For the Enrichment control, select which enrichment type you want to display by configuring the **enrichmentType** field.</span></span> <span data-ttu-id="9c715-151">Thêm điều khiển làm phong phú riêng biệt cho từng loại làm phong phú.</span><span class="sxs-lookup"><span data-stu-id="9c715-151">Add a separate enrichment control for each enrichment type.</span></span>

1. <span data-ttu-id="9c715-152">Chọn **Lưu** và **Xuất bản** để xuất bản biểu mẫu liên hệ đã cập nhật.</span><span class="sxs-lookup"><span data-stu-id="9c715-152">Select **Save** and **Publish** to publish the updated contact form.</span></span>

1. <span data-ttu-id="9c715-153">Chuyển đến biểu mẫu liên hệ đã phát hành.</span><span class="sxs-lookup"><span data-stu-id="9c715-153">Go to the published contact form.</span></span> <span data-ttu-id="9c715-154">Bạn sẽ thấy điều khiển mới được thêm vào.</span><span class="sxs-lookup"><span data-stu-id="9c715-154">You'll see the newly added control.</span></span> <span data-ttu-id="9c715-155">Bạn có thể cần phải đăng nhập trong lần đầu tiên bạn sử dụng.</span><span class="sxs-lookup"><span data-stu-id="9c715-155">You might need to sign in the first time you use it.</span></span>

1. <span data-ttu-id="9c715-156">Để tùy chỉnh nội dung bạn muốn hiển thị trên điều khiển tùy chỉnh, hãy chọn nút chỉnh sửa ở góc trên bên phải.</span><span class="sxs-lookup"><span data-stu-id="9c715-156">To customize what you want to show on the custom control, select the edit button in the upper-right corner.</span></span>

## <a name="upgrade-customer-card-add-in"></a><span data-ttu-id="9c715-157">Nâng cấp phần bổ trợ Thẻ Khách hàng</span><span class="sxs-lookup"><span data-stu-id="9c715-157">Upgrade Customer Card Add-in</span></span>
<span data-ttu-id="9c715-158">Phần bổ trợ Thẻ Khách hàng không tự động nâng cấp.</span><span class="sxs-lookup"><span data-stu-id="9c715-158">The Customer Card Add-in doesn't upgrade automatically.</span></span> <span data-ttu-id="9c715-159">Để nâng cấp lên phiên bản mới nhất, hãy làm theo quy trình này trong ứng dụng Dynamics 365 đã cài đặt Phần bổ trợ.</span><span class="sxs-lookup"><span data-stu-id="9c715-159">To upgrade to the latest version, follow this procedure in the Dynamics 365 app that has the Add-in installed.</span></span>

1. <span data-ttu-id="9c715-160">Trong ứng dụng Dynamics 365, hãy chuyển đến **Cài đặt** > **Tùy chỉnh** và chọn **Các giải pháp**.</span><span class="sxs-lookup"><span data-stu-id="9c715-160">In the Dynamics 365 app, go to **Settings** > **Customization** and select **Solutions**.</span></span>

1. <span data-ttu-id="9c715-161">Trong bảng phần bổ trợ, hãy tìm **CustomerInsightsCustomerCard** và chọn hàng.</span><span class="sxs-lookup"><span data-stu-id="9c715-161">In the table of add-ins look for **CustomerInsightsCustomerCard** and select the row.</span></span>

1. <span data-ttu-id="9c715-162">Chọn **Áp dụng nâng cấp giải pháp** trong thanh tác vụ.</span><span class="sxs-lookup"><span data-stu-id="9c715-162">Select the **Apply Solution Upgrade** in the action bar.</span></span>

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Nâng cấp giải pháp trong khu vực Tùy chỉnh của ứng dụng Dynamics 365":::

1. <span data-ttu-id="9c715-164">Sau khi bắt đầu quá trình nâng cấp, bạn sẽ thấy chỉ báo tải cho đến khi quá trình nâng cấp hoàn tất.</span><span class="sxs-lookup"><span data-stu-id="9c715-164">After starting the upgrade process, you'll see a loading indicator until the upgrade completes.</span></span> <span data-ttu-id="9c715-165">Nếu không có phiên bản mới hơn, bản nâng cấp sẽ hiển thị thông báo lỗi.</span><span class="sxs-lookup"><span data-stu-id="9c715-165">If there's no newer version, the upgrade will show an error message.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]