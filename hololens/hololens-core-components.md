---
title: 在商業環境中規劃 HoloLens 2 部署
description: 瞭解在企業環境中部署和管理 HoloLens 的核心需求，包括基礎結構、azure active directory 和行動裝置管理。
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: joyjaz
ms.author: v-jjaswinski
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 05/21/2021
appliesto:
- HoloLens 2
ms.openlocfilehash: 43162389eae82bc09135c62acd40d71048d14db1
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639075"
---
# <a name="planning-hololens-2-deployment-in-a-commercial-environment"></a><span data-ttu-id="257c3-103">在商業環境中規劃 HoloLens 2 部署</span><span class="sxs-lookup"><span data-stu-id="257c3-103">Planning HoloLens 2 deployment in a commercial environment</span></span>

## <a name="overview"></a><span data-ttu-id="257c3-104">概觀</span><span class="sxs-lookup"><span data-stu-id="257c3-104">Overview</span></span>

> [!NOTE]
> <span data-ttu-id="257c3-105">本總覽旨在協助 IT 專業人員瞭解部署及管理組織內 Microsoft HoloLens 2 裝置的考慮。</span><span class="sxs-lookup"><span data-stu-id="257c3-105">This overview is intended to help IT professionals understand considerations for deploying and managing Microsoft HoloLens 2 devices within an organization.</span></span> <span data-ttu-id="257c3-106">針對裝置終端使用者，請參閱[讓您的 HoloLens 2 準備好開始使用](hololens2-setup.md)。</span><span class="sxs-lookup"><span data-stu-id="257c3-106">For device end users, see [Get your HoloLens 2 ready to use](hololens2-setup.md) to get started.</span></span>

<span data-ttu-id="257c3-107">HoloLens 2 會在 Windows 10 全像攝影版上執行，這可為組織提供強大、有彈性、內建的行動裝置和應用程式管理技術。</span><span class="sxs-lookup"><span data-stu-id="257c3-107">HoloLens 2 runs on Windows 10 Holographic which provides organizations with robust, flexible, built-in mobile device and app management technologies.</span></span> <span data-ttu-id="257c3-108">Windows 10 全像攝影版支援端對端裝置生命週期管理，讓公司控制其裝置、資料和應用程式。</span><span class="sxs-lookup"><span data-stu-id="257c3-108">Windows 10 Holographic supports end-to-end device lifecycle management to give companies control over their devices, data, and apps.</span></span> <span data-ttu-id="257c3-109">您可以使用全方位的行動裝置管理解決方案，輕鬆地將 HoloLens 2 併入標準生命週期實務中，從裝置註冊、設定和應用程式管理到維護和淘汰。</span><span class="sxs-lookup"><span data-stu-id="257c3-109">The HoloLens 2 can easily be incorporated into standard lifecycle practices, from device enrollment, configuration, and application management to maintenance and retirement using a comprehensive mobile device management solution.</span></span>

<span data-ttu-id="257c3-110">下列步驟和影片可協助引導您完成在貴組織內 HoloLens 2 採用的流程。</span><span class="sxs-lookup"><span data-stu-id="257c3-110">The following steps and video can help guide you through the process of HoloLens 2 adoption within your organization.</span></span>

| &nbsp; | &nbsp; |
|--|--|
| ![步驟 1](images/1green.png)| <br/> <span data-ttu-id="257c3-112">**[常見的部署案例](hololens-requirements.md)**：瞭解部署案例，並探索部署 HoloLens 2 裝置所需的核心元件。</span><span class="sxs-lookup"><span data-stu-id="257c3-112">**[Common Deployment Scenarios](hololens-requirements.md)**: Understand deployment scenarios and explore the core components needed to deploy HoloLens 2 devices.</span></span> |
| ![步驟 2](images/2green.png)| <br/> <span data-ttu-id="257c3-114">**[準備](#prepare)**：熟悉 HoloLens 2 所需的基礎結構基本架構。</span><span class="sxs-lookup"><span data-stu-id="257c3-114">**[Prepare](#prepare)**: Become familiar with the infrastructure essentials needed for HoloLens 2.</span></span> |
| ![步驟 3](images/3green.png) | <br/> <span data-ttu-id="257c3-116">**[設定](#configure)**：瞭解如何設定雲端式部署的基本元件。</span><span class="sxs-lookup"><span data-stu-id="257c3-116">**[Configure](#configure)**: Learn how to configure your essential components for a cloud-based deployment.</span></span> |
| ![步驟 4](images/4green.png) | <br/> <span data-ttu-id="257c3-118">**[部署](#deploy)**：探索如何部署您的裝置，並安全且有效率地散發您的應用程式。</span><span class="sxs-lookup"><span data-stu-id="257c3-118">**[Deploy](#deploy)**: Discover how to deploy your devices and distribute your applications securely and efficiently.</span></span> |
| ![步驟 5](images/5green.png) | <br/> <span data-ttu-id="257c3-120">**[維護](#maintain)**：找出適當維護您 HoloLens 2 裝置狀態所需的內容，並確保符合公司原則。</span><span class="sxs-lookup"><span data-stu-id="257c3-120">**[Maintain](#maintain)**: Find out what's needed to properly maintain the state of your HoloLens 2 devices and ensure compliance with corporate policy.</span></span> |

<br/>

> [!VIDEO https://channel9.msdn.com/Shows/IT-Ops-Talk/HoloLens-2-Deployment-Overview/player]

## <a name="prepare"></a><span data-ttu-id="257c3-121">準備</span><span class="sxs-lookup"><span data-stu-id="257c3-121">Prepare</span></span>

<span data-ttu-id="257c3-122">瞭解支援一組完整的 HoloLens 2 功能所需的基本基礎結構服務。</span><span class="sxs-lookup"><span data-stu-id="257c3-122">Learn about essential infrastructure services required to support the full set of HoloLens 2 capabilities.</span></span>

| <span data-ttu-id="257c3-123">元件</span><span class="sxs-lookup"><span data-stu-id="257c3-123">Component</span></span> | <span data-ttu-id="257c3-124">描述</span><span class="sxs-lookup"><span data-stu-id="257c3-124">Description</span></span> |
|-----------|------------|
| [<span data-ttu-id="257c3-125">Azure AD</span><span class="sxs-lookup"><span data-stu-id="257c3-125">Azure AD</span></span>](hololens-identity.md) | <span data-ttu-id="257c3-126">提供 HoloLens 2 的身分識別和存取管理</span><span class="sxs-lookup"><span data-stu-id="257c3-126">Provides identity and access management for the HoloLens 2</span></span>  |
| [<span data-ttu-id="257c3-127">行動裝置管理</span><span class="sxs-lookup"><span data-stu-id="257c3-127">Mobile Device Management</span></span>](hololens-mdm-configure.md)| <span data-ttu-id="257c3-128">管理連線到您租使用者的 HoloLens 2 裝置</span><span class="sxs-lookup"><span data-stu-id="257c3-128">Manages HoloLens 2 devices connected to your tenant</span></span>  |
| [<span data-ttu-id="257c3-129">Wi-fi 網路</span><span class="sxs-lookup"><span data-stu-id="257c3-129">Wi-Fi Network</span></span>](hololens-commercial-infrastructure.md)| <span data-ttu-id="257c3-130">有 Wi-Fi 可供使用，且裝置可連線至網際網路</span><span class="sxs-lookup"><span data-stu-id="257c3-130">Wi-Fi is available and devices can be connected to the Internet</span></span>  |

## <a name="configure"></a><span data-ttu-id="257c3-131">設定</span><span class="sxs-lookup"><span data-stu-id="257c3-131">Configure</span></span>

<span data-ttu-id="257c3-132">使用 Intune 和 Autopilot 作為低觸控解決方案，為您的組織 Azure AD 租使用者和 MDM 註冊及設定 HoloLens 2。</span><span class="sxs-lookup"><span data-stu-id="257c3-132">Use Intune and Autopilot as low-touch solutions for enrolling and configuring HoloLens 2 to your organization’s Azure AD tenant and MDM.</span></span>

| <span data-ttu-id="257c3-133">元件</span><span class="sxs-lookup"><span data-stu-id="257c3-133">Component</span></span> | <span data-ttu-id="257c3-134">描述</span><span class="sxs-lookup"><span data-stu-id="257c3-134">Description</span></span> |
|-----------|------------|
| [<span data-ttu-id="257c3-135">自動註冊</span><span class="sxs-lookup"><span data-stu-id="257c3-135">Auto Enrollment</span></span>](hololens-enroll-mdm.md#auto-enrollment-in-mdm) | <span data-ttu-id="257c3-136">初始登入之後，裝置會自動向 Azure AD 註冊並註冊至 MDM</span><span class="sxs-lookup"><span data-stu-id="257c3-136">After initial login, devices automatically register with Azure AD and enroll into MDM</span></span>  |
| [<span data-ttu-id="257c3-137">應用程式授權</span><span class="sxs-lookup"><span data-stu-id="257c3-137">Application Licenses</span></span>](hololens2-cloud-connected-configure.md#application-licenses)| <span data-ttu-id="257c3-138">可以套用至使用者、使用者群組或裝置群組</span><span class="sxs-lookup"><span data-stu-id="257c3-138">Can be applied to either users, user groups, or device groups</span></span>  |
| [<span data-ttu-id="257c3-139">Azure 使用者和群組</span><span class="sxs-lookup"><span data-stu-id="257c3-139">Azure Users and Groups</span></span>](hololens2-cloud-connected-configure.md#azure-users-and-groups) | <span data-ttu-id="257c3-140">協助指派 HoloLens 2 的設定和授權</span><span class="sxs-lookup"><span data-stu-id="257c3-140">Helps assign configurations and licenses for the HoloLens 2</span></span>  |

## <a name="deploy"></a><span data-ttu-id="257c3-141">部署</span><span class="sxs-lookup"><span data-stu-id="257c3-141">Deploy</span></span>

<span data-ttu-id="257c3-142">散發您的 HoloLens 2 裝置，並驗證其設定。</span><span class="sxs-lookup"><span data-stu-id="257c3-142">Distribute your HoloLens 2 devices and validate their configuration.</span></span> 

| <span data-ttu-id="257c3-143">元件</span><span class="sxs-lookup"><span data-stu-id="257c3-143">Component</span></span> | <span data-ttu-id="257c3-144">描述</span><span class="sxs-lookup"><span data-stu-id="257c3-144">Description</span></span> |
|-----------|------------|
| [<span data-ttu-id="257c3-145">註冊驗證</span><span class="sxs-lookup"><span data-stu-id="257c3-145">Enrollment Validation</span></span>](hololens2-corp-connected-deploy.md#enrollment-validation) | <span data-ttu-id="257c3-146">驗證裝置已 Azure AD 從設定或 Azure 入口網站加入</span><span class="sxs-lookup"><span data-stu-id="257c3-146">Validate the device has Azure AD Joined from Settings or the Azure Portal</span></span> |
| [<span data-ttu-id="257c3-147">憑證驗證</span><span class="sxs-lookup"><span data-stu-id="257c3-147">Certificate Validation</span></span>](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation) | <span data-ttu-id="257c3-148">檢查設定並驗證它們是否已正確散發</span><span class="sxs-lookup"><span data-stu-id="257c3-148">Check settings and validate they have been distributed correctly</span></span> |
| [<span data-ttu-id="257c3-149">驗證應用程式安裝</span><span class="sxs-lookup"><span data-stu-id="257c3-149">Validate app installs</span></span>](hololens2-corp-connected-deploy.md#validate-lob-app-install) | <span data-ttu-id="257c3-150">確認應用程式存在且正在 HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="257c3-150">Confirm the app is present and working on your HoloLens 2</span></span> |

## <a name="maintain"></a><span data-ttu-id="257c3-151">維護</span><span class="sxs-lookup"><span data-stu-id="257c3-151">Maintain</span></span>

<span data-ttu-id="257c3-152">使用商務用 Windows Update 搭配您的 MDM 系統或 Microsoft Store，讓您的 HoloLens 2 和應用程式更新。</span><span class="sxs-lookup"><span data-stu-id="257c3-152">Use Windows Update for Business along with your MDM system or the Microsoft Store to keep your fleet of HoloLens 2 and apps updated.</span></span>

| <span data-ttu-id="257c3-153">元件</span><span class="sxs-lookup"><span data-stu-id="257c3-153">Component</span></span> | <span data-ttu-id="257c3-154">描述</span><span class="sxs-lookup"><span data-stu-id="257c3-154">Description</span></span> |
|-----------|------------|
| [<span data-ttu-id="257c3-155">更新 HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="257c3-155">Update HoloLens 2</span></span>](hololens-updates.md) | <span data-ttu-id="257c3-156">視需要透過商務 Windows 更新來設定更新</span><span class="sxs-lookup"><span data-stu-id="257c3-156">Configure updates as needed through Windows Updates for Business</span></span> |
| [<span data-ttu-id="257c3-157">更新應用程式</span><span class="sxs-lookup"><span data-stu-id="257c3-157">Update apps</span></span>](app-deploy-overview.md) | <span data-ttu-id="257c3-158">透過您的 MDM 系統或 Microsoft Store 設定</span><span class="sxs-lookup"><span data-stu-id="257c3-158">Configure through your MDM system or the Microsoft Store</span></span>
