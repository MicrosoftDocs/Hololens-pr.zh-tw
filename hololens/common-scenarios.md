---
title: 常見的基礎結構部署案例
description: 瞭解一些根據混合實境的不同基礎結構部署而最常見的部署案例。
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
ms.openlocfilehash: 4b9bd4335e45180276d69af2ce5f33a38ecb800f
ms.sourcegitcommit: d7c86ccad7be32f7223d4b801083798454fda740
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/25/2021
ms.locfileid: "11448491"
---
# <a name="common-infrastructure-deployment-scenarios-overview"></a><span data-ttu-id="fc3ec-104">一般基礎結構部署案例概觀</span><span class="sxs-lookup"><span data-stu-id="fc3ec-104">Common Infrastructure Deployment Scenarios Overview</span></span>

<span data-ttu-id="fc3ec-105">下列資訊提供企業內部署及管理 Microsoft HoloLens 2 裝置時三種常見案例的高層架構概觀。</span><span class="sxs-lookup"><span data-stu-id="fc3ec-105">This following information provides a high-level architecture overview for three common scenarios when deploying and managing Microsoft HoloLens 2 devices within the enterprise.</span></span> <span data-ttu-id="fc3ec-106">您管理裝置及存取組織資源方式通常主要取決於已有的因素。</span><span class="sxs-lookup"><span data-stu-id="fc3ec-106">Often how you manage your devices and how to access your organization's resources is largely determined by factors already in place.</span></span> <span data-ttu-id="fc3ec-107">根據現有的基礎結構，我們邀請您查看下列案例的常見裝置管理樣式，並試用我們的指南，以在符合您需求的情境中部署。</span><span class="sxs-lookup"><span data-stu-id="fc3ec-107">Based on the existing infrastructure we invite you to review the common device management style in the following scenarios, and try out our guides for deploying in the scenario matching your needs.</span></span>

## <a name="scenarios"></a><span data-ttu-id="fc3ec-108">案例</span><span class="sxs-lookup"><span data-stu-id="fc3ec-108">Scenarios</span></span>

<span data-ttu-id="fc3ec-109">下圖代表 HoloLens 2 部署的三種常見案例。</span><span class="sxs-lookup"><span data-stu-id="fc3ec-109">The diagram below represents three typical scenarios for HoloLens 2 deployments.</span></span>
![分析圖](images/scenarios.jpg)

### <a name="scenario-a-deploy-to-cloud-connect-devices"></a><span data-ttu-id="fc3ec-111">案例 A：部署至雲端連接裝置</span><span class="sxs-lookup"><span data-stu-id="fc3ec-111">Scenario A: Deploy to cloud connect devices</span></span>

<span data-ttu-id="fc3ec-112">HoloLens 2 主要部署在公司網路外部的環境中使用。</span><span class="sxs-lookup"><span data-stu-id="fc3ec-112">HoloLens 2 is deployed for use primarily in environments external to a corporate network.</span></span> <span data-ttu-id="fc3ec-113">無法透過 VPN 存取或限制公司資源。</span><span class="sxs-lookup"><span data-stu-id="fc3ec-113">Corporate resources aren't accessed or may be limited through VPN.</span></span> <span data-ttu-id="fc3ec-114">此部署與公司內受管理的行動裝置類似。</span><span class="sxs-lookup"><span data-stu-id="fc3ec-114">This  deployment is similar to managed mobile devices within a company.</span></span>
 * <span data-ttu-id="fc3ec-115">基本常見配置</span><span class="sxs-lookup"><span data-stu-id="fc3ec-115">Basic Common Configurations</span></span>
   * <span data-ttu-id="fc3ec-116">Wi-Fi網路通常會完全開放至網際網路和雲端服務。</span><span class="sxs-lookup"><span data-stu-id="fc3ec-116">Wi-Fi networks are typically fully open to the Internet and Cloud services.</span></span>
   * <span data-ttu-id="fc3ec-117">使用行動裝置管理加入 Azure AD (MDM) 自動註冊 --MDM (Intune) 管理</span><span class="sxs-lookup"><span data-stu-id="fc3ec-117">Azure AD Join with Mobile Device Management (MDM) Auto Enrollment--MDM (Intune) Managed</span></span>
   * <span data-ttu-id="fc3ec-118">使用者使用自己的公司帳戶 (Azure AD) </span><span class="sxs-lookup"><span data-stu-id="fc3ec-118">Users sign in with their own corporate account (Azure AD)</span></span>
     * <span data-ttu-id="fc3ec-119">支援每個裝置的單一或多個使用者</span><span class="sxs-lookup"><span data-stu-id="fc3ec-119">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="fc3ec-120">根據特定使用案例，從完全開啟到單一應用程式資訊站，會採用不同層級的裝置鎖定配置。</span><span class="sxs-lookup"><span data-stu-id="fc3ec-120">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="fc3ec-121">一或多個應用程式是透過 MDM 部署</span><span class="sxs-lookup"><span data-stu-id="fc3ec-121">One or more applications are deployed via MDM</span></span>

* <span data-ttu-id="fc3ec-122">常見的挑戰</span><span class="sxs-lookup"><span data-stu-id="fc3ec-122">Common Challenges</span></span>
   * <span data-ttu-id="fc3ec-123">根據案例需求，決定要套用哪些 MDM 組配置至 HoloLens 2。</span><span class="sxs-lookup"><span data-stu-id="fc3ec-123">Determining which MDM configurations to apply to the HoloLens 2 based on scenario requirements.</span></span>

<span data-ttu-id="fc3ec-124">如要瞭解類似案例的部署指南，請閱閱我們的雲端連接 [HoloLens 2 與遠端協助指南](hololens2-cloud-connected-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="fc3ec-124">For a deployment guide that is similar to scenario A review our guide for [Cloud connected HoloLens 2 with Remote Assist](hololens2-cloud-connected-overview.md).</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="fc3ec-125">部署指南 – 雲端連接的 HoloLens 2 與遠端輔助</span><span class="sxs-lookup"><span data-stu-id="fc3ec-125">Deployment Guide – Cloud connected HoloLens 2 with Remote Assist</span></span>](hololens2-cloud-connected-overview.md)

### <a name="scenario-b-deploy-inside-your-organizations-network"></a><span data-ttu-id="fc3ec-126">案例 B：在組織網路內部署</span><span class="sxs-lookup"><span data-stu-id="fc3ec-126">Scenario B: Deploy inside your organization's network</span></span>

<span data-ttu-id="fc3ec-127">HoloLens 2 主要部署在擁有內部公司資源存取權的公司網路上。</span><span class="sxs-lookup"><span data-stu-id="fc3ec-127">HoloLens 2 is deployed for use primarily on the corporate network with access to internal corporate resources.</span></span> <span data-ttu-id="fc3ec-128">網際網路和雲端服務可能受到限制。</span><span class="sxs-lookup"><span data-stu-id="fc3ec-128">Internet and cloud services may be limited.</span></span> <span data-ttu-id="fc3ec-129">此部署是大多數 Windows 10 電腦的典型部署。</span><span class="sxs-lookup"><span data-stu-id="fc3ec-129">This deployment is a typical deployment for most Windows 10 PCs.</span></span>

 * <span data-ttu-id="fc3ec-130">基本常見配置</span><span class="sxs-lookup"><span data-stu-id="fc3ec-130">Basic Common Configurations</span></span>
   * <span data-ttu-id="fc3ec-131">Wi-Fi網路是一種內部公司網路，可存取內部資源，且網際網路或雲端服務的存取受到限制。</span><span class="sxs-lookup"><span data-stu-id="fc3ec-131">Wi-Fi network is an internal corporate network with access to internal resources, and limited access to the internet or Cloud services.</span></span>
   * <span data-ttu-id="fc3ec-132">使用 MDM 自動註冊加入 Azure AD</span><span class="sxs-lookup"><span data-stu-id="fc3ec-132">Azure AD Join with MDM Auto Enrollment</span></span>
   * <span data-ttu-id="fc3ec-133">MDM (Intune) Managed</span><span class="sxs-lookup"><span data-stu-id="fc3ec-133">MDM (Intune) Managed</span></span>
   * <span data-ttu-id="fc3ec-134">使用者使用自己的公司帳戶 (Azure AD) </span><span class="sxs-lookup"><span data-stu-id="fc3ec-134">Users sign in with their own corporate account (Azure AD)</span></span>
     * <span data-ttu-id="fc3ec-135">支援每個裝置的單一或多個使用者</span><span class="sxs-lookup"><span data-stu-id="fc3ec-135">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="fc3ec-136">根據特定使用案例，從完全開啟到單一應用程式資訊站，會採用不同層級的裝置鎖定配置。</span><span class="sxs-lookup"><span data-stu-id="fc3ec-136">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="fc3ec-137">一或多個應用程式是透過 MDM 部署</span><span class="sxs-lookup"><span data-stu-id="fc3ec-137">One or more applications are deployed via MDM</span></span>

 * <span data-ttu-id="fc3ec-138">常見的挑戰</span><span class="sxs-lookup"><span data-stu-id="fc3ec-138">Common Challenges</span></span>
   * <span data-ttu-id="fc3ec-139">HoloLens 2 不支援內部部署 AD 連接或 SCCM。</span><span class="sxs-lookup"><span data-stu-id="fc3ec-139">HoloLens 2 doesn't support on premises AD join or SCCM.</span></span> <span data-ttu-id="fc3ec-140">只有 Azure AD 會與 MDM 加入。</span><span class="sxs-lookup"><span data-stu-id="fc3ec-140">Only Azure AD join with MDM.</span></span> <span data-ttu-id="fc3ec-141">目前許多公司仍在此案例部署 Windows 10 電腦，就像內部部署 AD 已加入裝置一樣，由 System Center Configuration Manager (SCCM) 管理，而且可能尚未部署/配置基礎結構，以透過雲端式 MDM 解決方案管理內部 Windows 10 裝置。</span><span class="sxs-lookup"><span data-stu-id="fc3ec-141">Many companies today still deploy Windows 10 PCs in this scenario as on premises AD joined devices, managed by System Center Configuration Manager (SCCM) and may not have the infrastructure deployed/configured for managing internal Windows 10 devices via cloud-based MDM solutions.</span></span>
   * <span data-ttu-id="fc3ec-142">HoloLens 2 是雲端第一個裝置，因此在使用者驗證、OS 更新、MDM 管理等方面，高度仰賴網際網路和雲端連接服務。</span><span class="sxs-lookup"><span data-stu-id="fc3ec-142">As HoloLens 2 is a cloud first device, it relies heavily on internet and cloud connected services for User authentication, OS updates, MDM management, and so on.</span></span> <span data-ttu-id="fc3ec-143">當連接到公司網路時，Proxy/防火牆規則很可能會需要調整，才能啟用 HoloLens 2 及其上執行的應用程式的存取。</span><span class="sxs-lookup"><span data-stu-id="fc3ec-143">When connecting to a corporate network, Proxy/Firewall rules will most likely need to be adjusted to enable access for HoloLens 2 and the applications that run on it.</span></span>
   * <span data-ttu-id="fc3ec-144">公司Wi-Fi連接通常需要憑證來驗證裝置或使用者至網路。</span><span class="sxs-lookup"><span data-stu-id="fc3ec-144">Corporate Wi-Fi connectivity typically requires certificates to authenticate the device or user to the network.</span></span> <span data-ttu-id="fc3ec-145">透過 MDM 將憑證部署到 Windows 10 裝置所需的基礎結構或設定可能難以設定。</span><span class="sxs-lookup"><span data-stu-id="fc3ec-145">The required infrastructure or settings to deploy certificates to Windows 10 devices through MDM can be challenging to configure.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="fc3ec-146">部署指南 – 使用 Dynamics 365 指南與公司連接的 HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="fc3ec-146">Deployment Guide – Corporate connected HoloLens 2 with Dynamics 365 Guides</span></span>](hololens2-corp-connected-overview.md)

### <a name="scenario-c-deploy-in-secure-offline-environment"></a><span data-ttu-id="fc3ec-147">案例 C：在安全的離線環境中部署</span><span class="sxs-lookup"><span data-stu-id="fc3ec-147">Scenario C: Deploy in secure offline environment</span></span>

<span data-ttu-id="fc3ec-148">HoloLens 2 主要部署為離線使用，沒有網路或網際網路存取。</span><span class="sxs-lookup"><span data-stu-id="fc3ec-148">HoloLens 2 is deployed for use primarily offline with no network or internet access.</span></span> <span data-ttu-id="fc3ec-149">這是高度安全或機密位置的典型部署。</span><span class="sxs-lookup"><span data-stu-id="fc3ec-149">This is a typical deployment for highly secure or confidential locations.</span></span>
 * <span data-ttu-id="fc3ec-150">基本常見配置</span><span class="sxs-lookup"><span data-stu-id="fc3ec-150">Basic Common Configurations</span></span>
   * <span data-ttu-id="fc3ec-151">Wi-Fi已停用連接。</span><span class="sxs-lookup"><span data-stu-id="fc3ec-151">Wi-Fi connectivity is disabled.</span></span> <span data-ttu-id="fc3ec-152">如有需要，可能已啟用透過 USB 的乙太網路進行 LAN 連接。</span><span class="sxs-lookup"><span data-stu-id="fc3ec-152">Ethernet via USB may be enabled for LAN connectivity if necessary.</span></span>
   * <span data-ttu-id="fc3ec-153">未管理。</span><span class="sxs-lookup"><span data-stu-id="fc3ec-153">Not Managed.</span></span>
   * <span data-ttu-id="fc3ec-154">裝置登錄的本地使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="fc3ec-154">Local user account for device sign-in.</span></span>
     * <span data-ttu-id="fc3ec-155">HoloLens 2 僅支援一個本地帳戶。</span><span class="sxs-lookup"><span data-stu-id="fc3ec-155">HoloLens 2 supports only one local account.</span></span>
   * <span data-ttu-id="fc3ec-156">根據特定使用案例，會透過部署套件套用不同層級的裝置鎖定配置。</span><span class="sxs-lookup"><span data-stu-id="fc3ec-156">Varying levels of device lockdown configurations are applied via Provisioning Packages based on specific use cases.</span></span> <span data-ttu-id="fc3ec-157">由於安全的環境需求，這些配置通常會受到限制。</span><span class="sxs-lookup"><span data-stu-id="fc3ec-157">These configurations are typically restricted because of secure environment requirements.</span></span>
   * <span data-ttu-id="fc3ec-158">一或多個應用程式會透過部署套件進行部署</span><span class="sxs-lookup"><span data-stu-id="fc3ec-158">One or more applications are deployed via Provisioning Package</span></span>

 * <span data-ttu-id="fc3ec-159">常見的挑戰</span><span class="sxs-lookup"><span data-stu-id="fc3ec-159">Common Challenges</span></span>
   * <span data-ttu-id="fc3ec-160">透過資源配置套件提供一組有限的設定</span><span class="sxs-lookup"><span data-stu-id="fc3ec-160">There's a limited set of configurations available through Provisioning Packages</span></span>
   * <span data-ttu-id="fc3ec-161">雲端服務無法使用，因此會限制 HoloLens 2 功能。</span><span class="sxs-lookup"><span data-stu-id="fc3ec-161">Cloud services aren't able to be used, therefore limiting the HoloLens 2 capabilities.</span></span>
   * <span data-ttu-id="fc3ec-162">由於這些裝置必須手動設定、設定和更新，因此系統管理費用較高。</span><span class="sxs-lookup"><span data-stu-id="fc3ec-162">Higher administrative overhead since these devices have to be set up, configured, and updated manually.</span></span>

<span data-ttu-id="fc3ec-163">若要瞭解類似此案例的部署指南，請閱覽我們的 [離線安全部署指南](hololens-common-scenarios-offline-secure.md)。</span><span class="sxs-lookup"><span data-stu-id="fc3ec-163">For a deployment guide that is similar to this scenario review our [Offline Secure Deployment Guide](hololens-common-scenarios-offline-secure.md).</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="fc3ec-164">部署指南 - 離線安全 HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="fc3ec-164">Deployment Guide – Offline Secure HoloLens 2</span></span>](hololens-common-scenarios-offline-secure.md)
