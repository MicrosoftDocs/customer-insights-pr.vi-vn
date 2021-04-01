---
title: Xuất dữ liệu Customer Insights sang Trình quản lý quảng cáo Facebook
description: Tìm hiểu cách định cấu hình kết nối tới Trình quản lý quảng cáo Facebook.
ms.date: 06/05/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3e2b52fe743563e4bf61d870cbf1718e6c752a67
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596709"
---
# <a name="connector-for-facebook-ads-manager-preview"></a><span data-ttu-id="ac8fd-103">Trình kết nối cho Trình quản lý quảng cáo Facebook (bản xem trước)</span><span class="sxs-lookup"><span data-stu-id="ac8fd-103">Connector for Facebook Ads Manager (preview)</span></span>

<span data-ttu-id="ac8fd-104">Xuất phân khúc hồ sơ khách hàng hợp nhất sang Trình quản lý quảng cáo Facebook để tạo chiến dịch trên Facebook và Instagram.</span><span class="sxs-lookup"><span data-stu-id="ac8fd-104">Export segments of unified customer profiles to Facebook Ads Manager to create campaigns on Facebook and Instagram.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ac8fd-105">Điều kiện tiên quyết</span><span class="sxs-lookup"><span data-stu-id="ac8fd-105">Prerequisites</span></span>

- <span data-ttu-id="ac8fd-106">Bạn cần có [**Tài khoản quảng cáo Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) bao gồm [**Tài khoản doanh nghiệp Facebook**](https://business.facebook.com/).</span><span class="sxs-lookup"><span data-stu-id="ac8fd-106">You need to have a [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) which includes a [**Facebook Business Account**](https://business.facebook.com/).</span></span>
- <span data-ttu-id="ac8fd-107">Bạn cần phải là một quản trị viên trên [**Tài khoản quảng cáo Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span><span class="sxs-lookup"><span data-stu-id="ac8fd-107">You need to be an administrator on the [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span></span>

## <a name="connect-to-facebook-ads-manager"></a><span data-ttu-id="ac8fd-108">Kết nối với Trình quản lý quảng cáo Facebook</span><span class="sxs-lookup"><span data-stu-id="ac8fd-108">Connect to Facebook Ads Manager</span></span>

1. <span data-ttu-id="ac8fd-109">Đi tới **Quản trị viên** > **Đích xuất**.</span><span class="sxs-lookup"><span data-stu-id="ac8fd-109">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="ac8fd-110">Trong **Trình quản lý quảng cáo Facebook**, chọn **Thiết lập**.</span><span class="sxs-lookup"><span data-stu-id="ac8fd-110">Under **Facebook Ads Manager**, select **Set up**.</span></span>

1. <span data-ttu-id="ac8fd-111">Trong trường **Tên hiển thị**, hãy đặt cho đích xuất một cái tên dễ nhận biết.</span><span class="sxs-lookup"><span data-stu-id="ac8fd-111">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="ac8fd-112">Chọn **Tiếp tục với Facebook** để đăng nhập vào Tài khoản quảng cáo Facebook.</span><span class="sxs-lookup"><span data-stu-id="ac8fd-112">Select **Continue with Facebook** to sign in to your Facebook Ad Account.</span></span>

1. <span data-ttu-id="ac8fd-113">Cho phép quyền **ads_management** sau khi xác thực với Facebook.</span><span class="sxs-lookup"><span data-stu-id="ac8fd-113">Allow the **ads_management** permission after authenticating with Facebook.</span></span>

1. <span data-ttu-id="ac8fd-114">Chọn **Tài khoản quảng cáo Facebook** mà bạn muốn làm việc.</span><span class="sxs-lookup"><span data-stu-id="ac8fd-114">Select the **Facebook Ads Account** that you want to work with.</span></span>

1. <span data-ttu-id="ac8fd-115">Chọn **Đối tượng tùy chỉnh hiện có** từ danh sách thả xuống hoặc tạo **Đối tượng tùy chỉnh mới**.</span><span class="sxs-lookup"><span data-stu-id="ac8fd-115">Select an **Existing custom audience** from the drop-down list or create a **New custom audience**.</span></span> <span data-ttu-id="ac8fd-116">Để biết thêm thông tin, hãy xem [**Đối tượng trong Trình quản lý quảng cáo Facebook**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span><span class="sxs-lookup"><span data-stu-id="ac8fd-116">For more information, see [**Audiences in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span></span>

1. <span data-ttu-id="ac8fd-117">Chọn **Tôi đồng ý** để xác nhận **Quyền riêng tư về dữ liệu và sự tuân thủ**.</span><span class="sxs-lookup"><span data-stu-id="ac8fd-117">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="ac8fd-118">Chọn **Tiếp** để định cấu hình xuất.</span><span class="sxs-lookup"><span data-stu-id="ac8fd-118">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="ac8fd-119">Đặt cấu hình trình kết nối</span><span class="sxs-lookup"><span data-stu-id="ac8fd-119">Configure the connector</span></span>

1. <span data-ttu-id="ac8fd-120">Trong **Chọn trường mã định danh chính của bạn**, chọn **Email**, **Tên và địa chỉ** hoặc **Điện thoại** để gửi đến Trình quản lý quảng cáo Facebook.</span><span class="sxs-lookup"><span data-stu-id="ac8fd-120">In the **Choose your key identifier field**, select **Email**, **Name and address**, or **Phone** to send to Facebook Ads Manager.</span></span>

1. <span data-ttu-id="ac8fd-121">Ánh xạ các thuộc tính tương ứng từ thực thể khách hàng hợp nhất của bạn cho khóa định danh đã chọn.</span><span class="sxs-lookup"><span data-stu-id="ac8fd-121">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>
   > <span data-ttu-id="ac8fd-122">[MẸO] Cơ hội tốt nhất để có kết quả khớp là khi bạn chọn **Email** làm mã định danh chính.</span><span class="sxs-lookup"><span data-stu-id="ac8fd-122">[TIP] The best chances for a match occur if you select **Email** as key identifier.</span></span> <span data-ttu-id="ac8fd-123">Thêm mã định danh bổ sung có thể cải thiện kết quả khớp.</span><span class="sxs-lookup"><span data-stu-id="ac8fd-123">Adding additional identifiers may improve the matching.</span></span>

1. <span data-ttu-id="ac8fd-124">Chọn **Thêm thuộc tính** để ánh xạ các thuộc tính bổ sung để gửi đến Trình quản lý quảng cáo Facebook.</span><span class="sxs-lookup"><span data-stu-id="ac8fd-124">Select **Add attribute** to map additional attributes to send to Facebook Ads Manager.</span></span> <span data-ttu-id="ac8fd-125">Các thuộc tính từ Trình quản lý quảng cáo Facebook đang ánh xạ tới các tên thân thiện với người dùng sau: **FN** = **Tên**, **LN** = **Họ**, **FI** = **Chữ cái đầu**, **PHONE** = **Điện thoại**, **GEN** = **Giới tính**, **DOB** = **Ngày sinh**, **ST** = **Tiểu bang**, **CT** = **Thành phố**, **ZIP** = **Mã bưu chính/Mã zip**, **COUNTRY** = **Quốc gia/Khu vực**</span><span class="sxs-lookup"><span data-stu-id="ac8fd-125">Attributes from Facebook Ads Manager are mapping to the following user friendly names: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / Zip code**, **COUNTRY** = **Country / Region**</span></span>

1. <span data-ttu-id="ac8fd-126">Chọn phân khúc mà bạn muốn xuất.</span><span class="sxs-lookup"><span data-stu-id="ac8fd-126">Select the segments you want to export.</span></span>

1. <span data-ttu-id="ac8fd-127">Chọn **Lưu**.</span><span class="sxs-lookup"><span data-stu-id="ac8fd-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="ac8fd-128">Xuất dữ liệu</span><span class="sxs-lookup"><span data-stu-id="ac8fd-128">Export the data</span></span>

<span data-ttu-id="ac8fd-129">Bạn có thể [xuất dữ liệu theo nhu cầu](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="ac8fd-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="ac8fd-130">Mỗi lần [làm mới theo lịch](system.md#schedule-tab), tác vụ xuất cũng sẽ chạy.</span><span class="sxs-lookup"><span data-stu-id="ac8fd-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="ac8fd-131">Các giới hạn đã biết</span><span class="sxs-lookup"><span data-stu-id="ac8fd-131">Known limitations</span></span>

- <span data-ttu-id="ac8fd-132">Lên đến 10 triệu hồ sơ khách hàng cho mỗi lần xuất sang Facebook Ads Manager</span><span class="sxs-lookup"><span data-stu-id="ac8fd-132">Up to 10 million customer profile per export to Facebook Ads Manager</span></span> 
- <span data-ttu-id="ac8fd-133">Xuất sang Facebook Ads Manager bị giới hạn ở các phân đoạn</span><span class="sxs-lookup"><span data-stu-id="ac8fd-133">Export to Facebook Ads Manager is limited to segments</span></span>
- <span data-ttu-id="ac8fd-134">Quá trình xuất phân đoạn với tổng số 10 triệu hồ sơ có thể mất đến 90 phút để hoàn tất</span><span class="sxs-lookup"><span data-stu-id="ac8fd-134">Exporting segments with a total of 10 million profiles can take up to 90 minutes to complete</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="ac8fd-135">Quyền riêng tư về dữ liệu và sự tuân thủ</span><span class="sxs-lookup"><span data-stu-id="ac8fd-135">Data privacy and compliance</span></span>

<span data-ttu-id="ac8fd-136">Khi bật Dynamics 365 Customer Insights để truyền dữ liệu tới Trình quản lý quảng cáo Facebook, bạn cho phép chuyển dữ liệu ra bên ngoài ranh giới tuân thủ cho Dynamics 365 Customer Insights, bao gồm dữ liệu nhạy cảm tiềm ẩn như Dữ liệu cá nhân.</span><span class="sxs-lookup"><span data-stu-id="ac8fd-136">When you enable Dynamics 365 Customer Insights to transmit data to Facebook Ads Manager, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="ac8fd-137">Microsoft sẽ chuyển những dữ liệu đó theo chỉ dẫn của bạn, nhưng bạn có trách nhiệm đảm bảo rằng Quảng cáo Facebook đáp ứng mọi nghĩa vụ về quyền riêng tư hoặc bảo mật mà bạn có thể có.</span><span class="sxs-lookup"><span data-stu-id="ac8fd-137">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Facebook Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="ac8fd-138">Để biết thêm thông tin, hãy xem [Tuyên bố về Quyền riêng tư của Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="ac8fd-138">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="ac8fd-139">Quản trị viên Dynamics 365 Customer Insights của bạn có thể xóa đích xuất này bất cứ lúc nào để ngừng sử dụng chức năng này.</span><span class="sxs-lookup"><span data-stu-id="ac8fd-139">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]