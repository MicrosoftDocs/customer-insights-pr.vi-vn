---
title: Phân khúc dựa trên đầu ra dự đoán
description: Tạo phân khúc dựa trên thực thể đầu ra của mô hình dự đoán.
ms.date: 03/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 488db1af865ce600ec012716327d053bee33aff8
ms.sourcegitcommit: a95c82f46c23f625cb34fceba021ccc70d4b1df6
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 03/30/2021
ms.locfileid: "5741455"
---
# <a name="create-a-segment-based-on-a-prediction-model-preview"></a><span data-ttu-id="1ae7c-103">Tạo phân khúc dựa trên mô hình dự đoán (bản xem trước)</span><span class="sxs-lookup"><span data-stu-id="1ae7c-103">Create a segment based on a prediction model (preview)</span></span>

<span data-ttu-id="1ae7c-104">Kết quả dự đoán đôi khi chỉ áp dụng cho một nhóm nhỏ khách hàng của bạn.</span><span class="sxs-lookup"><span data-stu-id="1ae7c-104">The results of predictions sometimes only apply to a subset of your customers.</span></span> <span data-ttu-id="1ae7c-105">Tăng khả năng cá nhân hóa các đề xuất bằng cách tạo phân khúc từ kết quả của các mô hình dự đoán.</span><span class="sxs-lookup"><span data-stu-id="1ae7c-105">Increase the personalization of recommendations by creating segments from results of prediction models.</span></span> <span data-ttu-id="1ae7c-106">Ví dụ: bạn có thể muốn đưa ra các đề xuất cụ thể cho những khách hàng thích một loại dịch vụ nhất định.</span><span class="sxs-lookup"><span data-stu-id="1ae7c-106">For example, you may want to give specific recommendations to customers that prefer a certain type of service.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="1ae7c-107">Điều kiện tiên quyết</span><span class="sxs-lookup"><span data-stu-id="1ae7c-107">Prerequisites</span></span>

- <span data-ttu-id="1ae7c-108">Ít nhất [Quyền của người đóng góp](permissions.md) trong Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="1ae7c-108">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>

- <span data-ttu-id="1ae7c-109">Mô hình đề xuất về sản phẩm, mô hình khách hàng ngừng giao dịch, mô hình khách hàng ngừng sử dụng gói đăng ký hoặc mô hình giá trị lâu dài của khách hàng được đặt cấu hình trong Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="1ae7c-109">A product recommendation, transactional churn, subscription churn, or customer lifetime value model configured in Customer Insights.</span></span> <span data-ttu-id="1ae7c-110">Xem lại yêu cầu để thiết lập các mô hình khác nhau:</span><span class="sxs-lookup"><span data-stu-id="1ae7c-110">Review the requirements to set up the different models:</span></span>

  - [<span data-ttu-id="1ae7c-111">Mô hình đề xuất sản phẩm</span><span class="sxs-lookup"><span data-stu-id="1ae7c-111">Product recommendation model</span></span>](predict-product-recommendation.md)
  - [<span data-ttu-id="1ae7c-112">Mô hình khách hàng ngừng sử dụng gói đăng ký</span><span class="sxs-lookup"><span data-stu-id="1ae7c-112">Subscription churn model</span></span>](predict-subscription-churn.md)
  - [<span data-ttu-id="1ae7c-113">Mô hình khách hàng ngừng giao dịch</span><span class="sxs-lookup"><span data-stu-id="1ae7c-113">Transactional churn model</span></span>](predict-transactional-churn.md)
  - [<span data-ttu-id="1ae7c-114">Giá trị trọn đời của khách hàng</span><span class="sxs-lookup"><span data-stu-id="1ae7c-114">Customer lifetime value model</span></span>](predict-customer-lifetime-value.md)

## <a name="create-a-customer-segment-based-on-predictions"></a><span data-ttu-id="1ae7c-115">Tạo phân khúc khách hàng dựa trên dự đoán</span><span class="sxs-lookup"><span data-stu-id="1ae7c-115">Create a customer segment based on predictions</span></span>

1. <span data-ttu-id="1ae7c-116">Đi đến **Thông tin** > **Dự đoán** và chọn tab **Dự đoán của tôi**.</span><span class="sxs-lookup"><span data-stu-id="1ae7c-116">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="1ae7c-117">Chọn các dấu ba chấm dọc bên cạnh mô hình mà bạn muốn xem lại rồi chọn **Xem**.</span><span class="sxs-lookup"><span data-stu-id="1ae7c-117">Select the vertical ellipses next to the model you want to review and select **View**.</span></span>

1. <span data-ttu-id="1ae7c-118">Trên trang kết quả, hãy chọn **Tạo phân khúc**.</span><span class="sxs-lookup"><span data-stu-id="1ae7c-118">On the results page, select **Create segment**.</span></span> <span data-ttu-id="1ae7c-119">Để biết thêm thông tin về trang kết quả, hãy xem lại bài viết về mô hình.</span><span class="sxs-lookup"><span data-stu-id="1ae7c-119">For more information about the results page, review the article about the model.</span></span>

   :::image type="content" source="media/prediction-create-segment.png" alt-text="Ảnh chụp màn hình về trang kết quả dự đoán có phần đánh dấu về hành động Tạo phân khúc.":::

1. <span data-ttu-id="1ae7c-121">Tạo phân khúc mới dựa trên thực thể đầu ra của mô hình đã chọn.</span><span class="sxs-lookup"><span data-stu-id="1ae7c-121">Create a new segment based on the output entity of the selected model.</span></span> <span data-ttu-id="1ae7c-122">Để biết thêm thông tin, hãy xem [Tạo và quản lý phân khúc](segments.md).</span><span class="sxs-lookup"><span data-stu-id="1ae7c-122">For more information, see [Create and manage segments](segments.md).</span></span>