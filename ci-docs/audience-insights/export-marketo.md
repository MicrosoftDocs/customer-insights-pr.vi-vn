---
title: Xuất dữ liệu Customer Insights sang Marketo
description: Tìm hiểu cách đặt cấu hình kết nối và xuất sang Marketo.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 01290d5fae7af1737b73373d75e334ae1ed67d37
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759847"
---
# <a name="export-segments-to-marketo-preview"></a><span data-ttu-id="47ec2-103">Xuất phân khúc sang Marketo (bản xem trước)</span><span class="sxs-lookup"><span data-stu-id="47ec2-103">Export segments to Marketo (preview)</span></span>

<span data-ttu-id="47ec2-104">Xuất các phân đoạn hồ sơ khách hàng hợp nhất để tạo chiến dịch, cung cấp email tiếp thị và tận dụng các nhóm khách hàng cụ thể với Marketo.</span><span class="sxs-lookup"><span data-stu-id="47ec2-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="47ec2-105">Điều kiện tiên quyết để kết nối</span><span class="sxs-lookup"><span data-stu-id="47ec2-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="47ec2-106">Bạn có một [Tài khoản Marketo](https://login.marketo.com/) và thông tin đăng nhập quản trị viên tương ứng.</span><span class="sxs-lookup"><span data-stu-id="47ec2-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="47ec2-107">Có danh sách hiện có trong Marketo và các ID tương ứng.</span><span class="sxs-lookup"><span data-stu-id="47ec2-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="47ec2-108">Để biết thêm thông tin, hãy xem phần [Danh sách Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="47ec2-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="47ec2-109">Bạn có [các phân đoạn được định cấu hình](segments.md).</span><span class="sxs-lookup"><span data-stu-id="47ec2-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="47ec2-110">Hồ sơ khách hàng hợp nhất trong các phân đoạn đã xuất chứa các trường đại diện cho địa chỉ email.</span><span class="sxs-lookup"><span data-stu-id="47ec2-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="47ec2-111">Các giới hạn đã biết</span><span class="sxs-lookup"><span data-stu-id="47ec2-111">Known limitations</span></span>

- <span data-ttu-id="47ec2-112">Lên đến 1 triệu hồ sơ mỗi lần xuất sang Marketo.</span><span class="sxs-lookup"><span data-stu-id="47ec2-112">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="47ec2-113">Việc xuất sang Marketo bị giới hạn ở các phân đoạn.</span><span class="sxs-lookup"><span data-stu-id="47ec2-113">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="47ec2-114">Quá trình xuất phân đoạn với tổng số 1 triệu hồ sơ có thể mất đến 3 giờ.</span><span class="sxs-lookup"><span data-stu-id="47ec2-114">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="47ec2-115">Số lượng hồ sơ mà bạn có thể xuất sang Marketo phụ thuộc và giới hạn vào hợp đồng của bạn với Marketo.</span><span class="sxs-lookup"><span data-stu-id="47ec2-115">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="set-up-connection-to-marketo"></a><span data-ttu-id="47ec2-116">Thiết lập kết nối với Marketo</span><span class="sxs-lookup"><span data-stu-id="47ec2-116">Set up connection to Marketo</span></span>

1. <span data-ttu-id="47ec2-117">Đi đến **Quản trị viên** > **Kết nối**.</span><span class="sxs-lookup"><span data-stu-id="47ec2-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="47ec2-118">Chọn **Thêm kết nối** rồi chọn **Marketo** để đặt cấu hình kết nối.</span><span class="sxs-lookup"><span data-stu-id="47ec2-118">Select **Add connection** and choose **Marketo** to configure the connection.</span></span>

1. <span data-ttu-id="47ec2-119">Đặt tên dễ nhận biết cho kết nối trong trường **Tên hiển thị**.</span><span class="sxs-lookup"><span data-stu-id="47ec2-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="47ec2-120">Tên và loại kết nối mô tả kết nối này.</span><span class="sxs-lookup"><span data-stu-id="47ec2-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="47ec2-121">Bạn nên chọn một tên giải thích mục đích và mục tiêu của kết nối.</span><span class="sxs-lookup"><span data-stu-id="47ec2-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="47ec2-122">Chọn người có thể sử dụng kết nối này.</span><span class="sxs-lookup"><span data-stu-id="47ec2-122">Choose who can use this connection.</span></span> <span data-ttu-id="47ec2-123">Nếu bạn không thực hiện hành động nào, giá trị mặc định sẽ là Quản trị viên.</span><span class="sxs-lookup"><span data-stu-id="47ec2-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="47ec2-124">Để biết thêm thông tin, hãy xem [Cho phép người đóng góp sử dụng một kết nối cho các lần xuất](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="47ec2-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="47ec2-125">Nhập **[ID máy khách Marketo, Mã bí mật máy khách và Tên máy chủ điểm cuối REST](https://developers.marketo.com/rest-api/authentication/)**.</span><span class="sxs-lookup"><span data-stu-id="47ec2-125">Enter your **[Marketo client ID, Client secret, and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span>

1. <span data-ttu-id="47ec2-126">Chọn **Tôi đồng ý** để xác nhận **Quyền riêng tư về dữ liệu và sự tuân thủ** và chọn **Kết nối** để khởi tạo kết nối với Marketo.</span><span class="sxs-lookup"><span data-stu-id="47ec2-126">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="47ec2-127">Chọn **Thêm chính bạn là người dùng xuất** và cung cấp thông tin xác thực Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="47ec2-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="47ec2-128">Chọn **Lưu** để hoàn thành kết nối.</span><span class="sxs-lookup"><span data-stu-id="47ec2-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="47ec2-129">Đặt cấu hình xuất</span><span class="sxs-lookup"><span data-stu-id="47ec2-129">Configure an export</span></span>

<span data-ttu-id="47ec2-130">Bạn có thể đặt cấu hình lần xuất này nếu bạn có quyền truy cập vào kết nối thuộc loại này.</span><span class="sxs-lookup"><span data-stu-id="47ec2-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="47ec2-131">Để biết thêm thông tin, hãy xem [Các quyền cần thiết để đặt cấu hình xuất](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="47ec2-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="47ec2-132">Đi tới **Dữ liệu** > **Nội dung xuất**.</span><span class="sxs-lookup"><span data-stu-id="47ec2-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="47ec2-133">Để tạo một nội dung xuất mới, hãy chọn **Thêm đích**.</span><span class="sxs-lookup"><span data-stu-id="47ec2-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="47ec2-134">Trong trường **Kết nối để xuất**, hãy chọn một kết nối từ phần Marketo.</span><span class="sxs-lookup"><span data-stu-id="47ec2-134">In the **Connection for export** field, choose a connection from the Marketo section.</span></span> <span data-ttu-id="47ec2-135">Nếu bạn không thấy tên phần này, tức là không có kết nối nào thuộc loại này dành cho bạn.</span><span class="sxs-lookup"><span data-stu-id="47ec2-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="47ec2-136">Nhập **[ID danh sách Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span><span class="sxs-lookup"><span data-stu-id="47ec2-136">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span></span> 

1. <span data-ttu-id="47ec2-137">Trong phần **So khớp dữ liệu**, trong trường **Email**, chọn trường trong hồ sơ khách hàng hợp nhất trình bày địa chỉ email của khách hàng.</span><span class="sxs-lookup"><span data-stu-id="47ec2-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="47ec2-138">Bạn có thể tùy ý xuất **Tên**, **Họ**, **Thành phố**, **Tiểu bang** và **Quốc gia/Khu vực** để tạo thêm nhiều email được cá nhân hóa hơn.</span><span class="sxs-lookup"><span data-stu-id="47ec2-138">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  to create more personalized emails.</span></span> <span data-ttu-id="47ec2-139">Chọn **Thêm thuộc tính** để ánh xạ những trường này.</span><span class="sxs-lookup"><span data-stu-id="47ec2-139">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="47ec2-140">Chọn phân khúc mà bạn muốn xuất.</span><span class="sxs-lookup"><span data-stu-id="47ec2-140">Select the segments you want to export.</span></span> <span data-ttu-id="47ec2-141">Bạn có thể xuất tổng cộng tối đa 1 triệu hồ sơ khách hàng sang Marketo.</span><span class="sxs-lookup"><span data-stu-id="47ec2-141">You can export up to 1 million customer profiles in total to Marketo.</span></span>

1. <span data-ttu-id="47ec2-142">Chọn **Lưu**.</span><span class="sxs-lookup"><span data-stu-id="47ec2-142">Select **Save**.</span></span>

<span data-ttu-id="47ec2-143">Việc lưu một nội dung xuất sẽ không chạy nội dung xuất đó ngay lập tức.</span><span class="sxs-lookup"><span data-stu-id="47ec2-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="47ec2-144">Nội dung xuất chạy trong mỗi lần [làm mới theo lịch trình](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="47ec2-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="47ec2-145">Bạn cũng có thể [xuất dữ liệu theo yêu cầu](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="47ec2-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="47ec2-146">Trong Marketo, bạn hiện có thể tìm thấy các phân đoạn của mình trong [Danh sách Marketo](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="47ec2-146">In Marketo, you can now find your segments under [Marketo lists](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="47ec2-147">Quyền riêng tư về dữ liệu và sự tuân thủ</span><span class="sxs-lookup"><span data-stu-id="47ec2-147">Data privacy and compliance</span></span>

<span data-ttu-id="47ec2-148">Khi bật Dynamics 365 Customer Insights để truyền dữ liệu tới Marketo, bạn cho phép chuyển dữ liệu ra bên ngoài ranh giới tuân thủ cho Dynamics 365 Customer Insights, bao gồm dữ liệu nhạy cảm tiềm ẩn như Dữ liệu cá nhân.</span><span class="sxs-lookup"><span data-stu-id="47ec2-148">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="47ec2-149">Microsoft sẽ chuyển những dữ liệu đó theo chỉ dẫn của bạn, nhưng bạn có trách nhiệm đảm bảo rằng Marketo đáp ứng mọi nghĩa vụ về quyền riêng tư hoặc bảo mật mà bạn có thể có.</span><span class="sxs-lookup"><span data-stu-id="47ec2-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="47ec2-150">Để biết thêm thông tin, hãy xem [Tuyên bố về Quyền riêng tư của Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="47ec2-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="47ec2-151">Quản trị viên Dynamics 365 Customer Insights của bạn có thể xóa đích xuất này bất cứ lúc nào để ngừng sử dụng chức năng này.</span><span class="sxs-lookup"><span data-stu-id="47ec2-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]