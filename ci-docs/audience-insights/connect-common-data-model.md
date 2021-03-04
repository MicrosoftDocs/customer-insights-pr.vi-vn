---
title: Kết nối dữ liệu Common Data Model với tài khoản Azure Data Lake
description: Làm việc với dữ liệu Common Data Model bằng cách sử dụng Azure Data Lake Storage.
ms.date: 05/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 247e4d9c47ff2373065ebf3c6d554323e45a120b
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267886"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a><span data-ttu-id="33f1d-103">Kết nối với thư mục Common Data Model sử dụng tài khoản Azure Data Lake</span><span class="sxs-lookup"><span data-stu-id="33f1d-103">Connect to a Common Data Model folder using an Azure Data Lake account</span></span>

<span data-ttu-id="33f1d-104">Bài viết này cung cấp thông tin về cách nhập dữ liệu từ thư mục Common Data Model bằng cách sử dụng tài khoản Azure Data Lake Storage Gen2.</span><span class="sxs-lookup"><span data-stu-id="33f1d-104">This article provides information on how to ingest data from a Common Data Model folder using your Azure Data Lake Storage Gen2 account.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="33f1d-105">Những điều quan trọng cần cân nhắc</span><span class="sxs-lookup"><span data-stu-id="33f1d-105">Important considerations</span></span>

- <span data-ttu-id="33f1d-106">Dữ liệu trong Azure Data Lake của bạn phải theo chuẩn Common Data Model.</span><span class="sxs-lookup"><span data-stu-id="33f1d-106">Data in your Azure Data Lake needs to follow the Common Data Model standard.</span></span> <span data-ttu-id="33f1d-107">Hiện các định dạng khác chưa được hỗ trợ.</span><span class="sxs-lookup"><span data-stu-id="33f1d-107">Other formats aren't supported at the moment.</span></span>

- <span data-ttu-id="33f1d-108">Nhập dữ liệu chỉ hỗ trợ tài khoản lưu trữ Azure Data Lake *Gen2*.</span><span class="sxs-lookup"><span data-stu-id="33f1d-108">Data ingestion supports Azure Data Lake *Gen2* storage accounts exclusively.</span></span> <span data-ttu-id="33f1d-109">Bạn không thể sử dụng tài khoản lưu trữ Azure Data Lake Gen1 để nhập dữ liệu.</span><span class="sxs-lookup"><span data-stu-id="33f1d-109">You can't use Azure Data Lake Gen1 storage accounts to ingest data.</span></span>

- <span data-ttu-id="33f1d-110">Để xác thực bằng dịch vụ chính Azure, hãy đảm bảo rằng dịch vụ chính được định cấu hình trong đối tượng thuê của bạn.</span><span class="sxs-lookup"><span data-stu-id="33f1d-110">To authenticate with an Azure service principal, make sure it's configured in your tenant.</span></span> <span data-ttu-id="33f1d-111">Để biết thêm thông tin, hãy xem [Kết nối thông tin chuyên sâu về đối tượng với tài khoản Azure Data Lake Storage Gen2 có dịch vụ chính Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="33f1d-111">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span>

- <span data-ttu-id="33f1d-112">Azure Data Lake mà bạn muốn kết nối và nhập dữ liệu phải ở cùng khu vực Azure với môi trường Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="33f1d-112">The Azure Data Lake you want to connect and ingest data from have to be in the same Azure region as the Dynamics 365 Customer Insights environment.</span></span> <span data-ttu-id="33f1d-113">Không hỗ trợ kết nối với thư mục Common Data Model từ một kho dữ liệu trong một vùng Azure khác.</span><span class="sxs-lookup"><span data-stu-id="33f1d-113">Connections to a Common Data Model folder from a data lake in a different Azure region is not supported.</span></span> <span data-ttu-id="33f1d-114">Để biết vùng Azure của môi trường, hãy đi tới **Quản trị viên** > **Hệ thống** > **Giới thiệu** trong thông tin chuyên sâu về đối tượng.</span><span class="sxs-lookup"><span data-stu-id="33f1d-114">To know the Azure region of the environment, go to **Admin** > **System** > **About** in audience insights.</span></span>

- <span data-ttu-id="33f1d-115">Dữ liệu được lưu trữ trong các dịch vụ trực tuyến, có thể được lưu trữ ở một vị trí khác với nơi dữ liệu được xử lý hoặc lưu trữ trong Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="33f1d-115">Data stored in online services, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="33f1d-116"> Khi nhập hoặc kết nối với dữ liệu lưu trữ trong các dịch vụ trực tuyến, bạn đồng ý rằng dữ liệu có thể được chuyển sang hoặc lưu trữ bằng Dynamics 365 Customer Insights. [Tìm hiểu thêm trên Trung tâm tin cậy Microsoft.](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="33f1d-116"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-model-folder"></a><span data-ttu-id="33f1d-117">Kết nối với thư mục Common Data Model</span><span class="sxs-lookup"><span data-stu-id="33f1d-117">Connect to a Common Data Model folder</span></span>

1. <span data-ttu-id="33f1d-118">Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Dữ liệu** > **Nguồn dữ liệu**.</span><span class="sxs-lookup"><span data-stu-id="33f1d-118">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="33f1d-119">Chọn **Thêm nguồn dữ liệu**.</span><span class="sxs-lookup"><span data-stu-id="33f1d-119">Select **Add data source**.</span></span>

1. <span data-ttu-id="33f1d-120">Chọn **Kết nối với thư mục Common Data Model**, nhập **Tên** cho nguồn dữ liệu và chọn **Tiếp theo**.</span><span class="sxs-lookup"><span data-stu-id="33f1d-120">Select **Connect to a Common Data Model folder**, enter a **Name** for the data source, and select **Next**.</span></span> <span data-ttu-id="33f1d-121">Hướng dẫn về tên:</span><span class="sxs-lookup"><span data-stu-id="33f1d-121">Name guidelines:</span></span> 
   - <span data-ttu-id="33f1d-122">Bắt đầu bằng một chữ cái.</span><span class="sxs-lookup"><span data-stu-id="33f1d-122">Start with a letter.</span></span>
   - <span data-ttu-id="33f1d-123">Chỉ sử dụng chữ cái và số.</span><span class="sxs-lookup"><span data-stu-id="33f1d-123">Use letters and numbers only.</span></span> <span data-ttu-id="33f1d-124">Không được phép nhập ký tự đặc biệt và khoảng trống.</span><span class="sxs-lookup"><span data-stu-id="33f1d-124">Special characters and spaces are not allowed.</span></span>
   - <span data-ttu-id="33f1d-125">Sử dụng từ 3 đến 64 ký tự.</span><span class="sxs-lookup"><span data-stu-id="33f1d-125">Use between 3 and 64 characters.</span></span>

1. <span data-ttu-id="33f1d-126">Bạn có thể chọn giữa sử dụng tùy chọn dựa trên nguồn lực và tùy chọn dựa trên đăng ký để xác thực.</span><span class="sxs-lookup"><span data-stu-id="33f1d-126">You can choose between using a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="33f1d-127">Để biết thêm thông tin, hãy xem [Kết nối thông tin chuyên sâu về đối tượng với tài khoản Azure Data Lake Storage Gen2 có dịch vụ chính Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="33f1d-127">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="33f1d-128">Nhập thông tin **Vùng chứa** và chọn **Tiếp theo**.</span><span class="sxs-lookup"><span data-stu-id="33f1d-128">Enter the **Container** information and select **Next**.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="33f1d-129">![Hộp thoại để nhập chi tiết kết nối mới cho Azure Data Lake](media/enter-new-storage-details.png)
   > </span><span class="sxs-lookup"><span data-stu-id="33f1d-129">![Dialog box to enter new connection details for Azure Data Lake](media/enter-new-storage-details.png)
   > </span></span>[!NOTE]
<span data-ttu-id="33f1d-130">Bạn cần một trong các vai trò sau đối với vùng chứa hoặc tài khoản lưu trữ được đề cập ở trên để có thể kết nối và tạo nguồn dữ liệu:</span><span class="sxs-lookup"><span data-stu-id="33f1d-130">You need one of the following roles either to the container or the storage account referred above to be able to connect to and create a data source:</span></span>
   >  - <span data-ttu-id="33f1d-131">Bộ đọc dữ liệu khối lưu trữ</span><span class="sxs-lookup"><span data-stu-id="33f1d-131">Storage Blob Data Reader</span></span>
   >  - <span data-ttu-id="33f1d-132">Chủ sở hữu dữ liệu khối lưu trữ</span><span class="sxs-lookup"><span data-stu-id="33f1d-132">Storage Blob Data Owner</span></span>
   >  - <span data-ttu-id="33f1d-133">Người đóng góp dữ liệu khối lưu trữ</span><span class="sxs-lookup"><span data-stu-id="33f1d-133">Storage Blob Data Contributor</span></span>

1. <span data-ttu-id="33f1d-134">Trong hộp thoại **Chọn thư mục Common Data Model**, chọn tệp model.json hoặc manifest.json để nhập dữ liệu từ đó và chọn **Tiếp theo**.</span><span class="sxs-lookup"><span data-stu-id="33f1d-134">In the **Select a Common Data Model folder** dialog, select the model.json or manifest.json file to import data from, and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="33f1d-135">Mọi tệp model.json hoặc manifest.json được liên kết với nguồn dữ liệu khác trong môi trường sẽ không hiển thị trong danh sách.</span><span class="sxs-lookup"><span data-stu-id="33f1d-135">Any model.json or manifest.json file associated with another data source in the environment won't show in the list.</span></span>

1. <span data-ttu-id="33f1d-136">Bạn sẽ nhận được danh sách các thực thể có sẵn trong tệp model.json hoặc manifest.json đã chọn.</span><span class="sxs-lookup"><span data-stu-id="33f1d-136">You'll get a list of available entities in the selected model.json or manifest.json file.</span></span> <span data-ttu-id="33f1d-137">Bạn có thể xem lại và chọn từ danh sách các thực thể có sẵn rồi chọn **Lưu**.</span><span class="sxs-lookup"><span data-stu-id="33f1d-137">You can review and select from the list of available entities and select **Save**.</span></span> <span data-ttu-id="33f1d-138">Tất cả thực thể đã chọn sẽ được nhập từ nguồn dữ liệu mới.</span><span class="sxs-lookup"><span data-stu-id="33f1d-138">All of the selected entities will be ingested from the new data source.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="33f1d-139">![Hộp thoại hiển thị danh sách thực thể từ tệp model.json](media/review-entities.png)</span><span class="sxs-lookup"><span data-stu-id="33f1d-139">![Dialog box showing a list of entities from a model.json file](media/review-entities.png)</span></span>

8. <span data-ttu-id="33f1d-140">Cho biết những thực thể dữ liệu nào bạn muốn bật tính năng phân tích chất lượng dữ liệu và chọn **Lưu**.</span><span class="sxs-lookup"><span data-stu-id="33f1d-140">Indicate which data entities you want to enable data profiling and select **Save**.</span></span> <span data-ttu-id="33f1d-141">Tính năng thu thập dữ liệu cho phép phân tích và các chức năng khác.</span><span class="sxs-lookup"><span data-stu-id="33f1d-141">Data profiling enables analytics and other capabilities.</span></span> <span data-ttu-id="33f1d-142">Bạn có thể chọn toàn bộ thực thể. Thao tác này sẽ chọn tất cả các thuộc tính từ thực thể hoặc chọn một số thuộc tính bạn chọn.</span><span class="sxs-lookup"><span data-stu-id="33f1d-142">You can select the whole entity, which selects all attributes from the entity, or select certain attributes of your choice.</span></span> <span data-ttu-id="33f1d-143">Theo mặc định, không có thực thể nào được bật cho phân tích chất lượng dữ liệu.</span><span class="sxs-lookup"><span data-stu-id="33f1d-143">By default, no entity is enabled for data profiling.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="33f1d-144">![Hộp thoại hiển thị phân tích chất lượng dữ liệu](media/dataprofiling-entities.png)</span><span class="sxs-lookup"><span data-stu-id="33f1d-144">![Dialog box showing a data profiling](media/dataprofiling-entities.png)</span></span>

9. <span data-ttu-id="33f1d-145">Sau khi bạn lưu các lựa chọn, trang **Nguồn dữ liệu** sẽ mở ra.</span><span class="sxs-lookup"><span data-stu-id="33f1d-145">After saving your selections, the **Data sources** page opens.</span></span> <span data-ttu-id="33f1d-146">Lúc này, bạn sẽ thấy kết nối thư mục Common Data Model dưới dạng nguồn dữ liệu.</span><span class="sxs-lookup"><span data-stu-id="33f1d-146">You should now see the Common Data Model folder connection as a data source.</span></span>

> [!NOTE]
> <span data-ttu-id="33f1d-147">Tệp model.json hoặc manifest.json chỉ có thể liên kết với một nguồn dữ liệu trong cùng một môi trường.</span><span class="sxs-lookup"><span data-stu-id="33f1d-147">A model.json file or manifest.json can only associate with one data source in the same environment.</span></span> <span data-ttu-id="33f1d-148">Tuy nhiên, cùng một tệp model.json hoặc manifest.json có thể được sử dụng cho các nguồn dữ liệu trong nhiều môi trường.</span><span class="sxs-lookup"><span data-stu-id="33f1d-148">However, the same model.json or manifest.json file can be used for data sources in multiple environments.</span></span>

## <a name="edit-a-common-data-model-folder-data-source"></a><span data-ttu-id="33f1d-149">Chỉnh sửa nguồn dữ liệu thư mục Common Data Model</span><span class="sxs-lookup"><span data-stu-id="33f1d-149">Edit a Common Data Model folder data source</span></span>

<span data-ttu-id="33f1d-150">Bạn có thể cập nhật khóa truy cập cho tài khoản lưu trữ có chứa thư mục Common Data Model.</span><span class="sxs-lookup"><span data-stu-id="33f1d-150">You can update the access key for the storage account containing the Common Data Model folder.</span></span> <span data-ttu-id="33f1d-151">Bạn cũng có thể thay đổi tệp model.json hoặc tệp manifest.json.</span><span class="sxs-lookup"><span data-stu-id="33f1d-151">You may also change the model.json or manifest.json file.</span></span> <span data-ttu-id="33f1d-152">Để kết nối với vùng chứa khác từ tài khoản lưu trữ của bạn hoặc đổi tên tài khoản, hãy [tạo một kết nối mới cho nguồn dữ liệu](#connect-to-a-common-data-model-folder).</span><span class="sxs-lookup"><span data-stu-id="33f1d-152">To connect to a different container from your storage account, or change the account name, [create a new data source connection](#connect-to-a-common-data-model-folder).</span></span>

1. <span data-ttu-id="33f1d-153">Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Dữ liệu** > **Nguồn dữ liệu**.</span><span class="sxs-lookup"><span data-stu-id="33f1d-153">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="33f1d-154">Cạnh nguồn dữ liệu mà bạn muốn thay đổi, hãy chọn dấu chấm lửng.</span><span class="sxs-lookup"><span data-stu-id="33f1d-154">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="33f1d-155">Nhấp vào tùy chọn **Chỉnh sửa** trong danh sách.</span><span class="sxs-lookup"><span data-stu-id="33f1d-155">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="33f1d-156">Nếu muốn, hãy thay đổi **Mã truy cập** rồi chọn **Tiếp**.</span><span class="sxs-lookup"><span data-stu-id="33f1d-156">Optionally, update the **Access key** and select **Next**.</span></span>

   ![Hộp thoại để chỉnh sửa và cập nhật mã truy cập cho nguồn dữ liệu hiện tại](media/edit-access-key.png)

5. <span data-ttu-id="33f1d-158">Theo tùy chọn, bạn có thể cập nhật từ kết nối khóa tài khoản thành kết nối dựa trên tài nguyên hoặc dựa trên đăng ký.</span><span class="sxs-lookup"><span data-stu-id="33f1d-158">Optionally, you can update from an account key connection to a resource-based or a subscription-based connection.</span></span> <span data-ttu-id="33f1d-159">Để biết thêm thông tin, hãy xem [Kết nối thông tin chuyên sâu về đối tượng với tài khoản Azure Data Lake Storage Gen2 có dịch vụ chính Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="33f1d-159">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="33f1d-160">Bạn không thể thay đổi thông tin **Vùng chứa** khi cập nhật kết nối.</span><span class="sxs-lookup"><span data-stu-id="33f1d-160">You can't change **Container** information when updating the connection.</span></span>
   > [!div class="mx-imgBorder"]

   > ![Hộp thoại để nhập chi tiết kết nối cho Azure Data Lake với tài khoản lưu trữ hiện có](media/enter-existing-storage-details.png)

   > [!NOTE]
   > <span data-ttu-id="33f1d-162">Bạn cần một trong các vai trò sau đối với vùng chứa hoặc tài khoản lưu trữ được đề cập ở trên để có thể kết nối và tạo nguồn dữ liệu:</span><span class="sxs-lookup"><span data-stu-id="33f1d-162">You need one of the following roles either to the container or the storage account referred above to be able to connect to and create a data source:</span></span>
   >  - <span data-ttu-id="33f1d-163">Bộ đọc dữ liệu khối lưu trữ</span><span class="sxs-lookup"><span data-stu-id="33f1d-163">Storage Blob Data Reader</span></span>
   >  - <span data-ttu-id="33f1d-164">Chủ sở hữu dữ liệu khối lưu trữ</span><span class="sxs-lookup"><span data-stu-id="33f1d-164">Storage Blob Data Owner</span></span>
   >  - <span data-ttu-id="33f1d-165">Người đóng góp dữ liệu khối lưu trữ</span><span class="sxs-lookup"><span data-stu-id="33f1d-165">Storage Blob Data Contributo</span></span>


6. <span data-ttu-id="33f1d-166">Tùy chọn, hãy chọn tệp model.json hoặc tệp manifest.json khác với một nhóm thực thể khác từ vùng chứa.</span><span class="sxs-lookup"><span data-stu-id="33f1d-166">Optionally, choose a different model.json or manifest.json file with a different set of entities from the container.</span></span>

7. <span data-ttu-id="33f1d-167">Theo tùy chọn, bạn có thể chọn các thực thể bổ sung để nhập.</span><span class="sxs-lookup"><span data-stu-id="33f1d-167">Optionally, you can select additional entities to ingest.</span></span> <span data-ttu-id="33f1d-168">Bạn cũng có thể xóa mọi thực thể đã chọn nếu không có phụ thuộc.</span><span class="sxs-lookup"><span data-stu-id="33f1d-168">You can also remove any already selected entities if there are no dependencies.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="33f1d-169">Nếu có các phần phụ thuộc vào tệp model.json hoặc tệp manifest.json hiện có và tập hợp các thực thể, bạn sẽ thấy thông báo lỗi và không thể chọn tệp model.json hoặc tệp manifest.json khác.</span><span class="sxs-lookup"><span data-stu-id="33f1d-169">If there are dependencies on the existing model.json or manifest.json file and the set of entities, you'll see an error message and can't select a different model.json or manifest.json file.</span></span> <span data-ttu-id="33f1d-170">Hãy xóa các phần phụ thuộc đó trước khi thay đổi tệp model.json hoặc tệp manifest.json hoặc tạo một nguồn dữ liệu mới với tệp model.json hoặc tệp manifest.json mà bạn muốn sử dụng để tránh xóa các phần phụ thuộc.</span><span class="sxs-lookup"><span data-stu-id="33f1d-170">Remove those dependencies before changing the model.json or manifest.json file or create a new data source with the model.json or manifest.json file that you want to use to avoid removing the dependencies.</span></span>

8. <span data-ttu-id="33f1d-171">Theo tùy chọn, bạn có thể chọn các thuộc tính hoặc thực thể bổ sung để bật hoặc tắt phân tích chất lượng dữ liệu đã được chọn.</span><span class="sxs-lookup"><span data-stu-id="33f1d-171">Optionally, you can select additional attributes or entities to enable data profiling on or disable already selected ones.</span></span>   


[!INCLUDE[footer-include](../includes/footer-banner.md)]