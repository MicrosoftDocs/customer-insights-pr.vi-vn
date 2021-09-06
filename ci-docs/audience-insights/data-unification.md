---
title: Thống nhất dữ liệu
description: Tìm hiểu cách hợp nhất dữ liệu đã nhập.
ms.date: 04/16/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: bf1bbcd31333c8a557b59b001112042a1783546ab0cd2af394d8af2953a493f4
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032784"
---
# <a name="data-unification-overview"></a>Tổng quan về hợp nhất dữ liệu

Sau khi [thiết lập các nguồn dữ liệu](data-sources.md), bạn có thể thống nhất dữ liệu. Thống nhất dữ liệu bao gồm ba bước: **Ánh xạ**, **Đối sánh**, và **Hợp nhất**.

Quá trình thống nhất dữ liệu cho phép bạn thống nhất các nguồn dữ liệu đã bị tách thành một tập dữ liệu chính duy nhất cung cấp chế độ xem hợp nhất về khách hàng. Các giai đoạn thống nhất là bắt buộc, và thực hiện theo thứ tự sau đây:

1. [Bản đồ](map-entities.md)
2. [Match](match-entities.md)
3. [Hợp nhất](merge-entities.md)

Sau khi hoàn thành hợp nhất dữ liệu, bạn có thể tùy chọn

- [thiết lập mối quan hệ giữa các thực thể](relationships.md) để tạo các phân đoạn phức tạp
- [làm phong phú dữ liệu của bạn](enrichment-hub.md) để có được nhiều thông tin chi tiết hơn về khách hàng
- [xác định các hoạt động](activities.md) từ một số thuộc tính đã nhập


[!INCLUDE[footer-include](../includes/footer-banner.md)]