---
title: Mang Azure Key Vault của riêng bạn để quản lý bí mật
description: Tìm hiểu cách đặt cấu hình Customer Insights để sử dụng Azure key vault của riêng bạn.
ms.date: 10/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: d4f2d5ebc828053c40e22065f4915c4d0f84153f
ms.sourcegitcommit: 6ec4626a185892dfb781d3c7af4384f9c13f3723
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 05/17/2022
ms.locfileid: "8763605"
---
# <a name="bring-your-own-azure-key-vault-preview"></a>Mang Azure key vault của riêng bạn (bản xem trước)

Liên kết chuyên dụng [Kho tiền khóa Azure](/azure/key-vault/general/basic-concepts) sang môi trường Thông tin chi tiết về khách hàng giúp các tổ chức đáp ứng các yêu cầu tuân thủ.
Có thể dùng Key vault chuyên dụng để chia giai đoạn và sử dụng bí mật trong ranh giới tuân thủ của một tổ chức. Thông tin chi tiết về khách hàng có thể sử dụng các bí mật trong Azure Key Vault để [thiết lập kết nối](connections.md) cho các hệ thống của bên thứ ba.

## <a name="link-the-key-vault-to-the-customer-insights-environment"></a>Liên kết kho tiền với môi trường Thông tin chi tiết về khách hàng

### <a name="prerequisites"></a>Điều kiện tiên quyết

Để định cấu hình kho quan trọng trong Thông tin chi tiết về khách hàng, bạn phải đáp ứng các điều kiện tiên quyết sau:

- Bạn phải có đăng ký Azure hiện hoạt.

- Bạn có một [Người quản lý](permissions.md#admin) vai trò trong Thông tin chi tiết về khách hàng. Học nhiều hơn về [quyền của người dùng trong Thông tin chi tiết về khách hàng](permissions.md#assign-roles-and-permissions).

- Bạn có vai trò [Người đóng góp](/azure/role-based-access-control/built-in-roles#contributor) và [Quản trị viên truy cập người dùng](/azure/role-based-access-control/built-in-roles#user-access-administrator) trên key vault hoặc nhóm tài nguyên chứa key vault đó. Để biết thêm thông tin, hãy chuyển đến [Thêm hoặc xóa các chỉ định vai trò Azure bằng cổng thông tin Azure](/azure/role-based-access-control/role-assignments-portal). Nếu bạn không có vai trò Quản trị viên truy cập người dùng trên key vault, bạn phải thiết lập các quyền kiểm soát truy cập dựa trên vai trò cho dịch vụ Azure chính cho Dynamics 365 Customer Insights một cách riêng biệt. Làm theo các bước để [sử dụng một dịch vụ Azure chính](connect-service-principal.md) cho key vault cần được liên kết.

- Key vault phải có tường lửa bị **vô hiệu hóa**.

- Kho tiền vẫn ở trong cùng [Vị trí Azure](https://azure.microsoft.com/global-infrastructure/geographies/#overview) là môi trường Thông tin chi tiết về khách hàng. Khu vực môi trường trong Thông tin chi tiết về khách hàng được liệt kê trong **Quản trị viên** > **Hệ thống** > **Về** > **Vùng đất**.

### <a name="link-a-key-vault-to-the-environment"></a>Liên kết key vault với môi trường

1. Đi đến **Quản trị viên** > **Bảo vệ**, và sau đó chọn **Kho chìa khóa** chuyển hướng.
1. Trên ngăn xếp **Key Vault**, chọn **Thiết lập**.
1. Chọn **Đăng ký**.
1. Chọn key vault từ danh sách thả xuống **Key Vault**. Nếu có quá nhiều key vault hiển thị, hãy chọn một nhóm tài nguyên để giới hạn kết quả tìm kiếm.
1. Chấp nhận câu lệch **Quyền riêng tư và tuân thủ dữ liệu**.
1. Chọn **Lưu.**

:::image type="content" source="media/set-up-azure-key-vault.png" alt-text="Các bước thiết lập kho khóa được liên kết trong Thông tin chi tiết về khách hàng.":::

Ngăn xếp **Key Vault** hiển thị tên key vault đã liên kết, nhóm tài nguyên và đăng ký. Nó đã sẵn sàng để được sử dụng trong thiết lập kết nối.
Để biết chi tiết về những quyền nào trên kho khóa được cấp cho Thông tin chi tiết về khách hàng, hãy truy cập [Quyền được cấp trên kho chìa khóa](#permissions-granted-on-the-key-vault), ở phần sau của bài viết này.

## <a name="use-the-key-vault-in-the-connection-setup"></a>Sử dụng key vault trong thiết lập kết nối

Khi [thiết lập kết nối](connections.md) cho các hệ thống bên thứ ba, có thể sử dụng bí mật từ Key Vault đã liên kết để đặt cấu hình kết nối.

1. Đi đến **Quản trị viên** > **Kết nối**.
1. Chọn **Thêm kết nối**.
1. Đối với các loại kết nối được hỗ trợ, có nút chuyển đổi **Sử dụng Key Vault** nếu bạn liên kết key vault.
1. Thay vì nhập bí mật theo cách thủ công, bạn có thể chọn tên bí mật trỏ đến giá trị bí mật trong key vault.

:::image type="content" source="media/use-key-vault-secret.png" alt-text="Ngăn kết nối với kết nối SFTP sử dụng bí mật Key Vault.":::

## <a name="supported-connection-types"></a>Loại hành động không được hỗ trợ

Các kết nối [xuất](export-destinations.md) sau đây được hỗ trợ:

* [ActiveCampaign](export-active-campaign.md)
* [Autopilot](export-autopilot.md)
* [DotDigital](export-dotdigital.md)
* [Google Ads](export-google-ads.md)
* [Klaviyo](export-klaviyo.md)
* [LiveRamp](export-liveramp.md)
* [Marketo](export-marketo.md)
* [Omnisend](export-omnisend.md)
* [Salesforce Marketing Cloud](export-salesforce.md)
* [Sendgrid](export-sendgrid.md)
* [Sendinblue](export-sendinblue.md)
* [SFTP](export-sftp.md)

## <a name="permissions-granted-on-the-key-vault"></a>Quyền được cấp trên kho chìa khóa

Các quyền sau đây được cấp cho Thông tin chi tiết về khách hàng trên kho khóa được liên kết nếu [Chính sách truy cập Key Vault](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) hoặc [Kiểm soát truy cập dựa trên vai trò Azure](/azure/key-vault/general/rbac-guide?tabs=azure-cli) được kích hoạt.

### <a name="key-vault-access-policy"></a>Chính sách truy cập Key Vault

| Loại        | Quyền          |
| ----------- | -------------------- |
| Khóa         | [Nhận chìa khóa](/rest/api/keyvault/keys/get-keys/get-keys), [Nhận chìa khóa](/rest/api/keyvault/keys/get-key/get-key)                                 |
| Mã bí mật      | [Nhận bí mật](/rest/api/keyvault/secrets/get-secrets/get-secrets), [Nhận bí mật](/rest/api/keyvault/secrets/get-secret/get-secret)                     |
| Chứng chỉ | [Nhận chứng chỉ](/rest/api/keyvault/certificates/get-certificates/get-certificates), [Nhận chứng chỉ](/rest/api/keyvault/certificates/get-certificate/get-certificate) |

Các giá trị trước là giá trị tối thiểu để liệt kê và đọc trong quá trình thực thi.

### <a name="azure-role-based-access-control"></a>Kiểm soát truy cập dựa trên vai trò Azure

Vai trò của Người dùng Key Vault Reader và Key Vault Secrets sẽ được thêm vào cho Thông tin chi tiết về khách hàng. Để biết chi tiết về các vai trò này, hãy chuyển đến [các vai trò Azure tích hợp cho thao tác dữ liệu Key Vault](/azure/key-vault/general/rbac-guide?tabs=azure-cli).

## <a name="recommendations"></a>Đề xuất

- Sử dụng kho khóa riêng biệt hoặc chuyên dụng chỉ chứa những bí mật cần thiết cho Thông tin chi tiết về khách hàng. Đọc thêm về lý do [đề xuất key vault riêng biệt](/azure/key-vault/general/best-practices#why-we-recommend-separate-key-vaults).

- Làm theo [các phương pháp hay nhất để sử dụng Key Vault](/azure/key-vault/general/best-practices#turn-on-logging) để biết các tùy chọn kiểm soát quyền truy cập, sao lưu, kiểm tra và khôi phục.

## <a name="frequently-asked-questions"></a>Các câu hỏi thường gặp

### <a name="can-customer-insights-write-secrets-or-overwrite-secrets-into-the-key-vault"></a>Thông tin chi tiết về khách hàng có thể ghi bí mật hoặc ghi đè bí mật vào kho tiền không?

Không. Chỉ các quyền đọc và danh sách được nêu trong [quyền được cấp](#permissions-granted-on-the-key-vault) phần trước trong bài viết này được cấp cho Thông tin chi tiết về khách hàng. Hệ thống không thể thêm, xóa hoặc ghi đè các bí mật trong key vault. Đó cũng là lý do tại sao bạn không thể nhập thông tin xác thực khi kết nối sử dụng Key Vault.

### <a name="can-i-change-a-connection-from-using-key-vault-secrets-to-default-authentication"></a>Tôi có thể thay đổi kết nối từ sử dụng bí mật Key Vault sang xác thực mặc định không?

Không. Bạn không thể thay đổi trở lại kết nối mặc định sau khi đã đặt cấu hình nó bằng cách sử dụng bí mật từ key vault được liên kết. Tạo một kết nối riêng và xóa kết nối cũ nếu bạn không cần nữa.

### <a name="how-can-i-revoke-access-to-a-key-vault-for-customer-insights"></a>Làm cách nào để tôi có thể thu hồi quyền truy cập vào một kho tiền chính dành cho Thông tin chi tiết về khách hàng?

Tùy thuộc vào việc [chính sách truy cập Key Vault](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) hay [kiểm soát quyền truy cập dựa trên vai trò](/azure/key-vault/general/rbac-guide?tabs=azure-cli) được bật, bạn cần xóa quyền cho `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` chính với tên `Dynamics 365 AI for Customer Insights`. Tất cả các kết nối sử dụng key vault sẽ ngừng hoạt động.

### <a name="a-secret-thats-used-in-a-connection-got-removed-from-the-key-vault-what-can-i-do"></a>Một bí mật được sử dụng trong một kết nối đã bị xóa khỏi key vault. Tôi có thể làm gì?

Thông báo xuất hiện trong Thông tin chi tiết về khách hàng khi bí mật được định cấu hình từ kho khóa không thể truy cập được nữa. Cho phép [xóa mềm](/azure/key-vault/general/soft-delete-overview) trên key vault để khôi phục bí mật nếu chúng vô tình bị xóa.

### <a name="a-connection-doesnt-work-but-my-secret-is-in-the-key-vault-what-might-be-the-cause"></a>Một kết nối không hoạt động, nhưng bí mật của tôi nằm trong key vault. Nguyên nhân có thể là gì?

Thông báo xuất hiện trong Thông tin chi tiết về khách hàng khi thông báo không thể truy cập kho chìa khóa. Nguyên nhân có thể:

- Quyền đối với chính dịch vụ Thông tin chi tiết về khách hàng đã bị xóa. Chúng cần được khôi phục theo cách thủ công.

- Tường lửa trên key vault được bật. Tường lửa phải được tắt để làm cho kho khóa có thể truy cập lại để sử dụng Thông tin chi tiết về khách hàng.
