---
title: Cấu hình hệ thống trong thông tin chi tiết về đối tượng
description: Tìm hiểu về cài đặt hệ thống trong khả năng thông tin chi tiết về đối tượng Dynamics 365 Customer Insights.
ms.date: 06/02/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: nimagen
manager: shellyha
ms.openlocfilehash: 7dd72e6512cd87ac70235d21667399298408db21
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407333"
---
# <a name="system-configuration"></a>Cấu hình hệ thống

Trang **Hệ thống** bao gồm 4 tab: **Trạng thái**, **Lịch trình**, **Giới thiệu** và **Tổng quát**.

> [!div class="mx-imgBorder"]
> ![Trang hệ thống](media/system-tabs.png "Trang hệ thống")

## <a name="status-tab"></a>Tab Trạng thái

**Tab Trạng thái** cho phép bạn theo dõi tiến trình nhập dữ liệu, xuất dữ liệu và một vài quy trình sản phẩm quan trọng. Xem lại thông tin trên tab này để đảm bảo tính đầy đủ của các quy trình hiện hoạt.

Tab này bao gồm cả các bảng trạng thái cho **Nguồn dữ liệu**, **Quy trình hệ thống** và **Chuẩn bị dữ liệu**. Mỗi bảng theo dõi **Tên** của nhiệm vụ và thực thể tương ứng, **Trạng thái** của lần chạy gần đây nhất và thời điểm **Cập nhật gần đây nhất**.

Xem chi tiết về một vài lần chạy gần đây nhất của nhiệm vụ bằng cách chọn tên nhiệm vụ.

### <a name="status-types"></a>Các loại trạng thái

Có 6 loại trạng thái cho các nhiệm vụ. Các loại trạng thái sau đây cũng hiển thị trên các trang *So khớp*, *Hợp nhất*, *Nguồn dữ liệu*, *Phân khúc*, *Biện pháp*, *Nội dung phong phú*, *Hoạt động* và *Dự đoán*:

- **Xử lý:** Nhiệm vụ đang được tiến hành. Trạng thái có thể thay đổi thành Thành công hoặc Thất bại.
- **Thành công:** Nhiệm vụ hoàn thành thành công.
- **Bỏ qua:** Nhiệm vụ đã bị bỏ qua. Một hoặc nhiều quá trình xuôi dòng mà nhiệm vụ này phụ thuộc vào bị lỗi hoặc bị bỏ qua.
- **Lỗi:** Xử lý nhiệm vụ không thành công.
- **Đã hủy:** Quá trình xử lý đã bị hủy bởi người dùng trước khi hoàn thành.
- **Xếp hàng:** Quá trình xử lý được xếp hàng và sẽ bắt đầu khi tất cả các nhiệm vụ hạ nguồn được hoàn thành. Để biết thêm thông tin, hãy xem [chính sách Làm mới](#refresh-policies).

### <a name="refresh-policies"></a>Chính sách làm mới

Danh sách này hiển thị các chính sách làm mới cho từng quy trình chính:

- **Nguồn dữ liệu:** Chạy theo [lịch trình đã đặt cấu hình](#schedule-tab). Không phụ thuộc vào bất kỳ quy trình nào khác. So khớp phụ thuộc vào sự hoàn thành thành công của quy trình này.
- **So khớp:** Chạy theo [lịch trình đã đặt cấu hình](#schedule-tab). Phụ thuộc vào việc xử lý các nguồn dữ liệu được sử dụng trong định nghĩa so khớp. Hợp nhất phụ thuộc vào sự hoàn thành thành công của quy trình này.
- **Hợp nhất**: Chạy theo [lịch trình đã đặt cấu hình](#schedule-tab). phụ thuộc vào sự hoàn thành thành công của quy trình so khớp. Phân đoạn, biện pháp, làm phong phú, tìm kiếm, hoạt động, dự đoán và chuẩn bị dữ liệu phụ thuộc vào sự hoàn thành thành công của quy trình này.
- **Phân đoạn**: Chạy thủ công (làm mới một lần) và theo [lịch trình đã đặt cấu hình](#schedule-tab). Phụ thuộc vào Hợp nhất. Thông tin chi tiết phụ thuộc vào quá trình xử lý.
- **Biện pháp**: Chạy thủ công (làm mới một lần) và theo [lịch trình đã đặt cấu hình](#schedule-tab). Phụ thuộc vào Hợp nhất.
- **Hoạt động**: Chạy thủ công (làm mới một lần) và theo [lịch trình đã đặt cấu hình](#schedule-tab). Phụ thuộc vào Hợp nhất.
- **Làm phong phú**: Chạy thủ công (làm mới một lần) và theo [lịch trình đã đặt cấu hình](#schedule-tab). Phụ thuộc vào Hợp nhất.
- **Tìm kiếm**: Chạy thủ công (làm mới một lần) và theo [lịch trình đã đặt cấu hình](#schedule-tab). Phụ thuộc vào Hợp nhất.
- **Chuẩn bị dữ liệu:**: Chạy theo [lịch trình đã đặt cấu hình](#schedule-tab). Phụ thuộc vào Hợp nhất.
- **Thông tin chi tiết**: Chạy thủ công (làm mới một lần) và theo [lịch trình đã đặt cấu hình](#schedule-tab). Phụ thuộc vào Phân đoạn.

Chọn trạng thái của một nhiệm vụ để xem chi tiết về tiến trình của toàn bộ công việc. Các chính sách làm mới ở trên có thể giúp hiểu những gì bạn có thể làm để giải quyết nhiệm vụ **Bỏ qua** hoặc **Xếp hàng**.

## <a name="schedule-tab"></a>Tab Lập lịch trình

Sử dụng tab **Lịch trình** để lên lịch làm mới tự động tất cả [nguồn dữ liệu đã nhập](data-sources.md). Tự động làm mới giúp đảm bảo rằng cập nhật từ các nguồn dữ liệu được phản ánh trong hồ sơ khách hàng hợp nhất.

1. Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Quản trị** > **Hệ thống** và chọn tab **Lịch trình**.

2. Trạng thái mặc định cho làm mới theo lịch trình là **Tắt**. Để bật làm mới theo lịch trình, thay chuyển nút ở đầu màn hình thành **Bật**.

3. Chọn tùy chọn làm mới **Hàng tuần** (mặc định) và **Hàng ngày**. Nếu bạn có ý định lên lịch làm mới hàng tuần, hãy chọn một hoặc nhiều ngày mà bạn muốn chạy quy trình làm mới.

4. Đặt **Múi giờ**, sau đó sử dụng mục thả xuống **Thời gian** để đặt thời gian làm mới. Khi bạn đã hoàn tất, chọn **Đặt**. Nếu bạn muốn lên lịch nhiều lần làm mới trong một ngày, hãy chọn **Thêm thời gian khác**.

5. Chọn **Lưu** để áp dụng thay đổi.

## <a name="about-tab"></a>Giới thiệu về tab

Tab **Giới thiệu** chứa **Tên hiển thị**, **ID môi trường** hiện hoạt, **Vùng** và **ID phiên** của tổ chức bạn. Nếu bạn có nhiều môi trường làm việc, bạn nên đặt cho mỗi môi trường một tên hiển thị dễ nhận dạng.

## <a name="general-tab"></a>Tab tổng quát

Có hai tùy chọn trên tab **Chung**, **Ngôn ngữ** và **định dạng Quốc gia/khu vực**.

Ứng dụng này [hỗ trợ một số ngôn ngữ](supported-languages.md). Để thay đổi ngôn ngữ ưa dùng của bạn, hãy chọn một **Ngôn ngữ** từ mục thả xuống.

Để thay đổi định dạng ưa dùng của bạn cho ngày, thời gian và số, hãy sử dụng mục thả xuống **Định dạng quốc gia/khu vực**. Một bản xem trước định dạng được hiển thị trong trường này. Hệ thống sẽ tự động đề xuất lựa chọn khi bạn chọn ngôn ngữ mới.

Chọn **Lưu** để xác nhận lựa chọn của bạn.

## <a name="api-usage-tab"></a>Tab sử dụng API

Tìm chi tiết về mức sử dụng API trong thời gian thực và xem sự kiện nào đã xảy ra trong khoảng thời gian nhất định. Để biết thêm thông tin, hãy xem [Nhập dữ liệu trong thời gian thực](real-time-data-ingestion.md).
