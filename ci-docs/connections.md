---
title: Tổng quan về kết nối (bản xem trước)
description: Kết nối với các dịch vụ khác từ Customer Insights.
ms.date: 08/04/2022
ms.reviewer: nikeller
ms.subservice: audience-insights
ms.topic: overview
author: m-hartmann
ms.author: mhart
manager: shellyha
searchScope:
- ci-connections
- customerInsights
ms.openlocfilehash: 8580dc7d90c75f66f73efc15f8e38f5e10fbb8a7
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245537"
---
# <a name="connections-preview-overview"></a>Tổng quan về kết nối (bản xem trước)

Kết nối là chìa khóa để cho phép chia sẻ dữ liệu với và từ Customer Insights. Mỗi kết nối thiết lập chế độ chia sẻ dữ liệu với một dịch vụ cụ thể. Sử dụng kết nối với [định cấu hình tính năng bổ sung của bên thứ ba](enrichment-hub.md) và [định cấu hình xuất khẩu](export-destinations.md). Một loại kết nối có thể được sử dụng nhiều lần. Ví dụ: một kết nối đến Dynamics 365 Marketing hoạt động cho nhiều lần xuất và một kết nối Leadspace có thể được sử dụng cho nhiều nội dung bổ sung.

## <a name="export-connections"></a>Xuất kết nối

Chỉ quản trị viên mới có thể định cấu hình các kết nối mới, nhưng họ có thể [cấp quyền truy cập cho những người đóng góp](#allow-contributors-to-use-a-connection-for-exports) để sử dụng các kết nối hiện có. Quản trị viên kiểm soát nơi dữ liệu có thể đến, những người đóng góp xác định tải trọng và tần suất phù hợp với nhu cầu của họ.

## <a name="enrichment-connections"></a>Làm giàu kết nối

Chỉ quản trị viên mới có thể định cấu hình các kết nối mới, nhưng các kết nối đã tạo luôn có sẵn cho cả quản trị viên và cộng tác viên. Quản trị viên quản lý thông tin xác thực và cho phép chuyển dữ liệu. Sau đó, cả quản trị viên và người đóng góp đều có thể dùng các kết nối cho những nội dung bổ sung.

## <a name="add-a-new-connection"></a>Thêm kết nối mới

### <a name="prerequisites"></a>Điều kiện tiên quyết

- [Quyền của quản trị viên](permissions.md)
- Các dịch vụ khác của Microsoft, nếu có, nằm trong cùng một tổ chức

1. Đi đến **Quản trị viên** > **Kết nối**.

1. Lựa chọn **Thêm kết nối** và chọn loại kết nối bạn muốn tạo. Hoặc, đi đến **Phát hiện** tab và chọn **Cài đặt** trên một ô kết nối.

1. Đặt tên dễ nhận biết cho kết nối trong trường **Tên hiển thị**. Tên và loại kết nối mô tả kết nối này. Bạn nên chọn một tên giải thích mục đích và mục tiêu của kết nối.

1. Nhập các chi tiết cần thiết. Các trường chính xác phụ thuộc vào dịch vụ bạn đang kết nối. Để biết chi tiết về loại kết nối cụ thể, hãy tham khảo bài viết về dịch vụ mục tiêu.

1. Nếu bạn [sử dụng Key Vault của riêng bạn](use-azure-key-vault.md) để lưu trữ bí mật, kích hoạt **Sử dụng Key Vault** và chọn bí mật từ danh sách.

1. Xem lại quyền riêng tư và tuân thủ dữ liệu và chọn **tôi đồng ý**.

1. Lựa chọn **Tiết kiệm** để tạo kết nối.

### <a name="data-privacy-and-compliance"></a>Quyền riêng tư về dữ liệu và sự tuân thủ

Khi bạn bật Dynamics 365 Customer Insights để truyền dữ liệu cho bên thứ ba hoặc các sản phẩm khác của Microsoft, bạn cho phép chuyển dữ liệu ra bên ngoài ranh giới tuân thủ đối với Dynamics 365 Customer Insights, bao gồm dữ liệu nhạy cảm tiềm ẩn như Dữ liệu cá nhân. Microsoft sẽ chuyển những dữ liệu đó theo hướng dẫn của bạn, nhưng bạn có trách nhiệm đảm bảo rằng bên thứ ba đáp ứng mọi nghĩa vụ về quyền riêng tư hoặc bảo mật mà bạn có thể có. Để biết thêm thông tin, hãy xem [Tuyên bố về Quyền riêng tư của Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Của bạn Dynamics 365 Customer Insights quản trị viên có thể xóa kết nối bất kỳ lúc nào để ngừng sử dụng chức năng.

## <a name="allow-contributors-to-use-a-connection-for-exports"></a>Cho phép người đóng góp sử dụng một kết nối cho các lần xuất

Khi thiết lập hoặc chỉnh sửa kết nối xuất, hãy chọn người dùng nào được phép sử dụng kết nối cụ thể này để xác định [hàng xuất khẩu](export-destinations.md). Theo mặc định, kết nối có sẵn cho người dùng có vai trò quản trị viên. Thay đổi **Chọn người có thể sử dụng kết nối này** cài đặt để cho phép người dùng có vai trò cộng tác viên sử dụng kết nối này.

- Những người đóng góp sẽ không thể xem hoặc chỉnh sửa kết nối. Họ sẽ chỉ thấy tên hiển thị và loại của nó khi tạo một bản xuất.
- Bằng cách chia sẻ kết nối, bạn cho phép những người đóng góp sử dụng kết nối. Những người đóng góp sẽ thấy các kết nối được chia sẻ khi họ thiết lập chế độ xuất. Họ có thể quản lý mọi lần xuất sử dụng kết nối cụ thể này.
- Bạn có thể thay đổi thiết đặt này trong khi vẫn giữ nội dung xuất đo những người đóng góp xác định.

## <a name="manage-existing-connections"></a>Quản lý các kết nối hiện có

1. Đi đến **Quản trị viên** > **Kết nối**.

1. Chọn **Làm giàu** hoặc **Xuất khẩu** để xem danh sách các kết nối bổ sung hoặc xuất, loại kết nối, thời điểm tạo và ai có quyền truy cập. Bạn có thể sắp xếp danh sách các kết nối theo bất kỳ cột nào.

1. Chọn kết nối để xem các hành động khả dụng.

   - **Chỉnh sửa** sự kết nối.
   - [**Loại bỏ**](#remove-a-connection) một kết nối.

### <a name="remove-a-connection"></a>Loại bỏ kết nối

Nếu kết nối bạn đang xóa được sử dụng bởi tính năng bổ sung hoặc xuất khẩu, trước tiên hãy tách hoặc xóa chúng. Hộp thoại loại bỏ hướng dẫn bạn đến các bổ sung hoặc xuất khẩu có liên quan.

> [!TIP]
> Chất làm giàu bị vô hiệu hóa và hàng xuất khẩu tách rời trở nên không hoạt động. Bạn hãy kích hoạt lại các nội dung bổ sung và nội dung xuất đã gỡ bỏ bằng cách thêm một kết nối khác vào chúng trên trang [Nội dung bổ sung](enrichment-hub.md) hoặc [Nội dung xuất](export-destinations.md).

1. Đi đến **Quản trị viên** > **Kết nối**.

1. Chọn **Làm giàu** hoặc **Xuất khẩu** chuyển hướng.

1. Chọn kết nối bạn muốn xóa.

1. Chọn **Xóa** trong menu thả xuống. Một hộp thoại xác nhận sẽ xuất hiện.

   1. Nếu có các nội dung bổ sung hoặc nội dung xuất sử dụng kết nối này, hãy chọn nút để xem những gì đang sử dụng kết nối.
      - **Xuất khẩu:** Chọn một trong hai **Loại bỏ** xuất khẩu hoặc **Tách kết nối**. Việc tách kết nối sẽ giữ cấu hình xuất, nhưng nó sẽ không được chạy cho đến khi một kết nối khác được thêm vào nó.
      - **Làm giàu:** Chọn một trong hai **Xóa bỏ** hoặc **Hủy kích hoạt** sự làm giàu.
   1. Khi kết nối không còn thành phần phụ thuộc nữa, hãy quay lại **Quản trị viên** > **Kết nối** và thử loại bỏ kết nối một lần nữa.

1. Để xác nhận xóa, hãy chọn **Loại bỏ**.

## <a name="set-up-connections-with-secrets-managed-by-your-own-key-vault"></a>Thiết lập kết nối với các bí mật do Key Vault của riêng bạn quản lý

Một số kết nối cần bí mật như khóa API hoặc mật khẩu. Một số kết nối hỗ trợ bí mật được lưu trữ trong Key Vault của riêng bạn. Tìm hiểu thêm về các kết nối được hỗ trợ và cách thiết lập trên [Kho chìa khóa của riêng bạn cho Thông tin chi tiết về khách hàng](use-azure-key-vault.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
