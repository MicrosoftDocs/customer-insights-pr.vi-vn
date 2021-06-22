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
ms.openlocfilehash: 69ae945b22819521db217508c6fc232876346747
ms.sourcegitcommit: 6b07c9c3102761be162e4842f3c9fbc19f948a9b
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 05/25/2021
ms.locfileid: "6095763"
---
# <a name="predictions-overview"></a><span data-ttu-id="04fa0-103">Tổng quan về chức năng dự đoán</span><span class="sxs-lookup"><span data-stu-id="04fa0-103">Predictions overview</span></span>

<span data-ttu-id="04fa0-104">Dynamics 365 Customer Insights đi kèm với nhiều tùy chọn tận dụng công nghệ AI và máy học để dự đoán dữ liệu.</span><span class="sxs-lookup"><span data-stu-id="04fa0-104">Dynamics 365 Customer Insights comes with a variety of options that leverage AI and machine learning to predict data.</span></span> 

## <a name="out-of-box-models"></a><span data-ttu-id="04fa0-105">Mô hình có sẵn</span><span class="sxs-lookup"><span data-stu-id="04fa0-105">Out-of-box models</span></span>

<span data-ttu-id="04fa0-106">Sử dụng các mô hình xác định sẵn, thường được gọi là mô hình có sẵn, là cách dễ nhất để bắt đầu dự đoán dữ liệu.</span><span class="sxs-lookup"><span data-stu-id="04fa0-106">The easiest way to start with predicting data are predefined models, often referred to as out-of-box models.</span></span> <span data-ttu-id="04fa0-107">Các mô hình này chỉ yêu cầu một số dữ liệu và cấu trúc nhất định để tạo ra thông tin chuyên sâu một cách nhanh chóng.</span><span class="sxs-lookup"><span data-stu-id="04fa0-107">They only require certain data and structure to generate insights quickly.</span></span> <span data-ttu-id="04fa0-108">Hiện tại, ứng dụng cung cấp các mô hình sau đây:</span><span class="sxs-lookup"><span data-stu-id="04fa0-108">Currently, the following models are available:</span></span> 
- <span data-ttu-id="04fa0-109">[Giá trị trọn đời của khách hàng](predict-customer-lifetime-value.md): Dự đoán doanh thu tiềm năng của khách hàng trong toàn bộ hoạt động tương tác với doanh nghiệp.</span><span class="sxs-lookup"><span data-stu-id="04fa0-109">[Customer lifetime value](predict-customer-lifetime-value.md): Predicts the potential revenue of a customer throughout the entire interaction with a business.</span></span> 
- <span data-ttu-id="04fa0-110">[Đề xuất sản phẩm](predict-product-recommendation.md): Gợi ý bộ đề xuất sản phẩm mang tính dự đoán dựa trên hành vi mua hàng và những khách hàng có kiểu mua hàng tương tự.</span><span class="sxs-lookup"><span data-stu-id="04fa0-110">[Product recommendation](predict-product-recommendation.md): Suggests sets of predictive product recommendations based on purchase behavior and customers with similar purchase patterns.</span></span>
- <span data-ttu-id="04fa0-111">[Khả năng rời bỏ đăng ký](predict-subscription-churn.md): Dự đoán xem liệu khách hàng có nguy cơ không còn sử dụng các sản phẩm hoặc dịch vụ đăng ký của công ty bạn nữa hay không.</span><span class="sxs-lookup"><span data-stu-id="04fa0-111">[Subscription churn](predict-subscription-churn.md): Predicts whether a customer is at risk for no longer using your company’s subscription products or services.</span></span>
- <span data-ttu-id="04fa0-112">[Khả năng rời bỏ giao dịch](predict-transactional-churn.md): Dự đoán xem liệu khách hàng sẽ không còn mua sản phẩm hoặc dịch vụ của bạn nữa trong một khung thời gian nhất định hay không.</span><span class="sxs-lookup"><span data-stu-id="04fa0-112">[Transactional churn](predict-transactional-churn.md): Predict if a customer will no longer purchase your products or services in a certain time frame.</span></span>

## <a name="azure-machine-learning-integration"></a><span data-ttu-id="04fa0-113">Phần tích hợp Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="04fa0-113">Azure Machine Learning integration</span></span>

<span data-ttu-id="04fa0-114">Nếu tổ chức đã sử dụng các kịch bản máy học dựa trên thử nghiệm Azure Machine Learning, thì tính năng mô hình tùy chỉnh trong Customer Insights sẽ giúp kết nối các điểm.</span><span class="sxs-lookup"><span data-stu-id="04fa0-114">If an organization already uses machine learning scenarios based on Azure Machine Learning experiments, the custom models feature in Customer Insights helps to connect the dots.</span></span> <span data-ttu-id="04fa0-115">Tạo quy trình làm việc giúp bạn chọn dữ liệu bạn muốn để tạo thông tin chuyên sâu và ánh xạ kết quả đến hồ sơ khách hàng hợp nhất.</span><span class="sxs-lookup"><span data-stu-id="04fa0-115">Create workflows that help you choose the data you want to generate insights from and map the results to your unified customer profiles.</span></span> <span data-ttu-id="04fa0-116">Để biết thêm thông tin, hãy xem [Mô hình máy học tùy chỉnh](custom-models.md).</span><span class="sxs-lookup"><span data-stu-id="04fa0-116">For more information, see [Custom machine learning models](custom-models.md).</span></span>

## <a name="ai-builder-prediction"></a><span data-ttu-id="04fa0-117">Dự đoán của AI Builder</span><span class="sxs-lookup"><span data-stu-id="04fa0-117">AI Builder prediction</span></span>

<span data-ttu-id="04fa0-118">Đôi khi, tập dữ liệu không hoàn chỉnh và thiếu một số giá trị.</span><span class="sxs-lookup"><span data-stu-id="04fa0-118">Sometimes, data sets are incomplete and some values are missing.</span></span> <span data-ttu-id="04fa0-119">Customer Insights có thể giúp dự đoán các giá trị còn thiếu cho thực thể và phân khúc Khách hàng.</span><span class="sxs-lookup"><span data-stu-id="04fa0-119">Customer Insights can help to predict missing values for the Customer entity and segments.</span></span> <span data-ttu-id="04fa0-120">Để biết thêm thông tin, hãy xem bài viết [Hoàn thành dữ liệu chưa hoàn chỉnh bằng tính năng dự đoán](predictions.md).</span><span class="sxs-lookup"><span data-stu-id="04fa0-120">For more information, see [Complete your partial data with predictions](predictions.md).</span></span>
