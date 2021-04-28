---
title: Các tính năng mới sắp ra mắt
description: Thông tin về các tính năng mới, cải tiến và sửa lỗi.
ms.date: 04/07/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: midevane
manager: shellyha
ms.openlocfilehash: 2159481f9355de738a7b457dcf0849a45c3e08db
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896261"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>Có gì mới trong khả năng thông tin chi tiết về đối tượng của Dynamics 365 Customer Insights

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Chúng tôi rất vui được công bố các bản cập nhật mới nhất của mình! Bài viết này tóm tắt các tính năng xem trước công khai, các điểm cải tiến được phát hành rộng rãi và những điểm cập nhật tính năng. Để xem các kế hoạch dài hạn đối với tính năng, hãy xem [kế hoạch phát hành Dynamics 365 và Power Platform](/dynamics365/release-plans/).

Chúng tôi sẽ triển khai các điểm cập nhật trên cơ sở từng khu vực. Do đó, một số khu vực sẽ thấy các tính năng trước khu vực khác. Trừ khi có lưu ý khác, bạn sẽ không phải thực hiện nào và chúng tôi sẽ tự động cập nhật ứng dụng mà không gây ra thời gian ngừng hoạt động.

> [!TIP]
> Để gửi và bình chọn cho các yêu cầu về tính năng cũng như gợi ý về sản phẩm, hãy truy cập vào [Cổng ý tưởng ứng dụng Dynamics 365](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).

## <a name="march-2021-updates"></a>Các bản cập nhật tháng 3 năm 2021

Các bản cập nhật vào tháng 3 năm 2021 bao gồm một số tính năng, bản nâng cấp hiệu suất và sửa lỗi.

### <a name="activities"></a>Hoạt động

- **Trình hướng dẫn hoạt động và các loại ngữ nghĩa** Chúng tôi đã cải thiện và cập nhật trải nghiệm ánh xạ hoạt động để hướng dẫn và đơn giản hóa việc tạo quá trình ánh xạ hoạt động. Trong phiên bản mới này, người dùng nhận được trải nghiệm có hướng dẫn để giúp hoàn thành từng bước của quy trình. Ở bước ánh xạ hoạt động, ngoài việc chọn từ nhiều loại hoạt động, người dùng có thể chọn ánh xạ dữ liệu theo ngữ nghĩa cho *Subscription* và/hoặc *SalesOrderLine* với các lược đồ theo tiêu chuẩn của ngành (có thể được dùng cho trường hợp sử dụng ở hạ nguồn).    
  Để biết thêm thông tin, hãy xem [Hoạt động của khách hàng](activities.md).

### <a name="data-ingestion"></a>Nhập dữ liệu

- **Kết nối với nguồn dữ liệu tại chỗ bằng cách sử dụng các cổng và luồng dữ liệu Power Platform** Chúng tôi vui mừng công bố bản xem trước của luồng dữ liệu Power Platform và khả năng kết nối tại chỗ thông qua các cổng trong Customer Insights có môi trường Power Platform hoặc Dataverse được liên kết. Mọi nguồn dữ liệu mới tạo trong môi trường Customer Insights có môi trường Dataverse được liên kết sẽ mặc định là luồng dữ liệu Power Platform mang lại khả năng kết nối dữ liệu tại chỗ và một bộ trình kết nối cũng như khả năng chuyển đổi phong phú.

### <a name="extensibility"></a>Khả năng mở rộng

- **Nội dung xuất được sắp xếp theo các kết nối và nội dung xuất** Chúng tôi đã thay đổi tên của trang **Đích xuất** thành **Kết nối** và đã thêm một trang riêng biệt cho **Nội dung xuất**. Là một phần của bản cập nhật này, chúng tôi sẽ chuyển các nội dung xuất hiện có thành các cặp kết nối và nội dung xuất sử dụng kết nối đó. Quản trị viên hiện đã hiểu rõ hơn về dữ liệu gửi đi trên trang **Kết nối**. Tất cả các vai trò người dùng đều có quyền truy cập vào trang **Nội dung xuất** nhưng chỉ có quản trị viên là có thể chọn cho phép người đóng góp chỉnh sửa các nội dung xuất cụ thể bằng các kết nối được chia sẻ.     
  Để biết thêm thông tin, hãy xem [Tổng quan về kết nối](connections.md) và [Tổng quan về nội dung xuất](export-destinations.md).

- **Xuất phân khúc sang Campaign Monitor** Chúng tôi đã mở rộng các đích xuất của mình để bao gồm cả Campaign Monitor. Giờ đây, bạn có thể xuất các phân khúc từ danh sách trên Customer Insights sang Campaign Monitor và sử dụng chúng làm cơ sở cho các chiến dịch tiếp thị của mình.    
   Để biết thêm thông tin, hãy xem [Xuất sang Campaign Monitor](export-campaign-monitor.md).

- **Xuất phân khúc sang Constant Contact** Chúng tôi đã mở rộng các đích xuất của mình để bao gồm cả Constant Contact. Giờ đây, bạn có thể xuất các phân khúc từ danh sách trên Customer Insights sang Constant Contact và sử dụng chúng làm cơ sở cho các chiến dịch tiếp thị của mình.   
   Để biết thêm thông tin, hãy xem [Xuất sang Constant Contact](export-constant-contact.md).

- **Xuất phân khúc sang RollWorks** Chúng tôi đã mở rộng các đích xuất của mình để bao gồm cả RollWorks. Giờ đây, bạn có thể xuất các phân khúc từ Customer Insights sang RollWorks audiences và sử dụng chúng làm cơ sở cho quảng cáo B2B của bạn.    
   Để biết thêm thông tin, hãy xem [Xuất sang RollWorks ](export-rollworks.md).

- **Xuất phân khúc sang Snapchat** Chúng tôi đã mở rộng các đích xuất của mình để bao gồm cả Snapchat. Giờ đây, bạn có thể xuất các phân khúc từ Customer Insights sang Snapchat và sử dụng chúng làm cơ sở cho quảng cáo của bạn.     
   Để biết thêm thông tin, hãy xem [Xuất sang Snapchat](export-snapchat.md).

### <a name="predictions"></a>Dự đoán

- **Sử dụng bộ lọc sản phẩm trong các đề xuất về sản phẩm dự đoán** Chúng tôi đã thêm tính năng sử dụng bộ lọc sản phẩm trong mô hình đề xuất sản phẩm của mình. Giờ đây, bạn có thể tạo dự đoán chỉ sử dụng một tập hợp con các sản phẩm của bạn.    
   Để biết thêm thông tin, hãy xem [Đặt cấu hình bộ lọc sản phẩm](predict-product-recommendation.md#configure-product-filters).

- **Tạo phân khúc từ dự đoán mô hình** Chúng tôi đã bổ sung một cách thức nhanh chóng để tạo phân khúc bằng kết quả của mô hình dự đoán. Từ trang kết quả của mô hình, bạn có thể dễ dàng tạo một phân khúc mới bằng cách chọn tùy chọn **Tạo phân khúc**.    
  Để biết thêm thông tin, hãy xem [Tạo phân khúc dựa trên mô hình dự đoán](prediction-based-segment.md).

- **Giải thích cho các đề xuất về sản phẩm** Chúng tôi đã bổ sung thông tin giải thích các yếu tố chính mà mô hình AI học được để đưa ra các đề xuất về sản phẩm và mức độ mà các yếu tố đó đóng góp vào các đề xuất về sản phẩm. Thông tin này được thêm vào màn hình kết quả của mô hình.    
   Để biết thêm thông tin, hãy xem [Xem lại dự đoán trạng thái và kết quả](predict-product-recommendation.md#review-a-prediction-status-and-results).

## <a name="february-2021-updates"></a>Bản cập nhật tháng 2 năm 2021

Các bản cập nhật vào tháng 2 năm 2021 bao gồm một số tính năng, nâng cấp hiệu suất và sửa lỗi.

#### <a name="extensibility"></a>Khả năng mở rộng

- **Xuất phân khúc sang AdRoll**

  Chúng tôi đã mở rộng các đích xuất để bao gồm AdRoll. Giờ đây, bạn có thể xuất các phân khúc từ Customer Insights hàng sang đối tượng AdRoll và sử dụng chúng làm cơ sở cho quảng cáo của mình. Để biết thêm thông tin, hãy xem [Trình kết nối cho AdRoll](export-adroll.md).

#### <a name="segments"></a>Phân khúc
 
- **Sao chép phân đoạn**
  
  Để tạo một phân khúc mới dựa trên một phân khúc hiện có, bạn có thể sao chép một phân khúc và chỉnh sửa phân khúc đã sao chép để tinh chỉnh thêm. 

- **Thêm các thuộc tính bổ sung vào một phân khúc**

  Giờ đây, bạn có thể bao gồm các thuộc tính trong đầu ra phân khúc, ngay cả khi các thuộc tính này không phải là một phần của hồ sơ khách hàng. Ví dụ: bao gồm các ID đăng ký trong một phân khúc mặc dù nó là một phần của thực thể đăng ký có mối quan hệ M: 1 với thực thể khách hàng. Miễn là thuộc tính thuộc về một thực thể có liên quan đến thực thể khách hàng, bây giờ bạn có thể bao gồm các thuộc tính này.  

#### <a name="predictions"></a>Dự đoán

- **Tạo đề xuất dự đoán về sản phẩm**

  Hiểu những gì khách hàng quan tâm khi mua hàng là một trong những bước đầu tiên cần thiết để cải thiện doanh thu kinh doanh và xây dựng lòng trung thành của khách hàng thông qua cá nhân hóa và tương tác. Việc cung cấp các đề xuất cho các sản phẩm không phù hợp với sở thích của khách hàng có thể tạo ra cảm giác mất kết nối giữa khách hàng và doanh nghiệp của bạn và cuối cùng hạn chế doanh thu tiềm năng và trải nghiệm tổng thể cho khách hàng. 

  Sử dụng dữ liệu của riêng bạn, giờ đây bạn có thể tạo dự đoán cho những sản phẩm mà khách hàng của bạn có khả năng mua trong tương lai. Để biết thêm thông tin, hãy xem [Đề xuất sản phẩm dự đoán](predict-product-recommendation.md).

#### <a name="system-administration"></a>Quản trị hệ thống

- **Môi trường sao chép hỗ trợ nhiều loại nguồn dữ liệu hơn**

  Quản trị viên có thể sao chép cấu hình môi trường sang môi trường mới trong cùng một tổ chức. Tính năng này mở rộng chức năng môi trường sao chép cho các trường hợp trong đó các nguồn dữ liệu dựa trên kho dữ liệu Common Data Service hoặc một thư mục Common Data Model được sử dụng.

## <a name="january-2021-updates"></a>Bản cập nhật tháng 1 năm 2021

Bản cập nhật tháng 1 năm 2021 bao gồm một vài tính năng, nâng cấp hiệu suất và sửa lỗi.

#### <a name="extensibility"></a>Khả năng mở rộng

- **Chức năng mở rộng và hiệu suất nâng cao cho chức năng xuất SFTP** Giờ đây, bạn có thể xuất tất cả các thực thể đầu ra từ Customer Insights sang máy chủ SFTP. Trước đây, tính năng xuất được giới hạn trong các thực thể phân đoạn. Ngoài ra, hiệu suất của tính năng xuất SFTP cho phép nhiều dữ liệu hơn trong thời gian ngắn hơn, tùy thuộc vào hiệu suất của máy chủ SFTP của bạn.    
  Để biết thêm thông tin, hãy xem [Trình kết nối cho SFTP (bản xem trước)](export-sftp.md).  

#### <a name="segments"></a>Phân khúc

- **Các phân đoạn đề xuất dựa trên công nghệ máy học để cải thiện chỉ số** Có một cách mới để khám phá và tạo phân đoạn. Hệ thống sử dụng mô hình trí tuệ nhân tạo để đề xuất các phân đoạn có thể giúp cải thiện KPI (giá trị đo) mà bạn đang theo dõi. Chúng tôi cho biết mức độ ảnh hưởng của các thuộc tính mà bạn chọn đối với giá trị đo hoặc một thuộc tính chính khác. Thông tin này giúp tìm kiếm các phân khúc tiềm năng mang lại cơ hội.    
  Để biết thêm thông tin, hãy xem [Phân đoạn được đề xuất (bản xem trước)](suggested-segments.md).

#### <a name="data-unification"></a>Thống nhất dữ liệu

- **Nâng cao trải nghiệm so khớp** Trong khu vực hợp nhất dữ liệu, trải nghiệm so khớp đã được cập nhật. Nó cho phép bạn định cấu hình và xem các quy tắc đối sánh, bao gồm số liệu thống kê chi tiết để giải thích thêm về cách đối sánh hoạt động. Có các tùy chọn để tắt quy tắc đối sánh để quy tắc đó không còn hoạt động trong khi vẫn giữ nguyên cấu hình, kéo và thả quy tắc đối sánh, v.v.
  Để biết thêm thông tin, hãy xem phần [Đối sánh các thực thể](match-entities.md).

- **Đầu ra khử trùng lặp từ quy trình đối sánh có sẵn dưới dạng thực thể** Đầu ra của quy trình khử trùng lặp từ quy trình đối sánh hiện được viết thành một thực thể riêng biệt để phân tích thêm. Thực thể này bao gồm các trường được sử dụng trong quá trình loại bỏ trùng lặp, đồng thời, bản ghi chiến thắng và bản ghi thay thế tương ứng được hợp nhất với bản ghi chiến thắng.
  Để biết thêm thông tin, hãy xem [Đầu ra khử trùng lặp dưới dạng một thực thể](match-entities.md#deduplication-output-as-an-entity).

#### <a name="system-administration"></a>Quản trị hệ thống

- **Chia sẻ dữ liệu liền mạch với Microsoft Dataverse** Giờ đây, bạn có thể chia sẻ kết quả Customer Insights với các ứng dụng Microsoft Dataverse bằng Microsoft Dataverse Managed Data Lake. Khi liên kết một môi trường Dataverse với Customer Insights, bạn có tùy chọn để bật chia sẻ dữ liệu.
  Để biết thêm thông tin, hãy xem [Quản lý môi trường](manage-environments.md).


## <a name="december-2020-updates"></a>Bản cập nhật tháng 12 năm 2020

Các bản cập nhật vào tháng 12 năm 2020 bao gồm một số tính năng, nâng cấp hiệu suất và sửa lỗi.

### <a name="new-and-updated-features-in-december-2020"></a>Các tính năng mới và cập nhật vào tháng 12 năm 2020

#### <a name="data-enrichment"></a>Làm phong phú dữ liệu

- **Cải thiện khả năng làm phong phú đối tượng chung sở thích và Thương hiệu**
  
  Chúng tôi đã đơn giản hóa điểm số sở thích để làm cho chúng dễ hiểu và dễ sử dụng hơn. Giờ đây, bạn có thể nhanh chóng xác định khách hàng dựa trên mức độ yêu thích của họ đối với một thương hiệu hoặc mối quan tâm nhất định.

  Ngoài ra, chúng tôi đã thêm các tùy chọn cấu hình mới để kiểm soát tốt hơn cách bạn muốn làm phong phú hồ sơ khách hàng của mình. 

  Để biết thêm thông tin, hãy xem [Làm phong phú hồ sơ khách hàng bằng thương hiệu và sở thích](enrichment-microsoft.md).

- **Kiểm soát cấu hình cần làm phong phú**

  Giờ đây, bạn chỉ có thể làm phong phú thêm một tập hợp con hồ sơ khách hàng với tùy chọn để chọn thực thể phân khúc thay vì thực thể khách hàng mặc định. Tạo phân khúc với hồ sơ khách hàng mà bạn muốn làm phong phú và chọn phân khúc đó trong cấu hình làm phong phú cho tập dữ liệu khách hàng của bạn.
  Tính năng này hiện chỉ khả dụng cho các phần làm phong phú được cung cấp bởi Công nghệ Experian và HERE. Chúng tôi sẽ sớm kích hoạt khả năng này để làm phong phú thêm.

  Để biết thêm thông tin, hãy xem [Làm phong phú hồ sơ khách hàng với thông tin nhân khẩu học từ Experian](enrichment-experian.md) hoặc [Làm phong phú hồ sơ khách hàng với Công nghệ HERE](enrichment-here.md).

#### <a name="extensibility"></a>Khả năng mở rộng

- **Kích hoạt các phân khúc của bạn thông qua Autopilot**

  Xuất các phân khúc sang Autopilot và sử dụng chúng cho mục đích tiếp thị. Để biết thêm thông tin, hãy xem [Trình kết nối cho Autopilot (bản xem trước)](export-autopilot.md).

- **Kích hoạt các phân khúc của bạn thông qua SendGrid**

  Xuất các phân khúc sang SendGrid và sử dụng chúng cho mục đích tiếp thị. Để biết thêm thông tin, hãy xem [Trình kết nối cho SendGrid](export-sendgrid.md).

#### <a name="system-administration"></a>Quản trị hệ thống

- **Cập nhật trải nghiệm quản lý môi trường**
  
  Giờ đây, bạn có thể tạo, chỉnh sửa, xóa và đặt lại môi trường trực tiếp từ bộ chọn môi trường trong tiêu đề ứng dụng. 
  
  Ngoài ra, môi trường bạn đang sử dụng sẽ được ghim ở đầu bảng điều khiển môi trường, vì vậy bạn không cần phải tìm kiếm nó nữa.

  Để biết thêm thông tin, hãy xem [Quản lý môi trường](manage-environments.md).

## <a name="november-2020-updates"></a>Bản cập nhật tháng 11 năm 2020

Các bản cập nhật vào tháng 11 năm 2020 bao gồm một số tính năng, nâng cấp hiệu suất và sửa lỗi.

### <a name="new-and-updated-features-in-november-2020"></a>Các tính năng mới và cập nhật vào tháng 11 năm 2020

#### <a name="data-enrichment"></a>Làm phong phú dữ liệu

- **Mang dữ liệu tăng cường của riêng bạn thông qua nhập tùy chỉnh Giao thức truyền tệp bảo mật (SFTP)**
  
  Nhập tùy chỉnh SFTP cho phép bạn nhập dữ liệu làm phong phú mà không phải trải qua quá trình hợp nhất dữ liệu. Tìm hiểu thêm về nhập tùy chỉnh SFTP.

  Để biết thêm thông tin, hãy xem [Tăng cường hồ sơ khách hàng với dữ liệu tùy chỉnh (bản xem trước)](enrichment-SFTP-custom-import.md).
 
- **Tăng cường dữ liệu khách hàng của bạn với dữ liệu vị trí từ HERE Technologies**

  Với các dịch vụ làm giàu dữ liệu của HERE Technologies, bạn có thể xây dựng kiến thức vị trí chính xác hơn về khách hàng của mình bằng cách chuẩn hóa địa chỉ, trích xuất vĩ độ và kinh độ, v.v. Tìm hiểu thêm về cách tăng cường với HERE Technologies.

  Để biết thêm thông tin, hãy xem [Tăng cường hồ sơ khách hàng với HERE Technologies](enrichment-here.md).

#### <a name="data-unification"></a>Thống nhất dữ liệu

- **Tính linh hoạt để bật hồ sơ dữ liệu trên các thực thể và trường được chọn từ tài khoản lưu trữ của bạn**

  Bạn có thể chỉ ra các thực thể và trường dữ liệu nào từ thư mục Common Data Model trong tài khoản lưu trữ Azure Data Lake mà bạn muốn bật hồ sơ dữ liệu như một phần của quá trình nhập dữ liệu.

  Để biết thêm thông tin, hãy xem [Kết nối với thư mục Common Data Model](connect-common-data-model.md#connect-to-a-common-data-model-folder).

#### <a name="extensibility"></a>Khả năng mở rộng

- **Kích hoạt các phân khúc của bạn thông qua Google Ads**

  Xuất các phân khúc sang sang danh sách đối tượng Google Ads và sử dụng những danh sách này để quảng cáo trên Google Tìm kiếm, Mạng hiển thị của Google, YouTube và Gmail. Tìm hiểu thêm về cách kích hoạt các phân khúc của bạn thông qua Google Ads.

  Để biết thêm thông tin, hãy xem [Trình kết nối cho Google Ads](export-google-ads.md).

- **Kích hoạt các phân khúc của bạn thông qua Marketo**

  Xuất phân khúc sang đối tượng Marketo và sử dụng các đối tượng này để tự động hóa tiếp thị. Tìm hiểu thêm về cách kích hoạt các phân khúc của bạn thông qua Marketo. 

  Để biết thêm thông tin, hãy xem [Trình kết nối cho Marketo](export-marketo.md).

- **Kích hoạt các phân khúc của bạn thông qua DotDigital**

  Xuất các phân khúc sang DotDigital và sử dụng chúng cho mục đích tiếp thị. Tìm hiểu thêm về cách kích hoạt các phân khúc của bạn thông qua DotDigital. 

  Để biết thêm thông tin, hãy xem [Trình kết nối cho DotDigital](export-dotdigital.md).

#### <a name="predictions"></a>Dự đoán

- **Dự đoán rời bỏ giao dịch**

  Tính năng dự đoán rời bỏ giao dịch cho phép bạn mà không cần sự trợ giúp của nhà khoa học dữ liệu, dự đoán khả năng khách hàng ngừng mua sản phẩm hoặc dịch vụ.  Bằng cách sử dụng điểm số dự đoán, bạn có thể kết hợp các thông tin khác về khách hàng của mình, chẳng hạn như giá trị khách hàng, để tạo phân khúc khách hàng có rủi ro cao hoặc khách hàng có giá trị cao. Sử dụng phân khúc này để nhắm mục tiêu trực tiếp đến khách hàng thông qua các hoạt động tiếp thị, hỗ trợ khách hàng và các tình huống khác để giảm rủi ro khách hàng rời đi.
 
  Định cấu hình định nghĩa về tỷ lệ rời đi là một khoảng thời gian cụ thể cho doanh nghiệp của bạn và xác định thời điểm khách hàng được coi là rời đi. Ví dụ: một cửa hàng tạp hóa có thể muốn xem xét một khách hàng rời đi nếu họ không mua bất cứ thứ gì trong 30 ngày qua.
 
  Khi bạn tiếp tục tạo dự đoán, chúng tôi sẽ hướng dẫn bạn những dữ liệu nào cần thiết và cho phép bạn ánh xạ dữ liệu về doanh nghiệp của mình với các trường cần thiết để dự đoán khách hàng rời đi. Bạn cũng có thể đặt lịch để đào tạo lại mô hình dựa trên thông tin mới trong hệ thống của mình để thích ứng với hoàn cảnh kinh doanh thay đổi.
 
  Để biết thêm thông tin, hãy xem [Dự đoán rời bỏ giao dịch (bản xem trước)](predict-transactional-churn.md).

#### <a name="system-administration"></a>Quản trị hệ thống

- **Đặt lại môi trường**

  Đặt lại mọi thứ trong môi trường của phiên bản đã chọn để bắt đầu làm mới.

  Để biết thêm thông tin, xem [Đặt lại môi trường hiện có](manage-environments.md#reset-an-existing-environment).


- **Kết nối với tài khoản lưu trữ Azure Data Lake của bạn bằng dịch vụ chính**

  Ghi đầu ra dữ liệu vào và đọc dữ liệu từ tài khoản lưu trữ của bạn bằng cách sử dụng dịch vụ chính Azure. Các kết nối tài khoản lưu trữ hiện tại có thể tiếp tục sử dụng khóa tài khoản. Chúng cũng cung cấp tùy chọn nâng cấp để sử dụng dịch vụ chính trong tương lai. Các kết nối mới sẽ dựa trên phương thức xác thực dịch vụ chính cho tài khoản lưu trữ của bạn.

  Để biết thêm thông tin, hãy xem [Kết nối thông tin chuyên sâu về đối tượng với tài khoản Azure Data Lake Storage Gen2 có dịch vụ chính Azure cho thông tin chi tiết về đối tượng](connect-service-principal.md).

## <a name="october-2020-updates"></a>Bản cập nhật tháng 10 năm 2020

Các bản cập nhật vào tháng 10 năm 2020 bao gồm một số tính năng, nâng cấp hiệu suất và sửa lỗi.

### <a name="new-and-updated-features-in-october-2020"></a>Các tính năng mới và cập nhật vào tháng 10 năm 2020

#### <a name="extensibility"></a>Khả năng mở rộng

- **Xuất sang Mailchimp**

Xuất phân khúc sang danh sách đối tượng hiện có trong Mailchimp để cung cấp trải nghiệm email được cá nhân hóa cho khách hàng của bạn.

Để biết thêm thông tin, hãy xem [Trình kết nối cho Mailchimp](export-mailchimp.md).

#### <a name="data-enrichment"></a>Làm phong phú dữ liệu

- **Sao chép các bản ghi nguồn trong một thực thể So khớp**

Chỉ định quy tắc chống trùng lặp trên các thực thể được sử dụng trong quy trình so khớp để xác định các bản ghi trùng lặp. Hợp nhất chúng thành một bản ghi và liên kết tất cả các bản ghi nguồn với bản ghi đã hợp nhất này. Sau đó bản ghi đã chống trùng lặp này sẽ được sử dụng trong quá trình so khớp thực thể chéo.

Để biết thêm thông tin, hãy xem [Xác định quy tắc chống trùng lặp trên một thực thể so khớp](match-entities.md#define-deduplication-on-a-match-entity).

#### <a name="system-administration"></a>Quản trị hệ thống

- **Điều phối: Tùy chọn làm mới mới trong Hợp nhất**

Cho đến hôm nay, khi bạn chạy quá trình hợp nhất, hệ thống đã chạy tất cả các quy trình xuôi dòng phụ thuộc vào quy trình hợp nhất và các quy trình tiếp theo. Giờ đây, bạn có thể xác minh đầu ra của quy trình hợp nhất (thực thể khách hàng hợp nhất) trước khi sử dụng nó trong quá trình xử lý xuôi dòng như phân khúc hoặc biện pháp.
Trên trang hợp nhất, bây giờ bạn có thể chọn chỉ chạy bước hợp nhất và chỉ chạy quy trình này. Để làm mới tất cả các quy trình xuôi dòng, bạn có thể chọn chạy các quy trình hợp nhất và xuôi dòng. 

## <a name="september-2020-updates"></a>Phần cập nhật tháng 9 năm 2020

Các bản cập nhật tháng 9 năm 2020 bao gồm một số tính năng, phần nâng cấp hiệu suất và bản sửa lỗi.

### <a name="new-and-updated-features-in-september-2020"></a>Các tính năng mới và cập nhật vào tháng 9 năm 2020

#### <a name="activities"></a>Hoạt động

- **Dự đoán thông minh ngữ nghĩa thuộc tính**

Tính năng mới này dự đoán các kiểu ngữ nghĩa của thuộc tính đầu vào được chuyển sang quy trình hợp nhất dữ liệu. Tính năng này sử dụng các mô hình máy học để cải thiện độ chính xác và tiết kiệm thời gian.

#### <a name="enrichments"></a>Nội dung tăng cường

- **Làm phong phú qua dữ liệu nhân khẩu học từ Experian**

Chức năng làm phong phú qua dữ liệu nhân khẩu học từ Experian hiện có sẵn trong bản xem trước. Experian là công ty tiên phong toàn cầu về các dịch vụ tiếp thị và báo cáo tín dụng cho người tiêu dùng và doanh nghiệp. Với [dịch vụ làm phong phú dữ liệu của Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage), bạn có thể có được sự hiểu biết sâu sắc hơn về khách hàng của mình qua việc làm phong phú hồ sơ khách hàng của bạn bằng dữ liệu nhân khẩu học, như: quy mô hộ gia đình, thu nhập, v.v.

Để sử dụng tính năng này, bạn phải có đăng ký Experian hiện hoạt.

Để biết thêm thông tin, hãy xem [Làm phong phú hồ sơ khách hàng với dữ liệu nhân khẩu học từ Experian](enrichment-experian.md)


#### <a name="system-administration"></a>Quản trị hệ thống

- **Ngăn chi tiết tác vụ**

Ngăn chi tiết tác vụ cho phép bạn xem chi tiết về các tác vụ mà hệ thống chạy. Đây là một cách tiện lợi để xác định các vấn đề với cấu hình và tìm giải pháp.
Xem lại các thông báo lỗi để tìm hiểu cách thức giải quyết các vấn đề tiềm ẩn.
 
- **Xử lý thông tin được thêm vào các trang khác**

Phần cải thiện này bổ sung thông tin về trạng thái của các thực thể của bạn trên trang **Thực thể** và **Khách hàng**.
 
Ngoài ra, bạn có thể tìm thấy thông tin chi tiết về tiến trình của các quy trình, cùng với chi tiết nhiệm vụ, trên cả hai trang này.

- **Phần cải thiện đối với trang trạng thái hệ thống**

Chúng tôi đã cải thiện cấu trúc của bảng chi tiết trạng thái trên **Hệ thống** > **Trạng thái** khi xem xét bản xuất dữ liệu.
 
Ngoài ra, các lỗi trong cột **Chi tiết** hiện được mô tả chi tiết hơn và bạn có thể thực hiện hành động ngay trên lỗi. 
 
- **Thao tác hủy sẽ hoàn nguyên công việc trở lại trạng thái trước**

Khi bạn hủy một nhiệm vụ, chẳng hạn, trong quá trình so khớp, nhiệm vụ đó sẽ trở lại trạng thái gần đây nhất. Ví dụ: nếu quá trình Đối sánh được hoàn tất hôm qua và bạn hủy nó vào hôm nay, thì quá trình đó sẽ trở lại trạng thái thành công của ngày hôm qua.


## <a name="august-2020-updates"></a>Phần cập nhật tháng 8 năm 2020

Bản cập nhật tháng 8 năm 2020 bao gồm một số tính năng, phần nâng cấp hiệu suất và bản sửa lỗi.

### <a name="new-and-updated-features-in-august-2020"></a>Các tính năng mới và cập nhật vào tháng 8 năm 2020

#### <a name="data-unification"></a>Thống nhất dữ liệu

- **Cải thiện trải nghiệm cho giai đoạn bản đồ trong quá trình hợp nhất dữ liệu**

  Trải nghiệm đối với giai đoạn bản đồ trong quá trình hợp nhất dữ liệu cho phép bạn chọn các thực thể, thuộc tính và xác định ngữ nghĩa một cách liền mạch hơn.

  Các thay đổi bao gồm:
  
  - bớt sự tương tác phải có để thêm thực thể và trường
  - cải thiện khả năng tìm kiếm trên trang bản đồ
  - xác định trực quan và dễ dàng loại trường được đề xuất

#### <a name="enrichment"></a>Tăng cường

- **Tính năng làm phong phú sở thích có sẵn ở nhiều thị trường hơn**

  Chúng tôi đang mở rộng phạm vi cung cấp dịch vụ làm phong phú sở thích từ Hoa Kỳ sang năm thị trường khác: Canada, Úc, Vương quốc Anh, Pháp và Đức. Với sự mở rộng này, bạn có thể làm phong phú thêm dữ liệu khách hàng của mình với nhiều sở thích hơn áp dụng cho các thị trường này. Chúng tôi cũng sẽ làm phong phú thêm hồ sơ khách hàng của bạn tại các thị trường này bằng cách sử dụng dữ liệu độc quyền tại địa phương từ Microsoft.
  Để biết thêm thông tin, hãy xem [Làm phong phú hồ sơ khách hàng bằng mối quan tâm về sở thích và thương hiệu](enrichment-microsoft.md)


## <a name="july-2020-updates"></a>Bản cập nhật tháng 7 năm 2020

Bản cập nhật tháng 7 năm 2020 bao gồm một vài tính năng, nâng cấp hiệu suất và sửa lỗi.

### <a name="new-and-updated-features-in-july-2020"></a>Các tính năng mới và cập nhật trong tháng 7 năm 2020

#### <a name="extensibility"></a>Khả năng mở rộng

- **Power Automate kích hoạt cho quy trình hợp nhất hoàn tất**

  Chúng tôi đã mở rộng bộ kích hoạt cho Power Automate và cho phép bạn tạo thông báo hoặc hành động khi quá trình làm mới quy trình hợp nhất (ánh xạ, ghép nối, hợp nhất) hoàn tất.    
  Để biết thêm thông tin, hãy xem [Trình kết nối Power Automate](export-power-automate.md)

#### <a name="enrichment"></a>Tăng cường

- **Tính năng làm phong phú thương hiệu có sẵn ở nhiều thị trường hơn**

  Chúng tôi đang mở rộng phạm vi cung cấp dịch vụ làm phong phú thương hiệu từ Hoa Kỳ sang năm thị trường khác: Canada, Úc, Vương quốc Anh, Pháp và Đức. Với sự mở rộng này, bạn có thể làm phong phú dữ liệu của khách hàng bằng các thương hiệu địa phương ở những thị trường này. Chúng tôi cũng sẽ làm phong phú thêm hồ sơ khách hàng của bạn tại các thị trường này bằng cách sử dụng dữ liệu độc quyền tại địa phương từ Microsoft.
  Để biết thêm thông tin, hãy xem [Làm phong phú hồ sơ khách hàng bằng mối quan tâm về sở thích và thương hiệu](enrichment-microsoft.md)

## <a name="june-2020-updates"></a>Bản cập nhật tháng 6 năm 2020

Bản cập nhật tháng 6 năm 2020 bao gồm một vài tính năng, nâng cấp hiệu suất và sửa lỗi.

### <a name="new-and-updated-features-in-june-2020"></a>Các tính năng mới và cập nhật trong tháng 6 năm 2020

#### <a name="enrichment"></a>Làm phong phú

- **Làm phong phú bằng dữ liệu công ty từ Leadspace**
  
  Xác định các trường trong hồ sơ khách hàng hợp nhất được dùng để tra cứu dữ liệu công ty liên quan từ Leadspace. Sau khi chạy quá trình làm phong phú, hồ sơ B2B được làm phong phú với nhiều thuộc tính hơn bao gồm quy mô công ty, vị trí, ngành, v.v.    
  Sự cộng này cho phép bạn cải thiện chất lượng của dữ liệu bằng đầu vào từ các dịch vụ bên thứ ba. Để sử dụng tùy chọn làm phong phú này, bạn cần có giấy phép từ Leadspace để truy nhập dữ liệu công ty B2B. Hệ thống sẽ sử dụng giấy phép đó để liên tục tăng cường dữ liệu của bạn.    
  Để biết thêm thông tin, hãy xem [Làm phong phú hồ sơ công ty bằng Leadspace](enrichment-leadspace.md).

- **Trang trung tâm làm phong phú**

  Tất cả nội dung phong phú dữ liệu hiện có từ nhà cung cấp nội dung phong phú bên thứ nhất và bên thứ ba sẽ được cấu hình ở cùng một nơi. Cấu hình tính năng làm phong phú dữ liệu là một trải nghiệm liền mạch được quản lý ở chung một nơi.    
  Để biết thêm thông tin, hãy xem [Nội dung phong phú cho hồ sơ khách hàng](enrichment-hub.md).

- **Nội dung phong phú về sở thích và thương hiệu riêng biệt**

  Thương hiệu và sở thích hiện có dưới dạng hai loại nội dung phong phú độc lập. Các nội dung phong phú riêng biệt giúp bạn linh hoạt trong việc cấu hình và quản lý từng nội dung, tùy theo yêu cầu hoặc nhu cầu của doanh nghiệp.    
  Để biết thêm thông tin, hãy xem [Làm phong phú hồ sơ khách hàng bằng thương hiệu và sở thích](enrichment-microsoft.md).

#### <a name="extensibility"></a>Khả năng mở rộng

- **URL có thể bấm cho các hoạt động hợp nhất trên Phần bổ trợ thẻ Dynamics 365 Customer**

  Các hoạt động hợp nhất trong tiện ích bổ sung Thẻ khách hàng hiện đang hiển thị các URL có thể nhấp nếu các URL đó đã được xác định trong quá trình cấu hình hoạt động.    
  Để biết thêm thông tin, hãy xem [Customer Card Add-in](customer-card-add-in.md).

- **Mối quan tâm về sở thích và thương hiệu có trên Phần bổ trợ thẻ Dynamics 365 Customer**

  Tùy chọn kiểm soát mới trên Phần bổ trợ thẻ Dynamics 365 Customer cho phép bạn hiển thị nội dung phong phú về thương hiệu và sở thích trên danh bạ của mình trong các ứng dụng tương tác với khách hàng trong Dynamics 365.    
  Để biết thêm thông tin, hãy xem [Customer Card Add-in](customer-card-add-in.md).

- **Nhiều trình kích hoạt Power Automate hơn**

  Chúng tôi đã mở rộng bộ kích hoạt cho Power Automate và thêm các bộ kích hoạt sau:
  - Nhận thông báo hoặc thực hiện hành động khi lệnh làm mới đầy đủ tự động (nguồn dữ liệu, hợp nhất, phân khúc, biện pháp, quy trình xuất) hoàn tất
  - Xác định ngưỡng cho số liệu đo lường công việc. Ví dụ: Bạn có thể tạo một thông báo được gửi đi mỗi khi vượt qua ngưỡng đã xác định. Ngoài ra, bộ kích hoạt hiển thị thông tin cho phép bạn tạo lập quy trình làm việc phức tạp hơn trong Power Automate.    
  Để biết thêm thông tin, hãy xem [Trình kết nối Power Automate](export-power-automate.md)

- **Xuất sang Trình quản lý quảng cáo Facebook**
  
  Khả năng này cho phép bạn xuất các phân khúc sang Trình quản lý quảng cáo Facebook. Các phân khúc được xuất dưới dạng đối tượng tùy chỉnh để sử dụng hồ sơ khách hàng hợp nhất trong các chiến dịch tiếp thị và quảng cáo trên Facebook. Đối tượng tùy chỉnh cũng sử dụng được để tạo chiến dịch trên Instagram thông qua Trình quản lý quảng cáo Facebook.    
  Để biết thêm thông tin, hãy xem [Trình kết nối cho Trình quản lý quảng cáo Facebook](export-facebook.md).

#### <a name="predictions"></a>Dự đoán

- **Dự đoán khả năng rời bỏ đăng ký**

  Làm theo trải nghiệm định hướng để tạo dự đoán về khả năng rời bỏ trong các khu vực đăng ký như dịch vụ đám mây, thành viên khách hàng và các khía cạnh khác. 

  Tính năng dự đoán khả năng rời bỏ đăng ký cho phép bạn dự đoán khả năng một khách hàng dừng sử dụng các sản phẩm hoặc dịch vụ dựa trên đăng ký mà không cần đến nhà khoa học dữ liệu. Sử dụng điểm số dự đoán, bạn có thể kết hợp thông tin khác về khách hàng để tạo các phân khúc có rủi ro rời bỏ cao. Với sự trợ giúp của phân khúc này, bạn có thể trực tiếp nhắm mục tiêu đến khách hàng trong các tình huống tiếp thị, hỗ trợ khách hàng và các tình huống khác để giảm nguy cơ rời đi cho các khách hàng cụ thể nhằm cải thiện doanh thu và giảm chi phí.

  Trong trải nghiệm này, bạn có thể cấu hình định nghĩa của rời bỏ dưới dạng thời gian cụ thể cho doanh nghiệp của mình. Ví dụ: doanh nghiệp truyền phát video có quy trình đăng ký hàng tháng nên cân nhắc một khách hàng đã rời bỏ sau 15 ngày kể từ khi kết thúc gói đăng ký của họ.

  Khi bạn tiếp tục đăng ký, chúng tôi sẽ hướng dẫn bạn biết dữ liệu nào cần thiết, đồng thời cho phép bạn ánh xạ dữ liệu về doanh nghiệp vào các trường cần để dự đoán khả năng rời bỏ của khách hàng. Khi thông tin doanh nghiệp thay đổi, bạn cũng có thể đặt lịch trình để đào tạo lại thông tin trên hệ thống nhằm thích nghi với các tình huống kinh doanh liên tục thay đổi.    
  Để biết thêm thông tin, hãy xem [Dự đoán khả năng rời bỏ đăng ký (xem trước)](predict-subscription-churn.md).

#### <a name="segments"></a>Phân đoạn

- **Tìm khách hàng tương tự**
  
  Tìm khách hàng tương tự trong cơ sở khách hàng của bạn bằng trí tuệ nhân tạo. Mô hình công cụ máy học phân loại nhị phân chỉ định điểm số tương tự cho khách hàng trong phân khúc mở rộng. Điểm số dựa trên sự tương đồng với khách hàng trong phân khúc nguồn. Tùy thuộc vào điểm số tương tự, hồ sơ khách hàng được thêm vào phân khúc mới tạo.

  Đôi khi được gọi là mô hình tương tự trong tiếp thị kỹ thuật số, nó sử dụng mô hình trí tuệ nhân tạo để giúp tìm kiếm những khách hàng tương tự với một phân khúc khách hàng khác của bạn bằng cách bao gồm nhiều thuộc tính hơn. Điều này không chỉ cho phép bạn chọn các thuộc tính mà còn chỉ định số lượng khách hàng lớn nhất nên có trong phân khúc mới này. Mô hình AI sẽ tính toán điểm số tương tự cho từng khách hàng dựa trên thuộc tính bạn đã chọn và tìm khách hàng có điểm số tương tự trung bình cao hơn. Phân khúc được tạo ra sẽ bao gồm khách hàng tương tự với khách hàng trong phân khúc ban đầu.    
  Để biết thêm thông tin, hãy xem [Khách hàng tương tự](find-similar-customer-segments.md).

- **Trùng lặp phân khúc và các yếu tố phân biệt**

  Trùng lặp phân khúc cho phép bạn xem số lượng và loại khách hàng chung nhau của hai phân khúc trở lên. Ví dụ: mức độ trùng lặp của phân khúc khách hàng chi tiêu nhiều với phân khúc khách hàng hài lòng hoặc mức độ trùng lặp của phân khúc khách hàng rời bỏ với phân khúc khách hàng không hài lòng. Ngoài ra, bạn có thể phân tích cách sự chồng chéo thay đổi dựa trên một thuộc tính bổ sung mà bạn chọn.

  Các yếu tố phân biệt phân khúc cho thấy sự khác biệt của một phân khúc so với số lượng khách hàng còn lại hoặc so với một phân khúc khác. Bạn chỉ cần xác định một phân khúc và hệ thống sẽ xác định các thuộc tính hồ sơ và số liệu phân biệt phân khúc này dưới dạng danh sách các điểm khác biệt theo thứ tự—từ điểm khác biệt lớn nhất đến điểm khác biệt nhỏ nhất.    
  Để biết thêm thông tin, hãy xem [Thông tin chi tiết về phân khúc (xem trước)](segment-insights.md).

- **Vòng đời phân khúc**
  
  Xác định lịch trình kích hoạt hoặc vô hiệu hóa một phân khúc.    
  Để biết thêm thông tin, hãy xem [Quản lý phân khúc hiện có](segments.md#manage-existing-segments).

## <a name="may-2020-updates"></a>Các điểm cập nhật tháng 5 năm 2020

Các bản cập nhật tháng 5 năm 2020 gồm có một số tính năng, nâng cấp hiệu suất và sửa một số lỗi.

### <a name="new-and-updated-features-in-may-2020"></a>Các tính năng mới và cập nhật trong tháng 5 năm 2020

#### <a name="data-ingestion"></a>Nhập dữ liệu

- **Tải nạp dữ liệu trong thời gian thực: chế độ xem lịch sử**

  Khi dùng API của chúng tôi để tải nạp các điểm cập nhật theo thời gian thực, bạn có thể xem lịch sử tổng hợp trong vòng 30 ngày cho những điểm cập nhật này. Bạn có quyền truy cập vào bản tổng hợp mọi cuộc gọi API thành công hoặc thất bại, gồm những thông tin như kết quả, hệ thống nguồn và các siêu dữ liệu hữu ích khác.    
  Để biết thêm thông tin, hãy xem [Nhập dữ liệu trong thời gian thực](real-time-data-ingestion.md).

- **Tải nạp dữ liệu theo thời gian thực: cập nhật hồ sơ**

  Phần mở rộng của tính năng tải nạp dữ liệu theo thời gian thực cho phép bạn nhanh chóng xem những thay đổi đối với các trường trong hồ sơ người dùng cụ thể.    
  Ngoài chức năng thời gian thực cho các hoạt động, hệ thống hỗ trợ cập nhật độ trễ thấp cho các trường hồ sơ. Việc cập nhật theo thời gian thực cho các trường hồ sơ sẽ có thời gian hết hạn, nên không phải là sự thay thế cho các lần làm mới theo lịch.    
  Để biết thêm thông tin, hãy xem [Nhập dữ liệu trong thời gian thực](real-time-data-ingestion.md).

#### <a name="extensibility"></a>Khả năng mở rộng

- **Cách dàn trang và dòng thời gian cập nhật trên tiện ích bổ trợ Customer Card**

  Dòng thời gian của giải pháp bổ trợ Thẻ khách hàng khớp với dòng thời gian hoạt động. Cải thiện cách dàn trang của dòng thời gian, hiển thị cùng lúc tới 50 hoạt động. Nó cũng cho phép tải nhiều hoạt động hơn trong dòng thời gian.    
  Để biết thêm thông tin, hãy xem [Customer Card Add-in](customer-card-add-in.md).

- **Tác nhân kích hoạt Power Automate cho các thay đổi của phân khúc**

  Các tác nhân kích hoạt cho Power Automate giúp bạn xác định xem mình có thể xây dựng một luồng từ những yếu tố nào. Tác nhân kích hoạt mới thêm cho phép bạn xác định ngưỡng cho phân khúc. Ví dụ: Bạn có thể tạo một thông báo được gửi đi mỗi khi vượt qua ngưỡng đã xác định.    
  Để biết thêm thông tin, hãy xem [Trình kết nối Power Automate](export-power-automate.md).

- **Hỗ trợ nhiều đối tượng thuê cho các mô hình tùy chỉnh**

  Đặt cấu hình quy trình công việc cho các mô hình tùy chỉnh bằng dịch vụ web của một đối tượng thuê Azure Machine Learning khác. Bạn có thể đăng nhập vào đối tượng thuê Azure Machine Learning khi tạo quy trình làm việc mới cho các mô hình tùy chỉnh. Chức năng này bổ trợ cho chức năng tích hợp hiện tại với dịch vụ web Azure Machine Learning tùy chỉnh của chính bạn.    
  Để biết thêm thông tin, hãy xem [Mô hình máy học tùy chỉnh](custom-models.md).

#### <a name="segments"></a>Phân đoạn

- **Tự động hóa đường dẫn thực thể**

  Khi tạo phân khúc, người dùng cần xác định đường dẫn thực thể. Chức năng này là bước đầu để tự động hóa cách xác định đường dẫn thực thể, nhờ đó bạn có thể tập trung vào ý tưởng về tiêu chí phân khúc.    
  Nếu thực thể mà bạn muốn phân khúc khách hàng có liên hệ trực tiếp với thực thể người dùng hợp nhất, thì bạn sẽ không cần phải xác định đường dẫn thực thể nữa. Tuy nhiên, nếu có nhiều hơn một cách xác định đường dẫn thực thể, bạn sẽ phải xác định theo cách thủ công.

- **Các hành động trên nhiều phân khúc**
  
  Người dùng có thể chọn nhiều phân khúc và thực hiện các hành động trên đó, chẳng hạn như làm mới phân khúc, chỉ bằng một lần bấm.    

- **Làm mới phân đoạn**

  Người dùng có thể làm mới một phân khúc duy nhất hoặc chỉ chọn các phân khúc mà họ muốn làm mới.    

  
- **Cải tiến đối với phân khúc tổ hợp**

  Người dùng có thể tạo, chỉnh sửa và xóa các phân khúc có mối quan hệ phụ thuộc với phân khúc khác. Ví dụ: Một phân khúc được xây dựng trên một phân khúc khác, phân khúc kia lại được xây dựng trên phân khúc thứ 3.    

- **Trang danh sách phân khúc**

  Thiết kế mới của trang phân khúc dùng định dạng danh sách, cho phép bạn xem cùng lúc nhiều phân khúc hơn. Chúng tôi đã thêm trường tìm kiếm để bạn có thể nhanh chóng tìm các phân khúc. Giờ đây, người dùng có thể áp dụng các hành động như tải xuống hoặc xóa cùng lúc trên nhiều phân khúc. Chúng tôi đã giới thiệu trải nghiệm theo xu hướng mới, cho phép bạn nhanh chóng xác định các thay đổi quan trọng đối với phân khúc.    
  Để biết thêm thông tin, hãy xem [Tạo và quản lý phân khúc](segments.md).

#### <a name="system-administration"></a>Quản trị hệ thống

- **Customer Insights có sẵn trong Microsoft Dynamics 365 Online Government**

  Với việc ngày càng có nhiều kênh để tương tác, dữ liệu công dân nằm rải rác trên vô số hệ thống, dẫn đến tình trạng dữ liệu bị ngăn cách và khiến cho cái nhìn đối với thông tin về hoạt động tương tác của công dân trở nên rời rạc. Khi không có cái nhìn toàn diện về hoạt động tương tác của từng công dân trên các kênh, thật khó để chính phủ có thể hiện đại hóa trên quy mô lớn. Microsoft cam kết đáp ứng các nhu cầu về công nghệ để chính phủ có thể bắt kịp kỳ vọng của công dân về những trải nghiệm nhanh chóng và nhất quán.    
  Trong đợt phát hành 1 năm 2020, Dynamics 365 Customer Insights sẽ được cung cấp cho Government Community Cloud (GCC), một môi trường được xây dựng để đáp ứng nhu cầu tuân thủ ngày càng cao của các cơ quan chính phủ Hoa Kỳ. Các cơ quan sẽ có cái nhìn hợp nhất về công dân của mình, cũng như có thể sử dụng AI xây dựng sẵn để rút ra thông tin chuyên sâu, từ đó cải thiện hoạt động tương tác, tạo điều kiện cho nhân viên và chuyển đổi cộng đồng, trong khi giảm thiểu sự phức tạp của hệ thống CNTT và đáp ứng các tiêu chuẩn bảo mật và tuân thủ của Hoa Kỳ. Dynamics 365 Government đáp ứng các yêu cầu khắt khe của US Federal Risk and Authorization Management Program (FedRAMP), nhờ đó các cơ quan liên bang của Hoa Kỳ sẽ được hưởng lợi từ khả năng bảo mật mạnh mẽ và tiết kiệm chi phí của Microsoft Cloud.

## <a name="april-2020-updates"></a>Các điểm cập nhật tháng 4 năm 2020

Các bản cập nhật tháng 4 năm 2020 bao gồm một số tính năng, nâng cấp hiệu suất và sửa lỗi.

### <a name="new-and-updated-features-in-april-2020"></a>Các tính năng mới và cập nhật trong tháng 4 năm 2020

#### <a name="activities"></a>Hoạt động

- **Kết nối thực thể hoạt động với loại hoạt động tiêu chuẩn**
  
  Hiện nay, cấu hình và nơi lưu trữ hoạt động đang dựa trên thiết kế tĩnh để xem trong dòng thời gian. Bối cảnh ngữ nghĩa của hoạt động, điều có tiềm năng áp dụng cho nhiều trường hợp sử dụng trong mô hình AI, hiện đang chưa được tận dụng đầy đủ. Chúng tôi dự định làm cho dòng thời gian hoạt động trở nên linh hoạt hơn, dựa trên loại hoạt động và khả năng hiểu bối cảnh của hoạt động tốt hơn. Tính năng này nhắm xác định loại hoạt động như đã nêu trong Common Data Model cho hoạt động tải nạp bất kỳ.
  Để biết thêm thông tin, hãy xem [Hoạt động của khách hàng](activities.md).

#### <a name="data-ingestion"></a>Nhập dữ liệu

- **Tải nạp dữ liệu theo thời gian thực: hoạt động**
  
  Nhập dữ liệu thời gian thực cung cấp dữ liệu ngay lập tức để sử dụng, cho đến khi quá trình làm mới theo lịch trình tiếp theo kéo dữ liệu này từ nguồn dữ liệu.    
  Để biết thêm thông tin, hãy xem [Nhập dữ liệu trong thời gian thực](real-time-data-ingestion.md).

- **Cải thiện việc chuẩn bị dữ liệu**
  
  Tìm hiểu thêm về dữ liệu được tải nạp trong thực thể. Với bản tóm tắt dữ liệu, bạn có thể hiểu hơn về đặc trưng và tính chất của dữ liệu, từ đó đưa ra hành động thích hợp.    
  Để biết thêm thông tin, hãy xem [Khám phá dữ liệu thực thể](entities.md#exploring-a-specific-entitys-data).

- **Tải nạp dữ liệu phân tích từ Dynamics 365 bằng Common Data Service**
  
  Common Data Service có sẵn như một cách để tạo nguồn dữ liệu. Khách hàng hiện tại của Dynamics 365 có thể tải nạp các thực thể phân tích từ Common Data Service vào Customer Insights. Một nguồn dữ liệu có thể đồng thời sử dụng cùng một kho do Common Data Service quản lý trong môi trường Customer Insights.    
  Để biết thêm thông tin, hãy xem [Kết nối với dữ liệu trong hồ dữ liệu Common Data Service có quản lý](connect-common-data-service-lake.md).

#### <a name="extensibility"></a>Khả năng mở rộng

- **Xuất sang LiveRamp**

  Kích hoạt dữ liệu của bạn trong LiveRamp® để kết nối với hơn 500 nền tảng trên hệ sinh thái kỹ thuật số, mạng xã hội và TV. Sử dụng dữ liệu của bạn trong LiveRamp để nhắm mục tiêu, xóa và cá nhân hóa các chiến dịch quảng cáo.    
  Để biết thêm thông tin, hãy xem [Trình kết nối LiveRamp&reg;](export-liveramp.md).

- **Tiện ích bổ trợ Customer Insights trong Teams**
  
  Bot mang đến các chức năng tra cứu đối với hồ sơ khách hàng hợp nhất. Bot sẽ hiển thị một thẻ chứa lên tới 15 trường từ hồ sơ khách hàng tìm được. Khi có nhiều kết quả khớp, hệ thống sẽ trả về một danh sách mà bạn có thể chọn hồ sơ.    
  Để biết thêm thông tin, hãy xem [Bot Teams dành cho Customer Insights](export-teams-bot.md).

#### <a name="measures"></a>Biện pháp

- **Trang danh sách đo lường**
  
  Cải thiện trang đo lường, bao gồm hỗ trợ cho các hành động đối với phép đo đơn lẻ và nhiều phép đo cùng lúc. Ngoài ra, bạn có thể dùng trường tìm kiếm để nhanh chóng tìm và theo dõi các phép đo.    
  Để biết thêm thông tin, hãy xem [Tạo và quản lý phân khúc](segments.md).

- **Cải tiến đối với phép đo tổ hợp**
  
  Người dùng có thể tạo, chỉnh sửa và xóa các phép đo có mối quan hệ phụ thuộc với phép đo khác. Ví dụ: Một phép đo được xây dựng trên một phép đo khác, phép đo kia lại được xây dựng trên phép đo thứ 3.

#### <a name="segments"></a>Phân khúc

- **Một toán tử khác**
  
  Toán tử theo bộ cho phép phân khúc khách hàng theo một số giá trị chuỗi có thể có. Trước khi toán tử này được thêm vào, bạn phải xây dựng những phân khúc đó với nhiều điều kiện HOẶC. Toán tử theo bộ cho phép bạn làm điều đó chỉ với một điều kiện.    
  Để biết thêm thông tin, hãy xem [Tạo và quản lý phân khúc](segments.md).

#### <a name="system-administration"></a>Quản trị hệ thống

- **Sao chép phần cài đặt cấu hình sang môi trường mới**
  
  Sao chép cấu hình của bạn từ môi trường này sang môi trường khác. Trong khi tạo môi trường mới, bạn có thể chọn môi trường hiện tại mà bạn muốn sao chép cấu hình. Chúng tôi hiện hỗ trợ việc sao chép nguồn dữ liệu, quy trình hợp nhất dữ liệu, mối quan hệ, phép đo và phân khúc. Bạn không thể sao chép dữ liệu thực và thông tin đăng nhập nguồn dữ liệu.    
  Để biết thêm thông tin, hãy xem [Quản lý môi trường](manage-environments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]