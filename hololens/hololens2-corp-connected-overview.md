---
title: 部署指南 – 使用 Dynamics 365 指南與公司連接的 HoloLens 2 - 概觀
description: 瞭解如何使用 Dynamics 365 指南，在公司已連接網路上註冊 HoloLens 2 裝置。
keywords: HoloLens，管理，公司關係，Dynamics 365 指南，AAD，Azure AD，MDM，行動裝置管理
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
ms.sourcegitcommit: d7c86ccad7be32f7223d4b801083798454fda740
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/25/2021
ms.locfileid: "11448529"
---
# <a name="deployment-guide---corporate-connected-hololens-2-with-dynamics-365-guides---overview"></a><span data-ttu-id="b371a-104">部署指南 - 使用 Dynamics 365 指南的公司聯通 HoloLens 2 - 概觀</span><span class="sxs-lookup"><span data-stu-id="b371a-104">Deployment Guide - Corporate Connected HoloLens 2 with Dynamics 365 Guides - Overview</span></span>

<span data-ttu-id="b371a-105">本指南可協助 IT 專業人員規劃 Microsoft HoloLens 2 裝置，並針對其組織部署 Dynamics 365 (指南) 指南。</span><span class="sxs-lookup"><span data-stu-id="b371a-105">This guide will help IT professionals plan for and deploy Microsoft HoloLens 2 devices with Dynamics 365 Guides (Guides) to their organization.</span></span> <span data-ttu-id="b371a-106">本指南適用于試驗及生產部署，與案例 B：部署在貴組織的網路指南 [中很](https://docs.microsoft.com/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network) 類似。</span><span class="sxs-lookup"><span data-stu-id="b371a-106">This guide is great for pilots as well as production deployments and is similar to the [Scenario B: Deploy inside your organization's network](https://docs.microsoft.com/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network) guide.</span></span> <span data-ttu-id="b371a-107">測試概念證明之後，請使用本指南，進一步將 HoloLens 整合至貴組織。</span><span class="sxs-lookup"><span data-stu-id="b371a-107">After testing your proof-of-concept, use this guide to move forward with integrating HoloLens into your organization.</span></span>

<span data-ttu-id="b371a-108">在本指南中，我們將涵蓋如何將您的裝置註冊到現有的裝置管理中、根據需要套用授權，以及驗證您的使用者是否能夠執行 Dynamics 365 指南，以及使用裝置設定後的自訂商務應用程式。</span><span class="sxs-lookup"><span data-stu-id="b371a-108">In this guide, we will cover how to enroll your devices into your existing device management, apply licenses as needed, and validate that your end users are able to operate a Dynamics 365 Guide, as well as use custom line of business apps, after device set up.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="b371a-109">必要條件</span><span class="sxs-lookup"><span data-stu-id="b371a-109">Prerequisites</span></span>

<span data-ttu-id="b371a-110">下列基礎結構應該已經就位：</span><span class="sxs-lookup"><span data-stu-id="b371a-110">The following infrastructure should already be in place:</span></span>
- <span data-ttu-id="b371a-111">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="b371a-111">Wi-Fi</span></span>
    - <span data-ttu-id="b371a-112">具有內部資源存取權的內部公司網路，以及網際網路或雲端服務有限存取權</span><span class="sxs-lookup"><span data-stu-id="b371a-112">Internal corporate network with access to internal resources and limited access to the internet or Cloud services</span></span>
    - <span data-ttu-id="b371a-113">裝置式憑證驗證。</span><span class="sxs-lookup"><span data-stu-id="b371a-113">Device-based certificate authentication.</span></span>
- <span data-ttu-id="b371a-114">Azure Active Directory (Azure AD) 加入 MDM 自動註冊 ([Azure AD P1](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) 訂閱) </span><span class="sxs-lookup"><span data-stu-id="b371a-114">Azure Active Directory (Azure AD) Join with MDM Auto Enrollment ([Azure AD P1 subscription](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) needed)</span></span>
- <span data-ttu-id="b371a-115">MDM (Intune) Managed</span><span class="sxs-lookup"><span data-stu-id="b371a-115">MDM (Intune) Managed</span></span>
    - <span data-ttu-id="b371a-116">一或多個應用程式會透過 MDM 部署。</span><span class="sxs-lookup"><span data-stu-id="b371a-116">One or more applications are deployed via MDM.</span></span>
- <span data-ttu-id="b371a-117">網路</span><span class="sxs-lookup"><span data-stu-id="b371a-117">Network</span></span> 
    - <span data-ttu-id="b371a-118">SCEP (PCCS) </span><span class="sxs-lookup"><span data-stu-id="b371a-118">Certificates (SCEP or PKCS)</span></span>
    - <span data-ttu-id="b371a-119">Proxy 設定</span><span class="sxs-lookup"><span data-stu-id="b371a-119">Proxy configuration</span></span>
- <span data-ttu-id="b371a-120">使用者使用自己的公司帳戶 (Azure AD) </span><span class="sxs-lookup"><span data-stu-id="b371a-120">Users sign in with their own corporate account (Azure AD)</span></span>
    - <span data-ttu-id="b371a-121">每個裝置支援單一或多個使用者。</span><span class="sxs-lookup"><span data-stu-id="b371a-121">Single or multiple users per device is supported.</span></span>
- <span data-ttu-id="b371a-122">根據特定使用案例，從完全開啟到單一應用程式資訊站，適用不同層級的裝置鎖定配置。</span><span class="sxs-lookup"><span data-stu-id="b371a-122">Varying levels of device lockdown configurations applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>

## [<a name="guides-licensing-and-requirements"></a><span data-ttu-id="b371a-123">指南授權與需求</span><span class="sxs-lookup"><span data-stu-id="b371a-123">Guides Licensing and Requirements</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements#licensing-and-product-requirements)
- <span data-ttu-id="b371a-124">Azure AD 帳戶</span><span class="sxs-lookup"><span data-stu-id="b371a-124">Azure AD account</span></span>
- <span data-ttu-id="b371a-125">Dynamics 365 Guides 應用程式 PC 和 HoloLens</span><span class="sxs-lookup"><span data-stu-id="b371a-125">Dynamics 365 Guides applications PC and HoloLens</span></span>
- <span data-ttu-id="b371a-126">Dynamics 365 指南訂閱</span><span class="sxs-lookup"><span data-stu-id="b371a-126">Dynamics 365 Guides subscription</span></span>
    - <span data-ttu-id="b371a-127">Microsoft Dataverse (包含) </span><span class="sxs-lookup"><span data-stu-id="b371a-127">Microsoft Dataverse (included)</span></span>
    - <span data-ttu-id="b371a-128">Power Apps (包含) </span><span class="sxs-lookup"><span data-stu-id="b371a-128">Power Apps (included)</span></span>
- <span data-ttu-id="b371a-129">Power BI Desktop</span><span class="sxs-lookup"><span data-stu-id="b371a-129">Power BI Desktop</span></span>
- <span data-ttu-id="b371a-130">網路連接</span><span class="sxs-lookup"><span data-stu-id="b371a-130">Network Connectivity</span></span>

![公司已連接網狀圖表](./images/corpconnected-diagHL2-guides.png)

## <a name="stages-of-deployment"></a><span data-ttu-id="b371a-132">部署階段</span><span class="sxs-lookup"><span data-stu-id="b371a-132">Stages of Deployment</span></span>
### <a name="prepare"></a><span data-ttu-id="b371a-133">準備</span><span class="sxs-lookup"><span data-stu-id="b371a-133">Prepare</span></span>
> [!div class="checklist"]
>- [<span data-ttu-id="b371a-134">瞭解 HoloLens 2 裝置的基本基礎結構。</span><span class="sxs-lookup"><span data-stu-id="b371a-134">Learn about the infrastructure essentials for HoloLens 2 devices.</span></span>](hololens2-corp-connected-prepare.md#infrastructure-essentials)
>- [<span data-ttu-id="b371a-135">深入瞭解 Azure AD，如果您沒有 Azure AD，請設定它。</span><span class="sxs-lookup"><span data-stu-id="b371a-135">Learn more about Azure AD and set up one if you don't have it.</span></span>](hololens2-corp-connected-prepare.md#azure-active-directory)
>- [<span data-ttu-id="b371a-136">瞭解身分識別管理，以及如何以最佳方式設定 Azure AD 帳戶。</span><span class="sxs-lookup"><span data-stu-id="b371a-136">Learn about Identity management and how to best set up Azure AD accounts.</span></span>](hololens2-corp-connected-prepare.md#identity-management)
>- [<span data-ttu-id="b371a-137">深入瞭解 MDM，如果您尚未準備好 MDM，請用 Intune 進行設定。</span><span class="sxs-lookup"><span data-stu-id="b371a-137">Learn more about MDM and set up with Intune if you don't already have one ready.</span></span>](hololens2-corp-connected-prepare.md#mobile-device-management)
>- [<span data-ttu-id="b371a-138">熟悉憑證型 Wi-Fi。</span><span class="sxs-lookup"><span data-stu-id="b371a-138">Familiarize yourself with certificate-based Wi-Fi.</span></span>](hololens2-corp-connected-prepare.md#certificates)
>- [<span data-ttu-id="b371a-139">熟悉 Proxy。</span><span class="sxs-lookup"><span data-stu-id="b371a-139">Familiarize yourself with Proxy.</span></span>](hololens2-corp-connected-prepare.md#proxy)
>- [<span data-ttu-id="b371a-140">瞭解如何使用商務用應用程式。</span><span class="sxs-lookup"><span data-stu-id="b371a-140">Understand how you can use Line of Business Apps.</span></span>](hololens2-corp-connected-prepare.md#line-of-business-apps)
>- [<span data-ttu-id="b371a-141">深入瞭解您為組織使用指南的方式。</span><span class="sxs-lookup"><span data-stu-id="b371a-141">Learn more about the way you can use Guides for your organization.</span></span>](hololens2-corp-connected-prepare.md#guides-playbook)
### <a name="configure"></a><span data-ttu-id="b371a-142">設定</span><span class="sxs-lookup"><span data-stu-id="b371a-142">Configure</span></span>
> [!div class="checklist"]
>- [<span data-ttu-id="b371a-143">如何建立使用者和群組。</span><span class="sxs-lookup"><span data-stu-id="b371a-143">How to create users and groups.</span></span>](hololens2-corp-connected-configure.md#azure-users-and-groups)
>- [<span data-ttu-id="b371a-144">如何設定自動註冊。</span><span class="sxs-lookup"><span data-stu-id="b371a-144">How to set up Auto Enrollment.</span></span>](hololens2-corp-connected-configure.md#auto-enrollment-on-hololens-2)
>- [<span data-ttu-id="b371a-145">如何設定公司Wi-Fi的憑證Wi-Fi設定檔。</span><span class="sxs-lookup"><span data-stu-id="b371a-145">How to set up Wi-Fi certificates and profiles for Corporate Wi-Fi Connectivity.</span></span>](hololens2-corp-connected-configure.md#corporate-wi-fi-connectivity)
>- [<span data-ttu-id="b371a-146">上傳並指派商務用 LOB (LOB) 套件。</span><span class="sxs-lookup"><span data-stu-id="b371a-146">Upload and Assign Line of Business (LOB) App packages.</span></span>](hololens2-corp-connected-configure.md#app-deployment)
>- [<span data-ttu-id="b371a-147">設定 Dynamics 365 輔助線。</span><span class="sxs-lookup"><span data-stu-id="b371a-147">Setup Dynamics 365 Guides.</span></span>](hololens2-corp-connected-configure.md#setup-guides-application-licenses-dataverse-and-authoring)
>- [<span data-ttu-id="b371a-148">如何設定資訊站模式 (選) 。</span><span class="sxs-lookup"><span data-stu-id="b371a-148">How to configure Kiosk Mode (optional).</span></span>](hololens2-corp-connected-configure.md#optional-kiosk-mode)
>- [<span data-ttu-id="b371a-149">如何設定 WDAC (選) 。</span><span class="sxs-lookup"><span data-stu-id="b371a-149">How to configure WDAC (optional).</span></span>](hololens2-corp-connected-configure.md#optional-wdac)
### <a name="deploy"></a><span data-ttu-id="b371a-150">部署</span><span class="sxs-lookup"><span data-stu-id="b371a-150">Deploy</span></span>
> [!div class="checklist"]
>-  [<span data-ttu-id="b371a-151">透過裝置和 MDM 驗證註冊。</span><span class="sxs-lookup"><span data-stu-id="b371a-151">Validate enrollment via device and MDM.</span></span>](hololens2-corp-connected-deploy.md#enrollment-validation)
>-  [<span data-ttu-id="b371a-152">驗證Wi-Fi憑證。</span><span class="sxs-lookup"><span data-stu-id="b371a-152">Validate Wi-Fi certificates.</span></span>](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation)
>-  [<span data-ttu-id="b371a-153">驗證 LOB App 安裝。</span><span class="sxs-lookup"><span data-stu-id="b371a-153">Validate LOB app install.</span></span>](hololens2-corp-connected-deploy.md#validate-lob-app-install)
>-  [<span data-ttu-id="b371a-154">透過撰寫和操作驗證指南。</span><span class="sxs-lookup"><span data-stu-id="b371a-154">Validate Guides via authoring and operating.</span></span>](hololens2-corp-connected-deploy.md#validate-dynamics-365-guides)
### <a name="maintain"></a><span data-ttu-id="b371a-155">維護</span><span class="sxs-lookup"><span data-stu-id="b371a-155">Maintain</span></span>
> [!div class="checklist"]
>- [<span data-ttu-id="b371a-156">更新 HoloLens 2。</span><span class="sxs-lookup"><span data-stu-id="b371a-156">Update HoloLens 2.</span></span>](hololens2-corp-connected-maintain.md#update-hololens)
>- [<span data-ttu-id="b371a-157">如何更新指南 (應用程式) 。</span><span class="sxs-lookup"><span data-stu-id="b371a-157">How to update Guides (store apps).</span></span>](hololens2-corp-connected-maintain.md#how-to-update-dynamics-365-guides-and-other-store-apps)
>- [<span data-ttu-id="b371a-158">如何更新 LOB 應用程式。</span><span class="sxs-lookup"><span data-stu-id="b371a-158">How to update LOB apps.</span></span>](hololens2-corp-connected-maintain.md#how-to-update-lob-apps) 
>- [<span data-ttu-id="b371a-159">開發計畫。</span><span class="sxs-lookup"><span data-stu-id="b371a-159">Development plan.</span></span>](hololens2-corp-connected-maintain.md#development-plan) 
>- [<span data-ttu-id="b371a-160">制定支援計畫。</span><span class="sxs-lookup"><span data-stu-id="b371a-160">Making a support plan.</span></span>](hololens2-corp-connected-maintain.md#support-plan)
>- [<span data-ttu-id="b371a-161">裝置管理選項。</span><span class="sxs-lookup"><span data-stu-id="b371a-161">Device management options.</span></span>](hololens2-corp-connected-maintain.md#device-management)

## <a name="next-step"></a><span data-ttu-id="b371a-162">下一步</span><span class="sxs-lookup"><span data-stu-id="b371a-162">Next step</span></span> 
> [!div class="nextstepaction"]
> [<span data-ttu-id="b371a-163">公司連接部署 - 準備</span><span class="sxs-lookup"><span data-stu-id="b371a-163">Corporate connected deployment - Prepare</span></span>](hololens2-corp-connected-prepare.md)
