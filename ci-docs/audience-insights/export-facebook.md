---
title: Xuất dữ liệu Customer Insights sang Trình quản lý quảng cáo Facebook
description: Tìm hiểu cách đặt cấu hình kết nối và xuất sang Facebook Ads Manager.
ms.date: 04/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ca32906a98bc734639fb369d6f5a92e8888fd850
ms.sourcegitcommit: 6d5dd572f75ba4c0303ec77c3b74e4318d52705c
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 04/16/2021
ms.locfileid: "5906836"
---
# <a name="export-segments-list-to-facebook-ads-manager-preview"></a><span data-ttu-id="e0970-103">Xuất danh sách phân khúc sang Facebook Ads Manager (bản xem trước)</span><span class="sxs-lookup"><span data-stu-id="e0970-103">Export segments list to Facebook Ads Manager (preview)</span></span>

<span data-ttu-id="e0970-104">Xuất phân khúc hồ sơ khách hàng hợp nhất sang Trình quản lý quảng cáo Facebook để tạo chiến dịch trên Facebook và Instagram.</span><span class="sxs-lookup"><span data-stu-id="e0970-104">Export segments of unified customer profiles to Facebook Ads Manager to create campaigns on Facebook and Instagram.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="e0970-105">Điều kiện tiên quyết để kết nối</span><span class="sxs-lookup"><span data-stu-id="e0970-105">Prerequisites for connection</span></span>

- <span data-ttu-id="e0970-106">Bạn cần có một [**Tài khoản quảng cáo Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) có chứa [**Tài khoản kinh doanh Facebook**](https://business.facebook.com/).</span><span class="sxs-lookup"><span data-stu-id="e0970-106">You need to have a [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) that includes a [**Facebook Business Account**](https://business.facebook.com/).</span></span>
- <span data-ttu-id="e0970-107">Bạn cần phải là một quản trị viên trên [**Tài khoản quảng cáo Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span><span class="sxs-lookup"><span data-stu-id="e0970-107">You need to be an administrator on the [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="e0970-108">Các giới hạn đã biết</span><span class="sxs-lookup"><span data-stu-id="e0970-108">Known limitations</span></span>

- <span data-ttu-id="e0970-109">Lên đến 10 triệu hồ sơ khách hàng cho mỗi lần xuất sang Facebook Ads Manager.</span><span class="sxs-lookup"><span data-stu-id="e0970-109">Up to 10 million customer profile per export to Facebook Ads Manager.</span></span>
- <span data-ttu-id="e0970-110">Chỉ có thể xuất các phân khúc sang Facebook.</span><span class="sxs-lookup"><span data-stu-id="e0970-110">Export to Facebook Ads Manager is limited to segments.</span></span>
- <span data-ttu-id="e0970-111">Chỉ tạo hoặc cập nhật đối tượng tùy chỉnh thuộc loại *danh sách khách hàng* trong Facebook.</span><span class="sxs-lookup"><span data-stu-id="e0970-111">Create or update custom audiences in Facebook of type *customer list* only.</span></span>
- <span data-ttu-id="e0970-112">Có thể mất đến 90 phút để hoàn tất quá trình xuất phân khúc với tổng số 10 triệu hồ sơ.</span><span class="sxs-lookup"><span data-stu-id="e0970-112">Exporting segments with a total of 10 million profiles can take up to 90 minutes to complete.</span></span>

## <a name="set-up-connection-to-facebook-ads-manager"></a><span data-ttu-id="e0970-113">Thiết lập kết nối với Facebook Ads Manager</span><span class="sxs-lookup"><span data-stu-id="e0970-113">Set up connection to Facebook Ads Manager</span></span>

<span data-ttu-id="e0970-114">Quản trị viên phải đặt cấu hình kết nối với dịch vụ và cho phép những người đóng góp sử dụng kết nối này thì người dùng mới có thể tạo nội dung xuất.</span><span class="sxs-lookup"><span data-stu-id="e0970-114">Before users can create an export, an administrator must configure the connection to the service and allow contributors to use the connection.</span></span>

1. <span data-ttu-id="e0970-115">Đi đến **Quản trị viên** > **Kết nối**.</span><span class="sxs-lookup"><span data-stu-id="e0970-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="e0970-116">Chọn **Thêm kết nối** rồi chọn **Facebook Ads Manager** để đặt cấu hình kết nối.</span><span class="sxs-lookup"><span data-stu-id="e0970-116">Select **Add connection** and choose **Facebook Ads Manager** to configure the connection.</span></span>

1. <span data-ttu-id="e0970-117">Đặt tên dễ nhận biết cho kết nối trong trường **Tên hiển thị**.</span><span class="sxs-lookup"><span data-stu-id="e0970-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="e0970-118">Tên và loại kết nối mô tả kết nối này.</span><span class="sxs-lookup"><span data-stu-id="e0970-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="e0970-119">Bạn nên chọn một tên giải thích mục đích và mục tiêu của kết nối.</span><span class="sxs-lookup"><span data-stu-id="e0970-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="e0970-120">Chọn người có thể sử dụng kết nối này.</span><span class="sxs-lookup"><span data-stu-id="e0970-120">Choose who can use this connection.</span></span> <span data-ttu-id="e0970-121">Nếu bạn không thực hiện hành động nào, giá trị mặc định sẽ là **Quản trị viên**.</span><span class="sxs-lookup"><span data-stu-id="e0970-121">If you take no action, the default will be **Administrators**.</span></span> <span data-ttu-id="e0970-122">Để biết thêm thông tin, hãy xem [Cho phép người đóng góp sử dụng một kết nối cho các lần xuất](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="e0970-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="e0970-123">Xác thực với Facebook Ads:</span><span class="sxs-lookup"><span data-stu-id="e0970-123">Authenticate with Facebook Ads:</span></span> 

   1. <span data-ttu-id="e0970-124">Chọn **Tiếp tục với Facebook** để đăng nhập vào Tài khoản quảng cáo Facebook.</span><span class="sxs-lookup"><span data-stu-id="e0970-124">Select **Continue with Facebook** to sign in to your Facebook Ad Account.</span></span>

   1. <span data-ttu-id="e0970-125">Cho phép quyền **ads_management** sau khi xác thực với Facebook.</span><span class="sxs-lookup"><span data-stu-id="e0970-125">Allow the **ads_management** permission after authenticating with Facebook.</span></span>

   1. <span data-ttu-id="e0970-126">Chọn **Tài khoản quảng cáo Facebook** mà bạn muốn làm việc.</span><span class="sxs-lookup"><span data-stu-id="e0970-126">Select the **Facebook Ads Account** that you want to work with.</span></span>

   1. <span data-ttu-id="e0970-127">Chọn **Đối tượng tùy chỉnh hiện có** từ danh sách thả xuống hoặc tạo **Đối tượng tùy chỉnh mới**.</span><span class="sxs-lookup"><span data-stu-id="e0970-127">Select an **Existing custom audience** from the drop-down list or create a **New custom audience**.</span></span> <span data-ttu-id="e0970-128">Để biết thêm thông tin, hãy xem [**Đối tượng trong Trình quản lý quảng cáo Facebook**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span><span class="sxs-lookup"><span data-stu-id="e0970-128">For more information, see [**Audiences in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span></span>
      > [!NOTE]
      > <span data-ttu-id="e0970-129">Bạn chỉ có thể tạo hoặc cập nhật đối tượng tùy chỉnh thuộc loại *danh sách khách hàng* trên Facebook qua lần xuất này.</span><span class="sxs-lookup"><span data-stu-id="e0970-129">You can only create or update custom audiences on Facebook of the type *customer list* with this export.</span></span> <span data-ttu-id="e0970-130">Trong một số trường hợp, bạn thấy các đối tượng tùy chỉnh thuộc loại khác nhau trong danh sách thả xuống.</span><span class="sxs-lookup"><span data-stu-id="e0970-130">In some cases, you see custom audiences of different types in the drop-down list.</span></span> <span data-ttu-id="e0970-131">Việc chọn một loại khác với *danh sách khách hàng* sẽ dẫn đến việc xuất không thành công.</span><span class="sxs-lookup"><span data-stu-id="e0970-131">Selecting a different type than *customer list* will result in a failing export.</span></span> 

1. <span data-ttu-id="e0970-132">Xem lại **Quyền riêng tư về dữ liệu và sự tuân thủ** rồi chọn **Tôi đồng ý**.</span><span class="sxs-lookup"><span data-stu-id="e0970-132">Review the **Data privacy and compliance** and select **I agree**.</span></span>

1. <span data-ttu-id="e0970-133">Chọn **Lưu** để hoàn thành kết nối.</span><span class="sxs-lookup"><span data-stu-id="e0970-133">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="e0970-134">Đặt cấu hình xuất</span><span class="sxs-lookup"><span data-stu-id="e0970-134">Configure an export</span></span>

<span data-ttu-id="e0970-135">Bạn có thể đặt cấu hình lần xuất này nếu bạn có quyền truy cập vào kết nối thuộc loại này.</span><span class="sxs-lookup"><span data-stu-id="e0970-135">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="e0970-136">Để biết thêm thông tin, hãy xem [Các quyền cần thiết để đặt cấu hình xuất](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="e0970-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="e0970-137">Đi tới **Dữ liệu** > **Nội dung xuất**.</span><span class="sxs-lookup"><span data-stu-id="e0970-137">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e0970-138">Để tạo một nội dung xuất mới, hãy chọn **Thêm đích**.</span><span class="sxs-lookup"><span data-stu-id="e0970-138">To create a new export, select **Add destination**.</span></span> 

1. <span data-ttu-id="e0970-139">Trong **Kết nối để xuất**, hãy chọn một kết nối từ phần **Facebook Ads Manager**.</span><span class="sxs-lookup"><span data-stu-id="e0970-139">In **Connection for export** choose a connection from the **Facebook Ads Manager** section.</span></span> <span data-ttu-id="e0970-140">Nếu bạn không thấy tên phần này, tức là không có kết nối nào thuộc loại này dành cho bạn.</span><span class="sxs-lookup"><span data-stu-id="e0970-140">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="e0970-141">Trong **Chọn trường mã định danh chính của bạn**, chọn **Email**, **Tên và địa chỉ** hoặc **Điện thoại** để gửi đến Trình quản lý quảng cáo Facebook.</span><span class="sxs-lookup"><span data-stu-id="e0970-141">In the **Choose your key identifier field**, select **Email**, **Name and address**, or **Phone** to send to Facebook Ads Manager.</span></span> 

1. <span data-ttu-id="e0970-142">Đặt tên dễ nhận biết cho kết nối trong trường **Tên hiển thị**.</span><span class="sxs-lookup"><span data-stu-id="e0970-142">Give your connection a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="e0970-143">Ánh xạ các thuộc tính tương ứng từ thực thể khách hàng hợp nhất của bạn cho khóa định danh đã chọn.</span><span class="sxs-lookup"><span data-stu-id="e0970-143">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>
   > <span data-ttu-id="e0970-144">[MẸO] Cơ hội tốt nhất để có kết quả khớp là khi bạn chọn **Email** làm mã định danh chính.</span><span class="sxs-lookup"><span data-stu-id="e0970-144">[TIP] The best chances for a match occur if you select **Email** as key identifier.</span></span> <span data-ttu-id="e0970-145">Thêm mã định danh bổ sung có thể cải thiện kết quả khớp.</span><span class="sxs-lookup"><span data-stu-id="e0970-145">Adding additional identifiers may improve the matching.</span></span>

1. <span data-ttu-id="e0970-146">Chọn **Thêm thuộc tính** để ánh xạ thêm các thuộc tính cho mục đích gửi đến Facebook Ads Manager.</span><span class="sxs-lookup"><span data-stu-id="e0970-146">Select **Add attribute** to map more attributes to send to Facebook Ads Manager.</span></span> <span data-ttu-id="e0970-147">Các thuộc tính từ Facebook Ads Manager đang ánh xạ tới các tên thân thiện với người dùng sau đây: **FN** = **Tên**, **LN** = **Họ**, **FI** = **Chữ cái đầu tiên của tên**, **PHONE** = **Số điện thoại**, **GEN** = **Giới tính**, **DOB** = **Ngày sinh**, **ST** = **Tiểu bang**, **CT** = **Thành phố**, **ZIP** = **Mã bưu chính/Mã zip**, **COUNTRY** = **Quốc gia/Khu vực**</span><span class="sxs-lookup"><span data-stu-id="e0970-147">Attributes from Facebook Ads Manager are mapping to the following user-friendly names: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / Zip code**, **COUNTRY** = **Country / Region**</span></span>

1. <span data-ttu-id="e0970-148">Chọn phân khúc mà bạn muốn xuất.</span><span class="sxs-lookup"><span data-stu-id="e0970-148">Select the segments you want to export.</span></span>

1. <span data-ttu-id="e0970-149">Chọn **Lưu**.</span><span class="sxs-lookup"><span data-stu-id="e0970-149">Select **Save**.</span></span>

<span data-ttu-id="e0970-150">Việc lưu một nội dung xuất sẽ không chạy nội dung xuất đó ngay lập tức.</span><span class="sxs-lookup"><span data-stu-id="e0970-150">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="e0970-151">Nội dung xuất chạy trong mỗi lần [làm mới theo lịch trình](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="e0970-151">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="e0970-152">Bạn cũng có thể [xuất dữ liệu theo yêu cầu](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="e0970-152">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="e0970-153">Quyền riêng tư về dữ liệu và sự tuân thủ</span><span class="sxs-lookup"><span data-stu-id="e0970-153">Data privacy and compliance</span></span>

<span data-ttu-id="e0970-154">Khi bật Dynamics 365 Customer Insights để truyền dữ liệu tới Trình quản lý quảng cáo Facebook, bạn cho phép chuyển dữ liệu ra bên ngoài ranh giới tuân thủ cho Dynamics 365 Customer Insights, bao gồm dữ liệu nhạy cảm tiềm ẩn như Dữ liệu cá nhân.</span><span class="sxs-lookup"><span data-stu-id="e0970-154">When you enable Dynamics 365 Customer Insights to transmit data to Facebook Ads Manager, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="e0970-155">Microsoft sẽ chuyển những dữ liệu đó theo chỉ dẫn của bạn, nhưng bạn có trách nhiệm đảm bảo rằng Quảng cáo Facebook đáp ứng mọi nghĩa vụ về quyền riêng tư hoặc bảo mật mà bạn có thể có.</span><span class="sxs-lookup"><span data-stu-id="e0970-155">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Facebook Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="e0970-156">Để biết thêm thông tin, hãy xem [Tuyên bố về Quyền riêng tư của Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="e0970-156">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="e0970-157">Quản trị viên Dynamics 365 Customer Insights của bạn có thể xóa đích xuất này bất cứ lúc nào để ngừng sử dụng chức năng này.</span><span class="sxs-lookup"><span data-stu-id="e0970-157">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
