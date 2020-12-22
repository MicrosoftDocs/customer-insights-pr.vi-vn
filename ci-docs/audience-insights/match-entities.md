---
title: So khớp các thực thể để hợp nhất dữ liệu
description: So khớp các thực thể để tạo hồ sơ khách hàng hợp nhất.
ms.date: 10/14/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 78549037f9c9e59329f5423c36eeb058128802c0
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407330"
---
# <a name="match-entities"></a>So khớp thực thể

Sau khi hoàn thành giai đoạn ánh xạ, bạn đã sẵn sàng để so khớp với các thực thể của mình. Giai đoạn so khớp chỉ định cách kết hợp bộ dữ liệu của bạn vào bộ dữ liệu hồ sơ khách hàng hợp nhất. Giai đoạn so khớp cần ít nhất [hai thực thể ánh xạ](map-entities.md).

## <a name="specify-the-match-order"></a>Chỉ định thứ tự so khớp

Đi đến **Hợp nhất** > **So khớp** và chọn **Đặt thứ tự** để bắt đầu giai đoạn so khớp.

Mỗi lần so khớp sẽ hợp nhất hai hoặc nhiều thực thể thành một thực thể, trong khi vẫn duy trì từng hồ sơ khách hàng duy nhất. Trong ví dụ sau, chúng tôi đã chọn 3 thực thể: **ContactCSV: TestData** làm thực thể **Chính**, **WebAccountCSV: TestData** làm **Thực thể 2** và **CallRecordSmall: TestData** làm **Thực thể 3**. Sơ đồ phía trên các lựa chọn minh họa cách thực hiện thứ tự so khớp.

> [!div class="mx-imgBorder"]
> ![Chỉnh sửa thứ tự so khớp dữ liệu](media/configure-data-match-order-edit-page.png "Chỉnh sửa thứ tự so khớp dữ liệu")
  
Thực thể **Chính** được so khớp với **Thực thể 2**. Tập dữ liệu thu được từ lần so khớp đầu tiên được so khớp với **Thực thể 3**.
Trong ví dụ này, chúng tôi chỉ chọn hai lượt so khớp, nhưng hệ thống có thể hỗ trợ nhiều hơn.

> [!IMPORTANT]
> Thực thể mà bạn chọn làm thực thể **Sơ cấp** sẽ làm cơ sở cho tập dữ liệu chính thống nhất của bạn. Các thực thể bổ sung được chọn trong giai đoạn so khớp sẽ được thêm vào thực thể này. Đồng thời, điều này không có nghĩa là thực thể hợp nhất sẽ bao gồm *tất cả* dữ liệu bao gồm trong thực thể này.
>
> Có hai cân nhắc có thể giúp bạn chọn phân cấp của các thực thể:
>
> - Bạn coi thực thể nào là có dữ liệu đầy đủ và đáng tin cậy nhất về khách hàng?
> - Thực thể mà bạn vừa xác định có các thuộc tính giống các thực thể khác (ví dụ: tên, số điện thoại hoặc địa chỉ email) không? Nếu không, hãy chọn thực thể đáng tin cậy thứ hai của bạn.

Chọn **Hoàn tất** để lưu thứ tự so khớp của bạn.

## <a name="define-rules-for-your-first-match-pair"></a>Xác định quy tắc cho cặp so khớp đầu tiên của bạn

Sau khi chỉ định thứ tự so khớp, bạn sẽ thấy các kết quả khớp được xác định trên trang **So khớp**. Các lát ở đầu màn hình sẽ trống cho đến khi bạn chạy thứ tự so khớp.

> [!div class="mx-imgBorder"]
> ![Xác định quy tắc](media/configure-data-match-need-rules.png "Xác định quy tắc")

Cảnh báo **Cần quy tắc** cho thấy rằng chưa xác định quy tắc so khớp cho một cặp so khớp. Quy tắc so khớp sẽ chỉ định logic mà một cặp thực thể cụ thể sẽ được so khớp.

1. Để xác định quy tắc đầu tiên của bạn, hãy mở ngăn **Định nghĩa quy tắc** bằng cách chọn hàng so khớp tương ứng trong bảng so khớp (1) và sau đó chọn **Tạo quy tắc mới** (2).

   > [!div class="mx-imgBorder"]
   > ![Tạo quy tắc mới](media/configure-data-match-new-rule2.png "Tạo quy tắc mới")

2. Trong ngăn **Chỉnh sửa quy tắc**, đặt cấu hình các điều kiện cho quy tắc đó. Mỗi điều kiện được đại diện bởi hai hàng bao gồm các lựa chọn bắt buộc.

   > [!div class="mx-imgBorder"]
   > ![Ngăn quy tắc mới](media/configure-data-match-new-rule-condition.png "Ngăn quy tắc mới")

   Thực thể/Trường (đầu tiên) - Một thuộc tính sẽ được sử dụng để so khớp từ thực thể cặp so khớp đầu tiên. Ví dụ có thể bao gồm một số điện thoại hoặc địa chỉ email. Chọn một thuộc tính có khả năng là thuộc tính duy nhất cho khách hàng.

   > [!TIP]
   > Tránh so khớp trên cơ sở các thuộc tính thuộc loại hoạt động. Nói cách khác, nếu một thuộc tính có vẻ là một hoạt động, thì đó có thể là một tiêu chí không phù hợp để so khớp.  

   Thực thể/Trường (Thứ hai) - Một thuộc tính sẽ được sử dụng để so khớp từ thực thể cặp so khớp thứ hai.

   Chuẩn hóa - **Phương pháp chuẩn hóa**: Tùy chọn chuẩn hóa khác nhau có sẵn cho các thuộc tính được chọn. Ví dụ: xóa dấu chấm câu hoặc xóa khoảng trắng

   Để chuẩn hóa tên Tổ chức (Xem trước), bạn cũng có thể chọn **Loại (Điện thoại, Tên, Tổ chức)**

   > [!div class="mx-imgBorder"]
   > ![Chuẩn hóa-B2B](media/match-normalization-b2b.png "Chuẩn hóa-B2B")

   Mức chính xác - Mức độ chính xác sẽ được sử dụng cho điều kiện này. Việc đặt mức chính xác cho điều kiện khớp có thể có hai loại: **Cơ bản** và **Tùy chỉnh**.  
   - Cơ bản: Cung cấp cho bạn bốn tùy chọn để chọn: Thấp, Trung bình, Cao và Chính xác. Chọn **Chính xác** để chỉ so khớp các bản ghi khớp 100%. Chọn một trong các cấp độ khác để khớp với các bản ghi không giống nhau 100%.
   - Tùy chỉnh: Sử dụng thanh trượt để xác định tỷ lệ phần trăm tùy chỉnh mà bản ghi cần khớp hoặc nhập giá trị trong trường **Tùy chỉnh**. Hệ thống sẽ chỉ khớp các bản ghi vượt qua ngưỡng này dưới dạng các cặp đối sánh cần hợp nhất làm một. Giá trị trên thanh trượt nằm trong khoảng từ 0 đến 1. Vì vậy, 0,64 đại diện cho 64%.

3. Chọn **Hoàn tất** để lưu quy tắc.

### <a name="add-multiple-conditions"></a>Thêm nhiều điều kiện

Để chỉ khớp các thực thể khi đáp ứng nhiều điều kiện, hãy thêm nhiều điều kiện được liên kết thông qua toán tử AND.

1. Trong ngăn **Chỉnh sửa quy tắc**, chọn **Thêm điều kiện**. Bạn cũng có thể xóa các điều kiện bằng cách chọn nút xóa bên cạnh một điều kiện hiện có.

2. Chọn **Hoàn tất** để lưu quy tắc.

## <a name="add-multiple-rules"></a>Thêm nhiều quy tắc

Mỗi điều kiện áp dụng cho một cặp thuộc tính, trong khi quy tắc đại diện cho các bộ điều kiện. Để so khớp các thực thể theo các bộ thuộc tính khác nhau, bạn có thể thêm nhiều quy tắc.

1. Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Dữ liệu** > **Hợp nhất** > **So khớp**.

2. Chọn thực thể bạn muốn cập nhật và chọn **Thêm quy tắc**.

3. Làm theo quy trình nêu trong [Xác định quy tắc cho cặp so khớp đầu tiên](#define-rules-for-your-first-match-pair).

> [!NOTE]
> Thứ tự quy tắc đóng vai trò quan trọng. Thuật toán so khớp cố gắng khớp trên cơ sở quy tắc đầu tiên của bạn và chỉ tiếp tục quy tắc thứ hai nếu không có kết quả khớp nào được xác định theo quy tắc đầu tiên.

## <a name="define-deduplication-on-a-match-entity"></a>Xác định quy tắc chống trùng lặp trên một thực thể so khớp

Cùng với việc chỉ định các quy tắc so khớp thực thể chéo như được nêu trong các phần trên, bạn cũng có thể chỉ định các quy tắc chống trùng lặp. *Chống trùng lặp* là một quy trình. Quy tắc này xác định các bản ghi trùng lặp, hợp nhất chúng thành một bản ghi và liên kết tất cả các bản ghi nguồn với bản ghi đã hợp nhất này với các ID thay thế với bản ghi đã hợp nhất.

Sau khi xác định được bản ghi chống trùng lặp, bản ghi đó sẽ được sử dụng trong quá trình so khớp thực thể chéo. Quy tắc chống trùng lặp được triển khai ở cấp thực thể và có thể được áp dụng cho mọi thực thể được sử dụng trong quy trình So khớp.

### <a name="add-deduplication-rules"></a>Thêm quy tắc chống trùng lặp

1. Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Dữ liệu** > **Hợp nhất** > **So khớp**.

1. Trong phần **Bản trùng lặp đã hợp nhất**, chọn **Đặt thực thể**.

1. Trong phần **Hợp nhất các tùy chọn**, chọn các thực thể bạn muốn áp dụng quy tắc chống trùng lặp.

1. Chỉ định cách hợp nhất các bản ghi trùng lặp và chọn một trong ba tùy chọn hợp nhất:
   - *Điền nhiều nhất*: Xác định bản ghi có các thuộc tính được điền nhiều nhất là bản ghi chiến thắng. Đây là tùy chọn trộn mặc định.
   - *Gần đây nhất*: Xác định bản ghi chiến thắng dựa trên lần truy cập gần đây nhất. Yêu cầu ngày hoặc trường số để xác định lần truy cập gần đây.
   - *Cách đây xa nhất*: Xác định bản ghi chiến thắng dựa trên lần truy cập cách đây xa nhất. Yêu cầu ngày hoặc trường số để xác định lần truy cập gần đây.
 
   > [!div class="mx-imgBorder"]
   > ![Quy tắc chống trùng lặp bước 1](media/match-selfconflation.png "Quy tắc chống trùng lặp bước 1")
 
1. Sau khi các thực thể được chọn và tùy chọn trộn của chúng được đặt, hãy chọn **Tạo quy tắc mới** để xác định các quy tắc chống trùng lặp ở cấp thực thể.
   - **Chọn trường** liệt kê tất cả các trường có sẵn từ thực thể mà bạn muốn chống trùng lặp dữ liệu nguồn.
   - Chỉ định cài đặt chuẩn hóa và độ chính xác theo cách tương tự như được chỉ định trong so khớp thực thể chéo.
   - Bạn có thể xác định các điều kiện bổ sung bằng cách chọn **Thêm điều kiện**.
 
   > [!div class="mx-imgBorder"]
   > ![Quy tắc chống trùng lặp bước 2](media/match-selfconflation-rules.png "Quy tắc chống trùng lặp bước 2")

  Bạn có thể tạo nhiều quy tắc chống trùng lặp cho một thực thể. 

1. Chạy quy trình so khớp hiện sẽ nhóm các bản ghi dựa trên các điều kiện được xác định trong quy tắc chống trùng lặp. Sau khi nhóm các bản ghi, chính sách trộn được áp dụng để xác định bản ghi chiến thắng.

1. Bản ghi người chiến thắng này sau đó được chuyển cho so khớp thực thể chéo.

1. Bất kỳ quy tắc so khớp tùy chỉnh nào được xác định luôn so khớp và không bao giờ so khớp sẽ được ưu tiên hơn quy tắc chống trùng lặp. Nếu quy tắc chống trùng lặp xác định các bản ghi phù hợp và quy tắc so khớp tùy chỉnh được đặt để không bao giờ khớp với các bản ghi đó, thì hai bản ghi này sẽ không được khớp.

1. Sau khi chạy quá trình so khớp, bạn sẽ thấy số liệu thống kê về chống trùng lặp.
   
> [!NOTE]
> Việc chỉ định các quy tắc chống trùng lặp là không bắt buộc. Nếu không có quy tắc nào như vậy được định cấu hình, các quy tắc do hệ thống xác định sẽ được áp dụng. Chúng thu gọn tất cả các bản ghi có cùng tổ hợp giá trị (so khớp chính xác) từ khóa chính và các trường trong quy tắc so khớp thành một bản ghi duy nhất trước khi chuyển dữ liệu đối tượng sang so khớp nhiều đối tượng để nâng cao hiệu suất và độ chính xác của hệ thống.

## <a name="run-your-match-order"></a>Chạy thứ tự so khớp của bạn

Sau khi xác định các quy tắc so khớp, bao gồm so khớp nhiều thực thể và quy tắc chống trùng lặp, bạn có thể chạy lệnh so khớp. Trên trang **So khớp**, chọn **Chạy** để bắt đầu quy trình. Thuật toán so khớp có thể mất một thời gian để hoàn thành. Bạn không thể thay đổi thuộc tính trên trang **So khớp** cho đến khi quá trình khớp hoàn thành. Bạn sẽ tìm thấy thực thể hồ sơ khách hàng hợp nhất đã được tạo trên trang **Các thực thể**. Thực thể khách hàng hợp nhất của bạn được gọi là **ConflationMatchPairs : CustomerInsights**.

Để thực hiện các thay đổi bổ sung và chạy lại bước này, bạn có thể hủy so khớp đang thực hiện. Chọn văn bản **Đang làm mới ...** rồi chọn **Hủy công việc** ở cuối ngăn bên xuất hiện.

Khi quá trình so khớp hoàn thành, văn bản **Đang làm mới ...** sẽ thay đổi thành **Thành công** và bạn có thể sử dụng tất cả chức năng của trang lần nữa.

Quá trình khớp đầu tiên sẽ tạo ra một thực thể chính hợp nhất. Tất cả các lần chạy so khớp tiếp theo sẽ mở rộng thực thể đó.

> [!TIP]
> Có [6 loại trạng thái](system.md#status-types) cho các nhiệm vụ/quy trình. Ngoài ra, hầu hết các quy trình [phụ thuộc vào các quá trình hạ nguồn khác](system.md#refresh-policies). Bạn có thể chọn trạng thái của một quy trình để xem chi tiết về tiến trình của toàn bộ công việc. Sau khi chọn **Xem chi tiết** đối với một trong các tác vụ của công việc, bạn sẽ tìm thấy thông tin bổ sung: thời gian xử lý, ngày xử lý gần nhất và tất cả các lỗi và cảnh báo liên quan đến tác vụ.

## <a name="review-and-validate-your-matches"></a>Xem lại và xác thực các so khớp của bạn

Đánh giá chất lượng của các cặp so khớp của bạn và tinh chỉnh nó:

- Trên trang **So khớp**, bạn sẽ tìm thấy hai lát hiển thị thông tin chi tiết ban đầu về dữ liệu của bạn.

  - **Khách hàng duy nhất**: hiển thị số lượng hồ sơ duy nhất mà hệ thống đã xác định.
  - **Hồ sơ đã so khớp**: hiển thị số lượng so khớp trên tất cả các cặp so khớp của bạn.

- Trong bảng **Thứ tự so khớp**, bạn có thể đánh giá kết quả của từng cặp so khớp bằng cách so sánh số lượng bản ghi xuất phát từ thực thể cặp đối sánh này với tỷ lệ phần trăm của các bản ghi được khớp thành công.

- Trong phần **Quy tắc** của một thực thể trong bảng **Thứ tự khớp**, bạn sẽ tìm thấy tỷ lệ phần trăm của các bản ghi khớp thành công ở cấp quy tắc. Bằng cách chọn biểu tượng bảng bên cạnh quy tắc, bạn có thể xem tất cả các bản ghi này ở cấp quy tắc. Chúng tôi khuyên bạn nên xem lại một tập hợp con của các bản ghi để xác thực rằng chúng được khớp chính xác.

- Thử nghiệm với các ngưỡng chính xác khác nhau xung quanh các điều kiện của bạn để xác định giá trị tối ưu.

  1. Chọn dấu chấm lửng (...) cho quy tắc cặp so khớp mà bạn muốn thử nghiệm và chọn **Chỉnh sửa**.

  2. Chọn điều kiện mà bạn muốn thử nghiệm. Mỗi tiêu chí được thể hiện bằng một hàng trong ngăn **Quy tắc khớp**.

  3. Bạn sẽ thấy gì trên trang **Xem trước tiêu chí** phụ thuộc vào mức độ chính xác bạn đã chọn cho một điều kiện. Tìm số lượng hồ sơ đã khớp và chưa khớp cho điều kiện được chọn.

     Nhận thông tin chi tiết về hiệu quả của các mức ngưỡng khác nhau. Bạn có thể so sánh số lượng bản ghi sẽ được khớp theo từng mức ngưỡng và xem các bản ghi dưới mỗi tùy chọn. Chọn từng ô và xem lại dữ liệu trong phần bảng.

## <a name="optimize-your-matches"></a>Tối ưu hóa các so khớp của bạn

Tăng chất lượng bằng cách cấu hình lại một số thông số so khớp của bạn:

- **Thay đổi thứ tự khớp** bằng cách chọn **Chỉnh sửa** và thay đổi các trường thứ tự khớp.

  > [!div class="mx-imgBorder"]
  > ![Chỉnh sửa thứ tự so khớp dữ liệu](media/configure-data-match-order-edit.png "Chỉnh sửa thứ tự so khớp dữ liệu")

- **Thay đổi thứ tự các quy tắc của bạn** nếu bạn đã xác định nhiều quy tắc. Bạn có thể sắp xếp lại các quy tắc khớp bằng cách chọn các tùy chọn **Di chuyển lên** và **Di chuyển xuống** trong lưới quy tắc so khớp.

  > [!div class="mx-imgBorder"]
  > ![Thay đổi thứ tự quy tắc](media/configure-data-change-rule-order.png "Thay đổi thứ tự quy tắc")

- **Sao chép quy tắc của bạn** nếu bạn đã xác định quy tắc khớp và muốn tạo quy tắc tương tự với sửa đổi. Làm như vậy bằng cách chọn **Sao chép**.

  > [!div class="mx-imgBorder"]
  > ![Sao chép quy tắc](media/configure-data-duplicate-rule.png "Sao chép quy tắc")

- **Chỉnh sửa quy tắc của bạn** bằng cách chọn biểu tượng **Chỉnh sửa**. Bạn có thể áp dụng các thay đổi sau:

  - Thay đổi thuộc tính cho một điều kiện: Chọn các thuộc tính mới trong hàng điều kiện cụ thể.
  - Thay đổi ngưỡng cho một điều kiện: Điều chỉnh thanh trượt chính xác.
  - Thay đổi phương thức chuẩn hóa cho một điều kiện: Cập nhật phương thức chuẩn hóa.

## <a name="specify-your-custom-match-records"></a>Chỉ định hồ sơ so khớp tùy chỉnh của bạn

Bạn có thể chỉ định các điều kiện mà hồ sơ phải luôn khớp hoặc không bao giờ khớp. Các quy tắc này có thể được tải lên hàng loạt vào quá trình khớp.

1. Chọn tùy chọn **So khớp tùy chỉnh** trên màn hình **Thứ tự khớp**.

   > [!div class="mx-imgBorder"]
   > ![Tạo so khớp tùy chỉnh](media/custom-match-create.png "Tạo so khớp tùy chỉnh")

2. Nếu bạn không có thực thể được tải lên, bạn sẽ thấy một hộp thoại **So khớp tùy chỉnh** mới yêu cầu bạn điền một số chi tiết. Nếu bạn đã cung cấp các chi tiết này trước đó, hãy tới bước 8.

   > [!div class="mx-imgBorder"]
   > ![Hộp thoại so khớp tùy chỉnh mới](media/custom-match-new-dialog-box.png "Hộp thoại so khớp tùy chỉnh mới")

3. Chọn **Điền vào mẫu** để có được một tệp mẫu có thể chỉ định các bản ghi mà từ đó các thực thể phải luôn khớp hoặc không bao giờ khớp. Bạn sẽ cần điền riêng vào các bản ghi "luôn khớp" và các bản ghi "không bao giờ khớp" trong hai tệp khác nhau.

4. Mẫu chứa các trường để chỉ định thực thể và các giá trị khóa chính của thực thể sẽ được sử dụng trong đối sánh tùy chỉnh. Ví dụ: nếu bạn muốn khóa chính 12345 từ thực thể Bán hàng luôn khớp với khóa chính 34567 từ thực thể Liên hệ, bạn sẽ cần chỉ định như sau:
    - Thực thể 1: Bán hàng
    - Entity1Key: 12345
    - Thực thể 2: Người liên hệ
    - Entity2Key: 34567

   Cùng một tệp mẫu có thể chỉ định các bản ghi so khớp tùy chỉnh từ nhiều thực thể.

5. Sau khi thêm tất cả các phần ghi đè bạn muốn áp dụng, hãy lưu tệp mẫu.

6. Đi tới **Dữ liệu** > **Nguồn dữ liệu** và nhập các tệp mẫu dưới dạng thực thể mới. Sau khi nhập, bạn có thể sử dụng chúng để chỉ định cấu hình So khớp.

7. Sau khi tải lên các tệp và thực thể có sẵn, chọn tùy chọn **So khớp tùy chỉnh** một lần nữa. Bạn sẽ thấy các tùy chọn để chỉ định các thực thể bạn muốn bao gồm. Chọn thực thể bắt buộc từ menu thả xuống.

   > [!div class="mx-imgBorder"]
   > ![Ghi đè so khớp tùy chỉnh](media/custom-match-overrides.png "Ghi đè so khớp tùy chỉnh")

8. Chọn các thực thể bạn muốn sử dụng cho **Luôn so khớp** và **Không bao giờ khớp**, chọn **Xong**.

9. Chọn **Lưu** trên trang **So khớp** cho cấu hình khớp tùy chỉnh bạn vừa thiết lập.

10. Chọn **Chạy** trên trang **So khớp** để bắt đầu quá trình khớp và cấu hình khớp tùy chỉnh sẽ có hiệu lực. Mọi quy tắc phù hợp với hệ thống đều bị ghi đè bởi bộ cấu hình.

11. Khi quá trình so khớp hoàn tất, bạn có thể xác minh thực thể **ConflationMatchPair** để xác nhận rằng các phần ghi đè được áp dụng trong các so khớp có thể hợp nhất.

## <a name="next-step"></a>Bước tiếp theo

Sau khi hoàn thành quy trình đối sánh cho ít nhất một cặp đối sánh, bạn có thể giải quyết các mâu thuẫn có thể có trong dữ liệu của mình bằng cách tham khảo chủ đề [**Hợp nhất**](merge-entities.md).
