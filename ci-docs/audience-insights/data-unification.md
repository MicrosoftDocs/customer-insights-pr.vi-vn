---
title: Thống nhất dữ liệu
description: Tìm hiểu cách hợp nhất dữ liệu đã nhập.
ms.date: 04/16/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 24321e9e11f9fd4e800526673726e5146ed33674
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 11/03/2020
ms.locfileid: "4407297"
---
# <a name="data-unification"></a><span data-ttu-id="6155c-103">Thống nhất dữ liệu</span><span class="sxs-lookup"><span data-stu-id="6155c-103">Data unification</span></span>

<span data-ttu-id="6155c-104">Sau khi [thiết lập các nguồn dữ liệu](data-sources.md), bạn có thể thống nhất dữ liệu.</span><span class="sxs-lookup"><span data-stu-id="6155c-104">After [setting up the data sources](data-sources.md), you can unify the data.</span></span> <span data-ttu-id="6155c-105">Thống nhất dữ liệu bao gồm ba bước: **Ánh xạ**, **Đối sánh**, và **Hợp nhất**.</span><span class="sxs-lookup"><span data-stu-id="6155c-105">Data unification includes three steps: **Map**, **Match**, and **Merge**.</span></span>

<span data-ttu-id="6155c-106">Quá trình thống nhất dữ liệu cho phép bạn thống nhất các nguồn dữ liệu đã bị tách thành một tập dữ liệu chính duy nhất cung cấp chế độ xem hợp nhất về khách hàng.</span><span class="sxs-lookup"><span data-stu-id="6155c-106">The data unification process lets you unify once-disparate data sources into a single master dataset that provides a unified view of your customers.</span></span> <span data-ttu-id="6155c-107">Các giai đoạn thống nhất là bắt buộc, và thực hiện theo thứ tự sau đây:</span><span class="sxs-lookup"><span data-stu-id="6155c-107">Unification stages are mandatory, and performed in the following order:</span></span>

1. [<span data-ttu-id="6155c-108">Bản đồ</span><span class="sxs-lookup"><span data-stu-id="6155c-108">Map</span></span>](map-entities.md)
2. [<span data-ttu-id="6155c-109">Match</span><span class="sxs-lookup"><span data-stu-id="6155c-109">Match</span></span>](match-entities.md)
3. [<span data-ttu-id="6155c-110">Hợp nhất</span><span class="sxs-lookup"><span data-stu-id="6155c-110">Merge</span></span>](merge-entities.md)

<span data-ttu-id="6155c-111">Sau khi hoàn thành hợp nhất dữ liệu, bạn có thể tùy chọn</span><span class="sxs-lookup"><span data-stu-id="6155c-111">After completing the data unification, you can optionally</span></span>

- <span data-ttu-id="6155c-112">[thiết lập mối quan hệ giữa các thực thể](relationships.md) để tạo các phân đoạn phức tạp</span><span class="sxs-lookup"><span data-stu-id="6155c-112">[set up relationships between entities](relationships.md) to create sophisticated segments</span></span>
- <span data-ttu-id="6155c-113">[làm phong phú dữ liệu của bạn](enrichment-hub.md) để có được nhiều thông tin chi tiết hơn về khách hàng</span><span class="sxs-lookup"><span data-stu-id="6155c-113">[enrich your data](enrichment-hub.md) to get a wider range of insights about your customers</span></span>
- <span data-ttu-id="6155c-114">[xác định các hoạt động](activities.md) từ một số thuộc tính đã nhập</span><span class="sxs-lookup"><span data-stu-id="6155c-114">[define activities](activities.md) from some of the ingested attributes</span></span>
