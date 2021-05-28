---
title: Phân khúc trong thông tin chuyên sâu về đối tượng
description: Tổng quan, cách tạo và quản lý phân khúc.
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: a7fa6515bd6e79dedfb21aa0f0b8e24b873a6771
ms.sourcegitcommit: 8341fa964365c185b65bc4b71fc0c695ea127dc0
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 05/14/2021
ms.locfileid: "6034038"
---
# <a name="segments-overview"></a>Tổng quan về phân khúc

Phân khúc cho phép bạn nhóm khách hàng của mình dựa trên các thuộc tính nhân khẩu học, giao dịch hoặc hành vi. Bạn có thể sử dụng các phân khúc để nhắm mục tiêu chiến dịch quảng cáo, hoạt động bán hàng và hành động hỗ trợ khách hàng để đạt được mục tiêu kinh doanh.

Hồ sơ khách hàng phù hợp với các bộ lọc của định nghĩa phân khúc được gọi là *các thành viên* của một phân khúc. Một số [giới hạn dịch vụ](service-limits.md) được áp dụng.

## <a name="create-a-new-segment"></a>Tạo phân đoạn mới

Có nhiều cách để tạo một phân khúc mới: 

- Phân khúc phức tạp với trình tạo phân khúc: [Phân khúc trống](segment-builder.md#create-a-new-segment)
- Các phân khúc đơn giản với một toán tử: [Phân khúc nhanh](segment-builder.md#quick-segments)
- Cách tìm khách hàng tương tự dựa trên AI: [Khách hàng tương tự](find-similar-customer-segments.md)
- Đề xuất do AI hỗ trợ dựa trên các biện pháp hoặc thuộc tính: [Các phân khúc được đề xuất nhằm cải thiện các biện pháp](suggested-segments.md)
- Đề xuất dựa trên các hoạt động: [Các phân khúc được đề xuất dựa trên hoạt động của khách hàng](suggested-segments-activity.md)

## <a name="get-insights-on-existing-segments"></a>Tải thông tin chi tiết về các phân khúc hiện có

Khám phá thông tin bổ sung liên quan đến các phân khúc hiện tại của bạn với [Segment insights](segment-insights.md). Tìm hiểu xem 2 phân khúc có gì khác hoặc tương tự nhau.

## <a name="find-similar-customers"></a>Tìm khách hàng tương tự

Tìm khách hàng tương tự với thành viên của một phân khúc đã chọn với sự trợ giúp của trí tuệ nhân tạo. Để biết thêm thông tin, hãy xem [khách hàng tương tự ](find-similar-customer-segments.md).

## <a name="manage-existing-segments"></a>Quản lý các phân đoạn hiện có

Chuyển tới trang **Phân khúc** để xem và quản lý tất cả các phân khúc đã lưu của bạn.

Mỗi phân khúc được đại diện bởi một hàng bao gồm thông tin bổ sung về phân khúc.

> [!div class="mx-imgBorder"]
> ![Tùy chọn để quản lý phân đoạn hiện có](media/segments-selected-segment.png "Tùy chọn để quản lý phân đoạn hiện có")

Hành động sau đây khả dụng khi bạn chọn một phân khúc:

- **Xem** chi tiết phân đoạn, bao gồm xu hướng số lượng thành viên của một bản xem trước thành viên phân đoạn.
- **Chỉnh sửa** phân đoạn để thay đổi các thuộc tính của phân đoạn đó.
- **Tạo bản sao** của một phân khúc. Bạn có thể chọn chỉnh sửa các thuộc tính của nó ngay lập tức hoặc chỉ cần lưu bản sao.
- **Làm mới** phân đoạn để bao gồm dữ liệu mới nhất.
- **Bật** hoặc **tắt** phân đoạn. Các phân khúc có thể có hai trạng thái: hiện hoạt hoặc không hoạt động. Các trạng thái này rất hữu ích khi bạn chỉnh sửa phân khúc. Đối với các phân khúc không hoạt động, định nghĩa phân khúc tồn tại nhưng phân khúc chưa chứa bất kỳ khách hàng nào. Khi bạn kích hoạt một phân khúc, phân khúc sẽ thay đổi trạng thái từ "không hoạt động" thành "hiện hoạt" và bắt đầu tìm kiếm khách hàng phù hợp với định nghĩa phân khúc. Nếu hoạt động [làm mới theo lịch trình](system.md#schedule-tab) được đặt cấu hình, thì các phân khúc không hoạt động sẽ có **Trạng thái** là **Đã bỏ qua**, biểu thị việc làm mới chưa được thực hiện. Khi phân khúc không hoạt động được kích hoạt, mục đó sẽ được làm mới và được đưa vào các lần làm mới theo lịch trình.
  Ngoài ra, bạn cũng có thể dùng chức năng **Lên lịch sau** trong menu thả xuống **Kích hoạt/Hủy kích hoạt** để xác định ngày giờ kích hoạt và hủy kích hoạt trong tương lai của một phân khúc cụ thể.
- **Đổi tên** phân đoạn.
- **Tải xuống** danh sách thành viên dưới dạng tệp .CSV.
- Tùy chọn **Thêm vào** sẽ gửi danh sách ID khách hàng trong phân khúc để xử lý trong một ứng dụng khác.
- **Xóa** phân đoạn.

## <a name="refresh-segments"></a>Làm mới phân đoạn

Bạn có thể làm mới tất cả phân phúc cùng lúc bằng cách chọn **Làm mới tất cả** trên trang **Phân khúc** hoặc bạn có thể làm mới một hoặc nhiều phân khúc khi chọn và chọn **Làm mới** từ các tùy chọn. Hoặc, bạn có thể đặt cấu hình làm mới lặp lại trên **Quản trị viên** > **Hệ thống** > **Lịch trình**.

> [!TIP]
> Có [6 loại trạng thái](system.md#status-types) cho các nhiệm vụ/quy trình. Ngoài ra, hầu hết các quy trình [phụ thuộc vào các quá trình hạ nguồn khác](system.md#refresh-policies). Bạn có thể chọn trạng thái của một quy trình để xem chi tiết về tiến trình của toàn bộ công việc. Sau khi chọn **Xem chi tiết** đối với một trong các tác vụ của công việc, bạn sẽ tìm thấy thông tin bổ sung: thời gian xử lý, ngày xử lý gần nhất và tất cả các lỗi và cảnh báo liên quan đến tác vụ.

## <a name="view-processing-history-and-segment-members"></a>Xem lịch sử xử lý và các thành phần trong phân đoạn

Bạn có thể xem dữ liệu tổng hợp về một phân đoạn bằng cách xem lại chi tiết của phân đoạn đó.

Trên trang **Phân đoạn**, chọn phân đoạn bạn muốn xem lại.

Phần trên của trang bao gồm một biểu đồ xu hướng nhằm trực quan hóa những thay đổi về số lượng thành phần. Di chuột qua các điểm dữ liệu để xem số lượng thành phần trong một ngày cụ thể.

Bạn có thể cập nhật khung thời gian của trực quan hóa.

> [!div class="mx-imgBorder"]
> ![Khoảng thời gian phân đoạn](media/segment-time-range.png "Khoảng thời gian phân đoạn")

Phần dưới chứa danh sách các thành phần phân đoạn.

> [!NOTE]
> Các trường xuất hiện trong danh sách này dựa trên các thuộc tính của các thực thể trong phân đoạn của bạn.
>
>Danh sách này là bản xem trước của các thành phần phân đoạn phù hợp và hiển thị 100 bản ghi đầu tiên của phân đoạn, từ đó bạn có thể đánh giá nhanh và xem lại định nghĩa nếu cần. Để xem tất cả các hồ sơ phù hợp, bạn cần [xuất phân đoạn](export-destinations.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)] 
