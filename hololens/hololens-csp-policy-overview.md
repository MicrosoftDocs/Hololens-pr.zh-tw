---
title: 設定 CSP 和裝置管理概覽
description: 瞭解如何使用行動裝置管理和置備套件來設定 Csp、原則和裝置管理。
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
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283244"
---
# <span data-ttu-id="89a34-103">設定 CSP 和裝置管理概覽</span><span class="sxs-lookup"><span data-stu-id="89a34-103">Configure CSPs and Device Management overview</span></span>

<span data-ttu-id="89a34-104">IT 管理員可以在 HoloLens 2 上定義並實施原則設定。</span><span class="sxs-lookup"><span data-stu-id="89a34-104">IT Administrators can define and implement policy settings on HoloLens 2.</span></span> <span data-ttu-id="89a34-105">您要使用哪些組態設定將根據部署案例而不同，而公司裝置將為 IT 提供範圍更廣泛的控制權。</span><span class="sxs-lookup"><span data-stu-id="89a34-105">What configuration settings you use will differ based on the deployment scenario, and corporate devices will offer IT the broadest range of control.</span></span> <span data-ttu-id="89a34-106">在 Windows 10 中，Configuration Services 提供者 (CSP) s 是一個介面，可用於讀取、設定、修改或刪除裝置上的配置設定。</span><span class="sxs-lookup"><span data-stu-id="89a34-106">In Windows 10, Configuration Service Providers (CSP)s are an interface to read, set, modify, or delete configuration settings on the device.</span></span> <span data-ttu-id="89a34-107">這些設定會對應到登錄機碼或檔案。</span><span class="sxs-lookup"><span data-stu-id="89a34-107">These settings map to registry keys or files.</span></span> <span data-ttu-id="89a34-108">某些配置服務提供者支援 WAP 格式、部分支援 SyncML，以及部分支援。</span><span class="sxs-lookup"><span data-stu-id="89a34-108">Some configuration service providers support the WAP format, some support SyncML, and some support both.</span></span>

<span data-ttu-id="89a34-109">如需有關 Windows 10 全息版裝置管理 Csp 的詳細資訊，請參閱 [HoloLens 裝置中支援的 csp](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens)完整清單。</span><span class="sxs-lookup"><span data-stu-id="89a34-109">For more information about Windows 10 Holographic device management CSPs, see the full list of [CSPs supported in HoloLens devices](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens).</span></span>
<span data-ttu-id="89a34-110">IT 管理員也可以在裝置上管理原則 CSP，請參閱 [HoloLens 2 支援之策略 csp](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2)的完整清單。</span><span class="sxs-lookup"><span data-stu-id="89a34-110">IT Administrators can also manage Policy CSP on devices, see the full list of [Policy CSPs supported by HoloLens 2](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2).</span></span>

## <span data-ttu-id="89a34-111">配置方法</span><span class="sxs-lookup"><span data-stu-id="89a34-111">Configuration methods</span></span>

### <span data-ttu-id="89a34-112">使用 MDM 進行設定</span><span class="sxs-lookup"><span data-stu-id="89a34-112">Configure with MDM</span></span>

<span data-ttu-id="89a34-113">在任何個人或公司裝置上註冊的 MDM 系統中，都可以輕鬆管理 Csp 與原則。</span><span class="sxs-lookup"><span data-stu-id="89a34-113">CSPs and Policies can be easily managed on any personal or corporate device enrolled in an MDM system.</span></span> <span data-ttu-id="89a34-114">在您的 MDM 方案中註冊裝置之後，您就可以使用裝置設定來管理該裝置或一組裝置。</span><span class="sxs-lookup"><span data-stu-id="89a34-114">Once a device is enrolled in your MDM solution, you will be able to manage that device, or set of devices using device configurations.</span></span> <span data-ttu-id="89a34-115">進一步瞭解如何 [透過 MDM 管理您的 HoloLens 裝置](hololens-mdm-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="89a34-115">Learn more about how to [manage your HoloLens devices through MDM](hololens-mdm-configure.md).</span></span>

### <span data-ttu-id="89a34-116">使用預配套件進行設定</span><span class="sxs-lookup"><span data-stu-id="89a34-116">Configure with Provisioning Packages</span></span>

<span data-ttu-id="89a34-117">HoloLens 2 也支援透過自訂的置備套件，為 HoloLens 2 裝置設定有限的 CSP 配置。</span><span class="sxs-lookup"><span data-stu-id="89a34-117">HoloLens 2 also supports setting a limited set of CSP configurations for HoloLens 2 devices through custom Provisioning Packages.</span></span> <span data-ttu-id="89a34-118">您通常會將預配套件用於非 MDM 管理的裝置，且需要手動套用到每個裝置。</span><span class="sxs-lookup"><span data-stu-id="89a34-118">Provisioning Packages are typically leveraged for non-MDM managed devices and require to be manually applied to each device.</span></span> <span data-ttu-id="89a34-119">閱讀有關建立 [適用于 HoloLens 的自訂預配套件的](https://docs.microsoft.com/hololens/hololens-provisioning)資訊。</span><span class="sxs-lookup"><span data-stu-id="89a34-119">Read information on building custom [Provisioning Packages for HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning).</span></span>

## <span data-ttu-id="89a34-120">設定</span><span class="sxs-lookup"><span data-stu-id="89a34-120">Configurations</span></span>

### <span data-ttu-id="89a34-121">常見的裝置限制</span><span class="sxs-lookup"><span data-stu-id="89a34-121">Common device restrictions</span></span>

<span data-ttu-id="89a34-122">某些裝置限制是簡單且停用裝置的功能或連線。</span><span class="sxs-lookup"><span data-stu-id="89a34-122">Some device restrictions are as simple and disabling a functionality or connection to the device.</span></span> <span data-ttu-id="89a34-123">若要深入瞭解這些資訊，請閱讀有關[常見裝置限制的](hololens-common-device-restrictions.md)詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="89a34-123">To learn about these read more about [common device restrictions.](hololens-common-device-restrictions.md)</span></span>

### <span data-ttu-id="89a34-124">展臺模式</span><span class="sxs-lookup"><span data-stu-id="89a34-124">Kiosk modes</span></span>

<span data-ttu-id="89a34-125">使用 Kiosk 模式控制哪些身分識別可存取預設的 app。</span><span class="sxs-lookup"><span data-stu-id="89a34-125">Use Kiosk mode to control which identities have access to which apps by default.</span></span> <span data-ttu-id="89a34-126">亭可用於單一 app 或多個 app UI 體驗。</span><span class="sxs-lookup"><span data-stu-id="89a34-126">Kiosks can be used for a single app or multiple app UI experience.</span></span> <span data-ttu-id="89a34-127">展臺配置的範圍是從單一應用程式使用裝置的任何人，到不同群組的 app 選擇。</span><span class="sxs-lookup"><span data-stu-id="89a34-127">Kiosk configurations range from a single app for anyone using the device, to different selections of apps for different groups.</span></span> <span data-ttu-id="89a34-128">Kiosk 模式不會停止啟動其他 app 的「允許的 app」，而不會發生任何情況。</span><span class="sxs-lookup"><span data-stu-id="89a34-128">Kiosk mode does not stop “allowed apps” from launching other apps and was not intended to ever.</span></span> <span data-ttu-id="89a34-129">[若要深入瞭解，請閱讀有關 Kiosk 模式以及如何使用](hololens-kiosk.md)的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="89a34-129">Learn more by [reading about Kiosk modes and how to use them](hololens-kiosk.md).</span></span>

### <span data-ttu-id="89a34-130">[設定頁面可見度]</span><span class="sxs-lookup"><span data-stu-id="89a34-130">Settings Page Visibility</span></span>

<span data-ttu-id="89a34-131">使用 [設定] app 原則來控制哪些身分識別可存取設定。</span><span class="sxs-lookup"><span data-stu-id="89a34-131">Use Settings app policy to control which identities have access to settings by default.</span></span> <span data-ttu-id="89a34-132">使用此原則，設定應用程式可以設定為只顯示選取頁面，或隱藏所有選取的頁面。</span><span class="sxs-lookup"><span data-stu-id="89a34-132">Using this policy the Settings app can be configured to either show only the select pages, or hide all selected pages.</span></span> <span data-ttu-id="89a34-133">瞭解[如何設定可用的頁面](settings-uri-list.md)。</span><span class="sxs-lookup"><span data-stu-id="89a34-133">[Read about how to configure the pages available](settings-uri-list.md).</span></span>

<span data-ttu-id="89a34-134">此功能目前僅適用于 Windows 測試人員 [組建](hololens-insider.md)。</span><span class="sxs-lookup"><span data-stu-id="89a34-134">This feature is currently only available in [Windows Insider builds](hololens-insider.md).</span></span> <span data-ttu-id="89a34-135">請確定您想要使用此功能的裝置在 [組建 19041.1349 +] 上。</span><span class="sxs-lookup"><span data-stu-id="89a34-135">Ensure devices you intend to use this feature for are on build 19041.1349+.</span></span>

### <span data-ttu-id="89a34-136">WDAC</span><span class="sxs-lookup"><span data-stu-id="89a34-136">WDAC</span></span>

<span data-ttu-id="89a34-137">使用 WDAC 設定來控制無論系統是否處於 kiosk 模式，允許或不允許啟動哪些應用程式/進程。</span><span class="sxs-lookup"><span data-stu-id="89a34-137">Use WDAC configuration to control which apps / processes are allowed / disallowed to be launched irrespective of whether system is in kiosk mode or not.</span></span>
[<span data-ttu-id="89a34-138">請參閱我們針對 WDAC 的概覽。</span><span class="sxs-lookup"><span data-stu-id="89a34-138">See our overview for WDAC.</span></span>](windows-defender-application-control-wdac.md)
