---
title: 概覽-App 管理
description: app、管理、app 管理
keywords: HoloLens、使用者、帳戶、app、應用程式管理、
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 2ca0b05b6ed61ddce327a44fedbbcf280b33a106
ms.sourcegitcommit: fc268335e5df529a1cedc2c6b88fa86245fe1b9b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/31/2020
ms.locfileid: "11252664"
---
# <span data-ttu-id="9a5d6-104">應用程式管理: 概觀</span><span class="sxs-lookup"><span data-stu-id="9a5d6-104">App Management: Overview</span></span>

<span data-ttu-id="9a5d6-105">您可以將應用程式部署在四個不同的路徑上： [行動 \*\*裝置管理] (MDM) \*\*、[ **商務用 microsoft store**]、[ **microsoft store**]，或是透過 [ **提供**] 進行安裝。</span><span class="sxs-lookup"><span data-stu-id="9a5d6-105">You can deploy apps on four different paths: **Mobile Device Management (MDM)**, **Microsoft Store for Business**, **Microsoft Store**, or by installing them via **Provisioning**.</span></span>

## <span data-ttu-id="9a5d6-106">行動裝置管理 (MDM)</span><span class="sxs-lookup"><span data-stu-id="9a5d6-106">Mobile Device Management (MDM)</span></span>

<span data-ttu-id="9a5d6-107">MDM 方案可讓 IT 決策者和系統管理員自行自動安裝 (推) 其內部、行業內應用程式，或透過使用者群組的商店購買 app。</span><span class="sxs-lookup"><span data-stu-id="9a5d6-107">An MDM solution enables IT decision-makers and administrators to privately auto-install (push) their in-house, line-of-business apps, or purchase apps through the store for a group of users.</span></span> <span data-ttu-id="9a5d6-108">HoloLens 裝置最適合使用 Microsoft 端點管理員 (Intune) 進行 [應用程式管理](app-deploy-intune.md)。</span><span class="sxs-lookup"><span data-stu-id="9a5d6-108">HoloLens devices work best with Microsoft Endpoint Manager (Intune) for [application management](app-deploy-intune.md).</span></span> <span data-ttu-id="9a5d6-109">Intune 也透過公司入口網站下載體驗，讓使用者能夠更精細地控制 IT 管理的 app。</span><span class="sxs-lookup"><span data-stu-id="9a5d6-109">Intune also offers users finer-grained control over IT-managed apps through the Company Portal downloadable experience.</span></span>

> [!NOTE]
> <span data-ttu-id="9a5d6-110">下列指示適用于想要使用 Intune 管理其應用程式的使用者。</span><span class="sxs-lookup"><span data-stu-id="9a5d6-110">The following instructions are for users who want to manage their applications with Intune.</span></span> <span data-ttu-id="9a5d6-111">Microsoft 建議使用 Intune 進行應用程式與裝置管理。</span><span class="sxs-lookup"><span data-stu-id="9a5d6-111">Microsoft recommends using Intune for application and device management.</span></span>

<span data-ttu-id="9a5d6-112">行動裝置管理 (MDM) 適用于下列情況：</span><span class="sxs-lookup"><span data-stu-id="9a5d6-112">Mobile Device Management (MDM) is applicable for:</span></span>

* <span data-ttu-id="9a5d6-113">MDM 已部署 + 公司入口網站</span><span class="sxs-lookup"><span data-stu-id="9a5d6-113">MDM deployed + Company Portal</span></span>
* <span data-ttu-id="9a5d6-114">商務線 (非公開) app</span><span class="sxs-lookup"><span data-stu-id="9a5d6-114">Line of Business (non-public) apps</span></span>
* <span data-ttu-id="9a5d6-115">透過公司入口網站手動安裝可用的應用程式</span><span class="sxs-lookup"><span data-stu-id="9a5d6-115">Manual installation of available applications through Company Portal</span></span>
* <span data-ttu-id="9a5d6-116">透過 MDM 原則管理推送</span><span class="sxs-lookup"><span data-stu-id="9a5d6-116">Admin push through MDM policy</span></span>
* <span data-ttu-id="9a5d6-117">透過 MDM 自動更新</span><span class="sxs-lookup"><span data-stu-id="9a5d6-117">Auto update through MDM</span></span>

## <span data-ttu-id="9a5d6-118">商務用 Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="9a5d6-118">Microsoft Store for Business</span></span>

<span data-ttu-id="9a5d6-119">[Microsoft 網上商店可為](app-deploy-store-business.md)IT 決策者與企業中的系統管理員，以尋找、取得、管理及發佈免費和付費的 app。</span><span class="sxs-lookup"><span data-stu-id="9a5d6-119">The [Microsoft Store for Business](app-deploy-store-business.md) provides IT decision-makers and administrators in businesses to find, acquire, manage, and distribute free and paid apps.</span></span> <span data-ttu-id="9a5d6-120">IT 管理員可以在一個庫存中管理 Microsoft Store app 和私人業務線應用程式，並視需要指派並重複使用授權。</span><span class="sxs-lookup"><span data-stu-id="9a5d6-120">IT administrators can manage Microsoft Store apps and private line-of-business apps in one inventory, plus assign and reuse licenses as needed.</span></span> <span data-ttu-id="9a5d6-121">如需詳細資訊，請參閱 [使用 Microsoft Store For Business 的先決條件](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business)。</span><span class="sxs-lookup"><span data-stu-id="9a5d6-121">For more information, visit [Prerequisites for using the Microsoft Store for Business](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business).</span></span>

<span data-ttu-id="9a5d6-122">商務用 Microsoft 網上商店適用于：</span><span class="sxs-lookup"><span data-stu-id="9a5d6-122">The Microsoft Store for Business is applicable for:</span></span>

* <span data-ttu-id="9a5d6-123">公開或商務線應用程式</span><span class="sxs-lookup"><span data-stu-id="9a5d6-123">Public or Line of Business apps</span></span>
* <span data-ttu-id="9a5d6-124">透過 MDM 關聯自動安裝所需的應用程式</span><span class="sxs-lookup"><span data-stu-id="9a5d6-124">Automatic installation of required applications through MDM association</span></span>
* <span data-ttu-id="9a5d6-125">使用者手動下載應用程式</span><span class="sxs-lookup"><span data-stu-id="9a5d6-125">User manually downloads apps</span></span>
* <span data-ttu-id="9a5d6-126">自動更新</span><span class="sxs-lookup"><span data-stu-id="9a5d6-126">Auto Update</span></span>

## <span data-ttu-id="9a5d6-127">Microsoft Store 應用程式</span><span class="sxs-lookup"><span data-stu-id="9a5d6-127">Microsoft Store apps</span></span>

<span data-ttu-id="9a5d6-128">Microsoft 市集中提供 IT 決策者與企業中的管理員，以尋找、取得、管理及發佈公用應用程式。</span><span class="sxs-lookup"><span data-stu-id="9a5d6-128">The Microsoft Store provides IT decision-makers and administrators in businesses to find, acquire, manage, and distribute public apps.</span></span>

<span data-ttu-id="9a5d6-129">此 Microsoft Store 適用于：</span><span class="sxs-lookup"><span data-stu-id="9a5d6-129">This Microsoft Store is applicable for:</span></span>

* <span data-ttu-id="9a5d6-130">僅限公用應用程式</span><span class="sxs-lookup"><span data-stu-id="9a5d6-130">Public apps only</span></span>
* <span data-ttu-id="9a5d6-131">使用者手動下載應用程式</span><span class="sxs-lookup"><span data-stu-id="9a5d6-131">User manually downloads apps</span></span>
* <span data-ttu-id="9a5d6-132">連線至網際網路時的自動更新</span><span class="sxs-lookup"><span data-stu-id="9a5d6-132">Auto update if connected to Internet</span></span>

<span data-ttu-id="9a5d6-133">如需詳細資訊，請造訪 [ [全息店應用程式](https://docs.microsoft.com/hololens/holographic-store-apps)]。</span><span class="sxs-lookup"><span data-stu-id="9a5d6-133">For more information, visit [Holographic Store Apps](https://docs.microsoft.com/hololens/holographic-store-apps).</span></span>

## <span data-ttu-id="9a5d6-134">透過預配套件安裝</span><span class="sxs-lookup"><span data-stu-id="9a5d6-134">Install via Provisioning Packages</span></span>

<span data-ttu-id="9a5d6-135">[[預配套件](app-deploy-provisioning-package.md)] 可讓您安裝自訂或連線的應用程式，讓 IT 專業人員和系統管理員透過 USB 將 app 快速安裝至本機裝置 () s。</span><span class="sxs-lookup"><span data-stu-id="9a5d6-135">[Provisioning Packages](app-deploy-provisioning-package.md) allow you to install custom or Line of Business apps, allowing IT pros and administrators to quickly install apps to a local device(s) via USB.</span></span> <span data-ttu-id="9a5d6-136">您可以在沒有網際網路連線及任何身分識別類型的情況下，執行此安裝。</span><span class="sxs-lookup"><span data-stu-id="9a5d6-136">This installation can be done without an internet connection and for any identity type.</span></span>

<span data-ttu-id="9a5d6-137">透過 [預配套件] 安裝適用于：</span><span class="sxs-lookup"><span data-stu-id="9a5d6-137">Installing via Provisioning Packages is applicable for:</span></span>

* <span data-ttu-id="9a5d6-138">經營線/自行開發 (非公開) 應用程式</span><span class="sxs-lookup"><span data-stu-id="9a5d6-138">Line of Business / Self-developed (non-public) apps</span></span>
* <span data-ttu-id="9a5d6-139">公用應用程式在離線安裝程式可用時 () </span><span class="sxs-lookup"><span data-stu-id="9a5d6-139">Public apps (if offline installer is available)</span></span>
* <span data-ttu-id="9a5d6-140">僅限 USB 側載</span><span class="sxs-lookup"><span data-stu-id="9a5d6-140">USB side-loading only</span></span>
* <span data-ttu-id="9a5d6-141">無自動更新 (需要透過預配套件進行手動更新) </span><span class="sxs-lookup"><span data-stu-id="9a5d6-141">No auto update (requires manual updates via Provisioning Package)</span></span>

## <span data-ttu-id="9a5d6-142">透過 App 安裝程式在 HoloLens 2 上安裝應用程式</span><span class="sxs-lookup"><span data-stu-id="9a5d6-142">Install Apps on HoloLens 2 via App Installer</span></span>

<span data-ttu-id="9a5d6-143">您可以使用 [應用程式安裝程式](app-deploy-app-installer.md) 使用者，輕鬆地在本機裝置上安裝應用程式，或與不熟悉 HoloLens 上其他 App 安裝方法的使用者共用應用程式。</span><span class="sxs-lookup"><span data-stu-id="9a5d6-143">Using the [App Installer](app-deploy-app-installer.md) users can have an experience that is simple for installing Apps on local devices or sharing an app with someone else who is unfamiliar with other app install methods on HoloLens.</span></span> <span data-ttu-id="9a5d6-144">您可以在不需要啟用開發人員模式或使用 Device Portal 的情況下執行此動作。</span><span class="sxs-lookup"><span data-stu-id="9a5d6-144">This can be done without needing to enable Developer Mode or use Device Portal.</span></span> <span data-ttu-id="9a5d6-145">這是發佈完全建立的 app 的簡單方法。</span><span class="sxs-lookup"><span data-stu-id="9a5d6-145">This is a simple method of distributing a completely built app.</span></span> <span data-ttu-id="9a5d6-146">不論您是否只想要使用 HoloLens 來示範您的 app，或者您想要部署您的應用程式，此方法很容易運作。</span><span class="sxs-lookup"><span data-stu-id="9a5d6-146">Regardless of if you simply wish to demo your app to another user with a HoloLens, or you'd like to deploy your app this method works easily.</span></span>

<span data-ttu-id="9a5d6-147">透過 App 安裝程式安裝適用于：</span><span class="sxs-lookup"><span data-stu-id="9a5d6-147">Installing via App Installer is applicable for:</span></span>

* <span data-ttu-id="9a5d6-148">商務用列/自行開發 (非公開) 應用程式</span><span class="sxs-lookup"><span data-stu-id="9a5d6-148">Line of Business / Self developed (non-public) apps</span></span>
* <span data-ttu-id="9a5d6-149">僅側邊載入</span><span class="sxs-lookup"><span data-stu-id="9a5d6-149">Side-load only</span></span>
* <span data-ttu-id="9a5d6-150">不需要開發人員模式或 Device portal</span><span class="sxs-lookup"><span data-stu-id="9a5d6-150">Does not require Developer mode or Device portal</span></span>
* <span data-ttu-id="9a5d6-151">便於使用者安裝</span><span class="sxs-lookup"><span data-stu-id="9a5d6-151">Easy for end user to install</span></span>
