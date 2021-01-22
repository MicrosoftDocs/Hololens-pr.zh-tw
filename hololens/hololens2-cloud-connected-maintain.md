---
title: 部署指南–雲端連接 HoloLens 2 部署，並以遠端協助維持規模
description: 使用我們在雲端連接的網路上維護和支援 HoloLens 裝置的秘訣，掌握最新資訊。
keywords: HoloLens、管理、雲端連線、遠端協助、AAD、Azure AD、MDM、行動裝置管理
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.date: 12/04/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: bc34c4e41c5a6cee8f3f9a0a97407ee38d419bbc
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283894"
---
# <span data-ttu-id="b6e0a-104">維護-雲端連接指南</span><span class="sxs-lookup"><span data-stu-id="b6e0a-104">Maintain - Cloud connected Guide</span></span>

## <span data-ttu-id="b6e0a-105">更新</span><span class="sxs-lookup"><span data-stu-id="b6e0a-105">Updates</span></span>

<span data-ttu-id="b6e0a-106">為了提供 IT 系統管理員以 Windows Update 為主的其他管理功能 (例如，能夠將更新部署到裝置群組，以及定義安裝更新的維護時段)，Microsoft 設計了商務用 Windows Update。</span><span class="sxs-lookup"><span data-stu-id="b6e0a-106">Microsoft designed Windows Update for Business to provide IT administrators with additional Windows Update-centric management capabilities, such as the ability to deploy updates to groups of devices and to define maintenance windows for installing updates.</span></span>

<span data-ttu-id="b6e0a-107">瞭解如何 [管理 HoloLens 更新](https://docs.microsoft.com/hololens/hololens-updates) ，包括排程的天數、排程時間，以及在裝置上設定使用中的時間，讓它會在工作時間以外更新。</span><span class="sxs-lookup"><span data-stu-id="b6e0a-107">Learn how to [manage HoloLens updates](https://docs.microsoft.com/hololens/hololens-updates) including scheduled days, scheduled time, and setting active hours on the device so it will update outside of working hours.</span></span>

<span data-ttu-id="b6e0a-108">遠端協助是 In-Box 應用程式，可以透過 Microsoft Store app 進行更新。</span><span class="sxs-lookup"><span data-stu-id="b6e0a-108">Remote Assist is an In-Box app, and can be update through the Microsoft Store app.</span></span> <span data-ttu-id="b6e0a-109">對於透過 Microsoft Store 下載的所有 app，都可以手動 [透過 Microsoft store](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) 應用程式本身進行更新。</span><span class="sxs-lookup"><span data-stu-id="b6e0a-109">For all apps that are downloaded through the Microsoft Store they can be [updated through the Microsoft Store](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) app itself manually.</span></span>

## <span data-ttu-id="b6e0a-110">支援方案</span><span class="sxs-lookup"><span data-stu-id="b6e0a-110">Support Plan</span></span>

<span data-ttu-id="b6e0a-111">支援方案是您必須準備好的工作。</span><span class="sxs-lookup"><span data-stu-id="b6e0a-111">A support plan is an excellent thing to have in place.</span></span> <span data-ttu-id="b6e0a-112">讓某個人或群組訓練了 HoloLens 裝置上的註冊程式，以及貴組織內的 HoloLens 裝置的一般用途，都很有説明。</span><span class="sxs-lookup"><span data-stu-id="b6e0a-112">Having someone, or a group trained up on troubleshooting the enrollment process on HoloLens devices and also general use of the HoloLens device within your organization is useful.</span></span> <span data-ttu-id="b6e0a-113">為了讓您的使用者能夠更快速地解決問題，我們建議您以類似的方式來處理升級程式：</span><span class="sxs-lookup"><span data-stu-id="b6e0a-113">In order to allow your users to have the faster resolution of their issues, we suggest that your escalation process is handled in a similar manner to this order:</span></span>

1. <span data-ttu-id="b6e0a-114">您的支援中心。</span><span class="sxs-lookup"><span data-stu-id="b6e0a-114">Your Support desk.</span></span>
2. <span data-ttu-id="b6e0a-115">您的 HoloLens 專家小組</span><span class="sxs-lookup"><span data-stu-id="b6e0a-115">Your HoloLens Expert team</span></span>
3. <span data-ttu-id="b6e0a-116">[HoloLens 檔](https://docs.microsoft.com/hololens/)  / [HoloLens 疑難排解](https://docs.microsoft.com/hololens/hololens-troubleshooting)檔</span><span class="sxs-lookup"><span data-stu-id="b6e0a-116">[HoloLens Docs](https://docs.microsoft.com/hololens/) / [HoloLens Troubleshooting Docs](https://docs.microsoft.com/hololens/hololens-troubleshooting)</span></span>
4. [<span data-ttu-id="b6e0a-117">連絡客戶支援</span><span class="sxs-lookup"><span data-stu-id="b6e0a-117">Contact Support</span></span>](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <span data-ttu-id="b6e0a-118">開發方案</span><span class="sxs-lookup"><span data-stu-id="b6e0a-118">Development Plan</span></span>

<span data-ttu-id="b6e0a-119">在您的裝置已成功註冊之後，您就可以開始將商務用 (LOB 應用程式) 到您的裝置上。</span><span class="sxs-lookup"><span data-stu-id="b6e0a-119">With your device successfully enrolled you are now prepared to deploy Line of Business apps (LOB apps) to your devices.</span></span> <span data-ttu-id="b6e0a-120">這些是為您的組織建立的自訂應用程式&#39;的需求。</span><span class="sxs-lookup"><span data-stu-id="b6e0a-120">These are custom apps built for your organization&#39;s needs.</span></span>

<span data-ttu-id="b6e0a-121">如果您已經有一個業務線 app，您&#39;隨時準備 [透過 MDM 部署您的應用程式](https://docs.microsoft.com/hololens/app-deploy-intune)。</span><span class="sxs-lookup"><span data-stu-id="b6e0a-121">If you already have a line of business app then you&#39;re ready to [deploy your app through MDM](https://docs.microsoft.com/hololens/app-deploy-intune).</span></span> <span data-ttu-id="b6e0a-122">如果您&#39;d 想要使用不同的方法，請參閱 [HoloLens 2 的應用程式部署概述](https://docs.microsoft.com/hololens/app-deploy-overview) ，瞭解如何將 LOB app 部署到您的裝置。</span><span class="sxs-lookup"><span data-stu-id="b6e0a-122">If you&#39;d prefer a different method then review the [application deployment overview for HoloLens 2](https://docs.microsoft.com/hololens/app-deploy-overview) to learn more methods of deploying your LOB app to your devices.</span></span>

<span data-ttu-id="b6e0a-123">如果您&#39;在建立您自己的 LOB app 或仍在建立過程中，請複習我們的混合式現實開發檔，以 [開始設計及建立原型](https://docs.microsoft.com/windows/mixed-reality/design/design) ，或瞭解核心概念，以 [開始使用混合式現實開發。](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)</span><span class="sxs-lookup"><span data-stu-id="b6e0a-123">If you&#39;ve yet to create your own LOB app or are still in the process of creation then review our mixed reality development docs to [start designing and prototyping](https://docs.microsoft.com/windows/mixed-reality/design/design) or learn the core concepts to [get started with mixed reality development.](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)</span></span>

## <span data-ttu-id="b6e0a-124">裝置管理</span><span class="sxs-lookup"><span data-stu-id="b6e0a-124">Device Management</span></span> 

<span data-ttu-id="b6e0a-125">本指南討論了如何設定行動裝置管理 (MDM) 沒有用來套用裝置限制或原則已套用到裝置。</span><span class="sxs-lookup"><span data-stu-id="b6e0a-125">While this guide talked about setting up Mobile Device Management (MDM) it wasn't employed to apply device restrictions or policies were applied to devices.</span></span> <span data-ttu-id="b6e0a-126">裝置管理可以用來透過推送證書來允許存取，或使用各種裝置限制來限制存取。</span><span class="sxs-lookup"><span data-stu-id="b6e0a-126">Device management can be used to both to allow access by pushing certificates, or restrict access with a variety of device restrictions.</span></span> 

<span data-ttu-id="b6e0a-127">在許多情況下，裝置可能會有連接限制，例如，藍牙、VPN、USB，或甚至關閉相機或麥克風的存取。</span><span class="sxs-lookup"><span data-stu-id="b6e0a-127">In many cases devices can have connectivity restrictions such as Bluetooth, VPN, USB or even turning off access to the camera or microphone.</span></span> <span data-ttu-id="b6e0a-128">如果有任何感興趣，我們會鼓勵您閱讀我們的 [常見裝置限制頁面](hololens-common-device-restrictions.md)。</span><span class="sxs-lookup"><span data-stu-id="b6e0a-128">If any of these interests you then we encourage you to read our [common device restrictions page](hololens-common-device-restrictions.md).</span></span>

<span data-ttu-id="b6e0a-129">您也可以使用其他更複雜的裝置限制。</span><span class="sxs-lookup"><span data-stu-id="b6e0a-129">There are other more complex device restrictions you can use.</span></span> <span data-ttu-id="b6e0a-130">例如：</span><span class="sxs-lookup"><span data-stu-id="b6e0a-130">Such as:</span></span>

- <span data-ttu-id="b6e0a-131">使用 [SettingsPageVisibility](settings-uri-list.md)限制在 [設定] 應用程式中查看的頁面，讓使用者只能存取他們需要調整的設定（例如變更其 Wi-Fi 連接）。</span><span class="sxs-lookup"><span data-stu-id="b6e0a-131">Limiting the pages that can be viewed in the Settings app by using [SettingsPageVisibility](settings-uri-list.md), allowing users to only access the settings they need to adjust such as changing their Wi-Fi connection.</span></span>
- <span data-ttu-id="b6e0a-132">使用 [Kiosk 模式](hololens-kiosk.md) ，限制在裝置上呈現給使用者的 UI。</span><span class="sxs-lookup"><span data-stu-id="b6e0a-132">Use [Kiosk mode](hololens-kiosk.md) to limit the UI presented to users on a device.</span></span> <span data-ttu-id="b6e0a-133">您可以將網亭設定為以自訂開始頁面顯示單一 app 或多個應用程式。</span><span class="sxs-lookup"><span data-stu-id="b6e0a-133">You can set Kiosks to show a single app, or multiple apps with a custom start page.</span></span> <span data-ttu-id="b6e0a-134">網亭也可以針對不同的使用者呈現不同的體驗。</span><span class="sxs-lookup"><span data-stu-id="b6e0a-134">Kiosks can also present different experiences to different users.</span></span>  
- <span data-ttu-id="b6e0a-135">[Windows 應用程式控制項 (WDAC) ](windows-defender-application-control-wdac.md) ，讓特定的 app 或程式無法完全啟動。</span><span class="sxs-lookup"><span data-stu-id="b6e0a-135">[Windows Application Control (WDAC)](windows-defender-application-control-wdac.md) to keep specific apps or processes from launching entirely.</span></span>

<span data-ttu-id="b6e0a-136">如果您想要瞭解更多不同的裝置管理或裝置限制方法，請執行下一個步驟並閱讀我們的裝置管理概覽。</span><span class="sxs-lookup"><span data-stu-id="b6e0a-136">If you'd like to learn about more different methods of device management or device restrictions, then take the next step and read our Device Management Overview.</span></span>

## <span data-ttu-id="b6e0a-137">後續步驟</span><span class="sxs-lookup"><span data-stu-id="b6e0a-137">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="b6e0a-138">閱讀 Csp 和裝置管理概覽</span><span class="sxs-lookup"><span data-stu-id="b6e0a-138">Read the CSPs and Device Management Overview</span></span>](hololens-csp-policy-overview.md)