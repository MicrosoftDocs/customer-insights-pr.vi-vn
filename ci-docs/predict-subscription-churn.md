---
title: Dự đoán thời gian ngừng đăng ký (có video)
description: Dự đoán xem khách hàng có nguy cơ không sử dụng sản phẩm hoặc dịch vụ đăng ký của công ty bạn nữa không.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 7464707864c418bfcc625ddfd245622131434b33
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610262"
---
# <a name="predict-subscription-churn"></a>Dự đoán khả năng rời bỏ đăng ký

Dự đoán xem khách hàng có nguy cơ không sử dụng sản phẩm hoặc dịch vụ đăng ký của công ty bạn nữa không. Dữ liệu đăng ký bao gồm các đăng ký đang hoạt động và không hoạt động cho mỗi khách hàng, do đó có nhiều mục nhập cho mỗi ID khách hàng.

Bạn phải có kiến thức kinh doanh để hiểu churn có ý nghĩa như thế nào đối với doanh nghiệp của bạn. Chúng tôi hỗ trợ các định nghĩa gián đoạn dựa trên thời gian, có nghĩa là một khách hàng được coi là đã bỏ qua một khoảng thời gian sau khi đăng ký của họ kết thúc.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOKNQ]

> [!TIP]
> Thử đăng ký churn dự đoán bằng dữ liệu mẫu: [Hướng dẫn mẫu về đăng ký churn dự đoán](sample-guide-predict-subscription-churn.md).

## <a name="prerequisites"></a>Điều kiện tiên quyết

- Tối thiểu [Quyền của cộng tác viên](permissions.md).
- Ít nhất 10 hồ sơ khách hàng, tốt nhất là hơn 1.000 khách hàng duy nhất.
- Số nhận dạng khách hàng, một số nhận dạng duy nhất để khớp các đăng ký với khách hàng của bạn.
- Dữ liệu đăng ký cho ít nhất gấp đôi khoảng thời gian đã chọn. Tốt nhất là hai đến ba năm dữ liệu gói đăng ký. Lịch sử đăng ký phải bao gồm:
  - **ID đăng ký:** Định danh duy nhất của một đăng ký.
  - **Ngày kết thúc đăng ký:** Ngày hết hạn đăng ký cho khách hàng.
  - **Ngày bắt đầu đăng ký:** Ngày bắt đầu đăng ký cho khách hàng.
  - **Ngày Giao dịch:** Ngày thay đổi đăng ký đã xảy ra. Ví dụ: một khách hàng mua hoặc hủy đăng ký.
  - **Đó có phải là một đăng ký định kỳ:** Trường đúng / sai Boolean xác định xem đăng ký sẽ gia hạn với cùng một ID đăng ký mà không có sự can thiệp của khách hàng hay không.
  - **Tần suất lặp lại (tính theo tháng):** Đối với đăng ký định kỳ, tháng đăng ký sẽ gia hạn. Ví dụ: đăng ký hàng năm tự động gia hạn cho khách hàng mỗi năm cho một năm khác có giá trị 12.
  - **Số tiền đăng ký** : Số tiền khách hàng thanh toán cho việc gia hạn đăng ký. Số tiền đó có thể giúp xác định các mẫu cho các cấp độ đăng ký khác nhau.
- Ít nhất hai bản ghi hoạt động của 50% khách hàng mà bạn muốn tính toán thời gian hoạt động. Các hoạt động của khách hàng phải bao gồm:
  - **Khóa chính:** Mã định danh duy nhất cho một hoạt động. Ví dụ: một lượt truy cập trang web hoặc bản ghi sử dụng cho thấy khách hàng đã xem một tập chương trình truyền hình.
  - **Dấu thời gian:** Ngày và giờ của sự kiện được xác định bởi khóa chính.
  - **Biến cố:** Tên của sự kiện bạn muốn sử dụng. Ví dụ: một trường có tên "UserAction" trong dịch vụ truyền phát video có thể có giá trị là "Đã xem".
  - **Chi tiết:** Thông tin chi tiết về sự kiện. Ví dụ: một trường có tên "ShowTitle" trong dịch vụ truyền phát video có thể có giá trị là video mà khách hàng đã xem.
- Dưới 20% giá trị bị thiếu trong trường dữ liệu của thực thể được cung cấp.

## <a name="create-a-subscription-churn-prediction"></a>Tạo dự đoán khả năng rời bỏ đăng ký

Lựa chọn **Lưu bản nháp** bất kỳ lúc nào để lưu dự đoán dưới dạng bản nháp. Bản nháp dự đoán hiển thị trong **Dự đoán của tôi** chuyển hướng.

1. Đi đến **Sự thông minh** > **Phỏng đoán**.

1. Trên **Tạo ra** tab, chọn **Sử dụng mô hình** trên **Mô hình churn khách hàng** ngói.

1. Lựa chọn **Đăng ký** cho kiểu churn và sau đó **Bắt đầu**.

1. **Đặt tên cho mô hình này** và **Tên thực thể đầu ra** để phân biệt chúng với các mô hình hoặc thực thể khác.

1. Chọn **Tiếp theo**.

### <a name="define-customer-churn"></a>Xác định khách hàng rời đi

1. Nhập số **Ngày kể từ khi đăng ký kết thúc** mà doanh nghiệp của bạn xem xét một khách hàng là đang ở trong trạng thái rời đi. Giai đoạn này thường liên quan đến các hoạt động kinh doanh như chào hàng hoặc các nỗ lực tiếp thị khác cố gắng ngăn chặn việc mất khách hàng.

1. Nhập số **Số ngày điều tra tương lai để dự đoán tình trạng hỗn loạn**. Ví dụ: dự đoán nguy cơ khách hàng rời đi trong 90 ngày tới để phù hợp với nỗ lực duy trì hoạt động tiếp thị của bạn. Việc dự đoán rủi ro khách hàng ngừng sử dụng gói đăng ký trong khoảng thời gian dài hơn hoặc ngắn hơn có thể khiến việc xử lý các yếu tố trong hồ sơ rủi ro khách hàng ngừng sử dụng gói đăng ký của bạn gặp nhiều khó khăn hơn, tùy thuộc vào yêu cầu kinh doanh cụ thể của bạn.

1. Chọn **Tiếp theo**.

### <a name="add-required-data"></a>Thêm dữ liệu bắt buộc

1. Lựa chọn **Thêm dữ liệu** vì **Lịch sử đăng ký**.

1. Chọn loại hoạt động ngữ nghĩa **Đăng ký** chứa thông tin lịch sử đăng ký bắt buộc. Nếu hoạt động chưa được thiết lập, hãy chọn **nơi đây** và tạo ra nó.

1. Dưới **Các hoạt động**, nếu các thuộc tính hoạt động được ánh xạ theo ngữ nghĩa khi hoạt động được tạo, hãy chọn các thuộc tính hoặc thực thể cụ thể mà bạn muốn tính toán tập trung vào. Nếu ánh xạ ngữ nghĩa không xảy ra, hãy chọn **Chỉnh sửa** và lập bản đồ dữ liệu của bạn.
  
   :::image type="content" source="media/subscription-churn-required.png" alt-text="Thêm dữ liệu bắt buộc cho mô hình gián đoạn Đăng ký":::

1. Lựa chọn **Tiếp theo** và xem xét các thuộc tính cần thiết cho mô hình này.

1. Chọn **Lưu.**

1. Lựa chọn **Thêm dữ liệu** vì **Hoạt động của khách hàng**.

1. Chọn loại hoạt động ngữ nghĩa cung cấp thông tin hoạt động của khách hàng. Nếu hoạt động chưa được thiết lập, hãy chọn **nơi đây** và tạo ra nó.

1. Dưới **Các hoạt động**, nếu các thuộc tính hoạt động được ánh xạ theo ngữ nghĩa khi hoạt động được tạo, hãy chọn các thuộc tính hoặc thực thể cụ thể mà bạn muốn tính toán tập trung vào. Nếu ánh xạ ngữ nghĩa không xảy ra, hãy chọn **Chỉnh sửa** và lập bản đồ dữ liệu của bạn.

1. Lựa chọn **Tiếp theo** và xem xét các thuộc tính cần thiết cho mô hình này.

1. Chọn **Lưu.**

1. Thêm các hoạt động khác hoặc chọn **Tiếp theo**.

### <a name="set-update-schedule"></a>Đặt lịch trình cập nhật

1. Chọn tần suất để đào tạo lại mô hình của bạn. Cài đặt này rất quan trọng để cập nhật độ chính xác của các dự đoán khi dữ liệu mới được nhập vào Thông tin chi tiết về khách hàng. Hầu hết các doanh nghiệp đều có thể đào tạo lại một lần mỗi tháng và có dự đoán chính xác cao.

1. Chọn **Tiếp theo**.

### <a name="review-and-run-the-model-configuration"></a>Xem lại và chạy cấu hình mô hình

Các **Xem lại và chạy** bước hiển thị tóm tắt cấu hình và cung cấp cơ hội thực hiện các thay đổi trước khi bạn tạo dự đoán.

1. Lựa chọn **Chỉnh sửa** về bất kỳ bước nào để xem xét và thực hiện bất kỳ thay đổi nào.

1. Nếu bạn hài lòng với lựa chọn của mình, hãy chọn **Lưu và chạy** để bắt đầu chạy mô hình. Chọn **Xong**. Các **Dự đoán của tôi** tab hiển thị trong khi dự đoán đang được tạo. Quá trình này có thể mất vài giờ mới hoàn thành, tùy thuộc vào lượng dữ liệu dùng trong dự đoán.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Xem kết quả dự đoán

1. Đi đến **Sự thông minh** > **Phỏng đoán**.

1. Bên trong **Dự đoán của tôi**, chọn dự đoán bạn muốn xem.

Có 3 phần dữ liệu chính trong trang kết quả:

- **Hiệu suất mô hình đào tạo** : Điểm A, B hoặc C cho biết hiệu suất của dự đoán và có thể giúp bạn đưa ra quyết định sử dụng kết quả được lưu trữ trong thực thể đầu ra.
  
  :::image type="content" source="media/subscription-churn-modelperformance.PNG" alt-text="Hình ảnh của hộp thông tin điểm mô hình với điểm A.":::

  Điểm được xác định dựa trên các quy tắc sau:
  - **Một** khi mô hình dự đoán chính xác ít nhất 50% trong tổng số dự đoán và khi tỷ lệ dự đoán chính xác cho những khách hàng đã dự đoán lớn hơn tỷ lệ dự đoán trung bình trong lịch sử ít nhất 10%.
  - **B** khi mô hình dự đoán chính xác ít nhất 50% tổng số dự đoán và khi tỷ lệ dự đoán chính xác cho những khách hàng đã dự đoán lớn hơn tới 10% so với tỷ lệ dự đoán trung bình trong lịch sử.
  - **C** khi mô hình dự đoán chính xác ít hơn 50% tổng số dự đoán hoặc khi tỷ lệ dự đoán chính xác cho những khách hàng đã dự đoán nhỏ hơn tỷ lệ dự đoán trung bình trong lịch sử.
  
- **Khả năng rời khỏi (số lượng khách hàng)**: Các nhóm khách hàng dựa trên rủi ro rời khỏi dự đoán. Tùy ý, [tạo phân khúc khách hàng](prediction-based-segment.md) với nguy cơ churn cao. Những phân khúc này giúp hiểu được điểm cắt nên dành cho các thành phần phân khúc.  

  :::image type="content" source="media/subscription-churn-resultdistribution.PNG" alt-text="Biểu đồ hiển thị mức độ phân phối kết quả rời bỏ, chia thành các phạm vi từ 0-100%":::

- **Các yếu tố có ảnh hưởng nhất:** Có nhiều yếu tố được tính đến khi tạo dự đoán. Mỗi yếu tố có tầm quan trọng được tính toán cho các dự đoán tổng hợp mà một mô hình tạo ra. Sử dụng các yếu tố này để giúp xác thực kết quả dự đoán của bạn. Hoặc sử dụng thông tin này sau để [tạo phân đoạn](.//prediction-based-segment.md) điều đó có thể giúp ảnh hưởng đến rủi ro churn cho khách hàng.

  :::image type="content" source="media/subscription-churn-influentialfactors.PNG" alt-text="Danh sách cho thấy các yếu tố ảnh hưởng và tầm quan trọng của chúng trong việc dự đoán kết quả rời bỏ.":::

> [!NOTE]
> Trong thực thể đầu ra cho mô hình này, *ChurnScore* là xác suất được dự đoán của sự churn và *IsChurn* là một nhãn nhị phân dựa trên *ChurnScore* với ngưỡng 0,5. Nếu ngưỡng mặc định này không phù hợp với tình huống của bạn, [tạo một phân khúc mới](segments.md) với ngưỡng ưa thích của bạn. Để xem điểm số churn, hãy truy cập **Dữ liệu** > **Thực thể** và xem tab dữ liệu cho thực thể đầu ra mà bạn đã xác định cho mô hình này.

[!INCLUDE [footer-include](includes/footer-banner.md)]
