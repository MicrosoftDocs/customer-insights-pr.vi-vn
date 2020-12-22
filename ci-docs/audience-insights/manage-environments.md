---
title: Tạo và quản lý môi trường
description: Tìm hiểu cách đăng ký dịch vụ và cách quản lý môi trường.
ms.date: 11/10/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
ms.reviewer: nimagen
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 010336445d0825a7ff82d1b7a65702fc12245788
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644159"
---
# <a name="manage-environments"></a><span data-ttu-id="84136-103">Quản lý môi trường</span><span class="sxs-lookup"><span data-stu-id="84136-103">Manage environments</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="84136-104">Bài viết này giải thích cách tạo một tổ chức mới và cách cung cấp môi trường.</span><span class="sxs-lookup"><span data-stu-id="84136-104">This article explains how to create a new organization and how to provision an environment.</span></span>

## <a name="sign-up-and-create-an-organization"></a><span data-ttu-id="84136-105">Đăng ký và tạo một tổ chức</span><span class="sxs-lookup"><span data-stu-id="84136-105">Sign up and create an organization</span></span>

1. <span data-ttu-id="84136-106">Truy cập trang web [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/).</span><span class="sxs-lookup"><span data-stu-id="84136-106">Go to the [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) website.</span></span>

2. <span data-ttu-id="84136-107">Chọn **Bắt đầu**.</span><span class="sxs-lookup"><span data-stu-id="84136-107">Select **Get Started**.</span></span>

3. <span data-ttu-id="84136-108">Chọn kịch bản đăng nhập bạn mong muốn rồi nhấp vào đường liên kết tương ứng.</span><span class="sxs-lookup"><span data-stu-id="84136-108">Choose your preferred sign-up scenario and select the corresponding link.</span></span>

4. <span data-ttu-id="84136-109">Chấp nhận các điều khoản và điều kiện rồi chọn **Tiếp tục** để bắt đầu tạo tổ chức.</span><span class="sxs-lookup"><span data-stu-id="84136-109">Accept the terms and conditions and select **Continue** to start creating the organization.</span></span>

5. <span data-ttu-id="84136-110">Sau khi môi trường được tạo, bạn sẽ được chuyển hướng đến [Customer Insights](https://home.ci.ai.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="84136-110">After the environment is created, you'll be redirected to [Customer Insights](https://home.ci.ai.dynamics.com).</span></span>

6. <span data-ttu-id="84136-111">Sử dụng môi trường demo để khám phá ứng dụng hoặc tạo môi trường mới bằng cách làm theo các bước trong phần tiếp theo.</span><span class="sxs-lookup"><span data-stu-id="84136-111">Use the demo environment to explore the app, or create a new environment by following the steps in the next section.</span></span>

7. <span data-ttu-id="84136-112">Sau khi xác định các tùy chọn cài đặt cho môi trường, hãy chọn **Tạo**.</span><span class="sxs-lookup"><span data-stu-id="84136-112">After specifying the environment settings, select **Create**.</span></span>

8. <span data-ttu-id="84136-113">Bạn sẽ được đăng nhập sau khi tạo thành công môi trường.</span><span class="sxs-lookup"><span data-stu-id="84136-113">You'll be signed in after the environment was created successfully.</span></span>

## <a name="create-an-environment-in-an-existing-organization"></a><span data-ttu-id="84136-114">Tạo môi trường trong tổ chức hiện có</span><span class="sxs-lookup"><span data-stu-id="84136-114">Create an environment in an existing organization</span></span>

<span data-ttu-id="84136-115">Có hai cách để tạo một môi trường mới.</span><span class="sxs-lookup"><span data-stu-id="84136-115">There are two ways to create a new environment.</span></span> <span data-ttu-id="84136-116">Bạn có thể chỉ định một cấu hình hoàn toàn mới hoặc sao chép một số thiết đặt cấu hình từ môi trường hiện có.</span><span class="sxs-lookup"><span data-stu-id="84136-116">You can either specify an entirely new configuration, or you can copy some configuration settings from an existing environment.</span></span>

<span data-ttu-id="84136-117">Để tạo môi trường:</span><span class="sxs-lookup"><span data-stu-id="84136-117">To create an environment:</span></span>

1. <span data-ttu-id="84136-118">Chọn biểu tượng **Cài đặt** ở đầu ứng dụng này.</span><span class="sxs-lookup"><span data-stu-id="84136-118">Select the **Settings** symbol in the header of the app.</span></span>

1. <span data-ttu-id="84136-119">Chọn **Môi trường mới**.</span><span class="sxs-lookup"><span data-stu-id="84136-119">Select **New environment**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="84136-120">![Thiết đặt Môi trường](media/environment-settings-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="84136-120">![Environment settings](media/environment-settings-dialog.png)</span></span>

1. <span data-ttu-id="84136-121">Trong hộp thoại **Tạo môi trường mới**, chọn **Môi trường mới**.</span><span class="sxs-lookup"><span data-stu-id="84136-121">In the **Create new environment** dialog, select **New environment**.</span></span>

   <span data-ttu-id="84136-122">Nếu bạn muốn [sao chép dữ liệu từ môi trường hiện tại](#additional-considerations-for-copy-configuration-preview), chọn **Sao chép từ môi trường hiện có**.</span><span class="sxs-lookup"><span data-stu-id="84136-122">If you want to [copy data from the current environment](#additional-considerations-for-copy-configuration-preview), select **Copy from existing environment**.</span></span> <span data-ttu-id="84136-123">Bạn sẽ nhìn thấy danh sách tất cả các môi trường có sẵn trong tổ chức, nơi bạn có thể sao chép dữ liệu từ đó.</span><span class="sxs-lookup"><span data-stu-id="84136-123">You'll see a list of all available environments in your organization where you can copy data from.</span></span>

1. <span data-ttu-id="84136-124">Cung cấp các chi tiết sau đây:</span><span class="sxs-lookup"><span data-stu-id="84136-124">Provide the following details:</span></span>
   - <span data-ttu-id="84136-125">**Tên**: Tên cho môi trường này.</span><span class="sxs-lookup"><span data-stu-id="84136-125">**Name**: The name for this environment.</span></span> <span data-ttu-id="84136-126">Trường này đã được điền nếu bạn sao chép một môi trường hiện có, nhưng bạn có thể thay đổi trường này.</span><span class="sxs-lookup"><span data-stu-id="84136-126">This field is already filled in if you've copied an existing environment, but you can change it.</span></span>
   - <span data-ttu-id="84136-127">**Vùng**: Vùng triển khai và lưu trư dịch vụ.</span><span class="sxs-lookup"><span data-stu-id="84136-127">**Region**: The region into which the service is deployed and hosted.</span></span>
   - <span data-ttu-id="84136-128">**Loại**: Chọn xem bạn muốn tạo môi trường sản xuất hay hộp cát.</span><span class="sxs-lookup"><span data-stu-id="84136-128">**Type**: Select whether you want to create a Production or Sandbox environment.</span></span>

2. <span data-ttu-id="84136-129">Bạn có thể chọn **Thiết đặt nâng cao**:</span><span class="sxs-lookup"><span data-stu-id="84136-129">Optionally, you can select **Advanced settings**:</span></span>

   - <span data-ttu-id="84136-130">**Lưu tất cả dữ liệu vào**: Chỉ định nơi bạn muốn lưu trữ dữ liệu đầu ra được tạo từ Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="84136-130">**Save all data to**: Specifies where you want to store the output data generated from Customer Insights.</span></span> <span data-ttu-id="84136-131">Bạn sẽ có hai lựa chọn: **Lưu trữ trong Customer Insights** (Azure Data Lake do đội ngũ Customer Insights quản lý) và **Azure Data Lake Storage thế hệ 2** (Azure Data Lake Storage của chính bạn).</span><span class="sxs-lookup"><span data-stu-id="84136-131">You'll have two options: **Customer Insights storage** (an Azure Data Lake managed by the Customer Insights team) and **Azure Data Lake Storage Gen2** (your own Azure Data Lake Storage).</span></span> <span data-ttu-id="84136-132">Tùy chọn mặc định là lưu trữ trong Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="84136-132">By default, the Customer Insights storage option is selected.</span></span>

   > [!NOTE]
   > <span data-ttu-id="84136-133">Bằng việc lưu dữ liệu vào Azure Data Lake Storage, bạn đồng ý rằng dữ liệu sẽ được chuyển sang và lưu trữ tại vị trí địa lý phù hợp cho tài khoản Azure Storage đó. Vị trí này có thể khác với nơi lưu trữ dữ liệu trong Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="84136-133">By saving data to Azure Data Lake Storage, you agree that data will be transferred to and stored in the appropriate geographic location for that Azure storage account, which may differ from where data is stored in Dynamics 365 Customer Insights.</span></span> [<span data-ttu-id="84136-134">Hãy tìm hiểu thêm tại Trung tâm tin cậy Microsoft.</span><span class="sxs-lookup"><span data-stu-id="84136-134">Learn more at the Microsoft Trust Center.</span></span>](https://www.microsoft.com/trust-center)
   >
   > <span data-ttu-id="84136-135">Hiện tại, các thực thể đã thu nạp sẽ luôn được lưu trữ trong hồ dữ liệu do Customer Insights quản lý.</span><span class="sxs-lookup"><span data-stu-id="84136-135">Currently, ingested entities are always stored in the Customer Insights managed data lake.</span></span>
   > <span data-ttu-id="84136-136">Chúng tôi chỉ hỗ trợ các tài khoản lưu trữ Azure Data Lake Gen2 từ cùng một vùng Azure mà bạn đã chọn khi tạo môi trường.</span><span class="sxs-lookup"><span data-stu-id="84136-136">We support only Azure Data Lake Gen2 storage accounts from the same Azure region you selected when creating the environment.</span></span>
   > <span data-ttu-id="84136-137">Chúng tôi chỉ hỗ trợ Không gian tên theo cấp bậc (HNS) Azure Data Lake thế hệ 2 có hỗ trợ tài khoản lưu trữ.</span><span class="sxs-lookup"><span data-stu-id="84136-137">We support only Azure Data Lake Gen2 Hierarchical Name Space (HNS) enabled storage accounts.</span></span>

   - <span data-ttu-id="84136-138">Đối với tùy chọn Azure Data Lake Storage Gen2, bạn có thể chọn giữa tùy chọn dựa trên nguồn lực và tùy chọn dựa trên đăng ký để xác thực.</span><span class="sxs-lookup"><span data-stu-id="84136-138">For the Azure Data Lake Storage Gen2 option, you can choose between a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="84136-139">Để biết thêm thông tin, hãy xem [Kết nối thông tin chuyên sâu về đối tượng với tài khoản Azure Data Lake Storage Gen2 có dịch vụ chính Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="84136-139">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="84136-140">Tên **Vùng chứa** không thể thay đổi và sẽ là "customerinsights".</span><span class="sxs-lookup"><span data-stu-id="84136-140">The **Container** name can't be changed and will be "customerinsights".</span></span>
   
   - <span data-ttu-id="84136-141">Nếu bạn muốn sử dụng [dự đoán](predictions.md), nhập URL phiên bản Common Data Service trong trường **Địa chỉ máy chủ** trong **Sử dụng dự đoán**.</span><span class="sxs-lookup"><span data-stu-id="84136-141">If you want to use [predictions](predictions.md), enter the Common Data Service instance URL in the **Server address** field under **Use predictions**.</span></span>

   <span data-ttu-id="84136-142">Khi bạn chạy các quy trình, chẳng hạn như nhập dữ liệu hoặc tạo phân đoạn, các thư mục tương ứng sẽ được tạo trong tài khoản lưu trữ mà bạn đã chỉ định ở trên.</span><span class="sxs-lookup"><span data-stu-id="84136-142">When you run processes, such as data ingestion or segment creation, corresponding folders will be created in the storage account you specified above.</span></span> <span data-ttu-id="84136-143">Các tệp dữ liệu và tệp model.json sẽ được tạo và thêm vào các thư mục con tương ứng dựa trên quy trình bạn chạy.</span><span class="sxs-lookup"><span data-stu-id="84136-143">Data files and model.json files will be created and added to the respective subfolders based on the process you run.</span></span>

   <span data-ttu-id="84136-144">Nếu bạn tạo nhiều môi trường Customer Insights và chọn lưu các thực thể đầu ra từ các môi trường đó trong tài khoản lưu trữ của mình, các thư mục riêng biệt sẽ được tạo cho từng môi trường với ci_<environmentid> trong vùng chứa.</span><span class="sxs-lookup"><span data-stu-id="84136-144">If you create multiple environments of Customer Insights and choose to save the output entities from those environments in your storage account, separate folders will be created for each environment with ci_<environmentid> in the container.</span></span>

### <a name="additional-considerations-for-copy-configuration-preview"></a><span data-ttu-id="84136-145">Các cân nhắc bổ sung đối với cấu hình sao chép (bản xem trước)</span><span class="sxs-lookup"><span data-stu-id="84136-145">Additional considerations for copy configuration (preview)</span></span>

<span data-ttu-id="84136-146">Các thiết đặt cấu hình sau được sao chép:</span><span class="sxs-lookup"><span data-stu-id="84136-146">The following configuration settings are copied:</span></span>

- <span data-ttu-id="84136-147">Cấu hình tính năng</span><span class="sxs-lookup"><span data-stu-id="84136-147">Feature configurations</span></span>
- <span data-ttu-id="84136-148">Nguồn dữ liệu nhập</span><span class="sxs-lookup"><span data-stu-id="84136-148">Inegsted/imported data sources</span></span>
- <span data-ttu-id="84136-149">Cấu hình hợp nhất dữ liệu (Bản đồ, kết hợp, hợp nhất)</span><span class="sxs-lookup"><span data-stu-id="84136-149">Data unification (Map, Match, Merge) configuration</span></span>
- <span data-ttu-id="84136-150">Phân đoạn</span><span class="sxs-lookup"><span data-stu-id="84136-150">Segments</span></span>
- <span data-ttu-id="84136-151">Biện pháp</span><span class="sxs-lookup"><span data-stu-id="84136-151">Measures</span></span>
- <span data-ttu-id="84136-152">Mối quan hệ</span><span class="sxs-lookup"><span data-stu-id="84136-152">Relationships</span></span>
- <span data-ttu-id="84136-153">Hoạt động</span><span class="sxs-lookup"><span data-stu-id="84136-153">Activities</span></span>
- <span data-ttu-id="84136-154">Chỉ mục tìm kiếm & lọc</span><span class="sxs-lookup"><span data-stu-id="84136-154">Search & filter Index</span></span>
- <span data-ttu-id="84136-155">Đích xuất</span><span class="sxs-lookup"><span data-stu-id="84136-155">Export destinations</span></span>
- <span data-ttu-id="84136-156">Làm mới theo lịch trình</span><span class="sxs-lookup"><span data-stu-id="84136-156">Scheduled refresh</span></span>
- <span data-ttu-id="84136-157">Nội dung làm phong phú</span><span class="sxs-lookup"><span data-stu-id="84136-157">Enrichments</span></span>
- <span data-ttu-id="84136-158">Quản lý mô hình</span><span class="sxs-lookup"><span data-stu-id="84136-158">Model management</span></span>
- <span data-ttu-id="84136-159">Chỉ định vai trò</span><span class="sxs-lookup"><span data-stu-id="84136-159">Role assignments</span></span>

<span data-ttu-id="84136-160">Các thiết đặt sau *không* được sao chép:</span><span class="sxs-lookup"><span data-stu-id="84136-160">The following settings are *not* copied:</span></span>

- <span data-ttu-id="84136-161">Hồ sơ khách hàng.</span><span class="sxs-lookup"><span data-stu-id="84136-161">Customer profiles.</span></span>
- <span data-ttu-id="84136-162">Thông tin xác thực nguồn dữ liệu.</span><span class="sxs-lookup"><span data-stu-id="84136-162">Data source credentials.</span></span> <span data-ttu-id="84136-163">Bạn sẽ phải cung cấp thông tin đăng nhập cho mỗi nguồn dữ liệu và làm mới các nguồn dữ liệu theo cách thủ công.</span><span class="sxs-lookup"><span data-stu-id="84136-163">You'll have to provide the credentials for every data source and refresh the data sources manually.</span></span>
- <span data-ttu-id="84136-164">Nguồn dữ liệu từ thư mục Common Data Model và kho được quản lý Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="84136-164">Data sources from Common Data Model folder and Common Data Service managed lake.</span></span> <span data-ttu-id="84136-165">Bạn sẽ phải tạo các nguồn dữ liệu đó theo cách thủ công có cùng tên như trong môi trường nguồn.</span><span class="sxs-lookup"><span data-stu-id="84136-165">You'll have to create those data sources manually with the same name as in the source environment.</span></span>

<span data-ttu-id="84136-166">Khi bạn sao chép một môi trường, bạn sẽ thấy một thông báo xác nhận rằng môi trường mới đã được tạo.</span><span class="sxs-lookup"><span data-stu-id="84136-166">When you copy an environment, you'll see a confirmation message that the new environment has been created.</span></span> <span data-ttu-id="84136-167">Chọn **Chuyển đến nguồn dữ liệu** để xem danh sách các nguồn dữ liệu.</span><span class="sxs-lookup"><span data-stu-id="84136-167">Select **Go to data sources** to see the list of data sources.</span></span>

<span data-ttu-id="84136-168">Tất cả nguồn dữ liệu sẽ hiển thị trạng thái **Đã yêu cầu thông tin đăng nhập**.</span><span class="sxs-lookup"><span data-stu-id="84136-168">All the data sources will show a **Credentials Required** status.</span></span> <span data-ttu-id="84136-169">Chỉnh sửa nguồn dữ liệu và nhập thông tin đăng nhập để làm mới những nguồn dữ liệu đó.</span><span class="sxs-lookup"><span data-stu-id="84136-169">Edit the data sources and enter the credentials to refresh them.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="84136-170">![Đã sao chép nguồn dữ liệu](media/data-sources-copied.png)</span><span class="sxs-lookup"><span data-stu-id="84136-170">![Data sources copied](media/data-sources-copied.png)</span></span>

<span data-ttu-id="84136-171">Sau khi làm mới nguồn dữ liệu, hãy chuyển đến **Dữ liệu** > **Hợp nhất**.</span><span class="sxs-lookup"><span data-stu-id="84136-171">After refreshing the data sources, go to **Data** > **Unify**.</span></span> <span data-ttu-id="84136-172">Tại đây, bạn sẽ tìm thấy các thiết đặt từ môi trường nguồn.</span><span class="sxs-lookup"><span data-stu-id="84136-172">Here you'll find settings from the source environment.</span></span> <span data-ttu-id="84136-173">Chỉnh sửa chúng khi cần hoặc chọn **Chạy** để bắt đầu quá trình hợp nhất dữ liệu và tạo ra thực thể khách hàng hợp nhất.</span><span class="sxs-lookup"><span data-stu-id="84136-173">Edit them as needed or select **Run** to start the data unification process and create the unified customer entity.</span></span>

<span data-ttu-id="84136-174">Khi quá trình hợp nhất dữ liệu hoàn tất, hãy chuyển đến **Biện pháp** và **Phân khúc** để đồng thời làm mới những dữ liệu này.</span><span class="sxs-lookup"><span data-stu-id="84136-174">When the data unification is complete, go to **Measures** and **Segments** to refresh them too.</span></span>

## <a name="edit-an-existing-environment"></a><span data-ttu-id="84136-175">Chỉnh sửa môi trường hiện có</span><span class="sxs-lookup"><span data-stu-id="84136-175">Edit an existing environment</span></span>

<span data-ttu-id="84136-176">Bạn có thể chỉnh sửa một số thông tin của các môi trường hiện có.</span><span class="sxs-lookup"><span data-stu-id="84136-176">You can edit some of the details of existing environments.</span></span>

1. <span data-ttu-id="84136-177">Truy cập **Quản trị viên** > **Hệ thống** > **Giới thiệu**.</span><span class="sxs-lookup"><span data-stu-id="84136-177">Go to **Admin** > **System** > **About**.</span></span>

2. <span data-ttu-id="84136-178">Chọn **Chỉnh sửa**.</span><span class="sxs-lookup"><span data-stu-id="84136-178">Select **Edit**.</span></span>

3. <span data-ttu-id="84136-179">Bạn có thể cập nhật **Tên hiển thị** của môi trường nhưng không thể thay đổi **Vùng** hoặc **Loại**.</span><span class="sxs-lookup"><span data-stu-id="84136-179">You can update the environment's **Display name**, but you can't change the **Region** or **Type**.</span></span>

4. <span data-ttu-id="84136-180">Nếu chọn lưu trữ dữ liệu của môi trường trong Azure Data Lake Storage thế hệ 2 thì bạn có thể thay đổi **Mã tài khoản**.</span><span class="sxs-lookup"><span data-stu-id="84136-180">If an environment is configured to store data in Azure Data Lake Storage Gen2, you can update the **Account key**.</span></span> <span data-ttu-id="84136-181">Tuy nhiên, bạn không thể thay đổi **Tên tài khoản** hoặc tên **Vùng chứa** .</span><span class="sxs-lookup"><span data-stu-id="84136-181">However, you can't change the **Account name** or **Container** name.</span></span>

5. <span data-ttu-id="84136-182">Theo tùy chọn, bạn có thể cập nhật từ kết nối dựa trên khóa tài khoản thành kết nối dựa trên tài nguyên hoặc dựa trên đăng ký.</span><span class="sxs-lookup"><span data-stu-id="84136-182">Optionally, you can update from an account key based connection to a resource-based or subscription-based connection.</span></span> <span data-ttu-id="84136-183">Sau khi nâng cấp, bạn không thể hoàn nguyên về khóa tài khoản sau khi cập nhật.</span><span class="sxs-lookup"><span data-stu-id="84136-183">Once upgraded, you cannot revert to account key after the update.</span></span> <span data-ttu-id="84136-184">Để biết thêm thông tin, hãy xem [Kết nối thông tin chuyên sâu về đối tượng với tài khoản Azure Data Lake Storage Gen2 có dịch vụ chính Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="84136-184">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="84136-185">Bạn không thể thay đổi thông tin **Vùng chứa** khi cập nhật kết nối.</span><span class="sxs-lookup"><span data-stu-id="84136-185">You can't change **Container** information when updating the connection.</span></span>

## <a name="reset-an-existing-environment"></a><span data-ttu-id="84136-186">Đặt lại môi trường hiện có</span><span class="sxs-lookup"><span data-stu-id="84136-186">Reset an existing environment</span></span>

<span data-ttu-id="84136-187">Bạn có thể đặt lại một môi trường về trạng thái trống nếu bạn muốn xóa tất cả các cấu hình và xóa dữ liệu đã nhập.</span><span class="sxs-lookup"><span data-stu-id="84136-187">You can reset an environment to an empty state if you want to delete all configurations and remove the ingested data.</span></span>

1.  <span data-ttu-id="84136-188">Truy cập **Quản trị viên** > **Hệ thống** > **Giới thiệu**.</span><span class="sxs-lookup"><span data-stu-id="84136-188">Go to **Admin** > **System** > **About**.</span></span>

2.  <span data-ttu-id="84136-189">Chọn **Đặt lại**.</span><span class="sxs-lookup"><span data-stu-id="84136-189">Select **Reset**.</span></span> 

3.  <span data-ttu-id="84136-190">Để xác nhận việc xóa, hãy nhập tên môi trường và chọn **Đặt lại**.</span><span class="sxs-lookup"><span data-stu-id="84136-190">To confirm the deletion, enter the environment name and select **Reset**.</span></span>


## <a name="delete-an-existing-environment"></a><span data-ttu-id="84136-191">Xóa môi trường hiện có</span><span class="sxs-lookup"><span data-stu-id="84136-191">Delete an existing environment</span></span>

1. <span data-ttu-id="84136-192">Truy cập **Quản trị viên** > **Hệ thống** > **Giới thiệu**.</span><span class="sxs-lookup"><span data-stu-id="84136-192">Go to **Admin** > **System** > **About**.</span></span>

1. <span data-ttu-id="84136-193">Chọn **Xóa**.</span><span class="sxs-lookup"><span data-stu-id="84136-193">Select **Delete**.</span></span>

1. <span data-ttu-id="84136-194">Để xác nhận thao tác xóa, hãy nhập tên môi trường rồi chọn **Xóa**.</span><span class="sxs-lookup"><span data-stu-id="84136-194">To confirm the deletion, enter the environment name and select **Delete**.</span></span>
