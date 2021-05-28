---
title: Tăng cường nâng cao địa chỉ
description: Tăng cường và chuẩn hóa thông tin địa chỉ của hồ sơ khách hàng bằng các mô hình của Microsoft.
ms.date: 04/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 07271d491460764f2c738e760e41c3492f2b6de9
ms.sourcegitcommit: 27f9dd837304ef9fc00f055a6e900fbf6fce1429
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 04/30/2021
ms.locfileid: "5965604"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a><span data-ttu-id="a4999-103">Tăng cường hồ sơ khách hàng với các địa chỉ nâng cao</span><span class="sxs-lookup"><span data-stu-id="a4999-103">Enrichment of customer profiles with enhanced addresses</span></span>

<span data-ttu-id="a4999-104">Địa chỉ trong dữ liệu của bạn có thể phi cấu trúc, không đầy đủ hoặc không chính xác.</span><span class="sxs-lookup"><span data-stu-id="a4999-104">Addresses in your data can be unstructured, incomplete, or incorrect.</span></span> <span data-ttu-id="a4999-105">Sử dụng các mô hình của Microsoft để chuẩn hóa và tăng cường các địa chỉ của bạn tại [định dạng Common Data Model](/common-data-model/schema/core/applicationcommon/address) để có thông tin chi tiết và độ chính xác cao hơn.</span><span class="sxs-lookup"><span data-stu-id="a4999-105">Use Microsoft's models to normalize and enrich your addresses into the [Common Data Model format](/common-data-model/schema/core/applicationcommon/address) for better accuracy and insights.</span></span>

## <a name="how-we-enhance-addresses"></a><span data-ttu-id="a4999-106">Cách chúng tôi nâng cao địa chỉ</span><span class="sxs-lookup"><span data-stu-id="a4999-106">How we enhance addresses</span></span>

<span data-ttu-id="a4999-107">Mô hình của chúng tôi nâng cao địa chỉ thông qua một quy trình hai bước.</span><span class="sxs-lookup"><span data-stu-id="a4999-107">Our model goes through a two-step process to enhance an address.</span></span> <span data-ttu-id="a4999-108">Đầu tiên, mô hình phân tích cú pháp địa chỉ để xác định các thành phần của địa chỉ này và đưa chúng vào một định dạng có cấu trúc.</span><span class="sxs-lookup"><span data-stu-id="a4999-108">First, it parses the address to identify its components and puts them into a structured format.</span></span> <span data-ttu-id="a4999-109">Sau đó, chúng tôi sử dụng trí tuệ nhân tạo để chỉnh sửa, hoàn thiện và chuẩn hóa các giá trị trong địa chỉ.</span><span class="sxs-lookup"><span data-stu-id="a4999-109">Then, we use artificial intelligence to correct, complete, and standardize the values in the address.</span></span>

### <a name="example"></a><span data-ttu-id="a4999-110">Ví dụ:</span><span class="sxs-lookup"><span data-stu-id="a4999-110">Example</span></span>

<span data-ttu-id="a4999-111">Thông tin địa chỉ có thể ở định dạng phi tiêu chuẩn và có lỗi chính tả.</span><span class="sxs-lookup"><span data-stu-id="a4999-111">Address information might be in a non-standard format and contain spelling errors.</span></span> <span data-ttu-id="a4999-112">Mô hình có thể khắc phục những vấn đề này và tạo địa chỉ nhất quán trong hồ sơ khách hàng hợp nhất.</span><span class="sxs-lookup"><span data-stu-id="a4999-112">The model can fix these issues and create consistent addresses in unified customer profiles.</span></span>

```Input
4567 w main stret californa missouri 54321 us
```

```Output
- Street1: 4567 W Main St
- City: California
- StateOrProvince: MO
- ZipOrPostalCode: 54321
- CountryOrRegion: United States of America

- Address: 4567 W Main St, California, MO, 54321, United States of America
```

### <a name="limitations"></a><span data-ttu-id="a4999-113">Giới hạn</span><span class="sxs-lookup"><span data-stu-id="a4999-113">Limitations</span></span>

<span data-ttu-id="a4999-114">Địa chỉ nâng cao chỉ hoạt động với các giá trị đã tồn tại trong dữ liệu địa chỉ đã nhập của bạn.</span><span class="sxs-lookup"><span data-stu-id="a4999-114">Enhanced addresses only works with the values that already exist in your ingested address data.</span></span> <span data-ttu-id="a4999-115">Mô hình không:</span><span class="sxs-lookup"><span data-stu-id="a4999-115">The model doesn't:</span></span> 

1. <span data-ttu-id="a4999-116">Xác minh tính hợp lệ của địa chỉ.</span><span class="sxs-lookup"><span data-stu-id="a4999-116">Verify if the address is a valid address.</span></span>
2. <span data-ttu-id="a4999-117">Xác minh tính hợp lệ của bất kỳ giá trị nào, chẳng hạn như mã ZIP hoặc tên phố.</span><span class="sxs-lookup"><span data-stu-id="a4999-117">Verify if any of the values, such as ZIP codes or street names, are valid.</span></span>
3. <span data-ttu-id="a4999-118">Thay đổi các giá trị mà mô hình không nhận dạng được.</span><span class="sxs-lookup"><span data-stu-id="a4999-118">Change values it doesn't recognize.</span></span>

<span data-ttu-id="a4999-119">Mô hình sử dụng các kỹ thuật dựa trên máy học để nâng cao địa chỉ.</span><span class="sxs-lookup"><span data-stu-id="a4999-119">The model uses machine learning-based techniques to enhance addresses.</span></span> <span data-ttu-id="a4999-120">Mặc dù áp dụng ngưỡng tin cậy cao khi mô hình thay đổi giá trị đầu vào nhưng giống với các mô hình dựa trên máy học khác, chúng tôi không thể đảm bảo độ chính xác 100%.</span><span class="sxs-lookup"><span data-stu-id="a4999-120">While we apply a high confidence threshold for when the model changes an input value, as with any ML-based model, 100% accuracy is not guaranteed.</span></span>

## <a name="supported-countries-or-regions"></a><span data-ttu-id="a4999-121">Các quốc gia hoặc vùng lãnh thổ được hỗ trợ</span><span class="sxs-lookup"><span data-stu-id="a4999-121">Supported countries or regions</span></span>

<span data-ttu-id="a4999-122">Chúng tôi hiện hỗ trợ tăng cường địa chỉ ở các quốc gia hoặc vùng lãnh thổ sau:</span><span class="sxs-lookup"><span data-stu-id="a4999-122">We currently support enriching addresses in these countries or regions:</span></span> 

- <span data-ttu-id="a4999-123">Australia</span><span class="sxs-lookup"><span data-stu-id="a4999-123">Australia</span></span>
- <span data-ttu-id="a4999-124">Canada</span><span class="sxs-lookup"><span data-stu-id="a4999-124">Canada</span></span>
- <span data-ttu-id="a4999-125">Vương quốc Anh</span><span class="sxs-lookup"><span data-stu-id="a4999-125">United Kingdom</span></span>
- <span data-ttu-id="a4999-126">Hoa Kỳ</span><span class="sxs-lookup"><span data-stu-id="a4999-126">United States</span></span>

<span data-ttu-id="a4999-127">Địa chỉ phải có thông tin quốc gia/vùng lãnh thổ.</span><span class="sxs-lookup"><span data-stu-id="a4999-127">Addresses must contain a country/region value.</span></span> <span data-ttu-id="a4999-128">Chúng tôi không xử lý các địa chỉ có quốc gia hoặc vùng lãnh thổ không được hỗ trợ và các địa chỉ không có thông tin quốc gia hoặc vùng lãnh thổ được cung cấp.</span><span class="sxs-lookup"><span data-stu-id="a4999-128">We don't process addresses for countries or regions that aren't supported and addresses that have no country or region provided.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="a4999-129">Đặt cấu hình nội dung bổ sung</span><span class="sxs-lookup"><span data-stu-id="a4999-129">Configure the enrichment</span></span>

1. <span data-ttu-id="a4999-130">Chuyển tới **Dữ liệu** > **Nội dung phong phú**.</span><span class="sxs-lookup"><span data-stu-id="a4999-130">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="a4999-131">Chọn **Tăng cường dữ liệu của tôi** trên ngăn xếp **Địa chỉ nâng cao**.</span><span class="sxs-lookup"><span data-stu-id="a4999-131">Select **Enrich my data** on the **Enhanced addresses** tile.</span></span>

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="Ảnh chụp màn hình ngăn xếp Địa chỉ nâng cao.":::

1. <span data-ttu-id="a4999-133">Chọn **Tập hợp dữ liệu khách hàng** và chọn thực thể chứa các địa chỉ bạn muốn tăng cường.</span><span class="sxs-lookup"><span data-stu-id="a4999-133">Select the **Customer data set** and choose the entity containing the addresses you want to enrich.</span></span> <span data-ttu-id="a4999-134">Bạn có thể chọn thực thể *Khách hàng* để tăng cường địa chỉ có trong tất cả các hồ sơ khách hàng của bạn hoặc chọn một thực thể phân khúc để tăng cường duy nhất địa chỉ có trong hồ sơ khách hàng thuộc phân khúc đó.</span><span class="sxs-lookup"><span data-stu-id="a4999-134">You can select the *Customer* entity to enrich addresses in all your customer profiles or select a segment entity to enrich addresses only in customer profiles contained in that segment.</span></span>

1. <span data-ttu-id="a4999-135">Chọn cách định dạng địa chỉ trong tập hợp dữ liệu của bạn.</span><span class="sxs-lookup"><span data-stu-id="a4999-135">Select how addresses are formatted in your data set.</span></span> <span data-ttu-id="a4999-136">Chọn **Địa chỉ một thuộc tính** nếu địa chỉ trong dữ liệu của bạn sử dụng một trường.</span><span class="sxs-lookup"><span data-stu-id="a4999-136">Choose **Single-attribute address** if addresses in your data use a single field.</span></span> <span data-ttu-id="a4999-137">Chọn **Địa chỉ nhiều thuộc tính** nếu địa chỉ trong dữ liệu của bạn sử dụng nhiều hơn một trường.</span><span class="sxs-lookup"><span data-stu-id="a4999-137">Choose **Multiple-attribute address** if addresses in your data use more than one data field.</span></span>

   > [!NOTE]
   > <span data-ttu-id="a4999-138">Bạn cần có thông tin về Quốc gia/Vùng lãnh thổ trong cả địa chỉ một thuộc tính đơn và địa chỉ nhiều thuộc tính.</span><span class="sxs-lookup"><span data-stu-id="a4999-138">Country/Region is mandatory in both single-attribute and multiple-attribute address.</span></span> <span data-ttu-id="a4999-139">Chúng tôi sẽ không tăng cường các địa chỉ không chứa giá trị quốc gia/vùng lãnh thổ hợp lệ hoặc được hỗ trợ</span><span class="sxs-lookup"><span data-stu-id="a4999-139">Addresses that don't contain valid or supported country/region values won't be enriched</span></span>

1.  <span data-ttu-id="a4999-140">Ánh xạ các trường địa chỉ từ thực thể khách hàng hợp nhất của bạn.</span><span class="sxs-lookup"><span data-stu-id="a4999-140">Map the address fields from your unified customer entity.</span></span>

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Trang ánh xạ trường địa chỉ nâng cao.":::

1. <span data-ttu-id="a4999-142">Chọn **Tiếp** để hoàn thành quá trình ánh xạ trường.</span><span class="sxs-lookup"><span data-stu-id="a4999-142">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="a4999-143">Cung cấp tên cho nội dung bổ sung và thực thể đầu ra.</span><span class="sxs-lookup"><span data-stu-id="a4999-143">Provide a name for the enrichment and the output entity.</span></span>

1. <span data-ttu-id="a4999-144">Chọn **Lưu nội dung bổ sung** sau khi xem xét các lựa chọn của bạn.</span><span class="sxs-lookup"><span data-stu-id="a4999-144">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="a4999-145">Kết quả làm phong phú</span><span class="sxs-lookup"><span data-stu-id="a4999-145">Enrichment results</span></span>

<span data-ttu-id="a4999-146">Để bắt đầu quá trình tăng cường, hãy chọn **Chạy** từ thanh lệnh.</span><span class="sxs-lookup"><span data-stu-id="a4999-146">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="a4999-147">Bạn cũng có thể để hệ thống chạy quá trình tăng cường tự động như một phần của [làm mới theo lịch trình](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="a4999-147">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="a4999-148">Thời gian xử lý phụ thuộc vào kích thước dữ liệu khách hàng của bạn.</span><span class="sxs-lookup"><span data-stu-id="a4999-148">The processing time depends on the size of your customer data.</span></span>

<span data-ttu-id="a4999-149">Sau khi quá trình tăng cường hoàn tất, bạn có thể xem lại dữ liệu hồ sơ khách hàng mới được bổ sung trong **Nội dung tăng cường của tôi**.</span><span class="sxs-lookup"><span data-stu-id="a4999-149">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="a4999-150">Ngoài ra, bạn sẽ tìm thấy thời gian của lần cập nhật gần nhất và số lượng hồ sơ được tăng cường.</span><span class="sxs-lookup"><span data-stu-id="a4999-150">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="a4999-151">Bạn có thể truy cập dạng xem chi tiết của từng hồ sơ được làm phong phú bằng cách chọn **Xem dữ liệu được làm phong phú**.</span><span class="sxs-lookup"><span data-stu-id="a4999-151">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a4999-152">Các bước tiếp theo</span><span class="sxs-lookup"><span data-stu-id="a4999-152">Next steps</span></span>

<span data-ttu-id="a4999-153">Xây dựng dựa trên dữ liệu khách hàng phong phú của bạn.</span><span class="sxs-lookup"><span data-stu-id="a4999-153">Build on top of your enriched customer data.</span></span> <span data-ttu-id="a4999-154">Tạo [phân khúc](segments.md), [biện pháp](measures.md) và [xuất dữ liệu](export-destinations.md) để cung cấp trải nghiệm cá nhân cho khách hàng của bạn.</span><span class="sxs-lookup"><span data-stu-id="a4999-154">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
