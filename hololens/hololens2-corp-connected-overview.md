---
title: 部署指南–與 Dynamics 365 的公司連線 HoloLens 2 指南-總覽
description: 瞭解如何透過公司連接的網路，使用 Dynamics 365 指南註冊 HoloLens 2 裝置。
keywords: HoloLens、管理、公司連線、Dynamics 365 指南、AAD、Azure AD、MDM、Mobile 裝置管理
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: aboeger
ms.date: 03/24/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 3041a31e6a4f8b51385fa02dfddc21d56993721d
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308933"
---
# <a name="deployment-guide---corporate-connected-hololens-2-with-dynamics-365-guides---overview"></a><span data-ttu-id="8bc1a-104">部署指南-使用 Dynamics 365 指南的公司連線 HoloLens 2-總覽</span><span class="sxs-lookup"><span data-stu-id="8bc1a-104">Deployment Guide - Corporate Connected HoloLens 2 with Dynamics 365 Guides - Overview</span></span>

<span data-ttu-id="8bc1a-105">本指南可協助 IT 專業人員規劃及部署 Microsoft HoloLens 2 裝置，並使用 Dynamics 365 指南 (指南) 其組織。</span><span class="sxs-lookup"><span data-stu-id="8bc1a-105">This guide will help IT professionals plan for and deploy Microsoft HoloLens 2 devices with Dynamics 365 Guides (Guides) to their organization.</span></span> <span data-ttu-id="8bc1a-106">本指南適用于試驗和生產環境部署，類似于 [案例 B：在組織的網路指南中部署](https://docs.microsoft.com/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network) 。</span><span class="sxs-lookup"><span data-stu-id="8bc1a-106">This guide is great for pilots as well as production deployments and is similar to the [Scenario B: Deploy inside your organization's network](https://docs.microsoft.com/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network) guide.</span></span> <span data-ttu-id="8bc1a-107">測試您的概念證明之後，請使用本指南將 HoloLens 整合到您的組織中。</span><span class="sxs-lookup"><span data-stu-id="8bc1a-107">After testing your proof-of-concept, use this guide to move forward with integrating HoloLens into your organization.</span></span>

<span data-ttu-id="8bc1a-108">在本指南中，我們將討論如何將您的裝置註冊到現有的裝置管理、視需要套用授權，以及驗證您的終端使用者在裝置設定之後，是否能夠操作 Dynamics 365 指南，以及使用自訂的企業營運應用程式。</span><span class="sxs-lookup"><span data-stu-id="8bc1a-108">In this guide, we will cover how to enroll your devices into your existing device management, apply licenses as needed, and validate that your end users are able to operate a Dynamics 365 Guide, as well as use custom line of business apps, after device set up.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="8bc1a-109">必要條件</span><span class="sxs-lookup"><span data-stu-id="8bc1a-109">Prerequisites</span></span>

<span data-ttu-id="8bc1a-110">下列基礎結構應該已準備就緒：</span><span class="sxs-lookup"><span data-stu-id="8bc1a-110">The following infrastructure should already be in place:</span></span>
- <span data-ttu-id="8bc1a-111">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="8bc1a-111">Wi-Fi</span></span>
    - <span data-ttu-id="8bc1a-112">具有內部資源存取權的內部公司網路，以及網際網路或雲端服務的有限存取權</span><span class="sxs-lookup"><span data-stu-id="8bc1a-112">Internal corporate network with access to internal resources and limited access to the internet or Cloud services</span></span>
    - <span data-ttu-id="8bc1a-113">以裝置為基礎的憑證驗證。</span><span class="sxs-lookup"><span data-stu-id="8bc1a-113">Device-based certificate authentication.</span></span>
- <span data-ttu-id="8bc1a-114">Azure Active Directory (Azure AD) 加入 MDM 自動註冊 (Azure AD [P1 訂](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) 用帳戶) </span><span class="sxs-lookup"><span data-stu-id="8bc1a-114">Azure Active Directory (Azure AD) Join with MDM Auto Enrollment ([Azure AD P1 subscription](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) needed)</span></span>
- <span data-ttu-id="8bc1a-115">MDM (Intune) 受控</span><span class="sxs-lookup"><span data-stu-id="8bc1a-115">MDM (Intune) Managed</span></span>
    - <span data-ttu-id="8bc1a-116">透過 MDM 部署一或多個應用程式。</span><span class="sxs-lookup"><span data-stu-id="8bc1a-116">One or more applications are deployed via MDM.</span></span>
- <span data-ttu-id="8bc1a-117">網路</span><span class="sxs-lookup"><span data-stu-id="8bc1a-117">Network</span></span> 
    - <span data-ttu-id="8bc1a-118"> (SCEP 或 PKCS) 的憑證</span><span class="sxs-lookup"><span data-stu-id="8bc1a-118">Certificates (SCEP or PKCS)</span></span>
    - <span data-ttu-id="8bc1a-119">Proxy 組態</span><span class="sxs-lookup"><span data-stu-id="8bc1a-119">Proxy configuration</span></span>
- <span data-ttu-id="8bc1a-120">使用者以自己的公司帳戶登入 (Azure AD) </span><span class="sxs-lookup"><span data-stu-id="8bc1a-120">Users sign in with their own corporate account (Azure AD)</span></span>
    - <span data-ttu-id="8bc1a-121">支援每個裝置的單一或多個使用者。</span><span class="sxs-lookup"><span data-stu-id="8bc1a-121">Single or multiple users per device is supported.</span></span>
- <span data-ttu-id="8bc1a-122">根據特定使用案例套用的各種裝置鎖定設定層級，從完全開放到單一應用程式 Kiosk。</span><span class="sxs-lookup"><span data-stu-id="8bc1a-122">Varying levels of device lockdown configurations applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>

## <a name="guides-licensing-and-requirements"></a>[<span data-ttu-id="8bc1a-123">引導授權和需求</span><span class="sxs-lookup"><span data-stu-id="8bc1a-123">Guides Licensing and Requirements</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements#licensing-and-product-requirements)
- <span data-ttu-id="8bc1a-124">Azure AD 帳戶</span><span class="sxs-lookup"><span data-stu-id="8bc1a-124">Azure AD account</span></span>
- <span data-ttu-id="8bc1a-125">Dynamics 365 會引導應用程式 PC 和 HoloLens</span><span class="sxs-lookup"><span data-stu-id="8bc1a-125">Dynamics 365 Guides applications PC and HoloLens</span></span>
- <span data-ttu-id="8bc1a-126">Dynamics 365 指南訂用帳戶</span><span class="sxs-lookup"><span data-stu-id="8bc1a-126">Dynamics 365 Guides subscription</span></span>
    - <span data-ttu-id="8bc1a-127">Microsoft Dataverse (包含) </span><span class="sxs-lookup"><span data-stu-id="8bc1a-127">Microsoft Dataverse (included)</span></span>
    - <span data-ttu-id="8bc1a-128">Power Apps (包含) </span><span class="sxs-lookup"><span data-stu-id="8bc1a-128">Power Apps (included)</span></span>
- <span data-ttu-id="8bc1a-129">Power BI Desktop</span><span class="sxs-lookup"><span data-stu-id="8bc1a-129">Power BI Desktop</span></span>
- <span data-ttu-id="8bc1a-130">網路連線</span><span class="sxs-lookup"><span data-stu-id="8bc1a-130">Network Connectivity</span></span>

![Corp 連接的網狀圖表](./images/corpconnected-diagHL2-guides.png)

## <a name="stages-of-deployment"></a><span data-ttu-id="8bc1a-132">部署階段</span><span class="sxs-lookup"><span data-stu-id="8bc1a-132">Stages of Deployment</span></span>
### <a name="prepare"></a><span data-ttu-id="8bc1a-133">準備</span><span class="sxs-lookup"><span data-stu-id="8bc1a-133">Prepare</span></span>
> [!div class="checklist"]
>- [<span data-ttu-id="8bc1a-134">瞭解 HoloLens 2 裝置的基礎結構基本資訊。</span><span class="sxs-lookup"><span data-stu-id="8bc1a-134">Learn about the infrastructure essentials for HoloLens 2 devices.</span></span>](hololens2-corp-connected-prepare.md#infrastructure-essentials)
>- [<span data-ttu-id="8bc1a-135">如果您沒有 Azure AD，請進一步瞭解，並設定一個。</span><span class="sxs-lookup"><span data-stu-id="8bc1a-135">Learn more about Azure AD and set up one if you don't have it.</span></span>](hololens2-corp-connected-prepare.md#azure-active-directory)
>- [<span data-ttu-id="8bc1a-136">瞭解身分識別管理，以及如何以最佳方式設定 Azure AD 帳戶。</span><span class="sxs-lookup"><span data-stu-id="8bc1a-136">Learn about Identity management and how to best set up Azure AD accounts.</span></span>](hololens2-corp-connected-prepare.md#identity-management)
>- [<span data-ttu-id="8bc1a-137">如果您還沒準備好，請深入瞭解 MDM 並設定 Intune。</span><span class="sxs-lookup"><span data-stu-id="8bc1a-137">Learn more about MDM and set up with Intune if you don't already have one ready.</span></span>](hololens2-corp-connected-prepare.md#mobile-device-management)
>- [<span data-ttu-id="8bc1a-138">熟悉以憑證為基礎的 Wi-fi。</span><span class="sxs-lookup"><span data-stu-id="8bc1a-138">Familiarize yourself with certificate-based Wi-Fi.</span></span>](hololens2-corp-connected-prepare.md#certificates)
>- [<span data-ttu-id="8bc1a-139">熟悉 Proxy。</span><span class="sxs-lookup"><span data-stu-id="8bc1a-139">Familiarize yourself with Proxy.</span></span>](hololens2-corp-connected-prepare.md#proxy)
>- [<span data-ttu-id="8bc1a-140">瞭解您可以如何使用企業營運應用程式。</span><span class="sxs-lookup"><span data-stu-id="8bc1a-140">Understand how you can use Line of Business Apps.</span></span>](hololens2-corp-connected-prepare.md#line-of-business-apps)
>- [<span data-ttu-id="8bc1a-141">深入瞭解您的組織可以使用指南的方式。</span><span class="sxs-lookup"><span data-stu-id="8bc1a-141">Learn more about the way you can use Guides for your organization.</span></span>](hololens2-corp-connected-prepare.md#guides-playbook)
### <a name="configure"></a><span data-ttu-id="8bc1a-142">設定</span><span class="sxs-lookup"><span data-stu-id="8bc1a-142">Configure</span></span>
> [!div class="checklist"]
>- [<span data-ttu-id="8bc1a-143">如何建立使用者和群組。</span><span class="sxs-lookup"><span data-stu-id="8bc1a-143">How to create users and groups.</span></span>](hololens2-corp-connected-configure.md#azure-users-and-groups)
>- [<span data-ttu-id="8bc1a-144">如何設定自動註冊。</span><span class="sxs-lookup"><span data-stu-id="8bc1a-144">How to set up Auto Enrollment.</span></span>](hololens2-corp-connected-configure.md#auto-enrollment-on-hololens-2)
>- [<span data-ttu-id="8bc1a-145">如何設定 Wi-Fi 的憑證和設定檔，以進行公司 Wi-Fi 的連線能力。</span><span class="sxs-lookup"><span data-stu-id="8bc1a-145">How to set up Wi-Fi certificates and profiles for Corporate Wi-Fi Connectivity.</span></span>](hololens2-corp-connected-configure.md#corporate-wi-fi-connectivity)
>- [<span data-ttu-id="8bc1a-146">上傳並指派企業營運 (LOB) 應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="8bc1a-146">Upload and Assign Line of Business (LOB) App packages.</span></span>](hololens2-corp-connected-configure.md#app-deployment)
>- [<span data-ttu-id="8bc1a-147">設定 Dynamics 365 指南。</span><span class="sxs-lookup"><span data-stu-id="8bc1a-147">Setup Dynamics 365 Guides.</span></span>](hololens2-corp-connected-configure.md#setup-guides-application-licenses-dataverse-and-authoring)
>- [<span data-ttu-id="8bc1a-148">如何設定 Kiosk 模式 (選擇性) 。</span><span class="sxs-lookup"><span data-stu-id="8bc1a-148">How to configure Kiosk Mode (optional).</span></span>](hololens2-corp-connected-configure.md#optional-kiosk-mode)
>- [<span data-ttu-id="8bc1a-149">如何設定 WDAC (選擇性) 。</span><span class="sxs-lookup"><span data-stu-id="8bc1a-149">How to configure WDAC (optional).</span></span>](hololens2-corp-connected-configure.md#optional-wdac)
### <a name="deploy"></a><span data-ttu-id="8bc1a-150">部署</span><span class="sxs-lookup"><span data-stu-id="8bc1a-150">Deploy</span></span>
> [!div class="checklist"]
>-  [<span data-ttu-id="8bc1a-151">透過裝置和 MDM 驗證註冊。</span><span class="sxs-lookup"><span data-stu-id="8bc1a-151">Validate enrollment via device and MDM.</span></span>](hololens2-corp-connected-deploy.md#enrollment-validation)
>-  [<span data-ttu-id="8bc1a-152">驗證 Wi-Fi 憑證。</span><span class="sxs-lookup"><span data-stu-id="8bc1a-152">Validate Wi-Fi certificates.</span></span>](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation)
>-  [<span data-ttu-id="8bc1a-153">驗證 LOB 應用程式安裝。</span><span class="sxs-lookup"><span data-stu-id="8bc1a-153">Validate LOB app install.</span></span>](hololens2-corp-connected-deploy.md#validate-lob-app-install)
>-  [<span data-ttu-id="8bc1a-154">透過撰寫和操作驗證輔助線。</span><span class="sxs-lookup"><span data-stu-id="8bc1a-154">Validate Guides via authoring and operating.</span></span>](hololens2-corp-connected-deploy.md#validate-dynamics-365-guides)
### <a name="maintain"></a><span data-ttu-id="8bc1a-155">維護</span><span class="sxs-lookup"><span data-stu-id="8bc1a-155">Maintain</span></span>
> [!div class="checklist"]
>- [<span data-ttu-id="8bc1a-156">更新 HoloLens 2。</span><span class="sxs-lookup"><span data-stu-id="8bc1a-156">Update HoloLens 2.</span></span>](hololens2-corp-connected-maintain.md#update-hololens)
>- [<span data-ttu-id="8bc1a-157">如何更新 (儲存應用程式) 的指南。</span><span class="sxs-lookup"><span data-stu-id="8bc1a-157">How to update Guides (store apps).</span></span>](hololens2-corp-connected-maintain.md#how-to-update-dynamics-365-guides-and-other-store-apps)
>- [<span data-ttu-id="8bc1a-158">如何更新 LOB 應用程式。</span><span class="sxs-lookup"><span data-stu-id="8bc1a-158">How to update LOB apps.</span></span>](hololens2-corp-connected-maintain.md#how-to-update-lob-apps) 
>- [<span data-ttu-id="8bc1a-159">開發計畫。</span><span class="sxs-lookup"><span data-stu-id="8bc1a-159">Development plan.</span></span>](hololens2-corp-connected-maintain.md#development-plan) 
>- [<span data-ttu-id="8bc1a-160">提出支援方案。</span><span class="sxs-lookup"><span data-stu-id="8bc1a-160">Making a support plan.</span></span>](hololens2-corp-connected-maintain.md#support-plan)
>- [<span data-ttu-id="8bc1a-161">裝置管理選項。</span><span class="sxs-lookup"><span data-stu-id="8bc1a-161">Device management options.</span></span>](hololens2-corp-connected-maintain.md#device-management)

## <a name="next-step"></a><span data-ttu-id="8bc1a-162">後續步驟</span><span class="sxs-lookup"><span data-stu-id="8bc1a-162">Next step</span></span> 
> [!div class="nextstepaction"]
> [<span data-ttu-id="8bc1a-163">公司連線部署-準備</span><span class="sxs-lookup"><span data-stu-id="8bc1a-163">Corporate connected deployment - Prepare</span></span>](hololens2-corp-connected-prepare.md)
