---
title: 授權需求
description: 隨時掌握行動裝置管理、HoloLens 和遠端協助所需的所有授權需求與指導方針。
ms.prod: hololens
ms.sitesec: library
author: pawinfie
ms.author: pawinfie
audience: HoloLens
ms.topic: article
ms.localizationpriority: high
ms.date: 1/23/2020
ms.reviewer: ''
manager: bradke
appliesto:
- HoloLens 2
ms.openlocfilehash: d0d8aa648df7901dec8636942e43aa549e626d7e
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635886"
---
# <a name="license-requirements"></a><span data-ttu-id="161ad-103">授權需求</span><span class="sxs-lookup"><span data-stu-id="161ad-103">License requirements</span></span>

## <a name="hololens-2-device-managed"></a><span data-ttu-id="161ad-104">HoloLens 2裝置 (受控) </span><span class="sxs-lookup"><span data-stu-id="161ad-104">HoloLens 2 Device (managed)</span></span>

[<span data-ttu-id="161ad-105">Azure AD 帳戶</span><span class="sxs-lookup"><span data-stu-id="161ad-105">Azure AD Account</span></span>](https://docs.microsoft.com/azure/active-directory/)

> [!IMPORTANT]
> <span data-ttu-id="161ad-106">Active Directory (AD) 不能用來管理 HoloLens 的裝置。</span><span class="sxs-lookup"><span data-stu-id="161ad-106">Active Directory (AD) cannot be used to manage HoloLens devices.</span></span>

<span data-ttu-id="161ad-107">[Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)或另一個 MDM。</span><span class="sxs-lookup"><span data-stu-id="161ad-107">[Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) or another MDM.</span></span>
- <span data-ttu-id="161ad-108">[適用于 HoloLens 2 的 Windows Autopilot](hololens2-autopilot.md)可簡化 IT 系統管理員和終端使用者的布建體驗。</span><span class="sxs-lookup"><span data-stu-id="161ad-108">[Windows Autopilot for HoloLens 2](hololens2-autopilot.md)- simplifies the provisioning experience for both IT admins and end users.</span></span> <span data-ttu-id="161ad-109">IT 系統管理員可以預先設定 HoloLens 2 原則，並在第一次開機時，將裝置部署為無終端使用者互動的商務就緒狀態。</span><span class="sxs-lookup"><span data-stu-id="161ad-109">IT admins can preconfigure HoloLens 2 policies, and upon first boot, devices will be deployed in business-ready state with zero end-user interaction.</span></span> 

  > [!NOTE]
  > <span data-ttu-id="161ad-110">WindowsAutopilot 需要先針對低觸控 Autopilot 流程和裝置部署設定[Azure P1](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)和[自動註冊](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)。</span><span class="sxs-lookup"><span data-stu-id="161ad-110">Windows Autopilot requires [Azure P1](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) and [Auto-enrollment](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment) to be configured first for the low-touch Autopilot flow and device deployment.</span></span> 

### <a name="business-use-case"></a><span data-ttu-id="161ad-111">商務使用案例：</span><span class="sxs-lookup"><span data-stu-id="161ad-111">Business Use Case:</span></span> 

- <span data-ttu-id="161ad-112">[部署案例](hololens-requirements.md#scenario-a-deploy-to-cloud-connected-devices) ：概念證明或試驗部署。</span><span class="sxs-lookup"><span data-stu-id="161ad-112">[Deployment Scenario A](hololens-requirements.md#scenario-a-deploy-to-cloud-connected-devices) - proof-of-concept or pilot deployment.</span></span>

- <span data-ttu-id="161ad-113">[部署案例 B](hololens-requirements.md#scenario-b-deploy-inside-your-organizations-network) -大規模部署。</span><span class="sxs-lookup"><span data-stu-id="161ad-113">[Deployment Scenario B](hololens-requirements.md#scenario-b-deploy-inside-your-organizations-network) - deployment at scale.</span></span>

## <a name="hololens-2-device-only-non-managed"></a><span data-ttu-id="161ad-114">HoloLens 2僅限裝置 (非受控) </span><span class="sxs-lookup"><span data-stu-id="161ad-114">HoloLens 2 Device-only (non-managed)</span></span>

<span data-ttu-id="161ad-115">使用 Microsoft 帳戶 (MSA) 或本機帳戶時，這些帳戶不需要額外的授權。</span><span class="sxs-lookup"><span data-stu-id="161ad-115">When using either a Microsoft Account (MSA) or Local account no additional licenses are required for these accounts.</span></span>

[<span data-ttu-id="161ad-116">本機帳戶</span><span class="sxs-lookup"><span data-stu-id="161ad-116">Local Account</span></span>](https://docs.microsoft.com/windows/security/identity-protection/access-control/local-accounts)

- <span data-ttu-id="161ad-117">您必須預先布[建](hololens-provisioning.md#provisioning-package-hololens-wizard)此帳戶，Windows 設定設計工具 (WCD) 。</span><span class="sxs-lookup"><span data-stu-id="161ad-117">This account must be [provisioned](hololens-provisioning.md#provisioning-package-hololens-wizard) ahead of time with Windows Configuration Designer (WCD).</span></span>

[<span data-ttu-id="161ad-118">Microsoft 帳戶 (MSA) </span><span class="sxs-lookup"><span data-stu-id="161ad-118">Microsoft Account (MSA)</span></span>](https://docs.microsoft.com/windows/security/identity-protection/access-control/microsoft-accounts)

> [!WARNING]
> <span data-ttu-id="161ad-119">使用上述任一帳戶的裝置不支援多個使用者。</span><span class="sxs-lookup"><span data-stu-id="161ad-119">Multiple users are not supported for a device using either of these accounts.</span></span>

### <a name="business-use-case"></a><span data-ttu-id="161ad-120">商務使用案例：</span><span class="sxs-lookup"><span data-stu-id="161ad-120">Business Use Case:</span></span> 

- <span data-ttu-id="161ad-121">[部署案例 C](hololens-requirements.md#scenario-c-deploy-in-secure-offline-environment) -離線或安全的部署。</span><span class="sxs-lookup"><span data-stu-id="161ad-121">[Deployment Scenario C](hololens-requirements.md#scenario-c-deploy-in-secure-offline-environment) - offline or secure deployment.</span></span>
 
## <a name="dynamics-365-licensing-and-requirements"></a><span data-ttu-id="161ad-122">Dynamics 365 授權和需求</span><span class="sxs-lookup"><span data-stu-id="161ad-122">Dynamics 365 Licensing and Requirements</span></span>

### <a name="dynamics-365-remote-assist"></a><span data-ttu-id="161ad-123">Dynamics 365 Remote Assist</span><span class="sxs-lookup"><span data-stu-id="161ad-123">Dynamics 365 Remote Assist</span></span> 

#### <a name="admin"></a><span data-ttu-id="161ad-124">管理</span><span class="sxs-lookup"><span data-stu-id="161ad-124">Admin</span></span>

- <span data-ttu-id="161ad-125">購買訂用帳戶和指派授權所需的 Azure AD 帳戶 () </span><span class="sxs-lookup"><span data-stu-id="161ad-125">Azure AD account (required for purchasing the subscription and assigning licenses)</span></span>
- <span data-ttu-id="161ad-126">[遠端協助訂閱](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (或 [遠端協助試用](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)) </span><span class="sxs-lookup"><span data-stu-id="161ad-126">[Remote Assist subscription](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (or [Remote Assist Trial](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist))</span></span>
    
#### <a name="dynamics-365-remote-assist-user"></a><span data-ttu-id="161ad-127">Dynamics 365 Remote Assist 使用者</span><span class="sxs-lookup"><span data-stu-id="161ad-127">Dynamics 365 Remote Assist user</span></span>

- <span data-ttu-id="161ad-128">Azure AD 帳戶</span><span class="sxs-lookup"><span data-stu-id="161ad-128">Azure AD account</span></span>

- <span data-ttu-id="161ad-129">遠端協助授權</span><span class="sxs-lookup"><span data-stu-id="161ad-129">Remote Assist license</span></span> 

  > [!NOTE]
  > <span data-ttu-id="161ad-130">Microsoft Teams 隨附于遠端協助</span><span class="sxs-lookup"><span data-stu-id="161ad-130">Microsoft Teams is bundled with Remote Assist</span></span>

- <span data-ttu-id="161ad-131">網路連線</span><span class="sxs-lookup"><span data-stu-id="161ad-131">Network Connectivity</span></span>

#### <a name="microsoft-teams-user"></a><span data-ttu-id="161ad-132">Microsoft Teams 使用者</span><span class="sxs-lookup"><span data-stu-id="161ad-132">Microsoft Teams user</span></span>

- <span data-ttu-id="161ad-133">Azure AD 帳戶</span><span class="sxs-lookup"><span data-stu-id="161ad-133">Azure AD account</span></span>

- <span data-ttu-id="161ad-134">Microsoft Teams 或[Teams 免費增值](https://products.office.com/microsoft-teams/free)。</span><span class="sxs-lookup"><span data-stu-id="161ad-134">Microsoft Teams or [Teams Freemium](https://products.office.com/microsoft-teams/free).</span></span>

- <span data-ttu-id="161ad-135">網路連線</span><span class="sxs-lookup"><span data-stu-id="161ad-135">Network connectivity</span></span>

<span data-ttu-id="161ad-136">如果您打算執行此 [跨租使用者案例](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)，您可能需要資訊障礙授權。</span><span class="sxs-lookup"><span data-stu-id="161ad-136">If you plan on implementing this [cross-tenant scenario](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants), you may need an Information Barriers license.</span></span> <span data-ttu-id="161ad-137">請參閱 [這篇文章](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) ，以判斷是否需要資訊屏障授權。</span><span class="sxs-lookup"><span data-stu-id="161ad-137">See [this article](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) to determine if an Information Barrier License is required.</span></span>

### <a name="dynamics-365-guides"></a><span data-ttu-id="161ad-138">Dynamics 365 Guides</span><span class="sxs-lookup"><span data-stu-id="161ad-138">Dynamics 365 Guides</span></span> 

#### <a name="admin"></a><span data-ttu-id="161ad-139">管理</span><span class="sxs-lookup"><span data-stu-id="161ad-139">Admin</span></span>

- <span data-ttu-id="161ad-140">購買訂用帳戶和指派授權所需的 Azure AD 帳戶 () </span><span class="sxs-lookup"><span data-stu-id="161ad-140">Azure AD account (required for purchasing the subscription and assigning licenses)</span></span>
- <span data-ttu-id="161ad-141">Dynamics 365 [指南訂用帳戶或免費試用](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-one)</span><span class="sxs-lookup"><span data-stu-id="161ad-141">Dynamics 365 [Guides subscription or free trial](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup-step-one)</span></span>

#### <a name="guides-author"></a><span data-ttu-id="161ad-142">手冊作者</span><span class="sxs-lookup"><span data-stu-id="161ad-142">Guides Author</span></span>

1. <span data-ttu-id="161ad-143">Azure AD 帳戶</span><span class="sxs-lookup"><span data-stu-id="161ad-143">Azure AD account</span></span>
1. [<span data-ttu-id="161ad-144">Dynamics 365 Guides 授權</span><span class="sxs-lookup"><span data-stu-id="161ad-144">Dynamics 365 Guides license</span></span>](/dynamics365/mixed-reality/guides/requirements)
1. <span data-ttu-id="161ad-145">Dynamics 365 Guides 安裝在電腦或 HoloLens 上的應用程式</span><span class="sxs-lookup"><span data-stu-id="161ad-145">Dynamics 365 Guides application installed on a PC or HoloLens</span></span>
1. <span data-ttu-id="161ad-146">用來查看分析儀表板的[Power BI Desktop](https://powerbi.microsoft.com/desktop/) () </span><span class="sxs-lookup"><span data-stu-id="161ad-146">[Power BI Desktop](https://powerbi.microsoft.com/desktop/) (used to view the Analytics dashboard)</span></span>
1. <span data-ttu-id="161ad-147">建立指南的作者角色 () </span><span class="sxs-lookup"><span data-stu-id="161ad-147">Author role (for creating guides)</span></span>
1. <span data-ttu-id="161ad-148">網路連線</span><span class="sxs-lookup"><span data-stu-id="161ad-148">Network Connectivity</span></span>

#### <a name="guides-user"></a><span data-ttu-id="161ad-149">引導使用者</span><span class="sxs-lookup"><span data-stu-id="161ad-149">Guides User</span></span>

1. <span data-ttu-id="161ad-150">Azure AD 帳戶</span><span class="sxs-lookup"><span data-stu-id="161ad-150">Azure AD account</span></span>
1. [<span data-ttu-id="161ad-151">Dynamics 365 Guides 授權</span><span class="sxs-lookup"><span data-stu-id="161ad-151">Dynamics 365 Guides license</span></span>](/dynamics365/mixed-reality/guides/requirements)
1. <span data-ttu-id="161ad-152">HoloLens 上安裝的 Dynamics 365 Guides 應用程式</span><span class="sxs-lookup"><span data-stu-id="161ad-152">Dynamics 365 Guides app installed on a HoloLens</span></span>
1. <span data-ttu-id="161ad-153">用於測試或使用指南的操作員角色 () </span><span class="sxs-lookup"><span data-stu-id="161ad-153">Operator role (for testing or using guides)</span></span>
1. <span data-ttu-id="161ad-154">網路連線</span><span class="sxs-lookup"><span data-stu-id="161ad-154">Network Connectivity</span></span>
