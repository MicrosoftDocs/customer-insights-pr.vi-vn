---
title: Xuất phân đoạn sang Adobe Experience Platform (xem trước)
description: Tìm hiểu cách sử dụng phân đoạn Thông tin chi tiết về khách hàng trong Adobe Experience Platform.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: c29b8264019669ffd954a298ce3a633c852477fa
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 06/29/2022
ms.locfileid: "9052537"
---
# <a name="export-segments-to-adobe-experience-platform-preview"></a>Xuất phân đoạn sang Adobe Experience Platform (xem trước)

Với tư cách là người dùng của Dynamics 365 Customer Insights, bạn có thể đã tạo các phân đoạn để làm cho các chiến dịch tiếp thị của mình hiệu quả hơn bằng cách nhắm mục tiêu các đối tượng có liên quan. Để sử dụng một phân đoạn từ Thông tin chi tiết về khách hàng trong Adobe Experience Platform và các ứng dụng như Adobe Tiêu chuẩn Chiến dịch, bạn cần thực hiện theo một số bước được nêu trong bài viết này.

:::image type="content" source="media/AEP-flow.png" alt-text="Sơ đồ quy trình các bước nêu trong bài viết này.":::

## <a name="prerequisites"></a>Điều kiện tiên quyết

-   Giấy phép Dynamics 365 Customer Insights
-   Giấy phép Adobe Experience Platform
-   Giấy phép Adobe Campaign Standard
-   Tài khoản Azure Blob Storage

## <a name="campaign-overview"></a>Tổng quan về chiến dịch

Để hiểu rõ hơn về cách bạn có thể sử dụng các phân đoạn từ Thông tin chi tiết về khách hàng trong Adobe Experience Platform, hãy xem một chiến dịch mẫu giả tưởng.

Giả sử rằng công ty của bạn cung cấp dịch vụ dựa trên đăng ký hàng tháng cho khách hàng của bạn ở Hoa Kỳ. Bạn muốn xác định những khách hàng có đăng ký sẽ đến hạn gia hạn trong 8 ngày tới nhưng chưa gia hạn đăng ký của họ. Để giữ chân những khách hàng này, bạn cần gửi cho họ một ưu đãi khuyến mại qua email, sử dụng Adobe Experience Platform.

Trong ví dụ này, chúng tôi muốn chạy chiến dịch email quảng cáo một lần. Bài viết này không đề cập đến trường hợp sử dụng của việc chạy chiến dịch nhiều lần.

## <a name="identify-your-target-audience"></a>Xác định đối tượng mục tiêu của bạn

Trong kịch bản của chúng tôi, chúng tôi giả định rằng địa chỉ email của khách hàng có sẵn trong Thông tin chi tiết về khách hàng và các sở thích khuyến mại của họ đã được phân tích để xác định các thành viên của phân khúc.

Các [phân đoạn bạn đã xác định trong Thông tin chi tiết về khách hàng](segments.md) được gọi là **ChurnProneCustomers** và bạn có kế hoạch gửi email quảng cáo cho những khách hàng này.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Ảnh chụp màn hình của trang phân khúc đã tạo phân khúc ChurnProneCustomers.":::

Email ưu đãi mà bạn muốn gửi sẽ chứa tên, họ, và ngày kết thúc đăng ký của khách hàng. Email đó thông báo cho khách hàng về khoản chiết khấu mà họ sẽ nhận được nếu họ gia hạn đăng ký trước khi nó kết thúc.

## <a name="export-your-target-audience"></a>Xuất đối tượng mục tiêu của bạn

Với đối tượng mục tiêu của chúng tôi đã được xác định, chúng tôi có thể định cấu hình xuất từ Thông tin chi tiết về khách hàng sang tài khoản Azure Blob Storage.

### <a name="configure-a-connection"></a>Định cấu hình kết nối

1. Đi đến **Quản trị viên** > **Kết nối**.

1. Chọn **Thêm kết nối** rồi chọn **Azure Blob Storage** hoặc chọn **Thiết lập** trong ngăn xếp **Azure Blob Storage** để định cấu hình kết nối.

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Ngăn xếp cấu hình cho Lưu trữ Azure Blob."::: 

1. Đặt tên dễ nhận biết cho kết nối trong trường **Tên hiển thị**. Tên và loại kết nối mô tả kết nối này. Bạn nên chọn một tên giải thích mục đích và mục tiêu của kết nối.

1. Chọn người có thể sử dụng kết nối này. Nếu bạn không thực hiện hành động nào, giá trị mặc định sẽ là Quản trị viên. Để biết thêm thông tin, hãy xem [Cho phép người đóng góp sử dụng một kết nối cho các lần xuất](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Nhập **Tên tài khoản**, **Khóa tài khoản** và **Vùng chứa** của tài khoản Blob Storage mà bạn muốn xuất phân khúc sang.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Ảnh chụp màn hình cấu hình tài khoản lưu trữ. "::: 
   
    - Để tìm hiểu thêm về cách tìm tên tài khoản Blob Storage và khóa tài khoản, hãy xem [Quản lý cài đặt tài khoản lưu trữ trong cổng thông tin Azure](/azure/storage/common/storage-account-manage).
    - Để tìm hiểu cách tạo vùng chứa, hãy xem [Tạo vùng chứa](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Chọn **Lưu** để hoàn thành kết nối. 

### <a name="configure-an-export"></a>Định cấu hình xuất

Bạn có thể định cấu hình lần xuất này nếu bạn có quyền truy cập vào kết nối thuộc loại này. Để biết thêm thông tin, hãy xem [Các quyền cần thiết để định cấu hình xuất](export-destinations.md#set-up-a-new-export).

1. Đi tới **Dữ liệu** > **Nội dung xuất**.

1. Để tạo nội dung xuất mới, hãy chọn **Thêm nội dung xuất**.

1. Trong trường **Kết nối để xuất**, hãy chọn một kết nối từ phần Azure Blob Storage. Nếu bạn không thấy tên phần này thì có nghĩa là không có kết nối nào thuộc loại này khả dụng cho bạn.

1. Chọn phân khúc mà bạn muốn xuất. Trong ví dụ này, phân khúc đó là **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Ảnh chụp màn hình giao diện người dùng chọn phân phúc đã chọn phân khúc ChurnProneCustomers.":::

1. Chọn **Lưu**.

Sau khi lưu đích xuất, bạn sẽ thấy đích này trên **Dữ liệu** > **Nội dung xuất**.

Bây giờ, bạn có thể [xuất phân khúc theo yêu cầu](export-destinations.md#run-exports-on-demand). Mỗi lần [làm mới theo lịch](system.md), tác vụ xuất cũng sẽ chạy.

> [!NOTE]
> Đảm bảo rằng số lượng bản ghi trong phân đoạn đã xuất nằm trong giới hạn cho phép của giấy phép Adobe Campaign Standard.

Dữ liệu đã xuất được lưu trữ trong vùng chứa Azure Blob Storage mà bạn đã định cấu hình ở trên. Đường dẫn thư mục sau được tạo tự động trong vùng chứa của bạn:

*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

Ví dụ: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

*model.json* cho các thực thể đã xuất có ở cấp độ *%ExportDestinationName%*.

Ví dụ: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>Xác định Experience Data Model (XDM) trong Adobe Experience Platform

Trước khi dữ liệu đã xuất từ Thông tin chi tiết về khách hàng có thể được sử dụng trong Adobe Experience Platform, chúng ta cần xác định lược đồ Mô hình dữ liệu trải nghiệm và [định cấu hình dữ liệu cho Hồ sơ khách hàng theo thời gian thực](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).

Tìm hiểu [XDM là gì](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) và hiểu [thông tin cơ bản về thành phần lược đồ](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).

## <a name="import-data-into-adobe-experience-platform"></a>Nhập dữ liệu vào Adobe Experience Platform

Bây giờ mọi thứ đã sẵn sàng, chúng tôi cần nhập dữ liệu đối tượng đã chuẩn bị từ Thông tin chi tiết về khách hàng vào Adobe Experience Platform.

Đầu tiên, [tạo kết nối nguồn lưu trữ Azure Blob](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).    

Sau khi xác định kết nối nguồn, [định cấu hình luồng dữ liệu](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) cho kết nối hàng loạt lưu trữ đám mây để nhập kết quả phân đoạn từ Thông tin chi tiết về khách hàng vào Adobe Experience Platform.

## <a name="create-an-audience-in-adobe-campaign-standard"></a>Tạo đối tượng trong Adobe Campaign Standard

Để gửi email cho chiến dịch này, chúng tôi sẽ sử dụng Adobe Campaign Standard. Sau khi nhập dữ liệu vào Adobe Experience Platform, chúng ta cần phải [tạo đối tượng](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) trong Adobe Campaign Standard sử dụng dữ liệu trong Adobe Experience Platform.


Tìm hiểu cách [sử dụng trình tạo phân đoạn](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) trong Adobe Campaign Standard để xác định đối tượng dựa trên dữ liệu trong Adobe Experience Platform.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Tạo và gửi email bằng Adobe Campaign Standard

Tạo nội dung email rồi [thử nghiệm và gửi](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) email của bạn.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Email mẫu với ưu đãi gia hạn từ Adobe Campaign Standard.":::
