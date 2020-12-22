---
title: Thử nghiệm Azure Machine Learning
description: Sử dụng các mô hình dựa trên Azure Machine Learning trong Dynamics 365 Customer Insights.
ms.date: 11/30/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: naravill
ms.author: mhart
ms.reviewer: m-hartmann
manager: shellyha
ms.openlocfilehash: 6f00d3202dc29d810bdd218d06c7d04e551846e8
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668807"
---
# <a name="use-azure-machine-learning-based-models"></a><span data-ttu-id="14b6b-103">Sử dụng các mô hình dựa trên Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="14b6b-103">Use Azure Machine Learning-based models</span></span>

<span data-ttu-id="14b6b-104">Dữ liệu hợp nhất trong Dynamics 365 Customer Insights là nguồn để xây dựng các mô hình máy học có thể tạo thêm thông tin chi tiết về doanh nghiệp.</span><span class="sxs-lookup"><span data-stu-id="14b6b-104">The unified data in Dynamics 365 Customer Insights is a source for building machine learning models that can generate additional business insights.</span></span> <span data-ttu-id="14b6b-105">Customer Insights tích hợp với Machine Learning Studio (cổ điển) và Azure Machine Learning để sử dụng các mô hình tùy chỉnh của riêng bạn.</span><span class="sxs-lookup"><span data-stu-id="14b6b-105">Customer Insights integrates with Machine Learning Studio (classic) and Azure Machine Learning to use your own custom models.</span></span> <span data-ttu-id="14b6b-106">Tham khảo [Thử nghiệm Machine Learning Studio (cổ điển)](machine-learning-studio-experiments.md) để biết ví dụ về các thử nghiệm được xây dựng trên Machine Learning Studio (cổ điển).</span><span class="sxs-lookup"><span data-stu-id="14b6b-106">Refer to [Machine Learning Studio (classic) experiments](machine-learning-studio-experiments.md) for examples of experiments built on Machine Learning Studio (classic).</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="14b6b-107">Điều kiện tiên quyết</span><span class="sxs-lookup"><span data-stu-id="14b6b-107">Prerequisites</span></span>

- <span data-ttu-id="14b6b-108">Truy cập Customer Insights</span><span class="sxs-lookup"><span data-stu-id="14b6b-108">Access to Customer Insights</span></span>
- <span data-ttu-id="14b6b-109">Gói đăng ký Azure Enterprise hiện hoạt</span><span class="sxs-lookup"><span data-stu-id="14b6b-109">Active Azure Enterprise subscription</span></span>
- [<span data-ttu-id="14b6b-110">Hồ sơ khách hàng hợp nhất</span><span class="sxs-lookup"><span data-stu-id="14b6b-110">Unified customer profiles</span></span>](data-unification.md)
- <span data-ttu-id="14b6b-111">[Xuất thực thể sang lưu trữ Azure Blob](export-azure-blob-storage.md) được định cấu hình</span><span class="sxs-lookup"><span data-stu-id="14b6b-111">[Entity export to Azure Blob storage](export-azure-blob-storage.md) configured</span></span>

## <a name="set-up-azure-machine-learning-workspace"></a><span data-ttu-id="14b6b-112">Thiết lập không gian làm việc Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="14b6b-112">Set up Azure Machine Learning workspace</span></span>

1. <span data-ttu-id="14b6b-113">Xem [tạo không gian làm việc Azure Machine Learning](https://docs.microsoft.com/azure/machine-learning/concept-workspace#-create-a-workspace) cho các tùy chọn khác nhau để tạo không gian làm việc.</span><span class="sxs-lookup"><span data-stu-id="14b6b-113">See [create a Azure Machine Learning workspace](https://docs.microsoft.com/azure/machine-learning/concept-workspace#-create-a-workspace) for different options to create the workspace.</span></span> <span data-ttu-id="14b6b-114">Để có hiệu suất tốt nhất, hãy tạo không gian làm việc trong khu vực Azure gần nhất về mặt địa lý với môi trường Customer Insights của bạn.</span><span class="sxs-lookup"><span data-stu-id="14b6b-114">For best performance, create the workspace in an Azure region that is geographically closest to your Customer Insights environment.</span></span>

1. <span data-ttu-id="14b6b-115">Truy cập không gian làm việc của bạn thông qua [Azure Machine Learning Studio](https://ml.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="14b6b-115">Access your workspace through the [Azure Machine Learning Studio](https://ml.azure.com/).</span></span> <span data-ttu-id="14b6b-116">Có một số [cách để tương tác](https://docs.microsoft.com/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) với không gian làm việc của bạn.</span><span class="sxs-lookup"><span data-stu-id="14b6b-116">There are several [ways to interact](https://docs.microsoft.com/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) with your workspace.</span></span>

## <a name="work-with-azure-machine-learning-designer"></a><span data-ttu-id="14b6b-117">Làm việc với trình thiết kế Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="14b6b-117">Work with Azure Machine Learning designer</span></span>

<span data-ttu-id="14b6b-118">Trình thiết kế Azure Machine Learning cung cấp bảng tùy biến trực quan, nơi bạn có thể kéo và thả tập dữ liệu và mô-đun, tương tự như Machine Learning Studio (cổ điển).</span><span class="sxs-lookup"><span data-stu-id="14b6b-118">Azure Machine Learning designer provides a visual canvas where you can drag and drop datasets and modules, similar to Machine Learning Studio (classic).</span></span> <span data-ttu-id="14b6b-119">Một đường dẫn hàng loạt được tạo từ trình thiết kế có thể được tích hợp vào Customer Insights nếu chúng được định cấu hình phù hợp.</span><span class="sxs-lookup"><span data-stu-id="14b6b-119">A batch pipeline created from the designer can be integrated into Customer Insights if they are configured accordingly.</span></span> 
   
## <a name="working-with-azure-machine-learning-sdk"></a><span data-ttu-id="14b6b-120">Làm việc với SDK Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="14b6b-120">Working with Azure Machine Learning SDK</span></span>

<span data-ttu-id="14b6b-121">Các nhà khoa học dữ liệu và nhà phát triển AI sử dụng [SDK Azure Machine Learning](https://docs.microsoft.com/python/api/overview/azure/ml/?view=azure-ml-py&preserve-view=true) để xây dựng các quy trình máy học.</span><span class="sxs-lookup"><span data-stu-id="14b6b-121">Data scientists and AI developers use the [Azure Machine Learning SDK](https://docs.microsoft.com/python/api/overview/azure/ml/?view=azure-ml-py&preserve-view=true) to build machine learning workflows.</span></span> <span data-ttu-id="14b6b-122">Hiện tại, các mô hình được đào tạo sử dụng SDK không thể được tích hợp trực tiếp với Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="14b6b-122">Currently, models trained using the SDK can't be integrated directly with Customer Insights.</span></span> <span data-ttu-id="14b6b-123">Cần có quy trình suy luận hàng loạt sử dụng mô hình đó để tích hợp với Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="14b6b-123">A batch inference pipeline that consumes that model is required for integration with Customer Insights.</span></span>

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a><span data-ttu-id="14b6b-124">Cần có quy trình hàng loạt để tích hợp với Customer Insights</span><span class="sxs-lookup"><span data-stu-id="14b6b-124">Batch pipeline requirements to integrate with Customer Insights</span></span>

### <a name="dataset-configuration"></a><span data-ttu-id="14b6b-125">Cấu hình tập dữ liệu</span><span class="sxs-lookup"><span data-stu-id="14b6b-125">Dataset Configuration</span></span>

<span data-ttu-id="14b6b-126">Bạn cần tạo tập dữ liệu để sử dụng dữ liệu thực thể từ Customer Insights vào quy trình suy luận hàng loạt của mình.</span><span class="sxs-lookup"><span data-stu-id="14b6b-126">You need to create datasets to use entity data from Customer Insights to your batch inference pipeline.</span></span> <span data-ttu-id="14b6b-127">Các tập dữ liệu này cần được đăng ký trong không gian làm việc.</span><span class="sxs-lookup"><span data-stu-id="14b6b-127">These datasets need to be registered in the workspace.</span></span> <span data-ttu-id="14b6b-128">Hiện tại, chúng tôi chỉ hỗ trợ [tập dữ liệu dạng bảng](https://docs.microsoft.com/azure/machine-learning/how-to-create-register-datasets#tabulardataset) ở định dạng .csv.</span><span class="sxs-lookup"><span data-stu-id="14b6b-128">Currently, we only support [tabular datasets](https://docs.microsoft.com/azure/machine-learning/how-to-create-register-datasets#tabulardataset) in .csv format.</span></span> <span data-ttu-id="14b6b-129">Các tập dữ liệu tương ứng với dữ liệu thực thể cần được tham số hóa dưới dạng tham số quy trình.</span><span class="sxs-lookup"><span data-stu-id="14b6b-129">The datasets that correspond to entity data need to be parameterized as a pipeline parameter.</span></span>
   
* <span data-ttu-id="14b6b-130">Tham số tập dữ liệu trong Trình thiết kế</span><span class="sxs-lookup"><span data-stu-id="14b6b-130">Dataset parameters in Designer</span></span>
   
     <span data-ttu-id="14b6b-131">Trong trình thiết kế, mở **Chọn cột trong tập dữ liệu** và chọn **Đặt làm tham số quy trình**, tại đây bạn cung cấp tên cho tham số đó.</span><span class="sxs-lookup"><span data-stu-id="14b6b-131">In the designer, open **Select Columns in Dataset** and select **Set as pipeline parameter** where you provide a name for the parameter.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="14b6b-132">![Tham số hóa tập dữ liệu trong trình thiết kế](media/intelligence-designer-dataset-parameters.png "Tham số hóa tập dữ liệu trong trình thiết kế")</span><span class="sxs-lookup"><span data-stu-id="14b6b-132">![Dataset parameterization in designer](media/intelligence-designer-dataset-parameters.png "Dataset parameterization in designer")</span></span>
   
* <span data-ttu-id="14b6b-133">Tham số tập dữ liệu trong SDK (Python)</span><span class="sxs-lookup"><span data-stu-id="14b6b-133">Dataset parameter in SDK (Python)</span></span>
   
   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a><span data-ttu-id="14b6b-134">Quy trình suy luận hàng loạt</span><span class="sxs-lookup"><span data-stu-id="14b6b-134">Batch inference pipeline</span></span>
  
* <span data-ttu-id="14b6b-135">Trong trình thiết kế, một quy trình huấn luyện có thể được sử dụng để tạo hoặc cập nhật một quy trình suy luận.</span><span class="sxs-lookup"><span data-stu-id="14b6b-135">In the designer, a training pipeline can be used to create or update an inference pipeline.</span></span> <span data-ttu-id="14b6b-136">Hiện tại, chỉ hỗ trợ các quy trình suy luận hàng loạt.</span><span class="sxs-lookup"><span data-stu-id="14b6b-136">Currently, only batch inference pipelines are supported.</span></span>

* <span data-ttu-id="14b6b-137">Sử dụng SDK, bạn có thể phát hành quy trình tới một điểm cuối.</span><span class="sxs-lookup"><span data-stu-id="14b6b-137">Using the SDK, you can publish the pipeline to an endpoint.</span></span> <span data-ttu-id="14b6b-138">Hiện tại, Customer Insights tích hợp với quy trình mặc định trong điểm cuối của đường dẫn hàng loạt trong không gian làm việc máy học.</span><span class="sxs-lookup"><span data-stu-id="14b6b-138">Currently, Customer Insights integrates with the default pipeline in a batch pipeline endpoint in the Machine Learning workspace.</span></span>
   
   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a><span data-ttu-id="14b6b-139">Nhập dữ liệu quy trình vào Customer Insights</span><span class="sxs-lookup"><span data-stu-id="14b6b-139">Import pipeline data into Customer Insights</span></span>

* <span data-ttu-id="14b6b-140">Trình thiết kế cung cấp [mô-đun Xuất dữ liệu](https://docs.microsoft.com/azure/machine-learning/algorithm-module-reference/export-data) cho phép xuất đầu ra của quy trình đến kho lưu trữ Azure.</span><span class="sxs-lookup"><span data-stu-id="14b6b-140">The designer provides the [Export Data module](https://docs.microsoft.com/azure/machine-learning/algorithm-module-reference/export-data) that allows the output of a pipeline to be exported to Azure storage.</span></span> <span data-ttu-id="14b6b-141">Hiện tại, mô-đun phải sử dụng loại kho dữ liệu **Bộ nhớ Azure Blob** và tham số hóa **Kho dữ liệu** và **Đường dẫn** liên quan.</span><span class="sxs-lookup"><span data-stu-id="14b6b-141">Currently, the module must use the datastore type **Azure Blob Storage** and parameterize the **Datastore** and relative **Path**.</span></span> <span data-ttu-id="14b6b-142">Customer Insights ghi đè cả hai tham số này trong quá trình thực thi quy trình bằng kho dữ liệu và đường dẫn có thể truy cập đến sản phẩm.</span><span class="sxs-lookup"><span data-stu-id="14b6b-142">Customer Insights overrides both these parameters during pipeline execution with a datastore and path that is accessible to the product.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="14b6b-143">![Cấu hình mô-đun xuất dữ liệu](media/intelligence-designer-importdata.png "Cấu hình mô-đun xuất dữ liệu")</span><span class="sxs-lookup"><span data-stu-id="14b6b-143">![Export Data Module Configuration](media/intelligence-designer-importdata.png "Export Data Module Configuration")</span></span>
   
* <span data-ttu-id="14b6b-144">Khi viết đầu ra suy luận bằng mã, bạn có thể tải đầu ra lên một đường dẫn trong *kho dữ liệu đã đăng ký* trong không gian làm việc.</span><span class="sxs-lookup"><span data-stu-id="14b6b-144">When writing the inference output using code, you can upload the output to the a path within a *registered datastore* in the workspace.</span></span> <span data-ttu-id="14b6b-145">Nếu đường dẫn và kho dữ liệu được tham số hóa trong đường dẫn, Customer insights sẽ có thể đọc và nhập kết quả suy luận.</span><span class="sxs-lookup"><span data-stu-id="14b6b-145">If the path and datastore are parameterized in the pipeline, Customer insights will be able to read and import the inference output.</span></span> <span data-ttu-id="14b6b-146">Hiện tại, một đầu ra dạng bảng duy nhất ở định dạng csv được hỗ trợ.</span><span class="sxs-lookup"><span data-stu-id="14b6b-146">Currently, a single tabular output in csv format is supported.</span></span> <span data-ttu-id="14b6b-147">Đường dẫn phải bao gồm thư mục và tên tệp.</span><span class="sxs-lookup"><span data-stu-id="14b6b-147">The path must include the directory and filename.</span></span>

   ```python
   # In Pipeline setup script
      OutputPathParameter = PipelineParameter(name="output_path", default_value="HotelChurnOutput/HotelChurnOutput.csv")
      OutputDatastoreParameter = PipelineParameter(name="output_datastore", default_value="workspaceblobstore")
   ...
   # In pipeline execution script
      run = Run.get_context()
      ws = run.experiment.workspace
      datastore = Datastore.get(ws, output_datastore) # output_datastore is parameterized
      directory_name =  os.path.dirname(output_path)  # output_path is parameterized.
      
      # Datastore.upload() or Dataset.File.upload_directory() are supported methods to uplaod the data
      # datastore.upload(src_dir=<<working directory>>, target_path=directory_name, overwrite=False, show_progress=True)
      output_dataset = Dataset.File.upload_directory(src_dir=<<working directory>>, target = (datastore, directory_name)) # Remove trailing "/" from directory_name
   ```
