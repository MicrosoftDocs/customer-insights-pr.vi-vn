---
title: Xuất dữ liệu Customer Insights sang Marketo
description: Tìm hiểu cách định cấu hình kết nối với Marketo.
ms.date: 11/12/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 74d19a0448123904210c26f7b8760d00296c9cfd
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597997"
---
# <a name="connector-for-marketo-preview"></a><span data-ttu-id="fb71b-103">Trình kết nối cho Marketo (bản xem trước)</span><span class="sxs-lookup"><span data-stu-id="fb71b-103">Connector for Marketo (preview)</span></span>

<span data-ttu-id="fb71b-104">Xuất các phân đoạn hồ sơ khách hàng hợp nhất để tạo chiến dịch, cung cấp email tiếp thị và tận dụng các nhóm khách hàng cụ thể với Marketo.</span><span class="sxs-lookup"><span data-stu-id="fb71b-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="fb71b-105">Điều kiện tiên quyết</span><span class="sxs-lookup"><span data-stu-id="fb71b-105">Prerequisites</span></span>

-   <span data-ttu-id="fb71b-106">Bạn có một [Tài khoản Marketo](https://login.marketo.com/) và thông tin đăng nhập quản trị viên tương ứng.</span><span class="sxs-lookup"><span data-stu-id="fb71b-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="fb71b-107">Có danh sách hiện có trong Marketo và các ID tương ứng.</span><span class="sxs-lookup"><span data-stu-id="fb71b-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="fb71b-108">Để biết thêm thông tin, hãy xem phần [Danh sách Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="fb71b-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="fb71b-109">Bạn có [các phân đoạn được định cấu hình](segments.md).</span><span class="sxs-lookup"><span data-stu-id="fb71b-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="fb71b-110">Hồ sơ khách hàng hợp nhất trong các phân đoạn đã xuất chứa các trường đại diện cho địa chỉ email.</span><span class="sxs-lookup"><span data-stu-id="fb71b-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-marketo"></a><span data-ttu-id="fb71b-111">Kết nối với Marketo</span><span class="sxs-lookup"><span data-stu-id="fb71b-111">Connect to Marketo</span></span>

1. <span data-ttu-id="fb71b-112">Đi tới **Quản trị viên** > **Đích xuất**.</span><span class="sxs-lookup"><span data-stu-id="fb71b-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="fb71b-113">Trong **Marketo**, chọn **Thiết lập**.</span><span class="sxs-lookup"><span data-stu-id="fb71b-113">Under **Marketo**, select **Set up**.</span></span>

1. <span data-ttu-id="fb71b-114">Trong trường **Tên hiển thị**, hãy đặt cho đích xuất một cái tên dễ nhận biết.</span><span class="sxs-lookup"><span data-stu-id="fb71b-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="fb71b-115">Nhập **[ID máy khách Marketo, Mã bí mật máy khách và Tên máy chủ điểm cuối REST](https://developers.marketo.com/rest-api/authentication/)**.</span><span class="sxs-lookup"><span data-stu-id="fb71b-115">Enter your **[Marketo client ID, Client secret and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span>

1. <span data-ttu-id="fb71b-116">Nhập **[ID danh sách Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span><span class="sxs-lookup"><span data-stu-id="fb71b-116">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span></span> 

1. <span data-ttu-id="fb71b-117">Chọn **Tôi đồng ý** để xác nhận **Quyền riêng tư về dữ liệu và sự tuân thủ** và chọn **Kết nối** để khởi tạo kết nối với Marketo.</span><span class="sxs-lookup"><span data-stu-id="fb71b-117">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="fb71b-118">Chọn **Thêm chính bạn là người dùng xuất** và cung cấp thông tin xác thực Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="fb71b-118">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-connect-marketo.png" alt-text="Xuất ảnh chụp màn hình cho kết nối Marketo":::

1. <span data-ttu-id="fb71b-120">Chọn **Tiếp** để định cấu hình xuất.</span><span class="sxs-lookup"><span data-stu-id="fb71b-120">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="fb71b-121">Đặt cấu hình trình kết nối</span><span class="sxs-lookup"><span data-stu-id="fb71b-121">Configure the connector</span></span>

1. <span data-ttu-id="fb71b-122">Trong phần **So khớp dữ liệu**, trong trường **Email**, chọn trường trong hồ sơ khách hàng hợp nhất trình bày địa chỉ email của khách hàng.</span><span class="sxs-lookup"><span data-stu-id="fb71b-122">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="fb71b-123">Theo tùy chọn, bạn có thể xuất **Tên**, **Họ**, **Thành phố**, **Tiểu bang** và **Quốc gia/Khu vực** dưới dạng các trường bổ sung để tạo email cá nhân hóa hơn.</span><span class="sxs-lookup"><span data-stu-id="fb71b-123">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  as additional fields to create more personalized emails.</span></span> <span data-ttu-id="fb71b-124">Chọn **Thêm thuộc tính** để ánh xạ những trường này.</span><span class="sxs-lookup"><span data-stu-id="fb71b-124">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="fb71b-125">Chọn phân khúc mà bạn muốn xuất.</span><span class="sxs-lookup"><span data-stu-id="fb71b-125">Select the segments you want to export.</span></span> <span data-ttu-id="fb71b-126">Bạn có thể xuất tổng cộng tối đa 1 triệu hồ sơ khách hàng sang Marketo.</span><span class="sxs-lookup"><span data-stu-id="fb71b-126">You can export up to 1 million customer profiles in total to Marketo.</span></span>

   :::image type="content" source="media/export-segment-marketo.png" alt-text="Chọn các trường và phân đoạn để xuất sang Marketo":::

1. <span data-ttu-id="fb71b-128">Chọn **Lưu**.</span><span class="sxs-lookup"><span data-stu-id="fb71b-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="fb71b-129">Xuất dữ liệu</span><span class="sxs-lookup"><span data-stu-id="fb71b-129">Export the data</span></span>

<span data-ttu-id="fb71b-130">Bạn có thể [xuất dữ liệu theo nhu cầu](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="fb71b-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="fb71b-131">Mỗi lần [làm mới theo lịch](system.md#schedule-tab), tác vụ xuất cũng sẽ chạy.</span><span class="sxs-lookup"><span data-stu-id="fb71b-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="fb71b-132">Trong Marketo, bạn hiện có thể tìm thấy các phân đoạn của mình trong [Danh sách Marketo](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="fb71b-132">In Marketo, you can now find your segments under [Marketo lists](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="fb71b-133">Các giới hạn đã biết</span><span class="sxs-lookup"><span data-stu-id="fb71b-133">Known limitations</span></span>

- <span data-ttu-id="fb71b-134">Lên đến 1 triệu hồ sơ mỗi lần xuất sang Marketo.</span><span class="sxs-lookup"><span data-stu-id="fb71b-134">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="fb71b-135">Việc xuất sang Marketo bị giới hạn ở các phân đoạn.</span><span class="sxs-lookup"><span data-stu-id="fb71b-135">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="fb71b-136">Quá trình xuất phân đoạn với tổng số 1 triệu hồ sơ có thể mất đến 3 giờ.</span><span class="sxs-lookup"><span data-stu-id="fb71b-136">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="fb71b-137">Số lượng hồ sơ mà bạn có thể xuất sang Marketo phụ thuộc và giới hạn vào hợp đồng của bạn với Marketo.</span><span class="sxs-lookup"><span data-stu-id="fb71b-137">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="fb71b-138">Quyền riêng tư về dữ liệu và tuân thủ</span><span class="sxs-lookup"><span data-stu-id="fb71b-138">Data privacy and compliance</span></span>

<span data-ttu-id="fb71b-139">Khi bật Dynamics 365 Customer Insights để truyền dữ liệu tới Marketo, bạn cho phép chuyển dữ liệu ra bên ngoài ranh giới tuân thủ cho Dynamics 365 Customer Insights, bao gồm dữ liệu nhạy cảm tiềm ẩn như Dữ liệu cá nhân.</span><span class="sxs-lookup"><span data-stu-id="fb71b-139">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="fb71b-140">Microsoft sẽ chuyển những dữ liệu đó theo chỉ dẫn của bạn, nhưng bạn có trách nhiệm đảm bảo rằng Marketo đáp ứng mọi nghĩa vụ về quyền riêng tư hoặc bảo mật mà bạn có thể có.</span><span class="sxs-lookup"><span data-stu-id="fb71b-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="fb71b-141">Để biết thêm thông tin, hãy xem [Tuyên bố về Quyền riêng tư của Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="fb71b-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="fb71b-142">Quản trị viên Dynamics 365 Customer Insights của bạn có thể xóa đích xuất này bất cứ lúc nào để ngừng sử dụng chức năng này.</span><span class="sxs-lookup"><span data-stu-id="fb71b-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]