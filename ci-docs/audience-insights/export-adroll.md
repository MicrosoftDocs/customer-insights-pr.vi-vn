---
title: Xuất dữ liệu Customer Insights sang AdRoll
description: Tìm hiểu cách định cấu hình kết nối với AdRoll.
ms.date: 02/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6fedd549c2e7de362f36e3fb23d363200bb92a04
ms.sourcegitcommit: d24e52150fe5a4fab45128e12d6a03637771d9b9
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 03/19/2021
ms.locfileid: "5697100"
---
# <a name="connector-for-adroll-preview"></a><span data-ttu-id="79ecc-103">Trình kết nối cho AdRoll (xem trước)</span><span class="sxs-lookup"><span data-stu-id="79ecc-103">Connector for AdRoll (preview)</span></span>

<span data-ttu-id="79ecc-104">Xuất phân khúc hồ sơ khách hàng hợp nhất sang AdRoll và sử dụng các phân khúc đó để quảng cáo.</span><span class="sxs-lookup"><span data-stu-id="79ecc-104">Export segments of unified customer profiles to AdRoll and use them for advertising.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="79ecc-105">Điều kiện tiên quyết</span><span class="sxs-lookup"><span data-stu-id="79ecc-105">Prerequisites</span></span>

-   <span data-ttu-id="79ecc-106">Bạn có một [tài khoản AdRoll](https://www.adroll.com/) và thông tin đăng nhập tương ứng của quản trị viên.</span><span class="sxs-lookup"><span data-stu-id="79ecc-106">You have an [AdRoll account](https://www.adroll.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="79ecc-107">Bạn có [các phân đoạn được định cấu hình](segments.md) trong thông tin chi tiết về đối tượng.</span><span class="sxs-lookup"><span data-stu-id="79ecc-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="79ecc-108">Hồ sơ khách hàng hợp nhất trong các phân đoạn đã xuất chứa các trường đại diện cho địa chỉ email.</span><span class="sxs-lookup"><span data-stu-id="79ecc-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-adroll"></a><span data-ttu-id="79ecc-109">Kết nối với AdRoll</span><span class="sxs-lookup"><span data-stu-id="79ecc-109">Connect to AdRoll</span></span>

1. <span data-ttu-id="79ecc-110">Đi tới **Quản trị viên** > **Đích xuất**.</span><span class="sxs-lookup"><span data-stu-id="79ecc-110">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="79ecc-111">Trong **AdRoll**, chọn **Thiết lập**.</span><span class="sxs-lookup"><span data-stu-id="79ecc-111">Under **AdRoll**, select **Set up**.</span></span>

1. <span data-ttu-id="79ecc-112">Trong trường **Tên hiển thị**, hãy đặt cho đích xuất một cái tên dễ nhận biết.</span><span class="sxs-lookup"><span data-stu-id="79ecc-112">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/AdRoll_config.PNG" alt-text="Ngăn cấu hình cho kết nối AdRoll.":::

1. <span data-ttu-id="79ecc-114">Chọn **Tôi đồng ý** để xác nhận **Quyền riêng tư về dữ liệu và sự tuân thủ**.</span><span class="sxs-lookup"><span data-stu-id="79ecc-114">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="79ecc-115">Chọn **Kết nối** để khởi tạo kết nối với AdRoll.</span><span class="sxs-lookup"><span data-stu-id="79ecc-115">Select **Connect** to initialize the connection to AdRoll.</span></span>

1. <span data-ttu-id="79ecc-116">Chọn **Xác thực bằng AdRoll** và cung cấp thông tin đăng nhập quản trị viên cho AdRoll.</span><span class="sxs-lookup"><span data-stu-id="79ecc-116">Select **Authenticate with AdRoll** and provide your admin credentials for AdRoll.</span></span> 

1. <span data-ttu-id="79ecc-117">Chọn **Thêm chính bạn là người dùng xuất** và cung cấp thông tin xác thực Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="79ecc-117">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="79ecc-118">Nhập **ID nhà quảng cáo AdRoll** [AdRoll có thể quảng cáo](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="79ecc-118">Enter your **AdRoll Advertiser ID** [AdRoll Advertisable](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).</span></span>

1. <span data-ttu-id="79ecc-119">Chọn **Tiếp** để định cấu hình xuất.</span><span class="sxs-lookup"><span data-stu-id="79ecc-119">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="79ecc-120">Đặt cấu hình trình kết nối</span><span class="sxs-lookup"><span data-stu-id="79ecc-120">Configure the connector</span></span>

1. <span data-ttu-id="79ecc-121">Trong phần **So khớp dữ liệu**, trong trường **Email**, chọn trường trong hồ sơ khách hàng hợp nhất trình bày địa chỉ email của khách hàng.</span><span class="sxs-lookup"><span data-stu-id="79ecc-121">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="79ecc-122">Bắt buộc phải xuất các phân khúc sang AdRoll.</span><span class="sxs-lookup"><span data-stu-id="79ecc-122">It's required to export segments to AdRoll.</span></span>

1. <span data-ttu-id="79ecc-123">Chọn phân khúc mà bạn muốn xuất.</span><span class="sxs-lookup"><span data-stu-id="79ecc-123">Select the segments you want to export.</span></span> <span data-ttu-id="79ecc-124">Chọn một phân khúc có ít nhất 100 thành viên.</span><span class="sxs-lookup"><span data-stu-id="79ecc-124">Select a segment with a least 100 members.</span></span> <span data-ttu-id="79ecc-125">Bạn không thể xuất các phân khúc nhỏ hơn.</span><span class="sxs-lookup"><span data-stu-id="79ecc-125">You can't export smaller segments.</span></span> <span data-ttu-id="79ecc-126">Ngoài ra, kích thước tối đa của một phân khúc để xuất là 250.000 thành viên cho mỗi lần xuất.</span><span class="sxs-lookup"><span data-stu-id="79ecc-126">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="79ecc-127">Chọn **Lưu**.</span><span class="sxs-lookup"><span data-stu-id="79ecc-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="79ecc-128">Xuất dữ liệu</span><span class="sxs-lookup"><span data-stu-id="79ecc-128">Export the data</span></span>

<span data-ttu-id="79ecc-129">Bạn có thể [xuất dữ liệu theo nhu cầu](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="79ecc-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="79ecc-130">Mỗi lần [làm mới theo lịch](system.md#schedule-tab), tác vụ xuất cũng sẽ chạy.</span><span class="sxs-lookup"><span data-stu-id="79ecc-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="79ecc-131">Các giới hạn đã biết</span><span class="sxs-lookup"><span data-stu-id="79ecc-131">Known limitations</span></span>

- <span data-ttu-id="79ecc-132">Bạn có thể xuất tối đa 250.000 hồ sơ cho mỗi lần xuất sang AdRoll.</span><span class="sxs-lookup"><span data-stu-id="79ecc-132">You can export up to 250'000 profiles in per export to AdRoll.</span></span>
- <span data-ttu-id="79ecc-133">Bạn không thể xuất các phân khúc có ít hơn 100 hồ sơ sang AdRoll.</span><span class="sxs-lookup"><span data-stu-id="79ecc-133">You can't export segments with fewer than 100 profiles to AdRoll.</span></span> 
- <span data-ttu-id="79ecc-134">Việc xuất sang AdRoll bị giới hạn ở các phân khúc.</span><span class="sxs-lookup"><span data-stu-id="79ecc-134">Exporting to AdRoll is limited to segments.</span></span>
- <span data-ttu-id="79ecc-135">Có thể mất tới 10 phút để hoàn tất việc xuất tối đa 250.000 hồ sơ sang AdRoll.</span><span class="sxs-lookup"><span data-stu-id="79ecc-135">Exporting up to 250'000 profiles to AdRoll can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="79ecc-136">Số lượng hồ sơ mà bạn có thể xuất sang AdRoll phụ thuộc và giới hạn vào hợp đồng của bạn với AdRoll.</span><span class="sxs-lookup"><span data-stu-id="79ecc-136">The number of profiles that you can export to AdRoll is dependent and limited on your contract with AdRoll.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="79ecc-137">Quyền riêng tư về dữ liệu và sự tuân thủ</span><span class="sxs-lookup"><span data-stu-id="79ecc-137">Data privacy and compliance</span></span>

<span data-ttu-id="79ecc-138">Khi bật Dynamics 365 Customer Insights để truyền dữ liệu sang AdRoll, bạn cho phép truyền dữ liệu ra ngoài ranh giới tuân thủ của Dynamics 365 Customer Insights, bao gồm cả dữ liệu nhạy cảm như Dữ liệu cá nhân.</span><span class="sxs-lookup"><span data-stu-id="79ecc-138">When you enable Dynamics 365 Customer Insights to transmit data to AdRoll, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="79ecc-139">Microsoft sẽ chuyển những dữ liệu đó theo chỉ dẫn của bạn, nhưng bạn có trách nhiệm đảm bảo rằng AdRoll đáp ứng mọi nghĩa vụ về quyền riêng tư hoặc bảo mật mà bạn có thể có.</span><span class="sxs-lookup"><span data-stu-id="79ecc-139">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that AdRoll meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="79ecc-140">Để biết thêm thông tin, hãy xem [Tuyên bố về Quyền riêng tư của Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="79ecc-140">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="79ecc-141">Quản trị viên Dynamics 365 Customer Insights của bạn có thể xóa đích xuất này bất cứ lúc nào để ngừng sử dụng chức năng này.</span><span class="sxs-lookup"><span data-stu-id="79ecc-141">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
