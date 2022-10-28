---
title: Khớp các điều kiện để hợp nhất dữ liệu
description: So khớp các thực thể để tạo hồ sơ khách hàng hợp nhất.
recommendations: false
ms.date: 10/07/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-map
- customerInsights
ms.openlocfilehash: bbd2c5f441b85460250c11f02358ea67260278d6
ms.sourcegitcommit: 52ea58c872b10f1e6f9d120be93df93cca1a12dd
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 10/26/2022
ms.locfileid: "9721547"
---
# <a name="match-conditions-for-data-unification"></a>Khớp các điều kiện để hợp nhất dữ liệu

Bước hợp nhất này xác định thứ tự đối sánh và các quy tắc để đối sánh nhiều thực thể. Bước này yêu cầu ít nhất hai thực thể.

> [!NOTE]
> Sau khi bạn tạo điều kiện đối sánh và chọn **Tiếp theo**, bạn không thể xóa một thực thể hoặc thuộc tính đã chọn. Nếu cần, hãy chọn **Mặt sau** để xem xét các thực thể và thuộc tính đã chọn trước khi tiếp tục.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

## <a name="include-enriched-entities-preview"></a>Bao gồm các thực thể được bổ sung chi tiết (xem trước)

Nếu bạn đã làm giàu các thực thể ở cấp nguồn dữ liệu để giúp cải thiện kết quả hợp nhất của mình, hãy chọn chúng. Để biết thêm thông tin, hãy xem [Làm giàu cho nguồn dữ liệu](data-sources-enrichment.md). Nếu bạn đã chọn các thực thể được bổ sung chi tiết trên **Bản ghi trùng lặp** trang, bạn không cần phải chọn lại chúng.

1. Trên **Điều kiện phù hợp** trang, chọn **Sử dụng các thực thể được bổ sung chi tiết** trên đầu của trang.

1. Từ **Sử dụng các thực thể được bổ sung chi tiết**, chọn một hoặc nhiều thực thể được bổ sung.

1. Chọn **Xong**.

## <a name="specify-the-match-order"></a>Chỉ định thứ tự so khớp

Mỗi quy tắc hợp nhất hai hoặc nhiều thực thể thành một thực thể hợp nhất. Đồng thời, nó lưu giữ hồ sơ khách hàng duy nhất. Thứ tự khớp cho biết thứ tự mà hệ thống cố gắng khớp các bản ghi.

> [!IMPORTANT]
> Thực thể đầu tiên được gọi là thực thể chính, đóng vai trò là cơ sở cho các cấu hình hợp nhất của bạn. Thực thể bổ sung được chọn sẽ được thêm vào thực thể này.
>
> Cân nhắc quan trọng:
>
> - Chọn pháp nhân có dữ liệu hồ sơ đầy đủ và đáng tin cậy nhất về khách hàng của bạn làm pháp nhân chính.
> - Chọn đối tượng có một số thuộc tính chung với các đối tượng khác (ví dụ: tên, số điện thoại hoặc địa chỉ email) làm đối tượng chính.

1. Trên **Điều kiện phù hợp**, sử dụng mũi tên di chuyển lên và xuống để di chuyển các thực thể theo thứ tự bạn muốn hoặc kéo và thả chúng. Ví dụ: chọn **Thương mại điện tử** là thực thể chính và **loyCustomers** như thực thể thứ hai.

1. Để có mọi bản ghi trong thực thể là một khách hàng duy nhất bất kể có tìm thấy kết quả trùng khớp hay không, hãy chọn **Bao gồm tất cả các bản ghi**. Bất kỳ hồ sơ nào trong thực thể này không khớp với hồ sơ trong bất kỳ thực thể nào khác đều được đưa vào hồ sơ hợp nhất. Các bản ghi không có khớp được gọi là đĩa đơn.
  
Thực thể chính *Liên hệ: Thương mại điện tử* được đối sánh với thực thể tiếp theo *CustomerLoyalty: Lòng trung thành*. Tập dữ liệu là kết quả của bước đối sánh đầu tiên được đối sánh với thực thể sau nếu bạn có nhiều hơn hai thực thể.

:::image type="content" source="media/m3_match.png" alt-text="Ảnh chụp màn hình của thứ tự khớp đã chọn cho các thực thể." lightbox="media/m3_match.png":::

## <a name="define-rules-for-match-pairs"></a>Xác định quy tắc cho các cặp so khớp

Quy tắc so khớp sẽ chỉ định logic mà một cặp thực thể cụ thể sẽ được so khớp. Một quy tắc bao gồm một hoặc nhiều điều kiện.

Cảnh báo bên cạnh tên thực thể có nghĩa là không có quy tắc đối sánh nào được xác định cho một cặp đối sánh.

1. Lựa chọn **Thêm quy tắc** cho một cặp thực thể để xác định các quy tắc đối sánh.

1. Bên trong **Thêm quy tắc**, cấu hình các điều kiện cho quy tắc.

   :::image type="content" source="media/m3_add_rule.png" alt-text="Ảnh chụp màn hình của ngăn Thêm quy tắc.":::

   - **Chọn Thực thể / Trường (hàng đầu tiên)** : Chọn một thực thể và một thuộc tính có thể là duy nhất đối với khách hàng. Ví dụ: số điện thoại hoặc địa chỉ email. Tránh trùng khớp theo thuộc tính loại hoạt động. Ví dụ: ID mua hàng có thể sẽ không khớp trong các loại bản ghi khác.

   - **Chọn Thực thể / Trường (hàng thứ hai)** : Chọn một thuộc tính có liên quan đến thuộc tính của thực thể được chỉ định trong hàng đầu tiên.

   - **Bình thường hóa**: Chọn trong số các tùy chọn chuẩn hóa sau cho các thuộc tính đã chọn.
     - **Chữ số** : Chuyển đổi các hệ thống chữ số khác, chẳng hạn như chữ số La Mã, sang chữ số Ả Rập. *VIII* trở thành *8*.
     - **Ký hiệu** : Loại bỏ tất cả các ký hiệu và ký tự đặc biệt. *Head&Shoulder* trở thành *HeadShoulder*.
     - **Chuyển văn bản thành chữ thường** : Chuyển đổi tất cả các ký tự thành chữ thường. *ALL CAPS and Title Case* trở thành *all caps and title case*.
     - **Loại (Điện thoại, Tên, Địa chỉ, Tổ chức)** : Chuẩn hóa tên, chức danh, số điện thoại, địa chỉ và tổ chức.
     - **Unicode sang ASCII** : Chuyển đổi ký hiệu unicode thành ký tự ASCII. */u00B2* trở thành *2*.
     - **Khoảng trắng** : Loại bỏ tất cả các khoảng trắng. *Hello   World* trở thành *HelloWorld*.

   - **Độ chính xác**: Đặt mức độ chính xác để áp dụng cho điều kiện này.
     - **Nền tảng** : Chọn từ *Thấp (30%)*, *bình (60%)*, *(80%)*, và *Chính xác (100%)*. Lựa chọn **Chính xác** để chỉ khớp các bản ghi khớp 100 phần trăm.
     - **Tùy chỉnh**: Đặt tỷ lệ phần trăm mà bản ghi cần so khớp. Hệ thống sẽ chỉ khớp các bản ghi vượt qua ngưỡng này.

   - **Tên** : Đặt tên cho quy tắc.

1. Để đối sánh các thực thể chỉ khi các thuộc tính đáp ứng nhiều điều kiện, hãy chọn **cộng** > **Thêm điều kiện** để thêm nhiều điều kiện hơn vào quy tắc đối sánh. Các điều kiện được kết nối với một toán tử logic AND và do đó chỉ được thực thi nếu tất cả các điều kiện được đáp ứng.

1. Theo tùy chọn, hãy xem xét các tùy chọn nâng cao như [ngoại lệ](#add-exceptions-to-a-rule) hoặc [điều kiện đối sánh tùy chỉnh](#specify-custom-match-conditions).

1. Lựa chọn **Xong** để hoàn thiện quy tắc.

1. Không bắt buộc, [thêm các quy tắc khác](#add-rules-to-a-match-pair).

1. Bấm vào **tiếp theo**.

> [!div class="nextstepaction"]
> [Bước tiếp theo: Hợp nhất các trường](merge-entities.md)

### <a name="add-rules-to-a-match-pair"></a>Thêm quy tắc vào một cặp so khớp

Các quy tắc so khớp đại diện cho các tập hợp các điều kiện. Để đối sánh các thực thể theo điều kiện dựa trên nhiều thuộc tính, hãy thêm nhiều quy tắc hơn.

1. Lựa chọn **Thêm quy tắc** trên thực thể bạn muốn thêm quy tắc.

1. Làm theo các bước trong [Xác định quy tắc cho các cặp so khớp](#define-rules-for-match-pairs).

> [!NOTE]
> Thứ tự của các quy tắc quan trọng. Thuật toán đối sánh cố gắng đối sánh một bản ghi khách hàng nhất định trên cơ sở quy tắc đầu tiên của bạn và chỉ tiếp tục với quy tắc thứ hai nếu không có kết quả phù hợp nào được xác định với quy tắc đầu tiên.

## <a name="advanced-options"></a>Tùy chọn nâng cao

### <a name="add-exceptions-to-a-rule"></a>Thêm ngoại lệ vào quy tắc

Trong hầu hết các trường hợp, đối sánh pháp nhân dẫn đến hồ sơ khách hàng duy nhất với dữ liệu tổng hợp. Để giải quyết các trường hợp hiếm hoi về dương tính giả và âm tính giả, hãy xác định các ngoại lệ cho quy tắc đối sánh. Các ngoại lệ được áp dụng sau khi xử lý các quy tắc đối sánh và tránh đối sánh tất cả các bản ghi đáp ứng các tiêu chí ngoại lệ.

Ví dụ: nếu quy tắc đối sánh của bạn kết hợp họ, thành phố và ngày sinh, hệ thống sẽ xác định các cặp song sinh có cùng họ sống trong cùng một thị trấn với cùng một hồ sơ. Bạn có thể chỉ định một ngoại lệ không khớp với các cấu hình nếu tên trong các thực thể bạn kết hợp không giống nhau.

1. Bên trong **Chỉnh sửa quy tắc** ngăn, chọn **cộng** > **Thêm ngoại lệ**.

1. Chỉ định các tiêu chí ngoại lệ.

1. Chọn **Hoàn tất** để lưu quy tắc.

### <a name="specify-custom-match-conditions"></a>Chỉ định các điều kiện so khớp tùy chỉnh

Chỉ định các điều kiện ghi đè logic đối sánh mặc định. Có bốn tùy chọn có sẵn:

|Tùy chọn  |Description |Ví dụ:  |
|---------|---------|---------|
|Luôn khớp     | Xác định các giá trị cho các khóa chính luôn được khớp.         |  Luôn khớp hàng với khóa chính *12345* vào hàng có khóa chính *54321*.       |
|Không khớp     | Xác định các giá trị cho các khóa chính không bao giờ khớp.        | Không bao giờ khớp hàng với khóa chính *12345* vào hàng có khóa chính *54321*.        |
|Bỏ qua            | Xác định các giá trị mà hệ thống luôn phải bỏ qua trong giai đoạn đối sánh. |  Bỏ qua các giá trị *11111* và *không xác định* trong trận đấu.        |
|Ánh xạ biệt danh    | Xác định các giá trị mà hệ thống nên coi là cùng một giá trị.         | Xem xét *Joe* ngang bằng với *Joseph*.        |

1. Chọn **Tùy chỉnh**.

   :::image type="content" source="media/m3_match_custom.png" alt-text="Nút tùy chỉnh":::

1. Chọn **Loại tùy chỉnh** và chọn **Tải xuống mẫu**. Đổi tên mẫu mà không sử dụng dấu cách. Sử dụng một mẫu riêng cho từng tùy chọn đối sánh.

1. Mở tệp mẫu đã tải xuống và điền thông tin chi tiết. Mẫu chứa các trường để chỉ định thực thể và các giá trị khóa chính của thực thể sẽ được sử dụng trong so khớp tùy chỉnh. Tên thực thể phân biệt chữ hoa chữ thường. Ví dụ: nếu bạn muốn khóa chính *12345* từ thực thể *Bán hàng* để luôn so khớp với khóa chính *34567* từ thực thể *Liên hệ*, hãy điền vào mẫu:
   - Thực thể 1: Bán hàng
   - Entity1Key: 12345
   - Thực thể 2: Người liên hệ
   - Entity2Key: 34567

   Cùng một tệp mẫu có thể chỉ định các bản ghi khớp tùy chỉnh từ nhiều thực thể.

   > [!NOTE]
   > Nếu bạn muốn chỉ định quá trình so khớp tùy chỉnh để loại bỏ trùng lặp trên một thực thể, hãy cung cấp cùng một thực thể cho cả Entity1 và Entity2 rồi đặt các giá trị khóa chính khác nhau. Bạn phải xác định ít nhất một quy tắc trùng lặp cho thực thể để sử dụng đối sánh tùy chỉnh.

1. Sau khi thêm tất cả các ghi đè, hãy lưu tệp mẫu.

1. Đi tới **Dữ liệu** > **Nguồn dữ liệu** và nhập các tệp mẫu dưới dạng thực thể mới.

1. Sau khi tải lên các tệp, hãy chọn **Phong tục** tùy chọn một lần nữa. Chọn các thực thể bắt buộc từ menu thả xuống và chọn **Xong**.

   :::image type="content" source="media/custom-match-overrides.png" alt-text="Ảnh chụp màn hình hộp thoại để chọn ghi đè cho tình huống so khớp tùy chỉnh.":::

1. Việc áp dụng đối sánh tùy chỉnh phụ thuộc vào tùy chọn đối sánh bạn muốn sử dụng.

   - Vì **Luôn phù hợp** hoặc **Không bao giờ phù hợp**, tiến hành bước tiếp theo.
   - Vì **Đường vòng** hoặc **Lập bản đồ bí danh**, lựa chọn **Chỉnh sửa** trên quy tắc đối sánh hiện có hoặc tạo quy tắc mới. Trong menu thả xuống Chuẩn hóa, hãy chọn **Bỏ qua tùy chỉnh** hoặc **Lập bản đồ bí danh** tùy chọn và chọn **Xong**.

1. Lựa chọn **Xong** trên **Phong tục** để áp dụng cấu hình đối sánh tùy chỉnh.

   Mỗi tệp mẫu được nhập là nguồn dữ liệu của chính tệp đó. Nếu các bản ghi được phát hiện cần xử lý đối sánh đặc biệt, hãy cập nhật nguồn dữ liệu thích hợp. Bản cập nhật sẽ được sử dụng trong quá trình thống nhất tiếp theo. Ví dụ: bạn xác định các cặp song sinh có tên gần giống nhau sống tại cùng một địa chỉ đã được hợp nhất thành một người. Cập nhật nguồn dữ liệu để xác định cặp song sinh là bản ghi riêng biệt, duy nhất.

> [!div class="nextstepaction"]
> [Bước tiếp theo: Hợp nhất các trường](merge-entities.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
