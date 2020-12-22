---
title: Mô hình máy học tùy chỉnh | Microsoft Docs
description: Làm việc với các mô hình tùy chỉnh của Azure Machine Learning trong Dynamics 365 Customer Insights.
ms.date: 11/19/2020
ms.reviewer: zacook
ms.service: dynamics-365-ai
ms.topic: article
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ef248086b30b870359970529a7bfb37792be62d5
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668929"
---
# <a name="custom-machine-learning-models"></a><span data-ttu-id="1246a-103">Mô hình máy học tùy chỉnh</span><span class="sxs-lookup"><span data-stu-id="1246a-103">Custom machine learning models</span></span>

<span data-ttu-id="1246a-104">**Thông tin** > **Mô hình tùy chỉnh** cho phép bạn quản lý quy trình công việc dựa trên mô hình Azure Machine Learning.</span><span class="sxs-lookup"><span data-stu-id="1246a-104">**Intelligence** > **Custom models** lets you manage workflows based on Azure Machine Learning models.</span></span> <span data-ttu-id="1246a-105">Quy trình làm việc giúp bạn chọn dữ liệu bạn muốn tạo thông tin chi tiết và ánh xạ kết quả với dữ liệu khách hàng hợp nhất của bạn.</span><span class="sxs-lookup"><span data-stu-id="1246a-105">Workflows help you choose the data you want to generate insights from and map the results to your unified customer data.</span></span> <span data-ttu-id="1246a-106">Để biết thêm thông tin về cách xây dựng mô hình ML tùy chỉnh, hãy xem [Sử dụng các mô hình dựa trên Azure Machine Learning](azure-machine-learning-experiments.md).</span><span class="sxs-lookup"><span data-stu-id="1246a-106">For more information about building custom ML models, see [Use Azure Machine Learning-based models](azure-machine-learning-experiments.md).</span></span>

## <a name="responsible-ai"></a><span data-ttu-id="1246a-107">AI có trách nhiệm</span><span class="sxs-lookup"><span data-stu-id="1246a-107">Responsible AI</span></span>

<span data-ttu-id="1246a-108">Dự đoán cung cấp các khả năng để tạo ra trải nghiệm khách hàng tốt hơn, cải thiện khả năng kinh doanh và luồng doanh thu.</span><span class="sxs-lookup"><span data-stu-id="1246a-108">Predictions offer capabilities to create better customer experiences, improve business capabilities, and revenue streams.</span></span> <span data-ttu-id="1246a-109">Chúng tôi thực sự khuyên bạn nên cân bằng giá trị của dự đoán so với tác động của nó và những thành kiến có thể được đưa ra theo cách có đạo đức.</span><span class="sxs-lookup"><span data-stu-id="1246a-109">We strongly recommend you balance the value of your prediction against the impact it has and biases that may be introduced in an ethical manner.</span></span> <span data-ttu-id="1246a-110">Tìm hiểu thêm về cách Microsoft [giải quyết AI có trách nhiệm](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span><span class="sxs-lookup"><span data-stu-id="1246a-110">Learn more about how Microsoft is [addressing Responsible AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span></span> <span data-ttu-id="1246a-111">Bạn cũng có thể tìm hiểu về [kỹ thuật và quy trình cho máy học chịu trách nhiệm](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) cụ thể cho Azure Machine Learning.</span><span class="sxs-lookup"><span data-stu-id="1246a-111">You can also learn about [techniques and processes for responsible machine learning](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) specific to Azure Machine Learning.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1246a-112">Điều kiện tiên quyết</span><span class="sxs-lookup"><span data-stu-id="1246a-112">Prerequisites</span></span>

- <span data-ttu-id="1246a-113">Hiện tại, tính năng này hỗ trợ các dịch vụ web được xuất bản thông qua [Machine Learning Studio (cổ điển)](https://studio.azureml.net) và [quy trình hàng loạt Azure Machine Learning](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).</span><span class="sxs-lookup"><span data-stu-id="1246a-113">Currently, this feature supports web services published through [Machine Learning Studio (classic)](https://studio.azureml.net) and [Azure Machine Learning batch pipelines](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).</span></span>

- <span data-ttu-id="1246a-114">Bạn cần có tài khoản lưu trữ Azure Data Lake Gen2 được liên kết với phiên bản Azure Studio của bạn để sử dụng tính năng này.</span><span class="sxs-lookup"><span data-stu-id="1246a-114">You need an Azure Data Lake Gen2 storage account associated with your Azure Studio instance to use this feature.</span></span> <span data-ttu-id="1246a-115">Để biết thêm thông tin, hãy xem [Tạo tài khoản Azure Data Lake Storage thế hệ 2](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)</span><span class="sxs-lookup"><span data-stu-id="1246a-115">For more information, see [Create an Azure Data Lake Storage Gen2 storage account](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)</span></span>

## <a name="add-a-new-workflow"></a><span data-ttu-id="1246a-116">Thêm quy trình mới</span><span class="sxs-lookup"><span data-stu-id="1246a-116">Add a new workflow</span></span>

1. <span data-ttu-id="1246a-117">Chuyển đến **Thông tin** > **Mô hình tùy chỉnh** rồi chọn **Quy trình làm việc mới**.</span><span class="sxs-lookup"><span data-stu-id="1246a-117">Go to **Intelligence** > **Custom models** and select **New workflow**.</span></span>

1. <span data-ttu-id="1246a-118">Đặt cho mô hình tùy chỉnh một tên dễ nhận ra trong trường **Tên**.</span><span class="sxs-lookup"><span data-stu-id="1246a-118">Give your custom model a recognizable name in the **Name** field.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1246a-119">![Ảnh chụp màn hình ngăn quy trình làm việc mới](media/new-workflowv2.png "Ảnh chụp màn hình ngăn Quy trình làm việc mới")</span><span class="sxs-lookup"><span data-stu-id="1246a-119">![Screenshot of the New workflow pane](media/new-workflowv2.png "Screenshot of the New workflow pane")</span></span>

1. <span data-ttu-id="1246a-120">Chọn tổ chức chứa dịch vụ web trong **Đối tượng thuê chứa dịch vụ web**.</span><span class="sxs-lookup"><span data-stu-id="1246a-120">Select the organization that contains the web service in **Tenant that contains your web service**.</span></span>

1. <span data-ttu-id="1246a-121">Nếu đăng ký Azure Machine Learning khác với đối tượng thuê trong Customer Insights, hãy chọn **Đăng nhập** bằng thông tin đăng nhập của bạn cho tổ chức đã chọn.</span><span class="sxs-lookup"><span data-stu-id="1246a-121">If your Azure Machine Learning subscription is in a different tenant than Customer Insights, select **Sign in** with your credentials for the selected organization.</span></span>

1. <span data-ttu-id="1246a-122">Chọn **Không gian làm việc** được liên kết với dịch vụ web của bạn.</span><span class="sxs-lookup"><span data-stu-id="1246a-122">Select the **Workspaces** associated with your web service.</span></span> <span data-ttu-id="1246a-123">Có hai phần được liệt kê, một dành cho Azure Machine Learning v1 (Machine Learning Studio (cổ điển)) và Azure Machine Learning v2 (Azure Machine Learning).</span><span class="sxs-lookup"><span data-stu-id="1246a-123">There are two sections listed, one for Azure Machine Learning v1 (Machine Learning Studio (classic)) and Azure Machine Learning v2 (Azure Machine Learning).</span></span> <span data-ttu-id="1246a-124">Nếu bạn không chắc không gian làm việc nào phù hợp với dịch vụ web Machine Learning Studio (cổ điển) của mình, hãy chọn **Bất kì**.</span><span class="sxs-lookup"><span data-stu-id="1246a-124">If you're not sure which workspace is the right one for your Machine Learning Studio (classic) web service, select **Any**.</span></span>

1. <span data-ttu-id="1246a-125">Chọn dịch vụ web Machine Learning Studio (cổ điển) hoặc quy trình Azure Machine Learning trong menu thả xuống **Dịch vụ web chứa mô hình của bạn**.</span><span class="sxs-lookup"><span data-stu-id="1246a-125">Choose the Machine Learning Studio (classic) web service or Azure Machine Learning pipeline in the **Web service that contains your model** dropdown.</span></span> <span data-ttu-id="1246a-126">Sau đó, chọn **Tiếp**.</span><span class="sxs-lookup"><span data-stu-id="1246a-126">Then, select **Next**.</span></span>
   - <span data-ttu-id="1246a-127">Tìm hiểu thêm về [phát hành một dịch vụ web trong Machine Learning Studio (cổ điển)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span><span class="sxs-lookup"><span data-stu-id="1246a-127">Learn more about [publishing a web service in Machine Learning Studio (classic)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span></span>
   - <span data-ttu-id="1246a-128">Tìm hiểu thêm về [phát hành một quy trình trong Azure Machine Learning bằng cách sử dụng trình thiết kế](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) hoặc [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span><span class="sxs-lookup"><span data-stu-id="1246a-128">Learn more about [publishing a pipeline in Azure Machine Learning using the designer](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) or [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span></span> 
     > [!NOTE]
     > <span data-ttu-id="1246a-129">Quy trình của bạn phải được thiết kế theo [điểm cuối quy trình](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span><span class="sxs-lookup"><span data-stu-id="1246a-129">Your pipeline must be published under a [pipeline endpoint](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span></span>

1. <span data-ttu-id="1246a-130">Đối với mỗi **Đầu vào dịch vụ web**, chọn **Thực thể** phù hợp từ thông tin chi tiết về đối tượng và chọn **Tiếp theo**.</span><span class="sxs-lookup"><span data-stu-id="1246a-130">For each **Web service input**, select the matching **Entity** from audience insights and select **Next**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1246a-131">![Đặt cấu hình cho quy trình](media/intelligence-screen2-updated.png "Đặt cấu hình cho quy trình")</span><span class="sxs-lookup"><span data-stu-id="1246a-131">![Configure a workflow](media/intelligence-screen2-updated.png "Configure a workflow")</span></span>

1. <span data-ttu-id="1246a-132">Trong bước **Tham số đầu ra mô hình**, đặt các thuộc tính sau:</span><span class="sxs-lookup"><span data-stu-id="1246a-132">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="1246a-133">Machine Learning Studio (cổ điển)</span><span class="sxs-lookup"><span data-stu-id="1246a-133">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="1246a-134">Nhập **Tên thực thể** đầu ra mà bạn muốn kết quả đầu ra của dịch vụ web chuyển vào.</span><span class="sxs-lookup"><span data-stu-id="1246a-134">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="1246a-135">Máy học của Azure</span><span class="sxs-lookup"><span data-stu-id="1246a-135">Azure Machine Learning</span></span>
      1. <span data-ttu-id="1246a-136">Nhập **Tên thực thể** đầu ra mà bạn muốn kết quả đầu ra của quy trình làm việc chuyển vào.</span><span class="sxs-lookup"><span data-stu-id="1246a-136">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="1246a-137">Chọn **Tên tham số đầu ra kho dữ liệu** của quy trình hàng loạt của bạn từ menu thả xuống.</span><span class="sxs-lookup"><span data-stu-id="1246a-137">Select the **Output data store parameter name** of your batch pipeline from the dropdown.</span></span>
      1. <span data-ttu-id="1246a-138">Chọn **Tên tham số đường dẫn đầu ra** của quy trình hàng loạt của bạn từ menu thả xuống.</span><span class="sxs-lookup"><span data-stu-id="1246a-138">Select the **Output Path parameter name** of your batch pipeline from the dropdown.</span></span>
      
      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="1246a-139">![Ngăn tham số đầu ra của mô hình](media/intelligence-screen3-outputparameters.png "Ngăn tham số đầu ra của mô hình")</span><span class="sxs-lookup"><span data-stu-id="1246a-139">![Model Output Parameter Pane](media/intelligence-screen3-outputparameters.png "Model Output Parameter Pane")</span></span>

1. <span data-ttu-id="1246a-140">Chọn thuộc tính kết hợp từ danh sách thả xuống **ID khách hàng trong kết quả** xác định khách hàng và chọn **Lưu**.</span><span class="sxs-lookup"><span data-stu-id="1246a-140">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1246a-141">![Liên kết kết quả với ngăn Dữ liệu khách hàng](media/intelligence-screen4-relatetocustomer.png "Liên kết kết quả với ngăn Dữ liệu khách hàng")</span><span class="sxs-lookup"><span data-stu-id="1246a-141">![Relate results to Customer data pane](media/intelligence-screen4-relatetocustomer.png "Relate results to Customer data pane")</span></span>

1. <span data-ttu-id="1246a-142">Bạn sẽ nhìn thấy màn hình **Quy trình làm việc được lưu** có thông tin chi tiết về quy trình làm việc.</span><span class="sxs-lookup"><span data-stu-id="1246a-142">You'll see the **Workflow Saved** screen with details about the workflow.</span></span>    
   <span data-ttu-id="1246a-143">Nếu bạn đã định cấu hình quy trình làm việc cho quy trình Azure Machine Learning, thông tin chi tiết về đối tượng sẽ đính kèm vào không gian làm việc chứa quy trình.</span><span class="sxs-lookup"><span data-stu-id="1246a-143">If you configured a workflow for an Azure Machine Learning pipeline, audience insights will attach to the workspace that contains the pipeline.</span></span> <span data-ttu-id="1246a-144">Thông tin chi tiết về đối tượng sẽ nhận được vai trò **Cộng tác viên** trên không gian làm việc Azure.</span><span class="sxs-lookup"><span data-stu-id="1246a-144">Audience insights will get a **Contributor** role on the Azure workspace.</span></span>

1. <span data-ttu-id="1246a-145">Chọn **Xong**.</span><span class="sxs-lookup"><span data-stu-id="1246a-145">Select **Done**.</span></span>

1. <span data-ttu-id="1246a-146">Bây giờ bạn có thể chạy quy trình làm việc từ trang **Mô hình tùy chỉnh**.</span><span class="sxs-lookup"><span data-stu-id="1246a-146">You can now run the workflow from the **Custom Models** page.</span></span>

## <a name="edit-a-workflow"></a><span data-ttu-id="1246a-147">Chỉnh sửa quy trình</span><span class="sxs-lookup"><span data-stu-id="1246a-147">Edit a workflow</span></span>

1. <span data-ttu-id="1246a-148">Trên trang **Mô hình tùy chỉnh**, chọn dấu 3 chấm dọc trong cột **Hành động** cạnh quy trình bạn đã tạo trước đó rồi chọn **Chính sửa**.</span><span class="sxs-lookup"><span data-stu-id="1246a-148">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created and select **Edit**.</span></span>

1. <span data-ttu-id="1246a-149">Bạn có thể cập nhật tên dễ nhận biết của quy trình làm việc của mình trong trường **Tên hiển thị** nhưng bạn không thể thay đổi quy trình hoặc dịch vụ web đã định cấu hình.</span><span class="sxs-lookup"><span data-stu-id="1246a-149">You can update your workflow's recognizable name in the **Display name** field, but you can't change the configured web service or pipeline.</span></span> <span data-ttu-id="1246a-150">Chọn **Tiếp theo**.</span><span class="sxs-lookup"><span data-stu-id="1246a-150">Select **Next**.</span></span>

1. <span data-ttu-id="1246a-151">Đối với mỗi **Đầu vào dịch vụ web**, bạn có thể cập nhật **Thực thể** phù hợp từ thông tin chi tiết về đối tượng.</span><span class="sxs-lookup"><span data-stu-id="1246a-151">For each **Web service input**, you can update the matching **Entity** from audience insights.</span></span> <span data-ttu-id="1246a-152">Sau đó, chọn **Tiếp**.</span><span class="sxs-lookup"><span data-stu-id="1246a-152">Then, select **Next**.</span></span>

1. <span data-ttu-id="1246a-153">Trong bước **Tham số đầu ra mô hình**, đặt các thuộc tính sau:</span><span class="sxs-lookup"><span data-stu-id="1246a-153">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="1246a-154">Machine Learning Studio (cổ điển)</span><span class="sxs-lookup"><span data-stu-id="1246a-154">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="1246a-155">Nhập **Tên thực thể** đầu ra mà bạn muốn kết quả đầu ra của dịch vụ web chuyển vào.</span><span class="sxs-lookup"><span data-stu-id="1246a-155">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="1246a-156">Máy học của Azure</span><span class="sxs-lookup"><span data-stu-id="1246a-156">Azure Machine Learning</span></span>
      1. <span data-ttu-id="1246a-157">Nhập **Tên thực thể** đầu ra mà bạn muốn kết quả đầu ra của quy trình làm việc chuyển vào.</span><span class="sxs-lookup"><span data-stu-id="1246a-157">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="1246a-158">Chọn **Tên tham số kho dữ liệu đầu ra** cho quy trình thử nghiệm của bạn.</span><span class="sxs-lookup"><span data-stu-id="1246a-158">Select the **Output data store parameter name** for your test pipeline.</span></span>
      1. <span data-ttu-id="1246a-159">Chọn **Tên tham số đường dẫn đầu ra** cho quy trình thử nghiệm của bạn.</span><span class="sxs-lookup"><span data-stu-id="1246a-159">Select the **Output Path parameter name** for your test pipeline.</span></span>

1. <span data-ttu-id="1246a-160">Chọn thuộc tính kết hợp từ danh sách thả xuống **ID khách hàng trong kết quả** xác định khách hàng và chọn **Lưu**.</span><span class="sxs-lookup"><span data-stu-id="1246a-160">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   <span data-ttu-id="1246a-161">Bạn cần chọn một thuộc tính từ đầu ra suy luận có giá trị tương tự như cột ID khách hàng của thực thể Khách hàng.</span><span class="sxs-lookup"><span data-stu-id="1246a-161">You need to choose an attribute from the inference output with values similar to the Customer ID column of the Customer entity.</span></span> <span data-ttu-id="1246a-162">Nếu không có cột như vậy trong tập hợp dữ liệu của bạn, hãy chọn một thuộc tính xác định duy nhất hàng.</span><span class="sxs-lookup"><span data-stu-id="1246a-162">If don't have such a column in your data set, choose an attribute that uniquely identifies the row.</span></span>

## <a name="run-a-workflow"></a><span data-ttu-id="1246a-163">Chạy quy trình</span><span class="sxs-lookup"><span data-stu-id="1246a-163">Run a workflow</span></span>

1. <span data-ttu-id="1246a-164">Trên trang **Mô hình tùy chỉnh**, chọn dấu 3 chấm dọc trong cột **Hành động** cạnh quy trình bạn vừa tạo trước đó.</span><span class="sxs-lookup"><span data-stu-id="1246a-164">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="1246a-165">Chọn **Chạy**.</span><span class="sxs-lookup"><span data-stu-id="1246a-165">Select **Run**.</span></span>

<span data-ttu-id="1246a-166">Quy trình làm việc cũng chạy tự động với mỗi lần làm mới theo lịch trình.</span><span class="sxs-lookup"><span data-stu-id="1246a-166">Your workflow also runs automatically with every scheduled refresh.</span></span> <span data-ttu-id="1246a-167">Tìm hiểu thêm về [cách thiết lập các lần làm mới theo lịch](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="1246a-167">Learn more about [setting up scheduled refreshes](system.md#schedule-tab).</span></span>

## <a name="delete-a-workflow"></a><span data-ttu-id="1246a-168">Xóa quy trình</span><span class="sxs-lookup"><span data-stu-id="1246a-168">Delete a workflow</span></span>

1. <span data-ttu-id="1246a-169">Trên trang **Mô hình tùy chỉnh**, chọn dấu 3 chấm dọc trong cột **Hành động** cạnh quy trình bạn vừa tạo trước đó.</span><span class="sxs-lookup"><span data-stu-id="1246a-169">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="1246a-170">Chọn **Xóa** rồi xác nhận tác vụ xóa của bạn.</span><span class="sxs-lookup"><span data-stu-id="1246a-170">Select **Delete** and confirm your deletion.</span></span>

<span data-ttu-id="1246a-171">Quy trình của bạn sẽ bị xóa.</span><span class="sxs-lookup"><span data-stu-id="1246a-171">Your workflow will be deleted.</span></span> <span data-ttu-id="1246a-172">[Thực thể](entities.md) đã được tạo khi bạn tạo quy trình sẽ vẫn tồn tại, và bạn có thể xem thực thể trên trang **Thực thể**.</span><span class="sxs-lookup"><span data-stu-id="1246a-172">The [entity](entities.md) that was created when you created the workflow persists, and can be viewed from the **Entities** page.</span></span>
