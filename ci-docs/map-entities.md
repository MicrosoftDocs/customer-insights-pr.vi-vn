---
title: Ánh xạ thực thể và thuộc tính để hợp nhất dữ liệu
description: Chọn các thực thể, thuộc tính, khóa chính và loại ngữ nghĩa để ánh xạ dữ liệu vào hồ sơ khách hàng hợp nhất.
ms.date: 10/18/2020
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-map
- ci-match
- customerInsights
ms.openlocfilehash: bebc600e91db471c3cd50eccb5e42be309ff09c9
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 04/27/2022
ms.locfileid: "8644013"
---
# <a name="map-entities-and-attributes"></a>Ánh xạ thực thể và thuộc tính

**Bản đồ** là giai đoạn đầu tiên trong quá trình hợp nhất dữ liệu. Ánh xạ bao gồm ba giai đoạn:

- *Lựa chọn thực thể*: Xác định các thực thể có thể kết hợp dẫn đến tập dữ liệu có thông tin đầy đủ hơn về khách hàng của bạn.
- *Lựa chọn thuộc tính*: Đối với mỗi thực thể, xác định các cột bạn muốn kết hợp và hợp nhất trong giai đoạn *so khớp* và *hợp nhất*. Các cột này có tên là *Thuộc tính*.
- *Khóa chính và lựa chọn kiểu ngữ nghĩa*: Đối với mỗi thực thể, hãy xác định một thuộc tính bạn muốn xác định làm khóa chính cho thực thể đó và đối với mỗi thuộc tính, hãy xác định một loại ngữ nghĩa mô tả tốt nhất thuộc tính đó.

Để biết thêm thông tin về quy trình hợp nhất dữ liệu chung, hãy xem [Hợp nhất](data-unification.md).

## <a name="select-the-first-entities"></a>Chọn thực thể đầu tiên

1. Chuyển đến **Dữ liệu** > **Hợp nhất** > **Ánh xạ**.

2. Bắt đầu giai đoạn ánh xạ bằng cách chọn **Chọn thực thể**.

3. Chọn các thực thể và thuộc tính bạn muốn sử dụng trong giai đoạn *khớp* và *hợp nhất*. Bạn có thể chọn các thuộc tính bắt buộc riêng lẻ từ một thực thể hoặc bao gồm tất cả các thuộc tính từ một thực thể bằng cách chọn hộp kiểm **Bao gồm tất cả các trường** ở cấp thực thể. Chúng tôi khuyên bạn nên chọn ít nhất hai thực thể để hưởng lợi từ quá trình thống nhất dữ liệu.

   > [!div class="mx-imgBorder"]
   > ![Ví dụ về thêm thực thể.](media/data-manager-configure-map-add-entities-example.png "Ví dụ về thêm thực thể")

   Trong ví dụ này, chúng tôi đang thêm thực thể **eCommerceContacts** và **loyCustomers**. Bằng cách chọn những thực thể này, bạn có thể có được thông tin chi tiết về khách hàng kinh doanh trực tuyến nào là thành viên của chương trình khách hàng thân thiết.
   
   Bạn có thể tìm kiếm từ khóa trên tất cả các thuộc tính và thực thể để chọn các thuộc tính bắt buộc mà bạn muốn ánh xạ.
   
     > [!div class="mx-imgBorder"]
   > ![Ví dụ về trường tìm kiếm.](media/data-manager-configure-map-search-fields-example.png "Ví dụ về trường tìm kiếm")

4. Lựa chọn **Áp dụng** để xác nhận lựa chọn của bạn.

## <a name="select-primary-key-and-semantic-type-for-attributes"></a>Chọn khóa chính và loại ngữ nghĩa cho các thuộc tính

Sau khi chọn các thực thể của bạn, trang **Bản đồ** sẽ liệt kê các thực thể đã chọn để bạn xem xét. Xác định khóa chính cho một thực thể và xác định kiểu ngữ nghĩa cho một thuộc tính trong thực thể.

- **Khóa chính**: Chọn một thuộc tính làm khóa chính cho từng thực thể của bạn. Để một thuộc tính là khóa chính hợp lệ, thuộc tính đó không được bao gồm các giá trị trùng lặp, giá trị bị thiếu hoặc giá trị rỗng. Các thuộc tính kiểu dữ liệu chuỗi, số nguyên và GUID được hỗ trợ làm khóa chính và sẽ được hiển thị trong một trường để bạn chọn.

- **Loại ngữ nghĩa thuộc tính**: Danh mục các thuộc tính của bạn, chẳng hạn như địa chỉ email hoặc tên. Để sử dụng mô hình trí tuệ nhân tạo cho dự đoán thông minh về ngữ nghĩa, tiết kiệm thời gian và cải thiện độ chính xác, hãy đặt **Ánh xạ thông minh** thành **BẬT**. Ánh xạ thông minh làm nổi bật các đề xuất ngữ nghĩa dựa trên AI trong trường **Loại**. Nếu bạn đặt nó thành **TẮT**, bạn sẽ thấy các đề xuất ánh xạ thông thường của chúng tôi. Bạn có thể chọn bất kỳ kiểu ngữ nghĩa nào từ danh sách tùy chọn có sẵn và ghi đè lựa chọn được gợi ý.

> [!div class="mx-imgBorder"]
> ![Loại thuộc tính và ngữ nghĩa dự đoán.](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Loại thuộc tính và ngữ nghĩa dự đoán")

Cũng có thể thêm một loại ngữ nghĩa tùy chỉnh. Chọn trường loại cho thuộc tính đó và nhập tên loại ngữ nghĩa tùy chỉnh của bạn. Như vậy, bạn cũng có thể thay đổi các loại thuộc tính được xác định bởi hệ thống.

Tất cả các thuộc tính mà một loại ngữ nghĩa được nhận dạng tự động được nhóm lại trong phần **Xem lại các trường được ánh xạ**. Xem lại các thuộc tính này và các loại ngữ nghĩa của chúng vì chúng sẽ được sử dụng để kết hợp các thực thể của bạn trong bước hợp nhất của hợp nhất dữ liệu.

Các thuộc tính không được ánh xạ tự động đến một loại ngữ nghĩa được nhóm lại trong phần **Xác định dữ liệu trong các trường chưa được ánh xạ**. Chọn trường loại ngữ nghĩa cho các thuộc tính chưa được ánh xạ hoặc nhập tên loại thuộc tính tùy chỉnh của bạn.

> [!div class="mx-imgBorder"]
> ![Khóa chính và loại thuộc tính.](media/data-manager-configure-map-add-attributes.png "Khóa chính và loại thuộc tính")

> [!NOTE]
> Một trường nên ánh xạ đến kiểu ngữ nghĩa Person.FullName để điền tên khách hàng vào thẻ khách hàng. Nếu không, thẻ khách hàng sẽ xuất hiện không tên. 

## <a name="add-and-remove-attributes-and-entities"></a>Thêm và xóa các thuộc tính và thực thể

1. Trên **Hợp nhất** > **Bản đồ**, chọn **Chỉnh sửa các trường**.

2. Trong ngăn **Chỉnh sửa các trường**, thêm hoặc xóa các thuộc tính và thực thể. Sử dụng tìm kiếm hoặc cuộn để tìm và chọn các thuộc tính và thực thể bạn quan tâm. Bạn không thể xóa một thuộc tính hoặc một thực thể nếu chúng đã được đối sánh.

   > [!div class="mx-imgBorder"]
   > ![Thêm hoặc loại bỏ thuộc tính.](media/configure-data-map-edit.png "Thêm hoặc loại bỏ thuộc tính")

3. Chọn **Áp dụng**.

## <a name="add-images-to-profiles"></a>Thêm hình ảnh vào hồ sơ

Nếu một thực thể chứa URL tới logo hoặc hình ảnh hồ sơ sẵn có công khai, bạn có thể thêm chúng vào hồ sơ khách hàng hợp nhất.

Chọn thực thể và tìm trường có chứa URL tới hình ảnh hồ sơ. Trong trường nhập **Loại**, hãy nhập giá trị sau: 
- Đối với một người: Person.ProfileImage
- Đối với một tổ chức: Organisation.LogoImage

Tiếp tục với các bước hợp nhất và đảm bảo thuộc tính chứa URL hình ảnh cũng được thêm vào bước [Hợp nhất](merge-entities.md).

## <a name="set-attributes-for-organizations"></a>Đặt thuộc tính cho tổ chức

Đối với tổ chức (Xem trước), loại thuộc tính sẽ được ánh xạ tới "Organization.Name"
> [!div class="mx-imgBorder"]
> ![Khóa chính và loại thuộc tính B2B.](media/configure-data-map-edit-b2b.png "Khóa chính và loại thuộc tính B2B")

## <a name="next-step"></a>Bước tiếp theo

Là một phần của quá trình thống nhất dữ liệu, hãy chuyển đến trang **So khớp**. Truy cập phần [**So khớp**](match-entities.md) để tìm hiểu về giai đoạn này.

> [!TIP]
> Xem video sau: [Bắt đầu: Tạo hồ sơ khách hàng hợp nhất](https://youtu.be/oBfGEhucAxs).


[!INCLUDE [footer-include](includes/footer-banner.md)]