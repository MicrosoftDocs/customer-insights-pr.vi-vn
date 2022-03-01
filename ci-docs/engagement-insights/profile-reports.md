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
ms.openlocfilehash: 3aa9599fc780098a2f7f31f0210d76ed2ef27ece774dd6212b5cb2a599ad537e
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033978"
---
# <a name="out-of-box-profile-reports"></a>Báo cáo hồ sơ có sẵn

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Báo cáo là một tập hợp các hình ảnh trực quan hóa dữ liệu giúp bạn hiểu về hành vi của người dùng. Bằng cách kết nối với thông tin chuyên sâu về đối tượng của Customer Insights, thông tin chuyên sâu về tương tác có thể hiển thị báo cáo với thông tin về hồ sơ khách hàng hợp nhất. Báo cáo này bao gồm số lượng hồ sơ bạn có, được nhóm theo giới tính, độ tuổi và vị trí địa lý.

## <a name="prerequisites"></a>Điều kiện tiên quyết

Môi trường thông tin chuyên sâu về đối tượng phải lưu trữ dữ liệu trong tài khoản Azure Data Lake Storage do khách hàng quản lý.

Nếu bạn đang sử dụng phiên bản thử nghiệm của chức năng thông tin chuyên sâu về đối tượng hoặc môi trường trong hồ dữ liệu do Customer Insights quản lý, [hãy liên hệ với chúng tôi](https://go.microsoft.com/fwlink/?linkid=2145734) để được hỗ trợ.  


## <a name="enable-the-customer-profile-report"></a>Kích hoạt báo cáo hồ sơ khách hàng

Quản trị viên môi trường phải [tạo kết nối với thông tin chuyên sâu về đối tượng](configure-connections.md).

Sau khi chỉ định chi tiết kết nối, quản trị viên có thể cấp quyền truy cập cho những người khác trong tổ chức để xem báo cáo. Quản trị viên môi trường thiết lập kết nối tự động có quyền truy cập tự động vào báo cáo. 

Sau khi hoàn tất kết nối, tính năng **Hồ sơ** sẽ có sẵn trong ngăn điều hướng bên trái. 

- Chuyển đến **Khám phá** > **Hồ sơ** để xem báo cáo.

Báo cáo **Hồ sơ** chứa các hình ảnh trực quan về giới tính, độ tuổi và vị trí địa lý của hồ sơ khách hàng được kết nối.

:::image type="content" source="media/customer-profiles.png" alt-text="Báo cáo hồ sơ khách hàng.":::

[!INCLUDE[footer-include](../includes/footer-banner.md)]