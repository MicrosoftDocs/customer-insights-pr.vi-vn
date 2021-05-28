---
title: Xuất dữ liệu Customer Insights sang Azure Synapse Analytics
description: Tìm hiểu cách đặt cấu hình kết nối và xuất sang Azure Synapse Analytics.
ms.date: 04/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 822082d661863e737ea3d3a749a6c878db766967
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 05/04/2021
ms.locfileid: "5977403"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a><span data-ttu-id="20e09-103">Xuất dữ liệu sang Azure Synapse Analytics (Bản xem trước)</span><span class="sxs-lookup"><span data-stu-id="20e09-103">Export data to Azure Synapse Analytics (Preview)</span></span>

<span data-ttu-id="20e09-104">Azure Synapse là một dịch vụ phân tích giúp tăng tốc thời gian để hiểu rõ hơn về các kho dữ liệu và hệ thống dữ liệu lớn.</span><span class="sxs-lookup"><span data-stu-id="20e09-104">Azure Synapse is an analytics service that accelerates time to insight across data warehouses and big data systems.</span></span> <span data-ttu-id="20e09-105">Bạn có thể nhập và sử dụng dữ liệu Customer Insights của mình trong [Azure Synapse](/azure/synapse-analytics/overview-what-is).</span><span class="sxs-lookup"><span data-stu-id="20e09-105">You can ingest and use your Customer Insights data in [Azure Synapse](/azure/synapse-analytics/overview-what-is).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="20e09-106">Điều kiện tiên quyết</span><span class="sxs-lookup"><span data-stu-id="20e09-106">Prerequisites</span></span>

<span data-ttu-id="20e09-107">Cần đáp ứng các điều kiện tiên quyết sau để định cấu hình kết nối từ Customer Insights sang Azure Synapse.</span><span class="sxs-lookup"><span data-stu-id="20e09-107">The following prerequisites must be met to configure the connection from Customer Insights to Azure Synapse.</span></span>

> [!NOTE]
> <span data-ttu-id="20e09-108">Đảm bảo bạn đặt tất cả các phép **gán vai trò** giống như mô tả.</span><span class="sxs-lookup"><span data-stu-id="20e09-108">Make sure to set all **role assignments** as described.</span></span>  

## <a name="prerequisites-in-customer-insights"></a><span data-ttu-id="20e09-109">Các điều kiện tiên quyết trong Customer Insights</span><span class="sxs-lookup"><span data-stu-id="20e09-109">Prerequisites in Customer Insights</span></span>

* <span data-ttu-id="20e09-110">Bạn có vai trò **Quản trị viên** trong thông tin chuyên sâu về đối tượng.</span><span class="sxs-lookup"><span data-stu-id="20e09-110">You have an **Administrator** role in audience insights.</span></span> <span data-ttu-id="20e09-111">Tìm hiểu thêm về [thiết lập quyền của người dùng trong phần thông tin chuyên sâu về đối tượng](permissions.md#assign-roles-and-permissions)</span><span class="sxs-lookup"><span data-stu-id="20e09-111">Learn more about [setting user permissions in audience insights](permissions.md#assign-roles-and-permissions)</span></span>

<span data-ttu-id="20e09-112">Trong Azure:</span><span class="sxs-lookup"><span data-stu-id="20e09-112">In Azure:</span></span> 

- <span data-ttu-id="20e09-113">Đăng ký Azure hiện hoạt.</span><span class="sxs-lookup"><span data-stu-id="20e09-113">An active Azure subscription.</span></span>

- <span data-ttu-id="20e09-114">Nếu bạn sử dụng một tài khoản Azure Data Lake Storage Thế hệ 2 mới, *tên dịch vụ chính cho thông tin chuyên sâu về đối tượng* cần được cấp quyền **Người đóng góp dữ liệu Storage Blob**.</span><span class="sxs-lookup"><span data-stu-id="20e09-114">If using a new Azure Data Lake Storage Gen2 account, the *service principal for audience insights* needs **Storage Blob Data Contributor** permissions.</span></span> <span data-ttu-id="20e09-115">Tìm hiểu thêm về [cách kết nối với tài khoản Azure Data Lake Storage Thế hệ 2 với tên dịch vụ chính Azure để có thông tin chuyên sâu về đối tượng](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="20e09-115">Learn more on [connecting to an Azure Data Lake Storage Gen2 account with Azure service principal for audience insights](connect-service-principal.md).</span></span> <span data-ttu-id="20e09-116">Bạn **cần bật** [vùng tên phân cấp](/azure/storage/blobs/data-lake-storage-namespace) trên Data Lake Storage Thế hệ 2.</span><span class="sxs-lookup"><span data-stu-id="20e09-116">The Data Lake Storage Gen2 **must have** [hierarchical namespace](/azure/storage/blobs/data-lake-storage-namespace) enabled.</span></span>

- <span data-ttu-id="20e09-117">Trên nhóm nguồn lực có đặt không gian làm việc Azure Synapse, *tên dịch vụ chính* và *người dùng thông tin chuyên sâu về đối tượng* cần được gán quyền **Người đọc**.</span><span class="sxs-lookup"><span data-stu-id="20e09-117">On the resource group the Azure Synapse workspace is located, the *service principal* and the *user for audience insights* needs to be assigned at least **Reader** permissions.</span></span> <span data-ttu-id="20e09-118">Để biết thêm thông tin, hãy xem [Vai trò Assign Azure bằng cách sử dụng cổng thông tin Azure](/azure/role-based-access-control/role-assignments-portal).</span><span class="sxs-lookup"><span data-stu-id="20e09-118">For more information, see [Assign Azure roles using the Azure portal](/azure/role-based-access-control/role-assignments-portal).</span></span>

- <span data-ttu-id="20e09-119">*Người dùng* cần được cấp quyền **Người đóng góp dữ liệu Storage Blob** trên tài khoản Azure Data Lake Storage Thế hệ 2 nơi đặt dữ liệu và liên kết với không gian làm việc Azure Synapse.</span><span class="sxs-lookup"><span data-stu-id="20e09-119">The *user* needs **Storage Blob Data Contributor** permissions on the Azure Data Lake Storage Gen2 account where the data is located and linked to the Azure Synapse workspace.</span></span> <span data-ttu-id="20e09-120">Tìm hiểu thêm về [cách sử dụng cổng thông tin Azure để gắn vai trò Azure nhằm truy cập vào dữ liệu blob và dữ liệu hàng đợi](/azure/storage/common/storage-auth-aad-rbac-portal) cũng như [quyền Người đóng góp dữ liệu Storage Blob](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span><span class="sxs-lookup"><span data-stu-id="20e09-120">Learn more about [using the Azure portal to assign an Azure role for access to blob and queue data](/azure/storage/common/storage-auth-aad-rbac-portal) and [Storage Blob Data Contributor permissions](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span></span>

- <span data-ttu-id="20e09-121">*[Danh tính có quản lý trong không gian làm việc Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* cần được cấp quyền **Người đóng góp dữ liệu Storage Blob** trên tài khoản Azure Data Lake Storage Thế hệ 2, nơi đặt và liên kết dữ liệu với không gian làm việc Azure Synapse.</span><span class="sxs-lookup"><span data-stu-id="20e09-121">The *[Azure Synapse workspace managed identity](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* needs **Storage Blob Data Contributor** permissions on the Azure Data Lake Storage Gen2 account where the data is located and linked to the Azure Synapse workspace.</span></span> <span data-ttu-id="20e09-122">Tìm hiểu thêm về [cách sử dụng cổng thông tin Azure để gắn vai trò Azure nhằm truy cập vào dữ liệu blob và dữ liệu hàng đợi](/azure/storage/common/storage-auth-aad-rbac-portal) cũng như [quyền Người đóng góp dữ liệu Storage Blob](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span><span class="sxs-lookup"><span data-stu-id="20e09-122">Learn more on [using the Azure portal to assign an Azure role for access to blob and queue data](/azure/storage/common/storage-auth-aad-rbac-portal) and [Storage Blob Data Contributor permissions](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span></span>

- <span data-ttu-id="20e09-123">Trên không gian làm việc Azure Synapse, *tên dịch vụ chính cho thông tin chuyên sâu về đối tượng* cần được gán vai trò **Quản trị viên Synapse**.</span><span class="sxs-lookup"><span data-stu-id="20e09-123">On the Azure Synapse workspace, the *service principal for audience insights* needs **Synapse Administrator** role assigned.</span></span> <span data-ttu-id="20e09-124">Để biết thêm thông tin, hãy xem [Cách thiết lập trạng thái kiểm soát truy cập cho không gian làm việc Synapse của bạn](/azure/synapse-analytics/security/how-to-set-up-access-control).</span><span class="sxs-lookup"><span data-stu-id="20e09-124">For more information, see [How to set up access control for your Synapse workspace](/azure/synapse-analytics/security/how-to-set-up-access-control).</span></span>

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a><span data-ttu-id="20e09-125">Thiết lập kết nối và xuất sang Azure Synapse</span><span class="sxs-lookup"><span data-stu-id="20e09-125">Set up the connection and export to Azure Synapse</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="20e09-126">Đặt cấu hình kết nối</span><span class="sxs-lookup"><span data-stu-id="20e09-126">Configure a connection</span></span>

1. <span data-ttu-id="20e09-127">Đi đến **Quản trị viên** > **Kết nối**.</span><span class="sxs-lookup"><span data-stu-id="20e09-127">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="20e09-128">Chọn **Thêm kết nối** và chọn **Azure Synapse Analytics** hoặc **Thiết lập** trên ngăn xếp **Azure Synapse Analytics** để đặt cấu hình kết nối.</span><span class="sxs-lookup"><span data-stu-id="20e09-128">Select **Add connection** and choose **Azure Synapse Analytics** or select the **Set up** on the **Azure Synapse Analytics** tile to configure the connection.</span></span>

1. <span data-ttu-id="20e09-129">Đặt tên dễ nhận biết cho kết nối trong trường Tên hiển thị.</span><span class="sxs-lookup"><span data-stu-id="20e09-129">Give your connection a recognizable name in the Display name field.</span></span> <span data-ttu-id="20e09-130">Tên và loại kết nối mô tả kết nối này.</span><span class="sxs-lookup"><span data-stu-id="20e09-130">The name and the type of the connection describes this connection.</span></span> <span data-ttu-id="20e09-131">Bạn nên chọn một tên giải thích mục đích và mục tiêu của kết nối.</span><span class="sxs-lookup"><span data-stu-id="20e09-131">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="20e09-132">Chọn người có thể sử dụng kết nối này.</span><span class="sxs-lookup"><span data-stu-id="20e09-132">Choose who can use this connection.</span></span> <span data-ttu-id="20e09-133">Nếu bạn không thực hiện hành động nào, giá trị mặc định sẽ là Quản trị viên.</span><span class="sxs-lookup"><span data-stu-id="20e09-133">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="20e09-134">Để biết thêm thông tin, hãy xem [Cho phép người đóng góp sử dụng một kết nối cho các lần xuất](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="20e09-134">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="20e09-135">Chọn hoặc tìm kiếm gói đăng ký nơi bạn muốn sử dụng dữ liệu Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="20e09-135">Select or search for the subscription you want to use the Customer Insights data in.</span></span> <span data-ttu-id="20e09-136">Ngay sau khi chọn gói đăng ký, bạn cũng có thể chọn **Không gian làm việc**, **Tài khoản lưu trữ** và **Bộ chứa**.</span><span class="sxs-lookup"><span data-stu-id="20e09-136">As soon as a subscription is selected, you can also select **Workspace**, **Storage account**, and **Container**.</span></span>

1. <span data-ttu-id="20e09-137">Để lưu kết nối, hãy chọn **Lưu**.</span><span class="sxs-lookup"><span data-stu-id="20e09-137">Select **Save** to save the connection.</span></span>

### <a name="configure-an-export"></a><span data-ttu-id="20e09-138">Đặt cấu hình xuất</span><span class="sxs-lookup"><span data-stu-id="20e09-138">Configure an export</span></span>

<span data-ttu-id="20e09-139">Bạn có thể đặt cấu hình lần xuất này nếu bạn có quyền truy cập vào kết nối thuộc loại này.</span><span class="sxs-lookup"><span data-stu-id="20e09-139">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="20e09-140">Để biết thêm thông tin, hãy xem [các quyền cần thiết để đặt cấu hình xuất](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="20e09-140">For more information, see [permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="20e09-141">Đi tới **Dữ liệu** > **Nội dung xuất**.</span><span class="sxs-lookup"><span data-stu-id="20e09-141">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="20e09-142">Để tạo nội dung xuất mới, hãy chọn **Thêm nội dung xuất**.</span><span class="sxs-lookup"><span data-stu-id="20e09-142">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="20e09-143">Trong trường **Kết nối để xuất**, hãy chọn một kết nối từ phần **Azure Synapse Analytics**.</span><span class="sxs-lookup"><span data-stu-id="20e09-143">In the **Connection for export** field, choose a connection from the **Azure Synapse Analytics** section.</span></span> <span data-ttu-id="20e09-144">Nếu bạn không thấy tên phần này, tức là không có [kết nối](connections.md) nào thuộc loại này dành cho bạn.</span><span class="sxs-lookup"><span data-stu-id="20e09-144">If you don't see this section name, there are no [connections](connections.md) of this type available to you.</span></span>

1. <span data-ttu-id="20e09-145">Đặt một **Tên hiển thị** dễ nhận biết cho việc xuất dữ liệu và **Tên cơ sở dữ liệu** của bạn.</span><span class="sxs-lookup"><span data-stu-id="20e09-145">Provide a recognizable **Display name** for your export and a **Database name**.</span></span>

1. <span data-ttu-id="20e09-146">Chọn thực thể bạn muốn xuất dữ liệu sang Azure Synapse Analytics.</span><span class="sxs-lookup"><span data-stu-id="20e09-146">Select which entities you want to export to Azure Synapse Analytics.</span></span>

1. <span data-ttu-id="20e09-147">Chọn **Lưu**.</span><span class="sxs-lookup"><span data-stu-id="20e09-147">Select **Save**.</span></span>

<span data-ttu-id="20e09-148">Việc lưu một nội dung xuất sẽ không chạy nội dung xuất đó ngay lập tức.</span><span class="sxs-lookup"><span data-stu-id="20e09-148">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="20e09-149">Nội dung xuất chạy trong mỗi lần [làm mới theo lịch trình](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="20e09-149">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="20e09-150">Bạn cũng có thể [xuất dữ liệu theo yêu cầu](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="20e09-150">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span>

### <a name="update-an-export"></a><span data-ttu-id="20e09-151">Cập nhật việc xuất dữ liệu</span><span class="sxs-lookup"><span data-stu-id="20e09-151">Update an export</span></span>

1. <span data-ttu-id="20e09-152">Đi tới **Dữ liệu** > **Nội dung xuất**.</span><span class="sxs-lookup"><span data-stu-id="20e09-152">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="20e09-153">Chọn **Chỉnh sửa** quá trình xuất bạn muốn cập nhật.</span><span class="sxs-lookup"><span data-stu-id="20e09-153">Select **Edit** on the export you want to update.</span></span>

   - <span data-ttu-id="20e09-154">**Thêm** hoặc **Xóa** các thực thể đã chọn.</span><span class="sxs-lookup"><span data-stu-id="20e09-154">**Add** or **Remove** entities from the selection.</span></span> <span data-ttu-id="20e09-155">Nếu bạn bỏ chọn các thực thể, những thực thể này sẽ không bị xóa khỏi cơ sở dữ liệu Synapse Analytics.</span><span class="sxs-lookup"><span data-stu-id="20e09-155">If entities are removed from the selection, they aren't deleted from the Synapse Analytics database.</span></span> <span data-ttu-id="20e09-156">Tuy nhiên, các thực thể đã xóa trong cơ sở dữ liệu đó sẽ không được cập nhật trong những lần làm mới dữ liệu tiếp theo.</span><span class="sxs-lookup"><span data-stu-id="20e09-156">However, future data refreshes won't update the removed entities in that database.</span></span>

   - <span data-ttu-id="20e09-157">Việc **thay đổi Tên cơ sở dữ liệu** tạo ra cơ sở dữ liệu Synapse Analytics mới.</span><span class="sxs-lookup"><span data-stu-id="20e09-157">**Changing the Database Name** creates a new Synapse Analytics database.</span></span> <span data-ttu-id="20e09-158">Cơ sở dữ liệu có tên đã được định cấu hình trước đó sẽ không nhận được bất kỳ bản cập nhật nào trong các lần làm mới tiếp theo.</span><span class="sxs-lookup"><span data-stu-id="20e09-158">The database with the name that was configured before won't receive any updates in future refreshes.</span></span>
