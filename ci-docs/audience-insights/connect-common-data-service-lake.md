---
title: Kết nối với các thực thể trong kho do Common Data Service quản lý
description: Nhập dữ liệu từ một kho dữ liệu Common Data Service được quản lý.
ms.date: 09/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.reviewer: adkuppa
ms.openlocfilehash: 18b6cd3fdaf5b738877a73b520b91dbc6ded40de
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267840"
---
# <a name="connect-to-data-in-a-common-data-service-managed-data-lake"></a>Kết nối với dữ liệu trong một kho dữ liệu được quản lý Common Data Service

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Bài viết này cung cấp thông tin về cách khách hàng Dynamics 365 hiện tại có thể nhanh chóng kết nối với các thực thể phân tích của họ trong kho dữ liệu Common Data Service được quản lý. Bạn phải là quản trị viên trên tổ chức Common Data Service để tiến hành và xem danh sách các thực thể có trong kho dữ liệu được quản lý.

## <a name="important-considerations"></a>Những điều quan trọng cần cân nhắc

Dữ liệu lưu trữ trong các dịch vụ trực tuyến như Azure Data Lake Storage có thể được lưu trữ ở địa điểm khác với nơi xử lý hoặc lưu trữ dữ liệu trong Dynamics 365 Customer Insights. Khi nhập hoặc kết nối với dữ liệu lưu trữ trong các dịch vụ trực tuyến, bạn đồng ý rằng dữ liệu có thể được chuyển sang hoặc lưu trữ bằng Dynamics 365 Customer Insights. [Tìm hiểu thêm trên Trung tâm tin cậy Microsoft.](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-common-data-service-managed-lake"></a>Kết nối với kho được quản lý Common Data Service

1. Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Dữ liệu** > **Nguồn dữ liệu**.

2. Chọn **Thêm nguồn dữ liệu**.

3. Chọn **Kết nối với Common Data Service** rồi chọn **Tiếp theo**.

4. Đặt **Tên** cho nguồn dữ liệu rồi chọn **Tiếp**. Hướng dẫn về tên: 
   - Bắt đầu bằng một chữ cái.
   - Chỉ sử dụng chữ cái và số. Không được phép nhập ký tự đặc biệt và khoảng trống.
   - Sử dụng từ 3 đến 64 ký tự.

5. Cung cấp **Địa chỉ máy chủ** cho tổ chức Common Data Service của bạn rồi chọn **Đăng nhập**.

   > [!div class="mx-imgBorder"]
   > ![Hộp thoại để nhập địa chỉ máy chủ Common Data Service](media/enter-CDS-org-details.png)

6. Chọn các thực thể bạn muốn nhập từ danh sách có sẵn.    

   > [!NOTE]
   > Nếu một số thực thể được chọn, thì chúng có thể được các ứng dụng khác của Dynamics 365 (chẳng hạn như Dynamics 365 Sales Insights hoặc Customer Service Insights) sử dụng. Bạn không thể thay đổi lựa chọn. Các thực thể này sẽ khả dụng sau khi nguồn dữ liệu được tạo.

   > [!div class="mx-imgBorder"]
   > ![Hộp thoại hiển thị danh sách các thực thể trong tổ chức Common Data Service](media/select-analytical-entities.png)

7. Lưu lựa chọn của bạn để bắt đầu đồng bộ hóa các thực thể được chọn với kho được quản lý Common Data Service. Bạn sẽ tìm thấy kết nối mới được thêm vào trang **Nguồn dữ liệu**. Thực thể sẽ được xếp hàng để làm mới và hiển thị các thực thể được tính là 0 cho đến khi tất cả các thực thể được đồng bộ hóa.

Chỉ một nguồn dữ liệu của một môi trường có thể đồng thời sử dụng cùng một kho do Common Data Service quản lý.

## <a name="edit-a-common-data-service-managed-lake-data-source"></a>Chỉnh sửa nguồn dữ liệu của kho được quản lý Common Data Service

Bạn chỉ chỉnh sửa lựa chọn thực thể sau khi tạo nguồn dữ liệu. Ví dụ: nếu các thực thể bổ sung được thêm vào Common Data Service và bạn cũng muốn nhập chúng.    
Cách kết nối với Common Data Service khác, [tạo nguồn dữ liệu mới](#connect-to-a-common-data-service-managed-lake).

1. Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Dữ liệu** > **Nguồn dữ liệu**.

2. Cạnh nguồn dữ liệu mà bạn muốn thay đổi, hãy chọn dấu chấm lửng.

3. Nhấp vào tùy chọn **Chỉnh sửa** trong danh sách.

4. Chọn các thực thể bổ sung từ danh sách các thực thể có sẵn rồi chọn **Lưu**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]