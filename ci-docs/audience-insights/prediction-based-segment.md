---
title: Phân khúc dựa trên đầu ra dự đoán
description: Tạo phân khúc dựa trên thực thể đầu ra của mô hình dự đoán.
ms.date: 03/24/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: b0b3357cdf3c049bd92f6c3f690f27433df9117b
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 02/16/2022
ms.locfileid: "8226689"
---
# <a name="create-a-segment-based-on-a-prediction-model-preview"></a>Tạo phân khúc dựa trên mô hình dự đoán (bản xem trước)

Kết quả dự đoán đôi khi chỉ áp dụng cho một nhóm nhỏ khách hàng của bạn. Tăng khả năng cá nhân hóa các đề xuất bằng cách tạo phân khúc từ kết quả của các mô hình dự đoán. Ví dụ: bạn có thể muốn đưa ra các đề xuất cụ thể cho những khách hàng thích một loại dịch vụ nhất định. 

## <a name="prerequisites"></a>Điều kiện tiên quyết

- Ít nhất [Quyền của người đóng góp](permissions.md) trong Customer Insights.

- Mô hình đề xuất về sản phẩm, mô hình khách hàng ngừng giao dịch, mô hình khách hàng ngừng sử dụng gói đăng ký hoặc mô hình giá trị lâu dài của khách hàng được đặt cấu hình trong Customer Insights. Xem lại yêu cầu để thiết lập các mô hình khác nhau:

  - [Mô hình đề xuất sản phẩm](predict-product-recommendation.md)
  - [Mô hình khách hàng ngừng sử dụng gói đăng ký](predict-subscription-churn.md)
  - [Mô hình khách hàng ngừng giao dịch](predict-transactional-churn.md)
  - [Giá trị trọn đời của khách hàng](predict-customer-lifetime-value.md)

## <a name="create-a-customer-segment-based-on-predictions"></a>Tạo phân khúc khách hàng dựa trên dự đoán

1. Đi đến **Thông tin** > **Dự đoán** và chọn tab **Dự đoán của tôi**.

1. Chọn các dấu ba chấm dọc bên cạnh mô hình mà bạn muốn xem lại rồi chọn **Xem**.

1. Trên trang kết quả, hãy chọn **Tạo phân khúc**. Để biết thêm thông tin về trang kết quả, hãy xem lại bài viết về mô hình.

   :::image type="content" source="media/prediction-create-segment.png" alt-text="Ảnh chụp màn hình về trang kết quả dự đoán có phần đánh dấu về hành động Tạo phân khúc.":::

1. Tạo phân khúc mới dựa trên thực thể đầu ra của mô hình đã chọn. Để biết thêm thông tin, hãy xem [Tạo và quản lý phân khúc](segments.md).