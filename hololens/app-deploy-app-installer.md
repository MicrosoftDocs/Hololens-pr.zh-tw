---
title: 如何透過 HoloLens 2 App 安裝程式載入並安裝應用程式
description: 透過 UI 進行投影片載入和安裝應用程式
keywords: app 管理、app、hololens、app 安裝程式
author: evmill
ms.author: v-evmill
ms.reviewer: qizho
ms.date: 9/17/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 2387c0eb65efc312db4eea7118f3cca44ce6d4b6
ms.sourcegitcommit: 4ad9b6c73913808175b1a448d2be9e33592f65af
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/18/2020
ms.locfileid: "11027462"
---
# <span data-ttu-id="686d1-104">透過 App 安裝程式在 HoloLens 2 上安裝應用程式</span><span class="sxs-lookup"><span data-stu-id="686d1-104">Install Apps on HoloLens 2 via App Installer</span></span>

<span data-ttu-id="686d1-105">現在，使用者可以透過 Appx 套件安裝應用程式，而不需要啟用開發人員模式或使用 Device Portal。</span><span class="sxs-lookup"><span data-stu-id="686d1-105">Users can now install Apps via Appx Bundles now without the need to enable Developer Mode or use Device Portal.</span></span> <span data-ttu-id="686d1-106">這種體驗對於在本機裝置上安裝 app 或與其他不熟悉 HoloLens 中其他 app 安裝方法的人共用應用程式很簡單。</span><span class="sxs-lookup"><span data-stu-id="686d1-106">This experience is simple for installing Apps on local devices or sharing an app with someone else who is unfamiliar with other app install methods on HoloLens.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="686d1-107">此功能目前僅適用于 Windows 測試人員組建 19041.1377 + 中的 avalible。</span><span class="sxs-lookup"><span data-stu-id="686d1-107">This feature is currently only avalible in Windows Insider builds 19041.1377+.</span></span> <span data-ttu-id="686d1-108">[深入瞭解如何在 Windows 測試人員組建中註冊](hololens-insider.md)。</span><span class="sxs-lookup"><span data-stu-id="686d1-108">[Learn more on how to enroll in Windows Insider builds](hololens-insider.md).</span></span>

> [!NOTE]
> <span data-ttu-id="686d1-109">您 app 的解決方案設定必須是 [ **主版** ] 或 [ **發行** ]，因為 app 安裝程式會使用市集中的相依性。</span><span class="sxs-lookup"><span data-stu-id="686d1-109">Your app’s Solution Configuration must be either **Master** or **Release** as the App Installer will use dependencies from the store.</span></span> <span data-ttu-id="686d1-110">查看更多關於 [建立應用程式套件](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs)的資訊。</span><span class="sxs-lookup"><span data-stu-id="686d1-110">See more about [creating app packages](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs).</span></span>

1.  <span data-ttu-id="686d1-111">確定您的 HoloLens 2 裝置已通電且已登入。</span><span class="sxs-lookup"><span data-stu-id="686d1-111">Ensure that your HoloLens 2 device is powered on and you are signed in.</span></span>
1.  <span data-ttu-id="686d1-112">在您的電腦上流覽至您的自訂應用程式，並將 yourapp 複製到 yourdevicename\Internal Storage\Downloads。</span><span class="sxs-lookup"><span data-stu-id="686d1-112">On your PC navigate to your custom app, and copy yourapp.appxbundle to yourdevicename\Internal Storage\Downloads.</span></span> 
    <span data-ttu-id="686d1-113">完成檔案複製之後，您可能會中斷裝置連線，並在稍後完成安裝。</span><span class="sxs-lookup"><span data-stu-id="686d1-113">After your finish copying your file you may disconnect your device and finish the install later.</span></span>
1.  <span data-ttu-id="686d1-114">從您的 HoloLens 2 裝置開啟 [ **開始] 功能表**，選取 [ **所有應用程式** ]，然後啟動檔案 **資源管理器** 應用程式。</span><span class="sxs-lookup"><span data-stu-id="686d1-114">From your HoloLens 2 device Open the **Start Menu**, select **All apps** and launch the **File Explorer** app.</span></span>
1.  <span data-ttu-id="686d1-115">流覽至 [下載] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="686d1-115">Navigate to the Downloads folder.</span></span> <span data-ttu-id="686d1-116">您可能需要在應用程式的左面板上，選取 [ **此裝置** ]，然後流覽至 [下載]。</span><span class="sxs-lookup"><span data-stu-id="686d1-116">You may need to on the left panel of the app select **This device** first, then navigate to Downloads.</span></span>
1.  <span data-ttu-id="686d1-117">選取 yourapp 檔案。</span><span class="sxs-lookup"><span data-stu-id="686d1-117">Select the yourapp.appxbundle file.</span></span> 
1.  <span data-ttu-id="686d1-118">App 安裝程式將會啟動。</span><span class="sxs-lookup"><span data-stu-id="686d1-118">The App Installer will launch.</span></span> <span data-ttu-id="686d1-119">選取 [ **安裝** ] 按鈕來安裝您的 app。</span><span class="sxs-lookup"><span data-stu-id="686d1-119">Select the **Install** button to install your app.</span></span> 

<span data-ttu-id="686d1-120">已安裝的應用程式會在安裝完成後自動啟動。</span><span class="sxs-lookup"><span data-stu-id="686d1-120">The installed app will automatically launch upon the completion of installing.</span></span> 

![透過 App 安裝程式安裝 MRTK 範例](images/hololens-app-installer-picture.jpg)

<span data-ttu-id="686d1-122">如果您的 app 安裝失敗，請檢查下列專案：</span><span class="sxs-lookup"><span data-stu-id="686d1-122">If your app failed to install check the following:</span></span>
-   <span data-ttu-id="686d1-123">您的應用程式是主版本或發行組建。</span><span class="sxs-lookup"><span data-stu-id="686d1-123">Your app is either a Master or Release build.</span></span>
-   <span data-ttu-id="686d1-124">您已 [連線至網際網路](hololens-network.md)。</span><span class="sxs-lookup"><span data-stu-id="686d1-124">You are [connected to the internet](hololens-network.md).</span></span>
-   <span data-ttu-id="686d1-125">您 [的 Microsoft Store 端點](hololens-offline.md) 已正確設定。</span><span class="sxs-lookup"><span data-stu-id="686d1-125">Your [endpoints for the Microsoft Store](hololens-offline.md) are correctly configured.</span></span>  
