---
title: 設定 Csp 和裝置管理總覽
description: 瞭解如何使用 Mobile 裝置管理和布建套件來設定 Csp、原則和裝置管理。
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 09/16/2020
ms.reviewer: lavinds
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 60e73a9a70a70c5c583edc73a0add2f0f502ef80
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308910"
---
# <a name="configure-csps-and-device-management-overview"></a><span data-ttu-id="a785a-103">設定 Csp 和裝置管理總覽</span><span class="sxs-lookup"><span data-stu-id="a785a-103">Configure CSPs and Device Management overview</span></span>

<span data-ttu-id="a785a-104">IT 系統管理員可以在 HoloLens 2 上定義和執行原則設定。</span><span class="sxs-lookup"><span data-stu-id="a785a-104">IT Administrators can define and implement policy settings on HoloLens 2.</span></span> <span data-ttu-id="a785a-105">您要使用哪些組態設定將根據部署案例而不同，而公司裝置將為 IT 提供範圍更廣泛的控制權。</span><span class="sxs-lookup"><span data-stu-id="a785a-105">What configuration settings you use will differ based on the deployment scenario, and corporate devices will offer IT the broadest range of control.</span></span> <span data-ttu-id="a785a-106">在 Windows 10 中， (CSP) 的設定服務提供者是在裝置上讀取、設定、修改或刪除設定設定的介面。</span><span class="sxs-lookup"><span data-stu-id="a785a-106">In Windows 10, Configuration Service Providers (CSP)s are an interface to read, set, modify, or delete configuration settings on the device.</span></span> <span data-ttu-id="a785a-107">這些設定會對應到登錄機碼或檔案。</span><span class="sxs-lookup"><span data-stu-id="a785a-107">These settings map to registry keys or files.</span></span> <span data-ttu-id="a785a-108">某些設定服務提供者支援 WAP 格式、某些支援 SyncML，以及兩者的支援。</span><span class="sxs-lookup"><span data-stu-id="a785a-108">Some configuration service providers support the WAP format, some support SyncML, and some support both.</span></span>

<span data-ttu-id="a785a-109">如需 Windows 10 全像攝影版裝置管理 Csp 的詳細資訊，請參閱 [HoloLens 裝置支援的 csp](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens)完整清單。</span><span class="sxs-lookup"><span data-stu-id="a785a-109">For more information about Windows 10 Holographic device management CSPs, see the full list of [CSPs supported in HoloLens devices](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens).</span></span>
<span data-ttu-id="a785a-110">IT 系統管理員也可以管理裝置上的原則 CSP，請參閱 [HoloLens 2 所支援之原則 csp](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2)的完整清單。</span><span class="sxs-lookup"><span data-stu-id="a785a-110">IT Administrators can also manage Policy CSP on devices, see the full list of [Policy CSPs supported by HoloLens 2](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2).</span></span>

## <a name="configuration-methods"></a><span data-ttu-id="a785a-111">設定方法</span><span class="sxs-lookup"><span data-stu-id="a785a-111">Configuration methods</span></span>

### <a name="configure-with-mdm"></a><span data-ttu-id="a785a-112">使用 MDM 設定</span><span class="sxs-lookup"><span data-stu-id="a785a-112">Configure with MDM</span></span>

<span data-ttu-id="a785a-113">在 MDM 系統中註冊的任何個人或公司裝置上，都可以輕鬆地管理 Csp 和原則。</span><span class="sxs-lookup"><span data-stu-id="a785a-113">CSPs and Policies can be easily managed on any personal or corporate device enrolled in an MDM system.</span></span> <span data-ttu-id="a785a-114">在您的 MDM 解決方案中註冊裝置之後，您就能夠使用裝置設定來管理該裝置或裝置的集合。</span><span class="sxs-lookup"><span data-stu-id="a785a-114">Once a device is enrolled in your MDM solution, you will be able to manage that device, or set of devices using device configurations.</span></span> <span data-ttu-id="a785a-115">深入瞭解如何 [透過 MDM 管理 HoloLens 裝置](hololens-mdm-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="a785a-115">Learn more about how to [manage your HoloLens devices through MDM](hololens-mdm-configure.md).</span></span>

### <a name="configure-with-provisioning-packages"></a><span data-ttu-id="a785a-116">使用布建套件進行設定</span><span class="sxs-lookup"><span data-stu-id="a785a-116">Configure with Provisioning Packages</span></span>

<span data-ttu-id="a785a-117">HoloLens 2 也支援透過自訂布建套件，為 HoloLens 2 裝置設定一組有限的 CSP 設定。</span><span class="sxs-lookup"><span data-stu-id="a785a-117">HoloLens 2 also supports setting a limited set of CSP configurations for HoloLens 2 devices through custom Provisioning Packages.</span></span> <span data-ttu-id="a785a-118">布建套件通常用於非 MDM 管理的裝置，且需要手動套用至每部裝置。</span><span class="sxs-lookup"><span data-stu-id="a785a-118">Provisioning Packages are typically leveraged for non-MDM managed devices and require to be manually applied to each device.</span></span> <span data-ttu-id="a785a-119">閱讀建立 HoloLens 自訂布建 [套件的](https://docs.microsoft.com/hololens/hololens-provisioning)相關資訊。</span><span class="sxs-lookup"><span data-stu-id="a785a-119">Read information on building custom [Provisioning Packages for HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning).</span></span>

## <a name="configurations"></a><span data-ttu-id="a785a-120">設定</span><span class="sxs-lookup"><span data-stu-id="a785a-120">Configurations</span></span>

### <a name="common-device-restrictions"></a><span data-ttu-id="a785a-121">常見的裝置限制</span><span class="sxs-lookup"><span data-stu-id="a785a-121">Common device restrictions</span></span>

<span data-ttu-id="a785a-122">某些裝置限制很簡單，且會停用裝置的功能或連接。</span><span class="sxs-lookup"><span data-stu-id="a785a-122">Some device restrictions are as simple and disabling a functionality or connection to the device.</span></span> <span data-ttu-id="a785a-123">若要深入瞭解，請閱讀有關[一般裝置限制的](hololens-common-device-restrictions.md)詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="a785a-123">To learn about these read more about [common device restrictions.](hololens-common-device-restrictions.md)</span></span>

### <a name="kiosk-modes"></a><span data-ttu-id="a785a-124">Kiosk 模式</span><span class="sxs-lookup"><span data-stu-id="a785a-124">Kiosk modes</span></span>

<span data-ttu-id="a785a-125">使用 Kiosk 模式來控制哪些身分識別可以依預設存取哪些應用程式。</span><span class="sxs-lookup"><span data-stu-id="a785a-125">Use Kiosk mode to control which identities have access to which apps by default.</span></span> <span data-ttu-id="a785a-126">Kiosk 可以用於單一應用程式或多個應用程式 UI 體驗。</span><span class="sxs-lookup"><span data-stu-id="a785a-126">Kiosks can be used for a single app or multiple app UI experience.</span></span> <span data-ttu-id="a785a-127">Kiosk 設定的範圍從單一應用程式，到使用裝置的任何人，到不同群組的不同應用程式選擇。</span><span class="sxs-lookup"><span data-stu-id="a785a-127">Kiosk configurations range from a single app for anyone using the device, to different selections of apps for different groups.</span></span> <span data-ttu-id="a785a-128">Kiosk 模式不會停止「允許的應用程式」啟動其他應用程式，也不會有任何預期。</span><span class="sxs-lookup"><span data-stu-id="a785a-128">Kiosk mode does not stop “allowed apps” from launching other apps and was not intended to ever.</span></span> <span data-ttu-id="a785a-129">[若要深入瞭解，請閱讀 Kiosk 模式及其使用方式](hololens-kiosk.md)。</span><span class="sxs-lookup"><span data-stu-id="a785a-129">Learn more by [reading about Kiosk modes and how to use them](hololens-kiosk.md).</span></span>

### <a name="settings-page-visibility"></a><span data-ttu-id="a785a-130">設定頁面可見度</span><span class="sxs-lookup"><span data-stu-id="a785a-130">Settings Page Visibility</span></span>

<span data-ttu-id="a785a-131">您可以使用 [設定] 應用程式原則來控制哪些身分識別可以存取設定的預設值。</span><span class="sxs-lookup"><span data-stu-id="a785a-131">Use Settings app policy to control which identities have access to settings by default.</span></span> <span data-ttu-id="a785a-132">使用此原則，設定應用程式可以設定為只顯示選取的頁面，或隱藏所有選取的頁面。</span><span class="sxs-lookup"><span data-stu-id="a785a-132">Using this policy the Settings app can be configured to either show only the select pages, or hide all selected pages.</span></span> <span data-ttu-id="a785a-133">瞭解[如何設定可用的頁面](settings-uri-list.md)。</span><span class="sxs-lookup"><span data-stu-id="a785a-133">[Read about how to configure the pages available](settings-uri-list.md).</span></span>

<span data-ttu-id="a785a-134">這項功能目前僅適用于 [Windows 測試人員組建](hololens-insider.md)。</span><span class="sxs-lookup"><span data-stu-id="a785a-134">This feature is currently only available in [Windows Insider builds](hololens-insider.md).</span></span> <span data-ttu-id="a785a-135">確定您想要使用這項功能的裝置位於 build 19041.1349 +。</span><span class="sxs-lookup"><span data-stu-id="a785a-135">Ensure devices you intend to use this feature for are on build 19041.1349+.</span></span>

### <a name="wdac"></a><span data-ttu-id="a785a-136">WDAC</span><span class="sxs-lookup"><span data-stu-id="a785a-136">WDAC</span></span>

<span data-ttu-id="a785a-137">使用 WDAC 設定來控制不論系統是否處於 kiosk 模式，都允許/不允許的啟動/處理常式。</span><span class="sxs-lookup"><span data-stu-id="a785a-137">Use WDAC configuration to control which apps / processes are allowed / disallowed to be launched irrespective of whether system is in kiosk mode or not.</span></span>
[<span data-ttu-id="a785a-138">請參閱我們對 WDAC 的總覽。</span><span class="sxs-lookup"><span data-stu-id="a785a-138">See our overview for WDAC.</span></span>](windows-defender-application-control-wdac.md)
