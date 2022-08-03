---
title: Cá nhân hóa trải nghiệm của bạn với dữ liệu về người dùng đã biết và chưa biết
description: Kết hợp thông tin về những người dùng chưa biết trước đây khi bạn biết danh tính của họ.
ms.date: 07/07/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: ff99721bef0004bc8cae1ec14ff9df16cbb0682e
ms.sourcegitcommit: ece8ff732490ecd3b3421ab273f331e6fd46a7f7
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 07/19/2022
ms.locfileid: "9173829"
---
# <a name="personalize-your-experiences-with-data-about-known-and-unknown-users"></a>Cá nhân hóa trải nghiệm của bạn với dữ liệu về người dùng đã biết và chưa biết

Quản lý dữ liệu khách hàng không phải là một thách thức mới, nhưng nó ngày càng trở nên khó khăn hơn khi người dùng điều hướng các kênh kỹ thuật số khác nhau mà các thương hiệu cung cấp. Người dùng được biết đến (được xác thực) trong một kênh này sẽ trở thành không xác định (chưa được xác thực) trong kênh khác nếu không đăng nhập. Vấn đề thường gặp là người dùng chưa được xác thực (không xác định) không có ID chung. Nó có thể được sử dụng để liên kết các thuộc tính hồ sơ có ý nghĩa và tạo hồ sơ khách hàng hợp nhất. Thông tin chi tiết về khách hàng giúp giải quyết vấn đề này bằng cách nhập dữ liệu từ các phương pháp theo dõi trên hệ thống nguồn của bạn. Các hồ sơ chưa biết và đã biết hợp nhất cung cấp cho các tổ chức cái nhìn đầy đủ về hồ sơ cập nhật và các giao dịch, hành vi và nhân khẩu học lịch sử của họ. Nó thậm chí còn tiến một bước xa hơn bằng cách cung cấp giải pháp nhận dạng cho phép bạn thống nhất hoạt động của khách hàng trên nhiều kênh, bao gồm trang web của bạn, mua hàng tại cửa hàng, các chương trình khách hàng thân thiết, v.v.

## <a name="sample-scenario"></a>Kịch bản mẫu

Hãy nghĩ về một chuỗi cà phê, có một lượng khách hàng lớn mua cà phê và thức ăn tại các cửa hàng và đặt hàng trực tuyến. Thông thường, khách truy cập trực tuyến không được xác thực khi duyệt các sản phẩm, khiến họ trở thành "người dùng không xác định". Rất khó để chuỗi cà phê cung cấp các ưu đãi và trải nghiệm được cá nhân hóa nếu người dùng không biết. Mặt khác, khách hàng có thể đăng nhập vào tài khoản của họ và trở thành "người dùng được biết đến" đối với công ty bằng cách tham gia hệ thống khách hàng thân thiết, từ đó cho phép nhiều trải nghiệm được cá nhân hóa hơn. Thông tin chi tiết về khách hàng có thể giúp chuỗi cà phê có được thông tin chi tiết về những người dùng đã biết và chưa biết trước đây.

Với Thông tin chi tiết về khách hàng, công ty có thể kết hợp hồ sơ khách hàng với dữ liệu hoạt động từ các phiên chưa được xác thực (không xác định) sau khi người dùng đăng nhập và được biết đến. Chuỗi cà phê có thể đưa dữ liệu từ các nguồn dữ liệu khác bằng cách sử dụng các trình kết nối tích hợp vào Thông tin chi tiết về khách hàng để hợp nhất danh tính cho khách hàng từ nhiều kênh khác nhau.

## <a name="prerequisites"></a>Điều kiện tiên quyết

- Dữ liệu web được thu thập và chứa "ID khách truy cập" cho tất cả khách truy cập.
- Dữ liệu web chứa "ID người dùng đã được xác thực" cho khách truy cập đã đăng nhập. Các ID này được liên kết với hệ thống khách hàng thân thiết.
- Dữ liệu sự kiện có giá trị cao như "Chế độ xem sản phẩm" và "Thanh toán" được xác định và đưa vào dữ liệu nguồn cùng với dấu thời gian của sự kiện và ID sự kiện.

Bảng sau đây cho thấy một ví dụ đơn giản về cách các sự kiện web có giá trị cao có thể được ghi lại.

|EventID|EventTimeStamp|Tên người dùng|ID trung thành|EventName|
|--|--|--|--|--|
|1|07-23-2022 10:00:00|abc123|--|Xem sản phẩm|
|2|07-23-2022 10:05:00|abc123|707|Đăng nhập mức độ trung thành|
|3|07-23-2022 10:10:00|abc123|707|Kiểm xuất|
|Tệp 4|07-23-2022 10:20:00|xyz789|--|Xem sản phẩm|

## <a name="data-ingestion"></a>Nhập dữ liệu

Dữ liệu về khách hàng có thể bắt nguồn từ trang web của bạn dưới dạng dữ liệu sự kiện và nó có thể được lưu trữ trong các dịch vụ phân tích dữ liệu nội bộ hoặc bên thứ ba của riêng bạn. Dữ liệu web chứa người dùng đã biết và chưa biết nếu trang web có luồng xác thực tích hợp với dịch vụ xác thực. Ví dụ: hệ thống Thương mại điện tử yêu cầu người dùng cung cấp thông tin chi tiết đầy đủ của họ để hoàn tất giao dịch mua hàng. Hoặc một hệ thống khách hàng thân thiết yêu cầu xác thực để xác nhận người nhận hợp lệ phần thưởng giảm giá.

Dữ liệu sự kiện trong ví dụ của chúng tôi ở trên chứa các ID hồ sơ riêng biệt của những người dùng đã biết và chưa biết. Trong trường hợp 1 và 4, người dùng không xác định trong khi trong trường hợp 2 và 3, người dùng có ID abc123 đăng ký chương trình khách hàng thân thiết.

:::image type="content" source="media/website-data-source.png" alt-text="Các nguồn dữ liệu bao gồm trang web Contoso.":::

Để biết thêm thông tin về các tùy chọn có sẵn để nhập dữ liệu, hãy xem [Tổng quan về nguồn dữ liệu](data-sources.md).

## <a name="data-unification"></a>Hợp nhất dữ liệu

Việc kết hợp danh tính chưa biết với danh tính đã biết giúp kích hoạt cá nhân hóa dựa trên hành vi của người dùng, bất kể trạng thái hồ sơ của họ (đã biết hay chưa biết). Nội dung được cá nhân hóa cho tất cả người dùng giúp khách hàng nhanh chóng nhận được các sản phẩm hoặc dịch vụ phù hợp nhất mà họ quan tâm tại thời điểm đó.

Vì một số người dùng trong dữ liệu của chúng tôi được biết đến, chúng tôi có thể sử dụng Thông tin chi tiết về khách hàng để kết hợp dữ liệu đó với hồ sơ của người dùng. Để biết thêm thông tin về việc hợp nhất hồ sơ khách hàng, hãy xem [Tổng quan về hợp nhất dữ liệu](data-unification.md).

1. Chọn các trường nguồn từ thực thể dữ liệu web. Sử dụng dữ liệu hồ sơ được lưu trữ trong dữ liệu web của bạn và chọn các trường đại diện cho Id với dữ liệu nhân khẩu học.

   :::image type="content" source="media/website-source-fields.png" alt-text="Các trường nguồn cho web nguồn dữ liệu.":::

1. Thêm quy tắc để hợp nhất các bản ghi trùng lặp. Đối với dữ liệu web, hãy chọn dữ liệu được lấp đầy nhất.

1. Định cấu hình các quy tắc và điều kiện đối sánh. Dữ liệu sự kiện cấu hình web trong ví dụ này sẽ được khớp trên ID với cấu hình từ các nguồn dữ liệu khác có chứa thông tin khách hàng. Thiết lập quy tắc đối sánh chính xác trên ID dưới dạng quy tắc riêng biệt với từng thực thể hồ sơ khác có khóa chính hoặc đối sánh ID tương ứng. Trong ví dụ này, dữ liệu hồ sơ sự kiện web được sử dụng làm đối tượng phù hợp cuối cùng để dữ liệu hồ sơ khác được kết hợp trước.
   1. Không kiểm tra **Bao gồm tất cả các bản ghi** tạo hồ sơ hợp nhất cho những người dùng đã biết và bao gồm các ID người dùng không xác định tương ứng của họ. Nó hữu ích trong các tình huống khi bạn quan tâm đến việc xem các hoạt động hành vi trong quá khứ của những người dùng đã biết khi họ vẫn chưa biết.
   1. Kiểm tra **Bao gồm tất cả các bản ghi** tạo các bản ghi hồ sơ riêng biệt cho những người dùng không xác định. Người dùng không xác định nhận được một ID khách hàng duy nhất. Trong tương lai khi một hồ sơ đã biết được liên kết trong dữ liệu hồ sơ sự kiện web, thì hành trình của người dùng mới được biết có thể được xem và sử dụng để cá nhân hóa dựa trên dữ liệu hành vi chưa biết trước đây.

:::image type="content" source="media/website-match-rule.png" alt-text="Đối sánh quy tắc cho thực thể nguồn dữ liệu của trang web.":::

## <a name="get-insights"></a>Tải thông tin chuyên sâu

Nếu hồ sơ khách hàng được tạo cho người dùng chưa biết và đã biết, thì dữ liệu sự kiện web có giá trị cao có thể được sử dụng làm [các hoạt động](activities.md). Những hoạt động này có thể được sử dụng để tạo thêm thông tin chi tiết. Ví dụ: những khách hàng đã truy cập một trang web sáu tháng trước (khi họ vẫn chưa được biết đến) hoặc những khách hàng không có ID khách hàng thân thiết sẽ không bao giờ hoàn tất thanh toán.

:::image type="content" source="media/website-known-unknown.png" alt-text="Ảnh chụp màn hình của trang khách hàng với những khách hàng đã biết và chưa biết.":::

[Làm giàu](enrichment-hub.md) dữ liệu của bạn, xây dựng [đo](measures.md) và tạo [phân đoạn](segments.md) để kích hoạt thêm.

Ví dụ: bạn có thể tạo phân đoạn người dùng đã biết đã xem một số sản phẩm nhưng chưa bao giờ hoàn thành thanh toán.

Để biết thêm thông tin, hãy xem [Tổng quan về phân đoạn](segments.md).

## <a name="activate-insights"></a>Kích hoạt thông tin chi tiết

Có một số cách để xuất dữ liệu của bạn và thực hiện hành động dựa trên thông tin chi tiết cơ bản.

Để biết thêm thông tin, hãy xem [Tổng quan về xuất khẩu](export-destinations.md).
