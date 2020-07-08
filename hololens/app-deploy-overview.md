---
title: 概覽-App 管理
description: app、管理、app 管理
keywords: HoloLens、使用者、帳戶、app、應用程式管理、
author: v-jodben
ms.date: 6/22/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
manager: yannisl
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: eeed478970d08eff8789a9decd084f1863c6d7f9
ms.sourcegitcommit: 29755f5af0086a43c532fb5a9a4ae65c36bc82de
ms.contentlocale: zh-TW
ms.lasthandoff: 07/07/2020
ms.locfileid: "10857914"
---
# <span data-ttu-id="ff82a-104">App 管理：簡介</span><span class="sxs-lookup"><span data-stu-id="ff82a-104">App Management: Overview</span></span>

<span data-ttu-id="ff82a-105">您可以將應用程式部署在四個不同的路徑上：行動**裝置管理（MDM）**、 **Microsoft store for Business**、 **microsoft Store**，或透過 [**提供**] 進行安裝。</span><span class="sxs-lookup"><span data-stu-id="ff82a-105">You can deploy apps on four different paths: **Mobile Device Management (MDM)**, **Microsoft Store for Business**, **Microsoft Store**, or by installing them via **Provisioning**.</span></span> 

## <span data-ttu-id="ff82a-106">行動裝置管理 (MDM)</span><span class="sxs-lookup"><span data-stu-id="ff82a-106">Mobile Device Management (MDM)</span></span>

<span data-ttu-id="ff82a-107">MDM 解決方案能讓 IT 決策者和系統管理員秘密地自動安裝（推入）自己的內部、行業內應用程式，或透過使用者群組的商店購買 app。</span><span class="sxs-lookup"><span data-stu-id="ff82a-107">An MDM solution enables IT decision-makers and administrators to privately auto-install (push) their in-house, line-of-business apps, or purchase apps through the store for a group of users.</span></span> <span data-ttu-id="ff82a-108">HoloLens 裝置最適合用於[應用程式管理](app-deploy-intune.md)的 Microsoft 端點管理員（Intune）。</span><span class="sxs-lookup"><span data-stu-id="ff82a-108">HoloLens devices work best with Microsoft Endpoint Manager (Intune) for [application management](app-deploy-intune.md).</span></span> <span data-ttu-id="ff82a-109">Intune 也透過公司入口網站下載體驗，讓使用者能夠更精細地控制 IT 管理的 app。</span><span class="sxs-lookup"><span data-stu-id="ff82a-109">Intune also offers users finer-grained control over IT-managed apps through the Company Portal downloadable experience.</span></span>

> [!NOTE] 
> <span data-ttu-id="ff82a-110">下列指示適用于想要使用 Intune 管理其應用程式的使用者。</span><span class="sxs-lookup"><span data-stu-id="ff82a-110">The following instructions are for users who want to manage their applications with Intune.</span></span> <span data-ttu-id="ff82a-111">Microsoft 建議使用 Intune 進行應用程式與裝置管理。</span><span class="sxs-lookup"><span data-stu-id="ff82a-111">Microsoft recommends using Intune for application and device management.</span></span>
    
<span data-ttu-id="ff82a-112">行動裝置管理（MDM）適用于下列情況：</span><span class="sxs-lookup"><span data-stu-id="ff82a-112">Mobile Device Management (MDM) is applicable for:</span></span> 
* <span data-ttu-id="ff82a-113">MDM 已部署 + 公司入口網站</span><span class="sxs-lookup"><span data-stu-id="ff82a-113">MDM deployed + Company Portal</span></span> 
* <span data-ttu-id="ff82a-114">Buisness （非公開）應用程式行</span><span class="sxs-lookup"><span data-stu-id="ff82a-114">Line of Buisness (non-public) apps</span></span>
* <span data-ttu-id="ff82a-115">透過公司入口網站手動安裝可用的應用程式</span><span class="sxs-lookup"><span data-stu-id="ff82a-115">Manual installation of available applications through Company Portal</span></span>
* <span data-ttu-id="ff82a-116">透過 MDM 原則管理推送</span><span class="sxs-lookup"><span data-stu-id="ff82a-116">Admin push through MDM policy</span></span>
* <span data-ttu-id="ff82a-117">透過 MDM 自動更新</span><span class="sxs-lookup"><span data-stu-id="ff82a-117">Auto update through MDM</span></span>

## <span data-ttu-id="ff82a-118">商務用 Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="ff82a-118">Microsoft Store for Business</span></span>

<span data-ttu-id="ff82a-119">[Microsoft 網上商店可為](app-deploy-store-business.md)IT 決策者與企業中的系統管理員，以尋找、取得、管理及發佈免費和付費的 app。</span><span class="sxs-lookup"><span data-stu-id="ff82a-119">The [Microsoft Store for Business](app-deploy-store-business.md) provides IT decision-makers and administrators in businesses to find, acquire, manage, and distribute free and paid apps.</span></span> <span data-ttu-id="ff82a-120">IT 系統管理員可以管理一個詳細目錄中的 Microsoft Store 應用程式與私人企業營運應用程式，以及視需要指派和重複使用授權。</span><span class="sxs-lookup"><span data-stu-id="ff82a-120">IT administrators can manage Microsoft Store apps and private line-of-business apps in one inventory, plus assign and re-use licenses as needed.</span></span> <span data-ttu-id="ff82a-121">如需詳細資訊，請參閱[使用 Microsoft Store For Business 的先決條件](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business)。</span><span class="sxs-lookup"><span data-stu-id="ff82a-121">For more information, visit [Prerequisites for using the Microsoft Store for Business](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business).</span></span>
    
<span data-ttu-id="ff82a-122">商務用 Microsoft 網上商店適用于：</span><span class="sxs-lookup"><span data-stu-id="ff82a-122">The Microsoft Store for Business is applicable for:</span></span> 
* <span data-ttu-id="ff82a-123">公開或商務線應用程式</span><span class="sxs-lookup"><span data-stu-id="ff82a-123">Public or Line of Business apps</span></span>
* <span data-ttu-id="ff82a-124">透過 MDM 關聯自動安裝所需的應用程式</span><span class="sxs-lookup"><span data-stu-id="ff82a-124">Automatic installation of required applications through MDM association</span></span>
* <span data-ttu-id="ff82a-125">使用者手動下載應用程式</span><span class="sxs-lookup"><span data-stu-id="ff82a-125">User manually downloads apps</span></span>
* <span data-ttu-id="ff82a-126">自動更新</span><span class="sxs-lookup"><span data-stu-id="ff82a-126">Auto Update</span></span>

## <span data-ttu-id="ff82a-127">Microsoft Store 應用程式</span><span class="sxs-lookup"><span data-stu-id="ff82a-127">Microsoft Store apps</span></span>

<span data-ttu-id="ff82a-128">Microsoft 市集中提供 IT 決策者與企業中的管理員，以尋找、取得、管理及發佈公用應用程式。</span><span class="sxs-lookup"><span data-stu-id="ff82a-128">The Microsoft Store provides IT decision-makers and administrators in businesses to find, acquire, manage, and distribute public apps.</span></span>
    
<span data-ttu-id="ff82a-129">此 Microsoft Store 適用于：</span><span class="sxs-lookup"><span data-stu-id="ff82a-129">This Microsoft Store is applicable for:</span></span> 
* <span data-ttu-id="ff82a-130">僅限公用應用程式</span><span class="sxs-lookup"><span data-stu-id="ff82a-130">Public apps only</span></span>
* <span data-ttu-id="ff82a-131">使用者手動下載應用程式</span><span class="sxs-lookup"><span data-stu-id="ff82a-131">User manually downloads apps</span></span>
* <span data-ttu-id="ff82a-132">連線至網際網路時的自動更新</span><span class="sxs-lookup"><span data-stu-id="ff82a-132">Auto update if connected to Internet</span></span>

<span data-ttu-id="ff82a-133">如需詳細資訊，請造訪 [[全息店應用程式](https://docs.microsoft.com/hololens/holographic-store-apps)]。</span><span class="sxs-lookup"><span data-stu-id="ff82a-133">For more information, visit [Holographic Store Apps](https://docs.microsoft.com/hololens/holographic-store-apps).</span></span>

## <span data-ttu-id="ff82a-134">透過預配套件安裝</span><span class="sxs-lookup"><span data-stu-id="ff82a-134">Install via Provisioning Packages</span></span>

<span data-ttu-id="ff82a-135">[[預配套件](app-deploy-provisioning-package.md)] 可讓您安裝自訂或連線的應用程式，讓 IT 專業人員和系統管理員透過 USB 快速地將 app 安裝至本機裝置。</span><span class="sxs-lookup"><span data-stu-id="ff82a-135">[Provisioning Packages](app-deploy-provisioning-package.md) allow you to install custom or Line of Business apps, allowing IT pros and administrators to quickly install apps to a local device(s) via USB.</span></span> <span data-ttu-id="ff82a-136">您可以在沒有網際網路連線及任何身分識別類型的情況下執行此動作。</span><span class="sxs-lookup"><span data-stu-id="ff82a-136">This can be done without an internet connection and for any identity type.</span></span>
    
<span data-ttu-id="ff82a-137">透過 [預配套件] 安裝適用于：</span><span class="sxs-lookup"><span data-stu-id="ff82a-137">Installing via Provisioning Packages is applicable for:</span></span> 
* <span data-ttu-id="ff82a-138">Buisness （非公開）應用程式行</span><span class="sxs-lookup"><span data-stu-id="ff82a-138">Line of Buisness (non-public) apps</span></span>
* <span data-ttu-id="ff82a-139">公用應用程式（如果有離線安裝程式的話）</span><span class="sxs-lookup"><span data-stu-id="ff82a-139">Public apps (if offline installer is available)</span></span>
* <span data-ttu-id="ff82a-140">僅限 USB 側邊載入</span><span class="sxs-lookup"><span data-stu-id="ff82a-140">USB side-load only</span></span>
* <span data-ttu-id="ff82a-141">無自動更新（需要透過預配套件進行手動更新）</span><span class="sxs-lookup"><span data-stu-id="ff82a-141">No auto update (requires manual updates via Provisioning Package)</span></span>
