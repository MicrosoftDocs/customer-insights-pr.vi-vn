---
title: Kết nối với dữ liệu trong một kho dữ liệu được quản lý Microsoft Dataverse
description: Nhập dữ liệu từ một kho dữ liệu Microsoft Dataverse được quản lý.
ms.date: 07/26/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: v-wendysmith
searchScope:
- ci-dataverse
- customerInsights
ms.openlocfilehash: b21150a1c51bdad35250cae7fde7f38a014ec876
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 07/28/2022
ms.locfileid: "9206979"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Kết nối với dữ liệu trong một kho dữ liệu được quản lý Microsoft Dataverse

Microsoft Dataverse người dùng có thể nhanh chóng kết nối với các thực thể phân tích trong một Microsoft Dataverse hồ quản lý. Chỉ một nguồn dữ liệu của một môi trường có thể đồng thời sử dụng cùng một kho do Dataverse quản lý.

> [!NOTE]
> Bạn phải là quản trị viên trên Dataverse tổ chức để tiến hành và xem danh sách các thực thể có trong hồ được quản lý.

## <a name="prerequisites"></a>Điều kiện tiên quyết

- Dữ liệu lưu trữ trong các dịch vụ trực tuyến như Azure Data Lake Storage có thể được lưu trữ ở địa điểm khác với nơi xử lý hoặc lưu trữ dữ liệu trong Dynamics 365 Customer Insights.Bằng cách nhập hoặc kết nối với dữ liệu được lưu trữ trong các dịch vụ trực tuyến, bạn đồng ý rằng dữ liệu có thể được chuyển đến và lưu trữ bằng Dynamics 365 Customer Insights . [Tìm hiểu thêm tại Trung tâm Tin cậy của Microsoft](https://www.microsoft.com/trust-center).

- Chỉ có Dataverse thực thể với [thay đổi theo dõi](/power-platform/admin/enable-change-tracking-control-data-synchronization) được kích hoạt có thể nhìn thấy. Các thực thể này có thể được xuất sang Dataverse - hồ dữ liệu được quản lý và được sử dụng trong Thông tin chi tiết về khách hàng. Ngoài hộp Dataverse các bảng được bật theo dõi thay đổi theo mặc định. Bạn cần bật theo dõi thay đổi cho các bảng tùy chỉnh. Để kiểm tra xem một Dataverse bảng được bật để theo dõi thay đổi, hãy chuyển đến [Power Apps](https://make.powerapps.com) > **Dữ liệu** > **Những cái bàn**. Tìm bảng quan tâm của bạn và chọn nó. Đi đến **Cài đặt** > **Tùy chọn nâng cao** và xem xét **Theo dõi các thay đổi** cài đặt.

## <a name="connect-to-a-dataverse-managed-lake"></a>Kết nối với kho được quản lý Dataverse

1. Chuyển tới **Dữ liệu** > **Nguồn dữ liệu**.

1. Chọn **Thêm nguồn dữ liệu**.

1. Chọn **Microsoft Dataverse**.

1. Nhập **Tên** cho nguồn dữ liệu và một tùy chọn **Sự mô tả**.

1. Cung cấp **Địa chỉ máy chủ** cho tổ chức Dataverse và chọn **Đăng nhập**.

1. Chọn các bảng bạn muốn nhập làm thực thể cho Thông tin chi tiết về khách hàng từ danh sách có sẵn.

   > [!NOTE]
   > Nếu một số bảng đã được chọn, chúng có thể được sử dụng bởi các ứng dụng Dynamics 365 khác (chẳng hạn như Dynamics 365 Sales Insights hoặc Customer Service Insights). Bạn không thể thay đổi lựa chọn. Các bảng này sẽ có sẵn dưới dạng thực thể sau khi nguồn dữ liệu được tạo.

    :::image type="content" source="media/select-dataverse-entities.png" alt-text="Hộp thoại hiển thị danh sách các thực thể trong môi trường Dataverse.":::

1. Lưu lựa chọn của bạn để bắt đầu đồng bộ hóa các bảng đã chọn từ Dataverse. Bạn sẽ tìm thấy kết nối mới được thêm vào trang **Nguồn dữ liệu**. Lựa chọn sẽ được đưa vào hàng đợi để làm mới và hiển thị số thực thể là 0 cho đến khi tất cả các bảng đã chọn được đồng bộ hóa.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Quá trình tải dữ liệu có thể mất một khoảng thời gian. Sau khi làm mới thành công, dữ liệu đã nhập có thể được xem xét từ [**Thực thể**](entities.md) trang.

## <a name="edit-a-dataverse-managed-lake-data-source"></a>Chỉnh sửa nguồn dữ liệu của kho được quản lý Dataverse

Bạn chỉ chỉnh sửa lựa chọn thực thể sau khi tạo nguồn dữ liệu. Ví dụ: nếu các thực thể bổ sung được thêm vào Dataverse và bạn cũng muốn nhập chúng.
Để kết nối với một kho dữ liệu Dataverse khác, [tạo một nguồn dữ liệu mới](#connect-to-a-dataverse-managed-lake).

1. Chuyển tới **Dữ liệu** > **Nguồn dữ liệu**.

1. Bên cạnh nguồn dữ liệu bạn muốn cập nhật, hãy chọn **Chỉnh sửa**.

1. Chọn các thực thể bổ sung từ danh sách các thực thể có sẵn.

1. Nhấp chuột **Tiết kiệm** để áp dụng các thay đổi của bạn và quay lại **Nguồn dữ liệu** trang.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
