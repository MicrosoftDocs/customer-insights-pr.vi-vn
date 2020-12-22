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
# <a name="custom-machine-learning-models"></a>Mô hình máy học tùy chỉnh

**Thông tin** > **Mô hình tùy chỉnh** cho phép bạn quản lý quy trình công việc dựa trên mô hình Azure Machine Learning. Quy trình làm việc giúp bạn chọn dữ liệu bạn muốn tạo thông tin chi tiết và ánh xạ kết quả với dữ liệu khách hàng hợp nhất của bạn. Để biết thêm thông tin về cách xây dựng mô hình ML tùy chỉnh, hãy xem [Sử dụng các mô hình dựa trên Azure Machine Learning](azure-machine-learning-experiments.md).

## <a name="responsible-ai"></a>AI có trách nhiệm

Dự đoán cung cấp các khả năng để tạo ra trải nghiệm khách hàng tốt hơn, cải thiện khả năng kinh doanh và luồng doanh thu. Chúng tôi thực sự khuyên bạn nên cân bằng giá trị của dự đoán so với tác động của nó và những thành kiến có thể được đưa ra theo cách có đạo đức. Tìm hiểu thêm về cách Microsoft [giải quyết AI có trách nhiệm](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6). Bạn cũng có thể tìm hiểu về [kỹ thuật và quy trình cho máy học chịu trách nhiệm](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) cụ thể cho Azure Machine Learning.

## <a name="prerequisites"></a>Điều kiện tiên quyết

- Hiện tại, tính năng này hỗ trợ các dịch vụ web được xuất bản thông qua [Machine Learning Studio (cổ điển)](https://studio.azureml.net) và [quy trình hàng loạt Azure Machine Learning](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).

- Bạn cần có tài khoản lưu trữ Azure Data Lake Gen2 được liên kết với phiên bản Azure Studio của bạn để sử dụng tính năng này. Để biết thêm thông tin, hãy xem [Tạo tài khoản Azure Data Lake Storage thế hệ 2](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)

## <a name="add-a-new-workflow"></a>Thêm quy trình mới

1. Chuyển đến **Thông tin** > **Mô hình tùy chỉnh** rồi chọn **Quy trình làm việc mới**.

1. Đặt cho mô hình tùy chỉnh một tên dễ nhận ra trong trường **Tên**.

   > [!div class="mx-imgBorder"]
   > ![Ảnh chụp màn hình ngăn quy trình làm việc mới](media/new-workflowv2.png "Ảnh chụp màn hình ngăn Quy trình làm việc mới")

1. Chọn tổ chức chứa dịch vụ web trong **Đối tượng thuê chứa dịch vụ web**.

1. Nếu đăng ký Azure Machine Learning khác với đối tượng thuê trong Customer Insights, hãy chọn **Đăng nhập** bằng thông tin đăng nhập của bạn cho tổ chức đã chọn.

1. Chọn **Không gian làm việc** được liên kết với dịch vụ web của bạn. Có hai phần được liệt kê, một dành cho Azure Machine Learning v1 (Machine Learning Studio (cổ điển)) và Azure Machine Learning v2 (Azure Machine Learning). Nếu bạn không chắc không gian làm việc nào phù hợp với dịch vụ web Machine Learning Studio (cổ điển) của mình, hãy chọn **Bất kì**.

1. Chọn dịch vụ web Machine Learning Studio (cổ điển) hoặc quy trình Azure Machine Learning trong menu thả xuống **Dịch vụ web chứa mô hình của bạn**. Sau đó, chọn **Tiếp**.
   - Tìm hiểu thêm về [phát hành một dịch vụ web trong Machine Learning Studio (cổ điển)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)
   - Tìm hiểu thêm về [phát hành một quy trình trong Azure Machine Learning bằng cách sử dụng trình thiết kế](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) hoặc [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk). 
     > [!NOTE]
     > Quy trình của bạn phải được thiết kế theo [điểm cuối quy trình](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).

1. Đối với mỗi **Đầu vào dịch vụ web**, chọn **Thực thể** phù hợp từ thông tin chi tiết về đối tượng và chọn **Tiếp theo**.

   > [!div class="mx-imgBorder"]
   > ![Đặt cấu hình cho quy trình](media/intelligence-screen2-updated.png "Đặt cấu hình cho quy trình")

1. Trong bước **Tham số đầu ra mô hình**, đặt các thuộc tính sau:
   - Machine Learning Studio (cổ điển)
      1. Nhập **Tên thực thể** đầu ra mà bạn muốn kết quả đầu ra của dịch vụ web chuyển vào.
   - Máy học của Azure
      1. Nhập **Tên thực thể** đầu ra mà bạn muốn kết quả đầu ra của quy trình làm việc chuyển vào.
      1. Chọn **Tên tham số đầu ra kho dữ liệu** của quy trình hàng loạt của bạn từ menu thả xuống.
      1. Chọn **Tên tham số đường dẫn đầu ra** của quy trình hàng loạt của bạn từ menu thả xuống.
      
      > [!div class="mx-imgBorder"]
      > ![Ngăn tham số đầu ra của mô hình](media/intelligence-screen3-outputparameters.png "Ngăn tham số đầu ra của mô hình")

1. Chọn thuộc tính kết hợp từ danh sách thả xuống **ID khách hàng trong kết quả** xác định khách hàng và chọn **Lưu**.
   
   > [!div class="mx-imgBorder"]
   > ![Liên kết kết quả với ngăn Dữ liệu khách hàng](media/intelligence-screen4-relatetocustomer.png "Liên kết kết quả với ngăn Dữ liệu khách hàng")

1. Bạn sẽ nhìn thấy màn hình **Quy trình làm việc được lưu** có thông tin chi tiết về quy trình làm việc.    
   Nếu bạn đã định cấu hình quy trình làm việc cho quy trình Azure Machine Learning, thông tin chi tiết về đối tượng sẽ đính kèm vào không gian làm việc chứa quy trình. Thông tin chi tiết về đối tượng sẽ nhận được vai trò **Cộng tác viên** trên không gian làm việc Azure.

1. Chọn **Xong**.

1. Bây giờ bạn có thể chạy quy trình làm việc từ trang **Mô hình tùy chỉnh**.

## <a name="edit-a-workflow"></a>Chỉnh sửa quy trình

1. Trên trang **Mô hình tùy chỉnh**, chọn dấu 3 chấm dọc trong cột **Hành động** cạnh quy trình bạn đã tạo trước đó rồi chọn **Chính sửa**.

1. Bạn có thể cập nhật tên dễ nhận biết của quy trình làm việc của mình trong trường **Tên hiển thị** nhưng bạn không thể thay đổi quy trình hoặc dịch vụ web đã định cấu hình. Chọn **Tiếp theo**.

1. Đối với mỗi **Đầu vào dịch vụ web**, bạn có thể cập nhật **Thực thể** phù hợp từ thông tin chi tiết về đối tượng. Sau đó, chọn **Tiếp**.

1. Trong bước **Tham số đầu ra mô hình**, đặt các thuộc tính sau:
   - Machine Learning Studio (cổ điển)
      1. Nhập **Tên thực thể** đầu ra mà bạn muốn kết quả đầu ra của dịch vụ web chuyển vào.
   - Máy học của Azure
      1. Nhập **Tên thực thể** đầu ra mà bạn muốn kết quả đầu ra của quy trình làm việc chuyển vào.
      1. Chọn **Tên tham số kho dữ liệu đầu ra** cho quy trình thử nghiệm của bạn.
      1. Chọn **Tên tham số đường dẫn đầu ra** cho quy trình thử nghiệm của bạn.

1. Chọn thuộc tính kết hợp từ danh sách thả xuống **ID khách hàng trong kết quả** xác định khách hàng và chọn **Lưu**.
   Bạn cần chọn một thuộc tính từ đầu ra suy luận có giá trị tương tự như cột ID khách hàng của thực thể Khách hàng. Nếu không có cột như vậy trong tập hợp dữ liệu của bạn, hãy chọn một thuộc tính xác định duy nhất hàng.

## <a name="run-a-workflow"></a>Chạy quy trình

1. Trên trang **Mô hình tùy chỉnh**, chọn dấu 3 chấm dọc trong cột **Hành động** cạnh quy trình bạn vừa tạo trước đó.

1. Chọn **Chạy**.

Quy trình làm việc cũng chạy tự động với mỗi lần làm mới theo lịch trình. Tìm hiểu thêm về [cách thiết lập các lần làm mới theo lịch](system.md#schedule-tab).

## <a name="delete-a-workflow"></a>Xóa quy trình

1. Trên trang **Mô hình tùy chỉnh**, chọn dấu 3 chấm dọc trong cột **Hành động** cạnh quy trình bạn vừa tạo trước đó.

1. Chọn **Xóa** rồi xác nhận tác vụ xóa của bạn.

Quy trình của bạn sẽ bị xóa. [Thực thể](entities.md) đã được tạo khi bạn tạo quy trình sẽ vẫn tồn tại, và bạn có thể xem thực thể trên trang **Thực thể**.
