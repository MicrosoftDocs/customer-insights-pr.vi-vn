---
title: Làm việc với API
description: Sử dụng API và hiểu các giới hạn.
ms.date: 12/04/2020
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 5a03e916676800afdd8692da865a1060952d5c4f
ms.sourcegitcommit: b50c754481d0af6d0cf4b550775d7b31d95846ef
ms.translationtype: HT
ms.contentlocale: vi-VN
ms.lasthandoff: 12/06/2020
ms.locfileid: "4689156"
---
# <a name="work-with-customer-insights-apis"></a>Làm việc với API Customer Insights

Dynamics 365 Customer Insights cung cấp các API để tạo ứng dụng dựa trên dữ liệu của bạn trong Customer Insights.

> [!IMPORTANT]
> Thông tin chi tiết về các API này được liệt kê trên [Tham chiếu API Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Những thông tin này bao gồm thông tin bổ sung về hoạt động, tham số và phản hồi.

Bài viết này hướng dẫn bạn truy cập vào các API Customer Insights, tạo Đăng ký ứng dụng Azure và giúp bạn bắt đầu với các thư viện ứng dụng khách có sẵn.

## <a name="get-started-trying-the-customer-insights-apis"></a>Bắt đầu dùng thử các API Customer Insights

1. [Đăng nhập](https://home.ci.ai.dynamics.com) vào Customer Insights. Nếu bạn chưa có đăng ký, [hãy đăng ký phiên bản dùng thử của Customer Insights](https://aka.ms/tryci).

1. Để bật API trên môi trường Customer Insights của bạn, hãy truy cập **Quản trị viên** > **Quyền hạn**. Bạn sẽ cần quyền quản trị viên để làm như vậy.

1. Đi đến **API** và chọn nút **Bật**.    
   Việc bật API sẽ tạo khóa đăng ký chính và phụ cho phiên bản của bạn, khóa này được sử dụng trong các yêu cầu API. Bạn có thể tạo lại các khóa bằng cách chọn **Tạo lại khóa chính** hoặc **Tạo lại khóa phụ** trên **Quản trị viên** > **Quyền** > **API**.

   :::image type="content" source="media/enable-apis.gif" alt-text="Bật API Customer Insights":::

1. Chọn **Khám phá API** để dùng thử các API.

1. Chọn một hoạt động API và chọn **Dùng thử**.

1. Trong ngăn bên, đặt giá trị trong menu thả xuống **Thẩm quyền** thành **ẩn**. Tiêu đề `Authorization` được thêm mã thông báo mang chuyển. Khóa đăng ký của bạn sẽ được tự động điền.
  
1. Theo tùy chọn, thêm tất cả các tham số truy vấn cần thiết.

1. Cuộn xuống cuối ngăn bên và chọn **Gửi**.

Phản hồi HTTP sẽ sớm xuất hiện bên dưới.

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>Tạo đăng ký ứng dụng mới trong cổng thông tin Azure

Các bước này giúp bạn bắt đầu sử dụng API Customer Insights trong ứng dụng Azure bằng các quyền được ủy quyền. Đảm bảo đã hoàn thành [Phần bắt đầu](#get-started-trying-the-customer-insights-apis) trước tiên.

1. Đăng nhập vào [Cổng thông tin Azure](https://portal.azure.com) bằng tài khoản có thể truy cập dữ liệu Customer Insights.

1. Ở bên trái, hãy chọn **Đăng ký ứng dụng**.

1. Chọn **Đăng ký mới** sẽ cung cấp tên ứng dụng và chọn loại tài khoản.
   Theo tùy chọn, thêm URL chuyển hướng. http://localhost là đủ để phát triển một ứng dụng trên máy tính cục bộ của bạn.

1. Trên đăng ký ứng dụng mới, hãy đi tới **Quyền API**.

1. Chọn **Thêm quyền** và chọn **Customer Insights** trong ngăn bên.

1. Đối với **Loại quyền**, hãy chọn **Quyền được ủy quyền** và chọn quyền **user_impersonation**.

1. Chọn **Thêm quyền**. Nếu bạn cần truy cập API mà không cần người dùng đăng nhập, hãy xem lại phần [Quyền của ứng dụng giữa các máy chủ](#server-to-server-application-permissions).

1. Chọn **Cấp quyền của quản trị viên cho...** để hoàn thành đăng ký ứng dụng.

Bạn có thể sử dụng ID ứng dụng/máy khách cho đăng ký ứng dụng này với Microsoft Authentication Library (MSAL) để nhận mã thông báo mang chuyển để gửi kèm theo yêu cầu của bạn đến API.

Để biết thêm thông tin về MSAL, hãy xem [Tổng quan về Microsoft Authentication Library (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview).

Để biết thêm thông tin về đăng ký ứng dụng trong Azure, hãy xem [Trải nghiệm đăng ký ứng dụng cổng Azure mới](https://docs.microsoft.com/azure/active-directory/develop/app-registration-portal-training-guide).

Để biết thông tin về cách sử dụng API thư viện máy khách của chúng tôi, hãy xem [Thư viện máy khách Customer Insights](#customer-insights-client-libraries).

### <a name="server-to-server-application-permissions"></a>Quyền của ứng dụng giữa các máy chủ

[Phần đăng ký ứng dụng](#create-a-new-app-registration-in-the-azure-portal) cho biết cách đăng ký ứng dụng cần người dùng đăng nhập để xác thực. Tìm hiểu cách tạo đăng ký ứng dụng không cần người dùng tương tác và có thể chạy trên máy chủ.

1. Khi đăng ký ứng dụng của bạn trong cổng Azure, hãy đi tới **Quyền API**.

1. Chọn **Thêm quyền** và chọn **Customer Insights** trong ngăn bên.

1. Đối với **Loại quyền**, hãy chọn **Quyền của ứng dụng** và chọn quyền **CustomerInsights.Api.All**.

1. Chọn **Thêm quyền**.

1. Để cung cấp sự đồng ý của quản trị viên đối với quyền của ứng dụng này, bạn cần thêm Tên dịch vụ chính.

   1. Cài đặt mô-đun Azure Active Directory (AD) PowerShell: `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`
   1. Kết nối với tài khoản AD: `Connect-AzureAD -TenantId <your tenant id>`. Bạn có thể tìm thấy ID đối tượng thuê của mình trên **Tổng quan** > **Azure Active Directory**.
   1. Chạy lệnh sau để thêm Tên dịch vụ chính Azure AD: `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` Tham số AppId gắn liền với ứng dụng API Customer Insights.

   :::image type="content" source="media/azureAD-service-principal.png" alt-text="Mẫu tên dịch vụ chính":::

1. Quay lại **Quyền API** cho đăng ký ứng dụng của bạn.

1. Chọn **Cấp quyền của quản trị viên cho...** để hoàn thành đăng ký ứng dụng.

1. Để kết thúc, chúng tôi phải thêm tên đăng ký ứng dụng làm người dùng trong Customer Insights.    
   Mở Customer Insights, đi tới **Quản trị viên** > **Quyền** và chọn **Thêm người dùng**.

1. Tìm kiếm tên đăng ký ứng dụng của bạn, chọn tên đó từ kết quả tìm kiếm và chọn **Lưu**.

## <a name="customer-insights-client-libraries"></a>Thư viện máy khách Customer Insights

Phần này giúp bạn bắt đầu sử dụng các thư viện máy khách có sẵn cho các API Customer Insights.

### <a name="c-nuget"></a>C# NuGet

Tìm hiểu cách bắt đầu sử dụng thư viện máy khách C# từ NuGet.org. Để biết thêm thông tin về gói NuGet, xem [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/). Hiện tại, gói này dành cho framework netstandard2.0 và netcoreapp2.0.

#### <a name="add-the-c-client-library-to-a-c-project"></a>Thêm thư viện máy khách C# vào dự án C#

1. Trong Visual Studio, mở **Trình quản lý gói NuGet** cho dự án của bạn.

1. Tìm kiếm **Microsoft.Dynamics.CustomerInsights.Api**.

1. Chọn **Cài đặt** để thêm gói vào dự án.
   Ngoài ra, hãy chạy lệnh này trong **Bảng điều khiển trình quản lý gói NuGet**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Thêm gói NuGet vào dự án Visual Studio":::

#### <a name="use-the-c-client-library"></a>Sử dụng thư viện máy khách C#

1. Sử dụng [Microsoft Authentication Library (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview) để nhận `AccessToken` bằng cách sử dụng [đăng ký ứng dụng Azure](#create-a-new-app-registration-in-the-azure-portal).

1. Sau khi xác thực thành công và có được mã thông báo, hãy tạo mã mới hoặc sử dụng `HttpClient` hiện tại với **DefaultRequestHeaders "Authorization"** bổ sung được đặt thành **<access token> mang chuyển** và **Ocp-Apim-Subscription-Key** được đặt thành [**khóa đăng ký** từ môi trường Customer Insights của bạn](#get-started-trying-the-customer-insights-apis).    
   Đặt lại tiêu đề **Ủy quyền** khi thích hợp. Ví dụ: khi mã thông báo hết hạn.

1. Chuyển `HttpClient` này vào việc xây dựng máy khách `CustomerInsights`.

   :::image type="content" source="media/httpclient-sample.png" alt-text="Mẫu httpclient":::

1. Thực hiện cuộc gọi với máy khách đến "phương pháp mở rộng", ví dụ: `GetAllInstancesAsync`. Nếu truy cập vào `Microsoft.Rest.HttpOperationResponse` cơ sở được ưu tiên, hãy sử dụng "phương thức thông báo http", ví dụ: `GetAllInstancesWithHttpMessagesAsync`.

1. Phản hồi sẽ có thể thuộc loại `object` vì phương thức này có thể trả về nhiều loại (ví dụ: `IList<InstanceInfo>` và `ApiErrorResult`). Để kiểm tra loại trả về, bạn có thể truyền an toàn các đối tượng vào các loại phản hồi được chỉ định trên [Trang chi tiết API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) cho hoạt động đó.    
   Nếu cần thêm thông tin về yêu cầu, hãy sử dụng **phương thức thông báo http** để truy cập đối tượng phản hồi thô.
