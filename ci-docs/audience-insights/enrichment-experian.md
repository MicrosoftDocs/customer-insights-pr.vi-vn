---
title: Tăng cường với Experian tăng cường của bên thứ ba
description: Thông tin chung về tăng cường của bên thứ ba Experian.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 9cf2a7fa18ecc022ea67f6829f52381ad59f3172
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896399"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Làm phong phú hồ sơ khách hàng với dữ liệu nhân khẩu học từ Experian (bản xem trước)

Experian là công ty tiên phong toàn cầu về các dịch vụ tiếp thị và báo cáo tín dụng cho người tiêu dùng và doanh nghiệp. Với dịch vụ làm phong phú dữ liệu của Experian, bạn có thể có được sự hiểu biết sâu sắc hơn về khách hàng của mình qua việc làm phong phú hồ sơ khách hàng của bạn bằng dữ liệu nhân khẩu học, như: quy mô hộ gia đình, thu nhập, v.v.

## <a name="prerequisites"></a>Điều kiện tiên quyết

Để đặt cấu hình Experian, các điều kiện tiên quyết sau phải được đáp ứng:

- Bạn có gói đăng ký Experian đang hoạt động. Để đăng ký, hãy [liên hệ trực tiếp với Experian](https://www.experian.com/marketing-services/contact). [Tìm hiểu thêm về Tăng cường dữ liệu bằng Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).

- Một kết nối Experian đã được quản trị viên đặt cấu hình *hoặc* bạn có quyền của [quản trị viên](permissions.md#administrator). Bạn cũng cần ID người dùng, ID bên và Số mô hình cho tài khoản Truyền tải an toàn (ST) có hỗ trợ SSH mà Experian đã tạo cho bạn.

## <a name="configure-the-enrichment"></a>Đặt cấu hình nội dung bổ sung

1. Đi đến **Dữ liệu** > **Tăng cường** và chọn tab **Khám phá**.

1. Chọn **Tăng cường dữ liệu của tôi** trên ngăn xếp Experian.

   > [!div class="mx-imgBorder"]
   > ![Ngăn xếp Experian](media/experian-tile.png "Ngăn xếp Experian")
   > 

1. Chọn một [kết nối](connections.md) từ danh sách thả xuống. Liên hệ với quản trị viên nếu không có kết nối. Nếu là quản trị viên, bạn có thể tạo kết nối bằng cách chọn **Thêm kết nối** rồi chọn Experian từ menu thả xuống. 

1. Chọn **Kết nối với Experian** để xác nhận lựa chọn kết nối.

1.  Chọn **Tiếp** rồi chọn **Tập hợp dữ liệu khách hàng** mà bạn muốn bổ sung thêm dữ liệu nhân khẩu học từ Experian. Bạn có thể chọn thực thể **khách hàng** để làm phong phú tất cả hồ sơ khách hàng của bạn hoặc chọn một thực thể phân khúc để chỉ làm phong phú thêm hồ sơ khách hàng có trong phân khúc đó.

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Ảnh chụp màn hình khi chọn tập dữ liệu khách hàng.":::

1. Chọn **Tiếp** và xác định loại trường nào từ hồ sơ hợp nhất của bạn sẽ được sử dụng để tìm kiếm dữ liệu nhân khẩu học phù hợp từ Experian. Ít nhất một trong các trường **Tên và địa chỉ**, **Điện thoại** hoặc **Email** là bắt buộc. Để có độ chính xác đối sánh cao hơn, có thể thêm tối đa hai trường khác. Lựa chọn này sẽ ảnh hưởng đến các trường ánh xạ mà bạn có quyền truy cập trong bước tiếp theo.

    > [!TIP]
    > Nhiều thuộc tính mã định danh chính được gửi đến Experian có thể cho tỷ lệ khớp cao hơn.

1. Chọn **Tiếp** để bắt đầu quá trình ánh xạ trường.

1. Xác định loại trường nào từ hồ sơ hợp nhất của bạn sẽ được sử dụng để tìm kiếm dữ liệu nhân khẩu học phù hợp từ Experian. Các trường bắt buộc đều được đánh dấu.

1. Đặt tên cho nội dung bổ sung và tên cho thực thể đầu ra.

1. Chọn **Lưu nội dung bổ sung** sau khi xem xét các lựa chọn của bạn.

## <a name="configure-the-connection-for-experian"></a>Đặt cấu hình kết nối cho Experian 

Bạn cần phải là quản trị viên thì mới có thể đặt cấu hình kết nối. Chọn **Thêm kết nối** khi đặt cấu hình nội dung bổ sung *hoặc* đi đến **Quản trị viên** > **Kết nối** rồi chọn **Thiết lập** trên ngăn xếp Experian.

1. Chọn **Bắt đầu**.

1. Nhập tên cho kết nối trong hộp **Tên hiển thị**.

1. Nhập ID người dùng, ID bên và Số mô hình hợp lệ cho tài khoản Truyền tải an toàn Experian của bạn.

1. Xem lại và đồng ý với **Quyền riêng tư về dữ liệu và tuân thủ** bằng cách đánh dấu vào hộp kiểm **Tôi đồng ý**

1. Chọn **Xác minh** để xác thực cấu hình.

1. Sau khi hoàn thành xác minh, hãy chọn **Lưu**.
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Ngăn cấu hình kết nối Experian.":::

## <a name="enrichment-results"></a>Kết quả làm phong phú

Để bắt đầu quá trình tăng cường, hãy chọn **Chạy** từ thanh lệnh. Bạn cũng có thể để hệ thống chạy quá trình tăng cường tự động như một phần của [làm mới theo lịch trình](system.md#schedule-tab). Thời gian xử lý sẽ phụ thuộc vào quy mô dữ liệu khách hàng của bạn và quy trình tăng cường được thiết lập cho tài khoản của bạn bởi Experian.

Sau khi quá trình tăng cường hoàn tất, bạn có thể xem lại dữ liệu hồ sơ khách hàng mới được bổ sung trong **Nội dung tăng cường của tôi**. Ngoài ra, bạn sẽ tìm thấy thời gian của lần cập nhật gần nhất và số lượng hồ sơ được tăng cường.

Bạn có thể truy cập dạng xem chi tiết của từng hồ sơ được làm phong phú bằng cách chọn **Xem dữ liệu được làm phong phú**.

## <a name="next-steps"></a>Các bước tiếp theo

Xây dựng dựa trên dữ liệu khách hàng phong phú của bạn. Tạo [phân khúc](segments.md), [biện pháp](measures.md) và [xuất dữ liệu](export-destinations.md) để cung cấp trải nghiệm cá nhân cho khách hàng của bạn.

## <a name="data-privacy-and-compliance"></a>Quyền riêng tư về dữ liệu và tuân thủ

Khi bật Dynamics 365 Customer Insights để truyền dữ liệu tới Experian, bạn cho phép chuyển dữ liệu ra bên ngoài ranh giới tuân thủ cho Dynamics 365 Customer Insights, bao gồm dữ liệu nhạy cảm tiềm ẩn như Dữ liệu cá nhân. Microsoft sẽ chuyển những dữ liệu đó theo chỉ dẫn của bạn, nhưng bạn có trách nhiệm đảm bảo rằng Experian đáp ứng mọi nghĩa vụ về quyền riêng tư hoặc bảo mật mà bạn có thể có. Để biết thêm thông tin, hãy xem [Tuyên bố về Quyền riêng tư của Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Quản trị viên Dynamics 365 Customer Insights của bạn có thể xóa tính năng tăng cường này bất kỳ lúc nào để ngừng sử dụng chức năng này.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
