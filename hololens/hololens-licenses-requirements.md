---
title: 授權需求
description: 保持您所需的行動裝置管理、HoloLens 和遠端協助的所有授權需求與指導方針在最新狀態。
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
ms.openlocfilehash: 2f7af532d2172dcaa6514ee11dbb0d6ab5631929
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283964"
---
# <span data-ttu-id="7aa24-103">授權需求</span><span class="sxs-lookup"><span data-stu-id="7aa24-103">License requirements</span></span>

## <span data-ttu-id="7aa24-104">行動裝置管理 (MDM) 授權指導方針</span><span class="sxs-lookup"><span data-stu-id="7aa24-104">Mobile Device Management (MDM) Licenses Guidance</span></span>

<span data-ttu-id="7aa24-105">如果您打算管理您的 HoloLens 裝置，您將需要 Azure AD 和 MDM。</span><span class="sxs-lookup"><span data-stu-id="7aa24-105">If you plan on managing your HoloLens devices, you will need Azure AD and an MDM.</span></span> <span data-ttu-id="7aa24-106">無法使用 Active Director (AD) 來管理 HoloLens 裝置。</span><span class="sxs-lookup"><span data-stu-id="7aa24-106">Active Director (AD) cannot be used to manage HoloLens devices.</span></span>
<span data-ttu-id="7aa24-107">如果您計劃使用 Intune 以外的 MDM，則需要 [Azure Active Directory 授權](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)。</span><span class="sxs-lookup"><span data-stu-id="7aa24-107">If you plan on using an MDM other than Intune, an [Azure Active Directory Licenses](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) is required.</span></span>
<span data-ttu-id="7aa24-108">如果您打算使用 Intune 做為 MDM，請參閱包含 Intune 授權之[套件清單](https://docs.microsoft.com/intune/fundamentals/licenses)。</span><span class="sxs-lookup"><span data-stu-id="7aa24-108">If you plan on using Intune as your MDM, read up on the [list of suites](https://docs.microsoft.com/intune/fundamentals/licenses) that include Intune licenses.</span></span> **<span data-ttu-id="7aa24-109">請注意，大多數套件中都包含 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="7aa24-109">Please note that Azure AD is included in the majority of these suites.</span></span>**

## <span data-ttu-id="7aa24-110">識別您的案例和產品所需的授權</span><span class="sxs-lookup"><span data-stu-id="7aa24-110">Identify the licenses needed for your scenario and products</span></span>

### <span data-ttu-id="7aa24-111">HoloLens (第1代) 授權需求</span><span class="sxs-lookup"><span data-stu-id="7aa24-111">HoloLens (1st gen) Licenses Requirements</span></span>

<span data-ttu-id="7aa24-112">您可能需要將 HoloLens (第1代) 裝置升級至 Windows Holographic for Business。</span><span class="sxs-lookup"><span data-stu-id="7aa24-112">You may need to upgrade your HoloLens (1st gen) device to Windows Holographic for Business.</span></span> <span data-ttu-id="7aa24-113">(請參閱 [HoloLens 商業功能](holoLens-commercial-features.md#feature-comparison-between-editions)，判斷您是否需要升級)。</span><span class="sxs-lookup"><span data-stu-id="7aa24-113">(See [HoloLens commercial features](holoLens-commercial-features.md#feature-comparison-between-editions) to determine if you need to upgrade).</span></span>

 <span data-ttu-id="7aa24-114">若是如此，您需要執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="7aa24-114">If so, you will need to do the following:</span></span>

- <span data-ttu-id="7aa24-115">取得 HoloLens 企業授權 XML 檔案</span><span class="sxs-lookup"><span data-stu-id="7aa24-115">Acquire a HoloLens Enterprise license XML file</span></span>
- <span data-ttu-id="7aa24-116">將 XML 檔案套用到 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="7aa24-116">Apply the XML file to the HoloLens.</span></span> <span data-ttu-id="7aa24-117">您可以透過[佈建套件](hololens-provisioning.md)或透過[行動裝置管理員](https://docs.microsoft.com/intune/configuration/holographic-upgrade)來執行此動作</span><span class="sxs-lookup"><span data-stu-id="7aa24-117">You can do this through a [Provisioning package](hololens-provisioning.md) or through your [Mobile Device Manager](https://docs.microsoft.com/intune/configuration/holographic-upgrade)</span></span>

### <span data-ttu-id="7aa24-118">遠端協助授權需求</span><span class="sxs-lookup"><span data-stu-id="7aa24-118">Remote Assist License Requirements</span></span>

<span data-ttu-id="7aa24-119">請確定您擁有所需的授權和裝置，您可以在[需求](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements)文件中查看。</span><span class="sxs-lookup"><span data-stu-id="7aa24-119">Make sure you have the required licensing and device, which you can check in the [requirements](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements) documentation.</span></span>

1. [<span data-ttu-id="7aa24-120">遠端協助授權</span><span class="sxs-lookup"><span data-stu-id="7aa24-120">Remote Assist License</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist)
    1. <span data-ttu-id="7aa24-121">或嘗試使用 [[遠端協助] 試用版](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)</span><span class="sxs-lookup"><span data-stu-id="7aa24-121">Or try a [Remote Assist trial](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)</span></span>
1. [<span data-ttu-id="7aa24-122">Teams 免費增值版/Teams</span><span class="sxs-lookup"><span data-stu-id="7aa24-122">Teams Freemium/Teams</span></span>](https://products.office.com/microsoft-teams/free)
1. [<span data-ttu-id="7aa24-123">Azure Active Directory (Azure AD) 授權</span><span class="sxs-lookup"><span data-stu-id="7aa24-123">Azure Active Directory (Azure AD) License</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)

<span data-ttu-id="7aa24-124">如果您打算實施**[此跨租用戶案例](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)**，您可能需要資訊屏障授權。</span><span class="sxs-lookup"><span data-stu-id="7aa24-124">If you plan on implementing **[this cross-tenant scenario](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)**, you may need an Information Barriers license.</span></span> <span data-ttu-id="7aa24-125">請參閱[本文](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary)，判斷是否需要資訊屏障授權。</span><span class="sxs-lookup"><span data-stu-id="7aa24-125">Please see [this article](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) to determine if an Information Barrier License is required.</span></span>

### <span data-ttu-id="7aa24-126">授權需求指南</span><span class="sxs-lookup"><span data-stu-id="7aa24-126">Guides License Requirements</span></span>

<span data-ttu-id="7aa24-127">請查看[更新的授權與裝置需求](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements)。</span><span class="sxs-lookup"><span data-stu-id="7aa24-127">Check out the [updated licensing and device requirements](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements).</span></span>

1. [<span data-ttu-id="7aa24-128">Azure Active Directory (Azure AD) 授權</span><span class="sxs-lookup"><span data-stu-id="7aa24-128">Azure Active Directory (Azure AD) License</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)
1. [<span data-ttu-id="7aa24-129">Power BI</span><span class="sxs-lookup"><span data-stu-id="7aa24-129">Power BI</span></span>](https://powerbi.microsoft.com/desktop/)
1. [<span data-ttu-id="7aa24-130">指南</span><span class="sxs-lookup"><span data-stu-id="7aa24-130">Guides</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup)
