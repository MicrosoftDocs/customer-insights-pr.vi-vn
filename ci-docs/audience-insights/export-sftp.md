---
title: Xuất dữ liệu Customer Insights sang máy chủ SFTP
description: Tìm hiểu cách định cấu hình kết nối tới máy chủ SFTP.
ms.date: 01/27/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 9ec14fafa8f99e34b95349371298082e166535d0
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598411"
---
# <a name="connector-for-sftp-preview"></a><span data-ttu-id="0ceeb-103">Trình kết nối cho SFTP (bản xem trước)</span><span class="sxs-lookup"><span data-stu-id="0ceeb-103">Connector for SFTP (preview)</span></span>

<span data-ttu-id="0ceeb-104">Sử dụng dữ liệu khách hàng của bạn trong các ứng dụng bên thứ ba bằng cách xuất sang máy chủ Giao thức truyền tệp bảo mật (SFTP).</span><span class="sxs-lookup"><span data-stu-id="0ceeb-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol (SFTP) host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0ceeb-105">Điều kiện tiên quyết</span><span class="sxs-lookup"><span data-stu-id="0ceeb-105">Prerequisites</span></span>

- <span data-ttu-id="0ceeb-106">Tính khả dụng của máy chủ SFTP và thông tin đăng nhập tương ứng.</span><span class="sxs-lookup"><span data-stu-id="0ceeb-106">Availability of an SFTP host and corresponding credentials.</span></span>

## <a name="connect-to-sftp"></a><span data-ttu-id="0ceeb-107">Kết nối với SFTP</span><span class="sxs-lookup"><span data-stu-id="0ceeb-107">Connect to SFTP</span></span>

1. <span data-ttu-id="0ceeb-108">Đi tới **Quản trị viên** > **Đích xuất**.</span><span class="sxs-lookup"><span data-stu-id="0ceeb-108">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="0ceeb-109">Trong phần **SFTP**, chọn **Thiết lập**.</span><span class="sxs-lookup"><span data-stu-id="0ceeb-109">Under **SFTP**, select **Set up**.</span></span>

1. <span data-ttu-id="0ceeb-110">Trong trường **Tên hiển thị**, hãy đặt tên cho vị trí để dễ nhận diện.</span><span class="sxs-lookup"><span data-stu-id="0ceeb-110">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="0ceeb-111">Cung cấp **Tên người dùng**, **Mật khẩu**, **Tên máy chủ** và **Thư mục xuất** cho tài khoản SFTP của bạn.</span><span class="sxs-lookup"><span data-stu-id="0ceeb-111">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="0ceeb-112">Chọn **Xác minh** để kiểm tra kết nối.</span><span class="sxs-lookup"><span data-stu-id="0ceeb-112">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="0ceeb-113">Sau khi xác minh thành công, hãy chọn xem bạn muốn xuất dữ liệu **Gzipped** hay **Đã giải nén** và chọn **dấu phân cách trường** cho các tệp đã xuất.</span><span class="sxs-lookup"><span data-stu-id="0ceeb-113">After successful verification, choose if you want to export your data **Gzipped** or **Unzipped**, and select the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="0ceeb-114">Chọn **Tôi đồng ý** để xác nhận **Quyền riêng tư về dữ liệu và sự tuân thủ**.</span><span class="sxs-lookup"><span data-stu-id="0ceeb-114">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="0ceeb-115">Chọn **Tiếp** để bắt đầu định cấu hình xuất.</span><span class="sxs-lookup"><span data-stu-id="0ceeb-115">Select **Next** to start configuring the export.</span></span>

## <a name="configure-the-export"></a><span data-ttu-id="0ceeb-116">Xuất cấu hình</span><span class="sxs-lookup"><span data-stu-id="0ceeb-116">Configure the export</span></span>

1. <span data-ttu-id="0ceeb-117">Chọn các thực thể, ví dụ như phân đoạn, bạn muốn xuất.</span><span class="sxs-lookup"><span data-stu-id="0ceeb-117">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="0ceeb-118">Mỗi thực thể được chọn sẽ có tối đa năm tệp đầu ra khi xuất.</span><span class="sxs-lookup"><span data-stu-id="0ceeb-118">Each selected entity will be up to five output files when exported.</span></span> 

1. <span data-ttu-id="0ceeb-119">Chọn **Lưu**.</span><span class="sxs-lookup"><span data-stu-id="0ceeb-119">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="0ceeb-120">Xuất dữ liệu</span><span class="sxs-lookup"><span data-stu-id="0ceeb-120">Export the data</span></span>

<span data-ttu-id="0ceeb-121">Bạn có thể [xuất dữ liệu theo nhu cầu](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="0ceeb-121">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="0ceeb-122">Mỗi lần [làm mới theo lịch](system.md#schedule-tab), tác vụ xuất cũng sẽ chạy.</span><span class="sxs-lookup"><span data-stu-id="0ceeb-122">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="0ceeb-123">Các giới hạn đã biết</span><span class="sxs-lookup"><span data-stu-id="0ceeb-123">Known limitations</span></span>

- <span data-ttu-id="0ceeb-124">Thời gian chạy của một lần xuất phụ thuộc vào hiệu suất hệ thống của bạn.</span><span class="sxs-lookup"><span data-stu-id="0ceeb-124">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="0ceeb-125">Chúng tôi khuyên bạn nên sử dụng máy chủ có tối thiểu hai lõi CPU và bộ nhớ 1 Gb.</span><span class="sxs-lookup"><span data-stu-id="0ceeb-125">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="0ceeb-126">Việc xuất các thực thể với tối đa 100 triệu hồ sơ khách hàng có thể mất 90 phút khi sử dụng cấu hình tối thiểu được khuyến nghị gồm CPU 2 lõi và 1 Gb bộ nhớ.</span><span class="sxs-lookup"><span data-stu-id="0ceeb-126">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration of two CPU cores and 1 Gb of memory.</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="0ceeb-127">Quyền riêng tư về dữ liệu và sự tuân thủ</span><span class="sxs-lookup"><span data-stu-id="0ceeb-127">Data privacy and compliance</span></span>

<span data-ttu-id="0ceeb-128">Khi bật Dynamics 365 Customer Insights để truyền dữ liệu qua SFTP, bạn cho phép chuyển dữ liệu ra bên ngoài ranh giới tuân thủ cho Dynamics 365 Customer Insights, bao gồm dữ liệu nhạy cảm tiềm ẩn như Dữ liệu cá nhân.</span><span class="sxs-lookup"><span data-stu-id="0ceeb-128">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="0ceeb-129">Microsoft sẽ chuyển những dữ liệu đó theo chỉ dẫn của bạn, nhưng bạn có trách nhiệm đảm bảo rằng điểm đến xuất đáp ứng mọi nghĩa vụ về quyền riêng tư hoặc bảo mật mà bạn có thể có.</span><span class="sxs-lookup"><span data-stu-id="0ceeb-129">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="0ceeb-130">Để biết thêm thông tin, hãy xem [Tuyên bố về Quyền riêng tư của Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="0ceeb-130">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="0ceeb-131">Quản trị viên Dynamics 365 Customer Insights của bạn có thể xóa đích xuất này bất cứ lúc nào để ngừng sử dụng chức năng này.</span><span class="sxs-lookup"><span data-stu-id="0ceeb-131">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]