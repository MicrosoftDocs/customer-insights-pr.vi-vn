---
title: Vai trò và quyền
description: Tổng quan về các vai trò và quyền có sẵn cho các thành viên của không gian làm việc.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 07/06/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 6d7f4db4a130fc15a69b380c892538db5492d96d8e13f3c070c6a6b9bd098371
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036719"
---
# <a name="roles-and-permissions"></a>Vai trò và quyền

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Không gian làm việc là cách bạn lưu trữ cũng như quản lý các sự kiện và báo cáo. Thành viên là người dùng có thể truy cập không gian làm việc. Bạn có thể chỉ định các thành viên vào không gian làm việc của mình, đồng thời xác định vai trò và quyền của họ. Vai trò quản trị viên quản lý không gian làm việc và môi trường, định cấu hình thông tin chi tiết về mức độ tương tác cho những người dùng khác. Vai trò cộng tác viên hướng đến các nhà phân tích, những người không cần định cấu hình thông tin chi tiết về mức độ tương tác nhưng muốn tạo báo cáo, kênh hoặc phân đoạn của riêng họ.

## <a name="permissions"></a>Quyền
  
Biểu đồ sau xác định các quyền cho từng vai trò. 

| Quyền | Quản trị viên môi trường | Quản trị viên không gian làm việc | Người đóng góp môi trường | Người đóng góp không gian làm việc | 
|--|--|--|--|--|
| Tạo môi trường (người tạo tự động trở thành quản trị viên môi trường) | X* | X* | X* | X* |  
| Định cấu hình môi trường (thành viên môi trường, xóa môi trường) | X |  |  |  |  
| Tạo không gian làm việc | X |  |  |  |  
| Định cấu hình không gian làm việc (thành viên không gian làm việc, xóa không gian làm việc) | X | X |  |  |  
| Đặt cấu hình sự kiện và sự kiện tinh chỉnh | X | X | |  |  
| Xem các sự kiện trong không gian làm việc và các sự kiện tinh chỉnh | X | X | |  |  
| Xem nguồn lực không gian làm việc (báo cáo, phân khúc và chỉ số)| X | X | X | X |  
| Tạo báo cáo tùy chỉnh và phễu | X | X | X | X |  
| Tạo các chỉ số và thứ nguyên cơ sở| X | X |  |  |  
| Tạo phân khúc| X | X | X | X |  

*Chỉ có thể tạo môi trường dùng thử trong bản xem trước. 

## <a name="add-members"></a>Thêm thành viên

Bạn có thể thêm và xóa thành viên khỏi không gian làm việc và môi trường. Để biết thêm thông tin, hãy xem [Môi trường và không gian làm việc](manage-environments-workspaces.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
