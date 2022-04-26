---
title: Phân khúc trong thông tin chuyên sâu về đối tượng
description: Tổng quan, cách tạo và quản lý phân khúc.
ms.date: 03/30/2022
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
ms.openlocfilehash: 68e71df3853470af47228c7365f25db3a71d15b0
ms.sourcegitcommit: 9ef2cf99b847e7bd8f890f83d84b3a4045aaf8cc
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 04/01/2022
ms.locfileid: "8529565"
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
- **Tạo bản sao** của một phân khúc. Bạn có thể chọn chỉnh sửa các thuộc tính của nó ngay lập tức hoặc chỉ cần lưu bản sao.
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
- Tất cả các phân đoạn với loại **Năng động** hoặc **Sự bành trướng** sẽ được tự động làm mới theo nhịp đã đặt. Khi quá trình làm mới hoàn tất, **Tình trạng** cho biết nếu có bất kỳ vấn đề nào khi làm mới phân đoạn. Các **Làm mới lần cuối** hiển thị dấu thời gian của lần làm mới thành công gần đây nhất. Nếu xảy ra lỗi, hãy chọn lỗi để xem chi tiết về những gì đã xảy ra.
- Phân đoạn có loại **Tĩnh** *sẽ không* được làm mới tự động. Các **Làm mới lần cuối** hiển thị dấu thời gian của lần cuối cùng các phân đoạn tĩnh được chạy hoặc làm mới theo cách thủ công.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="export-segments"></a>Xuất phân khúc

Bạn có thể xuất một phân khúc từ trang phân khúc hoặc [trang nội dung xuất](export-destinations.md). 

1. Chuyển đến trang **Phân khúc**.

1. Chọn **Hiển thị thêm [...]** cho phân khúc bạn muốn xuất.

1. Chọn **Quản lý nội dung xuất** từ danh sách thả xuống các hành động.

1. Trang **Nội dung xuất (xem trước) cho phân khúc** sẽ mở ra. Bạn có thể xem tất cả các bản xuất đã đặt cấu hình được nhóm theo nhóm có chứa phân khúc hiện tại hay không.

   1. Để thêm phân khúc đã chọn vào bản xuất, hãy **Chỉnh sửa** bản xuất tương ứng để chọn phân khúc tương ứng rồi lưu. Trong môi trường cho khách hàng cá nhân, bạn có thể chọn bản xuất trong danh sách và chọn **Thêm phân khúc** để đạt được cùng một kết quả.

   1. Để tạo nội dung xuất mới bằng phân khúc đã chọn, hãy chọn **Thêm nội dung xuất**. Để biết thêm thông tin về cách tạo nội dung xuất, hãy xem phần [Thiết lập nội dung xuất mới](export-destinations.md#set-up-a-new-export).

1. Chọn **Quay lại** để quay lại trang chính cho các phân khúc.

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


[!INCLUDE[footer-include](../includes/footer-banner.md)]
