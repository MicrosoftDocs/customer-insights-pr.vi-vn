---
title: Xuất dữ liệu Customer Insights sang Salesforce Marketing Cloud
description: Tìm hiểu cách định cấu hình kết nối và xuất sang Salesforce Marketing Cloud.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 123f8b2dbb6140785dec6c1b4164d2f513f66a53
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314693"
---
# <a name="export-segments-and-other-data-to-salesforce-marketing-cloud-preview"></a><span data-ttu-id="698dd-103">Xuất các phân khúc và dữ liệu khác sang Salesforce Marketing Cloud (bản xem trước)</span><span class="sxs-lookup"><span data-stu-id="698dd-103">Export segments and other data to Salesforce Marketing Cloud (preview)</span></span>

<span data-ttu-id="698dd-104">Sử dụng dữ liệu khách hàng của bạn trong Salesforce Marketing Cloud bằng cách xuất sang vị trí Giao thức truyền tệp bảo mật (SFTP).</span><span class="sxs-lookup"><span data-stu-id="698dd-104">Use your customer data in Salesforce Marketing Cloud by exporting them through a Secure File Transfer Protocol (SFTP) location.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="698dd-105">Điều kiện tiên quyết để kết nối</span><span class="sxs-lookup"><span data-stu-id="698dd-105">Prerequisites for connection</span></span>

- <span data-ttu-id="698dd-106">Tính khả dụng của máy chủ SFTP và thông tin xác thực tương ứng của quản trị viên.</span><span class="sxs-lookup"><span data-stu-id="698dd-106">Availability of an SFTP host and corresponding admin credentials.</span></span> [<span data-ttu-id="698dd-107">Cách thiết lập vị trí SFTP cho Salesforce Marketing Cloud</span><span class="sxs-lookup"><span data-stu-id="698dd-107">How to setup SFTP locations for Salesforce Marketing Cloud</span></span>](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) 

## <a name="known-limitations"></a><span data-ttu-id="698dd-108">Các hạn chế đã biết</span><span class="sxs-lookup"><span data-stu-id="698dd-108">Known limitations</span></span>

- <span data-ttu-id="698dd-109">Thời gian chạy của một lần xuất phụ thuộc vào hiệu suất hệ thống của bạn.</span><span class="sxs-lookup"><span data-stu-id="698dd-109">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="698dd-110">Chúng tôi khuyên bạn nên sử dụng máy chủ có tối thiểu hai lõi CPU và bộ nhớ 1 Gb.</span><span class="sxs-lookup"><span data-stu-id="698dd-110">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="698dd-111">Quy trình xuất các thực thể lên đến 100 triệu hồ sơ khách hàng có thể mất 90 phút khi sử dụng cấu hình tối thiểu được đề xuất.</span><span class="sxs-lookup"><span data-stu-id="698dd-111">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration.</span></span> 

## <a name="set-up-the-connection-to-salesforce-marketing-cloud"></a><span data-ttu-id="698dd-112">Thiết lập kết nối đến Salesforce Marketing Cloud</span><span class="sxs-lookup"><span data-stu-id="698dd-112">Set up the connection to Salesforce Marketing Cloud</span></span>

1. <span data-ttu-id="698dd-113">Đi đến **Quản trị viên** > **Kết nối**.</span><span class="sxs-lookup"><span data-stu-id="698dd-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="698dd-114">Chọn **Thêm kết nối** rồi chọn **Salesforce Marketing Cloud** để định cấu hình kết nối.</span><span class="sxs-lookup"><span data-stu-id="698dd-114">Select **Add connection** and choose **Salesforce Marketing Cloud** to configure the connection.</span></span>

1. <span data-ttu-id="698dd-115">Đặt tên dễ nhận biết cho kết nối trong trường **Tên hiển thị**.</span><span class="sxs-lookup"><span data-stu-id="698dd-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="698dd-116">Tên và loại kết nối mô tả kết nối này.</span><span class="sxs-lookup"><span data-stu-id="698dd-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="698dd-117">Bạn nên chọn một tên giải thích mục đích và mục tiêu của kết nối.</span><span class="sxs-lookup"><span data-stu-id="698dd-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="698dd-118">Chọn người có thể sử dụng kết nối này.</span><span class="sxs-lookup"><span data-stu-id="698dd-118">Choose who can use this connection.</span></span> <span data-ttu-id="698dd-119">Nếu bạn không thực hiện hành động nào, giá trị mặc định sẽ là Quản trị viên.</span><span class="sxs-lookup"><span data-stu-id="698dd-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="698dd-120">Để biết thêm thông tin, hãy xem [Cho phép người đóng góp sử dụng một kết nối cho các lần xuất](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="698dd-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="698dd-121">Cung cấp **Tên người dùng**, **Mật khẩu**, **Tên máy chủ** và **Thư mục xuất** cho tài khoản SFTP của bạn.</span><span class="sxs-lookup"><span data-stu-id="698dd-121">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="698dd-122">Chọn **Xác minh** để kiểm tra kết nối.</span><span class="sxs-lookup"><span data-stu-id="698dd-122">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="698dd-123">Chọn **Tôi đồng ý** để xác nhận **Quyền riêng tư về dữ liệu và sự tuân thủ**.</span><span class="sxs-lookup"><span data-stu-id="698dd-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="698dd-124">Chọn **Lưu** để hoàn thành kết nối.</span><span class="sxs-lookup"><span data-stu-id="698dd-124">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="698dd-125">Định cấu hình xuất</span><span class="sxs-lookup"><span data-stu-id="698dd-125">Configure an export</span></span>

<span data-ttu-id="698dd-126">Bạn có thể định cấu hình lần xuất này nếu bạn có quyền truy cập vào kết nối thuộc loại này.</span><span class="sxs-lookup"><span data-stu-id="698dd-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="698dd-127">Để biết thêm thông tin, hãy xem [Các quyền cần thiết để định cấu hình xuất](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="698dd-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="698dd-128">Đi tới **Dữ liệu** > **Nội dung xuất**.</span><span class="sxs-lookup"><span data-stu-id="698dd-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="698dd-129">Để tạo một nội dung xuất mới, hãy chọn **Thêm đích**.</span><span class="sxs-lookup"><span data-stu-id="698dd-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="698dd-130">Trong trường **Kết nối để xuất**, hãy chọn một kết nối từ phần SFTP.</span><span class="sxs-lookup"><span data-stu-id="698dd-130">In the **Connection for export** field, choose a connection from the SFTP section.</span></span> <span data-ttu-id="698dd-131">Nếu bạn không thấy tên phần này, tức là không có kết nối nào thuộc loại này dành cho bạn.</span><span class="sxs-lookup"><span data-stu-id="698dd-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="698dd-132">Chọn nếu bạn muốn xuất dữ liệu **Đã nén** hoặc **Đã giải nén** của mình và **dấu tách trường** cho các tệp đã xuất.</span><span class="sxs-lookup"><span data-stu-id="698dd-132">Choose if you want to export your data **Gzipped** or **Unzipped** and the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="698dd-133">Chọn các thực thể, ví dụ như phân khúc, bạn muốn xuất.</span><span class="sxs-lookup"><span data-stu-id="698dd-133">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="698dd-134">Mỗi thực thể đã chọn sẽ được chia thành tối đa năm tệp đầu ra khi xuất.</span><span class="sxs-lookup"><span data-stu-id="698dd-134">Each selected entity will be split up into up to five output files when exported.</span></span> 

1. <span data-ttu-id="698dd-135">Chọn **Lưu**.</span><span class="sxs-lookup"><span data-stu-id="698dd-135">Select **Save**.</span></span>

<span data-ttu-id="698dd-136">Việc lưu một nội dung xuất sẽ không chạy nội dung xuất đó ngay lập tức.</span><span class="sxs-lookup"><span data-stu-id="698dd-136">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="698dd-137">Nội dung xuất chạy trong mỗi lần [làm mới theo lịch trình](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="698dd-137">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="698dd-138">Bạn cũng có thể [xuất dữ liệu theo yêu cầu](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="698dd-138">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a><span data-ttu-id="698dd-139">Nhập dữ liệu Customer Insights từ vị trí SFTP sang Salesforce Marketing Cloud</span><span class="sxs-lookup"><span data-stu-id="698dd-139">Import Customer Insights data from SFTP location to Salesforce Marketing Cloud</span></span>

1. <span data-ttu-id="698dd-140">Tạo [phần mở rộng dữ liệu trong Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) để nhập tệp dữ liệu Customer Insights từ vị trí SFTP.</span><span class="sxs-lookup"><span data-stu-id="698dd-140">Create [data extensions in Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) to import the Customer Insights data file from the SFTP location.</span></span>

2. <span data-ttu-id="698dd-141">[Nhập dữ liệu từ vị trí SFTP](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) vào phần mở rộng dữ liệu Salesforce Marketing Cloud.</span><span class="sxs-lookup"><span data-stu-id="698dd-141">[Import the data from the SFTP location](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) into the Salesforce Marketing Cloud data extension.</span></span> 

3. <span data-ttu-id="698dd-142">Thiết lập quy trình tự động hóa để nhập dữ liệu vào phần mở rộng dữ liệu.</span><span class="sxs-lookup"><span data-stu-id="698dd-142">Set up the automation to import the data into the data extensions.</span></span> <span data-ttu-id="698dd-143">Tìm hiểu thêm về [quy trình tự động thả tệp và tự động hóa theo lịch trình](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="698dd-143">Learn more about [file drop automations and scheduled automations](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).</span></span>

   <span data-ttu-id="698dd-144">Xác định một [quy trình tự động thả tệp](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) hoặc một [quy trình tự động hóa theo lịch trình](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="698dd-144">Define a [file drop automation](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) or a  [scheduled automation](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).</span></span> 

<span data-ttu-id="698dd-145">Sau đây là một ví dụ về [quy trình tự động hóa với SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="698dd-145">Here's an example of [an automation with SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="698dd-146">Quyền riêng tư về dữ liệu và sự tuân thủ</span><span class="sxs-lookup"><span data-stu-id="698dd-146">Data privacy and compliance</span></span>

<span data-ttu-id="698dd-147">Khi bật Dynamics 365 Customer Insights để truyền dữ liệu qua SFTP, bạn cho phép truyền dữ liệu ra ngoài phạm vi tuân thủ cho Dynamics 365 Customer Insights, bao gồm dữ liệu có khả năng là thông tin nhạy cảm, chẳng hạn như Dữ liệu cá nhân.</span><span class="sxs-lookup"><span data-stu-id="698dd-147">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="698dd-148">Microsoft sẽ truyền những dữ liệu đó theo chỉ dẫn của bạn, nhưng bạn có trách nhiệm đảm bảo rằng điểm đến xuất đáp ứng mọi nghĩa vụ về quyền riêng tư hoặc bảo mật mà bạn có thể có.</span><span class="sxs-lookup"><span data-stu-id="698dd-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="698dd-149">Để biết thêm thông tin, hãy xem [Tuyên bố về Quyền riêng tư của Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="698dd-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="698dd-150">Quản trị viên Dynamics 365 Customer Insights của bạn có thể xóa đích xuất này bất cứ lúc nào để ngừng việc sử dụng chức năng này.</span><span class="sxs-lookup"><span data-stu-id="698dd-150">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
