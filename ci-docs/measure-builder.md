---
title: Tạo các thước đo với trình tạo thước đo
description: Xây dựng các thước đo từ đầu để phân tích các chỉ số chính về doanh nghiệp của bạn.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measure-builder
- customerInsights
ms.openlocfilehash: fac00b8a1b4ca6e09dd29abe46dfe240adcc029e
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170891"
---
# <a name="create-measures-with-measure-builder"></a>Tạo các thước đo với trình tạo thước đo

Trình tạo số đo cho phép bạn xác định các phép tính bằng cách sử dụng toán tử toán học, hàm tổng hợp và bộ lọc. Xác định các thước đo bằng cách sử dụng các thuộc tính từ các thực thể có liên quan đến hợp nhất *khách hàng* thực thể.

Tạo các thước đo trong môi trường B-to-C và B-to-B hoạt động theo cùng một cách. Tuy nhiên, nếu môi trường B-to-B của bạn [sử dụng tài khoản có phân cấp](relationships.md#set-up-account-hierarchies), chọn có tổng hợp số đo trên các tài khoản phụ có liên quan hay không.

# <a name="individual-consumers-b-to-c"></a>[Người tiêu dùng cá nhân (B2C)](#tab/b2c)

Tạo các thước đo ở cấp độ khách hàng cá nhân (thuộc tính khách hàng, thước đo khách hàng) hoặc cấp độ của doanh nghiệp / tổ chức (thước đo kinh doanh). Thuộc tính khách hàng và thước đo khách hàng cho phép bạn theo dõi hiệu suất trên mỗi khách hàng. Ví dụ: tổng chi tiêu của mỗi khách hàng. Các thước đo kinh doanh theo dõi hiệu quả hoạt động của mỗi doanh nghiệp. Ví dụ, tổng doanh thu của công ty.

- Thuộc tính khách hàng: Tạo đầu ra dưới dạng thuộc tính mới, được lưu dưới dạng cột mới trong thực thể do hệ thống tạo có tên *Khách hàng_Measure*. Khi làm mới một thuộc tính khách hàng, tất cả các thuộc tính khách hàng khác trong *Customer_Measure* làm mới thực thể đồng thời. Ngoài ra, các thuộc tính của khách hàng được thể hiện trong thẻ hồ sơ khách hàng. Sau khi chạy hoặc lưu, bạn không thể thay đổi thuộc tính khách hàng thành thước đo khách hàng.

- Đo lường khách hàng: Tạo đầu ra dưới dạng thực thể của chính nó và bạn không thể thay đổi nó thành thuộc tính khách hàng sau khi chạy hoặc lưu. Các thước đo khách hàng không hiển thị trong thẻ hồ sơ khách hàng.

- Biện pháp kinh doanh: Tạo đầu ra dưới dạng thực thể của chính nó và hiển thị trên trang chủ của môi trường Thông tin chi tiết về khách hàng của bạn.

1. Đi đến **Đo**.

1. Chọn **Mới** > **Xây dựng phân khúc của riêng bạn**.

   :::image type="content" source="media/measure-b2c.png" alt-text="Màn hình cấu hình trống cho phép đo B-to-C." lightbox="media/measure-b2c.png":::

1. Lựa chọn **Chỉnh sửa chi tiết** bên cạnh Biện pháp không có tiêu đề. Cung cấp tên cho biện pháp. Tùy chọn, thêm [thẻ](work-with-tags-columns.md#manage-tags) để đo lường.

   :::image type="content" source="media/measures_edit_details.png" alt-text="Hộp thoại chỉnh sửa chi tiết.":::

1. Chọn **Xong**.

1. Để theo dõi hiệu suất cấp doanh nghiệp, hãy chuyển đổi **Loại đo** đến **Cấp độ kinh doanh**. **Cấp độ khách hàng** được chọn theo mặc định. **Cấp độ khách hàng** tự động thêm *ID khách hàng* thuộc tính cho Thứ nguyên trong khi **Cấp độ kinh doanh** tự động loại bỏ nó.

1. Trong vùng cấu hình, hãy chọn chức năng tổng hợp từ **Chọn chức năng** trình đơn thả xuống. Các hàm tổng hợp bao gồm:
   - **Sum**
   - **Trung bình**
   - **Đếm**
   - **Số đếm Duy nhất**
   - **Tối đa**
   - **Min**
   - **Đầu tiên**: lấy giá trị đầu tiên của bản ghi dữ liệu
   - **Cuối cùng**: lấy giá trị cuối cùng đã được thêm vào bản ghi dữ liệu
   - **ArgMax** : tìm bản ghi dữ liệu cho giá trị lớn nhất từ một hàm mục tiêu
   - **ArgMin** : tìm bản ghi dữ liệu cho giá trị nhỏ nhất từ một hàm mục tiêu

1. Lựa chọn **Thêm thuộc tính** để chọn dữ liệu để tạo biện pháp này.

   1. Chọn thẻ **Thuộc tính**.
   1. Thực thể dữ liệu: Chọn thực thể bao gồm thuộc tính bạn muốn đo.
   1. Thuộc tính dữ liệu: Chọn thuộc tính bạn muốn sử dụng trong hàm tổng hợp để tính toán giá trị đo. Mỗi lần, bạn chỉ có thể chọn một thuộc tính.
   1. Theo tùy chọn, hãy chọn một thuộc tính dữ liệu từ một số đo hiện có bằng cách chọn **Đo** hoặc tìm kiếm một thực thể hoặc tên đo lường.
   1. Chọn **Thêm**.

1. Để xây dựng các thước đo phức tạp hơn, hãy thêm nhiều thuộc tính hơn hoặc sử dụng các toán tử toán học trên hàm đo lường của bạn.

1. Để thêm bộ lọc, hãy chọn **Bộ lọc** trong vùng cấu hình. Việc áp dụng bộ lọc sẽ chỉ sử dụng các bản ghi phù hợp với bộ lọc để tính toán số đo.
  
   1. Trong phần **Thêm thuộc tính** của ngăn **Bộ lọc**, chọn thuộc tính bạn muốn sử dụng để tạo bộ lọc.
   1. Đặt toán tử bộ lọc để xác định bộ lọc cho mọi thuộc tính đã chọn.
   1. Chọn **Áp dụng**.

1. Lựa chọn **Kích thước** để chọn thêm các trường để thêm dưới dạng cột vào thực thể đầu ra đo lường.

   1. Chọn **Chỉnh sửa thứ nguyên** để thêm các thuộc tính dữ liệu mà bạn muốn nhóm các giá trị đo lường. Ví dụ: thành phố hoặc giới tính.
      > [!TIP]
      > Nếu bạn đã chọn **Cấp độ khách hàng** như là **Loại đo** các *ID khách hàng* thuộc tính đã được thêm vào. Nếu bạn xóa thuộc tính, **Loại đo** chuyển sang **Cấp độ kinh doanh**.
   1. Chọn **Xong**.

1. Nếu có các giá trị trong dữ liệu của bạn phải được thay thế bằng một số nguyên, hãy chọn **Quy tắc**. Định cấu hình quy tắc và đảm bảo rằng bạn chỉ chọn các số nguyên làm giá trị thay thế. Ví dụ: thay thế *null* bằng *0*.

1. Nếu có nhiều đường dẫn giữa thực thể dữ liệu bạn đã ánh xạ và *khách hàng* thực thể, hãy chọn một trong những [các đường dẫn mối quan hệ thực thể](relationships.md). Kết quả giá trị đo có thể khác nhau tùy thuộc vào đường dẫn đã chọn.

   1. Chọn **Đường dẫn mối quan hệ** và chọn đường dẫn thực thể sẽ được dùng để xác định giá trị đo. Nếu chỉ có một đường dẫn đến thực thể *Khách hàng*, điều khiển này sẽ không hiển thị.
   1. Chọn **Xong**.

1. Để thêm các phép tính khác cho giá trị đo đó, hãy chọn **Tính toán mới**. Chỉ sử dụng các thực thể trên cùng một đường dẫn thực thể cho các phép tính mới. Các phép tính khác sẽ hiển thị dưới dạng cột mới trong thực thể đầu ra giá trị đo. Tùy ý, chọn **Chỉnh sửa tên** để tạo tên cho phép tính.

1. Chọn dấu chấm lửng dọc (&vellip;) trên phép tính để **Nhân bản** hoặc **Loại bỏ** một phép tính từ một số đo.

1. Trong ngăn **Xem trước**, bạn sẽ thấy giản đồ dữ liệu của thực thể đầu ra giá trị đo, bao gồm các bộ lọc và thứ nguyên. Bản xem trước phản ứng tự động với các thay đổi trong cấu hình.

1. Chọn **Chạy** để tính toán kết quả cho giá trị đo đã định cấu hình. Chọn **Lưu và đóng** nếu bạn muốn giữ cấu hình hiện tại và chạy giá trị đo sau. Các **Đo** hiển thị trang.

# <a name="business-accounts-b-to-b"></a>[Tài khoản doanh nghiệp (B2B)](#tab/b2b)

Tạo các thước đo ở cấp độ tài khoản cá nhân (thước đo khách hàng) hoặc ở cấp độ tất cả các tài khoản (thước đo kinh doanh).

- Thước đo khách hàng: Tạo ra sản lượng như thực thể của chính nó. Các thước đo khách hàng không hiển thị trong thẻ hồ sơ khách hàng.

- Biện pháp kinh doanh: Tạo đầu ra dưới dạng thực thể của chính nó và hiển thị trên trang chủ của môi trường Thông tin chi tiết về khách hàng của bạn.

1. Đi đến **Đo**.

1. Chọn **Mới**.

   :::image type="content" source="media/measure-b2b.png" alt-text="Màn hình cấu hình trống cho phép đo từ B đến B.":::

1. Lựa chọn **Chỉnh sửa chi tiết** bên cạnh Biện pháp không có tiêu đề. Cung cấp tên cho biện pháp. Tùy chọn, thêm [thẻ](work-with-tags-columns.md#manage-tags) để đo lường. 
   :::image type="content" source="media/measures_edit_details.png" alt-text="Hộp thoại chỉnh sửa chi tiết.":::

1. Chọn **Xong**.

1. Trong vùng cấu hình, hãy chọn chức năng tổng hợp từ **Chọn chức năng** trình đơn thả xuống. Các hàm tổng hợp bao gồm:
   - **Sum**
   - **Trung bình**
   - **Đếm**
   - **Số đếm Duy nhất**
   - **Tối đa**
   - **Min**
   - **Đầu tiên**: lấy giá trị đầu tiên của bản ghi dữ liệu
   - **Cuối cùng**: lấy giá trị cuối cùng đã được thêm vào bản ghi dữ liệu

1. Lựa chọn **Thêm thuộc tính** để chọn dữ liệu để tạo biện pháp này.

   1. Chọn thẻ **Thuộc tính**.
   1. Thực thể dữ liệu: Chọn thực thể bao gồm thuộc tính bạn muốn đo.
   1. Thuộc tính dữ liệu: Chọn thuộc tính bạn muốn sử dụng trong hàm tổng hợp để tính toán giá trị đo. Mỗi lần, bạn chỉ có thể chọn một thuộc tính.
   1. Theo tùy chọn, hãy chọn một thuộc tính dữ liệu từ một số đo hiện có bằng cách chọn **Đo** hoặc tìm kiếm một thực thể hoặc tên đo lường.
   1. Chọn **Thêm** để thêm thuộc tính đã chọn vào giá trị đo.

1. Để xây dựng các thước đo phức tạp hơn, hãy thêm nhiều thuộc tính hơn hoặc sử dụng các toán tử toán học trên hàm đo lường của bạn.

1. Để thêm bộ lọc, hãy chọn **Bộ lọc** trong vùng cấu hình. Việc áp dụng bộ lọc sẽ chỉ sử dụng các bản ghi phù hợp với bộ lọc để tính toán số đo.
  
   1. Trong phần **Thêm thuộc tính** của ngăn **Bộ lọc**, chọn thuộc tính bạn muốn sử dụng để tạo bộ lọc.
   1. Đặt toán tử bộ lọc để xác định bộ lọc cho mọi thuộc tính đã chọn.
   1. Chọn **Áp dụng** để thêm các bộ lọc vào giá trị đo.

1. Lựa chọn **Kích thước** để chọn thêm các trường để thêm dưới dạng cột vào thực thể đầu ra đo lường.

   1. Chọn **Chỉnh sửa thứ nguyên** để thêm các thuộc tính dữ liệu mà bạn muốn nhóm các giá trị đo lường. Ví dụ: thành phố hoặc giới tính.
      > [!TIP]
      > Các *ID khách hàng* thuộc tính đã được thêm vào cho biết đây là loại thước đo cấp độ khách hàng. Nếu bạn xóa thuộc tính, loại thước đo sẽ thay đổi thành cấp doanh nghiệp.
   1. Chọn **Xong** để thêm các thứ nguyên vào giá trị đo.

1. Nếu có các giá trị trong dữ liệu của bạn phải được thay thế bằng một số nguyên, hãy chọn **Quy tắc**. Định cấu hình quy tắc và đảm bảo rằng bạn chỉ chọn các số nguyên làm giá trị thay thế. Ví dụ: thay thế *null* bằng *0*.

1. Nếu bạn [sử dụng tài khoản có phân cấp](relationships.md#set-up-account-hierarchies), kiểm tra lại **Tổng hợp các tài khoản phụ**.
   - Nếu công tắc được đặt thành **Tắt**, giá trị đo được tính cho mọi tài khoản. Mọi tài khoản đều có kết quả riêng.
   - Nếu công tắc được đặt thành **Bật**, hãy chọn **Chỉnh sửa** để chọn hệ thống cấp bậc tài khoản theo cấp bậc đã nhập. Biện pháp sẽ chỉ mang lại một kết quả vì nó được tổng hợp với các tài khoản phụ.

1. Nếu có nhiều đường dẫn giữa thực thể dữ liệu bạn đã ánh xạ và *khách hàng* thực thể, hãy chọn một trong những [các đường dẫn mối quan hệ thực thể](relationships.md). Kết quả giá trị đo có thể khác nhau tùy thuộc vào đường dẫn đã chọn.

   1. Chọn **Đường dẫn mối quan hệ** và chọn đường dẫn thực thể sẽ được dùng để xác định giá trị đo. Nếu chỉ có một đường dẫn đến thực thể *Khách hàng*, điều khiển này sẽ không hiển thị.
   1. Chọn **Xong** để áp dụng lựa chọn của bạn.

1. Chọn dấu chấm lửng dọc (&vellip;) trên phép tính để **Nhân bản** hoặc **Loại bỏ** một phép tính từ một số đo.

1. Trong ngăn **Xem trước**, bạn sẽ thấy giản đồ dữ liệu của thực thể đầu ra giá trị đo, bao gồm các bộ lọc và thứ nguyên. Bản xem trước phản ứng tự động với các thay đổi trong cấu hình.

1. Chọn **Chạy** để tính toán kết quả cho giá trị đo đã định cấu hình. Chọn **Lưu và đóng** nếu bạn muốn giữ cấu hình hiện tại và chạy giá trị đo sau. Các **Đo** hiển thị trang.

---

## <a name="next-step"></a>Bước tiếp theo

Sử dụng các biện pháp hiện có để tạo [một phân khúc khách hàng](segments.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
