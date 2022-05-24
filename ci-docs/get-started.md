---
title: Bắt đầu với Dynamics 365 Customer Insights
description: Tổng quan về Thông tin chi tiết về khách hàng giúp các tài nguyên bắt đầu nhanh chóng.
ms.reviewer: v-wendysmith
ms.author: mhart
author: m-hartmann
ms.date: 04/12/2022
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: 1a19d83930d667bdca5301dcc5a3ffa5db6a7bdc
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741159"
---
# <a name="get-started-with-dynamics-365-customer-insights"></a>Bắt đầu với Dynamics 365 Customer Insights

Thông tin chi tiết về khách hàng có thể giúp bạn hiểu sâu hơn về khách hàng của mình. Kết nối dữ liệu từ nhiều nguồn giao dịch, hành vi và quan sát khác nhau để tạo ra một góc nhìn toàn diện về khách hàng. Sử dụng những hiểu biết này để thúc đẩy trải nghiệm và quy trình định hướng khách hàng. Hợp nhất và hiểu dữ liệu khách hàng và khai thác dữ liệu đó để có những hiểu biết và hành động thông minh.

## <a name="step-1-create-an-environment"></a>Bước 1: Tạo môi trường

Để bắt đầu, trước tiên bạn phải tạo ra một môi trường để làm việc. Nếu tổ chức của bạn đã mua giấy phép, hãy xem [Tạo môi trường](create-environment.md). Để bắt đầu dùng thử Thông tin chi tiết về khách hàng, hãy xem [Thiết lập môi trường thử nghiệm](trial-signup.md).

## <a name="step-2-explore-customer-insights"></a>Bước 2: Khám phá thông tin chi tiết về khách hàng

Lần đầu tiên đăng nhập vào Customer Insights, bạn có thể định cấu hình cài đặt và khám phá sản phẩm.

1. [đăng nhập vào Thông tin chi tiết về khách hàng](https://home.ci.ai.dynamics.com) sử dụng Microsoft của bạn Azure Active Directory (AAD) tài khoản người dùng.

1. [Thay đổi môi trường](manage-environments.md#switch-environments) để xem dữ liệu demo và [khám phá Thông tin chi tiết về khách hàng](home.md).

## <a name="step-3-ingest-unify-and-set-up-relationships-for-your-data"></a>Bước 3: Nhập, hợp nhất và thiết lập mối quan hệ cho dữ liệu của bạn

Hồ sơ thống nhất là nền tảng để có được thông tin chi tiết và thực hiện hành động trên dữ liệu. Mang dữ liệu từ nhiều nguồn khác nhau và chạy quy trình hợp nhất dữ liệu để kết hợp các cấu hình thống nhất. Chỉ định mối quan hệ giữa các thực thể được nhập sử dụng các tính năng bổ sung để thêm thông tin vào hồ sơ.

1. Nhập dữ liệu bằng cách tạo nguồn dữ liệu từ nhiều tùy chọn. Chọn giữa [Power Query đầu nối](connect-power-query.md), một [Thư mục Mô hình Dữ liệu Chung](connect-common-data-model.md), hoặc [Microsoft Dataverse](connect-dataverse-managed-lake.md). 

1. Chạy [quá trình hợp nhất dữ liệu](data-unification.md) bằng cách xác định [trường nguồn](map-entities.md), loại bỏ [trùng lặp](remove-duplicates.md),[điều kiện phù hợp](match-entities.md), và [thống nhất các lĩnh vực](merge-entities.md).

1. Làm quen với [các thực thể mà hệ thống tạo ra](entities.md) và tạo ra [mối quan hệ giữa các thực thể đã nhập](relationships.md).

## <a name="step-4-enhance-unified-profiles-with-predictions-activities-and-measures"></a>Bước 4: Nâng cao cấu hình thống nhất với các dự đoán, hoạt động và biện pháp

Với các cấu hình hợp nhất được thiết lập, bạn có thể nâng cao dữ liệu của mình và tăng thêm thông tin mà họ cung cấp.

1. Chọn từ một thư viện mở rộng của các nhà cung cấp dịch vụ tăng cường để [tăng cường dữ liệu khách hàng của bạn](enrichment-hub.md).

1. Sử dụng [mô hình sẵn dùng](predictions-overview.md) để dự đoán khả năng khách hàng rời khỏi hoặc doanh thu dự kiến.

1. [Đặt cấu hình các hoạt động](activities.md) dựa trên dữ liệu đã nhập và trực quan hóa các tương tác với khách hàng của bạn theo trình tự thời gian.

1. [Xây dựng các biện pháp](measures.md) để đánh giá mục tiêu kinh doanh và KPI của bạn.

## <a name="step-5-create-segments-and-activate-data-through-various-export-options"></a>Bước 5: Tạo phân khúc và kích hoạt dữ liệu thông qua các tùy chọn xuất khác nhau

Bây giờ dữ liệu của bạn đã hoàn tất và chứa nhiều thông tin về khách hàng của bạn, đã đến lúc tìm cách thực hiện hành động đối với dữ liệu đó.

1. [Tạo phân khúc](segments.md), tập hợp con của cơ sở khách hàng, để đảm bảo hành động của bạn phù hợp với khách hàng mục tiêu.

1. Duyệt qua danh mục mở rộng của [tùy chọn xuất](export-destinations.md) nơi bạn có thể sử dụng dữ liệu khách hàng. Ví dụ: bạn có thể sử dụng dữ liệu để quản lý các chương trình khuyến mãi và liên hệ với tiếp thị kỹ thuật số.

1. Xem lại các tùy chọn tích hợp, chẳng hạn như đối với các ứng dụng Dynamics 365 khác với [Tiện ích bổ sung Thẻ khách hàng](customer-card-add-in.md).  


[!INCLUDE [footer-include](includes/footer-banner.md)]
