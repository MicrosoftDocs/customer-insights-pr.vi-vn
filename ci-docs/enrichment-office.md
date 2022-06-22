---
title: Làm phong phú hồ sơ khách hàng với dữ liệu từ Microsoft Office 365
description: Sử dụng dữ liệu độc quyền từ Microsoft Office để làm phong phú hồ sơ khách hàng của bạn với dữ liệu tương tác.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahl
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 7192b7680e73a581dd603de174c57b20bec996dd
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 06/13/2022
ms.locfileid: "8954159"
---
# <a name="enrich-customer-profiles-with-engagement-data-preview"></a>Làm phong phú hồ sơ khách hàng bằng dữ liệu tương tác (xem trước)

Sử dụng dữ liệu từ Microsoft Office 365 để làm phong phú thêm hồ sơ tài khoản khách hàng của bạn với thông tin chi tiết về các cam kết thông qua Office 365 ứng dụng. Dữ liệu tương tác bao gồm email và hoạt động cuộc họp, được tổng hợp ở cấp tài khoản. Ví dụ: số lượng email từ tài khoản doanh nghiệp hoặc số cuộc họp với tài khoản. Không có dữ liệu về người dùng cá nhân được cung cấp.

## <a name="supported-countries-or-regions"></a>Các quốc gia hoặc khu vực được hỗ trợ

Chúng tôi hiện hỗ trợ các khu vực sau: Vương quốc Anh, Châu Âu, Bắc Mỹ.

## <a name="prerequisites"></a>Điều kiện tiên quyết

- Một hoạt động Office 365 giấy phép đám mây.
- [Hồ sơ khách hàng hợp nhất](customer-profiles.md) dựa trên [tài khoản doanh nghiệp](work-with-business-accounts.md).
- Một [Microsoft Dataverse tổ chức trực thuộc](create-environment.md#step-3-connect-to-microsoft-dataverse) trong môi trường Thông tin chi tiết về khách hàng của bạn.
- [Người quản lý](permissions.md#admin) quyền.
- Sự đồng ý từ bạn Office 365 quản trị viên thuê để sử dụng Office 365 dữ liệu để cung cấp **Thông tin chi tiết về Tổ chức** trong các ứng dụng Dynamics 365.

## <a name="configure-the-enrichment"></a>Đặt cấu hình dữ liệu tăng cường

1. Đi đến **Dữ liệu** > **Tăng cường** rồi chọn tab **Khám phá**.

1. Lựa chọn **Làm phong phú dữ liệu của tôi** trên **Tương tác tài khoản** ngói.

   :::image type="content" source="media/enrichment-office-tile.png" alt-text="Ô tương tác tài khoản.":::

1. Xem lại tổng quan và sau đó chọn **Tiếp theo**.

1. Nhập địa chỉ email từ tổ chức của bạn mà dữ liệu Office sẽ được tổng hợp. Chỉ dữ liệu từ các địa chỉ email được liệt kê mới được xử lý để liên lạc có liên quan. Một phương pháp hay nhất là sử dụng các nhóm email, ví dụ: *Nhóm bán hàng Hoa Kỳ*, mà bạn có thể quản lý trong Office 365. Số lượng địa chỉ email trong các nhóm được giải quyết và hiển thị. Tổng số địa chỉ email phải có ít nhất 2 và không được vượt quá 2.500.

   :::image type="content" source="media/enrichment-office-email-addresses.png" alt-text="Địa chỉ email tương tác tài khoản.":::

1. Xem xét và cung cấp sự đồng ý của bạn cho [Office 365 sự đồng ý của quản trị viên người thuê nhà](#office-365-tenant-administrator-consent) bằng việc lựa chọn **tôi đồng ý**.

1. Chọn **Tiếp theo**.

1. Chọn **Tập dữ liệu liên hệ** và chọn hồ sơ bạn muốn làm phong phú. Chọn **Tiếp theo**.

1. Ánh xạ trường địa chỉ email liên hệ và chọn **Tiếp theo**.

1. Cung cấp một **Tên** để làm giàu và **Thực thể đầu ra**.

1. Chọn **Lưu dữ liệu tăng cường** sau khi xem xét các lựa chọn của bạn.

1. Lựa chọn **Đóng** để trở lại **Làm giàu** trang.

### <a name="office-365-tenant-administrator-consent"></a>Office 365 sự đồng ý của quản trị viên người thuê nhà

Sự đồng ý từ một Office 365 Quản trị viên người thuê được yêu cầu để kích hoạt tính năng làm giàu. Một email được gửi đến Office 365 quản trị viên người thuê khi phần bổ sung được lưu, yêu cầu họ xem xét và đồng ý cho phép các ứng dụng Dynamics 365 sử dụng doanh nghiệp của bạn 'Office 365 dữ liệu để cung cấp **Thông tin chi tiết về Tổ chức**. Các Office 365 quản trị viên người thuê cũng có thể đồng ý trực tiếp trong Office 365 bảng điều khiển dành cho quản trị viên, bằng cách chọn **Thông tin chi tiết về Tổ chức**.

## <a name="running-the-enrichment-for-the-first-time"></a>Chạy làm giàu lần đầu tiên

Khi bắt đầu làm giàu lần đầu tiên, sau khi Office 365 quản trị viên người thuê đã đồng ý, dữ liệu tải xuống từ Office 365 bắt đầu. Quá trình này mất một thời gian. Lần chạy làm giàu đầu tiên sẽ được lên kế hoạch diễn ra với độ trễ là sáu giờ. Bạn có thể xem số ngày mà dữ liệu bao gồm trên trang tổng quan về mức độ tương tác với tài khoản sau khi kết thúc quá trình bổ sung. Với khối lượng dữ liệu lớn, hãy chạy lại phần bổ sung sau một vài ngày. Nó đảm bảo dữ liệu đầy đủ trong toàn bộ khoảng thời gian, là một năm.

Tùy thuộc vào kích thước dữ liệu Office của bạn, có thể mất vài giờ để hoàn tất quá trình bổ sung.

Khi bạn chạy phần bổ sung, Microsoft sẽ xử lý dữ liệu trong Office 365 ranh giới tuân thủ để tạo thông tin chi tiết tổng hợp, sau đó được thêm vào môi trường Thông tin chi tiết về khách hàng của bạn. Không có dữ liệu nào ở cấp độ cá nhân (ví dụ: nội dung của bất kỳ email hoặc lời mời lịch nào) được cung cấp cho người dùng Thông tin chi tiết về khách hàng.

Lựa chọn **Chạy** để bắt đầu quá trình làm giàu.

[!INCLUDE [progress-details-pane](includes/progress-details-pane.md)]

## <a name="enrichment-results"></a>Kết quả tăng cường

[!INCLUDE [enrichment-results](includes/enrichment-results.md)] Đây là *Văn phòng* thực thể. Các *Office_UserEntity* chứa các ID Active Directory cho các địa chỉ email đã được chọn trong quá trình cấu hình bổ sung.

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

## <a name="see-enrichment-data-on-the-customer-card"></a>Xem dữ liệu tăng cường trên thẻ khách hàng

Tương tác tài khoản cũng có thể được xem trên thẻ khách hàng cá nhân. Đi đến **Khách hàng** rồi chọn một hồ sơ khách hàng. Trong thẻ khách hàng, bạn sẽ tìm thấy điểm tương tác của tài khoản, tổng số email và tổng số cuộc họp được tổng hợp trong năm qua. Bạn cũng tìm thấy các biểu đồ hiển thị email và lịch sử cuộc họp.

:::image type="content" source="media/enrichment-office-customer-card.png" alt-text="Thẻ khách hàng với dữ liệu tăng cường.":::

## <a name="next-steps"></a>Các bước tiếp theo

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]
Ví dụ: một phân khúc chứa tất cả các khách hàng có giá trị trên 60 cho *ngày kể từ email cuối cùng* và *ngày kể từ lần gặp cuối cùng*. Phân đoạn đó chứa các tài khoản cũ mà bạn có thể thử kích hoạt lại.

[!INCLUDE [footer-include](includes/footer-banner.md)]
