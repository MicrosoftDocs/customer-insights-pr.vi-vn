---
title: Sử dụng sự đồng ý của khách hàng
description: Tôn vinh các tùy chọn đồng ý của khách hàng trong Thông tin chi tiết về khách hàng bằng cách nhập dữ liệu về sự đồng ý.
ms.date: 06/07/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 77b09b6eb0a916e724542d503d96d19c5581aca1
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 06/14/2022
ms.locfileid: "8947534"
---
# <a name="use-customer-consent"></a>Sử dụng sự đồng ý của khách hàng

Các quy định về quyền riêng tư và bảo vệ dữ liệu cung cấp cho các cá nhân quyền quản lý cách một tổ chức sử dụng dữ liệu cá nhân của họ. Ví dụ về các quy định như vậy là Quy định chung về bảo vệ dữ liệu ở Liên minh Châu Âu hoặc Đạo luật về quyền riêng tư của người tiêu dùng California ở Hoa Kỳ. Các quy định này cho phép mọi người chọn không tham gia thu thập, xử lý hoặc chia sẻ dữ liệu cá nhân của họ với các bên thứ ba.  

Khách hàng có thể chọn rút lại hoặc từ chối sự đồng ý của họ đối với các hình thức liên hệ cụ thể. Họ cũng có thể yêu cầu bạn không cho họ thu thập, lưu trữ, sử dụng hoặc bán dữ liệu cá nhân của họ. Điều quan trọng là tổ chức của bạn tôn trọng tất cả sự đồng ý và sở thích riêng tư của khách hàng.  

Dynamics 365 Customer Insights giúp bạn đáp ứng các yêu cầu của khách hàng bằng cách nhập và lưu trữ các sở thích của họ như một phần của hồ sơ khách hàng hợp nhất.

Nếu dữ liệu về sự đồng ý được lưu trữ riêng biệt với hồ sơ khách hàng của bạn, [thêm dữ liệu về sự đồng ý của bạn dưới dạng nguồn dữ liệu mới](#import-and-unify-consent-data). Nguồn dữ liệu chứa dữ liệu về sự đồng ý được thêm vào quy trình hợp nhất dữ liệu. Sau đó, việc hợp nhất thành công dữ liệu về sự đồng ý và hồ sơ khách hàng dẫn đến hồ sơ khách hàng hợp nhất có chứa thông tin về sự đồng ý. Đối với hồ sơ khách hàng đã chứa thông tin về sự đồng ý, hãy truy cập trực tiếp vào [sử dụng dữ liệu về sự đồng ý](#use-consent-data) tiết diện.

## <a name="prerequisites"></a>Điều kiện tiên quyết

Thông tin sau phải có sẵn trong dữ liệu nguồn của bạn để thống nhất dữ liệu về sự đồng ý với các hồ sơ khách hàng khác:

- Khóa thay thế để ánh xạ thông tin về sự đồng ý với hồ sơ người dùng trong Thông tin chi tiết về khách hàng. Ví dụ: địa chỉ email hoặc số điện thoại.
- Giá trị đồng ý để xác định trạng thái đồng ý của khách hàng.

Cân nhắc thêm những thứ sau *không bắt buộc* thông tin:

- Khóa chính để cập nhật trạng thái đồng ý nếu khách hàng yêu cầu thay đổi.
- Loại đồng ý, nếu có nhiều cách để xử lý thông tin khách hàng.
- Ngày của sự đồng ý hoặc bất kỳ loại dữ liệu nào khác có liên quan đến các tình huống đồng ý của bạn.

Bảng ví dụ về cơ sở dữ liệu về sự đồng ý đơn giản với nhiều tùy chọn về sự đồng ý:

|ID sự đồng ý (khóa chính)   |Email (khóa thay thế)  |Tùy chọn đồng ý  |Giá trị đồng ý  |
|---------|---------|---------|---------|
|1    |  holly@contoso.com       |  Bản tin       |  Sai       |
|2    |  holly@contoso.com       |  Bản cập nhật sản phẩm       |  Đúng       |
|3    |  frank@contoso.com       |  Bản tin       | Đúng        |
|Tệp 4    |  frank@contoso.com       |  Bản cập nhật sản phẩm       |  Sai       |

## <a name="import-and-unify-consent-data"></a>Nhập và hợp nhất dữ liệu về sự đồng ý

Bạn có thể nhập dữ liệu về sự đồng ý giống như cách bạn nhập các nguồn dữ liệu khác vào Thông tin chi tiết về khách hàng. Để biết thêm thông tin về các nguồn dữ liệu được hỗ trợ và cách nhập chúng, hãy xem [Tổng quan về nguồn dữ liệu](data-sources.md).

Để biết thêm thông tin về việc hợp nhất các nguồn dữ liệu của bạn, hãy xem [Tổng quan về hợp nhất dữ liệu](data-unification.md).

## <a name="use-consent-data"></a>Sử dụng dữ liệu về sự đồng ý

Sau khi dữ liệu về sự đồng ý của bạn là một phần của hồ sơ khách hàng hợp nhất, bạn có thể sử dụng dữ liệu đó trong Thông tin chi tiết về khách hàng. Ví dụ: tạo một phân đoạn có quy tắc để đảm bảo rằng bạn tôn trọng quyền riêng tư và các tùy chọn bảo vệ dữ liệu của khách hàng. Các quy tắc hỗ trợ tùy chọn đồng ý được sử dụng để loại trừ người dùng khỏi một phân khúc dựa trên các thuộc tính hồ sơ. Thêm quy tắc vào một phân đoạn loại trừ hồ sơ khách hàng không cung cấp sự đồng ý để liên hệ.

Tham chiếu đến bảng mẫu ở trên, một phân đoạn có thể chứa quy tắc sau:`Consent option=Newsletter & Consent value=True`. Cấu hình này dẫn đến một phân đoạn tôn trọng các tùy chọn liên hệ để gửi bản tin.

Để biết thêm thông tin về phân đoạn xây dựng, hãy xem [Tạo phân đoạn](segment-builder.md).

Khi phân đoạn được tạo, bạn có thể sử dụng một trong nhiều [tùy chọn xuất khẩu](export-destinations.md) để sử dụng phân đoạn trong các ứng dụng khác.

## <a name="ensure-updated-consent-status"></a>Đảm bảo cập nhật trạng thái đồng ý

Điều quan trọng là phải cập nhật trạng thái đồng ý cho khách hàng của bạn. Làm mới theo lịch trình trong Thông tin chi tiết về khách hàng luôn nhập trạng thái mới nhất của các nguồn dữ liệu của bạn. Thông tin này sau đó được xử lý thông qua thống nhất dữ liệu và dẫn đến hồ sơ khách hàng được cập nhật. Sau đó, các cấu hình cập nhật này được sử dụng để làm mới các phân đoạn nhằm đảm bảo rằng bạn làm việc với thông tin cập nhật nhất.

Nói cách khác, hãy đảm bảo dữ liệu nguồn được nhập vào Thông tin chi tiết về khách hàng luôn có thông tin mới nhất.

Để biết thêm thông tin, hãy xem [Làm mới các phân đoạn theo cách thủ công](segments.md#refresh-segments) hoặc [định cấu hình làm mới theo lịch trình](system.md#schedule-tab).
