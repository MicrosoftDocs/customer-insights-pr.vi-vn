---
title: Bảng thuật ngữ chức năng thông tin chuyên sâu về tương tác
description: Bảng chú giải thuật ngữ và khái niệm.
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 11/12/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: fd6513f66777f8be312c8b594d52836ac325f2825e9d019d2ba0f49c587cf8ca
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035762"
---
# <a name="engagement-insights-capability-glossary"></a>Bảng thuật ngữ chức năng thông tin chuyên sâu về tương tác

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Danh sách này xác định các thuật ngữ đã chọn xuất hiện trong chức năng thông tin chuyên sâu về tương tác của Dynamics 365 Customer Insights và trong tài liệu hỗ trợ của chức năng.

## <a name="base-event"></a>Sự kiện cơ sở

Sự kiện cơ sở là một tập hợp dữ liệu đại diện cho hoạt động trên một trang web, chẳng hạn như lượt xem trang hoặc nhấp chuột. 

## <a name="dimensions"></a>Thứ nguyên

Thứ nguyên là thuộc tính của sự kiện, có thể mô tả, lọc hoặc nhóm dữ liệu. Ví dụ: bạn có thể chọn *hệ điều hành (OS)*, *trình duyệt* hoặc *tên trang* làm thứ nguyên trong báo cáo.

## <a name="event"></a>Sự kiện

Trong phân tích kỹ thuật số, một sự kiện đại diện cho hành vi của người dùng. Sự kiện ghi lại khi người dùng xem một trang (xem sự kiện) hoặc tương tác với nội dung (sự kiện hành động). Dữ liệu hoạt động từ trang web của bạn được thu thập dưới dạng *sự kiện cơ sở*. Để báo cáo, bạn có thể quyết định các thuộc tính của dữ liệu mà bạn muốn hiển thị. Chế độ xem dữ liệu ảo này được gọi là *sự kiện tinh chỉnh*. 

## <a name="environment"></a>Môi trường

 Môi trường là không gian có thể chứa một hoặc nhiều không gian làm việc. Bạn có thể sử dụng môi trường để quản lý không gian làm việc và kết nối của mình với chức năng thông tin chuyên sâu về đối tượng của Customer Insights.

## <a name="member"></a>Thành viên

Thành viên của không gian làm việc là người dùng có thể truy cập vào không gian làm việc. Các thành viên có thể có các vai trò, cho phép người dùng quản lý không gian làm việc, dữ liệu và xem các báo cáo. Hiện nay, *Chủ sở hữu* là vai trò duy nhất có sẵn trong chức năng thông tin chuyên sâu về tương tác.

## <a name="metric"></a>Chỉ số

Chỉ số là một phép đo có thể định lượng được của dữ liệu được sử dụng để theo dõi hoặc đánh giá một quá trình. Số lượt xem trang và thời gian trung bình dành cho trang web là ví dụ về các chỉ số có liên quan.

## <a name="refined-event"></a>Sự kiện tinh chỉnh

Một sự kiện tinh chỉnh là một chế độ xem ảo của một sự kiện cơ sở được lọc theo các thuộc tính cụ thể của dữ liệu. Sử dụng các sự kiện tinh chỉnh nhằm đơn giản hóa sự kiện cơ sở để xuất hoặc xóa các thuộc tính khỏi sự kiện không cần thiết để hiển thị hoặc xuất.

## <a name="report"></a>Báo cáo

Báo cáo là một tập hợp các hình ảnh trực quan hóa dữ liệu giúp bạn đo lường và hiểu hành vi của người dùng. Chức năng thông tin chuyên sâu về tương tác bao gồm một số báo cáo được xác định trước cho các dự án web. Bạn cũng có thể tạo các báo cáo tùy chỉnh. 

## <a name="workspace"></a>Không gian làm việc

Không gian làm việc là cách bạn lưu trữ cũng như quản lý các sự kiện và báo cáo. Đó là nơi bạn có thể xem hoạt động của người dùng trong thời gian thực. Khi tạo không gian làm việc, bạn có thể chọn loại dữ liệu sẽ gửi đến không gian làm việc.


[!INCLUDE[footer-include](../includes/footer-banner.md)]