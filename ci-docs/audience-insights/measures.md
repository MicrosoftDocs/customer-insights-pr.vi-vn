---
title: Tạo và chỉnh sửa các giá trị đo
description: Xác định các chỉ số đo lường liên quan đến khách hàng để phân tích và phản ánh hiệu suất của các lĩnh vực kinh doanh nhất định.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 0e214a6eb66abd27f7292db3ce2c2a6e16a8ff33
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407332"
---
# <a name="define-and-manage-measures"></a>Xác định và quản lý các biện pháp

**Giá trị đo** đại diện cho các chỉ số đo lường hiệu suất chính (KPI) phản ánh hiệu suất và tình trạng của các lĩnh vực kinh doanh cụ thể. Thông tin chi tiết về đối tượng cung cấp trải nghiệm trực quan để xây dựng các loại giá trị đo khác nhau, sử dụng trình tạo truy vấn không yêu cầu bạn viết mã hoặc xác thực các giá trị đo của mình theo cách thủ công. Bạn có thể theo dõi các giá trị đo công việc trên **Trang chủ**, xem các giá trị đo cho khách hàng cụ thể trên **Thẻ khách hàng** và sử dụng các giá trị đo để xác định phân khúc khách hàng trên trang **Phân khúc**.

## <a name="create-a-measure"></a>Tạo giá trị đo

Phần này hướng dẫn bạn tạo một giá trị đo từ đầu. Bạn có thể xây dựng các giá trị đo với dữ liệu từ nhiều nguồn dữ liệu được kết nối thông qua thực thể Khách hàng. Một số [giới hạn dịch vụ](service-limits.md) được áp dụng.

1. Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Giá trị đo**.

2. Chọn **Giá trị đo mới**.

3. Chọn giá trị **Loại**:

   - **Thuộc tính khách hàng**: Một trường duy nhất cho mỗi khách hàng phản ánh điểm số, giá trị hoặc trạng thái cho khách hàng. Các thuộc tính khách hàng được tạo như các thuộc tính trong một thực thể mới do hệ thống tạo ra được gọi là **Giá trị đo Khách hàng**.

   - **Giá trị đo khách hàng**: Thông tin chi tiết về hành vi của khách hàng được phân tích theo các chỉ số đã chọn. Một thực thể mới được tạo cho mỗi giá trị đo, có khả năng có nhiều hồ sơ cho mỗi khách hàng.

   - **Giá trị đo công việc**: Theo dõi hiệu suất kinh doanh và tình trạng của doanh nghiệp. Các giá trị đo công việc có thể có hai đầu ra khác nhau: đầu ra số hiển thị trên **Trang chủ** hoặc một thực thể mới mà bạn tìm thấy trên trang **Các thực thể**.

4. Cung cấp một **Tên** và một **Tên hiển thị** hiển thị, sau đó chọn **Tiếp theo**.

5. Trong phần **Thực thể**, chọn thực thể đầu tiên từ danh sách thả xuống. Tại thời điểm này, bạn nên quyết định xem có cần thực thể bổ sung như là một phần của định nghĩa giá trị đo của bạn hay không.

   > [!div class="mx-imgBorder"]
   > ![Định nghĩa số liệu đo lường](media/measure-definition.png "Định nghĩa số liệu đo lường")

   Để thêm các thực thể khác, chọn **Thêm thực thể** và chọn thực thể bạn muốn dùng cho giá trị đo đó.

   > [!NOTE]
   > Bạn chỉ có thể chọn các thực thể có mối quan hệ với thực thể bắt đầu của bạn. Để biết thêm thông tin định nghĩa mối quan hệ, hãy xem [Mối quan hệ](relationships.md).

6. Hoặc bạn có thể cấu hình các biến. Trong phần **Biến**, chọn **Biến mới**.

   Các biến là các tính toán được thực hiện trên mỗi bản ghi đã chọn của bạn. Ví dụ: tổng hợp điểm bán hàng (POS) và bán hàng trực tuyến cho mỗi hồ sơ của khách hàng của bạn.

7. Cung cấp **Tên** cho biến.

8. Trong khu vực **Biểu thức**, chọn một trường để bắt đầu tính toán.

9. Nhập một biểu thức trong khu vực **Biểu thức** trong khi chọn nhiều trường được đưa vào tính toán của bạn.

   > [!NOTE]
   > Hiện tại, chỉ có biểu thức số học được hỗ trợ. Ngoài ra, tính toán biến không được hỗ trợ cho các thực thể từ [đường dẫn thực thể](relationships.md) khác.

10. Chọn **Xong**.

11. Trong phần **Định nghĩa số liệu đo lường**, bạn sẽ xác định cách các thực thể được chọn và các biến được tính toán được tổng hợp trong một thực thể hoặc thuộc tính đo lường mới.

12. Chọn **Kích thước mới**. Bạn có thể coi một kích thước là một hàm *nhóm theo*. Đầu ra dữ liệu của thực thể hoặc thuộc tính Giá trị đo sẽ được nhóm theo tất cả kích thước bạn xác định.

    > [!div class="mx-imgBorder"]
    > ![Chọn chu kỳ tổng hợp](media/measures-businessreport-measure-definition2.png "Chọn chu kỳ tổng hợp")

    Chọn hoặc nhập thông tin sau đây như một phần định nghĩa của kích thước của bạn:

    - **Thực thể**: Nếu bạn xác định thực thể Giá trị đo, nó sẽ bao gồm ít nhất một thuộc tính. Nếu bạn xác định thuộc tính Giá trị đo, nó sẽ chỉ bao gồm một thuộc tính theo mặc định. Lựa chọn này là về việc chọn thực thể bao gồm thuộc tính đó.
    - **Trường**: Chọn thuộc tính cụ thể được bao gồm trong thực thể hoặc thuộc tính Giá trị đo.
    - **Bộ chứa**: Chọn xem bạn muốn tổng hợp dữ liệu hàng ngày, hàng tháng hoặc hàng năm. Đó chỉ là lựa chọn bắt buộc nếu bạn đã chọn thuộc tính loại Ngày.
    - **Dưới dạng**: Xác định tên của trường mới của bạn.
    - **Tên hiển thị**: Xác định tên hiển thị của trường của bạn.

    > [!NOTE]
    > Giá trị đo công việc của bạn sẽ được lưu dưới dạng một thực thể số đơn và sẽ xuất hiện trên **Trang chủ** trừ khi bạn thêm nhiều kích thước vào số đo của bạn. Sau khi thêm nhiều kích thước, giá trị đo sẽ *không* hiện lên trên **Trang chủ**.

13. Bạn cũng có thể thêm các hàm tổng hợp. Bất kỳ tổng hợp nào bạn tạo sẽ dẫn đến trong một giá trị mới trong thực thể hoặc thuộc tính Giá trị đo. Các hàm tổng hợp được hỗ trợ là: **Min**, **Max**, **Average**, **Median**, **Sum**, **Count Unique**, **First** (lấy bản ghi đầu tiên của giá trị chỉ số) và **Last** (lấy bản ghi cuối cùng được thêm vào giá trị chỉ số).

14. Chọn **Lưu** để áp dụng các thay đổi cho giá trị đo.

## <a name="manage-your-measures"></a>Quản lý các giá trị đo của bạn

Sau khi tạo ít nhất một giá trị đo, bạn sẽ thấy danh sách các giá trị đo trên trang **Giá trị đo**.

Bạn sẽ tìm thấy thông tin về loại giá trị đo, người tạo, ngày và giờ tạo, ngày và giờ chỉnh sửa cuối cùng, trạng thái (cho dù giá trị đo đó đang hoạt động, không hoạt động hay lỗi) và ngày và giờ làm mới lần cuối. Khi bạn chọn một giá trị đo từ danh sách, bạn có thể thấy bản xem trước của đầu ra.

Để làm mới tất cả các giá trị đo của bạn cùng một lúc, hãy chọn **Làm mới tất cả** mà không chọn một giá trị đo cụ thể.

> [!div class="mx-imgBorder"]
> ![Các hành động để quản lý các giá trị đo đơn lẻ](media/measure-actions.png "Các hành động để quản lý các giá trị đo đơn lẻ")

Hoặc, chọn một giá trị đo từ danh sách và thực hiện một trong các hành động sau:

- Chọn tên giá trị đo để xem chi tiết về giá trị đo đó.
- **Chỉnh sửa** cấu hình của giá trị đo.
- **Đổi tên** giá trị đo.
- **Xóa** giá trị đo.
- Chọn dấu chấm lửng (...) rồi sau đó **Làm mới** để bắt đầu quá trình làm mới cho giá trị đo.
- Chọn dấu chấm lửng (...) và sau đó **Tải xuống** để tải tệp .CSV của giá trị đo.

> [!TIP]
> Có [6 loại trạng thái](system.md#status-types) cho các nhiệm vụ/quy trình. Ngoài ra, hầu hết các quy trình [phụ thuộc vào các quá trình hạ nguồn khác](system.md#refresh-policies). Bạn có thể chọn trạng thái của một quy trình để xem chi tiết về tiến trình của toàn bộ công việc. Sau khi chọn **Xem chi tiết** đối với một trong các tác vụ của công việc, bạn sẽ tìm thấy thông tin bổ sung: thời gian xử lý, ngày xử lý gần nhất và tất cả các lỗi và cảnh báo liên quan đến tác vụ.

## <a name="next-step"></a>Bước tiếp theo

Bạn có thể sử dụng các giá trị đo hiện có để tạo phân khúc khách hàng đầu tiên của mình trên trang **Phân khúc**. Để biết thêm thông tin, hãy xem [Phân khúc](segments.md).
