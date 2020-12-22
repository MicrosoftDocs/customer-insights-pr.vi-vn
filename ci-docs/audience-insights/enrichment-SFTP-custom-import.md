---
title: Tăng cường với nhập tùy chỉnh SFTP
description: Thông tin chung về tăng cường nhập tùy chỉnh SFTP.
ms.date: 11/18/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jdahl
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 59f7f05ca0825ba147e9e93f10fa3508ec3a16dd
ms.sourcegitcommit: ff824bbbd31fd666ab0da682bf48ea31580d242c
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 11/18/2020
ms.locfileid: "4568522"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a>Tăng cường hồ sơ khách hàng với dữ liệu tùy chỉnh (bản xem trước)

Nhập tùy chỉnh Giao thức truyền tệp bảo mật (SFTP) cho phép bạn nhập dữ liệu mà không phải trải qua quá trình hợp nhất dữ liệu. Đó là một cách linh hoạt, bảo mật và dễ dàng để đưa dữ liệu của bạn vào. Nhập tùy chỉnh SFTP có thể được sử dụng kết hợp với [Xuất SFTP](export-sftp.md) cho phép bạn xuất dữ liệu hồ sơ khách hàng cần thiết để tăng cường. Sau đó, dữ liệu có thể được xử lý, tăng cường và nhập tùy chỉnh SFTP có thể được sử dụng để đưa dữ liệu được tăng cường trở lại khả năng thông tin chi tiết của đối tượng Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Điều kiện tiên quyết

Để định cấu hình tính năng nhập tùy chỉnh SFTP, bạn phải đáp ứng các điều kiện tiên quyết sau:

- Bạn có thông tin xác thực người dùng (tên người dùng và mật khẩu) cho vị trí SFTP nơi dữ liệu sẽ được nhập từ đó.
- Bạn có URL và số cổng (thường là 22) cho máy chủ lưu trữ STFP.
- Bạn có tên tệp và vị trí của tệp sẽ được nhập trên máy chủ SFTP.
- Có 1 tệp *model.json* chỉ định lược đồ cho dữ liệu sẽ được nhập. Tệp này phải nằm trong cùng thư mục với tệp để nhập.
- Bạn có quyền [Quản trị viên](permissions.md#administrator).

## <a name="configuration"></a>Cấu hình

1. Đi đến **Dữ liệu** > **Tăng cường** và chọn tab **Khám phá**.

1. Trên **ngăn xếp nhập tùy chỉnh SFTP**, chọn **Tăng cường dữ liệu của tôi**.

   > [!div class="mx-imgBorder"]
   > ![Ngăn xếp Nhập tùy chỉnh SFTP](media/SFTP_Custom_Import_tile.png "Ngăn xếp Nhập tùy chỉnh SFTP")

1. Chọn **Bắt đầu** và cung cấp thông tin xác thực và địa chỉ cho máy chủ SFTP. Ví dụ: sftp: //mysftpserver.com:22.

1. Nhập tên của tệp chứa dữ liệu và đường dẫn đến tệp trên máy chủ SFTP nếu tệp không nằm trong thư mục gốc.

1. Xác nhận tất cả các đầu vào bằng cách chọn **Kết nối với Nhập tùy chỉnh**.

   > [!div class="mx-imgBorder"]
   > ![Hộp thả xuống Cấu hình nhập tùy chỉnh SFTP](media/SFTP_Custom_Import_Configuration_flyout.png "Hộp thả xuống Cấu hình nhập tùy chỉnh SFTP")

## <a name="defining-field-mappings"></a>Đang xác định ánh xạ trường 

Thư mục chứa tệp sẽ được nhập trên máy chủ SFTP cũng phải chứa tệp *model.json*. Tệp này xác định lược đồ sẽ sử dụng để nhập dữ liệu. Lược đồ phải sử dụng [Common Data Model](https://docs.microsoft.com/common-data-model/) để chỉ định ánh xạ trường. Một ví dụ đơn giản về tệp model.json trông như sau:

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


