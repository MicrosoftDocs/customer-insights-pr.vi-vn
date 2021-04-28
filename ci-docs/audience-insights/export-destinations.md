---
title: Xuất dữ liệu từ Customer Insights
description: Quản lý nội dung xuất để chia sẻ dữ liệu.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 354ce9ef30fe918975d06290430996c84f8bd3f7
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896169"
---
# <a name="exports-preview-overview"></a>Tổng quan về trang Nội dung xuất (bản xem trước)

Trang **Nội dung xuất** hiển thị cho bạn tất cả các nội dung xuất đã đặt cấu hình. Nội dung xuất chia sẻ dữ liệu cụ thể với các ứng dụng khác nhau. Chúng có thể bao gồm các thực thể hoặc hồ sơ khách hàng, lược đồ và thông tin chi tiết ánh xạ. Mỗi nội dung xuất yêu cầu một [kết nối, do quản trị viên thiết lập, để quản lý hoạt động xác thực và truy cập](connections.md).

> [!NOTE]
> Cho đến tháng 3 năm 2021, các nội dung xuất đã tự động tạo kết nối với dịch vụ tương ứng. Hiện tại, cần có một [kết nối, do quản trị viên tạo và chia sẻ](connections.md) thì bạn mới có thể tạo các nội dung xuất.

Đi đến **Dữ liệu** > **Nội dung xuất** để xem trang nội dung xuất. Tất cả các vai trò người dùng đều có quyền truy cập để xem các nội dung xuất đã đặt cấu hình. Sử dụng trường tìm kiếm trong thanh lệnh để tìm các nội dung xuất theo tên, tên kết nối hoặc loại kết nối.

## <a name="set-up-a-new-export"></a>Thiết lập một nội dung xuất mới

Để thiết lập hoặc chỉnh sửa một nội dung xuất, bạn cần có sẵn các kết nối. Kết nối phụ thuộc vào [vai trò người dùng](permissions.md) của bạn:
- Quản trị viên có quyền truy cập vào tất cả các kết nối. Họ cũng có thể tạo kết nối mới khi thiết lập nội dung xuất.
- Những người đóng góp có thể có quyền truy cập vào các kết nối cụ thể. Họ có thể đặt cấu hình và chia sẻ kết nối hay không là tùy thuộc vào quản trị viên. Để biết thêm thông tin, hãy xem [Cho phép người đóng góp sử dụng một kết nối cho các lần xuất](connections.md#allow-contributors-to-use-a-connection-for-exports).
- Người xem chỉ có thể xem các nội dung xuất hiện có nhưng không thể tạo chúng.

1. Đi tới **Dữ liệu** > **Nội dung xuất**.

1. Chọn **Thêm nội dung xuất** để tạo một đích xuất mới.

1. Trong ngăn **Thiết lập nội dung xuất**, hãy chọn kết nối để sử dụng. [Kết nối](connections.md) do quản trị viên quản lý. 

1. Cung cấp các thông tin chi tiết được yêu cầu rồi chọn **Lưu** để tạo nội dung xuất.

### <a name="edit-an-export"></a>Chỉnh sửa nội dung xuất

1. Chọn dấu ba chấm dọc cạnh đích xuất bạn muốn chỉnh sửa.

1. Chọn **Chỉnh sửa** từ menu thả xuống.

1. Thay đổi các giá trị mà bạn muốn cập nhật rồi chọn **Lưu**.

## <a name="view-exports-and-export-details"></a>Xem Nội dung xuất và thông tin chi tiết về nội dung xuất

Sau khi tạo đích xuất, chúng được liệt kê trên **Dữ liệu** > **Nội dung xuất**. Tất cả người dùng có thể xem dữ liệu nào được chia sẻ và trạng thái mới nhất của dữ liệu đó.

1. Đi tới **Dữ liệu** > **Nội dung xuất**.

1. Người dùng không có quyền chỉnh sửa hãy chọn **Xem** thay vì **Chỉnh sửa** để xem thông tin chi tiết về nội dung xuất.

1. Ngăn bên này hiển thị việc thiết lập nội dung xuất này. Nếu không có quyền chỉnh sửa, bạn không thể thay đổi giá trị. Chọn **Đóng** để quay lại trang nội dung xuất.

## <a name="run-exports-on-demand"></a>Chạy nội dung xuất theo yêu cầu

Sau khi đặt cấu hình nội dung xuất, nó sẽ chạy trong mỗi [lần làm mới theo lịch trình](system.md#schedule-tab) miễn là có kết nối đang hoạt động.

Để xuất dữ liệu mà không cần đợi làm mới theo lịch trình, hãy đi đến **Dữ liệu** > **Nội dung xuất**. Bạn có hai tùy chọn:

- Để chạy tất cả các nội dung xuất, hãy chọn **Chạy tất cả** trong thanh lệnh. 
- Để chạy một nội dung xuất, hãy chọn dấu chấm lửng (...) trên một mục danh sách rồi chọn **Chạy**.

## <a name="remove-an-export"></a>Loại bỏ một nội dung xuất

1. Đi tới **Dữ liệu** > **Nội dung xuất**.

1. Chọn dấu ba chấm dọc cho Nội dung xuất mà bạn muốn loại bỏ.

1. Chọn **Xóa** trong menu thả xuống.

1. Xác nhận việc xóa bằng cách chọn **Xóa** trên màn hình xác nhận.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
