---
title: Bắt đầu với tài khoản doanh nghiệp làm đối tượng mục tiêu chính
description: Tìm hiểu về tài khoản doanh nghiệp làm đối tượng mục tiêu chính Dynamics 365 Customer Insights.
ms.date: 10/19/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.custom: intro-internal
ms.author: wimohabb
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: fb943a91154e913c85c40fbf6077c171e9240ac5
ms.sourcegitcommit: bb1ca84bc38e81fb2ff2961c457384b7beb5b5fa
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 01/15/2022
ms.locfileid: "7977947"
---
# <a name="work-with-business-accounts-in-audience-insights"></a>Thao tác với tài khoản doanh nghiệp trong thông tin chuyên sâu về đối tượng

Khả năng của thông tin chi tiết về đối tượng trong Dynamics 365 Customer Insights cho phép bạn đặt cấu hình môi trường cho các đối tượng mục tiêu chính khác nhau: người tiêu dùng cá nhân (B2C) và tài khoản doanh nghiệp (B2B). Trong các tình huống B2C, dữ liệu tập trung xung quanh các cá nhân. Đối với B2B, đối tượng mục tiêu chính là tài khoản – tổ chức hoặc công ty – và các liên hệ. Bài viết này giúp bạn bắt đầu với một môi trường dành cho tài khoản doanh nghiệp. Bài viết liệt kê sự khác biệt của các khía cạnh tính năng trong thông tin chuyên sâu về đối tượng, tùy thuộc vào trọng tâm môi trường của bạn. Để biết thêm thông tin về sự khác biệt, hãy xem lại tài liệu về các khía cạnh tính năng. 

## <a name="create-an-environment-for-business-accounts"></a>Tạo môi trường cho tài khoản kinh doanh

Quản trị viên có thể [tạo môi trường trong tổ chức hiện có](create-environment.md). Một bước trong quy trình tạo môi trường mới yêu cầu quản trị viên của đối tượng mục tiêu chính trong môi trường. Trong trường hợp thiết lập ban đầu thông tin chuyên sâu về đối tượng sau khi mua giấy phép, trải nghiệm có hướng dẫn sẽ trợ giúp việc tạo môi trường đầu tiên.

Sau đó, bạn có thể [nhập dữ liệu](data-sources.md) cho các tài khoản doanh nghiệp và liên hệ liên quan làm nguồn dữ liệu từ tất cả các nguồn được hỗ trợ.

Sau khi hợp nhất dữ liệu, hãy [chỉ định hệ thống phân cấp tài khoản](relationships.md#set-up-account-hierarchies) trong quá trình đặt cấu hình mối quan hệ. Bạn cũng có thể [đặt cấu hình ánh xạ ngữ nghĩa](semantic-mappings.md) để kết nối thực thể liên hệ và tài khoản. 

## <a name="switch-between-primary-target-audience"></a>Chuyển đổi giữa đối tượng mục tiêu chính

Nếu tổ chức của bạn duy trì các môi trường cho tài khoản doanh nghiệp và khách hàng cá nhân, bạn có thể sử dụng bộ chuyển đổi ứng dụng ở ngăn bên trái để chọn đối tượng mục tiêu chính.

:::image type="content" source="media/switch-primary-target-audience.png" alt-text="Trình chuyển đổi để thay đổi đối tượng mục tiêu chính giữa các tài khoản khách hàng và doanh nghiệp.":::

## <a name="supported-feature-areas"></a>Các khía cạnh tính năng được hỗ trợ

- [Hoạt động](activities.md): Hỗ trợ cho tài khoản và liên hệ liên quan để tạo hoạt động và hiển thị trong tiến trình.
- [Mối quan hệ](relationships.md): Trình hướng dẫn hoạt động giúp tạo các mối quan hệ giữa các thực thể, để dạng xem tài khoản có thể hiển thị tất cả hoạt động của liên hệ. Địa chỉ liên hệ có thể xem chi tiết để xem chế độ xem liên hệ và hệ thống phân cấp có thể được sử dụng để tổng hợp hoạt động tài khoản.
- [Giá trị đo](measures.md): Hỗ trợ giá trị đo được tạo từ trình dựng giá trị đo với một phép tính. Thiết đặt tùy chọn cho phép tổng hợp các tài khoản phụ khi tạo các giá trị đo.
- [Phân khúc](segments.md): Hỗ trợ các phân khúc được tạo từ đầu bằng trình dựng phân khúc. Các toán tử mới cho phép kết hợp hệ thống phân cấp tài khoản khi xây dựng phân khúc.
- [Nhập dữ liệu](data-sources.md): Tất cả các tính năng trong khía cạnh này đều giống nhau đối với tài khoản doanh nghiệp và khách hàng cá nhân.
- [Hợp nhất dữ liệu](data-unification.md): Tất cả tính năng trong khía cạnh này đều giống nhau đối với tài khoản doanh nghiệp và khách hàng cá nhân.
- [Làm phong phú](enrichment-hub.md): Một số loại làm phong phú chỉ có đối với kịch bản khách hàng cá nhân, trong khi các loại khác chỉ có đối với tài khoản kinh doanh.
- [Dự đoán và mô hình xuất xưởng](predictions-overview.md): Dự đoán khả năng rời khỏi giao dịch chứa các bước bổ sung cho tài khoản doanh nghiệp. Các dự đoán khác chỉ dành cho khách hàng cá nhân.
- [Kích hoạt và xuất](export-destinations.md): Tính năng xuất chỉ có cho các tài khoản doanh nghiệp và khách hàng cá nhân. Một số bản xuất yêu cầu cấu hình bổ sung và thông tin liên hệ được chiếu trong các phân khúc cơ bản để hợp lệ cho tài khoản doanh nghiệp.
- [Thiết đặt hệ thống](system.md) và [quản lý người dùng](permissions.md): Tất cả các tính năng trong khía cạnh này đều giống nhau cho tài khoản doanh nghiệp và khách hàng cá nhân.

