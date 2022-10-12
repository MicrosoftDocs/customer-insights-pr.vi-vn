---
title: Kết nối với một Power Query nguồn dữ liệu (chứa video)
description: Nhập dữ liệu thông qua Power Query trình kết nối (chứa video).
ms.date: 09/29/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: 4cc7e57dfb0f8d050e91adc441c24e849882f5d8
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609922"
---
# <a name="connect-to-a-power-query-data-source"></a>Kết nối với một Power Query nguồn dữ liệu

Power Query cung cấp một loạt các trình kết nối để nhập dữ liệu. Hầu hết các trình kết nối này được hỗ trợ bởi Dynamics 365 Customer Insights.

Thêm nguồn dữ liệu dựa trên Power Query trình kết nối thường tuân theo các bước được nêu trong phần này. Tuy nhiên, tùy thuộc vào trình kết nối bạn sử dụng, bạn sẽ cần dùng thông tin khác nhau. Để tìm hiểu thêm, hãy xem tài liệu về các trình kết nối riêng lẻ trong [Power Query tham chiếu trình kết nối](/power-query/connectors/).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>Tạo một nguồn dữ liệu mới

1. Chuyển tới **Dữ liệu** > **Nguồn dữ liệu**.

1. Chọn **Thêm nguồn dữ liệu**.

1. Chọn **Microsoft Power Query**.

1. Cung cấp một **Tên** và một tùy chọn **Sự mô tả** cho nguồn dữ liệu và chọn **Tiếp theo**.

1. Chọn một trong các [trình kết nối có sẵn](#available-power-query-data-sources). Trong ví dụ này, chúng tôi chọn **Văn bản / CSV** kết nối.

1. Nhập các chi tiết được yêu cầu trong **Cài đặt kết nối** cho trình kết nối đã chọn và chọn **Tiếp theo** để xem bản xem trước của dữ liệu.

1. Chọn **Chuyển đổi dữ liệu**.

1. Xem xét và tinh chỉnh dữ liệu của bạn trong **Power Query - Chỉnh sửa các truy vấn** trang. Các thực thể mà các hệ thống được xác định trong nguồn dữ liệu đã chọn của bạn xuất hiện trong ngăn bên trái.

   :::image type="content" source="media/data-manager-configure-edit-queries.png" alt-text="Hộp thoại Chỉnh sửa truy vấn":::

1. Chuyển đổi dữ liệu của bạn. Chọn một thực thể để chỉnh sửa hoặc chuyển đổi. Sử dụng các tùy chọn trong Power Query cửa sổ để áp dụng các phép biến đổi. Mỗi biến đổi được liệt kê dưới **Các bước đã áp dụng**. Power Query cung cấp nhiều [chuyển đổi được xây dựng trước](/power-query/power-query-what-is-power-query#transformations) tùy chọn.

   > [!IMPORTANT]
   > Chúng tôi khuyên bạn nên sử dụng các biến đổi sau:
   >
   > - Nếu bạn đang nhập dữ liệu từ tệp CSV, hàng đầu tiên thường chứa các tiêu đề. Đi đến **Biến đổi** và chọn **Sử dụng hàng đầu tiên làm tiêu đề**.
   > - Đảm bảo kiểu dữ liệu được đặt phù hợp và khớp với dữ liệu. Ví dụ: đối với các trường ngày, hãy chọn một loại ngày.

1. Để thêm các thực thể bổ sung vào nguồn dữ liệu của bạn trong **Chỉnh sửa truy vấn** hộp thoại, đi tới **Nhà** và chọn **Lấy dữ liệu**. Lặp lại các bước 5-10 cho đến khi bạn đã thêm tất cả các thực thể cho nguồn dữ liệu này. Nếu bạn có một cơ sở dữ liệu bao gồm nhiều bộ dữ liệu, mỗi bộ dữ liệu là thực thể riêng của nó.

1. Chọn **Lưu.** Các **Nguồn dữ liệu** trang mở ra hiển thị nguồn dữ liệu mới trong **Làm mới** trạng thái.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Quá trình tải dữ liệu có thể mất một khoảng thời gian. Sau khi làm mới thành công, dữ liệu đã nhập có thể được xem xét từ [**Thực thể**](entities.md) trang.

> [!CAUTION]
>
> - Nguồn dữ liệu dựa trên Power Query tạo ra một [luồng dữ liệu trong Dataverse](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365). Không thay đổi tên của luồng dữ liệu trong Power Platform trung tâm quản trị được sử dụng trong Thông tin chi tiết về khách hàng. Đổi tên luồng dữ liệu gây ra sự cố với các tham chiếu giữa Thông tin chi tiết về khách hàng nguồn dữ liệu và Dataverse dòng dữ liệu.
> - Đánh giá đồng thời cho Power Query các nguồn dữ liệu trong Thông tin chi tiết về khách hàng có cùng [làm mới các giới hạn như Dataflows trong PowerBI.com](/power-query/power-query-online-limits#refresh-limits). Nếu quá trình làm mới dữ liệu không thành công vì đã đạt đến giới hạn đánh giá, chúng tôi khuyên bạn nên điều chỉnh lịch làm mới cho từng luồng dữ liệu để đảm bảo các nguồn dữ liệu không được xử lý cùng một lúc.

### <a name="available-power-query-data-sources"></a>Có sẵn Power Query nguồn dữ liệu

Xem [Power Query tham chiếu kết nối](/power-query/connectors/) để có danh sách các trình kết nối mà bạn có thể sử dụng để nhập dữ liệu vào Thông tin chi tiết về khách hàng.

Các trình kết nối có dấu kiểm trong **Thông tin chi tiết về khách hàng (Luồng dữ liệu)** cột có sẵn để tạo nguồn dữ liệu mới dựa trên Power Query. Xem lại tài liệu của một trình kết nối cụ thể để tìm hiểu thêm về các điều kiện tiên quyết của nó, [giới hạn truy vấn](/power-query/power-query-online-limits) và các chi tiết khác.

## <a name="add-data-from-on-premises-data-sources"></a>Thêm dữ liệu từ nguồn dữ liệu tại chỗ

Việc thay đổi dữ liệu từ nguồn dữ liệu tại chỗ được hỗ trợ dựa trên Microsoft Power Platform luồng dữ liệu (PPDF). Bạn có thể bật luồng dữ liệu trong Thông tin chi tiết về khách hàng bằng cách [cung cấp Microsoft Dataverse URL môi trường](create-environment.md) khi thiết lập môi trường.

Nguồn dữ liệu được tạo sau khi liên kết Dataverse môi trường sử dụng Thông tin chi tiết về khách hàng [Power Platform luồng dữ liệu](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) theo mặc định. Luồng dữ liệu hỗ trợ kết nối tại chỗ bằng cách sử dụng cổng dữ liệu. Bạn có thể xóa và tạo lại các nguồn dữ liệu đã tồn tại trước Dataverse môi trường được liên kết [bằng cách sử dụng cổng dữ liệu tại chỗ](/data-integration/gateway/service-gateway-app).

Cổng dữ liệu từ một cổng hiện có Power BI hoặc Power Apps môi trường sẽ hiển thị và bạn có thể sử dụng lại chúng trong Thông tin chi tiết về khách hàng nếu cổng dữ liệu và môi trường Thông tin chi tiết về khách hàng ở cùng Vùng Azure. Trang nguồn dữ liệu hiển thị các liên kết đi đến môi trường Microsoft Power Platform nơi bạn có thể xem và định cấu hình cổng dữ liệu tại chỗ.

> [!IMPORTANT]
> Đảm bảo rằng các cổng của bạn được cập nhật lên phiên bản mới nhất. Bạn có thể cài đặt bản cập nhật và định cấu hình lại cổng từ lời nhắc hiển thị trực tiếp trên màn hình cổng hoặc [tải xuống phiên bản mới nhất](https://powerapps.microsoft.com/downloads/). Nếu bạn không sử dụng phiên bản cổng mới nhất, quá trình làm mới luồng dữ liệu không thành công với các thông báo lỗi như **Từ khóa không được hỗ trợ: thuộc tính cấu hình. Tên tham số: từ khóa**.
>
> Lỗi với cổng dữ liệu tại chỗ trong Thông tin chi tiết về khách hàng thường do sự cố cấu hình gây ra. Để biết thêm thông tin về cách khắc phục sự cố cổng dữ liệu, hãy xem [Khắc phục sự cố cổng dữ liệu tại chỗ](/data-integration/gateway/service-gateway-tshoot).

## <a name="edit-power-query-data-sources"></a>Chỉnh sửa Power Query nguồn dữ liệu

> [!NOTE]
> Có thể không thực hiện được các thay đổi đối với nguồn dữ liệu hiện đang được sử dụng trong một trong các quy trình của ứng dụng (ví dụ: phân đoạn hoặc hợp nhất dữ liệu).
>
> Bên trong **Cài đặt**, bạn có thể theo dõi tiến trình của từng quy trình đang hoạt động. Khi một quá trình hoàn tất, bạn có thể quay lại trang **Nguồn dữ liệu** và thực hiện các thay đổi của bạn.

1. Chuyển tới **Dữ liệu** > **Nguồn dữ liệu**.

1. Bên cạnh nguồn dữ liệu bạn muốn cập nhật, hãy chọn **Chỉnh sửa**.

1. Áp dụng các thay đổi và chuyển đổi của bạn trong **Power Query - Chỉnh sửa các truy vấn** hộp thoại như được mô tả trong [Tạo nguồn dữ liệu mới](#create-a-new-data-source) tiết diện.

1. Lựa chọn **Tiết kiệm** để áp dụng các thay đổi của bạn và quay lại **Nguồn dữ liệu** trang.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="common-reasons-for-ingestion-errors-or-corrupt-data"></a>Các lý do phổ biến gây ra lỗi nhập hoặc dữ liệu bị hỏng

### <a name="data-type-does-not-match-data"></a>Loại dữ liệu không khớp với dữ liệu

Loại dữ liệu không khớp phổ biến nhất xảy ra khi trường ngày không được đặt thành định dạng ngày chính xác.

Dữ liệu có thể được sửa tại nguồn và được nhập lại. Hoặc khắc phục sự thay đổi trong Thông tin chi tiết về khách hàng. Để khắc phục sự biến đổi:

1. Chuyển tới **Dữ liệu** > **Nguồn dữ liệu**.

1. Bên cạnh nguồn dữ liệu có dữ liệu bị hỏng, hãy chọn **Chỉnh sửa**.

1. Chọn **Tiếp theo**.

1. Chọn từng truy vấn và tìm các biến đổi được áp dụng bên trong "Các bước được áp dụng" không chính xác hoặc các cột ngày chưa được chuyển đổi với định dạng ngày.

   :::image type="content" source="media/PQ_corruped_date.png" alt-text="Power Query- Chỉnh sửa hiển thị định dạng ngày không chính xác":::

1. Thay đổi kiểu dữ liệu để khớp chính xác với dữ liệu.

1. Chọn **Lưu.** Nguồn dữ liệu đó đã được làm mới.

## <a name="troubleshoot-ppdf-power-query-based-data-source-refresh-issues"></a>Khắc phục sự cố PPDF Power Query vấn đề làm mới -based nguồn dữ liệu

Nếu dữ liệu cũ hoặc bạn nhận được lỗi sau khi làm mới nguồn dữ liệu, hãy thực hiện các bước sau:

1. Điều hướng tới [Power Platform](https://make.powerapps.com)

1. Chọn **Môi trường** cho ví dụ về Thông tin chi tiết về khách hàng của bạn.

1. Hướng đến **Luồng dữ liệu**.

1. Đối với luồng dữ liệu tương ứng với nguồn dữ liệu trong Thông tin chi tiết về khách hàng, hãy chọn dấu ba chấm dọc (&vellip;) và sau đó chọn **Hiển thị lịch sử làm mới**.

1. Nếu **Trạng thái** của luồng dữ liệu là **Thành công**, quyền sở hữu của Power Query -based nguồn dữ liệu có thể đã thay đổi:

   1. Xem lại lịch trình làm mới từ lịch sử làm mới.
   1. Đặt lịch của chủ sở hữu mới và lưu cài đặt.

1. Nếu **Trạng thái** của luồng dữ liệu là **Thất bại**:

   1. Tải xuống tệp lịch sử làm mới.
   1. Xem lại tệp đã tải xuống để biết lý do lỗi.
   1. Nếu lỗi không thể được giải quyết, hãy chọn **?** để mở một phiếu hỗ trợ. Bao gồm tệp lịch sử làm mới đã tải xuống.


[!INCLUDE [footer-include](includes/footer-banner.md)]
