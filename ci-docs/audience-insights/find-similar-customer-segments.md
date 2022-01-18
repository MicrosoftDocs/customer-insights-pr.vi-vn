---
title: Tìm khách hàng tương tự bằng AI (có video)
description: Tìm phân khúc khách hàng tương tự nhờ trí tuệ nhân tạo.
ms.date: 06/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: de337ae989558c81fff25a6ff7cca01890ed306b
ms.sourcegitcommit: 9132fdf54070cc551ab878378078e6285852818f
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 12/18/2021
ms.locfileid: "7934866"
---
# <a name="similar-customers-preview"></a>Khách hàng tương tự (xem trước)

Tính năng này cho phép bạn tìm thấy những khách hàng tương tự trong cơ sở khách hàng của mình bằng cách sử dụng trí tuệ nhân tạo. Bạn cần phải có ít nhất một phân khúc được tạo để sử dụng tính năng này. Mở rộng các tiêu chí của một phân đoạn hiện có sẽ giúp tìm kiếm các khách hàng tương tự với phân khúc đó.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOFou]

> [!NOTE]
> *Tìm khách hàng tương tự* sử dụng các phương tiện tự động để đánh giá dữ liệu và đưa ra dự đoán dựa trên dữ liệu đó và do đó có khả năng được sử dụng làm phương pháp lập hồ sơ, theo định nghĩa về thuật ngữ đó trong Quy định chung về bảo vệ dữ liệu ("GDPR"). Việc khách hàng sử dụng tính năng này để xử lý dữ liệu phải tuân theo GDPR hoặc các luật/quy định khác. Bạn có trách nhiệm đảm bảo rằng việc sử dụng Dynamics 365 Customer Insights, bao gồm các dự đoán, tuân thủ tất cả các luật và quy định hiện hành, bao gồm các luật liên quan đến quyền riêng tư, dữ liệu cá nhân, dữ liệu sinh trắc học, bảo vệ dữ liệu và bảo mật thông tin liên lạc.

## <a name="finding-similar-customers"></a>Tìm khách hàng tương tự

1. Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Phân đoạn** và chọn phân đoạn bạn muốn làm cơ sở cho phân đoạn mới của mình. Đó là *phân khúc nguồn* của bạn.

1. Trên thanh hành động, chọn **Tìm khách hàng tương tự**.

1. Xem lại tên được gợi ý cho phân khúc mới của bạn và đổi tên nếu cần.

1. Xem lại các trường xác định phân khúc mới của bạn. Các trường này xác định cơ sở mà hệ thống sẽ cố gắng tìm khách hàng tương tự với phân khúc nguồn của bạn. Hệ thống sẽ chọn các trường được đề xuất theo mặc định.
  Các trường có thể làm giảm đáng kể hiệu suất mô hình sẽ tự động bị loại trừ:
  
   - Các trường có các kiểu dữ liệu sau: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType
   - Các trường có lượng số (số thành phần trong một trường) ít hơn 2 hoặc nhiều hơn 30

1. Chọn xem bạn muốn thêm **Tất cả khách hàng** hay chỉ khách hàng trong **Phân khúc cụ thể hiện có** vào phân khúc mới của mình.

1. Loại trừ khách hàng trong phân khúc nguồn của bạn bằng cách chọn hộp kiểm **Loại trừ tất cả mọi người trong phân khúc nguồn**.

1. Theo mặc định, hệ thống gợi ý chỉ nên bao gồm 20% kích thước đối tượng mục tiêu trong đầu ra của bạn. Chỉnh sửa ngưỡng này nếu cần. Tăng ngưỡng sẽ làm giảm độ chính xác.

1. Lựa chọn **Chạy** ở dưới cùng của trang để bắt đầu nhiệm vụ phân loại nhị phân (một phương thức máy học) để phân tích tập dữ liệu.

## <a name="view-the-similar-segment"></a>Xem phân khúc tương tự

Sau khi xử lý phân khúc tương tự, bạn sẽ tìm thấy phân khúc mới được liệt kê trên trang **Phân khúc**.

> [!div class="mx-imgBorder"]
> ![Phân khúc khách hàng tương tự.](media/expanded-segment.png "Phân khúc khách hàng tương tự")

Chọn **Xem** trên thành hành động để mở chi tiết phân khúc. Dạng xem này chứa thông tin về phân phối kết quả trên [điểm tương đồng](#about-similarity-scores). Bạn cũng sẽ tìm thấy các giá trị điểm tương đồng trong **Xem trước thành phần phân khúc**.

## <a name="use-the-output-of-a-similar-segment"></a>Sử dụng đầu ra của phân khúc tương tự

Bạn có thể [làm việc với đầu ra của phân khúc tương tự](segments.md) như với các phân khúc khác. Ví dụ: xuất phân khúc hoặc xây dựng một giá trị đo.

## <a name="refresh-and-edit-a-similar-segment"></a>Làm mới và chỉnh sửa phân khúc tương tự

Để làm mới phân khúc tương tự, hãy chọn phân khúc đó trên trang **Phân khúc** rồi chọn **Làm mới** trên thanh hành động.

Thao tác chỉnh sửa phân khúc tương tự sẽ xử lý lại dữ liệu của bạn. Phân khúc đã tạo trước đó được cập nhật dữ liệu làm mới.    
Để chỉnh sửa phân khúc tương tự, hãy chọn phân khúc đó trên trang **Phân khúc** rồi chọn **Chỉnh sửa** trên thanh hành động. Áp dụng thay đổi của bạn và chọn **Chạy** để bắt đầu xử lý.

## <a name="delete-a-similar-segment"></a>Xóa phân khúc tương tự

Chọn phân khúc trên trang **Phân khúc** rồi chọn **Xóa** trên thanh hành động. Sau đó, xác nhận xóa.

## <a name="about-similarity-scores"></a>Giới thiệu về điểm tương đồng

Mô hình học trên máy phân loại nhị phân gán một điểm số cho khách hàng trong phân khúc tương tự. Điểm số dựa trên sự tương đồng với khách hàng trong phân khúc nguồn.

- Điểm tương đồng dưới 0,55 có nghĩa khách hàng được hệ thống phân loại là *không giống* với khách hàng trong phân khúc nguồn
- Điểm tương đồng trong khoảng 0,55 – 0,7 được phân loại là *có phần giống*
- Điểm tương đồng trong khoảng 0,7 – 0,85 được phân loại là *giống*
- Điểm tương đồng trong khoảng 0,85 – 1 là các khách hàng được hệ thống phân loại là *rất giống*

Khách hàng có điểm tương tự dưới 0,4 không được bao gồm trong đầu ra mô hình. Hệ thống nhận định họ không đủ tương tự với phân khúc nguồn.


[!INCLUDE[footer-include](../includes/footer-banner.md)]