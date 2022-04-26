---
title: Các tính năng mới sắp ra mắt
description: Thông tin về các tính năng mới, cải tiến và sửa lỗi.
ms.date: 04/05/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: skumm
manager: shellyha
ms.openlocfilehash: 2f081306271a170cf3e250fc1a193cedb70aeec6
ms.sourcegitcommit: 0363559a1af7ae16da2a96b09d6a4a8a53a8cbb8
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 04/05/2022
ms.locfileid: "8547698"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>Có gì mới trong chức năng thông tin chi tiết về đối tượng của Dynamics 365 Customer Insights

Chúng tôi rất vui được công bố các bản cập nhật mới nhất của mình! Bài viết này tóm tắt các tính năng xem trước công khai, các điểm cải tiến được phát hành rộng rãi và những điểm cập nhật tính năng. Để xem các kế hoạch dài hạn đối với tính năng, hãy xem [kế hoạch phát hành Dynamics 365 và Power Platform](/dynamics365/release-plans/).

Chúng tôi sẽ triển khai các điểm cập nhật trên cơ sở từng khu vực. Do đó, một số khu vực sẽ thấy các tính năng trước khu vực khác. Trừ khi có lưu ý khác, bạn sẽ không phải thực hiện nào và chúng tôi sẽ tự động cập nhật ứng dụng mà không gây ra thời gian ngừng hoạt động.

> [!TIP]
> Để gửi và bình chọn cho các yêu cầu về tính năng cũng như gợi ý về sản phẩm, hãy truy cập vào [Cổng ý tưởng ứng dụng Dynamics 365](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).


## <a name="march-2022-updates"></a>Cập nhật tháng 3 năm 2022

Các bản cập nhật vào tháng 3 năm 2022 bao gồm các tính năng mới, nâng cấp hiệu suất và sửa lỗi.

### <a name="liveramp-abilitec-enrichment-preview"></a>Làm giàu LiveRamp AbiliTec (Xem trước)

LiveRamp cung cấp giải pháp nhận dạng và hợp nhất dữ liệu khách hàng. Bạn có thể ánh xạ các số nhận dạng cá nhân trong dữ liệu khách hàng của mình với biểu đồ nhận dạng AbiliTec và nhận các ID AbiliTec. Sau đó, bạn có thể sử dụng các ID này để thống nhất dữ liệu khách hàng của mình tốt hơn.

Để biết thêm thông tin, hãy xem [Làm phong phú hồ sơ khách hàng với dữ liệu nhận dạng từ LiveRamp (Xem trước)](enrichment-liveramp.md).

### <a name="organize-segments-and-measures-with-tags-and-filters"></a>Tổ chức các phân đoạn và thước đo bằng các thẻ và bộ lọc
Nếu tổ chức của bạn duy trì nhiều phân đoạn hoặc biện pháp, việc tìm kiếm phân khúc phù hợp đôi khi có thể cảm thấy khó khăn. Tính năng mới này cho phép bạn tổ chức danh sách bằng cách sử dụng thẻ và cột. Nó giúp tìm kiếm dữ liệu nhanh chóng và dễ dàng và tùy chỉnh các chế độ xem.

Để biết thêm thông tin, hãy xem [Làm việc với các thẻ và cột](work-with-tags-columns.md).

### <a name="enable-data-sharing-with-dataverse-when-using-your-own-storage-account"></a>Bật chia sẻ dữ liệu với Dataverse khi sử dụng tài khoản lưu trữ của riêng bạn

Nếu môi trường của bạn sử dụng Azure Data Lake Storage để lưu trữ dữ liệu Thông tin chi tiết về khách hàng, chia sẻ dữ liệu với Microsoft Dataverse cần một số cấu hình bổ sung.
Trước đó, bạn chỉ có thể bật chia sẻ dữ liệu với Dataverse khi dữ liệu của bạn được lưu trữ trong hồ dữ liệu được quản lý của chúng tôi. 

Để biết thêm thông tin, hãy xem [Bật chia sẻ dữ liệu với Dataverse từ của riêng bạn Azure Data Lake Storage (Xem trước)](manage-environments.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview).

### <a name="new-export-destinations-iterable-and-braze"></a>Các điểm đến xuất khẩu mới: Có thể lặp lại và Braze

Chúng tôi đang tiếp tục mở rộng hệ sinh thái các điểm đến xuất khẩu của mình với các kết nối mới. Bây giờ bạn có thể xuất các phân đoạn sang Iterable và Braze để sử dụng các dịch vụ kích hoạt của họ.

Để biết thêm thông tin, hãy xem [Xuất phân đoạn sang Có thể lặp lại (xem trước)](export-iterable.md) và [Xuất phân đoạn sang Braze (xem trước)](export-braze.md).

### <a name="improvements-to-marketo-and-google-ads-export"></a>Cải tiến Marketo và xuất Google Ads

Việc thay đổi API trong các dịch vụ được kết nối dẫn đến các bản cập nhật cho các trình kết nối chạy một cách đáng tin cậy và trơn tru. Chúng tôi đã phát hành một số cập nhật cho việc xuất sang các dịch vụ Marketo và Google Ads:

- Google Ads: Phiên bản mới của trình kết nối xuất Google Ads đơn giản hóa trải nghiệm xác thực và giờ đây cho phép bạn tự động tạo các đối tượng Google Ads mới. 
- Marketo: Phiên bản mới của trình kết nối xuất Marketo cung cấp hỗ trợ cho ID Marketo, cho phép bạn tránh trùng lặp dữ liệu, cập nhật các bản ghi hiện có và tạo bản ghi mới trong Marketo. 


## <a name="february-2022-updates"></a>Bản cập nhật tháng 2 năm 2022

Các bản cập nhật vào tháng 2 năm 2022 bao gồm các tính năng mới, nâng cấp hiệu suất và sửa lỗi.

### <a name="general-availability-for-prediction-models"></a>Tính sẵn có chung cho các mẫu dự đoán

Các mẫu dự đoán xuất xưởng, bao gồm **đăng ký churn**, **dịch churn**, và **giá trị lâu dài của khách hàng (CLV)** nói chung trở nên khả dụng như một phần của Thông tin chi tiết về khách hàng. 

Để biết thêm thông tin, hãy xem [Tổng quan về dự đoán](predictions-overview.md).

### <a name="new-data-source-integration-with-azure-synapse-analytics-preview"></a>Nguồn dữ liệu mới: Tích hợp với Azure Synapse Analytics (Xem trước)

Azure Synapse Analytics là một dịch vụ phân tích doanh nghiệp giúp tăng tốc thời gian để hiểu rõ hơn về các kho dữ liệu và hệ thống dữ liệu lớn.

Các tổ chức đã sử dụng Azure Synapse Analytics có thể nhập dữ liệu đó vào Thông tin chi tiết về khách hàng. 

Để biết thêm thông tin, hãy xem [Kết nối một Azure Synapse nguồn dữ liệu (Xem trước)](connect-synapse.md).

### <a name="liveramp-enrichment-preview"></a>Làm giàu LiveRamp (Xem trước)

LiveRamp cung cấp giải pháp nhận dạng và hợp nhất dữ liệu khách hàng. Bạn có thể ánh xạ các số nhận dạng cá nhân trong dữ liệu khách hàng của mình với biểu đồ nhận dạng AbiliTec và nhận các ID AbiliTec. Sau đó, bạn có thể sử dụng các ID này để thống nhất dữ liệu khách hàng của mình tốt hơn.

Để biết thêm thông tin, hãy xem [Làm phong phú hồ sơ khách hàng với dữ liệu nhận dạng từ LiveRamp (Xem trước)](enrichment-liveramp.md).

### <a name="enrichment-for-data-sources-preview"></a>Làm giàu cho nguồn dữ liệu (Xem trước)

Sử dụng dữ liệu từ các nguồn như Microsoft và các đối tác khác để làm phong phú thêm dữ liệu khách hàng của bạn trước khi thống nhất dữ liệu. Nguồn dữ liệu làm giàu giúp tạo ra chất lượng và độ hoàn chỉnh của dữ liệu cao hơn có thể giúp đạt được kết quả tốt hơn sau khi bạn thống nhất dữ liệu của mình.

Để biết thêm thông tin, hãy xem [Làm giàu cho nguồn dữ liệu (Xem trước)](data-sources-enrichment.md).

### <a name="change-owner-of-environment"></a>Thay đổi chủ sở hữu môi trường

Mặc dù một số người dùng có thể có quyền quản trị trong Thông tin chi tiết về khách hàng, nhưng chỉ một người dùng là chủ sở hữu của môi trường. Trải nghiệm được cải thiện cho phép bạn thay đổi chủ sở hữu của môi trường và xác nhận quyền sở hữu nếu chủ sở hữu cũ rời tổ chức. 

Để biết thêm thông tin, hãy xem [Thay đổi chủ sở hữu của một môi trường](manage-environments.md#change-the-owner-of-an-environment).

### <a name="data-preparation-process-lists-corruption-reason-for-corrupted-records"></a>Quá trình chuẩn bị dữ liệu liệt kê lý do hỏng cho các bản ghi bị hỏng

Việc chuẩn bị dữ liệu bây giờ cho thấy lý do gây ra hỏng cho tất cả các lĩnh vực có dữ liệu bị hỏng. Thông tin được cung cấp ở cấp độ hồ sơ cá nhân để dễ dàng xác định. 

Để biết thêm thông tin, hãy xem [Nguồn dữ liệu bị hỏng](entities.md#corrupted-data-sources).

### <a name="end-of-preview-for-reporting-features-in-the-engagement-insights-capability"></a>Kết thúc bản xem trước cho các tính năng báo cáo trong khả năng thông tin chi tiết về mức độ tương tác

Các Dynamics 365 Customer Insights bản xem trước khả năng thông tin chi tiết về mức độ tương tác đã kết thúc vào ngày 15 tháng 2 năm 2022.  
Thay đổi này có nghĩa là trải nghiệm dùng thử Customer Insights không còn bao gồm khả năng tạo kênh cũng như chức năng báo cáo khác.

Chúng tôi mời bạn khám phá và đánh giá nhiều tính năng khác của [Thấu hiểu khách hàng](https://dynamics.microsoft.com/ai/customer-insights/), nền tảng dữ liệu khách hàng của Microsoft (CDP).    
 
Trong khoảng thời gian chuyển tiếp, những người tham gia xem trước hiện tại vẫn có quyền truy cập vào một số chức năng và chức năng xem trước:

- Tải mã để trang bị cho một trang web hoặc ứng dụng dành cho thiết bị di động 
- Xem sự kiện và thuộc tính sự kiện 
- Nâng cao hồ sơ hợp nhất với các sự kiện được nhập và tinh chỉnh để hưởng lợi từ toàn bộ giá trị dữ liệu khách hàng của họ
  
Trong giai đoạn chuyển tiếp, các sự kiện đã ghi vẫn được truyền trực tuyến đến Data Lake được kết nối. Sau khi tắt chức năng này, việc chia sẻ dữ liệu giữa thông tin chi tiết về mức độ tương tác và thông tin chi tiết về đối tượng sẽ ngừng và không có sự kiện mới nào được gửi đến bộ nhớ được kết nối.
Liên hệ trực tiếp với nhóm Tài khoản Microsoft của bạn nếu bạn có thắc mắc về phần cuối của bản xem trước khả năng. Nhóm Tài khoản của bạn sẽ cập nhật cho bạn về các lần ra mắt sắp tới. 

## <a name="january-2022-updates"></a>Cập nhật tháng 1 năm 2022

Các bản cập nhật vào tháng 1 năm 2022 bao gồm các tính năng mới, nâng cấp hiệu suất và sửa lỗi.

### <a name="sentiment-analysis-of-your-customers-feedback"></a>Phân tích cảm xúc về phản hồi của khách hàng của bạn

Thông tin chi tiết về khách hàng cung cấp một tính năng mới do AI hỗ trợ để tổng hợp tâm lý khách hàng và xác định các khía cạnh kinh doanh cụ thể làm cơ hội cho các cải tiến được nhắm mục tiêu. Bằng cách phân tích phản hồi bằng văn bản của khách hàng, bạn có thể nhận được thông tin chi tiết chính xác với chi phí thấp. Phân tích tình cảm được cung cấp bởi các mô hình Xử lý ngôn ngữ tự nhiên (NLP) tạo ra hai thông tin chi tiết có được cho mỗi ID khách hàng. Điểm tình cảm (từ –5 đến 5) và danh sách các khía cạnh kinh doanh có thể áp dụng. 

Để biết thêm thông tin, hãy xem [Phân tích tình cảm trong phản hồi của khách hàng (Xem trước)](sentiment-analysis.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]