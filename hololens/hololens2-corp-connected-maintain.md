---
title: 部署指南 – 使用 Dynamics 365 指南與公司連接的 HoloLens 2 - 維護
description: 瞭解如何使用 Dynamics 365 指南，在公司已連接網路上維護 HoloLens 2 裝置。
keywords: HoloLens、管理、企業連線、Dynamics 365 指南、AAD、Azure AD、MDM、行動裝置管理
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: aboeger
ms.date: 03/24/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: f231e65e17ab053e34e7174e1ed7ff6e7a0a56b8
ms.sourcegitcommit: d7c86ccad7be32f7223d4b801083798454fda740
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/25/2021
ms.locfileid: "11448528"
---
# <a name="maintain---corporate-connected-guide"></a><span data-ttu-id="9b03c-104">維護 - 公司關聯指南</span><span class="sxs-lookup"><span data-stu-id="9b03c-104">Maintain - Corporate Connected Guide</span></span>

## <a name="update-hololens"></a><span data-ttu-id="9b03c-105">更新 HoloLens</span><span class="sxs-lookup"><span data-stu-id="9b03c-105">Update HoloLens</span></span>

<span data-ttu-id="9b03c-106">為了提供 IT 系統管理員以 Windows Update 為主的其他管理功能 (例如，能夠將更新部署到裝置群組，以及定義安裝更新的維護時段)，Microsoft 設計了商務用 Windows Update。</span><span class="sxs-lookup"><span data-stu-id="9b03c-106">Microsoft designed Windows Update for Business to provide IT administrators with additional Windows Update-centric management capabilities, such as the ability to deploy updates to groups of devices and to define maintenance windows for installing updates.</span></span>

<span data-ttu-id="9b03c-107">管理更新的一種常用方法是將功能延後 30 天。</span><span class="sxs-lookup"><span data-stu-id="9b03c-107">One popular method of managing updates is to do a feature deferral of 30 days.</span></span> <span data-ttu-id="9b03c-108">這可讓系統管理員更新和預覽新功能、取得第一手知識，並告知支援人員任何新的變更。</span><span class="sxs-lookup"><span data-stu-id="9b03c-108">This allows Admins to update and preview new features, gaining first hand knowledge and informing your support desk of any new changes.</span></span>

<span data-ttu-id="9b03c-109">瞭解如何管理 [HoloLens](https://docs.microsoft.com/hololens/hololens-updates)更新 ，包括排定的天數、排定的時間，以及設定裝置上的使用時數，因此它會在工作時間以外更新。</span><span class="sxs-lookup"><span data-stu-id="9b03c-109">Learn how to [manage HoloLens updates](https://docs.microsoft.com/hololens/hololens-updates), including scheduled days, scheduled time, and setting active hours on the device, so it will update outside of working hours.</span></span>

## <a name="how-to-update-dynamics-365-guides-and-other-store-apps"></a><span data-ttu-id="9b03c-110">如何更新 Dynamics 365 (和其他市) </span><span class="sxs-lookup"><span data-stu-id="9b03c-110">How to update Dynamics 365 Guides (and other store apps)</span></span>

<span data-ttu-id="9b03c-111">Dynamics 365 指南是一In-Box應用程式，可透過 Microsoft Store App 進行更新。</span><span class="sxs-lookup"><span data-stu-id="9b03c-111">Dynamics 365 Guides is an In-Box app, and can be updated through the Microsoft Store app.</span></span> <span data-ttu-id="9b03c-112">對於透過 Microsoft Store 下載的所有 App，它們都可以透過 [Microsoft Store](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) App 本身手動更新。</span><span class="sxs-lookup"><span data-stu-id="9b03c-112">For all apps that are downloaded through the Microsoft Store, they can be [updated through the Microsoft Store](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) app itself manually.</span></span>

## <a name="how-to-update-lob-apps"></a><span data-ttu-id="9b03c-113">如何更新 LOB 應用程式</span><span class="sxs-lookup"><span data-stu-id="9b03c-113">How to update LOB apps</span></span>

<span data-ttu-id="9b03c-114">LOB App 的更新方式，與新增到 Intune 的方式相同。</span><span class="sxs-lookup"><span data-stu-id="9b03c-114">LOB apps can be updated in the same way they were added to Intune.</span></span> <span data-ttu-id="9b03c-115">您可以在 Intune 中更新 App，將版本號碼較高的新應用程式上傳至現有的 App 組配置。</span><span class="sxs-lookup"><span data-stu-id="9b03c-115">Apps can be updated in Intune by uploading the new app with a higher version number to the existing App configuration.</span></span> <span data-ttu-id="9b03c-116">當裝置同步到 Intune 時，它會觀察是否有較新的應用程式版本，而且會下載較新的應用程式並取代舊的應用程式。</span><span class="sxs-lookup"><span data-stu-id="9b03c-116">When the device syncs to Intune, it will observe that there is a newer app version and the newer app will be downloaded and replace the old app.</span></span>

1. <span data-ttu-id="9b03c-117">若要上傳較新的應用程式，請流覽至[MEM](https://endpoint.microsoft.com/#home)入口網站  ->  **App** ->\*\* \*\*  ->  *所有應用程式 TheNameOfYourApp*  ->  **屬性。**</span><span class="sxs-lookup"><span data-stu-id="9b03c-117">To upload the newer app, navigate to the [MEM portal](https://endpoint.microsoft.com/#home) -> **Apps** -> All **apps** -> *TheNameOfYourApp* -> **Properties.**</span></span>
2. <span data-ttu-id="9b03c-118">在 App 資訊旁邊，選取編輯 **。**</span><span class="sxs-lookup"><span data-stu-id="9b03c-118">Next to App information, select **Edit.**</span></span>
3. <span data-ttu-id="9b03c-119">若要選取要 &quot; 更新的檔案值 &quot; ，請選取您的檔案。</span><span class="sxs-lookup"><span data-stu-id="9b03c-119">For the value of &quot;Select file to update&quot;, select your file.</span></span>
4. <span data-ttu-id="9b03c-120">在這裡，使用操作功能表開啟檔案檔案管理器並上傳較新版本的 LOB 應用程式。</span><span class="sxs-lookup"><span data-stu-id="9b03c-120">From here, use the context menu to open your file explorer and upload the newer version of the LOB app.</span></span> <span data-ttu-id="9b03c-121">請依需要確保包含相依性。</span><span class="sxs-lookup"><span data-stu-id="9b03c-121">Ensure to include dependencies as needed.</span></span>

<span data-ttu-id="9b03c-122">查看更多 [：HoloLens 的 Intune 應用程式部署](https://docs.microsoft.com/hololens/app-deploy-intune)</span><span class="sxs-lookup"><span data-stu-id="9b03c-122">See more: [Intune App Deployment for HoloLens](https://docs.microsoft.com/hololens/app-deploy-intune)</span></span>

## <a name="development-plan"></a><span data-ttu-id="9b03c-123">開發計畫</span><span class="sxs-lookup"><span data-stu-id="9b03c-123">Development Plan</span></span>

<span data-ttu-id="9b03c-124">成功註冊您的裝置後，您現在已準備好將更多 LOB 應用程式部署到您的裝置。</span><span class="sxs-lookup"><span data-stu-id="9b03c-124">With your device successfully enrolled, you are now prepared to deploy more LOB apps to your devices.</span></span> <span data-ttu-id="9b03c-125">在本指南期間，我們使用的是範例應用程式，但您很可能會想要使用專為貴組織需求所打造的自訂應用程式。</span><span class="sxs-lookup"><span data-stu-id="9b03c-125">For the duration of this Guide, we're using a sample app, but it's more likely that you will want to use custom apps built for your organization's needs.</span></span>

<span data-ttu-id="9b03c-126">如果您已經有 LOB 應用程式，那麼就可以透過 [MDM 部署應用程式了](https://docs.microsoft.com/hololens/app-deploy-intune)。</span><span class="sxs-lookup"><span data-stu-id="9b03c-126">If you already have a LOB app, then you're ready to [deploy your app through MDM](https://docs.microsoft.com/hololens/app-deploy-intune).</span></span> <span data-ttu-id="9b03c-127">如果您想要不同的方法，請查看 [HoloLens 2](https://docs.microsoft.com/hololens/app-deploy-overview) 的應用程式部署概觀，以深入瞭解將 LOB 應用程式部署到您的裝置的方法。</span><span class="sxs-lookup"><span data-stu-id="9b03c-127">If you'd prefer a different method, then review the [application deployment overview for HoloLens 2](https://docs.microsoft.com/hololens/app-deploy-overview) to learn more methods of deploying your LOB app to your devices.</span></span>

<span data-ttu-id="9b03c-128">如果您尚未建立自己的 LOB 應用程式，或仍在建立過程中，請閱閱我們的混合實境開發檔，開始設計和建立原型，[](https://docs.microsoft.com/windows/mixed-reality/design/design)或瞭解核心概念，以開始使用混合實境開發[](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)。</span><span class="sxs-lookup"><span data-stu-id="9b03c-128">If you've yet to create your own LOB app or are still in the process of creation, then review our mixed reality development docs to [start designing and prototyping](https://docs.microsoft.com/windows/mixed-reality/design/design) or learn the core concepts to [get started with mixed reality development.](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)</span></span>

## <a name="support-plan"></a><span data-ttu-id="9b03c-129">支援方案</span><span class="sxs-lookup"><span data-stu-id="9b03c-129">Support Plan</span></span>

<span data-ttu-id="9b03c-130">支援計畫是一項絕佳的專案。</span><span class="sxs-lookup"><span data-stu-id="9b03c-130">A support plan is an excellent thing to have in place.</span></span> <span data-ttu-id="9b03c-131">讓某人或群組接受有關在 HoloLens 裝置上針對註冊程式進行疑難排解訓練，以及組織中 HoloLens 裝置一般使用，非常實用。</span><span class="sxs-lookup"><span data-stu-id="9b03c-131">Having someone, or a group, trained up on troubleshooting the enrollment process on HoloLens devices and also general use of the HoloLens device within your organization is useful.</span></span> <span data-ttu-id="9b03c-132">為了讓您的使用者能夠更快速地解決其問題，我們建議您以類似此順序的方式處理您的升級程式：</span><span class="sxs-lookup"><span data-stu-id="9b03c-132">In order to allow your users to have the faster resolution of their issues, we suggest that your escalation process is handled in a similar manner to this order:</span></span>

1. <span data-ttu-id="9b03c-133">您的支援電話台。</span><span class="sxs-lookup"><span data-stu-id="9b03c-133">Your Support desk.</span></span>
2. <span data-ttu-id="9b03c-134">您的 HoloLens 專家團隊</span><span class="sxs-lookup"><span data-stu-id="9b03c-134">Your HoloLens Expert team</span></span>
3. <span data-ttu-id="9b03c-135">[HoloLens Docs](https://docs.microsoft.com/hololens/)  / [HoloLens 疑難排解檔](https://docs.microsoft.com/hololens/hololens-troubleshooting)</span><span class="sxs-lookup"><span data-stu-id="9b03c-135">[HoloLens Docs](https://docs.microsoft.com/hololens/) / [HoloLens Troubleshooting Docs](https://docs.microsoft.com/hololens/hololens-troubleshooting)</span></span>
4. [<span data-ttu-id="9b03c-136">連絡客戶支援</span><span class="sxs-lookup"><span data-stu-id="9b03c-136">Contact Support</span></span>](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="device-management"></a><span data-ttu-id="9b03c-137">裝置管理</span><span class="sxs-lookup"><span data-stu-id="9b03c-137">Device Management</span></span>

<span data-ttu-id="9b03c-138">本指南討論如何設定行動裝置管理 (MDM) ，並用來設定某些裝置設定，並套用設定以允許存取Wi-Fi憑證和 proxy。</span><span class="sxs-lookup"><span data-stu-id="9b03c-138">This guide talked about setting up Mobile Device Management (MDM) and used it to set up some device configurations and apply settings to allow access in terms of Wi-Fi certificates and proxy.</span></span> <span data-ttu-id="9b03c-139">不過，MDM 也可以透過 CSP 和原則來適用裝置限制。</span><span class="sxs-lookup"><span data-stu-id="9b03c-139">However, MDM can also be used to apply device restrictions via CSPs and Policies.</span></span>

<span data-ttu-id="9b03c-140">在許多情況下，裝置可能會有連接限制，例如藍牙、VPN、USB，甚至關閉相機或麥克風的存取。</span><span class="sxs-lookup"><span data-stu-id="9b03c-140">In many cases, devices can have connectivity restrictions, such as Bluetooth, VPN, USB or even turning off access to the camera or microphone.</span></span> <span data-ttu-id="9b03c-141">如果您有任何這些興趣，我們建議您閱讀我們的 [常見裝置限制頁面](https://docs.microsoft.com/hololens/hololens-common-device-restrictions)。</span><span class="sxs-lookup"><span data-stu-id="9b03c-141">If any of these interests you, then we encourage you to read our [common device restrictions page](https://docs.microsoft.com/hololens/hololens-common-device-restrictions).</span></span>

<span data-ttu-id="9b03c-142">您可以使用其他更複雜的裝置限制。</span><span class="sxs-lookup"><span data-stu-id="9b03c-142">There are other more complex device restrictions you can use.</span></span> <span data-ttu-id="9b03c-143">如：</span><span class="sxs-lookup"><span data-stu-id="9b03c-143">Such as:</span></span>

- <span data-ttu-id="9b03c-144">使用 [SettingsPageVisibility](https://docs.microsoft.com/hololens/settings-uri-list)限制可在設定 App 中查看的頁面，讓使用者只能存取需要調整的設定，例如變更Wi-Fi連接。</span><span class="sxs-lookup"><span data-stu-id="9b03c-144">Limiting the pages that can be viewed in the Settings app by using [SettingsPageVisibility](https://docs.microsoft.com/hololens/settings-uri-list), allowing users to only access the settings they need to adjust, such as changing their Wi-Fi connection.</span></span>
- <span data-ttu-id="9b03c-145">使用 [Kiosk 模式](https://docs.microsoft.com/hololens/hololens-kiosk) 來限制在裝置上呈現給使用者的 UI。</span><span class="sxs-lookup"><span data-stu-id="9b03c-145">Use [Kiosk mode](https://docs.microsoft.com/hololens/hololens-kiosk) to limit the UI presented to users on a device.</span></span> <span data-ttu-id="9b03c-146">您可以將資訊站設定為顯示單一應用程式，或顯示具有自訂開始頁面的多個 App。</span><span class="sxs-lookup"><span data-stu-id="9b03c-146">You can set Kiosks to show a single app, or multiple apps with a custom start page.</span></span> <span data-ttu-id="9b03c-147">資訊站也可以向不同的使用者呈現不同的體驗。</span><span class="sxs-lookup"><span data-stu-id="9b03c-147">Kiosks can also present different experiences to different users.</span></span>
- <span data-ttu-id="9b03c-148">[Windows 應用程式控制 (WDAC) ， ](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) 讓特定應用程式或程式完全啟動。</span><span class="sxs-lookup"><span data-stu-id="9b03c-148">[Windows Application Control (WDAC)](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) to keep specific apps or processes from launching entirely.</span></span>

<span data-ttu-id="9b03c-149">如果您想要瞭解其他裝置管理方法或裝置限制，請執行下一個步驟，並閱讀 [我們的裝置管理概觀](https://docs.microsoft.com/hololens/hololens-csp-policy-overview)。</span><span class="sxs-lookup"><span data-stu-id="9b03c-149">If you'd like to learn about additional methods of device management or device restrictions, then take the next step and read our [Device Management Overview](https://docs.microsoft.com/hololens/hololens-csp-policy-overview).</span></span>





