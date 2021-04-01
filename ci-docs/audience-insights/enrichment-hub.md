---
title: Tăng cường hồ sơ khách hàng hợp nhất
description: Sử dụng các khả năng để tăng cường dữ liệu khách hàng của bạn.
ms.date: 11/02/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 36e6f7f8fcd64fc2591e913910918b83bf27567b
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597721"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Làm phong phú hồ sơ khách hàng (Xem trước)

Sử dụng dữ liệu từ các nguồn như Microsoft và các đối tác khác để làm phong phú dữ liệu khách hàng của bạn.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Trang trung tâm làm phong phú":::

Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Dữ liệu** > **Tăng cường** để làm việc với các tùy chọn tăng cường.    
Bạn cần có quyền của Người đóng góp hoặc Quản trị viên để tạo hoặc chỉnh sửa phần nội dung phong phú. Để biết thêm thông tin, hãy xem [Quyền](permissions.md).

Trên tab **Khám phá**, bạn sẽ tìm thấy những nội dung phong phú sau:

- [Thương hiệu](enrichment-microsoft-graph.md) do Microsoft Graph cung cấp
- [Sở thích](enrichment-microsoft-graph.md) do Microsoft Graph cung cấp
- [Dữ liệu công ty](enrichment-leadspace.md) do Leadspace cung cấp
- [Dữ liệu nhân khẩu học](enrichment-experian.md) do Experian cung cấp
- [Dữ liệu vị trí](enrichment-here.md) do HERE Technologies cung cấp
- [Dữ liệu tùy chỉnh](enrichment-SFTP-custom-import.md) thông qua Secure File Transfer Protocol (SFTP)

Trên tab **Nội dung phong phú**, bạn có thể xem các nội dung phong phú mình đã đặt cấu hình và chỉnh sửa thuộc tính.

## <a name="manage-existing-enrichments"></a>Quản lý nội dung phong phú hiện có

Chuyển đến **Nội dung phong phú của tôi** để xem tất cả nội dung phong phú được cấu hình. Mỗi nội dung phong phú được biểu thị bằng một hàng bao gồm thông tin bổ sung về nội dung phong phú đó.

Chọn nội dung phong phú để xem các tùy chọn có sẵn. Ngoài ra, bạn có thể chọn dấu ba chấm (...) trên mục danh sách để xem các tùy chọn.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Các tùy chọn quản lý nội dung phong phú trong danh sách nội dung phong phú":::

- **Xem** thông tin chi tiết về nội dung phong phú với một số hồ sơ khách hàng phong phú.
- **Chỉnh sửa** cấu hình nội dung phong phú.
- **Chạy** sự nội dung tăng cường để cập nhật hồ sơ khách hàng với dữ liệu mới nhất.
- **Vô hiệu hóa** nội dung phong phú hiện có để nội dung đó không làm mới tự động với mỗi lần làm mới theo lịch. Dữ liệu từ lần làm mới thành công gần nhất sẽ tiếp tục hiển thị. **Kích hoạt** nội dung phong phú không hoạt động để khởi động lại tính năng làm mới tự động với mỗi lần làm mới theo lịch.
- **Xóa** nội dung tăng cường.

Bạn có thể chạy hoặc hủy kích hoạt nhiều nội dung tăng cường cùng một lúc bằng cách chọn trong danh sách. Xem và chỉnh sửa các tùy chọn hiện không thực hiện được dưới dạng hành động hàng loạt và tính năng này chỉ hoạt động với một nội dung phong phú mỗi lần.


[!INCLUDE[footer-include](../includes/footer-banner.md)]