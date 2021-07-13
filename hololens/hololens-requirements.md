---
title: 常見部署案例
description: 深入瞭解如何在企業環境中部署和管理 HoloLens，包括基礎結構、Azure Active Directory 和行動裝置管理。
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: bgener
ms.author: bogenera
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/04/2020
appliesto:
- HoloLens 2
ms.openlocfilehash: ccccdcc7d3188919d02eb5855131137415c12d16
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639823"
---
# <a name="common-deployment-scenarios"></a><span data-ttu-id="29858-103">常見部署案例</span><span class="sxs-lookup"><span data-stu-id="29858-103">Common Deployment Scenarios</span></span>

## <a name="overview"></a><span data-ttu-id="29858-104">概觀</span><span class="sxs-lookup"><span data-stu-id="29858-104">Overview</span></span>

<span data-ttu-id="29858-105">本頁面提供在部署及管理企業內 Microsoft HoloLens 2 裝置時，三個常見案例的高階架構總覽。</span><span class="sxs-lookup"><span data-stu-id="29858-105">This page provides a high-level architecture overview for three common scenarios when deploying and managing Microsoft HoloLens 2 devices within the enterprise.</span></span>

<span data-ttu-id="29858-106">通常，您管理裝置及存取組織資源的方式，主要取決於已有的因素。</span><span class="sxs-lookup"><span data-stu-id="29858-106">Often, how you manage your devices and access your organization's resources is largely determined by factors already in place.</span></span> <span data-ttu-id="29858-107">根據您現有的基礎結構，我們邀請您在下列案例中查看一般裝置管理樣式 (MDM) ，然後閱讀在[商業環境中規劃 HoloLens 2 部署](hololens-core-components.md)，以判斷哪一個案例符合您的需求。</span><span class="sxs-lookup"><span data-stu-id="29858-107">Based on your existing infrastructure, we invite you to review the common device management style (MDM) in the following scenarios and then read [Planning HoloLens 2 deployments in a commercial environment](hololens-core-components.md) to determine which scenario matches your needs.</span></span> <span data-ttu-id="29858-108">此外，您也可以在部署期間使用三個對應的指南。</span><span class="sxs-lookup"><span data-stu-id="29858-108">There are also three corresponding guides available for use during your deployment.</span></span>


 1. [<span data-ttu-id="29858-109">雲端連線環境部署指南</span><span class="sxs-lookup"><span data-stu-id="29858-109">Cloud connected environment deployment guide</span></span>](hololens2-cloud-connected-overview.md)
     1. [<span data-ttu-id="29858-110">雲端連線環境 (外部用戶端) 部署指南</span><span class="sxs-lookup"><span data-stu-id="29858-110">Cloud connected environment (External Clients) deployment guide</span></span>](hololens2-deployment-guide.md)
 1. [<span data-ttu-id="29858-111">公司網路部署指南</span><span class="sxs-lookup"><span data-stu-id="29858-111">Corporate network deployment guide</span></span>](hololens2-corp-connected-overview.md)
 1. [<span data-ttu-id="29858-112">離線安全環境部署指南</span><span class="sxs-lookup"><span data-stu-id="29858-112">Offline secure environment deployment guide</span></span>](hololens-common-scenarios-offline-secure.md)

## <a name="scenario-a-deploy-to-cloud-connected-devices"></a><span data-ttu-id="29858-113">案例 A：部署至雲端連接的裝置</span><span class="sxs-lookup"><span data-stu-id="29858-113">Scenario A: Deploy to cloud connected devices</span></span>

<span data-ttu-id="29858-114">此案例相當於在公司內部署受管理的行動裝置。</span><span class="sxs-lookup"><span data-stu-id="29858-114">This scenario is comparable to deploying managed mobile devices within a company.</span></span> <span data-ttu-id="29858-115">HoloLens 2 部署為主要用於公司網路外部的環境。</span><span class="sxs-lookup"><span data-stu-id="29858-115">HoloLens 2 is deployed for use primarily in environments external to a corporate network.</span></span> <span data-ttu-id="29858-116">公司資源無法存取，或可能會透過 VPN 來限制。</span><span class="sxs-lookup"><span data-stu-id="29858-116">Corporate resources aren't accessed or may be limited through VPN.</span></span> 
 * <span data-ttu-id="29858-117">基本的一般設定</span><span class="sxs-lookup"><span data-stu-id="29858-117">Basic Common Configurations</span></span>
   * <span data-ttu-id="29858-118">Wi-Fi 的網路通常會完全開放到網際網路和雲端服務。</span><span class="sxs-lookup"><span data-stu-id="29858-118">Wi-Fi networks are typically fully open to the Internet and Cloud services.</span></span>
   * <span data-ttu-id="29858-119">Azure AD 與行動裝置管理 (MDM) 自動註冊的聯結--MDM (Intune) 受控</span><span class="sxs-lookup"><span data-stu-id="29858-119">Azure AD Join with Mobile Device Management (MDM) Auto Enrollment--MDM (Intune) Managed</span></span>
   * <span data-ttu-id="29858-120">使用者以自己的公司帳戶登入 (Azure AD) </span><span class="sxs-lookup"><span data-stu-id="29858-120">Users sign in with their own corporate account (Azure AD)</span></span>
     * <span data-ttu-id="29858-121">每個裝置支援的單一或多個使用者</span><span class="sxs-lookup"><span data-stu-id="29858-121">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="29858-122">不同層級的裝置鎖定設定會根據特定使用案例套用，從完全開放到單一應用程式 Kiosk。</span><span class="sxs-lookup"><span data-stu-id="29858-122">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="29858-123">透過 MDM 部署一或多個應用程式</span><span class="sxs-lookup"><span data-stu-id="29858-123">One or more applications are deployed via MDM</span></span>

* <span data-ttu-id="29858-124">常見的挑戰</span><span class="sxs-lookup"><span data-stu-id="29858-124">Common Challenges</span></span>
   * <span data-ttu-id="29858-125">根據案例需求，判斷要套用至 HoloLens 2 的 MDM 設定。</span><span class="sxs-lookup"><span data-stu-id="29858-125">Determining which MDM configurations to apply to the HoloLens 2 based on scenario requirements.</span></span>

<span data-ttu-id="29858-126">[![案例圖 ](images/deployment-guides-revised-scenario-a.png)](images/deployment-guides-revised-scenario-a.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="29858-126">[ ![Scenario A diagram](images/deployment-guides-revised-scenario-a.png) ](images/deployment-guides-revised-scenario-a.png#lightbox)</span></span>

<span data-ttu-id="29858-127">對應的雲端連接指南會說明如何在裝置管理中註冊 HoloLens 2、視需要套用授權，以及驗證您的終端使用者是否能夠在裝置設定時立即使用遠端協助。</span><span class="sxs-lookup"><span data-stu-id="29858-127">The corresponding Cloud connected guide covers how to enroll HoloLens 2 into your device management, apply licenses as needed, and validate that your end users are able to immediately use Remote Assist upon device setup.</span></span> <span data-ttu-id="29858-128">使用外部用戶端指南將裝置部署到遠端網站，以進行短期或長期外部使用。</span><span class="sxs-lookup"><span data-stu-id="29858-128">Use the External Clients guide to deploy devices to a remote site for short-term or long-term external use.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="29858-129">雲端連線環境部署指南</span><span class="sxs-lookup"><span data-stu-id="29858-129">Cloud connected environment deployment guide</span></span>](hololens2-cloud-connected-overview.md)

> [!div class="nextstepaction"]
> [<span data-ttu-id="29858-130">雲端連線環境 (外部用戶端) 部署指南</span><span class="sxs-lookup"><span data-stu-id="29858-130">Cloud connected environment (External Clients) deployment guide</span></span>](hololens2-deployment-guide.md)

## <a name="scenario-b-deploy-inside-your-organizations-network"></a><span data-ttu-id="29858-131">案例 B：在組織的網路內部署</span><span class="sxs-lookup"><span data-stu-id="29858-131">Scenario B: Deploy inside your organization's network</span></span>

<span data-ttu-id="29858-132">此案例與大多數 Windows 10 電腦的傳統部署完全相同。</span><span class="sxs-lookup"><span data-stu-id="29858-132">This scenario is identical to a classic deployment for most Windows 10 PCs.</span></span> <span data-ttu-id="29858-133">HoloLens 2 部署在公司網路上，可存取內部公司資源。</span><span class="sxs-lookup"><span data-stu-id="29858-133">HoloLens 2 is deployed for use primarily on the corporate network with access to internal corporate resources.</span></span> <span data-ttu-id="29858-134">網際網路和雲端服務可能會受到限制。</span><span class="sxs-lookup"><span data-stu-id="29858-134">Internet and cloud services may be limited.</span></span> 

 * <span data-ttu-id="29858-135">基本的一般設定</span><span class="sxs-lookup"><span data-stu-id="29858-135">Basic Common Configurations</span></span>
   * <span data-ttu-id="29858-136">Wi-Fi network 是內部公司網路，可存取內部資源，並限制存取網際網路或雲端服務。</span><span class="sxs-lookup"><span data-stu-id="29858-136">Wi-Fi network is an internal corporate network with access to internal resources, and limited access to the internet or Cloud services.</span></span>
   * <span data-ttu-id="29858-137">使用 MDM 自動註冊 Azure AD 聯結</span><span class="sxs-lookup"><span data-stu-id="29858-137">Azure AD Join with MDM Auto Enrollment</span></span>
   * <span data-ttu-id="29858-138">MDM (Intune) 受控</span><span class="sxs-lookup"><span data-stu-id="29858-138">MDM (Intune) Managed</span></span>
   * <span data-ttu-id="29858-139">使用者以自己的公司帳戶登入 (Azure AD) </span><span class="sxs-lookup"><span data-stu-id="29858-139">Users sign in with their own corporate account (Azure AD)</span></span>
     * <span data-ttu-id="29858-140">每個裝置支援的單一或多個使用者</span><span class="sxs-lookup"><span data-stu-id="29858-140">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="29858-141">不同層級的裝置鎖定設定會根據特定使用案例套用，從完全開放到單一應用程式 Kiosk。</span><span class="sxs-lookup"><span data-stu-id="29858-141">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="29858-142">透過 MDM 部署一或多個應用程式</span><span class="sxs-lookup"><span data-stu-id="29858-142">One or more applications are deployed via MDM</span></span>

 * <span data-ttu-id="29858-143">常見的挑戰</span><span class="sxs-lookup"><span data-stu-id="29858-143">Common Challenges</span></span>
   * <span data-ttu-id="29858-144">HoloLens 2 不支援內部部署 AD 聯結或 SCCM。</span><span class="sxs-lookup"><span data-stu-id="29858-144">HoloLens 2 doesn't support on premises AD join or SCCM.</span></span> <span data-ttu-id="29858-145">僅 Azure AD 與 MDM 聯結。</span><span class="sxs-lookup"><span data-stu-id="29858-145">Only Azure AD join with MDM.</span></span> <span data-ttu-id="29858-146">現今許多公司仍在此案例中部署 Windows 10 的電腦，作為內部部署 AD 加入的裝置（由 System Center Configuration Manager (SCCM) 管理，而且可能不會部署/設定基礎結構，以透過雲端式 MDM 解決方案來管理內部 Windows 10 裝置。</span><span class="sxs-lookup"><span data-stu-id="29858-146">Many companies today still deploy Windows 10 PCs in this scenario as on premises AD joined devices, managed by System Center Configuration Manager (SCCM) and may not have the infrastructure deployed/configured for managing internal Windows 10 devices via cloud-based MDM solutions.</span></span>
   * <span data-ttu-id="29858-147">由於 HoloLens 2 是雲端的第一部裝置，因此其高度依賴網際網路和雲端聯機服務來進行使用者驗證、作業系統更新、MDM 管理等等。</span><span class="sxs-lookup"><span data-stu-id="29858-147">As HoloLens 2 is a cloud first device, it relies heavily on internet and cloud connected services for User authentication, OS updates, MDM management, and so on.</span></span> <span data-ttu-id="29858-148">連線到公司網路時，可能需要調整 Proxy/防火牆規則，才能啟用 HoloLens 2 的存取，以及對其執行的應用程式。</span><span class="sxs-lookup"><span data-stu-id="29858-148">When connecting to a corporate network, Proxy/Firewall rules will most likely need to be adjusted to enable access for HoloLens 2 and the applications that run on it.</span></span>
   * <span data-ttu-id="29858-149">公司 Wi-Fi 連線通常需要憑證來向網路驗證裝置或使用者。</span><span class="sxs-lookup"><span data-stu-id="29858-149">Corporate Wi-Fi connectivity typically requires certificates to authenticate the device or user to the network.</span></span> <span data-ttu-id="29858-150">透過 MDM 將憑證部署到 Windows 10 裝置所需的基礎結構或設定，可能是設定的挑戰。</span><span class="sxs-lookup"><span data-stu-id="29858-150">The required infrastructure or settings to deploy certificates to Windows 10 devices through MDM can be challenging to configure.</span></span>

<span data-ttu-id="29858-151">[![案例 B1 圖表 ](images/deployment-guides-revised-scenario-b-01-1.png)](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="29858-151">[ ![Scenario B1 diagram](images/deployment-guides-revised-scenario-b-01-1.png) ](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)</span></span>

<span data-ttu-id="29858-152">[![案例 B2 圖表 ](images/deployment-guides-revised-scenario-b-02-1.png)](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="29858-152">[ ![Scenario B2 diagram](images/deployment-guides-revised-scenario-b-02-1.png) ](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)</span></span>

<span data-ttu-id="29858-153">對應的公司網路指南會指示如何註冊 HoloLens 2 到您現有的裝置管理、視需要套用授權，以及驗證您的終端使用者是否能夠在裝置設定之後，操作 Dynamics 365 指南，以及使用自訂的企業營運應用程式。</span><span class="sxs-lookup"><span data-stu-id="29858-153">The corresponding Corporate network guide instructs on how to enroll HoloLens 2 into your existing device management, apply licenses as needed, and validate that your end users are able to operate a Dynamics 365 Guide, as well as use custom line of business apps, after device set up.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="29858-154">公司網路部署指南</span><span class="sxs-lookup"><span data-stu-id="29858-154">Corporate network deployment guide</span></span>](hololens2-corp-connected-overview.md)

## <a name="scenario-c-deploy-in-secure-offline-environment"></a><span data-ttu-id="29858-155">案例 C：在安全的離線環境中部署</span><span class="sxs-lookup"><span data-stu-id="29858-155">Scenario C: Deploy in secure offline environment</span></span>

<span data-ttu-id="29858-156">這是高度安全或機密位置的一般部署。</span><span class="sxs-lookup"><span data-stu-id="29858-156">This is a typical deployment for highly secure or confidential locations.</span></span> <span data-ttu-id="29858-157">部署 HoloLens 2，主要用於離線且無法存取網路或網際網路。</span><span class="sxs-lookup"><span data-stu-id="29858-157">HoloLens 2 is deployed for use primarily offline with no network or internet access.</span></span> 
 * <span data-ttu-id="29858-158">基本的一般設定</span><span class="sxs-lookup"><span data-stu-id="29858-158">Basic Common Configurations</span></span>
   * <span data-ttu-id="29858-159">Wi-Fi 連接已停用。</span><span class="sxs-lookup"><span data-stu-id="29858-159">Wi-Fi connectivity is disabled.</span></span> <span data-ttu-id="29858-160">如有需要，可透過 USB 來啟用乙太網路連線能力。</span><span class="sxs-lookup"><span data-stu-id="29858-160">Ethernet via USB may be enabled for LAN connectivity if necessary.</span></span>
   * <span data-ttu-id="29858-161">未受管理。</span><span class="sxs-lookup"><span data-stu-id="29858-161">Not Managed.</span></span>
   * <span data-ttu-id="29858-162">裝置登入的本機使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="29858-162">Local user account for device sign-in.</span></span>
     * <span data-ttu-id="29858-163">HoloLens 2 只支援一個本機帳戶。</span><span class="sxs-lookup"><span data-stu-id="29858-163">HoloLens 2 supports only one local account.</span></span>
   * <span data-ttu-id="29858-164">不同層級的裝置鎖定設定會透過根據特定使用案例提供的布建套件來套用。</span><span class="sxs-lookup"><span data-stu-id="29858-164">Varying levels of device lockdown configurations are applied via Provisioning Packages based on specific use cases.</span></span> <span data-ttu-id="29858-165">這些設定通常會因為安全的環境需求而受到限制。</span><span class="sxs-lookup"><span data-stu-id="29858-165">These configurations are typically restricted because of secure environment requirements.</span></span>
   * <span data-ttu-id="29858-166">透過布建套件部署一或多個應用程式</span><span class="sxs-lookup"><span data-stu-id="29858-166">One or more applications are deployed via Provisioning Package</span></span>

 * <span data-ttu-id="29858-167">常見的挑戰</span><span class="sxs-lookup"><span data-stu-id="29858-167">Common Challenges</span></span>
   * <span data-ttu-id="29858-168">布建套件提供一組有限的設定</span><span class="sxs-lookup"><span data-stu-id="29858-168">There's a limited set of configurations available through Provisioning Packages</span></span>
   * <span data-ttu-id="29858-169">無法使用雲端服務，因此會限制 HoloLens 2 的功能。</span><span class="sxs-lookup"><span data-stu-id="29858-169">Cloud services aren't able to be used, therefore limiting the HoloLens 2 capabilities.</span></span>
   * <span data-ttu-id="29858-170">更高的系統管理負荷，因為這些裝置必須手動設定、設定和更新。</span><span class="sxs-lookup"><span data-stu-id="29858-170">Higher administrative overhead since these devices have to be set up, configured, and updated manually.</span></span>

<span data-ttu-id="29858-171">[![離線安全圖 1 ](images/deployment-guides-revised-scenario-c-01.png)](images/deployment-guides-revised-scenario-c-01.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="29858-171">[ ![Offline Secure diagram 1](images/deployment-guides-revised-scenario-c-01.png) ](images/deployment-guides-revised-scenario-c-01.png#lightbox)</span></span>

<span data-ttu-id="29858-172">相對應的離線安全指南提供了套用範例布建套件的指示，可鎖定 HoloLens 2 以在安全環境中使用。</span><span class="sxs-lookup"><span data-stu-id="29858-172">The corresponding Offline secure guide provides instruction for applying a sample Provisioning Package that will lock down a HoloLens 2 for use in secure environments.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="29858-173">離線安全環境部署指南</span><span class="sxs-lookup"><span data-stu-id="29858-173">Offline secure environment deployment guide</span></span>](hololens-common-scenarios-offline-secure.md)


