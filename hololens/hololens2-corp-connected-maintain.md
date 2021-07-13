---
title: 部署指南-Dynamics 365 Guides 維護的公司連線 HoloLens 2
description: 瞭解如何使用 Dynamics 365 Guides 在公司連線的網路上維護 HoloLens 2 的裝置。
keywords: HoloLens、管理、公司連線、Dynamics 365 Guides、AAD、Azure AD、MDM、行動裝置管理
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
ms.openlocfilehash: 0176e816f167499574607bc16c8fbd6bde757daf
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "113636991"
---
# <a name="maintain---corporate-connected-guide"></a><span data-ttu-id="65554-104">維護-公司連接指南</span><span class="sxs-lookup"><span data-stu-id="65554-104">Maintain - Corporate Connected Guide</span></span>

## <a name="update-hololens"></a><span data-ttu-id="65554-105">更新 HoloLens</span><span class="sxs-lookup"><span data-stu-id="65554-105">Update HoloLens</span></span>

<span data-ttu-id="65554-106">為了提供 IT 系統管理員以 Windows Update 為主的其他管理功能 (例如，能夠將更新部署到裝置群組，以及定義安裝更新的維護時段)，Microsoft 設計了商務用 Windows Update。</span><span class="sxs-lookup"><span data-stu-id="65554-106">Microsoft designed Windows Update for Business to provide IT administrators with additional Windows Update-centric management capabilities, such as the ability to deploy updates to groups of devices and to define maintenance windows for installing updates.</span></span>

<span data-ttu-id="65554-107">管理更新的其中一個常用方法是，將功能延遲30天。</span><span class="sxs-lookup"><span data-stu-id="65554-107">One popular method of managing updates is to do a feature deferral of 30 days.</span></span> <span data-ttu-id="65554-108">這可讓系統管理員更新和預覽新功能、獲得搶先的知識，並通知支援人員有任何新的變更。</span><span class="sxs-lookup"><span data-stu-id="65554-108">This allows Admins to update and preview new features, gaining first hand knowledge and informing your support desk of any new changes.</span></span>

<span data-ttu-id="65554-109">瞭解如何[管理 HoloLens 更新](/hololens/hololens-updates)，包括排程的天數、排程時間，以及在裝置上設定使用中的時數，因此它會在工作時間之外進行更新。</span><span class="sxs-lookup"><span data-stu-id="65554-109">Learn how to [manage HoloLens updates](/hololens/hololens-updates), including scheduled days, scheduled time, and setting active hours on the device, so it will update outside of working hours.</span></span>

## <a name="how-to-update-dynamics-365-guides-and-other-store-apps"></a><span data-ttu-id="65554-110">如何更新 Dynamics 365 Guides (和其他商店應用程式) </span><span class="sxs-lookup"><span data-stu-id="65554-110">How to update Dynamics 365 Guides (and other store apps)</span></span>

<span data-ttu-id="65554-111">Dynamics 365 Guides 是 In-Box 的應用程式，並可透過 Microsoft Store 應用程式更新。</span><span class="sxs-lookup"><span data-stu-id="65554-111">Dynamics 365 Guides is an In-Box app, and can be updated through the Microsoft Store app.</span></span> <span data-ttu-id="65554-112">針對透過 Microsoft Store 下載的所有應用程式，可以[透過 Microsoft Store](/hololens/holographic-store-apps#update-apps)應用程式本身手動更新。</span><span class="sxs-lookup"><span data-stu-id="65554-112">For all apps that are downloaded through the Microsoft Store, they can be [updated through the Microsoft Store](/hololens/holographic-store-apps#update-apps) app itself manually.</span></span>

## <a name="how-to-update-lob-apps"></a><span data-ttu-id="65554-113">如何更新 LOB 應用程式</span><span class="sxs-lookup"><span data-stu-id="65554-113">How to update LOB apps</span></span>

<span data-ttu-id="65554-114">LOB 應用程式的更新方式與新增至 Intune 的方式相同。</span><span class="sxs-lookup"><span data-stu-id="65554-114">LOB apps can be updated in the same way they were added to Intune.</span></span> <span data-ttu-id="65554-115">您可以在 Intune 中更新應用程式，方法是將具有較高版本號碼的新應用程式上傳至現有的應用程式設定。</span><span class="sxs-lookup"><span data-stu-id="65554-115">Apps can be updated in Intune by uploading the new app with a higher version number to the existing App configuration.</span></span> <span data-ttu-id="65554-116">當裝置同步至 Intune 時，會觀察到有較新的應用程式版本，而且將會下載較新的應用程式，並取代舊的應用程式。</span><span class="sxs-lookup"><span data-stu-id="65554-116">When the device syncs to Intune, it will observe that there is a newer app version and the newer app will be downloaded and replace the old app.</span></span>

1. <span data-ttu-id="65554-117">若要上傳較新的應用程式，請流覽至 [[記憶體入口網站](https://endpoint.microsoft.com/#home)  ->  **應用程式**-> 所有 **應用程式**]  ->  *TheNameOfYourApp*  ->  **屬性。**</span><span class="sxs-lookup"><span data-stu-id="65554-117">To upload the newer app, navigate to the [MEM portal](https://endpoint.microsoft.com/#home) -> **Apps** -> All **apps** -> *TheNameOfYourApp* -> **Properties.**</span></span>
2. <span data-ttu-id="65554-118">在 [應用程式資訊] 旁邊，選取 [ **編輯]。**</span><span class="sxs-lookup"><span data-stu-id="65554-118">Next to App information, select **Edit.**</span></span>
3. <span data-ttu-id="65554-119">針對 [選取要更新的檔案] 的值 &quot; &quot; ，選取您的檔案。</span><span class="sxs-lookup"><span data-stu-id="65554-119">For the value of &quot;Select file to update&quot;, select your file.</span></span>
4. <span data-ttu-id="65554-120">從這裡，使用操作功能表來開啟檔案瀏覽器，並上傳較新版本的 LOB 應用程式。</span><span class="sxs-lookup"><span data-stu-id="65554-120">From here, use the context menu to open your file explorer and upload the newer version of the LOB app.</span></span> <span data-ttu-id="65554-121">請務必視需要加入相依性。</span><span class="sxs-lookup"><span data-stu-id="65554-121">Ensure to include dependencies as needed.</span></span>

<span data-ttu-id="65554-122">查看更多： [HoloLens 的 Intune 應用程式部署](/hololens/app-deploy-intune)</span><span class="sxs-lookup"><span data-stu-id="65554-122">See more: [Intune App Deployment for HoloLens](/hololens/app-deploy-intune)</span></span>

## <a name="development-plan"></a><span data-ttu-id="65554-123">開發計畫</span><span class="sxs-lookup"><span data-stu-id="65554-123">Development Plan</span></span>

<span data-ttu-id="65554-124">成功註冊您的裝置之後，您現在已準備好將更多 LOB 應用程式部署到您的裝置。</span><span class="sxs-lookup"><span data-stu-id="65554-124">With your device successfully enrolled, you are now prepared to deploy more LOB apps to your devices.</span></span> <span data-ttu-id="65554-125">在本指南中，我們會使用範例應用程式，但您可能會想要使用專為組織需求而打造的自訂應用程式。</span><span class="sxs-lookup"><span data-stu-id="65554-125">For the duration of this Guide, we're using a sample app, but it's more likely that you will want to use custom apps built for your organization's needs.</span></span>

<span data-ttu-id="65554-126">如果您已經有 LOB 應用程式，則您已準備好 [透過 MDM 部署應用程式](/hololens/app-deploy-intune)。</span><span class="sxs-lookup"><span data-stu-id="65554-126">If you already have a LOB app, then you're ready to [deploy your app through MDM](/hololens/app-deploy-intune).</span></span> <span data-ttu-id="65554-127">如果您偏好使用不同的方法，請參閱[HoloLens 2 的應用程式部署總覽](/hololens/app-deploy-overview)，以深入瞭解將 LOB 應用程式部署至裝置的方法。</span><span class="sxs-lookup"><span data-stu-id="65554-127">If you'd prefer a different method, then review the [application deployment overview for HoloLens 2](/hololens/app-deploy-overview) to learn more methods of deploying your LOB app to your devices.</span></span>

<span data-ttu-id="65554-128">如果您尚未建立自己的 LOB 應用程式，或仍在建立程式中，請參閱我們的混合現實開發檔，以 [開始設計和建立原型](/windows/mixed-reality/design/design) ，或學習核心概念以開始 [進行混合現實開發。](/windows/mixed-reality/discover/get-started-with-mr)</span><span class="sxs-lookup"><span data-stu-id="65554-128">If you've yet to create your own LOB app or are still in the process of creation, then review our mixed reality development docs to [start designing and prototyping](/windows/mixed-reality/design/design) or learn the core concepts to [get started with mixed reality development.](/windows/mixed-reality/discover/get-started-with-mr)</span></span>

## <a name="support-plan"></a><span data-ttu-id="65554-129">支援方案</span><span class="sxs-lookup"><span data-stu-id="65554-129">Support Plan</span></span>

<span data-ttu-id="65554-130">支援方案是很棒的一件事。</span><span class="sxs-lookup"><span data-stu-id="65554-130">A support plan is an excellent thing to have in place.</span></span> <span data-ttu-id="65554-131">有某人或群組訓練了針對 HoloLens 裝置上的註冊程式進行疑難排解，以及組織內的 HoloLens 裝置一般用途，都很有用。</span><span class="sxs-lookup"><span data-stu-id="65554-131">Having someone, or a group, trained up on troubleshooting the enrollment process on HoloLens devices and also general use of the HoloLens device within your organization is useful.</span></span> <span data-ttu-id="65554-132">為了讓您的使用者能夠更快速地解決問題，我們建議您以類似于下列順序的方式處理您的呈報流程：</span><span class="sxs-lookup"><span data-stu-id="65554-132">In order to allow your users to have the faster resolution of their issues, we suggest that your escalation process is handled in a similar manner to this order:</span></span>

1. <span data-ttu-id="65554-133">您的支援人員。</span><span class="sxs-lookup"><span data-stu-id="65554-133">Your Support desk.</span></span>
2. <span data-ttu-id="65554-134">您的 HoloLens 專家團隊</span><span class="sxs-lookup"><span data-stu-id="65554-134">Your HoloLens Expert team</span></span>
3. <span data-ttu-id="65554-135">[HoloLens 檔](/hololens/)  / [HoloLens 疑難排解](/hololens/hololens-troubleshooting)檔</span><span class="sxs-lookup"><span data-stu-id="65554-135">[HoloLens Docs](/hololens/) / [HoloLens Troubleshooting Docs](/hololens/hololens-troubleshooting)</span></span>
4. [<span data-ttu-id="65554-136">連絡人支援</span><span class="sxs-lookup"><span data-stu-id="65554-136">Contact Support</span></span>](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="device-management"></a><span data-ttu-id="65554-137">裝置管理</span><span class="sxs-lookup"><span data-stu-id="65554-137">Device Management</span></span>

<span data-ttu-id="65554-138">本指南討論如何設定行動裝置管理 (MDM) ，並使用它來設定某些裝置設定，並套用設定，以允許 Wi-Fi 憑證和 proxy 的存取。</span><span class="sxs-lookup"><span data-stu-id="65554-138">This guide talked about setting up Mobile Device Management (MDM) and used it to set up some device configurations and apply settings to allow access in terms of Wi-Fi certificates and proxy.</span></span> <span data-ttu-id="65554-139">不過，MDM 也可以用來透過 Csp 和原則套用裝置限制。</span><span class="sxs-lookup"><span data-stu-id="65554-139">However, MDM can also be used to apply device restrictions via CSPs and Policies.</span></span>

<span data-ttu-id="65554-140">在許多情況下，裝置可能會有連線能力限制，例如藍牙、VPN、USB，甚至是關閉相機或麥克風的存取。</span><span class="sxs-lookup"><span data-stu-id="65554-140">In many cases, devices can have connectivity restrictions, such as Bluetooth, VPN, USB or even turning off access to the camera or microphone.</span></span> <span data-ttu-id="65554-141">如果上述任何一項感興趣，建議您閱讀我們的 [一般裝置限制頁面](/hololens/hololens-common-device-restrictions)。</span><span class="sxs-lookup"><span data-stu-id="65554-141">If any of these interests you, then we encourage you to read our [common device restrictions page](/hololens/hololens-common-device-restrictions).</span></span>

<span data-ttu-id="65554-142">您可以使用其他更複雜的裝置限制。</span><span class="sxs-lookup"><span data-stu-id="65554-142">There are other more complex device restrictions you can use.</span></span> <span data-ttu-id="65554-143">例如：</span><span class="sxs-lookup"><span data-stu-id="65554-143">Such as:</span></span>

- <span data-ttu-id="65554-144">使用[SettingsPageVisibility](/hololens/settings-uri-list)限制可以在設定應用程式中查看的頁面，讓使用者只能存取他們需要調整的設定，例如變更其 Wi-Fi 連接。</span><span class="sxs-lookup"><span data-stu-id="65554-144">Limiting the pages that can be viewed in the Settings app by using [SettingsPageVisibility](/hololens/settings-uri-list), allowing users to only access the settings they need to adjust, such as changing their Wi-Fi connection.</span></span>
- <span data-ttu-id="65554-145">使用 [Kiosk 模式](/hololens/hololens-kiosk) 來限制對裝置上的使用者顯示的 UI。</span><span class="sxs-lookup"><span data-stu-id="65554-145">Use [Kiosk mode](/hololens/hololens-kiosk) to limit the UI presented to users on a device.</span></span> <span data-ttu-id="65554-146">您可以將 Kiosk 設定為顯示單一應用程式，或使用自訂起始頁來顯示多個應用程式。</span><span class="sxs-lookup"><span data-stu-id="65554-146">You can set Kiosks to show a single app, or multiple apps with a custom start page.</span></span> <span data-ttu-id="65554-147">Kiosk 也可以向不同的使用者呈現不同的體驗。</span><span class="sxs-lookup"><span data-stu-id="65554-147">Kiosks can also present different experiences to different users.</span></span>
- <span data-ttu-id="65554-148">[Windows 應用程式控制 (WDAC) ](/hololens/windows-defender-application-control-wdac)讓特定應用程式或進程完全啟動。</span><span class="sxs-lookup"><span data-stu-id="65554-148">[Windows Application Control (WDAC)](/hololens/windows-defender-application-control-wdac) to keep specific apps or processes from launching entirely.</span></span>

<span data-ttu-id="65554-149">如果您想要瞭解裝置管理或裝置限制的其他方法，請採取下一個步驟，並閱讀我們的 [裝置管理總覽](/hololens/hololens-csp-policy-overview)。</span><span class="sxs-lookup"><span data-stu-id="65554-149">If you'd like to learn about additional methods of device management or device restrictions, then take the next step and read our [Device Management Overview](/hololens/hololens-csp-policy-overview).</span></span>





