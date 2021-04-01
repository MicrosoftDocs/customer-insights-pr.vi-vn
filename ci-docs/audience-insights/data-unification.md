---
title: Thống nhất dữ liệu
description: Tìm hiểu cách hợp nhất dữ liệu đã nhập.
ms.date: 04/16/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: 73d8006c670268420f8cd6a2b37cb214ba1bbd6c
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597905"
---
# <a name="data-unification-overview"></a><span data-ttu-id="0a816-103">Tổng quan về hợp nhất dữ liệu</span><span class="sxs-lookup"><span data-stu-id="0a816-103">Data unification overview</span></span>

<span data-ttu-id="0a816-104">Sau khi [thiết lập các nguồn dữ liệu](data-sources.md), bạn có thể thống nhất dữ liệu.</span><span class="sxs-lookup"><span data-stu-id="0a816-104">After [setting up the data sources](data-sources.md), you can unify the data.</span></span> <span data-ttu-id="0a816-105">Thống nhất dữ liệu bao gồm ba bước: **Ánh xạ**, **Đối sánh**, và **Hợp nhất**.</span><span class="sxs-lookup"><span data-stu-id="0a816-105">Data unification includes three steps: **Map**, **Match**, and **Merge**.</span></span>

<span data-ttu-id="0a816-106">Quá trình thống nhất dữ liệu cho phép bạn thống nhất các nguồn dữ liệu đã bị tách thành một tập dữ liệu chính duy nhất cung cấp chế độ xem hợp nhất về khách hàng.</span><span class="sxs-lookup"><span data-stu-id="0a816-106">The data unification process lets you unify once-disparate data sources into a single master dataset that provides a unified view of your customers.</span></span> <span data-ttu-id="0a816-107">Các giai đoạn thống nhất là bắt buộc, và thực hiện theo thứ tự sau đây:</span><span class="sxs-lookup"><span data-stu-id="0a816-107">Unification stages are mandatory, and performed in the following order:</span></span>

1. [<span data-ttu-id="0a816-108">Bản đồ</span><span class="sxs-lookup"><span data-stu-id="0a816-108">Map</span></span>](map-entities.md)
2. [<span data-ttu-id="0a816-109">Match</span><span class="sxs-lookup"><span data-stu-id="0a816-109">Match</span></span>](match-entities.md)
3. [<span data-ttu-id="0a816-110">Hợp nhất</span><span class="sxs-lookup"><span data-stu-id="0a816-110">Merge</span></span>](merge-entities.md)

<span data-ttu-id="0a816-111">Sau khi hoàn thành hợp nhất dữ liệu, bạn có thể tùy chọn</span><span class="sxs-lookup"><span data-stu-id="0a816-111">After completing the data unification, you can optionally</span></span>

- <span data-ttu-id="0a816-112">[thiết lập mối quan hệ giữa các thực thể](relationships.md) để tạo các phân đoạn phức tạp</span><span class="sxs-lookup"><span data-stu-id="0a816-112">[set up relationships between entities](relationships.md) to create sophisticated segments</span></span>
- <span data-ttu-id="0a816-113">[làm phong phú dữ liệu của bạn](enrichment-hub.md) để có được nhiều thông tin chi tiết hơn về khách hàng</span><span class="sxs-lookup"><span data-stu-id="0a816-113">[enrich your data](enrichment-hub.md) to get a wider range of insights about your customers</span></span>
- <span data-ttu-id="0a816-114">[xác định các hoạt động](activities.md) từ một số thuộc tính đã nhập</span><span class="sxs-lookup"><span data-stu-id="0a816-114">[define activities](activities.md) from some of the ingested attributes</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]