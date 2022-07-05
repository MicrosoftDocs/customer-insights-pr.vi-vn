---
title: Hoàn thành một phần dữ liệu của bạn bằng tính năng dự đoán
description: Sử dụng dự đoán để điền vào dữ liệu khách hàng không đầy đủ.
ms.date: 11/01/2021
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-predictions
- ci-custom-models
- customerInsights
ms.openlocfilehash: 7e93670007db27d13b84d7516f56830988da083e
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082524"
---
# <a name="complete-your-partial-data-with-predictions-deprecated"></a>Hoàn thành từng phần dữ liệu của bạn với các dự đoán (không được dùng nữa)

> [!IMPORTANT]
> Tính năng này sẽ **không dùng nữa** kể từ **Ngày 5 tháng 11 năm 2021**. Các triển khai hiện tại sẽ tiếp tục hoạt động cho đến khi tính năng bị xóa, nhưng bạn sẽ không thể tạo các tích hợp mới bằng cách sử dụng hướng dẫn bên dưới.

Tính năng Dự đoán cho phép bạn dễ dàng tạo các giá trị dự đoán nhằm nâng cao sự hiểu biết của bạn về một khách hàng. Trên trang **Trí tuệ** > **Dự đoán**, bạn có thể chọn **Dự đoán của tôi** để xem các dự đoán mà bạn đã đặt cấu hình trong các phần khác của Customer Insights và có thể tùy chỉnh thêm những dự đoán này.

> [!NOTE]
> Bạn không thể sử dụng tính năng này nếu môi trường của bạn sử dụng lưu trữ Azure Data Lake Gen 2.
>
> Tính năng dự đoán sử dụng phương tiện tự động để đánh giá dữ liệu và đưa ra dự đoán dựa trên dữ liệu đó, do vậy có khả năng được dùng làm phương thức lập hồ sơ, theo định nghĩa về thuật ngữ đó trong Quy định chung về bảo vệ dữ liệu ("GDPR"). Việc khách hàng sử dụng tính năng này để xử lý dữ liệu phải tuân theo GDPR hoặc các luật/quy định khác. Bạn có trách nhiệm đảm bảo rằng việc sử dụng Dynamics 365 Customer Insights, bao gồm các dự đoán, tuân thủ tất cả các luật và quy định hiện hành, bao gồm các luật liên quan đến quyền riêng tư, dữ liệu cá nhân, dữ liệu sinh trắc học, bảo vệ dữ liệu và bảo mật thông tin liên lạc.

## <a name="prerequisites"></a>Điều kiện tiên quyết

Trước khi tổ chức của bạn có thể sử dụng tính năng dự đoán, hãy đảm bảo đáp ứng các điều kiện tiên quyết sau đây:

1. Tổ chức của bạn có một phiên bản [thiết lập trong Microsoft Dataverse](/ai-builder/build-model#prerequisites) và nằm trong cùng một tổ chức với Customer Insights.

2. Môi trường Customer Insights của bạn được đính kèm với phiên bản Dataverse.

Để biết thêm thông tin, hãy xem [Tạo môi trường mới](create-environment.md).

## <a name="create-a-prediction-in-the-customer-entity"></a>Tạo dự đoán trong thực thể Khách hàng

1. Đi đến **Dữ liệu** > **Thực thể**.

2. Chọn thực thể **Khách hàng**.

3. Trong thực thể **Khách hàng: CustomerInsights**, chọn trên tab **Trường**.

4. Tìm tên thuộc tính bạn muốn dự đoán giá trị, sau đó chọn biểu tượng **Tổng quan** trong cột **Tóm tắt**.
   > [!div class="mx-imgBorder"]
   > ![Biểu tượng tổng quan.](media/intelligence-overviewicon.png "Biểu tượng tổng quan")

5. Nếu có tỷ lệ cao là thiếu giá trị cho thuộc tính của bạn, chọn **Dự đoán các giá trị còn thiếu** để tiếp tục với dự đoán của bạn.
   > [!div class="mx-imgBorder"]
   > ![Nút hiển thị trạng thái tổng quan với dự đoán các giá trị còn thiếu.](media/intelligence-overviewpredictmissingvalues.png "Nút hiển thị trạng thái tổng quan với dự đoán các giá trị còn thiếu")

6. Cung cấp **Tên hiển thị** và **Tên thực thể đầu ra** cho kết quả dự đoán.

7. Một danh sách các tùy chọn được điền sẵn sẽ hiển thị ở nơi bạn có thể ánh xạ các giá trị vào thể loại được dự đoán. Trong trường hợp này, các tùy chọn thể loại duy nhất của bạn sẽ là 0 hoặc 1 khi chúng ánh xạ vào đặc điểm đúng/sai hoặc nhị phân của dự đoán. Trong cột Thể loại, ánh xạ các giá trị trường mà bạn muốn phân loại là "0" trong dự đoán cuối cùng vào "0" và các mục bạn muốn phân loại là "1" trong dự đoán cuối cùng vào "1".
   > [!div class="mx-imgBorder"]
   > ![Ví dụ hiển thị các giá trị trường đã ánh xạ vào thể loại.](media/intelligence-categorymapping.png "Ví dụ hiển thị các giá trị trường đã ánh xạ vào thể loại")

8. Chọn **Xong** và dự đoán sẽ được xử lý. Việc xử lý sẽ mất một lúc, tùy thuộc vào kích thước và độ phức tạp của dữ liệu. Kết quả sẽ có sẵn trong một thực thể mới dựa trên **Tên thực thể đầu ra** của dự đoán bạn đã tạo.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="create-a-prediction-while-creating-a-segment"></a>Tạo dự đoán trong khi tạo phân đoạn

Bạn cũng có thể dự đoán giá trị còn thiếu cho một thuộc tính cụ thể khi tạo phân đoạn. Cụ thể, khi bạn tạo nhanh phân đoạn dựa trên thực thể Khách hàng thống nhất hoặc thực thể Giá trị đo khách hàng.

Trong quy trình này, bạn chọn một thuộc tính cụ thể để căn cứ phân đoạn của mình, như Sự hài lòng của khách hàng hoặc Số tiền giao dịch. Khi tạo phân đoạn, hệ thống sẽ đề xuất một phương pháp để dự đoán bất kỳ giá trị thiếu nào cho thuộc tính này.

1. Đi đến **Phân đoạn** và chọn **Hồ sơ** ngói.

2. Chọn một **Trường** để tạo phân đoạn và chọn một **Toán tử**, sau đó chọn **Xem lại**.

3. Cung cấp **Tên** và **Tên hiển thị** cho phân đoạn.

4. Chọn **Lưu**.

5. Nếu phân đoạn bạn vừa tạo có dữ liệu chưa hoàn chỉnh trong trường nguồn, bạn có thể chọn để dự đoán các giá trị còn thiếu.
   > [!div class="mx-imgBorder"]
   > ![Nút dự đoán.](media/segments-predictoption.png "Nút dự đoán")

6. Cung cấp **Tên hiển thị** và **Tên thực thể đầu ra** cho kết quả dự đoán.

7. Chọn **Xong**. Dự đoán của bạn sẽ được tạo ngay trong một thực thể mới với tên bạn cung cấp trong **Tên thực thể đầu ra**.

## <a name="view-a-prediction"></a>Xem dự đoán

1. Đi đến **Sự thông minh** > **Phỏng đoán** > **Dự đoán của tôi**.

2. Chọn dự đoán bạn muốn xem lại.

3. Chọn dấu chấm lửng dọc (&vellip;) bên trong **Hành động** cột và chọn **Lượt xem**.

4. Bạn sẽ thấy một số điểm dữ liệu trong dạng xem dự đoán của mình.
   > [!div class="mx-imgBorder"]
   > ![Trang dự đoán.](media/intelligence-predictionsviewpage.png "Trang dự đoán")

   - **Giá trị dự đoán** cho thấy ánh xạ bạn tạo ra trong giai đoạn ánh xạ giá trị Trường sang Thể loại. Đó là các giá trị trong tập dữ liệu của bạn đã được ánh xạ tới một thể loại cụ thể.
   -**Các yếu tố ảnh hưởng hàng đầu** là các yếu tố trong tập dữ liệu của bạn có nhiều khả năng ảnh hưởng đến độ tin cậy của dự đoán về giá trị Trường được ánh xạ tới một thể loại cụ thể.
   - **Hiệu suất** cho biết hiệu quả dự đoán. Chọn liên kết để tìm hiểu thêm.
   - **Xem trước** hiển thị mẫu tập dữ liệu đầu ra từ dự đoán của bạn và khả năng, hoặc độ tin cậy, của giá trị dự đoán trong đó 0 là không chắc chắn và 1 là chắc chắn.

## <a name="update-a-prediction"></a>Cập nhật dự đoán

1. Đi đến **Sự thông minh** > **Phỏng đoán** > **Dự đoán của tôi**.

2. Chọn dự đoán bạn muốn cập nhật và chọn biểu tượng **cập nhật**.

3. Dự đoán sẽ được lên kế hoạch để xử lý. Bạn có thể xem thời gian cập nhật lần cuối trong cột **cập nhật** của trang **Dự đoán**.

## <a name="edit-a-prediction"></a>Chỉnh sửa dự đoán

Sau khi bạn đã tạo dự đoán, bạn có thể tùy chỉnh mô hình trong AI Builder để tăng hiệu quả của mô hình của bạn.  

1. Đi đến **Sự thông minh** > **Phỏng đoán** > **Dự đoán của tôi**.

2. Chọn dự đoán bạn muốn chỉnh sửa.

3. Chọn dấu chấm lửng dọc (&vellip;) bên trong **Hành động** cột và chọn **Lượt xem**.

4. Lựa chọn **Tùy chỉnh trong AI Builder**.

5. Cập nhật mô hình của bạn trong AI Builder. [Tìm hiểu thêm về cách quản lý mô hình trong AI Builder](/ai-builder/manage-model#retrain-and-republish-existing-models).

Trong lần chạy tiếp theo, dự đoán sẽ sử dụng mô hình cập nhật mà bạn đã tạo.

> [!NOTE]
> Các mô hình mới được tạo trong AI Builder sẽ không được hiển thị trong Thông tin chi tiết về khách hàng trừ khi mô hình được tạo từ những trải nghiệm được liệt kê ở trên.

## <a name="remove-a-prediction"></a>Loại bỏ dự đoán

1. Đi đến **Sự thông minh** > **Phỏng đoán** > **Dự đoán của tôi**.

2. Chọn dự đoán bạn muốn xóa.

3. Chọn dấu chấm lửng dọc (&vellip;) bên trong **Hành động** cột và chọn **Xóa bỏ**.

4. Xác nhận tác vụ xóa này.

## <a name="troubleshooting"></a>Gỡ rối

Nếu không thể hoàn thành quy trình đính kèm Dataverse do lỗi, bạn có thể cố hoàn thành quy trình theo cách thủ công. Có hai vấn đề đã biết có thể xảy ra trong quy trình đính kèm:

- Giải pháp Bổ trợ thẻ khách hàng chưa được cài đặt.
    1. Hoàn thành các hướng dẫn để [cài đặt và đặt cấu hình giải pháp](customer-card-add-in.md).

- Quyền ứng dụng không được cấp.
    1. Truy cập [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).
    1. Chọn **Môi trường**.
    1. Chọn dấu chấm lửng dọc (&vellip;) bên cạnh môi trường bạn muốn thêm quyền và chọn **Cài đặt**.
    1. Mở rộng **Người dùng + quyền** và chọn **Người dùng**.
    1. Chọn **+ Mới** và chọn **Người dùng**.
    1. Chọn **Người dùng ứng dụng** nếu chưa chọn và nhập thông tin sau:
        - **Tên người dùng:** cihelp@microsoft.com
        - **ID ứng dụng:** 38c77d00-5fcb-4cce-9d93-af4738258e3c
        - **Tên:** Khách hàng
        - **Họ:** Thông tin chi tiết
        - **Email chính:** cihelp@microsoft.com
    1. Chọn **Lưu & Đóng**.
    1. Chọn người dùng bạn vừa tạo.
    1. Chọn **Quản lý vai trò** trong thanh menu trên cùng.
    1. Chọn **Quản trị viên hệ thống** rồi chọn **OK**.


[!INCLUDE [footer-include](includes/footer-banner.md)]
