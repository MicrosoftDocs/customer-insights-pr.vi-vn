---
title: So khớp các thực thể để hợp nhất dữ liệu
description: So khớp các thực thể để kết hợp tập dữ liệu và tạo hồ sơ khách hàng hợp nhất.
ms.date: 11/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-match
ms.openlocfilehash: cabeddbc9d485108d166e6355175a01721b75a55
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732660"
---
# <a name="match-entities"></a>So khớp thực thể

Giai đoạn so khớp chỉ định cách kết hợp bộ dữ liệu của bạn vào bộ dữ liệu hồ sơ khách hàng hợp nhất. Sau khi hoàn thành [bước lập bản đồ](map-entities.md) trong quy trình hợp nhất dữ liệu, bạn đã sẵn sàng khớp các thực thể. Giai đoạn so khớp cần ít nhất hai thực thể ánh xạ.

Trang so khớp bao gồm ba phần: 
- Các chỉ số chính tóm tắt số lượng bản ghi khớp
- So khớp thứ tự và quy tắc để so khớp nhiều thực thể
- Quy tắc loại bỏ trùng lặp các thực thể so khớp

## <a name="specify-the-match-order"></a>Chỉ định thứ tự so khớp

Truy cập **Dữ liệu** > **Hợp nhất** > **So khớp** rồi chọn **Đặt thứ tự** để bắt đầu giai đoạn so khớp.

Mỗi quy tắc hợp nhất hai hoặc nhiều thực thể thành một thực thể hợp nhất. Đồng thời, nó lưu giữ hồ sơ khách hàng duy nhất. Ví dụ: chúng tôi đã chọn hai thực thể: **eCommerce:eCommerceContacts** làm thực thể chính và **LoyaltyScheme:loyCustomers** làm thực thể phụ. Thứ tự của các thực thể xác định thứ tự mà hệ thống sẽ cố gắng khớp các bản ghi.

:::image type="content" source="media/match-page.png" alt-text="Ảnh chụp màn hình của trang So khớp trong khu vực Hợp nhất của quá trình hợp nhất dữ liệu.":::
  
Thực thể chính *eCommerce:eCommerceContacts* được khớp với thực thể tiếp theo *LoyaltyScheme:loyCustomers*. Tập dữ liệu là kết quả của bước so khớp đầu tiên được so khớp với thực thể sau nếu bạn có nhiều hơn hai thực thể.

> [!IMPORTANT]
> Thực thể mà bạn chọn làm thực thể chính sẽ làm cơ sở cho tập dữ liệu hồ sơ hợp nhất. Các thực thể bổ sung được chọn trong giai đoạn so khớp sẽ được thêm vào thực thể này. Điều này không có nghĩa là thực thể hợp nhất sẽ bao gồm *tất cả* dữ liệu được bao gồm trong thực thể này.
>
> Có hai cân nhắc có thể giúp bạn chọn phân cấp của các thực thể:
>
> - Chọn thực thể có dữ liệu hồ sơ đầy đủ và đáng tin cậy nhất về khách hàng của bạn làm thực thể chính.
> - Chọn thực thể có một số thuộc tính chung với các thực thể khác (ví dụ: tên, số điện thoại hoặc địa chỉ email) làm thực thể chính.

Sau khi chỉ định thứ tự so khớp, bạn sẽ nhìn thấy các cặp so khớp xác định trong phần **Thông tin chi tiết bản ghi khớp** trên **Dữ liệu** > **Hợp nhất** > **So khớp**. Các chỉ số chính sẽ trống cho đến khi quá trình so khớp hoàn tất.

## <a name="define-rules-for-match-pairs"></a>Xác định quy tắc cho các cặp so khớp

Quy tắc so khớp sẽ chỉ định logic mà một cặp thực thể cụ thể sẽ được so khớp.

Cảnh báo **Cần quy tắc** bên cạnh tên thực thể đề xuất rằng không có quy tắc nào được xác định cho một cặp so khớp. 

:::image type="content" source="media/match-rule-add.png" alt-text="Ảnh chụp màn hình của phần Chi tiết bản ghi khớp có kiểm soát để thêm các quy tắc được đánh dấu.":::

1. Chọn **Thêm quy tắc** bên dưới một thực thể trong phần **Chi tiết bản ghi khớp** để xác định các quy tắc so khớp.

1. Trong ngăn **Tạo quy tắc**, hãy cấu hình các điều kiện cho quy tắc.

   :::image type="content" source="media/match-rule-conditions.png" alt-text="Ảnh chụp màn hình một quy tắc so khớp đã mở với các điều kiện được thêm vào.":::

   - **Thực thể/Trường (hàng đầu tiên)**: Chọn một thực thể liên quan và một thuộc tính để chỉ định thuộc tính bản ghi có khả năng dành riêng cho một khách hàng. Ví dụ: số điện thoại hoặc địa chỉ email. Tránh trùng khớp theo thuộc tính loại hoạt động. Ví dụ: ID mua hàng có thể sẽ không khớp trong các loại bản ghi khác.

   - **Thực thể/Trường (hàng thứ hai)**: Chọn một thuộc tính liên quan đến thuộc tính của thực thể được chỉ định trong hàng đầu tiên.

   - **Bình thường hóa**: Chọn trong số các tùy chọn chuẩn hóa sau cho các thuộc tính đã chọn. 
     - Khoảng trắng: Loại bỏ tất cả các khoảng trắng. *Hello   World* trở thành *HelloWorld*.
     - Biểu tượng: Loại bỏ tất cả biểu tượng và ký tự đặc biệt. *Head&Shoulder* trở thành *HeadShoulder*.
     - Văn bản thành chữ thường: Chuyển đổi tất cả các ký tự thành chữ thường. *ALL CAPS and Title Case* trở thành *all caps and title case*.
     - Unicode sang ASCII: Chuyển đổi ký hiệu unicode thành ký tự ASCII. */u00B2* trở thành *2*.
     - Chữ số: Chuyển đổi các hệ thống chữ số khác, chẳng hạn như chữ số La Mã, sang chữ số Ả Rập. *VIII* trở thành *8*.
     - Loại ngữ nghĩa: Chuẩn hóa tên, chức danh, số điện thoại, địa chỉ, v.v. 

   - **Độ chính xác**: Đặt mức độ chính xác để áp dụng cho điều kiện này. 
     - **Căn bản**: Chọn từ *Thấp*, *Trung bình*, *Cao* và *Chính xác*. Chọn **Chính xác** để chỉ so khớp các bản ghi khớp 100%. Chọn một trong các cấp độ khác để khớp với các bản ghi không giống nhau 100%.
     - **Tùy chỉnh**: Đặt tỷ lệ phần trăm mà bản ghi cần so khớp. Hệ thống sẽ chỉ khớp các bản ghi vượt qua ngưỡng này.

1. Cung cấp **Tên** cho quy tắc.

1. [Thêm các điều kiện khác](#add-conditions-to-a-rule) hoặc chọn [Xong](#add-conditions-to-a-rule) để hoàn thiện quy tắc.

1. Không bắt buộc, [thêm các quy tắc khác](#add-rules-to-a-match-pair).

1. Chọn **Lưu** để áp dụng thay đổi.

### <a name="add-conditions-to-a-rule"></a>Thêm điều kiện cho quy tắc

Để so khớp các thực thể chỉ khi các thuộc tính đáp ứng nhiều điều kiện, hãy thêm các điều kiện khác vào quy tắc so khớp. Các điều kiện được kết nối với một toán tử logic AND và do đó chỉ được thực thi nếu tất cả các điều kiện được đáp ứng.

1. Chuyển đến **Dữ liệu** > **Hợp nhất** > **So khớp** và chọn **Chỉnh sửa** cho quy tắc bạn muốn thêm điều kiện vào.

1. Trong ngăn **Chỉnh sửa quy tắc**, chọn **Thêm điều kiện**.

1. Chọn **Hoàn tất** để lưu quy tắc.

### <a name="add-rules-to-a-match-pair"></a>Thêm quy tắc vào một cặp so khớp

Các quy tắc so khớp đại diện cho các tập hợp các điều kiện. Để so khớp các thực thể theo điều kiện dựa trên nhiều thuộc tính, hãy thêm các quy tắc khác.

1.  Chuyển đến **Dữ liệu** > **Hợp nhất** > **So khớp** rồi chọn **Thêm quy tắc** đối với thực thể mà bạn muốn quy tắc vào.

2. Làm theo các bước trong [Xác định quy tắc cho các cặp so khớp](#define-rules-for-match-pairs).

> [!NOTE]
> Thứ tự của các quy tắc quan trọng. Thuật toán so khớp cố gắng so khớp trên cơ sở quy tắc đầu tiên của bạn và chỉ tiếp tục với quy tắc thứ hai nếu không có kết quả phù hợp nào được xác định với quy tắc đầu tiên.

### <a name="change-the-entity-order-in-match-rules"></a>Thay đổi thứ tự thực thể trong quy tắc so khớp

Bạn có thể sắp xếp lại thứ tự các thực thể cho các quy tắc so khớp để thay đổi trình tự xử lý. Các quy tắc bị xung đột do thay đổi thứ tự sẽ bị xóa. Bạn phải tạo lại các quy tắc đã xóa với cấu hình được cập nhật.

1. Chuyển tới mục **Dữ liệu** > **Hợp nhất** > **So khớp** và chọn **Chỉnh sửa**.

1. Trong ngăn **Chỉnh sửa quy tắc**, chọn bảng điều khiển **Di chuyển lên/xuống** hoặc kéo và thả các thực thể để thay đổi thứ tự.

   :::image type="content" source="media/reorder-match-rules.png" alt-text="Trong giai đoạn so khớp, các thực thể lệnh được thay đổi theo các tùy chọn.":::

1. Chọn **Hoàn tất** để lưu quy tắc.

## <a name="define-deduplication-on-a-match-entity"></a>Xác định quy tắc chống trùng lặp trên một thực thể so khớp

Ngoài [quy tắc so khớp trên nhiều thực thể](#define-rules-for-match-pairs), bạn cũng có thể chỉ định các quy tắc loại bỏ trùng lặp. *Loại bỏ trùng lặp* là một quy trình khác khi so khớp các bản ghi. Nó xác định các bản ghi trùng lặp và hợp nhất chúng thành một bản ghi. Bản ghi nguồn được liên kết với bản ghi đã hợp nhất bằng các ID thay thế.

Sau đó bản ghi đã loại bỏ trùng lặp này sẽ được sử dụng trong quá trình so khớp trên nhiều thực thể. Việc trùng lặp xảy ra trên các thực thể riêng lẻ và có thể được định cấu hình cho mọi thực thể được sử dụng trong các cặp so khớp.

Việc chỉ định các quy tắc chống trùng lặp là không bắt buộc. Nếu không có quy tắc nào như vậy được định cấu hình, các quy tắc do hệ thống xác định sẽ được áp dụng. Chúng kết hợp tất cả các bản ghi thành một bản ghi duy nhất trước khi chuyển dữ liệu thực thể sang so khớp nhiều thực thể để nâng cao hiệu suất.

### <a name="add-deduplication-rules"></a>Thêm quy tắc chống trùng lặp

1. Chuyển đến **Dữ liệu** > **Hợp nhất** > **So khớp**.

1. Trong phần **Bản trùng lặp đã hợp nhất**, chọn **Đặt thực thể**. Trong trường hợp các quy tắc khử trùng lặp đã được tạo, hãy chọn **Chỉnh sửa**.

1. Trong ngăn **Tùy chọn trộn**, hãy chọn các thực thể mà bạn muốn chạy loại bỏ trùng lặp.

1. Chỉ định cách kết hợp các bản ghi trùng lặp và chọn 1 trong 3 tùy chọn:
   - **Điền nhiều nhất**: Xác định bản ghi có các trường thuộc tính được điền nhiều nhất là bản ghi được chọn. Đây là tùy chọn phối mặc định.
   - **Gần đây nhất**: Xác định bản ghi chiến thắng dựa trên lần truy cập gần đây nhất. Yêu cầu ngày hoặc trường số để xác định lần truy cập gần đây.
   - **Cách đây xa nhất**: Xác định bản ghi chiến thắng dựa trên lần truy cập cách đây xa nhất. Yêu cầu ngày hoặc trường số để xác định lần truy cập gần đây.
 
   > [!div class="mx-imgBorder"]
   > ![Quy tắc chống trùng lặp bước 1.](media/match-selfconflation.png "Quy tắc chống trùng lặp bước 1")
 
1. Sau khi thực thể được chọn và tùy chọn trộn được đặt, hãy chọn **Thêm quy tắc** để xác định các quy tắc loại bỏ trùng lặp ở cấp độ thực thể.
   - **Chọn trường** liệt kê tất cả các trường hiện có từ thực thể đó. Chọn trường bạn muốn kiểm tra các bản trùng lặp. Chọn các trường có thể là duy nhất cho mọi khách hàng. Ví dụ: địa chỉ email hoặc sự kết hợp của tên, thành phố và số điện thoại.
   - Chỉ định cài đặt chuẩn hóa và thiết đặt độ chính xác.
   - Xác định các điều kiện khác bằng cách chọn **Thêm điều kiện**.
 
   > [!div class="mx-imgBorder"]
   > ![Quy tắc chống trùng lặp bước 2.](media/match-selfconflation-rules.png "Quy tắc chống trùng lặp bước 2")

  Bạn có thể tạo nhiều quy tắc chống trùng lặp cho một thực thể. 

1. Chạy quy trình so khớp hiện sẽ nhóm các bản ghi dựa trên các điều kiện được xác định trong quy tắc chống trùng lặp. Sau khi nhóm các bản ghi, chính sách trộn được áp dụng để xác định bản ghi chiến thắng.

1. Sau đó, hồ sơ chiến thắng này được chuyển cho quy trình so khớp giữa các thực thể, cùng với hồ sơ không chiến thắng (ví dụ: ID thay thế) để cải thiện chất lượng so khớp.

1. Bất kỳ quy tắc so khớp tùy chỉnh nào được xác định sẽ ghi đè quy tắc loại bỏ trùng lặp. Nếu quy tắc chống trùng lặp xác định các bản ghi khớp và quy tắc so khớp tùy chỉnh được đặt để không bao giờ khớp với các bản ghi đó, thì hai bản ghi này sẽ không được khớp.

1. Sau khi [chạy quá trình so khớp](#run-the-match-process), bạn sẽ nhìn thấy các thông số loại bỏ trùng lặp trong lát chỉ số chính.

### <a name="deduplication-output-as-an-entity"></a>Đầu ra khử trùng lặp dưới dạng một thực thể

Quá trình loại bỏ trùng lặp tạo một thực thể mới cho mọi thực thể từ các cặp so khớp để xác định các bản ghi được loại bỏ trùng lặp. Có thể tìm thấy các thực thể cùng với **ConflationMatchPairs:CustomerInsights** trong phần **Hệ thống** trên trang **Thực thể**, với tên **Deduplication_DataSource_Entity**.

Thực thể đầu ra loại bỏ trùng lặp chứa thông tin sau:
- ID/Khóa
  - Trường khóa chính và trường ID thay thế của nó. Trường ID thay thế bao gồm tất cả các ID thay thế được xác định cho một bản ghi.
  - Trường Deduplication_GroupId hiển thị nhóm hoặc cụm được xác định trong một thực thể sẽ nhóm tất cả các bản ghi tương tự dựa trên các trường loại bỏ trùng lặp được chỉ định. Tính năng này được sử dụng cho mục đích xử lý hệ thống. Nếu không có quy tắc khử trùng lặp thủ công nào được chỉ định và áp dụng quy tắc khử trùng lặp do hệ thống xác định, bạn có thể không tìm thấy trường này trong thực thể đầu ra khử trùng lặp.
  - Deduplication_WinnerId: Trường này chứa ID chiến thắng từ các nhóm hoặc cụm đã xác định. Nếu Deduplication_WinnerId giống với giá trị Khóa chính của một bản ghi, điều đó có nghĩa là bản ghi đó là bản ghi chiến thắng.
- Các trường được sử dụng để xác định các quy tắc khử trùng lặp.
- Các trường Quy tắc và Điểm để biểu thị quy tắc khử trùng lặp đã được áp dụng và điểm mà thuật toán so khớp trả về.
   
## <a name="run-the-match-process"></a>Chạy quá trình so khớp

Với các quy tắc so khớp đã định cấu hình, bao gồm cả quy tắc so khớp nhiều thực thể và loại bỏ trùng lặp, bạn có thể chạy quá trình so khớp. 

Chuyển đến **Dữ liệu** > **Hợp nhất** > **So khớp** rồi chọn **Chạy** để bắt đầu quy trình. Thuật toán so khớp mất một khoảng thời gian để hoàn thành và bạn không thể thay đổi cấu hình cho đến khi hoàn tất. Để thay đổi, bạn có thể hủy quá trình chạy. Chọn trạng thái của công việc rồi chọn **Hủy công việc** trên ngăn **Chi tiết về tiến độ**.

Bạn sẽ thấy kết quả của một lần chạy thành công, thực thể hồ sơ khách hàng hợp nhất trên trang **Thực thể**. Thực thể khách hàng hợp nhất được gọi là **Khách hàng** trong phần **Hồ sơ**. Lần chạy so khớp thành công đầu tiên tạo ra thực thể *Khách hàng* hợp nhất. Tất cả lần so khớp tiếp theo sẽ mở rộng thực thể đó.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="review-and-validate-your-matches"></a>Xem lại và xác thực các so khớp của bạn

Đi đến **Dữ liệu** > **Hợp nhất** > **So khớp** để đánh giá chất lượng của các cặp so khớp rồi xác định chúng nếu cần.

Các lát trên đầu trang hiển thị các chỉ số chính, tóm tắt số lượng bản ghi khớp và các bản sao.

:::image type="content" source="media/match-KPIs.png" alt-text="Ảnh chụp màn hình đã cắt của các chỉ số chính trên trang So khớp với các con số và chi tiết.":::

- **Bản ghi nguồn duy nhất** hiển thị số lượng bản ghi nguồn riêng lẻ đã được xử lý trong lần chạy so khớp cuối cùng.
- **Bản ghi khớp và không khớp** làm nổi bật số lượng bản ghi duy nhất còn lại sau khi xử lý các quy tắc so khớp.
- **Chỉ các bản ghi khớp** hiển thị số lượng trận đấu trên tất cả các cặp so khớp của bạn.

Bạn có thể đánh giá kết quả của từng cặp so khớp và quy tắc của từng cặp trong bảng **Chi tiết bản ghi khớp**. So sánh số bản ghi đến từ một cặp so khớp với tỷ lệ phần trăm các bản ghi được so khớp thành công.

Xem lại các quy tắc của một cặp so khớp để xem tỷ lệ phần trăm các bản ghi được so khớp thành công ở cấp quy tắc. Chọn dấu chấm lửng (...) rồi chọn **Xem trước so khớp** để xem tất cả các bản ghi này ở cấp quy tắc. Chúng tôi khuyên bạn nên xem một số bản ghi để xác thực rằng chúng đã được khớp chính xác hay chưa.

Thử các ngưỡng chính xác khác nhau trên các điều kiện để tìm giá trị tối ưu.

  1. Chọn dấu chấm lửng (...) cho quy tắc mà bạn muốn thử nghiệm và chọn **Chỉnh sửa**.

  2. Thay đổi các giá trị khu vực chính xác trong các điều kiện bạn muốn sửa đổi.

  3. Lựa chọn **Xem trước** vì vậy hãy xem số lượng bản ghi khớp và chưa khớp đối với điều kiện đã chọn.

## <a name="manage-match-rules"></a>Quản lý quy tắc so khớp

Bạn có thể định cấu hình lại và tinh chỉnh hầu hết các thông số khớp.

:::image type="content" source="media/match-rules-management.png" alt-text="Ảnh chụp màn hình của menu thả xuống với các tùy chọn quy tắc so khớp.":::

- **Thay đổi thứ tự các quy tắc của bạn** nếu bạn đã xác định nhiều quy tắc. Bạn có thể sắp xếp lại các quy tắc so khớp bằng cách chọn **Đi lên** và **Đi xuống** hoặc bằng cách kéo và thả.

- **Thay đổi điều kiện quy tắc** bằng cách chọn **Chỉnh sửa** rồi chọn các trường khác nhau.

- **Hủy kích hoạt quy tắc** để giữ lại quy tắc so khớp trong khi loại trừ nó khỏi quá trình so khớp.

- **Sao chép các quy tắc** nếu bạn đã xác định quy tắc so khớp và muốn tạo quy tắc tương tự có sửa đổi, hãy chọn **Sao chép**.

- **Xóa quy tắc** bằng cách chọn biểu tượng **Xóa**.

## <a name="specify-custom-match-conditions"></a>Chỉ định các điều kiện so khớp tùy chỉnh

Bạn có thể chỉ định các điều kiện mà hồ sơ phải luôn khớp hoặc không bao giờ khớp. Các quy tắc này có thể được tải lên để ghi đè quy trình so khớp tiêu chuẩn. Ví dụ: nếu có John Doe I và John Doe II trong hồ sơ của chúng tôi, hệ thống có thể khớp chúng với tư cách là một người. Quy tắc so khớp tùy chỉnh cho phép bạn chỉ định rằng hồ sơ của họ đề cập đến những người khác nhau. 

1. Chuyển đến **Dữ liệu** > **Hợp nhất** > **So khớp** rồi chọn **So khớp tùy chỉnh** trong phần **Chi tiết bản ghi khớp**.

  :::image type="content" source="media/custom-match-create.png" alt-text="Ảnh chụp màn hình của phần Chi tiết bản ghi khớp có kiểm soát để thêm các quy tắc được đánh dấu.":::

1. Nếu bạn chưa đặt quy tắc so khớp tùy chỉnh, bạn sẽ thấy ngăn **So khớp tùy chỉnh** với nhiều chi tiết hơn.

1. Chọn **Điền vào mẫu** để có được một tệp mẫu có thể chỉ định các bản ghi mà từ đó các thực thể phải luôn khớp hoặc không bao giờ khớp. Bạn sẽ cần điền riêng vào các bản ghi "luôn khớp" và các bản ghi "không bao giờ khớp" trong hai tệp khác nhau.

1. Mẫu chứa các trường để chỉ định thực thể và các giá trị khóa chính của thực thể sẽ được sử dụng trong so khớp tùy chỉnh. Ví dụ: nếu bạn muốn khóa chính *12345* từ thực thể *Bán hàng* để luôn so khớp với khóa chính *34567* từ thực thể *Liên hệ*, hãy điền vào mẫu:
    - Thực thể 1: Bán hàng
    - Entity1Key: 12345
    - Thực thể 2: Người liên hệ
    - Entity2Key: 34567

   Cùng một tệp mẫu có thể chỉ định các bản ghi khớp tùy chỉnh từ nhiều thực thể.
   
   Nếu bạn muốn chỉ định quá trình so khớp tùy chỉnh để loại bỏ trùng lặp trên một thực thể, hãy cung cấp cùng một thực thể cho cả Entity1 và Entity2 rồi đặt các giá trị khóa chính khác nhau.

1. Sau khi thêm tất cả các phần ghi đè bạn muốn áp dụng, hãy lưu tệp mẫu.

1. Đi tới **Dữ liệu** > **Nguồn dữ liệu** và nhập các tệp mẫu dưới dạng thực thể mới. Sau khi nhập, bạn có thể sử dụng chúng để chỉ định cấu hình So khớp.

1. Sau khi tải lên các tệp và thực thể có sẵn, chọn tùy chọn **So khớp tùy chỉnh** một lần nữa. Bạn sẽ thấy các tùy chọn để chỉ định các thực thể bạn muốn bao gồm. Chọn thực thể cần thiết từ menu thả xuống.

   :::image type="content" source="media/custom-match-overrides.png" alt-text="Ảnh chụp màn hình hộp thoại để chọn ghi đè cho tình huống so khớp tùy chỉnh.":::

1. Chọn các thực thể bạn muốn sử dụng cho **Luôn so khớp** và **Không bao giờ khớp**, chọn **Xong**.

1. Chọn **Lưu** trên trang **So khớp** để áp dụng cấu hình so khớp tùy chỉnh.

1. Chọn **Chạy** trên trang **So khớp** để bắt đầu quy trình so khớp. Các quy tắc so khớp được chỉ định khác bị ghi đè bởi cấu hình so khớp tùy chỉnh.

> [!TIP]
> Chuyển đến **Dữ liệu** > **Thực thể** và xem lại thực thể **ConflationMatchPair** để xác nhận rằng đã áp dụng giá trị ghi đè.

## <a name="next-step"></a>Bước tiếp theo

Sau khi hoàn thành quy trình so khớp cho ít nhất một cặp so khớp, bạn có thể giải quyết các mâu thuẫn có thể có trong dữ liệu của mình bằng cách tham khảo chủ đề [**Hợp nhất**](merge-entities.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
