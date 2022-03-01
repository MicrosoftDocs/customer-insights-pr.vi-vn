---
title: Xem và tạo phân khúc
description: Cách tạo, chỉnh sửa, xóa phân khúc và nơi sử dụng phân khúc.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 06/09/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: cedcd58373428dd35ba29ce8fdd00007257f8fa59b0d25bc584b4e832df13604
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036174"
---
# <a name="view-and-create-segments"></a>Xem và tạo phân khúc

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Phân khúc giúp bạn xác định tập hợp con của khách truy cập dựa trên các đặc điểm hoặc hoạt động tương tác với trang web. Phân khúc cho phép bạn áp dụng các bộ lọc và phân tích các tập hợp con đó. Số liệu phân tích có thể giúp kiểm tra và phản hồi các xu hướng trong doanh nghiệp của bạn. 

:::image type="content" source="media/segments-page.png" alt-text="Ảnh chụp màn hình ứng dụng thông tin chuyên sâu về tương tác hiển thị danh sách các phân khúc hiện có trong không gian làm việc.":::

## <a name="view-segments"></a>Xem phân khúc

1. Chuyển đến phần **Dữ liệu** ở ngăn điều hướng bên trái. 

1. Chọn tab **Phân khúc** để xem danh sách tất cả các phân khúc trong không gian làm việc. 

## <a name="create-a-segment"></a>Tạo phân khúc

Phân khúc bao gồm các quy tắc và điều kiện được kết nối bằng toán tử logic. Các điều kiện áp dụng bộ lọc vào thứ nguyên đã chọn. Mỗi phân khúc có thể dùng tối đa 5 thứ nguyên.

Ví dụ sau đây cho thấy một phân khúc có 2 điều kiện trong một quy tắc. Quy tắc này lọc tất cả các sự kiện trang web trong đó trình duyệt là Chrome và hệ điều hành là iOS hoặc Android.

:::image type="content" source="media/segment-sample.png" alt-text="Ví dụ về phân khúc có 2 điều kiện trong một quy tắc để lọc các sự kiện trang web.":::

Phần này mô tả cách tạo *phân khúc trống* từ đầu.

1. Chuyển đến phần **Dữ liệu** > **Phân khúc**.

1. Chọn **Phân khúc mới**.

1. Trong **Thư viện tài nguyên**, hãy chọn thuộc tính bạn muốn lọc theo. Hiện tại, bạn chỉ có thể tạo phân khúc dựa trên thứ nguyên.

1. Chọn một toán tử và một giá trị cho thuộc tính đã chọn. Các toán tử sau được hỗ trợ.
   - **là**: yêu cầu khớp chính xác để bao gồm các giá trị. Sử dụng **bằng** đối một giá trị duy nhất hoặc **bất kỳ trong số** để bao gồm nhiều giá trị.
   - **không phải là**: yêu cầu khớp chính xác để loại trừ các giá trị. Sử dụng **bằng** đối một giá trị duy nhất hoặc **bất kỳ trong số** để bao gồm nhiều giá trị.
   - **bắt đầu bằng**: một chuỗi mà các giá trị khớp bắt đầu bằng.
   - **kết thúc bằng**: một chuỗi mà các giá trị khớp kết thúc bằng.
   - **chứa**: một chuỗi có trong các giá trị khớp.

1. Để thêm nhiều điều kiện vào một nhóm, bạn có thể sử dụng 2 toán tử logic. Các thuộc tính dự kiến được coi như yếu tố khi sử dụng các toán tử tập hợp.
   - Toán tử **AND**: Cả hai điều kiện phải được thỏa mãn như một phần của quá trình tạo phân khúc. Tùy chọn này hữu ích nhất khi bạn xác định các điều kiện trên các thực thể khác nhau.
   - Toán tử **OR**: Một trong các điều kiện cần phải được thỏa mãn như một phần của quá trình tạo phân khúc. Tùy chọn này hữu ích nhất khi bạn xác định nhiều điều kiện cho cùng một thực thể.

1. Chọn **Lưu** và đặt tên cho phân khúc. 

Phân khúc đã lưu sẽ xuất hiện trên trang Phân khúc và bạn có thể áp dụng phân khúc này cho tất cả các báo cáo và phễu trong không gian làm việc.

## <a name="use-a-segment-in-a-report-or-funnel"></a>Sử dụng phân khúc trong báo cáo hoặc phễu

Bạn có thể áp dụng phân khúc cho báo cáo hoặc phễu để lọc chúng dựa trên các điều kiện trong phân khúc. Tuy nhiên, bạn không thể áp dụng phân khúc cho báo cáo mức sử dụng theo thời gian thực.

:::image type="content" source="media/segment-reports-filter.png" alt-text="Báo cáo lượt xem trang với danh sách thả xuống mở rộng để chọn phân khúc sẽ áp dụng.":::

Để áp dụng phân khúc, hãy mở báo cáo hoặc phễu. Chọn **Thêm điều kiện** rồi chọn **Lọc theo phân khúc**. Chọn phân khúc từ danh sách bạn muốn áp dụng. Phân khúc bạn chọn sẽ được áp dụng cho báo cáo. Nếu biểu đồ không hỗ trợ phân khúc đó, thông báo lỗi sẽ xuất hiện.
 
Bạn có thể áp dụng *tối đa 3 phân khúc* cho một báo cáo hoặc phễu.

## <a name="edit-a-segment"></a>Chỉnh sửa phân khúc

1. Chuyển đến phần **Dữ liệu** > **Phân khúc**.
1. Chọn phân khúc trong danh sách để mở. 
1. Thay đổi hoặc thêm các giá trị nếu cần.
1. Chọn **Lưu** để áp dụng thay đổi.

## <a name="change-the-name-of-a-segment"></a>Thay đổi tên của phân khúc

1. Chuyển đến phần **Dữ liệu** > **Phân khúc**.
1. Trong danh sách phân khúc, hãy chọn **Thêm [...]**. 
1. Chọn **Chỉnh sửa tên** từ danh sách thả xuống.
1. Nhập tên mới rồi chọn **Đổi tên**.

## <a name="delete-a-segment"></a>Xóa phân khúc

1. Chuyển đến phần **Dữ liệu** > **Phân khúc**.
1. Trong danh sách phân khúc, hãy chọn **Thêm [...]**. 
1. Chọn **Xóa** từ danh sách thả xuống.
1. Chọn **Xóa** để xác nhận.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
