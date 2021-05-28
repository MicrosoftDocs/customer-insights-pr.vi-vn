---
title: Bổ trợ thẻ khách hàng cho các ứng dụng Dynamics 365
description: Hiển thị dữ liệu từ thông tin chi tiết về khán giả trong ứng dụng Dynamics 365 với phần bổ trợ này.
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 88492943ddbf9ae30c64d92b261433b74f34f682
ms.sourcegitcommit: d74430270f1b754322287c4f045d7febdae35be2
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059614"
---
# <a name="customer-card-add-in-preview"></a><span data-ttu-id="430ec-103">Trình bổ sung thẻ khách hàng (xem trước)</span><span class="sxs-lookup"><span data-stu-id="430ec-103">Customer Card Add-in (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="430ec-104">Nhận thông tin toàn diện về khách hàng ngay trong ứng dụng Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="430ec-104">Get a 360-degree view of your customers directly in Dynamics 365 apps.</span></span> <span data-ttu-id="430ec-105">Với phần Bổ trợ thẻ khách hàng có trong ứng dụng Dynamics 365 được hỗ trợ, bạn có thể chọn hiển thị dữ liệu nhân khẩu học, thông tin chi tiết và tiến trình hoạt động.</span><span class="sxs-lookup"><span data-stu-id="430ec-105">With the Customer Card Add-in installed in a supported Dynamics 365 app you can choose to display demographics, insights, and activity timelines.</span></span> <span data-ttu-id="430ec-106">Phần bổ trợ sẽ truy xuất dữ liệu từ Customer Insights mà không ảnh hưởng đến dữ liệu trong ứng dụng Dynamics 365 được kết nối.</span><span class="sxs-lookup"><span data-stu-id="430ec-106">The add-in will retrieve data from Customer Insights without affecting the data in the connected Dynamics 365 app.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="430ec-107">Điều kiện tiên quyết</span><span class="sxs-lookup"><span data-stu-id="430ec-107">Prerequisites</span></span>

- <span data-ttu-id="430ec-108">Phần bổ trợ này chỉ hoạt động với các ứng dụng dựa trên mô hình Dynamics 365, chẳng hạn như ứng dụng Sales hoặc Customer Service, phiên bản 9.0 trở lên.</span><span class="sxs-lookup"><span data-stu-id="430ec-108">The add-in only works with Dynamics 365 model-driven apps, such as Sales or Customer Service, version 9.0 and later.</span></span>
- <span data-ttu-id="430ec-109">Để dữ liệu Dynamics 365 của bạn ánh xạ sang hồ sơ khách hàng trong thông tin chuyên sâu về đối tượng bắt buộc [nhập từ ứng dụng Dynamics 365 bằng cách sử dụng trình kết nối Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="430ec-109">For your Dynamics 365 data to map to the audience insights customer profiles they need to be [ingested from the Dynamics 365 app using the Common Data Service connector](connect-power-query.md).</span></span>
- <span data-ttu-id="430ec-110">Tất cả người dùng Dynamics 365 của phần Bổ trợ thẻ khách hàng phải [được thêm vào với tư cách là người dùng](permissions.md) trong thông tin chuyên sâu về đối tượng để xem dữ liệu.</span><span class="sxs-lookup"><span data-stu-id="430ec-110">All Dynamics 365 users of the Customer Card Add-in must be [added as users](permissions.md) in audience insights to see the data.</span></span>
- <span data-ttu-id="430ec-111">Cần có [các khả năng tìm kiếm và lọc đã định cấu hình](search-filter-index.md) trong thông tin chuyên sâu về đối tượng để tra cứu dữ liệu cho công việc.</span><span class="sxs-lookup"><span data-stu-id="430ec-111">[Configured search and filter capabilities](search-filter-index.md) in audience insights are required for lookup of data to work.</span></span>
- <span data-ttu-id="430ec-112">Các tính năng điều khiển bổ trợ đều dựa trên dữ liệu cụ thể trong phần thông tin chuyên sâu về đối tượng:</span><span class="sxs-lookup"><span data-stu-id="430ec-112">Each add-in control relies on specific data in audience insights:</span></span>
  - <span data-ttu-id="430ec-113">Kiểm soát đo lường: Yêu cầu [các biện pháp được đặt cấu hình](measures.md).</span><span class="sxs-lookup"><span data-stu-id="430ec-113">Measure control: Requires [configured measures](measures.md).</span></span>
  - <span data-ttu-id="430ec-114">Điều khiển thông minh: Bạn cần tạo dữ liệu bằng cách sử dụng phương thức [dự đoán](predictions.md) hoặc [mô hình tùy chỉnh](custom-models.md).</span><span class="sxs-lookup"><span data-stu-id="430ec-114">Intelligence control: Requires data generated using [predictions](predictions.md) or [custom models](custom-models.md).</span></span>
  - <span data-ttu-id="430ec-115">Kiểm soát nhân khẩu học: Các trường nhân khẩu học (chẳng hạn như tuổi hoặc giới tính) có sẵn trong hồ sơ khách hàng hợp nhất.</span><span class="sxs-lookup"><span data-stu-id="430ec-115">Demographic control: Demographic fields(such as age or gender) are available in the unified customer profile.</span></span>
  - <span data-ttu-id="430ec-116">Điều khiển tăng cường: Yêu cầu dữ liệu [tăng cường](enrichment-hub.md) hiện hoạt áp dụng cho hồ sơ khách hàng.</span><span class="sxs-lookup"><span data-stu-id="430ec-116">Enrichment control: Requires active [enrichments](enrichment-hub.md) applied to customer profiles.</span></span>
  - <span data-ttu-id="430ec-117">Kiểm soát dòng thời gian: Yêu cầu [các hoạt động được đặt cấu hình](activities.md).</span><span class="sxs-lookup"><span data-stu-id="430ec-117">Timeline control: Requires [configured activities](activities.md).</span></span>

## <a name="install-the-customer-card-add-in"></a><span data-ttu-id="430ec-118">Cài đặt phần bổ trợ Thẻ khách hàng</span><span class="sxs-lookup"><span data-stu-id="430ec-118">Install the Customer Card Add-in</span></span>

<span data-ttu-id="430ec-119">Phần bổ trợ Thẻ khách hàng là một giải pháp cho các ứng dụng gắn kết khách hàng trong Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="430ec-119">The Customer Card Add-in is a solution for customer engagement apps in Dynamics 365.</span></span> <span data-ttu-id="430ec-120">Để cài đặt giải pháp, hãy chuyển đến AppSource và tìm kiếm **Thẻ khách hàng Dynamics**.</span><span class="sxs-lookup"><span data-stu-id="430ec-120">To install the solution, go to AppSource and search for **Dynamics Customer Card**.</span></span> <span data-ttu-id="430ec-121">Chọn [Trình bổ sung thẻ khách hàng trên AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) và chọn **Tải ngay**.</span><span class="sxs-lookup"><span data-stu-id="430ec-121">Select the [Customer Card Add-in on AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) and select **Get It Now**.</span></span>

<span data-ttu-id="430ec-122">Bạn có thể cần phải đăng nhập bằng thông tin đăng nhập quản trị viên của mình cho ứng dụng Dynamics 365 để cài đặt giải pháp.</span><span class="sxs-lookup"><span data-stu-id="430ec-122">You may need to sign in with your admin credentials for the Dynamics 365 app to install the solution.</span></span>

<span data-ttu-id="430ec-123">Có thể mất một chút thời gian để cài đặt giải pháp vào môi trường của bạn.</span><span class="sxs-lookup"><span data-stu-id="430ec-123">It can take some time for the solution to be installed to your environment.</span></span>

## <a name="configure-the-customer-card-add-in"></a><span data-ttu-id="430ec-124">Đặt cấu hình Trình bổ trợ thẻ khách hàng</span><span class="sxs-lookup"><span data-stu-id="430ec-124">Configure the Customer Card Add-in</span></span>

1. <span data-ttu-id="430ec-125">Là quản trị viên, hãy đi tới phần **Cài đặt** trong ứng dụng hướng mô hình trong Dynamics 365 và chọn **Giải pháp**.</span><span class="sxs-lookup"><span data-stu-id="430ec-125">As an admin, go to the **Settings** section in Dynamics 365 and select **Solutions**.</span></span>

1. <span data-ttu-id="430ec-126">Chọn liên kết **Tên hiển thị** cho giải pháp Trình bổ trợ thẻ khách hàng **Dynamics 365 Customer Insights (Xem trước)**.</span><span class="sxs-lookup"><span data-stu-id="430ec-126">Select the **Display Name** link for the **Dynamics 365 Customer Insights Customer Card Add-in (Preview)** solution.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="430ec-127">![Chọn tên hiển thị](media/select-display-name.png "Chọn tên hiển thị")</span><span class="sxs-lookup"><span data-stu-id="430ec-127">![Select display name](media/select-display-name.png "Select display name")</span></span>

1. <span data-ttu-id="430ec-128">Chọn **Đăng nhập** và nhập thông tin xác thực cho tài khoản quản trị viên bạn sử dụng để đặt cấu hình Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="430ec-128">Select **Sign in** and enter the credentials for the admin account you use to configure Customer Insights.</span></span>

   > [!NOTE]
   > <span data-ttu-id="430ec-129">Kiểm tra để đảm bảo trình chặn cửa sổ bật lên trong trình duyệt không chặn cửa sổ xác thực khi bạn chọn nút **Đăng nhập**.</span><span class="sxs-lookup"><span data-stu-id="430ec-129">Check that the browser pop-up blocker does not block the authentication window when you select the **Sign in** button.</span></span>

1. <span data-ttu-id="430ec-130">Chọn môi trường Customer Insights bạn muốn lấy dữ liệu từ đó.</span><span class="sxs-lookup"><span data-stu-id="430ec-130">Select the Customer Insights environment you want to fetch data from.</span></span>

1. <span data-ttu-id="430ec-131">Xác định ánh xạ trường tới các bản ghi trong ứng dụng Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="430ec-131">Define the field mapping to records in the Dynamics 365 app.</span></span> <span data-ttu-id="430ec-132">Tùy thuộc vào dữ liệu của bạn trong Customer Insights, bạn có thể chọn ánh xạ các đối tượng sau:</span><span class="sxs-lookup"><span data-stu-id="430ec-132">Depending on your data in Customer Insights you can choose to map the following options:</span></span>
   - <span data-ttu-id="430ec-133">Để ánh xạ với một liên hệ, hãy chọn trường trong thực thể Khách hàng khớp với ID của thực thể liên hệ của bạn.</span><span class="sxs-lookup"><span data-stu-id="430ec-133">To map with a contact, select the field in the Customer entity that matches the ID of your contact entity.</span></span>
   - <span data-ttu-id="430ec-134">Để ánh xạ với một tài khoản, hãy chọn trường trong thực thể Khách hàng khớp với ID của thực thể tài khoản của bạn.</span><span class="sxs-lookup"><span data-stu-id="430ec-134">To map with an account, select the field in the Customer entity that matches the ID of your account entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="430ec-135">![Trường ID người liên hệ](media/contact-id-field.png "Trường ID người liên hệ")</span><span class="sxs-lookup"><span data-stu-id="430ec-135">![Contact ID field](media/contact-id-field.png "Contact ID field")</span></span>

1. <span data-ttu-id="430ec-136">Chọn **Lưu cấu hình** để lưu cài đặt.</span><span class="sxs-lookup"><span data-stu-id="430ec-136">Select **Save configuration** to save the settings.</span></span>

1. <span data-ttu-id="430ec-137">Tiếp theo, bạn cần chỉ định vai trò bảo mật trong Dynamics 365 để người dùng có thể tùy chỉnh và xem thẻ khách hàng.</span><span class="sxs-lookup"><span data-stu-id="430ec-137">Next, you need to assign security roles in Dynamics 365 so users can customize and see the customer card.</span></span> <span data-ttu-id="430ec-138">Trong Dynamics 365, hãy chuyển tới **Cài đặt** > **Bảo mật** > **Người dùng**.</span><span class="sxs-lookup"><span data-stu-id="430ec-138">In Dynamics 365, go to **Settings** > **Security** > **Users**.</span></span> <span data-ttu-id="430ec-139">Chọn người dùng để chỉnh sửa vai trò người dùng và chọn **Quản lý vai trò**.</span><span class="sxs-lookup"><span data-stu-id="430ec-139">Select the users to edit user roles and select **Manage roles**.</span></span>

1. <span data-ttu-id="430ec-140">Gán vai trò **Người tùy chỉnh thẻ Customer Insights** cho những người dùng sẽ tùy chỉnh nội dung hiển thị trên thẻ cho toàn bộ tổ chức.</span><span class="sxs-lookup"><span data-stu-id="430ec-140">Assign the **Customer Insights Card Customizer** role to users who will customize the content shown on the card for the whole organization.</span></span>

## <a name="add-customer-card-controls-to-forms"></a><span data-ttu-id="430ec-141">Thêm kiểm soát Thẻ khách hàng vào biểu mẫu</span><span class="sxs-lookup"><span data-stu-id="430ec-141">Add Customer Card controls to forms</span></span>
  
1. <span data-ttu-id="430ec-142">Để thêm các điều khiển Thẻ khách hàng vào biểu mẫu Liên hệ của bạn, hãy chuyển tới **Cài đặt** > **Tùy chỉnh** trong Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="430ec-142">To add the Customer Card controls to your Contact form, go to the **Settings** > **Customizations** in Dynamics 365.</span></span>

1. <span data-ttu-id="430ec-143">Chọn **Tùy chỉnh hệ thống**.</span><span class="sxs-lookup"><span data-stu-id="430ec-143">Select **Customize the System**.</span></span>

1. <span data-ttu-id="430ec-144">Duyệt đến thực thể **Người liên hệ**, mở rộng thực thể này rồi chọn **Biểu mẫu**.</span><span class="sxs-lookup"><span data-stu-id="430ec-144">Browse to the **Contact** entity, expand it and select **Forms**.</span></span>

1. <span data-ttu-id="430ec-145">Chọn biểu mẫu người liên hệ mà bạn muốn thêm điều khiển Thẻ khách hàng.</span><span class="sxs-lookup"><span data-stu-id="430ec-145">Select the contact form to which you want to add the Customer Card controls.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="430ec-146">![Chọn biểu mẫu người liên hệ](media/contact-active-forms.png "Chọn biểu mẫu người liên hệ")</span><span class="sxs-lookup"><span data-stu-id="430ec-146">![Select Contact form](media/contact-active-forms.png "Select Contact form")</span></span>

1. <span data-ttu-id="430ec-147">Để thêm một điều khiển, trong công cụ biên tập biểu mẫu, hãy kéo trường bất kỳ từ **Field Explorer** tới vị trí bạn muốn điều khiển xuất hiện.</span><span class="sxs-lookup"><span data-stu-id="430ec-147">To add a control, in the form editor, drag any field from the **Field Explorer** to where you want the control to appear.</span></span>

1. <span data-ttu-id="430ec-148">Chọn trường trên biểu mẫu mà bạn vừa thêm, sau đó chọn **Thay đổi thuộc tính**.</span><span class="sxs-lookup"><span data-stu-id="430ec-148">Select the field on the form that you just added, and select **Change Properties**.</span></span>

1. <span data-ttu-id="430ec-149">Truy cập tab **Kiểm soát** và chọn **Thêm kiểm soát**.</span><span class="sxs-lookup"><span data-stu-id="430ec-149">Go to the **Controls** tab and select **Add Control**.</span></span> <span data-ttu-id="430ec-150">Chọn một trong các điều khiển tùy chỉnh có sẵn và chọn **Thêm**.</span><span class="sxs-lookup"><span data-stu-id="430ec-150">Choose one of the available custom controls and select **Add**.</span></span>

1. <span data-ttu-id="430ec-151">Trong hộp thoại **Thuộc tính trường**, bỏ chọn hộp **Hiển thị nhãn trên biểu mẫu**.</span><span class="sxs-lookup"><span data-stu-id="430ec-151">In the **Field Properties** dialog, clear the **Display label on the form** check box.</span></span>

1. <span data-ttu-id="430ec-152">Chọn tùy chọn **Web** cho điều khiển.</span><span class="sxs-lookup"><span data-stu-id="430ec-152">Select the **Web** option for the control.</span></span> <span data-ttu-id="430ec-153">Đối với điều khiển Tăng cường, hãy chọn loại tăng cường mà bạn muốn hiển thị bằng cách định cấu hình trường **enrichmentType**.</span><span class="sxs-lookup"><span data-stu-id="430ec-153">For the Enrichment control, select which enrichment type you want to display by configuring the **enrichmentType** field.</span></span> <span data-ttu-id="430ec-154">Thêm điều khiển làm phong phú riêng biệt cho từng loại làm phong phú.</span><span class="sxs-lookup"><span data-stu-id="430ec-154">Add a separate enrichment control for each enrichment type.</span></span>

1. <span data-ttu-id="430ec-155">Chọn **Lưu** và **Xuất bản** để xuất bản biểu mẫu liên hệ đã cập nhật.</span><span class="sxs-lookup"><span data-stu-id="430ec-155">Select **Save** and **Publish** to publish the updated contact form.</span></span>

1. <span data-ttu-id="430ec-156">Chuyển đến biểu mẫu liên hệ đã phát hành.</span><span class="sxs-lookup"><span data-stu-id="430ec-156">Go to the published contact form.</span></span> <span data-ttu-id="430ec-157">Bạn sẽ thấy điều khiển mới được thêm vào.</span><span class="sxs-lookup"><span data-stu-id="430ec-157">You'll see the newly added control.</span></span> <span data-ttu-id="430ec-158">Bạn có thể cần phải đăng nhập trong lần đầu tiên bạn sử dụng.</span><span class="sxs-lookup"><span data-stu-id="430ec-158">You might need to sign in the first time you use it.</span></span>

1. <span data-ttu-id="430ec-159">Để tùy chỉnh nội dung bạn muốn hiển thị trên điều khiển tùy chỉnh, hãy chọn nút chỉnh sửa ở góc trên bên phải.</span><span class="sxs-lookup"><span data-stu-id="430ec-159">To customize what you want to show on the custom control, select the edit button in the upper-right corner.</span></span>

## <a name="upgrade-customer-card-add-in"></a><span data-ttu-id="430ec-160">Nâng cấp phần bổ trợ Thẻ Khách hàng</span><span class="sxs-lookup"><span data-stu-id="430ec-160">Upgrade Customer Card Add-in</span></span>
<span data-ttu-id="430ec-161">Phần bổ trợ Thẻ Khách hàng không tự động nâng cấp.</span><span class="sxs-lookup"><span data-stu-id="430ec-161">The Customer Card Add-in doesn't upgrade automatically.</span></span> <span data-ttu-id="430ec-162">Để nâng cấp lên phiên bản mới nhất, hãy làm theo quy trình này trong ứng dụng Dynamics 365 đã cài đặt Phần bổ trợ.</span><span class="sxs-lookup"><span data-stu-id="430ec-162">To upgrade to the latest version, follow this procedure in the Dynamics 365 app that has the Add-in installed.</span></span>

1. <span data-ttu-id="430ec-163">Trong ứng dụng Dynamics 365, hãy chuyển đến **Cài đặt** > **Tùy chỉnh** và chọn **Các giải pháp**.</span><span class="sxs-lookup"><span data-stu-id="430ec-163">In the Dynamics 365 app, go to **Settings** > **Customization** and select **Solutions**.</span></span>

1. <span data-ttu-id="430ec-164">Trong bảng phần bổ trợ, hãy tìm **CustomerInsightsCustomerCard** và chọn hàng.</span><span class="sxs-lookup"><span data-stu-id="430ec-164">In the table of add-ins look for **CustomerInsightsCustomerCard** and select the row.</span></span>

1. <span data-ttu-id="430ec-165">Chọn **Áp dụng nâng cấp giải pháp** trong thanh tác vụ.</span><span class="sxs-lookup"><span data-stu-id="430ec-165">Select the **Apply Solution Upgrade** in the action bar.</span></span>

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Nâng cấp giải pháp trong khu vực Tùy chỉnh của ứng dụng Dynamics 365":::

1. <span data-ttu-id="430ec-167">Sau khi bắt đầu quá trình nâng cấp, bạn sẽ thấy chỉ báo tải cho đến khi quá trình nâng cấp hoàn tất.</span><span class="sxs-lookup"><span data-stu-id="430ec-167">After starting the upgrade process, you'll see a loading indicator until the upgrade completes.</span></span> <span data-ttu-id="430ec-168">Nếu không có phiên bản mới hơn, bản nâng cấp sẽ hiển thị thông báo lỗi.</span><span class="sxs-lookup"><span data-stu-id="430ec-168">If there's no newer version, the upgrade will show an error message.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
