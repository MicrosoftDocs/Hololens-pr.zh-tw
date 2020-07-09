---
title: 授權需求
description: ''
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
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 18a583f407b19c5b86870a49b8182d45f46a45f5
ms.sourcegitcommit: 29755f5af0086a43c532fb5a9a4ae65c36bc82de
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/07/2020
ms.locfileid: "10857801"
---
# <span data-ttu-id="6a36e-102">授權需求</span><span class="sxs-lookup"><span data-stu-id="6a36e-102">License requirements</span></span>

## <span data-ttu-id="6a36e-103">行動裝置管理 (MDM) 授權指導方針</span><span class="sxs-lookup"><span data-stu-id="6a36e-103">Mobile Device Management (MDM) Licenses Guidance</span></span>

<span data-ttu-id="6a36e-104">如果您打算管理您的 HoloLens 裝置，您將需要 Azure AD 和 MDM。</span><span class="sxs-lookup"><span data-stu-id="6a36e-104">If you plan on managing your HoloLens devices, you will need Azure AD and an MDM.</span></span> <span data-ttu-id="6a36e-105">無法使用 Active Director (AD) 來管理 HoloLens 裝置。</span><span class="sxs-lookup"><span data-stu-id="6a36e-105">Active Director (AD) cannot be used to manage HoloLens devices.</span></span>
<span data-ttu-id="6a36e-106">如果您計劃使用 Intune 以外的 MDM，則需要 [Azure Active Directory 授權](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)。</span><span class="sxs-lookup"><span data-stu-id="6a36e-106">If you plan on using an MDM other than Intune, an [Azure Active Directory Licenses](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) is required.</span></span>
<span data-ttu-id="6a36e-107">如果您打算使用 Intune 做為 MDM，[這裡](https://docs.microsoft.com/intune/fundamentals/licenses)是包含 Intune 授權的套件清單。</span><span class="sxs-lookup"><span data-stu-id="6a36e-107">If you plan on using Intune as your MDM,  [here](https://docs.microsoft.com/intune/fundamentals/licenses) are a list of suites that includes Intune licenses.</span></span> **<span data-ttu-id="6a36e-108">請注意，大多數套件中都包含 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="6a36e-108">Please note that Azure AD is included in the majority of these suites.</span></span>**

## <span data-ttu-id="6a36e-109">識別您的案例和產品所需的授權</span><span class="sxs-lookup"><span data-stu-id="6a36e-109">Identify the licenses needed for your scenario and products</span></span>

### <span data-ttu-id="6a36e-110">HoloLens 授權需求</span><span class="sxs-lookup"><span data-stu-id="6a36e-110">HoloLens Licenses Requirements</span></span>

<span data-ttu-id="6a36e-111">您可能需要將 HoloLens 第一代裝置升級至 Windows Holographic for Business。</span><span class="sxs-lookup"><span data-stu-id="6a36e-111">You may need to upgrade your HoloLens 1st Gen Device to Windows Holographic for Business.</span></span> <span data-ttu-id="6a36e-112">(請參閱 [HoloLens 商業功能](holoLens-commercial-features.md#feature-comparison-between-editions)，判斷您是否需要升級)。</span><span class="sxs-lookup"><span data-stu-id="6a36e-112">(See [HoloLens commercial features](holoLens-commercial-features.md#feature-comparison-between-editions) to determine if you need to upgrade).</span></span>

 <span data-ttu-id="6a36e-113">若是如此，您需要執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="6a36e-113">If so, you will need to do the following:</span></span>

- <span data-ttu-id="6a36e-114">取得 HoloLens 企業授權 XML 檔案</span><span class="sxs-lookup"><span data-stu-id="6a36e-114">Acquire a HoloLens Enterprise license XML file</span></span>
- <span data-ttu-id="6a36e-115">將 XML 檔案套用到 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="6a36e-115">Apply the XML file to the HoloLens.</span></span> <span data-ttu-id="6a36e-116">您可以透過[佈建套件](hololens-provisioning.md)或透過[行動裝置管理員](https://docs.microsoft.com/intune/configuration/holographic-upgrade)來執行此動作</span><span class="sxs-lookup"><span data-stu-id="6a36e-116">You can do this through a [Provisioning package](hololens-provisioning.md) or through your [Mobile Device Manager](https://docs.microsoft.com/intune/configuration/holographic-upgrade)</span></span>

### <span data-ttu-id="6a36e-117">遠端協助授權需求</span><span class="sxs-lookup"><span data-stu-id="6a36e-117">Remote Assist License Requirements</span></span>

<span data-ttu-id="6a36e-118">請確定您具備所需的授權和裝置。</span><span class="sxs-lookup"><span data-stu-id="6a36e-118">Make sure you have the required licensing and device.</span></span> <span data-ttu-id="6a36e-119">您可以在[這裡](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements)找到更新的授權和產品需求。</span><span class="sxs-lookup"><span data-stu-id="6a36e-119">Updated licensing and product requirements can be found [here](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements).</span></span>

1. [<span data-ttu-id="6a36e-120">遠端協助授權</span><span class="sxs-lookup"><span data-stu-id="6a36e-120">Remote Assist License</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist)
1. [<span data-ttu-id="6a36e-121">Teams 免費增值版/Teams</span><span class="sxs-lookup"><span data-stu-id="6a36e-121">Teams Freemium/Teams</span></span>](https://products.office.com/microsoft-teams/free)
1. [<span data-ttu-id="6a36e-122">Azure Active Directory (Azure AD) 授權</span><span class="sxs-lookup"><span data-stu-id="6a36e-122">Azure Active Directory (Azure AD) License</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)

<span data-ttu-id="6a36e-123">如果您打算實施**[此跨租用戶案例](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)**，您可能需要資訊屏障授權。</span><span class="sxs-lookup"><span data-stu-id="6a36e-123">If you plan on implementing **[this cross-tenant scenario](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)**, you may need an Information Barriers license.</span></span> <span data-ttu-id="6a36e-124">請參閱[本文](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary)，判斷是否需要資訊屏障授權。</span><span class="sxs-lookup"><span data-stu-id="6a36e-124">Please see [this article](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) to determine if an Information Barrier License is required.</span></span>

### <span data-ttu-id="6a36e-125">授權需求指南</span><span class="sxs-lookup"><span data-stu-id="6a36e-125">Guides License Requirements</span></span>

<span data-ttu-id="6a36e-126">您可以在[這裡](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements)找到更新的授權和裝置需求。</span><span class="sxs-lookup"><span data-stu-id="6a36e-126">Updated licensing and device requirements can be found [here](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements).</span></span>

1. [<span data-ttu-id="6a36e-127">Azure Active Directory (Azure AD) 授權</span><span class="sxs-lookup"><span data-stu-id="6a36e-127">Azure Active Directory (Azure AD) License</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)
1. [<span data-ttu-id="6a36e-128">Power BI</span><span class="sxs-lookup"><span data-stu-id="6a36e-128">Power BI</span></span>](https://powerbi.microsoft.com/desktop/)
1. [<span data-ttu-id="6a36e-129">指南</span><span class="sxs-lookup"><span data-stu-id="6a36e-129">Guides</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup)
