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
# <a name="use-azure-machine-learning-based-models"></a>Sử dụng các mô hình dựa trên Azure Machine Learning

Dữ liệu hợp nhất trong Dynamics 365 Customer Insights là nguồn để xây dựng các mô hình máy học có thể tạo thêm thông tin chi tiết về doanh nghiệp. Customer Insights tích hợp với Machine Learning Studio (cổ điển) và Azure Machine Learning để sử dụng các mô hình tùy chỉnh của riêng bạn. Tham khảo [Thử nghiệm Machine Learning Studio (cổ điển)](machine-learning-studio-experiments.md) để biết ví dụ về các thử nghiệm được xây dựng trên Machine Learning Studio (cổ điển). 

## <a name="prerequisites"></a>Điều kiện tiên quyết

- Truy cập Customer Insights
- Gói đăng ký Azure Enterprise hiện hoạt
- [Hồ sơ khách hàng hợp nhất](data-unification.md)
- [Xuất thực thể sang lưu trữ Azure Blob](export-azure-blob-storage.md) được định cấu hình

## <a name="set-up-azure-machine-learning-workspace"></a>Thiết lập không gian làm việc Azure Machine Learning

1. Xem [tạo không gian làm việc Azure Machine Learning](https://docs.microsoft.com/azure/machine-learning/concept-workspace#-create-a-workspace) cho các tùy chọn khác nhau để tạo không gian làm việc. Để có hiệu suất tốt nhất, hãy tạo không gian làm việc trong khu vực Azure gần nhất về mặt địa lý với môi trường Customer Insights của bạn.

1. Truy cập không gian làm việc của bạn thông qua [Azure Machine Learning Studio](https://ml.azure.com/). Có một số [cách để tương tác](https://docs.microsoft.com/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) với không gian làm việc của bạn.

## <a name="work-with-azure-machine-learning-designer"></a>Làm việc với trình thiết kế Azure Machine Learning

Trình thiết kế Azure Machine Learning cung cấp bảng tùy biến trực quan, nơi bạn có thể kéo và thả tập dữ liệu và mô-đun, tương tự như Machine Learning Studio (cổ điển). Một đường dẫn hàng loạt được tạo từ trình thiết kế có thể được tích hợp vào Customer Insights nếu chúng được định cấu hình phù hợp. 
   
## <a name="working-with-azure-machine-learning-sdk"></a>Làm việc với SDK Azure Machine Learning

Các nhà khoa học dữ liệu và nhà phát triển AI sử dụng [SDK Azure Machine Learning](https://docs.microsoft.com/python/api/overview/azure/ml/?view=azure-ml-py&preserve-view=true) để xây dựng các quy trình máy học. Hiện tại, các mô hình được đào tạo sử dụng SDK không thể được tích hợp trực tiếp với Customer Insights. Cần có quy trình suy luận hàng loạt sử dụng mô hình đó để tích hợp với Customer Insights.

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a>Cần có quy trình hàng loạt để tích hợp với Customer Insights

### <a name="dataset-configuration"></a>Cấu hình tập dữ liệu

Bạn cần tạo tập dữ liệu để sử dụng dữ liệu thực thể từ Customer Insights vào quy trình suy luận hàng loạt của mình. Các tập dữ liệu này cần được đăng ký trong không gian làm việc. Hiện tại, chúng tôi chỉ hỗ trợ [tập dữ liệu dạng bảng](https://docs.microsoft.com/azure/machine-learning/how-to-create-register-datasets#tabulardataset) ở định dạng .csv. Các tập dữ liệu tương ứng với dữ liệu thực thể cần được tham số hóa dưới dạng tham số quy trình.
   
* Tham số tập dữ liệu trong Trình thiết kế
   
     Trong trình thiết kế, mở **Chọn cột trong tập dữ liệu** và chọn **Đặt làm tham số quy trình**, tại đây bạn cung cấp tên cho tham số đó.

     > [!div class="mx-imgBorder"]
     > ![Tham số hóa tập dữ liệu trong trình thiết kế](media/intelligence-designer-dataset-parameters.png "Tham số hóa tập dữ liệu trong trình thiết kế")
   
* Tham số tập dữ liệu trong SDK (Python)
   
   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a>Quy trình suy luận hàng loạt
  
* Trong trình thiết kế, một quy trình huấn luyện có thể được sử dụng để tạo hoặc cập nhật một quy trình suy luận. Hiện tại, chỉ hỗ trợ các quy trình suy luận hàng loạt.

* Sử dụng SDK, bạn có thể phát hành quy trình tới một điểm cuối. Hiện tại, Customer Insights tích hợp với quy trình mặc định trong điểm cuối của đường dẫn hàng loạt trong không gian làm việc máy học.
   
   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a>Nhập dữ liệu quy trình vào Customer Insights

* Trình thiết kế cung cấp [mô-đun Xuất dữ liệu](https://docs.microsoft.com/azure/machine-learning/algorithm-module-reference/export-data) cho phép xuất đầu ra của quy trình đến kho lưu trữ Azure. Hiện tại, mô-đun phải sử dụng loại kho dữ liệu **Bộ nhớ Azure Blob** và tham số hóa **Kho dữ liệu** và **Đường dẫn** liên quan. Customer Insights ghi đè cả hai tham số này trong quá trình thực thi quy trình bằng kho dữ liệu và đường dẫn có thể truy cập đến sản phẩm.
   > [!div class="mx-imgBorder"]
   > ![Cấu hình mô-đun xuất dữ liệu](media/intelligence-designer-importdata.png "Cấu hình mô-đun xuất dữ liệu")
   
* Khi viết đầu ra suy luận bằng mã, bạn có thể tải đầu ra lên một đường dẫn trong *kho dữ liệu đã đăng ký* trong không gian làm việc. Nếu đường dẫn và kho dữ liệu được tham số hóa trong đường dẫn, Customer insights sẽ có thể đọc và nhập kết quả suy luận. Hiện tại, một đầu ra dạng bảng duy nhất ở định dạng csv được hỗ trợ. Đường dẫn phải bao gồm thư mục và tên tệp.

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
