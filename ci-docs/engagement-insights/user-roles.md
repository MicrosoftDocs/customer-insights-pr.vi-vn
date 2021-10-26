---
title: Vai trò và quyền
description: Tổng quan về các vai trò và quyền có sẵn cho các thành viên của không gian làm việc.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 68e28caf1c14c23acd506da5f7b441f1e3b72e8b
ms.sourcegitcommit: 53b133a716c73cb71e8bcbedc6273cec70ceba6c
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 10/15/2021
ms.locfileid: "7645563"
---
# <a name="roles-and-permissions"></a>Vai trò và quyền

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Không gian làm việc là nơi bạn lưu trữ cũng như quản lý sự kiện và báo cáo. Để biết thêm thông tin, hãy xem [Tạo không gian làm việc và thêm thành viên](create-workspace.md). 

Không gian làm việc có thể bao gồm các vai trò và quyền sau:

- Vai trò *Thành viên* là những người dùng có thể truy cập vào không gian làm việc. Bạn có thể chỉ định các thành viên vào không gian làm việc của mình, đồng thời xác định vai trò và quyền của họ. 
- Vai trò *Quản trị viên* quản lý không gian làm việc và môi trường, đặt cấu hình thông tin chi tiết về mức độ tương tác cho những người dùng khác. 
- Vai trò *Người đóng góp* được chuyển cho các nhà phân tích, những người không cần đặt cấu hình thông tin chi tiết về mức độ tương tác, nhưng muốn tạo các báo cáo, phễu hoặc phân khúc của họ.

## <a name="permissions"></a>Quyền
  
Bảng sau xác định các quyền cho từng vai trò. 

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
