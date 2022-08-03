---
title: Tăng cường thông tin hồ sơ khách hàng bằng dữ liệu nhân khẩu học từ Experian (bản xem trước)
description: Thông tin chung về dịch vụ cung cấp dữ liệu của bên thứ ba Experian.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 876853ab42e8c08ad1abacb8d8a205c0aadabcf7
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195962"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Tăng cường thông tin hồ sơ khách hàng bằng dữ liệu nhân khẩu học từ Experian (bản xem trước)

Experian là công ty hàng đầu toàn cầu chuyên cung cấp dịch vụ tiếp thị và báo cáo tín dụng về người tiêu dùng cũng như doanh nghiệp. Với dịch vụ cung cấp dữ liệu của Experian, bạn có thể tìm hiểu sâu hơn về khách hàng của mình bằng cách tăng cường thông tin hồ sơ khách hàng bằng dữ liệu nhân khẩu học, chẳng hạn như quy mô hộ gia đình, mức thu nhập, v.v.

## <a name="supported-countriesregions"></a>Quốc gia/khu vực được hỗ trợ

Chúng tôi hiện chỉ hỗ trợ tăng cường thông tin hồ sơ khách hàng tại Hoa Kỳ.

## <a name="prerequisites"></a>Điều kiện tiên quyết

- Một hoạt động Experian đăng ký. Để có đăng ký, [hãy liên hệ trực tiếp với Experian](https://www.experian.com/marketing-services/contact). [Tìm hiểu thêm về dịch vụ cung cấp dữ liệu của Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).

- Một Experian [sự liên quan](connections.md) Là [đã cấu hình](#configure-the-connection-for-experian) bởi một quản trị viên.

- Experian ID người dùng, ID bên và Số mô hình cho tài khoản Truyền tải an toàn (ST) được hỗ trợ SSH của bạn Experian được tạo ra cho bạn.

## <a name="configure-the-connection-for-experian"></a>Định cấu hình kết nối cho Experian

Bạn phải là một [người quản lý](permissions.md#admin) trong Thông tin chi tiết về khách hàng và có Experian User ID, Party ID và Model Number.

1. Lựa chọn **Thêm kết nối** khi định cấu hình phần bổ sung hoặc đi tới **Quản trị viên** > **Kết nối** và chọn **Cài đặt** trên Experian ngói.

   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Ngăn cấu hình kết nối Experian.":::

1. Nhập tên cho kết nối và ID người dùng, ID bên và Số mô hình hợp lệ cho Experian Tài khoản vận tải an toàn.

1. Xem xét và chấp thuận [Quyền riêng tư dữ liệu và sự tuân thủ](#data-privacy-and-compliance) bằng cách chọn **Tôi đồng ý**.

1. Lựa chọn **Kiểm chứng** để xác thực cấu hình và sau đó chọn **Tiết kiệm**.

### <a name="data-privacy-and-compliance"></a>Quyền riêng tư về dữ liệu và sự tuân thủ

Khi bật Dynamics 365 Customer Insights để truyền dữ liệu tới Experian, bạn cho phép truyền dữ liệu ra ngoài phạm vi tuân thủ cho Dynamics 365 Customer Insights, bao gồm dữ liệu có khả năng là thông tin nhạy cảm, chẳng hạn như Dữ liệu cá nhân. Microsoft sẽ truyền những dữ liệu đó theo chỉ dẫn của bạn, nhưng bạn có trách nhiệm đảm bảo rằng Experian đáp ứng mọi nghĩa vụ về quyền riêng tư hoặc bảo mật mà bạn có thể có. Để biết thêm thông tin, hãy xem [Tuyên bố về Quyền riêng tư của Microsoft](https://go.microsoft.com/fwlink/?linkid=396732). Quản trị viên Dynamics 365 Customer Insights của bạn có thể loại bỏ dịch vụ tăng cường này bất kỳ lúc nào để ngừng sử dụng tính năng đó.

## <a name="configure-the-enrichment"></a>Đặt cấu hình dữ liệu tăng cường

1. Đi đến **Dữ liệu** > **Tăng cường** rồi chọn tab **Khám phá**.

1. Lựa chọn **Làm phong phú dữ liệu của tôi** trên **Nhân khẩu học** từ Experian ngói.

   :::image type="content" source="media/experian-tile.png" alt-text="Experian trong trang tổng quan về bổ sung.":::

1. Xem lại tổng quan và sau đó chọn **Tiếp theo**.

1. Chọn kết nối. Liên hệ với quản trị viên nếu không có kết nối.

1. Chọn **Tiếp theo**.

1. Chọn **Tập dữ liệu khách hàng** và chọn hồ sơ hoặc phân đoạn bạn muốn làm phong phú thêm với dữ liệu nhân khẩu học Experian. Các *khách hàng* thực thể làm phong phú tất cả hồ sơ khách hàng của bạn trong khi một phân khúc chỉ làm phong phú thêm hồ sơ khách hàng có trong phân khúc đó.

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Ảnh chụp màn hình khi chọn tập dữ liệu khách hàng.":::

1. Xác định loại trường nào từ các cấu hình hợp nhất của bạn để sử dụng để đối sánh dữ liệu nhân khẩu học từ Experian. Ít nhất một trong các trường **Tên và địa chỉ**, **Điện thoại** hoặc **Email** là bắt buộc. Để có độ chính xác đối sánh cao hơn, hãy thêm các trường khác. Chọn **Tiếp theo**.

1. Ánh xạ các trường của bạn với dữ liệu nhân khẩu học từ Experian.

1. Chọn **Tiếp** để hoàn thành quá trình ánh xạ trường.

1. Cung cấp một **Tên** để làm giàu và **Tên thực thể đầu ra**.

1. Chọn **Lưu dữ liệu tăng cường** sau khi xem xét các lựa chọn của bạn.

1. Lựa chọn **Chạy** để bắt đầu quá trình làm giàu hoặc đóng để quay lại **Làm giàu** trang.

## <a name="view-enrichment-results"></a>Xem kết quả bổ sung

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Các **Số lượng khách hàng làm giàu theo lĩnh vực** cung cấp thông tin chi tiết về phạm vi bao phủ của từng trường được bổ sung chi tiết.

## <a name="next-steps"></a>Các bước tiếp theo

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
