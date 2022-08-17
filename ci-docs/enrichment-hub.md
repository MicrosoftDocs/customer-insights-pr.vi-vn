---
title: Tổng quan về làm giàu dữ liệu (xem trước)
description: Sử dụng các khả năng từ Microsoft và các dịch vụ của bên thứ ba khác để làm phong phú thêm dữ liệu khách hàng của bạn.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-enrichments
- ci-enrichment-details
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: 0c2a900190b4ab6e93098d05a2fd66bcd2b847fd
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245905"
---
# <a name="data-enrichment-preview-overview"></a>Tổng quan về làm giàu dữ liệu (xem trước)

Sử dụng dữ liệu từ các nguồn như Microsoft và các đối tác khác để tăng cường dữ liệu khách hàng của bạn. Các dữ liệu tăng cường của bên thứ ba được đặt cấu hình bằng cách sử dụng [kết nối](connections.md) do quản trị viên thiết lập bằng thông tin xác thực và cho phép truyền dữ liệu. Quản trị viên và người đóng góp có thể sử dụng kết nối này để đặt cấu hình nội dung tăng cường.  

## <a name="multiple-enrichments-of-the-same-type"></a>Nhiều dữ liệu tăng cường thuộc cùng loại

Thực thể cần tăng cường sẽ được chỉ định trong quá trình đặt cấu hình dữ liệu tăng cường. Nhờ đó, bạn có thể chỉ cần tăng cường một tập hợp con các cấu hình của mình. Ví dụ: chỉ tăng cường dữ liệu cho một phân khúc cụ thể. Bạn có thể đặt cấu hình một số dữ liệu tăng cường thuộc cùng loại và sử dụng lại cùng một kết nối. Một số dữ liệu tăng cường sẽ có giới hạn về số lượng dữ liệu tăng cường thuộc cùng loại có thể được tạo ra. Các giới hạn và việc sử dụng hiện tại có thể được nhìn thấy trên mỗi ô trên **Phát hiện** tab của **Làm giàu** trang.

## <a name="enrich-data-sources-before-unification"></a>Làm phong phú nguồn dữ liệu trước khi hợp nhất

Bạn có thể làm giàu dữ liệu khách hàng của mình trước khi hợp nhất dữ liệu để giúp tăng chất lượng của đối sánh dữ liệu. Để biết thêm thông tin, hãy xem [nguồn dữ liệu làm giàu](data-sources-enrichment.md).

## <a name="create-an-enrichment"></a>Tạo nội dung tăng cường

Bạn cần có Người đóng góp hoặc Quản trị viên [sự cho phép](permissions.md) để tạo hoặc chỉnh sửa các nội dung phong phú.

Chuyển tới **Dữ liệu** > **Dữ liệu tăng cường**. Các **Phát hiện** tab hiển thị tất cả các tùy chọn bổ sung được hỗ trợ.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Trang trung tâm tăng cường.":::

# <a name="individual-consumers-b-to-c"></a>[Người tiêu dùng cá nhân (B2C)](#tab/b2c)

- [Nhận dạng AbiliTec](enrichment-liveramp.md) được cung cấp bởi LiveRamp AbiliTec
- [Thương hiệu](enrichment-microsoft.md) do Microsoft cung cấp
- [Dữ liệu nhân khẩu học](enrichment-experian.md) do Experian cung cấp
- [Địa chỉ nâng cao](enrichment-enhanced-addresses.md) do Microsoft cung cấp
- [Sở thích](enrichment-microsoft.md) do Microsoft cung cấp
- [Dữ liệu vị trí](enrichment-azure-maps.md) cung cấp bởi Microsoft Azure Bản đồ
- [Dữ liệu vị trí](enrichment-here.md) do HERE Technologies cung cấp
- [Dữ liệu tùy chỉnh SFTP](enrichment-SFTP-custom-import.md) thông qua Giao thức truyền tệp an toàn (SFTP)

# <a name="business-accounts-b-to-b"></a>[Tài khoản doanh nghiệp (B2B)](#tab/b2b)

- [Dữ liệu tương tác tài khoản](enrichment-office.md) do Microsoft cung cấp
- [Dữ liệu công ty](enrichment-dnb.md) cung cấp bởi Dun & Bradstreet
- [Dữ liệu công ty](enrichment-leadspace.md) do Leadspace cung cấp
- [Địa chỉ nâng cao](enrichment-enhanced-addresses.md) do Microsoft cung cấp
- [Dữ liệu công ty nâng cao](enrichment-enhanced-company-data.md) do Microsoft cung cấp
- [Dữ liệu vị trí](enrichment-azure-maps.md) cung cấp bởi Microsoft Azure Bản đồ
- [Dữ liệu vị trí](enrichment-here.md) do HERE Technologies cung cấp
- [Dữ liệu tùy chỉnh SFTP](enrichment-SFTP-custom-import.md) thông qua Giao thức truyền tệp an toàn (SFTP)

---

## <a name="manage-existing-enrichments"></a>Quản lý dữ liệu tăng cường hiện có

Chuyển tới **Dữ liệu** > **Dữ liệu tăng cường**. Trên **Sự làm giàu của tôi**, xem các phần bổ sung đã định cấu hình, trạng thái của họ, số lượng khách hàng đã bổ sung và lần cuối cùng dữ liệu được làm mới. Bạn có thể sắp xếp danh sách bổ sung theo bất kỳ cột nào hoặc sử dụng hộp tìm kiếm để tìm kiếm bổ sung mà bạn muốn quản lý.

Chọn phần bổ sung để xem các hành động có sẵn.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Các tùy chọn quản lý dữ liệu tăng cường trong danh sách dữ liệu tăng cường.":::

- **Xem** thông tin chi tiết về dữ liệu tăng cường với số hồ sơ khách hàng được tăng cường.
- **Chỉnh sửa** cấu hình dữ liệu tăng cường.
- [**Chạy**](#run-or-refresh-enrichments) sự phong phú để cập nhật hồ sơ khách hàng với dữ liệu mới nhất. Chạy nhiều phần bổ sung cùng một lúc bằng cách chọn chúng trong danh sách.
- **Hoạt động** hoặc **Hủy kích hoạt** một sự làm giàu. Các phần bổ sung không hoạt động sẽ không được làm mới trong một [làm mới theo lịch trình](schedule-refresh.md).
- **Xóa** dữ liệu tăng cường.

Bạn cũng có thể tạo [phân đoạn](segments.md) hoặc [đo](measures.md) từ làm giàu.

## <a name="run-or-refresh-enrichments"></a>Chạy hoặc làm mới tính năng bổ sung

Sau khi chạy, các phần bổ sung có thể được làm mới theo lịch trình tự động hoặc làm mới theo cách thủ công theo yêu cầu.

1. Để làm mới một hoặc nhiều bổ sung theo cách thủ công, hãy chọn chúng và chọn **Chạy**. Đến [lên lịch làm mới tự động](schedule-refresh.md), đi đến **Quản trị viên** > **Hệ thống** > **Lịch trình**. Thời gian xử lý phụ thuộc vào kích thước dữ liệu khách hàng của bạn.

1. Tùy ý, [xem tiến trình của quá trình làm giàu](#see-the-progress-of-the-enrichment-process).

1. Sau khi quá trình làm giàu hoàn tất, hãy chuyển đến **Sự làm giàu của tôi** để xem lại dữ liệu hồ sơ khách hàng mới được bổ sung, thời gian cập nhật lần cuối và số lượng hồ sơ được bổ sung.

1. Chọn phần bổ sung để xem [kết quả làm giàu](#view-enrichment-results).

### <a name="see-the-progress-of-the-enrichment-process"></a>Xem tiến trình của quy trình tăng cường

Bạn có thể tìm thấy thông tin chi tiết về quy trình tăng cường, bao gồm trạng thái của quy trình và các vấn đề tiềm ẩn trong khi làm mới hoặc sau khi hoàn thành quy trình làm mới. Hiểu các quy trình nào có liên quan để làm mới quy trình tăng cường và mất bao lâu để chạy các quy trình đó. Trạng thái tăng cường được hỗ trợ cho Experian, Leadspace, HERE Technologies, SFTP Import và Azure Maps.

1. Chuyển tới **Dữ liệu** > **Dữ liệu tăng cường**.
1. Bên trong **Sự làm giàu của tôi**, chọn trạng thái của phần bổ sung để mở một ngăn bên.
1. Trong ngăn **Chi tiết tiến trình**, hãy bung rộng phần **Nội dung tăng cường**.
1. Trong phần tăng cường bạn muốn xem tiến trình, hãy chọn **Xem chi tiết**.
1. Trong ngăn **Chi tiết công việc**, chọn **Hiển thị chi tiết** để xem các quy trình có liên quan đến việc cập nhật nội dung tăng cường và trạng thái của chúng.

[!INCLUDE [progress-details-pane](includes/progress-details-pane.md)]

## <a name="view-enrichment-results"></a>Xem kết quả bổ sung

Sau khi hoàn thành quá trình làm giàu, hãy xem lại kết quả làm giàu.

1. Chuyển tới **Dữ liệu** > **Dữ liệu tăng cường**.
1. Bên trong **Sự làm giàu của tôi**, chọn phần bổ sung mà bạn muốn xem.

Tất cả các phần bổ sung hiển thị thông tin cơ bản như số lượng cấu hình được bổ sung và số lượng cấu hình được bổ sung theo thời gian. Các **Phong phú khách hàng xem trước** ô hiển thị một mẫu của thực thể làm giàu được tạo. Để xem chế độ xem chi tiết, hãy chọn **Xem thêm** và chọn **Dữ liệu** chuyển hướng.

:::image type="content" source="media/enrichments-results.png" alt-text="Trang kết quả làm giàu.":::

Nếu có, **Số lượng khách hàng làm giàu theo lĩnh vực** cung cấp thông tin chi tiết về phạm vi bao phủ của từng trường được bổ sung chi tiết.

Một số làm giàu cũng hiển thị thông tin cụ thể cho loại làm giàu. Để biết thêm thông tin, hãy xem tài liệu liên quan.

[!INCLUDE [footer-include](includes/footer-banner.md)]
