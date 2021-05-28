---
title: Xuất dữ liệu Customer Insights sang DotDigital
description: Tìm hiểu cách đặt cấu hình kết nối và xuất sang DotDigital.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d08504856e1c673ef32433b83bf491d7f4e8cee4
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976872"
---
# <a name="export-segment-lists-to-dotdigital-preview"></a><span data-ttu-id="88a4a-103">Xuất danh sách phân khúc sang DotDigital (bản xem trước)</span><span class="sxs-lookup"><span data-stu-id="88a4a-103">Export segment lists to DotDigital (preview)</span></span>

<span data-ttu-id="88a4a-104">Xuất các phân đoạn hồ sơ khách hàng hợp nhất sang sổ địa chỉ DotDigital và sử dụng chúng cho các chiến dịch, tiếp thị qua email và để xây dựng phân khúc khách hàng với DotDigital.</span><span class="sxs-lookup"><span data-stu-id="88a4a-104">Export segments of unified customer profiles to DotDigital address books and use them for campaigns, email marketing, and to build customer segments with DotDigital.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="88a4a-105">Điều kiện tiên quyết để kết nối</span><span class="sxs-lookup"><span data-stu-id="88a4a-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="88a4a-106">Bạn có một [Tài khoản DotDigital](https://dotdigital.com/) và thông tin đăng nhập quản trị viên tương ứng.</span><span class="sxs-lookup"><span data-stu-id="88a4a-106">You have a [DotDigital account](https://dotdigital.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="88a4a-107">Có sổ địa chỉ hiện có trong DotDigital và các ID tương ứng.</span><span class="sxs-lookup"><span data-stu-id="88a4a-107">There are existing address books in DotDigital and the corresponding IDs.</span></span> <span data-ttu-id="88a4a-108">Có thể tìm thấy ID trong URL khi bạn chọn và mở sổ địa chỉ.</span><span class="sxs-lookup"><span data-stu-id="88a4a-108">The ID can be found in the URL when you select and open an address book.</span></span> <span data-ttu-id="88a4a-109">Để biết thêm thông tin, hãy xem [Sổ địa chỉ DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="88a4a-109">For more information, see [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>
-   <span data-ttu-id="88a4a-110">Bạn có [các phân đoạn được định cấu hình](segments.md) trong thông tin chi tiết về đối tượng.</span><span class="sxs-lookup"><span data-stu-id="88a4a-110">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="88a4a-111">Hồ sơ khách hàng hợp nhất trong các phân đoạn đã xuất chứa các trường đại diện cho địa chỉ email.</span><span class="sxs-lookup"><span data-stu-id="88a4a-111">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="88a4a-112">Các giới hạn đã biết</span><span class="sxs-lookup"><span data-stu-id="88a4a-112">Known limitations</span></span>

- <span data-ttu-id="88a4a-113">Lên đến 1 triệu hồ sơ mỗi lần xuất sang DotDigital.</span><span class="sxs-lookup"><span data-stu-id="88a4a-113">Up to 1 million profiles per export to DotDigital.</span></span>
- <span data-ttu-id="88a4a-114">Việc xuất sang DotDigital bị giới hạn ở các phân đoạn.</span><span class="sxs-lookup"><span data-stu-id="88a4a-114">Exporting to DotDigital is limited to segments.</span></span>
- <span data-ttu-id="88a4a-115">Việc xuất các phân đoạn với tổng số 1 triệu hồ sơ có thể mất đến 3 giờ vì những hạn chế từ phía nhà cung cấp.</span><span class="sxs-lookup"><span data-stu-id="88a4a-115">Exporting segments with a total of 1 million profiles can take up to 3 hours because of limitations on the provider side.</span></span> 
- <span data-ttu-id="88a4a-116">Số lượng hồ sơ mà bạn có thể xuất sang DotDigital phụ thuộc và giới hạn vào hợp đồng của bạn với DotDigital.</span><span class="sxs-lookup"><span data-stu-id="88a4a-116">The number of profiles that you can export to DotDigital is dependent and limited on your contract with DotDigital.</span></span>

## <a name="set-up-connection-to-dotdigital"></a><span data-ttu-id="88a4a-117">Thiết lập kết nối với DotDigital</span><span class="sxs-lookup"><span data-stu-id="88a4a-117">Set up connection to DotDigital</span></span>

1. <span data-ttu-id="88a4a-118">Đi đến **Quản trị viên** > **Kết nối**.</span><span class="sxs-lookup"><span data-stu-id="88a4a-118">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="88a4a-119">Chọn **Thêm kết nối** rồi chọn **DotDigital** để đặt cấu hình kết nối.</span><span class="sxs-lookup"><span data-stu-id="88a4a-119">Select **Add connection** and choose **DotDigital** to configure the connection.</span></span>

1. <span data-ttu-id="88a4a-120">Đặt tên dễ nhận biết cho kết nối trong trường **Tên hiển thị**.</span><span class="sxs-lookup"><span data-stu-id="88a4a-120">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="88a4a-121">Tên và loại kết nối mô tả kết nối này.</span><span class="sxs-lookup"><span data-stu-id="88a4a-121">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="88a4a-122">Bạn nên chọn một tên giải thích mục đích và mục tiêu của kết nối.</span><span class="sxs-lookup"><span data-stu-id="88a4a-122">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="88a4a-123">Chọn người có thể sử dụng kết nối này.</span><span class="sxs-lookup"><span data-stu-id="88a4a-123">Choose who can use this connection.</span></span> <span data-ttu-id="88a4a-124">Nếu bạn không thực hiện hành động nào, giá trị mặc định sẽ là Quản trị viên.</span><span class="sxs-lookup"><span data-stu-id="88a4a-124">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="88a4a-125">Để biết thêm thông tin, hãy xem [Cho phép người đóng góp sử dụng một kết nối cho các lần xuất](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="88a4a-125">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="88a4a-126">Nhập **Tên người dùng và mật khẩu DotDigital**.</span><span class="sxs-lookup"><span data-stu-id="88a4a-126">Enter your **DotDigital username and password**.</span></span>

1. <span data-ttu-id="88a4a-127">Nhập **[ID sổ địa chỉ DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span><span class="sxs-lookup"><span data-stu-id="88a4a-127">Enter your **[DotDigital address book ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span></span>

1. <span data-ttu-id="88a4a-128">Chọn **Tôi đồng ý** để xác nhận **Quyền riêng tư về dữ liệu và sự tuân thủ**.</span><span class="sxs-lookup"><span data-stu-id="88a4a-128">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="88a4a-129">Chọn **Kết nối** để khởi tạo kết nối với DotDigital.</span><span class="sxs-lookup"><span data-stu-id="88a4a-129">Select **Connect** to initialize the connection to DotDigital.</span></span>

1. <span data-ttu-id="88a4a-130">Chọn **Thêm chính bạn là người dùng xuất** và cung cấp thông tin xác thực Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="88a4a-130">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="88a4a-131">Chọn **Lưu** để hoàn thành kết nối.</span><span class="sxs-lookup"><span data-stu-id="88a4a-131">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="88a4a-132">Đặt cấu hình xuất</span><span class="sxs-lookup"><span data-stu-id="88a4a-132">Configure an export</span></span>

<span data-ttu-id="88a4a-133">Bạn có thể đặt cấu hình lần xuất này nếu bạn có quyền truy cập vào kết nối thuộc loại này.</span><span class="sxs-lookup"><span data-stu-id="88a4a-133">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="88a4a-134">Để biết thêm thông tin, hãy xem [Các quyền cần thiết để đặt cấu hình xuất](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="88a4a-134">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="88a4a-135">Đi tới **Dữ liệu** > **Nội dung xuất**.</span><span class="sxs-lookup"><span data-stu-id="88a4a-135">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="88a4a-136">Để tạo một nội dung xuất mới, hãy chọn **Thêm đích**.</span><span class="sxs-lookup"><span data-stu-id="88a4a-136">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="88a4a-137">Trong trường **Kết nối để xuất**, hãy chọn một kết nối từ phần DotDigital.</span><span class="sxs-lookup"><span data-stu-id="88a4a-137">In the **Connection for export** field, choose a connection from the DotDigital section.</span></span> <span data-ttu-id="88a4a-138">Nếu bạn không thấy tên phần này, tức là không có kết nối nào thuộc loại này dành cho bạn.</span><span class="sxs-lookup"><span data-stu-id="88a4a-138">If you don't see this section name, there are no connections of this type available to you.</span></span>


1. <span data-ttu-id="88a4a-139">Trong phần **So khớp dữ liệu**, trong trường **Email**, chọn trường trong hồ sơ khách hàng hợp nhất trình bày địa chỉ email của khách hàng.</span><span class="sxs-lookup"><span data-stu-id="88a4a-139">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="88a4a-140">Lặp lại các bước tương tự cho các trường tùy chọn khác như **Tên**, **Họ**, **Họ và tên**, **Giới tính** và **Mã bưu điện**.</span><span class="sxs-lookup"><span data-stu-id="88a4a-140">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Full name**, **Gender**, and **Post code**.</span></span>

1. <span data-ttu-id="88a4a-141">Chọn phân khúc mà bạn muốn xuất.</span><span class="sxs-lookup"><span data-stu-id="88a4a-141">Select the segments you want to export.</span></span> <span data-ttu-id="88a4a-142">Bạn có thể xuất tổng cộng tối đa 1 triệu hồ sơ khách hàng sang DotDigital.</span><span class="sxs-lookup"><span data-stu-id="88a4a-142">You can export up to 1 million customer profiles in total to DotDigital.</span></span>

1. <span data-ttu-id="88a4a-143">Chọn **Lưu**.</span><span class="sxs-lookup"><span data-stu-id="88a4a-143">Select **Save**.</span></span>

<span data-ttu-id="88a4a-144">Việc lưu một nội dung xuất sẽ không chạy nội dung xuất đó ngay lập tức.</span><span class="sxs-lookup"><span data-stu-id="88a4a-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="88a4a-145">Nội dung xuất chạy trong mỗi lần [làm mới theo lịch trình](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="88a4a-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="88a4a-146">Bạn cũng có thể [xuất dữ liệu theo yêu cầu](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="88a4a-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 
 
<span data-ttu-id="88a4a-147">Trong DotDigital, bây giờ bạn có thể tìm thấy các phân đoạn của mình trong [Sổ địa chỉ DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="88a4a-147">In DotDigital, you can now find your segments in [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="88a4a-148">Quyền riêng tư về dữ liệu và sự tuân thủ</span><span class="sxs-lookup"><span data-stu-id="88a4a-148">Data privacy and compliance</span></span>

<span data-ttu-id="88a4a-149">Khi bật Dynamics 365 Customer Insights để truyền dữ liệu tới DotDigital, bạn cho phép chuyển dữ liệu ra bên ngoài ranh giới tuân thủ cho Dynamics 365 Customer Insights, bao gồm dữ liệu nhạy cảm tiềm ẩn như Dữ liệu cá nhân.</span><span class="sxs-lookup"><span data-stu-id="88a4a-149">When you enable Dynamics 365 Customer Insights to transmit data to DotDigital, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="88a4a-150">Microsoft sẽ chuyển những dữ liệu đó theo chỉ dẫn của bạn, nhưng bạn có trách nhiệm đảm bảo rằng DotDigital đáp ứng mọi nghĩa vụ về quyền riêng tư hoặc bảo mật mà bạn có thể có.</span><span class="sxs-lookup"><span data-stu-id="88a4a-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that DotDigital meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="88a4a-151">Để biết thêm thông tin, hãy xem [Tuyên bố về Quyền riêng tư của Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="88a4a-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="88a4a-152">Quản trị viên Dynamics 365 Customer Insights của bạn có thể xóa đích xuất này bất cứ lúc nào để ngừng sử dụng chức năng này.</span><span class="sxs-lookup"><span data-stu-id="88a4a-152">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
