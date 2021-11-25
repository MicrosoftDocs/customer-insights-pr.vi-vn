---
title: Các tính năng mới sắp ra mắt
description: Thông tin về các tính năng mới, cải tiến và sửa lỗi.
ms.date: 11/04/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: midevane
manager: shellyha
ms.openlocfilehash: f7e2645e1608ea83b5d3af1073a5d6f6e97eec8f
ms.sourcegitcommit: 2a0947cffb52eaf885aa2e50c95b3693f7e4c589
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 11/04/2021
ms.locfileid: "7753143"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>Tính năng mới trong khả năng thông tin chi tiết về đối tượng của Dynamics 365 Customer Insights

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Chúng tôi rất vui được công bố các bản cập nhật mới nhất của mình! Bài viết này tóm tắt các tính năng xem trước công khai, các điểm cải tiến được phát hành rộng rãi và những điểm cập nhật tính năng. Để xem các kế hoạch tính năng dài hạn, hãy xem [Kế hoạch phát hành Dynamics 365 và Power Platform](/dynamics365/release-plans/).

Chúng tôi sẽ triển khai các điểm cập nhật trên cơ sở từng khu vực. Do đó, một số khu vực sẽ thấy các tính năng trước khu vực khác. Trừ khi có lưu ý khác, bạn sẽ không phải thực hiện nào và chúng tôi sẽ tự động cập nhật ứng dụng mà không gây ra thời gian ngừng hoạt động.

> [!TIP]
> Để gửi và bình chọn cho các yêu cầu về tính năng cũng như gợi ý về sản phẩm, hãy truy cập vào [Cổng ý tưởng ứng dụng Dynamics 365](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).

## <a name="october-2021-updates"></a>Cập nhật tháng 10 năm 2021

Các bản cập nhật vào tháng 10 năm 2021 bao gồm các tính năng mới, nâng cấp hiệu suất và sửa lỗi.

### <a name="b-to-b"></a>B-to-B

Bắt đầu từ tháng 10 năm 2021, bạn có thể làm việc với các tài khoản doanh nghiệp và các địa chỉ liên hệ có liên quan của họ trong Thông tin chi tiết về khách hàng. Trước đây, ứng dụng chủ yếu được điều chỉnh cho người tiêu dùng cá nhân. Một số khu vực tính năng đã được cập nhật để hỗ trợ các kịch bản B-to-B trên một loại môi trường mới. Để biết tổng quan về các tính năng B-to-B được hỗ trợ, hãy xem [Làm việc với các tài khoản doanh nghiệp trong thông tin chi tiết về đối tượng](work-with-business-accounts.md).

Các phần sau đây nêu bật một số lĩnh vực chính đã được điều chỉnh để hỗ trợ tài khoản doanh nghiệp và người tiêu dùng cá nhân.

#### <a name="export-segments-based-on-business-accounts"></a>Xuất phân đoạn dựa trên tài khoản doanh nghiệp

Tất cả các xuất khẩu phân khúc trong thông tin chi tiết về đối tượng đều có sẵn trong ngữ cảnh của tài khoản doanh nghiệp. Hầu hết các xuất khẩu phân khúc yêu cầu cấu hình bổ sung và [thông tin liên hệ dự kiến](segment-builder.md#create-a-new-segment) trong các phân đoạn cơ bản để hợp lệ cho tài khoản doanh nghiệp. Để biết thêm thông tin, hãy xem [Các phân đoạn xuất khẩu](export-destinations.md#export-segments).

#### <a name="use-the-linkedin-ads-export-with-business-accounts"></a>Sử dụng xuất Quảng cáo LinkedIn với các tài khoản doanh nghiệp

Bản xuất Quảng cáo LinkedIn hiện có sẵn để nhắm mục tiêu liên hệ và công ty trong bối cảnh tài khoản doanh nghiệp. Khi chọn nhắm mục tiêu theo công ty làm trọng tâm chính của quá trình xuất LinkedIn, bạn có thể xuất các phân đoạn được xây dựng trên tài khoản doanh nghiệp mà không cần chiếu thông tin liên hệ. Để biết thêm thông tin, hãy truy cập tài liệu về [Xuất Quảng cáo LinkedIn](export-linkedin-ads.md) và sự khác biệt giữa [nhắm mục tiêu liên hệ](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) và [nhắm mục tiêu công ty](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting). 

#### <a name="create-measures-based-on-business-accounts-and-their-hierarchy"></a>Tạo các biện pháp dựa trên tài khoản doanh nghiệp và hệ thống phân cấp của chúng

Trình tạo thước đo cho phép bạn tạo các thước đo xung quanh tài khoản doanh nghiệp và tùy chọn sử dụng thông tin phân cấp. Thông tin phân cấp được sử dụng để tổng hợp một phép tính đo lường trên một tài khoản và tất cả các tài khoản phụ có liên quan. Ví dụ: bạn có thể tạo các thước đo như tổng doanh thu cho từng nhóm tài khoản doanh nghiệp được xác định theo thứ bậc của chúng. Để biết thêm thông tin, hãy xem [Xác định và quản lý các biện pháp](measures.md).

#### <a name="create-segments-based-on-business-accounts-and-their-hierarchy"></a>Tạo phân khúc dựa trên tài khoản doanh nghiệp và hệ thống phân cấp của chúng

Trình tạo phân đoạn cho phép bạn tạo các phân đoạn tài khoản doanh nghiệp có tùy chọn bao gồm thông tin liên hệ cho từng tài khoản trong phân đoạn. Nếu bạn đã thiết lập phân cấp tài khoản, bạn có thể sử dụng thông tin phân cấp tài khoản khi tạo phân đoạn. Để biết thêm thông tin, hãy xem [Tạo một phân đoạn mới](segment-builder.md#create-a-new-segment).

#### <a name="retain-your-business-accounts-with-deep-insights-to-their-churn-tendency"></a>Giữ lại các tài khoản doanh nghiệp của bạn với những hiểu biết sâu sắc về xu hướng biến động của chúng

Mô hình churn dự đoán của khách hàng hiện cũng hỗ trợ tài khoản doanh nghiệp. Bạn có thể đánh giá rủi ro ngừng hoạt động không chỉ đối với tài khoản mà còn đối với sự kết hợp của tài khoản và danh mục sản phẩm hoặc dịch vụ mà họ mua từ bạn. Việc bổ sung này giúp bạn hiểu liệu một tài khoản có nhiều khả năng ngừng mua hàng của bạn nói chung hay chỉ đối với một danh mục hàng hóa hoặc dịch vụ nhất định. Để giúp bạn sử dụng thêm mô hình AI này, nó cũng liệt kê các lý do khiến tài khoản có khả năng bị gián đoạn. Để biết thêm thông tin, hãy xem [Giao dịch churn dự đoán (xem trước)](predict-transactional-churn.md).

#### <a name="see-contacts-of-a-business-account-in-customer-view"></a>Xem địa chỉ liên hệ của tài khoản doanh nghiệp trong chế độ xem Khách hàng

Nếu tài khoản doanh nghiệp được ánh xạ với các tài khoản có liên quan, ứng dụng Thông tin chi tiết về khách hàng sẽ hiển thị các địa chỉ liên hệ có liên quan này như một phần của chế độ xem chi tiết khách hàng. Để biết thêm thông tin, hãy xem [Hồ sơ khách hàng](customer-profiles.md).


## <a name="september-2021-updates"></a>Bản cập nhật tháng 9 năm 2021

Các bản cập nhật vào tháng 9 năm 2021 bao gồm các tính năng mới, nâng cấp hiệu suất và sửa lỗi.

### <a name="activities"></a>Hoạt động

- **Cải thiện tiến trình hoạt động** Chúng tôi đã mở rộng bộ lọc cho tiến trình hoạt động trên hồ sơ khách hàng. Ngoài ra, bạn có thể sử dụng khay lọc mới để lọc theo loại hoạt động và theo ngày. Ngày có thể được lọc bằng các điều kiện khác nhau. Để biết thêm thông tin, hãy xem phần [Xem tiến trình hoạt động trên hồ sơ khách hàng](activities.md#view-activity-timelines-on-customer-profiles).

### <a name="relationships"></a>Mối quan hệ

- **Hỗ trợ mối quan hệ nhiều bước** Sử dụng các mối quan hệ nhiều bước khi đặt cấu hình hoạt động và xác định mối quan hệ giữa các thực thể. Mối quan hệ nhiều bước sử dụng một thực thể trung gian để kết nối hai thực thể. Khi đặt cấu hình một hoạt động, bạn có thể sử dụng mối quan hệ nhiều bước để kết nối thực thể hoạt động với một thực thể trung gian, sau đó là thực thể khách hàng. Bạn có thể kết nối mối quan hệ nhiều bước với mối quan hệ nhiều đường dẫn. Để biết thêm thông tin, hãy xem [Mối quan hệ nhiều bước](relationships.md#multi-hop-relationship).

- **Hỗ trợ mối quan hệ nhiều đường dẫn** Sử dụng mối quan hệ nhiều đường dẫn khi đặt cấu hình hoạt động và xác định mối quan hệ giữa các thực thể. Mối quan hệ đa nhiều đường dẫn liên quan đến thực thể nguồn với nhiều hơn một thực thể. Khi đặt cấu hình một hoạt động, bạn có thể sử dụng mối quan hệ nhiều đường dẫn để kết nối thực thể hoạt động với nhiều thực thể khách hàng. Bạn có thể kết nối mối quan hệ nhiều đường dẫn với mối quan hệ nhiều bước. Để biết thêm thông tin, xem phần [Mối quan hệ nhiều đường dẫn](relationships.md#multi-path-relationship).

## <a name="august-2021-updates"></a>Bản cập nhật tháng 8 năm 2021

Bản cập nhật tháng 7 và tháng 8 năm 2021 bao gồm một tính năng mới, nâng cấp hiệu suất và sửa lỗi.

### <a name="extensibility"></a>Khả năng mở rộng

- **Xuất phân khúc sang Klaviyo** Chúng tôi đã mở rộng [các đích xuất của mình để bao gồm Klaviyo](export-klaviyo.md). Giờ đây, bạn có thể xuất các phân khúc để tạo chiến dịch, tiếp thị qua email và sử dụng các nhóm khách hàng cụ thể với Klaviyo. 


## <a name="june-2021-updates"></a>Bản cập nhật tháng 6 năm 2021

Bản cập nhật tháng 6 năm 2021 bao gồm một vài tính năng, nâng cấp hiệu suất và sửa lỗi.

### <a name="data-ingestion"></a>Nhập dữ liệu

- **Cải tiến bản cập nhật tiến trình hợp nhất dữ liệu** Bạn hiện có thể xem các bản cập nhật trạng thái động được cải tiến, chi tiết hơn trên các bước [quy trình hợp nhất dữ liệu](data-unification.md). Tính năng này cho phép bạn theo dõi tiến trình chi tiết để hiểu quy trình của quy trình và thực hiện hành động nếu bất kỳ bước nào cần chú ý.

### <a name="extensibility"></a>Khả năng mở rộng

- **Xuất các phân khúc và dữ liệu khác sang Salesforce Marketing Cloud** Chúng tôi đã mở rộng các đích xuất của mình để bao gồm [Salesforce Marketing Cloud](export-salesforce.md). Giờ đây, bạn có thể xuất các phân khúc và các loại dữ liệu khác sang Salesforce Marketing Cloud thông qua xuất SFTP có thương hiệu. Việc nhập dữ liệu có thể hoàn toàn tự động trong Salesforce và được sử dụng để tạo các chiến dịch tiếp thị hiệu quả hơn.  
 
- **Xuất phân khúc sang ActiveCampaign** Chúng tôi đã mở rộng các đích xuất của mình để bao gồm [Chiến dịch hiện hoạt](export-active-campaign.md). Bạn hiện có thể xuất các phân khúc để tạo chiến dịch, chạy email tiếp thị và hợp tác với các nhóm khách hàng cụ thể trong ActiveCampaign.
 
- **Xuất phân khúc sang Sendinblue** Chúng tôi đã mở rộng các đích xuất của mình để bao gồm [Sendinblue](export-sendinblue.md). Bạn hiện có thể xuất các phân khúc để tạo chiến dịch, chạy email tiếp thị và hợp tác với các nhóm khách hàng cụ thể thông qua Sendinblue.
 
### <a name="ux-updates"></a>Bản cập nhật UX 

- **Trang khách hàng mới và nâng cao và trang chi tiết hồ sơ** Chúng tôi đã thiết kế lại trang Khách hàng và trang chi tiết hồ sơ để cải thiện trải nghiệm người dùng và hiệu suất tốt hơn. Những thay đổi này cho phép bạn xem, sắp xếp, tìm kiếm và lọc khách hàng. Bộ lọc hiện được trình bày trong URL để chia sẻ kết quả tìm kiếm với những người dùng khác một cách liền mạch. Kết quả tìm kiếm cũng có thể được lưu dưới dạng phân khúc.    
  Trang chi tiết cho hồ sơ khách hàng hiện nhóm dữ liệu thành nhiều phần phụ khác nhau, chẳng hạn như dữ liệu nhân khẩu học, ID và các thuộc tính hồ sơ khác để cải thiện khả năng đọc. Các phần khác trên trang chi tiết hồ sơ hiện tương tác hơn. Ví dụ: phần hoạt động hiện cho phép lọc và sắp xếp.


## <a name="may-2021-updates"></a>Bản cập nhật tháng 5 năm 2021

Bản cập nhật tháng 5 năm 2021 bao gồm một số tính năng, bản nâng cấp hiệu suất và bản sửa lỗi.

### <a name="data-ingestion"></a>Nhập dữ liệu

- **Xem hoặc sửa đổi siêu dữ liệu hoặc định nghĩa đối tượng khi đính kèm dữ liệu từ Azure Data Lake Storage của bạn** Giờ đây, bạn có thể xem và chỉnh sửa siêu dữ liệu hoặc định nghĩa đối tượng trong thông tin chi tiết về đối tượng khi đính kèm dữ liệu từ thư mục Mô hình dữ liệu chung trong Azure Data Lake Storage của bạn. Chức năng này cung cấp ý kiến phản hồi theo thời gian thực, tùy chọn xác thực mô hình và kiểm tra lỗi. Chức năng này cho phép bạn chỉnh sửa dễ dàng cả tệp model.json và manifest.json.

### <a name="extensibility"></a>Khả năng mở rộng

- **Cải thiện nội dung xuất phân khúc, lịch trình tùy chỉnh và bản sao** Giờ đây, bạn có thể [xem tất cả nội dung xuất của một phân khúc cụ thể](export-destinations.md#view-exports-and-export-details) trong một danh sách. Dạng xem mới này giúp quản lý cách một phân khúc cụ thể được dùng và điều chỉnh nội dung xuất hiện có hoặc tạo nội dung xuất mới.    
  Bạn có thể [xác định lịch làm mới tùy chỉnh](export-destinations.md#schedule-and-run-exports) cho từng nội dung xuất hoặc một vài nội dung xuất cùng lúc. Cho đến nay, tất cả các nội dung xuất đều được chạy trong mỗi lần làm mới hệ thống.    
  Thay vì tạo nội dung xuất mới từ đầu, bạn có thể bắt đầu dựa trên một nội dung xuất hiện có để tiết kiệm thời gian.

- **Xuất phân khúc sang Microsoft Advertising** Chúng tôi đã mở rộng các đích xuất của mình để bao gồm cả Microsoft Advertising. Tạo đối tượng Customer Match trên Microsoft Advertising bằng dữ liệu hồ sơ khách hàng hợp nhất của bạn và sử dụng các đối tượng này cho chiến dịch quảng cáo. Để biết thêm thông tin, hãy xem bài viết [Xuất phân khúc sang Microsoft Advertising](export-microsoft-advertising.md).

- **Xuất phân khúc sang LinkedIn Ads** Chúng tôi đã mở rộng các đích xuất của mình để bao gồm cả LinkedIn Ads, đồng thời cho phép bạn mở khóa chức năng Nhắm mục tiêu người liên hệ và Nhắm mục tiêu công ty thông qua LinkedIn bằng cách xuất dữ liệu hồ sơ khách hàng hợp nhất của bạn. Để biết thêm thông tin, hãy xem bài viết [Xuất phân khúc sang LinkedIn Ads](export-linkedin-ads.md).


- **Xuất phân khúc sang Omnisend** Chúng tôi đã mở rộng các đích xuất của mình để bao gồm cả Omnisend. Sử dụng phân khúc đã tạo trong thông tin chi tiết về đối tượng để tạo chiến dịch, cung cấp email tiếp thị và tận dụng các nhóm khách hàng cụ thể với Omnisend. Để biết thêm thông tin, hãy xem bài viết [Xuất phân khúc sang Omnisend](export-omnisend.md)

### <a name="predictions"></a>Dự đoán

- **Báo cáo khả năng sử dụng dữ liệu đầu vào** Báo cáo này cung cấp một dạng xem tổng hợp về các lỗi và cảnh báo mà các dự đoán có sẵn của bạn có thể đang tạo ra. Báo cáo này cũng đưa ra đề xuất về cách cải thiện hiệu suất của mô hình.    
  Báo cáo này có sẵn sau khi một mô hình đã hoàn tất quá trình đào tạo. Báo cáo được tạo cho từng mô hình riêng biệt, bất kể quá trình có hoàn tất thành công hay không.
  Hiện tại, tính năng này chỉ hỗ trợ mô hình Khả năng rời bỏ giao dịch. Để biết thêm thông tin, hãy xem phần [Báo cáo khả năng sử dụng dữ liệu đầu vào](manage-predictions.md#input-data-usability-report).

### <a name="relationships"></a>Mối quan hệ

- **Trình hiển thị mối quan hệ** Dạng xem trình hiển thị mối quan hệ cho phép bạn xem tất cả các mối quan hệ hiện có giữa các thực thể và lượng số của chúng. Giờ đây, các mối quan hệ được sắp xếp theo nhóm: do người dùng tạo, hệ thống và kế thừa. Bạn cũng có thể xuất dạng xem dưới dạng hình ảnh. Để biết thêm thông tin, hãy xem phần [Xem mối quan hệ](relationships.md#view-relationships). 

## <a name="april-2021-updates"></a>Bản cập nhật tháng 4 năm 2021

Các bản cập nhật vào tháng 4 năm 2021 bao gồm một số tính năng, bản nâng cấp hiệu suất và sửa lỗi.

### <a name="data-unification"></a>Thống nhất dữ liệu
 
- **Nâng cao trải nghiệm hợp nhất cho quá trình hợp nhất dữ liệu**    
  
   Hiện nay, chúng tôi có trải nghiệm người dùng nâng cao trong cấu hình hợp nhất của quá trình hợp nhất dữ liệu. Những thay đổi bao gồm thứ tự trực quan của các trường đã hợp nhất cùng thống kê chi tiết về các trường kết hợp và trường đơn.

- **Thực thể sắp xếp lại thứ tự và đặt cấu hình tất cả các bản ghi nguồn sang thực thể Khách hàng**  
      
   Giờ đây, bạn có thể sắp xếp lại thứ tự và xóa các thực thể khỏi kế hoạch hợp nhất hiện có trong quá trình hợp nhất dữ liệu. Điều này giúp bạn có thể linh hoạt sắp xếp lại các thực thể trong quá trình đối sánh tùy theo nhu cầu kinh doanh. Ngoài ra, chúng tôi cho phép thêm tất cả các bản ghi không khớp vào bản cuối cùng thực thể *Khách hàng*, giúp họ xác định định nghĩa tập dữ liệu hồ sơ khách hàng của mình.

### <a name="enrichments"></a>Nội dung tăng cường

 - **Tính năng tăng cường mới: Địa chỉ nâng cao**    
  
   Chúng tôi rất vui được giới thiệu một cách tăng cường mới giúp nâng cao các địa chỉ trong dữ liệu khách hàng của bạn. Địa chỉ trong dữ liệu của bạn có thể phi cấu trúc, không đầy đủ hoặc không chính xác. Tính năng này sử dụng các mô hình của Microsoft để chuẩn hóa và tăng cường các địa chỉ của bạn thành định dạng Common Data Model để có thông tin chi tiết và độ chính xác cao hơn.
 
   Để biết thêm thông tin, hãy xem phần [Tăng cường hồ sơ khách hàng với địa chỉ nâng cao](enrichment-enhanced-addresses.md).

- **Trải nghiệm cấu hình có hướng dẫn nhằm tăng cường địa chỉ**    
  
   Chúng tôi đã xem xét lại trải nghiệm cấu hình để tăng cường địa chỉ với trải nghiệm đơn giản, có hướng dẫn. Giờ đây, bạn đã có quy trình từng bước rõ ràng để tạo và chỉnh sửa các nội dung tăng cường.
 
   Ngoài ra, chúng tôi đã tách cấu hình của các kết nối cho nội dung tăng cường của bên thứ ba nhằm cho phép các nội dung này có thể sử dụng cùng một kết nối. Chỉ quản trị viên là có thể đặt cấu hình các kết nối mới nhưng các kết nối đã tạo có sẵn cho cả quản trị viên và người đóng góp.    

   Để biết thêm thông tin, xem [Tổng quan về kết nối](connections.md).

- **Nhiều nội dung bổ sung thuộc cùng loại**    
  
   Giờ đây, người dùng có thể tạo và quản lý nhiều nội dung tăng cường cùng loại. Ví dụ: hiện tại, bạn có thể tạo hai nội dung tăng cường địa chỉ riêng biệt cho hai phân khúc khách hàng khác nhau. Các giới hạn áp dụng đối với số lượng nội dung tăng cường cùng loại có thể được tạo và thay đổi tùy thuộc vào loại nội dung tăng cường.
  
   Để biết thêm thông tin, hãy xem [Nội dung phong phú cho hồ sơ khách hàng](enrichment-hub.md).

## <a name="march-2021-updates"></a>Bản cập nhật tháng 3 năm 2021

Các bản cập nhật vào tháng 3 năm 2021 bao gồm một số tính năng, bản nâng cấp hiệu suất và sửa lỗi.

### <a name="activities"></a>Hoạt động

- **Trình hướng dẫn hoạt động và các kiểu ngữ nghĩa**

   Chúng tôi đã cải thiện và cập nhật trải nghiệm ánh xạ hoạt động để hướng dẫn và đơn giản hóa việc tạo quá trình ánh xạ hoạt động. Trong phiên bản mới này, người dùng nhận được trải nghiệm có hướng dẫn để giúp hoàn thành từng bước của quy trình. Ở bước ánh xạ hoạt động, ngoài việc chọn từ nhiều loại hoạt động, người dùng có thể chọn ánh xạ dữ liệu theo ngữ nghĩa cho *Subscription* và/hoặc *SalesOrderLine* với các lược đồ theo tiêu chuẩn của ngành (có thể được dùng cho trường hợp sử dụng ở hạ nguồn).   

   Để biết thêm thông tin, hãy xem [Hoạt động của khách hàng](activities.md).

### <a name="data-ingestion"></a>Nhập dữ liệu

- **Kết nối với nguồn dữ liệu tại chỗ bằng cách sử dụng Power Platform luồng dữ liệu và cổng** Chúng tôi vui mừng thông báo bản xem trước luồng dữ liệu Power Platform và kết nối tại chỗ sử dụng các cổng trong Thông tin chi tiết về khách hàng với môi trường Power Platform hoặc Dataverse được liên kết. Bất kỳ nguồn dữ liệu mới nào được tạo trong môi trường Thông tin chi tiết về khách hàng với môi trường Dataverse được liên kết sẽ mặc định thành luồng dữ liệu Power Platform mang đến kết nối dữ liệu tại chỗ và một loạt trình kết nối và khả năng chuyển đổi phong phú.

### <a name="extensibility"></a>Khả năng mở rộng

- **Nội dung xuất được sắp xếp theo các kết nối và nội dung xuất** Chúng tôi đã thay đổi tên của trang **Đích xuất** thành **Kết nối** và đã thêm một trang riêng biệt cho **Nội dung xuất**. Là một phần của bản cập nhật này, chúng tôi sẽ chuyển các nội dung xuất hiện có thành các cặp kết nối và nội dung xuất sử dụng kết nối đó. Quản trị viên hiện đã hiểu rõ hơn về dữ liệu gửi đi trên trang **Kết nối**. Tất cả các vai trò người dùng đều có quyền truy cập vào trang **Nội dung xuất** nhưng chỉ có quản trị viên là có thể chọn cho phép người đóng góp chỉnh sửa các nội dung xuất cụ thể bằng các kết nối được chia sẻ.     
  Để biết thêm thông tin, hãy xem [Tổng quan về kết nối](connections.md) và [Tổng quan về nội dung xuất](export-destinations.md).

- **Xuất phân khúc sang Campaign Monitor** Chúng tôi đã mở rộng các đích xuất của mình để bao gồm cả Campaign Monitor. Giờ đây, bạn có thể xuất các phân khúc từ danh sách trên Customer Insights sang Campaign Monitor và sử dụng chúng làm cơ sở cho các chiến dịch tiếp thị của mình.    
   Để biết thêm thông tin, hãy xem [Xuất sang Campaign Monitor](export-campaign-monitor.md).

- **Xuất phân khúc sang Constant Contact** Chúng tôi đã mở rộng các đích xuất của mình để bao gồm cả Constant Contact. Giờ đây, bạn có thể xuất các phân khúc từ danh sách trên Customer Insights sang Constant Contact và sử dụng chúng làm cơ sở cho các chiến dịch tiếp thị của mình.   
   Để biết thêm thông tin, hãy xem [Xuất sang Constant Contact](export-constant-contact.md).

- **Xuất phân khúc sang RollWorks** Chúng tôi đã mở rộng các đích xuất của mình để bao gồm cả RollWorks. Giờ đây, bạn có thể xuất các phân khúc từ Customer Insights sang đối tượng RollWorks và sử dụng chúng làm cơ sở cho quảng cáo B2B của mình.    
   Để biết thêm thông tin, hãy xem [Xuất sang RollWorks](export-rollworks.md).

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
 
- **Sao chép phân khúc**
  
  Để tạo một phân khúc mới dựa trên một phân khúc hiện có, bạn có thể sao chép một phân khúc và chỉnh sửa phân khúc đã sao chép để tinh chỉnh thêm. 

- **Thêm các thuộc tính bổ sung vào một phân khúc**

  Giờ đây, bạn có thể bao gồm các thuộc tính trong đầu ra phân khúc, ngay cả khi các thuộc tính này không phải là một phần của hồ sơ khách hàng. Ví dụ: bao gồm các ID đăng ký trong một phân khúc mặc dù nó là một phần của thực thể đăng ký có mối quan hệ M: 1 với thực thể khách hàng. Miễn là thuộc tính thuộc về một thực thể có liên quan đến thực thể khách hàng, bây giờ bạn có thể bao gồm các thuộc tính này.  

#### <a name="predictions"></a>Dự đoán

- **Tạo đề xuất dự đoán về sản phẩm**

  Hiểu những gì khách hàng quan tâm khi mua hàng là một trong những bước đầu tiên cần thiết để cải thiện doanh thu kinh doanh và xây dựng lòng trung thành của khách hàng thông qua cá nhân hóa và tương tác. Việc cung cấp các đề xuất cho các sản phẩm không phù hợp với sở thích của khách hàng có thể tạo ra cảm giác mất kết nối giữa khách hàng và doanh nghiệp của bạn và cuối cùng hạn chế doanh thu tiềm năng và trải nghiệm tổng thể cho khách hàng. 

  Sử dụng dữ liệu của riêng bạn, giờ đây bạn có thể tạo dự đoán cho những sản phẩm mà khách hàng của bạn có khả năng mua trong tương lai. Để biết thêm thông tin, hãy xem [Đề xuất sản phẩm dự đoán](predict-product-recommendation.md).

#### <a name="system-administration"></a>Quản trị hệ thống

- **Môi trường sao chép hỗ trợ nhiều loại nguồn dữ liệu hơn**

  Quản trị viên có thể sao chép cấu hình môi trường sang môi trường mới trong cùng một tổ chức. Tính năng này mở rộng chức năng môi trường sao chép cho các trường hợp sử dụng nguồn dữ liệu dựa trên hồ dữ liệu được quản lý Microsoft Dataverse hoặc thư mục Mô hình Dữ liệu Chung.

## <a name="january-2021-updates"></a>Bản cập nhật tháng 1 năm 2021

Bản cập nhật tháng 1 năm 2021 bao gồm một vài tính năng, nâng cấp hiệu suất và sửa lỗi.

#### <a name="extensibility"></a>Khả năng mở rộng

- **Chức năng mở rộng và hiệu suất nâng cao cho chức năng xuất SFTP** Giờ đây, bạn có thể xuất tất cả các thực thể đầu ra từ Customer Insights sang máy chủ SFTP. Trước đây, tính năng xuất được giới hạn trong các thực thể phân khúc. Ngoài ra, hiệu suất của tính năng xuất SFTP cho phép nhiều dữ liệu hơn trong thời gian ngắn hơn, tùy thuộc vào hiệu suất của máy chủ SFTP của bạn.    
  Để biết thêm thông tin, hãy xem [Trình kết nối cho SFTP (xem trước)](export-sftp.md).  

#### <a name="segments"></a>Phân khúc

- **Các phân khúc đề xuất dựa trên công nghệ máy học để cải thiện chỉ số** Có một cách mới để khám phá và tạo phân khúc. Hệ thống sử dụng mô hình trí tuệ nhân tạo để đề xuất các phân khúc có thể giúp cải thiện KPI (giá trị đo) mà bạn đang theo dõi. Chúng tôi cho biết mức độ ảnh hưởng của các thuộc tính mà bạn chọn đối với giá trị đo hoặc một thuộc tính chính khác. Thông tin này giúp tìm kiếm các phân khúc tiềm năng mang lại cơ hội.    
  Để biết thêm thông tin, hãy xem bài viết [Phân khúc đề xuất (xem trước)](suggested-segments.md).

#### <a name="data-unification"></a>Thống nhất dữ liệu

- **Nâng cao trải nghiệm so khớp** Trong khu vực hợp nhất dữ liệu, trải nghiệm so khớp đã được cập nhật. Nó cho phép bạn đặt cấu hình và xem các quy tắc đối sánh, bao gồm số liệu thống kê chi tiết để giải thích thêm về cách đối sánh hoạt động. Có các tùy chọn để tắt quy tắc đối sánh để quy tắc đó không còn hoạt động trong khi vẫn giữ nguyên cấu hình, kéo và thả quy tắc đối sánh, v.v.
  Để biết thêm thông tin, hãy xem phần [Đối sánh các thực thể](match-entities.md).

- **Đầu ra khử trùng lặp từ quy trình đối sánh có sẵn dưới dạng thực thể** Đầu ra của quy trình khử trùng lặp từ quy trình đối sánh hiện được viết thành một thực thể riêng biệt để phân tích thêm. Thực thể này bao gồm các trường được sử dụng trong quá trình loại bỏ trùng lặp, đồng thời, bản ghi chiến thắng và bản ghi thay thế tương ứng được hợp nhất với bản ghi chiến thắng.
  Để biết thêm thông tin, hãy xem [Đầu ra khử trùng lặp dưới dạng một thực thể](match-entities.md#deduplication-output-as-an-entity).

#### <a name="system-administration"></a>Quản trị hệ thống

- **Chia sẻ dữ liệu liền mạch với Microsoft Dataverse** Giờ đây, bạn có thể chia sẻ kết quả Thông tin chi tiết về khách hàng với các ứng dụng Microsoft Dataverse bằng cách sử dụng Hồ dữ liệu được quản lý Microsoft Dataverse. Sau khi liên kết môi trường Dataverse với Thông tin chi tiết về khách hàng, bạn sẽ có tùy chọn bật chia sẻ dữ liệu.
  Để biết thêm thông tin, hãy xem [Quản lý môi trường](manage-environments.md).




[!INCLUDE[footer-include](../includes/footer-banner.md)]