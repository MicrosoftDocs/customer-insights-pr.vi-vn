---
title: Mô hình máy học tùy chỉnh | Microsoft Docs
description: Làm việc với các mô hình tùy chỉnh của Azure Machine Learning trong Dynamics 365 Customer Insights.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 87fb517e9f0b380f9721f77470dceb3bcb7e5616
ms.sourcegitcommit: 55c00ea61c78db7b3b54894c01afb3246dff31c8
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 03/22/2021
ms.locfileid: "5700694"
---
# <a name="custom-machine-learning-models"></a><span data-ttu-id="b6528-103">Mô hình máy học tùy chỉnh</span><span class="sxs-lookup"><span data-stu-id="b6528-103">Custom machine learning models</span></span>

<span data-ttu-id="b6528-104">**Thông tin** > **Mô hình tùy chỉnh** cho phép bạn quản lý quy trình công việc dựa trên mô hình Azure Machine Learning.</span><span class="sxs-lookup"><span data-stu-id="b6528-104">**Intelligence** > **Custom models** lets you manage workflows based on Azure Machine Learning models.</span></span> <span data-ttu-id="b6528-105">Quy trình làm việc giúp bạn chọn dữ liệu bạn muốn tạo thông tin chi tiết và ánh xạ kết quả với dữ liệu khách hàng hợp nhất của bạn.</span><span class="sxs-lookup"><span data-stu-id="b6528-105">Workflows help you choose the data you want to generate insights from and map the results to your unified customer data.</span></span> <span data-ttu-id="b6528-106">Để biết thêm thông tin về cách xây dựng mô hình ML tùy chỉnh, hãy xem [Sử dụng các mô hình dựa trên Azure Machine Learning](azure-machine-learning-experiments.md).</span><span class="sxs-lookup"><span data-stu-id="b6528-106">For more information about building custom ML models, see [Use Azure Machine Learning-based models](azure-machine-learning-experiments.md).</span></span>

## <a name="responsible-ai"></a><span data-ttu-id="b6528-107">AI có trách nhiệm</span><span class="sxs-lookup"><span data-stu-id="b6528-107">Responsible AI</span></span>

<span data-ttu-id="b6528-108">Dự đoán cung cấp các khả năng để tạo ra trải nghiệm khách hàng tốt hơn, cải thiện khả năng kinh doanh và luồng doanh thu.</span><span class="sxs-lookup"><span data-stu-id="b6528-108">Predictions offer capabilities to create better customer experiences, improve business capabilities, and revenue streams.</span></span> <span data-ttu-id="b6528-109">Chúng tôi thực sự khuyên bạn nên cân bằng giá trị của dự đoán so với tác động của nó và những thành kiến có thể được đưa ra theo cách có đạo đức.</span><span class="sxs-lookup"><span data-stu-id="b6528-109">We strongly recommend you balance the value of your prediction against the impact it has and biases that may be introduced in an ethical manner.</span></span> <span data-ttu-id="b6528-110">Tìm hiểu thêm về cách Microsoft [giải quyết AI có trách nhiệm](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span><span class="sxs-lookup"><span data-stu-id="b6528-110">Learn more about how Microsoft is [addressing Responsible AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span></span> <span data-ttu-id="b6528-111">Bạn cũng có thể tìm hiểu về [kỹ thuật và quy trình cho máy học chịu trách nhiệm](/azure/machine-learning/concept-responsible-ml) cụ thể cho Azure Machine Learning.</span><span class="sxs-lookup"><span data-stu-id="b6528-111">You can also learn about [techniques and processes for responsible machine learning](/azure/machine-learning/concept-responsible-ml) specific to Azure Machine Learning.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b6528-112">Điều kiện tiên quyết</span><span class="sxs-lookup"><span data-stu-id="b6528-112">Prerequisites</span></span>

- <span data-ttu-id="b6528-113">Hiện tại, tính năng này hỗ trợ các dịch vụ web được xuất bản thông qua [Machine Learning Studio (cổ điển)](https://studio.azureml.net) và [quy trình hàng loạt Azure Machine Learning](/azure/machine-learning/concept-ml-pipelines).</span><span class="sxs-lookup"><span data-stu-id="b6528-113">Currently, this feature supports web services published through [Machine Learning Studio (classic)](https://studio.azureml.net) and [Azure Machine Learning batch pipelines](/azure/machine-learning/concept-ml-pipelines).</span></span>

- <span data-ttu-id="b6528-114">Bạn cần có tài khoản lưu trữ Azure Data Lake Gen2 được liên kết với phiên bản Azure Studio của bạn để sử dụng tính năng này.</span><span class="sxs-lookup"><span data-stu-id="b6528-114">You need an Azure Data Lake Gen2 storage account associated with your Azure Studio instance to use this feature.</span></span> <span data-ttu-id="b6528-115">Để biết thêm thông tin, hãy xem [Tạo tài khoản Azure Data Lake Storage thế hệ 2](/azure/storage/blobs/data-lake-storage-quickstart-create-account).</span><span class="sxs-lookup"><span data-stu-id="b6528-115">For more information, see [Create an Azure Data Lake Storage Gen2 storage account](/azure/storage/blobs/data-lake-storage-quickstart-create-account).</span></span>

- <span data-ttu-id="b6528-116">Đối với không gian làm việc Máy học Azure có quy trình, bạn cần quyền của chủ sở hữu hoặc quản trị viên quyền truy cập của người dùng vào không gian làm việc máy học Azure.</span><span class="sxs-lookup"><span data-stu-id="b6528-116">For Azure Machine Learning workspaces with pipelines, you need Owner or User Access Administrator permissions to the Azure Machine Learning Workspace.</span></span>

   > [!NOTE]
   > <span data-ttu-id="b6528-117">Dữ liệu được chuyển giữa các phiên bản Customer Insights của bạn và các dịch vụ web Azure hoặc quy trình đã chọn trong quy trình làm việc.</span><span class="sxs-lookup"><span data-stu-id="b6528-117">Data is transferred between your Customer Insights instances and the selected Azure web services or pipelines in the workflow.</span></span> <span data-ttu-id="b6528-118">Khi bạn chuyển dữ liệu sang dịch vụ Azure, vui lòng đảm bảo rằng dịch vụ được đặt cấu hình để xử lý dữ liệu theo cách thức và vị trí cần thiết để tuân thủ mọi yêu cầu pháp lý hoặc quy định đối với dữ liệu đó cho tổ chức của bạn.</span><span class="sxs-lookup"><span data-stu-id="b6528-118">When you transfer data to an Azure service, please ensure that service is configured to process data in the manner and location necessary to comply with any legal or regulatory requirements for that data for your organization.</span></span>

## <a name="add-a-new-workflow"></a><span data-ttu-id="b6528-119">Thêm quy trình mới</span><span class="sxs-lookup"><span data-stu-id="b6528-119">Add a new workflow</span></span>

1. <span data-ttu-id="b6528-120">Chuyển đến **Thông tin** > **Mô hình tùy chỉnh** rồi chọn **Quy trình làm việc mới**.</span><span class="sxs-lookup"><span data-stu-id="b6528-120">Go to **Intelligence** > **Custom models** and select **New workflow**.</span></span>

1. <span data-ttu-id="b6528-121">Đặt cho mô hình tùy chỉnh một tên dễ nhận ra trong trường **Tên**.</span><span class="sxs-lookup"><span data-stu-id="b6528-121">Give your custom model a recognizable name in the **Name** field.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b6528-122">![Ảnh chụp màn hình ngăn quy trình làm việc mới](media/new-workflowv2.png "Ảnh chụp màn hình ngăn Quy trình làm việc mới")</span><span class="sxs-lookup"><span data-stu-id="b6528-122">![Screenshot of the New workflow pane](media/new-workflowv2.png "Screenshot of the New workflow pane")</span></span>

1. <span data-ttu-id="b6528-123">Chọn tổ chức chứa dịch vụ web trong **Đối tượng thuê chứa dịch vụ web**.</span><span class="sxs-lookup"><span data-stu-id="b6528-123">Select the organization that contains the web service in **Tenant that contains your web service**.</span></span>

1. <span data-ttu-id="b6528-124">Nếu đăng ký Azure Machine Learning khác với đối tượng thuê trong Customer Insights, hãy chọn **Đăng nhập** bằng thông tin đăng nhập của bạn cho tổ chức đã chọn.</span><span class="sxs-lookup"><span data-stu-id="b6528-124">If your Azure Machine Learning subscription is in a different tenant than Customer Insights, select **Sign in** with your credentials for the selected organization.</span></span>

1. <span data-ttu-id="b6528-125">Chọn **Không gian làm việc** được liên kết với dịch vụ web của bạn.</span><span class="sxs-lookup"><span data-stu-id="b6528-125">Select the **Workspaces** associated with your web service.</span></span> <span data-ttu-id="b6528-126">Có hai phần được liệt kê, một dành cho Azure Machine Learning v1 (Machine Learning Studio (cổ điển)) và Azure Machine Learning v2 (Azure Machine Learning).</span><span class="sxs-lookup"><span data-stu-id="b6528-126">There are two sections listed, one for Azure Machine Learning v1 (Machine Learning Studio (classic)) and Azure Machine Learning v2 (Azure Machine Learning).</span></span> <span data-ttu-id="b6528-127">Nếu bạn không chắc không gian làm việc nào phù hợp với dịch vụ web Machine Learning Studio (cổ điển) của mình, hãy chọn **Bất kì**.</span><span class="sxs-lookup"><span data-stu-id="b6528-127">If you're not sure which workspace is the right one for your Machine Learning Studio (classic) web service, select **Any**.</span></span>

1. <span data-ttu-id="b6528-128">Chọn dịch vụ web Machine Learning Studio (cổ điển) hoặc quy trình Azure Machine Learning trong menu thả xuống **Dịch vụ web chứa mô hình của bạn**.</span><span class="sxs-lookup"><span data-stu-id="b6528-128">Choose the Machine Learning Studio (classic) web service or Azure Machine Learning pipeline in the **Web service that contains your model** dropdown.</span></span> <span data-ttu-id="b6528-129">Sau đó, chọn **Tiếp**.</span><span class="sxs-lookup"><span data-stu-id="b6528-129">Then, select **Next**.</span></span>
   - <span data-ttu-id="b6528-130">Tìm hiểu thêm về [phát hành một dịch vụ web trong Machine Learning Studio (cổ điển)](/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span><span class="sxs-lookup"><span data-stu-id="b6528-130">Learn more about [publishing a web service in Machine Learning Studio (classic)](/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span></span>
   - <span data-ttu-id="b6528-131">Tìm hiểu thêm về [phát hành một quy trình trong Azure Machine Learning bằng cách sử dụng trình thiết kế](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) hoặc [SDK](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span><span class="sxs-lookup"><span data-stu-id="b6528-131">Learn more about [publishing a pipeline in Azure Machine Learning using the designer](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) or [SDK](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span></span> <span data-ttu-id="b6528-132">Quy trình của bạn phải được thiết kế theo [điểm cuối quy trình](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span><span class="sxs-lookup"><span data-stu-id="b6528-132">Your pipeline must be published under a [pipeline endpoint](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span></span>

1. <span data-ttu-id="b6528-133">Đối với mỗi **Đầu vào dịch vụ web**, chọn **Thực thể** phù hợp từ thông tin chi tiết về đối tượng và chọn **Tiếp theo**.</span><span class="sxs-lookup"><span data-stu-id="b6528-133">For each **Web service input**, select the matching **Entity** from audience insights and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="b6528-134">Quy trình làm việc của mô hình tùy chỉnh sẽ áp dụng phương pháp phỏng đoán để ánh xạ các trường đầu vào của dịch vụ web với các thuộc tính thực thể dựa trên tên và kiểu dữ liệu của trường.</span><span class="sxs-lookup"><span data-stu-id="b6528-134">The custom model workflow will apply heuristics to map the web service input fields to the entity attributes based on the name and data type of the field.</span></span> <span data-ttu-id="b6528-135">Bạn sẽ thấy lỗi nếu không thể ánh xạ trường dịch vụ web tới một thực thể.</span><span class="sxs-lookup"><span data-stu-id="b6528-135">You'll see an error if a web service field can't be mapped to an entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b6528-136">![Đặt cấu hình cho quy trình](media/intelligence-screen2-updated.png "Đặt cấu hình cho quy trình")</span><span class="sxs-lookup"><span data-stu-id="b6528-136">![Configure a workflow](media/intelligence-screen2-updated.png "Configure a workflow")</span></span>

1. <span data-ttu-id="b6528-137">Trong bước **Tham số đầu ra mô hình**, đặt các thuộc tính sau:</span><span class="sxs-lookup"><span data-stu-id="b6528-137">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="b6528-138">Machine Learning Studio (cổ điển)</span><span class="sxs-lookup"><span data-stu-id="b6528-138">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="b6528-139">Nhập **Tên thực thể** đầu ra mà bạn muốn kết quả đầu ra của dịch vụ web chuyển vào.</span><span class="sxs-lookup"><span data-stu-id="b6528-139">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="b6528-140">Máy học của Azure</span><span class="sxs-lookup"><span data-stu-id="b6528-140">Azure Machine Learning</span></span>
      1. <span data-ttu-id="b6528-141">Nhập **Tên thực thể** đầu ra mà bạn muốn kết quả đầu ra của quy trình làm việc chuyển vào.</span><span class="sxs-lookup"><span data-stu-id="b6528-141">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="b6528-142">Chọn **Tên tham số đầu ra kho dữ liệu** của quy trình hàng loạt của bạn từ menu thả xuống.</span><span class="sxs-lookup"><span data-stu-id="b6528-142">Select the **Output data store parameter name** of your batch pipeline from the dropdown.</span></span>
      1. <span data-ttu-id="b6528-143">Chọn **Tên tham số đường dẫn đầu ra** của quy trình hàng loạt của bạn từ menu thả xuống.</span><span class="sxs-lookup"><span data-stu-id="b6528-143">Select the **Output Path parameter name** of your batch pipeline from the dropdown.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="b6528-144">![Ngăn tham số đầu ra của mô hình](media/intelligence-screen3-outputparameters.png "Ngăn tham số đầu ra của mô hình")</span><span class="sxs-lookup"><span data-stu-id="b6528-144">![Model Output Parameter Pane](media/intelligence-screen3-outputparameters.png "Model Output Parameter Pane")</span></span>

1. <span data-ttu-id="b6528-145">Chọn thuộc tính kết hợp từ danh sách thả xuống **ID khách hàng trong kết quả** xác định khách hàng và chọn **Lưu**.</span><span class="sxs-lookup"><span data-stu-id="b6528-145">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b6528-146">![Liên kết kết quả với ngăn Dữ liệu khách hàng](media/intelligence-screen4-relatetocustomer.png "Liên kết kết quả với ngăn Dữ liệu khách hàng")</span><span class="sxs-lookup"><span data-stu-id="b6528-146">![Relate results to Customer data pane](media/intelligence-screen4-relatetocustomer.png "Relate results to Customer data pane")</span></span>

1. <span data-ttu-id="b6528-147">Bạn sẽ nhìn thấy màn hình **Quy trình làm việc được lưu** có thông tin chi tiết về quy trình làm việc.</span><span class="sxs-lookup"><span data-stu-id="b6528-147">You'll see the **Workflow Saved** screen with details about the workflow.</span></span>    
   <span data-ttu-id="b6528-148">Nếu bạn đã định cấu hình quy trình làm việc cho quy trình Azure Machine Learning, thông tin chi tiết về đối tượng sẽ đính kèm vào không gian làm việc chứa quy trình.</span><span class="sxs-lookup"><span data-stu-id="b6528-148">If you configured a workflow for an Azure Machine Learning pipeline, audience insights will attach to the workspace that contains the pipeline.</span></span> <span data-ttu-id="b6528-149">Thông tin chi tiết về đối tượng sẽ nhận được vai trò **Cộng tác viên** trên không gian làm việc Azure.</span><span class="sxs-lookup"><span data-stu-id="b6528-149">Audience insights will get a **Contributor** role on the Azure workspace.</span></span>

1. <span data-ttu-id="b6528-150">Chọn **Xong**.</span><span class="sxs-lookup"><span data-stu-id="b6528-150">Select **Done**.</span></span>

1. <span data-ttu-id="b6528-151">Bây giờ bạn có thể chạy quy trình làm việc từ trang **Mô hình tùy chỉnh**.</span><span class="sxs-lookup"><span data-stu-id="b6528-151">You can now run the workflow from the **Custom Models** page.</span></span>

## <a name="edit-a-workflow"></a><span data-ttu-id="b6528-152">Chỉnh sửa quy trình</span><span class="sxs-lookup"><span data-stu-id="b6528-152">Edit a workflow</span></span>

1. <span data-ttu-id="b6528-153">Trên trang **Mô hình tùy chỉnh**, chọn dấu 3 chấm dọc trong cột **Hành động** cạnh quy trình bạn đã tạo trước đó rồi chọn **Chính sửa**.</span><span class="sxs-lookup"><span data-stu-id="b6528-153">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created and select **Edit**.</span></span>

1. <span data-ttu-id="b6528-154">Bạn có thể cập nhật tên dễ nhận biết của quy trình làm việc của mình trong trường **Tên hiển thị** nhưng bạn không thể thay đổi quy trình hoặc dịch vụ web đã định cấu hình.</span><span class="sxs-lookup"><span data-stu-id="b6528-154">You can update your workflow's recognizable name in the **Display name** field, but you can't change the configured web service or pipeline.</span></span> <span data-ttu-id="b6528-155">Chọn **Tiếp theo**.</span><span class="sxs-lookup"><span data-stu-id="b6528-155">Select **Next**.</span></span>

1. <span data-ttu-id="b6528-156">Đối với mỗi **Đầu vào dịch vụ web**, bạn có thể cập nhật **Thực thể** phù hợp từ thông tin chi tiết về đối tượng.</span><span class="sxs-lookup"><span data-stu-id="b6528-156">For each **Web service input**, you can update the matching **Entity** from audience insights.</span></span> <span data-ttu-id="b6528-157">Sau đó, chọn **Tiếp**.</span><span class="sxs-lookup"><span data-stu-id="b6528-157">Then, select **Next**.</span></span>

1. <span data-ttu-id="b6528-158">Trong bước **Tham số đầu ra mô hình**, đặt các thuộc tính sau:</span><span class="sxs-lookup"><span data-stu-id="b6528-158">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="b6528-159">Machine Learning Studio (cổ điển)</span><span class="sxs-lookup"><span data-stu-id="b6528-159">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="b6528-160">Nhập **Tên thực thể** đầu ra mà bạn muốn kết quả đầu ra của dịch vụ web chuyển vào.</span><span class="sxs-lookup"><span data-stu-id="b6528-160">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="b6528-161">Máy học của Azure</span><span class="sxs-lookup"><span data-stu-id="b6528-161">Azure Machine Learning</span></span>
      1. <span data-ttu-id="b6528-162">Nhập **Tên thực thể** đầu ra mà bạn muốn kết quả đầu ra của quy trình làm việc chuyển vào.</span><span class="sxs-lookup"><span data-stu-id="b6528-162">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="b6528-163">Chọn **Tên tham số kho dữ liệu đầu ra** cho quy trình thử nghiệm của bạn.</span><span class="sxs-lookup"><span data-stu-id="b6528-163">Select the **Output data store parameter name** for your test pipeline.</span></span>
      1. <span data-ttu-id="b6528-164">Chọn **Tên tham số đường dẫn đầu ra** cho quy trình thử nghiệm của bạn.</span><span class="sxs-lookup"><span data-stu-id="b6528-164">Select the **Output Path parameter name** for your test pipeline.</span></span>

1. <span data-ttu-id="b6528-165">Chọn thuộc tính kết hợp từ danh sách thả xuống **ID khách hàng trong kết quả** xác định khách hàng và chọn **Lưu**.</span><span class="sxs-lookup"><span data-stu-id="b6528-165">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   <span data-ttu-id="b6528-166">Chọn một thuộc tính từ đầu ra suy luận có giá trị tương tự như cột ID khách hàng của thực thể Khách hàng.</span><span class="sxs-lookup"><span data-stu-id="b6528-166">Choose an attribute from the inference output with values similar to the Customer ID column of the Customer entity.</span></span> <span data-ttu-id="b6528-167">Nếu không có cột như vậy trong tập hợp dữ liệu của bạn, hãy chọn một thuộc tính xác định duy nhất hàng.</span><span class="sxs-lookup"><span data-stu-id="b6528-167">If don't have such a column in your data set, choose an attribute that uniquely identifies the row.</span></span>

## <a name="run-a-workflow"></a><span data-ttu-id="b6528-168">Chạy quy trình</span><span class="sxs-lookup"><span data-stu-id="b6528-168">Run a workflow</span></span>

1. <span data-ttu-id="b6528-169">Trên trang **Mô hình tùy chỉnh**, chọn dấu 3 chấm dọc trong cột **Hành động** cạnh quy trình bạn vừa tạo trước đó.</span><span class="sxs-lookup"><span data-stu-id="b6528-169">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="b6528-170">Chọn **Chạy**.</span><span class="sxs-lookup"><span data-stu-id="b6528-170">Select **Run**.</span></span>

<span data-ttu-id="b6528-171">Quy trình làm việc cũng chạy tự động với mỗi lần làm mới theo lịch trình.</span><span class="sxs-lookup"><span data-stu-id="b6528-171">Your workflow also runs automatically with every scheduled refresh.</span></span> <span data-ttu-id="b6528-172">Tìm hiểu thêm về [cách thiết lập các lần làm mới theo lịch](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="b6528-172">Learn more about [setting up scheduled refreshes](system.md#schedule-tab).</span></span>

## <a name="delete-a-workflow"></a><span data-ttu-id="b6528-173">Xóa quy trình</span><span class="sxs-lookup"><span data-stu-id="b6528-173">Delete a workflow</span></span>

1. <span data-ttu-id="b6528-174">Trên trang **Mô hình tùy chỉnh**, chọn dấu 3 chấm dọc trong cột **Hành động** cạnh quy trình bạn vừa tạo trước đó.</span><span class="sxs-lookup"><span data-stu-id="b6528-174">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="b6528-175">Chọn **Xóa** rồi xác nhận tác vụ xóa của bạn.</span><span class="sxs-lookup"><span data-stu-id="b6528-175">Select **Delete** and confirm your deletion.</span></span>

<span data-ttu-id="b6528-176">Quy trình của bạn sẽ bị xóa.</span><span class="sxs-lookup"><span data-stu-id="b6528-176">Your workflow will be deleted.</span></span> <span data-ttu-id="b6528-177">[Thực thể](entities.md) đã được tạo khi bạn tạo quy trình sẽ vẫn tồn tại, và bạn có thể xem thực thể trên trang **Thực thể**.</span><span class="sxs-lookup"><span data-stu-id="b6528-177">The [entity](entities.md) that was created when you created the workflow persists, and can be viewed from the **Entities** page.</span></span>

## <a name="results"></a><span data-ttu-id="b6528-178">Kết quả</span><span class="sxs-lookup"><span data-stu-id="b6528-178">Results</span></span>

<span data-ttu-id="b6528-179">Kết quả từ quy trình làm việc được lưu trữ trong thực thể được định cấu hình trong giai đoạn Tham số đầu ra mô hình.</span><span class="sxs-lookup"><span data-stu-id="b6528-179">Results from a workflow are stored in the entity configured during the Model Output Parameter phase.</span></span> <span data-ttu-id="b6528-180">Bạn có thể truy cập dữ liệu này từ [trang thực thể](entities.md) hoặc với [Quyền truy cập API](apis.md).</span><span class="sxs-lookup"><span data-stu-id="b6528-180">You can access this data from the [entities page](entities.md) or with [API access](apis.md).</span></span>

### <a name="api-access"></a><span data-ttu-id="b6528-181">Truy cập API</span><span class="sxs-lookup"><span data-stu-id="b6528-181">API Access</span></span>

<span data-ttu-id="b6528-182">Đối với truy vấn OData cụ thể để lấy dữ liệu từ thực thể mô hình tùy chỉnh, hãy sử dụng định dạng sau:</span><span class="sxs-lookup"><span data-stu-id="b6528-182">For the specific OData query to get data from a custom model entity, use the following format:</span></span>

`https://api.ci.ai.dynamics.com/v1/instances/<your instance id>/data/<custom model output entity name>%3Ffilter%3DCustomerId%20eq%20'<guid value>'`

1. <span data-ttu-id="b6528-183">Thay thế`<your instance id>` bằng ID của môi trường Customer Insights mà bạn tìm thấy trong thanh địa chỉ của trình duyệt khi truy cập Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="b6528-183">Replace `<your instance id>` with the ID of your Customer Insights environment, which you find in the in the address bar of your browser when accessing Customer Insights.</span></span>

1. <span data-ttu-id="b6528-184">Thay thế `<custom model output entity>` bằng tên thực thể bạn đã cung cấp trong bước Tham số đầu ra mô hình của cấu hình mô hình tùy chỉnh.</span><span class="sxs-lookup"><span data-stu-id="b6528-184">Replace `<custom model output entity>` with the entity name you provided during the Model Output Parameters step of the custom model configuration.</span></span>

1. <span data-ttu-id="b6528-185">Thay thế `<guid value>` bằng ID khách hàng của khách hàng mà bạn muốn truy cập vào hồ sơ.</span><span class="sxs-lookup"><span data-stu-id="b6528-185">Replace `<guid value>` with the Customer ID of the customer you'd like to access the record for.</span></span> <span data-ttu-id="b6528-186">Bạn thường có thể tìm thấy ID này trên [trang hồ sơ khách hàng](customer-profiles.md) trong trường CustomerID.</span><span class="sxs-lookup"><span data-stu-id="b6528-186">You can usually find this ID on the [customer profiles page](customer-profiles.md) in the CustomerID field.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="b6528-187">Câu hỏi Thường Gặp</span><span class="sxs-lookup"><span data-stu-id="b6528-187">Frequently Asked Questions</span></span>

- <span data-ttu-id="b6528-188">Tại sao tôi không thể thấy đường dẫn của mình khi thiết lập quy trình làm việc của mô hình tùy chỉnh?</span><span class="sxs-lookup"><span data-stu-id="b6528-188">Why can't I see my pipeline when setting up a custom model workflow?</span></span>    
  <span data-ttu-id="b6528-189">Sự cố này thường do sự cố cấu hình trong quy trình gây ra.</span><span class="sxs-lookup"><span data-stu-id="b6528-189">This issue is frequently caused by a configuration issue in the pipeline.</span></span> <span data-ttu-id="b6528-190">Đảm bảo [tham số đầu vào được định cấu hình](azure-machine-learning-experiments.md#dataset-configuration), và [tham số đường dẫn và kho dữ liệu đầu ra](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights) cũng được định cấu hình.</span><span class="sxs-lookup"><span data-stu-id="b6528-190">Ensure the [input parameter is configured](azure-machine-learning-experiments.md#dataset-configuration), and the [output datastore and path parameters](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights) are also configured.</span></span>

- <span data-ttu-id="b6528-191">Lỗi "Không thể lưu quy trình làm việc thông minh" có nghĩa là gì?</span><span class="sxs-lookup"><span data-stu-id="b6528-191">What does the error "Couldn't save intelligence workflow" mean?</span></span>    
  <span data-ttu-id="b6528-192">Người dùng thường thấy thông báo lỗi này nếu họ không có quyền của Chủ sở hữu hoặc Quản trị viên quyền truy cập của người dùng trên không gian làm việc.</span><span class="sxs-lookup"><span data-stu-id="b6528-192">Users usually see this error message if they don't have Owner or User Access Administrator privileges on the workspace.</span></span> <span data-ttu-id="b6528-193">Người dùng cần cấp quyền cao hơn để cho phép Customer Insights xử lý quy trình làm việc như một dịch vụ thay vì sử dụng thông tin đăng nhập của người dùng cho các lần chạy quy trình công việc tiếp theo.</span><span class="sxs-lookup"><span data-stu-id="b6528-193">The user needs a higher level of permissions to enable Customer Insights to process the workflow as a service rather than using the user credentials for subsequent runs of the workflow.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
