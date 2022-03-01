---
title: Tạo dạng xem hợp nhất về khách hàng của bạn
description: Thực hiện quy trình hợp nhất dữ liệu với dữ liệu của bạn để tạo một tập hợp dữ liệu chính duy nhất về hồ sơ khách hàng.
ms.date: 10/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-unify
ms.openlocfilehash: 694bfd0e407975af64ca0971a73fe4c3f5ba5a23
ms.sourcegitcommit: 37182127b93b90846cc91fbeb26dd7a18cf5610a
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 10/18/2021
ms.locfileid: "7648097"
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