---
title: 如何透過 web 安裝程式安裝應用程式
description: 透過適用于 app 安裝程式的 web 安裝程式安裝應用程式
keywords: app 管理、app、hololens、app 安裝程式、web 安裝
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
ms.openlocfilehash: 186cbefb2822455dcf922804ea09533b833b8663
ms.sourcegitcommit: 4ad9b6c73913808175b1a448d2be9e33592f65af
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/18/2020
ms.locfileid: "11027461"
---
# <span data-ttu-id="c4b6f-104">從網頁安裝應用程式</span><span class="sxs-lookup"><span data-stu-id="c4b6f-104">Installing apps from a web page</span></span>

<span data-ttu-id="c4b6f-105">使用者可以直接從 web 伺服器安裝應用程式。</span><span class="sxs-lookup"><span data-stu-id="c4b6f-105">Users can install an app directly from a web server.</span></span> <span data-ttu-id="c4b6f-106">這會將 App 安裝程式與簡單的下載和安裝分發方法結合使用。</span><span class="sxs-lookup"><span data-stu-id="c4b6f-106">This takes use of the App Installer combined with an easy download and install distribution method.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="c4b6f-107">此功能目前僅適用于 Windows 測試人員組建 19041.1366 + 中的 avalible。</span><span class="sxs-lookup"><span data-stu-id="c4b6f-107">This feature is currently only avalible in Windows Insider builds 19041.1366+.</span></span> <span data-ttu-id="c4b6f-108">[深入瞭解如何在 Windows 測試人員組建中註冊](hololens-insider.md)。</span><span class="sxs-lookup"><span data-stu-id="c4b6f-108">[Learn more on how to enroll in Windows Insider builds](hololens-insider.md).</span></span>

## <span data-ttu-id="c4b6f-109">如何設定：</span><span class="sxs-lookup"><span data-stu-id="c4b6f-109">How to set this up:</span></span>
1.  <span data-ttu-id="c4b6f-110">確定您的 app 已正確設定為 [安裝]。</span><span class="sxs-lookup"><span data-stu-id="c4b6f-110">Ensure your app is correctly configured to install.</span></span>
1.  <span data-ttu-id="c4b6f-111">請依照下列 [步驟在網頁上啟用此操作](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage)。</span><span class="sxs-lookup"><span data-stu-id="c4b6f-111">Follow these [steps to enable this on a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).</span></span> 
1.  <span data-ttu-id="c4b6f-112">挑選證書部署方法。</span><span class="sxs-lookup"><span data-stu-id="c4b6f-112">Pick a certificate deployment method.</span></span> 
    1.  <span data-ttu-id="c4b6f-113">您可以將[預配套件](hololens-provisioning.md)套用到本機裝置。</span><span class="sxs-lookup"><span data-stu-id="c4b6f-113">[Provisioning Packages](hololens-provisioning.md) can be applied to local devices.</span></span>
    1.  <span data-ttu-id="c4b6f-114">MDM 可用來 [將憑證與裝置](https://docs.microsoft.com/mem/intune/protect/certificates-configure)設定搭配使用。</span><span class="sxs-lookup"><span data-stu-id="c4b6f-114">MDM can be used to [apply certificates with device configurations](https://docs.microsoft.com/mem/intune/protect/certificates-configure).</span></span>
    1.  <span data-ttu-id="c4b6f-115">使用 [裝置 [憑證管理員](hololens-insider.md#certificate-manager)]。</span><span class="sxs-lookup"><span data-stu-id="c4b6f-115">Use the on device [Certificate Manager](hololens-insider.md#certificate-manager).</span></span> 

## <span data-ttu-id="c4b6f-116">使用者體驗：</span><span class="sxs-lookup"><span data-stu-id="c4b6f-116">End User Experience:</span></span>
1.  <span data-ttu-id="c4b6f-117">使用者使用先前選取的方法，接收並將憑證安裝到裝置。</span><span class="sxs-lookup"><span data-stu-id="c4b6f-117">User receives and installs certificate to the device using a method previously chosen above.</span></span> 
1.  <span data-ttu-id="c4b6f-118">使用者造訪上述步驟所建立的 URL。</span><span class="sxs-lookup"><span data-stu-id="c4b6f-118">User visits the URL created from the step above.</span></span>

<span data-ttu-id="c4b6f-119">App 現在將會安裝到裝置上。</span><span class="sxs-lookup"><span data-stu-id="c4b6f-119">The app will now install to the device.</span></span> <span data-ttu-id="c4b6f-120">若要尋找應用程式，請開啟 [ **開始] 功能表** ，然後選取 [ **所有應用程式** ] 按鈕來尋找您的應用程式。</span><span class="sxs-lookup"><span data-stu-id="c4b6f-120">To find the app open the **Start menu** and select the **All apps** button to find your app.</span></span> 

-   <span data-ttu-id="c4b6f-121">如需此安裝方法的疑難排解說明，請參閱 [app 安裝程式問題疑難排解](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues)。</span><span class="sxs-lookup"><span data-stu-id="c4b6f-121">For help troubleshooting this installation method please visit [troubleshoot app installer issues](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues).</span></span> 

> [!NOTE]
> <span data-ttu-id="c4b6f-122">更新程式中不支援 UI。</span><span class="sxs-lookup"><span data-stu-id="c4b6f-122">UI during the update process is not supported.</span></span> <span data-ttu-id="c4b6f-123">所以不支援 [此頁面](https://docs.microsoft.com/windows/msix/app-installer/update-settings) 上的 [ShowPrompt] 選項和相關選項。</span><span class="sxs-lookup"><span data-stu-id="c4b6f-123">So the ShowPrompt option on [this page](https://docs.microsoft.com/windows/msix/app-installer/update-settings) and related options are not supported.</span></span>
