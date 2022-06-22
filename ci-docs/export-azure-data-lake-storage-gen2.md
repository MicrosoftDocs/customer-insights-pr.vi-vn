---
title: Xuất dữ liệu Customer Insights sang Azure Data Lake Storage thế hệ 2
description: Tìm hiểu cách định cấu hình kết nối với Azure Data Lake Storage thế hệ 2.
ms.date: 10/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 22eee11666752459a1750d728c4e254ab0c59e58
ms.sourcegitcommit: 8e9f0a9693fd8d91ad0227735ff03688fef5406f
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 06/10/2022
ms.locfileid: "8947256"
---
# <a name="export-segment-list-and-other-data-to-azure-data-lake-storage-gen2-preview"></a>Xuất danh sách phân khúc và dữ liệu khác sang Azure Data Lake Storage thế hệ 2 (xem trước)

Lưu trữ dữ liệu Customer Insights của bạn trong tài khoản Data Lake Storage thế hệ 2 hoặc sử dụng kho lưu trữ đó để chuyển dữ liệu của bạn sang các ứng dụng khác.

## <a name="known-limitations"></a>Các hạn chế đã biết

1. Đối với Azure Data Lake Storage thế hệ 2, bạn có thể chọn giữa [Bậc Hiệu suất tiêu chuẩn và Hiệu suất cao cấp](/azure/storage/blobs/create-data-lake-storage-account) khi bạn đang tạo tài khoản lưu trữ cho kho dữ liệu của mình. Nếu bạn chọn bậc Hiệu suất cao cấp, hãy chọn các blob khối cao cấp làm loại tài khoản.

## <a name="set-up-the-connection-to-azure-data-lake-storage-gen2"></a>Thiết lập kết nối với Azure Data Lake Storage thế hệ 2

1. Đi đến **Quản trị viên** > **Kết nối**.

1. Chọn **Thêm kết nối** rồi chọn **Azure Data Lake Thế hệ 2** để đặt cấu hình kết nối.

1. Đặt tên dễ nhận biết cho kết nối trong trường **Tên hiển thị**. Tên và loại kết nối mô tả kết nối này. Bạn nên chọn một tên giải thích mục đích và mục tiêu của kết nối.

1. Chọn người có thể sử dụng kết nối này. Nếu bạn không thực hiện hành động nào, giá trị mặc định sẽ là Quản trị viên. Để biết thêm thông tin, hãy xem [Cho phép người đóng góp sử dụng một kết nối cho các lần xuất](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Nhập **Tên tài khoản**, **Khóa tài khoản** và **Bộ chứa** cho Azure Data Lake Storage Thế hệ 2 của bạn.
    - Để tìm hiểu cách tạo tài khoản lưu trữ để sử dụng với Azure Data Lake Storage thế hệ 2, hãy xem [Tạo tài khoản lưu trữ](/azure/storage/blobs/create-data-lake-storage-account). 
    - Để tìm hiểu thêm về tên tài khoản lưu trữ Azure Data Lake Thế hệ 2 và khóa tài khoản, hãy xem [Quản lý các thiết đặt tài khoản lưu trữ trong cổng thông tin Azure](/azure/storage/common/storage-account-manage).

1. Chọn **Lưu** để hoàn thành kết nối.

## <a name="configure-an-export"></a>Đặt cấu hình xuất

Bạn có thể định cấu hình lần xuất này nếu bạn có quyền truy cập vào kết nối thuộc loại này. Để biết thêm thông tin, hãy xem [Các quyền cần thiết để định cấu hình xuất](export-destinations.md#set-up-a-new-export).

1. Đi tới **Dữ liệu** > **Nội dung xuất**.

1. Để tạo nội dung xuất mới, hãy chọn **Thêm nội dung xuất**.

1. Trong trường **Kết nối để xuất**, hãy chọn một kết nối từ phần **Azure Data Lake**. Nếu bạn không thấy tên phần này, tức là không có kết nối nào thuộc loại này dành cho bạn.

1. Chọn ô cạnh mỗi thực thể mà bạn muốn xuất sang vị trí này.

1. Chọn **Lưu**.

Việc lưu một nội dung xuất sẽ không chạy nội dung xuất đó ngay lập tức.

Nội dung xuất chạy trong mỗi lần [làm mới theo lịch trình](system.md#schedule-tab).
Bạn cũng có thể [xuất dữ liệu theo yêu cầu](export-destinations.md#run-exports-on-demand).

Dữ liệu đã xuất được lưu trữ trong bộ lưu trữ Azure Data Lake Thế hệ 2 mà bạn đã đặt cấu hình.

> [!TIP]
> Việc xuất các thực thể chứa một lượng lớn dữ liệu có thể dẫn đến nhiều tệp CSV trong cùng một thư mục cho mỗi lần xuất. Việc chia nhỏ xuất khẩu xảy ra vì lý do hiệu suất để giảm thiểu thời gian hoàn thành xuất khẩu.

[!INCLUDE [footer-include](includes/footer-banner.md)]
