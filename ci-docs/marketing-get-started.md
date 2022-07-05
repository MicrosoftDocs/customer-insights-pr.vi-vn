---
title: Sử dụng các cấu hình hợp nhất trong Dynamics 365 Marketing
description: Tìm hiểu cách tích hợp các cấu hình và phân đoạn hợp nhất với Dynamics 365 Marketing.
ms.date: 04/20/2022
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 99ec463299a24ea81cfe26bb785e36bdefdcd080
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 06/29/2022
ms.locfileid: "9054458"
---
# <a name="use-unified-customer-profiles-in-dynamics-365-marketing"></a>Sử dụng hồ sơ khách hàng hợp nhất trong Dynamics 365 Marketing

[Tiếp thị Dynamics 365](/dynamics365/marketing/overview) nâng cao trải nghiệm của khách hàng, cho phép bạn sắp xếp các hành trình được cá nhân hóa trên tất cả các điểm tiếp xúc để tăng cường mối quan hệ và kiếm được lòng trung thành. Ứng dụng Tiếp thị Dynamics 365 hoạt động liền mạch với Bán hàng Dynamics 365,Dynamics 365 Customer Insights,Microsoft Teams và các sản phẩm khác, đồng thời cho phép bạn đưa ra quyết định nhanh hơn và tốt hơn bằng cách sử dụng sức mạnh của dữ liệu và AI.

Bằng cách kết nối dữ liệu Thông tin chi tiết về khách hàng với Tiếp thị, bạn có thể:

- Nhắm mục tiêu hồ sơ và phân khúc khách hàng hợp nhất. Điều này cho phép bạn thu hút mọi khách hàng, bất kể vị trí dữ liệu của khách hàng.
- Nội dung động cơ bản (chẳng hạn như mã thông báo được cá nhân hóa) trong email, SMS và thông báo đẩy về các chỉ số như trạng thái khách hàng thân thiết, ngày gia hạn đăng ký, tài khoản mẹ hoặc bất kỳ số đo nào khác mà bạn đã ghi lại trong hồ sơ Thông tin chi tiết về khách hàng thống nhất.
- Tải dữ liệu từ Tiếp thị vào Thông tin chi tiết về khách hàng và kết hợp dữ liệu đó với dữ liệu khách hàng từ các nguồn khác.
- Áp dụng các công cụ làm sạch, làm giàu và đối sánh mờ dữ liệu Thông tin chi tiết về khách hàng.

## <a name="use-rich-customer-profiles-in-real-time-marketing"></a>Sử dụng hồ sơ khách hàng phong phú trong tiếp thị thời gian thực

Tiếp thị thời gian thực cho phép bạn tạo [trình kích hoạt tùy chỉnh](/dynamics365/marketing/real-time-marketing-custom-triggers) khởi động hành trình của khách hàng dựa trên bất kỳ hành động nào của khách hàng. Dữ liệu của bạn càng được cá nhân hóa thì hành trình của bạn càng phù hợp và được cá nhân hóa. Đây là điều làm cho việc kết hợp Tiếp thị và Thông tin chi tiết về khách hàng trở nên mạnh mẽ. Bạn có thể [thống nhất dữ liệu](data-unification.md) từ bất kỳ nguồn nào, sau đó sử dụng nó để cung cấp nhiên liệu cho các hành trình của khách hàng được siêu cá nhân hóa.

Tìm hiểu thêm: [Sử dụng hồ sơ và phân đoạn Thông tin chi tiết về khách hàng trong tiếp thị thời gian thực](/dynamics365/marketing/real-time-marketing-ci-profile)

## <a name="use-unified-segments-with-outbound-customer-journeys"></a>Sử dụng các phân đoạn hợp nhất với hành trình của khách hàng bên ngoài

Thông tin chi tiết về khách hàng cho phép bạn tinh chỉnh dữ liệu từ nhiều nguồn và kết hợp dữ liệu đó thành các phân khúc khách hàng tổng hợp. Qua [kết nối Thông tin chi tiết về khách hàng với tiếp thị ra nước ngoài](export-dynamics365-marketing.md), các phân đoạn này sẽ tự động xuất hiện *và* tự động làm mới trong trình thiết kế hành trình của khách hàng.

Tìm hiểu thêm: [Sử dụng các phân đoạn từ Dynamics 365 Customer Insights với Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)

## <a name="pull-data-from-your-own-azure-data-lake-storage"></a>Lấy dữ liệu từ của riêng bạn Azure Data Lake Storage

Bạn không bị giới hạn dung lượng lưu trữ đám mây nếu muốn sử dụng dữ liệu Thông tin chi tiết về khách hàng với Tiếp thị. Nếu bạn đã có của riêng bạn Azure Data Lake Storage thiết lập, bạn có thể kết nối với Customer Insights, sau đó chia sẻ dữ liệu với ứng dụng Tiếp thị giống như cách bạn làm với thiết lập dựa trên đám mây.

Tìm hiểu thêm: [Bật chia sẻ dữ liệu với Dataverse từ của riêng bạn Azure Data Lake Storage](customer-insights-dataverse.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview)
