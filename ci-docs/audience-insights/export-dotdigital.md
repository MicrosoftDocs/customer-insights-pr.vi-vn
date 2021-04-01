---
title: Xuất dữ liệu Customer Insights sang DotDigital
description: Tìm hiểu cách định cấu hình kết nối với DotDigital.
ms.date: 11/14/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 51a28bdf0de34f0555d8ad7e3d13b2ef8911d417
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598043"
---
# <a name="connector-for-dotdigital-preview"></a><span data-ttu-id="ca791-103">Trình kết nối cho DotDigital (bản xem trước)</span><span class="sxs-lookup"><span data-stu-id="ca791-103">Connector for DotDigital (preview)</span></span>

<span data-ttu-id="ca791-104">Xuất các phân đoạn hồ sơ khách hàng hợp nhất sang sổ địa chỉ DotDigital và sử dụng chúng cho các chiến dịch, tiếp thị qua email và để xây dựng phân khúc khách hàng với DotDigital.</span><span class="sxs-lookup"><span data-stu-id="ca791-104">Export segments of unified customer profiles to DotDigital address books and use them for campaigns, email marketing, and to build customer segments with DotDigital.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="ca791-105">Điều kiện tiên quyết</span><span class="sxs-lookup"><span data-stu-id="ca791-105">Prerequisites</span></span>

-   <span data-ttu-id="ca791-106">Bạn có một [Tài khoản DotDigital](https://dotdigital.com/) và thông tin đăng nhập quản trị viên tương ứng.</span><span class="sxs-lookup"><span data-stu-id="ca791-106">You have a [DotDigital account](https://dotdigital.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="ca791-107">Có sổ địa chỉ hiện có trong DotDigital và các ID tương ứng.</span><span class="sxs-lookup"><span data-stu-id="ca791-107">There are existing address books in DotDigital and the corresponding IDs.</span></span> <span data-ttu-id="ca791-108">Có thể tìm thấy ID trong URL khi bạn chọn và mở sổ địa chỉ.</span><span class="sxs-lookup"><span data-stu-id="ca791-108">The ID can be found in the URL when you select and open an address book.</span></span> <span data-ttu-id="ca791-109">Để biết thêm thông tin, hãy xem [Sổ địa chỉ DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="ca791-109">For more information, see [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>
-   <span data-ttu-id="ca791-110">Bạn có [các phân đoạn được định cấu hình](segments.md) trong thông tin chi tiết về đối tượng.</span><span class="sxs-lookup"><span data-stu-id="ca791-110">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="ca791-111">Hồ sơ khách hàng hợp nhất trong các phân đoạn đã xuất chứa các trường đại diện cho địa chỉ email.</span><span class="sxs-lookup"><span data-stu-id="ca791-111">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-dotdigital"></a><span data-ttu-id="ca791-112">Kết nối với DotDigital</span><span class="sxs-lookup"><span data-stu-id="ca791-112">Connect to DotDigital</span></span>

1. <span data-ttu-id="ca791-113">Đi tới **Quản trị viên** > **Đích xuất**.</span><span class="sxs-lookup"><span data-stu-id="ca791-113">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="ca791-114">Trong **DotDigital**, chọn **Thiết lập**.</span><span class="sxs-lookup"><span data-stu-id="ca791-114">Under **DotDigital**, select **Set up**.</span></span>

1. <span data-ttu-id="ca791-115">Trong trường **Tên hiển thị**, hãy đặt cho đích xuất một cái tên dễ nhận biết.</span><span class="sxs-lookup"><span data-stu-id="ca791-115">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/DotDigital_config.PNG" alt-text="Ngăn cấu hình để xuất DotDigital.":::

1. <span data-ttu-id="ca791-117">Nhập **Tên người dùng và mật khẩu DotDigital**.</span><span class="sxs-lookup"><span data-stu-id="ca791-117">Enter your **DotDigital username and password**.</span></span>

1. <span data-ttu-id="ca791-118">Nhập **[ID sổ địa chỉ DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span><span class="sxs-lookup"><span data-stu-id="ca791-118">Enter your **[DotDigital address book ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span></span>

1. <span data-ttu-id="ca791-119">Chọn **Tôi đồng ý** để xác nhận **Quyền riêng tư về dữ liệu và sự tuân thủ**.</span><span class="sxs-lookup"><span data-stu-id="ca791-119">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="ca791-120">Chọn **Kết nối** để khởi tạo kết nối với DotDigital.</span><span class="sxs-lookup"><span data-stu-id="ca791-120">Select **Connect** to initialize the connection to DotDigital.</span></span>

1. <span data-ttu-id="ca791-121">Chọn **Thêm chính bạn là người dùng xuất** và cung cấp thông tin xác thực Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="ca791-121">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="ca791-122">Chọn **Tiếp** để định cấu hình xuất.</span><span class="sxs-lookup"><span data-stu-id="ca791-122">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="ca791-123">Đặt cấu hình trình kết nối</span><span class="sxs-lookup"><span data-stu-id="ca791-123">Configure the connector</span></span>

1. <span data-ttu-id="ca791-124">Trong phần **So khớp dữ liệu**, trong trường **Email**, chọn trường trong hồ sơ khách hàng hợp nhất trình bày địa chỉ email của khách hàng.</span><span class="sxs-lookup"><span data-stu-id="ca791-124">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="ca791-125">Lặp lại các bước tương tự cho các trường tùy chọn khác như **Tên**, **Họ**, **Họ và tên**, **Giới tính** và **Mã bưu điện**.</span><span class="sxs-lookup"><span data-stu-id="ca791-125">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Full name**, **Gender**, and **Post code**.</span></span>

1. <span data-ttu-id="ca791-126">Chọn phân khúc mà bạn muốn xuất.</span><span class="sxs-lookup"><span data-stu-id="ca791-126">Select the segments you want to export.</span></span> <span data-ttu-id="ca791-127">Bạn có thể xuất tổng cộng tối đa 1 triệu hồ sơ khách hàng sang DotDigital.</span><span class="sxs-lookup"><span data-stu-id="ca791-127">You can export up to 1 million customer profiles in total to DotDigital.</span></span>

1. <span data-ttu-id="ca791-128">Chọn **Lưu**.</span><span class="sxs-lookup"><span data-stu-id="ca791-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="ca791-129">Xuất dữ liệu</span><span class="sxs-lookup"><span data-stu-id="ca791-129">Export the data</span></span>

<span data-ttu-id="ca791-130">Bạn có thể [xuất dữ liệu theo nhu cầu](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="ca791-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="ca791-131">Mỗi lần [làm mới theo lịch](system.md#schedule-tab), tác vụ xuất cũng sẽ chạy.</span><span class="sxs-lookup"><span data-stu-id="ca791-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="ca791-132">Trong DotDigital, bây giờ bạn có thể tìm thấy các phân đoạn của mình trong [Sổ địa chỉ DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="ca791-132">In DotDigital, you can now find your segments in [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="ca791-133">Các giới hạn đã biết</span><span class="sxs-lookup"><span data-stu-id="ca791-133">Known limitations</span></span>

- <span data-ttu-id="ca791-134">Lên đến 1 triệu hồ sơ mỗi lần xuất sang DotDigital.</span><span class="sxs-lookup"><span data-stu-id="ca791-134">Up to 1 million profiles per export to DotDigital.</span></span>
- <span data-ttu-id="ca791-135">Việc xuất sang DotDigital bị giới hạn ở các phân đoạn.</span><span class="sxs-lookup"><span data-stu-id="ca791-135">Exporting to DotDigital is limited to segments.</span></span>
- <span data-ttu-id="ca791-136">Việc xuất các phân đoạn với tổng số 1 triệu hồ sơ có thể mất đến 3 giờ vì những hạn chế từ phía nhà cung cấp.</span><span class="sxs-lookup"><span data-stu-id="ca791-136">Exporting segments with a total of 1 million profiles can take up to 3 hours because of limitations on the provider side.</span></span> 
- <span data-ttu-id="ca791-137">Số lượng hồ sơ mà bạn có thể xuất sang DotDigital phụ thuộc và giới hạn vào hợp đồng của bạn với DotDigital.</span><span class="sxs-lookup"><span data-stu-id="ca791-137">The number of profiles that you can export to DotDigital is dependent and limited on your contract with DotDigital.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="ca791-138">Quyền riêng tư về dữ liệu và tuân thủ</span><span class="sxs-lookup"><span data-stu-id="ca791-138">Data privacy and compliance</span></span>

<span data-ttu-id="ca791-139">Khi bật Dynamics 365 Customer Insights để truyền dữ liệu tới DotDigital, bạn cho phép chuyển dữ liệu ra bên ngoài ranh giới tuân thủ cho Dynamics 365 Customer Insights, bao gồm dữ liệu nhạy cảm tiềm ẩn như Dữ liệu cá nhân.</span><span class="sxs-lookup"><span data-stu-id="ca791-139">When you enable Dynamics 365 Customer Insights to transmit data to DotDigital, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="ca791-140">Microsoft sẽ chuyển những dữ liệu đó theo chỉ dẫn của bạn, nhưng bạn có trách nhiệm đảm bảo rằng DotDigital đáp ứng mọi nghĩa vụ về quyền riêng tư hoặc bảo mật mà bạn có thể có.</span><span class="sxs-lookup"><span data-stu-id="ca791-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that DotDigital meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="ca791-141">Để biết thêm thông tin, hãy xem [Tuyên bố về Quyền riêng tư của Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="ca791-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="ca791-142">Quản trị viên Dynamics 365 Customer Insights của bạn có thể xóa đích xuất này bất cứ lúc nào để ngừng sử dụng chức năng này.</span><span class="sxs-lookup"><span data-stu-id="ca791-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]