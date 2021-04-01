---
title: Kết nối với tài khoản Azure Data Lake Storage Gen2 có dịch vụ chính
description: Dùng dịch vụ chính Azure cho thông tin chi tiết về đối tượng để kết nối với kho dữ liệu của riêng bạn khi đính kèm với thông tin chi tiết về đối tượng.
ms.date: 02/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: c670b0065a2833a6dc311d9e86d2b351140382ce
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596525"
---
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a><span data-ttu-id="22949-103">Kết nối với tài khoản Azure Data Lake Storage Gen2 có dịch vụ chính Azure để biết thông tin chi tiết về đối tượng</span><span class="sxs-lookup"><span data-stu-id="22949-103">Connect to an Azure Data Lake Storage Gen2 account with an Azure service principal for audience insights</span></span>

<span data-ttu-id="22949-104">Các công cụ tự động sử dụng dịch vụ Azure luôn phải có các quyền hạn chế.</span><span class="sxs-lookup"><span data-stu-id="22949-104">Automated tools that use Azure services should always have restricted permissions.</span></span> <span data-ttu-id="22949-105">Thay vì để các ứng dụng đăng nhập với tư cách là người dùng có đầy đủ đặc quyền, Azure cung cấp các dịch vụ chính.</span><span class="sxs-lookup"><span data-stu-id="22949-105">Instead of having applications sign in as a fully privileged user, Azure offers service principals.</span></span> <span data-ttu-id="22949-106">Đọc tiếp để tìm hiểu cách kết nối thông tin chi tiết về đối tượng với tài khoản Azure Data Lake Storage Gen2 sử dụng dịch vụ chính Azure thay vì khóa tài khoản lưu trữ.</span><span class="sxs-lookup"><span data-stu-id="22949-106">Read on to learn how to connect audience insights with an Azure Data Lake Storage Gen2 account using an Azure service principal instead of storage account keys.</span></span> 

<span data-ttu-id="22949-107">Bạn có thể sử dụng dịch vụ chính để [thêm hoặc chỉnh sửa an toàn thư mục Common Data Model dưới dạng nguồn dữ liệu](connect-common-data-model.md) hoặc [tạo mới hoặc cập nhật môi trường hiện có](manage-environments.md#create-an-environment-in-an-existing-organization).</span><span class="sxs-lookup"><span data-stu-id="22949-107">You can use the service principal to securely [add or edit a Common Data Model folder as a data source](connect-common-data-model.md) or [create a new or update an existing environment](manage-environments.md#create-an-environment-in-an-existing-organization).</span></span>

> [!IMPORTANT]
> - <span data-ttu-id="22949-108">Tài khoản lưu trữ Azure Data Lake thế hệ 2 dự định sử dụng dịch vụ chính phải [Đã bật Không gian Tên phân cấp (HNS)](/azure/storage/blobs/data-lake-storage-namespace).</span><span class="sxs-lookup"><span data-stu-id="22949-108">The Azure Data Lake Gen2 storage account that intends to use the service principal must have [Hierarchical Name Space (HNS) enabled](/azure/storage/blobs/data-lake-storage-namespace).</span></span>
> - <span data-ttu-id="22949-109">Bạn cần quyền quản trị cho đăng ký Azure của mình để tạo dịch vụ chính.</span><span class="sxs-lookup"><span data-stu-id="22949-109">You need admin permissions for your Azure subscription to create the service principal.</span></span>

## <a name="create-azure-service-principal-for-audience-insights"></a><span data-ttu-id="22949-110">Tạo dịch vụ chính Azure để có thông tin chi tiết về đối tượng</span><span class="sxs-lookup"><span data-stu-id="22949-110">Create Azure service principal for audience insights</span></span>

<span data-ttu-id="22949-111">Trước khi tạo một dịch vụ chính mới để có thông tin chi tiết về đối tượng, hãy kiểm tra xem dịch vụ đó đã tồn tại trong tổ chức của bạn chưa.</span><span class="sxs-lookup"><span data-stu-id="22949-111">Before creating a new service principal for audience insights, check if it already exists in your organization.</span></span>

### <a name="look-for-an-existing-service-principal"></a><span data-ttu-id="22949-112">Tìm một dịch vụ chính hiện có</span><span class="sxs-lookup"><span data-stu-id="22949-112">Look for an existing service principal</span></span>

1. <span data-ttu-id="22949-113">Đi tới [Cổng quản trị Azure](https://portal.azure.com) và đăng nhập vào tổ chức của bạn.</span><span class="sxs-lookup"><span data-stu-id="22949-113">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

2. <span data-ttu-id="22949-114">Chọn **Azure Active Directory** từ các dịch vụ Azure.</span><span class="sxs-lookup"><span data-stu-id="22949-114">Select **Azure Active Directory** from the Azure services.</span></span>

3. <span data-ttu-id="22949-115">Trong **Quản lý**, chọn **Ứng dụng doanh nghiệp**.</span><span class="sxs-lookup"><span data-stu-id="22949-115">Under **Manage**, select **Enterprise Applications**.</span></span>

4. <span data-ttu-id="22949-116">Tìm kiếm ID ứng dụng của bên thứ nhất thông tin chi tiết về đối tượng `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` hoặc tên `Dynamics 365 AI for Customer Insights`.</span><span class="sxs-lookup"><span data-stu-id="22949-116">Search for the audience insights first party application ID `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` or the name `Dynamics 365 AI for Customer Insights`.</span></span>

5. <span data-ttu-id="22949-117">Nếu bạn tìm thấy một bản ghi phù hợp, điều đó có nghĩa là dịch vụ chính cho thông tin chi tiết về đối tượng tồn tại.</span><span class="sxs-lookup"><span data-stu-id="22949-117">If you find a matching record, it means that the service principal for audience insights exists.</span></span> <span data-ttu-id="22949-118">Bạn không cần tạo lại dịch vụ chính.</span><span class="sxs-lookup"><span data-stu-id="22949-118">You don't need to create it again.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Ảnh chụp màn hình hiển thị dịch vụ chính hiện có.":::
   
6. <span data-ttu-id="22949-120">Nếu không có kết quả nào được trả lại, hãy tạo một dịch vụ chính mới.</span><span class="sxs-lookup"><span data-stu-id="22949-120">If no results are returned, create a new service principal.</span></span>

### <a name="create-a-new-service-principal"></a><span data-ttu-id="22949-121">Tạo dịch vụ chính mới</span><span class="sxs-lookup"><span data-stu-id="22949-121">Create a new service principal</span></span>

1. <span data-ttu-id="22949-122">Cài đặt phiên bản mới nhất của **Azure Active Directory PowerShell for Graph**.</span><span class="sxs-lookup"><span data-stu-id="22949-122">Install the latest version of the **Azure Active Directory PowerShell for Graph**.</span></span> <span data-ttu-id="22949-123">Để biết thêm thông tin, hãy xem [Cài đặt Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).</span><span class="sxs-lookup"><span data-stu-id="22949-123">For more information, see [Install Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).</span></span>
   - <span data-ttu-id="22949-124">Trên PC, chọn phím Windows trên bàn phím và tìm kiếm **Windows PowerShell** và **Chạy với tư cách quản trị viên**.</span><span class="sxs-lookup"><span data-stu-id="22949-124">On your PC, select the Windows key on your keyboard and search for **Windows PowerShell** and **Run as Administrator**.</span></span>
   
   - <span data-ttu-id="22949-125">Trong cửa sổ PowerShell mở ra, hãy nhập `Install-Module AzureAD`.</span><span class="sxs-lookup"><span data-stu-id="22949-125">In the PowerShell window that opens, enter `Install-Module AzureAD`.</span></span>

2. <span data-ttu-id="22949-126">Tạo dịch vụ chính cho thông tin chi tiết về đối tượng với mô-đun Azure AD PowerShell.</span><span class="sxs-lookup"><span data-stu-id="22949-126">Create the  service principal for audience insights with the Azure AD PowerShell Module.</span></span>
   - <span data-ttu-id="22949-127">Trong cửa sổ PowerShell, hãy nhập `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span><span class="sxs-lookup"><span data-stu-id="22949-127">In the PowerShell window, enter `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span></span> <span data-ttu-id="22949-128">Thay thế “ID đối tượng thuê của bạn” bằng ID thực tế của đối tượng thuê mà bạn muốn tạo dịch vụ chính.</span><span class="sxs-lookup"><span data-stu-id="22949-128">Replace “your tenant ID” with the actual ID of your tenant where you want to create the service principal.</span></span> <span data-ttu-id="22949-129">Tham số tên môi trường `AzureEnvironmentName` là không bắt buộc.</span><span class="sxs-lookup"><span data-stu-id="22949-129">The environment name parameter `AzureEnvironmentName` is optional.</span></span>
  
   - <span data-ttu-id="22949-130">Nhập `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span><span class="sxs-lookup"><span data-stu-id="22949-130">Enter `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span></span> <span data-ttu-id="22949-131">Lệnh này tạo dịch vụ chính cho thông tin chi tiết về đối tượng trên đối tượng thuê đã chọn.</span><span class="sxs-lookup"><span data-stu-id="22949-131">This command creates the service principal for audience insights on the selected tenant.</span></span>  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a><span data-ttu-id="22949-132">Cấp quyền cho dịch vụ chính để truy cập vào tài khoản lưu trữ</span><span class="sxs-lookup"><span data-stu-id="22949-132">Grant permissions to the service principal to access the storage account</span></span>

<span data-ttu-id="22949-133">Truy cập cổng Azure để cấp quyền cho dịch vụ chính đối với tài khoản lưu trữ mà bạn muốn sử dụng trong thông tin chi tiết về đối tượng.</span><span class="sxs-lookup"><span data-stu-id="22949-133">Go to the Azure portal to grant permissions to the service principal for the storage account you want to use in audience insights.</span></span>

1. <span data-ttu-id="22949-134">Đi tới [Cổng quản trị Azure](https://portal.azure.com) và đăng nhập vào tổ chức của bạn.</span><span class="sxs-lookup"><span data-stu-id="22949-134">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

1. <span data-ttu-id="22949-135">Mở tài khoản lưu trữ mà bạn muốn dịch vụ chính cho thông tin chi tiết về đối tượng có quyền truy cập.</span><span class="sxs-lookup"><span data-stu-id="22949-135">Open the storage account you want the service principal for audience insights to have access to.</span></span>

1. <span data-ttu-id="22949-136">Chọn **Kiểm soát truy cập (IAM)** từ ngăn điều hướng và chọn **Thêm** > **Thêm gán vai trò**.</span><span class="sxs-lookup"><span data-stu-id="22949-136">Select **Access control (IAM)** from the navigation pane and select **Add** > **Add role assignment**.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Ảnh chụp màn hình hiển thị cổng Azure trong khi thêm gán vai trò.":::
   
1. <span data-ttu-id="22949-138">Trong ngăn **Thêm gán vai trò**, hãy đặt các thuộc tính sau:</span><span class="sxs-lookup"><span data-stu-id="22949-138">In the **Add role assignment** pane, set the following properties:</span></span>
   - <span data-ttu-id="22949-139">Vai trò: *Người đóng góp dữ liệu Storage Blob*</span><span class="sxs-lookup"><span data-stu-id="22949-139">Role: *Storage Blob Data Contributor*</span></span>
   - <span data-ttu-id="22949-140">Gán quyền truy cập cho: *Người dùng, nhóm hoặc dịch vụ chính*</span><span class="sxs-lookup"><span data-stu-id="22949-140">Assign access to: *User, group, or service principal*</span></span>
   - <span data-ttu-id="22949-141">Chọn: *Dynamics 365 AI cho Customer Insights* ([dịch vụ chính mà bạn đã tạo](#create-a-new-service-principal))</span><span class="sxs-lookup"><span data-stu-id="22949-141">Select: *Dynamics 365 AI for Customer Insights* (the [service principal you created](#create-a-new-service-principal))</span></span>

1.  <span data-ttu-id="22949-142">Chọn **Lưu**.</span><span class="sxs-lookup"><span data-stu-id="22949-142">Select **Save**.</span></span>

<span data-ttu-id="22949-143">Có thể mất đến 15 phút để các thay đổi được thực hiện.</span><span class="sxs-lookup"><span data-stu-id="22949-143">It can take up to 15 minutes to propagate the changes.</span></span>

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a><span data-ttu-id="22949-144">Nhập ID tài nguyên Azure hoặc chi tiết Đăng ký Azure trong tệp đính kèm tài khoản lưu trữ cho Audience Insights.</span><span class="sxs-lookup"><span data-stu-id="22949-144">Enter the Azure Resource ID or the Azure Subscription details in the storage account attachment to Audience Insights.</span></span>

<span data-ttu-id="22949-145">Đính kèm tài khoản lưu trữ Azure Data Lake trong thông tin chi tiết về đối tượng để [lưu trữ dữ liệu kết quả](manage-environments.md) hoặc [sử dụng làm nguồn dữ liệu](connect-common-data-service-lake.md).</span><span class="sxs-lookup"><span data-stu-id="22949-145">Attach an Azure Data Lake storage account in audience insights to [store output data](manage-environments.md) or [use it as a data source](connect-common-data-service-lake.md).</span></span> <span data-ttu-id="22949-146">Chọn tùy chọn Azure Data Lake cho phép bạn chọn giữa phương pháp dựa trên tài nguyên hoặc dựa trên đăng ký.</span><span class="sxs-lookup"><span data-stu-id="22949-146">Choosing the Azure Data Lake option lets you choose between a resource-based or a subscription-based based approach.</span></span>

<span data-ttu-id="22949-147">Thực hiện theo các bước dưới đây để cung cấp thông tin cần thiết về phương pháp đã chọn.</span><span class="sxs-lookup"><span data-stu-id="22949-147">Follow the below steps to provide the required information on the selected approach.</span></span>

### <a name="resource-based-storage-account-connection"></a><span data-ttu-id="22949-148">Kết nối tài khoản lưu trữ dựa trên tài nguyên</span><span class="sxs-lookup"><span data-stu-id="22949-148">Resource-based storage account connection</span></span>

1. <span data-ttu-id="22949-149">Đi tới [Cổng quản trị Azure](https://portal.azure.com), đăng nhập vào gói đăng ký của bạn và mở tài khoản lưu trữ.</span><span class="sxs-lookup"><span data-stu-id="22949-149">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="22949-150">Đi đến **Cài đặt** > **Thuộc tính** trên ngăn điều hướng.</span><span class="sxs-lookup"><span data-stu-id="22949-150">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="22949-151">Sao chép giá trị ID tài nguyên tài khoản lưu trữ.</span><span class="sxs-lookup"><span data-stu-id="22949-151">Copy the storage account resource ID value.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Sao chép ID tài nguyên tài khoản lưu trữ.":::

1. <span data-ttu-id="22949-153">Trong thông tin chi tiết về đối tượng, hãy chèn ID tài nguyên vào trường tài nguyên được hiển thị trong màn hình kết nối tài khoản lưu trữ.</span><span class="sxs-lookup"><span data-stu-id="22949-153">In audience insights, insert the resource ID in the resource field displayed in the storage account connection screen.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Nhập thông tin ID tài nguyên tài khoản lưu trữ.":::   
   
1. <span data-ttu-id="22949-155">Tiếp tục với các bước còn lại trong thông tin chi tiết về đối tượng để đính kèm tài khoản lưu trữ.</span><span class="sxs-lookup"><span data-stu-id="22949-155">Continue with the remaining steps in audience insights to attach the storage account.</span></span>

### <a name="subscription-based-storage-account-connection"></a><span data-ttu-id="22949-156">Kết nối tài khoản lưu trữ dựa trên đăng ký</span><span class="sxs-lookup"><span data-stu-id="22949-156">Subscription-based storage account connection</span></span>

1. <span data-ttu-id="22949-157">Đi tới [Cổng quản trị Azure](https://portal.azure.com), đăng nhập vào gói đăng ký của bạn và mở tài khoản lưu trữ.</span><span class="sxs-lookup"><span data-stu-id="22949-157">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="22949-158">Đi đến **Cài đặt** > **Thuộc tính** trên ngăn điều hướng.</span><span class="sxs-lookup"><span data-stu-id="22949-158">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="22949-159">Xem lại **Đăng ký**, **Nhóm tài nguyên** và **Tên** của tài khoản lưu trữ để đảm bảo bạn chọn đúng giá trị trong thông tin chi tiết về đối tượng.</span><span class="sxs-lookup"><span data-stu-id="22949-159">Review the **Subscription**, **Resource group**, and the **Name** of the storage account to make sure you select the right values in audience insights.</span></span>

1. <span data-ttu-id="22949-160">Trong thông tin chi tiết về đối tượng, hãy chọn giá trị hoặc cho các trường tương ứng khi đính kèm tài khoản lưu trữ.</span><span class="sxs-lookup"><span data-stu-id="22949-160">In audience insights, choose the values or for the corresponding fields when attaching the storage account.</span></span>
   
1. <span data-ttu-id="22949-161">Tiếp tục với các bước còn lại trong thông tin chi tiết về đối tượng để đính kèm tài khoản lưu trữ.</span><span class="sxs-lookup"><span data-stu-id="22949-161">Continue with the remaining steps in audience insights to attach the storage account.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]