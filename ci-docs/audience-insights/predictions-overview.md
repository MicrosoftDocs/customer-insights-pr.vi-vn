---
title: Tổng quan về các kịch bản dự đoán được hỗ trợ
description: Các kịch bản và tùy chọn dự đoán được ứng dụng Dynamics 365 Customer Insights hỗ trợ.
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: get-started
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 57c61895d636273fc90a0ac5a942fd0c9abf583c687ae20621949554e581cdf8
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036035"
---
# <a name="predictions-overview"></a>Tổng quan về chức năng dự đoán

Dynamics 365 Customer Insights đi kèm với nhiều tùy chọn tận dụng công nghệ AI và máy học để dự đoán dữ liệu. 

## <a name="out-of-box-models"></a>Mô hình có sẵn

Sử dụng các mô hình xác định sẵn, thường được gọi là mô hình có sẵn, là cách dễ nhất để bắt đầu dự đoán dữ liệu. Các mô hình này chỉ yêu cầu một số dữ liệu và cấu trúc nhất định để tạo ra thông tin chuyên sâu một cách nhanh chóng. Hiện tại, ứng dụng cung cấp các mô hình sau đây: 
- [Giá trị trọn đời của khách hàng](predict-customer-lifetime-value.md): Dự đoán doanh thu tiềm năng của khách hàng trong toàn bộ hoạt động tương tác với doanh nghiệp. 
- [Đề xuất sản phẩm](predict-product-recommendation.md): Gợi ý bộ đề xuất sản phẩm mang tính dự đoán dựa trên hành vi mua hàng và những khách hàng có kiểu mua hàng tương tự.
- [Khả năng rời bỏ đăng ký](predict-subscription-churn.md): Dự đoán xem liệu khách hàng có nguy cơ không còn sử dụng các sản phẩm hoặc dịch vụ đăng ký của công ty bạn nữa hay không.
- [Khả năng rời bỏ giao dịch](predict-transactional-churn.md): Dự đoán xem liệu khách hàng sẽ không còn mua sản phẩm hoặc dịch vụ của bạn nữa trong một khung thời gian nhất định hay không.

## <a name="azure-machine-learning-integration"></a>Phần tích hợp Azure Machine Learning

Nếu tổ chức đã sử dụng các kịch bản máy học dựa trên thử nghiệm Azure Machine Learning, thì tính năng mô hình tùy chỉnh trong Customer Insights sẽ giúp kết nối các điểm. Tạo quy trình làm việc giúp bạn chọn dữ liệu bạn muốn để tạo thông tin chuyên sâu và ánh xạ kết quả đến hồ sơ khách hàng hợp nhất. Để biết thêm thông tin, hãy xem [Mô hình máy học tùy chỉnh](custom-models.md).

## <a name="ai-builder-prediction"></a>Dự đoán của AI Builder

Đôi khi, tập dữ liệu không hoàn chỉnh và thiếu một số giá trị. Customer Insights có thể giúp dự đoán các giá trị còn thiếu cho thực thể và phân khúc Khách hàng. Để biết thêm thông tin, hãy xem bài viết [Hoàn thành dữ liệu chưa hoàn chỉnh bằng tính năng dự đoán](predictions.md).
