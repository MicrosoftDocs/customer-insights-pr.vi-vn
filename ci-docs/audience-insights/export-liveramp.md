---
title: Trình kết nối LiveRamp
description: Tìm hiểu cách xuất dữ liệu sang LiveRamp.
ms.date: 12/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 86aa8c66a47ee61741082c95f05d2e5ce3f06f35
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667210"
---
# <a name="liverampreg-connector-preview"></a><span data-ttu-id="5fe36-103">Trình kết nối LiveRamp&reg; (xem trước)</span><span class="sxs-lookup"><span data-stu-id="5fe36-103">LiveRamp&reg; connector (preview)</span></span>

<span data-ttu-id="5fe36-104">Kích hoạt dữ liệu của bạn trong LiveRamp để kết nối với hơn 500 nền tảng trên hệ sinh thái kỹ thuật số, mạng xã hội và TV.</span><span class="sxs-lookup"><span data-stu-id="5fe36-104">Activate your data in LiveRamp to connect with over 500 platforms across digital, social, and TV ecosystems.</span></span> <span data-ttu-id="5fe36-105">Làm việc với dữ liệu của bạn trong LiveRamp nhắm mục tiêu, chặn và cá nhân hóa chiến dịch quảng cáo.</span><span class="sxs-lookup"><span data-stu-id="5fe36-105">Work with your data in LiveRamp to target, suppress, and personalize ad campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5fe36-106">Điều kiện tiên quyết</span><span class="sxs-lookup"><span data-stu-id="5fe36-106">Prerequisites</span></span>

- <span data-ttu-id="5fe36-107">Bạn phải có gói đăng ký LiveRamp thì mới dùng được trình kết nối này.</span><span class="sxs-lookup"><span data-stu-id="5fe36-107">You need a LiveRamp subscription to use this connector.</span></span>
- <span data-ttu-id="5fe36-108">Để đăng ký, hãy trực tiếp [liên hệ với LiveRamp](https://liveramp.com/contact/).</span><span class="sxs-lookup"><span data-stu-id="5fe36-108">To get a subscription, [contact LiveRamp](https://liveramp.com/contact/) directly.</span></span> <span data-ttu-id="5fe36-109">[Tìm hiểu thêm về LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span><span class="sxs-lookup"><span data-stu-id="5fe36-109">[Learn more about LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span></span>

## <a name="connect-to-liveramp"></a><span data-ttu-id="5fe36-110">Kết nối với LiveRamp</span><span class="sxs-lookup"><span data-stu-id="5fe36-110">Connect to LiveRamp</span></span>

1. <span data-ttu-id="5fe36-111">Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Quản trị viên** > **Nơi xuất đích**.</span><span class="sxs-lookup"><span data-stu-id="5fe36-111">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="5fe36-112">Trong ngăn xếp **LiveRamp**, chọn **Thiết lập**.</span><span class="sxs-lookup"><span data-stu-id="5fe36-112">In the **LiveRamp** tile, select **Set up**.</span></span>

1. <span data-ttu-id="5fe36-113">Trong trường **Tên hiển thị**, hãy đặt tên cho vị trí để dễ nhận diện.</span><span class="sxs-lookup"><span data-stu-id="5fe36-113">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="5fe36-114">Điền **Tên người dùng** và **Mật khẩu** cho tài khoản LiveRamp Secure FTP (SFTP) của bạn.</span><span class="sxs-lookup"><span data-stu-id="5fe36-114">Provide a **Username** and **Password** for your LiveRamp Secure FTP (SFTP) account.</span></span>
<span data-ttu-id="5fe36-115">Thông tin đăng nhập này có thể khác với thông tin đăng nhập LiveRamp Onboarding.</span><span class="sxs-lookup"><span data-stu-id="5fe36-115">These credentials may be different from your LiveRamp Onboarding credentials.</span></span>

1. <span data-ttu-id="5fe36-116">Chọn **Xác minh** để kiểm tra kết nối với LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="5fe36-116">Select **Verify** to test the connection to LiveRamp.</span></span>

1. <span data-ttu-id="5fe36-117">Sau khi xác minh xong, hãy đồng ý với **Quyền riêng tư và tuân thủ dữ liệu** bằng cách đánh dấu vào ô **Tôi đồng ý**.</span><span class="sxs-lookup"><span data-stu-id="5fe36-117">After successful verification, provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="5fe36-118">Chọn **Tiếp** để thiết lập trình kết nối LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="5fe36-118">Select **Next** to set up the LiveRamp connector.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="5fe36-119">Đặt cấu hình trình kết nối</span><span class="sxs-lookup"><span data-stu-id="5fe36-119">Configure the connector</span></span>

1. <span data-ttu-id="5fe36-120">Trong trường **Chọn khóa định danh**, chọn **Email**,  **Tên và địa chỉ** hoặc **Điện thoại** để gửi phương án định danh cho LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="5fe36-120">In the **Choose your key identifier** field, select **Email**,  **Name and address**, or **Phone** to send to LiveRamp for identity resolution.</span></span>

1. <span data-ttu-id="5fe36-121">Ánh xạ các thuộc tính tương ứng từ thực thể khách hàng hợp nhất của bạn cho khóa định danh đã chọn.</span><span class="sxs-lookup"><span data-stu-id="5fe36-121">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>

1. <span data-ttu-id="5fe36-122">Chọn **Thêm thuộc tính** để ánh xạ thêm các thuộc tính cần gửi đến LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="5fe36-122">Select **Add attribute** to map additional attributes to send to LiveRamp.</span></span>

   > [!TIP]
   > <span data-ttu-id="5fe36-123">Khi gửi thêm thuộc tính khóa định danh đến LiveRamp, bạn sẽ có tỷ lệ khớp cao hơn.</span><span class="sxs-lookup"><span data-stu-id="5fe36-123">Sending more key identifier attributes to LiveRamp is likely to get you a higher match rate.</span></span>

1. <span data-ttu-id="5fe36-124">Chọn các phân đoạn bạn muốn xuất sang LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="5fe36-124">Select the segments you want to export to LiveRamp.</span></span>

1. <span data-ttu-id="5fe36-125">Chọn **Lưu**.</span><span class="sxs-lookup"><span data-stu-id="5fe36-125">Select **Save**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="5fe36-126">![Trình kết nối LiveRamp khi ánh xạ thuộc tính](media/export-liveramp-segments.png "Trình kết nối LiveRamp khi ánh xạ thuộc tính")</span><span class="sxs-lookup"><span data-stu-id="5fe36-126">![LiveRamp connector with attribute mapping](media/export-liveramp-segments.png "LiveRamp connector with attribute mapping")</span></span>

## <a name="export-the-data"></a><span data-ttu-id="5fe36-127">Xuất dữ liệu</span><span class="sxs-lookup"><span data-stu-id="5fe36-127">Export the data</span></span>

<span data-ttu-id="5fe36-128">Tác vụ xuất sẽ bắt đầu ngay khi mọi điều kiện tiên quyết đã được đáp ứng.</span><span class="sxs-lookup"><span data-stu-id="5fe36-128">The export will start shortly if all prerequisites for export have been completed.</span></span> <span data-ttu-id="5fe36-129">Mỗi lần [làm mới theo lịch](system.md#schedule-tab), tác vụ xuất cũng sẽ chạy.</span><span class="sxs-lookup"><span data-stu-id="5fe36-129">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
<span data-ttu-id="5fe36-130">Khi quá trình xuất hoàn thành, bạn có thể đăng nhập vào LiveRamp Onboarding để kích hoạt và phân phối dữ liệu.</span><span class="sxs-lookup"><span data-stu-id="5fe36-130">Once the export is successfully completed, you can sign in to LiveRamp Onboarding to activate and distribute your data.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="5fe36-131">Quyền riêng tư về dữ liệu và tuân thủ</span><span class="sxs-lookup"><span data-stu-id="5fe36-131">Data privacy and compliance</span></span>

<span data-ttu-id="5fe36-132">Khi bật Dynamics 365 Customer Insights để truyền dữ liệu tới Liveramp, bạn cho phép chuyển dữ liệu ra bên ngoài ranh giới tuân thủ cho Dynamics 365 Customer Insights, bao gồm dữ liệu nhạy cảm tiềm ẩn như Dữ liệu cá nhân.</span><span class="sxs-lookup"><span data-stu-id="5fe36-132">When you enable Dynamics 365 Customer Insights to transmit data to Liveramp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="5fe36-133">Microsoft sẽ chuyển những dữ liệu đó theo chỉ dẫn của bạn, nhưng bạn có trách nhiệm đảm bảo rằng Liveramp đáp ứng mọi nghĩa vụ về quyền riêng tư hoặc bảo mật mà bạn có thể có.</span><span class="sxs-lookup"><span data-stu-id="5fe36-133">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Liveramp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="5fe36-134">Để biết thêm thông tin, hãy xem [Tuyên bố về Quyền riêng tư của Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="5fe36-134">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="5fe36-135">Quản trị viên Dynamics 365 Customer Insights của bạn có thể xóa đích xuất này bất cứ lúc nào để ngừng sử dụng chức năng này.</span><span class="sxs-lookup"><span data-stu-id="5fe36-135">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>