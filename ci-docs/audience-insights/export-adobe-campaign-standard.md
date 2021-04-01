---
title: Xuất dữ liệu Customer Insights sang Adobe Campaign Standard
description: Tìm hiểu cách sử dụng phân đoạn thông tin chi tiết về đối tượng trong Adobe Campaign Standard.
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: a5d0154c3d7c473dcba03fac0847bafcf97de2f2
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596341"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a>Sử dụng phân đoạn Customer Insights trong Adobe Campaign Standard (xem trước)

Là người dùng thông tin chi tiết đối tượng trong Dynamics 365 Customer Insights, bạn có thể đã tạo các phân khúc để chiến dịch tiếp thị trở nên hiệu quả hơn bằng cách nhắm mục tiêu các đối tượng phù hợp. Để sử dụng phân khúc từ thông tin chi tiết đối tượng trong Nền tảng trải nghiệm Adobe và các ứng dụng như Adobe Campaign Standard, bạn cần làm theo một vài bước nêu trong bài viết này.

:::image type="content" source="media/ACS-flow.png" alt-text="Sơ đồ quy trình các bước nêu trong bài viết này.":::

## <a name="prerequisites"></a>Điều kiện tiên quyết

-   Giấy phép Dynamics 365 Customer Insights
-   Giấy phép Adobe Campaign Standard
-   Tài khoản lưu trữ Azure Blob

## <a name="campaign-overview"></a>Tổng quan Chiến dịch

Để hiểu rõ hơn về cách bạn có thể sử dụng các phân khúc từ thông tin chi tiết về đối tượng trong Nền tảng trải nghiệm Adobe, hãy xem một chiến dịch mẫu giả tưởng.

Giả sử rằng công ty của bạn cung cấp dịch vụ dựa trên đăng ký hàng tháng cho khách hàng của bạn ở Hoa Kỳ. Bạn muốn xác định những khách hàng có đăng ký sẽ đến hạn gia hạn trong 8 ngày tới nhưng chưa gia hạn đăng ký của họ. Để giữ chân những khách hàng này, bạn nên gửi khuyến mại cho họ qua email, sử dụng Adobe Campaign Standard.

Trong ví dụ này, chúng tôi muốn chạy chiến dịch email quảng cáo một lần. Bài viết này không đề cập đến trường hợp sử dụng của việc chạy chiến dịch nhiều lần. Tuy nhiên, thông tin chi tiết về đối tượng và Adobe Campaign Standard cũng có thể được định cấu hình để hoạt động cho một kịch bản chiến dịch lặp lại.

## <a name="identify-your-target-audience"></a>Xác định đối tượng mục tiêu của bạn

Trong kịch bản của chúng tôi, chúng tôi giả định rằng địa chỉ email của khách hàng có sẵn trong thông tin chi tiết về đối tượng và các sở thích khuyến mại của họ đã được phân tích để xác định các thành viên của phân khúc.

[Phân khúc bạn đã xác định trong thông tin chi tiết về đối tượng](segments.md) được gọi là **ChurnProneCustomers** và bạn dự định gửi những khách hàng này ưu đãi qua email.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Ảnh chụp màn hình của trang phân khúc đã tạo phân khúc ChurnProneCustomers.":::

Email ưu đãi mà bạn muốn gửi sẽ chứa tên, họ, và ngày kết thúc đăng ký của khách hàng. Email đó thông báo cho khách hàng về khoản chiết khấu mà họ sẽ nhận được nếu họ gia hạn đăng ký trước khi nó kết thúc.

## <a name="export-your-target-audience"></a>Xuất đối tượng mục tiêu của bạn

Với đối tượng mục tiêu đã được xác định, chúng tôi có thể định cấu hình xuất từ thông tin chi tiết về đối tượng sang tài khoản Lưu trữ Azure Blob.

1. Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Quản trị viên** > **Nơi xuất đích**.

1. Trong ngăn xếp **Adobe Campaign**, chọn **Thiết lập**.

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Ngăn xếp cấu hình cho Adobe Campaign Standard.":::

1. Cung cấp **Tên hiển thị** cho đích xuất mới này rồi nhập **Tên tài khoản**, **Khóa tài khoản** và **Vùng chứa** của tài khoản Lưu trữ Azure Blob nơi bạn muốn xuất phân khúc.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Ảnh chụp màn hình cấu hình tài khoản lưu trữ. "::: 

   - Để biết cách tìm tên tài khoản và mã tài khoản Azure Blob Storage, hãy xem [Quản lý tùy chọn cài đặt của tài khoản lưu trữ trong cổng Azure](/azure/storage/common/storage-account-manage).

   - Để tìm hiểu cách tạo bộ chứa, hãy xem [Tạo bộ chứa](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Chọn **Tiếp theo**.

1. Chọn phân khúc mà bạn muốn xuất. Trong ví dụ này, phân khúc đó là **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Ảnh chụp màn hình giao diện người dùng chọn phân phúc đã chọn phân khúc ChurnProneCustomers.":::

1. Chọn **Tiếp theo**.

1. Bây giờ, chúng ta sẽ lập bản đồ trường **Nguồn** từ phân khúc thông tin chi tiết đối tượng đến tên trường **Đích** trong sơ đồ hồ sơ Adobe Campaign Standard.

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Ánh xạ trường cho trình kết nối Adobe Campaign Standard.":::

   Nếu bạn muốn thêm nhiều thuộc tính, hãy chọn **Thêm thuộc tính**. Tên mục tiêu có thể khác với tên trường nguồn để bạn vẫn có thể ánh xạ đầu ra của phân khúc từ thông tin chi tiết về đối tượng sang Adobe Campaign Standard nếu các trường không có cùng tên trong hai hệ thống.

   > [!NOTE]
   > Địa chỉ email được sử dụng làm trường nhận dạng, nhưng bạn có thể sử dụng bất kỳ số nhận dạng nào khác từ đối tượng của bạn thông tin chi tiết về hồ sơ khách hàng để ánh xạ dữ liệu tới Adobe Campaign Standard.

1. Chọn **Lưu**.

Sau khi lưu đích xuất, bạn sẽ tìm thấy trên **Quản trị** > **Xuất** > **Đích xuất**.

:::image type="content" source="media/export-destination-adobe-campaign-standard.png" alt-text="Ảnh chụp màn hình với danh sách các mục xuất và phân khúc mẫu được đánh dấu.":::

Bây giờ, bạn có thể [xuất phân khúc theo yêu cầu](export-destinations.md#export-data-on-demand). Mỗi lần [làm mới theo lịch](system.md), tác vụ xuất cũng sẽ chạy.

> [!NOTE]
> Đảm bảo rằng số lượng bản ghi trong phân khúc đã xuất nằm trong giới hạn cho phép của giấy phép Adobe Campaign Standard.

Dữ liệu đã xuất được lưu trữ trong vùng chứa Azure Blob mà bạn đã định cấu hình ở trên. Đường dẫn thư mục sau được tạo tự động trong vùng chứa của bạn:

*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*

Ví dụ: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Đặt cấu hình Adobe Campaign Standard

Khi một phân khúc từ thông tin chi tiết về đối tượng được xuất, phân khúc đó chứa các cột bạn đã chọn trong khi xác định đích xuất ở bước trước. Dữ liệu này có thể được dùng để [tạo hồ sơ trong Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).

Để sử dụng phân khúc trong Adobe Campaign Standard, chúng ta cần mở rộng sơ đồ hồ sơ trong Adobe Campaign Standard để bao gồm hai trường bổ sung. Tìm hiểu cách [mở rộng tài nguyên hồ sơ](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) với các trường mới trong Adobe Campaign Standard.

Trong ví dụ của chúng tôi các trường này là *Tên phân khúc và ngày phân khúc (tùy chọn).*

Chúng tôi sẽ sử dụng các trường này để xác định những hồ sơ trong Adobe Campaign Standard mà chúng tôi muốn nhắm mục tiêu cho chiến dịch này.

Nếu không có bản ghi nào khác trong Adobe Campaign Standard, ngoài những gì bạn sẽ nhập, bạn có thể bỏ qua bước này.

## <a name="import-data-into-adobe-campaign-standard"></a>Nhập dữ liệu vào Adobe Campaign Standard

Bây giờ mọi thứ đã sẵn sàng, chúng tôi cần nhập dữ liệu đối tượng đã chuẩn bị từ thông tin chi tiết về đối tượng vào Adobe Campaign Standard để tạo hồ sơ. Tìm hiểu [cách nhập hồ sơ trong Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) bằng quy trình làm việc.

Quy trình nhập trong hình ảnh bên dưới đã được định cấu hình để chạy 8 giờ một lần và tìm kiếm các phân khúc thông tin chi tiết về đối tượng được xuất (tệp .csv trong Azure Blob Storage). Dòng công việc trích xuất nội dung tệp .csv theo thứ tự cột được chỉ định. Quy trình làm việc này đã được xây dựng để thực hiện xử lý lỗi cơ bản và đảm bảo rằng mỗi bản ghi đều có địa chỉ email trước khi cung cấp dữ liệu trong Adobe Campaign Standard. Dòng công việc cũng trích xuất tên phân khúc từ tên tệp trước khi bổ sung vào dữ liệu Hồ sơ ACS.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Ảnh chụp màn hình quy trình nhập trong giao diện người dùng Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Truy xuất đối tượng trong Adobe Campaign Standard

Sau khi dữ liệu được nhập vào Adobe Campaign Standard, bạn [có thể tạo quy trình là việc](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) và [truy vấn](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) khách hàng dựa trên *Tên phân khúc* và *Ngày phân khúc* để chọn các hồ sơ đã được xác định cho chiến dịch mẫu của chúng tôi.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Tạo và gửi email bằng Adobe Campaign Standard

Tạo nội dung email rồi [thử nghiệm và gửi](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) email của bạn.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Email mẫu với đề nghị gia hạn từ Adobe Campaign Standard.":::