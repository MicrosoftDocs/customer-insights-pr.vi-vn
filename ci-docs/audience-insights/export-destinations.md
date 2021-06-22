---
title: Xuất dữ liệu từ Customer Insights
description: Quản lý nội dung xuất để chia sẻ dữ liệu.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6e7793fa99f8431d9d420529b39e0b5b5dbf6748
ms.sourcegitcommit: 0689e7ed4265855d1f76745d68af390f8f4af8a0
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 06/14/2021
ms.locfileid: "6253066"
---
# <a name="exports-preview-overview"></a>Tổng quan về trang Nội dung xuất (xem trước)

Trang **Nội dung xuất** hiển thị cho bạn tất cả các nội dung xuất đã đặt cấu hình. Nội dung xuất chia sẻ dữ liệu cụ thể với các ứng dụng khác nhau. Chúng có thể bao gồm các thực thể hoặc hồ sơ khách hàng, lược đồ và thông tin chi tiết ánh xạ. Mỗi nội dung xuất yêu cầu một [kết nối, do quản trị viên thiết lập, để quản lý hoạt động xác thực và truy cập](connections.md).

Đi đến **Dữ liệu** > **Nội dung xuất** để xem trang nội dung xuất. Tất cả các vai trò người dùng đều có quyền truy cập để xem các nội dung xuất đã đặt cấu hình. Sử dụng trường tìm kiếm trong thanh lệnh để tìm các nội dung xuất theo tên, tên kết nối hoặc loại kết nối.

## <a name="set-up-a-new-export"></a>Thiết lập một nội dung xuất mới

Để thiết lập hoặc chỉnh sửa một nội dung xuất, bạn cần có sẵn các kết nối. Kết nối phụ thuộc vào [vai trò người dùng](permissions.md) của bạn:
- Quản trị viên có quyền truy cập vào tất cả các kết nối. Họ cũng có thể tạo kết nối mới khi thiết lập nội dung xuất.
- Những người đóng góp có thể có quyền truy cập vào các kết nối cụ thể. Họ có thể đặt cấu hình và chia sẻ kết nối hay không là tùy thuộc vào quản trị viên. Danh sách nội dung xuất cho người đóng góp biết họ có thể chỉnh sửa hay chỉ được xem nội dung xuất trong cột **Quyền của bạn**. Để biết thêm thông tin, hãy xem [Cho phép người đóng góp sử dụng một kết nối cho các lần xuất](connections.md#allow-contributors-to-use-a-connection-for-exports).
- Người xem chỉ có thể xem các nội dung xuất hiện có nhưng không thể tạo chúng.

### <a name="define-a-new-export"></a>Xác định nội dung xuất mới

1. Đi tới **Dữ liệu** > **Nội dung xuất**.

1. Chọn **Thêm nội dung xuất** để tạo nội dung xuất mới.

1. Trong ngăn **Thiết lập nội dung xuất**, hãy chọn kết nối để sử dụng. [Kết nối](connections.md) do quản trị viên quản lý. 

1. Cung cấp các thông tin chi tiết được yêu cầu rồi chọn **Lưu** để tạo nội dung xuất.

### <a name="define-a-new-export-based-on-an-existing-export"></a>Xác định nội dung xuất mới dựa trên nội dung xuất hiện có

1. Đi tới **Dữ liệu** > **Nội dung xuất**.

1. Trong danh sách nội dung xuất, hãy chọn nội dung xuất bạn muốn sao chép.

1. Chọn **Tạo bản sao** trên thanh lệnh để mở ngăn **Thiết lập nội dung xuất** với thông tin chi tiết về nội dung xuất đã chọn.

1. Xem lại và điều chỉnh nội dung xuất rồi chọn **Lưu** để tạo nội dung xuất mới.

### <a name="edit-an-export"></a>Chỉnh sửa nội dung xuất

1. Đi tới **Dữ liệu** > **Nội dung xuất**.

1. Trong danh sách nội dung xuất, hãy chọn nội dung xuất bạn muốn chỉnh sửa.

1. Chọn **Chỉnh sửa** trên thanh lệnh.

1. Thay đổi các giá trị mà bạn muốn cập nhật rồi chọn **Lưu**.

## <a name="view-exports-and-export-details"></a>Xem nội dung xuất và thông tin chi tiết về nội dung xuất

Sau khi tạo đích xuất, các đích xuất đã tạo sẽ có trong phần **Dữ liệu** > **Nội dung xuất**. Tất cả người dùng có thể xem dữ liệu nào được chia sẻ và trạng thái mới nhất của dữ liệu đó.

1. Đi tới **Dữ liệu** > **Nội dung xuất**.

1. Người dùng không có quyền chỉnh sửa hãy chọn **Xem** thay vì **Chỉnh sửa** để xem thông tin chi tiết về nội dung xuất.

1. Ngăn bên hiển thị cấu hình của nội dung xuất. Nếu không có quyền chỉnh sửa, bạn không thể thay đổi giá trị. Chọn **Đóng** để quay lại trang nội dung xuất.

## <a name="schedule-and-run-exports"></a>Lên lịch và chạy nội dung xuất

Mỗi nội dung xuất bạn đặt cấu hình đều có lịch làm mới. Trong quá trình làm mới, hệ thống sẽ tìm dữ liệu mới hoặc dữ liệu cập nhật để đưa vào nội dung xuất. Theo mặc định, các nội dung xuất được chạy trong mỗi lần [làm mới hệ thống theo lịch](system.md#schedule-tab). Bạn có thể tùy chỉnh lịch làm mới hoặc tắt đi để chạy nội dung xuất theo cách thủ công.

Lịch xuất phụ thuộc vào trạng thái môi trường của bạn. Nếu hệ thống đang cập nhật [các phần phụ thuộc](system.md#refresh-policies) khi quá trình xuất theo lịch bắt đầu, thì trước tiên, hệ thống sẽ hoàn thành các phần phụ thuộc rồi mới chạy nội dung xuất. Bạn có thể biết thời điểm gần đây nhất mà nội dung xuất được làm mới trong cột **Đã làm mới**.

### <a name="schedule-exports"></a>Lên lịch nội dung xuất

Bạn có thể xác định lịch làm mới tùy chỉnh cho từng nội dung xuất hoặc một vài nội dung xuất cùng lúc. Lịch trình hiện tại được xác định có trong cột **Lịch trình** của danh sách nội dung xuất. Quyền thay đổi lịch trình tương tự như [chỉnh sửa và xác định nội dung xuất](export-destinations.md#set-up-a-new-export). 

1. Đi tới **Dữ liệu** > **Nội dung xuất**.

1. Chọn nội dung xuất bạn muốn lên lịch.

1. Chọn **Lên lịch** trên thanh lệnh.

1. Trong ngăn **Lên lịch xuất**, đặt tùy chọn **Lên lịch chạy** thành **Bật** để tự động chạy nội dung xuất. Đặt thành **Tắt** để làm mới nội dung xuất theo cách thủ công.

1. Đối với nội dung xuất được làm mới tự động, hãy chọn một giá trị **Lặp lại** rồi chỉ định thông tin chi tiết. Thời gian đã xác định sẽ được áp dụng cho tất cả các trường hợp lặp lại. Đây là thời gian mà một nội dung xuất sẽ bắt đầu làm mới.

1. Áp dụng và kích hoạt các thay đổi bằng cách chọn **Lưu**.

Khi chỉnh sửa lịch trình cho một số nội dung xuất, bạn cần thực hiện lựa chọn trong phần **Giữ hoặc ghi đè lịch trình**:
- **Giữ lịch trình riêng**: Duy trì lịch trình đã xác định từ trước cho các nội dung xuất đã chọn và chỉ tắt hoặc bật.
- **Xác định lịch trình mới cho tất cả nội dung xuất đã chọn**: Ghi đè lên lịch trình hiện có của các nội dung xuất đã chọn.

### <a name="run-exports-on-demand"></a>Chạy nội dung xuất theo yêu cầu

Để xuất dữ liệu mà không cần đợi làm mới theo lịch trình, hãy đi đến **Dữ liệu** > **Nội dung xuất**.

- Để chạy tất cả các nội dung xuất, hãy chọn **Chạy tất cả** trong thanh lệnh. Thao tác này sẽ chỉ chạy các nội dung xuất có lịch trình hiện hoạt.
- Để chạy một nội dung xuất, hãy chọn nội dung xuất đó trong danh sách rồi chọn **Chạy** trên thanh lệnh. Đó là cách bạn chạy nội dung xuất không có lịch trình hiện hoạt. 

## <a name="remove-an-export"></a>Loại bỏ một nội dung xuất

1. Đi tới **Dữ liệu** > **Nội dung xuất**.

1. Chọn nội dung xuất mà bạn muốn loại bỏ.

1. Chọn **Loại bỏ** trên thanh lệnh.

1. Xác nhận việc xóa bằng cách chọn **Xóa** trên màn hình xác nhận.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
