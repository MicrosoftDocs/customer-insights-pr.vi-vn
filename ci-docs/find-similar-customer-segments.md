---
title: Tìm khách hàng tương tự bằng AI (xem trước) (chứa video)
description: Tìm phân khúc khách hàng tương tự nhờ trí tuệ nhân tạo.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-segment-builder
- ci-segment-insights
- customerInsights
ms.openlocfilehash: 09fe36a4da45d114cbfccf8dad1e7b80b4b7e320
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170753"
---
# <a name="find-similar-customers-with-ai-preview"></a>Tìm khách hàng tương tự bằng AI (xem trước)

Tìm khách hàng tương tự trong cơ sở khách hàng của bạn bằng trí tuệ nhân tạo. Bạn cần tạo ít nhất một phân đoạn để sử dụng tính năng này. Mở rộng tiêu chí của một phân khúc hiện tại giúp tìm kiếm những khách hàng tương tự với phân khúc đó.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOFou]

> [!NOTE]
> *Tìm khách hàng tương tự* sử dụng các phương tiện tự động để đánh giá dữ liệu và đưa ra dự đoán dựa trên dữ liệu đó. Do đó, nó có khả năng được sử dụng như một phương pháp lập hồ sơ, vì thuật ngữ đó được xác định bởi Quy định chung về bảo vệ dữ liệu ("GDPR"). Việc khách hàng sử dụng tính năng này để xử lý dữ liệu phải tuân theo GDPR hoặc các luật/quy định khác. Bạn có trách nhiệm đảm bảo rằng việc sử dụng Dynamics 365 Customer Insights, bao gồm các dự đoán, tuân thủ tất cả các luật và quy định hiện hành, bao gồm các luật liên quan đến quyền riêng tư, dữ liệu cá nhân, dữ liệu sinh trắc học, bảo vệ dữ liệu và bảo mật thông tin liên lạc.

## <a name="find-similar-customers"></a>Tìm khách hàng tương tự

1. Đi đến **Phân đoạn** và chọn phân đoạn bạn muốn làm cơ sở cho phân đoạn mới của mình. Đó là *phân khúc nguồn* của bạn.

1. Lựa chọn **Tìm những khách hàng tương tự**.

1. Xem lại tên được gợi ý cho phân khúc mới của bạn và đổi tên nếu cần.

1. Tùy chọn, thêm [thẻ](work-with-tags-columns.md#manage-tags) sang phân khúc mới.

1. Xem lại các trường xác định phân khúc mới của bạn. Các trường này xác định cơ sở mà hệ thống sẽ cố gắng tìm khách hàng tương tự với phân khúc nguồn của bạn. Hệ thống chọn các trường được đề xuất theo mặc định. Nếu cần, hãy thêm các trường khác.
  Các trường có thể làm giảm đáng kể hiệu suất mô hình sẽ tự động bị loại trừ:
  
   - Các trường có các kiểu dữ liệu sau: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType
   - Các trường có lượng số (số thành phần trong một trường) ít hơn 2 hoặc nhiều hơn 30

1. Chọn nếu bạn muốn bao gồm **Tất cả khách hàng** ngoại trừ phân khúc nguồn hoặc chỉ những khách hàng trong **phân khúc khác nhau** trong phân khúc mới của bạn.

1. Theo mặc định, hệ thống gợi ý chỉ nên bao gồm 20% kích thước đối tượng mục tiêu trong đầu ra của bạn. Chỉnh sửa ngưỡng này nếu cần. Tăng ngưỡng sẽ làm giảm độ chính xác.

1. Bao gồm khách hàng trong phân khúc nguồn của bạn bằng cách chọn **Bao gồm các thành viên từ phân khúc nguồn ngoài những khách hàng có các thuộc tính tương tự** hộp kiểm.

1. Lựa chọn **Chạy** ở cuối trang để bắt đầu [nhiệm vụ phân loại nhị phân](#about-similarity-scores) (một phương pháp của máy học) phân tích tập dữ liệu.

## <a name="view-the-similar-segment"></a>Xem phân khúc tương tự

Sau khi xử lý phân đoạn tương tự, bạn sẽ tìm thấy phân đoạn mới được liệt kê trên **Phân đoạn** trang có loại **Sự bành trướng**.

Lựa chọn **Lượt xem** để xem phân phối kết quả trên [điểm tương tự](#about-similarity-scores) và các giá trị điểm tương tự dưới **Xem trước thành viên phân khúc**.

:::image type="content" source="media/expanded-segment.png" alt-text="Phân khúc khách hàng tương tự.":::

## <a name="manage-a-similar-segment"></a>Quản lý một phân đoạn tương tự

[Làm việc với và quản lý một phân đoạn tương tự](segments.md#manage-existing-segments) như bạn làm với các phân đoạn khác. Ví dụ: xuất phân khúc hoặc xây dựng một giá trị đo.

Chỉnh sửa, làm mới, đổi tên, tải xuống và xóa một phân đoạn tương tự. Việc chỉnh sửa một phân đoạn tương tự sẽ xử lý lại dữ liệu của bạn. Phân khúc đã tạo trước đó được cập nhật dữ liệu làm mới.

## <a name="about-similarity-scores"></a>Giới thiệu về điểm tương đồng

Mô hình học trên máy phân loại nhị phân gán một điểm số cho khách hàng trong phân khúc tương tự. Điểm số dựa trên sự tương đồng với khách hàng trong phân khúc nguồn.

- Điểm tương đồng dưới 0,55 có nghĩa khách hàng được hệ thống phân loại là *không giống* với khách hàng trong phân khúc nguồn
- Điểm tương đồng trong khoảng 0,55 – 0,7 được phân loại là *có phần giống*
- Điểm tương đồng trong khoảng 0,7 – 0,85 được phân loại là *giống*
- Điểm tương đồng trong khoảng 0,85 – 1 là các khách hàng được hệ thống phân loại là *rất giống*

Khách hàng có điểm tương tự dưới 0,4 không được bao gồm trong đầu ra mô hình. Hệ thống nhận định họ không đủ tương tự với phân khúc nguồn.

[!INCLUDE [footer-include](includes/footer-banner.md)]
