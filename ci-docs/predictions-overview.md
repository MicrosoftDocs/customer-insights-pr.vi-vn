---
title: Tổng quan về chức năng dự đoán
description: Các kịch bản và tùy chọn dự đoán được ứng dụng Dynamics 365 Customer Insights hỗ trợ.
ms.date: 03/24/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: a87af80fa713a1ac70493345c0c920e416692b0f
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 06/29/2022
ms.locfileid: "9083112"
---
# <a name="predictions-overview"></a>Tổng quan về chức năng dự đoán

Dynamics 365 Customer Insights đi kèm với nhiều tùy chọn tận dụng công nghệ AI và máy học để dự đoán dữ liệu. 

## <a name="out-of-box-models"></a>Mô hình có sẵn

Sử dụng các mô hình xác định sẵn, thường được gọi là mô hình có sẵn, là cách dễ nhất để bắt đầu dự đoán dữ liệu. Các mô hình này chỉ yêu cầu một số dữ liệu và cấu trúc nhất định để tạo ra thông tin chuyên sâu một cách nhanh chóng. Hiện tại, ứng dụng cung cấp các mô hình sau đây: 

# <a name="individual-consumers-b-to-c"></a>[Người tiêu dùng cá nhân (B2C)](#tab/b2c)

- [Giá trị trọn đời của khách hàng](predict-customer-lifetime-value.md): Dự đoán doanh thu tiềm năng của khách hàng trong toàn bộ hoạt động tương tác với doanh nghiệp.
- [Đề xuất sản phẩm](predict-product-recommendation.md): Gợi ý bộ đề xuất sản phẩm mang tính dự đoán dựa trên hành vi mua hàng và những khách hàng có kiểu mua hàng tương tự.
- [Khả năng rời bỏ đăng ký](predict-subscription-churn.md): Dự đoán xem liệu khách hàng có nguy cơ không còn sử dụng các sản phẩm hoặc dịch vụ đăng ký của công ty bạn nữa hay không.
- [Khả năng rời bỏ giao dịch](predict-transactional-churn.md): Dự đoán xem liệu khách hàng sẽ không còn mua sản phẩm hoặc dịch vụ của bạn nữa trong một khung thời gian nhất định hay không.
- [Phân tích tình cảm](sentiment-analysis.md) : Phân tích cảm tính về phản hồi của khách hàng và xác định các khía cạnh kinh doanh thường xuyên được đề cập.

# <a name="business-accounts-b-to-b"></a>[Tài khoản doanh nghiệp (B2B)](#tab/b2b)

- [Khả năng rời bỏ giao dịch](predict-transactional-churn.md): Dự đoán xem liệu khách hàng sẽ không còn mua sản phẩm hoặc dịch vụ của bạn nữa trong một khung thời gian nhất định hay không.

---

> [!TIP]
> Chúng tôi khuyên bạn nên thường xuyên làm mới các mẫu mới với dữ liệu cập nhật để đảm bảo chúng thông báo chính xác cho trường hợp sử dụng của doanh nghiệp bạn. Dữ liệu được làm mới đặc biệt khi hệ thống nhập các nguồn dữ liệu mới hoặc cập nhật. Tuy nhiên, các mô hình sẽ chỉ điểm lại trong trường hợp này và tiếp tục sử dụng dữ liệu đào tạo hiện có.
> 
> Bạn có thể cấu hình một **Cập nhật lịch trình** bằng cách đặt lịch trình đào tạo lại mô hình trong trải nghiệm cấu hình. Mô hình sẽ đào tạo lại và xếp hạng lại theo lịch trình này, bạn có thể thay đổi lịch biểu này bất kỳ lúc nào.


## <a name="azure-machine-learning-integration"></a>Phần tích hợp Azure Machine Learning

Nếu tổ chức đã sử dụng các kịch bản máy học dựa trên thử nghiệm Azure Machine Learning, thì tính năng mô hình tùy chỉnh trong Customer Insights sẽ giúp kết nối các điểm. Tạo quy trình làm việc giúp bạn chọn dữ liệu bạn muốn để tạo thông tin chuyên sâu và ánh xạ kết quả đến hồ sơ khách hàng hợp nhất. Để biết thêm thông tin, hãy xem [Mô hình máy học tùy chỉnh](custom-models.md).

## <a name="ai-builder-prediction"></a>AI Builder dự đoán

Đôi khi, tập dữ liệu không hoàn chỉnh và thiếu một số giá trị. Customer Insights có thể giúp dự đoán các giá trị còn thiếu cho thực thể và phân khúc Khách hàng. Để biết thêm thông tin, hãy xem bài viết [Hoàn thành dữ liệu chưa hoàn chỉnh bằng tính năng dự đoán](predictions.md).
