---
title: Xuất dữ liệu Customer Insights sang máy chủ SFTP
description: Tìm hiểu cách định cấu hình kết nối tới máy chủ SFTP.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c2529744d7a26a06324b79cad6a8001d75903545
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643529"
---
# <a name="connector-for-sftp-preview"></a><span data-ttu-id="54a95-103">Trình kết nối cho SFTP (bản xem trước)</span><span class="sxs-lookup"><span data-stu-id="54a95-103">Connector for SFTP (preview)</span></span>

<span data-ttu-id="54a95-104">Sử dụng dữ liệu khách hàng của bạn trong các ứng dụng bên thứ ba bằng cách xuất sang máy chủ Giao thức truyền tệp bảo mật (SFTP).</span><span class="sxs-lookup"><span data-stu-id="54a95-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol(SFTP) host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="54a95-105">Điều kiện tiên quyết</span><span class="sxs-lookup"><span data-stu-id="54a95-105">Prerequisites</span></span>

- <span data-ttu-id="54a95-106">Tính khả dụng của máy chủ SFTP và thông tin xác thực tương ứng.</span><span class="sxs-lookup"><span data-stu-id="54a95-106">Availability of a SFTP host and corresponding credentials.</span></span>

## <a name="connect-to-sftp"></a><span data-ttu-id="54a95-107">Kết nối với SFTP</span><span class="sxs-lookup"><span data-stu-id="54a95-107">Connect to SFTP</span></span>

1. <span data-ttu-id="54a95-108">Đi tới **Quản trị viên** > **Đích xuất**.</span><span class="sxs-lookup"><span data-stu-id="54a95-108">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="54a95-109">Trong phần **SFTP**, chọn **Thiết lập**.</span><span class="sxs-lookup"><span data-stu-id="54a95-109">Under **SFTP**, select **Set up**.</span></span>

1. <span data-ttu-id="54a95-110">Trong trường **Tên hiển thị**, hãy đặt tên cho vị trí để dễ nhận diện.</span><span class="sxs-lookup"><span data-stu-id="54a95-110">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="54a95-111">Cung cấp **Tên người dùng**, **Mật khẩu** và **Tên máy chủ** cho tài khoản SFTP của bạn.</span><span class="sxs-lookup"><span data-stu-id="54a95-111">Provide a **Username**, **Password** and **Hostname** for your SFTP account.</span></span> <span data-ttu-id="54a95-112">Ví dụ: Nếu thư mục gốc của máy chủ SFTP là /root/folder và bạn muốn xuất dữ liệu sang /root/folder/ci_export_destination_folder, máy chủ sẽ là sftp://<server_address>/ci_export_destination_folder".</span><span class="sxs-lookup"><span data-stu-id="54a95-112">Example: If your SFTP server's root folder is /root/folder, and you would like the data to be exported to /root/folder/ci_export_destination_folder, the the host should be sftp://<server_address>/ci_export_destination_folder".</span></span>

1. <span data-ttu-id="54a95-113">Chọn **Xác minh** để kiểm tra kết nối.</span><span class="sxs-lookup"><span data-stu-id="54a95-113">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="54a95-114">Sau khi đã xác minh, chọn xem bạn muốn xuất dữ liệu **Nén** hay **Không nén** rồi chọn **dấu tách trường** cho các tệp đã xuất.</span><span class="sxs-lookup"><span data-stu-id="54a95-114">After successful verification, choose if you want to export your data **Zipped** or **Unzipped**, and select the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="54a95-115">Chọn **Tôi đồng ý** để xác nhận **Quyền riêng tư về dữ liệu và sự tuân thủ**.</span><span class="sxs-lookup"><span data-stu-id="54a95-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="54a95-116">Chọn **Tiếp** để bắt đầu định cấu hình xuất.</span><span class="sxs-lookup"><span data-stu-id="54a95-116">Select **Next** to start configuring the export.</span></span>

## <a name="configure-the-connection"></a><span data-ttu-id="54a95-117">Định cấu hình kết nối</span><span class="sxs-lookup"><span data-stu-id="54a95-117">Configure the connection</span></span>

1. <span data-ttu-id="54a95-118">Chọn **thuộc tính khách hàng** mà bạn muốn xuất.</span><span class="sxs-lookup"><span data-stu-id="54a95-118">Select the **customer attributes** you want to export.</span></span> <span data-ttu-id="54a95-119">Bạn có thể xuất một hoặc nhiều thuộc tính.</span><span class="sxs-lookup"><span data-stu-id="54a95-119">You can export one or multiple attributes.</span></span>

1. <span data-ttu-id="54a95-120">Chọn **Tiếp theo**.</span><span class="sxs-lookup"><span data-stu-id="54a95-120">Select **Next**.</span></span>

1. <span data-ttu-id="54a95-121">Chọn phân khúc mà bạn muốn xuất.</span><span class="sxs-lookup"><span data-stu-id="54a95-121">Select the segments you want to export.</span></span>

1. <span data-ttu-id="54a95-122">Chọn **Lưu**.</span><span class="sxs-lookup"><span data-stu-id="54a95-122">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="54a95-123">Xuất dữ liệu</span><span class="sxs-lookup"><span data-stu-id="54a95-123">Export the data</span></span>

<span data-ttu-id="54a95-124">Bạn có thể [xuất dữ liệu theo nhu cầu](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="54a95-124">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="54a95-125">Mỗi lần [làm mới theo lịch](system.md#schedule-tab), tác vụ xuất cũng sẽ chạy.</span><span class="sxs-lookup"><span data-stu-id="54a95-125">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="54a95-126">Quyền riêng tư về dữ liệu và tuân thủ</span><span class="sxs-lookup"><span data-stu-id="54a95-126">Data privacy and compliance</span></span>

<span data-ttu-id="54a95-127">Khi bật Dynamics 365 Customer Insights để truyền dữ liệu qua SFTP, bạn cho phép chuyển dữ liệu ra bên ngoài ranh giới tuân thủ cho Dynamics 365 Customer Insights, bao gồm dữ liệu nhạy cảm tiềm ẩn như Dữ liệu cá nhân.</span><span class="sxs-lookup"><span data-stu-id="54a95-127">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="54a95-128">Microsoft sẽ chuyển những dữ liệu đó theo chỉ dẫn của bạn, nhưng bạn có trách nhiệm đảm bảo rằng điểm đến xuất đáp ứng mọi nghĩa vụ về quyền riêng tư hoặc bảo mật mà bạn có thể có.</span><span class="sxs-lookup"><span data-stu-id="54a95-128">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="54a95-129">Để biết thêm thông tin, hãy xem [Tuyên bố về Quyền riêng tư của Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="54a95-129">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="54a95-130">Quản trị viên Dynamics 365 Customer Insights của bạn có thể xóa đích xuất này bất cứ lúc nào để ngừng sử dụng chức năng này.</span><span class="sxs-lookup"><span data-stu-id="54a95-130">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
