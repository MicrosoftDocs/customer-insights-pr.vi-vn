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
ms.openlocfilehash: b935be08199f20e83bceb3317985b0e1dc120016
ms.sourcegitcommit: 6b07c9c3102761be162e4842f3c9fbc19f948a9b
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 05/25/2021
ms.locfileid: "6095764"
---
# <a name="manage-predictions"></a><span data-ttu-id="93229-103">Quản lý dự đoán</span><span class="sxs-lookup"><span data-stu-id="93229-103">Manage predictions</span></span>

<span data-ttu-id="93229-104">Bài viết này thảo luận về một số tác vụ mà hầu hết các kịch bản dự đoán đều có.</span><span class="sxs-lookup"><span data-stu-id="93229-104">This article discusses some tasks that most prediction scenarios share.</span></span>

## <a name="troubleshoot-a-failed-prediction"></a><span data-ttu-id="93229-105">Khắc phục sự cố dự đoán không thành công</span><span class="sxs-lookup"><span data-stu-id="93229-105">Troubleshoot a failed prediction</span></span>

1. <span data-ttu-id="93229-106">Đi đến **Thông tin** > **Dự đoán** và chọn tab **Dự đoán của tôi**.</span><span class="sxs-lookup"><span data-stu-id="93229-106">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="93229-107">Chọn dấu chấm lửng dọc bên cạnh dự đoán mà bạn muốn xem nhật ký lỗi.</span><span class="sxs-lookup"><span data-stu-id="93229-107">Select the vertical ellipses next to the prediction you want to view error logs for.</span></span>

1. <span data-ttu-id="93229-108">Chọn **Nhật ký**.</span><span class="sxs-lookup"><span data-stu-id="93229-108">Select **Logs**.</span></span>

1. <span data-ttu-id="93229-109">Xem lại tất cả lỗi.</span><span class="sxs-lookup"><span data-stu-id="93229-109">Review all the errors.</span></span> <span data-ttu-id="93229-110">Có một số loại lỗi có thể xảy ra và chúng mô tả nguyên nhân gây ra lỗi.</span><span class="sxs-lookup"><span data-stu-id="93229-110">There are several types of errors that can occur, and they describe what condition caused the error.</span></span> <span data-ttu-id="93229-111">Ví dụ: một lỗi không đủ dữ liệu để dự đoán chính xác thường được giải quyết bằng cách tải thêm dữ liệu vào Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="93229-111">For example, an error that there's not enough data to accurately predict is typically resolved by loading additional data into Customer Insights.</span></span>

## <a name="input-data-usability-report"></a><span data-ttu-id="93229-112">Báo cáo khả năng sử dụng dữ liệu đầu vào</span><span class="sxs-lookup"><span data-stu-id="93229-112">Input data usability report</span></span>

<span data-ttu-id="93229-113">Báo cáo khả năng sử dụng dữ liệu đầu vào cung cấp một dạng xem tổng hợp về các lỗi và cảnh báo mà các dự đoán có sẵn của bạn có thể đang tạo ra.</span><span class="sxs-lookup"><span data-stu-id="93229-113">The input data usability report provides a consolidated view of the errors and warnings that your out-of-box predictions may be generating.</span></span> <span data-ttu-id="93229-114">Báo cáo này cũng đưa ra đề xuất về cách cải thiện hiệu suất của mô hình.</span><span class="sxs-lookup"><span data-stu-id="93229-114">It also gives recommendations how to improve the model performance.</span></span>

<span data-ttu-id="93229-115">Báo cáo này có sẵn sau khi một mô hình đã hoàn tất quá trình đào tạo.</span><span class="sxs-lookup"><span data-stu-id="93229-115">The report is available after a model has completed its training process.</span></span> <span data-ttu-id="93229-116">Báo cáo được tạo cho từng mô hình riêng biệt, bất kể quá trình có hoàn tất thành công hay không.</span><span class="sxs-lookup"><span data-stu-id="93229-116">It's created for each model separately, regardless if it completed successfully or not.</span></span>

> [!NOTE]
> <span data-ttu-id="93229-117">Hiện tại, tính năng này chỉ hoạt động cho mô hình Khả năng rời bỏ giao dịch.</span><span class="sxs-lookup"><span data-stu-id="93229-117">Currently, this feature only works for the Transaction Churn model.</span></span>

### <a name="view-the-input-data-usability-report"></a><span data-ttu-id="93229-118">Xem báo cáo khả năng sử dụng dữ liệu đầu vào</span><span class="sxs-lookup"><span data-stu-id="93229-118">View the input data usability report</span></span>

<span data-ttu-id="93229-119">Sau khi một mô hình có sẵn đã hoàn thành bước đào tạo, hãy xem báo cáo theo các cách sau:</span><span class="sxs-lookup"><span data-stu-id="93229-119">After an out-of-box model has completed its training step, view the report:</span></span>
- <span data-ttu-id="93229-120">Chọn dấu chấm lửng bên cạnh tên mô hình rồi chọn **Báo cáo khả năng sử dụng dữ liệu đầu vào**.</span><span class="sxs-lookup"><span data-stu-id="93229-120">Select the ellipses next to the model name and choose **Input data usability report**.</span></span>
- <span data-ttu-id="93229-121">Chọn trạng thái của một mô hình rồi chọn **Xem báo cáo khả năng sử dụng dữ liệu đầu vào** trong ngăn bên.</span><span class="sxs-lookup"><span data-stu-id="93229-121">Select the status of a model select **See Input data usability report** in the side pane.</span></span>
- <span data-ttu-id="93229-122">Chọn một trong các mô hình trong danh sách rồi chọn **Báo cáo khả năng sử dụng dữ liệu đầu vào** trên thanh lệnh.</span><span class="sxs-lookup"><span data-stu-id="93229-122">Selecting one of the models in the list and select **Input data usability report** in the command bar.</span></span>
- <span data-ttu-id="93229-123">Mở trang kết quả mô hình rồi chọn **Báo cáo khả năng sử dụng dữ liệu đầu vào** trên thanh lệnh.</span><span class="sxs-lookup"><span data-stu-id="93229-123">Open the model results page and select **Input data usability report** in the command bar.</span></span>

### <a name="information-in-the-input-data-usability-report"></a><span data-ttu-id="93229-124">Thông tin trong báo cáo khả năng sử dụng dữ liệu đầu vào</span><span class="sxs-lookup"><span data-stu-id="93229-124">Information in the input data usability report</span></span>

<span data-ttu-id="93229-125">Các cột sau trong báo cáo chứa thông tin hữu ích để cải thiện dữ liệu cho mô hình.</span><span class="sxs-lookup"><span data-stu-id="93229-125">The following columns in the report contain helpful information to improve the data for the model.</span></span>

:::image type="content" source="media/input-data-usability-report.png" alt-text="Ví dụ về một báo cáo khả năng sử dụng dữ liệu đầu vào hiển thị một bảng có lỗi, cảnh báo và đề xuất.":::

- <span data-ttu-id="93229-127">Tên: Tên mô tả của lỗi, cảnh báo hoặc đề xuất.</span><span class="sxs-lookup"><span data-stu-id="93229-127">Name: Descriptive name of the error, warning, or recommendation.</span></span>
- <span data-ttu-id="93229-128">Bước: Giai đoạn của mô hình, đào tạo hoặc điểm số, thông tin đề cập đến.</span><span class="sxs-lookup"><span data-stu-id="93229-128">Step: Model phase, train or score, the information refers to.</span></span>
- <span data-ttu-id="93229-129">Trạng thái: Mức độ nghiêm trọng của thông tin (lỗi, cảnh báo, đề xuất).</span><span class="sxs-lookup"><span data-stu-id="93229-129">State: Severity of the information (error, warning, recommendation).</span></span>
- <span data-ttu-id="93229-130">Tên cột: Cột trong thực thể cần được sửa đổi để cải thiện hiệu suất mô hình.</span><span class="sxs-lookup"><span data-stu-id="93229-130">Column name: Column in an entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="93229-131">Tên thực thể: Tên của thực thể cần được sửa đổi để cải thiện hiệu suất mô hình.</span><span class="sxs-lookup"><span data-stu-id="93229-131">Entity name: Name of the entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="93229-132">Chi tiết: Thông tin chi tiết về lỗi, cảnh báo hoặc đề xuất.</span><span class="sxs-lookup"><span data-stu-id="93229-132">Details: Details about the error, warning, or recommendation.</span></span>

## <a name="refresh-a-prediction"></a><span data-ttu-id="93229-133">Làm mới một dự đoán</span><span class="sxs-lookup"><span data-stu-id="93229-133">Refresh a prediction</span></span>

<span data-ttu-id="93229-134">Các dự đoán sẽ tự động làm mới trên cùng một [trình làm mới dữ liệu](system.md#schedule-tab) như đặt cấu hình trong thiết đặt.</span><span class="sxs-lookup"><span data-stu-id="93229-134">Predictions will automatically refresh on the same [schedule your data refreshes](system.md#schedule-tab) as configured in settings.</span></span> <span data-ttu-id="93229-135">Bạn cũng có thể làm mới chúng theo cách thủ công.</span><span class="sxs-lookup"><span data-stu-id="93229-135">You can refresh them manually too.</span></span>

1. <span data-ttu-id="93229-136">Đi đến **Thông tin** > **Dự đoán** và chọn tab **Dự đoán của tôi**.</span><span class="sxs-lookup"><span data-stu-id="93229-136">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="93229-137">Chọn các hình elip dọc bên cạnh dự đoán bạn muốn làm mới.</span><span class="sxs-lookup"><span data-stu-id="93229-137">Select the vertical ellipses next to the prediction you want to refresh.</span></span>

1. <span data-ttu-id="93229-138">Chọn **Làm mới**.</span><span class="sxs-lookup"><span data-stu-id="93229-138">Select **Refresh**.</span></span>

## <a name="delete-a-prediction"></a><span data-ttu-id="93229-139">Xóa dự đoán</span><span class="sxs-lookup"><span data-stu-id="93229-139">Delete a prediction</span></span>

<span data-ttu-id="93229-140">Xóa dự đoán cũng xóa thực thể đầu ra của nó.</span><span class="sxs-lookup"><span data-stu-id="93229-140">Deleting a prediction also removes its output entity.</span></span>

1. <span data-ttu-id="93229-141">Đi đến **Thông tin** > **Dự đoán** và chọn tab **Dự đoán của tôi**.</span><span class="sxs-lookup"><span data-stu-id="93229-141">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="93229-142">Chọn các hình elip dọc bên cạnh dự đoán bạn muốn xóa.</span><span class="sxs-lookup"><span data-stu-id="93229-142">Select the vertical ellipses next to the prediction you want to delete.</span></span>

1. <span data-ttu-id="93229-143">Chọn **Xóa**.</span><span class="sxs-lookup"><span data-stu-id="93229-143">Select **Delete**.</span></span>
