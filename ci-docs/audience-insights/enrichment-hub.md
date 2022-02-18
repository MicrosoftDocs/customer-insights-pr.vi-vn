---
title: Tăng cường dữ liệu hồ sơ khách hàng hợp nhất
description: Sử dụng các khả năng để tăng cường dữ liệu khách hàng của bạn.
ms.date: 02/07/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 5c3dda3b9bae828857258025ff79958ee22bdb6f
ms.sourcegitcommit: a399bd17523c8d06afd7d78af4fc711f93c0e8be
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 02/07/2022
ms.locfileid: "8098815"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Tăng cường dữ liệu hồ sơ khách hàng (bản xem trước)

Sử dụng dữ liệu từ các nguồn như Microsoft và các đối tác khác để tăng cường dữ liệu khách hàng của bạn.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Trang trung tâm tăng cường.":::

Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Dữ liệu** > **Tăng cường** để làm việc với các tùy chọn tăng cường.  

Bạn cần có quyền của Người đóng góp hoặc Quản trị viên để tạo hoặc chỉnh sửa phần dữ liệu tăng cường. Để biết thêm thông tin, hãy xem [Quyền](permissions.md).

Trên tab **Khám phá**, bạn sẽ tìm thấy tất cả các tùy chọn tăng cường được hỗ trợ.

# <a name="individual-consumers-b-to-c"></a>[Người tiêu dùng cá nhân (B2C)](#tab/b2c)

- [Thương hiệu](enrichment-microsoft.md) do Microsoft cung cấp
- [Sở thích](enrichment-microsoft.md) do Microsoft cung cấp
- [Địa chỉ nâng cao](enrichment-enhanced-addresses.md) do Microsoft cung cấp 
- [Dữ liệu nhân khẩu học](enrichment-experian.md) do Experian cung cấp
- [Dữ liệu tùy chỉnh](enrichment-SFTP-custom-import.md) thông qua Secure File Transfer Protocol (SFTP) 
- [Azure Maps](enrichment-azure-maps.md) được cung cấp bởi Microsoft
- [Dữ liệu vị trí](enrichment-here.md) do HERE Technologies cung cấp 

# <a name="business-accounts-b-to-b"></a>[Tài khoản doanh nghiệp (B2B)](#tab/b2b)

- [Dữ liệu công ty](enrichment-leadspace.md) do Leadspace cung cấp
- [Địa chỉ nâng cao](enrichment-enhanced-addresses.md) do Microsoft cung cấp 
- [Dữ liệu công ty nâng cao](enrichment-enhanced-company-data.md) do Microsoft cung cấp
- [Dữ liệu vị trí](enrichment-here.md) do HERE Technologies cung cấp 
- [Dữ liệu tùy chỉnh](enrichment-SFTP-custom-import.md) thông qua Secure File Transfer Protocol (SFTP) 
- [Azure Maps](enrichment-azure-maps.md) được cung cấp bởi Microsoft
- [Dữ liệu tương tác tài khoản](enrichment-office.md) do Microsoft cung cấp

---

Trên tab **Dữ liệu tăng cường của tôi**, bạn có thể xem thông tin bổ sung mà mình đã đặt cấu hình và chỉnh sửa thuộc tính.

## <a name="manage-existing-enrichments"></a>Quản lý dữ liệu tăng cường hiện có

Đi đến tab **Dữ liệu tăng cường của tôi** để xem tất cả thông tin bổ sung đã đặt cấu hình. Mỗi dữ liệu tăng cường được biểu thị bằng một hàng bao gồm thông tin bổ sung về dữ liệu tăng cường đó.

Chọn phần tăng cường để xem các tùy chọn có sẵn. Bạn cũng có thể chọn dấu chấm lửng (...) trên một mục danh sách để xem các tùy chọn. Nếu bạn đã đặt cấu hình một số phần tăng cường, bạn có thể sử dụng hộp tìm kiếm để tìm nhanh.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Các tùy chọn quản lý dữ liệu tăng cường trong danh sách dữ liệu tăng cường.":::

- **Xem** thông tin chi tiết về dữ liệu tăng cường với số hồ sơ khách hàng được tăng cường.
- **Chỉnh sửa** cấu hình dữ liệu tăng cường.
- **Chạy** sự dữ liệu tăng cường để cập nhật hồ sơ khách hàng với dữ liệu mới nhất.
- **Vô hiệu hóa** dữ liệu tăng cường hiện có để thông tin đó không làm mới tự động với mỗi lần làm mới theo lịch. Dữ liệu từ lần làm mới thành công gần nhất sẽ tiếp tục hiển thị. **Kích hoạt** dữ liệu tăng cường không hoạt động để khởi động lại tính năng làm mới tự động với mỗi lần làm mới theo lịch.
- **Xóa** dữ liệu tăng cường.

Chạy hoặc hủy kích hoạt nhiều dữ liệu tăng cường cùng lúc bằng cách chọn chúng trong danh sách. Các tùy chọn xem và chỉnh sửa không khả dụng dưới dạng hành động hàng loạt. Chúng chỉ phù hợp với một dữ liệu tăng cường tại một thời điểm.

## <a name="enrichments-and-connections"></a>Dữ liệu tăng cường và kết nối

Các dữ liệu tăng cường của bên thứ ba được đặt cấu hình bằng cách sử dụng [kết nối](connections.md) do quản trị viên thiết lập bằng thông tin xác thực và cho phép truyền dữ liệu. Quản trị viên và người đóng góp có thể sử dụng kết nối này để đặt cấu hình nội dung tăng cường.  

## <a name="multiple-enrichments-of-the-same-type"></a>Nhiều dữ liệu tăng cường thuộc cùng loại

Thực thể cần tăng cường sẽ được chỉ định trong quá trình đặt cấu hình dữ liệu tăng cường. Nhờ đó, bạn có thể chỉ cần tăng cường một tập hợp con các cấu hình của mình. Ví dụ: chỉ tăng cường dữ liệu cho một phân khúc cụ thể. Bạn có thể đặt cấu hình một số dữ liệu tăng cường thuộc cùng loại và sử dụng lại cùng một kết nối. Một số dữ liệu tăng cường sẽ có giới hạn về số lượng dữ liệu tăng cường thuộc cùng loại có thể được tạo ra. Bạn có thể xem các giới hạn và việc sử dụng hiện tại trên trang **Dữ liệu tăng cường**.

## <a name="see-the-progress-of-the-enrichment-process"></a>Xem tiến trình của quy trình tăng cường

Bạn có thể tìm thấy thông tin chi tiết về quy trình tăng cường, bao gồm trạng thái của quy trình và các vấn đề tiềm ẩn trong khi làm mới hoặc sau khi hoàn thành quy trình làm mới. Hiểu các quy trình nào có liên quan để làm mới quy trình tăng cường và mất bao lâu để chạy các quy trình đó. Trạng thái tăng cường được hỗ trợ cho Experian, Leadspace, HERE Technologies, SFTP Import và Azure Maps.

Để xem tình trạng của quy trình tăng cường

1. Chuyển tới **Dữ liệu** > **Dữ liệu tăng cường**. 
1. Trong tab **Nội dung tăng cường của tôi**, chọn trạng thái bổ sung để mở ngăn bên. 
1. Trong ngăn **Chi tiết tiến trình**, hãy bung rộng phần **Nội dung tăng cường**. 
1. Trong phần tăng cường bạn muốn xem tiến trình, hãy chọn **Xem chi tiết**. 
1. Trong ngăn **Chi tiết công việc**, chọn **Hiển thị chi tiết** để xem các quy trình có liên quan đến việc cập nhật nội dung tăng cường và trạng thái của chúng. 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
