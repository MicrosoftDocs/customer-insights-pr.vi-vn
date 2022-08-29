---
title: Tạo một hồ sơ liên hệ thống nhất (xem trước)
description: Thực hiện quy trình hợp nhất dữ liệu để tạo một tập dữ liệu chính duy nhất về các địa chỉ liên hệ.
ms.date: 08/12/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: overview
author: Scott-Stabbert
ms.author: sstabbert
manager: shellyha
searchScope:
- ci-map
- ci-match
- ci-merge
- customerInsights
ms.openlocfilehash: 721f47563582a94b5b8244ca5d5d7d1350695512
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 08/16/2022
ms.locfileid: "9305089"
---
# <a name="create-a-unified-contact-profile-preview"></a>Tạo một hồ sơ liên hệ thống nhất (xem trước)

Sau [hợp nhất các tài khoản kinh doanh](map-entities.md), bạn có thể tùy chọn hợp nhất danh bạ cho các tài khoản đó và liên kết danh bạ hợp nhất với các tài khoản hợp nhất. Quy trình hợp nhất địa chỉ liên hệ ánh xạ dữ liệu liên hệ từ nhiều nguồn dữ liệu, loại bỏ trùng lặp, đối sánh dữ liệu giữa các thực thể, thiết lập ánh xạ ngữ nghĩa, tạo mối quan hệ giữa địa chỉ liên hệ và tài khoản, sau đó tạo hồ sơ liên hệ thống nhất.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

Một số bước đầu tiên giống với các bước hợp nhất tài khoản.

## <a name="prerequisites"></a>Điều kiện tiên quyết

Bản ghi tài khoản và liên hệ phải có một khóa duy nhất (được gọi là khóa ngoại) để kết nối chúng. Ví dụ: ID tài khoản tồn tại trong bản ghi tài khoản và bản ghi liên hệ liên kết tài khoản và liên hệ với nhau.

## <a name="preview-limitations"></a>Xem trước các giới hạn

- Các liên hệ không có liên kết đến tài khoản sẽ bị xóa.
- Nếu một tài khoản được loại bỏ trùng lặp, một bản ghi chiến thắng sẽ được xác định dựa trên các tùy chọn hợp nhất. Các bản ghi thua cuộc không được chọn và do đó sẽ bị loại bỏ. Địa chỉ liên hệ liên quan đến hồ sơ bị mất sẽ bị xóa.
- Một tài khoản có thể có nhiều địa chỉ liên hệ, nhưng một địa chỉ liên hệ được liên kết với một tài khoản.
- Các thuộc tính liên hệ được ánh xạ trong bước ánh xạ ngữ nghĩa là các thuộc tính duy nhất có thể hiển thị trên thẻ Khách hàng. Tuy nhiên, 17 thuộc tính có sẵn.

## <a name="select-source-fields"></a>Chọn các trường nguồn

1. Dưới **Hợp nhất danh bạ (xem trước)**, lựa chọn **Bắt đầu**.

1. [Chọn các thực thể và trường](map-entities.md) cho các nguồn dữ liệu liên hệ của bạn, bao gồm các khóa chính và các loại thuộc tính.

1. Chọn **Tiếp theo**.

## <a name="remove-duplicate-records"></a>Loại bỏ các bản ghi trùng lặp

1. Tùy ý, [xác định các quy tắc trùng lặp](remove-duplicates.md) cho các thực thể đã chọn của bạn.

1. Chọn **Tiếp theo**.

## <a name="match-conditions"></a>Điều kiện phù hợp

1. [Xác định thứ tự và quy tắc đối sánh](match-entities.md) để đối sánh nhiều thực thể.

1. Chọn **Tiếp theo**.

## <a name="unify-contact-fields"></a>Hợp nhất các trường liên hệ

1. [Kết hợp và loại trừ các trường liên hệ](merge-entities.md).

1. Chọn **Tiếp theo**.

## <a name="define-the-semantic-fields-for-unified-contacts"></a>Xác định trường ngữ nghĩa cho danh sách người liên hệ đã hợp nhất

Bước này trong quy trình hợp nhất ánh xạ các trường liên hệ hợp nhất của bạn thành các kiểu ngữ nghĩa. Trong B-to-B, thẻ khách hàng hiển thị tài khoản. Khi thẻ được chọn, tất cả các địa chỉ liên hệ được liên kết với tài khoản sẽ hiển thị. Các trường bạn ánh xạ trong bước này là các trường sẽ hiển thị trên thẻ.

1. Chọn kiểu ngữ nghĩa ánh xạ tới từng trường hợp nhất. Lựa chọn **Không có** nếu một loại ngữ nghĩa không có sẵn.

   :::image type="content" source="media/semantic_mapping.png" alt-text="Ảnh chụp màn hình trang Trường ngữ nghĩa để xác định các kiểu ngữ nghĩa." lightbox="media/semantic_mapping.png":::

1. Sau khi ánh xạ tất cả các trường hợp nhất, hãy chọn **Tiếp theo**.

## <a name="set-the-relationship-between-contacts-and-accounts"></a>Đặt mối quan hệ giữa danh bạ và tài khoản

Bước này trong quy trình hợp nhất kết nối dữ liệu liên hệ của bạn với dữ liệu tài khoản tương ứng.

1. Đối với mỗi thực thể, hãy nhập thông tin sau:

   - **Khóa ngoại từ thực thể liên hệ** : Chọn thuộc tính kết nối thực thể liên hệ của bạn với tài khoản.
   - **Tới thực thể tài khoản** : Chọn thực thể tài khoản được liên kết với địa chỉ liên hệ.

   :::image type="content" source="media/contact_relationship.png" alt-text="Ảnh chụp màn hình trang Mối quan hệ để kết nối các thực thể liên hệ và tài khoản.":::

1. Chọn **Tiếp theo**.

## <a name="review-contact-unification"></a>Xem xét hợp nhất liên hệ

Xem lại bản tóm tắt các thay đổi, tạo hồ sơ hợp nhất và xem xét kết quả.

### <a name="review-and-create-contact-profiles"></a>Xem xét và tạo hồ sơ người liên hệ

Bước cuối cùng này trong quy trình hợp nhất hiển thị tóm tắt các bước trong quy trình và cung cấp cơ hội thực hiện các thay đổi trước khi bạn tạo hồ sơ liên hệ hợp nhất.

:::image type="content" source="media/b2b_review_contacts.png" alt-text="Ảnh chụp màn hình Đánh giá và tạo hồ sơ liên hệ.":::

1. Lựa chọn **Chỉnh sửa** trên bất kỳ bước hợp nhất liên hệ nào để xem xét và thực hiện bất kỳ thay đổi nào.

1. Nếu bạn hài lòng với lựa chọn của mình, hãy chọn **Tạo hồ sơ liên hệ**. Các **Thống nhất** trang hiển thị trong khi hồ sơ liên hệ hợp nhất đang được tạo.
  
   :::image type="content" source="media/b2b_unify_refreshing.png" alt-text="Ảnh chụp màn hình trang Unify Danh bạ với các ô hiển thị Đã xếp hàng hoặc Đang làm mới.":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Thuật toán hợp nhất cần một thời gian để hoàn thành và bạn không thể thay đổi cấu hình cho đến khi hoàn tất.

### <a name="view-the-results-of-contact-unification"></a>Xem kết quả thống nhất liên hệ

Sau khi thống nhất hoàn tất, **Dữ liệu** > **Thống nhất** trang hiển thị số lượng hồ sơ liên hệ hợp nhất. Kết quả của mỗi bước trong quá trình hợp nhất hiển thị trên mỗi ô. Ví dụ, **Các trường nguồn** hiển thị số lượng thuộc tính được ánh xạ (trường) và **Bản ghi trùng lặp** hiển thị số lượng bản ghi trùng lặp được tìm thấy.

:::image type="content" source="media/unified_contacts.png" alt-text="Ảnh chụp màn hình trang Thống nhất dữ liệu sau khi các địa chỉ liên hệ được thống nhất.":::

> [!TIP]
> Các **Điều kiện phù hợp** chỉ hiển thị nếu nhiều thực thể đã được chọn.

Chúng tôi khuyên bạn nên xem lại kết quả, đặc biệt là chất lượng của [phù hợp với các quy tắc](data-unification-update.md#manage-match-rules) và tinh chỉnh chúng nếu cần thiết.

Khi cần, [thực hiện các thay đổi đối với cài đặt hợp nhất địa chỉ liên hệ](data-unification-update.md) và chạy lại cấu hình hợp nhất.

### <a name="verify-output-entities-from-data-unification"></a>Xác minh các thực thể đầu ra từ hợp nhất dữ liệu

Đi đến **Dữ liệu** > **Thực thể** để xác minh các thực thể đầu ra.

Thực thể hồ sơ liên hệ hợp nhất, được gọi là *ContactProfile*, hiển thị trong **Thực thể ngữ nghĩa** tiết diện. Lần chạy hợp nhất thành công đầu tiên tạo ra sự hợp nhất *ContactProfile* thực thể. Tất cả các lần chạy tiếp theo sẽ mở rộng thực thể đó.

Các *Liên hệ Khách hàng* thực thể (xem trước) được tạo và hiển thị trong **Hồ sơ** tiết diện. Thực thể này chứa dữ liệu liên hệ không có liên kết đến tài khoản. Thực thể này được sử dụng làm đầu vào cho các bước ánh xạ ngữ nghĩa và mối quan hệ của sự hợp nhất liên hệ.

Các thực thể trùng lặp và hỗn hợp được tạo và hiển thị trong **Hệ thống** tiết diện. Thực thể loại trừ trùng lặp cho mỗi thực thể nguồn được tạo với tên **Deduplication_DataSource_Entity**. Các **Danh bạConflationMatchPairs** thực thể chứa thông tin về các đối sánh giữa nhiều thực thể.

Thực thể đầu ra loại bỏ trùng lặp chứa thông tin sau:
- ID/Khóa
  - Trường khóa chính và ID thay thế. Trường ID thay thế bao gồm tất cả các ID thay thế được xác định cho một bản ghi.
  - Trường Deduplication_GroupId hiển thị nhóm hoặc cụm được xác định trong một thực thể sẽ nhóm tất cả các bản ghi tương tự dựa trên các trường loại bỏ trùng lặp được chỉ định. Tính năng này được sử dụng cho mục đích xử lý hệ thống. Nếu không có quy tắc khử trùng lặp thủ công nào được chỉ định và áp dụng quy tắc khử trùng lặp do hệ thống xác định, bạn có thể không tìm thấy trường này trong thực thể đầu ra khử trùng lặp.
  - Deduplication_WinnerId: Trường này chứa ID chiến thắng từ các nhóm hoặc cụm đã xác định. Nếu Deduplication_WinnerId giống với giá trị Khóa chính của một bản ghi, điều đó có nghĩa là bản ghi đó là bản ghi chiến thắng.
- Các trường được sử dụng để xác định các quy tắc khử trùng lặp.
- Các trường Quy tắc và Điểm để biểu thị quy tắc khử trùng lặp đã được áp dụng và điểm mà thuật toán so khớp trả về.

## <a name="next-step"></a>Bước tiếp theo

Định cấu hình [các hoạt động](activities.md),[làm giàu](enrichment-hub.md), hoặc [các mối quan hệ](relationships.md) để có thêm thông tin chi tiết về các địa chỉ liên hệ của bạn.
