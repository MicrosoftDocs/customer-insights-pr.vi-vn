---
title: Tăng cường dữ liệu bằng tính năng nhập tùy chỉnh SFTP
description: Thông tin chung về tính năng nhập tùy chỉnh SFTP để tăng cường dữ liệu.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 657afb6fcb68429680eb677734b4115e69769008
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 06/13/2022
ms.locfileid: "8953745"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a>Tăng cường thông tin hồ sơ khách hàng bằng dữ liệu tùy chỉnh (bản xem trước)

Nhập tùy chỉnh Giao thức truyền tệp bảo mật (SFTP) cho phép bạn nhập dữ liệu mà không phải trải qua quá trình hợp nhất dữ liệu. Đó là một cách linh hoạt, bảo mật và dễ dàng để đưa dữ liệu của bạn vào. Tính năng nhập tùy chỉnh SFTP có thể được sử dụng kết hợp với [Xuất SFTP](export-sftp.md) cho phép bạn xuất dữ liệu hồ sơ khách hàng cần thiết để tăng cường. Sau đó, dữ liệu có thể được xử lý và bổ sung chi tiết đồng thời có thể sử dụng tính năng nhập tùy chỉnh SFTP để chuyển dữ liệu đã được bổ sung chi tiết trở lại Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Điều kiện tiên quyết

- Đã biết tên tệp và vị trí (đường dẫn) của tệp sẽ được nhập trên máy chủ SFTP.

- Một *model.json* tệp chỉ định lược đồ Mô hình Dữ liệu Chung cho dữ liệu được nhập sẵn có. Tệp này phải nằm trong cùng thư mục với tệp để nhập.

- SFTP [sự liên quan](connections.md) Là [đã cấu hình](#configure-the-connection-for-sftp-custom-import).

## <a name="file-schema-example"></a>Ví dụ về lược đồ tệp

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
                    "friendlyName": "Client ID",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred city for vacation",
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

## <a name="configure-the-connection-for-sftp-custom-import"></a>Định cấu hình kết nối cho Nhập tùy chỉnh SFTP

Bạn phải là một [người quản lý](permissions.md#admin) trong Thông tin chi tiết về khách hàng và có bằng chứng xác thực người dùng, URL và số cổng cho vị trí SFTP nơi bạn muốn nhập dữ liệu từ đó.

1. Lựa chọn **Thêm kết nối** khi định cấu hình phần bổ sung hoặc đi đến **Quản trị viên** > **Kết nối** và chọn **Cài đặt** trên ô Nhập tùy chỉnh.

   :::image type="content" source="media/enrichment-SFTP-connection.png" alt-text="Trang cấu hình kết nối Nhập tùy chỉnh.":::

1. Nhập tên cho kết nối.

1. Nhập tên người dùng, mật khẩu và URL máy chủ hợp lệ cho máy chủ SFTP chứa dữ liệu được nhập.

1. Xem xét và chấp thuận [Quyền riêng tư dữ liệu và sự tuân thủ](#data-privacy-and-compliance) bằng cách chọn **Tôi đồng ý**.

1. Lựa chọn **Kiểm chứng** để xác thực cấu hình và sau đó chọn **Tiết kiệm**.

### <a name="data-privacy-and-compliance"></a>Quyền riêng tư về dữ liệu và sự tuân thủ

Khi bạn bật Dynamics 365 Customer Insights để truyền dữ liệu bằng Nhập tùy chỉnh, bạn cho phép chuyển dữ liệu ra bên ngoài ranh giới tuân thủ đối với Dynamics 365 Customer Insights, bao gồm dữ liệu nhạy cảm tiềm ẩn như Dữ liệu cá nhân. Microsoft sẽ chuyển những dữ liệu đó theo chỉ dẫn của bạn, nhưng bạn có trách nhiệm đảm bảo rằng dữ liệu đáp ứng mọi nghĩa vụ về quyền riêng tư hoặc bảo mật mà bạn có thể có. Để biết thêm thông tin, hãy xem [Tuyên bố về Quyền riêng tư của Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Quản trị viên Dynamics 365 Customer Insights của bạn có thể loại bỏ dịch vụ tăng cường này bất kỳ lúc nào để ngừng sử dụng tính năng đó.

## <a name="configure-the-import"></a>Định cấu hình dữ liệu nhập

1. Đi đến **Dữ liệu** > **Tăng cường** rồi chọn tab **Khám phá**.

1. Lựa chọn **Làm phong phú dữ liệu của tôi** trên **Nhập tùy chỉnh SFTP** ngói.

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="Ngăn xếp nhập tùy chỉnh SFTP.":::

1. Xem lại tổng quan và sau đó chọn **Tiếp theo**.

1. Chọn kết nối. Liên hệ với quản trị viên nếu không có sẵn.

1. Chọn **Tập dữ liệu khách hàng** và chọn hồ sơ hoặc phân đoạn bạn muốn làm phong phú thêm. Các *khách hàng* thực thể làm phong phú tất cả hồ sơ khách hàng của bạn trong khi một phân khúc chỉ làm phong phú thêm hồ sơ khách hàng có trong phân khúc đó.

1. Chọn **Tiếp theo**.

1. Nhập **Đường dẫn** và **Tên tệp** của tệp dữ liệu mà bạn muốn nhập.

1. Chọn **Tiếp theo**.

1. Cung cấp một **Tên** để làm giàu và **Tên thực thể đầu ra**.

1. Chọn **Lưu dữ liệu tăng cường** sau khi xem xét các lựa chọn của bạn.

1. Lựa chọn **Chạy** để bắt đầu quá trình làm giàu hoặc đóng để quay lại **Làm giàu** trang.

## <a name="enrichment-results"></a>Kết quả tăng cường

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

## <a name="next-steps"></a>Các bước tiếp theo

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
