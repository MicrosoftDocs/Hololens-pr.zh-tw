---
title: 總覽-應用程式管理
description: 透過行動裝置管理、商務用 Microsoft store 及布建套件，開始概述混合現實應用程式管理。
keywords: HoloLens、使用者、帳戶、應用程式、應用程式管理、
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
ms.openlocfilehash: 951c79e49d67c1a0308e236e4283ffa498a7139f
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308359"
---
# <a name="app-management-overview"></a><span data-ttu-id="882b1-104">應用程式管理：總覽</span><span class="sxs-lookup"><span data-stu-id="882b1-104">App Management: Overview</span></span>

<span data-ttu-id="882b1-105">您可以將應用程式部署在四個不同的路徑上： **Mobile 裝置管理 (MDM)**、**商務用 Microsoft Store**、 **Microsoft Store**，或透過布建來安裝 **它們。**</span><span class="sxs-lookup"><span data-stu-id="882b1-105">You can deploy apps on four different paths: **Mobile Device Management (MDM)**, **Microsoft Store for Business**, **Microsoft Store**, or by installing them via **Provisioning**.</span></span>

## <a name="mobile-device-management-mdm"></a><span data-ttu-id="882b1-106">行動裝置管理 (MDM)</span><span class="sxs-lookup"><span data-stu-id="882b1-106">Mobile Device Management (MDM)</span></span>

<span data-ttu-id="882b1-107">MDM 解決方案可讓 IT 決策者和系統管理員私下自動安裝 (推送) 其內部、企業營運應用程式，或透過使用者群組的商店購買應用程式。</span><span class="sxs-lookup"><span data-stu-id="882b1-107">An MDM solution enables IT decision-makers and administrators to privately auto-install (push) their in-house, line-of-business apps, or purchase apps through the store for a group of users.</span></span> <span data-ttu-id="882b1-108">HoloLens 裝置最適合搭配 Microsoft 端點管理員 (Intune) 來 [管理應用程式](app-deploy-intune.md)。</span><span class="sxs-lookup"><span data-stu-id="882b1-108">HoloLens devices work best with Microsoft Endpoint Manager (Intune) for [application management](app-deploy-intune.md).</span></span> <span data-ttu-id="882b1-109">透過公司入口網站可下載體驗，Intune 也可讓使用者更精細地控制 IT 管理的應用程式。</span><span class="sxs-lookup"><span data-stu-id="882b1-109">Intune also offers users finer-grained control over IT-managed apps through the Company Portal downloadable experience.</span></span>

> [!NOTE]
> <span data-ttu-id="882b1-110">下列指示適用于想要使用 Intune 管理應用程式的使用者。</span><span class="sxs-lookup"><span data-stu-id="882b1-110">The following instructions are for users who want to manage their applications with Intune.</span></span> <span data-ttu-id="882b1-111">Microsoft 建議使用 Intune 進行應用程式和裝置管理。</span><span class="sxs-lookup"><span data-stu-id="882b1-111">Microsoft recommends using Intune for application and device management.</span></span>

<span data-ttu-id="882b1-112">行動裝置管理 (MDM) 適用于：</span><span class="sxs-lookup"><span data-stu-id="882b1-112">Mobile Device Management (MDM) is applicable for:</span></span>

* <span data-ttu-id="882b1-113">已部署 MDM + 公司入口網站</span><span class="sxs-lookup"><span data-stu-id="882b1-113">MDM deployed + Company Portal</span></span>
* <span data-ttu-id="882b1-114">企業營運 (非公用) 應用程式</span><span class="sxs-lookup"><span data-stu-id="882b1-114">Line of Business (non-public) apps</span></span>
* <span data-ttu-id="882b1-115">透過公司入口網站手動安裝可用的應用程式</span><span class="sxs-lookup"><span data-stu-id="882b1-115">Manual installation of available applications through Company Portal</span></span>
* <span data-ttu-id="882b1-116">透過 MDM 原則的系統管理推播</span><span class="sxs-lookup"><span data-stu-id="882b1-116">Admin push through MDM policy</span></span>
* <span data-ttu-id="882b1-117">透過 MDM 自動更新</span><span class="sxs-lookup"><span data-stu-id="882b1-117">Auto update through MDM</span></span>

## <a name="microsoft-store-for-business"></a><span data-ttu-id="882b1-118">商務用 Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="882b1-118">Microsoft Store for Business</span></span>

<span data-ttu-id="882b1-119">[商務用 Microsoft Store](app-deploy-store-business.md)在企業中提供 IT 決策者和系統管理員，以尋找、取得、管理及散發免費和付費應用程式。</span><span class="sxs-lookup"><span data-stu-id="882b1-119">The [Microsoft Store for Business](app-deploy-store-business.md) provides IT decision-makers and administrators in businesses to find, acquire, manage, and distribute free and paid apps.</span></span> <span data-ttu-id="882b1-120">IT 系統管理員可以在單一清查中管理 Microsoft Store apps 和私用企業營運應用程式，並視需要指派和重複使用授權。</span><span class="sxs-lookup"><span data-stu-id="882b1-120">IT administrators can manage Microsoft Store apps and private line-of-business apps in one inventory, plus assign and reuse licenses as needed.</span></span> <span data-ttu-id="882b1-121">如需詳細資訊，請參閱 [使用商務用 Microsoft Store 的必要條件](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business)。</span><span class="sxs-lookup"><span data-stu-id="882b1-121">For more information, visit [Prerequisites for using the Microsoft Store for Business](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business).</span></span>

<span data-ttu-id="882b1-122">商務用 Microsoft Store 適用于：</span><span class="sxs-lookup"><span data-stu-id="882b1-122">The Microsoft Store for Business is applicable for:</span></span>

* <span data-ttu-id="882b1-123">公共或企業營運應用程式</span><span class="sxs-lookup"><span data-stu-id="882b1-123">Public or Line of Business apps</span></span>
* <span data-ttu-id="882b1-124">透過 MDM 關聯自動安裝必要的應用程式</span><span class="sxs-lookup"><span data-stu-id="882b1-124">Automatic installation of required applications through MDM association</span></span>
* <span data-ttu-id="882b1-125">使用者手動下載應用程式</span><span class="sxs-lookup"><span data-stu-id="882b1-125">User manually downloads apps</span></span>
* <span data-ttu-id="882b1-126">自動更新</span><span class="sxs-lookup"><span data-stu-id="882b1-126">Auto Update</span></span>

## <a name="microsoft-store-apps"></a><span data-ttu-id="882b1-127">Microsoft Store 應用程式</span><span class="sxs-lookup"><span data-stu-id="882b1-127">Microsoft Store apps</span></span>

<span data-ttu-id="882b1-128">Microsoft Store 在企業中提供 IT 決策者和系統管理員來尋找、取得、管理及散發公開的應用程式。</span><span class="sxs-lookup"><span data-stu-id="882b1-128">The Microsoft Store provides IT decision-makers and administrators in businesses to find, acquire, manage, and distribute public apps.</span></span>

<span data-ttu-id="882b1-129">此 Microsoft Store 適用于：</span><span class="sxs-lookup"><span data-stu-id="882b1-129">This Microsoft Store is applicable for:</span></span>

* <span data-ttu-id="882b1-130">僅限公用應用程式</span><span class="sxs-lookup"><span data-stu-id="882b1-130">Public apps only</span></span>
* <span data-ttu-id="882b1-131">使用者手動下載應用程式</span><span class="sxs-lookup"><span data-stu-id="882b1-131">User manually downloads apps</span></span>
* <span data-ttu-id="882b1-132">如果連線到網際網路，則自動更新</span><span class="sxs-lookup"><span data-stu-id="882b1-132">Auto update if connected to Internet</span></span>

<span data-ttu-id="882b1-133">如需詳細資訊，請造訪全像 [店 Store 應用程式](https://docs.microsoft.com/hololens/holographic-store-apps)。</span><span class="sxs-lookup"><span data-stu-id="882b1-133">For more information, visit [Holographic Store Apps](https://docs.microsoft.com/hololens/holographic-store-apps).</span></span>

## <a name="install-via-provisioning-packages"></a><span data-ttu-id="882b1-134">透過布建套件安裝</span><span class="sxs-lookup"><span data-stu-id="882b1-134">Install via Provisioning Packages</span></span>

<span data-ttu-id="882b1-135">布建[封裝](app-deploy-provisioning-package.md)可讓您安裝自訂或企業營運應用程式，讓 IT 專業人員和系統管理員能夠快速地將應用程式安裝到本機裝置 (s) 透過 USB。</span><span class="sxs-lookup"><span data-stu-id="882b1-135">[Provisioning Packages](app-deploy-provisioning-package.md) allow you to install custom or Line of Business apps, allowing IT pros and administrators to quickly install apps to a local device(s) via USB.</span></span> <span data-ttu-id="882b1-136">您可以在沒有網際網路連線和任何身分識別類型的情況下完成此安裝。</span><span class="sxs-lookup"><span data-stu-id="882b1-136">This installation can be done without an internet connection and for any identity type.</span></span>

<span data-ttu-id="882b1-137">透過布建套件安裝適用于：</span><span class="sxs-lookup"><span data-stu-id="882b1-137">Installing via Provisioning Packages is applicable for:</span></span>

* <span data-ttu-id="882b1-138">企業營運/自我開發的 (非公用) 應用程式</span><span class="sxs-lookup"><span data-stu-id="882b1-138">Line of Business / Self-developed (non-public) apps</span></span>
* <span data-ttu-id="882b1-139">如果有離線安裝程式，公用應用程式 () </span><span class="sxs-lookup"><span data-stu-id="882b1-139">Public apps (if offline installer is available)</span></span>
* <span data-ttu-id="882b1-140">僅 USB 側載</span><span class="sxs-lookup"><span data-stu-id="882b1-140">USB side-loading only</span></span>
* <span data-ttu-id="882b1-141">沒有自動更新 (需要透過布建套件進行手動更新) </span><span class="sxs-lookup"><span data-stu-id="882b1-141">No auto update (requires manual updates via Provisioning Package)</span></span>

## <a name="install-apps-on-hololens-2-via-app-installer"></a><span data-ttu-id="882b1-142">透過應用程式安裝程式在 HoloLens 2 上安裝應用程式</span><span class="sxs-lookup"><span data-stu-id="882b1-142">Install Apps on HoloLens 2 via App Installer</span></span>

<span data-ttu-id="882b1-143">使用 [應用程式安裝程式](app-deploy-app-installer.md) 使用者可能會有很簡單的體驗，可在本機裝置上安裝應用程式，或與其他不熟悉 HoloLens 上其他應用程式安裝方法的其他人共用應用程式。</span><span class="sxs-lookup"><span data-stu-id="882b1-143">Using the [App Installer](app-deploy-app-installer.md) users can have an experience that is simple for installing Apps on local devices or sharing an app with someone else who is unfamiliar with other app install methods on HoloLens.</span></span> <span data-ttu-id="882b1-144">這可以在不需要啟用開發人員模式或使用裝置入口網站的情況下完成。</span><span class="sxs-lookup"><span data-stu-id="882b1-144">This can be done without needing to enable Developer Mode or use Device Portal.</span></span> <span data-ttu-id="882b1-145">這是散發完全建立之應用程式的簡單方法。</span><span class="sxs-lookup"><span data-stu-id="882b1-145">This is a simple method of distributing a completely built app.</span></span> <span data-ttu-id="882b1-146">無論您是否只是想要向 HoloLens 示範您的應用程式，或是想要部署應用程式，這個方法都可以輕鬆地運作。</span><span class="sxs-lookup"><span data-stu-id="882b1-146">Regardless of if you simply wish to demo your app to another user with a HoloLens, or you'd like to deploy your app this method works easily.</span></span>

<span data-ttu-id="882b1-147">透過應用程式安裝程式安裝適用于：</span><span class="sxs-lookup"><span data-stu-id="882b1-147">Installing via App Installer is applicable for:</span></span>

* <span data-ttu-id="882b1-148">企業營運/自我開發 (非公用) 應用程式</span><span class="sxs-lookup"><span data-stu-id="882b1-148">Line of Business / Self developed (non-public) apps</span></span>
* <span data-ttu-id="882b1-149">僅限側載</span><span class="sxs-lookup"><span data-stu-id="882b1-149">Side-load only</span></span>
* <span data-ttu-id="882b1-150">不需要開發人員模式或裝置入口網站</span><span class="sxs-lookup"><span data-stu-id="882b1-150">Does not require Developer mode or Device portal</span></span>
* <span data-ttu-id="882b1-151">讓終端使用者輕鬆安裝</span><span class="sxs-lookup"><span data-stu-id="882b1-151">Easy for end user to install</span></span>
