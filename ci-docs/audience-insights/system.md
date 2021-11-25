---
title: Cấu hình hệ thống trong thông tin chi tiết về đối tượng
description: Tìm hiểu về cài đặt hệ thống trong khả năng thông tin chi tiết về đối tượng Dynamics 365 Customer Insights.
ms.date: 11/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 1b790106f8b9617d0c1f244e1d15a74c7ef9a82b
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732396"
---
# <a name="system-configuration"></a>Cấu hình hệ thống

Để truy cập cấu hình hệ thống trong thông tin chi tiết về đối tượng, từ thanh điều hướng bên trái, hãy chọn **quản trị viên** > **Hệ thống** để xem danh sách các tác vụ và quy trình của hệ thống.

Trang **Hệ thống** bao gồm các tab sau:
- [Trạng thái](#status-tab)
- [Lịch trình](#schedule-tab)
- [Sử dụng API](#api-usage-tab)
- [Giới thiệu](#about-tab)
- [Chung](#general-tab)
- [Bảo mật](#security-tab)

:::image type="content" source="media/system-tabs.png" alt-text="Các tab thiết đặt trên trang hệ thống.":::

## <a name="status-tab"></a>Tab Trạng thái

Các **Tab trạng thái** cho phép bạn theo dõi tiến trình của các tác vụ, quá trình nhập dữ liệu, xuất dữ liệu và một số quy trình sản phẩm quan trọng khác. Xem lại thông tin trên tab này để đảm bảo tính hoàn chỉnh của các tác vụ và quy trình đang hoạt động của bạn.

Tab này bao gồm các bảng với trạng thái và thông tin xử lý cho các quy trình khác nhau. Mỗi bảng theo dõi **Tên** của nhiệm vụ và thực thể tương ứng, **Trạng thái** của lần chạy gần đây nhất và thời điểm **Cập nhật gần đây nhất**. Bạn có thể xem chi tiết của vài lần chạy gần đây nhất bằng cách chọn tác vụ hoặc tên quy trình. 

Chọn trạng thái bên cạnh nhiệm vụ hoặc quy trình trong **Trạng thái** cột để mở **Chi tiết tiến độ** ngăn.

   :::image type="content" source="media/system-progress-details.png" alt-text="Ngăn chi tiết tiến trình hệ thống":::

### <a name="status-definitions"></a>Định nghĩa trạng thái

Hệ thống sử dụng các trạng thái sau cho các tác vụ và quy trình:

|Trạng thái  |Định nghĩa  |
|---------|---------|
|Đã huỷ |Người dùng đã hủy quá trình xử lý trước khi quá trình kết thúc.   |
|Không thành công   |Phiên nhập dữ liệu gặp lỗi.         |
|Thất bại  |Xử lý không thành công.  |
|Chưa bắt đầu   |Nguồn dữ liệu chưa nhập dữ liệu nào hoặc vẫn ở chế độ nháp.         |
|Đang xử lý  |Nhiệm vụ hoặc quy trình đang được thực hiện.  |
|Làm mới    |Đang nhập dữ liệu. Bạn có thể hủy thao tác này bằng cách chọn **Ngừng làm mới** trong cột **Hành động**. Dừng việc làm mới nguồn dữ liệu sẽ hoàn nguyên nguồn dữ liệu về trạng thái làm mới cuối cùng.       |
|Đã bỏ qua  |Tác vụ hoặc quy trình đã bị bỏ qua. Một hoặc nhiều quá trình xuôi dòng mà nhiệm vụ này phụ thuộc vào bị lỗi hoặc bị bỏ qua.|
|Thành công  |Tác vụ hoặc quy trình đã hoàn thành thành công. Đối với nguồn dữ liệu, cho biết dữ liệu đã được nhập thành công nếu thời gian được đề cập trong **Làm mới** cột.|
|Đã xếp hàng đợi | Quá trình xử lý được xếp hàng đợi và sẽ bắt đầu sau khi hoàn thành tất cả các tác vụ và quy trình ngược dòng. Để biết thêm thông tin, hãy xem [Làm mới quy trình](#refresh-processes).|

### <a name="refresh-processes"></a>Làm mới quy trình

Làm mới cho các tác vụ và quy trình được chạy theo [lịch trình đã định cấu hình](#schedule-tab). 

|Xử lý  |Mô tả  |
|---------|---------|
|Hoạt động  |Chạy thủ công (làm mới một lần). Phụ thuộc vào quá trình hợp nhất. Thông tin chi tiết phụ thuộc vào quá trình xử lý.|
|Liên kết phân tích |Chạy thủ công (làm mới một lần). Phụ thuộc vào các phân đoạn.  |
|Chuẩn bị phân tích |Chạy thủ công (làm mới một lần). Phụ thuộc vào các phân đoạn.  |
|Chuẩn bị dữ liệu   |Phụ thuộc vào hợp nhất.   |
|Nguồn dữ liệu   |Không phụ thuộc vào bất kỳ quy trình nào khác. So khớp phụ thuộc vào sự hoàn thành thành công của quy trình này.  |
|Nội dung tăng cường   |Chạy thủ công (làm mới một lần). Phụ thuộc vào quá trình hợp nhất. |
|Xuất khẩu các điểm đến |Chạy thủ công (làm mới một lần). Phụ thuộc vào các phân đoạn.  |
|Thông tin chuyên sâu |Chạy thủ công (làm mới một lần). Phụ thuộc vào các phân đoạn.  |
|Thông tin   |Phụ thuộc vào hợp nhất.   |
|Kết quả khớp |Phụ thuộc vào việc xử lý các nguồn dữ liệu được sử dụng trong định nghĩa so khớp.      |
|Biện pháp  |Chạy thủ công (làm mới một lần). Phụ thuộc vào quá trình hợp nhất.  |
|Hợp nhất   |phụ thuộc vào sự hoàn thành thành công của quy trình so khớp. Phân khúc, biện pháp, làm phong phú, tìm kiếm, hoạt động, dự đoán và chuẩn bị dữ liệu phụ thuộc vào sự hoàn thành thành công của quy trình này.   |
|Hồ sơ   |Chạy thủ công (làm mới một lần). Phụ thuộc vào quá trình hợp nhất. |
|Tìm kiếm   |Chạy thủ công (làm mới một lần). Phụ thuộc vào quá trình hợp nhất. |
|Phân khúc  |Chạy thủ công (làm mới một lần). Phụ thuộc vào quá trình hợp nhất. Thông tin chi tiết phụ thuộc vào quá trình xử lý.|
|Hệ thống   |phụ thuộc vào sự hoàn thành thành công của quy trình so khớp. Phân khúc, biện pháp, làm phong phú, tìm kiếm, hoạt động, dự đoán và chuẩn bị dữ liệu phụ thuộc vào sự hoàn thành thành công của quy trình này.   |
|Người dùng  |Chạy thủ công (làm mới một lần). Phụ thuộc vào các thực thể.  |

Chọn trạng thái của một quá trình để xem chi tiết tiến độ của toàn bộ công việc mà nó đã thực hiện. Các quy trình làm mới ở trên có thể giúp hiểu những gì bạn có thể làm để giải quyết **Đã bỏ qua** hoặc **Đã xếp hàng** nhiệm vụ hoặc quy trình.

## <a name="schedule-tab"></a>Tab Lập lịch trình

Sử dụng tab **Lịch trình** để lên lịch làm mới tự động tất cả [nguồn dữ liệu đã nhập](data-sources.md). Tự động làm mới giúp đảm bảo rằng cập nhật từ các nguồn dữ liệu được phản ánh trong hồ sơ khách hàng hợp nhất.

1. Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Quản trị** > **Hệ thống** và chọn tab **Lịch trình**.

2. Trạng thái mặc định cho làm mới theo lịch trình là **Tắt**. Để bật làm mới theo lịch trình, thay chuyển nút ở đầu màn hình thành **Bật**.

3. Chọn tùy chọn làm mới **Hàng tuần** (mặc định) và **Hàng ngày**. Nếu bạn có ý định lên lịch làm mới hàng tuần, hãy chọn một hoặc nhiều ngày mà bạn muốn chạy quy trình làm mới.

4. Đặt **Múi giờ**, sau đó sử dụng mục thả xuống **Thời gian** để đặt thời gian làm mới. Khi bạn đã hoàn tất, chọn **Đặt**. Nếu bạn muốn lên lịch nhiều lần làm mới trong một ngày, hãy chọn **Thêm thời gian khác**.

5. Chọn **Lưu** để áp dụng thay đổi.

## <a name="about-tab"></a>Giới thiệu về tab

Tab **Giới thiệu** chứa **Tên hiển thị**, **ID môi trường** hiện hoạt, **Vùng** và **ID phiên** của tổ chức bạn. Nếu bạn có nhiều môi trường làm việc, bạn nên đặt cho mỗi môi trường một tên hiển thị dễ nhận dạng.

## <a name="general-tab"></a>Tab Tổng quát

Bạn có thể thay đổi ngôn ngữ và định dạng quốc gia/khu vực trên tab **Tổng quát**.

Thấu hiểu khách hàng [hỗ trợ nhiều ngôn ngữ](/dynamics365/get-started/availability). Ứng dụng này sử dụng tùy chọn ngôn ngữ của bạn để hiển thị các thành phần như menu, văn bản nhãn và thông báo hệ thống bằng ngôn ngữ ưa thích của bạn.

Dữ liệu đã nhập và thông tin bạn đã nhập theo cách thủ công sẽ không được dịch.

### <a name="update-the-settings"></a>Cập nhật thiết đặt

Để thay đổi ngôn ngữ ưa dùng của bạn, hãy chọn một **Ngôn ngữ** từ mục thả xuống.

Để thay đổi định dạng ưa dùng của bạn cho ngày, thời gian và số, hãy sử dụng mục thả xuống **Định dạng quốc gia/khu vực**. Một bản xem trước định dạng được hiển thị trong trường này. Hệ thống sẽ tự động đề xuất lựa chọn khi bạn chọn ngôn ngữ mới.

Chọn **Lưu** để xác nhận lựa chọn của bạn.

## <a name="api-usage-tab"></a>Tab sử dụng API

Tìm chi tiết về việc sử dụng API thời gian thực và xem sự kiện nào đã xảy ra trong một khung thời gian nhất định. Bạn chọn khung thời gian trong menu thả xuống **Chọn khung thời gian**. 

**Sử dụng API** chứa ba phần: 
- **Lệnh gọi API** - biểu đồ hiển thị tổng số cuộc gọi đến API trong khung thời gian đã chọn.

- **Truyền dữ liệu** - biểu đồ hiển thị lượng dữ liệu đã được chuyển qua API trong khung thời gian đã chọn.

-  **Hoạt động** - một bảng với các hàng cho mỗi hoạt động API có sẵn và thông tin chi tiết về việc sử dụng các hoạt động. Bạn có thể chọn một tên hoạt động để truy cập [tham chiếu API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

   Các hoạt động sử dụng [nhập dữ liệu thời gian thực](real-time-data-ingestion.md) chứa một nút có biểu tượng ống nhòm để xem việc sử dụng API trong thời gian thực. Chọn nút để mở ngăn bên chứa chi tiết sử dụng cho việc sử dụng API thời gian thực trong môi trường hiện tại.   
   Sử dụng hộp **Nhóm theo** trong ngăn **Sử dụng API thời gian thực** để chọn cách tốt nhất để trình bày các tương tác trong thời gian thực của bạn. Bạn có thể nhóm dữ liệu theo phương pháp API, tên đủ điều kiện của thực thể (thực thể được nhập), tạo bởi (nguồn sự kiện), kết quả (thành công hay thất bại) hoặc mã lỗi. Dữ liệu có sẵn dưới dạng biểu đồ lịch sử và dưới dạng bảng.

## <a name="security-tab"></a>Tab Bảo mật

Tab **Bảo mật** cho phép bạn liên kết và quản lý [Tín liệu khóa Azure](/azure/key-vault/general/basic-concepts) của riêng bạn với môi trường.
Có thể dùng Key vault chuyên dụng để chia giai đoạn và sử dụng bí mật trong ranh giới tuân thủ của một tổ chức. Thông tin chuyên sâu về đối tượng có thể sử dụng bí mật trong Azure Key Vault để [thiết lập kết nối](connections.md) cho các hệ thống của bên thứ ba.

Để biết thêm thông tin, hãy xem [Mang tín liệu khóa Azure của riêng bạn](use-azure-key-vault.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
