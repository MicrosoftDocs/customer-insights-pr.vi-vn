---
title: Xuất phân đoạn Thông tin chi tiết về khách hàng sang Adobe Tiêu chuẩn Chiến dịch (xem trước)
description: Tìm hiểu cách sử dụng phân đoạn Thông tin chi tiết về khách hàng trong Adobe Tiêu chuẩn Chiến dịch.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 834880cac9c5023157983081ff2513d9b051491f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195546"
---
# <a name="export-customer-insights-segments-to-adobe-campaign-standard-preview"></a>Xuất phân đoạn Thông tin chi tiết về khách hàng sang Adobe Tiêu chuẩn Chiến dịch (xem trước)

Xuất các phân đoạn nhắm mục tiêu đến các đối tượng có liên quan sang Adobe Tiêu chuẩn Chiến dịch.

:::image type="content" source="media/ACS-flow.png" alt-text="Sơ đồ quy trình các bước nêu trong bài viết này.":::

## <a name="prerequisites"></a>Điều kiện tiên quyết

- Một Adobe Giấy phép Chiến dịch Chuẩn.
- Một [Tài khoản lưu trữ Azure Blob](/azure/storage/blobs/create-data-lake-storage-account) tên và khóa tài khoản. Để tìm tên và khóa, hãy xem [Quản lý cài đặt tài khoản lưu trữ trong cổng Azure](/azure/storage/common/storage-account-manage).
- Một [Hộp chứa Azure Blob Storage](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="campaign-overview"></a>Tổng quan về chiến dịch

Để hiểu rõ hơn về cách bạn có thể sử dụng các phân đoạn từ Thông tin chi tiết về khách hàng trong Adobe Experience Platform, hãy xem một chiến dịch mẫu giả tưởng.

Giả sử rằng công ty của bạn cung cấp dịch vụ dựa trên đăng ký hàng tháng cho khách hàng của bạn ở Hoa Kỳ. Bạn muốn xác định những khách hàng có đăng ký sẽ đến hạn gia hạn trong 8 ngày tới nhưng chưa gia hạn đăng ký của họ. Để giữ chân những khách hàng này, bạn cần gửi cho họ một ưu đãi khuyến mại qua email, sử dụng Adobe Campaign Standard.

Trong ví dụ này, chúng tôi muốn chạy chiến dịch email quảng cáo một lần. Bài viết này không đề cập đến trường hợp sử dụng của việc chạy chiến dịch nhiều lần. Tuy nhiên, Thông tin chi tiết về khách hàng và Adobe Tiêu chuẩn chiến dịch cũng có thể được định cấu hình để hoạt động cho một kịch bản chiến dịch lặp lại.

## <a name="identify-your-target-audience"></a>Xác định đối tượng mục tiêu của bạn

Trong kịch bản của chúng tôi, chúng tôi giả định rằng địa chỉ email của khách hàng có sẵn trong Thông tin chi tiết về khách hàng và các sở thích khuyến mại của họ đã được phân tích để xác định các thành viên của phân khúc.

Các [phân đoạn bạn đã xác định trong Thông tin chi tiết về khách hàng](segments.md) được gọi là **ChurnProneCustomers** và bạn dự định gửi cho những khách hàng này chương trình khuyến mãi qua email.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Ảnh chụp màn hình của trang phân khúc đã tạo phân khúc ChurnProneCustomers.":::

Email ưu đãi mà bạn muốn gửi sẽ chứa tên, họ, và ngày kết thúc đăng ký của khách hàng. Email đó thông báo cho khách hàng về khoản chiết khấu mà họ sẽ nhận được nếu họ gia hạn đăng ký trước khi nó kết thúc.

## <a name="export-your-target-audience"></a>Xuất đối tượng mục tiêu của bạn

### <a name="set-up-connection-to-adobe-campaign"></a>Thiết lập kết nối với Adobe Chiến dịch

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Đi đến **Quản trị viên** > **Kết nối**.

1. Lựa chọn **Thêm kết nối** và lựa chọn **Adobe Chiến dịch**.

1. Đặt tên dễ nhận biết cho kết nối trong trường **Tên hiển thị**. Tên và loại kết nối mô tả kết nối này. Bạn nên chọn một tên giải thích mục đích và mục tiêu của kết nối.

1. Chọn người có thể sử dụng kết nối này. Theo mặc định, giá trị này là quản trị viên. Để biết thêm thông tin, hãy xem [Cho phép người đóng góp sử dụng một kết nối cho các lần xuất](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Nhập **Tên tài khoản**, **khóa tài khoản**, và **Thùng đựng hàng** cho tài khoản Blob Storage của bạn.  

   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Ảnh chụp màn hình cấu hình tài khoản lưu trữ. ":::

1. Xem lại [quyền riêng tư và tuân thủ dữ liệu](connections.md#data-privacy-and-compliance) và chọn **tôi đồng ý**.

1. Chọn **Lưu** để hoàn thành kết nối.

### <a name="configure-an-export"></a>Định cấu hình xuất

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Đi tới **Dữ liệu** > **Nội dung xuất**.

1. Lựa chọn **Thêm xuất khẩu**.

1. Trong trường **Kết nối để xuất**, hãy chọn một kết nối từ phần Adobe Campaign. Liên hệ với quản trị viên nếu không có kết nối.

1. Nhập tên cho lần xuất.

1. Chọn phân khúc mà bạn muốn xuất. Trong ví dụ này, phân khúc đó là **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Ảnh chụp màn hình giao diện người dùng chọn phân phúc đã chọn phân khúc ChurnProneCustomers.":::

1. Chọn **Tiếp theo**.

1. Lập bản đồ **Nguồn** từ phân đoạn Thông tin chi tiết về khách hàng đến **Mục tiêu** tên trường trong Adobe Lược đồ cấu hình Tiêu chuẩn của Chiến dịch.

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Ánh xạ trường cho trình kết nối Adobe Campaign Standard.":::

   Nếu bạn muốn thêm nhiều thuộc tính, hãy chọn **Thêm thuộc tính**. Tên mục tiêu có thể khác với tên trường nguồn để bạn vẫn có thể ánh xạ đầu ra của phân đoạn từ Thông tin chi tiết về khách hàng đến Adobe Tiêu chuẩn Chiến dịch nếu các trường không có cùng tên trong hai hệ thống.

   > [!NOTE]
   > Địa chỉ email được sử dụng làm trường nhận dạng, nhưng bạn có thể sử dụng bất kỳ số nhận dạng nào khác từ hồ sơ khách hàng để ánh xạ dữ liệu tới Adobe Tiêu chuẩn Chiến dịch.

1. Chọn **Lưu.**

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!NOTE]
> Đảm bảo rằng số lượng bản ghi trong phân đoạn đã xuất nằm trong giới hạn cho phép của giấy phép Adobe Campaign Standard.

Dữ liệu đã xuất được lưu trữ trong vùng chứa Azure Blob Storage mà bạn đã định cấu hình ở trên. Đường dẫn thư mục sau được tạo tự động trong vùng chứa của bạn: *%ContainerName% /Thấu hiểu khách hàng_%instanceID% /% exportdestination-name%_%segmentname%_%timestamp% .csv*

Ví dụ: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Định cấu hình Adobe Campaign Standard

Các phân đoạn đã xuất chứa các cột bạn đã chọn trong khi định cấu hình xuất. Dữ liệu này có thể được sử dụng để [tạo hồ sơ trong Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).

Để sử dụng phân đoạn trong Adobe Tiêu chuẩn Chiến dịch, [mở rộng lược đồ hồ sơ](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) Trong Adobe Tiêu chuẩn Chiến dịch để bao gồm hai trường bổ sung.

Trong ví dụ của chúng tôi, các trường này là Tên phân đoạn và Ngày phân đoạn. Chúng tôi sẽ sử dụng những trường này để xác định các hồ sơ trong Adobe Campaign Standard mà chúng tôi muốn nhắm mục tiêu cho chiến dịch này.

Nếu không có hồ sơ nào khác trong Adobe Chiến dịch Chuẩn, ngoài những gì bạn sẽ nhập, hãy bỏ qua bước này.

## <a name="import-data-into-adobe-campaign-standard"></a>Nhập dữ liệu vào Adobe Campaign Standard

Nhập dữ liệu đối tượng đã chuẩn bị từ Thông tin chi tiết về khách hàng vào Adobe Tiêu chuẩn Chiến dịch để [tạo hồ sơ bằng quy trình làm việc](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences).

Quy trình nhập trong hình ảnh bên dưới đã được định cấu hình để chạy tám giờ một lần và tìm kiếm các phân đoạn Thông tin chi tiết về khách hàng đã xuất (tệp .csv trong Azure Blob Storage). Quy trình này trích xuất nội dung tệp .csv theo thứ tự cột được chỉ định. Quy trình làm việc này đã được xây dựng để thực hiện xử lý lỗi cơ bản và đảm bảo rằng mỗi hồ sơ có một địa chỉ email trước khi cung cấp dữ liệu trong Adobe Campaign Standard. Quy trình này cũng trích xuất tên phân đoạn từ tên tệp trước khi bổ sung vào dữ liệu hồ sơ Adobe Campaign Standard.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Ảnh chụp màn hình quy trình nhập trong giao diện người dùng Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Thu hút đối tượng trong Adobe Campaign Standard

Sau khi dữ liệu được nhập vào Adobe Tiêu chuẩn Chiến dịch, [tạo quy trình làm việc](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) và [truy vấn](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) khách hàng dựa trên Tên phân đoạn và Ngày phân đoạn để chọn các cấu hình đã được xác định cho chiến dịch mẫu của chúng tôi.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Tạo và gửi email bằng Adobe Campaign Standard

Tạo nội dung email rồi [thử nghiệm và gửi](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) email của bạn.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Email mẫu với ưu đãi gia hạn từ Adobe Campaign Standard.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
