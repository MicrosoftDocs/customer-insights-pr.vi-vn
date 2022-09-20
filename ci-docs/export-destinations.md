---
title: Tổng quan về trang Nội dung xuất (xem trước)
description: Quản lý nội dung xuất để chia sẻ dữ liệu.
ms.date: 08/12/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- ci-connections
- customerInsights
ms.openlocfilehash: 44f58d694b9bd35a8d8c04d487d40743291e0566
ms.sourcegitcommit: ef3e17134d44d2731605381ea0385dbc5aef6120
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 09/09/2022
ms.locfileid: "9460216"
---
# <a name="exports-preview-overview"></a>Tổng quan về trang Nội dung xuất (xem trước)

 Xuất cho phép bạn chia sẻ dữ liệu cụ thể với các ứng dụng khác nhau. Chúng có thể bao gồm hồ sơ khách hàng, thực thể, lược đồ và chi tiết ánh xạ. Mỗi nội dung xuất yêu cầu một [kết nối, do quản trị viên thiết lập, để quản lý hoạt động xác thực và truy cập](connections.md). Trang **Nội dung xuất** hiển thị cho bạn tất cả các nội dung xuất đã định cấu hình.

## <a name="export-types"></a>Loại xuất

Có hai loại xuất chính:  

- **Xuất dữ liệu ra ngoài** cho phép bạn xuất bất kỳ loại thực thể nào có sẵn trong Thông tin chi tiết về khách hàng. Các thực thể mà bạn chọn để xuất được xuất với tất cả các trường dữ liệu, siêu dữ liệu, lược đồ và chi tiết ánh xạ.
- **Xuất khẩu phân đoạn** cho phép bạn xuất các thực thể phân đoạn từ Thông tin chi tiết về khách hàng. Đối với người tiêu dùng cá nhân (B-to-C), các phân đoạn thể hiện danh sách hồ sơ khách hàng. Đối với doanh nghiệp (B-to-B), [phân đoạn có thể đại diện cho một danh sách các tài khoản hoặc địa chỉ liên hệ](segment-builder.md#create-a-new-segment-with-segment-builder). Khi định cấu hình xuất, bạn chọn các trường dữ liệu được bao gồm, tùy thuộc vào hệ thống đích mà bạn đang xuất dữ liệu.

### <a name="export-segments"></a>Xuất phân khúc

**Xuất phân khúc trong môi trường dành cho tài khoản doanh nghiệp (B2B) hoặc khách hàng cá nhân (B2C)**  
Hầu hết các tùy chọn xuất hỗ trợ cả hai loại môi trường. Việc xuất khẩu các phân đoạn sang các hệ thống mục tiêu khác nhau có các yêu cầu cụ thể. 

**Xuất phân khúc trong môi trường dành cho người tiêu dùng cá nhân (B2C)**  
- Các phân khúc trong bối cảnh môi trường dành cho khách hàng cá nhân được xây dựng dựa trên thực thể *hồ sơ khách hàng hợp nhất*. Mọi phân khúc đáp ứng yêu cầu của hệ thống mục tiêu (ví dụ: địa chỉ email) đều có thể được xuất.

**Xuất phân đoạn trong môi trường dành cho tài khoản doanh nghiệp (B-to-B)**  
- Các phân đoạn trong bối cảnh môi trường dành cho tài khoản doanh nghiệp được xây dựng dựa trên *tài khoản* thực thể hoặc *tiếp xúc* thực thể. Để xuất các phân khúc tài khoản như hiện tại, hệ thống mục tiêu cần hỗ trợ các phân khúc tài khoản thuần túy. Đây là trường hợp cho [LinkedIn](export-linkedin-ads.md) khi bạn chọn tùy chọn **công ty** trong khi xác định xuất.
- Tất cả các hệ thống đích khác đều yêu cầu các trường từ thực thể liên hệ.
- Với hai loại phân đoạn (địa chỉ liên hệ và tài khoản), Customer Insights tự động xác định loại phân đoạn nào đủ điều kiện để xuất dựa trên hệ thống mục tiêu. Ví dụ: đối với hệ thống nhắm mục tiêu tập trung vào địa chỉ liên hệ như Mailchimp, Thông tin chi tiết về khách hàng chỉ cho phép bạn chọn các phân đoạn liên hệ để xuất.

**Giới hạn đối với xuất phân khúc**  
- Hệ thống mục tiêu của bên thứ ba có thể giới hạn số lượng hồ sơ khách hàng mà bạn có thể xuất. 
- Đối với khách hàng cá nhân, bạn sẽ thấy số lượng thành phần phân khúc thực tế khi chọn phân khúc để xuất. Bạn sẽ nhận được cảnh báo nếu một phân đoạn quá lớn. 
- Đối với tài khoản doanh nghiệp, bạn sẽ thấy số lượng tài khoản hoặc địa chỉ liên hệ tùy thuộc vào phân khúc. Bạn sẽ nhận được cảnh báo nếu phân đoạn quá lớn. Vượt quá giới hạn của kết quả hệ thống đích sẽ bỏ qua quá trình xuất.

## <a name="set-up-a-new-export"></a>Thiết lập một nội dung xuất mới

Để thiết lập hoặc chỉnh sửa bản xuất, bạn cần có các kết nối phù hợp với mình. Kết nối phụ thuộc vào [vai trò người dùng](permissions.md) của bạn:
- **Quản trị viên** có quyền truy cập vào tất cả các kết nối. Họ cũng có thể tạo kết nối mới khi thiết lập nội dung xuất.
- **Người đóng góp** có thể có quyền truy cập vào các kết nối cụ thể. Họ có thể định cấu hình và chia sẻ kết nối hay không là tùy thuộc vào quản trị viên. Danh sách nội dung xuất cho người đóng góp biết họ có thể chỉnh sửa hay chỉ được xem nội dung xuất trong cột **Quyền của bạn**. Để biết thêm thông tin, hãy truy cập [Cho phép những người đóng góp sử dụng kết nối để xuất](connections.md#allow-contributors-to-use-a-connection-for-exports).
- **Người xem** chỉ có thể xem các xuất hiện có chứ không thể tạo.

1. Đi tới **Dữ liệu** > **Nội dung xuất**.

1. Chọn **Thêm nội dung xuất** để tạo nội dung xuất mới.

1. Bên trong **Thiết lập xuất** ngăn, chọn cái nào [sự liên quan](connections.md) để sử dụng.

1. Cung cấp các thông tin chi tiết được yêu cầu rồi chọn **Lưu** để tạo nội dung xuất. Để biết chi tiết bắt buộc, hãy xem lại tài liệu Thông tin chi tiết về khách hàng cho lần xuất cụ thể.

## <a name="manage-existing-exports"></a>Quản lý các xuất hiện có

Đi đến **Dữ liệu** > **Xuất khẩu** để xem các kết xuất, tên kết nối, loại kết nối và trạng thái của chúng. Tất cả các vai trò người dùng đều có thể xem nội dung xuất đã định cấu hình. Bạn có thể sắp xếp danh sách xuất theo bất kỳ cột nào hoặc sử dụng hộp tìm kiếm để tìm xuất bạn muốn quản lý.

Chọn một bản xuất để xem các hành động có sẵn.

:::image type="content" source="media/exports_showmore.png" alt-text="Trang xuất khẩu.":::

- **Lượt xem** hoặc **Chỉnh sửa** việc xuất khẩu. Để xem chi tiết xuất, người dùng không có quyền chỉnh sửa chọn **Xem** thay vì **Chỉnh sửa**.
- **Chạy** xuất để xuất dữ liệu mới nhất.
- **Tạo bản sao** của một xuất khẩu.
- **[Lịch trình](#schedule-and-run-exports)** việc xuất khẩu.
- **Tách kết nối** để xóa kết nối cho lần xuất này. Detach không xóa kết nối, nhưng hủy kích hoạt quá trình xuất. Các **Kết nối được sử dụng** cột hiển thị Không có kết nối.
- **Loại bỏ** việc xuất khẩu.

## <a name="schedule-and-run-exports"></a>Lên lịch và chạy nội dung xuất

Mỗi nội dung xuất bạn đặt cấu hình đều có lịch làm mới. Trong quá trình làm mới, hệ thống sẽ tìm dữ liệu mới hoặc dữ liệu cập nhật để đưa vào nội dung xuất. Theo mặc định, các nội dung xuất được chạy trong mỗi lần [làm mới hệ thống theo lịch](schedule-refresh.md). Bạn có thể tùy chỉnh lịch làm mới hoặc tắt đi để chạy nội dung xuất theo cách thủ công.

> [!TIP]
> Giảm thiểu thời gian xử lý xuất khẩu phân đoạn bằng các phương pháp hay nhất sau:
> - Phân phối các thực thể phân đoạn trên nhiều lần xuất khẩu.
> - Tránh lập lịch cho tất cả các lần xuất cùng một lúc. Chừa 30 phút hoặc một giờ giữa thời gian dự kiến của mỗi lần xuất.

Lịch xuất phụ thuộc vào trạng thái môi trường của bạn. Nếu đang tiến hành cập nhật [yếu tố phụ thuộc](system.md#refresh-processes) khi quy trình xuất theo lịch trình chuẩn bị bắt đầu, trước tiên hệ thống sẽ hoàn thành việc cập nhật đó rồi mới chạy quy trình xuất. Các **Làm mới** cột hiển thị khi lần xuất được làm mới lần cuối.

### <a name="schedule-exports"></a>Lên lịch nội dung xuất

Xác định lịch trình làm mới tùy chỉnh cho từng lần xuất hoặc nhiều lần xuất cùng một lúc. Lịch trình hiện tại được xác định có trong cột **Lịch trình** của danh sách nội dung xuất. Quyền thay đổi lịch biểu giống như [chỉnh sửa và xác định xuất khẩu](export-destinations.md#set-up-a-new-export).

1. Đi tới **Dữ liệu** > **Nội dung xuất**.

1. Chọn nội dung xuất bạn muốn lên lịch.

1. Chọn **Lịch trình**.

1. Trong ngăn **Lên lịch xuất**, đặt tùy chọn **Lên lịch chạy** thành **Bật** để tự động chạy nội dung xuất. Đặt thành **Tắt** để làm mới nội dung xuất theo cách thủ công.

1. Đối với nội dung xuất được làm mới tự động, hãy chọn một giá trị **Lặp lại** rồi chỉ định thông tin chi tiết. Thời gian đã xác định sẽ được áp dụng cho tất cả các trường hợp lặp lại. Đây là thời gian mà một nội dung xuất sẽ bắt đầu làm mới.

1. Chọn **Lưu.**

Khi chỉnh sửa lịch biểu cho một số lần xuất, hãy lựa chọn trong **Giữ hoặc ghi đè lịch biểu**:

- **Giữ lịch trình cá nhân** : Giữ lịch trình đã xác định trước đó cho các lần xuất đã chọn và chỉ tắt hoặc bật chúng.
- **Xác định lịch trình mới cho tất cả nội dung xuất đã chọn**: Ghi đè lên lịch trình hiện có của các nội dung xuất đã chọn.

### <a name="run-exports-on-demand"></a>Chạy nội dung xuất theo yêu cầu

Để xuất dữ liệu mà không cần đợi làm mới theo lịch trình, hãy đi đến **Dữ liệu** > **Nội dung xuất**.

- Để chạy tất cả các nội dung xuất, hãy chọn **Chạy tất cả** trong thanh lệnh. Chỉ các bản xuất có lịch biểu hoạt động mới được chạy. Để chạy một xuất hiện không hoạt động, hãy chạy một xuất duy nhất.
- Để chạy một nội dung xuất, hãy chọn nội dung xuất đó trong danh sách rồi chọn **Chạy** trên thanh lệnh.

## <a name="troubleshooting"></a>Gỡ rối

### <a name="segment-not-eligible-for-export"></a>Phân đoạn không đủ điều kiện xuất khẩu

**Vấn đề** Trong môi trường tài khoản doanh nghiệp, quá trình xuất của bạn không thành công với thông báo lỗi: "Phân đoạn sau không đủ điều kiện cho điểm đến xuất này: '{ tên của phân khúc} '. Vui lòng chỉ chọn các phân đoạn thuộc loại ContactProfile và thử lại. "

**Nghị quyết** Môi trường Customer Insights dành cho tài khoản doanh nghiệp đã được cập nhật để hỗ trợ các phân đoạn liên hệ ngoài các phân đoạn tài khoản. Do sự thay đổi đó, các mục xuất cần chi tiết liên hệ chỉ hoạt động với các phân đoạn dựa trên địa chỉ liên hệ.

1. [Tạo phân đoạn dựa trên danh bạ](segment-builder.md) phù hợp với phân đoạn đã sử dụng trước đây của bạn.

1. Khi phân đoạn liên hệ đó được chạy, hãy chỉnh sửa bản xuất tương ứng và chọn phân đoạn mới.

1. Lựa chọn **Tiết kiệm** để lưu cấu hình hoặc **Lưu và chạy** để kiểm tra xuất này ngay lập tức.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]


[!INCLUDE [footer-include](includes/footer-banner.md)]
