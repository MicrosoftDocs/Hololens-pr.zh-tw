---
title: 常見的基礎結構部署案例
description: 根據混合現實的不同基礎結構部署，瞭解一些最常見的部署案例。
ms.assetid: 651d0430-bfbc-4685-a4fd-db7c33ce9325
ms.date: 3/24/2021
keywords: hololens
manager: yannisle
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: v-evmill
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
appliesto:
- HoloLens 2
ms.openlocfilehash: 30a35fb0fe5d5b669249df25ebff0228b552596c
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397413"
---
# <a name="common-infrastructure-deployment-scenarios-overview"></a><span data-ttu-id="19a4b-104">常見的基礎結構部署案例總覽</span><span class="sxs-lookup"><span data-stu-id="19a4b-104">Common Infrastructure Deployment Scenarios Overview</span></span>

<span data-ttu-id="19a4b-105">在部署和管理企業內的 Microsoft HoloLens 2 裝置時，下列資訊可提供三種常見案例的高階架構總覽。</span><span class="sxs-lookup"><span data-stu-id="19a4b-105">This following information provides a high-level architecture overview for three common scenarios when deploying and managing Microsoft HoloLens 2 devices within the enterprise.</span></span> <span data-ttu-id="19a4b-106">通常，您管理裝置的方式，以及如何存取組織的資源，主要取決於已有的因素。</span><span class="sxs-lookup"><span data-stu-id="19a4b-106">Often how you manage your devices and how to access your organization's resources is largely determined by factors already in place.</span></span> <span data-ttu-id="19a4b-107">根據現有的基礎結構，我們會在下列案例中邀請您複習一般裝置管理樣式，並嘗試在符合您需求的案例中進行部署的指南。</span><span class="sxs-lookup"><span data-stu-id="19a4b-107">Based on the existing infrastructure we invite you to review the common device management style in the following scenarios, and try out our guides for deploying in the scenario matching your needs.</span></span>

## <a name="scenarios"></a><span data-ttu-id="19a4b-108">案例</span><span class="sxs-lookup"><span data-stu-id="19a4b-108">Scenarios</span></span>

<span data-ttu-id="19a4b-109">下圖代表 HoloLens 2 部署的兩個典型受控案例。</span><span class="sxs-lookup"><span data-stu-id="19a4b-109">The diagram below represents two typical managed scenarios for HoloLens 2 deployments.</span></span>
 

<span data-ttu-id="19a4b-110">另外還有第三種情況允許離線的安全部署。</span><span class="sxs-lookup"><span data-stu-id="19a4b-110">There is also third scenario that allows for offline secure deployments.</span></span>

### <a name="scenario-a-deploy-to-cloud-connected-devices"></a><span data-ttu-id="19a4b-111">案例 A：部署至雲端連接的裝置</span><span class="sxs-lookup"><span data-stu-id="19a4b-111">Scenario A: Deploy to cloud connected devices</span></span>

<span data-ttu-id="19a4b-112">HoloLens 2 部署為主要用於公司網路外部的環境。</span><span class="sxs-lookup"><span data-stu-id="19a4b-112">HoloLens 2 is deployed for use primarily in environments external to a corporate network.</span></span> <span data-ttu-id="19a4b-113">公司資源無法存取，或可能會透過 VPN 來限制。</span><span class="sxs-lookup"><span data-stu-id="19a4b-113">Corporate resources aren't accessed or may be limited through VPN.</span></span> <span data-ttu-id="19a4b-114">此部署與公司內受管理的行動裝置類似。</span><span class="sxs-lookup"><span data-stu-id="19a4b-114">This  deployment is similar to managed mobile devices within a company.</span></span>
 * <span data-ttu-id="19a4b-115">基本的一般設定</span><span class="sxs-lookup"><span data-stu-id="19a4b-115">Basic Common Configurations</span></span>
   * <span data-ttu-id="19a4b-116">Wi-Fi 的網路通常會完全開放到網際網路和雲端服務。</span><span class="sxs-lookup"><span data-stu-id="19a4b-116">Wi-Fi networks are typically fully open to the Internet and Cloud services.</span></span>
   * <span data-ttu-id="19a4b-117">Azure AD 與行動裝置管理 (MDM) 自動註冊的聯結--MDM (Intune) 受控</span><span class="sxs-lookup"><span data-stu-id="19a4b-117">Azure AD Join with Mobile Device Management (MDM) Auto Enrollment--MDM (Intune) Managed</span></span>
   * <span data-ttu-id="19a4b-118">使用者以自己的公司帳戶登入 (Azure AD) </span><span class="sxs-lookup"><span data-stu-id="19a4b-118">Users sign in with their own corporate account (Azure AD)</span></span>
     * <span data-ttu-id="19a4b-119">每個裝置支援的單一或多個使用者</span><span class="sxs-lookup"><span data-stu-id="19a4b-119">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="19a4b-120">不同層級的裝置鎖定設定會根據特定使用案例套用，從完全開放到單一應用程式 Kiosk。</span><span class="sxs-lookup"><span data-stu-id="19a4b-120">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="19a4b-121">透過 MDM 部署一或多個應用程式</span><span class="sxs-lookup"><span data-stu-id="19a4b-121">One or more applications are deployed via MDM</span></span>



* <span data-ttu-id="19a4b-122">常見的挑戰</span><span class="sxs-lookup"><span data-stu-id="19a4b-122">Common Challenges</span></span>
   * <span data-ttu-id="19a4b-123">根據案例需求，判斷要套用至 HoloLens 2 的 MDM 設定。</span><span class="sxs-lookup"><span data-stu-id="19a4b-123">Determining which MDM configurations to apply to the HoloLens 2 based on scenario requirements.</span></span>

<span data-ttu-id="19a4b-124">[![案例圖 ](images/deployment-guides-revised-scenario-a.png)](images/deployment-guides-revised-scenario-a.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="19a4b-124">[ ![Scenario A diagram](images/deployment-guides-revised-scenario-a.png) ](images/deployment-guides-revised-scenario-a.png#lightbox)</span></span>

<span data-ttu-id="19a4b-125">如需類似于此案例的部署指南，請參閱《 [雲端連線環境部署指南](hololens2-cloud-connected-overview.md)》的指南。</span><span class="sxs-lookup"><span data-stu-id="19a4b-125">For a deployment guide that is similar to this scenario review our guide for [Cloud connected environment deployment guide](hololens2-cloud-connected-overview.md).</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="19a4b-126">雲端連線環境部署指南</span><span class="sxs-lookup"><span data-stu-id="19a4b-126">Cloud connected environment deployment guide</span></span>](hololens2-cloud-connected-overview.md)
> [!div class="nextstepaction"]
> [<span data-ttu-id="19a4b-127">雲端連線環境 (外部用戶端) 部署指南</span><span class="sxs-lookup"><span data-stu-id="19a4b-127">Cloud connected environment (External Clients) deployment guide</span></span>](hololens2-deployment-guide.md)

### <a name="scenario-b-deploy-inside-your-organizations-network"></a><span data-ttu-id="19a4b-128">案例 B：在組織的網路內部署</span><span class="sxs-lookup"><span data-stu-id="19a4b-128">Scenario B: Deploy inside your organization's network</span></span>

<span data-ttu-id="19a4b-129">HoloLens 2 部署在公司網路上，可存取內部公司資源。</span><span class="sxs-lookup"><span data-stu-id="19a4b-129">HoloLens 2 is deployed for use primarily on the corporate network with access to internal corporate resources.</span></span> <span data-ttu-id="19a4b-130">網際網路和雲端服務可能會受到限制。</span><span class="sxs-lookup"><span data-stu-id="19a4b-130">Internet and cloud services may be limited.</span></span> <span data-ttu-id="19a4b-131">此部署是大多數 Windows 10 電腦的一般部署。</span><span class="sxs-lookup"><span data-stu-id="19a4b-131">This deployment is a typical deployment for most Windows 10 PCs.</span></span>

 * <span data-ttu-id="19a4b-132">基本的一般設定</span><span class="sxs-lookup"><span data-stu-id="19a4b-132">Basic Common Configurations</span></span>
   * <span data-ttu-id="19a4b-133">Wi-Fi network 是內部公司網路，可存取內部資源，並限制存取網際網路或雲端服務。</span><span class="sxs-lookup"><span data-stu-id="19a4b-133">Wi-Fi network is an internal corporate network with access to internal resources, and limited access to the internet or Cloud services.</span></span>
   * <span data-ttu-id="19a4b-134">使用 MDM 自動註冊 Azure AD 聯結</span><span class="sxs-lookup"><span data-stu-id="19a4b-134">Azure AD Join with MDM Auto Enrollment</span></span>
   * <span data-ttu-id="19a4b-135">MDM (Intune) 受控</span><span class="sxs-lookup"><span data-stu-id="19a4b-135">MDM (Intune) Managed</span></span>
   * <span data-ttu-id="19a4b-136">使用者以自己的公司帳戶登入 (Azure AD) </span><span class="sxs-lookup"><span data-stu-id="19a4b-136">Users sign in with their own corporate account (Azure AD)</span></span>
     * <span data-ttu-id="19a4b-137">每個裝置支援的單一或多個使用者</span><span class="sxs-lookup"><span data-stu-id="19a4b-137">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="19a4b-138">不同層級的裝置鎖定設定會根據特定使用案例套用，從完全開放到單一應用程式 Kiosk。</span><span class="sxs-lookup"><span data-stu-id="19a4b-138">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="19a4b-139">透過 MDM 部署一或多個應用程式</span><span class="sxs-lookup"><span data-stu-id="19a4b-139">One or more applications are deployed via MDM</span></span>

 * <span data-ttu-id="19a4b-140">常見的挑戰</span><span class="sxs-lookup"><span data-stu-id="19a4b-140">Common Challenges</span></span>
   * <span data-ttu-id="19a4b-141">HoloLens 2 不支援內部部署 AD 聯結或 SCCM。</span><span class="sxs-lookup"><span data-stu-id="19a4b-141">HoloLens 2 doesn't support on premises AD join or SCCM.</span></span> <span data-ttu-id="19a4b-142">僅 Azure AD 與 MDM 聯結。</span><span class="sxs-lookup"><span data-stu-id="19a4b-142">Only Azure AD join with MDM.</span></span> <span data-ttu-id="19a4b-143">現今許多公司仍在此案例中部署 Windows 10 的電腦，就像內部部署 AD 加入的裝置一樣，由 System Center 設定管理員 (SCCM) 管理，而且可能不會部署/設定基礎結構，以透過雲端式 MDM 解決方案來管理內部 Windows 10 裝置。</span><span class="sxs-lookup"><span data-stu-id="19a4b-143">Many companies today still deploy Windows 10 PCs in this scenario as on premises AD joined devices, managed by System Center Configuration Manager (SCCM) and may not have the infrastructure deployed/configured for managing internal Windows 10 devices via cloud-based MDM solutions.</span></span>
   * <span data-ttu-id="19a4b-144">由於 HoloLens 2 是雲端的第一部裝置，因此其高度依賴網際網路和雲端聯機服務來進行使用者驗證、作業系統更新、MDM 管理等等。</span><span class="sxs-lookup"><span data-stu-id="19a4b-144">As HoloLens 2 is a cloud first device, it relies heavily on internet and cloud connected services for User authentication, OS updates, MDM management, and so on.</span></span> <span data-ttu-id="19a4b-145">連線到公司網路時，可能需要調整 Proxy/防火牆規則，才能啟用 HoloLens 2 的存取，以及對其執行的應用程式。</span><span class="sxs-lookup"><span data-stu-id="19a4b-145">When connecting to a corporate network, Proxy/Firewall rules will most likely need to be adjusted to enable access for HoloLens 2 and the applications that run on it.</span></span>
   * <span data-ttu-id="19a4b-146">公司 Wi-Fi 連線通常需要憑證來向網路驗證裝置或使用者。</span><span class="sxs-lookup"><span data-stu-id="19a4b-146">Corporate Wi-Fi connectivity typically requires certificates to authenticate the device or user to the network.</span></span> <span data-ttu-id="19a4b-147">透過 MDM 將憑證部署到 Windows 10 裝置所需的基礎結構或設定，可能是設定的挑戰。</span><span class="sxs-lookup"><span data-stu-id="19a4b-147">The required infrastructure or settings to deploy certificates to Windows 10 devices through MDM can be challenging to configure.</span></span>

<span data-ttu-id="19a4b-148">[![案例 B1 圖表 ](images/deployment-guides-revised-scenario-b-01-1.png)](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="19a4b-148">[ ![Scenario B1 diagram](images/deployment-guides-revised-scenario-b-01-1.png) ](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)</span></span>

<span data-ttu-id="19a4b-149">[![案例 B2 圖表 ](images/deployment-guides-revised-scenario-b-02-1.png)](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="19a4b-149">[ ![Scenario B2 diagram](images/deployment-guides-revised-scenario-b-02-1.png) ](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)</span></span>

<span data-ttu-id="19a4b-150">如需類似于此案例的部署指南，請參閱《 [商業網路部署指南](hololens2-corp-connected-overview.md)》的指南。</span><span class="sxs-lookup"><span data-stu-id="19a4b-150">For a deployment guide that is similar to this scenario review our guide for [Corporate network deployment guide](hololens2-corp-connected-overview.md).</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="19a4b-151">公司網路部署指南</span><span class="sxs-lookup"><span data-stu-id="19a4b-151">Corporate network deployment guide</span></span>](hololens2-corp-connected-overview.md)

### <a name="scenario-c-deploy-in-secure-offline-environment"></a><span data-ttu-id="19a4b-152">案例 C：在安全的離線環境中部署</span><span class="sxs-lookup"><span data-stu-id="19a4b-152">Scenario C: Deploy in secure offline environment</span></span>

<span data-ttu-id="19a4b-153">部署 HoloLens 2，主要用於離線且無法存取網路或網際網路。</span><span class="sxs-lookup"><span data-stu-id="19a4b-153">HoloLens 2 is deployed for use primarily offline with no network or internet access.</span></span> <span data-ttu-id="19a4b-154">這是高度安全或機密位置的一般部署。</span><span class="sxs-lookup"><span data-stu-id="19a4b-154">This is a typical deployment for highly secure or confidential locations.</span></span>
 * <span data-ttu-id="19a4b-155">基本的一般設定</span><span class="sxs-lookup"><span data-stu-id="19a4b-155">Basic Common Configurations</span></span>
   * <span data-ttu-id="19a4b-156">Wi-Fi 連接已停用。</span><span class="sxs-lookup"><span data-stu-id="19a4b-156">Wi-Fi connectivity is disabled.</span></span> <span data-ttu-id="19a4b-157">如有需要，可透過 USB 來啟用乙太網路連線能力。</span><span class="sxs-lookup"><span data-stu-id="19a4b-157">Ethernet via USB may be enabled for LAN connectivity if necessary.</span></span>
   * <span data-ttu-id="19a4b-158">未受管理。</span><span class="sxs-lookup"><span data-stu-id="19a4b-158">Not Managed.</span></span>
   * <span data-ttu-id="19a4b-159">裝置登入的本機使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="19a4b-159">Local user account for device sign-in.</span></span>
     * <span data-ttu-id="19a4b-160">HoloLens 2 只支援一個本機帳戶。</span><span class="sxs-lookup"><span data-stu-id="19a4b-160">HoloLens 2 supports only one local account.</span></span>
   * <span data-ttu-id="19a4b-161">不同層級的裝置鎖定設定會透過根據特定使用案例提供的布建套件來套用。</span><span class="sxs-lookup"><span data-stu-id="19a4b-161">Varying levels of device lockdown configurations are applied via Provisioning Packages based on specific use cases.</span></span> <span data-ttu-id="19a4b-162">這些設定通常會因為安全的環境需求而受到限制。</span><span class="sxs-lookup"><span data-stu-id="19a4b-162">These configurations are typically restricted because of secure environment requirements.</span></span>
   * <span data-ttu-id="19a4b-163">透過布建套件部署一或多個應用程式</span><span class="sxs-lookup"><span data-stu-id="19a4b-163">One or more applications are deployed via Provisioning Package</span></span>

 * <span data-ttu-id="19a4b-164">常見的挑戰</span><span class="sxs-lookup"><span data-stu-id="19a4b-164">Common Challenges</span></span>
   * <span data-ttu-id="19a4b-165">布建套件提供一組有限的設定</span><span class="sxs-lookup"><span data-stu-id="19a4b-165">There's a limited set of configurations available through Provisioning Packages</span></span>
   * <span data-ttu-id="19a4b-166">無法使用雲端服務，因此會限制 HoloLens 2 的功能。</span><span class="sxs-lookup"><span data-stu-id="19a4b-166">Cloud services aren't able to be used, therefore limiting the HoloLens 2 capabilities.</span></span>
   * <span data-ttu-id="19a4b-167">更高的系統管理負荷，因為這些裝置必須手動設定、設定和更新。</span><span class="sxs-lookup"><span data-stu-id="19a4b-167">Higher administrative overhead since these devices have to be set up, configured, and updated manually.</span></span>

<span data-ttu-id="19a4b-168">[![離線安全圖 1 ](images/deployment-guides-revised-scenario-c-01.png)](images/deployment-guides-revised-scenario-c-01.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="19a4b-168">[ ![Offline Secure diagram 1](images/deployment-guides-revised-scenario-c-01.png) ](images/deployment-guides-revised-scenario-c-01.png#lightbox)</span></span>

<span data-ttu-id="19a4b-169">如需類似于此案例的部署指南，請參閱我們的 [離線安全環境部署指南](hololens-common-scenarios-offline-secure.md)。</span><span class="sxs-lookup"><span data-stu-id="19a4b-169">For a deployment guide that is similar to this scenario review our [Offline secure environment deployment guide](hololens-common-scenarios-offline-secure.md).</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="19a4b-170">離線安全環境部署指南</span><span class="sxs-lookup"><span data-stu-id="19a4b-170">Offline secure environment deployment guide</span></span>](hololens-common-scenarios-offline-secure.md)
