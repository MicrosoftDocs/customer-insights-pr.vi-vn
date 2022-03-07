---
title: Tăng cường thông tin bằng dịch vụ cung cấp dữ liệu của bên thứ ba Experian
description: Thông tin chung về dịch vụ cung cấp dữ liệu của bên thứ ba Experian.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: ad1023135516ca9c49818d19aa84df68d16b2e3c
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 02/16/2022
ms.locfileid: "8229995"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Tăng cường thông tin hồ sơ khách hàng bằng dữ liệu nhân khẩu học từ Experian (bản xem trước)

Experian là công ty hàng đầu toàn cầu chuyên cung cấp dịch vụ tiếp thị và báo cáo tín dụng về người tiêu dùng cũng như doanh nghiệp. Với dịch vụ cung cấp dữ liệu của Experian, bạn có thể tìm hiểu sâu hơn về khách hàng của mình bằng cách tăng cường thông tin hồ sơ khách hàng bằng dữ liệu nhân khẩu học, chẳng hạn như quy mô hộ gia đình, mức thu nhập, v.v.

## <a name="prerequisites"></a>Điều kiện tiên quyết

Để định cấu hình Experian, bạn phải đáp ứng các điều kiện tiên quyết sau:

- Bạn phải có đăng ký Experian hiện hoạt. Để có đăng ký, [hãy liên hệ trực tiếp với Experian](https://www.experian.com/marketing-services/contact). [Tìm hiểu thêm về dịch vụ cung cấp dữ liệu của Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).

- Một kết nối Experian đã được quản trị viên định cấu hình *hoặc* bạn có quyền của [quản trị viên](permissions.md#administrator). Bạn cũng cần có ID người dùng, ID bên và Số mô hình cho tài khoản Truyền tải an toàn (ST) hỗ trợ SSH mà Experian tạo cho bạn.

## <a name="supported-countriesregions"></a>Quốc gia/khu vực được hỗ trợ

Chúng tôi hiện chỉ hỗ trợ tăng cường thông tin hồ sơ khách hàng tại Hoa Kỳ.

## <a name="configure-the-enrichment"></a>Định cấu hình dữ liệu tăng cường

1. Đi đến **Dữ liệu** > **Tăng cường** rồi chọn tab **Khám phá**.

1. Chọn **Tăng cường dữ liệu của tôi** trên ngăn xếp Experian.

   > [!div class="mx-imgBorder"]
   > ![Ngăn xếp Experian.](media/experian-tile.png "Ngăn xếp Experian")
   > 

1. Chọn một [kết nối](connections.md) từ danh sách thả xuống. Liên hệ với quản trị viên nếu không có kết nối. Nếu là quản trị viên, bạn có thể tạo kết nối bằng cách chọn **Thêm kết nối** rồi chọn Experian từ danh sách thả xuống. 

1. Chọn **Kết nối với Experian** để xác nhận kết nối được chọn.

1.  Chọn **Tiếp** rồi chọn **Tập hợp dữ liệu khách hàng** bạn muốn tăng cường bằng dữ liệu nhân khẩu học từ Experian. Bạn có thể chọn thực thể **Khách hàng** để tăng cường dữ liệu cho tất cả hồ sơ khách hàng của bạn hoặc chọn một thực thể phân khúc để chỉ tăng cường dữ liệu cho hồ sơ khách hàng có trong phân khúc đó.

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Ảnh chụp màn hình khi chọn tập dữ liệu khách hàng.":::

1. Chọn **Tiếp** và xác định loại trường nào từ hồ sơ hợp nhất của bạn sẽ được dùng để tìm kiếm dữ liệu nhân khẩu học phù hợp từ Experian. Ít nhất một trong các trường **Tên và địa chỉ**, **Điện thoại** hoặc **Email** là bắt buộc. Để có độ chính xác đối sánh cao hơn, có thể thêm tối đa hai trường khác. Lựa chọn này sẽ ảnh hưởng đến các trường ánh xạ mà bạn có quyền truy cập trong bước tiếp theo.

    > [!TIP]
    > Càng gửi nhiều thuộc tính định danh chính đến Experian, tỷ lệ đối sánh càng cao.

1. Chọn **Tiếp** để bắt đầu quá trình ánh xạ trường.

1. Xác định trường nào từ hồ sơ hợp nhất của bạn sẽ được dùng để tìm kiếm dữ liệu nhân khẩu học phù hợp từ Experian. Các trường bắt buộc đều được đánh dấu.

1. Đặt tên cho dữ liệu tăng cường và tên cho thực thể đầu ra.

1. Chọn **Lưu dữ liệu tăng cường** sau khi xem xét các lựa chọn của bạn.

## <a name="configure-the-connection-for-experian"></a>Định cấu hình kết nối cho Experian 

Bạn cần phải là quản trị viên thì mới có thể định cấu hình kết nối. Chọn **Thêm kết nối** khi định cấu hình tăng cường *hoặc* đi đến phần **Quản trị viên** > **Kết nối** rồi chọn **Thiết lập** trên ngăn xếp Experian.

1. Chọn **Bắt đầu**.

1. Nhập tên cho kết nối trong hộp **Tên hiển thị**.

1. Nhập ID người dùng, ID bên và Số mô hình hợp lệ cho tài khoản Truyền tải an toàn Experian.

1. Xem xét và chấp thuận **Quyền riêng tư dữ liệu và sự tuân thủ** bằng cách chọn **Tôi đồng ý**.

1. Chọn **Xác minh** để xác thực cấu hình.

1. Sau khi hoàn thành xác minh, hãy chọn **Lưu**.
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Ngăn cấu hình kết nối Experian.":::

## <a name="enrichment-results"></a>Kết quả tăng cường

Để bắt đầu quá trình tăng cường, hãy chọn **Chạy** từ thanh lệnh. Bạn cũng có thể để hệ thống chạy quá trình tăng cường tự động như một phần của [làm mới theo lịch trình](system.md#schedule-tab). Thời gian xử lý sẽ phụ thuộc vào kích thước dữ liệu khách hàng và quy trình tăng cường do Experian thiết lập cho tài khoản của bạn.

Sau khi quá trình tăng cường hoàn tất, bạn có thể xem xét dữ liệu hồ sơ khách hàng mới được bổ sung trong **Dữ liệu tăng cường của tôi**. Ngoài ra, bạn sẽ tìm thấy thời gian của lần cập nhật gần nhất và số lượng hồ sơ được tăng cường.

Bạn có thể truy cập dạng xem chi tiết của từng hồ sơ được tăng cường dữ liệu bằng cách chọn **Xem dữ liệu tăng cường**.

## <a name="next-steps"></a>Các bước tiếp theo

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Quyền riêng tư về dữ liệu và sự tuân thủ

Khi bật Dynamics 365 Customer Insights để truyền dữ liệu tới Experian, bạn cho phép truyền dữ liệu ra ngoài phạm vi tuân thủ cho Dynamics 365 Customer Insights, bao gồm dữ liệu có khả năng là thông tin nhạy cảm, chẳng hạn như Dữ liệu cá nhân. Microsoft sẽ truyền những dữ liệu đó theo chỉ dẫn của bạn, nhưng bạn có trách nhiệm đảm bảo rằng Experian đáp ứng mọi nghĩa vụ về quyền riêng tư hoặc bảo mật mà bạn có thể có. Để biết thêm thông tin, hãy xem [Tuyên bố về Quyền riêng tư của Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Quản trị viên Dynamics 365 Customer Insights của bạn có thể loại bỏ dịch vụ tăng cường này bất kỳ lúc nào để ngừng sử dụng tính năng đó.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
