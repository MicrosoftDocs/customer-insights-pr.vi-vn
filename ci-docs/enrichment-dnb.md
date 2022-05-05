---
title: Làm giàu hồ sơ công ty với Dun & Bradstreet
description: Thông tin chung về cách làm giàu của bên thứ ba Dun & Bradstreet.
ms.date: 04/26/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: ecbbf2c94020bf395f4eb70a99a63cea335af2dd
ms.sourcegitcommit: cf74b8c20d88eb96e1ac86e18cd44fe27aad5ab9
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 04/28/2022
ms.locfileid: "8653806"
---
# <a name="enrichment-of-company-profiles-with-dun--bradstreet-preview"></a>Làm giàu hồ sơ công ty với Dun & Bradstreet (xem trước)

Dun & Bradstreet cung cấp dữ liệu thương mại, số liệu phân tích và thông tin chi tiết cho các doanh nghiệp. Công ty này hỗ trợ hồ sơ khách hàng hợp nhất cho các công ty để tăng cường dữ liệu của họ. Sự phong phú bao gồm các thuộc tính như số DUNS, quy mô công ty, vị trí, ngành, v.v.

## <a name="prerequisites"></a>Điều kiện tiên quyết

Để định cấu hình làm giàu Dun & Bradstreet, bạn phải đáp ứng các điều kiện tiên quyết sau:

- Bạn có một hoạt động [Dun & Bradstreet](https://www.dnb.com/marketing/media/give-your-data-a-boost.html?source=microsoft_audience_insights) giấy phép.
- Bạn có [hồ sơ khách hàng hợp nhất](customer-profiles.md) cho các công ty.
- A Dun & Bradstreet [sự liên quan](connections.md) được định cấu hình bởi quản trị viên. Bạn có thể tạo nó nếu bạn có [người quản lý](permissions.md#admin) quyền và thông tin xác thực từ Dun & Bradstreet Connect. 

## <a name="setting-up-your-dun--bradstreet-project"></a>Thiết lập dự án Dun & Bradstreet của bạn

Là người dùng được cấp phép của Dun & Bradstreet, bạn có thể thiết lập một dự án trong [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights). 


1. đăng nhập vào [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights). Để truy xuất thông tin đăng nhập, [khôi phục mật khẩu của bạn](https://sso.dnb.com/signin/forgot-password?lead_source=microsoft_audienceinsights).

1. Tải xuống [tệp mẫu csv của chúng tôi](https://c360devenrichment.blob.core.windows.net/mapping/DnBCIdatamapping.csv) sẽ được sử dụng để ánh xạ các trường thông tin chi tiết về đối tượng với các trường Dun & Bradstreet tương ứng. 

1. Tải lên tệp trong **Tải dữ liệu lên** bước của trải nghiệm tạo dự án Dun & Bradstreet. 

1. Chọn các dấu chấm ngang dưới liên quan **nguồn** trong dự án Dun & Bradstreet mới được tạo để xem các tùy chọn có sẵn.

   :::image type="content" source="media/enrichment-dnb-dots.png" alt-text="Ảnh chụp màn hình các chấm trong một dự án Dun & Bradstreet.":::

1. Chọn **Nhận thông tin chi tiết về S3**. Lưu trữ thông tin này ở một nơi an toàn. Bạn sẽ cần nó để [thiết lập kết nối để làm giàu](#configure-a-connection-for-dun--bradstreet) trong thông tin chi tiết về khán giả. 

   :::image type="content" source="media/enrichment-dnb-s3info.png" alt-text="Ảnh chụp màn hình lựa chọn thông tin s3 trong một dự án Dun & Bradstreet.":::



## <a name="configure-the-enrichment"></a>Đặt cấu hình dữ liệu tăng cường

1. Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Dữ liệu** > **Tăng cường**.

1. Lựa chọn **Làm phong phú dữ liệu của tôi** trên ô Dun & Bradstreet và chọn **Bắt đầu**.

   :::image type="content" source="media/enrichment-dnb-tile.png" alt-text="Ảnh chụp màn hình lát gạch Dun & Bradstreet.":::

1. Chọn một [kết nối](connections.md) từ danh sách thả xuống. Liên hệ với quản trị viên nếu không có kết nối. Nếu bạn là quản trị viên, bạn có thể tạo kết nối. Lựa chọn **Thêm kết nối** và lựa chọn **Dun & Bradstreet**. 

1. Lựa chọn **Kết nối với Dun & Bradstreet** để xác nhận kết nối.

1. Lựa chọn **Kế tiếp** và chọn **Tập dữ liệu khách hàng** bạn muốn làm giàu với dữ liệu công ty từ Dun & Bradstreet. Bạn có thể chọn **Khách hàng** thực thể để làm phong phú tất cả hồ sơ khách hàng của bạn hoặc chọn một thực thể phân khúc để chỉ làm phong phú thêm hồ sơ khách hàng hợp nhất có trong phân khúc đó.

1. Lựa chọn **Kế tiếp** và xác định trường nào từ hồ sơ hợp nhất của bạn được sử dụng để tìm kiếm dữ liệu công ty phù hợp từ Dun & Bradstreet. Hoặc **Số DUNS** hoặc **Tên công ty** và **Quốc gia** Mục này bắt buộc. Trường quốc gia hỗ trợ [mã quốc gia hai hoặc ba chữ cái](https://www.iso.org/iso-3166-country-codes.html), tên quốc gia bằng tiếng Anh, tên quốc gia bằng ngôn ngữ mẹ đẻ và tiền tố số điện thoại. Một số biến thể quốc gia phổ biến bao gồm:

   * Hoa Kỳ: Hợp chủng quốc Hoa Kỳ, Hoa Kỳ, Hoa Kỳ, Hoa Kỳ.
   * CA: Canada.
   * GB: Vương quốc Anh, Vương quốc Anh, Vương quốc Anh, GB, Vương quốc Liên hiệp Anh và Bắc Ireland, Vương quốc Liên hiệp Anh.
   * AU: Australia, Khối thịnh vượng chung Australia.
   * FR: Pháp, Cộng hòa Pháp.
   * DE: Đức, Đức, Deutschland, Allemagne, Cộng hòa Liên bang Đức, Cộng hòa Đức.

   :::image type="content" source="media/enrichment-dnb-mapping.png" alt-text="Ngăn ánh xạ trường Dun & Bradstreet.":::

1. Chọn **Tiếp** để hoàn thành quá trình ánh xạ trường.

1. Đặt tên cho dữ liệu tăng cường rồi chọn **Lưu dữ liệu tăng cường** sau khi xem xét các lựa chọn của bạn.


## <a name="configure-a-connection-for-dun--bradstreet"></a>Định cấu hình kết nối cho Dun & Bradstreet 

Bạn cần phải là quản trị viên thì mới có thể định cấu hình kết nối. Lựa chọn **Thêm kết nối** khi định cấu hình làm giàu *hoặc* đi đến **Quản trị viên** > **Kết nối** và chọn **Thiết lập** trên ngói Dun & Bradstreet.

1. Chọn **Bắt đầu**. 

1. Nhập tên cho kết nối trong hộp **Tên hiển thị**.

1. Cung cấp thông tin đăng nhập Dun & Bradstreet hợp lệ và chi tiết dự án Dun & Bradstreet *Khu vực, đường dẫn thư mục Drop và tên thư mục Drop*. Bạn [lấy thông tin này](#setting-up-your-dun--bradstreet-project) từ dự án Dun & Bradstreet.

1. Xem xét và chấp thuận **Quyền riêng tư dữ liệu và sự tuân thủ** bằng cách chọn **Tôi đồng ý**.

1. Chọn **Xác minh** để xác thực cấu hình.

1. Sau khi hoàn thành xác minh, hãy chọn **Lưu**.
   
   :::image type="content" source="media/enrichment-dnb-connection.png" alt-text="Trang cấu hình kết nối Dun & Bradstreet.":::

## <a name="enrichment-results"></a>Kết quả tăng cường

Sau khi làm mới dữ liệu tăng cường, bạn có thể xem xét dữ liệu công ty mới được bổ sung trong phần [Dữ liệu tăng cường của tôi](enrichment-hub.md). Bạn có thể tìm thấy thời điểm cập nhật gần đây nhất và số lượng hồ sơ tăng cường.

Bạn có thể truy cập dạng xem chi tiết của từng hồ sơ được tăng cường dữ liệu bằng cách chọn **Xem dữ liệu tăng cường**.

## <a name="next-steps"></a>Các bước tiếp theo

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Quyền riêng tư về dữ liệu và sự tuân thủ

Khi bạn bật Dynamics 365 Customer Insights để truyền dữ liệu đến Dun & Bradstreet, bạn cho phép chuyển dữ liệu ra bên ngoài ranh giới tuân thủ đối với Dynamics 365 Customer Insights, bao gồm dữ liệu nhạy cảm tiềm ẩn như Dữ liệu cá nhân. Microsoft sẽ chuyển những dữ liệu đó theo chỉ dẫn của bạn, nhưng bạn có trách nhiệm đảm bảo rằng Dun & Bradstreet đáp ứng mọi nghĩa vụ về quyền riêng tư hoặc bảo mật mà bạn có thể có. Để biết thêm thông tin, hãy xem [Tuyên bố về Quyền riêng tư của Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Quản trị viên Dynamics 365 Customer Insights của bạn có thể loại bỏ dịch vụ tăng cường này bất kỳ lúc nào để ngừng sử dụng tính năng đó.


[!INCLUDE[footer-include](includes/footer-banner.md)]
