---
title: 設定您的 HoloLens 2
description: 瞭解如何使用 Microsoft (MSA) 或 Azure Active Directory (AAD) 帳戶，透過 Wi-Fi 的網路，第一次設定您的 HoloLens 2。
ms.assetid: 507305f4-e85a-47c5-a055-a3400ae8a10e
ms.date: 6/09/2021
keywords: hololens
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 2
ms.openlocfilehash: a5c0e28eff9bb71135309ec5e484fc5b88f02d08
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "113636516"
---
# <a name="set-up-your-hololens-2"></a><span data-ttu-id="92d78-104">設定您的 HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="92d78-104">Set up your HoloLens 2</span></span>

<span data-ttu-id="92d78-105">當您第一次開啟 HoloLens 時，將會引導您設定裝置、使用使用者帳戶登入，以及將 HoloLens 校準至眼睛。</span><span class="sxs-lookup"><span data-stu-id="92d78-105">The first time you turn on your HoloLens, you'll be guided through setting up your device, signing in with a user account, and calibrating the HoloLens to your eyes.</span></span>  <span data-ttu-id="92d78-106">本節將逐步解說 HoloLens 2 初始安裝體驗。</span><span class="sxs-lookup"><span data-stu-id="92d78-106">This section walks through the HoloLens 2 initial setup experience.</span></span>

<span data-ttu-id="92d78-107">在下一節中，您將瞭解如何使用 HoloLens 並與全像的互動。</span><span class="sxs-lookup"><span data-stu-id="92d78-107">In the next section, you'll learn how to work with HoloLens and interact with holograms.</span></span> <span data-ttu-id="92d78-108">若要直接跳到這篇文章，請參閱[HoloLens 2](hololens2-basic-usage.md)。</span><span class="sxs-lookup"><span data-stu-id="92d78-108">To skip ahead to that article, see [Getting around HoloLens 2](hololens2-basic-usage.md).</span></span>

## <a name="before-you-start"></a><span data-ttu-id="92d78-109">在您開始使用 Intune 之前</span><span class="sxs-lookup"><span data-stu-id="92d78-109">Before you start</span></span>

<span data-ttu-id="92d78-110">開始之前，請確定您有下列可用：</span><span class="sxs-lookup"><span data-stu-id="92d78-110">Before you get started, make sure you have the following available:</span></span>

<span data-ttu-id="92d78-111">**網路連接**。</span><span class="sxs-lookup"><span data-stu-id="92d78-111">**A network connection**.</span></span> <span data-ttu-id="92d78-112">您必須將 HoloLens 連接到網路以進行設定。</span><span class="sxs-lookup"><span data-stu-id="92d78-112">You'll need to connect your HoloLens to a network to set it up.</span></span> <span data-ttu-id="92d78-113">使用 HoloLens 2 時，您可以使用 Wi-Fi 連接，或使用 ethernet (您需要 USB-C 乙太網路介面卡) 。</span><span class="sxs-lookup"><span data-stu-id="92d78-113">With HoloLens 2, you can connect with Wi-Fi or by using ethernet (you'll need a USB-C-to-Ethernet adapter).</span></span> <span data-ttu-id="92d78-114">當您第一次連線時，您將需要一個開啟或受密碼保護的網路，而不需要流覽至網站或使用憑證來連接。</span><span class="sxs-lookup"><span data-stu-id="92d78-114">The first time you connect, you'll need an open or password-protected network that doesn't require navigating to a website or using certificates to connect.</span></span> <span data-ttu-id="92d78-115">[深入瞭解 HoloLens 使用的網站](hololens-offline.md)。</span><span class="sxs-lookup"><span data-stu-id="92d78-115">[Learn more about the websites that HoloLens uses](hololens-offline.md).</span></span>

<span data-ttu-id="92d78-116">**Microsoft 帳戶**。</span><span class="sxs-lookup"><span data-stu-id="92d78-116">**A Microsoft account**.</span></span> <span data-ttu-id="92d78-117">如果您的組織擁有裝置) ，您也需要使用 Microsoft 帳戶 (或您的工作帳戶登入 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="92d78-117">You'll also need to sign in to HoloLens with a Microsoft account (or with your work account, if your organization owns the device).</span></span> <span data-ttu-id="92d78-118">如果您沒有 Microsoft 帳戶，請移至 [account.microsoft.com](https://account.microsoft.com) ，並免費設定一個。</span><span class="sxs-lookup"><span data-stu-id="92d78-118">If you don't have a Microsoft account, go to [account.microsoft.com](https://account.microsoft.com) and set one up for free.</span></span>

<span data-ttu-id="92d78-119">**安全、亮點的空間，且不會有任何風險**。</span><span class="sxs-lookup"><span data-stu-id="92d78-119">**A safe, well-lit space with no tripping hazards**.</span></span> <span data-ttu-id="92d78-120">[健全狀況和安全性資訊](https://go.microsoft.com/fwlink/p/?LinkId=746661)。</span><span class="sxs-lookup"><span data-stu-id="92d78-120">[Health and safety info](https://go.microsoft.com/fwlink/p/?LinkId=746661).</span></span>

<span data-ttu-id="92d78-121">您的 HoloLens 隨附 **的選用緩和附屬配件**，可協助您取得最合適的大小。</span><span class="sxs-lookup"><span data-stu-id="92d78-121">**The optional comfort accessories** that came with your HoloLens, to help you get the most comfortable fit.</span></span> <span data-ttu-id="92d78-122">[深入瞭解和緩和](hololens2-setup.md#adjust-fit)。</span><span class="sxs-lookup"><span data-stu-id="92d78-122">[More on fit and comfort](hololens2-setup.md#adjust-fit).</span></span>

## <a name="set-up-windows"></a><span data-ttu-id="92d78-123">設定 Windows</span><span class="sxs-lookup"><span data-stu-id="92d78-123">Set up Windows</span></span>

<span data-ttu-id="92d78-124">當您第一次開始 HoloLens 2 時，您的第一個工作是設定 Windows 全像全像）。</span><span class="sxs-lookup"><span data-stu-id="92d78-124">The first time you start your HoloLens 2, your first task is to set up Windows Holographic.</span></span>  <span data-ttu-id="92d78-125">當您啟動 HoloLens 時，您會聽到音樂並查看 Windows 標誌。</span><span class="sxs-lookup"><span data-stu-id="92d78-125">When you start your HoloLens, you will hear music and see a Windows logo.</span></span>

![第一次開機期間的第一個畫面](images/01-magic-moment.png)

<span data-ttu-id="92d78-127">您將會看到 hummingbird 的四處飛行。</span><span class="sxs-lookup"><span data-stu-id="92d78-127">You will see a hummingbird flying around.</span></span>

![Hummingbird 飛行](images/hummingbird-1.png)

<span data-ttu-id="92d78-129">跟您手。</span><span class="sxs-lookup"><span data-stu-id="92d78-129">Follow it with your hand.</span></span>

![Hummingbird 飛行特寫](images/hummingbird-2.png)

<span data-ttu-id="92d78-131">HoloLens 2 將逐步引導您完成下列步驟：</span><span class="sxs-lookup"><span data-stu-id="92d78-131">HoloLens 2 will walk you through the following steps:</span></span>

1. <span data-ttu-id="92d78-132">選取您的語言。</span><span class="sxs-lookup"><span data-stu-id="92d78-132">Select your language.</span></span>

    ![選取語言](images/04-language.png)

1. <span data-ttu-id="92d78-134">選取您的區域。</span><span class="sxs-lookup"><span data-stu-id="92d78-134">Select your region.</span></span>

    ![選取區域](images/05-region.png)

1. <span data-ttu-id="92d78-136">HoloLens 您的眼睛校正。</span><span class="sxs-lookup"><span data-stu-id="92d78-136">Calibrate HoloLens to your eyes.</span></span>  <span data-ttu-id="92d78-137">如果您選擇略過校正，系統會在您下次登入時提示您。</span><span class="sxs-lookup"><span data-stu-id="92d78-137">If you choose to skip calibration, you'll be prompted the next time you log in.</span></span> 

    1. <span data-ttu-id="92d78-138">首先，您將會調整您的面板。</span><span class="sxs-lookup"><span data-stu-id="92d78-138">First, you'll adjust your visor.</span></span>
    
        ![校正選取畫面](images/06-et-corners.png)

    2. <span data-ttu-id="92d78-140">為了進行校正，您將會看到一組目標 (稱為 gem) 。</span><span class="sxs-lookup"><span data-stu-id="92d78-140">To calibrate, you'll look at a set of targets (referred to as gems).</span></span> <span data-ttu-id="92d78-141">如果您在校正期間閃爍或關閉您的眼睛，但不想 stare 空間或實體空間中的其他物件，則可正常運作。</span><span class="sxs-lookup"><span data-stu-id="92d78-141">It's fine if you blink or close your eyes during calibration, but try not to stare at other objects in the room or physical space.</span></span> <span data-ttu-id="92d78-142">HoloLens 使用此程式來瞭解您的眼睛位置，讓它能夠更妥善地呈現您的全像世界。</span><span class="sxs-lookup"><span data-stu-id="92d78-142">HoloLens uses this process to learn about your eye position so that it can better render your holographic world.</span></span> 

        ![調整您的眼睛](images/07-adjust-eyes.png)

        <span data-ttu-id="92d78-144">在校正之後，即使面板在您的頭上轉移，還是會正確顯示全像投影。</span><span class="sxs-lookup"><span data-stu-id="92d78-144">After calibration, holograms will appear correctly even as the visor shifts on your head.</span></span> <span data-ttu-id="92d78-145">校正資訊會儲存在本機裝置上，而且不會與任何帳戶資訊相關聯。</span><span class="sxs-lookup"><span data-stu-id="92d78-145">Calibration information is stored locally on the device and is not associated with any account information.</span></span> <span data-ttu-id="92d78-146">如需詳細資訊，請參閱 [校正資料和安全性](hololens-calibration.md#calibration-data-and-security)。</span><span class="sxs-lookup"><span data-stu-id="92d78-146">For more information, see [Calibration data and security](hololens-calibration.md#calibration-data-and-security).</span></span>

        ![校正已完成](images/calibration-complete.png)

1. <span data-ttu-id="92d78-148">連線至網際網路 (選取 Wi-Fi 或您的乙太網路連接) 。</span><span class="sxs-lookup"><span data-stu-id="92d78-148">Connect to the internet (select Wi-Fi or your ethernet connection).</span></span>

     <span data-ttu-id="92d78-149">HoloLens 會根據從 Wi-Fi 網路取得的資訊自動設定您的時區。</span><span class="sxs-lookup"><span data-stu-id="92d78-149">HoloLens sets your time zone automatically based on information obtained from the Wi-Fi network.</span></span> <span data-ttu-id="92d78-150">安裝程式完成之後，您可以使用設定應用程式來變更時區。</span><span class="sxs-lookup"><span data-stu-id="92d78-150">After setup finishes, you can change the time zone by using the Settings app.</span></span>

    ![連線到 Wi-Fi](images/11-network.png)

    > [!NOTE] 
    > <span data-ttu-id="92d78-152">如果您的進度超過 Wi-Fi 步驟，而且之後需要切換到不同的網路，但仍在安裝程式中，則如果您執行2019年10月或更新版本的 OS 版本，則可以同時按 **下音量** 和 **電源** 按鈕來返回此步驟。</span><span class="sxs-lookup"><span data-stu-id="92d78-152">If you progress past the Wi-Fi step and later need to switch to a different network while still in setup, you can press the **Volume Down** and **Power** buttons simultaneously to return to this step if you are running an OS version from October 2019 or later.</span></span> <span data-ttu-id="92d78-153">針對較舊的版本，您可能需要 [重設裝置](hololens-recovery.md) ，或在 Wi-Fi 網路無法使用的位置中重新開機，以防止它自動連接。</span><span class="sxs-lookup"><span data-stu-id="92d78-153">For earlier versions, you may need to [reset the device](hololens-recovery.md) or restart it in a location where the Wi-Fi network is not available to prevent it from automatically connecting.</span></span>
    > 
    > <span data-ttu-id="92d78-154">另請注意，在 HoloLens 設定期間，會有兩分鐘的認證超時。</span><span class="sxs-lookup"><span data-stu-id="92d78-154">Also note that during HoloLens Setup, there is a credential timeout of two minutes.</span></span> <span data-ttu-id="92d78-155">使用者名稱/密碼必須在兩分鐘內輸入，否則會自動清除使用者名稱欄位。</span><span class="sxs-lookup"><span data-stu-id="92d78-155">The username/password needs to be entered within two minutes otherwise the username field will be automatically cleared.</span></span>

1. <span data-ttu-id="92d78-156">HoloLens 2 會搜尋並套用 Autopilot 設定檔（如果有的話）。</span><span class="sxs-lookup"><span data-stu-id="92d78-156">HoloLens 2 will search and apply an Autopilot profile if one exists.</span></span> <span data-ttu-id="92d78-157">此畫面上不需要採取任何動作。</span><span class="sxs-lookup"><span data-stu-id="92d78-157">No action is needed on this screen.</span></span>
 
    ![Autopilot 設定檔搜尋](images/autopilot-profile-search.png) 

1. <span data-ttu-id="92d78-159">在授權畫面上按一下 [ **接受** ]。</span><span class="sxs-lookup"><span data-stu-id="92d78-159">Click **Accept** on the licensing screen.</span></span>

    ![Windows 授權合約](images/windows-license-agreement.png)

1. <span data-ttu-id="92d78-161">登入您的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="92d78-161">Sign in to your user account.</span></span> <span data-ttu-id="92d78-162">您可以選擇 **我的工作或學校擁有它** ，而 **我擁有它**。</span><span class="sxs-lookup"><span data-stu-id="92d78-162">You'll choose between **My work or school owns it** and **I own it**.</span></span>

    ![設定使用者](images/13-device-owner.png)
    - <span data-ttu-id="92d78-164">當您選擇 \[我的公司或學校擁有它\]，您可使用 Azure AD 帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="92d78-164">When you choose **My work or school owns it**, you sign in with an Azure AD account.</span></span> <span data-ttu-id="92d78-165">如果您的組織使用 Azure AD Premium 並已設定自動 mdm 註冊，HoloLens 會自動在 mdm 中註冊。</span><span class="sxs-lookup"><span data-stu-id="92d78-165">If your organization uses Azure AD Premium and has configured automatic MDM enrollment, HoloLens automatically enrolls in MDM.</span></span> <span data-ttu-id="92d78-166">如果您的組織未使用 Azure AD Premium，則無法使用自動 MDM 註冊。</span><span class="sxs-lookup"><span data-stu-id="92d78-166">If your organization does not use Azure AD Premium, automatic MDM enrollment isn't available.</span></span> <span data-ttu-id="92d78-167">在此情況下，您需要[在裝置管理中手動註冊 HoloLens](hololens-enroll-mdm.md#different-ways-to-enroll)。</span><span class="sxs-lookup"><span data-stu-id="92d78-167">In that case, you need to [manually enroll HoloLens in device management](hololens-enroll-mdm.md#different-ways-to-enroll).</span></span>

        1. <span data-ttu-id="92d78-168">輸入您的組織帳戶資訊。</span><span class="sxs-lookup"><span data-stu-id="92d78-168">Enter your organizational account information.</span></span>
        1. <span data-ttu-id="92d78-169">接受隱私權聲明與使用者授權合約。</span><span class="sxs-lookup"><span data-stu-id="92d78-169">Accept the privacy statement and the end user license agreement.</span></span>
        1. <span data-ttu-id="92d78-170">使用您的 Azure AD 認證登入。</span><span class="sxs-lookup"><span data-stu-id="92d78-170">Sign in by using your Azure AD credentials.</span></span> <span data-ttu-id="92d78-171">這可能會重新導向至您組織的登入頁面。</span><span class="sxs-lookup"><span data-stu-id="92d78-171">This may redirect to your organization's sign-in page.</span></span>
        1. <span data-ttu-id="92d78-172">繼續設定裝置。</span><span class="sxs-lookup"><span data-stu-id="92d78-172">Continue setting up the device.</span></span>

    - <span data-ttu-id="92d78-173">當您選擇 \[我擁有它\]，您可使用 Microsoft 帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="92d78-173">When you choose **I own it**, you sign in with a Microsoft account.</span></span> <span data-ttu-id="92d78-174">安裝完成之後，您可以[在裝置管理中手動註冊 HoloLens](hololens-enroll-mdm.md#different-ways-to-enroll)。</span><span class="sxs-lookup"><span data-stu-id="92d78-174">After setup is complete, you can [manually enroll HoloLens in device management](hololens-enroll-mdm.md#different-ways-to-enroll).</span></span>

        1. <span data-ttu-id="92d78-175">輸入您的 Microsoft 帳戶資訊。</span><span class="sxs-lookup"><span data-stu-id="92d78-175">Enter your Microsoft account information.</span></span>
        2. <span data-ttu-id="92d78-176">輸入您的密碼。</span><span class="sxs-lookup"><span data-stu-id="92d78-176">Enter your password.</span></span> <span data-ttu-id="92d78-177">如果您的 Microsoft 帳戶需要[兩步驟驗證 (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/)，請完成驗證程序。</span><span class="sxs-lookup"><span data-stu-id="92d78-177">If your Microsoft account requires [two-step verification (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/), complete the verification process.</span></span>

        
1. <span data-ttu-id="92d78-178">選取 **[下一步]** 以安裝鳶尾花登入。</span><span class="sxs-lookup"><span data-stu-id="92d78-178">Setup Iris sign-in by selecting **Next**.</span></span> <span data-ttu-id="92d78-179">您將會經歷類似的視覺校正體驗。</span><span class="sxs-lookup"><span data-stu-id="92d78-179">You will go through a similar experience to the eye calibration.</span></span> <span data-ttu-id="92d78-180">當掃描完成時，請選取 [ **完成** ]。</span><span class="sxs-lookup"><span data-stu-id="92d78-180">Select **Done** when the scan is complete.</span></span> <span data-ttu-id="92d78-181">您也可以選取 [ **略過** ] 略過此步驟。</span><span class="sxs-lookup"><span data-stu-id="92d78-181">You may also select **Skip** to bypass this step.</span></span>
    
    <span data-ttu-id="92d78-182">![鳶尾花安裝 ](images/setup-iris.png) ![ 鳶尾花安裝程式完成](images/iris-setup-complete.png)</span><span class="sxs-lookup"><span data-stu-id="92d78-182">![Iris setup](images/setup-iris.png) ![Iris setup completion](images/iris-setup-complete.png)</span></span> 
     
  
1. <span data-ttu-id="92d78-183">您將設定 PIN 以登入裝置。</span><span class="sxs-lookup"><span data-stu-id="92d78-183">You'll setup a PIN to log into the device.</span></span> <span data-ttu-id="92d78-184">此 PIN 是裝置特定的。</span><span class="sxs-lookup"><span data-stu-id="92d78-184">This PIN is device specific.</span></span> 

    ![安裝 Windows Hello](images/setup-windows-hello.png)

    ![設定 Windows Hello 釘選](images/windows-hello-pin.png)

    ![Windows Hello安裝成功](images/windows-hello-successful.png) 
    
1. <span data-ttu-id="92d78-188">選取是否要在 HoloLens 2 上啟用語音。</span><span class="sxs-lookup"><span data-stu-id="92d78-188">Select whether to enable speech on HoloLens 2.</span></span>

    ![啟用 Cortana](images/22-do-more-with-voice.png)

1. <span data-ttu-id="92d78-190">選取是否要在 HoloLens 2 上啟用位置。</span><span class="sxs-lookup"><span data-stu-id="92d78-190">Select whether to enable location on HoloLens 2.</span></span>
    
    ![啟用定位服務](images/setup-location-services.png)

1. <span data-ttu-id="92d78-192">選取您的遙測層級。</span><span class="sxs-lookup"><span data-stu-id="92d78-192">Select your telemetry level.</span></span> <span data-ttu-id="92d78-193">如果可以，請啟用選用的遙測。</span><span class="sxs-lookup"><span data-stu-id="92d78-193">If you can, please enable Optional telemetry.</span></span> <span data-ttu-id="92d78-194">這種資訊真的有助於 HoloLens 工程團隊。</span><span class="sxs-lookup"><span data-stu-id="92d78-194">This information really helps the HoloLens engineering team.</span></span>

     ![遙測層級](images/24-telemetry.png)

1. <span data-ttu-id="92d78-196">瞭解如何在 HoloLens 2 上使用開始手勢。</span><span class="sxs-lookup"><span data-stu-id="92d78-196">Learn how to use the start gesture on HoloLens 2.</span></span>

     ![瞭解如何使用開始手勢，圖1](images/26-01-startmenu-learning.png)

     ![瞭解如何使用開始手勢，圖2](images/26-02-startmenu-learning.png)

<span data-ttu-id="92d78-199">恭喜！</span><span class="sxs-lookup"><span data-stu-id="92d78-199">Congratulations!</span></span>  <span data-ttu-id="92d78-200">安裝程式已完成，而且您已準備好使用 HoloLens！</span><span class="sxs-lookup"><span data-stu-id="92d78-200">Setup is complete and you're ready to use HoloLens!</span></span>

## <a name="next-steps"></a><span data-ttu-id="92d78-201">下一步</span><span class="sxs-lookup"><span data-stu-id="92d78-201">Next steps</span></span>

1. <span data-ttu-id="92d78-202">立即開始與混合現實互動，並在您的 HoloLens 上流覽 Windows 10-查看 **提示** 應用程式，以取得實際操作教學課程進行手動互動。</span><span class="sxs-lookup"><span data-stu-id="92d78-202">Start interacting right away with Mixed Reality and navigating Windows 10 on your HoloLens - check out the **Tips** app for hands-on tutorials for hand interactions.</span></span> <span data-ttu-id="92d78-203">使用開始手勢移至 [開始] 或 [移至開始]，然後選取 [提示]。</span><span class="sxs-lookup"><span data-stu-id="92d78-203">Use the start gesture to go to Start or say "Go to Start" and select Tips.</span></span>

1. <span data-ttu-id="92d78-204">按一下下方以繼續閱讀有關 HoloLens 2 的資訊。</span><span class="sxs-lookup"><span data-stu-id="92d78-204">Click below to continue reading about getting around HoloLens 2.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="92d78-205">瀏覽 HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="92d78-205">Getting around HoloLens 2</span></span>](hololens2-basic-usage.md)
