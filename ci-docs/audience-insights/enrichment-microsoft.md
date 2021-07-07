---
title: Tăng cường thông tin hồ sơ khách hàng bằng dữ liệu từ Microsoft
description: Sử dụng dữ liệu độc quyền từ Microsoft để bổ sung các mối quan hệ về thương hiệu và sở thích cho dữ liệu khách hàng của bạn.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 1b11c325649b91ebb47cde924227eacedae64b7a
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305182"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a><span data-ttu-id="b32e5-103">Tăng cường dữ liệu hồ sơ khách hàng bằng mối quan hệ thương hiệu và sở thích (bản xem trước)</span><span class="sxs-lookup"><span data-stu-id="b32e5-103">Enrich customer profiles with brand and interest affinities (preview)</span></span>

<span data-ttu-id="b32e5-104">Sử dụng dữ liệu độc quyền của Microsoft để bổ sung các mối quan hệ về sở thích và thương hiệu cho dữ liệu khách hàng của bạn.</span><span class="sxs-lookup"><span data-stu-id="b32e5-104">Use Microsoft's proprietary data to enrich your customer data with brand and interest affinities.</span></span> <span data-ttu-id="b32e5-105">Các mối quan hệ này dựa trên dữ liệu từ những người thuộc nhóm nhân khẩu học tương tự với khách hàng của bạn.</span><span class="sxs-lookup"><span data-stu-id="b32e5-105">These affinities are based on data from people with demographics similar to your customers.</span></span> <span data-ttu-id="b32e5-106">Thông tin này giúp bạn hiểu rõ hơn và chia phân khúc khách hàng của bạn dựa trên mối quan hệ của họ với các thương hiệu và sở thích cụ thể.</span><span class="sxs-lookup"><span data-stu-id="b32e5-106">This information helps you to better understand and segment your customers based on their affinities to specific brands and interests.</span></span>

<span data-ttu-id="b32e5-107">Trong thông tin chuyên sâu về đối tượng, hãy đi tới **Dữ liệu** > **Tăng cường dữ liệu** để [định cấu hình và xem dữ liệu tăng cường](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="b32e5-107">In audience insights, go to **Data** > **Enrichment** to [configure and view enrichments](enrichment-hub.md).</span></span>

<span data-ttu-id="b32e5-108">Để định cấu hình dữ liệu tăng cường phụ về mối quan hệ thương hiệu, hãy chuyển đến tab **Khám phá** rồi chọn **Tăng cường dữ liệu của tôi** trên ngăn xếp **Thương hiệu**.</span><span class="sxs-lookup"><span data-stu-id="b32e5-108">To configure brand affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Brands** tile.</span></span>

<span data-ttu-id="b32e5-109">Để định cấu hình dữ liệu tăng cường mối quan hệ về sở thích, hãy chuyển đến tab **Khám phá** rồi chọn **Tăng cường dữ liệu của tôi** trên ngăn xếp **Sở thích**.</span><span class="sxs-lookup"><span data-stu-id="b32e5-109">To configure interest affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Interests** tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b32e5-110">![Ngăn xếp Thương hiệu và Sở thích](media/BrandsInterest-tile-Hub.png "Ngăn xếp Thương hiệu và Sở thích")</span><span class="sxs-lookup"><span data-stu-id="b32e5-110">![Brands and Interests tiles](media/BrandsInterest-tile-Hub.png "Brands and Interest tiles")</span></span>

## <a name="how-we-determine-affinities"></a><span data-ttu-id="b32e5-111">Cách chúng tôi xác định mối quan hệ</span><span class="sxs-lookup"><span data-stu-id="b32e5-111">How we determine affinities</span></span>

<span data-ttu-id="b32e5-112">Chúng tôi sử dụng dữ liệu tìm kiếm trực tuyến của Microsoft để tìm mối quan hệ về thương hiệu và sở thích trên các phân khúc nhân khẩu học khác nhau (được xác định theo độ tuổi, giới tính hoặc vị trí).</span><span class="sxs-lookup"><span data-stu-id="b32e5-112">We use Microsoft’s online search data to find affinities for brands and interests across various demographic segments (defined by age, gender, or location).</span></span> <span data-ttu-id="b32e5-113">Khối lượng tìm kiếm trực tuyến cho một thương hiệu hoặc sở thích xác định mức độ quan hệ của một phân khúc nhân khẩu học, so với các phân khúc khác, đối với thương hiệu hoặc sở thích đó.</span><span class="sxs-lookup"><span data-stu-id="b32e5-113">The online search volume for a brand or interest determines how much affinity a demographic segment, compared to other segments, has to that brand or interest.</span></span>

## <a name="affinity-level-and-score"></a><span data-ttu-id="b32e5-114">Mức độ và điểm số mối quan hệ</span><span class="sxs-lookup"><span data-stu-id="b32e5-114">Affinity level and score</span></span>

<span data-ttu-id="b32e5-115">Trên mỗi hồ sơ khách hàng được tăng cường dữ liệu, chúng tôi cung cấp hai giá trị liên quan: mức độ mối quan hệ và điểm số mối quan hệ.</span><span class="sxs-lookup"><span data-stu-id="b32e5-115">On every enriched customer profile, we provide two related values: affinity level and affinity score.</span></span> <span data-ttu-id="b32e5-116">Những giá trị này giúp bạn xác định mức độ quan tâm đối với phân khúc nhân khẩu học của hồ sơ đó, đối với thương hiệu hoặc sở thích so với các phân khúc nhân khẩu học khác.</span><span class="sxs-lookup"><span data-stu-id="b32e5-116">These values help you determine how strong the affinity is for that profile’s demographic segment, for a brand or interest, as compared to other demographic segments.</span></span>

<span data-ttu-id="b32e5-117">*Mức độ mối quan hệ* bao gồm 4 cấp độ và *điểm mối quan hệ* được tính toán trên thang điểm 100 ánh xạ tới các mức độ mối quan hệ.</span><span class="sxs-lookup"><span data-stu-id="b32e5-117">*Affinity level* consists of four levels and *affinity score* is calculated on a 100-point scale that maps to the affinity levels.</span></span>


|<span data-ttu-id="b32e5-118">Mức độ mối quan hệ</span><span class="sxs-lookup"><span data-stu-id="b32e5-118">Affinity level</span></span> |<span data-ttu-id="b32e5-119">Điểm số mối quan hệ</span><span class="sxs-lookup"><span data-stu-id="b32e5-119">Affinity score</span></span>  |
|---------|---------|
|<span data-ttu-id="b32e5-120">Rất cao</span><span class="sxs-lookup"><span data-stu-id="b32e5-120">Very high</span></span>     | <span data-ttu-id="b32e5-121">85-100</span><span class="sxs-lookup"><span data-stu-id="b32e5-121">85-100</span></span>       |
|<span data-ttu-id="b32e5-122">Cao</span><span class="sxs-lookup"><span data-stu-id="b32e5-122">High</span></span>     | <span data-ttu-id="b32e5-123">70-84</span><span class="sxs-lookup"><span data-stu-id="b32e5-123">70-84</span></span>        |
|<span data-ttu-id="b32e5-124">Trung bình</span><span class="sxs-lookup"><span data-stu-id="b32e5-124">Medium</span></span>     | <span data-ttu-id="b32e5-125">35-69</span><span class="sxs-lookup"><span data-stu-id="b32e5-125">35-69</span></span>        |
|<span data-ttu-id="b32e5-126">Thấp</span><span class="sxs-lookup"><span data-stu-id="b32e5-126">Low</span></span>     | <span data-ttu-id="b32e5-127">1-34</span><span class="sxs-lookup"><span data-stu-id="b32e5-127">1-34</span></span>        |

<span data-ttu-id="b32e5-128">Tùy thuộc vào mức độ chi tiết mà bạn muốn đo lường mối quan hệ, bạn có thể sử dụng mức độ hoặc điểm số mối quan hệ.</span><span class="sxs-lookup"><span data-stu-id="b32e5-128">Depending on the granularity you would like for measuring the affinity, you can use either affinity level or score.</span></span> <span data-ttu-id="b32e5-129">Điểm số mối quan hệ giúp bạn kiểm soát chính xác hơn.</span><span class="sxs-lookup"><span data-stu-id="b32e5-129">Affinity score gives you more precise control.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="b32e5-130">Quốc gia/khu vực được hỗ trợ</span><span class="sxs-lookup"><span data-stu-id="b32e5-130">Supported countries/regions</span></span>

<span data-ttu-id="b32e5-131">Chúng tôi hiện hỗ trợ các tùy chọn quốc gia/vùng sau đây: Úc, Canada (Tiếng Anh), Pháp, Đức, Vương quốc Anh hoặc Hoa Kỳ (Tiếng Anh).</span><span class="sxs-lookup"><span data-stu-id="b32e5-131">We currently support the following country/region options: Australia, Canada (English), France, Germany, United Kingdom, or United States (English).</span></span>

<span data-ttu-id="b32e5-132">Để chọn một quốc gia hoặc khu vực, hãy mở **Dữ liệu tăng cường về thương hiệu** hoặc **Dữ liệu tăng cường về sở thích** rồi chọn **Thay đổi** bên cạnh **Quốc gia/Khu vực**.</span><span class="sxs-lookup"><span data-stu-id="b32e5-132">To select a country or region, open **Brands enrichment** or **Interest enrichment** and select **Change** next to **Country/Region**.</span></span> <span data-ttu-id="b32e5-133">Trong ngăn **Cài đặt Quốc gia/Khu vực**, chọn một tùy chọn rồi chọn **Áp dụng**.</span><span class="sxs-lookup"><span data-stu-id="b32e5-133">In the **Country/Region settings** pane, choose an option and select **Apply**.</span></span>

### <a name="implications-related-to-country-selection"></a><span data-ttu-id="b32e5-134">Ý nghĩa liên quan đến chọn quốc gia</span><span class="sxs-lookup"><span data-stu-id="b32e5-134">Implications related to country selection</span></span>

- <span data-ttu-id="b32e5-135">Khi [chọn thương hiệu của riêng bạn](#define-your-brands-or-interests), hệ thống cung cấp các đề xuất dựa trên quốc gia hoặc khu vực đã chọn.</span><span class="sxs-lookup"><span data-stu-id="b32e5-135">When [choosing your own brands](#define-your-brands-or-interests), the system provides suggestions based on the selected country or region.</span></span>

- <span data-ttu-id="b32e5-136">Khi [chọn một ngành](#define-your-brands-or-interests), bạn sẽ nhận được các thương hiệu hoặc sở thích phù hợp nhất dựa trên quốc gia hoặc khu vực đã chọn.</span><span class="sxs-lookup"><span data-stu-id="b32e5-136">When [choosing an industry](#define-your-brands-or-interests), you'll get the most relevant brands or interests based on the selected country or region.</span></span>

- <span data-ttu-id="b32e5-137">Khi [tăng cường dữ liệu hồ sơ](#refresh-enrichment), chúng tôi sẽ bổ sung thông tin cho tất cả hồ sơ khách hàng mà chúng tôi lấy dữ liệu cho thương hiệu và sở thích đã chọn, bao gồm cả các hồ sơ không thuộc quốc gia hoặc khu vực đã chọn.</span><span class="sxs-lookup"><span data-stu-id="b32e5-137">When [enriching profiles](#refresh-enrichment), we'll enrich all customer profiles for which we get data for the selected brands and interests, including profiles that are not in the selected country or region.</span></span> <span data-ttu-id="b32e5-138">Ví dụ: nếu bạn đã chọn Đức, chúng tôi sẽ tăng cường dữ liệu cho hồ sơ ở Hoa Kỳ nếu có sẵn dữ liệu về các thương hiệu và sở thích đã chọn ở Hoa Kỳ.</span><span class="sxs-lookup"><span data-stu-id="b32e5-138">For example, if you selected Germany, we'll enrich profiles located in the United States if we have data available for the selected brands and interests in the US.</span></span>

## <a name="configure-enrichment"></a><span data-ttu-id="b32e5-139">Định cấu hình dữ liệu tăng cường</span><span class="sxs-lookup"><span data-stu-id="b32e5-139">Configure enrichment</span></span>

<span data-ttu-id="b32e5-140">Trải nghiệm có hướng dẫn sẽ giúp bạn hoàn thành quá trình cấu hình dữ liệu tăng cường.</span><span class="sxs-lookup"><span data-stu-id="b32e5-140">A guided experience helps you through the configuration of the enrichments.</span></span> 

### <a name="define-your-brands-or-interests"></a><span data-ttu-id="b32e5-141">Xác định thương hiệu hoặc sở thích của bạn</span><span class="sxs-lookup"><span data-stu-id="b32e5-141">Define your brands or interests</span></span>

<span data-ttu-id="b32e5-142">Chọn tối đa 5 thương hiệu hoặc sở thích bằng cách sử dụng một hoặc cả hai tùy chọn sau:</span><span class="sxs-lookup"><span data-stu-id="b32e5-142">Choose up to five brands or interests using one or both of these options:</span></span>

- <span data-ttu-id="b32e5-143">**Ngành**: Chọn ngành của bạn từ danh sách thả xuống, sau đó chọn trong số các thương hiệu hoặc sở thích hàng đầu cho ngành đó.</span><span class="sxs-lookup"><span data-stu-id="b32e5-143">**Industry**: Select your industry from the dropdown list and then choose from the top brands or interests for that industry.</span></span>
- <span data-ttu-id="b32e5-144">**Tự chọn**: Nhập thương hiệu hoặc sở thích có liên quan đến tổ chức của bạn, sau đó chọn trong số các đề xuất phù hợp.</span><span class="sxs-lookup"><span data-stu-id="b32e5-144">**Choose your own**: Enter a brand or interest that is relevant to your organization and then choose from the matching suggestions.</span></span> <span data-ttu-id="b32e5-145">Nếu chúng tôi không liệt kê một thương hiệu hoặc sở thích mà bạn đang tìm kiếm, hãy gửi cho chúng tôi thông tin phản hồi bằng cách sử dụng liên kết **Đề xuất**.</span><span class="sxs-lookup"><span data-stu-id="b32e5-145">If we don't list a brand or interest you're looking for, send us feedback using the **Suggest** link.</span></span>

### <a name="review-enrichment-preferences"></a><span data-ttu-id="b32e5-146">Xem xét các tùy chọn tăng cường dữ liệu</span><span class="sxs-lookup"><span data-stu-id="b32e5-146">Review enrichment preferences</span></span>

<span data-ttu-id="b32e5-147">Xem xét các tùy chọn tăng cường dữ liệu mặc định của bạn và cập nhật chúng nếu cần.</span><span class="sxs-lookup"><span data-stu-id="b32e5-147">Review your default enrichment preferences and update them as needed.</span></span>

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Ảnh chụp màn hình của cửa sổ tùy chọn tăng cường dữ liệu.":::

### <a name="select-entity-to-enrich"></a><span data-ttu-id="b32e5-149">Chọn thực thể để tăng cường</span><span class="sxs-lookup"><span data-stu-id="b32e5-149">Select entity to enrich</span></span>

<span data-ttu-id="b32e5-150">Chọn **Thực thể được tăng cường** rồi chọn tập hợp dữ liệu mà bạn muốn bổ sung thêm dữ liệu công ty từ Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b32e5-150">Select **Enriched entity** and choose the data set you want to enrich with company data from the Microsoft.</span></span> <span data-ttu-id="b32e5-151">Bạn có thể chọn thực thể khách hàng để tăng cường dữ liệu cho tất cả hồ sơ khách hàng của bạn hoặc chọn một thực thể phân khúc để chỉ tăng cường dữ liệu cho hồ sơ khách hàng có trong phân khúc đó.</span><span class="sxs-lookup"><span data-stu-id="b32e5-151">You can select the Customer entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

### <a name="map-your-fields"></a><span data-ttu-id="b32e5-152">Ánh xạ trường của bạn</span><span class="sxs-lookup"><span data-stu-id="b32e5-152">Map your fields</span></span>

<span data-ttu-id="b32e5-153">Ánh xạ các trường từ thực thể khách hàng hợp nhất để xác định phân khúc nhân khẩu học mà bạn muốn hệ thống sử dụng để tăng cường dữ liệu khách hàng của bạn.</span><span class="sxs-lookup"><span data-stu-id="b32e5-153">Map fields from your unified customer entity to define the demographic segment you want the system to use for enriching your customer data.</span></span> <span data-ttu-id="b32e5-154">Ánh xạ Quốc gia/Khu vực và tối thiểu là thuộc tính Ngày sinh hoặc Giới tính.</span><span class="sxs-lookup"><span data-stu-id="b32e5-154">Map Country/Region and at least Date of Birth or Gender attributes.</span></span> <span data-ttu-id="b32e5-155">Ngoài ra, bạn phải ánh xạ tối thiểu là Thành phố (và Tiểu bang/Tỉnh) hoặc Mã bưu chính.</span><span class="sxs-lookup"><span data-stu-id="b32e5-155">Additionally, you must map at least one of City (and State/Province) or Postal code.</span></span> <span data-ttu-id="b32e5-156">Chọn **Chỉnh sửa** để xác định ánh xạ của các trường rồi chọn **Áp dụng** khi bạn hoàn thành.</span><span class="sxs-lookup"><span data-stu-id="b32e5-156">Select **Edit** to define the mapping of the fields and select **Apply** when you're done.</span></span> <span data-ttu-id="b32e5-157">Chọn **Lưu** để hoàn tất quá trình ánh xạ trường.</span><span class="sxs-lookup"><span data-stu-id="b32e5-157">Select **Save** to complete the field mapping.</span></span>

<span data-ttu-id="b32e5-158">Các định dạng và giá trị sau được hỗ trợ (giá trị không phân biệt chữ hoa hay chữ thường):</span><span class="sxs-lookup"><span data-stu-id="b32e5-158">The following formats and values are supported (values are not case-sensitive):</span></span>

- <span data-ttu-id="b32e5-159">**Ngày sinh**: Ngày sinh nên chuyển thành loại DateTime trong khi nhập dữ liệu.</span><span class="sxs-lookup"><span data-stu-id="b32e5-159">**Date of Birth**: We recommend that date of birth is converted to DateTime type during data ingestion.</span></span> <span data-ttu-id="b32e5-160">Ngoài ra, giá trị này có thể là một chuỗi theo định dạng của [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) là "yyyy-MM-dd" or "yyyy-MM-ddTHH:mm:ss".</span><span class="sxs-lookup"><span data-stu-id="b32e5-160">Alternatively, it can be a string in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format "yyyy-MM-dd" or "yyyy-MM-ddTHH:mm:ss".</span></span>
- <span data-ttu-id="b32e5-161">**Giới tính**: Nam, nữ, không xác định.</span><span class="sxs-lookup"><span data-stu-id="b32e5-161">**Gender**: Male, Female, Unknown.</span></span>
- <span data-ttu-id="b32e5-162">**Mã bưu chính**: Mã ZIP gồm 5 chữ số ở Hoa Kỳ hoặc mã bưu chính tiêu chuẩn ở mọi nơi khác.</span><span class="sxs-lookup"><span data-stu-id="b32e5-162">**Postal code**: Five-digit ZIP codes for United States, standard postal code everywhere else.</span></span>
- <span data-ttu-id="b32e5-163">**Thành phố**: Tên thành phố bằng tiếng Anh.</span><span class="sxs-lookup"><span data-stu-id="b32e5-163">**City**: City name in English.</span></span>
- <span data-ttu-id="b32e5-164">**Bang/Tỉnh**: Từ viết tắt gồm 2 chữ cái cho Hoa Kỳ và Canada.</span><span class="sxs-lookup"><span data-stu-id="b32e5-164">**State/Province**: Two-letter abbreviation for the US and Canada.</span></span> <span data-ttu-id="b32e5-165">Từ viết tắt gồm 2 hoặc 3 chữ cái cho Úc.</span><span class="sxs-lookup"><span data-stu-id="b32e5-165">Two- or three-letter abbreviation for Australia.</span></span> <span data-ttu-id="b32e5-166">Không áp dụng với Pháp, Đức hoặc Vương quốc Anh.</span><span class="sxs-lookup"><span data-stu-id="b32e5-166">Not applicable for France, Germany, or the UK.</span></span>
- <span data-ttu-id="b32e5-167">**Quốc gia/Khu vực**:</span><span class="sxs-lookup"><span data-stu-id="b32e5-167">**Country/Region**:</span></span>

  - <span data-ttu-id="b32e5-168">US: Hợp chủng quốc Hoa Kỳ, Hoa Kỳ, USA, US, Mỹ</span><span class="sxs-lookup"><span data-stu-id="b32e5-168">US: United States of America, United States, USA, US, America</span></span>
  - <span data-ttu-id="b32e5-169">CA: Canada, CA</span><span class="sxs-lookup"><span data-stu-id="b32e5-169">CA: Canada, CA</span></span>
  - <span data-ttu-id="b32e5-170">GB: Vương quốc Anh, UK, Great Britain, GB, Vương quốc Liên hiệp Anh và Bắc Ireland, Vương quốc Liên hiệp Anh</span><span class="sxs-lookup"><span data-stu-id="b32e5-170">GB: United Kingdom, UK, Great Britain, GB, United Kingdom of Great Britain and Northern Ireland, United Kingdom of Great Britain</span></span>
  - <span data-ttu-id="b32e5-171">AU: Úc, AU, Liên bang Úc</span><span class="sxs-lookup"><span data-stu-id="b32e5-171">AU: Australia, AU, Commonwealth of Australia</span></span>
  - <span data-ttu-id="b32e5-172">FR: Pháp, FR, Cộng hòa Pháp</span><span class="sxs-lookup"><span data-stu-id="b32e5-172">FR: France, FR, French Republic</span></span>
  - <span data-ttu-id="b32e5-173">DE: Đức, German, Deutschland, Allemagne, DE, Cộng hòa Liên bang Đức, Cộng hòa Đức</span><span class="sxs-lookup"><span data-stu-id="b32e5-173">DE: Germany, German, Deutschland, Allemagne, DE, Federal Republic of Germany, Republic of Germany</span></span>

## <a name="review-and-name-the-enrichment"></a><span data-ttu-id="b32e5-174">Xem xét và đặt tên cho dữ liệu tăng cường</span><span class="sxs-lookup"><span data-stu-id="b32e5-174">Review and name the enrichment</span></span>

<span data-ttu-id="b32e5-175">Cuối cùng, bạn phải xem xét thông tin và đặt tên cho dữ liệu tăng cường.</span><span class="sxs-lookup"><span data-stu-id="b32e5-175">Finally, you get to review the information and provide a name for the enrichment.</span></span>

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="Trang xem xét và đặt tên cho sở thích.":::

## <a name="refresh-enrichment"></a><span data-ttu-id="b32e5-177">Làm mới dữ liệu tăng cường</span><span class="sxs-lookup"><span data-stu-id="b32e5-177">Refresh enrichment</span></span>

<span data-ttu-id="b32e5-178">Chạy quá trình cung cấp dữ liệu tăng cường sau khi định cấu hình thương hiệu, sở thích và ánh xạ trường cho nhân khẩu học.</span><span class="sxs-lookup"><span data-stu-id="b32e5-178">Run the enrichment after configuring brands, interests, and the field mapping for demographics.</span></span> <span data-ttu-id="b32e5-179">Để bắt đầu quá trình, chọn **Chạy** trên trang cấu hình thương hiệu hoặc sở thích.</span><span class="sxs-lookup"><span data-stu-id="b32e5-179">To start the process, select **Run** on the brand or interest configuration page.</span></span> <span data-ttu-id="b32e5-180">Ngoài ra, bạn có thể để hệ thống tự động chạy tính năng tăng cường như một phần của việc làm mới theo lịch trình.</span><span class="sxs-lookup"><span data-stu-id="b32e5-180">Additionally, you can let the system run the enrichment automatically as part of a scheduled refresh.</span></span>

<span data-ttu-id="b32e5-181">Tùy thuộc vào kích thước dữ liệu khách hàng của bạn, có thể mất vài phút để quá trình cung cấp dữ liệu tăng cường hoàn tất.</span><span class="sxs-lookup"><span data-stu-id="b32e5-181">Depending on the size of your customer data, it may take several minutes for an enrichment run to complete.</span></span>

> [!TIP]
> <span data-ttu-id="b32e5-182">Có [6 loại trạng thái](system.md#status-types) cho các nhiệm vụ/quy trình.</span><span class="sxs-lookup"><span data-stu-id="b32e5-182">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="b32e5-183">Ngoài ra, hầu hết các quy trình [phụ thuộc vào các quy trình xuôi dòng khác](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="b32e5-183">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="b32e5-184">Bạn có thể chọn trạng thái của một quy trình để xem chi tiết về tiến trình của toàn bộ công việc.</span><span class="sxs-lookup"><span data-stu-id="b32e5-184">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="b32e5-185">Sau khi chọn **Xem chi tiết** đối với một trong các nhiệm vụ của công việc, bạn sẽ tìm thấy thông tin bổ sung như: thời gian xử lý, ngày xử lý cuối cùng và tất cả các lỗi cũng như cảnh báo liên quan đến nhiệm vụ.</span><span class="sxs-lookup"><span data-stu-id="b32e5-185">After selecting **See details** for one of the job's tasks, you'll find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="b32e5-186">Kết quả tăng cường</span><span class="sxs-lookup"><span data-stu-id="b32e5-186">Enrichment results</span></span>

<span data-ttu-id="b32e5-187">Sau khi chạy quá trình tăng cường, hãy chuyển đến **Dữ liệu tăng cường của tôi** để xem xét tổng số khách hàng được tăng cường dữ liệu và số liệu phân tích về các thương hiệu hoặc sở thích trong hồ sơ khách hàng được tăng cường dữ liệu.</span><span class="sxs-lookup"><span data-stu-id="b32e5-187">After running the enrichment process, go to **My enrichments** to review the total number of enriched customers and a breakdown of brands or interests in the enriched customer profiles.</span></span>

:::image type="content" source="media/my-enrichments.png" alt-text="Xem trước kết quả sau khi chạy quy trình tăng cường":::

<span data-ttu-id="b32e5-189">Xem xét dữ liệu tăng cường bằng cách chọn **Xem dữ liệu tăng cường** trong biểu đồ.</span><span class="sxs-lookup"><span data-stu-id="b32e5-189">Review the enriched data by selecting **View enriched data** in the chart.</span></span> <span data-ttu-id="b32e5-190">Dữ liệu tăng cường cho các thương hiệu đi đến thực thể **BrandAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="b32e5-190">Enriched data for brands goes to the **BrandAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="b32e5-191">Dữ liệu cho sở thích trong thực thể **InterestAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="b32e5-191">Data for interests is in the **InterestAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="b32e5-192">Bạn cũng sẽ tìm thấy các thực thể được liệt kê trong nhóm **Tăng cường** trong **Dữ liệu** > **Thực thể**.</span><span class="sxs-lookup"><span data-stu-id="b32e5-192">You'll also find these entities listed in the **Enrichment** group in **Data** > **Entities**.</span></span>

## <a name="see-enrichment-data-on-the-customer-card"></a><span data-ttu-id="b32e5-193">Xem dữ liệu tăng cường trên thẻ khách hàng</span><span class="sxs-lookup"><span data-stu-id="b32e5-193">See enrichment data on the customer card</span></span>

<span data-ttu-id="b32e5-194">Các mối quan hệ về thương hiệu và sở thích cũng có thể được xem trên thẻ khách hàng cá nhân.</span><span class="sxs-lookup"><span data-stu-id="b32e5-194">Brand and interest affinities can also be viewed on individual customer cards.</span></span> <span data-ttu-id="b32e5-195">Đi đến **Khách hàng** rồi chọn một hồ sơ khách hàng.</span><span class="sxs-lookup"><span data-stu-id="b32e5-195">Go to **Customers** and select a customer profile.</span></span> <span data-ttu-id="b32e5-196">Trong thẻ khách hàng, bạn sẽ tìm thấy biểu đồ cho các thương hiệu hoặc sở thích mà mọi người trong hồ sơ nhân khẩu học của khách hàng có mối quan hệ.</span><span class="sxs-lookup"><span data-stu-id="b32e5-196">In the customer card, you'll find charts for the brands or interests that people in that customer's demographic profile have affinity for.</span></span>

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Thẻ khách hàng với dữ liệu tăng cường":::

## <a name="next-steps"></a><span data-ttu-id="b32e5-198">Bước tiếp theo</span><span class="sxs-lookup"><span data-stu-id="b32e5-198">Next steps</span></span>

<span data-ttu-id="b32e5-199">Xây dựng dựa trên dữ liệu khách hàng tăng cường của bạn.</span><span class="sxs-lookup"><span data-stu-id="b32e5-199">Build on top of your enriched customer data.</span></span> <span data-ttu-id="b32e5-200">Tạo [Phân khúc](segments.md) và [Giá trị đo](measures.md), thậm chí [xuất dữ liệu](export-destinations.md) để cung cấp trải nghiệm được cá nhân hóa cho khách hàng của bạn.</span><span class="sxs-lookup"><span data-stu-id="b32e5-200">Create [Segments](segments.md) and [Measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
