---
title: 設定您的 HoloLens 2
description: 瞭解如何使用 Microsoft (MSA) 或 Azure Active Directory (AAD) 帳戶，在 Wi-Fi 網路上首次設定 HoloLens 2。
ms.assetid: 507305f4-e85a-47c5-a055-a3400ae8a10e
ms.date: 9/17/2019
keywords: Hololens
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 2
ms.openlocfilehash: 9824de1d81fd6ba9ccafc8627d660aebefeaed15
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283874"
---
# <span data-ttu-id="6c851-104">設定您的 HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="6c851-104">Set up your HoloLens 2</span></span>

<span data-ttu-id="6c851-105">第一次開啟 HoloLens 時，系統會引導您設定裝置、使用使用者帳戶登入，以及將 HoloLens 校正到您的眼睛。</span><span class="sxs-lookup"><span data-stu-id="6c851-105">The first time you turn on your HoloLens, you'll be guided through setting up your device, signing in with a user account, and calibrating the HoloLens to your eyes.</span></span>  <span data-ttu-id="6c851-106">本節將逐步解說 HoloLens 2 初次設定體驗。</span><span class="sxs-lookup"><span data-stu-id="6c851-106">This section walks through the HoloLens 2 initial setup experience.</span></span>

<span data-ttu-id="6c851-107">在下一節中，您將了解如何使用 HoloLens 並與全像投影互動。</span><span class="sxs-lookup"><span data-stu-id="6c851-107">In the next section, you'll learn how to work with HoloLens and interact with holograms.</span></span> <span data-ttu-id="6c851-108">若要跳到該篇文章，請參閱[開始使用 HoloLens 2](hololens2-basic-usage.md)。</span><span class="sxs-lookup"><span data-stu-id="6c851-108">To skip ahead to that article, see [Get started with HoloLens 2](hololens2-basic-usage.md).</span></span>

## <span data-ttu-id="6c851-109">開始之前</span><span class="sxs-lookup"><span data-stu-id="6c851-109">Before you start</span></span>

<span data-ttu-id="6c851-110">開始使用之前，請確定您有下列項目可用：</span><span class="sxs-lookup"><span data-stu-id="6c851-110">Before you get started, make sure you have the following available:</span></span>

<span data-ttu-id="6c851-111">**網路連線**。</span><span class="sxs-lookup"><span data-stu-id="6c851-111">**A network connection**.</span></span> <span data-ttu-id="6c851-112">您需要將 HoloLens 連線至網路來進行設定。</span><span class="sxs-lookup"><span data-stu-id="6c851-112">You'll need to connect your HoloLens to a network to set it up.</span></span> <span data-ttu-id="6c851-113">使用 HoloLens 2，您可以使用 Wi-Fi 或使用乙太網路進行連線 (您將需要 USB-C 轉乙太網路配接器)。</span><span class="sxs-lookup"><span data-stu-id="6c851-113">With HoloLens 2, you can connect with Wi-Fi or by using ethernet (you'll need a USB-C-to-Ethernet adapter).</span></span> <span data-ttu-id="6c851-114">第一次連線時，您需要不必瀏覽至網站或使用憑證即可連線的開放式網路或受密碼保護網路。</span><span class="sxs-lookup"><span data-stu-id="6c851-114">The first time you connect, you'll need an open or password-protected network that doesn't require navigating to a website or using certificates to connect.</span></span> <span data-ttu-id="6c851-115">[深入了解 HoloLens 所使用的網站](hololens-offline.md)。</span><span class="sxs-lookup"><span data-stu-id="6c851-115">[Learn more about the websites that HoloLens uses](hololens-offline.md).</span></span>

<span data-ttu-id="6c851-116">**Microsoft 帳戶**。</span><span class="sxs-lookup"><span data-stu-id="6c851-116">**A Microsoft account**.</span></span> <span data-ttu-id="6c851-117">您還需要使用 Microsoft 帳戶 (如果您的組織擁有裝置，則是工作帳戶) 來登入 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="6c851-117">You'll also need to sign in to HoloLens with a Microsoft account (or with your work account, if your organization owns the device).</span></span> <span data-ttu-id="6c851-118">如果沒有 Microsoft 帳戶，請前往 [account.microsoft.com](https://account.microsoft.com) 免費設定一個帳戶。</span><span class="sxs-lookup"><span data-stu-id="6c851-118">If you don't have a Microsoft account, go to [account.microsoft.com](https://account.microsoft.com) and set one up for free.</span></span>

<span data-ttu-id="6c851-119">**安全、照明充足且無絆倒危險的活動空間**。</span><span class="sxs-lookup"><span data-stu-id="6c851-119">**A safe, well-lit space with no tripping hazards**.</span></span> <span data-ttu-id="6c851-120">[健康與安全資訊](https://go.microsoft.com/fwlink/p/?LinkId=746661)。</span><span class="sxs-lookup"><span data-stu-id="6c851-120">[Health and safety info](https://go.microsoft.com/fwlink/p/?LinkId=746661).</span></span>

<span data-ttu-id="6c851-121">HoloLens 隨附的**選用舒適配件**，可協助您獲得最舒適的配戴感受。</span><span class="sxs-lookup"><span data-stu-id="6c851-121">**The optional comfort accessories** that came with your HoloLens, to help you get the most comfortable fit.</span></span> <span data-ttu-id="6c851-122">[適合和舒適性的詳細說明](hololens2-setup.md#adjust-fit)。</span><span class="sxs-lookup"><span data-stu-id="6c851-122">[More on fit and comfort](hololens2-setup.md#adjust-fit).</span></span>

## <span data-ttu-id="6c851-123">設定 Windows</span><span class="sxs-lookup"><span data-stu-id="6c851-123">Set up Windows</span></span>

<span data-ttu-id="6c851-124">首次啟動 HoloLens 2 時，第一項工作是設定 Windows 全像攝影版。</span><span class="sxs-lookup"><span data-stu-id="6c851-124">The first time you start your HoloLens 2, your first task is to set up Windows Holographic.</span></span>  <span data-ttu-id="6c851-125">啟動 HoloLens 時，您會聽到音樂並看到 Windows 標誌。</span><span class="sxs-lookup"><span data-stu-id="6c851-125">When you start your HoloLens, you will hear music and see a Windows logo.</span></span>

![首次啟動期間的第一個畫面](images/01-magic-moment.png)

<span data-ttu-id="6c851-127">HoloLens 2 會逐步引導您完成下列步驟：</span><span class="sxs-lookup"><span data-stu-id="6c851-127">HoloLens 2 will walk you through the following steps:</span></span>

1. <span data-ttu-id="6c851-128">選取您的語言。</span><span class="sxs-lookup"><span data-stu-id="6c851-128">Select your language.</span></span>
    ![選取語言](images/04-language.png)

1. <span data-ttu-id="6c851-130">選取您的地區。</span><span class="sxs-lookup"><span data-stu-id="6c851-130">Select your region.</span></span>
    ![選取區域](images/05-region.png)

1. <span data-ttu-id="6c851-132">將 HoloLens 校正到您的眼睛。</span><span class="sxs-lookup"><span data-stu-id="6c851-132">Calibrate HoloLens to your eyes.</span></span>  <span data-ttu-id="6c851-133">如果您選擇略過校正，下次登入時，系統會提示您。</span><span class="sxs-lookup"><span data-stu-id="6c851-133">If you choose to skip calibration, you'll be prompted the next time you log in.</span></span>

    <span data-ttu-id="6c851-134">若要校正，您會看到一組目標 (稱為寶石)。</span><span class="sxs-lookup"><span data-stu-id="6c851-134">To calibrate, you'll look at a set of targets (referred to as gems).</span></span> <span data-ttu-id="6c851-135">在校正期間眨眼或閉眼沒關係，但請不要注視著房間或實體空間中的其他物體。</span><span class="sxs-lookup"><span data-stu-id="6c851-135">It's fine if you blink or close your eyes during calibration, but try not to stare at other objects in the room or physical space.</span></span> <span data-ttu-id="6c851-136">HoloLens 使用此程序來了解您的眼睛位置，以便更理想地轉譯您的全像世界。</span><span class="sxs-lookup"><span data-stu-id="6c851-136">HoloLens uses this process to learn about your eye position so that it can better render your holographic world.</span></span> <span data-ttu-id="6c851-137">校正之後，即使面板在您的頭上移動，全像投影仍能正確顯示。</span><span class="sxs-lookup"><span data-stu-id="6c851-137">After calibration, holograms will appear correctly even as the visor shifts on your head.</span></span>

    <span data-ttu-id="6c851-138">校正資訊是儲存在裝置本機上，不會與任何帳戶資訊相關聯。</span><span class="sxs-lookup"><span data-stu-id="6c851-138">Calibration information is stored locally on the device and is not associated with any account information.</span></span> <span data-ttu-id="6c851-139">如需詳細資訊，請參閱[校正資料與安全性](hololens-calibration.md#calibration-data-and-security)。</span><span class="sxs-lookup"><span data-stu-id="6c851-139">For more information, see [Calibration data and security](hololens-calibration.md#calibration-data-and-security).</span></span>

    ![校正選取畫面](images/06-et-corners.png)

1. <span data-ttu-id="6c851-141">連線至網際網路 (選取 Wi-Fi 或乙太網路連線)。</span><span class="sxs-lookup"><span data-stu-id="6c851-141">Connect to the internet (select Wi-Fi or your ethernet connection).</span></span>
     <span data-ttu-id="6c851-142">HoloLens 會根據從 Wi-Fi 網路取得的資訊，自動設定您的時區。</span><span class="sxs-lookup"><span data-stu-id="6c851-142">HoloLens sets your time zone automatically based on information obtained from the Wi-Fi network.</span></span> <span data-ttu-id="6c851-143">設定完成後，您可以使用 [設定] 應用程式變更時區。</span><span class="sxs-lookup"><span data-stu-id="6c851-143">After setup finishes, you can change the time zone by using the Settings app.</span></span>

    ![連線至 Wi-Fi](images/11-network.png)
> [!NOTE] 
> <span data-ttu-id="6c851-145">如果您執行 2019 年 10 月或更新版本的作業系統版本，如果您已完成 Wi-Fi 步驟，但稍後需要在設定中切換到其他網路，則可以同時按**降低音量**和**電源**按鈕以返回此步驟。</span><span class="sxs-lookup"><span data-stu-id="6c851-145">If you progress past the Wi-Fi step and later need to switch to a different network while still in setup, you can press the **Volume Down** and **Power** buttons simultaneously to return to this step if you are running an OS version from October 2019 or later.</span></span> <span data-ttu-id="6c851-146">對於較舊版本，您可能需要[重設裝置](hololens-recovery.md)或在 Wi-Fi 網路不可用的位置重新開機裝置，以防止其自動連線。</span><span class="sxs-lookup"><span data-stu-id="6c851-146">For earlier versions, you may need to [reset the device](hololens-recovery.md) or restart it in a location where the Wi-Fi network is not available to prevent it from automatically connecting.</span></span>
> 
> <span data-ttu-id="6c851-147">另請注意，在 HoloLens 設定期間，認證將在兩分鐘後逾時。</span><span class="sxs-lookup"><span data-stu-id="6c851-147">Also note that during HoloLens Setup, there is a credential timeout of two minutes.</span></span> <span data-ttu-id="6c851-148">請在兩分鐘內輸入使用者名稱/密碼，否則使用者名稱欄位會自動清除。</span><span class="sxs-lookup"><span data-stu-id="6c851-148">The username/password needs to be entered within two minutes otherwise the username field will be automatically cleared.</span></span>

1. <span data-ttu-id="6c851-149">登入您的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="6c851-149">Sign in to your user account.</span></span> <span data-ttu-id="6c851-150">您可以選擇 [我的公司或學校擁有它]\*\*\*\* 或 [我擁有它]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6c851-150">You'll choose between **My work or school owns it** and **I own it**.</span></span>
    - <span data-ttu-id="6c851-151">當您選擇 [我的公司或學校擁有它]\*\*\*\*，您可使用 Azure AD 帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="6c851-151">When you choose **My work or school owns it**, you sign in with an Azure AD account.</span></span> <span data-ttu-id="6c851-152">如果您的組織使用 Azure AD Premium，且已設定自動 MDM 註冊，HoloLens 會自動在 MDM 中註冊。</span><span class="sxs-lookup"><span data-stu-id="6c851-152">If your organization uses Azure AD Premium and has configured automatic MDM enrollment, HoloLens automatically enrolls in MDM.</span></span> <span data-ttu-id="6c851-153">如果您的組織未使用 Azure AD Premium，則無法使用自動 MDM 註冊。</span><span class="sxs-lookup"><span data-stu-id="6c851-153">If your organization does not use Azure AD Premium, automatic MDM enrollment isn't available.</span></span> <span data-ttu-id="6c851-154">在這種情況下，您必須[在裝置管理中手動註冊 HoloLens](hololens-enroll-mdm.md#different-ways-to-enroll)。</span><span class="sxs-lookup"><span data-stu-id="6c851-154">In that case, you need to [manually enroll HoloLens in device management](hololens-enroll-mdm.md#different-ways-to-enroll).</span></span>
        1. <span data-ttu-id="6c851-155">輸入您組織的帳戶資訊。</span><span class="sxs-lookup"><span data-stu-id="6c851-155">Enter your organizational account information.</span></span>
        1. <span data-ttu-id="6c851-156">接受隱私權聲明和使用者授權合約。</span><span class="sxs-lookup"><span data-stu-id="6c851-156">Accept the privacy statement and the end user license agreement.</span></span>
        1. <span data-ttu-id="6c851-157">使用您的 Azure AD 認證登入。</span><span class="sxs-lookup"><span data-stu-id="6c851-157">Sign in by using your Azure AD credentials.</span></span> <span data-ttu-id="6c851-158">這可能會重新導向至您組織的登入頁面。</span><span class="sxs-lookup"><span data-stu-id="6c851-158">This may redirect to your organization's sign-in page.</span></span>
        1. <span data-ttu-id="6c851-159">繼續設定裝置。</span><span class="sxs-lookup"><span data-stu-id="6c851-159">Continue setting up the device.</span></span>
    - <span data-ttu-id="6c851-160">當您選擇 [我擁有它]\*\*\*\*，您可使用 Microsoft 帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="6c851-160">When you choose **I own it**, you sign in with a Microsoft account.</span></span> <span data-ttu-id="6c851-161">設定完成後，您可以[在裝置管理中手動註冊 HoloLens](hololens-enroll-mdm.md#different-ways-to-enroll)。</span><span class="sxs-lookup"><span data-stu-id="6c851-161">After setup is complete, you can [manually enroll HoloLens in device management](hololens-enroll-mdm.md#different-ways-to-enroll).</span></span>
        1. <span data-ttu-id="6c851-162">輸入您的 Microsoft 帳戶資訊。</span><span class="sxs-lookup"><span data-stu-id="6c851-162">Enter your Microsoft account information.</span></span>
        2. <span data-ttu-id="6c851-163">輸入您的密碼。</span><span class="sxs-lookup"><span data-stu-id="6c851-163">Enter your password.</span></span> <span data-ttu-id="6c851-164">如果您的 Microsoft 帳戶需要[雙步驟驗證 (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/)，請完成驗證程序。</span><span class="sxs-lookup"><span data-stu-id="6c851-164">If your Microsoft account requires [two-step verification (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/), complete the verification process.</span></span>

    ![設定使用者](images/13-device-owner.png)

1. <span data-ttu-id="6c851-166">選取是否要在 HoloLens 2 上啟用語音，以及是否要傳送診斷遙測。</span><span class="sxs-lookup"><span data-stu-id="6c851-166">Select whether to enable speech on HoloLens 2, and whether to send diagnostic telemetry.</span></span>
    ![啟用 Cortana](images/22-do-more-with-voice.png)

1. <span data-ttu-id="6c851-168">選取您的遙測等級。</span><span class="sxs-lookup"><span data-stu-id="6c851-168">Select your telemetry level.</span></span> <span data-ttu-id="6c851-169">如有可能，請啟用完整的遙測。</span><span class="sxs-lookup"><span data-stu-id="6c851-169">If you can, please enable Full telemetry.</span></span> <span data-ttu-id="6c851-170">此資訊確實可協助 HoloLens 工程團隊。</span><span class="sxs-lookup"><span data-stu-id="6c851-170">This information really helps the HoloLens engineering team.</span></span>
     ![遙測等級](images/24-telemetry.png)

1. <span data-ttu-id="6c851-172">了解如何在 HoloLens 2 上使用 [開始] 手勢。</span><span class="sxs-lookup"><span data-stu-id="6c851-172">Learn how to use the start gesture on HoloLens 2.</span></span>
     ![了解如何使用 [開始] 手勢，影像 1](images/26-01-startmenu-learning.png) ![了解如何使用 [開始] 手勢，影像 2](images/26-02-startmenu-learning.png)

<span data-ttu-id="6c851-174">恭喜！</span><span class="sxs-lookup"><span data-stu-id="6c851-174">Congratulations!</span></span>  <span data-ttu-id="6c851-175">設定完成後，您就可以開始使用 HoloLens 了！</span><span class="sxs-lookup"><span data-stu-id="6c851-175">Setup is complete and you're ready to use HoloLens!</span></span>

## <span data-ttu-id="6c851-176">後續步驟</span><span class="sxs-lookup"><span data-stu-id="6c851-176">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="6c851-177">開始使用 HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="6c851-177">Get started with HoloLens 2</span></span>](hololens2-basic-usage.md)
