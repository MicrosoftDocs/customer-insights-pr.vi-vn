---
title: Yêu cầu theo Quyền của chủ thể dữ liệu (DSR) phù hợp với GDPR | Microsoft Docs
description: Trả lời các yêu cầu về chủ đề dữ liệu cho khả năng thông tin chi tiết về đối tượng Dynamics 365 Customer Insights.
ms.date: 05/14/2020
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f276a73feca52023391ad92fbc84359921b85328
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407320"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a><span data-ttu-id="ab2aa-103">Yêu cầu theo Quyền của chủ thể dữ liệu (DSR) phù hợp với GDPR</span><span class="sxs-lookup"><span data-stu-id="ab2aa-103">Data Subject Rights (DSR) requests under GDPR</span></span>

## <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a><span data-ttu-id="ab2aa-104">Trả lời yêu cầu xóa chủ đề dữ liệu GDPR cho khả năng thông tin chi tiết về đối tượng Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="ab2aa-104">Responding to GDPR data subject delete requests for Dynamics 365 Customer Insights audience insights capability</span></span>

<span data-ttu-id="ab2aa-105">"Quyền xóa" dữ liệu cá nhân khỏi dữ liệu khách hàng của tổ chức là sự bảo vệ chính trong Quy định Chung về Bảo vệ Dữ liệu (GDPR).</span><span class="sxs-lookup"><span data-stu-id="ab2aa-105">The “right to erasure” by the removal of personal data from an organization’s customer data is a key protection in the General Data Protection Regulation (GDPR).</span></span> <span data-ttu-id="ab2aa-106">Việc xóa dữ liệu cá nhân bao gồm xóa tất cả dữ liệu cá nhân và nhật ký do hệ thống tạo, ngoại trừ thông tin nhật ký kiểm tra.</span><span class="sxs-lookup"><span data-stu-id="ab2aa-106">Removing personal data includes removing all personal data and system-generated logs, except audit log information.</span></span>

### <a name="manage-data-subject-delete-requests"></a><span data-ttu-id="ab2aa-107">Quản lý yêu cầu xóa của chủ thể dữ liệu</span><span class="sxs-lookup"><span data-stu-id="ab2aa-107">Manage data subject delete requests</span></span>

<span data-ttu-id="ab2aa-108">Thông tin chi tiết về đối tượng cung cấp những trải nghiệm trong sản phẩm sau để xóa dữ liệu cá nhân cho một khách hàng hoặc người dùng cụ thể:</span><span class="sxs-lookup"><span data-stu-id="ab2aa-108">Audience insights offers the following in-product experiences to delete personal data for a specific customer or user:</span></span>

- <span data-ttu-id="ab2aa-109">**Quản lý yêu cầu xóa đối với dữ liệu khách hàng**: Dữ liệu khách hàng trong Customer Insights được nhập từ các nguồn dữ liệu ban đầu bên ngoài Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="ab2aa-109">**Manage delete requests for customer data**: Customer data in Customer Insights is ingested from original data sources external to Customer Insights.</span></span> <span data-ttu-id="ab2aa-110">Tất cả yêu cầu xóa theo GDPR phải được thực hiện trong nguồn dữ liệu gốc.</span><span class="sxs-lookup"><span data-stu-id="ab2aa-110">All GDPR delete requests must be performed in the original data source.</span></span>
- <span data-ttu-id="ab2aa-111">**Quản lý yêu cầu xóa đối với dữ liệu người dùng Customer Insights**: Dữ liệu cho người dùng được tạo bởi Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="ab2aa-111">**Manage delete requests for Customer Insights user data**: Data for users is created by Customer Insights.</span></span> <span data-ttu-id="ab2aa-112">Tất cả yêu cầu xóa GDPR phải được thực hiện trong Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="ab2aa-112">All GDPR delete requests must be performed in Customer Insights.</span></span>

#### <a name="manage-delete-requests-for-customer-data"></a><span data-ttu-id="ab2aa-113">Quản lý yêu cầu xóa dữ liệu khách hàng</span><span class="sxs-lookup"><span data-stu-id="ab2aa-113">Manage delete requests for customer data</span></span>

<span data-ttu-id="ab2aa-114">Quản trị viên Customer Insights có thể làm theo các bước sau để xóa dữ liệu khách hàng đã bị xóa trong nguồn dữ liệu:</span><span class="sxs-lookup"><span data-stu-id="ab2aa-114">A Customer Insights admin can follow these steps to remove customer data that was deleted in the data source:</span></span>

1. <span data-ttu-id="ab2aa-115">Đăng nhập vào Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="ab2aa-115">Sign in to Dynamics 365 Customer Insights.</span></span>
2. <span data-ttu-id="ab2aa-116">Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Dữ liệu** > **Nguồn dữ liệu**</span><span class="sxs-lookup"><span data-stu-id="ab2aa-116">In audience insights, go to **Data** > **Data sources**</span></span>
3. <span data-ttu-id="ab2aa-117">Đối với từng nguồn dữ liệu trong danh sách chứa dữ liệu khách hàng đã xóa:</span><span class="sxs-lookup"><span data-stu-id="ab2aa-117">For each data source in the list that contains deleted customer data:</span></span>
   1. <span data-ttu-id="ab2aa-118">Chọn (...) rồi chọn **Làm mới**.</span><span class="sxs-lookup"><span data-stu-id="ab2aa-118">Select (...) and then select **Refresh**.</span></span>
   2. <span data-ttu-id="ab2aa-119">Kiểm tra trạng thái nguồn dữ liệu trong **Trạng thái**.</span><span class="sxs-lookup"><span data-stu-id="ab2aa-119">Check the status of the data source under **Status**.</span></span> <span data-ttu-id="ab2aa-120">Một dấu kiểm có nghĩa là làm mới đã thành công.</span><span class="sxs-lookup"><span data-stu-id="ab2aa-120">A check mark means the refresh was successful.</span></span> <span data-ttu-id="ab2aa-121">Một tam giác cảnh báo có nghĩa là đã có vấn đề.</span><span class="sxs-lookup"><span data-stu-id="ab2aa-121">A warning triangle means something went wrong.</span></span> <span data-ttu-id="ab2aa-122">Nếu hình tam giác cảnh báo được hiển thị, hãy liên hệ với D365CI@microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="ab2aa-122">If a warning triangle is displayed, contact D365CI@microsoft.com.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ab2aa-123">![Xử lý yêu cầu xóa dữ liệu khách hàng theo GDPR](media/gdpr-data-sources.png "Xử lý yêu cầu xóa dữ liệu khách hàng theo GDPR")</span><span class="sxs-lookup"><span data-stu-id="ab2aa-123">![Handling GDPR delete requests for customer data](media/gdpr-data-sources.png "Handling GDPR delete requests for customer data")</span></span>

#### <a name="manage-delete-requests-for-user-data"></a><span data-ttu-id="ab2aa-124">Quản lý yêu cầu xóa dữ liệu người dùng</span><span class="sxs-lookup"><span data-stu-id="ab2aa-124">Manage delete requests for user data</span></span>

<span data-ttu-id="ab2aa-125">Quản trị viên Customer Insights có thể làm theo các bước sau để xóa dữ liệu người dùng Customer Insights:</span><span class="sxs-lookup"><span data-stu-id="ab2aa-125">A Customer Insights admin can follow these steps to delete Customer Insights user data:</span></span>

1. <span data-ttu-id="ab2aa-126">Đăng nhập vào Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="ab2aa-126">Sign in to Dynamics 365 Customer Insights.</span></span>
2. <span data-ttu-id="ab2aa-127">Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Quản trị** > **Quyền**.</span><span class="sxs-lookup"><span data-stu-id="ab2aa-127">In audience insights, go to **Admin** > **Permissions**.</span></span>
3. <span data-ttu-id="ab2aa-128">Chọn hộp kiểm tương ứng với người dùng bạn muốn xóa.</span><span class="sxs-lookup"><span data-stu-id="ab2aa-128">Select the check box for the user you want to delete.</span></span>
4. <span data-ttu-id="ab2aa-129">Chọn **Loại bỏ**.</span><span class="sxs-lookup"><span data-stu-id="ab2aa-129">Select **Remove**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ab2aa-130">![Xử lý yêu cầu xóa GDPR đối với dữ liệu người dùng](media/gdpr-permissions.png "Xử lý yêu cầu xóa dữ liệu người dùng theo GDPR")</span><span class="sxs-lookup"><span data-stu-id="ab2aa-130">![Handling GDPR delete requests foruser data](media/gdpr-permissions.png "Handling GDPR delete requests for user data")</span></span>

## <a name="responding-to-gdpr-data-subject-export-requests"></a><span data-ttu-id="ab2aa-131">Trả lời yêu cầu xuất của chủ thể dữ liệu theo GDPR</span><span class="sxs-lookup"><span data-stu-id="ab2aa-131">Responding to GDPR data subject export requests</span></span>

<span data-ttu-id="ab2aa-132">Là một phần trong cam kết của chúng tôi để hợp tác với bạn trên hành trình của bạn theo Quy định chung về bảo vệ dữ liệu (GDPR), chúng tôi đã phát triển tài liệu để giúp bạn chuẩn bị.</span><span class="sxs-lookup"><span data-stu-id="ab2aa-132">As part of our commitment to partner with you on your journey to the General Data Protection Regulation (GDPR), we’ve developed documentation to help you prepare.</span></span> <span data-ttu-id="ab2aa-133">Tài liệu này mô tả các bước bạn có thể thực hiện ngay hôm nay để hỗ trợ tuân thủ GDPR khi sử dụng thông tin chi tiết về đối tượng.</span><span class="sxs-lookup"><span data-stu-id="ab2aa-133">This documentation describes steps you can take today to support GDPR compliance when using audience insights.</span></span>

### <a name="manage-export-and-view-requests"></a><span data-ttu-id="ab2aa-134">Quản lý các yêu cầu xuất và xem</span><span class="sxs-lookup"><span data-stu-id="ab2aa-134">Manage export and view requests</span></span>

<span data-ttu-id="ab2aa-135">Quyền chuyển đổi dữ liệu cho phép chủ thể dữ liệu yêu cầu lấy bản sao dữ liệu cá nhân của họ ở định dạng điện tử ("định dạng có cấu trúc, thường dùng, có thể đọc được bằng máy và có thể tương tác") có thể được truyền đến đơn vị kiểm soát dữ liệu khác.</span><span class="sxs-lookup"><span data-stu-id="ab2aa-135">The right of data portability allows data subjects to request a copy of their personal data in an electronic format (a “structured, commonly used, machine readable, and interoperable format”) that can be transmitted to another data controller.</span></span>

#### <a name="export-customer-data-tenant-admin"></a><span data-ttu-id="ab2aa-136">Xuất dữ liệu khách hàng (quản trị viên đối tượng thuê)</span><span class="sxs-lookup"><span data-stu-id="ab2aa-136">Export customer data (tenant admin)</span></span>

<span data-ttu-id="ab2aa-137">Quản trị viên đối tượng thuê có thể tuân theo các bước sau để xuất dữ liệu:</span><span class="sxs-lookup"><span data-stu-id="ab2aa-137">A tenant administrator can follow these steps to export data:</span></span>

1. <span data-ttu-id="ab2aa-138">Gửi email tới D365CI@microsoft.com cho biết địa chỉ email của khách hàng trong yêu cầu.</span><span class="sxs-lookup"><span data-stu-id="ab2aa-138">Send an email to D365CI@microsoft.com specifying the customer’s email address in the request.</span></span> <span data-ttu-id="ab2aa-139">Nhóm Customer Insights sẽ gửi email đến địa chỉ email quản trị viên đối tượng thuê đã đăng ký, yêu cầu xác nhận để xuất dữ liệu.</span><span class="sxs-lookup"><span data-stu-id="ab2aa-139">The Customer Insights team will send an email to the registered tenant admin email address, asking for confirmation to export data.</span></span>
2. <span data-ttu-id="ab2aa-140">Hãy xác minh để xuất dữ liệu cho khách hàng yêu cầu.</span><span class="sxs-lookup"><span data-stu-id="ab2aa-140">Acknowledge the confirmation to export the data for the requested customer.</span></span>
3. <span data-ttu-id="ab2aa-141">Nhận dữ liệu được xuất thông qua địa chỉ email quản trị viên đối tượng thuê.</span><span class="sxs-lookup"><span data-stu-id="ab2aa-141">Receive the exported data through the tenant admin email address.</span></span>

#### <a name="export-user-data-tenant-admin"></a><span data-ttu-id="ab2aa-142">Xuất dữ liệu người dùng (quản trị viên đối tượng thuê)</span><span class="sxs-lookup"><span data-stu-id="ab2aa-142">Export user data (tenant admin)</span></span>

1. <span data-ttu-id="ab2aa-143">Gửi email tới D365CI@microsoft.com cho biết địa chỉ email của người dùng trong yêu cầu.</span><span class="sxs-lookup"><span data-stu-id="ab2aa-143">Send an email to D365CI@microsoft.com specifying the user’s email address in the request.</span></span> <span data-ttu-id="ab2aa-144">Nhóm Customer Insights sẽ gửi email đến địa chỉ email quản trị viên đối tượng thuê đã đăng ký, yêu cầu xác nhận để xuất dữ liệu.</span><span class="sxs-lookup"><span data-stu-id="ab2aa-144">The Customer Insights team will send an email to the registered tenant admin email address, asking for confirmation to export data.</span></span>
2. <span data-ttu-id="ab2aa-145">Hãy xác minh để xuất dữ liệu cho người dùng yêu cầu.</span><span class="sxs-lookup"><span data-stu-id="ab2aa-145">Acknowledge the confirmation to export the data for the requested user.</span></span>
3. <span data-ttu-id="ab2aa-146">Nhận dữ liệu được xuất thông qua địa chỉ email quản trị viên đối tượng thuê.</span><span class="sxs-lookup"><span data-stu-id="ab2aa-146">Receive the exported data through the tenant admin email address.</span></span>
