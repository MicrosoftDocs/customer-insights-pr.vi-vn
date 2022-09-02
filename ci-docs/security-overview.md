---
title: Định cấu hình cài đặt bảo mật
description: Tìm hiểu về cài đặt bảo mật trong Dynamics 365 Customer Insights.
ms.date: 08/02/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: d20d57e9b7724e9921f9341eeaa39141b4555ff1
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387284"
---
# <a name="configure-security-settings"></a>Định cấu hình cài đặt bảo mật

Quản lý khóa API, truy cập dữ liệu khách hàng và thiết lập Liên kết riêng Azure.

## <a name="manage-api-keys"></a>Quản lý khóa API

Xem và quản lý các khóa để sử dụng [API thông tin chi tiết về khách hàng](apis.md) với dữ liệu trong môi trường của bạn.

1. Đi đến **Quản trị viên** > **Bảo vệ** và chọn **API** chuyển hướng.

1. Nếu quyền truy cập API vào môi trường chưa được thiết lập, hãy chọn **Cho phép** . Hoặc, để chặn quyền truy cập API vào môi trường, hãy chọn **Vô hiệu hóa** Và xác nhận.

1. Quản lý các khóa API chính và phụ:

   1. Để hiển thị khóa API chính hoặc phụ, hãy chọn **Trình diễn** Biểu tượng.

   1. Để sao chép khóa API chính hoặc phụ, hãy chọn **Sao chép** Biểu tượng.

   1. Để tạo khóa API chính hoặc phụ mới, hãy chọn **Tạo lại chính** hoặc **Tạo lại thứ cấp** .

## <a name="securely-access-customer-data-with-customer-lockbox-preview"></a>Truy cập an toàn dữ liệu khách hàng với Hộp khóa khách hàng (Xem trước)

Thông tin chi tiết về khách hàng sử dụng Power Platform Khả năng của Hộp khóa khách hàng. Khách hàng Lockbox cung cấp một giao diện để xem xét và phê duyệt (hoặc từ chối) các yêu cầu truy cập dữ liệu. Những yêu cầu này xảy ra khi cần truy cập dữ liệu vào dữ liệu khách hàng để giải quyết một trường hợp hỗ trợ. Để sử dụng tính năng này, Thông tin chi tiết về khách hàng phải có kết nối hiện có với Microsoft Dataverse môi trường trong người thuê nhà của bạn.

Để biết thêm thông tin về Hộp khóa khách hàng, hãy xem [bản tóm tắt](/power-platform/admin/about-lockbox#summary) của Power Platform Hộp khóa khách hàng. Bài báo cũng mô tả [quy trình làm việc](/power-platform/admin/about-lockbox#workflow) và yêu cầu [thành lập](/power-platform/admin/about-lockbox#enable-the-lockbox-policy) để bật Hộp khóa khách hàng.

> [!IMPORTANT]
> Quản trị viên toàn cầu cho Power Platform hoặc Power Platform quản trị viên có thể phê duyệt các yêu cầu Hộp khóa khách hàng được cấp cho Thông tin chi tiết về khách hàng.

## <a name="set-up-an-azure-private-link"></a>Thiết lập liên kết riêng Azure

[Liên kết cá nhân Azure](/azure/private-link/private-link-overview) cho phép Thông tin chi tiết về khách hàng kết nối với Azure Data Lake Storage tài khoản qua một điểm cuối riêng trong mạng ảo của bạn. Đối với dữ liệu trong tài khoản lưu trữ không được tiếp xúc với Internet công cộng, Liên kết riêng tư cho phép kết nối với mạng bị hạn chế đó.

> [!IMPORTANT]
> Yêu cầu vai trò tối thiểu để thiết lập kết nối Private Link:
>
> - Thông tin chi tiết về khách hàng: Quản trị viên
> - Vai trò tích hợp Azure: [Người đóng góp tài khoản lưu trữ](/azure/role-based-access-control/built-in-roles#storage-account-contributor)
> - Quyền cho vai trò Azure tùy chỉnh: [Microsoft.Storage/storageAccounts/read và Microsoft.Storage/storageAccounts/PrivateEndpointConnectionsApproval/action](/azure/role-based-access-control/resource-provider-operations#microsoftstorage)

1. Trong Thông tin chi tiết về khách hàng, hãy chuyển đến **Quản trị viên** > **Bảo vệ** và chọn **Liên kết riêng tư** chuyển hướng.

1. Lựa chọn **Thêm liên kết riêng tư** .

   Các **Thêm liên kết riêng tư** ngăn liệt kê các tài khoản lưu trữ từ người thuê của bạn mà bạn có quyền xem.

1. Chọn đăng ký, nhóm tài nguyên và tài khoản lưu trữ.

1. Xem lại [quyền riêng tư và tuân thủ dữ liệu](connections.md#data-privacy-and-compliance) và chọn **tôi đồng ý** .

1. Chọn **Lưu.**

1. Truy cập tài khoản Data Lake Storage của bạn và mở liên kết hiển thị trên màn hình.

1. Phê duyệt Liên kết Riêng tư.


[!INCLUDE [footer-include](includes/footer-banner.md)]
