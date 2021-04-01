---
title: Xuất dữ liệu Customer Insights sang Azure Data Lake Storage thế hệ 2
description: Tìm hiểu cách định cấu hình kết nối với Azure Data Lake Storage thế hệ 2.
ms.date: 02/04/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 7c0eef575f745efa6312d7141a6dd96607f9797e
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596670"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="e5fe1-103">Trình kết nối cho Azure Data Lake Storage thế hệ 2 (bản xem trước)</span><span class="sxs-lookup"><span data-stu-id="e5fe1-103">Connector for Azure Data Lake Storage Gen2 (preview)</span></span>

<span data-ttu-id="e5fe1-104">Lưu trữ dữ liệu Customer Insights của bạn trong Azure Data Lake Storage thế hệ 2 hoặc sử dụng kho lưu trữ đó để chuyển dữ liệu của bạn sang các ứng dụng khác.</span><span class="sxs-lookup"><span data-stu-id="e5fe1-104">Store your Customer Insights data in Azure Data Lake Storage Gen2 or use it to transfer your data to other applications.</span></span>

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a><span data-ttu-id="e5fe1-105">Định cấu hình trình kết nối cho Azure Data Lake Storage thế hệ 2</span><span class="sxs-lookup"><span data-stu-id="e5fe1-105">Configure the connector for Azure Data Lake Storage Gen2</span></span>

1. <span data-ttu-id="e5fe1-106">Trong thông tin chi tiết về đối tượng, hãy chuyển đến **Quản trị viên** > **Nơi xuất đích**.</span><span class="sxs-lookup"><span data-stu-id="e5fe1-106">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="e5fe1-107">Trong **Azure Data Lake Storage thế hệ 2**, chọn **Thiết lập**.</span><span class="sxs-lookup"><span data-stu-id="e5fe1-107">Under **Azure Data Lake Storage Gen2**, select **Set up**.</span></span>

1. <span data-ttu-id="e5fe1-108">Trong trường **Tên hiển thị**, hãy đặt tên cho vị trí để dễ nhận diện.</span><span class="sxs-lookup"><span data-stu-id="e5fe1-108">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="e5fe1-109">Nhập **Tên tài khoản**, **Khóa tài khoản** và **Bộ chứa** cho Azure Data Lake Storage Thế hệ 2 của bạn.</span><span class="sxs-lookup"><span data-stu-id="e5fe1-109">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="e5fe1-110">Để tìm hiểu cách tạo tài khoản lưu trữ để sử dụng với Azure Data Lake Storage thế hệ 2, hãy xem [Tạo tài khoản lưu trữ](/azure/storage/blobs/create-data-lake-storage-account).</span><span class="sxs-lookup"><span data-stu-id="e5fe1-110">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="e5fe1-111">Để tìm hiểu thêm về cách tìm tên tài khoản lưu trữ Azure Data Lake thế hệ 2 và khóa tài khoản, hãy xem [Quản lý cài đặt tài khoản lưu trữ trong cổng Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="e5fe1-111">To learn more about how to find the Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="e5fe1-112">Chọn **Tiếp theo**.</span><span class="sxs-lookup"><span data-stu-id="e5fe1-112">Select **Next**.</span></span>

1. <span data-ttu-id="e5fe1-113">Chọn ô cạnh mỗi thực thể mà bạn muốn xuất sang vị trí này.</span><span class="sxs-lookup"><span data-stu-id="e5fe1-113">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="e5fe1-114">Chọn **Lưu**.</span><span class="sxs-lookup"><span data-stu-id="e5fe1-114">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="e5fe1-115">Xuất dữ liệu</span><span class="sxs-lookup"><span data-stu-id="e5fe1-115">Export the data</span></span>

<span data-ttu-id="e5fe1-116">Bạn có thể [xuất dữ liệu theo nhu cầu](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="e5fe1-116">You can [export data on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="e5fe1-117">Mỗi lần [làm mới theo lịch](system.md#schedule-tab), tác vụ xuất cũng sẽ chạy.</span><span class="sxs-lookup"><span data-stu-id="e5fe1-117">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>