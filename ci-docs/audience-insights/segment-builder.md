---
title: Tạo và quản lý phân đoạn
description: Tạo phân đoạn khách hàng để nhóm họ lại dựa trên các đặc điểm khác nhau.
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 550e509a24701fe5fcdeb9d54311872dc954156c
ms.sourcegitcommit: 72603fb39c4d5dbca71128815a2e1692542ea4dc
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 05/19/2021
ms.locfileid: "6064963"
---
# <a name="create-and-manage-segments"></a>Tạo và quản lý phân đoạn

Xác định các bộ lọc phức hợp xung quanh thực thể khách hàng hợp nhất và các thực thể có liên quan. Mỗi phân khúc, sau khi xử lý, sẽ tạo một bộ hồ sơ khách hàng mà bạn có thể xuất và hành động. Các phân khúc được quản lý trên trang **Phân khúc**. 

Ví dụ sau minh họa khả năng tạo phân khúc. Chúng tôi đã xác định một phân đoạn cho khách hàng đặt hàng hóa trị giá ít nhất $500 trong 90 ngày qua *và* đã tham gia vào cuộc gọi dịch vụ khách hàng đã báo cáo.

:::image type="content" source="media/segmentation-group1-2.png" alt-text="Ảnh chụp màn hình của giao diện người dùng từ trình tạo phân khúc với hai nhóm chỉ định phân khúc khách hàng.":::

## <a name="create-a-new-segment"></a>Tạo phân đoạn mới

Có nhiều cách để tạo một phân khúc mới. Phần này mô tả cách tạo *phân khúc trống* từ đầu. Bạn cũng có thể tạo một *phân khúc nhanh* dựa trên các thực thể hiện có hoặc sử dụng các mô hình máy học để có được *phân khúc đề xuất*. Thông tin thêm: [Tổng quan về các phân khúc](segments.md).

Trong khi tạo phân khúc, bạn có thể lưu bản nháp. Bản nháp sẽ được lưu dưới dạng một phân khúc không hoạt động và không thể kích hoạt với cấu hình hợp lệ.

1. Truy cập trang **Phân đoạn**.

1. Chọn **Mới** > **Phân đoạn trống**.

1. Trong ngăn **Phân khúc mới**, chọn một loại phân khúc:

   - **Phân khúc động** [làm mới](segments.md#refresh-segments) theo lịch trình định kỳ.
   - **Phân khúc tĩnh** chạy một lần khi bạn khởi tạo.

1. Đặt **Tên thực thể đầu ra** cho phân khúc. Bạn cũng có thể cung cấp tên hiển thị và mô tả nhằm xác định phân đoạn.

1. Chọn **Tiếp theo** để đi đến trang **Trình tạo phân đoạn** và xác định nhóm. Một nhóm là một tập hợp các khách hàng.

1. Chọn thực thể bao gồm thuộc tính mà bạn muốn tạo phân đoạn.

1. Chọn thuộc tính để tạo phân đoạn. Thuộc tính này có thể có 1 trong số 4 loại giá trị: số, chuỗi, ngày hoặc Boolean.

1. Chọn một toán tử và một giá trị cho thuộc tính đã chọn.

   > [!div class="mx-imgBorder"]
   > ![Bộ lọc nhóm tùy chỉnh](media/customer-group-numbers.png "Bộ lọc nhóm khách hàng")

   |Số điện thoại |Định nghĩa  |
   |---------|---------|
   |1     |Thực thể          |
   |2     |Thuộc tính          |
   |3    |Toán tử         |
   |Tệp 4    |Giá trị         |

   1. Để thêm nhiều điều kiện vào một nhóm, bạn có thể sử dụng hai toán tử logic:

      - Toán tử **AND**: Cả hai điều kiện phải được thỏa mãn như một phần của quá trình tạo phân đoạn. Tùy chọn này hữu ích nhất khi bạn xác định các điều kiện trên các thực thể khác nhau.

      - Toán tử **OR**: Một trong các điều kiện cần phải được thỏa mãn như một phần của quá trình tạo phân đoạn. Tùy chọn này hữu ích nhất khi bạn xác định nhiều điều kiện cho cùng một thực thể.

      > [!div class="mx-imgBorder"]
      > ![Toán tử OR trong đó một trong hai điều kiện cần phải được thỏa mãn](media/segmentation-either-condition.png "Toán tử OR trong đó một trong hai điều kiện cần phải được thỏa mãn")

      Hiện tại, có thể lồng một toán tử **OR** trong toán tử **AND** nhưng không phải là ngược lại.

   1. Mỗi nhóm phù hợp với tập khách hàng. Bạn có thể kết hợp các nhóm để có được những khách hàng cần thiết cho hoạt động kinh doanh của bạn.    
   Chọn **Thêm nhóm**.

      > [!div class="mx-imgBorder"]
      > ![Thêm nhóm khách hàng](media/customer-group-add-group.png "Thêm nhóm khách hàng")

   1. Chọn một trong các toán tử đã đặt: **Hợp nhất**, **Giao nhau** hoặc **Ngoại trừ**.

   > [!div class="mx-imgBorder"]
   > ![Thêm tập hợp nhóm khách hàng](media/customer-group-union.png "Thêm tập hợp nhóm khách hàng")

   - **Hợp nhất** sẽ hợp nhất hai nhóm với nhau.

   - **Giao nhau** sẽ chồng chéo hai nhóm với nhau. Chỉ dữ liệu *là phổ biến* cho cả hai nhóm được giữ lại trong nhóm hợp nhất.

   - **Trừ** kết hợp hai nhóm với nhau. Chỉ dữ liệu trong nhóm A *là không phổ biến* cho dữ liệu trong nhóm B được giữ lại.

1. Nếu thực thể được kết nối với thực thể khách hàng hợp nhất qua [các mối quan hệ](relationships.md), thì bạn cần xác định đường dẫn mối quan hệ để tạo một phân đoạn hợp lệ. Thêm các thực thể từ đường dẫn mối quan hệ cho đến khi bạn có thể chọn thực thể **Khách hàng : CustomerInsights** từ danh sách thả xuống. Sau đó chọn **Tất cả hồ sơ** cho mỗi bước.

   > [!div class="mx-imgBorder"]
   > ![Đường dẫn mối quan hệ trong khi tạo phận đoạn](media/segments-multiple-relationships.png "Đường dẫn mối quan hệ trong khi tạo phận đoạn")

1. Theo mặc định, các phân khúc tạo một thực thể đầu ra chứa tất cả các thuộc tính của hồ sơ khách hàng phù hợp với các bộ lọc đã xác định. Nếu một phân khúc dựa trên các thực thể khác với *Khách hàng*, bạn có thể thêm nhiều thuộc tính hơn từ các thực thể này vào thực thể đầu ra. Chọn **Thuộc tính dự án** để chọn các thuộc tính sẽ được thêm vào thực thể đầu ra.  
  
   Ví dụ: Một phân khúc dựa trên một thực thể chứa dữ liệu về hoạt động khách hàng, liên quan đến thực thể *Khách hàng*. Phân đoạn này tìm kiếm tất cả khách hàng đã gọi điện đến bộ phận trợ giúp trong 60 ngày qua. Bạn có thể chọn thêm thời lượng cuộc gọi và số lượng cuộc gọi vào tất cả các bản ghi khách hàng phù hợp trong thực thể đầu ra. Thông tin này có thể hữu ích để gửi một email với các liên kết hữu ích đến các bài báo trợ giúp trực tuyến và Câu hỏi thường gặp cho những khách hàng đã gọi điện thường xuyên.

   > [!NOTE]
   > - Các thuộc tính dự kiến chỉ hoạt động với các thực thể có mối quan hệ một-nhiều với thực thể khách hàng. Ví dụ: một khách hàng có thể có nhiều gói đăng ký.
   > - Bạn chỉ có thể chiếu các thuộc tính từ một thực thể được sử dụng trong tất cả các nhóm truy vấn phân khúc mà bạn đang tạo.
   > - Các thuộc tính dự kiến được coi như yếu tố khi sử dụng các toán tử tập hợp.

1. Chọn **Lưu** để lưu phân đoạn của bạn. Phân đoạn của bạn sẽ được lưu và xử lý nếu tất cả các yêu cầu được xác thực. Nếu không, nó sẽ được lưu dưới dạng bản nháp.

1. Chọn **Quay lại phân khúc** để quay lại trang **Phân khúc**.



## <a name="quick-segments"></a>Phân đoạn nhanh

Phân khúc nhanh cho phép bạn tạo nhanh các phân khúc đơn giản với một toán tử để có thông tin chi tiết nhanh chóng hơn.

1. Trên trang **Phân khúc**, chọn **Mới** > **Tạo từ**.

   - Chọn **Hồ sơ** để xây dựng phân khúc dựa trên thực thể *khách hàng hợp nhất*.
   - Chọn các tùy chọn **Biện pháp** để xây dựng một phân khúc xung quanh các biện pháp bạn đã tạo trước đó.
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

## <a name="next-steps"></a>Các bước tiếp theo

[Xuất phân đoạn](export-destinations.md) và khám phá [Thẻ khách hàng](customer-card-add-in.md) và [Bộ kết nối](export-power-bi.md) để nắm được thông tin chi tiết ở cấp độ khách hàng.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
