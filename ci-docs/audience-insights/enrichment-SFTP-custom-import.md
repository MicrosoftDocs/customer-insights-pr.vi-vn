---
title: Tăng cường với nhập tùy chỉnh SFTP
description: Thông tin chung về tăng cường nhập tùy chỉnh SFTP.
ms.date: 11/18/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: d9e095ef793cbd25415864f76a541dce68fafe47
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595881"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="acd1f-103">Tăng cường hồ sơ khách hàng với dữ liệu tùy chỉnh (bản xem trước)</span><span class="sxs-lookup"><span data-stu-id="acd1f-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="acd1f-104">Nhập tùy chỉnh Giao thức truyền tệp bảo mật (SFTP) cho phép bạn nhập dữ liệu mà không phải trải qua quá trình hợp nhất dữ liệu.</span><span class="sxs-lookup"><span data-stu-id="acd1f-104">Secure File Transfer Protocol(SFTP) custom import enables you to import data that doesn't have to go through the process of data unification.</span></span> <span data-ttu-id="acd1f-105">Đó là một cách linh hoạt, bảo mật và dễ dàng để đưa dữ liệu của bạn vào.</span><span class="sxs-lookup"><span data-stu-id="acd1f-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="acd1f-106">Nhập tùy chỉnh SFTP có thể được sử dụng kết hợp với [Xuất SFTP](export-sftp.md) cho phép bạn xuất dữ liệu hồ sơ khách hàng cần thiết để tăng cường.</span><span class="sxs-lookup"><span data-stu-id="acd1f-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="acd1f-107">Sau đó, dữ liệu có thể được xử lý, tăng cường và nhập tùy chỉnh SFTP có thể được sử dụng để đưa dữ liệu được tăng cường trở lại khả năng thông tin chi tiết của đối tượng Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="acd1f-107">The data can then be processed, enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="acd1f-108">Điều kiện tiên quyết</span><span class="sxs-lookup"><span data-stu-id="acd1f-108">Prerequisites</span></span>

<span data-ttu-id="acd1f-109">Để định cấu hình tính năng nhập tùy chỉnh SFTP, bạn phải đáp ứng các điều kiện tiên quyết sau:</span><span class="sxs-lookup"><span data-stu-id="acd1f-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="acd1f-110">Bạn có thông tin xác thực người dùng (tên người dùng và mật khẩu) cho vị trí SFTP nơi dữ liệu sẽ được nhập từ đó.</span><span class="sxs-lookup"><span data-stu-id="acd1f-110">You have user credentials (user name and password) for the SFTP location where the data that is going to be imported from.</span></span>
- <span data-ttu-id="acd1f-111">Bạn có URL và số cổng (thường là 22) cho máy chủ lưu trữ STFP.</span><span class="sxs-lookup"><span data-stu-id="acd1f-111">You have the URL and port number (usually 22) for the STFP host.</span></span>
- <span data-ttu-id="acd1f-112">Bạn có tên tệp và vị trí của tệp sẽ được nhập trên máy chủ SFTP.</span><span class="sxs-lookup"><span data-stu-id="acd1f-112">You have the filename and location of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="acd1f-113">Có 1 tệp *model.json* chỉ định lược đồ cho dữ liệu sẽ được nhập.</span><span class="sxs-lookup"><span data-stu-id="acd1f-113">There's a *model.json* file that specifies the schema for the data that are to be imported.</span></span> <span data-ttu-id="acd1f-114">Tệp này phải nằm trong cùng thư mục với tệp để nhập.</span><span class="sxs-lookup"><span data-stu-id="acd1f-114">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="acd1f-115">Bạn có quyền [Quản trị viên](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="acd1f-115">You have [Administrator](permissions.md#administrator) permission.</span></span>

## <a name="configuration"></a><span data-ttu-id="acd1f-116">Cấu hình</span><span class="sxs-lookup"><span data-stu-id="acd1f-116">Configuration</span></span>

1. <span data-ttu-id="acd1f-117">Đi đến **Dữ liệu** > **Tăng cường** và chọn tab **Khám phá**.</span><span class="sxs-lookup"><span data-stu-id="acd1f-117">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="acd1f-118">Trên **ngăn xếp nhập tùy chỉnh SFTP**, chọn **Tăng cường dữ liệu của tôi**.</span><span class="sxs-lookup"><span data-stu-id="acd1f-118">On the **SFTP custom import tile**, select **Enrich my data**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="acd1f-119">![Ngăn xếp Nhập tùy chỉnh SFTP](media/SFTP_Custom_Import_tile.png "Ngăn xếp Nhập tùy chỉnh SFTP")</span><span class="sxs-lookup"><span data-stu-id="acd1f-119">![SFTP Custom Import tile](media/SFTP_Custom_Import_tile.png "SFTP Custom Import tile")</span></span>

1. <span data-ttu-id="acd1f-120">Chọn **Bắt đầu** và cung cấp thông tin xác thực và địa chỉ cho máy chủ SFTP.</span><span class="sxs-lookup"><span data-stu-id="acd1f-120">Select **Get started** and provide the credentials and the address for the SFTP server.</span></span> <span data-ttu-id="acd1f-121">Ví dụ: sftp: //mysftpserver.com:22.</span><span class="sxs-lookup"><span data-stu-id="acd1f-121">For example, sftp://mysftpserver.com:22.</span></span>

1. <span data-ttu-id="acd1f-122">Nhập tên của tệp chứa dữ liệu và đường dẫn đến tệp trên máy chủ SFTP nếu tệp không nằm trong thư mục gốc.</span><span class="sxs-lookup"><span data-stu-id="acd1f-122">Enter the name of the file that contains the data and path to the file on the SFTP server if it's not in the root folder.</span></span>

1. <span data-ttu-id="acd1f-123">Xác nhận tất cả các đầu vào bằng cách chọn **Kết nối với Nhập tùy chỉnh**.</span><span class="sxs-lookup"><span data-stu-id="acd1f-123">Confirm all inputs by selecting **Connect to Custom Import**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="acd1f-124">![Hộp thả xuống Cấu hình nhập tùy chỉnh SFTP](media/SFTP_Custom_Import_Configuration_flyout.png "Hộp thả xuống Cấu hình nhập tùy chỉnh SFTP")</span><span class="sxs-lookup"><span data-stu-id="acd1f-124">![SFTP Custom Import Configuration flyout](media/SFTP_Custom_Import_Configuration_flyout.png "SFTP Custom Import Configuration flyout")</span></span>

## <a name="defining-field-mappings"></a><span data-ttu-id="acd1f-125">Đang xác định ánh xạ trường</span><span class="sxs-lookup"><span data-stu-id="acd1f-125">Defining field mappings</span></span> 

<span data-ttu-id="acd1f-126">Thư mục chứa tệp sẽ được nhập trên máy chủ SFTP cũng phải chứa tệp *model.json*.</span><span class="sxs-lookup"><span data-stu-id="acd1f-126">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="acd1f-127">Tệp này xác định lược đồ sẽ sử dụng để nhập dữ liệu.</span><span class="sxs-lookup"><span data-stu-id="acd1f-127">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="acd1f-128">Lược đồ phải sử dụng [Common Data Model](/common-data-model/) để chỉ định ánh xạ trường.</span><span class="sxs-lookup"><span data-stu-id="acd1f-128">The schema has to use [the Common Data Model](/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="acd1f-129">Một ví dụ đơn giản về tệp model.json trông như sau:</span><span class="sxs-lookup"><span data-stu-id="acd1f-129">A simple example of a model.json file looks like this:</span></span>

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

## <a name="enrichment-results"></a><span data-ttu-id="acd1f-130">Kết quả làm phong phú</span><span class="sxs-lookup"><span data-stu-id="acd1f-130">Enrichment results</span></span>

<span data-ttu-id="acd1f-131">Để bắt đầu quá trình tăng cường, hãy chọn **Chạy** từ thanh lệnh.</span><span class="sxs-lookup"><span data-stu-id="acd1f-131">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="acd1f-132">Bạn cũng có thể để hệ thống chạy quá trình tăng cường tự động như một phần của [làm mới theo lịch trình](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="acd1f-132">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="acd1f-133">Thời gian xử lý sẽ phụ thuộc vào kích thước của dữ liệu được nhập và kết nối với máy chủ SFTP.</span><span class="sxs-lookup"><span data-stu-id="acd1f-133">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="acd1f-134">Sau khi quá trình tăng cường hoàn tất, bạn có thể xem lại dữ liệu bổ sung tùy chỉnh mới được nhập của mình trong **Nội dung tăng cường của tôi**.</span><span class="sxs-lookup"><span data-stu-id="acd1f-134">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="acd1f-135">Ngoài ra, bạn sẽ tìm thấy thời gian của lần cập nhật gần nhất và số lượng hồ sơ được tăng cường.</span><span class="sxs-lookup"><span data-stu-id="acd1f-135">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="acd1f-136">Bạn có thể truy cập dạng xem chi tiết của từng hồ sơ được làm phong phú bằng cách chọn **Xem dữ liệu được làm phong phú**.</span><span class="sxs-lookup"><span data-stu-id="acd1f-136">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="acd1f-137">Các bước tiếp theo</span><span class="sxs-lookup"><span data-stu-id="acd1f-137">Next steps</span></span>

<span data-ttu-id="acd1f-138">Xây dựng dựa trên dữ liệu khách hàng phong phú của bạn.</span><span class="sxs-lookup"><span data-stu-id="acd1f-138">Build on top of your enriched customer data.</span></span> <span data-ttu-id="acd1f-139">Tạo [phân đoạn](segments.md), [đo lường](measures.md) và [xuất dữ liệu](export-destinations.md) để cung cấp trải nghiệm cá nhân hóa cho khách hàng của bạn.</span><span class="sxs-lookup"><span data-stu-id="acd1f-139">Create [segments](segments.md), [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>




[!INCLUDE[footer-include](../includes/footer-banner.md)]