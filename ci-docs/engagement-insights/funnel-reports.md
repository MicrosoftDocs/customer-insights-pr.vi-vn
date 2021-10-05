---
title: Báo cáo phễu
description: Cách sử dụng báo cáo phễu để hiểu cách đối tượng đưa ra quyết định.
ms.reviewer: mhart
ms.author: kamacdon
author: kamacdon
ms.date: 09/21/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: efb10f2664630a5851d9582ff09c378c01777b96
ms.sourcegitcommit: f1e3cc51ea4cf68210eaf0210ad6e14b15ac4fe8
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 09/27/2021
ms.locfileid: "7558968"
---
# <a name="create-and-manage-funnel-reports"></a>Tạo và quản lý báo cáo phễu

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Báo cáo phễu thu thập thông tin về các bước diễn ra trong hành trình của khách hàng thông qua trang web hoặc ứng dụng dành cho thiết bị di động của bạn. Báo cáo giúp bạn hiểu về tiến trình của đối tượng thông qua quá trình và xác định các điểm dừng. Ví dụ: bạn có thể sử dụng báo cáo phễu để xác định hành trình của khách hàng trước khi họ mua hàng. Báo cáo phễu cung cấp dữ liệu để thông báo về quyết định và xác định các khu vực để tối ưu hóa cũng như cải tiến quy trình.

## <a name="create-a-funnel-report"></a>Tạo báo cáo phễu

Để tạo báo cáo phễu, hãy chỉ định các bước bạn muốn thực hiện và hoạt động cho mỗi bước. Hoạt động là một [sự kiện](glossary.md) đại diện cho hành vi của người dùng. Báo cáo phễu hiển thị số lượng người dùng đã hoàn thành từng bước được xác định. 

1. Chuyển đến **Phễu** và chọn **+ Phễu mới** để bắt đầu báo cáo phễu.

1. Trong **Trình chỉnh sửa phễu**, dưới phần **Các bước**, hãy chọn **+ Thêm bước.** 

1. Nhập tên trong phần **Tiêu đề bước**.

   :::image type="content" source="media/new-funnel-report.png" alt-text="Báo cáo phễu mới.":::

1. Chọn một **Hoạt động**. Hoạt động ghi lại khi người dùng xem một trang (hoạt động **Xem**) hoặc tương tác với nội dung (hoạt động **Hành động**).

1. Sử dụng **Tiêu chí bước** để chỉ định thứ nguyên của hoạt động. [Thứ nguyên](dimensions.md) là các thuộc tính có thể mô tả, lọc hoặc nhóm dữ liệu.

1. Bạn có thể tùy ý đặt cấu hình các bước phễu nhiều điều kiện. Chọn **Thêm điều kiện** để chỉ định nhiều thứ nguyên trong một bước. Các tiêu chí bổ sung phải sử dụng cùng một loại hoạt động. Bạn có thể chọn nếu có nhiều điều kiện được kết nối bằng toán tử AND hoặc OR.

   :::image type="content" source="media/funnel-add-condition.png" alt-text="Trình chỉnh sửa phễu hiển thị cấu hình bước với các bước nhiều điều kiện.":::

1. Chọn **Thêm bước** cho đến khi bạn hoàn thành tất cả các bước mong muốn trong báo cáo.

1. Chọn **Lưu**, đặt tên cho báo cáo và **Lưu** lần nữa. 

### <a name="example-fourth-coffee-company-funnel-report"></a>Ví dụ: Báo cáo phễu của công ty Fourth Coffee

Tình huống sau đây trình bày một cách sử dụng báo cáo phễu. Một nhà phân tích của công ty Fourth Coffee muốn tìm hiểu tác động của chương trình khuyến mãi gần đây đối với tỷ lệ đăng ký. Nhà phân tích này tạo báo cáo phễu để xác định hoạt động của khách hàng. Quá trình này bắt đầu từ khi khách hàng truy cập vào trang chủ của công ty cho đến khi họ sử dụng mã khuyến mãi đăng ký. Nhà phân tích tạo báo cáo phễu với các bước sau:

Bước 1: Khách hàng truy cập trang chủ   
Bước 2: Khách hàng mua hàng   
Bước 3: Khách hàng sử dụng mã khuyến mãi để được giảm giá đăng ký   
Bước 4: Đăng ký dùng gói đăng ký   

:::image type="content" source="media/funnel-report-example.png" alt-text="ví dụ về báo cáo phễu.":::
  
Phễu này cho phép bạn xem số lượng người dùng đã sử dụng mã khuyến mãi sau khi mua một lần để đăng ký chương trình đăng ký.

### <a name="configure-advanced-settings"></a>Đặt cấu hình thiết đặt nâng cao 

Báo cáo phễu cho phép bạn xác định giới hạn về thời gian cần để hoàn thành một phễu. Ví dụ: bạn có thể đặt thời gian để hoàn thành phễu là 4 ngày. Tùy chọn thiết đặt này sẽ chỉ tính những lượt đăng ký thành công xảy ra trong vòng 4 ngày kể từ khi người dùng truy cập vào trang chủ.

1. Chuyển đến **Phễu** để mở **Thư viện phễu**.

1. Chọn tên để mở báo cáo. 

1. Trong ngăn **Trình chỉnh sửa phễu**, hãy chọn **Thiết đặt nâng cao**. 

1. Đặt tùy chọn Giới hạn thời gian hoàn thành phễu thành **Bật**.

   :::image type="content" source="media/funnel-limit-time.png" alt-text="Trình chỉnh sửa phễu hiển thị phần thiết đặt nâng cao và các tùy chọn để giới hạn thời gian hoàn thành phễu.":::

1. Chọn thời gian phễu phải được hoàn thành trong danh sách thả xuống của phần **Đặt giới hạn thành**.

1. Chọn **Lưu** để áp dụng thay đổi.


## <a name="cross-channel-funnel-reports"></a>Báo cáo phễu đa kênh 

Thông tin chi tiết về tương tác cũng có thể thu thập dữ liệu hành vi của khách hàng trên ứng dụng dành cho thiết bị di động của bạn. Sau khi trang bị cho ứng dụng dành cho thiết bị di động của mình bằng thông tin chi tiết về tương tác [SDK Android](get-started-android.md) hoặc [SDK iOS](get-started-ios.md), bạn có thể tạo báo cáo phễu đa kênh. 

### <a name="create-a-cross-channel-funnel-report"></a>Tạo báo cáo phễu đa kênh 

1. Làm theo các bước để [tạo báo cáo phễu](#create-a-funnel-report).    

1. Để theo dõi cách khách hàng tương tác với thương hiệu của bạn trên cả trang web lẫn ứng dụng dành cho thiết bị di động hoặc nhiều trang web, hãy sử dụng trình chuyển đổi không gian làm việc để tạo các bước phễu bằng dữ liệu từ không gian làm việc khác. Trong **Trình chỉnh sửa phễu**, ở phần **Các bước**, chọn không gian làm việc chứa dữ liệu cần thu thập cho bước phễu của bạn.

## <a name="manage-funnel-reports"></a>Quản lý báo cáo phễu

Bạn có thể xem lại báo cáo phễu để phân tích dữ liệu, theo dõi hiệu suất và thu thập thông tin chi tiết.

> [!NOTE]
> - Báo cáo phễu thông tin chi tiết về tương tác hiện hỗ trợ các tình huống trong đó tất cả người dùng trong phễu đều ẩn danh hoặc tất cả người dùng đều được xác thực. 
> - Dữ liệu lịch sử trong báo cáo phễu có sẵn trong 30 ngày qua.

### <a name="view-funnel-reports"></a>Xem báo cáo phễu

1. Chuyển đến **Phễu** để mở **Thư viện phễu**.
1. Chọn tên để mở báo cáo.    

### <a name="see-the-data-collected-for-a-report"></a>Xem dữ liệu được thu thập cho một báo cáo   

Để xem thông tin về một giai đoạn

- Trỏ đến một bước trong báo cáo.

:::image type="content" source="media/funnel-step-data.png" alt-text="dữ liệu phễu.":::

### <a name="change-the-date-range-for-the-funnel-report"></a>Thay đổi phạm vi ngày cho báo cáo phễu

1. Chuyển đến **Phễu** để mở **Thư viện phễu**.

1. Chọn tên để mở báo cáo.

1. Mở phần **phạm vi thời gian** và chọn một khoảng thời gian mới từ danh sách hoặc **Phạm vi ngày cố định** để chỉ định một phạm vi ngày.

## <a name="edit-or-delete-funnel-reports"></a>Chỉnh sửa hoặc xóa báo cáo phễu

Bạn có thể thay đổi tên của báo cáo phễu, xóa hoặc sửa đổi các bước trong báo cáo.

### <a name="rename-or-delete-a-funnel-report"></a>Đổi tên hoặc xóa báo cáo phễu

1. Chuyển đến **Phễu** để mở **Thư viện phễu**. 

1. Chọn **Thêm** bên cạnh báo cáo bạn muốn thay đổi và chọn **Chỉnh sửa tên** hoặc là **Xóa**.

### <a name="edit-a-funnel-step"></a>Chỉnh sửa bước phễu  

1. Chuyển đến **Phễu** để mở **Thư viện phễu**. 

1. Chọn tên để mở báo cáo.

1. Chọn bước bạn muốn chỉnh sửa.

1. Chọn **Chỉnh sửa**.

1. Bên trong **Trình chỉnh sửa phễu**, hãy cập nhật thông tin bạn muốn thay đổi.  

1. Chọn **Lưu**.

### <a name="reorder-a-funnel-step"></a>Sắp xếp lại bước phễu

1. Chuyển đến **Phễu** để mở **Thư viện phễu**. 

1. Chọn tên để mở báo cáo.

1. Chọn bước bạn muốn sắp xếp lại.

1. Chọn **Di chuyển** rồi chọn **Lên trên**, **Xuống dưới**, **Lên đầu trang** hoặc **Xuống dưới cùng** để di chuyển bước.

### <a name="delete-a-funnel-step"></a>Xóa bước phễu

1. Chuyển đến **Phễu** để mở **Thư viện phễu**. 

1. Chọn tên để mở báo cáo.

1. Chọn bước bạn muốn xóa rồi chọn **Xóa**.

## <a name="funnel-insights"></a>Thông tin chi tiết về phễu 

Thông tin chi tiết về mức độ tương tác hiện cung cấp thông tin chi tiết về phễu cho khách hàng. Sử dụng thông tin chi tiết về phễu để hiểu sâu hơn về hành vi của khách hàng về các bước trong báo cáo phễu của bạn. Khi bạn tạo và lưu báo cáo phễu mới, thông tin chi tiết về phễu sẽ tự động được tạo cho báo cáo của bạn. 

:::image type="content" source="media/funnel-insights.png" alt-text="Thông tin chi tiết về phễu.":::

> [!NOTE]
> Chỉ có thể tạo thông tin chi tiết về phễu cho các bước trong phễu **không** bao gồm các kích thước tùy chỉnh. Để tạo thông tin chi tiết về phễu cho tất cả các bước trong phễu của bạn, hãy sử dụng các thứ nguyên có thể dùng được ngay của thông tin chi tiết về tương tác để tạo các bước trong phễu của bạn. 

Bạn có thể xem thông tin chi tiết về phễu từ các danh mục sau, ở cả cấp độ chính và cấp độ bước: 

 - Tỉ lệ chuyển đổi
 -    Tỷ lệ chuyển đổi từ Thanh toán đến Mua là 22%.
 - Thời gian chuyển tiếp 
 -    Thời gian chuyển tiếp trung bình từ Giỏ hàng đến Thanh toán là 23 phút. 
 - Thời gian hoàn thành 
 -    Lượng thời gian trung bình mà khách hàng cần để hoàn thành phễu là 47 phút. 

Sử dụng những thông tin chi tiết này để khám phá sâu hơn về hành vi của khách hàng cũng như hiểu rõ hơn về các điểm giảm và chuyển đổi cho báo cáo phễu của bạn. 

Để so sánh thông tin chi tiết qua các bước khác nhau, hãy chọn **Xem phân tích bước** hoặc **So sánh với các bước khác** từ thẻ thông tin chi tiết. Những thẻ này sẽ hiển thị biểu đồ thanh so sánh số liệu của từng bước trong phễu. 

Thông tin chi tiết về phễu được tính toán lại sau mỗi 24 giờ hoặc khi bạn **Lưu** báo cáo phễu của bạn. 

> [!NOTE]
> Để xem thông tin chi tiết cho phễu của bạn, bạn phải lưu báo cáo của mình mỗi khi bạn thực hiện các thay đổi. 

