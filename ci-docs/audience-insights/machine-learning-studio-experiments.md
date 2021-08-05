---
title: Thử nghiệm Machine Learning Studio (cổ điển)
description: Sử dụng các mô hình Machine Learning Studio (cổ điển) trong Dynamics 365 Customer Insights.
ms.date: 12/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: ameetj
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 2eb44604e72b32292f971754d4f8c4fd1988c697
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 07/13/2021
ms.locfileid: "6555195"
---
# <a name="use-models-based-on-azure-machine-learning-studio-classic"></a>Sử dụng các mô hình dựa trên Azure Machine Learning Studio (cổ điển)

Dữ liệu hợp nhất trong Dynamics 365 Customer Insights là nguồn để xây dựng các mô hình máy học có thể tạo thêm thông tin chi tiết về doanh nghiệp. Customer Insights tích hợp với Machine Learning Studio (cổ điển) để sử dụng các mô hình tùy chỉnh của riêng bạn. Để biết cách tích hợp các mô hình được phát triển trong Azure Machine Learning với Customer Insights, hãy xem [Thử nghiệm Azure Machine Learning](azure-machine-learning-experiments.md).

## <a name="prerequisites"></a>Điều kiện tiên quyết

- Truy cập Customer Insights
- Gói đăng ký Azure Enterprise hiện hoạt
- [Hồ sơ khách hàng hợp nhất](data-unification.md)
- [Xuất thực thể sang bộ nhớ Azure Blob](export-azure-blob-storage.md) thiết lập

## <a name="set-up-machine-learning-studio-classic"></a>Thiết lập Machine Learning Studio Cổ điển

Trong bước đầu tiên, chúng ta cần tạo không gian làm việc và mở Machine Learning Studio (cổ điển).

1. Truy cập[https://www.portal.azure.com](https://www.portal.azure.com/) và đăng nhập.

1. Chọn **Tạo nguồn lực**.

1. Tìm kiếm **Không gian làm việc Studio máy học** rồi chọn **Tạo**.

1. Nhập các chi tiết cần thiết để [tạo không gian làm việc](/azure/machine-learning/studio/create-workspace). Chọn **Bậc định giá gói dịch vụ web** dựa trên lượng dữ liệu bạn muốn nhập. Để có hiệu suất tốt nhất, hãy chọn **Vị trí** gần nhất về mặt địa lý với bạn.

1. Sau khi tạo nguồn lực, bảng thông tin không gian làm việc Studio máy học sẽ xuất hiện. Chọn **Khởi chạy Studio máy học**.

   ![Giao diện người dùng Studio máy học của Azure.](media/azure-machine-learning-studio.png)

## <a name="work-with-azure-machine-learning-studio"></a>Làm việc với Studio máy học của Azure

Giờ đây, bạn có thể tạo một thử nghiệm mới hoặc nhập một mẫu thử nghiệm hiện có từ thư viện mẫu. Có các thử nghiệm mẫu cho ba trường hợp tiêu chuẩn:

- [Dự đoán khả năng rời đi](#churn-analysis)

- [Giá trị trọn đời của khách hàng](#customer-lifetime-value-prediction)

- [Đề xuất sản phẩm hoặc hành động tốt nhất tiếp theo](#productrecommendation-or-next-best-action)

1. Nếu bạn tạo thử nghiệm mới hoặc sử dụng mẫu thử nghiệm từ thư viện, bạn cần đặt cấu hình thuộc tính **Nhập dữ liệu**. Sử dụng trải nghiệm được hướng dẫn hoặc trực tiếp cung cấp thông tin chi tiết để truy cập Azure Blob Storage chứa dữ liệu của bạn.  

   ![Thử nghiệm Studio máy học của Azure.](media/azure-machine-learning-studio-experiment.png)

1. Giờ đây, bạn có thể xây dựng một quy trình bán hàng xử lý tùy chỉnh để làm sạch và xử lý trước dữ liệu, trích xuất các đặc điểm và đào tạo một mô hình phù hợp.

1. Kiểm tra và tối ưu hóa hiệu suất của mô hình.

1. Khi bạn hài lòng với chất lượng của một mô hình, hãy chọn **Thiết lập dịch vụ web** > **Dịch vụ web dự đoán**. Tùy chọn này nhập mô hình được đào tạo và quy trình bán hàng phát triển các đặc điểm bổ sung từ thử nghiệm đào tạo đến dịch vụ dự đoán. Dịch vụ dự đoán có thể lấy một tập hợp dữ liệu đầu vào khác với lược đồ được sử dụng trong thử nghiệm đào tạo để đưa ra dự đoán.

   ![Thiết lập dịch vụ web dự đoán.](media/predictive-webservice-control.png)

1. Sau khi thử nghiệm dịch vụ web dự đoán thành công, bạn có thể triển khai nó để lập lịch tự động. Để dịch vụ web hoạt động với Customer Insights, hãy chọn **Triển khai dịch vụ web** > **Xem trước Triển khai dịch vụ web [Mới]**. [Tìm hiểu thêm về việc triển khai dịch vụ web](/azure/machine-learning/studio/deploy-a-machine-learning-web-service)

   ![Triển khai dịch vụ web dự đoán.](media/predictive-webservice-deploy.png)

## <a name="sample-models-from-the-gallery"></a>Các chế độ mẫu từ thư viện

Chúng tôi sẽ sử dụng một kịch bản hư cấu về Khách sạn Contoso cho các mô hình trong bài viết này. Khách sạn Contoso thu thập các dữ liệu sau:

- Dữ liệu CRM bao gồm hoạt động lưu trú tại khách sạn. Tập hợp dữ liệu bao gồm thông tin về ngày lưu trú của từng khách hàng đã đăng ký. Nó cũng chứa thông tin về đặt phòng, loại phòng, chi tiết chi tiêu, v.v. Dữ liệu kéo dài bốn năm, từ tháng 1 năm 2014 đến tháng 1 năm 2018.
- Hồ sơ khách hàng của khách trong khách sạn. Những hồ sơ này chứa thông tin về từng khách hàng, bao gồm tên, ngày sinh, địa chỉ bưu điện, giới tính và số điện thoại của họ.
- Sử dụng các dịch vụ do khách sạn cung cấp, chẳng hạn như spa, giặt là, Wi-Fi hoặc chuyển phát nhanh. Thông tin này được ghi lại cho mỗi khách hàng đã đăng ký. Thông thường, việc sử dụng các dịch vụ được liên kết với việc lưu trú. Trong một số trường hợp, khách hàng có thể sử dụng dịch vụ mà không cần lưu trú trong khách sạn.

## <a name="churn-analysis"></a>Phân tích khả năng rời đi

Phân tích khả năng rời đi áp dụng cho các lĩnh vực kinh doanh khác nhau. Trong ví dụ này, chúng ta sẽ xem xét khả năng ngừng sử dụng dịch vụ, cụ thể là trong bối cảnh của các dịch vụ khách sạn như được mô tả ở trên. Nó cung cấp một ví dụ hoạt động của một quy trình bán hàng mô hình toàn diện có thể được sử dụng làm điểm khởi đầu cho bất kỳ loại mô hình rời đi nào khác.

### <a name="definition-of-churn"></a>Định nghĩa của việc rời đi

Định nghĩa của việc rời đi có thể khác nhau tùy theo tình huống. Trong ví dụ này, một khách đã không ghé thăm khách sạn trong năm qua sẽ được gắn nhãn là đã rời đi.  

Mẫu thử nghiệm có thể được nhập từ thư viện. Trước tiên, hãy đảm bảo rằng bạn nhập dữ liệu cho **Hoạt động lưu trú tại khách sạn**, **Dữ liệu khách hàng** và **Dữ liệu sử dụng dịch vụ** từ bộ nhớ Azure Blob.

   ![Nhập dữ liệu cho mô hình rời đi.](media/import-data-azure-blob-storage.png)

### <a name="featurization"></a>Phát triển các đặc điểm bổ sung

Dựa trên định nghĩa của việc rời đi, trước tiên chúng tôi xác định các đặc điểm thô sẽ ảnh hưởng đến nhãn. Sau đó, chúng tôi xử lý các đặc điểm thô này thành đặc điểm dạng số có thể dùng với mô hình học trên máy. Tích hợp dữ liệu diễn ra trong Customer Insights để chúng tôi có thể kết hợp các bảng này bằng cách sử dụng *ID khách hàng*.

   ![Kết hợp dữ liệu đã nhập.](media/join-imported-data.png)

Việc phát triển các đặc điểm bổ sung để xây dựng mô hình nhằm phân tích khả năng rời đi có thể hơi phức tạp. Dữ liệu là một hàm thời gian với hoạt động mới của khách sạn được ghi lại hàng ngày. Trong quá trình phát triển các đặc điểm bổ sung, chúng tôi muốn tạo các đặc điểm tĩnh từ dữ liệu động. Trong trường hợp này, chúng tôi tạo ra nhiều đặc điểm từ hoạt động của khách sạn với cửa sổ trượt trong một năm. Chúng tôi cũng mở rộng các đặc điểm phân loại như loại phòng hoặc loại đặt phòng thành các đặc điểm riêng biệt bằng cách sử dụng mã hóa one-hot.  

Danh sách cuối cùng của các đặc điểm:

| **Số**  | **Original_Column**          | **Các đặc điểm bắt nguồn**                                                                                                                      |
|-------------|------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|
| 1           | Loại phòng                    | RoomTypeLargeCount, RoomTypeSmallCount                                                                                                    |
| 2           | Loại Đăng ký                 | BookingTypeOnlineCount, BookingTypePhoneCallCount                                                                                         |
| 3           | Danh mục di chuyển              | TravelCategoryBusinessCount, TravelCategoryLeisureCount                                                                                   |
| 4           | Đô la đã chi                | TotalDollarSpent                                                                                                                          |
| 5           | Ngày nhận phòng và ngày thanh toán  | StayDayCount, StayDayCount2016, StayDayCount2015, StayDayCount2014, StayCount, StayCount2016. StayCount2015, StayCount2014                |
| 6           | Việc sử dụng dịch vụ                | UsageTenure, ConciergeUsage, CourierUsage, DryCleaningUsage, GymUsage, PhoneUsage, RestaurantUsage, SpaUsage, TelevisionUsage, WifiUsage  |

### <a name="model-selection"></a>Lựa chọn chế độ

Bây giờ chúng ta cần chọn thuật toán tối ưu để sử dụng. Trong trường hợp này, hầu hết các đặc điểm đều dựa trên các đặc điểm phân loại. Thông thường, các mô hình dựa trên cây quyết định hoạt động tốt. Nếu chỉ có các đặc điểm số, mạng nơ-ron có thể là lựa chọn tốt hơn. Máy vectơ hỗ trợ (SVM) cũng hữu ích trong những tình huống như vậy; tuy nhiên, nó cần khá nhiều điều chỉnh để trích xuất hiệu suất tốt nhất. Chúng tôi chọn **Cây quyết định tăng cường hai lớp** là mô hình được lựa chọn đầu tiên, tiếp theo là **SVM hai lớp** làm mô hình thứ hai. Studio máy học của Azure cho phép bạn thực hiện thử nghiệm A/B, vì vậy sẽ có lợi khi bắt đầu với hai mô hình thay vì một.

Hình ảnh sau đây cho thấy quy trình đào tạo và đánh giá mô hình từ Studio máy học của Azure:

![Mô hình rời đi trong Studio máy học của Azure.](media/azure-machine-learning-model.png)

Chúng tôi cũng áp dụng một kỹ thuật gọi là **Tầm quan trọng của đặc điểm hoán vị**, một khía cạnh quan trọng của tối ưu hóa mô hình. Các mô hình tích hợp có rất ít hoặc không có thông tin chuyên sâu về tác động của bất kỳ đặc điểm cụ thể nào đối với dự đoán cuối cùng. Máy tính mức độ quan trọng của đặc điểm sử dụng một thuật toán tùy chỉnh để tính toán ảnh hưởng của các đặc điểm riêng lẻ đến kết quả của một mô hình cụ thể. Mức độ quan trọng của đặc điểm được chuẩn hóa từ +1 đến -1. Ảnh hưởng tiêu cực có nghĩa là đặc điểm tương ứng có ảnh hưởng ngược lại trực quan đến kết quả và cần được loại bỏ khỏi mô hình. Ảnh hưởng tích cực cho thấy đặc điểm này đang đóng góp rất nhiều vào dự đoán. Các giá trị này không phải là hệ số tương quan vì chúng là các chỉ số khác nhau. Để biết thêm thông tin, hãy xem [Tầm quan trọng của đặc điểm hoán vị](/azure/machine-learning/studio-module-reference/permutation-feature-importance).

Toàn bộ [thử nghiệm rời đi có sẵn trong Thư viện trí tuệ nhân tạo Azure](https://gallery.azure.ai/Experiment/Hotel-Churn-Predictive-Exp).

## <a name="customer-lifetime-value-prediction"></a>Dự đoán giá trị trọn đời của khách hàng

Việc tính toán giá trị trọn đời của khách hàng (CLTV) là một trong những số liệu chính mà doanh nghiệp có thể sử dụng để đánh giá và phân khúc khách hàng của mình. Đối với kinh doanh khách sạn, điều quan trọng là phải biết khách hàng của họ. Ví dụ: hiểu các yếu tố tạo nên khách hàng tốt là thông tin quan trọng. Nó giúp ban quản lý khách sạn đánh giá họ cần tập trung vào những đặc điểm nào và cải tiến để làm hài lòng những khách hàng trả tiền cao của họ. Những quyết định này có thể có tác động trực tiếp đến doanh số bán hàng và thu nhập.  

### <a name="definition-of-cltv"></a>Định nghĩa về CLTV

Đối với ví dụ này, chúng tôi xác định CLTV của một khách hàng là tổng số tiền mà khách hàng dự kiến sẽ chi trong 365 ngày tới. Chúng tôi sẽ sử dụng dữ liệu có giá trị trong ba năm qua cho tất cả khách hàng để dự đoán giá trị này.

### <a name="featurization"></a>Phát triển các đặc điểm bổ sung

Trong trường hợp này, việc phát triển các đặc điểm bổ sung sẽ giống như tình huống rời đi. Tuy nhiên, các nhãn và giá trị dự đoán khác với định nghĩa ở trên.

### <a name="model-selection"></a>Lựa chọn chế độ

Dự đoán CLTV là một bài toán hồi quy vì giá trị dự đoán là một biến liên tục có giá trị dương. Dựa trên các thuộc tính đối tượng, chúng tôi chọn **Hồi quy cây quyết định tăng cường** như một thuật toán và **Hồi quy mạng nơ-ron** như một thuật toán khác để đào tạo mô hình.

## <a name="product-recommendation-or-next-best-action"></a>Đề xuất sản phẩm hoặc Hành động tốt nhất tiếp theo

Đề xuất sản phẩm trong kịch bản khách sạn được hiểu là giới thiệu các dịch vụ do khách sạn cung cấp cho khách hàng. Mục tiêu là lựa chọn các dịch vụ phù hợp cho khách hàng sao cho hiệu quả sử dụng của họ là tối đa. Nó tương tự như các đề xuất phim cho người dùng dịch vụ phát trực tuyến video.

### <a name="definition-of-product-recommendation-or-next-best-action"></a>Định nghĩa đề xuất sản phẩm hoặc hành động tốt nhất tiếp theo

Chúng tôi xác định mục tiêu là tối đa hóa số tiền sử dụng dịch vụ bằng cách cung cấp các dịch vụ phù hợp nhất cho khách hàng theo sở thích của họ.

### <a name="featurization"></a>Phát triển các đặc điểm bổ sung

Giống như mô hình rời đi, chúng tôi đang kết hợp ServiceCustomerID của khách sạn với CustomerID để tạo các đề xuất nhất quán cho mỗi CustomerID.

![Phát triển đặc điểm bổ sung của mô hình đề xuất.](media/azure-machine-learning-model-featurization.png)

Dữ liệu được lấy từ ba thực thể khác nhau và các đặc điểm được lấy từ chúng. Việc phát triển đặc điểm bổ sung cho vấn đề khuyến nghị khác với tình huống rời đi hoặc CLTV. Mô hình khuyến nghị cần dữ liệu đầu vào dưới dạng ba bộ đặc điểm.

### <a name="model-selection"></a>Lựa chọn chế độ

Chúng tôi dự đoán các sản phẩm hoặc dịch vụ bằng cách sử dụng thuật toán được gọi là **Trình đề xuất hộp đối sánh đào tạo** để đào tạo mô hình khuyến nghị.

![Thuật toán đề xuất sản phẩm.](media/azure-machine-learning-model-recommendation-algorithm.png)

Ba cổng đầu vào cho mô hình **Trình đề xuất hộp đối sánh đào tạo** lấy dữ liệu sử dụng dịch vụ đào tạo, mô tả khách hàng (tùy chọn) và mô tả dịch vụ. Có ba cách khác nhau để cho tính điểm mô hình. Một là để đánh giá mô hình trong đó điểm Độ lợi tích lũy giảm dần (NDCG) được tính để xếp hạng các mặt hàng được xếp hạng. Trong thử nghiệm này, chúng tôi có điểm NDCG là 0,97. Hai tùy chọn khác là chấm điểm mô hình trên toàn bộ danh mục dịch vụ được đề xuất, hoặc chỉ cho điểm trên các mặt hàng mà người dùng chưa sử dụng trước đó.

Xem xét thêm về việc phân phối các đề xuất trên toàn bộ danh mục dịch vụ, chúng tôi nhận thấy rằng điện thoại, Wi-Fi và chuyển phát nhanh là những dịch vụ hàng đầu được đề xuất. Điều này phù hợp với những gì chúng tôi tìm thấy từ việc phân phối dữ liệu tiêu thụ dịch vụ:

![Đầu ra mô hình đề xuất.](media/azure-machine-learning-model-output.png)

Toàn bộ [thử nghiệm đề xuất sản phẩm có thể được truy cập trong Thư viện trí tuệ nhân tạo Azure.](https://gallery.azure.ai/Experiment/Recommendation-4)

## <a name="integrate-custom-models"></a>Tích hợp mô hình tùy chỉnh

Để sử dụng những dự đoán này trong Customer Insights, bạn cần **xuất** dự đoán cùng với ID khách hàng. [Xuất chúng sang cùng một vị trí lưu trữ Azure Blob](/azure/storage/common/storage-import-export-data-from-blobs) mà bạn xuất dữ liệu nguồn sang. Dịch vụ web dự đoán có thể được lên lịch chạy thường xuyên và cập nhật điểm số.

Dữ liệu do mô hình tùy chỉnh tạo ra có thể được sử dụng để tăng cường thêm dữ liệu khách hàng của bạn. Để biết thêm thông tin, hãy xem [Mô hình máy học tùy chỉnh](custom-models.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]