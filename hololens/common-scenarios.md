---
title: 常見的基礎結構部署案例
ms.assetid: 651d0430-bfbc-4685-a4fd-db7c33ce9325
ms.date: 6/30/2020
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
ms.openlocfilehash: f8d69fc988afabad5f4ae1cce9003381ceb8e68c
ms.sourcegitcommit: 29755f5af0086a43c532fb5a9a4ae65c36bc82de
ms.contentlocale: zh-TW
ms.lasthandoff: 07/07/2020
ms.locfileid: "10857873"
---
# <span data-ttu-id="4ed76-103">常見的基礎結構部署案例</span><span class="sxs-lookup"><span data-stu-id="4ed76-103">Common Infrastructure Deployment Scenarios</span></span>
<span data-ttu-id="4ed76-104">下列資訊提供在企業中部署和管理 Microsoft HoloLens 2 裝置的三種常見案例的高層結構概覽。</span><span class="sxs-lookup"><span data-stu-id="4ed76-104">This following information provides a high-level architecture overview for three common scenarios when deploying and managing Microsoft HoloLens 2 devices within the enterprise.</span></span>

## <span data-ttu-id="4ed76-105">案例</span><span class="sxs-lookup"><span data-stu-id="4ed76-105">Scenarios</span></span>

<span data-ttu-id="4ed76-106">下圖代表 HoloLens 2 部署的三種典型案例。</span><span class="sxs-lookup"><span data-stu-id="4ed76-106">The diagram below represents three typical scenarios for HoloLens 2 deployments.</span></span> 
![案例](images/scenarios.jpg)

### <span data-ttu-id="4ed76-108">案例 A</span><span class="sxs-lookup"><span data-stu-id="4ed76-108">Scenario A</span></span>

<span data-ttu-id="4ed76-109">已部署 HoloLens 2，主要用於公司網路中的外部環境。</span><span class="sxs-lookup"><span data-stu-id="4ed76-109">HoloLens 2 is deployed for use primarily in environments external to a corporate network.</span></span> <span data-ttu-id="4ed76-110">公司資源無法存取，或可能受 VPN 限制。</span><span class="sxs-lookup"><span data-stu-id="4ed76-110">Corporate resources are not accessed or may be limited through VPN.</span></span> <span data-ttu-id="4ed76-111">這個部署與公司內受管理的行動裝置非常類似。</span><span class="sxs-lookup"><span data-stu-id="4ed76-111">This is a deployment very similar to managed mobile devices within a company.</span></span>
 * <span data-ttu-id="4ed76-112">基本常見設定</span><span class="sxs-lookup"><span data-stu-id="4ed76-112">Basic Common Configurations</span></span>
   * <span data-ttu-id="4ed76-113">Wi-fi 網路通常會完全開啟至網際網路和雲端服務。</span><span class="sxs-lookup"><span data-stu-id="4ed76-113">Wi-Fi networks are typically fully open to the Internet and Cloud services.</span></span>
   * <span data-ttu-id="4ed76-114">使用 MDM 自動註冊的 Azure AD 聯接--MDM （Intune）管理</span><span class="sxs-lookup"><span data-stu-id="4ed76-114">Azure AD Join with MDM Auto Enrollment -- MDM (Intune) Managed</span></span>
   * <span data-ttu-id="4ed76-115">使用者以自己的公司帳戶（AAD）登入</span><span class="sxs-lookup"><span data-stu-id="4ed76-115">Users sign in with their own corporate account (AAD)</span></span> 
     * <span data-ttu-id="4ed76-116">每個裝置支援單一或多個使用者</span><span class="sxs-lookup"><span data-stu-id="4ed76-116">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="4ed76-117">根據特定的使用案例，從完全開啟到單一應用程式亭，就會套用各種不同的裝置鎖定設定等級。</span><span class="sxs-lookup"><span data-stu-id="4ed76-117">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="4ed76-118">一或多個應用程式是透過 MDM 部署</span><span class="sxs-lookup"><span data-stu-id="4ed76-118">One or more applications are deployed via MDM</span></span>

* <span data-ttu-id="4ed76-119">常見的難題</span><span class="sxs-lookup"><span data-stu-id="4ed76-119">Common Challenges</span></span>
   * <span data-ttu-id="4ed76-120">根據案例需求決定要套用至 HoloLens 2 的 MDM 設定。</span><span class="sxs-lookup"><span data-stu-id="4ed76-120">Determining which MDM configurations to apply to the HoloLens 2 based on scenario requirements.</span></span>

### <span data-ttu-id="4ed76-121">案例 B</span><span class="sxs-lookup"><span data-stu-id="4ed76-121">Scenario B</span></span>

<span data-ttu-id="4ed76-122">HoloLens 2 已部署，主要用於公司網路，可存取內部公司資源。</span><span class="sxs-lookup"><span data-stu-id="4ed76-122">HoloLens 2 is deployed for use primarily on the corporate network with access to internal corporate resources.</span></span> <span data-ttu-id="4ed76-123">網際網路和雲端服務可能受到限制。</span><span class="sxs-lookup"><span data-stu-id="4ed76-123">Internet and cloud services may be limited.</span></span> <span data-ttu-id="4ed76-124">這是大部分 Windows 10 電腦的典型部署。</span><span class="sxs-lookup"><span data-stu-id="4ed76-124">This is a typical deployment for most Windows 10 PCs.</span></span>
 * <span data-ttu-id="4ed76-125">基本常見設定</span><span class="sxs-lookup"><span data-stu-id="4ed76-125">Basic Common Configurations</span></span>
   * <span data-ttu-id="4ed76-126">Wi-fi 網路是一種內部公司網路，有權存取內部資源，以及網際網路或雲端服務的有限存取權。</span><span class="sxs-lookup"><span data-stu-id="4ed76-126">Wi-Fi network is an internal corporate network with access to internal resources, and limited access to the internet or Cloud services.</span></span>
   * <span data-ttu-id="4ed76-127">使用 MDM 自動註冊的 Azure AD 加入</span><span class="sxs-lookup"><span data-stu-id="4ed76-127">Azure AD Join with MDM Auto Enrollment</span></span> 
   * <span data-ttu-id="4ed76-128">MDM （Intune）管理</span><span class="sxs-lookup"><span data-stu-id="4ed76-128">MDM (Intune) Managed</span></span>
   * <span data-ttu-id="4ed76-129">使用者以自己的公司帳戶（AAD）登入</span><span class="sxs-lookup"><span data-stu-id="4ed76-129">Users sign in with their own corporate account (AAD)</span></span>
     * <span data-ttu-id="4ed76-130">每個裝置支援單一或多個使用者</span><span class="sxs-lookup"><span data-stu-id="4ed76-130">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="4ed76-131">根據特定的使用案例，從完全開啟到單一應用程式亭，就會套用各種不同的裝置鎖定設定等級。</span><span class="sxs-lookup"><span data-stu-id="4ed76-131">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="4ed76-132">一或多個應用程式是透過 MDM 部署</span><span class="sxs-lookup"><span data-stu-id="4ed76-132">One or more applications are deployed via MDM</span></span>

 * <span data-ttu-id="4ed76-133">常見的難題</span><span class="sxs-lookup"><span data-stu-id="4ed76-133">Common Challenges</span></span>
   * <span data-ttu-id="4ed76-134">HoloLens 2 不支援內部部署廣告連接或 SCCM。</span><span class="sxs-lookup"><span data-stu-id="4ed76-134">HoloLens 2 does not support on premises AD join or SCCM.</span></span> <span data-ttu-id="4ed76-135">僅限使用 MDM 的 Azure AD 加入。</span><span class="sxs-lookup"><span data-stu-id="4ed76-135">Only Azure AD join with MDM.</span></span> <span data-ttu-id="4ed76-136">在此案例中，許多公司現在仍會部署 Windows 10 電腦，就像是由 System Center Configuration Manager （SCCM）管理，而且可能沒有部署/設定的基礎結構，可透過雲端的 MDM 解決方案來管理內部 Windows 10 裝置。</span><span class="sxs-lookup"><span data-stu-id="4ed76-136">Many companies today still deploy Windows 10 PCs in this scenario as on premises AD joined devices, managed by System Center Configuration Manager (SCCM) and may not have the infrastructure deployed/configured for managing internal Windows 10 devices via cloud based MDM solutions.</span></span>
   * <span data-ttu-id="4ed76-137">因為 HoloLens 2 是雲端第一個裝置，所以它大量依賴網際網路和雲端聯機服務來進行使用者驗證、作業系統更新、MDM 管理等。連線至公司網路時，最可能需要調整 Proxy/防火牆規則，才能啟用 HoloLens 2 以及在其上執行的應用程式的存取權。</span><span class="sxs-lookup"><span data-stu-id="4ed76-137">As HoloLens 2 is a cloud first device, it relies heavily on internet and cloud connected services for User authentication, OS updates, MDM management, etc. When connecting to a corporate network, Proxy/Firewall rules will most likely need to be adjusted to enable access for HoloLens 2 and the applications that run on it.</span></span> 
   * <span data-ttu-id="4ed76-138">公司 Wi-fi 連線通常需要認證，才能向網路驗證裝置或使用者。</span><span class="sxs-lookup"><span data-stu-id="4ed76-138">Corporate Wi-Fi connectivity typically requires certificates to authenticate the device or user to the network.</span></span> <span data-ttu-id="4ed76-139">透過 MDM 將憑證部署到 Windows 10 裝置所需的基礎結構或設定，可能很難設定。</span><span class="sxs-lookup"><span data-stu-id="4ed76-139">The required infrastructure or settings to deploy certificates to Windows 10 devices through MDM can be challenging to configure.</span></span>

### <span data-ttu-id="4ed76-140">案例 C</span><span class="sxs-lookup"><span data-stu-id="4ed76-140">Scenario C</span></span>

<span data-ttu-id="4ed76-141">HoloLens 2 已部署，主要用於離線使用，沒有網路或網際網路存取。</span><span class="sxs-lookup"><span data-stu-id="4ed76-141">HoloLens 2 is deployed for use primarily offline with no network or internet access.</span></span> <span data-ttu-id="4ed76-142">這是高度安全或機密位置的典型部署。</span><span class="sxs-lookup"><span data-stu-id="4ed76-142">This is a typical deployment for highly secure or confidential locations.</span></span>
 * <span data-ttu-id="4ed76-143">基本常見設定</span><span class="sxs-lookup"><span data-stu-id="4ed76-143">Basic Common Configurations</span></span>
   * <span data-ttu-id="4ed76-144">Wi-fi 連接已停用。</span><span class="sxs-lookup"><span data-stu-id="4ed76-144">Wi-Fi connectivity is disabled.</span></span> <span data-ttu-id="4ed76-145">如果需要，可以透過 USB 乙太網上的乙太網路進行局域網連線。</span><span class="sxs-lookup"><span data-stu-id="4ed76-145">Ethernet via USB may be enabled for LAN connectivity if required.</span></span>
   * <span data-ttu-id="4ed76-146">未管理。</span><span class="sxs-lookup"><span data-stu-id="4ed76-146">Not Managed.</span></span>
   * <span data-ttu-id="4ed76-147">裝置登入的本機使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="4ed76-147">Local user account for device sign in.</span></span>
     * <span data-ttu-id="4ed76-148">HoloLens 2 只支援1個本機帳戶。</span><span class="sxs-lookup"><span data-stu-id="4ed76-148">HoloLens 2 supports only 1 local account.</span></span>
   * <span data-ttu-id="4ed76-149">根據特定使用案例，會透過置備套件來套用不同的裝置鎖定設定等級。</span><span class="sxs-lookup"><span data-stu-id="4ed76-149">Varying levels of device lockdown configurations are applied via Provisioning Packages based on specific use cases.</span></span> <span data-ttu-id="4ed76-150">由於安全的環境需求，這些設定通常會受到很大的限制。</span><span class="sxs-lookup"><span data-stu-id="4ed76-150">These configurations are typically very restricted due to secure environment requirements.</span></span>
   * <span data-ttu-id="4ed76-151">一或多個應用程式是透過 [預配套件] 來部署</span><span class="sxs-lookup"><span data-stu-id="4ed76-151">One or more applications are deployed via Provisioning Package</span></span>

 * <span data-ttu-id="4ed76-152">常見的難題</span><span class="sxs-lookup"><span data-stu-id="4ed76-152">Common Challenges</span></span>
   * <span data-ttu-id="4ed76-153">您可以透過預配套件使用一組有限的設定</span><span class="sxs-lookup"><span data-stu-id="4ed76-153">There are a limited set of configurations available through Provisioning Packages</span></span>
   * <span data-ttu-id="4ed76-154">雲端服務無法被利用，因此限制 HoloLens 2 的功能。</span><span class="sxs-lookup"><span data-stu-id="4ed76-154">Cloud services are not able to be leveraged, therefore limiting the HoloLens 2 capabilities.</span></span>
   * <span data-ttu-id="4ed76-155">更高的管理負荷，因為這些裝置必須手動設定、設定及更新。</span><span class="sxs-lookup"><span data-stu-id="4ed76-155">Higher administrative overhead since these devices have to be setup, configured, and updated manually.</span></span>
