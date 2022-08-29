---
title: Chọn các trường nguồn để hợp nhất dữ liệu
description: Bước đầu tiên trong quá trình hợp nhất là chọn các thực thể, thuộc tính, khóa chính và loại ngữ nghĩa để ánh xạ dữ liệu vào hồ sơ khách hàng hợp nhất.
recommendations: false
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-map
- ci-match
- customerInsights
ms.openlocfilehash: bc120aa7a3713e1184ff278edf0942925faafa12
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304591"
---
# <a name="select-source-fields-for-data-unification"></a>Chọn các trường nguồn để hợp nhất dữ liệu

Bước đầu tiên trong quá trình hợp nhất là chọn các thực thể và trường trong tập dữ liệu mà bạn muốn hợp nhất. Chọn các thực thể chứa các chi tiết liên quan đến khách hàng như tên, địa chỉ, số điện thoại và email. Bạn có thể chọn một hoặc nhiều thực thể.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

## <a name="select-entities-and-fields"></a>Chọn thực thể và trường

1. Đi đến **Dữ liệu** > **Hợp nhất**.

   Đối với khách hàng cá nhân (B-to-C), **Thống nhất** trang đích hiển thị **Bắt đầu** ở bước đầu tiên, **Các trường nguồn**.

   :::image type="content" source="media/m3_unify_land.png" alt-text="Ảnh chụp màn hình của trang đích thống nhất cho trải nghiệm chạy lần đầu tiên dành cho khách hàng cá nhân.":::

   Đối với tài khoản doanh nghiệp (B-to-B), **Thống nhất** trang đích hiển thị **Hợp nhất các tài khoản** hiển thị **Bắt đầu** ở bước đầu tiên, **Các trường nguồn**. Các **Hợp nhất danh bạ (xem trước)** các bước là tùy chọn và đang chờ hoàn thành hợp nhất tài khoản.

   :::image type="content" source="media/b2b_unify_land.png" alt-text="Ảnh chụp màn hình trang đích thống nhất để có trải nghiệm chạy lần đầu tiên cho các tài khoản doanh nghiệp.":::

1. Chọn **Bắt đầu**.

1. Trên **Các trường nguồn** trang, chọn **Chọn các thực thể và trường**. Các **Chọn các thực thể và trường** bảng hiển thị.

1. Chọn ít nhất một thực thể.

1. Đối với mỗi thực thể đã chọn, hãy xác định các trường bạn muốn sử dụng để khớp với hồ sơ khách hàng và các trường để đưa vào hồ sơ hợp nhất. Các trường này được gọi là *Thuộc tính*. Bạn có thể chọn từng thuộc tính bắt buộc từ một thực thể hoặc bao gồm tất cả các thuộc tính từ một thực thể bằng cách chọn hộp kiểm ở cấp thực thể. Bạn có thể tìm kiếm từ khóa trên tất cả các thuộc tính và thực thể để chọn các thuộc tính bắt buộc mà bạn muốn ánh xạ.

   :::image type="content" source="media/m3_select_entities.png" alt-text="Ảnh chụp màn hình của các thực thể và thuộc tính đã chọn.":::

   Trong ví dụ này, chúng tôi đang thêm **eCommerceContacts** và **loyCustomer** các thực thể. Bằng cách chọn những thực thể này, bạn có thể có được thông tin chi tiết về khách hàng kinh doanh trực tuyến nào là thành viên của chương trình khách hàng thân thiết.

1. Lựa chọn **Áp dụng** để xác nhận lựa chọn của bạn. Các thực thể và thuộc tính đã chọn sẽ hiển thị.

## <a name="select-primary-key-and-semantic-type-for-attributes"></a>Chọn khóa chính và loại ngữ nghĩa cho các thuộc tính

   :::image type="content" source="media/m3_select_primary.png" alt-text="Ảnh chụp màn hình của các thực thể đã chọn với khóa chính chưa được chọn." lightbox="media/m3_select_primary.png":::

Đối với mỗi thực thể, hãy thực hiện các bước sau.

1. Chọn **Khóa chính**. Khóa chính là một thuộc tính duy nhất của thực thể. Để một thuộc tính là khóa chính hợp lệ, thuộc tính đó không được bao gồm các giá trị trùng lặp, giá trị bị thiếu hoặc giá trị rỗng. Các thuộc tính kiểu dữ liệu chuỗi, số nguyên và GUID được hỗ trợ làm khóa chính.

1. Để sử dụng mô hình AI cho dự đoán thông minh về ngữ nghĩa, giúp tiết kiệm thời gian và cải thiện độ chính xác, hãy đảm bảo **Lập bản đồ thông minh** đang bật. Lập bản đồ thông minh cung cấp các đề xuất ngữ nghĩa dựa trên AI trong **Loại hình** đồng ruộng.

1. Đối với mỗi thuộc tính, hãy chọn một ngữ nghĩa **Loại hình** mô tả tốt nhất thuộc tính đó, chẳng hạn như tên, thành phố hoặc địa chỉ email.

   > [!NOTE]
   > Trong B-to-C, một trường sẽ ánh xạ đến kiểu ngữ nghĩa *Person.FullName* để điền tên khách hàng vào thẻ khách hàng. Trong B-to-B, tên tài khoản phải liên kết với *Organization.Name*. Nếu không, thẻ khách hàng sẽ xuất hiện không tên.

   1. Để ghi đè một loại thuộc tính được hệ thống xác định, hãy chọn một tùy chọn khác. Nếu loại không tồn tại, hãy tạo một loại ngữ nghĩa tùy chỉnh bằng cách chọn **Loại hình** trường cho thuộc tính và nhập tên loại ngữ nghĩa tùy chỉnh của bạn.

   1. Để thêm thuộc tính có chứa URL vào hình ảnh hoặc biểu trưng hồ sơ có sẵn công khai, hãy chọn thực thể và trường chứa URL. Bên trong **Loại hình**, hãy nhập như sau:
      - Đối với một người: Person.ProfileImage
      - Đối với một tổ chức: Organisation.LogoImage

1. Xem lại các thuộc tính nơi loại ngữ nghĩa được tự động xác định. Các thuộc tính này được liệt kê dưới **Xem lại các trường được ánh xạ**. Chỉ các thuộc tính có cùng loại mới có thể được kết hợp trong **Hợp nhất các trường khách hàng** bươc. Các loại ngữ nghĩa được sử dụng để tự động đề xuất thông tin chi tiết. Đảm bảo các loại bạn đã chọn nhất quán trên tất cả các thực thể đã chọn.

1. Đối với các thuộc tính không được ánh xạ tự động đến một loại ngữ nghĩa, hãy chọn trường loại ngữ nghĩa, nhập tên loại thuộc tính tùy chỉnh của bạn hoặc để chúng không được ánh xạ. Các thuộc tính này được liệt kê dưới **Xác định dữ liệu trong các trường chưa được ánh xạ**.

1. Sau khi hoàn thành các bước cho từng thực thể, hãy chọn **Lưu các trường nguồn**.

1. Chọn **Tiếp theo**.

> [!div class="nextstepaction"]
> [Bước tiếp theo: Xóa các bản sao](remove-duplicates.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
