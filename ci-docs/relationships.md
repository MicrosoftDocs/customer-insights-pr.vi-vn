---
title: Mối quan hệ giữa các thực thể và đường dẫn thực thể
description: Tạo và quản lý mối quan hệ giữa các thực thể từ nhiều nguồn dữ liệu.
ms.date: 09/27/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-semantic-mapping
- ci-entities
- ci-relationships
- ci-activities
- ci-activities-wizard
- ci-measures
- ci-segments
- ci-segment-builder
- ci-measure-builder
- ci-measure-template
- ci-permissions
- customerInsights
ms.openlocfilehash: e622e5fa0b5738e31db1c668d95312adbc4f7d36
ms.sourcegitcommit: ad74ace653db9a25fce4343adef7db1c9b0d8904
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 07/21/2022
ms.locfileid: "9183598"
---
# <a name="relationships-between-entities-and-entity-paths"></a>Mối quan hệ giữa các thực thể và đường dẫn thực thể

Mối quan hệ kết nối các thực thể và xác định một biểu đồ dữ liệu của bạn khi các thực thể có cùng một khóa ngoại, mã định danh chung. Khóa ngoại này có thể được tham chiếu từ thực thể này sang thực thể khác. Các thực thể được kết nối cho phép bạn xác định các phân khúc và giá trị đo dựa trên nhiều nguồn dữ liệu.

Có 3 loại mối quan hệ: 
- Các mối quan hệ hệ thống không thể chỉnh sửa được hệ thống tạo ra như một phần của quá trình hợp nhất dữ liệu
- Các mối quan hệ kế thừa không thể chỉnh sửa được tạo tự động từ việc nhập các nguồn dữ liệu
- Các mối quan hệ tùy chỉnh có thể chỉnh sửa được người dùng tạo và định cấu hình

## <a name="non-editable-system-relationships"></a>Mối quan hệ hệ thống không thể chỉnh sửa

Trong quá trình hợp nhất dữ liệu, các mối quan hệ hệ thống được tạo tự động dựa trên tính năng kết hợp thông minh. Các mối quan hệ này giúp liên kết bản ghi hồ sơ khách hàng với bản ghi tương ứng. Sơ đồ sau minh họa quá trình tạo ra 3 mối quan hệ dựa trên hệ thống. Thực thể khách hàng được kết hợp với các thực thể khác để tạo ra thực thể *Customer* hợp nhất.

:::image type="content" source="media/relationships-entities-merge.png" alt-text="Sơ đồ với các đường dẫn mối quan hệ cho thực thể khách hàng với 3 mối quan hệ 1-n.":::

- **Mối quan hệ *CustomerToContact*** được tạo giữa thực thể *Customer* và *Contact*. Thực thể *Customer* lấy trường khóa **Contact_contactID** để liên kết với trường khóa **contactID** của thực thể *Contact*.
- **Mối quan hệ *CustomerToAccount*** được tạo giữa thực thể *Customer* và thực thể *Account*. Thực thể *Customer* lấy trường khóa **Account_accountID** để liên kết với trường khóa **accountID** của thực thể *Account*.
- **Mối quan hệ *CustomerToWebAccount*** được tạo giữa thực thể *Customer* và thực thể *WebAccount*. Thực thể *Customer* lấy trường khóa **WebAccount_webaccountID** để liên kết với trường khóa **webaccountID** của thực thể *WebAccount*.

## <a name="non-editable-inherited-relationships"></a>Mối quan hệ kế thừa không thể chỉnh sửa

Trong quá trình nhập dữ liệu, hệ thống sẽ kiểm tra nguồn dữ liệu để tìm các mối quan hệ hiện có. Nếu không có mối quan hệ nào tồn tại, hệ thống sẽ tự động tạo. Các mối quan hệ này cũng dùng trong các quy trình xuôi tuyến.

## <a name="create-a-custom-relationship"></a>Tạo mối quan hệ tùy chỉnh

Mối quan hệ bao gồm một *thực thể nguồn* chứa khóa ngoại và một *thực thể đích* mà khóa ngoại của thực thể nguồn trỏ đến. 

1. Chuyển đến **Dữ liệu** > **Mối quan hệ**.

2. Chọn **Mối quan hệ mới**.

3. Trong ngăn **Mối quan hệ mới**, hãy cung cấp các thông tin sau:

   :::image type="content" source="media/relationship-add.png" alt-text="Ngăn bên Mối quan hệ mới với các trường nhập dữ liệu trống.":::

   - **Tên mối quan hệ**: Tên phản ánh mục đích của mối quan hệ. Ví dụ: CustomerToSupportCase.
   - **Mô tả**: Mô tả về mối quan hệ.
   - **Thực thể nguồn**: Thực thể dùng làm nguồn trong mối quan hệ. Ví dụ: SupportCase.
   - **Thực thể đích**: Thực thể dùng làm đích trong mối quan hệ. Ví dụ: Customer.
   - **Cardinality nguồn** : Bản số của thực thể nguồn. Lượng số mô tả số phần tử có thể có trong một tập hợp. Lượng số nguồn luôn liên quan đến lượng số đích. Bạn có thể chọn giữa **Một** và **Nhiều**. Chỉ hỗ trợ các mối quan hệ nhiều-một và một-một.  
     - Nhiều-một: Nhiều bản ghi nguồn có thể liên kết với một bản ghi đích. Ví dụ: Nhiều trường hợp hỗ trợ từ một khách hàng.
     - Một-một: Một bản ghi nguồn liên kết với một bản ghi đích. Ví dụ: Một ID khách hàng thân thiết cho một khách hàng.

     > [!NOTE]
     > Bạn có thể tạo mối quan hệ nhiều-nhiều bằng cách sử dụng 2 mối quan hệ nhiều-một và một thực thể liên kết, kết nối thực thể nguồn và thực thể đích.

   - **Cardinality mục tiêu** : Số lượng bản ghi thực thể đích.
   - **Trường khóa nguồn** : Trường khóa ngoại trong thực thể nguồn. Ví dụ: SupportCase sử dụng **CaseID** với tư cách là lĩnh vực khóa nước ngoài.
   - **Trường chính mục tiêu** : Trường chính của thực thể mục tiêu. Ví dụ: Khách hàng sử dụng **ID khách hàng** là lĩnh vực quan trọng.

4. Chọn **Lưu** để tạo mối quan hệ tùy chỉnh.

## <a name="set-up-account-hierarchies"></a>Thiết lập hệ thống phân cấp tài khoản

Các môi trường được định cấu hình để sử dụng tài khoản doanh nghiệp làm đối tượng mục tiêu chính có thể định cấu hình phân cấp tài khoản cho các tài khoản doanh nghiệp có liên quan. Ví dụ, một công ty có các đơn vị kinh doanh riêng biệt.

Các tổ chức tạo phân cấp tài khoản để quản lý tốt hơn các tài khoản và mối quan hệ của chúng với nhau. Thông tin chi tiết về khách hàng hỗ trợ phân cấp tài khoản mẹ-con đã tồn tại trong dữ liệu khách hàng được nhập. Ví dụ: tài khoản từ Dynamics 365 Sales. Các cấu trúc phân cấp này có thể được định cấu hình trên **Các mối quan hệ** trang.

1. Chuyển đến **Dữ liệu** > **Mối quan hệ**.
1. Chọn tab **Phân cấp tài khoản**.
1. Chọn **Hệ thống cấp bậc tài khoản mới**.
1. Trong ngăn **Hệ thống cấp bậc tài khoản**, cung cấp tên cho hệ thống cấp bậc. Hệ thống tạo tên cho thực thể đầu ra, nhưng bạn có thể thay đổi nó.
1. Chọn thực thể chứa hệ thống cấp bậc tài khoản của bạn. Nó thường nằm trong cùng một thực thể có chứa các tài khoản.
1. Chọn **UID tài khoản** và **UID cha** từ thực thể đã chọn.
1. Lựa chọn **Tiết kiệm** để hoàn thiện phân cấp tài khoản.

## <a name="manage-existing-relationships"></a>Quản lý mối quan hệ hiện có

Đi đến **Các mối quan hệ** trang để xem tất cả các mối quan hệ đã được tạo, thực thể nguồn của chúng, thực thể đích và bản số.

:::image type="content" source="media/relationships-list.png" alt-text="Danh sách các mối quan hệ và tùy chọn trong thanh tác vụ của trang Mối quan hệ.":::

Sử dụng **Lọc bởi** hoặc **Tìm kiếm các mối quan hệ** các tùy chọn để xác định một mối quan hệ cụ thể. Để xem sơ đồ mạng của các mối quan hệ hiện có và số lượng của chúng, hãy chọn [**Trình hiển thị**](#explore-the-relationship-visualizer).

Chọn một mối quan hệ để xem các hành động có sẵn:
- **Chỉnh sửa**: Cập nhật các thuộc tính của mối quan hệ tùy chỉnh trong ngăn chỉnh sửa và lưu các thay đổi.
- **Xóa**: Xóa mối quan hệ tùy chỉnh.
- **Xem**: Xem mối quan hệ do hệ thống tạo và mối quan hệ kế thừa.

### <a name="explore-the-relationship-visualizer"></a>Khám phá trình hiển thị mối quan hệ

Trình hiển thị mối quan hệ hiển thị sơ đồ mạng lưới của các mối quan hệ hiện có giữa các thực thể được kết nối và lượng số của chúng. Trình hiển thị cũng hiển thị đường dẫn mối quan hệ.

:::image type="content" source="media/relationship-visualizer.png" alt-text="Ảnh chụp màn hình sơ đồ mạng lưới của trình hiển thị mối quan hệ với các kết nối giữa các thực thể liên quan.":::

Để tùy chỉnh dạng xem này, bạn có thể thay đổi vị trí của các hộp bằng cách kéo chúng trên canvas. Các tùy chọn khác bao gồm: 
- **Xuất dưới dạng hình ảnh**: Lưu dạng xem hiện tại dưới dạng tệp hình ảnh.
- **Thay đổi thành bố cục ngang/dọc**: Thay đổi hướng của các thực thể và mối quan hệ.
- **Chỉnh sửa**: Cập nhật các thuộc tính của mối quan hệ tùy chỉnh trong ngăn chỉnh sửa và lưu các thay đổi.

## <a name="relationship-paths"></a>Đường dẫn mối quan hệ

Đường dẫn mối quan hệ mô tả các thực thể được kết nối bằng các mối quan hệ giữa một thực thể nguồn và một thực thể đích. Nó được sử dụng khi tạo một phân đoạn hoặc một thước đo bao gồm các thực thể khác với thực thể cấu hình hợp nhất và có nhiều tùy chọn để tiếp cận thực thể cấu hình hợp nhất. Các đường dẫn mối quan hệ khác nhau có thể mang lại những kết quả khác nhau.

Ví dụ: thực thể *eCommerce_eCommercePurchases* có các mối quan hệ sau với thực thể *Khách hàng* hồ sơ hợp nhất:

- eCommerce_eCommercePurchases > Khách hàng
- eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > Khách hàng
- eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > loyaltyScheme_loyCustomers > Khách hàng

Đường dẫn mối quan hệ xác định thực thể mà bạn có thể sử dụng khi tạo quy tắc cho các biện pháp hoặc phân đoạn. Việc chọn tùy chọn có đường dẫn mối quan hệ dài nhất có thể sẽ mang lại ít kết quả hơn vì các bản ghi phù hợp cần phải là một phần của tất cả các thực thể. Trong ví dụ này, khách hàng đã mua hàng hóa thông qua thương mại điện tử(eCommerce_eCommercePurchases) làm điểm bán hàng (POS_posPurchases) và tham gia vào chương trình khách hàng thân thiết (loyaltyScheme_loyCustomers). Khi chọn tùy chọn đầu tiên, bạn có thể sẽ nhận được nhiều kết quả hơn vì khách hàng chỉ cần tồn tại trong một thực thể bổ sung.

### <a name="direct-relationship"></a>Mối quan hệ trực tiếp

Một mối quan hệ được phân loại là **mối quan hệ trực tiếp** khi một thực thể nguồn liên quan đến một thực thể đích chỉ có một mối quan hệ.

Ví dụ: nếu một thực thể hoạt động được gọi là *eCommerce_eCommercePurchases* kết nối với một thực thể đích *eCommerce_eCommerceContacts* thực thể chỉ thông qua *ContactId*, đó là một mối quan hệ trực tiếp.

:::image type="content" source="media/direct_Relationship.png" alt-text="Thực thể nguồn kết nối trực tiếp với thực thể đích.":::

#### <a name="multi-path-relationship"></a>Mối quan hệ nhiều đường dẫn

Một **mối quan hệ nhiều đường dẫn** là một kiểu quan hệ trực tiếp đặc biệt kết nối một thực thể nguồn với nhiều thực thể đích.

Ví dụ: nếu một thực thể hoạt động được gọi là *eCommerce_eCommercePurchases* liên quan đến hai thực thể đích, thì cả hai *eCommerce_eCommerceContacts* và *loyaltyScheme_loyCustomers* là một mối quan hệ nhiều đường dẫn.

:::image type="content" source="media/multi-path_relationship.png" alt-text="Thực thể nguồn kết nối trực tiếp với nhiều thực thể đích thông qua mối quan hệ nhiều bước.":::

### <a name="indirect-relationship"></a>Mối quan hệ gián tiếp

Một mối quan hệ được phân loại là **mối quan hệ gián tiếp** khi một thực thể nguồn có liên quan đến một hoặc nhiều thực thể bổ sung trước khi có liên quan đến một thực thể đích.

#### <a name="multi-hop-relationship"></a>Mối quan hệ nhiều bước

Một **mối quan hệ nhiều bước** là một *mối quan hệ gián tiếp* cho phép bạn kết nối một thực thể nguồn với một thực thể đích thông qua một hoặc nhiều thực thể trung gian khác.

Ví dụ: nếu một thực thể hoạt động được gọi là *eCommerce_eCommercePurchasesWest* kết nối với một thực thể trung gian được gọi là *eCommerce_eCommercePurchasesEast*, sau đó kết nối với một thực thể đích được gọi là *eCommerce_eCommerceContacts*, đó là một mối quan hệ nhiều bước.

:::image type="content" source="media/multi-hop_relationship.png" alt-text="Thực thể nguồn kết nối trực tiếp với một thực thể đích qua một thực thể trung gian.":::

### <a name="multi-hop-multi-path-relationship"></a>Mối quan hệ nhiều bước, nhiều đường dẫn

Các mối quan hệ nhiều bước và nhiều đường dẫn có thể được sử dụng cùng nhau để tạo **các mối quan hệ nhiều bước, nhiều đường dẫn**. Loại đặc biệt này kết hợp các chức năng của mối quan hệ **nhiều bước** và **nhiều đường dẫn**. Mối quan hệ này giúp bạn kết nối với nhiều thực thể đích thông qua các thực thể trung gian.

Ví dụ: nếu một thực thể hoạt động được gọi là *eCommerce_eCommercePurchasesWest* kết nối với một thực thể trung gian được gọi là *eCommerce_eCommercePurchasesEast*, sau đó kết nối với hai thực thể đích, cả hai *eCommerce_eCommerceContacts* và *loyaltyScheme_loyCustomers* là mối quan hệ nhiều bước, nhiều đường dẫn.

:::image type="content" source="media/multi-hop_multi-path_relationship.png" alt-text="Thực thể nguồn kết nối trực tiếp với một thực thể đích và kết nối với một thực thể đích khác thông qua một thực thể trung gian.":::

## <a name="next-step"></a>Bước tiếp theo

Các mối quan hệ hệ thống và tùy chỉnh được sử dụng để [tạo phân khúc](segments.md) và [đo](measures.md) dựa trên nhiều nguồn dữ liệu không còn được lưu trữ.

[!INCLUDE [footer-include](includes/footer-banner.md)]
