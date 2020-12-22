---
title: Thực thể và tập hợp dữ liệu
description: Xem dữ liệu trên trang Thực thể.
ms.date: 04/16/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: e3f41c0424b2cd756d72ae6af9d5225ebba92628
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407300"
---
# <a name="entities-in-audience-insights"></a>Các thực thể trong thông tin chi tiết về đối tượng

Sau khi [định cấu hình nguồn dữ liệu](data-sources.md), hãy truy cập trang **Thực thể** để đánh giá chất lượng của dữ liệu được nhập. Các thực thể được coi là tập hợp dữ liệu. Nhiều chức năng của Dynamics 365 Customer Insights được xây dựng liên quan đến những thực thể này. Việc xem xét chúng một cách chi tiết có thể giúp bạn xác thực đầu ra của những khả năng.

Trang **Thực thể** liệt kê các thực thể và bao gồm một số cột:

- **Tên**: Tên của thực thể dữ liệu của bạn. Nếu bạn thấy biểu tượng cảnh báo bên cạnh tên thực thể, điều đó có nghĩa là dữ liệu cho thực thể đó không tải thành công.
- **Nguồn**: Hiển thị loại nguồn dữ liệu được nhập vào thực thể
- **Người tạo**: Tên của người đã tạo thực thể
- **Ngày tạo**: Ngày và giờ tạo thực thể
- **Người cập nhật**: Tên của người cập nhật thực thể
- **Cập nhật lần cuối**: Ngày và giờ của bản cập nhật cuối cùng của thực thể
- **Làm mới lần cuối**: Ngày và giờ làm mới dữ liệu cuối cùng

## <a name="exploring-a-specific-entitys-data"></a>Khám phá dữ liệu của một thực thể cụ thể

Chọn một thực thể để khám phá các trường và bản ghi khác nhau được bao gồm trong thực thể đó.

> [!div class="mx-imgBorder"]
> ![Chọn một thực thể](media/data-manager-entities-data.png "Chọn một thực thể")

- Tab **Dữ liệu** được chọn theo mặc định và hiển thị chi tiết danh sách bảng về các bản ghi cá nhân của thực thể.

> [!div class="mx-imgBorder"]
> ![Bảng trường](media/data-manager-entities-fields.PNG "Bảng trường")

- Tab **Trường** hiển thị bảng để đánh giá chi tiết cho thực thể đã chọn, chẳng hạn như tên trường, loại dữ liệu và loại. Cột **Loại** hiển thị các loại liên kết Common Data Model được tự động xác định bởi hệ thống hoặc [được ánh xạ thủ công](map-entities.md) bởi người dùng. Đây là các loại ngữ nghĩa có thể khác với các loại dữ liệu của thuộc tính — ví dụ: trường *Email* dưới đây có loại dữ liệu *Văn bản* nhưng kiểu Common Data Model có thể là *Email* hoặc *Địa chỉ email*.

> [!NOTE]
> Cả hai bảng chỉ hiển thị một mẫu dữ liệu của thực thể của bạn. Để xem tập dữ liệu đầy đủ, hãy đi tới trang **Nguồn dữ liệu**, chọn một thực thể, chọn **Chỉnh sửa**, sau đó xem dữ liệu của thực thể này bằng trình chỉnh sửa Power Query như giải thích trong [Nguồn dữ liệu](data-sources.md).

Để tìm hiểu thêm về dữ liệu được nhập vào thực thể, cột **Tóm tắt** cung cấp cho bạn một số đặc điểm quan trọng của dữ liệu, chẳng hạn như giá trị rỗng, các giá trị còn thiếu, giá trị duy nhất, số lượng và phân phối, như áp dụng cho dữ liệu của bạn.

Chọn biểu tượng biểu đồ để xem tóm tắt dữ liệu.

> [!div class="mx-imgBorder"]
> ![Biểu tượng tóm tắt](media/data-manager-entities-summary.png "Bảng tóm tắt dữ liệu")

### <a name="next-step"></a>Bước tiếp theo

Xem chủ đề [Hợp nhất](data-unification.md) để tìm hiểu cách *ánh xạ*, *so khớp* và *hợp nhất* dữ liệu đã nhập.
