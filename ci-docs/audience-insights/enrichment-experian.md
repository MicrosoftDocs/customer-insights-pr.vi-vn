---
title: Tăng cường với Experian tăng cường của bên thứ ba
description: Thông tin chung về tăng cường của bên thứ ba Experian.
ms.date: 09/17/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 60fc49734e54740e83b47a7028be216a0eb81e49
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668839"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Làm phong phú hồ sơ khách hàng với dữ liệu nhân khẩu học từ Experian (bản xem trước)

Experian là công ty tiên phong toàn cầu về các dịch vụ tiếp thị và báo cáo tín dụng cho người tiêu dùng và doanh nghiệp. Với dịch vụ làm phong phú dữ liệu của Experian, bạn có thể có được sự hiểu biết sâu sắc hơn về khách hàng của mình qua việc làm phong phú hồ sơ khách hàng của bạn bằng dữ liệu nhân khẩu học, như: quy mô hộ gia đình, thu nhập, v.v.

## <a name="prerequisites"></a>Điều kiện tiên quyết

Để đặt cấu hình Experian, các điều kiện tiên quyết sau phải được đáp ứng:

- Bạn có gói đăng ký Experian đang hoạt động. Để đăng ký, hãy [liên hệ trực tiếp với Experian](https://www.experian.com/marketing-services/contact). [Tìm hiểu thêm về Tăng cường dữ liệu bằng Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).
- Bạn có ID người dùng, ID bên và Số mô hình cho tài khoản Secure Transport (ST) hỗ trợ SSH của mình mà Experian đã tạo cho bạn.
- Bạn có quyền [Quản trị viên](permissions.md#administrator) trong thông tin chi tiết về đối tượng.

## <a name="configuration"></a>Cấu hình

1. Đi đến **Dữ liệu** > **Tăng cường** và chọn tab **Khám phá**.

1. Chọn **Tăng cường dữ liệu của tôi** trên ngăn xếp Experian.

   > [!div class="mx-imgBorder"]
   > ![Ngăn xếp Experian](media/experian-tile.png "Ngăn xếp Experian")

1. Chọn **Bắt đầu** rồi nhập ID người dùng, ID bên và Số mô hình cho tài khoản Experian Secure Transport của bạn. Xem lại và đồng ý với **Quyền riêng tư và tuân thủ dữ liệu** bằng cách đánh dấu ô **Tôi đồng ý**. Xác nhận tất cả các đầu vào bằng cách chọn **Áp dụng**.

## <a name="map-your-fields"></a>Ánh xạ trường của bạn

1. Chọn **Thêm dữ liệu** rồi chọn mã định danh chính từ **Tên và địa chỉ**, **Email** hoặc **Điện thoại** và gửi đến Experian để thực hiện quá trình nhận dạng danh tính.

   > [!TIP]
   > Nhiều thuộc tính mã định danh chính được gửi đến Experian có thể cho tỷ lệ khớp cao hơn.

1. Chọn **Tiếp** và ánh xạ các thuộc tính tương ứng từ thực thể khách hàng hợp nhất của bạn cho các trường mã định danh chính đã chọn.

1. Chọn **Thêm thuộc tính** để ánh xạ thêm thuộc tính mà bạn muốn gửi đến Experian.

1.  Chọn **Lưu** để hoàn tất quá trình ánh xạ trường.

   > [!div class="mx-imgBorder"]
   > ![Ánh xạ trường Experian](media/experian-field-mapping.png "Ánh xạ trường Experian")

## <a name="enrichment-results"></a>Kết quả làm phong phú

Để bắt đầu quá trình tăng cường, hãy chọn **Chạy** từ thanh lệnh. Bạn cũng có thể để hệ thống chạy quá trình tăng cường tự động như một phần của [làm mới theo lịch trình](system.md#schedule-tab). Thời gian xử lý sẽ phụ thuộc vào quy mô dữ liệu khách hàng của bạn và quy trình tăng cường được thiết lập cho tài khoản của bạn bởi Experian.

Sau khi quá trình tăng cường hoàn tất, bạn có thể xem lại dữ liệu hồ sơ khách hàng mới được bổ sung trong **Nội dung tăng cường của tôi**. Ngoài ra, bạn sẽ tìm thấy thời gian của lần cập nhật gần nhất và số lượng hồ sơ được tăng cường.

Bạn có thể truy cập dạng xem chi tiết của từng hồ sơ được làm phong phú bằng cách chọn **Xem dữ liệu được làm phong phú**.

## <a name="next-steps"></a>Các bước tiếp theo

Xây dựng dựa trên dữ liệu khách hàng phong phú của bạn. Tạo [phân khúc](segments.md), [biện pháp](measures.md) và [xuất dữ liệu](export-destinations.md) để cung cấp trải nghiệm cá nhân cho khách hàng của bạn.

## <a name="data-privacy-and-compliance"></a>Quyền riêng tư về dữ liệu và tuân thủ

Khi bật Dynamics 365 Customer Insights để truyền dữ liệu tới Experian, bạn cho phép chuyển dữ liệu ra bên ngoài ranh giới tuân thủ cho Dynamics 365 Customer Insights, bao gồm dữ liệu nhạy cảm tiềm ẩn như Dữ liệu cá nhân. Microsoft sẽ chuyển những dữ liệu đó theo chỉ dẫn của bạn, nhưng bạn có trách nhiệm đảm bảo rằng Experian đáp ứng mọi nghĩa vụ về quyền riêng tư hoặc bảo mật mà bạn có thể có. Để biết thêm thông tin, hãy xem [Tuyên bố về Quyền riêng tư của Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Quản trị viên Dynamics 365 Customer Insights của bạn có thể xóa tính năng tăng cường này bất kỳ lúc nào để ngừng sử dụng chức năng này.
