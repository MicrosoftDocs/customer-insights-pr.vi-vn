---
title: Tạo và quản lý phân đoạn
description: Tạo phân đoạn khách hàng để nhóm họ lại dựa trên các đặc điểm khác nhau.
ms.date: 03/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 4a6e8a3216a2c0738d60247054afa9fc18412f55
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597089"
---
# <a name="create-and-manage-segments"></a>Tạo và quản lý phân đoạn

Phân khúc cho phép bạn nhóm khách hàng của mình dựa trên các thuộc tính nhân khẩu học, giao dịch hoặc hành vi. Bạn có thể sử dụng các phân khúc để nhắm mục tiêu chiến dịch quảng cáo, hoạt động bán hàng và hành động hỗ trợ khách hàng để đạt được mục tiêu kinh doanh.

Bạn có thể xác định các bộ lọc phức hợp xung quanh thực thể Hồ sơ khách hàng và các thực thể liên quan. Mỗi phân khúc, sau khi xử lý, sẽ tạo một bộ hồ sơ khách hàng mà bạn có thể xuất và hành động. Một số [giới hạn dịch vụ](service-limits.md) được áp dụng.

Trừ khi có quy định khác, tất cả các phân khúc đều là **Phân khúc động**, được làm mới theo lịch trình định kỳ.

Ví dụ sau minh họa khả năng tạo phân khúc. Chúng tôi đã xác định một phân đoạn cho khách hàng đặt hàng hóa trị giá ít nhất $500 trong 90 ngày qua *và* đã tham gia vào cuộc gọi dịch vụ khách hàng đã báo cáo.

> [!div class="mx-imgBorder"]
> ![Nhiều nhóm](media/segmentation-group1-2.png "Nhiều nhóm")

## <a name="create-a-new-segment"></a>Tạo phân đoạn mới

Các phân khúc được quản lý trên trang **Phân khúc**.

1. Trong thông tin chi tiết về đối tượng, hãy chuyển đến trang **Phân khúc**.

1. Chọn **Mới** > **Phân đoạn trống**.

1. Trong ngăn **Phân đoạn mới**, chọn loại phân đoạn và cung cấp **Tên**.

   Bạn cũng có thể cung cấp tên hiển thị và mô tả nhằm xác định phân đoạn.

1. Chọn **Tiếp theo** để đi đến trang **Trình tạo phân đoạn** và xác định nhóm. Một nhóm là một tập hợp các khách hàng.

1. Chọn thực thể bao gồm thuộc tính mà bạn muốn tạo phân đoạn.

1. Chọn thuộc tính để tạo phân đoạn. Thuộc tính này có thể có 1 trong số 4 loại giá trị: số, chuỗi, ngày hoặc Boolean.

1. Chọn một toán tử và một giá trị cho thuộc tính đã chọn.

   > [!div class="mx-imgBorder"]
   > ![Bộ lọc nhóm tùy chỉnh](media/customer-group-numbers.png "Bộ lọc nhóm khách hàng")

   |Số |Định nghĩa  |
   |---------|---------|
   |1     |Entity          |
   |2     |Đặc điểm          |
   |3    |Toán tử         |
   |4    |Giá trị         |

8. Nếu thực thể được kết nối với thực thể khách hàng hợp nhất qua [các mối quan hệ](relationships.md), thì bạn cần xác định đường dẫn mối quan hệ để tạo một phân đoạn hợp lệ. Thêm các thực thể từ đường dẫn mối quan hệ cho đến khi bạn có thể chọn thực thể **Khách hàng : CustomerInsights** từ danh sách thả xuống. Sau đó, chọn **Tất cả bản ghi** cho mỗi điều kiện.

   > [!div class="mx-imgBorder"]
   > ![Đường dẫn mối quan hệ trong khi tạo phận đoạn](media/segments-multiple-relationships.png "Đường dẫn mối quan hệ trong khi tạo phận đoạn")

1. Theo mặc định, các phân khúc tạo một thực thể đầu ra chứa tất cả các thuộc tính của hồ sơ khách hàng phù hợp với các bộ lọc đã xác định. Nếu một phân khúc dựa trên các thực thể khác với *Khách hàng*, bạn có thể thêm nhiều thuộc tính hơn từ các thực thể này vào thực thể đầu ra. Chọn **Thuộc tính dự án** để chọn các thuộc tính sẽ được thêm vào thực thể đầu ra.  

   
   Ví dụ: Một phân khúc dựa trên một thực thể chứa dữ liệu về hoạt động khách hàng, liên quan đến thực thể *Khách hàng*. Phân đoạn này tìm kiếm tất cả khách hàng đã gọi điện đến bộ phận trợ giúp trong 60 ngày qua. Bạn có thể chọn thêm thời lượng cuộc gọi và số lượng cuộc gọi vào tất cả các bản ghi khách hàng phù hợp trong thực thể đầu ra. Thông tin này có thể hữu ích để gửi một email với các liên kết hữu ích đến các bài báo trợ giúp trực tuyến và Câu hỏi thường gặp cho những khách hàng đã gọi điện thường xuyên.

1. Chọn **Lưu** để lưu phân đoạn của bạn. Phân đoạn của bạn sẽ được lưu và xử lý nếu tất cả các yêu cầu được xác thực. Nếu không, nó sẽ được lưu dưới dạng bản nháp.

1. Chọn **Quay lại phân khúc** để quay lại trang **Phân khúc**.

## <a name="manage-existing-segments"></a>Quản lý các phân đoạn hiện có

Trên trang **Phân đoạn**, bạn có thể xem tất cả các phân đoạn đã lưu và quản lý chúng.

Mỗi phân khúc được đại diện bởi một hàng bao gồm thông tin bổ sung về phân khúc.

Bạn có thể sắp xếp các phân đoạn trong một cột bằng cách chọn tiêu đề cột.

Sử dụng hộp **Tìm kiếm** ở góc trên cùng bên phải để lọc các phân khúc.

> [!div class="mx-imgBorder"]
> ![Tùy chọn để quản lý phân đoạn hiện có](media/segments-selected-segment.png "Tùy chọn để quản lý phân đoạn hiện có")

Hành động sau đây khả dụng khi bạn chọn một phân khúc:

- **Xem** chi tiết phân đoạn, bao gồm xu hướng số lượng thành viên của một bản xem trước thành viên phân đoạn.
- **Chỉnh sửa** phân đoạn để thay đổi các thuộc tính của phân đoạn đó.
- **Tạo bản sao** của một phân khúc. Bạn có thể chọn chỉnh sửa các thuộc tính của nó ngay lập tức hoặc chỉ cần lưu bản sao.
- **Làm mới** phân đoạn để bao gồm dữ liệu mới nhất.
- **Bật** hoặc **tắt** phân đoạn. Các phân khúc có thể có hai trạng thái: hiện hoạt hoặc không hoạt động. Các trạng thái này rất hữu ích khi bạn chỉnh sửa phân khúc. Đối với các phân khúc không hoạt động, định nghĩa phân khúc tồn tại nhưng phân khúc chưa chứa bất kỳ khách hàng nào. Khi bạn kích hoạt một phân khúc, phân khúc sẽ thay đổi trạng thái từ "không hoạt động" thành "hiện hoạt" và bắt đầu tìm kiếm khách hàng phù hợp với định nghĩa phân khúc. Nếu hoạt động [làm mới theo lịch trình](system.md#schedule-tab) được đặt cấu hình, thì các phân khúc không hoạt động sẽ có **Trạng thái** là **Đã bỏ qua**, biểu thị việc làm mới chưa được thực hiện. Khi phân khúc không hoạt động được kích hoạt, mục đó sẽ được làm mới và được đưa vào các lần làm mới theo lịch trình.
  Ngoài ra, bạn cũng có thể dùng chức năng **Lên lịch sau** trong menu thả xuống **Kích hoạt/Hủy kích hoạt** để xác định ngày giờ kích hoạt và hủy kích hoạt trong tương lai của một phân khúc cụ thể.
- **Đổi tên** phân đoạn.
- **Tải xuống** danh sách thành viên dưới dạng tệp .CSV.
- Tùy chọn **Thêm vào** sẽ gửi danh sách ID khách hàng trong phân khúc để xử lý trong một ứng dụng khác.
- **Xóa** phân đoạn.

## <a name="refresh-segments"></a>Làm mới phân đoạn

Bạn có thể làm mới tất cả phân phúc cùng lúc bằng cách chọn **Làm mới tất cả** trên trang **Phân khúc** hoặc bạn có thể làm mới một hoặc nhiều phân khúc khi chọn và chọn **Làm mới** từ các tùy chọn. Hoặc, bạn có thể đặt cấu hình làm mới lặp lại trên **Quản trị viên** > **Hệ thống** > **Lịch trình**.

> [!TIP]
> Có [6 loại trạng thái](system.md#status-types) cho các nhiệm vụ/quy trình. Ngoài ra, hầu hết các quy trình [phụ thuộc vào các quá trình hạ nguồn khác](system.md#refresh-policies). Bạn có thể chọn trạng thái của một quy trình để xem chi tiết về tiến trình của toàn bộ công việc. Sau khi chọn **Xem chi tiết** đối với một trong các tác vụ của công việc, bạn sẽ tìm thấy thông tin bổ sung: thời gian xử lý, ngày xử lý gần nhất và tất cả các lỗi và cảnh báo liên quan đến tác vụ.

## <a name="download-and-export-segments"></a>Tải xuống và xuất phân đoạn

Bạn có thể tải xuống các phân đoạn của mình vào tệp CSV hoặc xuất chúng sang Dynamics 365 Sales.

### <a name="download-segments-to-a-csv-file"></a>Tải xuống các phân đoạn vào tệp CSV

1. Trong thông tin chi tiết về đối tượng, hãy chuyển đến trang **Phân khúc**.

2. Chọn dấu chấm lửng trong ngăn xếp của một phân đoạn cụ thể.

3. Chọn **Tải xuống dưới dạng CSV** từ danh sách thả xuống hành động.

### <a name="export-segments-to-dynamics-365-sales"></a>Xuất phân đoạn sang Dynamics 365 Sales

Trước khi xuất phân đoạn sang Dynamics 365 Sales, quản trị viên cần phải [tạo đích xuất](export-destinations.md) cho Dynamics 365 Sales.

1. Trong thông tin chi tiết về đối tượng, hãy chuyển đến trang **Phân khúc**.

2. Chọn dấu chấm lửng trong ngăn xếp của một phân đoạn cụ thể.

3. Chọn **Thêm vào** từ danh sách hành động thả xuống và chọn đích xuất bạn muốn gửi dữ liệu vào.

## <a name="draft-mode-for-segments"></a>Chế độ bản nháp cho phân đoạn

Nếu không đáp ứng tất cả các yêu cầu để xử lý phân đoạn, bạn có thể lưu phân đoạn dưới dạng bản nháp và truy cập từ trang **Phân đoạn**.

Phân đoạn sẽ được lưu dưới dạng phân đoạn không hoạt động và không bật được cho tới khi có hiệu lực.

## <a name="add-more-conditions-to-a-group"></a>Thêm nhiều điều kiện cho một nhóm

Để thêm nhiều điều kiện vào một nhóm, bạn có thể sử dụng hai toán tử logic:

- Toán tử **AND**: Cả hai điều kiện phải được thỏa mãn như một phần của quá trình tạo phân đoạn. Tùy chọn này hữu ích nhất khi bạn xác định các điều kiện trên các thực thể khác nhau.

- Toán tử **OR**: Một trong các điều kiện cần phải được thỏa mãn như một phần của quá trình tạo phân đoạn. Tùy chọn này hữu ích nhất khi bạn xác định nhiều điều kiện cho cùng một thực thể.

   > [!div class="mx-imgBorder"]
   > ![Toán tử OR trong đó một trong hai điều kiện cần phải được thỏa mãn](media/segmentation-either-condition.png "Toán tử OR trong đó một trong hai điều kiện cần phải được thỏa mãn")

Hiện tại, có thể lồng một toán tử **OR** trong toán tử **AND** nhưng không phải là ngược lại.

## <a name="combine-multiple-groups"></a>Kết hợp nhiều nhóm

Mỗi nhóm tạo một nhóm khách hàng cụ thể. Bạn có thể kết hợp các nhóm này để bao gồm các khách hàng cần thiết cho trường hợp công việc của bạn.

1. Trong thông tin chi tiết về đối tượng, hãy chuyển đến trang **Phân khúc** và chọn một phân khúc.

2. Chọn **Thêm nhóm**.

   > [!div class="mx-imgBorder"]
   > ![Thêm nhóm khách hàng](media/customer-group-add-group.png "Thêm nhóm khách hàng")

3. Chọn một trong các toán tử tập hợp sau: **Liên hiệp**, **Giao nhau** hoặc **Ngoại trừ**.

   > [!div class="mx-imgBorder"]
   > ![Thêm tập hợp nhóm khách hàng](media/customer-group-union.png "Thêm tập hợp nhóm khách hàng")

   Chọn một toán tử bộ để xác định nhóm mới. Lưu các nhóm khác nhau để quyết định dữ liệu gì được giữ lại:

   - **Hợp nhất** sẽ hợp nhất hai nhóm với nhau.

   - **Giao nhau** sẽ chồng chéo hai nhóm với nhau. Chỉ dữ liệu *là phổ biến* cho cả hai nhóm được giữ lại trong nhóm hợp nhất.

   - **Trừ** kết hợp hai nhóm với nhau. Chỉ dữ liệu trong nhóm A *là không phổ biến* cho dữ liệu trong nhóm B được giữ lại.

## <a name="view-processing-history-and-segment-members"></a>Xem lịch sử xử lý và các thành phần trong phân đoạn

Bạn có thể xem dữ liệu tổng hợp về một phân đoạn bằng cách xem lại chi tiết của phân đoạn đó.

Trên trang **Phân đoạn**, chọn phân đoạn bạn muốn xem lại.

Phần trên của trang bao gồm một biểu đồ xu hướng nhằm trực quan hóa những thay đổi về số lượng thành phần. Di chuột qua các điểm dữ liệu để xem số lượng thành phần trong một ngày cụ thể.

Bạn có thể cập nhật khung thời gian của trực quan hóa.

> [!div class="mx-imgBorder"]
> ![Khoảng thời gian phân đoạn](media/segment-time-range.png "Khoảng thời gian phân đoạn")

Phần dưới chứa danh sách các thành phần phân đoạn.

> [!NOTE]
> Các trường xuất hiện trong danh sách này dựa trên các thuộc tính của các thực thể trong phân đoạn của bạn.
>
>Danh sách này là bản xem trước của các thành phần phân đoạn phù hợp và hiển thị 100 bản ghi đầu tiên của phân đoạn, từ đó bạn có thể đánh giá nhanh và xem lại định nghĩa nếu cần. Để xem tất cả các hồ sơ phù hợp, bạn cần [xuất phân đoạn](export-destinations.md).

## <a name="quick-segments"></a>Phân đoạn nhanh

Ngoài trình tạo phân khúc, có một đường dẫn khác để tạo phân khúc. Phân khúc nhanh cho phép bạn xây dựng các phân khúc đơn giản (với một toán tử) nhanh chóng và có thông tin chuyên sâu tức thì.

1. Trên trang **Phân đoạn**, hãy chọn **Mới** > **Tạo nhanh từ**.

   - Chọn **Hồ sơ** để xây dựng phân đoạn dựa trên thực thể Khách hàng hợp nhất.
   - Chọn **Số liệu đo lường** để xây dựng phân đoạn xung quanh từng loại số liệu đo lường của Thuộc tính khách hàng mà bạn đã tạo trên trang **Giá trị đo lường**.
   - Chọn tùy chọn **Thông tin** để xây dựng một phân đoạn xung quanh một trong các thực thể đầu ra mà bạn tạo bằng một trong hai chức năng **Dự đoán** hoặc **Mô hình tùy chỉnh**.

2. Trong hộp thoại **Phân đoạn nhanh mới**, hãy chọn một thuộc tính từ mục thả xuống **Trường**.

3. Hệ thống sẽ cung cấp thêm một số thông tin chi tiết để giúp bạn tạo các phân đoạn khách hàng tốt hơn.
   - Đối với các trường có phân loại, chúng tôi sẽ hiển thị 10 lượt khách hàng tốt nhất. Chọn **Giá trị** rồi chọn **Xem lại**.

   - Đối với một thuộc tính số, hệ thống sẽ hiển thị giá trị thuộc tính nào nằm trong phần trăm của mỗi khách hàng. Chọn một **Toán tử** và một **Giá trị**, sau đó chọn **Xem lại**.

4. Hệ thống sẽ cung cấp cho bạn một **Kích cỡ phân đoạn ước tính**. Bạn có thể chọn tạo phân đoạn bạn đã xác định hoặc truy cập lại vào phân đoạn đó để có kích cỡ phân đoạn khác.

    > [!div class="mx-imgBorder"]
    > ![Tên và ước tính cho một phân đoạn nhanh](media/quick-segment-name.png "Tên và ước tính cho một phân đoạn nhanh")

5. Đặt **Tên** cho phân đoạn của bạn. Bạn cũng có thể cung cấp **Tên hiển thị**.

6. Chọn **Lưu** để tạo phân đoạn.

7. Sau khi phân đoạn đã xử lý xong, bạn có thể xem nó như bất kỳ phân đoạn nào khác mà bạn đã tạo.

Đối với các tình huống sau, bạn nên sử dụng trình tạo phân đoạn thay vì chức năng phân đoạn được đề xuất:

- Tạo các phân đoạn với các bộ lọc trên các trường phân loại trong đó toán tử không phải là toán tử **Is**
- Tạo các phân đoạn với các bộ lọc trên các trường số trong đó toán tử không phải là **Between**, **Greater than** và **Less than**
- Tạo phân đoạn với các bộ lọc trên các trường loại ngày

## <a name="next-steps"></a>Bước tiếp theo

[Xuất phân đoạn](export-destinations.md) và khám phá [Thẻ khách hàng](customer-card-add-in.md) và [Bộ kết nối](export-power-bi.md) để nắm được thông tin chi tiết ở cấp độ khách hàng.


[!INCLUDE[footer-include](../includes/footer-banner.md)]