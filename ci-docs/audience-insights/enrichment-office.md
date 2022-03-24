---
title: Làm phong phú hồ sơ khách hàng với dữ liệu từ Microsoft Office 365
description: Sử dụng dữ liệu độc quyền từ Microsoft Office để làm phong phú hồ sơ khách hàng của bạn với dữ liệu tương tác.
ms.date: 12/03/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahl
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 47239bd7f0c89742cf9c673bb2ebe4c41d853233
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376856"
---
# <a name="enrich-customer-profiles-with-engagement-data-preview"></a>Làm phong phú hồ sơ khách hàng bằng dữ liệu tương tác (xem trước)

Sử dụng dữ liệu từ Microsoft Office 365 để làm phong phú thêm hồ sơ tài khoản khách hàng của bạn với thông tin chi tiết về các cam kết thông qua Office 365 ứng dụng. Dữ liệu tương tác bao gồm email và hoạt động cuộc họp, được tổng hợp ở cấp tài khoản. Ví dụ: số lượng email từ tài khoản doanh nghiệp hoặc số cuộc họp với tài khoản. Không có dữ liệu về người dùng cá nhân được cung cấp. 

Tính năng làm giàu này có sẵn ở các khu vực sau: Vương quốc Anh, Châu Âu, Bắc Mỹ.

## <a name="prerequisites"></a>Điều kiện tiên quyết

Để định cấu hình bổ sung, các điều kiện tiên quyết sau phải được đáp ứng:

- Bạn có một hoạt động Office 365 giấy phép đám mây.
- Bạn có [hồ sơ khách hàng hợp nhất](customer-profiles.md) dựa trên [tài khoản doanh nghiệp](work-with-business-accounts.md).
- Môi trường Thông tin chi tiết về khách hàng của bạn phải có [Microsoft Dataverse tổ chức trực thuộc](create-environment.md#step-3-connect-to-microsoft-dataverse).
- Bạn có [người quản lý](permissions.md#admin) quyền.
- Bạn có hoặc có thể nhận được sự đồng ý từ Office 365 quản trị viên thuê để sử dụng Office 365 dữ liệu để cung cấp **Thông tin chi tiết về Tổ chức** trong các ứng dụng Dynamics 365.

## <a name="configure-the-enrichment"></a>Đặt cấu hình dữ liệu tăng cường

1. Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Dữ liệu** > **Tăng cường**.

1. Đi đến **Phát hiện** tab và chọn **Làm phong phú dữ liệu của tôi** trên **Tương tác tài khoản** ngói.

   :::image type="content" source="media/enrichment-office-tile.png" alt-text="Ô tương tác tài khoản.":::
   
1. Lựa chọn **Tiếp theo** bên trong **Tổng quat** bước và nhập địa chỉ email từ tổ chức của bạn mà dữ liệu Office sẽ được tổng hợp. Chỉ dữ liệu từ các địa chỉ email được liệt kê mới được xử lý để liên lạc có liên quan. Một phương pháp hay nhất là sử dụng các nhóm email, ví dụ: *Nhóm bán hàng Hoa Kỳ*, dễ dàng quản lý trong Office 365. Số lượng địa chỉ email trong các nhóm được giải quyết và hiển thị. Tổng số địa chỉ email phải có ít nhất 2 và không được vượt quá 2.500.

   :::image type="content" source="media/enrichment-office-email-addresses.png" alt-text="Địa chỉ email tương tác tài khoản.":::

1. Xem lại tuyên bố đồng ý, chọn **tôi đồng ý** hộp kiểm và chọn **Tiếp theo**.

1. Chọn tập dữ liệu khách hàng và chọn **Tiếp theo**.

1. Ánh xạ trường địa chỉ email liên hệ và chọn **Tiếp theo**.

1. Xem lại cấu hình bổ sung, đặt tên cho bổ sung và chọn **Tiết kiệm làm giàu** để tiết kiệm làm giàu.

## <a name="office-365-tenant-administrator-consent"></a>Office 365 sự đồng ý của quản trị viên người thuê nhà

Sự đồng ý từ một Office 365 Quản trị viên người thuê được yêu cầu để kích hoạt tính năng làm giàu. Một email được gửi đến Office 365 quản trị viên người thuê khi phần bổ sung được lưu, yêu cầu họ xem xét và đồng ý cho phép các ứng dụng Dynamics 365 sử dụng doanh nghiệp của bạn 'Office 365 dữ liệu để cung cấp **Thông tin chi tiết về Tổ chức**. Các Office 365 quản trị viên người thuê cũng có thể đồng ý trực tiếp trong Office 365 bảng điều khiển dành cho quản trị viên, bằng cách chọn **Thông tin chi tiết về Tổ chức**.

## <a name="running-the-enrichment-for-the-first-time"></a>Chạy làm giàu lần đầu tiên

Khi bắt đầu làm giàu lần đầu tiên, sau khi Office 365 quản trị viên người thuê đã đồng ý, dữ liệu tải xuống từ Office 365 bắt đầu. Quá trình này mất một thời gian. Lần chạy làm giàu đầu tiên sẽ được lên kế hoạch diễn ra với độ trễ là sáu giờ. Bạn có thể xem số ngày mà dữ liệu bao gồm trên trang tổng quan về mức độ tương tác với tài khoản sau khi quá trình bổ sung kết thúc. Với khối lượng dữ liệu lớn, hãy chạy lại phần bổ sung sau một vài ngày. Nó đảm bảo dữ liệu đầy đủ trong toàn bộ khoảng thời gian, là một năm.

Để bắt đầu quá trình, hãy chọn **Chạy** trên trang cấu hình tương tác với tài khoản. Ngoài ra, bạn có thể để hệ thống chạy phần bổ sung tự động như một phần của [làm mới theo lịch trình](system.md#schedule-tab). Theo mặc định, phần bổ sung sẽ chạy một lần mỗi tuần.

Tùy thuộc vào kích thước dữ liệu Office của bạn, có thể mất vài giờ để hoàn tất quá trình bổ sung.

Khi bạn chạy phần bổ sung, Microsoft sẽ xử lý dữ liệu trong Office 365 ranh giới tuân thủ để tạo thông tin chi tiết tổng hợp, sau đó được thêm vào môi trường Thông tin chi tiết về khách hàng của bạn. Không có dữ liệu nào ở cấp độ cá nhân (ví dụ: nội dung của bất kỳ email hoặc lời mời lịch nào) được cung cấp cho người dùng Thông tin chi tiết về khách hàng. 

[!INCLUDE [progress-details-pane](../includes/progress-details-pane.md)]

## <a name="enrichment-results"></a>Kết quả tăng cường

Sau khi chạy quá trình làm giàu, hãy chuyển đến **Sự làm giàu của tôi** để xem xét các kết quả làm giàu. Bạn sẽ tìm thấy tổng số khách hàng đã làm giàu và tổng quan về kết quả làm giàu. Nó bao gồm số lượng email và cuộc họp đã xử lý, số ngày mà dữ liệu đã được tổng hợp, v.v.

Bạn cũng sẽ tìm thấy một biểu đồ với số lượng khách hàng đã tăng cường theo thời gian và bản xem trước của dữ liệu làm giàu.  

:::image type="content" source="media/enrichment-office-results-overview.png" alt-text="Xem trước kết quả sau khi chạy quy trình tăng cường.":::

Tất cả dữ liệu được tổng hợp đến cấp tài khoản. Hệ thống tính toán điểm tương tác, nằm trong khoảng từ 0 đến 100, cho mọi tài khoản. Điểm số tương tác cung cấp một thước đo tổng hợp về mức độ tương tác của tài khoản trên các email và cuộc họp liên quan đến các tài khoản khác của bạn. Danh sách sau đây chứa dữ liệu tổng hợp mà hoạt động nâng cao mức độ tương tác tài khoản cung cấp:



| Dữ liệu                                                                              | Tên cột                              |
| :-------------------------------------------------------------------------------- |:---------------------------------------- |
| Điểm tương tác                                                                  |  Điểm tương tác                         |
| Số lượng email đến tài khoản                                                       |  NoOfEmails_ToAccount                    |
| Số lượng email từ tài khoản                                                     |  NoOfEmails_FromAccount                  | 
| Số cuộc họp do tài khoản khởi xướng                                           |  NoOfMeetings_FromAccount                | 
| Số cuộc họp do tổ chức của bạn bắt đầu                                 |  NoOfMeetings_ToAccount                  | 
| Số người từ tổ chức của bạn trong các cuộc họp có tài khoản                  |  NoOfContactsInvolved_Meetings           | 
| Số người từ tổ chức của bạn trong các cuộc trò chuyện qua email với tài khoản       |  NoOfContactsInvolved_Emails             | 
| Số người từ tài khoản trong các cuộc họp với tổ chức của bạn                  |  NoOfAccountContactsInvolved_Meetings    | 
| Số người từ tài khoản trong các cuộc trò chuyện qua email với tổ chức của bạn       |  NoOfAccountContactsInvolved_Emails      | 
| Ngày bắt đầu tương tác (email hoặc cuộc họp đầu tiên trong dữ liệu)                        |  EngagementStartDate                     | 
| Số ngày kể từ email cuối cùng                                                             |  DaysSinceLastEmail                      | 
| Số ngày kể từ lần gặp cuối cùng                                                           |  DaysSinceLastMeeting                    | 
| Thời lượng trung bình của các cuộc họp                                                      |  AverageDuration_Of_Meetings             | 
| Thời lượng trung bình của các email trả lời từ tài khoản                                    |  AverageDuration_Of_AccountEmailReplies  | 
| Ngày bắt đầu tổng hợp                                                            |  AggregationStartDate                    | 
| Mức độ tổng hợp (năm, tháng hoặc tuần)                                          |  AggregationLevel                        | 


Xem lại dữ liệu đã được bổ sung chi tiết bằng cách chọn **Xem thêm** trong phần xem trước. Nó mở ra *Văn phòng* thực thể. Bạn cũng có thể tìm thấy thực thể được liệt kê trong **Làm giàu** nhóm trong **Dữ liệu** > **Các thực thể**. Bạn cũng sẽ tìm thấy *Office_UserEntity*, chứa các ID Active Directory cho các địa chỉ email đã được chọn trong quá trình cấu hình bổ sung 

## <a name="see-enrichment-data-on-the-customer-card"></a>Xem dữ liệu tăng cường trên thẻ khách hàng

Tương tác tài khoản cũng có thể được xem trên thẻ khách hàng cá nhân. Đi đến **Khách hàng** rồi chọn một hồ sơ khách hàng. Trong thẻ khách hàng, bạn sẽ tìm thấy điểm tương tác của tài khoản, tổng số email và tổng số cuộc họp được tổng hợp trong năm qua. Bạn cũng tìm thấy các biểu đồ hiển thị lịch sử email và cuộc họp.

:::image type="content" source="media/enrichment-office-customer-card.png" alt-text="Thẻ khách hàng với dữ liệu tăng cường.":::

## <a name="create-segments-and-measures-based-on-the-enriched-data"></a>Tạo các phân đoạn và thước đo dựa trên dữ liệu đã được bổ sung chi tiết

Dữ liệu đã được bổ sung chi tiết có thể được sử dụng để tạo các phân đoạn và các thước đo như được trình bày chi tiết bên dưới. Ví dụ: một phân khúc chứa tất cả các khách hàng có giá trị trên 60 cho *ngày kể từ email cuối cùng* và *ngày kể từ lần gặp cuối cùng*. Phân đoạn đó chứa các tài khoản cũ mà bạn có thể thử kích hoạt lại. 

## <a name="next-steps"></a>Các bước tiếp theo

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]


[!INCLUDE[footer-include](../includes/footer-banner.md)]
