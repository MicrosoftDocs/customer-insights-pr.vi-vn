---
title: Tạo dạng xem hợp nhất về khách hàng của bạn
description: Thực hiện quy trình hợp nhất dữ liệu với dữ liệu của bạn để tạo một tập dữ liệu chính duy nhất về hồ sơ tài khoản hoặc khách hàng.
ms.date: 08/12/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: overview
author: Scott-Stabbert
ms.author: sstabbert
manager: shellyha
searchScope:
- ci-map
- customerInsights
ms.openlocfilehash: c2a81776eab147c4b5209a6fbf89c0f4c9853d1d
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304453"
---
# <a name="data-unification-overview"></a>Tổng quan về hợp nhất dữ liệu

Sau khi [thiết lập các nguồn dữ liệu](data-sources.md), bạn có thể thống nhất dữ liệu. Hợp nhất dữ liệu cho phép bạn hợp nhất các nguồn dữ liệu riêng biệt một lần thành một tập dữ liệu chính duy nhất cung cấp chế độ xem thống nhất về dữ liệu đó.

Đối với người tiêu dùng cá nhân (B-to-C) nơi dữ liệu tập trung xung quanh các cá nhân, hợp nhất cung cấp một cái nhìn thống nhất về khách hàng của bạn. Đối với tài khoản doanh nghiệp (B-to-B) nơi dữ liệu tập trung xung quanh các tài khoản, hợp nhất cung cấp một cái nhìn thống nhất về các tài khoản của bạn. [Liên hệ thống nhất (xem trước)](data-unification-contacts.md) cho phép địa chỉ liên hệ của các tài khoản đó được hợp nhất riêng biệt và được liên kết với các tài khoản.

Dữ liệu có thể được thống nhất trên một thực thể duy nhất hoặc nhiều thực thể.

# <a name="individual-consumers-b-to-c"></a>[Người tiêu dùng cá nhân (B2C)](#tab/b2c)

Quy trình hợp nhất ánh xạ dữ liệu khách hàng từ các nguồn dữ liệu của bạn, xóa các bản sao, khớp dữ liệu giữa các thực thể và tạo một hồ sơ thống nhất. Việc hợp nhất được thực hiện theo thứ tự sau:

1. [Các trường nguồn](map-entities.md) (trước đây được gọi là Bản đồ): Trong bước trường nguồn, chọn các thực thể và trường để đưa vào quy trình thống nhất. Ánh xạ các trường thành một kiểu ngữ nghĩa chung mô tả mục đích của trường.

1. [Bản ghi trùng lặp](remove-duplicates.md) (trước đây là một phần của Đối sánh): Trong bước bản ghi trùng lặp, tùy chọn xác định các quy tắc để loại bỏ các bản ghi khách hàng trùng lặp từ bên trong mỗi thực thể.

1. [Điều kiện phù hợp](match-entities.md) (trước đây được gọi là Đối sánh): Trong bước điều kiện đối sánh, xác định các quy tắc đối sánh hồ sơ khách hàng giữa các thực thể. Khi khách hàng được tìm thấy trong hai hoặc nhiều thực thể, một bản ghi tổng hợp duy nhất sẽ được tạo với tất cả các cột và dữ liệu từ mỗi thực thể.

1. [Các trường khách hàng hợp nhất](merge-entities.md) (trước đây được gọi là Hợp nhất): Trong bước trường khách hàng hợp nhất, xác định trường nguồn nào nên được bao gồm, loại trừ hoặc hợp nhất thành một hồ sơ khách hàng hợp nhất.  

1. [Kiểm tra lại](review-unification.md) và tạo hồ sơ thống nhất.

# <a name="business-accounts-b-to-b"></a>[Tài khoản doanh nghiệp (B2B)](#tab/b2b)

Quá trình hợp nhất ánh xạ dữ liệu tài khoản từ các nguồn dữ liệu của bạn, xóa các bản sao, khớp dữ liệu giữa các thực thể và tạo một hồ sơ thống nhất. Việc hợp nhất được thực hiện theo thứ tự sau:

1. [Các trường nguồn](map-entities.md) (trước đây được gọi là Bản đồ): Trong bước trường nguồn, chọn các thực thể và trường để đưa vào quy trình thống nhất tài khoản. Ánh xạ các trường thành một kiểu ngữ nghĩa chung mô tả mục đích của trường.

1. [Bản ghi trùng lặp](remove-duplicates.md) (trước đây là một phần của Đối sánh): Trong bước bản ghi trùng lặp, tùy chọn xác định các quy tắc để loại bỏ các bản ghi tài khoản trùng lặp từ bên trong mỗi thực thể.

1. [Điều kiện phù hợp](match-entities.md) (trước đây được gọi là Khớp): Trong bước điều kiện đối sánh, xác định các quy tắc đối sánh các bản ghi tài khoản giữa các thực thể. Khi một tài khoản được tìm thấy trong hai hoặc nhiều thực thể, một bản ghi tổng hợp duy nhất sẽ được tạo với tất cả các cột và dữ liệu từ mỗi thực thể.

1. [Các trường khách hàng hợp nhất](merge-entities.md) (trước đây được gọi là Hợp nhất): Trong bước trường khách hàng hợp nhất, xác định trường nguồn nào nên được bao gồm, loại trừ hoặc hợp nhất thành một hồ sơ khách hàng hợp nhất.  

1. [Kiểm tra lại](review-unification.md) và tạo hồ sơ thống nhất.

Sau khi hợp nhất các tài khoản, bạn có thể tùy chọn [thống nhất địa chỉ liên hệ (xem trước)](data-unification-contacts.md) cho các tài khoản đó và liên kết các địa chỉ liên hệ hợp nhất với các tài khoản hợp nhất.

---

Sau khi hoàn thành hợp nhất dữ liệu, bạn có thể tùy chọn:

- [Thiết lập mối quan hệ giữa các thực thể](relationships.md) để tạo ra các phân đoạn tinh vi.
- [Làm phong phú dữ liệu của bạn](enrichment-hub.md) để có được nhiều thông tin chi tiết hơn về khách hàng của bạn.
- [Xác định các hoạt động](activities.md) từ một số thuộc tính đã nhập.
- [Xây dựng các biện pháp](measures.md) để hiểu rõ hơn về hành vi của khách hàng và hiệu quả kinh doanh.

[!INCLUDE [footer-include](includes/footer-banner.md)]
