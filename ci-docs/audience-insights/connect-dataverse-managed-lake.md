---
title: Kết nối với bảng trong Microsoft Dataverse
description: Nhập dữ liệu từ một kho dữ liệu Microsoft Dataverse được quản lý.
ms.date: 12/06/2021
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: mhart
searchScope:
- ci-dataverse
- customerInsights
ms.openlocfilehash: 8e11b60295fa5c187b1ac4877fb347e2d9bb41a1
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 02/25/2022
ms.locfileid: "8354168"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Kết nối với dữ liệu trong một kho dữ liệu được quản lý Microsoft Dataverse



Bài viết này cung cấp thông tin về cách Dataverse người dùng có thể nhanh chóng kết nối với các thực thể phân tích trong một Microsoft Dataverse hồ quản lý. 

> [!NOTE]
> Bạn phải là quản trị viên trên Dataverse tổ chức để tiến hành và xem danh sách các thực thể có trong hồ được quản lý.

## <a name="important-considerations"></a>Những điều quan trọng cần cân nhắc

Dữ liệu lưu trữ trong các dịch vụ trực tuyến như Azure Data Lake Storage có thể được lưu trữ ở địa điểm khác với nơi xử lý hoặc lưu trữ dữ liệu trong Dynamics 365 Customer Insights.Bằng cách nhập hoặc kết nối với dữ liệu được lưu trữ trong các dịch vụ trực tuyến, bạn đồng ý rằng dữ liệu có thể được chuyển đến và lưu trữ bằng Dynamics 365 Customer Insights . [Tìm hiểu thêm tại Trung tâm Tin cậy của Microsoft](https://www.microsoft.com/trust-center).

## <a name="connect-to-a-dataverse-managed-lake"></a>Kết nối với kho được quản lý Dataverse

1. Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Dữ liệu** > **Nguồn dữ liệu**.

2. Chọn **Thêm nguồn dữ liệu**.

3. Lựa chọn **Microsoft Dataverse** và chọn **Tiếp theo**.

4. Đặt **Tên** cho nguồn dữ liệu rồi chọn **Tiếp**. 

5. Cung cấp **Địa chỉ máy chủ** cho tổ chức Dataverse và chọn **Đăng nhập**.

   :::image type="content" source="media/ingest-dataverse-server-address.png" alt-text="Màn hình trong bước nhập dữ liệu nơi người dùng có thể nhập URL môi trường Dataverse.":::

6. Chọn các bảng bạn muốn nhập dưới dạng thực thể vào thông tin chi tiết về đối tượng từ danh sách có sẵn.    

   > [!NOTE]
   > Nếu một số bảng đã được chọn, chúng có thể được sử dụng bởi các ứng dụng Dynamics 365 khác (chẳng hạn như Dynamics 365 Sales Insights hoặc Customer Service Insights). Bạn không thể thay đổi lựa chọn. Các bảng này sẽ có sẵn dưới dạng thực thể sau khi nguồn dữ liệu được tạo.

   :::image type="content" source="media/select-dataverse-entities.png" alt-text="Hộp thoại hiển thị danh sách các thực thể trong môi trường Dataverse.":::

7. Lưu lựa chọn của bạn để bắt đầu đồng bộ hóa các bảng đã chọn từ Dataverse. Bạn sẽ tìm thấy kết nối mới được thêm vào trang **Nguồn dữ liệu**. Lựa chọn sẽ được đưa vào hàng đợi để làm mới và hiển thị số thực thể là 0 cho đến khi tất cả các bảng đã chọn được đồng bộ hóa.

Chỉ một nguồn dữ liệu của một môi trường có thể đồng thời sử dụng cùng một kho do Dataverse quản lý.

## <a name="edit-a-dataverse-managed-lake-data-source"></a>Chỉnh sửa nguồn dữ liệu của kho được quản lý Dataverse

Bạn chỉ chỉnh sửa lựa chọn thực thể sau khi tạo nguồn dữ liệu. Ví dụ: nếu các thực thể bổ sung được thêm vào Dataverse và bạn cũng muốn nhập chúng.    
Để kết nối với một kho dữ liệu Dataverse khác, [tạo một nguồn dữ liệu mới](#connect-to-a-dataverse-managed-lake).

1. Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Dữ liệu** > **Nguồn dữ liệu**.

2. Cạnh nguồn dữ liệu mà bạn muốn thay đổi, hãy chọn dấu chấm lửng.

3. Nhấp vào tùy chọn **Chỉnh sửa** trong danh sách.

4. Chọn các thực thể bổ sung từ danh sách các thực thể có sẵn rồi chọn **Lưu**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
