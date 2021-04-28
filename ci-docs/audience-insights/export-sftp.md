---
title: Xuất dữ liệu Customer Insights sang máy chủ SFTP
description: Tìm hiểu cách đặt cấu hình kết nối và xuất sang vị trí SFTP.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 96c6026aded315008439740646827ca910cead90
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760445"
---
# <a name="export-segment-lists-and-other-data-to-sftp-preview"></a><span data-ttu-id="01c2b-103">Xuất danh sách phân khúc và dữ liệu khác sang SFTP (bản xem trước)</span><span class="sxs-lookup"><span data-stu-id="01c2b-103">Export segment lists and other data to SFTP (preview)</span></span>

<span data-ttu-id="01c2b-104">Sử dụng dữ liệu khách hàng của bạn trong các ứng dụng của bên thứ ba bằng cách xuất chúng sang vị trí Giao thức truyền tệp bảo mật (SFTP).</span><span class="sxs-lookup"><span data-stu-id="01c2b-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol (SFTP) location.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="01c2b-105">Điều kiện tiên quyết để kết nối</span><span class="sxs-lookup"><span data-stu-id="01c2b-105">Prerequisites for connection</span></span>

- <span data-ttu-id="01c2b-106">Tính khả dụng của máy chủ SFTP và thông tin đăng nhập tương ứng.</span><span class="sxs-lookup"><span data-stu-id="01c2b-106">Availability of an SFTP host and corresponding credentials.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="01c2b-107">Các giới hạn đã biết</span><span class="sxs-lookup"><span data-stu-id="01c2b-107">Known limitations</span></span>

- <span data-ttu-id="01c2b-108">Thời gian chạy của một lần xuất phụ thuộc vào hiệu suất hệ thống của bạn.</span><span class="sxs-lookup"><span data-stu-id="01c2b-108">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="01c2b-109">Chúng tôi khuyên bạn nên sử dụng máy chủ có tối thiểu hai lõi CPU và bộ nhớ 1 Gb.</span><span class="sxs-lookup"><span data-stu-id="01c2b-109">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="01c2b-110">Việc xuất các thực thể với tối đa 100 triệu hồ sơ khách hàng có thể mất 90 phút khi sử dụng cấu hình tối thiểu được khuyến nghị gồm CPU 2 lõi và 1 Gb bộ nhớ.</span><span class="sxs-lookup"><span data-stu-id="01c2b-110">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration of two CPU cores and 1 Gb of memory.</span></span> 

## <a name="set-up-connection-to-sftp"></a><span data-ttu-id="01c2b-111">Thiết lập kết nối với SFTP</span><span class="sxs-lookup"><span data-stu-id="01c2b-111">Set up connection to SFTP</span></span>

1. <span data-ttu-id="01c2b-112">Đi đến **Quản trị viên** > **Kết nối**.</span><span class="sxs-lookup"><span data-stu-id="01c2b-112">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="01c2b-113">Chọn **Thêm kết nối** rồi chọn **SFTP** để đặt cấu hình kết nối.</span><span class="sxs-lookup"><span data-stu-id="01c2b-113">Select **Add connection** and choose **SFTP** to configure the connection.</span></span>

1. <span data-ttu-id="01c2b-114">Đặt tên dễ nhận biết cho kết nối trong trường **Tên hiển thị**.</span><span class="sxs-lookup"><span data-stu-id="01c2b-114">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="01c2b-115">Tên và loại kết nối mô tả kết nối này.</span><span class="sxs-lookup"><span data-stu-id="01c2b-115">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="01c2b-116">Bạn nên chọn một tên giải thích mục đích và mục tiêu của kết nối.</span><span class="sxs-lookup"><span data-stu-id="01c2b-116">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="01c2b-117">Chọn người có thể sử dụng kết nối này.</span><span class="sxs-lookup"><span data-stu-id="01c2b-117">Choose who can use this connection.</span></span> <span data-ttu-id="01c2b-118">Nếu bạn không thực hiện hành động nào, giá trị mặc định sẽ là Quản trị viên.</span><span class="sxs-lookup"><span data-stu-id="01c2b-118">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="01c2b-119">Để biết thêm thông tin, hãy xem [Cho phép người đóng góp sử dụng một kết nối cho các lần xuất](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="01c2b-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="01c2b-120">Cung cấp **Tên người dùng**, **Mật khẩu**, **Tên máy chủ** và **Thư mục xuất** cho tài khoản SFTP của bạn.</span><span class="sxs-lookup"><span data-stu-id="01c2b-120">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="01c2b-121">Chọn **Xác minh** để kiểm tra kết nối.</span><span class="sxs-lookup"><span data-stu-id="01c2b-121">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="01c2b-122">Chọn nếu bạn muốn xuất dữ liệu **Đã nén** hoặc **Đã giải nén** của mình và **dấu tách trường** cho các tệp đã xuất.</span><span class="sxs-lookup"><span data-stu-id="01c2b-122">Choose if you want to export your data **Gzipped** or **Unzipped** and the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="01c2b-123">Chọn **Tôi đồng ý** để xác nhận **Quyền riêng tư về dữ liệu và sự tuân thủ**.</span><span class="sxs-lookup"><span data-stu-id="01c2b-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="01c2b-124">Chọn **Lưu** để hoàn thành kết nối.</span><span class="sxs-lookup"><span data-stu-id="01c2b-124">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="01c2b-125">Đặt cấu hình xuất</span><span class="sxs-lookup"><span data-stu-id="01c2b-125">Configure an export</span></span>

<span data-ttu-id="01c2b-126">Bạn có thể đặt cấu hình lần xuất này nếu bạn có quyền truy cập vào kết nối thuộc loại này.</span><span class="sxs-lookup"><span data-stu-id="01c2b-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="01c2b-127">Để biết thêm thông tin, hãy xem [Các quyền cần thiết để đặt cấu hình xuất](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="01c2b-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="01c2b-128">Đi tới **Dữ liệu** > **Nội dung xuất**.</span><span class="sxs-lookup"><span data-stu-id="01c2b-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="01c2b-129">Để tạo một nội dung xuất mới, hãy chọn **Thêm đích**.</span><span class="sxs-lookup"><span data-stu-id="01c2b-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="01c2b-130">Trong trường **Kết nối để xuất**, hãy chọn một kết nối từ phần SFTP.</span><span class="sxs-lookup"><span data-stu-id="01c2b-130">In the **Connection for export** field, choose a connection from the SFTP section.</span></span> <span data-ttu-id="01c2b-131">Nếu bạn không thấy tên phần này, tức là không có kết nối nào thuộc loại này dành cho bạn.</span><span class="sxs-lookup"><span data-stu-id="01c2b-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="01c2b-132">Chọn các thực thể, ví dụ như phân đoạn, bạn muốn xuất.</span><span class="sxs-lookup"><span data-stu-id="01c2b-132">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="01c2b-133">Mỗi thực thể đã chọn sẽ được chia thành tối đa năm tệp đầu ra khi xuất.</span><span class="sxs-lookup"><span data-stu-id="01c2b-133">Each selected entity will be split up into up to five output files when exported.</span></span> 

1. <span data-ttu-id="01c2b-134">Chọn **Lưu**.</span><span class="sxs-lookup"><span data-stu-id="01c2b-134">Select **Save**.</span></span>

<span data-ttu-id="01c2b-135">Việc lưu một nội dung xuất sẽ không chạy nội dung xuất đó ngay lập tức.</span><span class="sxs-lookup"><span data-stu-id="01c2b-135">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="01c2b-136">Nội dung xuất chạy trong mỗi lần [làm mới theo lịch trình](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="01c2b-136">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="01c2b-137">Bạn cũng có thể [xuất dữ liệu theo yêu cầu](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="01c2b-137">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="01c2b-138">Quyền riêng tư về dữ liệu và sự tuân thủ</span><span class="sxs-lookup"><span data-stu-id="01c2b-138">Data privacy and compliance</span></span>

<span data-ttu-id="01c2b-139">Khi bật Dynamics 365 Customer Insights để truyền dữ liệu qua SFTP, bạn cho phép chuyển dữ liệu ra bên ngoài ranh giới tuân thủ cho Dynamics 365 Customer Insights, bao gồm dữ liệu nhạy cảm tiềm ẩn như Dữ liệu cá nhân.</span><span class="sxs-lookup"><span data-stu-id="01c2b-139">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="01c2b-140">Microsoft sẽ chuyển những dữ liệu đó theo chỉ dẫn của bạn, nhưng bạn có trách nhiệm đảm bảo rằng điểm đến xuất đáp ứng mọi nghĩa vụ về quyền riêng tư hoặc bảo mật mà bạn có thể có.</span><span class="sxs-lookup"><span data-stu-id="01c2b-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="01c2b-141">Để biết thêm thông tin, hãy xem [Tuyên bố về Quyền riêng tư của Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="01c2b-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="01c2b-142">Quản trị viên Dynamics 365 Customer Insights của bạn có thể xóa đích xuất này bất cứ lúc nào để ngừng sử dụng chức năng này.</span><span class="sxs-lookup"><span data-stu-id="01c2b-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
