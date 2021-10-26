---
title: Xuất dữ liệu từ Customer Insights
description: Quản lý nội dung xuất để chia sẻ dữ liệu.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 45a4c964e9810640c764357a72b9794f4fda89f4
ms.sourcegitcommit: 5d82e5b808517e0e99fdfdd7e4a4422a5b8ebd5c
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 10/11/2021
ms.locfileid: "7623159"
---
# <a name="exports-preview-overview"></a>Tổng quan về trang Nội dung xuất (xem trước)

Trang **Nội dung xuất** hiển thị cho bạn tất cả các nội dung xuất đã định cấu hình. Nội dung xuất chia sẻ dữ liệu cụ thể với các ứng dụng khác nhau. Chúng có thể bao gồm hồ sơ khách hàng, thực thể, lược đồ và chi tiết ánh xạ. Mỗi nội dung xuất yêu cầu một [kết nối, do quản trị viên thiết lập, để quản lý hoạt động xác thực và truy cập](connections.md).

Đi đến **Dữ liệu** > **Nội dung xuất** để xem trang nội dung xuất. Tất cả các vai trò người dùng đều có thể xem nội dung xuất đã định cấu hình. Sử dụng trường tìm kiếm trong thanh lệnh để tìm nội dung xuất theo tên, tên kết nối hoặc kiểu kết nối.

## <a name="export-types"></a>Loại xuất

Có hai loại xuất chính:  

- **Xuất dữ liệu ra** cho phép bạn xuất bất kỳ loại thực thể nào có sẵn trong thông tin chuyên sâu về đối tượng. Các thực thể mà bạn chọn để xuất được xuất với tất cả các trường dữ liệu, siêu dữ liệu, lược đồ và chi tiết ánh xạ. 
- **Xuất phân khúc** cho phép bạn xuất các thực thể phân khúc từ thông tin chuyên sâu về đối tượng. Các phân khúc đại diện cho một danh sách các hồ sơ khách hàng. Khi đặt cấu hình xuất, bạn chọn các trường dữ liệu được bao gồm, tùy thuộc vào hệ thống đích mà bạn đang xuất dữ liệu. 

### <a name="export-segments"></a>Xuất phân khúc

**Xuất phân khúc trong môi trường dành cho tài khoản doanh nghiệp (B2B) hoặc khách hàng cá nhân (B2C)**  
Hầu hết tùy chọn xuất hỗ trợ cả hai loại môi trường. Việc xuất phân khúc sang các hệ thống mục tiêu khác nhau có các yêu cầu cụ thể. Nói chung, thành phần phân khúc, hồ sơ khách hàng, chứa thông tin liên hệ. Mặc dù điều này thường xảy ra đối với các phân khúc được xây dựng trên khách hàng cá nhân (B2C), nhưng nó không nhất thiết phải xảy ra đối với các phân khúc dựa trên tài khoản doanh nghiệp (B2B). 

**Môi trường xuất phân khúc cho tài khoản doanh nghiệp (B2B)**  
- Các phân khúc trong bối cảnh môi trường dành cho tài khoản doanh nghiệp được xây dựng dựa trên thực thể *tài khoản*. Để xuất các phân khúc tài khoản như hiện tại, hệ thống mục tiêu cần hỗ trợ các phân khúc tài khoản thuần túy. Đây là trường hợp cho [LinkedIn](export-linkedin-ads.md) khi bạn chọn tùy chọn **công ty** trong khi xác định xuất.
- Tất cả các hệ thống đích khác đều yêu cầu các trường từ thực thể liên hệ. Để đảm bảo các phân khúc tài khoản có thể truy xuất dữ liệu từ các liên hệ có liên quan, định nghĩa phân khúc của bạn cần phải chiếu các thuộc tính của thực thể liên hệ. Tìm hiểu thêm về cách [đặt cấu hình các phân khúc và chiếu thuộc tính](segment-builder.md).

**Xuất phân khúc trong môi trường dành cho khách hàng cá nhân (B2C)**  
- Các phân khúc trong bối cảnh môi trường dành cho khách hàng cá nhân được xây dựng dựa trên thực thể *hồ sơ khách hàng hợp nhất*. Mọi phân khúc đáp ứng yêu cầu của hệ thống mục tiêu (ví dụ: địa chỉ email) đều có thể được xuất.

**Giới hạn đối với xuất phân khúc**  
- Hệ thống mục tiêu của bên thứ ba có thể giới hạn số lượng hồ sơ khách hàng mà bạn có thể xuất. 
- Đối với khách hàng cá nhân, bạn sẽ thấy số lượng thành phần phân khúc thực tế khi chọn phân khúc để xuất. Bạn sẽ nhận được cảnh báo nếu một phân khúc quá lớn. 
- Đối với tài khoản doanh nghiệp, bạn sẽ thấy số lượng tài khoản trong một phân khúc; tuy nhiên, số lượng liên hệ có thể được chiếu không hiển thị. Trong một số trường hợp, điều này có thể dẫn đến phân khúc đã xuất thực sự chứa nhiều hồ sơ khách hàng hơn hệ thống mục tiêu chấp nhận. Vượt quá giới hạn của kết quả hệ thống đích sẽ bỏ qua quá trình xuất. 

## <a name="set-up-a-new-export"></a>Thiết lập một nội dung xuất mới  
Để thiết lập hoặc chỉnh sửa một nội dung xuất, bạn cần có sẵn các kết nối. Kết nối phụ thuộc vào [vai trò người dùng](permissions.md) của bạn:
- **Quản trị viên** có quyền truy cập vào tất cả các kết nối. Họ cũng có thể tạo kết nối mới khi thiết lập nội dung xuất.
- **Người đóng góp** có thể có quyền truy cập vào các kết nối cụ thể. Họ có thể định cấu hình và chia sẻ kết nối hay không là tùy thuộc vào quản trị viên. Danh sách nội dung xuất cho người đóng góp biết họ có thể chỉnh sửa hay chỉ được xem nội dung xuất trong cột **Quyền của bạn**. Để biết thêm thông tin, hãy truy cập [Cho phép những người đóng góp sử dụng kết nối để xuất](connections.md#allow-contributors-to-use-a-connection-for-exports).
- **Người xem** chỉ có thể xem các xuất hiện có chứ không thể tạo.

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

1. Để xem chi tiết xuất, người dùng không có quyền chỉnh sửa chọn **Xem** thay vì **Chỉnh sửa**.

1. Ngăn bên hiển thị cấu hình của nội dung xuất. Nếu không có quyền chỉnh sửa, bạn không thể thay đổi giá trị. Chọn **Đóng** để quay lại trang nội dung xuất.

## <a name="schedule-and-run-exports"></a>Lên lịch và chạy nội dung xuất

Mỗi nội dung xuất bạn đặt cấu hình đều có lịch làm mới. Trong quá trình làm mới, hệ thống sẽ tìm dữ liệu mới hoặc dữ liệu cập nhật để đưa vào nội dung xuất. Theo mặc định, các nội dung xuất được chạy trong mỗi lần [làm mới hệ thống theo lịch](system.md#schedule-tab). Bạn có thể tùy chỉnh lịch làm mới hoặc tắt đi để chạy nội dung xuất theo cách thủ công.

Lịch xuất phụ thuộc vào trạng thái môi trường của bạn. Nếu đang tiến hành cập nhật [yếu tố phụ thuộc](system.md#refresh-policies) khi quy trình xuất theo lịch trình chuẩn bị bắt đầu, trước tiên hệ thống sẽ hoàn thành việc cập nhật đó rồi mới chạy quy trình xuất. Bạn có thể biết thời điểm gần đây nhất mà nội dung xuất được làm mới trong cột **Đã làm mới**.

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
