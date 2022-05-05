---
title: Cài đặt bảo mật trong Dynamics 365 Customer Insights
description: Tìm hiểu về cài đặt bảo mật trong Dynamics 365 Customer Insights.
ms.date: 04/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 5d73bacccadc9193d76d8dfafd0365dabc911e00
ms.sourcegitcommit: cf74b8c20d88eb96e1ac86e18cd44fe27aad5ab9
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 04/28/2022
ms.locfileid: "8653807"
---
# <a name="security-overview-page"></a>Trang tổng quan về bảo mật

Các **Bảo vệ** trang liệt kê các tùy chọn để định cấu hình quyền của người dùng và các tính năng giúp tạo Dynamics 365 Customer Insights an toàn hơn. Chỉ quản trị viên mới có thể truy cập trang này. 

Đi đến **Quản trị viên** > **Bảo vệ** để định cấu hình cài đặt.

Các **Bảo vệ** trang bao gồm các tab sau:
- [Người dùng](#users-tab)
- [API](#apis-tab)
- [Kho lưu trữ khóa](#key-vault-tab)

## <a name="users-tab"></a>Tab Người dùng

Quyền truy cập vào Thông tin chi tiết về khách hàng bị hạn chế đối với người dùng trong tổ chức của bạn đã được quản trị viên thêm vào ứng dụng. Các **Người dùng** cho phép bạn quản lý quyền truy cập của người dùng và quyền của họ. Để biết thêm thông tin, hãy xem [Quyền Người dùng](permissions.md).

## <a name="apis-tab"></a>Tab API

Xem và quản lý các khóa để sử dụng [API thông tin chi tiết về khách hàng](apis.md) với dữ liệu của môi trường của bạn.

Bạn có thể tạo khóa chính và khóa phụ mới bằng cách chọn **Tạo lại chính** hoặc **Tạo lại thứ cấp**. 

Để chặn quyền truy cập API vào môi trường, hãy chọn **Vô hiệu**. Nếu các API bị tắt, bạn có thể chọn **Cho phép** để cấp lại quyền truy cập.

## <a name="key-vault-tab"></a>Tab Key Vault

Các **Kho chìa khóa** tab cho phép bạn liên kết và quản lý của riêng bạn [Kho tiền khóa Azure](/azure/key-vault/general/basic-concepts) cho môi trường.
Có thể dùng Key vault chuyên dụng để chia giai đoạn và sử dụng bí mật trong ranh giới tuân thủ của một tổ chức. Thông tin chi tiết về khách hàng có thể sử dụng các bí mật trong Azure Key Vault để [thiết lập kết nối](connections.md) cho các hệ thống của bên thứ ba.

Để biết thêm thông tin, hãy xem [Mang tín liệu khóa Azure của riêng bạn](use-azure-key-vault.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]
