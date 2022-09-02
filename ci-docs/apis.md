---
title: Làm việc với API Customer Insights
description: Sử dụng API và hiểu các giới hạn.
ms.date: 08/31/2022
ms.reviewer: wimohabb
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: f499bff4a6ac07a88ff0f773b9cee77dc74989e8
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: MT
ms.contentlocale: vi-VN
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387366"
---
# <a name="work-with-customer-insights-apis"></a>Làm việc với API Customer Insights

Dynamics 365 Customer Insights cung cấp các API để bạn xây dựng ứng dụng dựa trên dữ liệu của mình trong Customer Insights.

> [!IMPORTANT]
> Thông tin chi tiết về các API này được liệt kê trên [Tham chiếu API Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Những thông tin này bao gồm thông tin bổ sung về hoạt động, tham số và phản hồi.

Hãy thử các API của Customer Insights, tạo Đăng ký ứng dụng Azure và bắt đầu với các thư viện khách hàng.

## <a name="get-started-trying-the-customer-insights-apis"></a>Bắt đầu dùng thử các API Customer Insights

Bật API thông tin chi tiết về khách hàng và dùng thử chúng. Quản trị viên Thông tin chi tiết về khách hàng phải cho phép truy cập API vào Thông tin chi tiết về khách hàng. Sau khi quyền truy cập được bật, bất kỳ người dùng nào cũng có thể sử dụng API với khóa đăng ký.

1. [Đăng nhập](https://home.ci.ai.dynamics.com) vào Customer Insights. Nếu bạn chưa có đăng ký, [hãy đăng ký phiên bản dùng thử của Customer Insights](https://aka.ms/tryci).

1. Đi đến **Quản trị viên** > **Bảo vệ** và chọn **API** chuyển hướng.

1. Nếu quyền truy cập API vào môi trường chưa được thiết lập, hãy chọn **Cho phép** .

   Việc bật API sẽ tạo khóa đăng ký chính và phụ cho phiên bản của bạn, khóa này được sử dụng trong các yêu cầu API. Để tạo lại các phím, hãy chọn **Tạo lại chính** hoặc **Tạo lại thứ cấp** trên **API** chuyển hướng.

1. Lựa chọn [**Khám phá các API của chúng tôi**](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) để thử các API.

1. Tìm kiếm và chọn một hoạt động API và chọn **Thử nó**.

   :::image type="content" source="media/try-api.png" alt-text="Cách thử nghiệm API.":::

1. Trong ngăn bên, đặt giá trị trong menu thả xuống **Thẩm quyền** thành **ẩn**. Tiêu đề `Authorization` được thêm với một mã thông báo mang chuyển. Khóa đăng ký của bạn được tự động điền.
  
1. Theo tùy chọn, thêm tất cả các tham số truy vấn cần thiết.

1. Cuộn xuống cuối ngăn bên và chọn **Gửi**.

   Phản hồi HTTP hiển thị ở cuối ngăn.

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>Tạo đăng ký ứng dụng mới trong cổng thông tin Azure

Tạo một cái mới [đăng ký ứng dụng](/graph/auth-register-app-v2) để sử dụng API thông tin chi tiết về khách hàng trong ứng dụng Azure bằng cách sử dụng các quyền được ủy quyền.

1. Hoàn thành việc [Phần bắt đầu](#get-started-trying-the-customer-insights-apis).

1. Đăng nhập vào [Cổng thông tin Azure](https://portal.azure.com) bằng tài khoản có thể truy cập dữ liệu Customer Insights.

1. Tìm kiếm và sau đó chọn **Đăng ký ứng dụng**.

1. Chọn **Đăng ký mới** để cung cấp tên ứng dụng và chọn loại tài khoản.

   Theo tùy chọn, thêm URL chuyển hướng. http://localhost là đủ để phát triển một ứng dụng trên máy tính cục bộ của bạn.

1. Chọn **Đăng ký**.

1. Trên đăng ký ứng dụng mới, hãy đi tới **Quyền API**.

1. Lựa chọn **Thêm một quyền** và chọn **Dynamics 365 AI cho thông tin chi tiết về khách hàng** trong ngăn bên.

1. Đối với **Loại quyền**, chọn **Quyền được ủy thác** và sau đó chọn quyền **user_impersonation**.

1. Chọn **Thêm quyền**.

1. Chọn **Cấp quyền của quản trị viên cho...** để hoàn thành đăng ký ứng dụng.

1. Để truy cập API mà không cần người dùng đăng nhập, hãy truy cập [Quyền của ứng dụng từ máy chủ đến máy chủ](#server-to-server-application-permissions).

Bạn có thể sử dụng ID ứng dụng / ứng dụng khách để đăng ký ứng dụng này với [Thư viện xác thực Microsoft (MSAL)](/azure/active-directory/develop/msal-overview) để lấy mã thông báo mang tên để gửi cùng với yêu cầu của bạn tới API.

<!-- :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

Để biết thông tin về cách sử dụng API trong thư viện máy khách của chúng tôi, hãy xem [Thư viện máy khách Customer Insights](#customer-insights-client-libraries).

### <a name="server-to-server-application-permissions"></a>Quyền của ứng dụng giữa các máy chủ

Tạo đăng ký ứng dụng không cần sự tương tác của người dùng và có thể chạy trên máy chủ.

1. Khi đăng ký ứng dụng của bạn trong cổng Azure, hãy đi tới **Quyền API**.

1. Chọn **Thêm quyền**.

1. Chọn tab **API mà tổ chức của tôi sử dụng** và chọn **Dynamics 365 AI cho Customer Insights** từ danh sách.

1. Đối với **Loại quyền**, chọn **Quyền ứng dụng** và sau đó chọn quyền **CustomerInsights.Api.All**.

1. Chọn **Thêm quyền**.

1. Quay lại **Quyền API** cho đăng ký ứng dụng của bạn.

1. Chọn **Cấp quyền của quản trị viên cho...** để hoàn thành đăng ký ứng dụng.

   <!--  :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

1. Thêm tên đăng ký ứng dụng với tư cách là người dùng trong Thông tin chi tiết về khách hàng.

   1. Mở Thông tin chi tiết về khách hàng, truy cập **Quản trị viên** > **Bảo vệ** và chọn **Thêm người dùng**.

   1. Tìm kiếm tên đăng ký ứng dụng của bạn, chọn tên đó từ kết quả tìm kiếm và chọn **Lưu**.

## <a name="sample-queries"></a>Truy vấn mẫu

Để có danh sách ngắn các truy vấn mẫu OData hoạt động với các API, hãy xem [Ví dụ về truy vấn OData](odata-examples.md).

## <a name="customer-insights-client-libraries"></a>Thư viện máy khách Customer Insights

Bắt đầu sử dụng các thư viện khách hàng có sẵn cho API Thông tin chi tiết về khách hàng. Tất cả mã nguồn thư viện và các ứng dụng mẫu có thể được tìm thấy trên [Trang GitHub Customer Insights](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).

### <a name="c-nuget"></a>C# NuGet

Sử dụng các thư viện máy khách C # từ NuGet .org. Hiện tại, gói này nhắm mục tiêu các khung netstandard2.0 và netcoreapp2.0. Để biết thêm thông tin về NuGet gói, xem [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).

#### <a name="add-the-c-client-library-to-a-c-project"></a>Thêm thư viện máy khách C# vào dự án C#

1. Trong Visual Studio, mở **Trình quản lý gói NuGet** cho dự án của bạn.

1. Tìm kiếm **Microsoft.Dynamics.CustomerInsights.Api**.

1. Chọn **Cài đặt** để thêm gói vào dự án.

   Ngoài ra, hãy chạy lệnh này trong **Bảng điều khiển trình quản lý gói NuGet**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`

   <!--  :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Add NuGet package to Visual Studio project."::: -->

#### <a name="use-the-c-client-library"></a>Sử dụng thư viện máy khách C#

1. Sử dụng [Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview) để nhận `AccessToken` bằng cách sử dụng [đăng ký ứng dụng Azure](#create-a-new-app-registration-in-the-azure-portal).

1. Sau khi xác thực thành công và có được mã thông báo, hãy tạo mã mới hoặc sử dụng`HttpClient` với **DefaultRequestHeaders "Ủy quyền"** đặt thành **Mang "mã thông báo truy cập"** và **Ocp-Apim-Đăng ký-Khóa** đặt thành [**khóa đăng ký** từ môi trường Thông tin chi tiết về khách hàng của bạn](#get-started-trying-the-customer-insights-apis).   

   Đặt lại tiêu đề **Ủy quyền** khi thích hợp. Ví dụ: khi mã thông báo hết hạn.

1. Chuyển `HttpClient` này vào việc xây dựng máy khách `CustomerInsights`.

   <!--   :::image type="content" source="media/httpclient-sample.png" alt-text="Sample of httpclient."::: -->

1. Thực hiện cuộc gọi với máy khách đến "phương pháp mở rộng", ví dụ: `GetAllInstancesAsync`. Nếu truy cập vào cơ sở`Microsoft.Rest.HttpOperationResponse` được ưu tiên, hãy sử dụng "phương pháp nhắn tin http", ví dụ:`GetAllInstancesWithHttpMessagesAsync`.

1. Câu trả lời có khả năng`object` nhập vì phương thức có thể trả về nhiều kiểu (ví dụ:`IList<InstanceInfo>` và`ApiErrorResult`). Để kiểm tra kiểu trả về, hãy sử dụng các đối tượng trong kiểu phản hồi được chỉ định trên [Trang chi tiết API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) cho hoạt động đó.

   Nếu cần thêm thông tin về yêu cầu, hãy sử dụng **phương thức thông báo http** để truy cập đối tượng phản hồi thô.

### <a name="nodejs-package"></a>Gói NodeJS

Sử dụng các thư viện máy khách NodeJS có sẵn thông qua NPM: https://www.npmjs.com/package/@microsoft/customerinsights

### <a name="python-package"></a>Gói Python

Sử dụng các thư viện máy khách Python có sẵn thông qua PyPi: https://pypi.org/project/customerinsights/

[!INCLUDE [footer-include](includes/footer-banner.md)]
