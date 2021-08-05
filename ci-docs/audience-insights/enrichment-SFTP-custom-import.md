---
title: Tăng cường dữ liệu bằng tính năng nhập tùy chỉnh SFTP
description: Thông tin chung về tính năng nhập tùy chỉnh SFTP để tăng cường dữ liệu.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 9331cf8057850e2fbe03622831f388e73056d938
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 07/13/2021
ms.locfileid: "6555425"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a>Tăng cường thông tin hồ sơ khách hàng bằng dữ liệu tùy chỉnh (bản xem trước)

Nhập tùy chỉnh Giao thức truyền tệp bảo mật (SFTP) cho phép bạn nhập dữ liệu mà không phải trải qua quá trình hợp nhất dữ liệu. Đó là một cách linh hoạt, bảo mật và dễ dàng để đưa dữ liệu của bạn vào. Tính năng nhập tùy chỉnh SFTP có thể được sử dụng kết hợp với [Xuất SFTP](export-sftp.md) cho phép bạn xuất dữ liệu hồ sơ khách hàng cần thiết để tăng cường. Sau đó, dữ liệu có thể được xử lý và tăng cường, đồng thời bạn có thể sử dùng tính năng nhập tùy chỉnh SFTP để đưa dữ liệu tăng cường quay lại khả năng thông tin chi tiết về đối tượng của Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Điều kiện tiên quyết

Để định cấu hình tính năng nhập tùy chỉnh SFTP, bạn phải đáp ứng các điều kiện tiên quyết sau:

- Bạn có tên tệp và vị trí (đường dẫn) của tệp sẽ được nhập trên máy chủ SFTP.
- Có một tệp *model.json* chỉ định [giản đồ Common Data Model](/common-data-model/) cho dữ liệu được nhập. Tệp này phải nằm trong cùng thư mục với tệp để nhập.
- Một kết nối SFTP đã được quản trị viên định cấu hình *hoặc* bạn có quyền của [quản trị viên](permissions.md#administrator). Bạn sẽ cần thông tin xác thực của người dùng, URL và số cổng cho vị trí SFTP mà bạn muốn nhập dữ liệu từ đó.


## <a name="configure-the-import"></a>Định cấu hình dữ liệu nhập

1. Đi đến **Dữ liệu** > **Tăng cường** rồi chọn tab **Khám phá**.

1. Trên **ngăn xếp nhập tùy chỉnh SFTP**, hãy chọn **Tăng cường dữ liệu của tôi** rồi chọn **Bắt đầu**.

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="Ngăn xếp nhập tùy chỉnh SFTP.":::

1. Chọn một [kết nối](connections.md) từ danh sách thả xuống. Liên hệ với quản trị viên nếu không có kết nối. Nếu là quản trị viên, bạn có thể tạo kết nối bằng cách chọn **Thêm kết nối** rồi chọn **Nhập tùy chỉnh SFTP** từ danh sách thả xuống.

1. Chọn **Kết nối với Nhập tùy chỉnh** để xác nhận kết nối đã chọn.

1.  Chọn **Tiếp** và nhập **Đường dẫn** và **Tên tệp** của tệp dữ liệu mà bạn muốn nhập.

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="Ảnh chụp màn hình khi nhập vị trí dữ liệu.":::

1. Chọn **Tiếp** rồi đặt tên cho dữ liệu tăng cường và tên cho thực thể đầu ra. 

1. Chọn **Lưu dữ liệu tăng cường** sau khi xem xét các lựa chọn của bạn.

## <a name="configure-the-connection-for-sftp-custom-import"></a>Định cấu hình kết nối cho Nhập tùy chỉnh SFTP 

Bạn cần phải là quản trị viên thì mới có thể định cấu hình kết nối. Chọn **Thêm kết nối** khi định cấu hình dữ liệu tăng cường *hoặc* đi đến **Quản trị viên** > **Kết nối** rồi chọn **Thiết lập** trên ngăn xếp Nhập tùy chỉnh.

1. Nhập tên cho kết nối trong hộp **Tên hiển thị**.

1. Nhập tên người dùng, mật khẩu và URL máy chủ hợp lệ cho máy chủ SFTP chứa dữ liệu được nhập.

1. Xem xét và đồng ý với **Quyền riêng tư và tuân thủ dữ liệu** bằng cách đánh dấu ô **Tôi đồng ý**.

1. Chọn **Xác minh** để xác thực cấu hình.

1. Sau khi quá trình xác minh hoàn tất, bạn có thể lưu kết nối bằng cách chọn **Lưu**.

   > [!div class="mx-imgBorder"]
   > ![Trang cấu hình kết nối Experian.](media/enrichment-SFTP-connection.png "Trang cấu hình kết nối Experian")


## <a name="defining-field-mappings"></a>Đang xác định ánh xạ trường 

Thư mục chứa tệp sẽ được nhập trên máy chủ SFTP cũng phải chứa tệp *model.json*. Tệp này xác định lược đồ sẽ sử dụng để nhập dữ liệu. Lược đồ phải sử dụng [Common Data Model](/common-data-model/) để chỉ định ánh xạ trường. Một ví dụ đơn giản về tệp model.json trông như sau:

```
{
    "name": "EnrichmentFromMicrosoft",
    "description": "Model containing data enrichment",
    "entities": [
        {
            "name": "CustomImport",
            "attributes": [
                {
                    "name": "CustomerId",
                    "friendlyName": "Client id",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred City for vacation",
                    "dataType": "string"
                },
                {
                    "name": "PreferredTransportation",
                    "friendlyName": "Preferred transportation",
                    "dataType": "string"
                }
            ],
            "annotations": [
                {
                    "name": "c360:PrimaryKey",
                    "value": "CustomerId"
                }
            ]
        }
    ],
    "modifiedTime": "2020-01-02T12:00:00+08:00",
    "annotations": [
        {
            "name": "testAnnotation",
            "value": "testValue"
        }
    ]
}
```

## <a name="enrichment-results"></a>Kết quả tăng cường

Để bắt đầu quá trình tăng cường, hãy chọn **Chạy** từ thanh lệnh. Bạn cũng có thể để hệ thống chạy quá trình tăng cường tự động như một phần của [làm mới theo lịch trình](system.md#schedule-tab). Thời gian xử lý sẽ phụ thuộc vào kích thước của dữ liệu được nhập và kết nối với máy chủ SFTP.

Sau khi quá trình tăng cường hoàn tất, bạn có thể xem xét dữ liệu bổ sung tùy chỉnh mới được nhập của mình trong **Dữ liệu tăng cường của tôi**. Ngoài ra, bạn sẽ tìm thấy thời gian của lần cập nhật gần nhất và số lượng hồ sơ được tăng cường.

Bạn có thể truy cập dạng xem chi tiết của từng hồ sơ được tăng cường dữ liệu bằng cách chọn **Xem dữ liệu tăng cường**.

## <a name="next-steps"></a>Các bước tiếp theo

Xây dựng dựa trên dữ liệu khách hàng tăng cường của bạn. Tạo [phân khúc](segments.md) và [giá trị đo](measures.md), cũng như [xuất dữ liệu](export-destinations.md) để cung cấp trải nghiệm được cá nhân hóa cho khách hàng của bạn.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
