---
title: Xuất dữ liệu Customer Insights sang Azure Data Lake Storage thế hệ 2
description: Tìm hiểu cách định cấu hình kết nối với Azure Data Lake Storage thế hệ 2.
ms.date: 02/04/2021
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b00c3d6178150cbc93fe800779f094809d4dc67b
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477205"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="262c9-103">Trình kết nối cho Azure Data Lake Storage thế hệ 2 (bản xem trước)</span><span class="sxs-lookup"><span data-stu-id="262c9-103">Connector for Azure Data Lake Storage Gen2 (preview)</span></span>

<span data-ttu-id="262c9-104">Lưu trữ dữ liệu Customer Insights của bạn trong Azure Data Lake Storage thế hệ 2 hoặc sử dụng kho lưu trữ đó để chuyển dữ liệu của bạn sang các ứng dụng khác.</span><span class="sxs-lookup"><span data-stu-id="262c9-104">Store your Customer Insights data in Azure Data Lake Storage Gen2 or use it to transfer your data to other applications.</span></span>

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a><span data-ttu-id="262c9-105">Định cấu hình trình kết nối cho Azure Data Lake Storage thế hệ 2</span><span class="sxs-lookup"><span data-stu-id="262c9-105">Configure the connector for Azure Data Lake Storage Gen2</span></span>

1. <span data-ttu-id="262c9-106">Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Quản trị viên** > **Nơi xuất đích**.</span><span class="sxs-lookup"><span data-stu-id="262c9-106">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="262c9-107">Trong **Azure Data Lake Storage thế hệ 2**, chọn **Thiết lập**.</span><span class="sxs-lookup"><span data-stu-id="262c9-107">Under **Azure Data Lake Storage Gen2**, select **Set up**.</span></span>

1. <span data-ttu-id="262c9-108">Trong trường **Tên hiển thị**, hãy đặt tên cho vị trí để dễ nhận diện.</span><span class="sxs-lookup"><span data-stu-id="262c9-108">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="262c9-109">Nhập **Tên tài khoản**, **Khóa tài khoản** và **Bộ chứa** cho Azure Data Lake Storage Thế hệ 2 của bạn.</span><span class="sxs-lookup"><span data-stu-id="262c9-109">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="262c9-110">Để tìm hiểu cách tạo tài khoản lưu trữ để sử dụng với Azure Data Lake Storage thế hệ 2, hãy xem [Tạo tài khoản lưu trữ](https://docs.microsoft.com/azure/storage/blobs/create-data-lake-storage-account).</span><span class="sxs-lookup"><span data-stu-id="262c9-110">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](https://docs.microsoft.com/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="262c9-111">Để tìm hiểu thêm về cách tìm tên tài khoản lưu trữ Azure Data Lake thế hệ 2 và khóa tài khoản, hãy xem [Quản lý cài đặt tài khoản lưu trữ trong cổng Azure](https://docs.microsoft.com/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="262c9-111">To learn more about how to find the Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](https://docs.microsoft.com/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="262c9-112">Chọn **Tiếp theo**.</span><span class="sxs-lookup"><span data-stu-id="262c9-112">Select **Next**.</span></span>

1. <span data-ttu-id="262c9-113">Chọn ô cạnh mỗi thực thể mà bạn muốn xuất sang vị trí này.</span><span class="sxs-lookup"><span data-stu-id="262c9-113">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="262c9-114">Chọn **Lưu**.</span><span class="sxs-lookup"><span data-stu-id="262c9-114">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="262c9-115">Xuất dữ liệu</span><span class="sxs-lookup"><span data-stu-id="262c9-115">Export the data</span></span>

<span data-ttu-id="262c9-116">Bạn có thể [xuất dữ liệu theo nhu cầu](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="262c9-116">You can [export data on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="262c9-117">Mỗi lần [làm mới theo lịch](system.md#schedule-tab), tác vụ xuất cũng sẽ chạy.</span><span class="sxs-lookup"><span data-stu-id="262c9-117">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
