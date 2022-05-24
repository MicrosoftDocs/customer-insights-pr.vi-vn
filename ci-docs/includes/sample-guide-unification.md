---
ms.openlocfilehash: 1d79987893986148421c316193b27d268cfe0a0b
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755570"
---
Sau khi nhập dữ liệu, hãy bắt đầu quy trình hợp nhất dữ liệu để tạo hồ sơ khách hàng thống nhất. Để biết thêm thông tin, hãy xem [Hợp nhất dữ liệu](../data-unification.md).

### <a name="select-source-fields"></a>Chọn các trường nguồn

1. Sau khi nhập dữ liệu, hãy ánh xạ các địa chỉ liên hệ từ dữ liệu Thương mại điện tử và Mức độ trung thành thành các loại dữ liệu phổ biến. Đi đến **Dữ liệu** > **Hợp nhất**.

1. Chọn các thực thể đại diện cho hồ sơ khách hàng – **eCommerceContacts** và **loyCustomers**.

   ![hợp nhất nguồn dữ liệu thương mại điện tử và khách hàng thân thiết.](../media/unify-ecommerce-loyalty.png)

1. Chọn **ContactId** làm khóa chính cho **eCommerceContacts** và **LoyaltyID** làm khóa chính cho **loyCustomers**.

1. Chọn **Tiếp theo**. Bỏ qua các bản ghi trùng lặp và chọn **Kế tiếp**.

### <a name="match-conditions"></a>Điều kiện phù hợp

1. Chọn **eCommerceLiên hệ: eCommerce** là thực thể chính và bao gồm tất cả các bản ghi.

1. Chọn **loyCustomers: LoyaltyScheme** và bao gồm tất cả các bản ghi.

1. Thêm quy tắc:
   - Lựa chọn **Họ và tên** cho cả eCommerceContacts và loyCustomers.
   - Lựa chọn **Nhập (Điện thoại, Tên, Địa chỉ, ...)** vì **Bình thường hóa**.
   - Đặt **Mức độ chính xác**: **Cơ bản** và **Giá trị**: **Cao**.
   - đi vào **FullName, Email** cho cái tên.

1. Thêm điều kiện thứ hai cho địa chỉ email:
   - Lựa chọn **E-mail** cho cả eCommerceContacts và loyCustomers.
   - Để trống trường Chuẩn hóa.
   - Đặt **Mức độ chính xác**: **Cơ bản** và **Giá trị**: **Cao**.

   ![Hợp nhất quy tắc so khớp cho tên và email.](../media/unify-match-rule.png)

1. Chọn **Xong**.

1. Chọn **Tiếp theo**.

### <a name="unify-fields"></a>Hợp nhất các trường

1. Đổi tên **ContactId** vì **loyCustomers** thực thể đến **ContactIdLOYALTY** để phân biệt nó với các ID khác đã nhập.

1. Lựa chọn **Kế tiếp** để xem xét và sau đó chọn **Tạo hồ sơ khách hàng**.
