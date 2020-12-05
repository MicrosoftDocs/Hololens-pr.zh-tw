---
title: 常見的基礎結構部署案例
description: 根據不同常見基礎結構的一些常見部署案例
ms.assetid: 651d0430-bfbc-4685-a4fd-db7c33ce9325
ms.date: 11/04/2020
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
ms.openlocfilehash: e9e91535bb49b5076547e8b9934bdc86808d41fc
ms.sourcegitcommit: 8e2c268733adce2662bf320cf96ccfea5919425e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/04/2020
ms.locfileid: "11195566"
---
# <span data-ttu-id="b4641-104">常見的基礎結構部署案例概述</span><span class="sxs-lookup"><span data-stu-id="b4641-104">Common Infrastructure Deployment Scenarios Overview</span></span>

<span data-ttu-id="b4641-105">下列資訊提供在企業中部署和管理 Microsoft HoloLens 2 裝置的三種常見案例的高層結構概覽。</span><span class="sxs-lookup"><span data-stu-id="b4641-105">This following information provides a high-level architecture overview for three common scenarios when deploying and managing Microsoft HoloLens 2 devices within the enterprise.</span></span> <span data-ttu-id="b4641-106">您通常會如何管理裝置，以及如何存取貴組織的資源主要是由目前已準備好的因素決定。</span><span class="sxs-lookup"><span data-stu-id="b4641-106">Often how you manage your devices and how access your organization's resources is largely determined by factors already in place.</span></span> <span data-ttu-id="b4641-107">根據現有的基礎結構，我們會邀請您在下列案例中審查常見的裝置管理樣式，並嘗試在符合您需求的案例中部署輔助線。</span><span class="sxs-lookup"><span data-stu-id="b4641-107">Based on the existing infrastructure we invite you to review the common device management style in the following scenarios, and try out our guides for deploying in the scenario matching your needs.</span></span>

## <span data-ttu-id="b4641-108">案例</span><span class="sxs-lookup"><span data-stu-id="b4641-108">Scenarios</span></span>

<span data-ttu-id="b4641-109">下圖代表 HoloLens 2 部署的三種典型案例。</span><span class="sxs-lookup"><span data-stu-id="b4641-109">The diagram below represents three typical scenarios for HoloLens 2 deployments.</span></span>
![案例圖表](images/scenarios.jpg)

### <span data-ttu-id="b4641-111">案例 A：部署到雲端連接裝置</span><span class="sxs-lookup"><span data-stu-id="b4641-111">Scenario A: Deploy to cloud connect devices</span></span>

<span data-ttu-id="b4641-112">已部署 HoloLens 2，主要用於公司網路中的外部環境。</span><span class="sxs-lookup"><span data-stu-id="b4641-112">HoloLens 2 is deployed for use primarily in environments external to a corporate network.</span></span> <span data-ttu-id="b4641-113">公司資源無法存取，或可能受 VPN 限制。</span><span class="sxs-lookup"><span data-stu-id="b4641-113">Corporate resources are not accessed or may be limited through VPN.</span></span> <span data-ttu-id="b4641-114">這個部署與公司內受管理的行動裝置非常類似。</span><span class="sxs-lookup"><span data-stu-id="b4641-114">This is a deployment very similar to managed mobile devices within a company.</span></span>
 * <span data-ttu-id="b4641-115">基本常見設定</span><span class="sxs-lookup"><span data-stu-id="b4641-115">Basic Common Configurations</span></span>
   * <span data-ttu-id="b4641-116">Wi-Fi 的網路通常會完全開啟網際網路和雲端服務。</span><span class="sxs-lookup"><span data-stu-id="b4641-116">Wi-Fi networks are typically fully open to the Internet and Cloud services.</span></span>
   * <span data-ttu-id="b4641-117">使用 MDM 自動註冊的 Azure AD 聯接--MDM (Intune) 管理</span><span class="sxs-lookup"><span data-stu-id="b4641-117">Azure AD Join with MDM Auto Enrollment -- MDM (Intune) Managed</span></span>
   * <span data-ttu-id="b4641-118">使用者以自己的公司帳戶登入 (AAD) </span><span class="sxs-lookup"><span data-stu-id="b4641-118">Users sign in with their own corporate account (AAD)</span></span>
     * <span data-ttu-id="b4641-119">每個裝置支援單一或多個使用者</span><span class="sxs-lookup"><span data-stu-id="b4641-119">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="b4641-120">根據特定的使用案例，從完全開啟到單一應用程式亭，就會套用各種不同的裝置鎖定設定等級。</span><span class="sxs-lookup"><span data-stu-id="b4641-120">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="b4641-121">一或多個應用程式是透過 MDM 部署</span><span class="sxs-lookup"><span data-stu-id="b4641-121">One or more applications are deployed via MDM</span></span>

* <span data-ttu-id="b4641-122">常見的難題</span><span class="sxs-lookup"><span data-stu-id="b4641-122">Common Challenges</span></span>
   * <span data-ttu-id="b4641-123">根據案例需求決定要套用至 HoloLens 2 的 MDM 設定。</span><span class="sxs-lookup"><span data-stu-id="b4641-123">Determining which MDM configurations to apply to the HoloLens 2 based on scenario requirements.</span></span>

<span data-ttu-id="b4641-124">如需與此案例類似的部署指南，請參閱我們的 [雲端連線 HoloLens （含遠端協助](hololens2-cloud-connected-overview.md)）指南。</span><span class="sxs-lookup"><span data-stu-id="b4641-124">For a deployment guide that is similar to this scenario please review our guide for [Cloud connected HoloLens 2 with Remote Assist](hololens2-cloud-connected-overview.md).</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="b4641-125">部署指南–雲端連線的 HoloLens 2 （含遠端協助）</span><span class="sxs-lookup"><span data-stu-id="b4641-125">Deployment Guide – Cloud connected HoloLens 2 with Remote Assist</span></span>](hololens2-cloud-connected-overview.md)

### <span data-ttu-id="b4641-126">案例 B：在貴組織的網路內部部署</span><span class="sxs-lookup"><span data-stu-id="b4641-126">Scenario B: Deploy inside your organization's network</span></span>

<span data-ttu-id="b4641-127">HoloLens 2 已部署，主要用於公司網路，可存取內部公司資源。</span><span class="sxs-lookup"><span data-stu-id="b4641-127">HoloLens 2 is deployed for use primarily on the corporate network with access to internal corporate resources.</span></span> <span data-ttu-id="b4641-128">網際網路和雲端服務可能受到限制。</span><span class="sxs-lookup"><span data-stu-id="b4641-128">Internet and cloud services may be limited.</span></span> <span data-ttu-id="b4641-129">這是大部分 Windows 10 電腦的典型部署。</span><span class="sxs-lookup"><span data-stu-id="b4641-129">This is a typical deployment for most Windows 10 PCs.</span></span>
 * <span data-ttu-id="b4641-130">基本常見設定</span><span class="sxs-lookup"><span data-stu-id="b4641-130">Basic Common Configurations</span></span>
   * <span data-ttu-id="b4641-131">Wi-Fi 網路是內部公司網路，可存取內部資源，以及網際網路或雲端服務的有限存取權。</span><span class="sxs-lookup"><span data-stu-id="b4641-131">Wi-Fi network is an internal corporate network with access to internal resources, and limited access to the internet or Cloud services.</span></span>
   * <span data-ttu-id="b4641-132">使用 MDM 自動註冊的 Azure AD 加入</span><span class="sxs-lookup"><span data-stu-id="b4641-132">Azure AD Join with MDM Auto Enrollment</span></span>
   * <span data-ttu-id="b4641-133">MDM (Intune) 管理</span><span class="sxs-lookup"><span data-stu-id="b4641-133">MDM (Intune) Managed</span></span>
   * <span data-ttu-id="b4641-134">使用者以自己的公司帳戶登入 (AAD) </span><span class="sxs-lookup"><span data-stu-id="b4641-134">Users sign in with their own corporate account (AAD)</span></span>
     * <span data-ttu-id="b4641-135">每個裝置支援單一或多個使用者</span><span class="sxs-lookup"><span data-stu-id="b4641-135">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="b4641-136">根據特定的使用案例，從完全開啟到單一應用程式亭，就會套用各種不同的裝置鎖定設定等級。</span><span class="sxs-lookup"><span data-stu-id="b4641-136">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="b4641-137">一或多個應用程式是透過 MDM 部署</span><span class="sxs-lookup"><span data-stu-id="b4641-137">One or more applications are deployed via MDM</span></span>

 * <span data-ttu-id="b4641-138">常見的難題</span><span class="sxs-lookup"><span data-stu-id="b4641-138">Common Challenges</span></span>
   * <span data-ttu-id="b4641-139">HoloLens 2 不支援內部部署廣告連接或 SCCM。</span><span class="sxs-lookup"><span data-stu-id="b4641-139">HoloLens 2 does not support on premises AD join or SCCM.</span></span> <span data-ttu-id="b4641-140">僅限使用 MDM 的 Azure AD 加入。</span><span class="sxs-lookup"><span data-stu-id="b4641-140">Only Azure AD join with MDM.</span></span> <span data-ttu-id="b4641-141">在這種情況下，許多公司現在仍會部署 Windows 10 電腦，因為內部部署廣告已加入裝置是由 System Center Configuration Manager () SCCM 所管理，而且可能不會透過雲端的 MDM 解決方案部署/設定基礎結構來管理內部 Windows 10 裝置。</span><span class="sxs-lookup"><span data-stu-id="b4641-141">Many companies today still deploy Windows 10 PCs in this scenario as on premises AD joined devices, managed by System Center Configuration Manager (SCCM) and may not have the infrastructure deployed/configured for managing internal Windows 10 devices via cloud based MDM solutions.</span></span>
   * <span data-ttu-id="b4641-142">因為 HoloLens 2 是雲端第一個裝置，所以它大量依賴網際網路和雲端聯機服務來進行使用者驗證、作業系統更新、MDM 管理等。連線至公司網路時，最可能需要調整 Proxy/防火牆規則，才能啟用 HoloLens 2 以及在其上執行的應用程式的存取權。</span><span class="sxs-lookup"><span data-stu-id="b4641-142">As HoloLens 2 is a cloud first device, it relies heavily on internet and cloud connected services for User authentication, OS updates, MDM management, etc. When connecting to a corporate network, Proxy/Firewall rules will most likely need to be adjusted to enable access for HoloLens 2 and the applications that run on it.</span></span>
   * <span data-ttu-id="b4641-143">企業 Wi-Fi 連線通常需要認證，才能向網路驗證裝置或使用者。</span><span class="sxs-lookup"><span data-stu-id="b4641-143">Corporate Wi-Fi connectivity typically requires certificates to authenticate the device or user to the network.</span></span> <span data-ttu-id="b4641-144">透過 MDM 將憑證部署到 Windows 10 裝置所需的基礎結構或設定，可能很難設定。</span><span class="sxs-lookup"><span data-stu-id="b4641-144">The required infrastructure or settings to deploy certificates to Windows 10 devices through MDM can be challenging to configure.</span></span>

### <span data-ttu-id="b4641-145">案例 C：在安全的離線環境中部署</span><span class="sxs-lookup"><span data-stu-id="b4641-145">Scenario C: Deploy in secure offline environment</span></span>

<span data-ttu-id="b4641-146">HoloLens 2 已部署，主要用於離線使用，沒有網路或網際網路存取。</span><span class="sxs-lookup"><span data-stu-id="b4641-146">HoloLens 2 is deployed for use primarily offline with no network or internet access.</span></span> <span data-ttu-id="b4641-147">這是高度安全或機密位置的典型部署。</span><span class="sxs-lookup"><span data-stu-id="b4641-147">This is a typical deployment for highly secure or confidential locations.</span></span>
 * <span data-ttu-id="b4641-148">基本常見設定</span><span class="sxs-lookup"><span data-stu-id="b4641-148">Basic Common Configurations</span></span>
   * <span data-ttu-id="b4641-149">Wi-Fi 連線性已停用。</span><span class="sxs-lookup"><span data-stu-id="b4641-149">Wi-Fi connectivity is disabled.</span></span> <span data-ttu-id="b4641-150">如果需要，可以透過 USB 乙太網上的乙太網路進行局域網連線。</span><span class="sxs-lookup"><span data-stu-id="b4641-150">Ethernet via USB may be enabled for LAN connectivity if required.</span></span>
   * <span data-ttu-id="b4641-151">未管理。</span><span class="sxs-lookup"><span data-stu-id="b4641-151">Not Managed.</span></span>
   * <span data-ttu-id="b4641-152">裝置登入的本機使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="b4641-152">Local user account for device sign in.</span></span>
     * <span data-ttu-id="b4641-153">HoloLens 2 只支援1個本機帳戶。</span><span class="sxs-lookup"><span data-stu-id="b4641-153">HoloLens 2 supports only 1 local account.</span></span>
   * <span data-ttu-id="b4641-154">根據特定使用案例，會透過置備套件來套用不同的裝置鎖定設定等級。</span><span class="sxs-lookup"><span data-stu-id="b4641-154">Varying levels of device lockdown configurations are applied via Provisioning Packages based on specific use cases.</span></span> <span data-ttu-id="b4641-155">由於安全的環境需求，這些設定通常會受到很大的限制。</span><span class="sxs-lookup"><span data-stu-id="b4641-155">These configurations are typically very restricted due to secure environment requirements.</span></span>
   * <span data-ttu-id="b4641-156">一或多個應用程式是透過 [預配套件] 來部署</span><span class="sxs-lookup"><span data-stu-id="b4641-156">One or more applications are deployed via Provisioning Package</span></span>

 * <span data-ttu-id="b4641-157">常見的難題</span><span class="sxs-lookup"><span data-stu-id="b4641-157">Common Challenges</span></span>
   * <span data-ttu-id="b4641-158">您可以透過預配套件使用一組有限的設定</span><span class="sxs-lookup"><span data-stu-id="b4641-158">There are a limited set of configurations available through Provisioning Packages</span></span>
   * <span data-ttu-id="b4641-159">雲端服務無法被利用，因此限制 HoloLens 2 的功能。</span><span class="sxs-lookup"><span data-stu-id="b4641-159">Cloud services are not able to be leveraged, therefore limiting the HoloLens 2 capabilities.</span></span>
   * <span data-ttu-id="b4641-160">更高的管理負荷，因為這些裝置必須手動設定、設定及更新。</span><span class="sxs-lookup"><span data-stu-id="b4641-160">Higher administrative overhead since these devices have to be setup, configured, and updated manually.</span></span>

<span data-ttu-id="b4641-161">如需與此案例類似的部署指南，請參閱我們的 [離線安全部署指南](hololens-common-scenarios-offline-secure.md)。</span><span class="sxs-lookup"><span data-stu-id="b4641-161">For a deployment guide that is similar to this scenario please review our [Offline Secure Deployment Guide](hololens-common-scenarios-offline-secure.md).</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="b4641-162">部署指南–離線安全 HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="b4641-162">Deployment Guide – Offline Secure HoloLens 2</span></span>](hololens-common-scenarios-offline-secure.md)
