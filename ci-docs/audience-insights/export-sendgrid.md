---
title: Xuất dữ liệu Customer Insights sang SendGrid
description: Tìm hiểu cách đặt cấu hình kết nối và xuất sang SendGrid.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 5d3d61d2b5b68079c7717e41dee5a2f698f2b62c
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976942"
---
# <a name="export-segments-to-sendgrid-preview"></a><span data-ttu-id="e66c9-103">Xuất phân khúc sang SendGrid (bản xem trước)</span><span class="sxs-lookup"><span data-stu-id="e66c9-103">Export segments to SendGrid (preview)</span></span>

<span data-ttu-id="e66c9-104">Xuất phân đoạn hồ sơ khách hàng hợp nhất sang danh sách liên hệ SendGrid và sử dụng chúng cho các chiến dịch và tiếp thị qua email trong SendGrid.</span><span class="sxs-lookup"><span data-stu-id="e66c9-104">Export segments of unified customer profiles to SendGrid contact lists and use them for campaigns and email marketing in SendGrid.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="e66c9-105">Điều kiện tiên quyết để kết nối</span><span class="sxs-lookup"><span data-stu-id="e66c9-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="e66c9-106">Bạn có một [Tài khoản SendGrid](https://sendgrid.com/) và thông tin đăng nhập quản trị viên tương ứng.</span><span class="sxs-lookup"><span data-stu-id="e66c9-106">You have a [SendGrid account](https://sendgrid.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="e66c9-107">Có danh sách liên hệ hiện có trong SendGrid và các ID tương ứng.</span><span class="sxs-lookup"><span data-stu-id="e66c9-107">There are existing contact lists in SendGrid and the corresponding IDs.</span></span> <span data-ttu-id="e66c9-108">Để biết thêm thông tin, hãy xem [SendGrid - Quản lý liên hệ](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span><span class="sxs-lookup"><span data-stu-id="e66c9-108">For more information, see [SendGrid - Manage contacts](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span></span>
-   <span data-ttu-id="e66c9-109">Bạn có [các phân đoạn được định cấu hình](segments.md) trong thông tin chi tiết về đối tượng.</span><span class="sxs-lookup"><span data-stu-id="e66c9-109">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="e66c9-110">Hồ sơ khách hàng hợp nhất trong các phân đoạn đã xuất chứa các trường đại diện cho địa chỉ email.</span><span class="sxs-lookup"><span data-stu-id="e66c9-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="e66c9-111">Các giới hạn đã biết</span><span class="sxs-lookup"><span data-stu-id="e66c9-111">Known limitations</span></span>

- <span data-ttu-id="e66c9-112">Tối đa 100.000 hồ sơ trên SendGrid.</span><span class="sxs-lookup"><span data-stu-id="e66c9-112">Up to 100'000 profiles in total to SendGrid.</span></span>
- <span data-ttu-id="e66c9-113">Việc xuất sang SendGrid bị giới hạn ở các phân đoạn.</span><span class="sxs-lookup"><span data-stu-id="e66c9-113">Exporting to SendGrid is limited to segments.</span></span>
- <span data-ttu-id="e66c9-114">Có thể mất tới vài giờ để hoàn thành việc xuất lên đến 100.000 hồ sơ sang SendGrid.</span><span class="sxs-lookup"><span data-stu-id="e66c9-114">Exporting up to 100'000 profiles to SendGrid can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="e66c9-115">Số lượng hồ sơ mà bạn có thể xuất sang SendGrid còn phụ thuộc vào giới hạn cho hợp đồng của bạn với SendGrid.</span><span class="sxs-lookup"><span data-stu-id="e66c9-115">The number of profiles that you can export to SendGrid is dependent and limited on your contract with SendGrid.</span></span>

## <a name="set-up-connection-to-sendgrid"></a><span data-ttu-id="e66c9-116">Thiết lập kết nối với SendGrid</span><span class="sxs-lookup"><span data-stu-id="e66c9-116">Set up connection to SendGrid</span></span>

1. <span data-ttu-id="e66c9-117">Đi đến **Quản trị viên** > **Kết nối**.</span><span class="sxs-lookup"><span data-stu-id="e66c9-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="e66c9-118">Chọn **Thêm kết nối** rồi chọn **SendGrid** để đặt cấu hình kết nối.</span><span class="sxs-lookup"><span data-stu-id="e66c9-118">Select **Add connection** and choose **SendGrid** to configure the connection.</span></span>

1. <span data-ttu-id="e66c9-119">Đặt tên dễ nhận biết cho kết nối trong trường **Tên hiển thị**.</span><span class="sxs-lookup"><span data-stu-id="e66c9-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="e66c9-120">Tên và loại kết nối mô tả kết nối này.</span><span class="sxs-lookup"><span data-stu-id="e66c9-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="e66c9-121">Bạn nên chọn một tên giải thích mục đích và mục tiêu của kết nối.</span><span class="sxs-lookup"><span data-stu-id="e66c9-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="e66c9-122">Chọn người có thể sử dụng kết nối này.</span><span class="sxs-lookup"><span data-stu-id="e66c9-122">Choose who can use this connection.</span></span> <span data-ttu-id="e66c9-123">Nếu bạn không thực hiện hành động nào, giá trị mặc định sẽ là Quản trị viên.</span><span class="sxs-lookup"><span data-stu-id="e66c9-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="e66c9-124">Để biết thêm thông tin, hãy xem [Cho phép người đóng góp sử dụng một kết nối cho các lần xuất](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="e66c9-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="e66c9-125">Nhập **Khóa API SendGrid** [Khóa API SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span><span class="sxs-lookup"><span data-stu-id="e66c9-125">Enter your **SendGrid API key** [SendGrid API key](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span></span>

1. <span data-ttu-id="e66c9-126">Chọn **Tôi đồng ý** để xác nhận **Quyền riêng tư về dữ liệu và sự tuân thủ**.</span><span class="sxs-lookup"><span data-stu-id="e66c9-126">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="e66c9-127">Chọn **Kết nối** để khởi tạo kết nối với SendGrid.</span><span class="sxs-lookup"><span data-stu-id="e66c9-127">Select **Connect** to initialize the connection to SendGrid.</span></span>

1. <span data-ttu-id="e66c9-128">Chọn **Thêm chính bạn là người dùng xuất** và cung cấp thông tin xác thực Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="e66c9-128">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="e66c9-129">Chọn **Lưu** để hoàn thành kết nối.</span><span class="sxs-lookup"><span data-stu-id="e66c9-129">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="e66c9-130">Đặt cấu hình xuất</span><span class="sxs-lookup"><span data-stu-id="e66c9-130">Configure an export</span></span>

<span data-ttu-id="e66c9-131">Bạn có thể đặt cấu hình lần xuất này nếu bạn có quyền truy cập vào kết nối thuộc loại này.</span><span class="sxs-lookup"><span data-stu-id="e66c9-131">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="e66c9-132">Để biết thêm thông tin, hãy xem [Các quyền cần thiết để đặt cấu hình xuất](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="e66c9-132">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="e66c9-133">Đi tới **Dữ liệu** > **Nội dung xuất**.</span><span class="sxs-lookup"><span data-stu-id="e66c9-133">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e66c9-134">Để tạo một nội dung xuất mới, hãy chọn **Thêm đích**.</span><span class="sxs-lookup"><span data-stu-id="e66c9-134">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="e66c9-135">Trong trường **Kết nối để xuất**, hãy chọn một kết nối từ phần SendGrid.</span><span class="sxs-lookup"><span data-stu-id="e66c9-135">In the **Connection for export** field, choose a connection from the SendGrid section.</span></span> <span data-ttu-id="e66c9-136">Nếu bạn không thấy tên phần này, tức là không có kết nối nào thuộc loại này dành cho bạn.</span><span class="sxs-lookup"><span data-stu-id="e66c9-136">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="e66c9-137">Nhập **[ID danh sách SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span><span class="sxs-lookup"><span data-stu-id="e66c9-137">Enter your **[SendGrid list ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span></span>

1. <span data-ttu-id="e66c9-138">Trong phần **So khớp dữ liệu**, trong trường **Email**, chọn trường trong hồ sơ khách hàng hợp nhất trình bày địa chỉ email của khách hàng.</span><span class="sxs-lookup"><span data-stu-id="e66c9-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="e66c9-139">Lặp lại các bước tương tự cho các trường tùy chọn khác như **Tên**, **Họ**, **Quốc gia/Khu vực**, **Tiểu bang**, **Thành phố** và **Mã bưu điện**.</span><span class="sxs-lookup"><span data-stu-id="e66c9-139">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Country/Region**, **State**, **City**, and **Post code**.</span></span>

1. <span data-ttu-id="e66c9-140">Chọn phân khúc mà bạn muốn xuất.</span><span class="sxs-lookup"><span data-stu-id="e66c9-140">Select the segments you want to export.</span></span> <span data-ttu-id="e66c9-141">Chúng tôi **khuyên bạn không nên xuất tổng cộng hơn 100.000 hồ sơ khách hàng** tới SendGrid.</span><span class="sxs-lookup"><span data-stu-id="e66c9-141">We strongly **recommend to not export more than 100'000 customer profiles in total** to SendGrid.</span></span> 

1. <span data-ttu-id="e66c9-142">Chọn **Lưu**.</span><span class="sxs-lookup"><span data-stu-id="e66c9-142">Select **Save**.</span></span>

<span data-ttu-id="e66c9-143">Việc lưu một nội dung xuất sẽ không chạy nội dung xuất đó ngay lập tức.</span><span class="sxs-lookup"><span data-stu-id="e66c9-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="e66c9-144">Nội dung xuất chạy trong mỗi lần [làm mới theo lịch trình](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="e66c9-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="e66c9-145">Bạn cũng có thể [xuất dữ liệu theo yêu cầu](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="e66c9-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="e66c9-146">Quyền riêng tư về dữ liệu và sự tuân thủ</span><span class="sxs-lookup"><span data-stu-id="e66c9-146">Data privacy and compliance</span></span>

<span data-ttu-id="e66c9-147">Khi bật Dynamics 365 Customer Insights để truyền dữ liệu tới SendGrid, bạn cho phép chuyển dữ liệu ra bên ngoài ranh giới tuân thủ cho Dynamics 365 Customer Insights, bao gồm dữ liệu nhạy cảm tiềm ẩn như Dữ liệu cá nhân.</span><span class="sxs-lookup"><span data-stu-id="e66c9-147">When you enable Dynamics 365 Customer Insights to transmit data to SendGrid, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="e66c9-148">Microsoft sẽ chuyển những dữ liệu đó theo chỉ dẫn của bạn, nhưng bạn có trách nhiệm đảm bảo rằng SendGrid đáp ứng mọi nghĩa vụ về quyền riêng tư hoặc bảo mật mà bạn có thể có.</span><span class="sxs-lookup"><span data-stu-id="e66c9-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that SendGrid meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="e66c9-149">Để biết thêm thông tin, hãy xem [Tuyên bố về Quyền riêng tư của Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="e66c9-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="e66c9-150">Quản trị viên Dynamics 365 Customer Insights của bạn có thể xóa đích xuất này bất cứ lúc nào để ngừng sử dụng chức năng này.</span><span class="sxs-lookup"><span data-stu-id="e66c9-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]