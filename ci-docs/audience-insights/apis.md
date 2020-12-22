---
title: Làm việc với API
description: Sử dụng API và hiểu các giới hạn.
ms.date: 12/04/2020
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 5a03e916676800afdd8692da865a1060952d5c4f
ms.sourcegitcommit: b50c754481d0af6d0cf4b550775d7b31d95846ef
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 12/06/2020
ms.locfileid: "4689156"
---
# <a name="work-with-customer-insights-apis"></a><span data-ttu-id="9c0be-103">Làm việc với API Customer Insights</span><span class="sxs-lookup"><span data-stu-id="9c0be-103">Work with Customer Insights APIs</span></span>

<span data-ttu-id="9c0be-104">Dynamics 365 Customer Insights cung cấp các API để tạo ứng dụng dựa trên dữ liệu của bạn trong Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="9c0be-104">Dynamics 365 Customer Insights provides APIs to build your own applications based you data in Customer Insights.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9c0be-105">Thông tin chi tiết về các API này được liệt kê trên [Tham chiếu API Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span><span class="sxs-lookup"><span data-stu-id="9c0be-105">Details of these APIs, are listed on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="9c0be-106">Những thông tin này bao gồm thông tin bổ sung về hoạt động, tham số và phản hồi.</span><span class="sxs-lookup"><span data-stu-id="9c0be-106">They include additional information about operations, parameters, and responses.</span></span>

<span data-ttu-id="9c0be-107">Bài viết này hướng dẫn bạn truy cập vào các API Customer Insights, tạo Đăng ký ứng dụng Azure và giúp bạn bắt đầu với các thư viện ứng dụng khách có sẵn.</span><span class="sxs-lookup"><span data-stu-id="9c0be-107">This article guides you to access to the Customer Insights APIs, create an Azure App Registration, and help you get started with the available client libraries.</span></span>

## <a name="get-started-trying-the-customer-insights-apis"></a><span data-ttu-id="9c0be-108">Bắt đầu dùng thử các API Customer Insights</span><span class="sxs-lookup"><span data-stu-id="9c0be-108">Get started trying the Customer Insights APIs</span></span>

1. <span data-ttu-id="9c0be-109">[Đăng nhập](https://home.ci.ai.dynamics.com) vào Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="9c0be-109">[Sign in](https://home.ci.ai.dynamics.com) to Customer Insights.</span></span> <span data-ttu-id="9c0be-110">Nếu bạn chưa có đăng ký, [hãy đăng ký phiên bản dùng thử của Customer Insights](https://aka.ms/tryci).</span><span class="sxs-lookup"><span data-stu-id="9c0be-110">If you don't have a subscription yet, [sign up for a trial of Customer Insights](https://aka.ms/tryci).</span></span>

1. <span data-ttu-id="9c0be-111">Để bật API trên môi trường Customer Insights của bạn, hãy truy cập **Quản trị viên** > **Quyền hạn**.</span><span class="sxs-lookup"><span data-stu-id="9c0be-111">To enable APIs on your Customer Insights environment, go to **Admin** > **Permissions**.</span></span> <span data-ttu-id="9c0be-112">Bạn sẽ cần quyền quản trị viên để làm như vậy.</span><span class="sxs-lookup"><span data-stu-id="9c0be-112">You'll need admin permissions to do so.</span></span>

1. <span data-ttu-id="9c0be-113">Đi đến **API** và chọn nút **Bật**.</span><span class="sxs-lookup"><span data-stu-id="9c0be-113">Go to the **APIs** tab and select the **Enable** button.</span></span>    
   <span data-ttu-id="9c0be-114">Việc bật API sẽ tạo khóa đăng ký chính và phụ cho phiên bản của bạn, khóa này được sử dụng trong các yêu cầu API.</span><span class="sxs-lookup"><span data-stu-id="9c0be-114">Enabling the APIs creates a primary and secondary subscription key for your instance that gets used in the API requests.</span></span> <span data-ttu-id="9c0be-115">Bạn có thể tạo lại các khóa bằng cách chọn **Tạo lại khóa chính** hoặc **Tạo lại khóa phụ** trên **Quản trị viên** > **Quyền** > **API**.</span><span class="sxs-lookup"><span data-stu-id="9c0be-115">You can regenerate the keys by selecting the **Regenerate primary** or **Regenerate secondary** on **Admin** > **Permissions** > **APIs**.</span></span>

   :::image type="content" source="media/enable-apis.gif" alt-text="Bật API Customer Insights":::

1. <span data-ttu-id="9c0be-117">Chọn **Khám phá API** để dùng thử các API.</span><span class="sxs-lookup"><span data-stu-id="9c0be-117">Select **Explore our APIs** to try out the APIs.</span></span>

1. <span data-ttu-id="9c0be-118">Chọn một hoạt động API và chọn **Dùng thử**.</span><span class="sxs-lookup"><span data-stu-id="9c0be-118">Choose an API operation and select **Try it**.</span></span>

1. <span data-ttu-id="9c0be-119">Trong ngăn bên, đặt giá trị trong menu thả xuống **Thẩm quyền** thành **ẩn**.</span><span class="sxs-lookup"><span data-stu-id="9c0be-119">In the side pane, set the value in the **Authorization** drop-down menu to **implicit**.</span></span> <span data-ttu-id="9c0be-120">Tiêu đề `Authorization` được thêm mã thông báo mang chuyển.</span><span class="sxs-lookup"><span data-stu-id="9c0be-120">The `Authorization` header gets with a bearer token added.</span></span> <span data-ttu-id="9c0be-121">Khóa đăng ký của bạn sẽ được tự động điền.</span><span class="sxs-lookup"><span data-stu-id="9c0be-121">Your subscription key will be automatically populated.</span></span>
  
1. <span data-ttu-id="9c0be-122">Theo tùy chọn, thêm tất cả các tham số truy vấn cần thiết.</span><span class="sxs-lookup"><span data-stu-id="9c0be-122">Optionally, add all necessary query parameters.</span></span>

1. <span data-ttu-id="9c0be-123">Cuộn xuống cuối ngăn bên và chọn **Gửi**.</span><span class="sxs-lookup"><span data-stu-id="9c0be-123">Scroll to the bottom of the side pane and select **Send**.</span></span>

<span data-ttu-id="9c0be-124">Phản hồi HTTP sẽ sớm xuất hiện bên dưới.</span><span class="sxs-lookup"><span data-stu-id="9c0be-124">The HTTP response will soon appear below.</span></span>

## <a name="create-a-new-app-registration-in-the-azure-portal"></a><span data-ttu-id="9c0be-125">Tạo đăng ký ứng dụng mới trong cổng thông tin Azure</span><span class="sxs-lookup"><span data-stu-id="9c0be-125">Create a new app registration in the Azure portal</span></span>

<span data-ttu-id="9c0be-126">Các bước này giúp bạn bắt đầu sử dụng API Customer Insights trong ứng dụng Azure bằng các quyền được ủy quyền.</span><span class="sxs-lookup"><span data-stu-id="9c0be-126">These steps help you get started in using the Customer Insights APIs in an Azure application using delegated permissions.</span></span> <span data-ttu-id="9c0be-127">Đảm bảo đã hoàn thành [Phần bắt đầu](#get-started-trying-the-customer-insights-apis) trước tiên.</span><span class="sxs-lookup"><span data-stu-id="9c0be-127">Make sure to have completed [Getting started section](#get-started-trying-the-customer-insights-apis) first.</span></span>

1. <span data-ttu-id="9c0be-128">Đăng nhập vào [Cổng thông tin Azure](https://portal.azure.com) bằng tài khoản có thể truy cập dữ liệu Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="9c0be-128">Sign in to the [Azure portal](https://portal.azure.com) with the account that can access the Customer Insights data.</span></span>

1. <span data-ttu-id="9c0be-129">Ở bên trái, hãy chọn **Đăng ký ứng dụng**.</span><span class="sxs-lookup"><span data-stu-id="9c0be-129">On the left, select **App registrations**.</span></span>

1. <span data-ttu-id="9c0be-130">Chọn **Đăng ký mới** sẽ cung cấp tên ứng dụng và chọn loại tài khoản.</span><span class="sxs-lookup"><span data-stu-id="9c0be-130">Select **New registration** provide an application name and choose the account type.</span></span>
   <span data-ttu-id="9c0be-131">Theo tùy chọn, thêm URL chuyển hướng.</span><span class="sxs-lookup"><span data-stu-id="9c0be-131">Optionally, add a redirect URL.</span></span> <span data-ttu-id="9c0be-132">http://localhost là đủ để phát triển một ứng dụng trên máy tính cục bộ của bạn.</span><span class="sxs-lookup"><span data-stu-id="9c0be-132">http://localhost is sufficient for developing an application on your local computer.</span></span>

1. <span data-ttu-id="9c0be-133">Trên đăng ký ứng dụng mới, hãy đi tới **Quyền API**.</span><span class="sxs-lookup"><span data-stu-id="9c0be-133">On your new App registration, go to **API permissions**.</span></span>

1. <span data-ttu-id="9c0be-134">Chọn **Thêm quyền** và chọn **Customer Insights** trong ngăn bên.</span><span class="sxs-lookup"><span data-stu-id="9c0be-134">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="9c0be-135">Đối với **Loại quyền**, hãy chọn **Quyền được ủy quyền** và chọn quyền **user_impersonation**.</span><span class="sxs-lookup"><span data-stu-id="9c0be-135">For **Permission type**, select **Delegated permissions** and select the **user_impersonation** permission.</span></span>

1. <span data-ttu-id="9c0be-136">Chọn **Thêm quyền**.</span><span class="sxs-lookup"><span data-stu-id="9c0be-136">Select **Add permissions**.</span></span> <span data-ttu-id="9c0be-137">Nếu bạn cần truy cập API mà không cần người dùng đăng nhập, hãy xem lại phần [Quyền của ứng dụng giữa các máy chủ](#server-to-server-application-permissions).</span><span class="sxs-lookup"><span data-stu-id="9c0be-137">If you need to access the API without a user signing in, review the [Server-to-server application permissions](#server-to-server-application-permissions) section.</span></span>

1. <span data-ttu-id="9c0be-138">Chọn **Cấp quyền của quản trị viên cho...** để hoàn thành đăng ký ứng dụng.</span><span class="sxs-lookup"><span data-stu-id="9c0be-138">Select **Grant admin consent for...** to complete the app registration.</span></span>

<span data-ttu-id="9c0be-139">Bạn có thể sử dụng ID ứng dụng/máy khách cho đăng ký ứng dụng này với Microsoft Authentication Library (MSAL) để nhận mã thông báo mang chuyển để gửi kèm theo yêu cầu của bạn đến API.</span><span class="sxs-lookup"><span data-stu-id="9c0be-139">You can use the Application/Client ID for this app registration with the Microsoft Authentication Library (MSAL) to obtain a bearer token to send with your request to the API.</span></span>

<span data-ttu-id="9c0be-140">Để biết thêm thông tin về MSAL, hãy xem [Tổng quan về Microsoft Authentication Library (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview).</span><span class="sxs-lookup"><span data-stu-id="9c0be-140">For more information about MSAL, see [Overview of Microsoft Authentication Library (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview).</span></span>

<span data-ttu-id="9c0be-141">Để biết thêm thông tin về đăng ký ứng dụng trong Azure, hãy xem [Trải nghiệm đăng ký ứng dụng cổng Azure mới](https://docs.microsoft.com/azure/active-directory/develop/app-registration-portal-training-guide).</span><span class="sxs-lookup"><span data-stu-id="9c0be-141">For more information about app registration in Azure, see [The new Azure portal app registration experience](https://docs.microsoft.com/azure/active-directory/develop/app-registration-portal-training-guide).</span></span>

<span data-ttu-id="9c0be-142">Để biết thông tin về cách sử dụng API thư viện máy khách của chúng tôi, hãy xem [Thư viện máy khách Customer Insights](#customer-insights-client-libraries).</span><span class="sxs-lookup"><span data-stu-id="9c0be-142">For information on using the APIs our client libraries, see [Customer Insights client libraries](#customer-insights-client-libraries).</span></span>

### <a name="server-to-server-application-permissions"></a><span data-ttu-id="9c0be-143">Quyền của ứng dụng giữa các máy chủ</span><span class="sxs-lookup"><span data-stu-id="9c0be-143">Server-to-server application permissions</span></span>

<span data-ttu-id="9c0be-144">[Phần đăng ký ứng dụng](#create-a-new-app-registration-in-the-azure-portal) cho biết cách đăng ký ứng dụng cần người dùng đăng nhập để xác thực.</span><span class="sxs-lookup"><span data-stu-id="9c0be-144">The [app registration section](#create-a-new-app-registration-in-the-azure-portal) outlines how to register an app that requires a user to sign in for authentication.</span></span> <span data-ttu-id="9c0be-145">Tìm hiểu cách tạo đăng ký ứng dụng không cần người dùng tương tác và có thể chạy trên máy chủ.</span><span class="sxs-lookup"><span data-stu-id="9c0be-145">Learn how to create an app registration that does not need user interaction and can be run on a server.</span></span>

1. <span data-ttu-id="9c0be-146">Khi đăng ký ứng dụng của bạn trong cổng Azure, hãy đi tới **Quyền API**.</span><span class="sxs-lookup"><span data-stu-id="9c0be-146">On your App registration in the Azure portal, go to **API permissions**.</span></span>

1. <span data-ttu-id="9c0be-147">Chọn **Thêm quyền** và chọn **Customer Insights** trong ngăn bên.</span><span class="sxs-lookup"><span data-stu-id="9c0be-147">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="9c0be-148">Đối với **Loại quyền**, hãy chọn **Quyền của ứng dụng** và chọn quyền **CustomerInsights.Api.All**.</span><span class="sxs-lookup"><span data-stu-id="9c0be-148">For **Permission type**, select **Application permissions** and select the **CustomerInsights.Api.All** permission.</span></span>

1. <span data-ttu-id="9c0be-149">Chọn **Thêm quyền**.</span><span class="sxs-lookup"><span data-stu-id="9c0be-149">Select **Add permissions**.</span></span>

1. <span data-ttu-id="9c0be-150">Để cung cấp sự đồng ý của quản trị viên đối với quyền của ứng dụng này, bạn cần thêm Tên dịch vụ chính.</span><span class="sxs-lookup"><span data-stu-id="9c0be-150">To give admin consent on this Application permission, you need to add a Service Principal.</span></span>

   1. <span data-ttu-id="9c0be-151">Cài đặt mô-đun Azure Active Directory (AD) PowerShell: `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`</span><span class="sxs-lookup"><span data-stu-id="9c0be-151">Install the Azure Active Directory (AD) PowerShell module: `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`</span></span>
   1. <span data-ttu-id="9c0be-152">Kết nối với tài khoản AD: `Connect-AzureAD -TenantId <your tenant id>`.</span><span class="sxs-lookup"><span data-stu-id="9c0be-152">Connect to your AD account: `Connect-AzureAD -TenantId <your tenant id>`.</span></span> <span data-ttu-id="9c0be-153">Bạn có thể tìm thấy ID đối tượng thuê của mình trên **Tổng quan** > **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="9c0be-153">You can find your tenant ID on **Overview** > **Azure Active Directory**.</span></span>
   1. <span data-ttu-id="9c0be-154">Chạy lệnh sau để thêm Tên dịch vụ chính Azure AD: `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` Tham số AppId gắn liền với ứng dụng API Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="9c0be-154">Run the following command to add an Azure AD Service Principal: `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` The AppId parameter pertains to the Customer Insights API app.</span></span>

   :::image type="content" source="media/azureAD-service-principal.png" alt-text="Mẫu tên dịch vụ chính":::

1. <span data-ttu-id="9c0be-156">Quay lại **Quyền API** cho đăng ký ứng dụng của bạn.</span><span class="sxs-lookup"><span data-stu-id="9c0be-156">Go back to **API permissions** for your app registration.</span></span>

1. <span data-ttu-id="9c0be-157">Chọn **Cấp quyền của quản trị viên cho...** để hoàn thành đăng ký ứng dụng.</span><span class="sxs-lookup"><span data-stu-id="9c0be-157">Select **Grant admin consent for...** to complete the app registration.</span></span>

1. <span data-ttu-id="9c0be-158">Để kết thúc, chúng tôi phải thêm tên đăng ký ứng dụng làm người dùng trong Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="9c0be-158">To conclude, we have to add the name of the app registration as a user in Customer Insights.</span></span>    
   <span data-ttu-id="9c0be-159">Mở Customer Insights, đi tới **Quản trị viên** > **Quyền** và chọn **Thêm người dùng**.</span><span class="sxs-lookup"><span data-stu-id="9c0be-159">Open Customer Insights, go to **Admin** > **Permissions** and select **Add user**.</span></span>

1. <span data-ttu-id="9c0be-160">Tìm kiếm tên đăng ký ứng dụng của bạn, chọn tên đó từ kết quả tìm kiếm và chọn **Lưu**.</span><span class="sxs-lookup"><span data-stu-id="9c0be-160">Search for the name of your app registration, select it from the search results, and select **Save**.</span></span>

## <a name="customer-insights-client-libraries"></a><span data-ttu-id="9c0be-161">Thư viện máy khách Customer Insights</span><span class="sxs-lookup"><span data-stu-id="9c0be-161">Customer Insights client libraries</span></span>

<span data-ttu-id="9c0be-162">Phần này giúp bạn bắt đầu sử dụng các thư viện máy khách có sẵn cho các API Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="9c0be-162">This section helps you get started using the client libraries available for the Customer Insights APIs.</span></span>

### <a name="c-nuget"></a><span data-ttu-id="9c0be-163">C# NuGet</span><span class="sxs-lookup"><span data-stu-id="9c0be-163">C# NuGet</span></span>

<span data-ttu-id="9c0be-164">Tìm hiểu cách bắt đầu sử dụng thư viện máy khách C# từ NuGet.org. Để biết thêm thông tin về gói NuGet, xem [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span><span class="sxs-lookup"><span data-stu-id="9c0be-164">Learn how to get started using the C# client libraries from NuGet.org. For more information on the NuGet package, see [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span></span> <span data-ttu-id="9c0be-165">Hiện tại, gói này dành cho framework netstandard2.0 và netcoreapp2.0.</span><span class="sxs-lookup"><span data-stu-id="9c0be-165">Currently, this package targets the netstandard2.0 and netcoreapp2.0 frameworks.</span></span>

#### <a name="add-the-c-client-library-to-a-c-project"></a><span data-ttu-id="9c0be-166">Thêm thư viện máy khách C# vào dự án C#</span><span class="sxs-lookup"><span data-stu-id="9c0be-166">Add the C# client library to a C# project</span></span>

1. <span data-ttu-id="9c0be-167">Trong Visual Studio, mở **Trình quản lý gói NuGet** cho dự án của bạn.</span><span class="sxs-lookup"><span data-stu-id="9c0be-167">In Visual Studio, open the **NuGet Package Manager** for your project.</span></span>

1. <span data-ttu-id="9c0be-168">Tìm kiếm **Microsoft.Dynamics.CustomerInsights.Api**.</span><span class="sxs-lookup"><span data-stu-id="9c0be-168">Search for **Microsoft.Dynamics.CustomerInsights.Api**.</span></span>

1. <span data-ttu-id="9c0be-169">Chọn **Cài đặt** để thêm gói vào dự án.</span><span class="sxs-lookup"><span data-stu-id="9c0be-169">Select **Install** to add the package to the project.</span></span>
   <span data-ttu-id="9c0be-170">Ngoài ra, hãy chạy lệnh này trong **Bảng điều khiển trình quản lý gói NuGet**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span><span class="sxs-lookup"><span data-stu-id="9c0be-170">Alternatively, run this command in the **NuGet Package Manager Console**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span></span>

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Thêm gói NuGet vào dự án Visual Studio":::

#### <a name="use-the-c-client-library"></a><span data-ttu-id="9c0be-172">Sử dụng thư viện máy khách C#</span><span class="sxs-lookup"><span data-stu-id="9c0be-172">Use the C# client library</span></span>

1. <span data-ttu-id="9c0be-173">Sử dụng [Microsoft Authentication Library (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview) để nhận `AccessToken` bằng cách sử dụng [đăng ký ứng dụng Azure](#create-a-new-app-registration-in-the-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="9c0be-173">Use the [Microsoft Authentication Library (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview) to get an `AccessToken` using your existing [Azure app registration](#create-a-new-app-registration-in-the-azure-portal).</span></span>

1. <span data-ttu-id="9c0be-174">Sau khi xác thực thành công và có được mã thông báo, hãy tạo mã mới hoặc sử dụng `HttpClient` hiện tại với **DefaultRequestHeaders "Authorization"** bổ sung được đặt thành **<access token> mang chuyển** và **Ocp-Apim-Subscription-Key** được đặt thành [**khóa đăng ký** từ môi trường Customer Insights của bạn](#get-started-trying-the-customer-insights-apis).</span><span class="sxs-lookup"><span data-stu-id="9c0be-174">After successfully authenticating and acquiring a token, construct a new or use an existing `HttpClient` with the additional **DefaultRequestHeaders "Authorization"** set to **Bearer <access token>** and **Ocp-Apim-Subscription-Key** set to the [**subscription key** from your Customer Insights environment](#get-started-trying-the-customer-insights-apis).</span></span>    
   <span data-ttu-id="9c0be-175">Đặt lại tiêu đề **Ủy quyền** khi thích hợp.</span><span class="sxs-lookup"><span data-stu-id="9c0be-175">Reset the **Authorization** header when appropriate.</span></span> <span data-ttu-id="9c0be-176">Ví dụ: khi mã thông báo hết hạn.</span><span class="sxs-lookup"><span data-stu-id="9c0be-176">For example, when the token expired.</span></span>

1. <span data-ttu-id="9c0be-177">Chuyển `HttpClient` này vào việc xây dựng máy khách `CustomerInsights`.</span><span class="sxs-lookup"><span data-stu-id="9c0be-177">Pass this `HttpClient` into the construction of the `CustomerInsights` client.</span></span>

   :::image type="content" source="media/httpclient-sample.png" alt-text="Mẫu httpclient":::

1. <span data-ttu-id="9c0be-179">Thực hiện cuộc gọi với máy khách đến "phương pháp mở rộng", ví dụ: `GetAllInstancesAsync`.</span><span class="sxs-lookup"><span data-stu-id="9c0be-179">Make calls with the client to the "extension methods", for example, `GetAllInstancesAsync`.</span></span> <span data-ttu-id="9c0be-180">Nếu truy cập vào `Microsoft.Rest.HttpOperationResponse` cơ sở được ưu tiên, hãy sử dụng "phương thức thông báo http", ví dụ: `GetAllInstancesWithHttpMessagesAsync`.</span><span class="sxs-lookup"><span data-stu-id="9c0be-180">If access to the underlying `Microsoft.Rest.HttpOperationResponse` is preferred, use the "http message methods", for example `GetAllInstancesWithHttpMessagesAsync`.</span></span>

1. <span data-ttu-id="9c0be-181">Phản hồi sẽ có thể thuộc loại `object` vì phương thức này có thể trả về nhiều loại (ví dụ: `IList<InstanceInfo>` và `ApiErrorResult`).</span><span class="sxs-lookup"><span data-stu-id="9c0be-181">The response will likely be of type `object` because the method can return multiple types (for example, `IList<InstanceInfo>` and `ApiErrorResult`).</span></span> <span data-ttu-id="9c0be-182">Để kiểm tra loại trả về, bạn có thể truyền an toàn các đối tượng vào các loại phản hồi được chỉ định trên [Trang chi tiết API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) cho hoạt động đó.</span><span class="sxs-lookup"><span data-stu-id="9c0be-182">To check the return type, you can safely cast the objects into the response types specified on the [API details page](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) for that operation.</span></span>    
   <span data-ttu-id="9c0be-183">Nếu cần thêm thông tin về yêu cầu, hãy sử dụng **phương thức thông báo http** để truy cập đối tượng phản hồi thô.</span><span class="sxs-lookup"><span data-stu-id="9c0be-183">If more information on the request is needed, use the **http message methods** to access the raw response object.</span></span>
