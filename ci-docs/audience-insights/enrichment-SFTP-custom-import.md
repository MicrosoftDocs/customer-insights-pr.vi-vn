---
title: Tăng cường với nhập tùy chỉnh SFTP
description: Thông tin chung về tăng cường nhập tùy chỉnh SFTP.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: a2d450635c19432bdd88db74b61c17febdeb568d
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896307"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a>Tăng cường hồ sơ khách hàng với dữ liệu tùy chỉnh (bản xem trước)

Công cụ nhập tùy chỉnh Giao thức truyền tệp bảo mật (SFTP) cho phép bạn nhập dữ liệu mà không phải trải qua quá trình hợp nhất dữ liệu. Đó là một cách linh hoạt, bảo mật và dễ dàng để đưa dữ liệu của bạn vào. Nhập tùy chỉnh SFTP có thể được sử dụng kết hợp với [Xuất SFTP](export-sftp.md) cho phép bạn xuất dữ liệu hồ sơ khách hàng cần thiết để tăng cường. Sau đó, dữ liệu có thể được xử lý, tăng cường và nhập tùy chỉnh SFTP có thể được sử dụng để đưa dữ liệu được tăng cường trở lại khả năng thông tin chi tiết của đối tượng Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Điều kiện tiên quyết

Để định cấu hình tính năng nhập tùy chỉnh SFTP, bạn phải đáp ứng các điều kiện tiên quyết sau:

- Bạn có tên tệp và vị trí (đường dẫn) của tệp sẽ được nhập trên máy chủ SFTP.
- Có một tệp *model.json* chỉ định [giản đồ Common Data Model](/common-data-model/) cho dữ liệu được nhập. Tệp này phải nằm trong cùng thư mục với tệp để nhập.
- Một kết nối SFTP đã được quản trị viên đặt cấu hình *hoặc* bạn có quyền của [quản trị viên](permissions.md#administrator). Bạn sẽ cần thông tin xác thực của người dùng, URL và số cổng cho vị trí SFTP mà bạn muốn nhập dữ liệu từ đó.


## <a name="configure-the-import"></a>Đặt cấu hình nội dung nhập

1. Đi đến **Dữ liệu** > **Tăng cường** và chọn tab **Khám phá**.

1. Trên **ngăn xếp nhập tùy chỉnh SFTP**, hãy chọn **Làm phong phú dữ liệu của tôi** rồi chọn **Bắt đầu**.

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="Ngăn xếp nhập tùy chỉnh SFTP.":::

1. Chọn một [kết nối](connections.md) từ danh sách thả xuống. Liên hệ với quản trị viên nếu không có kết nối. Nếu là quản trị viên, bạn có thể tạo kết nối bằng cách chọn **Thêm kết nối** rồi chọn **Nhập tùy chỉnh SFTP** từ danh sách thả xuống.

1. Chọn **Kết nối với Nhập tùy chỉnh** để xác nhận kết nối đã chọn.

1.  Chọn **Tiếp** rồi nhập **Tên tệp** và **Đường dẫn** của tệp dữ liệu mà bạn muốn nhập.

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="Ảnh chụp màn hình khi nhập vị trí dữ liệu.":::

1. Chọn **Tiếp** rồi đặt tên cho nội dung bổ sung và tên cho thực thể đầu ra. 

1. Chọn **Lưu nội dung bổ sung** sau khi xem xét các lựa chọn của bạn.

## <a name="configure-the-connection-for-sftp-custom-import"></a>Đặt cấu hình kết nối cho Nhập tùy chỉnh SFTP 

Bạn cần phải là quản trị viên thì mới có thể đặt cấu hình kết nối. Chọn **Thêm kết nối** khi đặt cấu hình nội dung bổ sung *hoặc* đi đến **Quản trị viên** > **Kết nối** rồi chọn **Thiết lập** trên ngăn xếp Nhập tùy chỉnh.

1. Nhập tên cho kết nối trong hộp **Tên hiển thị**.

1. Nhập tên người dùng, mật khẩu và URL máy chủ hợp lệ cho máy chủ STFP mà dữ liệu được nhập nằm trên đó.

1. Xem lại và đồng ý với **Quyền riêng tư và tuân thủ dữ liệu** bằng cách đánh dấu ô **Tôi đồng ý**.

1. Chọn **Xác minh** để xác thực cấu hình.

1. Sau khi xác minh xong, bạn có thể lưu kết nối bằng cách nhấp vào **Lưu**.

> [!div class="mx-imgBorder"]
   > ![Trang cấu hình kết nối Experian](media/enrichment-SFTP-connection.png "Trang cấu hình kết nối Experian")


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

## <a name="enrichment-results"></a>Kết quả làm phong phú

Để bắt đầu quá trình tăng cường, hãy chọn **Chạy** từ thanh lệnh. Bạn cũng có thể để hệ thống chạy quá trình tăng cường tự động như một phần của [làm mới theo lịch trình](system.md#schedule-tab). Thời gian xử lý sẽ phụ thuộc vào kích thước của dữ liệu được nhập và kết nối với máy chủ SFTP.

Sau khi quá trình tăng cường hoàn tất, bạn có thể xem lại dữ liệu bổ sung tùy chỉnh mới được nhập của mình trong **Nội dung tăng cường của tôi**. Ngoài ra, bạn sẽ tìm thấy thời gian của lần cập nhật gần nhất và số lượng hồ sơ được tăng cường.

Bạn có thể truy cập dạng xem chi tiết của từng hồ sơ được làm phong phú bằng cách chọn **Xem dữ liệu được làm phong phú**.

## <a name="next-steps"></a>Các bước tiếp theo

Xây dựng dựa trên dữ liệu khách hàng phong phú của bạn. Tạo [phân đoạn](segments.md), [đo lường](measures.md) và [xuất dữ liệu](export-destinations.md) để cung cấp trải nghiệm cá nhân hóa cho khách hàng của bạn.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
