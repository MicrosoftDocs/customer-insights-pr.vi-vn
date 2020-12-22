---
title: Tăng cường với Experian tăng cường của bên thứ ba
description: Thông tin chung về tăng cường của bên thứ ba Experian.
ms.date: 09/17/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 60fc49734e54740e83b47a7028be216a0eb81e49
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668839"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="6d245-103">Làm phong phú hồ sơ khách hàng với dữ liệu nhân khẩu học từ Experian (bản xem trước)</span><span class="sxs-lookup"><span data-stu-id="6d245-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="6d245-104">Experian là công ty tiên phong toàn cầu về các dịch vụ tiếp thị và báo cáo tín dụng cho người tiêu dùng và doanh nghiệp.</span><span class="sxs-lookup"><span data-stu-id="6d245-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="6d245-105">Với dịch vụ làm phong phú dữ liệu của Experian, bạn có thể có được sự hiểu biết sâu sắc hơn về khách hàng của mình qua việc làm phong phú hồ sơ khách hàng của bạn bằng dữ liệu nhân khẩu học, như: quy mô hộ gia đình, thu nhập, v.v.</span><span class="sxs-lookup"><span data-stu-id="6d245-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6d245-106">Điều kiện tiên quyết</span><span class="sxs-lookup"><span data-stu-id="6d245-106">Prerequisites</span></span>

<span data-ttu-id="6d245-107">Để đặt cấu hình Experian, các điều kiện tiên quyết sau phải được đáp ứng:</span><span class="sxs-lookup"><span data-stu-id="6d245-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="6d245-108">Bạn có gói đăng ký Experian đang hoạt động.</span><span class="sxs-lookup"><span data-stu-id="6d245-108">You have an active Experian subscription.</span></span> <span data-ttu-id="6d245-109">Để đăng ký, hãy [liên hệ trực tiếp với Experian](https://www.experian.com/marketing-services/contact).</span><span class="sxs-lookup"><span data-stu-id="6d245-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="6d245-110">[Tìm hiểu thêm về Tăng cường dữ liệu bằng Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="6d245-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>
- <span data-ttu-id="6d245-111">Bạn có ID người dùng, ID bên và Số mô hình cho tài khoản Secure Transport (ST) hỗ trợ SSH của mình mà Experian đã tạo cho bạn.</span><span class="sxs-lookup"><span data-stu-id="6d245-111">You have the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>
- <span data-ttu-id="6d245-112">Bạn có quyền [Quản trị viên](permissions.md#administrator) trong thông tin chi tiết về đối tượng.</span><span class="sxs-lookup"><span data-stu-id="6d245-112">You have [Administrator](permissions.md#administrator) permissions in audience insights.</span></span>

## <a name="configuration"></a><span data-ttu-id="6d245-113">Cấu hình</span><span class="sxs-lookup"><span data-stu-id="6d245-113">Configuration</span></span>

1. <span data-ttu-id="6d245-114">Đi đến **Dữ liệu** > **Tăng cường** và chọn tab **Khám phá**.</span><span class="sxs-lookup"><span data-stu-id="6d245-114">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="6d245-115">Chọn **Tăng cường dữ liệu của tôi** trên ngăn xếp Experian.</span><span class="sxs-lookup"><span data-stu-id="6d245-115">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6d245-116">![Ngăn xếp Experian](media/experian-tile.png "Ngăn xếp Experian")</span><span class="sxs-lookup"><span data-stu-id="6d245-116">![Experian tile](media/experian-tile.png "Experian tile")</span></span>

1. <span data-ttu-id="6d245-117">Chọn **Bắt đầu** rồi nhập ID người dùng, ID bên và Số mô hình cho tài khoản Experian Secure Transport của bạn.</span><span class="sxs-lookup"><span data-stu-id="6d245-117">Select **Get started** and enter the User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span> <span data-ttu-id="6d245-118">Xem lại và đồng ý với **Quyền riêng tư và tuân thủ dữ liệu** bằng cách đánh dấu ô **Tôi đồng ý**.</span><span class="sxs-lookup"><span data-stu-id="6d245-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="6d245-119">Xác nhận tất cả các đầu vào bằng cách chọn **Áp dụng**.</span><span class="sxs-lookup"><span data-stu-id="6d245-119">Confirm all inputs by selecting **Apply**.</span></span>

## <a name="map-your-fields"></a><span data-ttu-id="6d245-120">Ánh xạ trường của bạn</span><span class="sxs-lookup"><span data-stu-id="6d245-120">Map your fields</span></span>

1. <span data-ttu-id="6d245-121">Chọn **Thêm dữ liệu** rồi chọn mã định danh chính từ **Tên và địa chỉ**, **Email** hoặc **Điện thoại** và gửi đến Experian để thực hiện quá trình nhận dạng danh tính.</span><span class="sxs-lookup"><span data-stu-id="6d245-121">Select **Add data** and choose your key identifiers from **Name and Address**, **E-mail**, or **Phone** to send to Experian for identity resolution.</span></span>

   > [!TIP]
   > <span data-ttu-id="6d245-122">Nhiều thuộc tính mã định danh chính được gửi đến Experian có thể cho tỷ lệ khớp cao hơn.</span><span class="sxs-lookup"><span data-stu-id="6d245-122">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="6d245-123">Chọn **Tiếp** và ánh xạ các thuộc tính tương ứng từ thực thể khách hàng hợp nhất của bạn cho các trường mã định danh chính đã chọn.</span><span class="sxs-lookup"><span data-stu-id="6d245-123">Select **Next** and map the corresponding attributes from your unified customer entity for the selected key identifier fields.</span></span>

1. <span data-ttu-id="6d245-124">Chọn **Thêm thuộc tính** để ánh xạ thêm thuộc tính mà bạn muốn gửi đến Experian.</span><span class="sxs-lookup"><span data-stu-id="6d245-124">Select **Add attribute** to map any additional attributes you would like to send to Experian.</span></span>

1.  <span data-ttu-id="6d245-125">Chọn **Lưu** để hoàn tất quá trình ánh xạ trường.</span><span class="sxs-lookup"><span data-stu-id="6d245-125">Select **Save** to complete the field mapping.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6d245-126">![Ánh xạ trường Experian](media/experian-field-mapping.png "Ánh xạ trường Experian")</span><span class="sxs-lookup"><span data-stu-id="6d245-126">![Experian field mapping](media/experian-field-mapping.png "Experian field mapping")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="6d245-127">Kết quả làm phong phú</span><span class="sxs-lookup"><span data-stu-id="6d245-127">Enrichment results</span></span>

<span data-ttu-id="6d245-128">Để bắt đầu quá trình tăng cường, hãy chọn **Chạy** từ thanh lệnh.</span><span class="sxs-lookup"><span data-stu-id="6d245-128">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="6d245-129">Bạn cũng có thể để hệ thống chạy quá trình tăng cường tự động như một phần của [làm mới theo lịch trình](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="6d245-129">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="6d245-130">Thời gian xử lý sẽ phụ thuộc vào quy mô dữ liệu khách hàng của bạn và quy trình tăng cường được thiết lập cho tài khoản của bạn bởi Experian.</span><span class="sxs-lookup"><span data-stu-id="6d245-130">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="6d245-131">Sau khi quá trình tăng cường hoàn tất, bạn có thể xem lại dữ liệu hồ sơ khách hàng mới được bổ sung trong **Nội dung tăng cường của tôi**.</span><span class="sxs-lookup"><span data-stu-id="6d245-131">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="6d245-132">Ngoài ra, bạn sẽ tìm thấy thời gian của lần cập nhật gần nhất và số lượng hồ sơ được tăng cường.</span><span class="sxs-lookup"><span data-stu-id="6d245-132">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="6d245-133">Bạn có thể truy cập dạng xem chi tiết của từng hồ sơ được làm phong phú bằng cách chọn **Xem dữ liệu được làm phong phú**.</span><span class="sxs-lookup"><span data-stu-id="6d245-133">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="6d245-134">Các bước tiếp theo</span><span class="sxs-lookup"><span data-stu-id="6d245-134">Next steps</span></span>

<span data-ttu-id="6d245-135">Xây dựng dựa trên dữ liệu khách hàng phong phú của bạn.</span><span class="sxs-lookup"><span data-stu-id="6d245-135">Build on top of your enriched customer data.</span></span> <span data-ttu-id="6d245-136">Tạo [phân khúc](segments.md), [biện pháp](measures.md) và [xuất dữ liệu](export-destinations.md) để cung cấp trải nghiệm cá nhân cho khách hàng của bạn.</span><span class="sxs-lookup"><span data-stu-id="6d245-136">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="6d245-137">Quyền riêng tư về dữ liệu và tuân thủ</span><span class="sxs-lookup"><span data-stu-id="6d245-137">Data privacy and compliance</span></span>

<span data-ttu-id="6d245-138">Khi bật Dynamics 365 Customer Insights để truyền dữ liệu tới Experian, bạn cho phép chuyển dữ liệu ra bên ngoài ranh giới tuân thủ cho Dynamics 365 Customer Insights, bao gồm dữ liệu nhạy cảm tiềm ẩn như Dữ liệu cá nhân.</span><span class="sxs-lookup"><span data-stu-id="6d245-138">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="6d245-139">Microsoft sẽ chuyển những dữ liệu đó theo chỉ dẫn của bạn, nhưng bạn có trách nhiệm đảm bảo rằng Experian đáp ứng mọi nghĩa vụ về quyền riêng tư hoặc bảo mật mà bạn có thể có.</span><span class="sxs-lookup"><span data-stu-id="6d245-139">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="6d245-140">Để biết thêm thông tin, hãy xem [Tuyên bố về Quyền riêng tư của Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="6d245-140">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="6d245-141">Quản trị viên Dynamics 365 Customer Insights của bạn có thể xóa tính năng tăng cường này bất kỳ lúc nào để ngừng sử dụng chức năng này.</span><span class="sxs-lookup"><span data-stu-id="6d245-141">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>
