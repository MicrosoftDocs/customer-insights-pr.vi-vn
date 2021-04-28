---
title: Bổ sung dữ liệu từ Microsoft cho hồ sơ khách hàng
description: Sử dụng dữ liệu độc quyền từ Microsoft để bổ sung các mối quan hệ về sở thích và thương hiệu cho dữ liệu khách hàng của bạn.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 6f19033236190547f68d2b91ec6b32074bf7912a
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896628"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a><span data-ttu-id="2ee4a-103">Làm phong phú hồ sơ khách hàng với mối quan hệ thương hiệu và sở thích (xem trước)</span><span class="sxs-lookup"><span data-stu-id="2ee4a-103">Enrich customer profiles with brand and interest affinities (preview)</span></span>

<span data-ttu-id="2ee4a-104">Sử dụng dữ liệu độc quyền của Microsoft để bổ sung các mối quan hệ về sở thích và thương hiệu cho dữ liệu khách hàng của bạn.</span><span class="sxs-lookup"><span data-stu-id="2ee4a-104">Use Microsoft's proprietary data to enrich your customer data with brand and interest affinities.</span></span> <span data-ttu-id="2ee4a-105">Những mối quan hệ này được xác định dựa trên dữ liệu từ những người có nhân khẩu học tương tự với khách hàng của bạn.</span><span class="sxs-lookup"><span data-stu-id="2ee4a-105">These affinities are determined based on data from people with similar demographics to your customers.</span></span> <span data-ttu-id="2ee4a-106">Thông tin này giúp bạn hiểu rõ hơn và phân khúc khách hàng của bạn dựa trên mối quan hệ của họ với các nhãn hiệu và sở thích cụ thể.</span><span class="sxs-lookup"><span data-stu-id="2ee4a-106">This information helps you to better understand and segment your customers based on their affinities to specific brands and interests.</span></span>

<span data-ttu-id="2ee4a-107">Trong thông tin chi tiết về đối tượng, hãy đi tới **Dữ liệu** > **Làm phong phú** để [định cấu hình và xem các chức năng làm phong phú](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="2ee4a-107">In audience insights, go to **Data** > **Enrichment** to [configure and view enrichments](enrichment-hub.md).</span></span>

<span data-ttu-id="2ee4a-108">Để đặt cấu hình nội dung phong phú phụ cho thương hiệu, hãy chuyển đến tab **Khám phá** và chọn **Làm phong phú dữ liệu của tôi** trên ngăn xếp **Thương hiệu**.</span><span class="sxs-lookup"><span data-stu-id="2ee4a-108">To configure brand affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Brands** tile.</span></span>

<span data-ttu-id="2ee4a-109">Để đặt cấu hình nội dung phong phú phụ cho sở thích, hãy chuyển đến tab **Khám phá** rồi chọn **Làm phong phú dữ liệu của tôi** trên ngăn xếp **Sở thích**.</span><span class="sxs-lookup"><span data-stu-id="2ee4a-109">To configure interest affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Interests** tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2ee4a-110">![Ngăn xếp Thương hiệu & Sở thích](media/BrandsInterest-tile-Hub.png "Ngăn xếp Thương hiệu & Sở thích")</span><span class="sxs-lookup"><span data-stu-id="2ee4a-110">![Brands & Interests tiles](media/BrandsInterest-tile-Hub.png "Brands & Interest tiles")</span></span>

## <a name="how-we-determine-affinities"></a><span data-ttu-id="2ee4a-111">Cách chúng tôi xác định mối quan hệ</span><span class="sxs-lookup"><span data-stu-id="2ee4a-111">How we determine affinities</span></span>

<span data-ttu-id="2ee4a-112">Chúng tôi sử dụng dữ liệu tìm kiếm trực tuyến của Microsoft để tìm mối quan hệ cho thương hiệu và sở thích trên các phân khúc nhân khẩu học khác nhau (được xác định theo độ tuổi, giới tính hoặc vị trí).</span><span class="sxs-lookup"><span data-stu-id="2ee4a-112">We use Microsoft’s online search data to find affinities for brands and interests across various demographic segments (defined by age, gender, or location).</span></span> <span data-ttu-id="2ee4a-113">Khối lượng tìm kiếm trực tuyến cho một thương hiệu hoặc sở thích xác định mức độ quan hệ của một phân khúc nhân khẩu học, so với các phân khúc khác, đối với thương hiệu hoặc sở thích đó.</span><span class="sxs-lookup"><span data-stu-id="2ee4a-113">The online search volume for a brand or interest determines how much affinity a demographic segment, compared to other segments, has to that brand or interest.</span></span> <span data-ttu-id="2ee4a-114">thương hiệu hoặc sở thích.</span><span class="sxs-lookup"><span data-stu-id="2ee4a-114">brand or interest.</span></span>

## <a name="affinity-level-and-score"></a><span data-ttu-id="2ee4a-115">Mức độ sở thích và điểm số</span><span class="sxs-lookup"><span data-stu-id="2ee4a-115">Affinity level and score</span></span>

<span data-ttu-id="2ee4a-116">Trên mỗi hồ sơ khách hàng được làm phong phú, chúng tôi cung cấp hai giá trị liên quan - mức độ sở thích và điểm số sở thích.</span><span class="sxs-lookup"><span data-stu-id="2ee4a-116">On every enriched customer profile, we provide two related values – affinity level and affinity score.</span></span> <span data-ttu-id="2ee4a-117">Những giá trị này giúp bạn xác định mức độ quan tâm đối với phân đoạn nhân khẩu học của hồ sơ đó, đối với thương hiệu hoặc sở thích so với các phân đoạn nhân khẩu học khác.</span><span class="sxs-lookup"><span data-stu-id="2ee4a-117">These values help you determine how strong the affinity is for that profile’s demographic segment, for a brand or interest, as compared to other demographic segments.</span></span>

<span data-ttu-id="2ee4a-118">*Mức độ sở thích* bao gồm bốn cấp độ và *điểm sở thích* được tính toán trên thang điểm 100 ánh xạ tới các mức độ sở thích.</span><span class="sxs-lookup"><span data-stu-id="2ee4a-118">*Affinity level* consists of four levels and *affinity score* is calculated on a 100-point scale that maps to the affinity levels.</span></span>


|<span data-ttu-id="2ee4a-119">Mức độ sở thích</span><span class="sxs-lookup"><span data-stu-id="2ee4a-119">Affinity level</span></span> |<span data-ttu-id="2ee4a-120">Điểm mối quan hệ</span><span class="sxs-lookup"><span data-stu-id="2ee4a-120">Affinity score</span></span>  |
|---------|---------|
|<span data-ttu-id="2ee4a-121">Rất cao</span><span class="sxs-lookup"><span data-stu-id="2ee4a-121">Very high</span></span>     | <span data-ttu-id="2ee4a-122">85-100</span><span class="sxs-lookup"><span data-stu-id="2ee4a-122">85-100</span></span>       |
|<span data-ttu-id="2ee4a-123">Cao</span><span class="sxs-lookup"><span data-stu-id="2ee4a-123">High</span></span>     | <span data-ttu-id="2ee4a-124">70-84</span><span class="sxs-lookup"><span data-stu-id="2ee4a-124">70-84</span></span>        |
|<span data-ttu-id="2ee4a-125">Trung bình</span><span class="sxs-lookup"><span data-stu-id="2ee4a-125">Medium</span></span>     | <span data-ttu-id="2ee4a-126">35-69</span><span class="sxs-lookup"><span data-stu-id="2ee4a-126">35-69</span></span>        |
|<span data-ttu-id="2ee4a-127">Thấp</span><span class="sxs-lookup"><span data-stu-id="2ee4a-127">Low</span></span>     | <span data-ttu-id="2ee4a-128">1-34</span><span class="sxs-lookup"><span data-stu-id="2ee4a-128">1-34</span></span>        |

<span data-ttu-id="2ee4a-129">Tùy thuộc vào mức độ chi tiết mà bạn muốn đo lường sở thích, bạn có thể sử dụng mức độ hoặc điểm số sở thích.</span><span class="sxs-lookup"><span data-stu-id="2ee4a-129">Depending on the granularity you would like for measuring the affinity, you can use either affinity level or score.</span></span> <span data-ttu-id="2ee4a-130">Điểm số sở thích giúp bạn kiểm soát chính xác hơn.</span><span class="sxs-lookup"><span data-stu-id="2ee4a-130">Affinity score gives you more precise control.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="2ee4a-131">Khu vực/vùng lãnh thổ được hỗ trợ</span><span class="sxs-lookup"><span data-stu-id="2ee4a-131">Supported countries/regions</span></span>

<span data-ttu-id="2ee4a-132">Chúng tôi hiện hỗ trợ các tùy chọn quốc gia/vùng sau đây: Úc, Canada (Tiếng Anh), Pháp, Đức, Vương quốc Anh hoặc Hoa Kỳ (Tiếng Anh).</span><span class="sxs-lookup"><span data-stu-id="2ee4a-132">We currently support the following country/region options: Australia, Canada (English), France, Germany, United Kingdom, or United States (English).</span></span>

<span data-ttu-id="2ee4a-133">Để chọn quốc gia, hãy mở trình đơn **Làm phong phú thương hiệu** hoặc **Làm phong phú sở thích** rồi chọn **Thay đổi** bên cạnh **Quốc gia/Vùng lãnh thổ**.</span><span class="sxs-lookup"><span data-stu-id="2ee4a-133">To select a country, open the **Brands enrichment** or **Interest enrichment** and select **Change** next to **Country/Region**.</span></span> <span data-ttu-id="2ee4a-134">Trong ngăn **Thiết đặt quốc gia/vùng lãnh thổ**, chọn một tùy chọn rồi chọn **Áp dụng**.</span><span class="sxs-lookup"><span data-stu-id="2ee4a-134">In the **Country/Region settings** pane, choose an option and select **Apply**.</span></span>

### <a name="implications-related-to-country-selection"></a><span data-ttu-id="2ee4a-135">Ý nghĩa liên quan đến chọn quốc gia</span><span class="sxs-lookup"><span data-stu-id="2ee4a-135">Implications related to country selection</span></span>

- <span data-ttu-id="2ee4a-136">Khi [chọn thương hiệu của riêng bạn](#define-your-brands-or-interests), hệ thống cung cấp các đề xuất dựa trên quốc gia hoặc khu vực đã chọn.</span><span class="sxs-lookup"><span data-stu-id="2ee4a-136">When [choosing your own brands](#define-your-brands-or-interests), the system provides suggestions based on the selected country or region.</span></span>

- <span data-ttu-id="2ee4a-137">Khi [chọn một ngành](#define-your-brands-or-interests), bạn sẽ nhận được các thương hiệu hoặc sở thích phù hợp nhất dựa trên quốc gia hoặc khu vực đã chọn.</span><span class="sxs-lookup"><span data-stu-id="2ee4a-137">When [choosing an industry](#define-your-brands-or-interests), you'll get the most relevant brands or interests based on the selected country or region.</span></span>

- <span data-ttu-id="2ee4a-138">Khi [làm phong phú hồ sơ](#refresh-enrichment), chúng tôi sẽ làm phong phú thêm tất cả các hồ sơ khách hàng mà chúng tôi lấy dữ liệu cho các thương hiệu và sở thích đã chọn.</span><span class="sxs-lookup"><span data-stu-id="2ee4a-138">When [enriching profiles](#refresh-enrichment), we'll enrich all customer profiles for which we get data for the selected brands and interests.</span></span> <span data-ttu-id="2ee4a-139">Bao gồm các hồ sơ không thuộc quốc gia hoặc khu vực đã chọn.</span><span class="sxs-lookup"><span data-stu-id="2ee4a-139">Including profiles that are not in the selected country or region.</span></span> <span data-ttu-id="2ee4a-140">Ví dụ: nếu bạn đã chọn Đức, chúng tôi sẽ bổ sung dữ liệu cho hồ sơ ở Hoa Kỳ nếu chúng tôi có sẵn dữ liệu về các thương hiệu và sở thích đã chọn ở Hoa Kỳ.</span><span class="sxs-lookup"><span data-stu-id="2ee4a-140">For example, if you selected Germany, we'll enrich profiles located in the United States if we have data available for the selected brands and interests in the US.</span></span>

## <a name="configure-enrichment"></a><span data-ttu-id="2ee4a-141">Cấu hình làm phong phú</span><span class="sxs-lookup"><span data-stu-id="2ee4a-141">Configure Enrichment</span></span>

<span data-ttu-id="2ee4a-142">Trải nghiệm có hướng dẫn sẽ giúp bạn hoàn thành quá trình cấu hình nội dung bổ sung.</span><span class="sxs-lookup"><span data-stu-id="2ee4a-142">A guided experience helps you through the configuration of the enrichments.</span></span> 

### <a name="define-your-brands-or-interests"></a><span data-ttu-id="2ee4a-143">Xác định thương hiệu hoặc sở thích của bạn</span><span class="sxs-lookup"><span data-stu-id="2ee4a-143">Define your brands or interests</span></span>

<span data-ttu-id="2ee4a-144">Chọn một trong các tùy chọn sau:</span><span class="sxs-lookup"><span data-stu-id="2ee4a-144">Select one of the following options:</span></span>

- <span data-ttu-id="2ee4a-145">**Ngành**: Hệ thống xác định thương hiệu hoặc sở thích hàng đầu liên quan đến ngành của bạn và làm phong phú dữ liệu khách hàng với họ.</span><span class="sxs-lookup"><span data-stu-id="2ee4a-145">**Industry**: The system identifies the top brands or interests relevant to your industry and enriches your customer data with them.</span></span>
- <span data-ttu-id="2ee4a-146">**Chọn tùy chọn của riêng bạn**: Chọn tối đa 5 mục từ danh sách các thương hiệu hoặc sở thích phù hợp nhất với tổ chức của bạn.</span><span class="sxs-lookup"><span data-stu-id="2ee4a-146">**Choose your own**: Select up to five items from the list of brands or interests that are most relevant to your organization.</span></span>

<span data-ttu-id="2ee4a-147">Để thêm thương hiệu hoặc sở thích, hãy nhập dữ liệu liệu vào khu vực đầu vào để nhận đề xuất dựa trên các điều khoản phù hợp.</span><span class="sxs-lookup"><span data-stu-id="2ee4a-147">To add a brand or interest, enter it in the input area to get suggestions based on matching terms.</span></span> <span data-ttu-id="2ee4a-148">Nếu chúng tôi không liệt kê một thương hiệu hoặc sở thích mà bạn đang tìm kiếm, hãy gửi cho chúng tôi thông tin phản hồi bằng cách sử dụng liên kết **Đề xuất**.</span><span class="sxs-lookup"><span data-stu-id="2ee4a-148">If we don't list a brand or interest you're looking for, send us feedback using the **Suggest** link.</span></span>

### <a name="review-enrichment-preferences"></a><span data-ttu-id="2ee4a-149">Xem xét các tùy chọn làm phong phú</span><span class="sxs-lookup"><span data-stu-id="2ee4a-149">Review enrichment preferences</span></span>

<span data-ttu-id="2ee4a-150">Xem lại các tùy chọn làm phong phú mặc định của bạn và cập nhật chúng nếu cần.</span><span class="sxs-lookup"><span data-stu-id="2ee4a-150">Review your default enrichment preferences and update them as needed.</span></span>

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Ảnh chụp màn hình của cửa sổ tùy chọn làm phong phú.":::

### <a name="select-entity-to-enrich"></a><span data-ttu-id="2ee4a-152">Chọn thực thể để làm phong phú</span><span class="sxs-lookup"><span data-stu-id="2ee4a-152">Select entity to enrich</span></span>

<span data-ttu-id="2ee4a-153">Chọn **Thực thể được bổ sung** rồi chọn tập hợp dữ liệu mà bạn muốn bổ sung thêm dữ liệu công ty từ Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2ee4a-153">Select **Enriched entity** and choose the data set you want to enrich with company data from the Microsoft.</span></span> <span data-ttu-id="2ee4a-154">Bạn có thể chọn thực thể khách hàng để làm phong phú tất cả hồ sơ khách hàng của bạn hoặc chọn một thực thể phân khúc để chỉ làm phong phú thêm hồ sơ khách hàng có trong phân khúc đó.</span><span class="sxs-lookup"><span data-stu-id="2ee4a-154">You can select the Customer entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

### <a name="map-your-fields"></a><span data-ttu-id="2ee4a-155">Ánh xạ trường của bạn</span><span class="sxs-lookup"><span data-stu-id="2ee4a-155">Map your fields</span></span>

<span data-ttu-id="2ee4a-156">Ánh xạ các trường từ thực thể khách hàng hợp nhất để xác định phân đoạn nhân khẩu học mà bạn muốn hệ thống sử dụng để làm phong phú dữ liệu khách hàng của bạn.</span><span class="sxs-lookup"><span data-stu-id="2ee4a-156">Map fields from your unified customer entity to define the demographic segment you want the system to use for enriching your customer data.</span></span> <span data-ttu-id="2ee4a-157">Ánh xạ Quốc gia/Khu vực và tối thiểu là thuộc tính Ngày sinh hoặc Giới tính.</span><span class="sxs-lookup"><span data-stu-id="2ee4a-157">Map Country/Region and at least Date of Birth or Gender attributes.</span></span> <span data-ttu-id="2ee4a-158">Ngoài ra, bạn phải ánh xạ tối thiểu là Thành phố (và Tiểu bang/Tỉnh) hoặc Mã bưu chính.</span><span class="sxs-lookup"><span data-stu-id="2ee4a-158">Additionally, you must map at least one of City (and State/Province) or Postal code.</span></span> <span data-ttu-id="2ee4a-159">Chọn **Chỉnh sửa** để xác định ánh xạ của các trường và chọn **Áp dụng** khi bạn hoàn thành.</span><span class="sxs-lookup"><span data-stu-id="2ee4a-159">Select **Edit** to define the mapping of the fields and select **Apply** when you're done.</span></span> <span data-ttu-id="2ee4a-160">Chọn **Lưu** để hoàn tất quá trình ánh xạ trường.</span><span class="sxs-lookup"><span data-stu-id="2ee4a-160">Select **Save** to complete the field mapping.</span></span>

<span data-ttu-id="2ee4a-161">Các định dạng và giá trị sau được hỗ trợ, giá trị không phân biệt chữ hoa chữ thường:</span><span class="sxs-lookup"><span data-stu-id="2ee4a-161">The following formats and values are supported, values are not case-sensitive:</span></span>

- <span data-ttu-id="2ee4a-162">**Ngày sinh**: Ngày sinh nên chuyển thành loại DateTime trong khi nhập dữ liệu.</span><span class="sxs-lookup"><span data-stu-id="2ee4a-162">**Date of Birth**: We recommend that date of birth is converted to DateTime type during data ingestion.</span></span> <span data-ttu-id="2ee4a-163">Ngoài ra, ngày sinh có thể là chuỗi ở định dạng [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) "yyyy-MM-dd" hoặc "yyyy-MM-ddTHH:mm:ssZ".</span><span class="sxs-lookup"><span data-stu-id="2ee4a-163">Alternatively, it can be a string in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format "yyyy-MM-dd" or "yyyy-MM-ddTHH:mm:ssZ".</span></span>
- <span data-ttu-id="2ee4a-164">**Giới tính**: Nam, nữ, không rõ</span><span class="sxs-lookup"><span data-stu-id="2ee4a-164">**Gender**: Male, Female, Unknown</span></span>
- <span data-ttu-id="2ee4a-165">**Mã bưu chính**: Mã ZIP năm chữ số cho Hoa Kỳ, mã bưu chính tiêu chuẩn ở mọi nơi khác</span><span class="sxs-lookup"><span data-stu-id="2ee4a-165">**Postal code**: Five-digit ZIP Codes for US, standard postal code everywhere else</span></span>
- <span data-ttu-id="2ee4a-166">**Thành phố**: Tên thành phố bằng Tiếng Anh</span><span class="sxs-lookup"><span data-stu-id="2ee4a-166">**City**: City name in English</span></span>
- <span data-ttu-id="2ee4a-167">**Bang/Tỉnh**: Từ viết tắt 2 chữ cái của Hoa Kỳ và Canada.</span><span class="sxs-lookup"><span data-stu-id="2ee4a-167">**State/Province**: Two-letter abbreviation for the US and Canada.</span></span> <span data-ttu-id="2ee4a-168">Từ viết tắt 2 hoặc 3 chữ cái cho Úc.</span><span class="sxs-lookup"><span data-stu-id="2ee4a-168">Two or three letter abbreviation for Australia.</span></span> <span data-ttu-id="2ee4a-169">Không áp dụng với Pháp, Đức hoặc Vương quốc Anh.</span><span class="sxs-lookup"><span data-stu-id="2ee4a-169">Not applicable for France, Germany, or the UK.</span></span>
- <span data-ttu-id="2ee4a-170">**Quốc gia/Vùng lãnh thổ**:</span><span class="sxs-lookup"><span data-stu-id="2ee4a-170">**Country/Region**:</span></span>

  - <span data-ttu-id="2ee4a-171">US: Hợp chủng quốc Hoa Kỳ, Hoa Kỳ, USA, US, Mỹ</span><span class="sxs-lookup"><span data-stu-id="2ee4a-171">US: United States of America, United States, USA, US, America</span></span>
  - <span data-ttu-id="2ee4a-172">CA: Canada, CA</span><span class="sxs-lookup"><span data-stu-id="2ee4a-172">CA: Canada, CA</span></span>
  - <span data-ttu-id="2ee4a-173">GB: Vương quốc Anh, UK, Great Britain, GB, Vương quốc Liên hiệp Anh và Bắc Ireland, Vương quốc Liên hiệp Anh</span><span class="sxs-lookup"><span data-stu-id="2ee4a-173">GB: United Kingdom, UK, Great Britain, GB, United Kingdom of Great Britain and Northern Ireland, United Kingdom of Great Britain</span></span>
  - <span data-ttu-id="2ee4a-174">AU: Úc, AU, Liên bang Australia</span><span class="sxs-lookup"><span data-stu-id="2ee4a-174">AU: Australia, AU, Common Wealth of Australia</span></span>
  - <span data-ttu-id="2ee4a-175">FR: Pháp, FR, Cộng hòa Pháp</span><span class="sxs-lookup"><span data-stu-id="2ee4a-175">FR: France, FR, French Republic</span></span>
  - <span data-ttu-id="2ee4a-176">DE: Đức, German, Deutschland, Allemagne, DE, Cộng hòa Liên bang Đức, Cộng hòa Đức</span><span class="sxs-lookup"><span data-stu-id="2ee4a-176">DE: Germany, German, Deutschland, Allemagne, DE, Federal Republic of Germany, Republic of Germany</span></span>

## <a name="review-and-name-the-enrichment"></a><span data-ttu-id="2ee4a-177">Xem lại và đặt tên cho nội dung bổ sung</span><span class="sxs-lookup"><span data-stu-id="2ee4a-177">Review and name the enrichment</span></span>

<span data-ttu-id="2ee4a-178">Cuối cùng, bạn phải xem lại thông tin và đặt tên cho nội dung bổ sung.</span><span class="sxs-lookup"><span data-stu-id="2ee4a-178">Finally, you get to review the information and provide a name for the enrichment.</span></span>

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="Trang xem lại và đặt tên cho sở thích.":::

## <a name="refresh-enrichment"></a><span data-ttu-id="2ee4a-180">Làm mới nội dung phong phú</span><span class="sxs-lookup"><span data-stu-id="2ee4a-180">Refresh enrichment</span></span>

<span data-ttu-id="2ee4a-181">Chạy quá trình cung cấp thông tin phong phú sau khi đặt cấu hình thương hiệu, sở thích và ánh xạ trường cho nhân khẩu học.</span><span class="sxs-lookup"><span data-stu-id="2ee4a-181">Run the enrichment after configuring brands, interests, and the field mapping for demographics.</span></span> <span data-ttu-id="2ee4a-182">Để bắt đầu quá trình, chọn **Chạy** trên trang cấu hình thương hiệu hoặc sở thích.</span><span class="sxs-lookup"><span data-stu-id="2ee4a-182">To start the process, select **Run** on the brand or interest configuration page.</span></span> <span data-ttu-id="2ee4a-183">Ngoài ra, bạn có thể để hệ thống tự động chạy làm phong phú như một phần của việc làm mới theo lịch trình.</span><span class="sxs-lookup"><span data-stu-id="2ee4a-183">Additionally, you can let the system run the enrichment automatically as part of a scheduled refresh.</span></span>
<span data-ttu-id="2ee4a-184">Tùy thuộc vào kích thước dữ liệu khách hàng của bạn, có thể mất vài phút để quá trình cung cấp thông tin phong phú hoàn tất.</span><span class="sxs-lookup"><span data-stu-id="2ee4a-184">Depending on the size of your customer data, it may take several minutes for an enrichment run to complete.</span></span>

> [!TIP]
> <span data-ttu-id="2ee4a-185">Có [6 loại trạng thái](system.md#status-types) cho các nhiệm vụ/quy trình.</span><span class="sxs-lookup"><span data-stu-id="2ee4a-185">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="2ee4a-186">Ngoài ra, hầu hết các quy trình [phụ thuộc vào các quá trình hạ nguồn khác](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="2ee4a-186">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="2ee4a-187">Bạn có thể chọn trạng thái của một quy trình để xem chi tiết về tiến trình của toàn bộ công việc.</span><span class="sxs-lookup"><span data-stu-id="2ee4a-187">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="2ee4a-188">Sau khi chọn **Xem chi tiết** đối với một trong các tác vụ của công việc, bạn sẽ tìm thấy thông tin bổ sung: thời gian xử lý, ngày xử lý gần nhất và tất cả các lỗi và cảnh báo liên quan đến tác vụ.</span><span class="sxs-lookup"><span data-stu-id="2ee4a-188">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="2ee4a-189">Kết quả làm phong phú</span><span class="sxs-lookup"><span data-stu-id="2ee4a-189">Enrichment results</span></span>

<span data-ttu-id="2ee4a-190">Sau khi chạy quá trình làm phong phú, hãy chuyển đến **Nội dung phong phú của tôi** để xem lại tổng số khách hàng làm phong phú và số liệu phân tích về các thương hiệu hoặc sở thích trong hồ sơ khách hàng được làm phong phú.</span><span class="sxs-lookup"><span data-stu-id="2ee4a-190">After running the enrichment process, go to **My enrichments** to review the total number of enriched customers and a breakdown of brands or interests in the enriched customer profiles.</span></span>

:::image type="content" source="media/my-enrichments.png" alt-text="Xem trước kết quả sau khi chạy quy trình làm phong phú":::

<span data-ttu-id="2ee4a-192">Xem lại dữ liệu được làm phong phú bằng cách chọn **Xem dữ liệu phong phú** trong biểu đồ.</span><span class="sxs-lookup"><span data-stu-id="2ee4a-192">Review the enriched data by selecting **View enriched data** in the chart.</span></span> <span data-ttu-id="2ee4a-193">Dữ liệu phong phú cho các thương hiệu đi đến thực thể **BrandAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="2ee4a-193">Enriched data for brands goes to the **BrandAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="2ee4a-194">Dữ liệu cho sở thích trong thực thể **InterestAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="2ee4a-194">Data for interests is in the **InterestAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="2ee4a-195">Bạn cũng sẽ tìm thấy các thực thể được liệt kê trong nhóm **Làm phong phú** trong **Dữ liệu** > **Các thực thể**.</span><span class="sxs-lookup"><span data-stu-id="2ee4a-195">You'll also find these entities listed in the **Enrichment** group in **Data** > **Entities**.</span></span>

## <a name="see-enrichment-data-on-the-customer-card"></a><span data-ttu-id="2ee4a-196">Xem dữ liệu làm phong phú trên thẻ khách hàng</span><span class="sxs-lookup"><span data-stu-id="2ee4a-196">See enrichment data on the customer card</span></span>

<span data-ttu-id="2ee4a-197">Các mối quan hệ thương hiệu và lợi ích cũng có thể được xem trên thẻ khách hàng cá nhân.</span><span class="sxs-lookup"><span data-stu-id="2ee4a-197">Brand and interest affinities can also be viewed on individual customer cards.</span></span> <span data-ttu-id="2ee4a-198">Đi đến **Khách hàng** và chọn một hồ sơ khách hàng.</span><span class="sxs-lookup"><span data-stu-id="2ee4a-198">Go to **Customers** and select a customer profile.</span></span> <span data-ttu-id="2ee4a-199">Trong thẻ khách hàng, bạn sẽ tìm thấy biểu đồ cho các thương hiệu hoặc sở thích mà mọi người trong hồ sơ nhân khẩu học của khách hàng có ái lực.</span><span class="sxs-lookup"><span data-stu-id="2ee4a-199">In the customer card, you'll find charts for the brands or interests that people in that customer's demographic profile have affinity for.</span></span>

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Thẻ khách hàng với dữ liệu phong phú":::

## <a name="next-steps"></a><span data-ttu-id="2ee4a-201">Bước tiếp theo</span><span class="sxs-lookup"><span data-stu-id="2ee4a-201">Next steps</span></span>

<span data-ttu-id="2ee4a-202">Xây dựng dựa trên dữ liệu khách hàng phong phú của bạn.</span><span class="sxs-lookup"><span data-stu-id="2ee4a-202">Build on top of your enriched customer data.</span></span> <span data-ttu-id="2ee4a-203">Tạo [Phân khúc](segments.md), [Biện pháp](measures.md) và [xuất dữ liệu](export-destinations.md) để cung cấp trải nghiệm cá nhân cho khách hàng của bạn.</span><span class="sxs-lookup"><span data-stu-id="2ee4a-203">Create [Segments](segments.md), [Measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
