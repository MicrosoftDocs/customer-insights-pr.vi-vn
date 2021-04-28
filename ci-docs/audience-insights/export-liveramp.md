---
title: Trình kết nối LiveRamp
description: Tìm hiểu cách đặt cấu hình kết nối và xuất sang LiveRamp.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 987457966fe1fc034d9e3cd2a1ce33902c7a84f4
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760353"
---
# <a name="export-segments-to-liverampreg-preview"></a><span data-ttu-id="1ee39-103">Xuất phân khúc sang LiveRamp&reg; (bản xem trước)</span><span class="sxs-lookup"><span data-stu-id="1ee39-103">Export segments to LiveRamp&reg; (preview)</span></span>

<span data-ttu-id="1ee39-104">Kích hoạt dữ liệu của bạn trong LiveRamp để kết nối với hơn 500 nền tảng kỹ thuật số, mạng xã hội và TV.</span><span class="sxs-lookup"><span data-stu-id="1ee39-104">Activate your data in LiveRamp to connect with over 500 platforms across digital, social, and TVs.</span></span> <span data-ttu-id="1ee39-105">Làm việc với dữ liệu của bạn trong LiveRamp nhắm mục tiêu, chặn và cá nhân hóa chiến dịch quảng cáo.</span><span class="sxs-lookup"><span data-stu-id="1ee39-105">Work with your data in LiveRamp to target, suppress, and personalize ad campaigns.</span></span>

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="1ee39-106">Điều kiện tiên quyết để kết nối</span><span class="sxs-lookup"><span data-stu-id="1ee39-106">Prerequisites for a connection</span></span>

- <span data-ttu-id="1ee39-107">Bạn phải có gói đăng ký LiveRamp thì mới dùng được trình kết nối này.</span><span class="sxs-lookup"><span data-stu-id="1ee39-107">You need a LiveRamp subscription to use this connector.</span></span>
- <span data-ttu-id="1ee39-108">Để đăng ký, hãy trực tiếp [liên hệ với LiveRamp](https://liveramp.com/contact/).</span><span class="sxs-lookup"><span data-stu-id="1ee39-108">To get a subscription, [contact LiveRamp](https://liveramp.com/contact/) directly.</span></span> <span data-ttu-id="1ee39-109">[Tìm hiểu thêm về LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span><span class="sxs-lookup"><span data-stu-id="1ee39-109">[Learn more about LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span></span>

## <a name="set-up-connection-to-liveramp"></a><span data-ttu-id="1ee39-110">Thiết lập kết nối với LiveRamp</span><span class="sxs-lookup"><span data-stu-id="1ee39-110">Set up connection to LiveRamp</span></span>

1. <span data-ttu-id="1ee39-111">Đi đến **Quản trị viên** > **Kết nối**.</span><span class="sxs-lookup"><span data-stu-id="1ee39-111">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="1ee39-112">Chọn **Thêm kết nối** rồi chọn **LiveRamp** để đặt cấu hình kết nối.</span><span class="sxs-lookup"><span data-stu-id="1ee39-112">Select **Add connection** and choose **LiveRamp** to configure the connection.</span></span>

1. <span data-ttu-id="1ee39-113">Đặt tên dễ nhận biết cho kết nối trong trường **Tên hiển thị**.</span><span class="sxs-lookup"><span data-stu-id="1ee39-113">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="1ee39-114">Tên và loại kết nối mô tả kết nối này.</span><span class="sxs-lookup"><span data-stu-id="1ee39-114">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="1ee39-115">Bạn nên chọn một tên giải thích mục đích và mục tiêu của kết nối.</span><span class="sxs-lookup"><span data-stu-id="1ee39-115">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="1ee39-116">Chọn người có thể sử dụng kết nối này.</span><span class="sxs-lookup"><span data-stu-id="1ee39-116">Choose who can use this connection.</span></span> <span data-ttu-id="1ee39-117">Nếu bạn không thực hiện hành động nào, giá trị mặc định sẽ là Quản trị viên.</span><span class="sxs-lookup"><span data-stu-id="1ee39-117">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="1ee39-118">Để biết thêm thông tin, hãy xem [Cho phép người đóng góp sử dụng một kết nối cho các lần xuất](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="1ee39-118">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="1ee39-119">Điền **Tên người dùng** và **Mật khẩu** cho tài khoản LiveRamp Secure FTP (SFTP) của bạn.</span><span class="sxs-lookup"><span data-stu-id="1ee39-119">Provide a **Username** and **Password** for your LiveRamp Secure FTP (SFTP) account.</span></span>
<span data-ttu-id="1ee39-120">Thông tin đăng nhập này có thể khác với thông tin đăng nhập LiveRamp Onboarding.</span><span class="sxs-lookup"><span data-stu-id="1ee39-120">These credentials may be different from your LiveRamp Onboarding credentials.</span></span>

1. <span data-ttu-id="1ee39-121">Chọn **Xác minh** để kiểm tra kết nối với LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="1ee39-121">Select **Verify** to test the connection to LiveRamp.</span></span>

1. <span data-ttu-id="1ee39-122">Sau khi xác minh xong, hãy đồng ý với **Quyền riêng tư và tuân thủ dữ liệu** bằng cách đánh dấu vào ô **Tôi đồng ý**.</span><span class="sxs-lookup"><span data-stu-id="1ee39-122">After successful verification, provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="1ee39-123">Chọn **Lưu** để hoàn thành kết nối.</span><span class="sxs-lookup"><span data-stu-id="1ee39-123">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="1ee39-124">Đặt cấu hình xuất</span><span class="sxs-lookup"><span data-stu-id="1ee39-124">Configure an export</span></span>

<span data-ttu-id="1ee39-125">Bạn có thể đặt cấu hình lần xuất này nếu bạn có quyền truy cập vào kết nối thuộc loại này.</span><span class="sxs-lookup"><span data-stu-id="1ee39-125">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="1ee39-126">Để biết thêm thông tin, hãy xem [Các quyền cần thiết để đặt cấu hình xuất](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="1ee39-126">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="1ee39-127">Đi tới **Dữ liệu** > **Nội dung xuất**.</span><span class="sxs-lookup"><span data-stu-id="1ee39-127">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="1ee39-128">Để tạo một nội dung xuất mới, hãy chọn **Thêm đích**.</span><span class="sxs-lookup"><span data-stu-id="1ee39-128">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="1ee39-129">Trong trường **Kết nối để xuất**, hãy chọn một kết nối từ phần LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="1ee39-129">In the **Connection for export** field, choose a connection from the LiveRamp section.</span></span> <span data-ttu-id="1ee39-130">Nếu bạn không thấy tên phần này, tức là không có kết nối nào thuộc loại này dành cho bạn.</span><span class="sxs-lookup"><span data-stu-id="1ee39-130">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="1ee39-131">Trong trường **Chọn khóa định danh**, chọn **Email**,  **Tên và địa chỉ** hoặc **Điện thoại** để gửi phương án định danh cho LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="1ee39-131">In the **Choose your key identifier** field, select **Email**,  **Name and address**, or **Phone** to send to LiveRamp for identity resolution.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1ee39-132">![Trình kết nối LiveRamp khi ánh xạ thuộc tính](media/export-liveramp-segments.png "Trình kết nối LiveRamp khi ánh xạ thuộc tính")</span><span class="sxs-lookup"><span data-stu-id="1ee39-132">![LiveRamp connector with attribute mapping](media/export-liveramp-segments.png "LiveRamp connector with attribute mapping")</span></span>

1. <span data-ttu-id="1ee39-133">Ánh xạ các thuộc tính tương ứng từ thực thể khách hàng hợp nhất của bạn cho khóa định danh đã chọn.</span><span class="sxs-lookup"><span data-stu-id="1ee39-133">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>

1. <span data-ttu-id="1ee39-134">Chọn **Thêm thuộc tính** để ánh xạ thêm các thuộc tính cho mục đích gửi đến LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="1ee39-134">Select **Add attribute** to map more attributes to send to LiveRamp.</span></span>

   > [!TIP]
   > <span data-ttu-id="1ee39-135">Khi gửi thêm thuộc tính khóa định danh đến LiveRamp, bạn sẽ có tỷ lệ khớp cao hơn.</span><span class="sxs-lookup"><span data-stu-id="1ee39-135">Sending more key identifier attributes to LiveRamp is likely to get you a higher match rate.</span></span>

1. <span data-ttu-id="1ee39-136">Chọn các phân đoạn bạn muốn xuất sang LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="1ee39-136">Select the segments you want to export to LiveRamp.</span></span>

1. <span data-ttu-id="1ee39-137">Chọn **Lưu**.</span><span class="sxs-lookup"><span data-stu-id="1ee39-137">Select **Save**.</span></span>

<span data-ttu-id="1ee39-138">Việc lưu một nội dung xuất sẽ không chạy nội dung xuất đó ngay lập tức.</span><span class="sxs-lookup"><span data-stu-id="1ee39-138">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="1ee39-139">Nội dung xuất chạy trong mỗi lần [làm mới theo lịch trình](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="1ee39-139">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="1ee39-140">Bạn cũng có thể [xuất dữ liệu theo yêu cầu](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="1ee39-140">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="1ee39-141">Quyền riêng tư về dữ liệu và sự tuân thủ</span><span class="sxs-lookup"><span data-stu-id="1ee39-141">Data privacy and compliance</span></span>

<span data-ttu-id="1ee39-142">Khi bật Dynamics 365 Customer Insights để truyền dữ liệu tới Liveramp, bạn cho phép chuyển dữ liệu ra bên ngoài ranh giới tuân thủ cho Dynamics 365 Customer Insights, bao gồm dữ liệu nhạy cảm tiềm ẩn như Dữ liệu cá nhân.</span><span class="sxs-lookup"><span data-stu-id="1ee39-142">When you enable Dynamics 365 Customer Insights to transmit data to Liveramp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="1ee39-143">Microsoft sẽ chuyển những dữ liệu đó theo chỉ dẫn của bạn, nhưng bạn có trách nhiệm đảm bảo rằng Liveramp đáp ứng mọi nghĩa vụ về quyền riêng tư hoặc bảo mật mà bạn có thể có.</span><span class="sxs-lookup"><span data-stu-id="1ee39-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Liveramp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="1ee39-144">Để biết thêm thông tin, hãy xem [Tuyên bố về Quyền riêng tư của Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="1ee39-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="1ee39-145">Quản trị viên Dynamics 365 Customer Insights của bạn có thể xóa đích xuất này bất cứ lúc nào để ngừng sử dụng chức năng này.</span><span class="sxs-lookup"><span data-stu-id="1ee39-145">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
