---
title: Windows Autopilot HoloLens 2 的註冊支援
description: 瞭解如何在 HoloLens 2 裝置上取得 Autopilot 的註冊支援。
author: joyjaz
ms.author: v-jjaswinski
ms.date: 5/20/2021
ms.prod: hololens
ms.topic: article
ms.custom:
- CI 116283
- CSSTroubleshooting
audience: ITPro
ms.localizationpriority: high
keywords: 自動駕駛儀
manager: ylempidakis
ms.openlocfilehash: cdd2ab68905d5cc82b1c5ccc50640112e857f2f4
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/25/2021
ms.locfileid: "110398956"
---
# <a name="hololens-2-registration-support-for-autopilot"></a><span data-ttu-id="5015a-104">Autopilot 的 HoloLens 2 註冊支援</span><span class="sxs-lookup"><span data-stu-id="5015a-104">HoloLens 2 Registration Support for Autopilot</span></span>

<span data-ttu-id="5015a-105">客戶與 Microsoft 雲端解決方案提供者 (Csp) 現在可以直接提交要求至 Microsoft 支援服務，以註冊 HoloLens 2 裝置。</span><span class="sxs-lookup"><span data-stu-id="5015a-105">Customers and Microsoft Cloud Solution Providers (CSPs) can now register HoloLens 2 devices by directly submitting requests to Microsoft Support.</span></span> <span data-ttu-id="5015a-106">本頁概述下列支援的 Autopilot 註冊案例需求：</span><span class="sxs-lookup"><span data-stu-id="5015a-106">This page outlines the requirements for the following supported Autopilot registration scenarios:</span></span>

- <span data-ttu-id="5015a-107">**HoloLens 2 裝置 Autopilot 註冊**。</span><span class="sxs-lookup"><span data-stu-id="5015a-107">**HoloLens 2 Device Autopilot Registration**.</span></span> <span data-ttu-id="5015a-108">提交要求以向 Windows Autopilot 註冊 HoloLens 2 裝置。</span><span class="sxs-lookup"><span data-stu-id="5015a-108">Submits request to register HoloLens 2 devices into Windows Autopilot.</span></span>
- <span data-ttu-id="5015a-109">**HoloLens 2 裝置硬體雜湊要求**。</span><span class="sxs-lookup"><span data-stu-id="5015a-109">**HoloLens 2 Device Hardware Hash Request**.</span></span> <span data-ttu-id="5015a-110">將要求提交給 Microsoft 支援服務，以提供硬體雜湊，讓客戶或 Csp 可透過 Microsoft Intune 或 Microsoft 合作夥伴中心來自行註冊裝置。</span><span class="sxs-lookup"><span data-stu-id="5015a-110">Submits request to Microsoft Support to provide you with hardware hashes that customers or CSPs can use to self-register devices via Microsoft Intune or the Microsoft Partner Center.</span></span>
- <span data-ttu-id="5015a-111">**HoloLens 2 裝置 Autopilot 取消註冊**。</span><span class="sxs-lookup"><span data-stu-id="5015a-111">**HoloLens 2 Device Autopilot Deregistration**.</span></span> <span data-ttu-id="5015a-112">從 Windows Autopilot 提交刪除裝置的要求，通常用於裝置終止案例。</span><span class="sxs-lookup"><span data-stu-id="5015a-112">Submits request to delete devices from Windows Autopilot, typically used in device end of life scenarios.</span></span>

<span data-ttu-id="5015a-113">下表詳細說明將註冊要求提交給 Microsoft 支援服務 *之前* 需要收集的資訊。</span><span class="sxs-lookup"><span data-stu-id="5015a-113">The following table details the information you will need to collect *prior* to submitting registration requests to Microsoft Support.</span></span>

| <span data-ttu-id="5015a-114">必要資訊</span><span class="sxs-lookup"><span data-stu-id="5015a-114">Required Information</span></span> | <span data-ttu-id="5015a-115">描述</span><span class="sxs-lookup"><span data-stu-id="5015a-115">Description</span></span> | <span data-ttu-id="5015a-116">Autopilot 註冊</span><span class="sxs-lookup"><span data-stu-id="5015a-116">Autopilot Registration</span></span>  | <span data-ttu-id="5015a-117">硬體雜湊要求</span><span class="sxs-lookup"><span data-stu-id="5015a-117">Hardware Hash Request</span></span> | <span data-ttu-id="5015a-118">Autopilot 取消註冊</span><span class="sxs-lookup"><span data-stu-id="5015a-118">Autopilot Deregistration</span></span> |
------------|-------------------------------|--------------------------------------------------|------------------------------|--------------------------------|
|  <span data-ttu-id="5015a-119">Azure Active Directory 租使用者識別碼</span><span class="sxs-lookup"><span data-stu-id="5015a-119">Azure Active Directory Tenant ID</span></span>    |    <span data-ttu-id="5015a-120">您 Azure Active Directory 租使用者識別碼是 (GUID) 的全域唯一識別碼，與您的組織名稱或網域不同。</span><span class="sxs-lookup"><span data-stu-id="5015a-120">Your Azure Active Directory tenant ID is a globally unique identifier (GUID) that is different than your organization name or domain.</span></span>    <span data-ttu-id="5015a-121">若要尋找您的租使用者識別碼，請登入 [Azure 入口網站](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)。</span><span class="sxs-lookup"><span data-stu-id="5015a-121">To find your Tenant ID sign into the [Azure Portal](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>    |     <span data-ttu-id="5015a-122">✔️</span><span class="sxs-lookup"><span data-stu-id="5015a-122">✔️</span></span>                         |                              |                         <span data-ttu-id="5015a-123">✔️</span><span class="sxs-lookup"><span data-stu-id="5015a-123">✔️</span></span>                        |
|  <span data-ttu-id="5015a-124">Azure Active Directory 功能變數名稱</span><span class="sxs-lookup"><span data-stu-id="5015a-124">Azure Active Directory Domain Name</span></span>    |   <span data-ttu-id="5015a-125">您的最上層功能變數名稱;例如，contoso.com。</span><span class="sxs-lookup"><span data-stu-id="5015a-125">Your top-level domain name; for example, contoso.com.</span></span>    |     <span data-ttu-id="5015a-126">✔️</span><span class="sxs-lookup"><span data-stu-id="5015a-126">✔️</span></span>                         |                              |                         <span data-ttu-id="5015a-127">✔️</span><span class="sxs-lookup"><span data-stu-id="5015a-127">✔️</span></span>                        |
|  <span data-ttu-id="5015a-128">擁有權證明</span><span class="sxs-lookup"><span data-stu-id="5015a-128">Proof of Ownership</span></span>    |   <span data-ttu-id="5015a-129">以 PDF 格式上傳原始的銷售帳單或發票，以確認擁有權證明。</span><span class="sxs-lookup"><span data-stu-id="5015a-129">Verify proof of ownership by uploading the original bill of sale or invoice in PDF format.</span></span> <span data-ttu-id="5015a-130">不接受螢幕擷取畫面。</span><span class="sxs-lookup"><span data-stu-id="5015a-130">Screenshots are not accepted.</span></span> <span data-ttu-id="5015a-131">帳單或發票必須包含下列各項：裝置序號。</span><span class="sxs-lookup"><span data-stu-id="5015a-131">The bill of sale or invoice must include the following: Device serial numbers.</span></span> <span data-ttu-id="5015a-132">公司名稱。</span><span class="sxs-lookup"><span data-stu-id="5015a-132">Company name.</span></span>     |     <span data-ttu-id="5015a-133">✔️</span><span class="sxs-lookup"><span data-stu-id="5015a-133">✔️</span></span>                         |              <span data-ttu-id="5015a-134">✔️</span><span class="sxs-lookup"><span data-stu-id="5015a-134">✔️</span></span>                |                         <span data-ttu-id="5015a-135">✔️</span><span class="sxs-lookup"><span data-stu-id="5015a-135">✔️</span></span>                        |
|  <span data-ttu-id="5015a-136">裝置序號</span><span class="sxs-lookup"><span data-stu-id="5015a-136">Device serial numbers</span></span>    |   <span data-ttu-id="5015a-137">以 CSV 格式上傳 Excel 檔案，並在新行中使用每個裝置序號。</span><span class="sxs-lookup"><span data-stu-id="5015a-137">Upload Excel file in CSV format with each device serial number in a new line.</span></span>     |     <span data-ttu-id="5015a-138">✔️</span><span class="sxs-lookup"><span data-stu-id="5015a-138">✔️</span></span>                         |              <span data-ttu-id="5015a-139">✔️</span><span class="sxs-lookup"><span data-stu-id="5015a-139">✔️</span></span>                |                         <span data-ttu-id="5015a-140">✔️</span><span class="sxs-lookup"><span data-stu-id="5015a-140">✔️</span></span>                        |

## <a name="submit-support-requests"></a><span data-ttu-id="5015a-141">提交支援要求</span><span class="sxs-lookup"><span data-stu-id="5015a-141">Submit support requests</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="5015a-142">提交 HoloLens 2 的 Autopilot 註冊支援</span><span class="sxs-lookup"><span data-stu-id="5015a-142">Submit Autopilot Registration Support for HoloLens 2</span></span>](https://prod.support.services.microsoft.com/supportrequestform/0d8bf192-cab7-6d39-143d-5a17840b9f5f)
