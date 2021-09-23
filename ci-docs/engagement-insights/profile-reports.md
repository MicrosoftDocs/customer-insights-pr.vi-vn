---
title: Kích hoạt báo cáo hồ sơ có sẵn
description: Cách tạo báo cáo hồ sơ có sẵn được nhóm theo giới tính, độ tuổi và hạt hoặc khu vực xuất xứ.
author: darrinw-docs
ms.reviewer: mhart
ms.author: darrinw
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: bf2ec67c9fb99918b87841d3c0b131934e31b58b
ms.sourcegitcommit: 0ceb46c4f57ab49d3a2ebb1c8a816bbafe979e3d
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 09/09/2021
ms.locfileid: "7486146"
---
# <a name="out-of-box-profile-reports"></a>Báo cáo hồ sơ có sẵn

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Báo cáo là một tập hợp các hình ảnh trực quan hóa dữ liệu giúp bạn hiểu về hành vi của người dùng. Bằng cách kết nối với thông tin chi tiết về đối tượng của Customer Insights, thông tin chi tiết về tương tác có thể hiển thị báo cáo với thông tin về hồ sơ khách hàng hợp nhất. Báo cáo này bao gồm số lượng hồ sơ bạn có, được nhóm theo giới tính, độ tuổi và vị trí địa lý.

## <a name="prerequisites"></a>Điều kiện tiên quyết

Môi trường thông tin chi tiết về đối tượng phải lưu trữ dữ liệu trong tài khoản Azure Data Lake Storage do khách hàng quản lý.

Nếu bạn đang sử dụng phiên bản thử nghiệm của chức năng thông tin chi tiết về đối tượng hoặc môi trường trong hồ dữ liệu do Customer Insights quản lý, [hãy liên hệ với chúng tôi](https://go.microsoft.com/fwlink/?linkid=2145734) để được hỗ trợ.  


## <a name="enable-the-customer-profile-report"></a>Kích hoạt báo cáo hồ sơ khách hàng

Quản trị viên môi trường phải [liên kết thông tin chi tiết về mức độ tương tác và thông tin chi tiết về đối tượng](integrate-audience-insights-engagement-insights.md).

Sau khi chỉ định chi tiết kết nối, quản trị viên có thể cấp quyền truy cập cho những người khác trong tổ chức để xem báo cáo. Quản trị viên môi trường thiết lập kết nối tự động có quyền truy cập tự động vào báo cáo. 

Sau khi hoàn tất kết nối, tính năng **Hồ sơ** sẽ có sẵn trong ngăn điều hướng bên trái. 

- Chuyển đến **Khám phá** > **Hồ sơ** để xem báo cáo.

Báo cáo **Hồ sơ** chứa các hình ảnh trực quan về giới tính, độ tuổi và vị trí địa lý của hồ sơ khách hàng được kết nối.

:::image type="content" source="media/customer-profiles.png" alt-text="Báo cáo hồ sơ khách hàng.":::

[!INCLUDE[footer-include](../includes/footer-banner.md)]