---
title: Cài đặt bảo mật trong Thông tin chi tiết về khách hàng
description: Tìm hiểu về cài đặt bảo mật trong Dynamics 365 Customer Insights.
ms.date: 06/08/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 163deb9bed4f82d742c46cace27dd128f0aca18b
ms.sourcegitcommit: 8e9f0a9693fd8d91ad0227735ff03688fef5406f
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 06/10/2022
ms.locfileid: "8947441"
---
# <a name="security-settings-in-customer-insights"></a>Cài đặt bảo mật trong Thông tin chi tiết về khách hàng

Các **Bảo vệ** trang liệt kê các tùy chọn để định cấu hình quyền của người dùng và các tính năng giúp tạo Dynamics 365 Customer Insights an toàn hơn. Chỉ quản trị viên mới có thể truy cập trang này.

Đi đến **Quản trị viên** > **Bảo vệ** để định cấu hình cài đặt.

Các **Bảo vệ** trang bao gồm các tab sau:

- [Người dùng](#users-tab)
- [API](#apis-tab)
- [Liên kết Riêng tư](#private-links-tab)
- [Kho lưu trữ khóa](#key-vault-tab)
- [Truy cập an toàn vào dữ liệu khách hàng với Hộp khóa khách hàng (Xem trước)](#securely-access-customer-data-with-customer-lockbox-preview)

## <a name="users-tab"></a>Tab Người dùng

Quyền truy cập vào Thông tin chi tiết về khách hàng bị hạn chế đối với người dùng trong tổ chức của bạn đã được quản trị viên thêm vào ứng dụng. Các **Người dùng** cho phép bạn quản lý quyền truy cập của người dùng và quyền của họ. Để biết thêm thông tin, hãy xem [Quyền Người dùng](permissions.md).

## <a name="apis-tab"></a>Tab API

Xem và quản lý các khóa để sử dụng [API thông tin chi tiết về khách hàng](apis.md) với dữ liệu của môi trường của bạn.

Bạn có thể tạo khóa chính và khóa phụ mới bằng cách chọn **Tạo lại chính** hoặc **Tạo lại thứ cấp**. 

Để chặn quyền truy cập API vào môi trường, hãy chọn **Vô hiệu hóa**. Nếu các API bị tắt, bạn có thể chọn **Cho phép** để cấp lại quyền truy cập.

## <a name="private-links-tab"></a>Tab Liên kết Riêng tư

[Liên kết riêng Azure](/azure/private-link/private-link-overview) hãy để Thông tin chi tiết về khách hàng kết nối với Azure Data Lake Storage tài khoản qua một điểm cuối riêng trong mạng ảo của bạn. Đối với dữ liệu trong tài khoản lưu trữ không được tiếp xúc với internet công cộng, Liên kết riêng tư cho phép kết nối với mạng bị hạn chế đó.

> [!IMPORTANT]
> Yêu cầu vai trò tối thiểu để thiết lập kết nối Private Link:
>
> - Thông tin chi tiết về khách hàng: Quản trị viên
> - Vai trò tích hợp Azure: [Người đóng góp tài khoản lưu trữ](/azure/role-based-access-control/built-in-roles#storage-account-contributor)
> - Quyền cho vai trò Azure tùy chỉnh: [Microsoft.Storage/storageAccounts/read và Microsoft.Storage/storageAccounts/PrivateEndpointConnectionsApproval/action](/azure/role-based-access-control/resource-provider-operations#microsoftstorage)
>

Thiết lập Liên kết riêng trong Thông tin chi tiết về khách hàng là một quy trình gồm hai bước. Trước tiên, bạn bắt đầu tạo Liên kết riêng từ **Quản trị viên** > **Bảo vệ** > **Liên kết riêng tư** trong Thông tin chi tiết về khách hàng. Các **Thêm liên kết riêng tư** ngăn liệt kê các tài khoản lưu trữ từ người thuê của bạn mà bạn có quyền xem. Chọn tài khoản lưu trữ và cung cấp sự đồng ý để tạo Liên kết riêng tư.

Tiếp theo, bạn cần phê duyệt Liên kết Riêng tư ở phía tài khoản Data Lake Storage. Mở liên kết hiển thị trên màn hình để phê duyệt Liên kết Riêng tư mới.

## <a name="key-vault-tab"></a>Tab Key Vault

Các **Kho chìa khóa** tab cho phép bạn liên kết và quản lý của riêng bạn [Kho tiền khóa Azure](/azure/key-vault/general/basic-concepts) cho môi trường.
Có thể dùng Key vault chuyên dụng để chia giai đoạn và sử dụng bí mật trong ranh giới tuân thủ của một tổ chức. Thông tin chi tiết về khách hàng có thể sử dụng các bí mật trong Azure Key Vault để [thiết lập kết nối](connections.md) cho các hệ thống của bên thứ ba.

Để biết thêm thông tin, hãy xem [Mang tín liệu khóa Azure của riêng bạn](use-azure-key-vault.md).

## <a name="securely-access-customer-data-with-customer-lockbox-preview"></a>Truy cập an toàn vào dữ liệu khách hàng với Hộp khóa khách hàng (Xem trước)

Thông tin chi tiết về khách hàng đang sử dụng Power Platform Khả năng của Hộp khóa khách hàng. Khách hàng Lockbox cung cấp một giao diện để xem xét và phê duyệt (hoặc từ chối) các yêu cầu truy cập dữ liệu. Các yêu cầu này xảy ra khi cần truy cập dữ liệu vào dữ liệu khách hàng để giải quyết một trường hợp hỗ trợ. Để sử dụng tính năng này, Thông tin chi tiết về khách hàng phải có kết nối hiện có với Microsoft Dataverse môi trường trong người thuê nhà của bạn.

Để biết thêm thông tin về Hộp khóa khách hàng, hãy xem [bản tóm tắt](/power-platform/admin/about-lockbox#summary) của Power Platform Hộp khóa khách hàng. Bài báo cũng mô tả [quy trình làm việc](/power-platform/admin/about-lockbox#workflow) và yêu cầu [thành lập](/power-platform/admin/about-lockbox#enable-the-lockbox-policy) để bật Hộp khóa khách hàng.

> [!IMPORTANT]
> Quản trị viên toàn cầu cho Power Platform hoặc Power Platform quản trị viên có thể phê duyệt các yêu cầu Hộp khóa khách hàng được cấp cho Thông tin chi tiết về khách hàng.

[!INCLUDE [footer-include](includes/footer-banner.md)]
