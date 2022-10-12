---
title: Mô hình máy học tùy chỉnh | Microsoft Docs
description: Làm việc với các mô hình tùy chỉnh của Azure Machine Learning trong Dynamics 365 Customer Insights.
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: zacookmsft
ms.author: zacook
manager: shellyha
searchScope:
- ci-custom-models
- customerInsights
ms.openlocfilehash: 89553b511d249fd586e36a1c4944a977513b0643
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609772"
---
# <a name="custom-machine-learning-models"></a>Mô hình máy học tùy chỉnh

> [!NOTE]
> Hỗ trợ cho máy học Studio (cổ điển) sẽ kết thúc vào ngày 31 tháng 8 năm 2024. Chúng tôi khuyên bạn nên chuyển sang [Azure máy học](/azure/machine-learning/overview-what-is-azure-machine-learning) vào ngày đó.
>
> Bắt đầu từ ngày 1 tháng 12 năm 2021, bạn sẽ không thể tạo tài nguyên máy học Studio (cổ điển) mới. Cho đến hết ngày 31 tháng 8 năm 2024, bạn có thể tiếp tục sử dụng các tài nguyên máy học Studio (cổ điển) hiện có. Để biết thêm thông tin, hãy xem [Di chuyển sang Azure máy học](/azure/machine-learning/migrate-overview).

Mô hình tùy chỉnh cho phép bạn quản lý quy trình công việc dựa trên mô hình Azure máy học. Quy trình làm việc giúp bạn chọn dữ liệu bạn muốn tạo thông tin chi tiết và ánh xạ kết quả với dữ liệu khách hàng hợp nhất của bạn. Để biết thêm thông tin về cách xây dựng mô hình ML tùy chỉnh, hãy xem [Sử dụng các mô hình dựa trên Azure Machine Learning](azure-machine-learning-experiments.md).

## <a name="prerequisites"></a>Điều kiện tiên quyết

- Các dịch vụ web được xuất bản thông qua [Đường ống dẫn hàng loạt Azure máy học](/azure/machine-learning/concept-ml-pipelines).
- Pipeline phải được xuất bản theo một [điểm cuối đường ống](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).
- Một [Tài khoản lưu trữ Azure Data Lake Gen2](/azure/storage/blobs/data-lake-storage-quickstart-create-account) liên kết với phiên bản Azure Studio của bạn.
- Đối với không gian làm việc Azure máy học có đường ống, Chủ sở hữu hoặc Người dùng truy cập Quản trị viên quyền đối với Không gian làm việc Azure máy học.

  > [!NOTE]
  > Dữ liệu được chuyển giữa các phiên bản Customer Insights của bạn và các dịch vụ web Azure hoặc quy trình đã chọn trong quy trình làm việc. Khi bạn chuyển dữ liệu sang dịch vụ Azure, vui lòng đảm bảo rằng dịch vụ được đặt cấu hình để xử lý dữ liệu theo cách thức và vị trí cần thiết để tuân thủ mọi yêu cầu pháp lý hoặc quy định đối với dữ liệu đó cho tổ chức của bạn.

## <a name="add-a-new-workflow"></a>Thêm quy trình mới

1. Chuyển đến **Thông tin** > **Mô hình tùy chỉnh** rồi chọn **Quy trình làm việc mới**.

1. Cung cấp một **Tên**.

   :::image type="content" source="media/new-workflowv2.png" alt-text="Ảnh chụp màn hình ngăn quy trình làm việc mới.":::

1. Chọn tổ chức chứa dịch vụ web trong **Đối tượng thuê chứa dịch vụ web**.

1. Nếu đăng ký Azure Machine Learning khác với đối tượng thuê trong Customer Insights, hãy chọn **Đăng nhập** bằng thông tin đăng nhập của bạn cho tổ chức đã chọn.

1. Chọn **Không gian làm việc** được liên kết với dịch vụ web của bạn.

1. Chọn đường dẫn Azure máy học trong **Dịch vụ web chứa mô hình của bạn** trình đơn thả xuống. Sau đó, chọn **Tiếp**.
   Tìm hiểu thêm về [phát hành một quy trình trong Azure Machine Learning bằng cách sử dụng trình thiết kế](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) hoặc [SDK](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).

1. Đối với từng **Đầu vào dịch vụ web**, hãy chọn **Thực thể** phù hợp từ Customer Insights. Sau đó, chọn **Tiếp**.
   > [!NOTE]
   > Quy trình làm việc của mô hình tùy chỉnh sẽ áp dụng phương pháp phỏng đoán để ánh xạ các trường đầu vào của dịch vụ web với các thuộc tính thực thể dựa trên tên và kiểu dữ liệu của trường. Bạn sẽ thấy lỗi nếu không thể ánh xạ trường dịch vụ web tới một thực thể.

   :::image type="content" source="media/intelligence-screen2-updated.png" alt-text="Đặt cấu hình cho quy trình.":::

1. Vì **Tham số đầu ra mô hình**, đặt các thuộc tính sau:
   - **Tên thực thể** cho kết quả đầu ra của đường ống
   - **Tên thông số đầu ra kho dữ liệu** của đường ống hàng loạt của bạn
   - **Tên thông số Đường dẫn đầu ra** của đường ống hàng loạt của bạn

   :::image type="content" source="media/intelligence-screen3-outputparameters.png" alt-text="Ngăn tham số đầu ra của mô hình.":::

1. Chọn thuộc tính phù hợp từ **ID khách hàng trong kết quả** xác định khách hàng và chọn **Tiết kiệm**.

   :::image type="content" source="media/intelligence-screen4-relatetocustomer.png" alt-text="Liên kết kết quả với ngăn Dữ liệu khách hàng.":::

   Các **Dòng công việc đã được lưu** màn hình hiển thị chi tiết về quy trình làm việc. Nếu bạn đã định cấu hình quy trình làm việc cho đường dẫn Azure máy học, thì Customer Insights sẽ đính kèm vào không gian làm việc chứa đường dẫn. Thông tin chi tiết về khách hàng sẽ nhận được một **Người đóng góp** vai trò trên không gian làm việc Azure.

1. Chọn **Xong**. Các **Mô hình tùy chỉnh** hiển thị trang.

1. Chọn dấu chấm lửng dọc (&vellip;) cho quy trình làm việc và chọn **Chạy**. Quy trình làm việc của bạn cũng tự động chạy với mọi [làm mới theo lịch trình](schedule-refresh.md).

## <a name="manage-an-existing-workflow"></a>Quản lý quy trình làm việc hiện có

Đi đến **Sự thông minh** > **Mô hình tùy chỉnh** để xem các quy trình công việc bạn đã tạo.

Chọn một quy trình làm việc để xem các hành động có sẵn.

- **Chỉnh sửa** một quy trình làm việc
- **Chạy** một quy trình làm việc
- [**Xóa bỏ**](#delete-a-workflow) một quy trình làm việc

### <a name="edit-a-workflow"></a>Chỉnh sửa quy trình

1. Đi đến **Sự thông minh** > **Mô hình tùy chỉnh**.

1. Bên cạnh dòng công việc bạn muốn cập nhật, hãy chọn dấu chấm lửng dọc (&vellip;) và chọn **Chỉnh sửa**.

1. Biến đổi **Tên hiển thị** nếu cần, và chọn **Tiếp theo**.

1. Cho mỗi **Đầu vào dịch vụ web**, cập nhật kết quả phù hợp **Thực thể** từ Thông tin chi tiết về khách hàng, nếu cần. Sau đó, chọn **Tiếp**.

1. Vì **Tham số đầu ra mô hình**, thay đổi bất kỳ điều nào sau đây:
   - **Tên thực thể** cho kết quả đầu ra của đường ống
   - **Tên thông số đầu ra kho dữ liệu** của đường ống hàng loạt của bạn
   - **Tên thông số Đường dẫn đầu ra** của đường ống hàng loạt của bạn

1. Thay đổi thuộc tính phù hợp từ **ID khách hàng trong kết quả** để xác định khách hàng. Chọn một thuộc tính từ đầu ra suy luận có giá trị tương tự như cột ID khách hàng của thực thể Khách hàng. Nếu bạn không có cột như vậy trong tập dữ liệu của mình, hãy chọn một thuộc tính xác định duy nhất hàng.

1. Chọn **Lưu**

### <a name="delete-a-workflow"></a>Xóa quy trình

1. Đi đến **Sự thông minh** > **Mô hình tùy chỉnh**.

1. Bên cạnh dòng công việc bạn muốn xóa, hãy chọn dấu chấm lửng dọc (&vellip;) và chọn **Xóa bỏ**.

1. Xác nhận tác vụ xóa của bạn.

Quy trình của bạn sẽ bị xóa. Các [thực thể](entities.md) được tạo khi bạn tạo dòng công việc vẫn tồn tại và có thể được xem từ **Dữ liệu** > **Thực thể** trang.

## <a name="view-the-results"></a>Xem kết quả

Kết quả từ quy trình làm việc được lưu trữ trong tên thực thể được xác định cho **Tham số đầu ra mô hình**. Truy cập dữ liệu này từ [**Dữ liệu** > **Thực thể** trang](entities.md) Hoặc với [Quyền truy cập API](apis.md).

### <a name="api-access"></a>Truy cập API

Đối với truy vấn OData cụ thể để lấy dữ liệu từ thực thể mô hình tùy chỉnh, hãy sử dụng định dạng sau:

`https://api.ci.ai.dynamics.com/v1/instances/<your instance id>/data/<custom model output entity name>%3Ffilter%3DCustomerId%20eq%20'<guid value>'`

1. Thay thế`<your instance id>` với ID của môi trường Thông tin chi tiết về khách hàng, sẽ hiển thị trong thanh địa chỉ của trình duyệt khi truy cập Thông tin chi tiết về khách hàng.

1. Thay thế`<custom model output entity>` với tên pháp nhân bạn đã cung cấp cho **Tham số đầu ra mô hình**.

1. Thay thế`<guid value>` với ID khách hàng của khách hàng mà bạn muốn truy cập. ID này hiển thị trên [trang hồ sơ khách hàng](customer-profiles.md) trong trường CustomerID.

## <a name="frequently-asked-questions"></a>Câu hỏi thường gặp

- Tại sao tôi không thể thấy đường dẫn của mình khi thiết lập quy trình làm việc của mô hình tùy chỉnh?
  Sự cố này thường do sự cố cấu hình trong quy trình gây ra. Đảm bảo [tham số đầu vào được định cấu hình](azure-machine-learning-experiments.md#dataset-configuration), và [tham số đường dẫn và kho dữ liệu đầu ra](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights) cũng được định cấu hình.

- Lỗi "Không thể lưu quy trình làm việc thông minh" có nghĩa là gì? 
  Người dùng thường thấy thông báo lỗi này nếu họ không có quyền của Chủ sở hữu hoặc Quản trị viên quyền truy cập của người dùng trên không gian làm việc. Người dùng cần cấp quyền cao hơn để cho phép Customer Insights xử lý quy trình làm việc như một dịch vụ thay vì sử dụng thông tin đăng nhập của người dùng cho các lần chạy quy trình công việc tiếp theo.

- Một điểm cuối riêng tư / liên kết riêng tư cho dòng công việc mô hình tùy chỉnh của tôi có được hỗ trợ không?
  Thông tin chi tiết về khách hàng hiện không hỗ trợ điểm cuối riêng tư cho các mô hình tùy chỉnh ngoài hộp, nhưng có sẵn một giải pháp thủ công. Vui lòng liên hệ với bộ phận hỗ trợ để biết thêm chi tiết.

## <a name="responsible-ai"></a>AI có trách nhiệm

Dự đoán cung cấp các khả năng để tạo ra trải nghiệm khách hàng tốt hơn, cải thiện khả năng kinh doanh và luồng doanh thu. Chúng tôi thực sự khuyên bạn nên cân bằng giá trị của dự đoán so với tác động của nó và những thành kiến có thể được đưa ra theo cách có đạo đức. Tìm hiểu thêm về cách Microsoft [giải quyết AI có trách nhiệm](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6). Bạn cũng có thể tìm hiểu về [kỹ thuật và quy trình cho máy học chịu trách nhiệm](/azure/machine-learning/concept-responsible-ml) cụ thể cho Azure Machine Learning.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElk]

[!INCLUDE [footer-include](includes/footer-banner.md)]
