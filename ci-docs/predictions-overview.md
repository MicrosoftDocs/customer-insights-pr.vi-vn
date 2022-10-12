---
title: Tổng quan về chức năng dự đoán
description: Các kịch bản và tùy chọn dự đoán được ứng dụng Dynamics 365 Customer Insights hỗ trợ.
ms.date: 09/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: f8c61d7530126890d26ce482a27a0f97a39e836c
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610216"
---
# <a name="predictions-overview"></a>Tổng quan về chức năng dự đoán

Dynamics 365 Customer Insights đi kèm với nhiều tùy chọn tận dụng công nghệ AI và máy học để dự đoán dữ liệu.

## <a name="out-of-box-models"></a>Mô hình có sẵn

Sử dụng các mô hình xác định sẵn, thường được gọi là mô hình có sẵn, là cách dễ nhất để bắt đầu dự đoán dữ liệu. Các mô hình này chỉ yêu cầu một số dữ liệu và cấu trúc nhất định để tạo ra thông tin chuyên sâu một cách nhanh chóng. Các mô hình sau có sẵn:

# <a name="individual-consumers-b-to-c"></a>[Người tiêu dùng cá nhân (B2C)](#tab/b2c)

- [Giá trị trọn đời của khách hàng](predict-customer-lifetime-value.md): Dự đoán doanh thu tiềm năng của khách hàng trong toàn bộ hoạt động tương tác với doanh nghiệp.
- [Đề xuất sản phẩm](predict-product-recommendation.md): Gợi ý bộ đề xuất sản phẩm mang tính dự đoán dựa trên hành vi mua hàng và những khách hàng có kiểu mua hàng tương tự.
- [Khả năng rời bỏ đăng ký](predict-subscription-churn.md): Dự đoán xem liệu khách hàng có nguy cơ không còn sử dụng các sản phẩm hoặc dịch vụ đăng ký của công ty bạn nữa hay không.
- [Churn giao dịch](predict-transactional-churn.md) : Dự đoán liệu một khách hàng cá nhân sẽ không còn mua sản phẩm hoặc dịch vụ của bạn trong một khung thời gian nhất định hay không.
- [Phân tích tình cảm](sentiment-analysis.md) : Phân tích cảm nhận về phản hồi của khách hàng và xác định các khía cạnh kinh doanh thường được đề cập.

# <a name="business-accounts-b-to-b"></a>[Tài khoản doanh nghiệp (B2B)](#tab/b2b)

- [Churn giao dịch](predict-transactional-churn.md) : Dự đoán liệu tài khoản khách hàng sẽ không còn mua sản phẩm hoặc dịch vụ của bạn trong một khung thời gian nhất định hay không.

---

> [!TIP]
> Chúng tôi khuyên bạn nên thường xuyên làm mới các mẫu mới với dữ liệu cập nhật để đảm bảo chúng thông báo chính xác cho trường hợp sử dụng của doanh nghiệp bạn. Dữ liệu được làm mới đặc biệt khi hệ thống nhập các nguồn dữ liệu mới hoặc cập nhật. Tuy nhiên, các mô hình sẽ chỉ điểm lại trong trường hợp này và tiếp tục sử dụng dữ liệu đào tạo hiện có.
>
> Định cấu hình một **Cập nhật lịch trình** bằng cách đặt lịch trình đào tạo lại mô hình trong quá trình cấu hình. Mô hình sẽ đào tạo lại và xếp hạng lại theo lịch trình này, bạn có thể thay đổi lịch biểu này bất kỳ lúc nào.

## <a name="azure-machine-learning-integration"></a>Phần tích hợp Azure Machine Learning

Nếu tổ chức đã sử dụng các kịch bản máy học dựa trên thử nghiệm Azure Machine Learning, thì tính năng mô hình tùy chỉnh trong Customer Insights sẽ giúp kết nối các điểm. Tạo quy trình làm việc giúp bạn chọn dữ liệu bạn muốn để tạo thông tin chuyên sâu và ánh xạ kết quả đến hồ sơ khách hàng hợp nhất. Để biết thêm thông tin, hãy xem [Mô hình máy học tùy chỉnh](custom-models.md).

## <a name="manage-existing-predictions"></a>Quản lý các dự đoán hiện có

Đi đến **Sự thông minh** > **Phỏng đoán** trang. Trên **Dự đoán của tôi**, xem các dự đoán bạn đã tạo, loại dự đoán, tên thực thể đầu ra, trạng thái, lần cuối cùng dự đoán được chỉnh sửa và lần cuối cùng dữ liệu được làm mới. Bạn có thể sắp xếp danh sách các gợi ý theo bất kỳ cột nào.

Chọn dự đoán để xem các hành động có sẵn.

:::image type="content" source="media/predictions.png" alt-text="Trang dự đoán của tôi.":::

- **Chỉnh sửa** dự đoán để thay đổi thuộc tính của nó.
- [**Làm mới**](#refresh-a-prediction) dự đoán để bao gồm dữ liệu mới nhất.
- **Lượt xem** chi tiết về dự đoán.
- [**Báo cáo khả năng sử dụng dữ liệu đầu vào**](#view-the-input-data-usability-report) để xem các lỗi, cảnh báo và khuyến nghị.
- **Xóa bỏ** dự đoán.

### <a name="refresh-a-prediction"></a>Làm mới một dự đoán

Các dự đoán có thể được làm mới theo lịch trình tự động hoặc làm mới theo cách thủ công theo yêu cầu. Để làm mới tất cả các dự đoán theo cách thủ công, hãy chọn **Làm mới tất cả**. Để làm mới thủ công dự đoán, hãy chọn nó và chọn **Làm mới**. Đến [lên lịch làm mới tự động](schedule-refresh.md), đi đến **Quản trị viên** > **Hệ thống** > **Lịch trình**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

### <a name="view-the-input-data-usability-report"></a>Xem báo cáo khả năng sử dụng dữ liệu đầu vào

Báo cáo khả năng sử dụng dữ liệu đầu vào cung cấp một dạng xem tổng hợp về các lỗi và cảnh báo mà các dự đoán có sẵn của bạn có thể đang tạo ra. Nó cũng đưa ra các khuyến nghị về cách cải thiện hiệu suất của mô hình.

Báo cáo này có sẵn sau khi một mô hình đã hoàn tất quá trình đào tạo. Nó được tạo cho từng mô hình riêng biệt, bất kể nó đã hoàn thành đào tạo thành công hay chưa.

Trên **Dự đoán của tôi**, chọn dự đoán và chọn **Báo cáo khả năng sử dụng dữ liệu đầu vào**. Hoặc từ chế độ xem chi tiết dự đoán, hãy chọn **Báo cáo khả năng sử dụng dữ liệu đầu vào**.

:::image type="content" source="media/input-data-usability-report.png" alt-text="Ví dụ về một báo cáo khả năng sử dụng dữ liệu đầu vào hiển thị một bảng có lỗi, cảnh báo và đề xuất.":::

Báo cáo bao gồm:

- **Tên:** Tên mô tả của lỗi, cảnh báo hoặc khuyến nghị.
- **Bươc:** Giai đoạn mô hình, đào tạo hoặc điểm số, thông tin đề cập đến.
- **Tiểu bang:** Mức độ nghiêm trọng của thông tin (lỗi, cảnh báo, khuyến nghị).
- **Tên cột dọc:** Cột trong một thực thể cần được sửa đổi để cải thiện hiệu suất mô hình.
- **Tên thực thể:** Tên của thực thể cần được sửa đổi để cải thiện hiệu suất của mô hình.
- **Thông tin chi tiết:** Thông tin chi tiết về lỗi, cảnh báo hoặc khuyến nghị.

[!INCLUDE [footer-include](includes/footer-banner.md)]
