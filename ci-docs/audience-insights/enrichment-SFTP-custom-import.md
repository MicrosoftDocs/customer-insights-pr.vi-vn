---
title: Tăng cường dữ liệu bằng tính năng nhập tùy chỉnh SFTP
description: Thông tin chung về tính năng nhập tùy chỉnh SFTP để tăng cường dữ liệu.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: f92b36ac5364ea8586f9cbba7ba03178641555c0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304676"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="10340-103">Tăng cường thông tin hồ sơ khách hàng bằng dữ liệu tùy chỉnh (bản xem trước)</span><span class="sxs-lookup"><span data-stu-id="10340-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="10340-104">Nhập tùy chỉnh Giao thức truyền tệp bảo mật (SFTP) cho phép bạn nhập dữ liệu mà không phải trải qua quá trình hợp nhất dữ liệu.</span><span class="sxs-lookup"><span data-stu-id="10340-104">Secure File Transfer Protocol (SFTP) custom import enables you to import data that doesn't have to go through the process of data unification.</span></span> <span data-ttu-id="10340-105">Đó là một cách linh hoạt, bảo mật và dễ dàng để đưa dữ liệu của bạn vào.</span><span class="sxs-lookup"><span data-stu-id="10340-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="10340-106">Tính năng nhập tùy chỉnh SFTP có thể được sử dụng kết hợp với [Xuất SFTP](export-sftp.md) cho phép bạn xuất dữ liệu hồ sơ khách hàng cần thiết để tăng cường.</span><span class="sxs-lookup"><span data-stu-id="10340-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="10340-107">Sau đó, dữ liệu có thể được xử lý và tăng cường, đồng thời bạn có thể sử dùng tính năng nhập tùy chỉnh SFTP để đưa dữ liệu tăng cường quay lại khả năng thông tin chi tiết về đối tượng của Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="10340-107">The data can then be processed and enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="10340-108">Điều kiện tiên quyết</span><span class="sxs-lookup"><span data-stu-id="10340-108">Prerequisites</span></span>

<span data-ttu-id="10340-109">Để định cấu hình tính năng nhập tùy chỉnh SFTP, bạn phải đáp ứng các điều kiện tiên quyết sau:</span><span class="sxs-lookup"><span data-stu-id="10340-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="10340-110">Bạn có tên tệp và vị trí (đường dẫn) của tệp sẽ được nhập trên máy chủ SFTP.</span><span class="sxs-lookup"><span data-stu-id="10340-110">You have the file name and location (path) of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="10340-111">Có một tệp *model.json* chỉ định [giản đồ Common Data Model](/common-data-model/) cho dữ liệu được nhập.</span><span class="sxs-lookup"><span data-stu-id="10340-111">There is a *model.json* file that specifies [the Common Data Model schema](/common-data-model/) for the data to be imported.</span></span> <span data-ttu-id="10340-112">Tệp này phải nằm trong cùng thư mục với tệp để nhập.</span><span class="sxs-lookup"><span data-stu-id="10340-112">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="10340-113">Một kết nối SFTP đã được quản trị viên định cấu hình *hoặc* bạn có quyền của [quản trị viên](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="10340-113">An SFTP connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="10340-114">Bạn sẽ cần thông tin xác thực của người dùng, URL và số cổng cho vị trí SFTP mà bạn muốn nhập dữ liệu từ đó.</span><span class="sxs-lookup"><span data-stu-id="10340-114">You'll need the user credentials, URL, and port number for the SFTP location where you want to import data from.</span></span>


## <a name="configure-the-import"></a><span data-ttu-id="10340-115">Định cấu hình dữ liệu nhập</span><span class="sxs-lookup"><span data-stu-id="10340-115">Configure the import</span></span>

1. <span data-ttu-id="10340-116">Đi đến **Dữ liệu** > **Tăng cường** rồi chọn tab **Khám phá**.</span><span class="sxs-lookup"><span data-stu-id="10340-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="10340-117">Trên **ngăn xếp nhập tùy chỉnh SFTP**, hãy chọn **Tăng cường dữ liệu của tôi** rồi chọn **Bắt đầu**.</span><span class="sxs-lookup"><span data-stu-id="10340-117">On the **SFTP custom import tile**, select **Enrich my data** and then select **Get started**.</span></span>

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="Ngăn xếp nhập tùy chỉnh SFTP.":::

1. <span data-ttu-id="10340-119">Chọn một [kết nối](connections.md) từ danh sách thả xuống.</span><span class="sxs-lookup"><span data-stu-id="10340-119">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="10340-120">Liên hệ với quản trị viên nếu không có kết nối.</span><span class="sxs-lookup"><span data-stu-id="10340-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="10340-121">Nếu là quản trị viên, bạn có thể tạo kết nối bằng cách chọn **Thêm kết nối** rồi chọn **Nhập tùy chỉnh SFTP** từ danh sách thả xuống.</span><span class="sxs-lookup"><span data-stu-id="10340-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **SFTP Custom Import** from the dropdown list.</span></span>

1. <span data-ttu-id="10340-122">Chọn **Kết nối với Nhập tùy chỉnh** để xác nhận kết nối đã chọn.</span><span class="sxs-lookup"><span data-stu-id="10340-122">Select **Connect to Custom Import** to confirm the selected connection.</span></span>

1.  <span data-ttu-id="10340-123">Chọn **Tiếp** và nhập **Đường dẫn** và **Tên tệp** của tệp dữ liệu mà bạn muốn nhập.</span><span class="sxs-lookup"><span data-stu-id="10340-123">Select **Next** and enter the **Path** and **Filename** of the data file that you want to import.</span></span>

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="Ảnh chụp màn hình khi nhập vị trí dữ liệu.":::

1. <span data-ttu-id="10340-125">Chọn **Tiếp** rồi đặt tên cho dữ liệu tăng cường và tên cho thực thể đầu ra.</span><span class="sxs-lookup"><span data-stu-id="10340-125">Select **Next** and provide a name for the enrichment and a name for the output entity.</span></span> 

1. <span data-ttu-id="10340-126">Chọn **Lưu dữ liệu tăng cường** sau khi xem xét các lựa chọn của bạn.</span><span class="sxs-lookup"><span data-stu-id="10340-126">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-sftp-custom-import"></a><span data-ttu-id="10340-127">Định cấu hình kết nối cho Nhập tùy chỉnh SFTP</span><span class="sxs-lookup"><span data-stu-id="10340-127">Configure the connection for SFTP Custom Import</span></span> 

<span data-ttu-id="10340-128">Bạn cần phải là quản trị viên thì mới có thể định cấu hình kết nối.</span><span class="sxs-lookup"><span data-stu-id="10340-128">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="10340-129">Chọn **Thêm kết nối** khi định cấu hình dữ liệu tăng cường *hoặc* đi đến **Quản trị viên** > **Kết nối** rồi chọn **Thiết lập** trên ngăn xếp Nhập tùy chỉnh.</span><span class="sxs-lookup"><span data-stu-id="10340-129">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Custom Import tile.</span></span>

1. <span data-ttu-id="10340-130">Nhập tên cho kết nối trong hộp **Tên hiển thị**.</span><span class="sxs-lookup"><span data-stu-id="10340-130">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="10340-131">Nhập tên người dùng, mật khẩu và URL máy chủ hợp lệ cho máy chủ SFTP chứa dữ liệu được nhập.</span><span class="sxs-lookup"><span data-stu-id="10340-131">Enter a valid username, password, and host URL for the SFTP server that the data to be imported resides on.</span></span>

1. <span data-ttu-id="10340-132">Xem xét và đồng ý với **Quyền riêng tư và tuân thủ dữ liệu** bằng cách đánh dấu ô **Tôi đồng ý**.</span><span class="sxs-lookup"><span data-stu-id="10340-132">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="10340-133">Chọn **Xác minh** để xác thực cấu hình.</span><span class="sxs-lookup"><span data-stu-id="10340-133">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="10340-134">Sau khi quá trình xác minh hoàn tất, bạn có thể lưu kết nối bằng cách chọn **Lưu**.</span><span class="sxs-lookup"><span data-stu-id="10340-134">Once the verification has completed, the connection can be saved by selecting **Save**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="10340-135">![Trang cấu hình kết nối Experian](media/enrichment-SFTP-connection.png "Trang cấu hình kết nối Experian")</span><span class="sxs-lookup"><span data-stu-id="10340-135">![Experian connection configuration page](media/enrichment-SFTP-connection.png "Experian connection configuration page")</span></span>


## <a name="defining-field-mappings"></a><span data-ttu-id="10340-136">Đang xác định ánh xạ trường</span><span class="sxs-lookup"><span data-stu-id="10340-136">Defining field mappings</span></span> 

<span data-ttu-id="10340-137">Thư mục chứa tệp sẽ được nhập trên máy chủ SFTP cũng phải chứa tệp *model.json*.</span><span class="sxs-lookup"><span data-stu-id="10340-137">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="10340-138">Tệp này xác định lược đồ sẽ sử dụng để nhập dữ liệu.</span><span class="sxs-lookup"><span data-stu-id="10340-138">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="10340-139">Lược đồ phải sử dụng [Common Data Model](/common-data-model/) để chỉ định ánh xạ trường.</span><span class="sxs-lookup"><span data-stu-id="10340-139">The schema has to use [Common Data Model](/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="10340-140">Một ví dụ đơn giản về tệp model.json trông như sau:</span><span class="sxs-lookup"><span data-stu-id="10340-140">A simple example of a model.json file looks like this:</span></span>

```
{
    "name": "EnrichmentFromMicrosoft",
    "description": "Model containing data enrichment",
    "entities": [
        {
            "name": "CustomImport",
            "attributes": [
                {
                    "name": "CustomerId",
                    "friendlyName": "Client id",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred City for vacation",
                    "dataType": "string"
                },
                {
                    "name": "PreferredTransportation",
                    "friendlyName": "Preferred transportation",
                    "dataType": "string"
                }
            ],
            "annotations": [
                {
                    "name": "c360:PrimaryKey",
                    "value": "CustomerId"
                }
            ]
        }
    ],
    "modifiedTime": "2020-01-02T12:00:00+08:00",
    "annotations": [
        {
            "name": "testAnnotation",
            "value": "testValue"
        }
    ]
}
```

## <a name="enrichment-results"></a><span data-ttu-id="10340-141">Kết quả tăng cường</span><span class="sxs-lookup"><span data-stu-id="10340-141">Enrichment results</span></span>

<span data-ttu-id="10340-142">Để bắt đầu quá trình tăng cường, hãy chọn **Chạy** từ thanh lệnh.</span><span class="sxs-lookup"><span data-stu-id="10340-142">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="10340-143">Bạn cũng có thể để hệ thống chạy quá trình tăng cường tự động như một phần của [làm mới theo lịch trình](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="10340-143">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="10340-144">Thời gian xử lý sẽ phụ thuộc vào kích thước của dữ liệu được nhập và kết nối với máy chủ SFTP.</span><span class="sxs-lookup"><span data-stu-id="10340-144">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="10340-145">Sau khi quá trình tăng cường hoàn tất, bạn có thể xem xét dữ liệu bổ sung tùy chỉnh mới được nhập của mình trong **Dữ liệu tăng cường của tôi**.</span><span class="sxs-lookup"><span data-stu-id="10340-145">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="10340-146">Ngoài ra, bạn sẽ tìm thấy thời gian của lần cập nhật gần nhất và số lượng hồ sơ được tăng cường.</span><span class="sxs-lookup"><span data-stu-id="10340-146">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="10340-147">Bạn có thể truy cập dạng xem chi tiết của từng hồ sơ được tăng cường dữ liệu bằng cách chọn **Xem dữ liệu tăng cường**.</span><span class="sxs-lookup"><span data-stu-id="10340-147">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="10340-148">Các bước tiếp theo</span><span class="sxs-lookup"><span data-stu-id="10340-148">Next steps</span></span>

<span data-ttu-id="10340-149">Xây dựng dựa trên dữ liệu khách hàng tăng cường của bạn.</span><span class="sxs-lookup"><span data-stu-id="10340-149">Build on top of your enriched customer data.</span></span> <span data-ttu-id="10340-150">Tạo [phân khúc](segments.md) và [giá trị đo](measures.md), cũng như [xuất dữ liệu](export-destinations.md) để cung cấp trải nghiệm được cá nhân hóa cho khách hàng của bạn.</span><span class="sxs-lookup"><span data-stu-id="10340-150">Create [segments](segments.md) and [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
