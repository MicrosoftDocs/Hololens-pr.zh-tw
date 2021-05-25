---
title: 推出新的設定應用程式
description: 瞭解新的設定應用程式
author: joyjaz
ms.author: v-jjaswinski
keywords: HoloLens，設定，應用程式選擇器，磁片區
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: yannisle
ms.openlocfilehash: bf1a2080c15346843b9ea9b2d0dc93154e185107
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/25/2021
ms.locfileid: "110398969"
---
# <a name="new-settings-app"></a><span data-ttu-id="e06e4-104">新增設定應用程式</span><span class="sxs-lookup"><span data-stu-id="e06e4-104">New Settings app</span></span>

<span data-ttu-id="e06e4-105">在 [Windows 全像21H1 版](hololens-release-notes.md#windows-holographic-version-21h1)中，我們引進了新版本的「設定」應用程式。</span><span class="sxs-lookup"><span data-stu-id="e06e4-105">With [Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1), we're introducing a new version of the Settings app.</span></span> <span data-ttu-id="e06e4-106">新的 [設定] 應用程式包括下欄區域中 HoloLens 2 的新功能和展開的設定：音效、Power & 睡眠、網路 & 網際網路、應用程式、帳戶、輕鬆存取等。</span><span class="sxs-lookup"><span data-stu-id="e06e4-106">The new Settings app includes new features and expanded settings for HoloLens 2 in the following areas: Sound, Power & sleep, Network & Internet, Apps, Accounts, Ease of Access, and more.</span></span>

> [!NOTE]
> <span data-ttu-id="e06e4-107">因為新的設定應用程式與舊版的設定應用程式不同，所以您先前在環境中放置的任何設定視窗將會在更新時移除。</span><span class="sxs-lookup"><span data-stu-id="e06e4-107">Because the new Settings app is distinct from the legacy Settings app, any Settings windows you previously placed around your environment will be removed upon update.</span></span>

![新的設定應用程式首頁](images/new-settings-app.png)

<span data-ttu-id="e06e4-109">**新功能與設定**</span><span class="sxs-lookup"><span data-stu-id="e06e4-109">**New features and settings**</span></span>
- <span data-ttu-id="e06e4-110">設定搜尋：使用關鍵字或設定的名稱搜尋設定首頁的設定。</span><span class="sxs-lookup"><span data-stu-id="e06e4-110">Settings search: search for settings from the Settings homepage using keywords or the setting's name.</span></span>
- <span data-ttu-id="e06e4-111">系統 > [色彩校正](hololens2-display.md#how-to-use-display-color-calibration)</span><span class="sxs-lookup"><span data-stu-id="e06e4-111">System > [Color calibration](hololens2-display.md#how-to-use-display-color-calibration)</span></span>
    - <span data-ttu-id="e06e4-112">為您的 HoloLens 2 顯示選取替代色彩設定檔。</span><span class="sxs-lookup"><span data-stu-id="e06e4-112">Select an alternative color profile for your HoloLens 2 display.</span></span>
- <span data-ttu-id="e06e4-113">系統 > 音效：</span><span class="sxs-lookup"><span data-stu-id="e06e4-113">System > Sound:</span></span>
  - <span data-ttu-id="e06e4-114">輸入和輸出音訊裝置：個別選擇您的輸入和輸出音訊裝置 (例如，透過藍牙耳機聆聽音訊，或使用 USB USB 麥克風進行音訊輸入) 。</span><span class="sxs-lookup"><span data-stu-id="e06e4-114">Input and output audio devices: independently choose your input and output audio devices (for example, listen to audio via Bluetooth headphones or use a USB-C microphone for audio input).</span></span>
    > [!NOTE]
    > <span data-ttu-id="e06e4-115">HoloLens 2 不支援藍牙麥克風。</span><span class="sxs-lookup"><span data-stu-id="e06e4-115">Bluetooth microphones are not supported by HoloLens 2.</span></span>
  - <span data-ttu-id="e06e4-116">應用程式磁片區：個別調整每個應用程式的磁片區。</span><span class="sxs-lookup"><span data-stu-id="e06e4-116">App volume: independently adjust the volume of each app.</span></span> <span data-ttu-id="e06e4-117">請參閱 [每個應用程式音量控制](holographic-home.md#per-app-volume-control)。</span><span class="sxs-lookup"><span data-stu-id="e06e4-117">See [per app volume control](holographic-home.md#per-app-volume-control).</span></span>
- <span data-ttu-id="e06e4-118">系統 > 電源 & 睡眠：選擇裝置在閒置一段時間後應進入睡眠狀態的時間。</span><span class="sxs-lookup"><span data-stu-id="e06e4-118">System > Power & sleep: choose when the device should go to sleep after a period of inactivity.</span></span>
- <span data-ttu-id="e06e4-119">系統 > 電池：以手動方式啟用省電模式模式，或設定省電模式模式自動開啟的電池閾值。</span><span class="sxs-lookup"><span data-stu-id="e06e4-119">System > Battery: manually enable battery saver mode or set a battery threshold at which point battery saver mode turns on automatically.</span></span>
- <span data-ttu-id="e06e4-120">裝置 > USB：您預設可以停用 USB 連接。</span><span class="sxs-lookup"><span data-stu-id="e06e4-120">Devices > USB: you can disable USB connections by default.</span></span>
- <span data-ttu-id="e06e4-121">網路 & 網際網路：</span><span class="sxs-lookup"><span data-stu-id="e06e4-121">Network & Internet:</span></span>
  - <span data-ttu-id="e06e4-122">USB 乙太網路介面卡現在會出現在 Network & Internet 中。</span><span class="sxs-lookup"><span data-stu-id="e06e4-122">USB-C Ethernet adapters will now appear in Network & Internet.</span></span>
  - <span data-ttu-id="e06e4-123">現在已可使用 USB 乙太網路介面卡設定，包括其 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="e06e4-123">USB-C Ethernet adapter settings are now available, including its IP address.</span></span>
  - <span data-ttu-id="e06e4-124">您現在可以在 HoloLens 2 上啟用飛機模式。</span><span class="sxs-lookup"><span data-stu-id="e06e4-124">You can now enable airplane mode on HoloLens 2.</span></span>
- <span data-ttu-id="e06e4-125">應用程式：您可以重設用於檔案和連結類型的預設應用程式。</span><span class="sxs-lookup"><span data-stu-id="e06e4-125">Apps: you can reset the default apps used for file and link types.</span></span> <span data-ttu-id="e06e4-126">如需詳細資訊，請參閱 [預設應用程式選擇器](holographic-home.md#default-app-picker)。</span><span class="sxs-lookup"><span data-stu-id="e06e4-126">For more information see [Default app picker](holographic-home.md#default-app-picker).</span></span>
- <span data-ttu-id="e06e4-127">帳戶 > 其他使用者：裝置擁有者可以新增使用者、將標準使用者升級為裝置擁有者、將裝置擁有者降級為標準使用者，以及移除使用者。</span><span class="sxs-lookup"><span data-stu-id="e06e4-127">Accounts > Other users: device owners can add users, upgrade standard users to device owners, downgrade device owners to standard users, and remove users.</span></span>
- <span data-ttu-id="e06e4-128">輕鬆存取：變更文字大小和某些視覺效果。</span><span class="sxs-lookup"><span data-stu-id="e06e4-128">Ease of Access: change text size and some visual effects.</span></span>

<span data-ttu-id="e06e4-129">**已知問題**</span><span class="sxs-lookup"><span data-stu-id="e06e4-129">**Known issues**</span></span>
- <span data-ttu-id="e06e4-130">將會移除先前放置的設定視窗 (請參閱) 上述的附注。</span><span class="sxs-lookup"><span data-stu-id="e06e4-130">Previously placed Settings windows will be removed (see note above).</span></span>
- <span data-ttu-id="e06e4-131">您無法再使用 [設定] 應用程式重新命名您的裝置。</span><span class="sxs-lookup"><span data-stu-id="e06e4-131">You can no longer rename your device with the Settings app.</span></span> <span data-ttu-id="e06e4-132">IT 系統管理員可以使用 HoloLens 2 裝置名稱範本的 [Windows Autopilot](https://docs.microsoft.com/hololens/hololens2-autopilot) 或 MDM [DevDetail CSP](https://docs.microsoft.com/windows/client-management/mdm/devdetail-csp) Ext/Microsoft/DNSComputerName 節點來重新命名裝置。</span><span class="sxs-lookup"><span data-stu-id="e06e4-132">IT admins can rename devices by using the [Windows Autopilot for HoloLens 2](https://docs.microsoft.com/hololens/hololens2-autopilot) device name template or the MDM [DevDetail CSP](https://docs.microsoft.com/windows/client-management/mdm/devdetail-csp) Ext/Microsoft/DNSComputerName node.</span></span>
- <span data-ttu-id="e06e4-133">[乙太網路] 頁面會 ( [UsbNcm] ) 隨時顯示虛擬乙太網路裝置。</span><span class="sxs-lookup"><span data-stu-id="e06e4-133">The Ethernet page shows a virtual Ethernet device ("UsbNcm") at all times.</span></span>
- <span data-ttu-id="e06e4-134">新 Microsoft Edge 的電池使用量可能不准確，因為它的本質是 UWP 介面卡層所支援的 Win32 桌面應用程式 (不會在) 中預期任何修正。</span><span class="sxs-lookup"><span data-stu-id="e06e4-134">Battery usage for the new Microsoft Edge may not be accurate, due to its nature as a Win32 desktop application supported by a UWP adapter layer (no fix anticipated soon).</span></span>

