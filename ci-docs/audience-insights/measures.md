---
title: Tạo và quản lý các giá trị đo
description: Xác định các giá trị đo để phân tích và phản ánh tình hình hoạt động của doanh nghiệp bạn.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 3593a02ce89233cf1e66c6beee669dd6dd261ba3b0e1d2d0cc966731349d7d0b
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 08/10/2021
ms.locfileid: "7037034"
---
# <a name="define-and-manage-measures"></a>Xác định và quản lý các biện pháp

Giá trị đo giúp bạn hiểu rõ hơn về hành vi của khách hàng và hiệu quả kinh doanh. Giá trị đo xem xét các giá trị có liên quan từ [hồ sơ hợp nhất](data-unification.md). Ví dụ: một doanh nghiệp muốn xem *tổng mức chi tiêu của mỗi khách hàng* để nắm được lịch sử mua hàng của một khách hàng cá nhân hoặc đo lường *tổng doanh số của công ty* để nắm được tổng doanh thu của toàn bộ doanh nghiệp.  

Các giá trị đo được tạo bằng cách sử dụng trình tạo giá trị đo, một nền tảng truy vấn dữ liệu với các toán tử khác nhau và các tùy chọn ánh xạ đơn giản. Nó cho phép bạn lọc dữ liệu, nhóm kết quả, phát hiện [đường dẫn mối quan hệ thực thể](relationships.md) và xem trước đầu ra.

Hãy sử dụng trình tạo giá trị đo để lập kế hoạch hoạt động kinh doanh bằng cách truy vấn dữ liệu khách hàng và trích xuất thông tin chi tiết. Ví dụ: tạo một giá trị đo *tổng chi tiêu mỗi khách hàng* và *tổng lợi nhuận trên mỗi khách hàng* giúp xác định nhóm khách hàng có mức chi tiêu cao nhưng lợi nhuận thu về cao. Bạn có thể [tạo một phân đoạn](segments.md) để thúc đẩy các hành động tốt nhất tiếp theo. 

## <a name="build-your-own-measure-from-scratch"></a>Tạo giá trị đo của riêng bạn từ đầu

Phần này sẽ hướng dẫn bạn cách tạo một giá trị đo mới từ đầu. Bạn có thể tạo một giá trị đo với các thuộc tính dữ liệu từ các thực thể dữ liệu có mối quan hệ được thiết lập để kết nối với thực thể Khách hàng. 

1. Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Giá trị đo**.

1. Chọn **Mới** rồi chọn **Tạo giá trị đo riêng**.

1. Chọn **Chỉnh sửa tên** và cung cấp một **Tên** cho giá trị đo. 
   > [!NOTE]
   > Nếu cấu hình giá trị đo mới của bạn chỉ có hai trường, ví dụ: CustomerID và một phép tính thì kết quả đầu ra sẽ được thêm vào thực thể do hệ thống tạo ra có tên là Customer_Measure dưới dạng một cột mới. Và bạn sẽ có thể thấy giá trị của giá trị đo trong hồ sơ khách hàng hợp nhất. Các giá trị đo khác sẽ tạo ra các thực thể của riêng chúng.

1. Trong vùng cấu hình, hãy chọn hàm tổng hợp từ menu thả xuống **Chọn hàm**. Các hàm tổng hợp bao gồm: 
   - **Sum**
   - **Trung bình**
   - **Đếm**
   - **Số đếm Duy nhất**
   - **Tối đa**
   - **Min**
   - **Đầu tiên**: lấy giá trị đầu tiên của bản ghi dữ liệu
   - **Cuối cùng**: lấy giá trị cuối cùng đã được thêm vào bản ghi dữ liệu

   :::image type="content" source="media/measure-operators.png" alt-text="Các toán tử để tính toán giá trị đo.":::

1. Chọn **Thêm thuộc tính** để chọn dữ liệu bạn cần để tạo giá trị đo này.
   
   1. Chọn thẻ **Thuộc tính**. 
   1. Thực thể dữ liệu: Chọn thực thể bao gồm thuộc tính bạn muốn đo. 
   1. Thuộc tính dữ liệu: Chọn thuộc tính bạn muốn sử dụng trong hàm tổng hợp để tính toán giá trị đo. Mỗi lần, bạn chỉ có thể chọn một thuộc tính.
   1. Bạn cũng có thể chọn một thuộc tính dữ liệu từ một giá trị đo hiện có bằng cách chọn thẻ **Giá trị đo**. Hoặc bạn có thể tìm kiếm một thực thể hoặc tên giá trị đo. 
   1. Chọn **Thêm** để thêm thuộc tính đã chọn vào giá trị đo.

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Chọn một thuộc tính để sử dụng trong tính toán.":::

1. Để xây dựng các giá trị đo phức tạp hơn, bạn có thể thêm nhiều thuộc tính hơn hoặc sử dụng các toán tử toán học trên hàm đo lường của mình.

   :::image type="content" source="media/measure-math-operators.png" alt-text="Tạo một giá trị đo phức tạp với các toán tử toán học.":::

1. Để thêm bộ lọc, hãy chọn **Bộ lọc** trong vùng cấu hình. 
  
   1. Trong phần **Thêm thuộc tính** của ngăn **Bộ lọc**, chọn thuộc tính bạn muốn sử dụng để tạo bộ lọc.
   1. Đặt toán tử bộ lọc để xác định bộ lọc cho mọi thuộc tính đã chọn.
   1. Chọn **Áp dụng** để thêm các bộ lọc vào giá trị đo.

1. Để thêm các thứ nguyên, hãy chọn **Thứ nguyên** trong vùng cấu hình. Thứ nguyên sẽ hiển thị dưới dạng cột trong thực thể đầu ra giá trị đo.
 
   1. Chọn **Chỉnh sửa thứ nguyên** để thêm các thuộc tính dữ liệu mà bạn muốn nhóm các giá trị đo lường. Ví dụ: thành phố hoặc giới tính. Theo mặc định, thứ nguyên *ID khách hàng* được chọn để tạo *giá trị đo cấp khách hàng*. Bạn có thể xóa thứ nguyên mặc định nếu muốn tạo *giá trị đo cấp doanh nghiệp*.
   1. Chọn **Xong** để thêm các thứ nguyên vào giá trị đo.

1. Nếu có các giá trị trong dữ liệu của bạn mà bạn cần thay thế bằng một số nguyên, chẳng hạn như thay thế *null* bằng *0*, hãy chọn **Quy tắc**. Định cấu hình quy tắc và đảm bảo rằng bạn chỉ chọn các số nguyên làm giá trị thay thế.

1. Nếu có nhiều đường dẫn giữa thực thể dữ liệu bạn đã ánh xạ và thực thể *Khách hàng*,bạn phải chọn một trong các [đường dẫn mối quan hệ thực thể](relationships.md) đã xác định. Kết quả giá trị đo có thể khác nhau tùy thuộc vào đường dẫn đã chọn. 
   
   1. Chọn **Tùy chọn dữ liệu** và chọn đường dẫn thực thể sẽ được sử dụng để xác định giá trị đo của bạn. Nếu chỉ có một đường dẫn đến thực thể *Khách hàng*, điều khiển này sẽ không hiển thị.
   1. Chọn **Xong** để áp dụng lựa chọn của bạn. 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Chọn đường dẫn thực thể cho giá trị đo đó.":::

1. Để thêm các phép tính khác cho giá trị đo đó, hãy chọn **Tính toán mới**. Bạn chỉ có thể sử dụng các thực thể trên cùng một đường dẫn thực thể cho các phép tính mới. Các phép tính khác sẽ hiển thị dưới dạng cột mới trong thực thể đầu ra giá trị đo.

1. Chọn **...** trên phép tính để **Nhân bản**, **Đổi tên** hoặc **Xóa** phép tính khỏi giá trị đo.

1. Trong ngăn **Xem trước**, bạn sẽ thấy giản đồ dữ liệu của thực thể đầu ra giá trị đo, bao gồm các bộ lọc và thứ nguyên. Bản xem trước phản ứng tự động với các thay đổi trong cấu hình.

1. Chọn **Chạy** để tính toán kết quả cho giá trị đo đã định cấu hình. Chọn **Lưu và đóng** nếu bạn muốn giữ cấu hình hiện tại và chạy giá trị đo sau.

1. Đi đến **Giá trị đo** để xem số đo mới được tạo trong danh sách.

## <a name="use-a-template-to-build-a-measure"></a>Sử dụng mẫu để tạo giá trị đo

Bạn có thể sử dụng các mẫu định sẵn có chứa các giá trị đo thường dùng để tạo giá trị đo. Mô tả chi tiết về các mẫu và trải nghiệm có hướng dẫn sẽ giúp bạn tạo giá trị đo hiệu quả. Các mẫu xây dựng dựa trên dữ liệu được ánh xạ từ thực thể *Hoạt động được hợp nhất*. Vì vậy, hãy đảm bảo rằng bạn đã định cấu hình [hoạt động của khách hàng](activities.md) trước khi tạo giá trị đo từ một mẫu.

Các mẫu giá trị đo sẵn có: 
- Giá trị giao dịch trung bình (ATV)
- Tổng giá trị giao dịch
- Doanh thu trung bình hàng ngày
- Doanh thu trung bình hàng năm
- Số lượng giao dịch
- Điểm khách hàng thân thiết kiếm được
- Điểm khách hàng thân thiết đã quy đổi
- Số dư điểm khách hàng thân thiết
- Quãng thời gian khách hàng hoạt động
- Thời lượng là thành viên khách hàng thân thiết
- Thời gian kể từ giao dịch mua gần nhất

Quy trình sau đây phác thảo các bước để tạo giá trị đo mới bằng cách sử dụng một mẫu.

1. Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Giá trị đo**.

1. Chọn **Mới** rồi chọn **Chọn một mẫu**.

   :::image type="content" source="media/measure-use-template.png" alt-text="Ảnh chụp màn hình của menu thả xuống khi tạo một giá trị đo mới được tô sáng trên mẫu.":::

1. Tìm mẫu phù hợp với nhu cầu của bạn rồi chọn **Chọn mẫu**.

1. Xem lại dữ liệu bắt buộc rồi chọn **Bắt đầu** nếu bạn có sẵn tất cả dữ liệu.

1. Trong ngăn **Chỉnh sửa tên**, hãy đặt tên cho giá trị đo của bạn và thực thể đầu ra. 

1. Chọn **Xong**.

1. Trong phần **Đặt khoảng thời gian**, hãy xác định khung thời gian của dữ liệu sẽ sử dụng. Chọn **Mọi lúc** nếu bạn muốn giá trị đo mới bao quát toàn bộ tập dữ liệu hoặc chọn **Khoảng thời gian cụ thể** nếu muốn giá trị đo tập trung vào một khoảng thời gian.

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Ảnh chụp màn hình về phần khoảng thời gian khi định cấu hình giá trị đo từ một mẫu.":::

1. Trong phần tiếp theo, hãy chọn **Thêm dữ liệu** để chọn các hoạt động rồi ánh xạ dữ liệu tương ứng từ thực thể *Hoạt động được hợp nhất*.

    1. Bước 1/2: Trong mục **Loại hoạt động**, hãy chọn loại thực thể mà bạn muốn sử dụng. Đối với **Hoạt động**, hãy chọn các thực thể mà bạn muốn ánh xạ.
    1. Bước 2/2: Chọn thuộc tính từ *Hoạt động được hợp nhất* cho thành phần theo yêu cầu của công thức. Ví dụ: đối với giá trị giao dịch Trung bình, đó là thuộc tính đại diện cho Giá trị giao dịch. Đối với **Dấu thời gian hoạt động**, hãy chọn thuộc tính từ thực thể Hoạt động được hợp nhất đại diện cho ngày và giờ của hoạt động.
   
1. Khi ánh xạ dữ liệu thành công, bạn có thể thấy trạng thái là **Hoàn thành** cũng như tên của các hoạt động và thuộc tính được ánh xạ.

   :::image type="content" source="media/measure-template-configured.png" alt-text="Ảnh chụp màn hình về cấu hình mẫu giá trị đo đã hoàn thành.":::

1. Bây giờ, bạn có thể chọn **Chạy** để tính toán kết quả của giá trị đo. Để tinh chỉnh giá trị đo về sau, hãy chọn **Lưu bản nháp**.

## <a name="manage-your-measures"></a>Quản lý các giá trị đo của bạn

Bạn có thể tìm thấy danh sách các giá trị đo trên trang **Giá trị đo**.

Bạn sẽ tìm thấy thông tin về loại giá trị đo, người tạo, ngày tạo, trạng thái và tình trạng. Khi chọn một giá trị đo từ danh sách, bạn có thể xem trước kết quả đầu ra và tải xuống tệp CSV.

Để làm mới tất cả các giá trị đo của bạn cùng một lúc, hãy chọn **Làm mới tất cả** mà không chọn một giá trị đo cụ thể.

> [!div class="mx-imgBorder"]
> ![Các hành động để quản lý các giá trị đo đơn lẻ.](media/measure-actions.png "Các hành động để quản lý các giá trị đo đơn lẻ.")

Chọn một giá trị đo từ danh sách cho các tùy chọn sau:

- Chọn tên giá trị đo để xem chi tiết về giá trị đo đó.
- **Chỉnh sửa** cấu hình của giá trị đo.
- **Làm mới** giá trị đo dựa trên dữ liệu mới nhất.
- **Đổi tên** giá trị đo.
- **Xóa** giá trị đo.
- **Kích hoạt** hoặc **hủy kích hoạt**. Các giá trị đo không hoạt động sẽ không được làm mới trong [quá trình làm mới theo lịch trình](system.md#schedule-tab).

> [!TIP]
> Có [6 loại trạng thái](system.md#status-types) cho các nhiệm vụ/quy trình. Ngoài ra, hầu hết các quy trình [phụ thuộc vào các quá trình hạ nguồn khác](system.md#refresh-policies). Bạn có thể chọn trạng thái của một quy trình để xem chi tiết về tiến trình của toàn bộ công việc. Sau khi chọn **Xem chi tiết** đối với một trong các nhiệm vụ của công việc, bạn sẽ tìm thấy thông tin bổ sung như: thời gian xử lý, ngày xử lý cuối cùng và tất cả các lỗi cũng như cảnh báo liên quan đến nhiệm vụ.

## <a name="next-step"></a>Bước tiếp theo

Bạn có thể sử dụng các giá trị đo hiện có để tạo [một phân khúc khách hàng](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
