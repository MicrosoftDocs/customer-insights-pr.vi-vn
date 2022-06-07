---
title: Các phân đoạn trong Thông tin chi tiết về khách hàng
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
ms.openlocfilehash: d616ec8273115203dddb59334a348c66e72fa678
ms.sourcegitcommit: b515120bebd2638f2639004422cee3cff42fbdf7
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 05/24/2022
ms.locfileid: "8800768"
---
# <a name="segments-overview"></a>Tổng quan về phân khúc

Phân khúc cho phép bạn nhóm khách hàng của mình dựa trên các thuộc tính nhân khẩu học, giao dịch hoặc hành vi. Bạn có thể sử dụng các phân khúc để nhắm mục tiêu chiến dịch quảng cáo, hoạt động bán hàng và hành động hỗ trợ khách hàng để đạt được mục tiêu kinh doanh.

Hồ sơ khách hàng phù hợp với các bộ lọc của định nghĩa phân khúc được gọi là *các thành viên* của một phân khúc. Một số [giới hạn dịch vụ](/dynamics365/customer-insights/service-limits) được áp dụng.

## <a name="create-a-new-segment"></a>Tạo phân khúc mới

Có nhiều cách để tạo một phân khúc mới: 

# <a name="individual-consumers-b-to-c"></a>[Người tiêu dùng cá nhân (B2C)](#tab/b2c)

- Phân khúc phức tạp với trình dựng phân khúc [Tạo phân khúc của riêng bạn](segment-builder.md#create-a-new-segment) 
- Các phân khúc đơn giản với một toán tử: [Phân khúc nhanh](segment-builder.md#quick-segments) 
- Cách tìm khách hàng tương tự dựa trên AI: [Khách hàng tương tự](find-similar-customer-segments.md) 
- Đề xuất do AI hỗ trợ dựa trên các biện pháp hoặc thuộc tính: [Các phân khúc được đề xuất nhằm cải thiện các biện pháp](suggested-segments.md) 
- Đề xuất dựa trên các hoạt động: [Các phân khúc được đề xuất dựa trên hoạt động của khách hàng](suggested-segments-activity.md) 

# <a name="business-accounts-b-to-b"></a>[Tài khoản doanh nghiệp (B2B)](#tab/b2b)

- Phân khúc phức tạp với trình dựng phân khúc [Tạo phân khúc của riêng bạn](segment-builder.md#create-a-new-segment)

---

## <a name="manage-existing-segments"></a>Quản lý các phân khúc hiện có

Đi đến **Phân đoạn** để xem tất cả các phân đoạn đã lưu của bạn và quản lý chúng.

Mỗi phân khúc được đại diện bởi một hàng bao gồm thông tin bổ sung về phân khúc.

:::image type="content" source="media/segments-selected-segment.png" alt-text="Phân khúc đã chọn với danh sách tùy chọn thả xuống và các tùy chọn có sẵn." lightbox="media/segments-selected-segment.png":::

Các hành động sau đây khả dụng khi bạn chọn một phân đoạn:

- **Xem** chi tiết phân khúc, bao gồm xu hướng số lượng thành viên của một bản xem trước thành phần phân khúc.
- **Tải xuống** danh sách thành viên dưới dạng tệp .CSV.
- **Chỉnh sửa** phân khúc để thay đổi các thuộc tính của phân khúc đó.
- **Tạo bản sao** của một phân khúc. Bạn có thể chọn chỉnh sửa các thuộc tính của nó ngay lập tức hoặc lưu bản sao.
- **Làm mới** phân khúc để bao gồm dữ liệu mới nhất.
- **Kích hoạt** hoặc **Hủy kích hoạt** phân khúc. Đối với các phân khúc không hoạt động, định nghĩa phân khúc tồn tại nhưng phân khúc chưa chứa bất kỳ khách hàng nào. Một phân khúc đang hoạt động sẽ tìm kiếm những khách hàng phù hợp với định nghĩa phân khúc. Nếu hoạt động [làm mới theo lịch trình](system.md#schedule-tab) được định cấu hình thì các phân khúc không hoạt động sẽ có **Trạng thái** là **Đã bỏ qua**, biểu thị việc làm mới chưa được thực hiện. Khi phân khúc không hoạt động được kích hoạt, mục đó sẽ được làm mới và được đưa vào các lần làm mới theo lịch trình.
  Ngoài ra, bạn cũng có thể dùng chức năng **Lên lịch sau** trong menu thả xuống **Kích hoạt/Hủy kích hoạt** để xác định ngày giờ kích hoạt và hủy kích hoạt trong tương lai của một phân khúc cụ thể.
- **[Tìm khách hàng tương tự](find-similar-customer-segments.md)** khỏi phân khúc.
- **Đổi tên** phân khúc.
- **Nhãn** đến [quản lý thẻ](work-with-tags-columns.md#manage-tags) cho phân khúc.
- **Tải xuống** danh sách thành viên dưới dạng tệp .CSV.
- **Quản lý nội dung xuất** để xem và quản lý phân khúc liên quan đến nội dung xuất. [Tìm hiểu thêm về nội dung xuất.](export-destinations.md)
- **Xóa** phân khúc.
- **Cột** đến [tùy chỉnh các cột](work-with-tags-columns.md#customize-columns) màn hình đó.
- **Lọc** đến [lọc trên các thẻ](work-with-tags-columns.md#filter-on-tags).
- **Tim kiêm tên** để tìm kiếm theo tên phân đoạn.

## <a name="refresh-segments"></a>Làm mới phân khúc

Bạn có thể làm mới tất cả phân phúc cùng lúc bằng cách chọn **Làm mới tất cả** trên trang **Phân khúc** hoặc bạn có thể làm mới một hoặc nhiều phân khúc khi chọn và chọn **Làm mới** từ các tùy chọn. Hoặc bạn có thể định cấu hình làm mới lặp lại trên **Quản trị viên** > **Hệ thống** > **Lịch trình**. Khi cấu hình làm mới định kỳ, các quy tắc sau sẽ áp dụng:

- Tất cả các phân đoạn với loại **Năng động** hoặc **Sự bành trướng** sẽ được tự động làm mới theo nhịp đã đặt. Sau khi quá trình làm mới hoàn tất, **Trạng thái** cho biết nếu có bất kỳ vấn đề nào khi làm mới phân đoạn. Các **Làm mới lần cuối** hiển thị dấu thời gian của lần làm mới thành công gần đây nhất. Nếu xảy ra lỗi, hãy chọn lỗi để xem chi tiết về những gì đã xảy ra.
- Phân đoạn có loại **Tĩnh** *sẽ không* được làm mới tự động. Các **Làm mới lần cuối** hiển thị dấu thời gian của lần cuối cùng các phân đoạn tĩnh được chạy hoặc làm mới theo cách thủ công.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="export-segments"></a>Xuất phân khúc

Bạn có thể xuất một phân khúc từ trang phân khúc hoặc [trang nội dung xuất](export-destinations.md). 

1. Chuyển đến trang **Phân khúc**.

1. Chọn dấu chấm lửng dọc (&vellip;) cho phân đoạn bạn muốn xuất.

1. Chọn **Quản lý nội dung xuất** từ danh sách thả xuống các hành động.

1. Trang **Nội dung xuất (xem trước) cho phân khúc** sẽ mở ra. Bạn có thể xem tất cả các bản xuất đã đặt cấu hình được nhóm theo nhóm có chứa phân khúc hiện tại hay không.

   1. Để thêm phân khúc đã chọn vào bản xuất, hãy **Chỉnh sửa** bản xuất tương ứng để chọn phân khúc tương ứng rồi lưu. Trong môi trường dành cho khách hàng cá nhân, thay vào đó, bạn có thể chọn xuất trong danh sách và chọn **Thêm phân đoạn** để đạt được cùng một kết quả.

   1. Để tạo nội dung xuất mới bằng phân khúc đã chọn, hãy chọn **Thêm nội dung xuất**. Để biết thêm thông tin về cách tạo nội dung xuất, hãy xem phần [Thiết lập nội dung xuất mới](export-destinations.md#set-up-a-new-export).

1. Chọn **Quay lại** để quay lại trang chính cho các phân khúc.

## <a name="track-usage-of-a-segment"></a>Theo dõi việc sử dụng một đoạn

Nếu bạn sử dụng các phân đoạn trong ứng dụng, dựa trên cùng một Microsoft Dataverse tổ chức được kết nối với Thông tin chi tiết về khách hàng, bạn có thể theo dõi việc sử dụng một phân khúc. Vì [Phân đoạn Thông tin chi tiết về khách hàng được sử dụng trong hành trình của khách hàng của Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile), hệ thống sẽ thông báo cho bạn về việc sử dụng phân đoạn đó.

Khi chỉnh sửa phân đoạn đang được sử dụng trong môi trường Thông tin chi tiết về khách hàng hoặc trong hành trình của khách hàng trong Tiếp thị, một biểu ngữ trong [người xây dựng phân đoạn](segment-builder.md) thông báo cho bạn về các phụ thuộc. Bạn có thể kiểm tra chi tiết phụ thuộc trực tiếp từ biểu ngữ hoặc bằng cách chọn **Cách sử dụng** trong trình tạo phân đoạn.

Các **Phân đoạn sử dụng** ngăn hiển thị chi tiết về việc sử dụng phân đoạn này trong Dataverse ứng dụng dựa trên. Đối với các phân đoạn được sử dụng trong hành trình của khách hàng, bạn sẽ tìm thấy một liên kết để kiểm tra hành trình trong Tiếp thị nơi phân đoạn này được sử dụng. Nếu bạn có quyền truy cập ứng dụng Tiếp thị, bạn có thể truy cập thêm thông tin chi tiết tại đó.

:::image type="content" source="media/segment-usage-pane.png" alt-text="Ngăn bên với các chi tiết về việc sử dụng phân đoạn trong trình tạo phân đoạn.":::

Hệ thống thông báo cho bạn về việc sử dụng phân đoạn được theo dõi khi bạn cố gắng xóa nó. Nếu phân khúc bạn sắp xóa được sử dụng trong hành trình của khách hàng trong Tiếp thị, hành trình đó sẽ dừng lại đối với tất cả người dùng trong phân khúc. Nếu hành trình là một phần của chiến dịch tiếp thị, việc xóa sẽ ảnh hưởng đến chính chiến dịch đó. Tuy nhiên, bạn vẫn có thể xóa phân đoạn bất chấp các cảnh báo.

:::image type="content" source="media/segment-usage-delete.png" alt-text="Hộp thoại để xác nhận xóa phân đoạn khi một phân đoạn được sử dụng trong Dataverse đăng kí.":::

### <a name="supported-apps"></a>Các ứng dụng được hỗ trợ

Việc sử dụng hiện được theo dõi trong phần sau Dataverse ứng dụng dựa trên:

- [Hành trình của khách hàng trong Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile)

## <a name="view-processing-history-and-segment-members"></a>Xem lịch sử xử lý và các thành phần phân khúc

Bạn có thể xem dữ liệu tổng hợp về một phân khúc bằng cách xem lại chi tiết của phân khúc đó.

Trên trang **Phân khúc**, chọn phân khúc bạn muốn xem lại.

Phần trên của trang bao gồm một biểu đồ xu hướng nhằm trực quan hóa những thay đổi về số lượng thành phần. Di chuột qua các điểm dữ liệu để xem số lượng thành phần trong một ngày cụ thể.

Bạn có thể cập nhật khung thời gian của trực quan hóa.

> [!div class="mx-imgBorder"]
> ![Khoảng thời gian phân đoạn.](media/segment-time-range.png "Khoảng thời gian phân khúc")

Phần dưới chứa danh sách các thành phần phân khúc.

> [!NOTE]
> Các trường xuất hiện trong danh sách này dựa trên các thuộc tính của các thực thể trong phân khúc của bạn.
>
>Danh sách này là bản xem trước của các thành phần phân khúc phù hợp và hiển thị 100 bản ghi đầu tiên của phân khúc, từ đó bạn có thể đánh giá nhanh và xem lại định nghĩa nếu cần. Để xem tất cả các hồ sơ phù hợp, bạn cần [xuất phân khúc](export-destinations.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
