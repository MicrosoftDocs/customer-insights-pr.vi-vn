---
title: Các tác vụ chung cho kịch bản dự đoán
description: Tìm hiểu cách quản lý, khắc phục sự cố và tinh chỉnh dự đoán.
ms.date: 05/17/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: dccb8dcca8f65f64973e46fed9d83034d58282e2
ms.sourcegitcommit: bcc47d15d4f0eacf008e4dbc09baac7f062b3ca8
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 06/29/2021
ms.locfileid: "6315904"
---
# <a name="manage-predictions"></a><span data-ttu-id="213ad-103">Quản lý dự đoán</span><span class="sxs-lookup"><span data-stu-id="213ad-103">Manage predictions</span></span>

<span data-ttu-id="213ad-104">Bài viết này thảo luận về một số tác vụ mà hầu hết các kịch bản dự đoán đều có.</span><span class="sxs-lookup"><span data-stu-id="213ad-104">This article discusses some tasks that most prediction scenarios share.</span></span>

## <a name="troubleshoot-a-failed-prediction"></a><span data-ttu-id="213ad-105">Khắc phục sự cố dự đoán không thành công</span><span class="sxs-lookup"><span data-stu-id="213ad-105">Troubleshoot a failed prediction</span></span>

1. <span data-ttu-id="213ad-106">Đi đến **Thông tin** > **Dự đoán** và chọn tab **Dự đoán của tôi**.</span><span class="sxs-lookup"><span data-stu-id="213ad-106">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="213ad-107">Chọn dấu chấm lửng dọc bên cạnh dự đoán mà bạn muốn xem nhật ký lỗi.</span><span class="sxs-lookup"><span data-stu-id="213ad-107">Select the vertical ellipses next to the prediction you want to view error logs for.</span></span>

1. <span data-ttu-id="213ad-108">Chọn **Nhật ký**.</span><span class="sxs-lookup"><span data-stu-id="213ad-108">Select **Logs**.</span></span>

1. <span data-ttu-id="213ad-109">Xem lại tất cả lỗi.</span><span class="sxs-lookup"><span data-stu-id="213ad-109">Review all the errors.</span></span> <span data-ttu-id="213ad-110">Có một số loại lỗi có thể xảy ra và chúng mô tả nguyên nhân gây ra lỗi.</span><span class="sxs-lookup"><span data-stu-id="213ad-110">There are several types of errors that can occur, and they describe what condition caused the error.</span></span> <span data-ttu-id="213ad-111">Ví dụ: một lỗi không đủ dữ liệu để dự đoán chính xác thường được giải quyết bằng cách tải thêm dữ liệu vào Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="213ad-111">For example, an error that there's not enough data to accurately predict is typically resolved by loading additional data into Customer Insights.</span></span>

## <a name="input-data-usability-report"></a><span data-ttu-id="213ad-112">Báo cáo khả năng sử dụng dữ liệu đầu vào</span><span class="sxs-lookup"><span data-stu-id="213ad-112">Input data usability report</span></span>

<span data-ttu-id="213ad-113">Báo cáo khả năng sử dụng dữ liệu đầu vào cung cấp một dạng xem tổng hợp về các lỗi và cảnh báo mà các dự đoán có sẵn của bạn có thể đang tạo ra.</span><span class="sxs-lookup"><span data-stu-id="213ad-113">The input data usability report provides a consolidated view of the errors and warnings that your out-of-box predictions may be generating.</span></span> <span data-ttu-id="213ad-114">Báo cáo này cũng đưa ra đề xuất về cách cải thiện hiệu suất của mô hình.</span><span class="sxs-lookup"><span data-stu-id="213ad-114">It also gives recommendations how to improve the model performance.</span></span>

<span data-ttu-id="213ad-115">Báo cáo này có sẵn sau khi một mô hình đã hoàn tất quá trình đào tạo.</span><span class="sxs-lookup"><span data-stu-id="213ad-115">The report is available after a model has completed its training process.</span></span> <span data-ttu-id="213ad-116">Báo cáo được tạo cho từng mô hình riêng biệt, bất kể quá trình có hoàn tất thành công hay không.</span><span class="sxs-lookup"><span data-stu-id="213ad-116">It's created for each model separately, regardless if it completed successfully or not.</span></span>

### <a name="view-the-input-data-usability-report"></a><span data-ttu-id="213ad-117">Xem báo cáo khả năng sử dụng dữ liệu đầu vào</span><span class="sxs-lookup"><span data-stu-id="213ad-117">View the input data usability report</span></span>

<span data-ttu-id="213ad-118">Sau khi một mô hình có sẵn đã hoàn thành bước đào tạo, hãy xem báo cáo theo các cách sau:</span><span class="sxs-lookup"><span data-stu-id="213ad-118">After an out-of-box model has completed its training step, view the report:</span></span>
- <span data-ttu-id="213ad-119">Chọn dấu chấm lửng bên cạnh tên mô hình rồi chọn **Báo cáo khả năng sử dụng dữ liệu đầu vào**.</span><span class="sxs-lookup"><span data-stu-id="213ad-119">Select the ellipses next to the model name and choose **Input data usability report**.</span></span>
- <span data-ttu-id="213ad-120">Chọn trạng thái của một mô hình rồi chọn **Xem báo cáo khả năng sử dụng dữ liệu đầu vào** trong ngăn bên.</span><span class="sxs-lookup"><span data-stu-id="213ad-120">Select the status of a model select **See Input data usability report** in the side pane.</span></span>
- <span data-ttu-id="213ad-121">Chọn một trong các mô hình trong danh sách rồi chọn **Báo cáo khả năng sử dụng dữ liệu đầu vào** trên thanh lệnh.</span><span class="sxs-lookup"><span data-stu-id="213ad-121">Selecting one of the models in the list and select **Input data usability report** in the command bar.</span></span>
- <span data-ttu-id="213ad-122">Mở trang kết quả mô hình rồi chọn **Báo cáo khả năng sử dụng dữ liệu đầu vào** trên thanh lệnh.</span><span class="sxs-lookup"><span data-stu-id="213ad-122">Open the model results page and select **Input data usability report** in the command bar.</span></span>

### <a name="information-in-the-input-data-usability-report"></a><span data-ttu-id="213ad-123">Thông tin trong báo cáo khả năng sử dụng dữ liệu đầu vào</span><span class="sxs-lookup"><span data-stu-id="213ad-123">Information in the input data usability report</span></span>

<span data-ttu-id="213ad-124">Các cột sau trong báo cáo chứa thông tin hữu ích để cải thiện dữ liệu cho mô hình.</span><span class="sxs-lookup"><span data-stu-id="213ad-124">The following columns in the report contain helpful information to improve the data for the model.</span></span>

:::image type="content" source="media/input-data-usability-report.png" alt-text="Ví dụ về một báo cáo khả năng sử dụng dữ liệu đầu vào hiển thị một bảng có lỗi, cảnh báo và đề xuất.":::

- <span data-ttu-id="213ad-126">Tên: Tên mô tả của lỗi, cảnh báo hoặc đề xuất.</span><span class="sxs-lookup"><span data-stu-id="213ad-126">Name: Descriptive name of the error, warning, or recommendation.</span></span>
- <span data-ttu-id="213ad-127">Bước: Giai đoạn của mô hình, đào tạo hoặc điểm số, thông tin đề cập đến.</span><span class="sxs-lookup"><span data-stu-id="213ad-127">Step: Model phase, train or score, the information refers to.</span></span>
- <span data-ttu-id="213ad-128">Trạng thái: Mức độ nghiêm trọng của thông tin (lỗi, cảnh báo, đề xuất).</span><span class="sxs-lookup"><span data-stu-id="213ad-128">State: Severity of the information (error, warning, recommendation).</span></span>
- <span data-ttu-id="213ad-129">Tên cột: Cột trong thực thể cần được sửa đổi để cải thiện hiệu suất mô hình.</span><span class="sxs-lookup"><span data-stu-id="213ad-129">Column name: Column in an entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="213ad-130">Tên thực thể: Tên của thực thể cần được sửa đổi để cải thiện hiệu suất mô hình.</span><span class="sxs-lookup"><span data-stu-id="213ad-130">Entity name: Name of the entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="213ad-131">Chi tiết: Thông tin chi tiết về lỗi, cảnh báo hoặc đề xuất.</span><span class="sxs-lookup"><span data-stu-id="213ad-131">Details: Details about the error, warning, or recommendation.</span></span>

## <a name="refresh-a-prediction"></a><span data-ttu-id="213ad-132">Làm mới một dự đoán</span><span class="sxs-lookup"><span data-stu-id="213ad-132">Refresh a prediction</span></span>

<span data-ttu-id="213ad-133">Các dự đoán sẽ tự động làm mới trên cùng một [trình làm mới dữ liệu](system.md#schedule-tab) như định cấu hình trong thiết đặt.</span><span class="sxs-lookup"><span data-stu-id="213ad-133">Predictions will automatically refresh on the same [schedule your data refreshes](system.md#schedule-tab) as configured in settings.</span></span> <span data-ttu-id="213ad-134">Bạn cũng có thể làm mới chúng theo cách thủ công.</span><span class="sxs-lookup"><span data-stu-id="213ad-134">You can refresh them manually too.</span></span>

1. <span data-ttu-id="213ad-135">Đi đến **Thông tin** > **Dự đoán** và chọn tab **Dự đoán của tôi**.</span><span class="sxs-lookup"><span data-stu-id="213ad-135">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="213ad-136">Chọn các hình elip dọc bên cạnh dự đoán bạn muốn làm mới.</span><span class="sxs-lookup"><span data-stu-id="213ad-136">Select the vertical ellipses next to the prediction you want to refresh.</span></span>

1. <span data-ttu-id="213ad-137">Chọn **Làm mới**.</span><span class="sxs-lookup"><span data-stu-id="213ad-137">Select **Refresh**.</span></span>

## <a name="delete-a-prediction"></a><span data-ttu-id="213ad-138">Xóa dự đoán</span><span class="sxs-lookup"><span data-stu-id="213ad-138">Delete a prediction</span></span>

<span data-ttu-id="213ad-139">Xóa dự đoán cũng xóa thực thể đầu ra của nó.</span><span class="sxs-lookup"><span data-stu-id="213ad-139">Deleting a prediction also removes its output entity.</span></span>

1. <span data-ttu-id="213ad-140">Đi đến **Thông tin** > **Dự đoán** và chọn tab **Dự đoán của tôi**.</span><span class="sxs-lookup"><span data-stu-id="213ad-140">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="213ad-141">Chọn các hình elip dọc bên cạnh dự đoán bạn muốn xóa.</span><span class="sxs-lookup"><span data-stu-id="213ad-141">Select the vertical ellipses next to the prediction you want to delete.</span></span>

1. <span data-ttu-id="213ad-142">Chọn **Xóa**.</span><span class="sxs-lookup"><span data-stu-id="213ad-142">Select **Delete**.</span></span>
