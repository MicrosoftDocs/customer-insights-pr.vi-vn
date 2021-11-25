---
title: Yêu cầu theo Quyền của chủ thể dữ liệu (DSR) phù hợp với GDPR | Microsoft Docs
description: Trả lời Yêu cầu về chủ đề dữ liệu để có khả năng thông tin chi tiết về đối tượng Dynamics 365 Customer Insights.
ms.date: 08/11/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: c116f7ce208c0288851a4b2230e27784ba3a5337
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732706"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Yêu cầu theo Quyền của chủ thể dữ liệu (DSR) phù hợp với GDPR

Quy định Chung về Bảo vệ Dữ liệu (GDPR) của Liên minh Châu Âu đã có hiệu lực kể từ ngày 25 tháng 5 năm 2018. Quy định này cung cấp các quyền quan trọng cho các cá nhân liên quan đến dữ liệu của họ. GDPR là quy định về việc bảo vệ và cho phép các quyền riêng tư của các cá nhân. Bạn có thể đọc thêm về cam kết của Microsoft về vấn đề bảo mật và tuân thủ tại [Trung tâm Tin cậy của Microsoft](https://www.microsoft.com/trust-center).

Chúng tôi cam kết giúp khách hàng của mình đáp ứng các yêu cầu về GDPR của họ. Chức năng này bao gồm quyền xóa và xuất dữ liệu có chứa thông tin cá nhân như ID người dùng, số điện thoại và địa chỉ email. Quản trị viên có thể thực hiện các yêu cầu của người dùng để xóa hoặc xuất dữ liệu cá nhân.

## <a name="audience-insights"></a>Thông tin chuyên sâu về đối tượng

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a>Đáp ứng yêu cầu xóa chủ đề dữ liệu GDPR cho khả năng thông tin chi tiết về đối tượng Dynamics 365 Customer Insights

"Quyền xóa" dữ liệu cá nhân khỏi dữ liệu khách hàng của tổ chức là sự bảo vệ chính trong Quy định Chung về Bảo vệ Dữ liệu (GDPR). Việc xóa dữ liệu cá nhân bao gồm xóa tất cả dữ liệu cá nhân và nhật ký do hệ thống tạo, ngoại trừ thông tin nhật ký kiểm tra.

#### <a name="manage-data-subject-delete-requests"></a>Quản lý yêu cầu xóa của chủ thể dữ liệu

Thông tin chi tiết về đối tượng cung cấp những trải nghiệm trong sản phẩm sau để xóa dữ liệu cá nhân cho một khách hàng hoặc người dùng cụ thể:

- **Quản lý yêu cầu xóa đối với dữ liệu khách hàng**: Dữ liệu khách hàng trong Customer Insights được nhập từ các nguồn dữ liệu ban đầu bên ngoài Customer Insights. Tất cả yêu cầu xóa theo GDPR phải được thực hiện trong nguồn dữ liệu gốc.
- **Quản lý yêu cầu xóa đối với dữ liệu người dùng Customer Insights**: Dữ liệu cho người dùng được tạo bởi Customer Insights. Tất cả yêu cầu xóa GDPR phải được thực hiện trong Customer Insights.

##### <a name="manage-requests-to-delete-customer-data"></a>Quản lý yêu cầu xóa dữ liệu khách hàng

Quản trị viên Customer Insights có thể làm theo các bước sau để xóa dữ liệu khách hàng đã bị xóa trong nguồn dữ liệu:

1. đăng nhập vào Dynamics 365 Customer Insights.
2. Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Dữ liệu** > **Nguồn dữ liệu**
3. Đối với từng nguồn dữ liệu trong danh sách chứa dữ liệu khách hàng đã xóa:
   1. Chọn (...) rồi chọn **Làm mới**.
   2. Kiểm tra trạng thái nguồn dữ liệu trong **Trạng thái**. Một dấu kiểm có nghĩa là làm mới đã thành công. Một tam giác cảnh báo có nghĩa là đã có vấn đề. Nếu hình tam giác cảnh báo được hiển thị, hãy liên hệ với D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![Xử lý yêu cầu xóa dữ liệu khách hàng theo GDPR.](audience-insights/media/gdpr-data-sources.png "Xử lý yêu cầu xóa dữ liệu khách hàng theo GDPR")

##### <a name="manage-delete-requests-for-user-data"></a>Quản lý yêu cầu xóa dữ liệu người dùng

Quản trị viên Customer Insights có thể làm theo các bước sau để xóa dữ liệu người dùng Customer Insights:

1. đăng nhập vào Dynamics 365 Customer Insights.
2. Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Quản trị** > **Quyền**.
3. Chọn hộp kiểm tương ứng với người dùng bạn muốn xóa.
4. Chọn **Loại bỏ**.

### <a name="responding-to-gdpr-data-subject-export-requests"></a>Trả lời yêu cầu xuất của chủ thể dữ liệu theo GDPR

Là một phần trong cam kết của chúng tôi để hợp tác với bạn trên hành trình của bạn theo Quy định chung về bảo vệ dữ liệu (GDPR), chúng tôi đã phát triển tài liệu để giúp bạn chuẩn bị. Tài liệu này mô tả các bước bạn có thể thực hiện ngay hôm nay để hỗ trợ tuân thủ GDPR khi sử dụng thông tin chi tiết về đối tượng.

#### <a name="manage-export-and-view-requests"></a>Quản lý các yêu cầu xuất và xem

Quyền chuyển đổi dữ liệu cho phép chủ thể dữ liệu yêu cầu lấy bản sao dữ liệu cá nhân của họ ở định dạng điện tử ("định dạng có cấu trúc, thường dùng, có thể đọc được bằng máy và có thể tương tác") có thể được truyền đến đơn vị kiểm soát dữ liệu khác.

##### <a name="export-customer-data-tenant-admin"></a>Xuất dữ liệu khách hàng (quản trị viên đối tượng thuê)

Quản trị viên đối tượng thuê có thể tuân theo các bước sau để xuất dữ liệu:

1. Gửi email tới D365CI@microsoft.com cho biết địa chỉ email của khách hàng trong yêu cầu. Nhóm Customer Insights sẽ gửi email đến địa chỉ email quản trị viên đối tượng thuê đã đăng ký, yêu cầu xác nhận để xuất dữ liệu.
2. Hãy xác minh để xuất dữ liệu cho khách hàng yêu cầu.
3. Nhận dữ liệu được xuất thông qua địa chỉ email quản trị viên đối tượng thuê.

##### <a name="export-user-data-tenant-admin"></a>Xuất dữ liệu người dùng (quản trị viên đối tượng thuê)

1. Gửi email tới D365CI@microsoft.com cho biết địa chỉ email của người dùng trong yêu cầu. Nhóm Customer Insights sẽ gửi email đến địa chỉ email quản trị viên đối tượng thuê đã đăng ký, yêu cầu xác nhận để xuất dữ liệu.
2. Hãy xác minh để xuất dữ liệu cho người dùng yêu cầu.
3. Nhận dữ liệu được xuất thông qua địa chỉ email quản trị viên đối tượng thuê.

## <a name="consent-management-preview"></a>Quản lý sự đồng ý (xem trước)

Khả năng quản lý sự đồng ý không trực tiếp thu thập dữ liệu người dùng. Nó chỉ nhập và xử lý dữ liệu về sự đồng ý do người dùng cung cấp trong các ứng dụng khác.

Để xóa dữ liệu về sự đồng ý về những người dùng cụ thể, hãy xóa dữ liệu đó trong các nguồn dữ liệu được nhập vào khả năng quản lý sự đồng ý. Sau khi làm mới nguồn dữ liệu, dữ liệu đã xóa cũng sẽ bị xóa trong Trung tâm đồng ý. Các ứng dụng sử dụng pháp nhân đồng ý cũng sẽ xóa dữ liệu đã bị xóa trên nguồn sau [Làm tươi](audience-insights/system.md#refresh-processes). Chúng tôi khuyên bạn nên nhanh chóng làm mới nguồn dữ liệu sau khi phản hồi yêu cầu chủ thể dữ liệu để xóa dữ liệu của người dùng khỏi tất cả các quy trình và ứng dụng khác.


## <a name="engagement-insights-preview"></a>Thông tin chuyên sâu về tương tác (bản xem trước)

### <a name="deleting-and-exporting-event-data-containing-end-user-identifiable-information"></a>Xóa và xuất dữ liệu sự kiện có chứa thông tin nhận dạng người dùng cuối

Các phần sau đây mô tả cách xóa và xuất dữ liệu sự kiện có thể chứa dữ liệu cá nhân.

Để xóa hoặc xuất dữ liệu:

1. Gắn thẻ các thuộc tính sự kiện có chứa dữ liệu với thông tin cá nhân.
2. Xóa hoặc xuất dữ liệu được liên kết với các giá trị cụ thể (ví dụ: ID người dùng được chỉ định).

#### <a name="tag-and-update-event-properties"></a>Gắn thẻ và cập nhật thuộc tính sự kiện

Dữ liệu cá nhân được gắn thẻ ở cấp độ thuộc tính sự kiện. Trước tiên, hãy gắn thẻ các thuộc tính đang được xem xét để xóa hoặc xuất.

Để gắn thẻ thuộc tính sự kiện vì có chứa thông tin cá nhân, hãy làm theo các bước sau:

1. Mở không gian làm việc có chứa sự kiện.

1. Chuyển đến **Dữ liệu** > **Sự kiện** để xem danh sách các sự kiện trong không gian làm việc đã chọn.
  
1. Chọn sự kiện bạn muốn gắn thẻ.

1. Chọn **Chỉnh sửa thuộc tính** để mở ngăn danh sách có chứa tất cả các thuộc tính của sự kiện đã chọn.
     
1. Chọn **...** rồi chọn **Chỉnh sửa** để truy cập hộp thoại **Cập nhật thuộc tính**.

   ![Chỉnh sửa sự kiện.](engagement-insights/media/edit-event.png "Chỉnh sửa sự kiện")

1. Trong cửa sổ **Cập nhật thuộc tính**, hãy chọn **...** ở góc trên bên phải rồi chọn hộp **Chứa EUII**. Chọn **Cập nhật** để lưu thay đổi của bạn.

   ![Lưu thay đổi của bạn.](engagement-insights/media/update-property.png "Lưu thay đổi của bạn")

   > [!NOTE]
   > Mỗi khi lược đồ sự kiện thay đổi hoặc bạn tạo một sự kiện mới, bạn nên đánh giá các thuộc tính sự kiện được liên kết và gắn thẻ hoặc bỏ gắn thẻ là chứa dữ liệu cá nhân, nếu cần.

#### <a name="delete-or-export-tagged-event-data"></a>Xóa hoặc xuất dữ liệu sự kiện được gắn thẻ

Nếu tất cả các thuộc tính sự kiện đã được gắn thẻ thích hợp như được mô tả trong bước trước đó, quản trị viên môi trường có thể đưa ra yêu cầu xóa đối với dữ liệu sự kiện được gắn thẻ.

Để quản lý các yêu cầu xóa hoặc xuất EUII

1. Chuyển đến **Quản trị viên** > **Môi trường** > **Cài đặt**.

1. Trong phần **Quản lý thông tin nhận dạng người dùng cuối (EUII)**, hãy chọn **Quản lý EUII**.

##### <a name="deletion"></a>Thao tác xóa

Để xóa, bạn có thể nhập danh sách ID người dùng được phân tách bằng dấu phẩy trong phần **Xóa thông tin nhận dạng người dùng cuối (EUII)**. Các ID này sau đó sẽ được so sánh với tất cả các thuộc tính sự kiện đã gắn thẻ của mọi dự án trong môi trường hiện tại thông qua so khớp chuỗi chính xác. 

Nếu giá trị thuộc tính khớp với một trong các ID được cung cấp, thì sự kiện được liên kết sẽ bị xóa vĩnh viễn. Do không thể thay đổi tác vụ này, bạn phải xác nhận việc xóa sau khi chọn **Xóa**.

##### <a name="export"></a>Xuất

Quá trình xuất giống với quá trình xóa khi nói đến việc xác định các giá trị thuộc tính sự kiện trong phần **Xuất thông tin nhận dạng người dùng cuối (EUII)**. Ngoài ra, bạn sẽ cần cung cấp **URL lưu trữ Azure blob** để chỉ định đích xuất. URL Azure Blob phải bao gồm [Chữ ký truy cập được chia sẻ (SAS)](/azure/storage/common/storage-sas-overview).

Sau khi chọn **Xuất**, tất cả các sự kiện của nhóm hiện tại chứa các thuộc tính được gắn thẻ phù hợp sẽ được xuất ở định dạng CSV đến đích xuất.

### <a name="good-practices"></a>Biện pháp hiệu quả

* Cố gắng tránh gửi bất kỳ sự kiện nào chứa dữ liệu cá nhân.
* Nếu bạn cần gửi sự kiện chứa dữ liệu EUII, hãy giới hạn số lượng sự kiện và thuộc tính sự kiện có chứa dữ liệu EUII. Tốt nhất, bạn nên hạn chế tham gia vào một sự kiện như vậy.
* Đảm bảo rằng số người có quyền truy cập vào dữ liệu cá nhân đã gửi là ít nhất có thể.
* Đối với các sự kiện có chứa dữ liệu cá nhân, hãy đảm bảo rằng bạn đặt một thuộc tính để tạo ra số nhận dạng duy nhất có thể dễ dàng được liên kết với một người dùng cụ thể (ví dụ: ID người dùng). Biện pháp này giúp dễ dàng tách dữ liệu và xuất hoặc xóa dữ liệu phù hợp.
* Chỉ gắn thẻ một thuộc tính cho mỗi sự kiện là chứa dữ liệu cá nhân. Tốt nhất là chỉ chứa một mã định danh duy nhất.
* Không gắn thẻ các thuộc tính chứa giá trị diễn giải (ví dụ: toàn bộ nội dung yêu cầu). Chức năng năng thông tin chi tiết về tương tác sử dụng so khớp chuỗi chính xác khi quyết định xóa hoặc xuất sự kiện nào.

[!INCLUDE[footer-include](includes/footer-banner.md)]