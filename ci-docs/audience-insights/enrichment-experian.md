---
title: Tăng cường thông tin bằng dịch vụ cung cấp dữ liệu của bên thứ ba Experian
description: Thông tin chung về dịch vụ cung cấp dữ liệu của bên thứ ba Experian.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 7c82fe92b3351a782a4fa6510300d870b742d042
ms.sourcegitcommit: 42b3bce1e20e7cc707d232844dacfeed3d6fc096
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 06/28/2021
ms.locfileid: "6309846"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="04ba9-103">Tăng cường thông tin hồ sơ khách hàng bằng dữ liệu nhân khẩu học từ Experian (bản xem trước)</span><span class="sxs-lookup"><span data-stu-id="04ba9-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="04ba9-104">Experian là công ty hàng đầu toàn cầu chuyên cung cấp dịch vụ tiếp thị và báo cáo tín dụng về người tiêu dùng cũng như doanh nghiệp.</span><span class="sxs-lookup"><span data-stu-id="04ba9-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="04ba9-105">Với dịch vụ cung cấp dữ liệu của Experian, bạn có thể tìm hiểu sâu hơn về khách hàng của mình bằng cách tăng cường thông tin hồ sơ khách hàng bằng dữ liệu nhân khẩu học, chẳng hạn như quy mô hộ gia đình, mức thu nhập, v.v.</span><span class="sxs-lookup"><span data-stu-id="04ba9-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="04ba9-106">Điều kiện tiên quyết</span><span class="sxs-lookup"><span data-stu-id="04ba9-106">Prerequisites</span></span>

<span data-ttu-id="04ba9-107">Để định cấu hình Experian, bạn phải đáp ứng các điều kiện tiên quyết sau:</span><span class="sxs-lookup"><span data-stu-id="04ba9-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="04ba9-108">Bạn phải có đăng ký Experian hiện hoạt.</span><span class="sxs-lookup"><span data-stu-id="04ba9-108">You have an active Experian subscription.</span></span> <span data-ttu-id="04ba9-109">Để có đăng ký, [hãy liên hệ trực tiếp với Experian](https://www.experian.com/marketing-services/contact).</span><span class="sxs-lookup"><span data-stu-id="04ba9-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="04ba9-110">[Tìm hiểu thêm về dịch vụ cung cấp dữ liệu của Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="04ba9-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>

- <span data-ttu-id="04ba9-111">Một kết nối Experian đã được quản trị viên định cấu hình *hoặc* bạn có quyền của [quản trị viên](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="04ba9-111">An Experian connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="04ba9-112">Bạn cũng cần có ID người dùng, ID bên và Số mô hình cho tài khoản Truyền tải an toàn (ST) hỗ trợ SSH mà Experian tạo cho bạn.</span><span class="sxs-lookup"><span data-stu-id="04ba9-112">You also need the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="04ba9-113">Quốc gia/khu vực được hỗ trợ</span><span class="sxs-lookup"><span data-stu-id="04ba9-113">Supported countries/regions</span></span>

<span data-ttu-id="04ba9-114">Chúng tôi hiện chỉ hỗ trợ tăng cường thông tin hồ sơ khách hàng tại Hoa Kỳ.</span><span class="sxs-lookup"><span data-stu-id="04ba9-114">We currently support enriching customer profiles in the United States only.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="04ba9-115">Định cấu hình dữ liệu tăng cường</span><span class="sxs-lookup"><span data-stu-id="04ba9-115">Configure the enrichment</span></span>

1. <span data-ttu-id="04ba9-116">Đi đến **Dữ liệu** > **Tăng cường** rồi chọn tab **Khám phá**.</span><span class="sxs-lookup"><span data-stu-id="04ba9-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="04ba9-117">Chọn **Tăng cường dữ liệu của tôi** trên ngăn xếp Experian.</span><span class="sxs-lookup"><span data-stu-id="04ba9-117">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="04ba9-118">![Ngăn xếp Experian](media/experian-tile.png "Ngăn xếp Experian")</span><span class="sxs-lookup"><span data-stu-id="04ba9-118">![Experian tile](media/experian-tile.png "Experian tile")</span></span>
   > 

1. <span data-ttu-id="04ba9-119">Chọn một [kết nối](connections.md) từ danh sách thả xuống.</span><span class="sxs-lookup"><span data-stu-id="04ba9-119">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="04ba9-120">Liên hệ với quản trị viên nếu không có kết nối.</span><span class="sxs-lookup"><span data-stu-id="04ba9-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="04ba9-121">Nếu là quản trị viên, bạn có thể tạo kết nối bằng cách chọn **Thêm kết nối** rồi chọn Experian từ danh sách thả xuống.</span><span class="sxs-lookup"><span data-stu-id="04ba9-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing Experian from the dropdown list.</span></span> 

1. <span data-ttu-id="04ba9-122">Chọn **Kết nối với Experian** để xác nhận kết nối được chọn.</span><span class="sxs-lookup"><span data-stu-id="04ba9-122">Select **Connect to Experian** to confirm the connection selection.</span></span>

1.  <span data-ttu-id="04ba9-123">Chọn **Tiếp** rồi chọn **Tập hợp dữ liệu khách hàng** bạn muốn tăng cường bằng dữ liệu nhân khẩu học từ Experian.</span><span class="sxs-lookup"><span data-stu-id="04ba9-123">Select **Next** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="04ba9-124">Bạn có thể chọn thực thể **Khách hàng** để tăng cường dữ liệu cho tất cả hồ sơ khách hàng của bạn hoặc chọn một thực thể phân khúc để chỉ tăng cường dữ liệu cho hồ sơ khách hàng có trong phân khúc đó.</span><span class="sxs-lookup"><span data-stu-id="04ba9-124">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Ảnh chụp màn hình khi chọn tập dữ liệu khách hàng.":::

1. <span data-ttu-id="04ba9-126">Chọn **Tiếp** và xác định loại trường nào từ hồ sơ hợp nhất của bạn sẽ được dùng để tìm kiếm dữ liệu nhân khẩu học phù hợp từ Experian.</span><span class="sxs-lookup"><span data-stu-id="04ba9-126">Select **Next** and define which type of fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="04ba9-127">Ít nhất một trong các trường **Tên và địa chỉ**, **Điện thoại** hoặc **Email** là bắt buộc.</span><span class="sxs-lookup"><span data-stu-id="04ba9-127">At least one of the fields **Name and address**, **Phone**, or **Email** is required.</span></span> <span data-ttu-id="04ba9-128">Để có độ chính xác đối sánh cao hơn, có thể thêm tối đa hai trường khác.</span><span class="sxs-lookup"><span data-stu-id="04ba9-128">For a higher match accuracy, up to two other fields can be added.</span></span> <span data-ttu-id="04ba9-129">Lựa chọn này sẽ ảnh hưởng đến các trường ánh xạ mà bạn có quyền truy cập trong bước tiếp theo.</span><span class="sxs-lookup"><span data-stu-id="04ba9-129">This selection will affect the mapping fields you have access to in the next step.</span></span>

    > [!TIP]
    > <span data-ttu-id="04ba9-130">Càng gửi nhiều thuộc tính định danh chính đến Experian, tỷ lệ đối sánh càng cao.</span><span class="sxs-lookup"><span data-stu-id="04ba9-130">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="04ba9-131">Chọn **Tiếp** để bắt đầu quá trình ánh xạ trường.</span><span class="sxs-lookup"><span data-stu-id="04ba9-131">Select **Next** to start the field mapping.</span></span>

1. <span data-ttu-id="04ba9-132">Xác định trường nào từ hồ sơ hợp nhất của bạn sẽ được dùng để tìm kiếm dữ liệu nhân khẩu học phù hợp từ Experian.</span><span class="sxs-lookup"><span data-stu-id="04ba9-132">Define which fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="04ba9-133">Các trường bắt buộc đều được đánh dấu.</span><span class="sxs-lookup"><span data-stu-id="04ba9-133">Required fields are marked.</span></span>

1. <span data-ttu-id="04ba9-134">Đặt tên cho dữ liệu tăng cường và tên cho thực thể đầu ra.</span><span class="sxs-lookup"><span data-stu-id="04ba9-134">Provide a name for the enrichment and a name for the output entity.</span></span>

1. <span data-ttu-id="04ba9-135">Chọn **Lưu dữ liệu tăng cường** sau khi xem xét các lựa chọn của bạn.</span><span class="sxs-lookup"><span data-stu-id="04ba9-135">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-experian"></a><span data-ttu-id="04ba9-136">Định cấu hình kết nối cho Experian</span><span class="sxs-lookup"><span data-stu-id="04ba9-136">Configure the connection for Experian</span></span> 

<span data-ttu-id="04ba9-137">Bạn cần phải là quản trị viên thì mới có thể định cấu hình kết nối.</span><span class="sxs-lookup"><span data-stu-id="04ba9-137">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="04ba9-138">Chọn **Thêm kết nối** khi định cấu hình tăng cường *hoặc* đi đến phần **Quản trị viên** > **Kết nối** rồi chọn **Thiết lập** trên ngăn xếp Experian.</span><span class="sxs-lookup"><span data-stu-id="04ba9-138">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Experian tile.</span></span>

1. <span data-ttu-id="04ba9-139">Chọn **Bắt đầu**.</span><span class="sxs-lookup"><span data-stu-id="04ba9-139">Select **Get Started**.</span></span>

1. <span data-ttu-id="04ba9-140">Nhập tên cho kết nối trong hộp **Tên hiển thị**.</span><span class="sxs-lookup"><span data-stu-id="04ba9-140">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="04ba9-141">Nhập ID người dùng, ID bên và Số mô hình hợp lệ cho tài khoản Truyền tải an toàn Experian.</span><span class="sxs-lookup"><span data-stu-id="04ba9-141">Enter valid User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span>

1. <span data-ttu-id="04ba9-142">Xem xét và chấp thuận **Quyền riêng tư dữ liệu và sự tuân thủ** bằng cách chọn **Tôi đồng ý**.</span><span class="sxs-lookup"><span data-stu-id="04ba9-142">Review and provide your consent for **Data privacy and compliance** by selecting **I agree**.</span></span>

1. <span data-ttu-id="04ba9-143">Chọn **Xác minh** để xác thực cấu hình.</span><span class="sxs-lookup"><span data-stu-id="04ba9-143">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="04ba9-144">Sau khi hoàn thành xác minh, hãy chọn **Lưu**.</span><span class="sxs-lookup"><span data-stu-id="04ba9-144">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Ngăn cấu hình kết nối Experian.":::

## <a name="enrichment-results"></a><span data-ttu-id="04ba9-146">Kết quả tăng cường</span><span class="sxs-lookup"><span data-stu-id="04ba9-146">Enrichment results</span></span>

<span data-ttu-id="04ba9-147">Để bắt đầu quá trình tăng cường, hãy chọn **Chạy** từ thanh lệnh.</span><span class="sxs-lookup"><span data-stu-id="04ba9-147">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="04ba9-148">Bạn cũng có thể để hệ thống chạy quá trình tăng cường tự động như một phần của [làm mới theo lịch trình](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="04ba9-148">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="04ba9-149">Thời gian xử lý sẽ phụ thuộc vào kích thước dữ liệu khách hàng và quy trình tăng cường do Experian thiết lập cho tài khoản của bạn.</span><span class="sxs-lookup"><span data-stu-id="04ba9-149">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="04ba9-150">Sau khi quá trình tăng cường hoàn tất, bạn có thể xem xét dữ liệu hồ sơ khách hàng mới được bổ sung trong **Dữ liệu tăng cường của tôi**.</span><span class="sxs-lookup"><span data-stu-id="04ba9-150">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="04ba9-151">Ngoài ra, bạn sẽ tìm thấy thời gian của lần cập nhật gần nhất và số lượng hồ sơ được tăng cường.</span><span class="sxs-lookup"><span data-stu-id="04ba9-151">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="04ba9-152">Bạn có thể truy cập dạng xem chi tiết của từng hồ sơ được tăng cường dữ liệu bằng cách chọn **Xem dữ liệu tăng cường**.</span><span class="sxs-lookup"><span data-stu-id="04ba9-152">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="04ba9-153">Các bước tiếp theo</span><span class="sxs-lookup"><span data-stu-id="04ba9-153">Next steps</span></span>

<span data-ttu-id="04ba9-154">Xây dựng dựa trên dữ liệu khách hàng tăng cường của bạn.</span><span class="sxs-lookup"><span data-stu-id="04ba9-154">Build on top of your enriched customer data.</span></span> <span data-ttu-id="04ba9-155">Tạo [phân khúc](segments.md) và [giá trị đo](measures.md), thậm chí [xuất dữ liệu](export-destinations.md) để cung cấp trải nghiệm được cá nhân hóa cho khách hàng của bạn.</span><span class="sxs-lookup"><span data-stu-id="04ba9-155">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="04ba9-156">Quyền riêng tư về dữ liệu và sự tuân thủ</span><span class="sxs-lookup"><span data-stu-id="04ba9-156">Data privacy and compliance</span></span>

<span data-ttu-id="04ba9-157">Khi bật Dynamics 365 Customer Insights để truyền dữ liệu tới Experian, bạn cho phép truyền dữ liệu ra ngoài phạm vi tuân thủ cho Dynamics 365 Customer Insights, bao gồm dữ liệu có khả năng là thông tin nhạy cảm, chẳng hạn như Dữ liệu cá nhân.</span><span class="sxs-lookup"><span data-stu-id="04ba9-157">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="04ba9-158">Microsoft sẽ truyền những dữ liệu đó theo chỉ dẫn của bạn, nhưng bạn có trách nhiệm đảm bảo rằng Experian đáp ứng mọi nghĩa vụ về quyền riêng tư hoặc bảo mật mà bạn có thể có.</span><span class="sxs-lookup"><span data-stu-id="04ba9-158">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="04ba9-159">Để biết thêm thông tin, hãy xem [Tuyên bố về Quyền riêng tư của Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="04ba9-159">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="04ba9-160">Quản trị viên Dynamics 365 Customer Insights của bạn có thể loại bỏ dịch vụ tăng cường này bất kỳ lúc nào để ngừng sử dụng tính năng đó.</span><span class="sxs-lookup"><span data-stu-id="04ba9-160">Your Dynamics 365 Customer Insights administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
