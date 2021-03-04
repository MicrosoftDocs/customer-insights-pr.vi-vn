---
title: Mô hình máy học tùy chỉnh | Microsoft Docs
description: Làm việc với các mô hình tùy chỉnh của Azure Machine Learning trong Dynamics 365 Customer Insights.
ms.date: 11/19/2020
ms.reviewer: zacook
ms.service: dynamics-365-ai
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 34489faaecc5da1ce3dd68d799b3e0e0d9672ab7
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267260"
---
# <a name="custom-machine-learning-models"></a><span data-ttu-id="b27f8-103">Mô hình máy học tùy chỉnh</span><span class="sxs-lookup"><span data-stu-id="b27f8-103">Custom machine learning models</span></span>

<span data-ttu-id="b27f8-104">**Thông tin** > **Mô hình tùy chỉnh** cho phép bạn quản lý quy trình công việc dựa trên mô hình Azure Machine Learning.</span><span class="sxs-lookup"><span data-stu-id="b27f8-104">**Intelligence** > **Custom models** lets you manage workflows based on Azure Machine Learning models.</span></span> <span data-ttu-id="b27f8-105">Quy trình làm việc giúp bạn chọn dữ liệu bạn muốn tạo thông tin chi tiết và ánh xạ kết quả với dữ liệu khách hàng hợp nhất của bạn.</span><span class="sxs-lookup"><span data-stu-id="b27f8-105">Workflows help you choose the data you want to generate insights from and map the results to your unified customer data.</span></span> <span data-ttu-id="b27f8-106">Để biết thêm thông tin về cách xây dựng mô hình ML tùy chỉnh, hãy xem [Sử dụng các mô hình dựa trên Azure Machine Learning](azure-machine-learning-experiments.md).</span><span class="sxs-lookup"><span data-stu-id="b27f8-106">For more information about building custom ML models, see [Use Azure Machine Learning-based models](azure-machine-learning-experiments.md).</span></span>

## <a name="responsible-ai"></a><span data-ttu-id="b27f8-107">AI có trách nhiệm</span><span class="sxs-lookup"><span data-stu-id="b27f8-107">Responsible AI</span></span>

<span data-ttu-id="b27f8-108">Dự đoán cung cấp các khả năng để tạo ra trải nghiệm khách hàng tốt hơn, cải thiện khả năng kinh doanh và luồng doanh thu.</span><span class="sxs-lookup"><span data-stu-id="b27f8-108">Predictions offer capabilities to create better customer experiences, improve business capabilities, and revenue streams.</span></span> <span data-ttu-id="b27f8-109">Chúng tôi thực sự khuyên bạn nên cân bằng giá trị của dự đoán so với tác động của nó và những thành kiến có thể được đưa ra theo cách có đạo đức.</span><span class="sxs-lookup"><span data-stu-id="b27f8-109">We strongly recommend you balance the value of your prediction against the impact it has and biases that may be introduced in an ethical manner.</span></span> <span data-ttu-id="b27f8-110">Tìm hiểu thêm về cách Microsoft [giải quyết AI có trách nhiệm](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span><span class="sxs-lookup"><span data-stu-id="b27f8-110">Learn more about how Microsoft is [addressing Responsible AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span></span> <span data-ttu-id="b27f8-111">Bạn cũng có thể tìm hiểu về [kỹ thuật và quy trình cho máy học chịu trách nhiệm](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) cụ thể cho Azure Machine Learning.</span><span class="sxs-lookup"><span data-stu-id="b27f8-111">You can also learn about [techniques and processes for responsible machine learning](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) specific to Azure Machine Learning.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b27f8-112">Điều kiện tiên quyết</span><span class="sxs-lookup"><span data-stu-id="b27f8-112">Prerequisites</span></span>

- <span data-ttu-id="b27f8-113">Hiện tại, tính năng này hỗ trợ các dịch vụ web được xuất bản thông qua [Machine Learning Studio (cổ điển)](https://studio.azureml.net) và [quy trình hàng loạt Azure Machine Learning](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).</span><span class="sxs-lookup"><span data-stu-id="b27f8-113">Currently, this feature supports web services published through [Machine Learning Studio (classic)](https://studio.azureml.net) and [Azure Machine Learning batch pipelines](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).</span></span>

- <span data-ttu-id="b27f8-114">Bạn cần có tài khoản lưu trữ Azure Data Lake Gen2 được liên kết với phiên bản Azure Studio của bạn để sử dụng tính năng này.</span><span class="sxs-lookup"><span data-stu-id="b27f8-114">You need an Azure Data Lake Gen2 storage account associated with your Azure Studio instance to use this feature.</span></span> <span data-ttu-id="b27f8-115">Để biết thêm thông tin, hãy xem [Tạo tài khoản Azure Data Lake Storage thế hệ 2](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)</span><span class="sxs-lookup"><span data-stu-id="b27f8-115">For more information, see [Create an Azure Data Lake Storage Gen2 storage account](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)</span></span>

## <a name="add-a-new-workflow"></a><span data-ttu-id="b27f8-116">Thêm quy trình mới</span><span class="sxs-lookup"><span data-stu-id="b27f8-116">Add a new workflow</span></span>

1. <span data-ttu-id="b27f8-117">Chuyển đến **Thông tin** > **Mô hình tùy chỉnh** rồi chọn **Quy trình làm việc mới**.</span><span class="sxs-lookup"><span data-stu-id="b27f8-117">Go to **Intelligence** > **Custom models** and select **New workflow**.</span></span>

1. <span data-ttu-id="b27f8-118">Đặt cho mô hình tùy chỉnh một tên dễ nhận ra trong trường **Tên**.</span><span class="sxs-lookup"><span data-stu-id="b27f8-118">Give your custom model a recognizable name in the **Name** field.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b27f8-119">![Ảnh chụp màn hình ngăn quy trình làm việc mới](media/new-workflowv2.png "Ảnh chụp màn hình ngăn Quy trình làm việc mới")</span><span class="sxs-lookup"><span data-stu-id="b27f8-119">![Screenshot of the New workflow pane](media/new-workflowv2.png "Screenshot of the New workflow pane")</span></span>

1. <span data-ttu-id="b27f8-120">Chọn tổ chức chứa dịch vụ web trong **Đối tượng thuê chứa dịch vụ web**.</span><span class="sxs-lookup"><span data-stu-id="b27f8-120">Select the organization that contains the web service in **Tenant that contains your web service**.</span></span>

1. <span data-ttu-id="b27f8-121">Nếu đăng ký Azure Machine Learning khác với đối tượng thuê trong Customer Insights, hãy chọn **Đăng nhập** bằng thông tin đăng nhập của bạn cho tổ chức đã chọn.</span><span class="sxs-lookup"><span data-stu-id="b27f8-121">If your Azure Machine Learning subscription is in a different tenant than Customer Insights, select **Sign in** with your credentials for the selected organization.</span></span>

1. <span data-ttu-id="b27f8-122">Chọn **Không gian làm việc** được liên kết với dịch vụ web của bạn.</span><span class="sxs-lookup"><span data-stu-id="b27f8-122">Select the **Workspaces** associated with your web service.</span></span> <span data-ttu-id="b27f8-123">Có hai phần được liệt kê, một dành cho Azure Machine Learning v1 (Machine Learning Studio (cổ điển)) và Azure Machine Learning v2 (Azure Machine Learning).</span><span class="sxs-lookup"><span data-stu-id="b27f8-123">There are two sections listed, one for Azure Machine Learning v1 (Machine Learning Studio (classic)) and Azure Machine Learning v2 (Azure Machine Learning).</span></span> <span data-ttu-id="b27f8-124">Nếu bạn không chắc không gian làm việc nào phù hợp với dịch vụ web Machine Learning Studio (cổ điển) của mình, hãy chọn **Bất kì**.</span><span class="sxs-lookup"><span data-stu-id="b27f8-124">If you're not sure which workspace is the right one for your Machine Learning Studio (classic) web service, select **Any**.</span></span>

1. <span data-ttu-id="b27f8-125">Chọn dịch vụ web Machine Learning Studio (cổ điển) hoặc quy trình Azure Machine Learning trong menu thả xuống **Dịch vụ web chứa mô hình của bạn**.</span><span class="sxs-lookup"><span data-stu-id="b27f8-125">Choose the Machine Learning Studio (classic) web service or Azure Machine Learning pipeline in the **Web service that contains your model** dropdown.</span></span> <span data-ttu-id="b27f8-126">Sau đó, chọn **Tiếp**.</span><span class="sxs-lookup"><span data-stu-id="b27f8-126">Then, select **Next**.</span></span>
   - <span data-ttu-id="b27f8-127">Tìm hiểu thêm về [phát hành một dịch vụ web trong Machine Learning Studio (cổ điển)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span><span class="sxs-lookup"><span data-stu-id="b27f8-127">Learn more about [publishing a web service in Machine Learning Studio (classic)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span></span>
   - <span data-ttu-id="b27f8-128">Tìm hiểu thêm về [phát hành một quy trình trong Azure Machine Learning bằng cách sử dụng trình thiết kế](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) hoặc [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span><span class="sxs-lookup"><span data-stu-id="b27f8-128">Learn more about [publishing a pipeline in Azure Machine Learning using the designer](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) or [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span></span> <span data-ttu-id="b27f8-129">Quy trình của bạn phải được thiết kế theo [điểm cuối quy trình](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span><span class="sxs-lookup"><span data-stu-id="b27f8-129">Your pipeline must be published under a [pipeline endpoint](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span></span>

1. <span data-ttu-id="b27f8-130">Đối với mỗi **Đầu vào dịch vụ web**, chọn **Thực thể** phù hợp từ thông tin chi tiết về đối tượng và chọn **Tiếp theo**.</span><span class="sxs-lookup"><span data-stu-id="b27f8-130">For each **Web service input**, select the matching **Entity** from audience insights and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="b27f8-131">Quy trình làm việc của mô hình tùy chỉnh sẽ áp dụng phương pháp phỏng đoán để ánh xạ các trường đầu vào của dịch vụ web với các thuộc tính thực thể dựa trên tên và kiểu dữ liệu của trường.</span><span class="sxs-lookup"><span data-stu-id="b27f8-131">The custom model workflow will apply heuristics to map the web service input fields to the entity attributes based on the name and data type of the field.</span></span> <span data-ttu-id="b27f8-132">Bạn sẽ thấy lỗi nếu không thể ánh xạ trường dịch vụ web tới một thực thể.</span><span class="sxs-lookup"><span data-stu-id="b27f8-132">You'll see an error if a web service field can't be mapped to an entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b27f8-133">![Đặt cấu hình cho quy trình](media/intelligence-screen2-updated.png "Đặt cấu hình cho quy trình")</span><span class="sxs-lookup"><span data-stu-id="b27f8-133">![Configure a workflow](media/intelligence-screen2-updated.png "Configure a workflow")</span></span>
   
1. <span data-ttu-id="b27f8-134">Trong bước **Tham số đầu ra mô hình**, đặt các thuộc tính sau:</span><span class="sxs-lookup"><span data-stu-id="b27f8-134">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="b27f8-135">Machine Learning Studio (cổ điển)</span><span class="sxs-lookup"><span data-stu-id="b27f8-135">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="b27f8-136">Nhập **Tên thực thể** đầu ra mà bạn muốn kết quả đầu ra của dịch vụ web chuyển vào.</span><span class="sxs-lookup"><span data-stu-id="b27f8-136">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="b27f8-137">Máy học của Azure</span><span class="sxs-lookup"><span data-stu-id="b27f8-137">Azure Machine Learning</span></span>
      1. <span data-ttu-id="b27f8-138">Nhập **Tên thực thể** đầu ra mà bạn muốn kết quả đầu ra của quy trình làm việc chuyển vào.</span><span class="sxs-lookup"><span data-stu-id="b27f8-138">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="b27f8-139">Chọn **Tên tham số đầu ra kho dữ liệu** của quy trình hàng loạt của bạn từ menu thả xuống.</span><span class="sxs-lookup"><span data-stu-id="b27f8-139">Select the **Output data store parameter name** of your batch pipeline from the dropdown.</span></span>
      1. <span data-ttu-id="b27f8-140">Chọn **Tên tham số đường dẫn đầu ra** của quy trình hàng loạt của bạn từ menu thả xuống.</span><span class="sxs-lookup"><span data-stu-id="b27f8-140">Select the **Output Path parameter name** of your batch pipeline from the dropdown.</span></span>
      
      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="b27f8-141">![Ngăn tham số đầu ra của mô hình](media/intelligence-screen3-outputparameters.png "Ngăn tham số đầu ra của mô hình")</span><span class="sxs-lookup"><span data-stu-id="b27f8-141">![Model Output Parameter Pane](media/intelligence-screen3-outputparameters.png "Model Output Parameter Pane")</span></span>

1. <span data-ttu-id="b27f8-142">Chọn thuộc tính kết hợp từ danh sách thả xuống **ID khách hàng trong kết quả** xác định khách hàng và chọn **Lưu**.</span><span class="sxs-lookup"><span data-stu-id="b27f8-142">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b27f8-143">![Liên kết kết quả với ngăn Dữ liệu khách hàng](media/intelligence-screen4-relatetocustomer.png "Liên kết kết quả với ngăn Dữ liệu khách hàng")</span><span class="sxs-lookup"><span data-stu-id="b27f8-143">![Relate results to Customer data pane](media/intelligence-screen4-relatetocustomer.png "Relate results to Customer data pane")</span></span>

1. <span data-ttu-id="b27f8-144">Bạn sẽ nhìn thấy màn hình **Quy trình làm việc được lưu** có thông tin chi tiết về quy trình làm việc.</span><span class="sxs-lookup"><span data-stu-id="b27f8-144">You'll see the **Workflow Saved** screen with details about the workflow.</span></span>    
   <span data-ttu-id="b27f8-145">Nếu bạn đã định cấu hình quy trình làm việc cho quy trình Azure Machine Learning, thông tin chi tiết về đối tượng sẽ đính kèm vào không gian làm việc chứa quy trình.</span><span class="sxs-lookup"><span data-stu-id="b27f8-145">If you configured a workflow for an Azure Machine Learning pipeline, audience insights will attach to the workspace that contains the pipeline.</span></span> <span data-ttu-id="b27f8-146">Thông tin chi tiết về đối tượng sẽ nhận được vai trò **Cộng tác viên** trên không gian làm việc Azure.</span><span class="sxs-lookup"><span data-stu-id="b27f8-146">Audience insights will get a **Contributor** role on the Azure workspace.</span></span>

1. <span data-ttu-id="b27f8-147">Chọn **Xong**.</span><span class="sxs-lookup"><span data-stu-id="b27f8-147">Select **Done**.</span></span>

1. <span data-ttu-id="b27f8-148">Bây giờ bạn có thể chạy quy trình làm việc từ trang **Mô hình tùy chỉnh**.</span><span class="sxs-lookup"><span data-stu-id="b27f8-148">You can now run the workflow from the **Custom Models** page.</span></span>

## <a name="edit-a-workflow"></a><span data-ttu-id="b27f8-149">Chỉnh sửa quy trình</span><span class="sxs-lookup"><span data-stu-id="b27f8-149">Edit a workflow</span></span>

1. <span data-ttu-id="b27f8-150">Trên trang **Mô hình tùy chỉnh**, chọn dấu 3 chấm dọc trong cột **Hành động** cạnh quy trình bạn đã tạo trước đó rồi chọn **Chính sửa**.</span><span class="sxs-lookup"><span data-stu-id="b27f8-150">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created and select **Edit**.</span></span>

1. <span data-ttu-id="b27f8-151">Bạn có thể cập nhật tên dễ nhận biết của quy trình làm việc của mình trong trường **Tên hiển thị** nhưng bạn không thể thay đổi quy trình hoặc dịch vụ web đã định cấu hình.</span><span class="sxs-lookup"><span data-stu-id="b27f8-151">You can update your workflow's recognizable name in the **Display name** field, but you can't change the configured web service or pipeline.</span></span> <span data-ttu-id="b27f8-152">Chọn **Tiếp theo**.</span><span class="sxs-lookup"><span data-stu-id="b27f8-152">Select **Next**.</span></span>

1. <span data-ttu-id="b27f8-153">Đối với mỗi **Đầu vào dịch vụ web**, bạn có thể cập nhật **Thực thể** phù hợp từ thông tin chi tiết về đối tượng.</span><span class="sxs-lookup"><span data-stu-id="b27f8-153">For each **Web service input**, you can update the matching **Entity** from audience insights.</span></span> <span data-ttu-id="b27f8-154">Sau đó, chọn **Tiếp**.</span><span class="sxs-lookup"><span data-stu-id="b27f8-154">Then, select **Next**.</span></span>

1. <span data-ttu-id="b27f8-155">Trong bước **Tham số đầu ra mô hình**, đặt các thuộc tính sau:</span><span class="sxs-lookup"><span data-stu-id="b27f8-155">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="b27f8-156">Machine Learning Studio (cổ điển)</span><span class="sxs-lookup"><span data-stu-id="b27f8-156">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="b27f8-157">Nhập **Tên thực thể** đầu ra mà bạn muốn kết quả đầu ra của dịch vụ web chuyển vào.</span><span class="sxs-lookup"><span data-stu-id="b27f8-157">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="b27f8-158">Máy học của Azure</span><span class="sxs-lookup"><span data-stu-id="b27f8-158">Azure Machine Learning</span></span>
      1. <span data-ttu-id="b27f8-159">Nhập **Tên thực thể** đầu ra mà bạn muốn kết quả đầu ra của quy trình làm việc chuyển vào.</span><span class="sxs-lookup"><span data-stu-id="b27f8-159">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="b27f8-160">Chọn **Tên tham số kho dữ liệu đầu ra** cho quy trình thử nghiệm của bạn.</span><span class="sxs-lookup"><span data-stu-id="b27f8-160">Select the **Output data store parameter name** for your test pipeline.</span></span>
      1. <span data-ttu-id="b27f8-161">Chọn **Tên tham số đường dẫn đầu ra** cho quy trình thử nghiệm của bạn.</span><span class="sxs-lookup"><span data-stu-id="b27f8-161">Select the **Output Path parameter name** for your test pipeline.</span></span>

1. <span data-ttu-id="b27f8-162">Chọn thuộc tính kết hợp từ danh sách thả xuống **ID khách hàng trong kết quả** xác định khách hàng và chọn **Lưu**.</span><span class="sxs-lookup"><span data-stu-id="b27f8-162">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   <span data-ttu-id="b27f8-163">Bạn cần chọn một thuộc tính từ đầu ra suy luận có giá trị tương tự như cột ID khách hàng của thực thể Khách hàng.</span><span class="sxs-lookup"><span data-stu-id="b27f8-163">You need to choose an attribute from the inference output with values similar to the Customer ID column of the Customer entity.</span></span> <span data-ttu-id="b27f8-164">Nếu không có cột như vậy trong tập hợp dữ liệu của bạn, hãy chọn một thuộc tính xác định duy nhất hàng.</span><span class="sxs-lookup"><span data-stu-id="b27f8-164">If don't have such a column in your data set, choose an attribute that uniquely identifies the row.</span></span>

## <a name="run-a-workflow"></a><span data-ttu-id="b27f8-165">Chạy quy trình</span><span class="sxs-lookup"><span data-stu-id="b27f8-165">Run a workflow</span></span>

1. <span data-ttu-id="b27f8-166">Trên trang **Mô hình tùy chỉnh**, chọn dấu 3 chấm dọc trong cột **Hành động** cạnh quy trình bạn vừa tạo trước đó.</span><span class="sxs-lookup"><span data-stu-id="b27f8-166">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="b27f8-167">Chọn **Chạy**.</span><span class="sxs-lookup"><span data-stu-id="b27f8-167">Select **Run**.</span></span>

<span data-ttu-id="b27f8-168">Quy trình làm việc cũng chạy tự động với mỗi lần làm mới theo lịch trình.</span><span class="sxs-lookup"><span data-stu-id="b27f8-168">Your workflow also runs automatically with every scheduled refresh.</span></span> <span data-ttu-id="b27f8-169">Tìm hiểu thêm về [cách thiết lập các lần làm mới theo lịch](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="b27f8-169">Learn more about [setting up scheduled refreshes](system.md#schedule-tab).</span></span>

## <a name="delete-a-workflow"></a><span data-ttu-id="b27f8-170">Xóa quy trình</span><span class="sxs-lookup"><span data-stu-id="b27f8-170">Delete a workflow</span></span>

1. <span data-ttu-id="b27f8-171">Trên trang **Mô hình tùy chỉnh**, chọn dấu 3 chấm dọc trong cột **Hành động** cạnh quy trình bạn vừa tạo trước đó.</span><span class="sxs-lookup"><span data-stu-id="b27f8-171">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="b27f8-172">Chọn **Xóa** rồi xác nhận tác vụ xóa của bạn.</span><span class="sxs-lookup"><span data-stu-id="b27f8-172">Select **Delete** and confirm your deletion.</span></span>

<span data-ttu-id="b27f8-173">Quy trình của bạn sẽ bị xóa.</span><span class="sxs-lookup"><span data-stu-id="b27f8-173">Your workflow will be deleted.</span></span> <span data-ttu-id="b27f8-174">[Thực thể](entities.md) đã được tạo khi bạn tạo quy trình sẽ vẫn tồn tại, và bạn có thể xem thực thể trên trang **Thực thể**.</span><span class="sxs-lookup"><span data-stu-id="b27f8-174">The [entity](entities.md) that was created when you created the workflow persists, and can be viewed from the **Entities** page.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]