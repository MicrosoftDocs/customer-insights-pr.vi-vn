---
title: Xuất dữ liệu Customer Insights vào nền tảng trải nghiệm Adobe
description: Tìm hiểu cách sử dụng phân khúc thông tin chi tiết về đối tượng trong Nền tảng trải nghiệm Adobe.
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: d1856861562be55c6d1d051050fe965560fa42f8
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596295"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a>Sử dụng phân khúc Customer Insights trong nền tảng trải nghiệm Adobe (xem trước)

Là người dùng thông tin chi tiết đối tượng trong Dynamics 365 Customer Insights, bạn có thể đã tạo các phân khúc để chiến dịch tiếp thị trở nên hiệu quả hơn bằng cách nhắm mục tiêu các đối tượng phù hợp. Để sử dụng phân khúc từ thông tin chi tiết đối tượng trong Nền tảng trải nghiệm Adobe và các ứng dụng như Adobe Campaign Standard, bạn cần làm theo một vài bước nêu trong bài viết này.

:::image type="content" source="media/AEP-flow.png" alt-text="Sơ đồ quy trình các bước nêu trong bài viết này.":::

## <a name="prerequisites"></a>Điều kiện tiên quyết

-   Giấy phép Dynamics 365 Customer Insights
-   Giấy phép Nền tảng Trải nghiệm Adobe
-   Giấy phép Adobe Campaign Standard
-   Tài khoản lưu trữ Azure Blob

## <a name="campaign-overview"></a>Tổng quan Chiến dịch

Để hiểu rõ hơn về cách bạn có thể sử dụng các phân khúc từ thông tin chi tiết về đối tượng trong Nền tảng trải nghiệm Adobe, hãy xem một chiến dịch mẫu giả tưởng.

Giả sử rằng công ty của bạn cung cấp dịch vụ dựa trên đăng ký hàng tháng cho khách hàng của bạn ở Hoa Kỳ. Bạn muốn xác định những khách hàng có đăng ký sẽ đến hạn gia hạn trong 8 ngày tới nhưng chưa gia hạn đăng ký của họ. Để giữ chân những khách hàng này, bạn nên gửi khuyến mại cho họ qua email, sử dụng Nền tảng trải nghiệm Adobe.

Trong ví dụ này, chúng tôi muốn chạy chiến dịch email quảng cáo một lần. Bài viết này không đề cập đến trường hợp sử dụng của việc chạy chiến dịch nhiều lần.

## <a name="identify-your-target-audience"></a>Xác định đối tượng mục tiêu của bạn

Trong kịch bản của chúng tôi, chúng tôi giả định rằng địa chỉ email của khách hàng có sẵn trong thông tin chi tiết về đối tượng và các sở thích khuyến mại của họ đã được phân tích để xác định các thành viên của phân khúc.

[Phân khúc bạn đã xác định trong thông tin chi tiết về đối tượng](segments.md) được gọi là **ChurnProneCustomers** và bạn dự định gửi những khách hàng này ưu đãi qua email.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Ảnh chụp màn hình của trang phân khúc đã tạo phân khúc ChurnProneCustomers.":::

Email ưu đãi mà bạn muốn gửi sẽ chứa tên, họ, và ngày kết thúc đăng ký của khách hàng. Email đó thông báo cho khách hàng về khoản chiết khấu mà họ sẽ nhận được nếu họ gia hạn đăng ký trước khi nó kết thúc.

## <a name="export-your-target-audience"></a>Xuất đối tượng mục tiêu của bạn

Với đối tượng mục tiêu đã được xác định, chúng tôi có thể định cấu hình xuất từ thông tin chi tiết về đối tượng sang tài khoản Lưu trữ Azure Blob.

1. Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Quản trị viên** > **Nơi xuất đích**.

1. Trong ngăn xếp **Lưu trữ Azure Blob**, chọn **Thiết lập**.

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Ngăn xếp cấu hình cho Lưu trữ Azure Blob.":::

1. Cung cấp **Tên hiển thị** cho đích xuất mới này rồi nhập **Tên tài khoản**, **Khóa tài khoản** và **Vùng chứa** của tài khoản Lưu trữ Azure Blob nơi bạn muốn xuất phân khúc.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Ảnh chụp màn hình cấu hình tài khoản lưu trữ. "::: 

   - Để biết cách tìm tên tài khoản và mã tài khoản Azure Blob Storage, hãy xem [Quản lý tùy chọn cài đặt của tài khoản lưu trữ trong cổng Azure](/azure/storage/common/storage-account-manage).

   - Để tìm hiểu cách tạo bộ chứa, hãy xem [Tạo bộ chứa](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Chọn **Tiếp theo**.

1. Chọn phân khúc mà bạn muốn xuất. Trong ví dụ này, phân khúc đó là **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Ảnh chụp màn hình giao diện người dùng chọn phân phúc đã chọn phân khúc ChurnProneCustomers.":::

1. Chọn **Lưu**.

Sau khi lưu đích xuất, bạn sẽ tìm thấy trên **Quản trị** > **Xuất** > **Đích xuất**.

:::image type="content" source="media/export-destination-azure-blob-storage.png" alt-text="Ảnh chụp màn hình với danh sách các mục xuất và phân khúc mẫu được đánh dấu.":::

Bây giờ, bạn có thể [xuất phân khúc theo yêu cầu](export-destinations.md#export-data-on-demand). Mỗi lần [làm mới theo lịch](system.md), tác vụ xuất cũng sẽ chạy.

> [!NOTE]
> Đảm bảo rằng số lượng bản ghi trong phân khúc đã xuất nằm trong giới hạn cho phép của giấy phép Adobe Campaign Standard.

Dữ liệu đã xuất được lưu trữ trong vùng chứa Azure Blob mà bạn đã định cấu hình ở trên. Đường dẫn thư mục sau được tạo tự động trong vùng chứa của bạn:

*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

Ví dụ: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

*model.json* cho các thực thể đã xuất có ở cấp độ *%ExportDestinationName%*.

Ví dụ: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>Xác định mô hình dữ liệu trải nghiệm Experience Data Model (XDM) trong Nền tảng trải nghiệm Adobe

Trước khi dữ liệu đã xuất từ audience insights có thể được dùng với Nền tảng trải nghiệm Adobe, chúng ta cần xác định lược đồ Mô hình dữ liệu trải nghiệm và [định cấu hình dữ liệu cho Hồ sơ khách hàng trong thời gian thực](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).

Tìm hiểu [XDM là gì](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) và hiểu [thông tin cơ bản về thành phần lược đồ](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).

## <a name="import-data-into-adobe-experience-platform"></a>Nhập dữ liệu vào Nền tảng Trải nghiệm Adobe

Bây giờ mọi thứ đã sẵn sàng, chúng tôi cần nhập dữ liệu đối tượng đã chuẩn bị từ thông tin chi tiết về đối tượng vào Nền tảng trải nghiệm Adobe.

Đầu tiên, [tạo kết nối nguồn lưu trữ Azure Blob](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).    

Sau khi xác định kết nối nguồn, hãy [định cấu hình luồng dữ liệu](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) cho kết nối loạt lưu trữ đám mây để nhập kết quả phân khúc từ thông tin chi tiết về đối tượng vào Nền tảng trải nghiệm Adobe.

## <a name="create-an-audience-in-adobe-campaign-standard"></a>Tạo đối tượng trong Adobe Campaign Standard

Để gửi email cho chiến dịch này, chúng tôi sẽ sử dụng Adobe Campaign Standard. Sau khi nhập dữ liệu vào Nền tảng trải nghiệm Adobe, chúng ta cần [tạo đối tượng](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) trong Adobe Campaign Standard bằng dữ liệu trong Nền tảng trải nghiệm Adobe.

Tìm hiểu cách [sử dụng trình tạo phân phúc](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) trong Adobe Campaign Standard để xác định đối tượng dựa trên dữ liệu trong Nền tảng trải nghiệm Adobe.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Tạo và gửi email bằng Adobe Campaign Standard

Tạo nội dung email rồi [thử nghiệm và gửi](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) email của bạn.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Email mẫu với đề nghị gia hạn từ Adobe Campaign Standard.":::