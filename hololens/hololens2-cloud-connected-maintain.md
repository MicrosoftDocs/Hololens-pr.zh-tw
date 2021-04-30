---
title: 部署指南–雲端連線 HoloLens 2 大規模部署與遠端協助-維護
description: 透過雲端連線的網路，隨時掌握維護和支援 HoloLens 裝置的秘訣。
keywords: HoloLens、管理、雲端連線、遠端協助、AAD、Azure AD、MDM、Mobile 裝置管理
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
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308937"
---
# <a name="maintain---cloud-connected-guide"></a><span data-ttu-id="1e5ef-104">維護-雲端連接指南</span><span class="sxs-lookup"><span data-stu-id="1e5ef-104">Maintain - Cloud connected Guide</span></span>

## <a name="updates"></a><span data-ttu-id="1e5ef-105">更新</span><span class="sxs-lookup"><span data-stu-id="1e5ef-105">Updates</span></span>

<span data-ttu-id="1e5ef-106">為了提供 IT 系統管理員以 Windows Update 為主的其他管理功能 (例如，能夠將更新部署到裝置群組，以及定義安裝更新的維護時段)，Microsoft 設計了商務用 Windows Update。</span><span class="sxs-lookup"><span data-stu-id="1e5ef-106">Microsoft designed Windows Update for Business to provide IT administrators with additional Windows Update-centric management capabilities, such as the ability to deploy updates to groups of devices and to define maintenance windows for installing updates.</span></span>

<span data-ttu-id="1e5ef-107">瞭解如何 [管理 HoloLens 更新](https://docs.microsoft.com/hololens/hololens-updates) （包括排程的天數、排程時間，以及在裝置上設定使用中的時數），以在工作時間以外的時間進行更新。</span><span class="sxs-lookup"><span data-stu-id="1e5ef-107">Learn how to [manage HoloLens updates](https://docs.microsoft.com/hololens/hololens-updates) including scheduled days, scheduled time, and setting active hours on the device so it will update outside of working hours.</span></span>

<span data-ttu-id="1e5ef-108">遠端協助是 In-Box 的應用程式，可透過 Microsoft Store 應用程式更新。</span><span class="sxs-lookup"><span data-stu-id="1e5ef-108">Remote Assist is an In-Box app, and can be update through the Microsoft Store app.</span></span> <span data-ttu-id="1e5ef-109">針對透過 Microsoft Store 下載的所有應用程式，可以 [透過 Microsoft Store](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) 應用程式本身手動更新。</span><span class="sxs-lookup"><span data-stu-id="1e5ef-109">For all apps that are downloaded through the Microsoft Store they can be [updated through the Microsoft Store](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) app itself manually.</span></span>

## <a name="support-plan"></a><span data-ttu-id="1e5ef-110">支援方案</span><span class="sxs-lookup"><span data-stu-id="1e5ef-110">Support Plan</span></span>

<span data-ttu-id="1e5ef-111">支援方案是很棒的一件事。</span><span class="sxs-lookup"><span data-stu-id="1e5ef-111">A support plan is an excellent thing to have in place.</span></span> <span data-ttu-id="1e5ef-112">讓某人或群組訓練了 HoloLens 裝置上的註冊程式，以及組織內的 HoloLens 裝置一般用途，都很有用。</span><span class="sxs-lookup"><span data-stu-id="1e5ef-112">Having someone, or a group trained up on troubleshooting the enrollment process on HoloLens devices and also general use of the HoloLens device within your organization is useful.</span></span> <span data-ttu-id="1e5ef-113">為了讓您的使用者能夠更快速地解決問題，我們建議您以類似于下列順序的方式處理您的呈報流程：</span><span class="sxs-lookup"><span data-stu-id="1e5ef-113">In order to allow your users to have the faster resolution of their issues, we suggest that your escalation process is handled in a similar manner to this order:</span></span>

1. <span data-ttu-id="1e5ef-114">您的支援人員。</span><span class="sxs-lookup"><span data-stu-id="1e5ef-114">Your Support desk.</span></span>
2. <span data-ttu-id="1e5ef-115">您的 HoloLens 專家小組</span><span class="sxs-lookup"><span data-stu-id="1e5ef-115">Your HoloLens Expert team</span></span>
3. <span data-ttu-id="1e5ef-116">[HoloLens 檔](https://docs.microsoft.com/hololens/)  / [HoloLens 疑難排解](https://docs.microsoft.com/hololens/hololens-troubleshooting)檔</span><span class="sxs-lookup"><span data-stu-id="1e5ef-116">[HoloLens Docs](https://docs.microsoft.com/hololens/) / [HoloLens Troubleshooting Docs](https://docs.microsoft.com/hololens/hololens-troubleshooting)</span></span>
4. [<span data-ttu-id="1e5ef-117">連絡人支援</span><span class="sxs-lookup"><span data-stu-id="1e5ef-117">Contact Support</span></span>](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="development-plan"></a><span data-ttu-id="1e5ef-118">開發計畫</span><span class="sxs-lookup"><span data-stu-id="1e5ef-118">Development Plan</span></span>

<span data-ttu-id="1e5ef-119">成功註冊您的裝置之後，您現在已準備好將企業營運應用程式部署 (LOB 應用程式) 到您的裝置。</span><span class="sxs-lookup"><span data-stu-id="1e5ef-119">With your device successfully enrolled you are now prepared to deploy Line of Business apps (LOB apps) to your devices.</span></span> <span data-ttu-id="1e5ef-120">這些是為您的組織建立的自訂應用程式&#39;的需求。</span><span class="sxs-lookup"><span data-stu-id="1e5ef-120">These are custom apps built for your organization&#39;s needs.</span></span>

<span data-ttu-id="1e5ef-121">如果您已經有企業營運應用程式，則&#39;已準備好 [透過 MDM 部署應用程式](https://docs.microsoft.com/hololens/app-deploy-intune)。</span><span class="sxs-lookup"><span data-stu-id="1e5ef-121">If you already have a line of business app then you&#39;re ready to [deploy your app through MDM](https://docs.microsoft.com/hololens/app-deploy-intune).</span></span> <span data-ttu-id="1e5ef-122">如果您&#39;d 偏好不同的方法，請參閱 [HoloLens 2 的應用程式部署總覽](https://docs.microsoft.com/hololens/app-deploy-overview) ，以深入瞭解將 LOB 應用程式部署至裝置的方法。</span><span class="sxs-lookup"><span data-stu-id="1e5ef-122">If you&#39;d prefer a different method then review the [application deployment overview for HoloLens 2](https://docs.microsoft.com/hololens/app-deploy-overview) to learn more methods of deploying your LOB app to your devices.</span></span>

<span data-ttu-id="1e5ef-123">&#39;如果您尚未建立自己的 LOB 應用程式，或仍在建立程式中，請參閱我們的混合現實開發檔，以 [開始設計和建立原型，](https://docs.microsoft.com/windows/mixed-reality/design/design) 或學習核心概念以開始 [進行混合現實開發。](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)</span><span class="sxs-lookup"><span data-stu-id="1e5ef-123">If you&#39;ve yet to create your own LOB app or are still in the process of creation then review our mixed reality development docs to [start designing and prototyping](https://docs.microsoft.com/windows/mixed-reality/design/design) or learn the core concepts to [get started with mixed reality development.](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)</span></span>

## <a name="device-management"></a><span data-ttu-id="1e5ef-124">裝置管理</span><span class="sxs-lookup"><span data-stu-id="1e5ef-124">Device Management</span></span> 

<span data-ttu-id="1e5ef-125">雖然本指南討論的是如何設定行動裝置管理 (MDM) 但它並不適用于套用裝置限制或套用至裝置的原則。</span><span class="sxs-lookup"><span data-stu-id="1e5ef-125">While this guide talked about setting up Mobile Device Management (MDM) it wasn't employed to apply device restrictions or policies were applied to devices.</span></span> <span data-ttu-id="1e5ef-126">裝置管理可用來透過推送憑證來允許存取，或使用各種裝置限制來限制存取。</span><span class="sxs-lookup"><span data-stu-id="1e5ef-126">Device management can be used to both to allow access by pushing certificates, or restrict access with a variety of device restrictions.</span></span> 

<span data-ttu-id="1e5ef-127">在許多情況下，裝置可以有連線能力限制，例如 Bluetooth、VPN、USB，甚至是關閉相機或麥克風的存取。</span><span class="sxs-lookup"><span data-stu-id="1e5ef-127">In many cases devices can have connectivity restrictions such as Bluetooth, VPN, USB or even turning off access to the camera or microphone.</span></span> <span data-ttu-id="1e5ef-128">如果上述任何一項感興趣，建議您閱讀我們的 [一般裝置限制頁面](hololens-common-device-restrictions.md)。</span><span class="sxs-lookup"><span data-stu-id="1e5ef-128">If any of these interests you then we encourage you to read our [common device restrictions page](hololens-common-device-restrictions.md).</span></span>

<span data-ttu-id="1e5ef-129">您可以使用其他更複雜的裝置限制。</span><span class="sxs-lookup"><span data-stu-id="1e5ef-129">There are other more complex device restrictions you can use.</span></span> <span data-ttu-id="1e5ef-130">例如：</span><span class="sxs-lookup"><span data-stu-id="1e5ef-130">Such as:</span></span>

- <span data-ttu-id="1e5ef-131">使用 [SettingsPageVisibility](settings-uri-list.md)限制可在 [設定] 應用程式中查看的頁面，讓使用者只能存取他們需要調整的設定，例如變更其 Wi-Fi 連接。</span><span class="sxs-lookup"><span data-stu-id="1e5ef-131">Limiting the pages that can be viewed in the Settings app by using [SettingsPageVisibility](settings-uri-list.md), allowing users to only access the settings they need to adjust such as changing their Wi-Fi connection.</span></span>
- <span data-ttu-id="1e5ef-132">使用 [Kiosk 模式](hololens-kiosk.md) 來限制對裝置上的使用者顯示的 UI。</span><span class="sxs-lookup"><span data-stu-id="1e5ef-132">Use [Kiosk mode](hololens-kiosk.md) to limit the UI presented to users on a device.</span></span> <span data-ttu-id="1e5ef-133">您可以將 Kiosk 設定為顯示單一應用程式，或使用自訂起始頁來顯示多個應用程式。</span><span class="sxs-lookup"><span data-stu-id="1e5ef-133">You can set Kiosks to show a single app, or multiple apps with a custom start page.</span></span> <span data-ttu-id="1e5ef-134">Kiosk 也可以向不同的使用者呈現不同的體驗。</span><span class="sxs-lookup"><span data-stu-id="1e5ef-134">Kiosks can also present different experiences to different users.</span></span>  
- <span data-ttu-id="1e5ef-135">[Windows 應用程式控制 (WDAC) ](windows-defender-application-control-wdac.md) 讓特定應用程式或進程完全啟動。</span><span class="sxs-lookup"><span data-stu-id="1e5ef-135">[Windows Application Control (WDAC)](windows-defender-application-control-wdac.md) to keep specific apps or processes from launching entirely.</span></span>

<span data-ttu-id="1e5ef-136">如果您想要深入瞭解裝置管理或裝置限制的不同方法，請採取下一個步驟，並閱讀我們的裝置管理總覽。</span><span class="sxs-lookup"><span data-stu-id="1e5ef-136">If you'd like to learn about more different methods of device management or device restrictions, then take the next step and read our Device Management Overview.</span></span>

## <a name="next-step"></a><span data-ttu-id="1e5ef-137">後續步驟</span><span class="sxs-lookup"><span data-stu-id="1e5ef-137">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="1e5ef-138">閱讀 Csp 和裝置管理總覽</span><span class="sxs-lookup"><span data-stu-id="1e5ef-138">Read the CSPs and Device Management Overview</span></span>](hololens-csp-policy-overview.md)