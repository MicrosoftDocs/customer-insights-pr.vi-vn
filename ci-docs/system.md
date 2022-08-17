---
title: Xem cấu hình hệ thống
description: Tìm hiểu về cài đặt hệ thống trong Dynamics 365 Customer Insights.
ms.date: 08/09/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-status
- ci-system-about
- ci-system-general
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: 2498814a3d2e6330124fb97c036b9b310bcf1f7a
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246273"
---
# <a name="view-system-configuration"></a>Xem cấu hình hệ thống

Xem thông tin hệ thống, trạng thái hệ thống và sử dụng API.

## <a name="view-api-usage"></a>Xem mức sử dụng API

Xem chi tiết về việc sử dụng API thời gian thực và xem sự kiện nào đã xảy ra trong một khung thời gian nhất định.

1. Đi đến **Quản trị viên** > **Hệ thống** và chọn **Sử dụng API** chuyển hướng.

1. **Chọn khung thời gian** xem.

   Các **Sử dụng API** trang có ba phần:

   - **Lệnh gọi API** - biểu đồ hiển thị tổng số cuộc gọi đến API trong khung thời gian đã chọn.
   - **Truyền dữ liệu** - biểu đồ hiển thị lượng dữ liệu đã được chuyển qua API trong khung thời gian đã chọn.
   - **Hoạt động** - một bảng với các hàng cho mỗi hoạt động API có sẵn và thông tin chi tiết về việc sử dụng các hoạt động. Chọn một tên hoạt động để truy cập [tham chiếu API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

   Các hoạt động sử dụng [nhập dữ liệu thời gian thực](real-time-data-ingestion.md) chứa một biểu tượng hai mắt để xem việc sử dụng API trong thời gian thực.

   1. Chọn ống nhòm để mở **Sử dụng API thời gian thực** ngăn chứa chi tiết sử dụng cho hoạt động.
   1. **Chọn khung thời gian** xem.
   1. Sử dụng **Nhóm theo** để chọn cách trình bày tốt nhất các tương tác trong thời gian thực của bạn. Nhóm dữ liệu theo API **Phương pháp**, **thực thể đủ điều kiện** (thực thể đã nhập), **Được tạo bởi** (nguồn của sự kiện), **Kết quả** (thành công hay thất bại) hoặc **Mã lỗi**. Dữ liệu có sẵn dưới dạng biểu đồ lịch sử và dưới dạng bảng.

## <a name="view-system-information"></a>Xem thông tin hệ thống

Xem tên hiển thị môi trường, ID, khu vực, loại và ID phiên.

1. Đi đến **Quản trị viên** > **Hệ thống** và chọn **Về** chuyển hướng.

1. Để xem ngôn ngữ và quốc gia / khu vực, hãy chọn **Chung** chuyển hướng.

### <a name="update-preferred-language-or-countryregion"></a>Cập nhật ngôn ngữ ưa thích hoặc quốc gia / khu vực

Thấu hiểu khách hàng [hỗ trợ nhiều ngôn ngữ](/dynamics365/get-started/availability). Ứng dụng này sử dụng tùy chọn ngôn ngữ của bạn để hiển thị các thành phần như menu, văn bản nhãn và thông báo hệ thống bằng ngôn ngữ ưa thích của bạn.

Dữ liệu đã nhập và thông tin bạn đã nhập theo cách thủ công sẽ không được dịch.

1. Đi đến **Quản trị viên** > **Hệ thống** và chọn **Chung** chuyển hướng.

1. Để thay đổi ngôn ngữ ưa dùng của bạn, hãy chọn một **Ngôn ngữ** từ mục thả xuống.

1. Để thay đổi định dạng ưa dùng của bạn cho ngày, thời gian và số, hãy sử dụng mục thả xuống **Định dạng quốc gia/khu vực**. Bản xem trước định dạng được hiển thị. Hệ thống tự động gợi ý lựa chọn khi bạn chọn ngôn ngữ mới.

1. Chọn **Lưu.**

## <a name="view-system-status"></a>Xem trạng thái hệ thống

Theo dõi tiến trình của các tác vụ, nhập dữ liệu, xuất dữ liệu và một số quy trình sản phẩm quan trọng khác. Xem lại thông tin để đảm bảo tính đầy đủ của các nhiệm vụ và quy trình đang hoạt động của bạn.

1. Đi đến **Quản trị viên** > **Hệ thống** và chọn **Trạng thái** chuyển hướng.

   Trạng thái và thông tin xử lý cho các quy trình khác nhau hiển thị. Xem **Tên** của nhiệm vụ, **Trạng thái** lần chạy gần đây nhất và khi **Cập nhật mới nhất**.

1. Để xem chi tiết của vài lần chạy gần đây nhất, hãy chọn tác vụ hoặc tên quy trình.

1. Để xem chi tiết tiến độ cho một nhiệm vụ, hãy chọn trạng thái. Các **Chi tiết tiến độ** bảng hiển thị.

   :::image type="content" source="media/system-progress-details.png" alt-text="Ngăn chi tiết tiến trình hệ thống":::

1. Để xem chi tiết tiến độ cho tất cả các nhiệm vụ, hãy chọn **Toàn bộ quy trình làm việc**.

### <a name="status-definitions"></a>Định nghĩa trạng thái

Hệ thống sử dụng các trạng thái sau cho các tác vụ và quy trình:

|Trạng thái  |Định nghĩa  |
|---------|---------|
|Đã huỷ |Tác vụ hoặc quy trình đã bị người dùng hủy bỏ trước khi hoàn thành.   |
|Không thành công   |Tác vụ hoặc quy trình gặp lỗi.         |
|Thất bại  |Tác vụ hoặc quy trình không thành công.  |
|Chưa bắt đầu   |Nguồn dữ liệu chưa nhập dữ liệu nào hoặc tác vụ vẫn ở chế độ nháp.         |
|Đang xử lý  |Nhiệm vụ hoặc quy trình đang được thực hiện.  |
|Làm mới    |Nhiệm vụ hoặc quy trình đang được thực hiện. Để hủy thao tác này, hãy chọn **Làm mới** và **Hủy bỏ công việc**. Dừng làm mới một nhiệm vụ hoặc quy trình sẽ hoàn nguyên nó về trạng thái làm mới cuối cùng.       |
|Đã bỏ qua  |Tác vụ hoặc quy trình đã bị bỏ qua. Một hoặc nhiều quá trình xuôi dòng mà nhiệm vụ này phụ thuộc vào bị lỗi hoặc bị bỏ qua.|
|Thành công  |Tác vụ hoặc quy trình đã hoàn thành thành công. Đối với nguồn dữ liệu, cho biết dữ liệu đã được nhập thành công nếu thời gian được đề cập trong **Làm mới** cột.|
|Đã xếp hàng đợi | Quá trình xử lý được xếp hàng đợi và sẽ bắt đầu sau khi hoàn thành tất cả các tác vụ và quy trình ngược dòng. Để biết thêm thông tin, hãy xem [Làm mới quy trình](#refresh-processes).|

### <a name="refresh-processes"></a>Làm mới quy trình

Làm mới cho các tác vụ và quy trình được chạy theo [lịch trình đã định cấu hình](schedule-refresh.md).

|Quá trình  |Description  |
|---------|---------|
|Hoạt động  |Chạy thủ công (làm mới một lần). Phụ thuộc vào quá trình hợp nhất. Thông tin chi tiết phụ thuộc vào quá trình xử lý.|
|Liên kết phân tích |Chạy thủ công (làm mới một lần). Phụ thuộc vào các phân đoạn.  |
|Chuẩn bị phân tích |Chạy thủ công (làm mới một lần). Phụ thuộc vào các phân đoạn.  |
|Chuẩn bị dữ liệu   |Cần một thực thể để chạy. Nguồn dữ liệu thực thể phụ thuộc vào quá trình nhập. Các thực thể được làm giàu phụ thuộc vào việc làm giàu. Thực thể Khách hàng phụ thuộc vào việc hợp nhất.  |
|Nguồn dữ liệu   |Không phụ thuộc vào bất kỳ quy trình nào khác. So khớp phụ thuộc vào sự hoàn thành thành công của quy trình này.  |
|Nội dung tăng cường   |Chạy thủ công (làm mới một lần). Phụ thuộc vào quá trình hợp nhất. |
|Xuất khẩu các điểm đến |Chạy thủ công (làm mới một lần). Phụ thuộc vào các phân đoạn.  |
|Thông tin chuyên sâu |Chạy thủ công (làm mới một lần). Phụ thuộc vào các phân đoạn.  |
|Thông tin   |Phụ thuộc vào hợp nhất.   |
|Kết quả khớp |Phụ thuộc vào việc xử lý các nguồn dữ liệu được sử dụng trong định nghĩa so khớp.      |
|Measures  |Chạy thủ công (làm mới một lần). Phụ thuộc vào quá trình hợp nhất.  |
|Hợp nhất   |phụ thuộc vào sự hoàn thành thành công của quy trình so khớp. Phân khúc, biện pháp, làm phong phú, tìm kiếm, hoạt động, dự đoán và chuẩn bị dữ liệu phụ thuộc vào sự hoàn thành thành công của quy trình này.   |
|Hồ sơ   |Chạy thủ công (làm mới một lần). Phụ thuộc vào quá trình hợp nhất. |
|Tìm kiếm   |Chạy thủ công (làm mới một lần). Phụ thuộc vào quá trình hợp nhất. |
|Phân khúc  |Chạy thủ công (làm mới một lần). Phụ thuộc vào quá trình hợp nhất. Thông tin chi tiết phụ thuộc vào quá trình xử lý.|
|Hệ thống   |phụ thuộc vào sự hoàn thành thành công của quy trình so khớp. Phân khúc, biện pháp, làm phong phú, tìm kiếm, hoạt động, dự đoán và chuẩn bị dữ liệu phụ thuộc vào sự hoàn thành thành công của quy trình này.   |
|Người dùng  |Chạy thủ công (làm mới một lần). Phụ thuộc vào các thực thể.  |

Chọn trạng thái của một quá trình để xem chi tiết tiến độ của toàn bộ công việc mà nó đã thực hiện. Các quy trình làm mới ở trên có thể giúp hiểu những gì bạn có thể làm để giải quyết **Đã bỏ qua** hoặc **Đã xếp hàng** nhiệm vụ hoặc quy trình.


[!INCLUDE [footer-include](includes/footer-banner.md)]
