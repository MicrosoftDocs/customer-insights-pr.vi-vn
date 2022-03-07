---
title: Tạo và quản lý các giá trị đo
description: Xác định các giá trị đo để phân tích và phản ánh tình hình hoạt động của doanh nghiệp bạn.
ms.date: 02/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 5bcee3b4c51880740715575b18fd7a4dbf87e6d0
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269954"
---
# <a name="define-and-manage-measures"></a>Xác định và quản lý các biện pháp

Các giá trị đo giúp bạn hiểu rõ hơn về hành vi của khách hàng và hiệu suất kinh doanh bằng cách truy xuất các giá trị có liên quan từ [hồ sơ thống nhất](data-unification.md). Ví dụ: một doanh nghiệp muốn xem *tổng chi tiêu mỗi khách hàng* để hiểu lịch sử mua hàng của từng khách hàng. Hoặc đo lường *tổng doanh số của công ty* để hiểu tổng doanh thu trong toàn bộ doanh nghiệp.  

Các giá trị đo được tạo bằng cách sử dụng trình tạo giá trị đo, một nền tảng truy vấn dữ liệu với các toán tử khác nhau và các tùy chọn ánh xạ đơn giản. Nó cho phép bạn lọc dữ liệu, nhóm kết quả, phát hiện [đường dẫn mối quan hệ thực thể](relationships.md) và xem trước đầu ra.

Hãy sử dụng trình tạo giá trị đo để lập kế hoạch hoạt động kinh doanh bằng cách truy vấn dữ liệu khách hàng và trích xuất thông tin chi tiết. Ví dụ: tạo một giá trị đo *tổng chi tiêu mỗi khách hàng* và *tổng lợi nhuận trên mỗi khách hàng* giúp xác định nhóm khách hàng có mức chi tiêu cao nhưng lợi nhuận thu về cao. Bạn có thể [tạo một phân đoạn](segments.md) để thúc đẩy các hành động tốt nhất tiếp theo. 

## <a name="create-a-measure"></a>Tạo giá trị đo

Phần này sẽ hướng dẫn bạn cách tạo một giá trị đo mới từ đầu. Bạn có thể tạo một giá trị đo với các thuộc tính dữ liệu từ các thực thể dữ liệu có mối quan hệ được thiết lập để kết nối với thực thể Khách hàng. 

1. Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Giá trị đo**.

1. Chọn **Mới**.

1. Chọn **Chỉnh sửa tên** và cung cấp một **Tên** cho giá trị đo. 
   > [!NOTE]
   > Nếu cấu hình giá trị đo mới của bạn chỉ có hai trường, ví dụ CustomerID và một phép tính, đầu ra sẽ được thêm dưới dạng một cột mới vào thực thể do hệ thống tạo có tên là Customer_Measure. Và bạn sẽ có thể thấy giá trị của giá trị đo trong hồ sơ khách hàng hợp nhất. Các giá trị đo khác sẽ tạo ra các thực thể của riêng chúng.

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
   1. Bạn cũng có thể chọn một thuộc tính dữ liệu từ một giá trị đo hiện có bằng cách chọn thẻ **Giá trị đo**. Hoặc, bạn có thể tìm kiếm một thực thể hoặc tên giá trị đo. 
   1. Chọn **Thêm** để thêm thuộc tính đã chọn vào giá trị đo.

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Chọn một thuộc tính để sử dụng trong tính toán.":::

1. Để xây dựng các giá trị đo phức tạp hơn, bạn có thể thêm nhiều thuộc tính hơn hoặc sử dụng các toán tử toán học trên hàm đo lường của mình.

   :::image type="content" source="media/measure-math-operators.png" alt-text="Tạo một giá trị đo phức tạp với các toán tử toán học.":::

1. Để thêm bộ lọc, hãy chọn **Bộ lọc** trong vùng cấu hình. 
  
   1. Trong mục **Thêm thuộc tính** của ngăn **Bộ lọc**, hãy chọn thuộc tính bạn muốn sử dụng để tạo bộ lọc.
   1. Đặt toán tử bộ lọc để xác định bộ lọc cho mọi thuộc tính đã chọn.
   1. Chọn **Áp dụng** để thêm các bộ lọc vào giá trị đo.

1. Để thêm các thứ nguyên, hãy chọn **Thứ nguyên** trong vùng cấu hình. Thứ nguyên sẽ hiển thị dưới dạng cột trong thực thể đầu ra giá trị đo.
   1. Chọn **Chỉnh sửa thứ nguyên** để thêm các thuộc tính dữ liệu mà bạn muốn nhóm các giá trị đo lường. Ví dụ: thành phố hoặc giới tính. Theo mặc định, thứ nguyên *ID khách hàng* được chọn để tạo *giá trị đo cấp khách hàng*. Bạn có thể xóa thứ nguyên mặc định nếu muốn tạo *giá trị đo cấp doanh nghiệp*.
   1. Chọn **Xong** để thêm các thứ nguyên vào giá trị đo.

1. Nếu có nhiều đường dẫn giữa thực thể dữ liệu bạn đã ánh xạ và thực thể Khách hàng, bạn phải chọn một trong những [đường dẫn mối quan hệ thực thể](relationships.md) được xác định. Kết quả giá trị đo có thể khác nhau tùy thuộc vào đường dẫn đã chọn.
   1. Chọn **Tùy chọn dữ liệu** và chọn đường dẫn thực thể sẽ được sử dụng để xác định giá trị đo của bạn.
   1. Chọn **Xong** để áp dụng lựa chọn của bạn. 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Chọn đường dẫn thực thể cho giá trị đo đó.":::

1. Để thêm các phép tính khác cho giá trị đo đó, hãy chọn **Tính toán mới**. Bạn chỉ có thể sử dụng các thực thể trên cùng một đường dẫn thực thể cho các phép tính mới. Các phép tính khác sẽ hiển thị dưới dạng cột mới trong thực thể đầu ra giá trị đo.

1. Chọn **...** trên phép tính để **Nhân bản**, **Đổi tên** hoặc **Xóa** phép tính khỏi giá trị đo.

1. Trong ngăn **Xem trước**, bạn sẽ thấy giản đồ dữ liệu của thực thể đầu ra giá trị đo, bao gồm các bộ lọc và thứ nguyên. Bản xem trước phản ứng tự động với các thay đổi trong cấu hình.

1. Chọn **Chạy** để tính toán kết quả cho giá trị đo đã định cấu hình. Chọn **Lưu và đóng** nếu bạn muốn giữ cấu hình hiện tại và chạy giá trị đo sau.

1. Đi đến **Giá trị đo** để xem số đo mới được tạo trong danh sách.

## <a name="manage-your-measures"></a>Quản lý các giá trị đo của bạn

Sau khi [tạo một giá trị đo](#create-a-measure), bạn sẽ thấy danh sách các giá trị đo trên trang **Giá trị đo**.

Bạn sẽ tìm thấy thông tin về loại giá trị đo, người tạo, ngày tạo, trạng thái và tình trạng. Khi bạn chọn một giá trị đo từ danh sách, bạn có thể xem trước kết quả đầu ra và tải xuống tệp .CSV.

Để làm mới tất cả các giá trị đo của bạn cùng một lúc, hãy chọn **Làm mới tất cả** mà không chọn một giá trị đo cụ thể.

> [!div class="mx-imgBorder"]
> ![Các hành động để quản lý các giá trị đo đơn lẻ](media/measure-actions.png "Các hành động để quản lý các giá trị đo đơn lẻ")

Chọn một giá trị đo từ danh sách cho các tùy chọn sau:

- Chọn tên giá trị đo để xem chi tiết về giá trị đo đó.
- **Chỉnh sửa** cấu hình của giá trị đo.
- **Làm mới** giá trị đo dựa trên dữ liệu mới nhất.
- **Đổi tên** giá trị đo.
- **Xóa** giá trị đo.
- **Kích hoạt** hoặc **hủy kích hoạt**. Các giá trị đo không hoạt động sẽ không được làm mới trong [quá trình làm mới theo lịch trình](system.md#schedule-tab).

> [!TIP]
> Có [6 loại trạng thái](system.md#status-types) cho các nhiệm vụ/quy trình. Ngoài ra, hầu hết các quy trình [phụ thuộc vào các quá trình hạ nguồn khác](system.md#refresh-policies). Bạn có thể chọn trạng thái của một quy trình để xem chi tiết về tiến trình của toàn bộ công việc. Sau khi chọn **Xem chi tiết** đối với một trong các tác vụ của công việc, bạn sẽ tìm thấy thông tin bổ sung: thời gian xử lý, ngày xử lý gần nhất và tất cả các lỗi và cảnh báo liên quan đến tác vụ.

## <a name="next-step"></a>Bước tiếp theo

Bạn có thể sử dụng các giá trị hiện có để tạo [một phân khúc khách hàng](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]