---
title: Mối quan hệ giữa các thực thể và đường dẫn thực thể
description: Tạo và quản lý mối quan hệ giữa các thực thể từ nhiều nguồn dữ liệu.
ms.date: 06/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: d5b9566ec88096fec31d8e164a51598159ec26d4
ms.sourcegitcommit: ece48f80a7b470fb33cd36e3096b4f1e9190433a
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 06/03/2021
ms.locfileid: "6171190"
---
# <a name="relationships-between-entities"></a>Mối quan hệ giữa các thực thể

Mối quan hệ kết nối các thực thể và xác định một biểu đồ dữ liệu của bạn khi các thực thể có cùng một khóa ngoại, mã định danh chung. Khóa ngoại này có thể được tham chiếu từ thực thể này sang thực thể khác. Các thực thể được kết nối cho phép bạn xác định các phân khúc và giá trị đo dựa trên nhiều nguồn dữ liệu.

Có 3 loại mối quan hệ: 
- Mối quan hệ hệ thống không thể chỉnh sửa, do hệ thống tạo trong quá trình hợp nhất dữ liệu
- Mối quan hệ kế thừa không thể chỉnh sửa, được tạo tự động từ quá trình nhập nguồn dữ liệu 
- Mối quan hệ tùy chỉnh có thể chỉnh sửa, do người dùng tạo và đặt cấu hình

## <a name="non-editable-system-relationships"></a>Mối quan hệ hệ thống không thể chỉnh sửa

Trong quá trình hợp nhất dữ liệu, các mối quan hệ hệ thống được tạo tự động dựa trên tính năng kết hợp thông minh. Các mối quan hệ này giúp liên kết bản ghi hồ sơ khách hàng với bản ghi tương ứng. Sơ đồ sau minh họa quá trình tạo ra 3 mối quan hệ dựa trên hệ thống. Thực thể khách hàng được kết hợp với các thực thể khác để tạo ra thực thể *Customer* hợp nhất.

:::image type="content" source="media/relationships-entities-merge.png" alt-text="Sơ đồ với các đường dẫn mối quan hệ cho thực thể khách hàng với 3 mối quan hệ 1-n.":::

- **Mối quan hệ *CustomerToContact*** được tạo giữa thực thể *Customer* và *Contact*. Thực thể *Customer* lấy trường khóa **Contact_contactID** để liên kết với trường khóa **contactID** của thực thể *Contact*.
- **Mối quan hệ *CustomerToAccount*** được tạo giữa thực thể *Customer* và thực thể *Account*. Thực thể *Customer* lấy trường khóa **Account_accountID** để liên kết với trường khóa **accountID** của thực thể *Account*.
- **Mối quan hệ *CustomerToWebAccount*** được tạo giữa thực thể *Customer* và thực thể *WebAccount*. Thực thể *Customer* lấy trường khóa **WebAccount_webaccountID** để liên kết với trường khóa **webaccountID** của thực thể *WebAccount*.

## <a name="non-editable-inherited-relationships"></a>Mối quan hệ kế thừa không thể chỉnh sửa

Trong quá trình nhập dữ liệu, hệ thống sẽ kiểm tra nguồn dữ liệu để tìm các mối quan hệ hiện có. Nếu không có mối quan hệ nào tồn tại, hệ thống sẽ tự động tạo. Các mối quan hệ này cũng dùng trong các quy trình xuôi tuyến.

## <a name="create-a-custom-relationship"></a>Tạo mối quan hệ tùy chỉnh

Mối quan hệ bao gồm một *thực thể nguồn* chứa khóa ngoại và một *thực thể đích* mà khóa ngoại của thực thể nguồn trỏ đến. 

1. Trong thông tin chuyên sâu về đối tượng, hãy chuyển đến **Dữ liệu** > **Mối quan hệ**.

2. Chọn **Mối quan hệ mới**.

3. Trong ngăn **Mối quan hệ mới**, hãy cung cấp các thông tin sau:

   :::image type="content" source="media/relationship-add.png" alt-text="Ngăn bên Mối quan hệ mới với các trường nhập dữ liệu trống.":::

   - **Tên mối quan hệ**: Tên phản ánh mục đích của mối quan hệ. Ví dụ: CustomerToSupportCase.
   - **Mô tả**: Mô tả về mối quan hệ.
   - **Thực thể nguồn**: Thực thể dùng làm nguồn trong mối quan hệ. Ví dụ: SupportCase.
   - **Thực thể đích**: Thực thể dùng làm đích trong mối quan hệ. Ví dụ: Customer.
   - **Lượng số nguồn**: Chỉ định lượng số của thực thể nguồn. Lượng số mô tả số phần tử có thể có trong một tập hợp. Lượng số nguồn luôn liên quan đến lượng số đích. Bạn có thể chọn giữa **Một** và **Nhiều**. Chỉ hỗ trợ các mối quan hệ nhiều-một và một-một.  
     - Nhiều-một: Nhiều bản ghi nguồn có thể liên kết với một bản ghi đích. Ví dụ: Nhiều trường hợp hỗ trợ từ một khách hàng.
     - Một-một: Một bản ghi nguồn liên kết với một bản ghi đích. Ví dụ: Một ID khách hàng thân thiết cho một khách hàng.

     > [!NOTE]
     > Bạn có thể tạo mối quan hệ nhiều-nhiều bằng cách sử dụng 2 mối quan hệ nhiều-một và một thực thể liên kết, kết nối thực thể nguồn và thực thể đích.

   - **Lượng số đích**: Chọn lượng số của các bản ghi thực thể đích. 
   - **Trường khóa nguồn**: Trường khóa ngoại trong thực thể nguồn. Ví dụ: SupportCase có thể sử dụng CaseID làm trường khóa ngoại.
   - **Trường khóa đích**: Trường khóa của thực thể đích. Ví dụ: Thực thể Customer có thể sử dụng trường khóa **CustomerID**.

4. Chọn **Lưu** để tạo mối quan hệ tùy chỉnh.

## <a name="view-relationships"></a>Xem mối quan hệ

Trang Mối quan hệ liệt kê tất cả các mối quan hệ đã được tạo. Mỗi hàng đại diện cho một mối quan hệ, cũng bao gồm thông tin chi tiết về thực thể nguồn, thực thể đích và lượng số. 

:::image type="content" source="media/relationships-list.png" alt-text="Danh sách các mối quan hệ và tùy chọn trong thanh tác vụ của trang Mối quan hệ.":::

Trang này cung cấp một bộ tùy chọn cho các mối quan hệ hiện có và mới: 
- **Mối quan hệ mới**: [Tạo mối quan hệ tùy chỉnh](#create-a-custom-relationship).
- **Trình hiển thị**: [Khám phá trình hiển thị mối quan hệ](#explore-the-relationship-visualizer) để xem sơ đồ mạng lưới của các mối quan hệ hiện có và lượng số của chúng.
- **Lọc theo**: Chọn loại mối quan hệ để hiển thị trong danh sách.
- **Tìm kiếm mối quan hệ**: Sử dụng chức năng tìm kiếm dựa trên văn bản trên các thuộc tính của mối quan hệ.

### <a name="explore-the-relationship-visualizer"></a>Khám phá trình hiển thị mối quan hệ

Trình hiển thị mối quan hệ hiển thị sơ đồ mạng lưới của các mối quan hệ hiện có giữa các thực thể được kết nối và lượng số của chúng.

Để tùy chỉnh dạng xem này, bạn có thể thay đổi vị trí của các hộp bằng cách kéo chúng trên canvas.

:::image type="content" source="media/relationship-visualizer.png" alt-text="Ảnh chụp màn hình sơ đồ mạng lưới của trình hiển thị mối quan hệ với các kết nối giữa các thực thể liên quan.":::

Các tùy chọn có thể dùng: 
- **Xuất dưới dạng hình ảnh**: Lưu dạng xem hiện tại dưới dạng tệp hình ảnh.
- **Thay đổi thành bố cục ngang/dọc**: Thay đổi hướng của các thực thể và mối quan hệ.
- **Chỉnh sửa**: Cập nhật các thuộc tính của mối quan hệ tùy chỉnh trong ngăn chỉnh sửa và lưu các thay đổi.

## <a name="manage-existing-relationships"></a>Quản lý mối quan hệ hiện có 

Trên trang Mối quan hệ, mỗi mối quan hệ được thể hiện bằng một hàng. 

Chọn một mối quan hệ rồi chọn một trong các tùy chọn sau: 
 
- **Chỉnh sửa**: Cập nhật các thuộc tính của mối quan hệ tùy chỉnh trong ngăn chỉnh sửa và lưu các thay đổi.
- **Xóa**: Xóa mối quan hệ tùy chỉnh.
- **Xem**: Xem mối quan hệ do hệ thống tạo và mối quan hệ kế thừa. 

## <a name="next-step"></a>Bước tiếp theo

Các mối quan hệ tùy chỉnh và hệ thống dùng để [tạo phân khúc](segments.md) dựa trên nhiều nguồn dữ liệu không còn lưu trữ theo dạng silo.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
