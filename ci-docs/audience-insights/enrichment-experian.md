---
title: Tăng cường với Experian tăng cường của bên thứ ba
description: Thông tin chung về tăng cường của bên thứ ba Experian.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 9cf2a7fa18ecc022ea67f6829f52381ad59f3172
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896399"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="8d114-103">Làm phong phú hồ sơ khách hàng với dữ liệu nhân khẩu học từ Experian (bản xem trước)</span><span class="sxs-lookup"><span data-stu-id="8d114-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="8d114-104">Experian là công ty tiên phong toàn cầu về các dịch vụ tiếp thị và báo cáo tín dụng cho người tiêu dùng và doanh nghiệp.</span><span class="sxs-lookup"><span data-stu-id="8d114-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="8d114-105">Với dịch vụ làm phong phú dữ liệu của Experian, bạn có thể có được sự hiểu biết sâu sắc hơn về khách hàng của mình qua việc làm phong phú hồ sơ khách hàng của bạn bằng dữ liệu nhân khẩu học, như: quy mô hộ gia đình, thu nhập, v.v.</span><span class="sxs-lookup"><span data-stu-id="8d114-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8d114-106">Điều kiện tiên quyết</span><span class="sxs-lookup"><span data-stu-id="8d114-106">Prerequisites</span></span>

<span data-ttu-id="8d114-107">Để đặt cấu hình Experian, các điều kiện tiên quyết sau phải được đáp ứng:</span><span class="sxs-lookup"><span data-stu-id="8d114-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="8d114-108">Bạn có gói đăng ký Experian đang hoạt động.</span><span class="sxs-lookup"><span data-stu-id="8d114-108">You have an active Experian subscription.</span></span> <span data-ttu-id="8d114-109">Để đăng ký, hãy [liên hệ trực tiếp với Experian](https://www.experian.com/marketing-services/contact).</span><span class="sxs-lookup"><span data-stu-id="8d114-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="8d114-110">[Tìm hiểu thêm về Tăng cường dữ liệu bằng Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="8d114-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>

- <span data-ttu-id="8d114-111">Một kết nối Experian đã được quản trị viên đặt cấu hình *hoặc* bạn có quyền của [quản trị viên](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="8d114-111">An Experian connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="8d114-112">Bạn cũng cần ID người dùng, ID bên và Số mô hình cho tài khoản Truyền tải an toàn (ST) có hỗ trợ SSH mà Experian đã tạo cho bạn.</span><span class="sxs-lookup"><span data-stu-id="8d114-112">You also need the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="8d114-113">Đặt cấu hình nội dung bổ sung</span><span class="sxs-lookup"><span data-stu-id="8d114-113">Configure the enrichment</span></span>

1. <span data-ttu-id="8d114-114">Đi đến **Dữ liệu** > **Tăng cường** và chọn tab **Khám phá**.</span><span class="sxs-lookup"><span data-stu-id="8d114-114">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="8d114-115">Chọn **Tăng cường dữ liệu của tôi** trên ngăn xếp Experian.</span><span class="sxs-lookup"><span data-stu-id="8d114-115">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8d114-116">![Ngăn xếp Experian](media/experian-tile.png "Ngăn xếp Experian")</span><span class="sxs-lookup"><span data-stu-id="8d114-116">![Experian tile](media/experian-tile.png "Experian tile")</span></span>
   > 

1. <span data-ttu-id="8d114-117">Chọn một [kết nối](connections.md) từ danh sách thả xuống.</span><span class="sxs-lookup"><span data-stu-id="8d114-117">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="8d114-118">Liên hệ với quản trị viên nếu không có kết nối.</span><span class="sxs-lookup"><span data-stu-id="8d114-118">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="8d114-119">Nếu là quản trị viên, bạn có thể tạo kết nối bằng cách chọn **Thêm kết nối** rồi chọn Experian từ menu thả xuống.</span><span class="sxs-lookup"><span data-stu-id="8d114-119">If you are an administrator, you can create a connection by selecting **Add connection** and choosing Experian from the drop-down.</span></span> 

1. <span data-ttu-id="8d114-120">Chọn **Kết nối với Experian** để xác nhận lựa chọn kết nối.</span><span class="sxs-lookup"><span data-stu-id="8d114-120">Select **Connect to Experian** to confirm the connection selection.</span></span>

1.  <span data-ttu-id="8d114-121">Chọn **Tiếp** rồi chọn **Tập hợp dữ liệu khách hàng** mà bạn muốn bổ sung thêm dữ liệu nhân khẩu học từ Experian.</span><span class="sxs-lookup"><span data-stu-id="8d114-121">Select **Next** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="8d114-122">Bạn có thể chọn thực thể **khách hàng** để làm phong phú tất cả hồ sơ khách hàng của bạn hoặc chọn một thực thể phân khúc để chỉ làm phong phú thêm hồ sơ khách hàng có trong phân khúc đó.</span><span class="sxs-lookup"><span data-stu-id="8d114-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Ảnh chụp màn hình khi chọn tập dữ liệu khách hàng.":::

1. <span data-ttu-id="8d114-124">Chọn **Tiếp** và xác định loại trường nào từ hồ sơ hợp nhất của bạn sẽ được sử dụng để tìm kiếm dữ liệu nhân khẩu học phù hợp từ Experian.</span><span class="sxs-lookup"><span data-stu-id="8d114-124">Select **Next** and define which type of fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="8d114-125">Ít nhất một trong các trường **Tên và địa chỉ**, **Điện thoại** hoặc **Email** là bắt buộc.</span><span class="sxs-lookup"><span data-stu-id="8d114-125">At least one of the fields **Name and address**, **Phone**, or **Email** is required.</span></span> <span data-ttu-id="8d114-126">Để có độ chính xác đối sánh cao hơn, có thể thêm tối đa hai trường khác.</span><span class="sxs-lookup"><span data-stu-id="8d114-126">For a higher match accuracy, up to two other fields can be added.</span></span> <span data-ttu-id="8d114-127">Lựa chọn này sẽ ảnh hưởng đến các trường ánh xạ mà bạn có quyền truy cập trong bước tiếp theo.</span><span class="sxs-lookup"><span data-stu-id="8d114-127">This selection will affect the mapping fields you have access to in the next step.</span></span>

    > [!TIP]
    > <span data-ttu-id="8d114-128">Nhiều thuộc tính mã định danh chính được gửi đến Experian có thể cho tỷ lệ khớp cao hơn.</span><span class="sxs-lookup"><span data-stu-id="8d114-128">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="8d114-129">Chọn **Tiếp** để bắt đầu quá trình ánh xạ trường.</span><span class="sxs-lookup"><span data-stu-id="8d114-129">Select **Next** to start the field mapping.</span></span>

1. <span data-ttu-id="8d114-130">Xác định loại trường nào từ hồ sơ hợp nhất của bạn sẽ được sử dụng để tìm kiếm dữ liệu nhân khẩu học phù hợp từ Experian.</span><span class="sxs-lookup"><span data-stu-id="8d114-130">Define which fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="8d114-131">Các trường bắt buộc đều được đánh dấu.</span><span class="sxs-lookup"><span data-stu-id="8d114-131">Required fields are marked.</span></span>

1. <span data-ttu-id="8d114-132">Đặt tên cho nội dung bổ sung và tên cho thực thể đầu ra.</span><span class="sxs-lookup"><span data-stu-id="8d114-132">Provide a name for the enrichment and a name for the output entity.</span></span>

1. <span data-ttu-id="8d114-133">Chọn **Lưu nội dung bổ sung** sau khi xem xét các lựa chọn của bạn.</span><span class="sxs-lookup"><span data-stu-id="8d114-133">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-experian"></a><span data-ttu-id="8d114-134">Đặt cấu hình kết nối cho Experian</span><span class="sxs-lookup"><span data-stu-id="8d114-134">Configure the connection for Experian</span></span> 

<span data-ttu-id="8d114-135">Bạn cần phải là quản trị viên thì mới có thể đặt cấu hình kết nối.</span><span class="sxs-lookup"><span data-stu-id="8d114-135">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="8d114-136">Chọn **Thêm kết nối** khi đặt cấu hình nội dung bổ sung *hoặc* đi đến **Quản trị viên** > **Kết nối** rồi chọn **Thiết lập** trên ngăn xếp Experian.</span><span class="sxs-lookup"><span data-stu-id="8d114-136">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Experian tile.</span></span>

1. <span data-ttu-id="8d114-137">Chọn **Bắt đầu**.</span><span class="sxs-lookup"><span data-stu-id="8d114-137">Select **Get Started**.</span></span>

1. <span data-ttu-id="8d114-138">Nhập tên cho kết nối trong hộp **Tên hiển thị**.</span><span class="sxs-lookup"><span data-stu-id="8d114-138">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="8d114-139">Nhập ID người dùng, ID bên và Số mô hình hợp lệ cho tài khoản Truyền tải an toàn Experian của bạn.</span><span class="sxs-lookup"><span data-stu-id="8d114-139">Enter valid User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span>

1. <span data-ttu-id="8d114-140">Xem lại và đồng ý với **Quyền riêng tư về dữ liệu và tuân thủ** bằng cách đánh dấu vào hộp kiểm **Tôi đồng ý**</span><span class="sxs-lookup"><span data-stu-id="8d114-140">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox</span></span>

1. <span data-ttu-id="8d114-141">Chọn **Xác minh** để xác thực cấu hình.</span><span class="sxs-lookup"><span data-stu-id="8d114-141">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="8d114-142">Sau khi hoàn thành xác minh, hãy chọn **Lưu**.</span><span class="sxs-lookup"><span data-stu-id="8d114-142">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Ngăn cấu hình kết nối Experian.":::

## <a name="enrichment-results"></a><span data-ttu-id="8d114-144">Kết quả làm phong phú</span><span class="sxs-lookup"><span data-stu-id="8d114-144">Enrichment results</span></span>

<span data-ttu-id="8d114-145">Để bắt đầu quá trình tăng cường, hãy chọn **Chạy** từ thanh lệnh.</span><span class="sxs-lookup"><span data-stu-id="8d114-145">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="8d114-146">Bạn cũng có thể để hệ thống chạy quá trình tăng cường tự động như một phần của [làm mới theo lịch trình](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="8d114-146">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="8d114-147">Thời gian xử lý sẽ phụ thuộc vào quy mô dữ liệu khách hàng của bạn và quy trình tăng cường được thiết lập cho tài khoản của bạn bởi Experian.</span><span class="sxs-lookup"><span data-stu-id="8d114-147">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="8d114-148">Sau khi quá trình tăng cường hoàn tất, bạn có thể xem lại dữ liệu hồ sơ khách hàng mới được bổ sung trong **Nội dung tăng cường của tôi**.</span><span class="sxs-lookup"><span data-stu-id="8d114-148">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="8d114-149">Ngoài ra, bạn sẽ tìm thấy thời gian của lần cập nhật gần nhất và số lượng hồ sơ được tăng cường.</span><span class="sxs-lookup"><span data-stu-id="8d114-149">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="8d114-150">Bạn có thể truy cập dạng xem chi tiết của từng hồ sơ được làm phong phú bằng cách chọn **Xem dữ liệu được làm phong phú**.</span><span class="sxs-lookup"><span data-stu-id="8d114-150">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="8d114-151">Các bước tiếp theo</span><span class="sxs-lookup"><span data-stu-id="8d114-151">Next steps</span></span>

<span data-ttu-id="8d114-152">Xây dựng dựa trên dữ liệu khách hàng phong phú của bạn.</span><span class="sxs-lookup"><span data-stu-id="8d114-152">Build on top of your enriched customer data.</span></span> <span data-ttu-id="8d114-153">Tạo [phân khúc](segments.md), [biện pháp](measures.md) và [xuất dữ liệu](export-destinations.md) để cung cấp trải nghiệm cá nhân cho khách hàng của bạn.</span><span class="sxs-lookup"><span data-stu-id="8d114-153">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="8d114-154">Quyền riêng tư về dữ liệu và tuân thủ</span><span class="sxs-lookup"><span data-stu-id="8d114-154">Data privacy and compliance</span></span>

<span data-ttu-id="8d114-155">Khi bật Dynamics 365 Customer Insights để truyền dữ liệu tới Experian, bạn cho phép chuyển dữ liệu ra bên ngoài ranh giới tuân thủ cho Dynamics 365 Customer Insights, bao gồm dữ liệu nhạy cảm tiềm ẩn như Dữ liệu cá nhân.</span><span class="sxs-lookup"><span data-stu-id="8d114-155">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="8d114-156">Microsoft sẽ chuyển những dữ liệu đó theo chỉ dẫn của bạn, nhưng bạn có trách nhiệm đảm bảo rằng Experian đáp ứng mọi nghĩa vụ về quyền riêng tư hoặc bảo mật mà bạn có thể có.</span><span class="sxs-lookup"><span data-stu-id="8d114-156">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="8d114-157">Để biết thêm thông tin, hãy xem [Tuyên bố về Quyền riêng tư của Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="8d114-157">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="8d114-158">Quản trị viên Dynamics 365 Customer Insights của bạn có thể xóa tính năng tăng cường này bất kỳ lúc nào để ngừng sử dụng chức năng này.</span><span class="sxs-lookup"><span data-stu-id="8d114-158">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
