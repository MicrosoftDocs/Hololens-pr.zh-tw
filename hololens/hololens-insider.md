---
title: 適用於 Microsoft HoloLens 的 Insider Preview
description: 您可以輕鬆開始使用測試人員組建，並為我們的下一個主要作業系統更新提供寶貴的意見反應，以進行 HoloLens。
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 4/21/2020
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: e00c043f7de1142e4d2e08e41ff0d91123d4a98b
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827795"
---
# <span data-ttu-id="78153-103">適用於 Microsoft HoloLens 的 Insider Preview</span><span class="sxs-lookup"><span data-stu-id="78153-103">Insider preview for Microsoft HoloLens</span></span>

<span data-ttu-id="78153-104">歡迎使用 HoloLens 的最新 Insider Preview 組建！</span><span class="sxs-lookup"><span data-stu-id="78153-104">Welcome to the latest Insider Preview builds for HoloLens!</span></span>  <span data-ttu-id="78153-105">開始使用並為我們的下一個重要作業系統更新提供寶貴的意見反應，這是一件簡單的工作。</span><span class="sxs-lookup"><span data-stu-id="78153-105">It's simple to get started and provide valuable feedback for our next major operating system update for HoloLens.</span></span>

## <span data-ttu-id="78153-106">開始接收測試人員組建</span><span class="sxs-lookup"><span data-stu-id="78153-106">Start receiving Insider builds</span></span>

<span data-ttu-id="78153-107">在 HoloLens 2 裝置上，移至 [**設定**  ->  **更新] & 安全性**  ->  **Windows**測試人員計畫，然後選取 [**開始**使用]。</span><span class="sxs-lookup"><span data-stu-id="78153-107">On a HoloLens 2 device go to **Settings** -> **Update & Security** -> **Windows Insider Program** and select **Get started**.</span></span> <span data-ttu-id="78153-108">連結您用來註冊為「Windows 測試人員」的帳戶。</span><span class="sxs-lookup"><span data-stu-id="78153-108">Link the account you used to register as a Windows Insider.</span></span>

<span data-ttu-id="78153-109">接著，選取 [Windows 作用中**的開發**]，選擇您要接收的是**快速**或**慢速**組建，並查看程式條款。</span><span class="sxs-lookup"><span data-stu-id="78153-109">Then, select **Active development of Windows**, choose whether you'd like to receive **Fast** or **Slow** builds, and review the program terms.</span></span>

<span data-ttu-id="78153-110">選取 [**確認]-> [立即重新開機**] 完成。</span><span class="sxs-lookup"><span data-stu-id="78153-110">Select **Confirm -> Restart Now** to finish up.</span></span> <span data-ttu-id="78153-111">重新開機裝置之後，請移至 [**設定]-> 更新 & 安全性-> 檢查更新**以取得最新的組建。</span><span class="sxs-lookup"><span data-stu-id="78153-111">After your device has rebooted, go to **Settings -> Update & Security -> Check for updates** to get the latest build.</span></span>

## <span data-ttu-id="78153-112">停止接收測試人員組建</span><span class="sxs-lookup"><span data-stu-id="78153-112">Stop receiving Insider builds</span></span>

<span data-ttu-id="78153-113">如果您不想再收到 Windows 全息版的測試人員組建，您可以在 HoloLens 執行生產組建時退出宣告，或者，您可以[使用 [](hololens-recovery.md)高級恢復] 隨附的功能，將您的裝置復原至非測試人員版本的 Windows 全息版。</span><span class="sxs-lookup"><span data-stu-id="78153-113">If you no longer want to receive Insider builds of Windows Holographic, you can opt out when your HoloLens is running a production build, or you can [recover your device](hololens-recovery.md) using the Advanced Recovery Companion to recover your device to a non-Insider version of Windows Holographic.</span></span>

> [!CAUTION]
> <span data-ttu-id="78153-114">在手動重新安裝新的預覽組建之後，從測試人員預覽版中取消登錄的已知問題，將會出現藍屏。</span><span class="sxs-lookup"><span data-stu-id="78153-114">There is a known issue in which users who un-enroll from Insider Preview builds after manually reinstalling a fresh preview build would experience a blue screen.</span></span> <span data-ttu-id="78153-115">之後，他們必須手動復原其裝置。</span><span class="sxs-lookup"><span data-stu-id="78153-115">Afterwards they must manually recover their device.</span></span> <span data-ttu-id="78153-116">如需有關您是否會受到影響的完整詳細資料，請查看此[已知問題](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build)的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="78153-116">For full details on if you would be impacted or not, please view more on this [Known Issue](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build).</span></span>

<span data-ttu-id="78153-117">若要確認您的 HoloLens 正在執行生產組建：</span><span class="sxs-lookup"><span data-stu-id="78153-117">To verify that your HoloLens is running a production build:</span></span>

1. <span data-ttu-id="78153-118">移至 [**設定] > [系統 >**]，然後找出組建編號。</span><span class="sxs-lookup"><span data-stu-id="78153-118">Go to **Settings > System > About**, and find the build number.</span></span>
1. [<span data-ttu-id="78153-119">請參閱生產組建編號的版本資訊。</span><span class="sxs-lookup"><span data-stu-id="78153-119">See the release notes for production build numbers.</span></span>](hololens-release-notes.md)

<span data-ttu-id="78153-120">若要退出宣告測試人員組建：</span><span class="sxs-lookup"><span data-stu-id="78153-120">To opt out of Insider builds:</span></span>

1. <span data-ttu-id="78153-121">在運行生產組建的 HoloLens 中，移至 [**設定] > 更新 & 安全性 > Windows**測試人員計畫，然後選取 [停止測試人員**組建**]。</span><span class="sxs-lookup"><span data-stu-id="78153-121">On a HoloLens running a production build, go to **Settings > Update & Security > Windows Insider Program**, and select **Stop Insider builds**.</span></span>
1. <span data-ttu-id="78153-122">依照指示操作以選擇您的裝置。</span><span class="sxs-lookup"><span data-stu-id="78153-122">Follow the instructions to opt out your device.</span></span>



## <span data-ttu-id="78153-123">提供意見反應與報告問題</span><span class="sxs-lookup"><span data-stu-id="78153-123">Provide feedback and report issues</span></span>

<span data-ttu-id="78153-124">請在您的 HoloLens 上使用「[意見反應中樞」 app](hololens-feedback.md) ，以提供意見反應與報告問題。</span><span class="sxs-lookup"><span data-stu-id="78153-124">Please use [the Feedback Hub app](hololens-feedback.md) on your HoloLens to provide feedback and report issues.</span></span> <span data-ttu-id="78153-125">使用意見反應中樞可確保所有必要的診斷資訊都包含在內，以協助我們的工程師快速調試並解決問題。</span><span class="sxs-lookup"><span data-stu-id="78153-125">Using Feedback Hub ensures that all necessary diagnostics information is included to help our engineers quickly debug and resolve the problem.</span></span>  <span data-ttu-id="78153-126">使用中文和日文版的 HoloLens 時，必須以相同的方式報告問題。</span><span class="sxs-lookup"><span data-stu-id="78153-126">Issues with the Chinese and Japanese version of HoloLens should be reported the same way.</span></span>

> [!NOTE]
> <span data-ttu-id="78153-127">請務必接受詢問您是否希望意見反應中樞存取您的 [檔] 資料夾的提示（在出現提示時，選取 **[是]** ）。</span><span class="sxs-lookup"><span data-stu-id="78153-127">Be sure to accept the prompt that asks whether you'd like Feedback Hub to access your Documents folder (select **Yes** when prompted).</span></span>

## <span data-ttu-id="78153-128">開發人員注意事項</span><span class="sxs-lookup"><span data-stu-id="78153-128">Note for developers</span></span>

<span data-ttu-id="78153-129">歡迎與鼓勵您使用 HoloLens 測試人員組建來開發應用程式。</span><span class="sxs-lookup"><span data-stu-id="78153-129">You are welcome and encouraged to try developing your applications using Insider builds of HoloLens.</span></span>  <span data-ttu-id="78153-130">請參閱[HoloLens 開發人員檔](https://developer.microsoft.com/windows/mixed-reality/development)以開始使用。</span><span class="sxs-lookup"><span data-stu-id="78153-130">Check out the [HoloLens Developer Documentation](https://developer.microsoft.com/windows/mixed-reality/development) to get started.</span></span> <span data-ttu-id="78153-131">這些相同的指示可與 HoloLens 測試人員組建搭配使用。</span><span class="sxs-lookup"><span data-stu-id="78153-131">Those same instructions work with Insider builds of HoloLens.</span></span>  <span data-ttu-id="78153-132">您可以使用與您已在 HoloLens 開發中使用的相同 Unity 與 Visual Studio 組建。</span><span class="sxs-lookup"><span data-stu-id="78153-132">You can use the same builds of Unity and Visual Studio that you're already using for HoloLens development.</span></span>


## <span data-ttu-id="78153-133">Windows 測試人員版本資訊</span><span class="sxs-lookup"><span data-stu-id="78153-133">Windows Insider Release Notes</span></span>

<span data-ttu-id="78153-134">從我們的 Windows 全息版開始，您[可能會在2020更新](hololens-release-notes.md)發行版本本中，所有的版本預覽 feautres 現在都 avalible 了！</span><span class="sxs-lookup"><span data-stu-id="78153-134">As of our [Windows Holographic May 2020 Update](hololens-release-notes.md) release all of our release preview feautres are now generally avalible!</span></span> <span data-ttu-id="78153-135">請務必[更新您的 HoloLens](hololens-update-hololens.md) ，以取得所有最新功能。</span><span class="sxs-lookup"><span data-stu-id="78153-135">Make sure to [update your HoloLens](hololens-update-hololens.md) to get all the latest features.</span></span>  

<span data-ttu-id="78153-136">我們將在我們發行給 Windows 測試人員組建時再次更新此頁面，並提供新功能。</span><span class="sxs-lookup"><span data-stu-id="78153-136">We'll be updating this page again with new features again as we release them to Windows Insider builds.</span></span> 

### <span data-ttu-id="78153-137">FFU 下載和快閃路線</span><span class="sxs-lookup"><span data-stu-id="78153-137">FFU download and flash directions</span></span>
<span data-ttu-id="78153-138">若要使用 [航班式簽署 ffu] 進行測試，您必須先將裝置解除鎖定，然後才能閃爍 [航班已簽署] ffu。</span><span class="sxs-lookup"><span data-stu-id="78153-138">To test with a flight signed ffu, you first have to flight unlock your device prior to flashing the flight signed ffu.</span></span>
1. <span data-ttu-id="78153-139">在 PC 上</span><span class="sxs-lookup"><span data-stu-id="78153-139">On PC</span></span>
    1. <span data-ttu-id="78153-140">從以下來源下載 ffu 至您的電腦：[https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload)</span><span class="sxs-lookup"><span data-stu-id="78153-140">Download ffu to your PC from: [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload)</span></span>
    1. <span data-ttu-id="78153-141">從 Microsoft 網上商店安裝弧形（高級恢復隨附版）：[https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8)</span><span class="sxs-lookup"><span data-stu-id="78153-141">Install ARC (Advanced Recovery Companion) from the Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8)</span></span> 
1. <span data-ttu-id="78153-142">在 HoloLens-航班解鎖：開啟**設定**  >  **更新 & 安全性**  >  **Windows**測試人員計畫，然後註冊、重新開機裝置</span><span class="sxs-lookup"><span data-stu-id="78153-142">On HoloLens - Flight Unlock: Open **Settings** > **Update & Security** > **Windows Insider Program** then sign up, reboot device</span></span>
1. <span data-ttu-id="78153-143">快閃 FFU-現在您可以使用 ARC 來閃現已簽署的航班 FFU</span><span class="sxs-lookup"><span data-stu-id="78153-143">Flash FFU - Now you can flash the flight signed FFU using ARC</span></span> 
