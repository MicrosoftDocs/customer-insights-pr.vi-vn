---
title: Kết nối với các dịch vụ khác từ Customer Insights.
description: Chia sẻ dữ liệu với các dịch vụ khác.
ms.date: 04/09/2021
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: overview
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: e78e18b75ee9797b5fc76486615992e301e4c650
ms.sourcegitcommit: bb1ca84bc38e81fb2ff2961c457384b7beb5b5fa
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 01/15/2022
ms.locfileid: "7977763"
---
# <a name="connections-preview-overview"></a>Tổng quan về kết nối (bản xem trước)

Kết nối là chìa khóa để cho phép chia sẻ dữ liệu với và từ Customer Insights. Mỗi kết nối thiết lập chế độ chia sẻ dữ liệu với một dịch vụ cụ thể. Kết nối là nền tảng để [đặt cấu hình nội dung bổ sung của bên thứ ba](enrichment-hub.md) và [đặt cấu hình nội dung xuất](export-destinations.md). Một loại kết nối có thể được sử dụng nhiều lần. Ví dụ: một kết nối đến Dynamics 365 Marketing hoạt động cho nhiều lần xuất và một kết nối Leadspace có thể được sử dụng cho nhiều nội dung bổ sung.

Đi đến **Quản trị viên** > **Kết nối** để tạo và xem các kết nối.

Tab **Kết nối** hiển thị cho bạn tất cả các kết nối hiện hoạt. Danh sách hiển thị một hàng cho mỗi kết nối. 

Xem tổng quan nhanh, nội dung mô tả và tìm hiểu những gì bạn có thể làm với từng tùy chọn khả năng mở rộng trên tab **Khám phá**.

### <a name="exports"></a>Nội dung xuất

Chỉ quản trị viên là có thể đặt cấu hình các kết nối mới, nhưng họ có thể cấp quyền truy cập cho những người đóng góp để sử dụng các kết nối hiện có. Quản trị viên kiểm soát nơi dữ liệu có thể đến, những người đóng góp xác định tải trọng và tần suất phù hợp với nhu cầu của họ. Để biết thêm thông tin, hãy xem [Cho phép người đóng góp sử dụng một kết nối cho các lần xuất](#allow-contributors-to-use-a-connection-for-exports).

### <a name="enrichments"></a>Nội dung tăng cường

Chỉ quản trị viên là có thể đặt cấu hình các kết nối mới nhưng các kết nối đã tạo luôn có sẵn cho cả quản trị viên và người đóng góp. Quản trị viên quản lý thông tin xác thực và cho phép chuyển dữ liệu. Sau đó, cả quản trị viên và người đóng góp đều có thể dùng các kết nối cho những nội dung bổ sung.

## <a name="add-a-new-connection"></a>Thêm kết nối mới

Để thêm kết nối, bạn cần có [quyền của quản trị viên](permissions.md). Nếu bạn kết nối với các dịch vụ khác của Microsoft, chúng tôi giả định rằng cả hai dịch vụ đều nằm trong cùng một tổ chức.

1. Đi đến **Quản trị viên** > **Kết nối (bản xem trước)**.

1. Đi đến tab **Kết nối**.

1. Chọn **Thêm kết nối** để tạo kết nối mới. Chọn loại kết nối bạn muốn tạo từ menu thả xuống.

1. Trong ngăn **Thiết lập kết nối**, hãy cung cấp thông tin chi tiết được yêu cầu. 
   1. **Tên hiển thị** và loại kết nối mô tả một kết nối. Bạn nên chọn một tên giải thích mục đích và mục tiêu của kết nối này.
   1. Các trường chính xác phụ thuộc vào dịch vụ bạn đang kết nối. Bạn có thể tìm hiểu về thông tin chi tiết của một loại kết nối cụ thể trong bài viết về dịch vụ mục tiêu.
   1. Nếu bạn [sử dụng Key Vault của riêng bạn](use-azure-key-vault.md) để lưu trữ bí mật, kích hoạt **Sử dụng Key Vault** và chọn bí mật từ danh sách.

1. Để tạo kết nối, hãy chọn **Lưu**.

Bạn cũng có thể chọn **Thiết lập** trên một lát ở tab **Khám phá**.

### <a name="allow-contributors-to-use-a-connection-for-exports"></a>Cho phép người đóng góp sử dụng một kết nối cho các lần xuất

Khi thiết lập hoặc chỉnh sửa kết nối xuất, bạn hãy chọn người dùng nào được phép sử dụng kết nối cụ thể này để xác định [các nội dung xuất](export-destinations.md). Theo mặc định, một kết nối có sẵn cho người dùng có vai trò quản trị viên. Bạn có thể thay đổi thiết đặt này trong **Chọn người có thể sử dụng kết nối này** và cho phép người dùng có vai trò người đóng góp sử dụng kết nối này.

- Những người đóng góp sẽ không thể xem hoặc chỉnh sửa kết nối. Họ sẽ chỉ thấy tên hiển thị và loại kết nối khi tạo một nội dung xuất.
- Bằng cách chia sẻ kết nối, bạn cho phép những người đóng góp sử dụng kết nối. Những người đóng góp sẽ thấy các kết nối được chia sẻ khi họ thiết lập chế độ xuất. Họ có thể quản lý mọi lần xuất sử dụng kết nối cụ thể này.
- Bạn có thể thay đổi thiết đặt này trong khi vẫn giữ nội dung xuất đo những người đóng góp xác định.

## <a name="edit-a-connection"></a>Chỉnh sửa kết nối

1. Đi đến **Quản trị viên** > **Kết nối (bản xem trước)**.

1. Đi đến tab **Kết nối**.

1. Chọn dấu ba chấm dọc cho kết nối mà bạn muốn chỉnh sửa.

1. Chọn **Chỉnh sửa**.

1. Thay đổi các giá trị mà bạn muốn cập nhật rồi chọn **Lưu**.

## <a name="remove-a-connection"></a>Loại bỏ kết nối

Nếu kết nối mà bạn đang loại bỏ được dùng cho các nội dung bổ sung hoặc nội dung xuất, thì trước tiên, bạn cần gỡ bỏ hoặc loại bỏ các nội dung bổ sung hoặc nội dung xuất đó. Hộp thoại loại bỏ sẽ hướng dẫn bạn chuyển đến các nội dung bổ sung hoặc nội dung xuất có liên quan. 

Các nội dung bổ sung và nội dung xuất đã gỡ bỏ chuyển sang chế độ không hoạt động. Bạn hãy kích hoạt lại các nội dung bổ sung và nội dung xuất đã gỡ bỏ bằng cách thêm một kết nối khác vào chúng trên trang [Nội dung bổ sung](enrichment-hub.md) hoặc [Nội dung xuất](export-destinations.md).

1. Đi đến **Quản trị viên** > **Kết nối (bản xem trước)**.

1. Đi đến tab **Kết nối**.

1. Chọn dấu ba chấm dọc cho kết nối mà bạn muốn loại bỏ.

1. Chọn **Xóa** trong menu thả xuống. Một hộp thoại xác nhận sẽ xuất hiện.

   1. Nếu có các nội dung bổ sung hoặc nội dung xuất sử dụng kết nối này, hãy chọn nút để xem những gì đang sử dụng kết nối.
      - **Nội dung xuất:** Bạn có thể chọn loại bỏ hoặc ngắt kết nối các nội dung xuất để có thể loại bỏ kết nối. Để ngắt kết nối nội dung xuất, quản trị viên có thể sử dụng thao tác **Ngắt kết nối**. Hành động này có thể áp dụng cho từng nội dung xuất và nhiều nội dung xuất đã chọn. Bằng cách ngắt kết nối, bạn vẫn giữ được cấu hình xuất, nhưng cấu hình này sẽ không chạy cho đến khi bạn thêm một kết nối khác.
      - **Phiên tăng cường:** Bạn có thể chọn loại bỏ hoặc vô hiệu hóa các nội dung bổ sung để có thể loại bỏ kết nối. 
   1. Khi kết nối không còn thành phần phụ thuộc nữa, hãy quay lại **Quản trị viên** > **Kết nối** và thử loại bỏ kết nối một lần nữa.

1. Để xác nhận xóa, hãy chọn **Loại bỏ**.

## <a name="set-up-connections-with-secrets-managed-by-your-own-key-vault"></a>Thiết lập kết nối với các bí mật do Key Vault của riêng bạn quản lý

Một số kết nối cần bí mật như khóa API hoặc mật khẩu. Một số kết nối hỗ trợ bí mật được lưu trữ trong Key Vault của riêng bạn. Tìm hiểu thêm về các kết nối được hỗ trợ và cách thiết lập trên [Key Vault của riêng bạn để có thông tin chi tiết về đối tượng](use-azure-key-vault.md).
