---
title: Kết nối với tài khoản Azure Data Lake Storage Gen2 có dịch vụ chính
description: sử dụng dịch vụ chính Azure cho thông tin chi tiết về đối tượng để kết nối với kho dữ liệu của riêng bạn khi đính kèm với thông tin chi tiết về đối tượng.
ms.date: 11/24/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: c2fae278d34fa02b9168ac70dfa8dd351653245e
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644114"
---
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a><span data-ttu-id="6c49c-103">Kết nối với tài khoản Azure Data Lake Storage Gen2 có dịch vụ chính Azure để biết thông tin chi tiết về đối tượng</span><span class="sxs-lookup"><span data-stu-id="6c49c-103">Connect to an Azure Data Lake Storage Gen2 account with an Azure service principal for audience insights</span></span>

<span data-ttu-id="6c49c-104">Các công cụ tự động sử dụng dịch vụ Azure luôn phải có các quyền hạn chế.</span><span class="sxs-lookup"><span data-stu-id="6c49c-104">Automated tools that use Azure services should always have restricted permissions.</span></span> <span data-ttu-id="6c49c-105">Thay vì để các ứng dụng đăng nhập với tư cách là người dùng có đầy đủ đặc quyền, Azure cung cấp các dịch vụ chính.</span><span class="sxs-lookup"><span data-stu-id="6c49c-105">Instead of having applications sign in as a fully privileged user, Azure offers service principals.</span></span> <span data-ttu-id="6c49c-106">Đọc tiếp để tìm hiểu cách kết nối thông tin chi tiết về đối tượng với tài khoản Azure Data Lake Storage Gen2 sử dụng dịch vụ chính Azure thay vì khóa tài khoản lưu trữ.</span><span class="sxs-lookup"><span data-stu-id="6c49c-106">Read on to learn how to connect audience insights with an Azure Data Lake Storage Gen2 account using an Azure service principal instead of storage account keys.</span></span> 

<span data-ttu-id="6c49c-107">Bạn có thể sử dụng dịch vụ chính để [thêm hoặc chỉnh sửa an toàn thư mục Common Data Model dưới dạng nguồn dữ liệu](connect-common-data-model.md) hoặc [tạo mới hoặc cập nhật môi trường hiện có](manage-environments.md#create-an-environment-in-an-existing-organization).</span><span class="sxs-lookup"><span data-stu-id="6c49c-107">You can use the service principal to securely [add or edit a Common Data Model folder as a data source](connect-common-data-model.md) or [create a new or update an existing environment](manage-environments.md#create-an-environment-in-an-existing-organization).</span></span>

<span data-ttu-id="6c49c-108">Bạn cần quyền quản trị cho đăng ký Azure của mình để tạo dịch vụ chính.</span><span class="sxs-lookup"><span data-stu-id="6c49c-108">You need admin permissions for your Azure subscription to create the service principal.</span></span>

## <a name="create-azure-service-principal-for-audience-insights"></a><span data-ttu-id="6c49c-109">Tạo dịch vụ chính Azure để có thông tin chi tiết về đối tượng</span><span class="sxs-lookup"><span data-stu-id="6c49c-109">Create Azure service principal for audience insights</span></span>

<span data-ttu-id="6c49c-110">Trước khi tạo một dịch vụ chính mới để có thông tin chi tiết về đối tượng, hãy kiểm tra xem dịch vụ đó đã tồn tại trong tổ chức của bạn chưa.</span><span class="sxs-lookup"><span data-stu-id="6c49c-110">Before creating a new service principal for audience insights, check if it already exists in your organization.</span></span>

### <a name="look-for-an-existing-service-principal"></a><span data-ttu-id="6c49c-111">Tìm một dịch vụ chính hiện có</span><span class="sxs-lookup"><span data-stu-id="6c49c-111">Look for an existing service principal</span></span>

1. <span data-ttu-id="6c49c-112">Đi tới [Cổng quản trị Azure](https://portal.azure.com) và đăng nhập vào tổ chức của bạn.</span><span class="sxs-lookup"><span data-stu-id="6c49c-112">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

2. <span data-ttu-id="6c49c-113">Chọn **Azure Active Directory** từ các dịch vụ Azure.</span><span class="sxs-lookup"><span data-stu-id="6c49c-113">Select **Azure Active Directory** from the Azure services.</span></span>

3. <span data-ttu-id="6c49c-114">Trong **Quản lý**, chọn **Ứng dụng doanh nghiệp**.</span><span class="sxs-lookup"><span data-stu-id="6c49c-114">Under **Manage**, select **Enterprise Applications**.</span></span>

4. <span data-ttu-id="6c49c-115">Tìm kiếm ID ứng dụng của bên thứ nhất thông tin chi tiết về đối tượng `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` hoặc tên `Dynamics 365 AI for Customer Insights`.</span><span class="sxs-lookup"><span data-stu-id="6c49c-115">Search for the audience insights first party application ID `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` or the name `Dynamics 365 AI for Customer Insights`.</span></span>

5. <span data-ttu-id="6c49c-116">Nếu bạn tìm thấy một bản ghi phù hợp, điều đó có nghĩa là dịch vụ chính cho thông tin chi tiết về đối tượng tồn tại.</span><span class="sxs-lookup"><span data-stu-id="6c49c-116">If you find a matching record, it means that the service principal for audience insights exists.</span></span> <span data-ttu-id="6c49c-117">Bạn không cần tạo lại dịch vụ chính.</span><span class="sxs-lookup"><span data-stu-id="6c49c-117">You don't need to create it again.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Ảnh chụp màn hình hiển thị dịch vụ chính hiện có.":::
   
6. <span data-ttu-id="6c49c-119">Nếu không có kết quả nào được trả lại, hãy tạo một dịch vụ chính mới.</span><span class="sxs-lookup"><span data-stu-id="6c49c-119">If no results are returned, create a new service principal.</span></span>

### <a name="create-a-new-service-principal"></a><span data-ttu-id="6c49c-120">Tạo dịch vụ chính mới</span><span class="sxs-lookup"><span data-stu-id="6c49c-120">Create a new service principal</span></span>

1. <span data-ttu-id="6c49c-121">Cài đặt phiên bản mới nhất của **Azure Active Directory PowerShell for Graph**.</span><span class="sxs-lookup"><span data-stu-id="6c49c-121">Install the latest version of the **Azure Active Directory PowerShell for Graph**.</span></span> <span data-ttu-id="6c49c-122">Để biết thêm thông tin, hãy xem [Cài đặt Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span><span class="sxs-lookup"><span data-stu-id="6c49c-122">For more information, see [Install Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span></span>
   - <span data-ttu-id="6c49c-123">Trên PC, chọn phím Windows trên bàn phím và tìm kiếm **Windows PowerShell** và **Chạy với tư cách quản trị viên**.</span><span class="sxs-lookup"><span data-stu-id="6c49c-123">On your PC, select the Windows key on your keyboard and search for **Windows PowerShell** and **Run as Administrator**.</span></span>
   
   - <span data-ttu-id="6c49c-124">Trong cửa sổ PowerShell mở ra, hãy nhập `Install-Module AzureAD`.</span><span class="sxs-lookup"><span data-stu-id="6c49c-124">In the PowerShell window that opens, enter `Install-Module AzureAD`.</span></span>

2. <span data-ttu-id="6c49c-125">Tạo dịch vụ chính cho thông tin chi tiết về đối tượng với mô-đun Azure AD PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6c49c-125">Create the  service principal for audience insights with the Azure AD PowerShell Module.</span></span>
   - <span data-ttu-id="6c49c-126">Trong cửa sổ PowerShell, hãy nhập `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span><span class="sxs-lookup"><span data-stu-id="6c49c-126">In the PowerShell window, enter `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span></span> <span data-ttu-id="6c49c-127">Thay thế “ID đối tượng thuê của bạn” bằng ID thực tế của đối tượng thuê mà bạn muốn tạo dịch vụ chính.</span><span class="sxs-lookup"><span data-stu-id="6c49c-127">Replace “your tenant ID” with the actual ID of your tenant where you want to create the service principal.</span></span> <span data-ttu-id="6c49c-128">Tham số tên môi trường `AzureEnvironmentName` là không bắt buộc.</span><span class="sxs-lookup"><span data-stu-id="6c49c-128">The environment name parameter `AzureEnvironmentName` is optional.</span></span>
  
   - <span data-ttu-id="6c49c-129">Nhập `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span><span class="sxs-lookup"><span data-stu-id="6c49c-129">Enter `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span></span> <span data-ttu-id="6c49c-130">Lệnh này tạo dịch vụ chính cho thông tin chi tiết về đối tượng trên đối tượng thuê đã chọn.</span><span class="sxs-lookup"><span data-stu-id="6c49c-130">This command creates the service principal for audience insights on the selected tenant.</span></span>  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a><span data-ttu-id="6c49c-131">Cấp quyền cho dịch vụ chính để truy cập vào tài khoản lưu trữ</span><span class="sxs-lookup"><span data-stu-id="6c49c-131">Grant permissions to the service principal to access the storage account</span></span>

<span data-ttu-id="6c49c-132">Truy cập cổng Azure để cấp quyền cho dịch vụ chính đối với tài khoản lưu trữ mà bạn muốn sử dụng trong thông tin chi tiết về đối tượng.</span><span class="sxs-lookup"><span data-stu-id="6c49c-132">Go to the Azure portal to grant permissions to the service principal for the storage account you want to use in audience insights.</span></span>

1. <span data-ttu-id="6c49c-133">Đi tới [Cổng quản trị Azure](https://portal.azure.com) và đăng nhập vào tổ chức của bạn.</span><span class="sxs-lookup"><span data-stu-id="6c49c-133">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

1. <span data-ttu-id="6c49c-134">Mở tài khoản lưu trữ mà bạn muốn dịch vụ chính cho thông tin chi tiết về đối tượng có quyền truy cập.</span><span class="sxs-lookup"><span data-stu-id="6c49c-134">Open the storage account you want the service principal for audience insights to have access to.</span></span>

1. <span data-ttu-id="6c49c-135">Chọn **Kiểm soát truy cập (IAM)** từ ngăn điều hướng và chọn **Thêm** > **Thêm gán vai trò**.</span><span class="sxs-lookup"><span data-stu-id="6c49c-135">Select **Access control (IAM)** from the navigation pane and select **Add** > **Add role assignment**.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Ảnh chụp màn hình hiển thị cổng Azure trong khi thêm gán vai trò.":::
   
1. <span data-ttu-id="6c49c-137">Trong ngăn **Thêm gán vai trò**, hãy đặt các thuộc tính sau:</span><span class="sxs-lookup"><span data-stu-id="6c49c-137">In the **Add role assignment** pane, set the following properties:</span></span>
   - <span data-ttu-id="6c49c-138">Vai trò: *Người đóng góp dữ liệu Storage Blob*</span><span class="sxs-lookup"><span data-stu-id="6c49c-138">Role: *Storage Blob Data Contributor*</span></span>
   - <span data-ttu-id="6c49c-139">Gán quyền truy cập cho: *Người dùng, nhóm hoặc dịch vụ chính*</span><span class="sxs-lookup"><span data-stu-id="6c49c-139">Assign access to: *User, group, or service principal*</span></span>
   - <span data-ttu-id="6c49c-140">Chọn: *Dynamics 365 AI cho Customer Insights* ([dịch vụ chính mà bạn đã tạo](#create-a-new-service-principal))</span><span class="sxs-lookup"><span data-stu-id="6c49c-140">Select: *Dynamics 365 AI for Customer Insights* (the [service principal you created](#create-a-new-service-principal))</span></span>

1.  <span data-ttu-id="6c49c-141">Chọn **Lưu**.</span><span class="sxs-lookup"><span data-stu-id="6c49c-141">Select **Save**.</span></span>

<span data-ttu-id="6c49c-142">Có thể mất đến 15 phút để các thay đổi được thực hiện.</span><span class="sxs-lookup"><span data-stu-id="6c49c-142">It can take up to 15 minutes to propagate the changes.</span></span>

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a><span data-ttu-id="6c49c-143">Nhập ID tài nguyên Azure hoặc chi tiết Đăng ký Azure trong tệp đính kèm tài khoản lưu trữ cho Audience Insights.</span><span class="sxs-lookup"><span data-stu-id="6c49c-143">Enter the Azure Resource ID or the Azure Subscription details in the storage account attachment to Audience Insights.</span></span>

<span data-ttu-id="6c49c-144">Đính kèm tài khoản lưu trữ Azure Data Lake trong thông tin chi tiết về đối tượng để [lưu trữ dữ liệu kết quả](manage-environments.md) hoặc [sử dụng làm nguồn dữ liệu](connect-common-data-service-lake.md).</span><span class="sxs-lookup"><span data-stu-id="6c49c-144">Attach an Azure Data Lake storage account in audience insights to [store output data](manage-environments.md) or [use it as a data source](connect-common-data-service-lake.md).</span></span> <span data-ttu-id="6c49c-145">Chọn tùy chọn Azure Data Lake cho phép bạn chọn giữa phương pháp dựa trên tài nguyên hoặc dựa trên đăng ký.</span><span class="sxs-lookup"><span data-stu-id="6c49c-145">Choosing the Azure Data Lake option lets you choose between a resource-based or a subscription-based based approach.</span></span>

<span data-ttu-id="6c49c-146">Thực hiện theo các bước dưới đây để cung cấp thông tin cần thiết về phương pháp đã chọn.</span><span class="sxs-lookup"><span data-stu-id="6c49c-146">Follow the below steps to provide the required information on the selected approach.</span></span>

### <a name="resounce-based-storage-account-connection"></a><span data-ttu-id="6c49c-147">Kết nối tài khoản lưu trữ dựa trên tài nguyên</span><span class="sxs-lookup"><span data-stu-id="6c49c-147">Resounce-based storage account connection</span></span>

1. <span data-ttu-id="6c49c-148">Đi tới [Cổng quản trị Azure](https://portal.azure.com), đăng nhập vào gói đăng ký của bạn và mở tài khoản lưu trữ.</span><span class="sxs-lookup"><span data-stu-id="6c49c-148">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="6c49c-149">Đi đến **Cài đặt** > **Thuộc tính** trên ngăn điều hướng.</span><span class="sxs-lookup"><span data-stu-id="6c49c-149">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="6c49c-150">Sao chép giá trị ID tài nguyên tài khoản lưu trữ.</span><span class="sxs-lookup"><span data-stu-id="6c49c-150">Copy the storage account resource ID value.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Sao chép ID tài nguyên tài khoản lưu trữ.":::

1. <span data-ttu-id="6c49c-152">Trong thông tin chi tiết về đối tượng, hãy chèn ID tài nguyên vào trường tài nguyên được hiển thị trong màn hình kết nối tài khoản lưu trữ.</span><span class="sxs-lookup"><span data-stu-id="6c49c-152">In audience insights, insert the resource ID in the resource field displayed in the storage account connection screen.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Nhập thông tin ID tài nguyên tài khoản lưu trữ.":::   
   
1. <span data-ttu-id="6c49c-154">Tiếp tục với các bước còn lại trong thông tin chi tiết về đối tượng để đính kèm tài khoản lưu trữ.</span><span class="sxs-lookup"><span data-stu-id="6c49c-154">Continue with the remaining steps in audience insights to attach the storage account.</span></span>

### <a name="subscription-based-storage-account-connection"></a><span data-ttu-id="6c49c-155">Kết nối tài khoản lưu trữ dựa trên đăng ký</span><span class="sxs-lookup"><span data-stu-id="6c49c-155">Subscription-based storage account connection</span></span>

1. <span data-ttu-id="6c49c-156">Đi tới [Cổng quản trị Azure](https://portal.azure.com), đăng nhập vào gói đăng ký của bạn và mở tài khoản lưu trữ.</span><span class="sxs-lookup"><span data-stu-id="6c49c-156">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="6c49c-157">Đi đến **Cài đặt** > **Thuộc tính** trên ngăn điều hướng.</span><span class="sxs-lookup"><span data-stu-id="6c49c-157">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="6c49c-158">Xem lại **Đăng ký**, **Nhóm tài nguyên** và **Tên** của tài khoản lưu trữ để đảm bảo bạn chọn đúng giá trị trong thông tin chi tiết về đối tượng.</span><span class="sxs-lookup"><span data-stu-id="6c49c-158">Review the **Subscription**, **Resource group**, and the **Name** of the storage account to make sure you select the right values in audience insights.</span></span>

1. <span data-ttu-id="6c49c-159">Trong thông tin chi tiết về đối tượng, hãy chọn giá trị hoặc cho các trường tương ứng khi đính kèm tài khoản lưu trữ.</span><span class="sxs-lookup"><span data-stu-id="6c49c-159">In audience insights, choose the values or for the corresponding fields when attaching the storage account.</span></span>

   :::image type="content" source="media/ADLS-SP-SubscriptionConnection.png" alt-text="Nhập thông tin ID tài nguyên tài khoản lưu trữ.":::
   
1. <span data-ttu-id="6c49c-161">Tiếp tục với các bước còn lại trong thông tin chi tiết về đối tượng để đính kèm tài khoản lưu trữ.</span><span class="sxs-lookup"><span data-stu-id="6c49c-161">Continue with the remaining steps in audience insights to attach the storage account.</span></span>
