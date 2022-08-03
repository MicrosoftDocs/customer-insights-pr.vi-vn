---
title: Tổng quan về hợp nhất dữ liệu
description: Thực hiện quy trình hợp nhất dữ liệu với dữ liệu của bạn để tạo một tập dữ liệu duy nhất về hồ sơ khách hàng hợp nhất.
ms.date: 05/10/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: overview
author: v-wendysmith
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-map
- customerInsights
ms.openlocfilehash: 766e688cb80c50a0d620943f87b76eb84a2fb89a
ms.sourcegitcommit: 3c5b0b40b2b45e420015bbdd228ce0e610245e6f
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 07/12/2022
ms.locfileid: "9139544"
---
# <a name="data-unification-overview"></a>Tổng quan về hợp nhất dữ liệu

Sau khi [thiết lập các nguồn dữ liệu](data-sources.md), bạn có thể thống nhất dữ liệu. Hợp nhất dữ liệu cho phép bạn hợp nhất các nguồn dữ liệu riêng biệt một lần thành một tập dữ liệu chính duy nhất cung cấp chế độ xem thống nhất về dữ liệu đó. Đối với người tiêu dùng cá nhân (B-to-C) nơi dữ liệu tập trung xung quanh các cá nhân, hợp nhất cung cấp một cái nhìn thống nhất về khách hàng của bạn. Đối với tài khoản doanh nghiệp (B-to-B) nơi dữ liệu tập trung xung quanh các tài khoản, hợp nhất cung cấp một cái nhìn thống nhất về các tài khoản của bạn.

Dữ liệu có thể được thống nhất trên một thực thể duy nhất hoặc nhiều thực thể. Việc hợp nhất được thực hiện theo thứ tự sau:

1. [Các trường nguồn](map-entities.md) (trước đây được gọi là Bản đồ): Trong bước trường nguồn, chọn các thực thể và trường để đưa vào quy trình thống nhất. Ánh xạ các trường thành một kiểu ngữ nghĩa chung mô tả mục đích của trường.

1. [Bản ghi trùng lặp](remove-duplicates.md) (trước đây là một phần của Đối sánh): Trong bước bản ghi trùng lặp, tùy chọn xác định các quy tắc để loại bỏ các bản ghi khách hàng trùng lặp từ bên trong mỗi thực thể.

1. [Điều kiện phù hợp](match-entities.md) (trước đây được gọi là Đối sánh): Trong bước điều kiện đối sánh, xác định các quy tắc đối sánh hồ sơ khách hàng giữa các thực thể. Khi khách hàng được tìm thấy trong hai hoặc nhiều thực thể, một bản ghi tổng hợp duy nhất sẽ được tạo với tất cả các cột và dữ liệu từ mỗi thực thể.

1. [Các trường khách hàng hợp nhất](merge-entities.md) (trước đây được gọi là Hợp nhất): Trong bước trường khách hàng hợp nhất, xác định trường nguồn nào nên được bao gồm, loại trừ hoặc hợp nhất thành một hồ sơ khách hàng hợp nhất.  

1. [Kiểm tra lại](review-unification.md) và tạo hồ sơ thống nhất.

Sau khi hoàn thành hợp nhất dữ liệu, bạn có thể tùy chọn:

- [Thiết lập mối quan hệ giữa các thực thể](relationships.md) để tạo ra các phân đoạn tinh vi.
- [Làm phong phú dữ liệu của bạn](enrichment-hub.md) để có được nhiều thông tin chi tiết hơn về khách hàng của bạn.
- [Xác định các hoạt động](activities.md) từ một số thuộc tính đã nhập.
- [Xây dựng các biện pháp](measures.md) để hiểu rõ hơn về hành vi của khách hàng và hiệu quả kinh doanh.

[!INCLUDE [footer-include](includes/footer-banner.md)]
