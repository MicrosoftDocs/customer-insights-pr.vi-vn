---
title: Tổng quan về phân khúc
description: Tổng quan, cách tạo và quản lý phân khúc.
ms.date: 05/20/2022
ms.subservice: audience-insights
ms.topic: overview
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-customers-page
- ci-enrichment-details
- ci-segments
- ci-segment-details
- customerInsights
ms.openlocfilehash: 195a7c733f047c24f9f47a151c1cb623fe34d055
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246319"
---
# <a name="segments-overview"></a>Tổng quan về phân khúc

Phân khúc cho phép bạn nhóm khách hàng của mình dựa trên các thuộc tính nhân khẩu học, giao dịch hoặc hành vi. Bạn có thể sử dụng các phân khúc để nhắm mục tiêu chiến dịch quảng cáo, hoạt động bán hàng và hành động hỗ trợ khách hàng để đạt được mục tiêu kinh doanh.

Hồ sơ khách hàng phù hợp với các bộ lọc của định nghĩa phân khúc được gọi là *các thành viên* của một phân khúc. Một số [giới hạn dịch vụ](/dynamics365/customer-insights/service-limits) được áp dụng.

## <a name="create-a-segment"></a>Tạo phân khúc

Chọn cách tạo phân khúc dựa trên đối tượng mục tiêu của bạn.

# <a name="individual-consumers-b-to-c"></a>[Người tiêu dùng cá nhân (B2C)](#tab/b2c)

- Các phân đoạn phức tạp với trình tạo phân đoạn: [Xây dựng của riêng bạn](segment-builder.md)
- Các phân khúc đơn giản với một toán tử: [Phân khúc nhanh](segment-quick.md)
- Cách thức được hỗ trợ bởi AI để tìm những khách hàng tương tự: [Khách hàng tương tự](find-similar-customer-segments.md)
- Đề xuất do AI hỗ trợ dựa trên các biện pháp hoặc thuộc tính: [Các phân đoạn được đề xuất dựa trên các thước đo](suggested-segments.md)
- Đề xuất dựa trên các hoạt động: [Các phân khúc được đề xuất dựa trên hoạt động của khách hàng](suggested-segments-activity.md)

# <a name="business-accounts-b-to-b"></a>[Tài khoản doanh nghiệp (B2B)](#tab/b2b)

- Phân đoạn đơn giản hoặc phức tạp với trình tạo phân đoạn: [Xây dựng của riêng bạn](segment-builder.md)

---

## <a name="manage-existing-segments"></a>Quản lý các phân khúc hiện có

Đi đến **Phân đoạn** để xem các phân đoạn bạn đã tạo, trạng thái và trạng thái của chúng, số lượng thành viên và lần cuối cùng dữ liệu được làm mới. Bạn có thể sắp xếp danh sách các phân đoạn theo bất kỳ cột nào hoặc sử dụng hộp tìm kiếm để tìm phân đoạn bạn muốn quản lý.

Chọn một phân đoạn để xem các hành động có sẵn.

:::image type="content" source="media/segments-selected-segment.png" alt-text="Phân khúc đã chọn với danh sách tùy chọn thả xuống và các tùy chọn có sẵn." lightbox="media/segments-selected-segment.png":::

- [**Lượt xem**](#view-segment-details) chi tiết phân khúc, bao gồm xu hướng số lượng thành viên và bản xem trước của các thành viên phân khúc.
- **Tải xuống** danh sách thành viên dưới dạng tệp .CSV.
- **Chỉnh sửa** phân khúc để thay đổi các thuộc tính của phân khúc đó.
- **Tạo bản sao** của một phân khúc. Bạn có thể chọn chỉnh sửa các thuộc tính của nó ngay lập tức hoặc lưu bản sao.
- [**Làm mới**](#refresh-segments) phân đoạn để bao gồm dữ liệu mới nhất.
- **Kích hoạt** hoặc **Hủy kích hoạt** phân khúc. Các phân đoạn không hoạt động sẽ không được làm mới trong [làm mới theo lịch trình](schedule-refresh.md) và có **Trạng thái** được liệt kê là **Đã bỏ qua**, cho thấy rằng việc làm mới thậm chí còn chưa được thử. Các phân đoạn đang hoạt động được làm mới dựa trên loại của chúng: tĩnh hoặc động.
- **Tạo tĩnh** hoặc **Làm cho năng động** loại phân đoạn. Các phân đoạn tĩnh phải được làm mới theo cách thủ công. Các phân đoạn động được tự động làm mới trong quá trình làm mới hệ thống.
- [**Tìm khách hàng tương tự**](find-similar-customer-segments.md) khỏi phân khúc.
- **Đổi tên** phân khúc.
- **Nhãn** đến [quản lý thẻ](work-with-tags-columns.md#manage-tags) cho phân khúc.
- [**Quản lý xuất**](#export-segments) để xem các phân đoạn liên quan đến xuất khẩu và quản lý chúng. [Tìm hiểu thêm về nội dung xuất.](export-destinations.md)
- **Xóa** phân khúc.
- **Cột** đến [tùy chỉnh các cột](work-with-tags-columns.md#customize-columns) màn hình đó.
- **Lọc** đến [lọc trên các thẻ](work-with-tags-columns.md#filter-on-tags).
- **Tim kiêm tên** để tìm kiếm theo tên phân đoạn.

## <a name="view-segment-details"></a>Xem chi tiết phân đoạn

Trên **Phân đoạn**, chọn một phân đoạn để xem lịch sử xử lý và các thành viên phân đoạn.

Phần trên của trang bao gồm một biểu đồ xu hướng nhằm trực quan hóa những thay đổi về số lượng thành phần. Di chuột qua các điểm dữ liệu để xem số lượng thành phần trong một ngày cụ thể. Thay đổi khung thời gian của hình ảnh trực quan.

:::image type="content" source="media/segment-time-range.png" alt-text="Khoảng thời gian phân đoạn.":::

Phần dưới chứa danh sách các thành phần phân khúc.

> [!NOTE]
> Các trường xuất hiện trong danh sách này dựa trên các thuộc tính của các thực thể trong phân khúc của bạn.
>
>Danh sách này là bản xem trước của các thành phần phân khúc phù hợp và hiển thị 100 bản ghi đầu tiên của phân khúc, từ đó bạn có thể đánh giá nhanh và xem lại định nghĩa nếu cần. Để xem tất cả các bản ghi phù hợp, [xuất phân đoạn](export-destinations.md).

## <a name="refresh-segments"></a>Làm mới phân khúc

Các phân đoạn có thể được làm mới theo lịch trình tự động hoặc được làm mới theo cách thủ công theo yêu cầu. Để làm mới một hoặc nhiều phân đoạn theo cách thủ công, hãy chọn chúng và chọn **Làm mới**.

Đến [lên lịch làm mới tự động](schedule-refresh.md), đi đến **Quản trị viên** > **Hệ thống** > **Lịch trình**. Các quy tắc sau được áp dụng:

- Tất cả các phân đoạn với loại **Năng động** hoặc **Sự bành trướng** sẽ được tự động làm mới theo nhịp đã đặt. Khi quá trình làm mới hoàn tất, **Trạng thái** cho biết nếu có bất kỳ vấn đề nào khi làm mới phân đoạn. Các **Làm mới lần cuối** hiển thị dấu thời gian của lần làm mới thành công gần đây nhất. Nếu xảy ra lỗi, hãy chọn lỗi để xem chi tiết về những gì đã xảy ra.
- Phân đoạn có loại **Tĩnh** *sẽ không* được làm mới tự động. Các **Làm mới lần cuối** hiển thị dấu thời gian của lần cuối cùng phân khúc tĩnh được chạy hoặc làm mới theo cách thủ công.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="export-segments"></a>Xuất phân khúc

Xuất phân đoạn sang các ứng dụng khác để sử dụng thêm dữ liệu. Xuất một phân đoạn từ trang phân đoạn hoặc [trang xuất khẩu](export-destinations.md).

1. Đi đến **Phân đoạn** và chọn phân đoạn bạn muốn xuất.

1. Lựa chọn **Quản lý xuất**. Trang **Nội dung xuất (xem trước) cho phân khúc** sẽ mở ra. Xem tất cả các xuất đã định cấu hình được nhóm theo nhóm có chứa phân đoạn hiện tại hay không.

   1. Để thêm phân khúc đã chọn vào bản xuất, hãy **Chỉnh sửa** bản xuất tương ứng để chọn phân khúc tương ứng rồi lưu. Trong môi trường dành cho khách hàng cá nhân, hãy chọn xuất trong danh sách và chọn **Thêm phân đoạn** để đạt được cùng một kết quả.

   1. Để tạo nội dung xuất mới bằng phân khúc đã chọn, hãy chọn **Thêm nội dung xuất**. Để biết thêm thông tin về cách tạo nội dung xuất, hãy xem phần [Thiết lập nội dung xuất mới](export-destinations.md#set-up-a-new-export).

1. Chọn **Quay lại** để quay lại trang chính cho các phân khúc.

## <a name="track-usage-of-a-segment"></a>Theo dõi việc sử dụng một phân đoạn

Nếu bạn sử dụng các phân đoạn trong các ứng dụng dựa trên cùng một Microsoft Dataverse tổ chức được kết nối với Thông tin chi tiết về khách hàng, bạn có thể theo dõi việc sử dụng một phân khúc. Vì [Các phân đoạn Thông tin chi tiết về khách hàng được sử dụng trong hành trình của khách hàng của Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile), hệ thống thông báo cho bạn về việc sử dụng phân đoạn đó.

Khi chỉnh sửa phân đoạn đang được sử dụng trong môi trường Thông tin chi tiết về khách hàng hoặc trong hành trình của khách hàng trong Tiếp thị, một biểu ngữ trong [người xây dựng phân đoạn](segment-builder.md) thông báo cho bạn về các phụ thuộc. Kiểm tra chi tiết phụ thuộc trực tiếp từ biểu ngữ hoặc bằng cách chọn **Cách sử dụng** trong trình tạo phân đoạn.

Các **Sử dụng đoạn đường** ngăn hiển thị chi tiết về việc sử dụng phân đoạn này trong Dataverse ứng dụng dựa trên. Đối với các phân đoạn được sử dụng trong hành trình của khách hàng, bạn sẽ tìm thấy một liên kết để kiểm tra hành trình trong Tiếp thị nơi phân đoạn này được sử dụng. Nếu bạn có quyền truy cập ứng dụng Tiếp thị, hãy xem thêm chi tiết tại đó.

:::image type="content" source="media/segment-usage-pane.png" alt-text="Ngăn bên với các chi tiết về việc sử dụng phân đoạn trong trình tạo phân đoạn.":::

Hệ thống thông báo cho bạn về việc sử dụng phân đoạn được theo dõi khi bạn cố gắng xóa nó. Nếu phân khúc bạn sắp xóa được sử dụng trong hành trình của khách hàng trong Tiếp thị, hành trình đó sẽ dừng lại đối với tất cả người dùng trong phân khúc. Nếu hành trình là một phần của chiến dịch tiếp thị, việc xóa sẽ ảnh hưởng đến chính chiến dịch đó. Tuy nhiên, bạn vẫn có thể xóa phân đoạn bất chấp các cảnh báo.

:::image type="content" source="media/segment-usage-delete.png" alt-text="Hộp thoại để xác nhận xóa phân đoạn khi một phân đoạn được sử dụng trong Dataverse đăng kí.":::

### <a name="supported-apps"></a>Các ứng dụng được hỗ trợ

Việc sử dụng hiện được theo dõi như sau Dataverse ứng dụng dựa trên:

- [Hành trình của khách hàng trong Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile)

[!INCLUDE [footer-include](includes/footer-banner.md)]
