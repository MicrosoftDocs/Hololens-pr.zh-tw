---
title: 部署指南-Dynamics 365 Guides-部署的公司連線 HoloLens 2
description: 瞭解如何使用 Dynamics 365 Guides 透過公司連線網路設定 HoloLens 2 裝置的部署。
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
ms.openlocfilehash: 6407517bca9efd02fdaf45a78cba7a215ec05670
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "113637058"
---
# <a name="deploy---corporate-connected-guide"></a><span data-ttu-id="933fc-104">部署-公司連接指南</span><span class="sxs-lookup"><span data-stu-id="933fc-104">Deploy - Corporate Connected Guide</span></span>

<span data-ttu-id="933fc-105">每個部署的重要部分是確保您的部署在自行測試之前已正確設定，以確保使用者能順暢地體驗。</span><span class="sxs-lookup"><span data-stu-id="933fc-105">An important part of each deployment is ensuring that your deployment is properly set up before testing it yourself to ensure a smooth experience for the end user.</span></span>

<span data-ttu-id="933fc-106">由於我們是透過 MDM 部署 Wi-Fi 憑證，因此我們必須先在開啟的 Wi-Fi 網路或不需要憑證的網路上設定 HoloLens 和註冊裝置。</span><span class="sxs-lookup"><span data-stu-id="933fc-106">Because we are deploying the Wi-Fi certificate via MDM, we'll need to initially set up HoloLens and enroll devices on an open Wi-Fi network, or a network that doesn't require the certificate.</span></span> <span data-ttu-id="933fc-107">一旦 HoloLens 完成 OOBE 並註冊之後，裝置將會接收先前設定的網路憑證和 LOB，而且我們將能夠驗證這兩者都是由裝置所接收。</span><span class="sxs-lookup"><span data-stu-id="933fc-107">Once the HoloLens has finished OOBE and Enrolled, the device will receive the network certificate and LOB configured previously and we'll be able to validate both were received by the device.</span></span>

<span data-ttu-id="933fc-108">之後，您將能夠確認是否可以撰寫和操作測試指南。</span><span class="sxs-lookup"><span data-stu-id="933fc-108">Afterwards, you'll be able confirm you can both author and operate a test Guide.</span></span>

## <a name="enrollment-validation"></a><span data-ttu-id="933fc-109">註冊驗證</span><span class="sxs-lookup"><span data-stu-id="933fc-109">Enrollment Validation</span></span>

<span data-ttu-id="933fc-110">現在所有專案都已針對 Azure AD 和 MDM 註冊正確設定，接下來應該是貼齊。</span><span class="sxs-lookup"><span data-stu-id="933fc-110">Now that everything is properly configured for Azure AD and MDM Enrollment, the rest should now be a snap.</span></span> <span data-ttu-id="933fc-111">您將需要 Wi-Fi 連接和 HoloLens 裝置，以及先前設定的 Azure AD 使用者帳戶之一。</span><span class="sxs-lookup"><span data-stu-id="933fc-111">You'll need a Wi-Fi connection and the HoloLens device, and one of the previously configured Azure AD user accounts.</span></span>

<span data-ttu-id="933fc-112">如果您的裝置目前未處於原廠設定狀態，現在是 [重新刷新裝置](/hololens/hololens-recovery#clean-reflash-the-device)的好時機。</span><span class="sxs-lookup"><span data-stu-id="933fc-112">If your device isn't currently sitting in a factory settings state, now would be a good time to [reflash the device](/hololens/hololens-recovery#clean-reflash-the-device).</span></span>

1. <span data-ttu-id="933fc-113">當您的裝置在 OOBE 之後，您必須開始互動並遵循提示。</span><span class="sxs-lookup"><span data-stu-id="933fc-113">Once your device is in OOBE, you'll need to start interacting and following the prompts.</span></span>

2. <span data-ttu-id="933fc-114">連線至不需要憑證來加入 Wi-fi 的開啟 Wi-Fi 網路。</span><span class="sxs-lookup"><span data-stu-id="933fc-114">Connect to an open Wi-Fi network that does not require certificates to join the Wi-Fi.</span></span> <span data-ttu-id="933fc-115">這可讓裝置下載憑證，以便在初始安裝之後用於組織的 Wi-Fi。</span><span class="sxs-lookup"><span data-stu-id="933fc-115">This will allow the device to download the certificate to be used on the organization's Wi-Fi after initial setup.</span></span>

3. <span data-ttu-id="933fc-116">當系統詢問您 **神秘擁有此 HoloLens** 時，關鍵提示會是什麼？</span><span class="sxs-lookup"><span data-stu-id="933fc-116">The critical prompt will be when you are asked **Who owns this HoloLens?**</span></span> <span data-ttu-id="933fc-117">選取 [ **我的工作或學校擁有** ]，然後輸入您的 Azure AD 帳號憑證。</span><span class="sxs-lookup"><span data-stu-id="933fc-117">Select **My work or school owns it** and enter your Azure AD account credentials.</span></span>

4. <span data-ttu-id="933fc-118">註冊成功時，系統會提示您設定 PIN。</span><span class="sxs-lookup"><span data-stu-id="933fc-118">When enrollment is successful, you'll be prompted to set up a PIN.</span></span> <span data-ttu-id="933fc-119">這是此使用者對此裝置而言唯一的 PIN。</span><span class="sxs-lookup"><span data-stu-id="933fc-119">This PIN is unique to this device for this user.</span></span> <span data-ttu-id="933fc-120">系統也會提示您輸入鳶尾花掃描、語音資料和遙測設定，最後您將能夠學習如何開啟 [開始] 功能表並完成 OOBE。</span><span class="sxs-lookup"><span data-stu-id="933fc-120">You will also be prompted for Iris scans, voice data, and telemetry settings and finally, you'll be able to learn how to open the start menu and complete OOBE.</span></span>

5. <span data-ttu-id="933fc-121">當您進入混合現實首頁之後，請使用您剛剛學到的 **開始手勢** 來開啟 [開始] 功能表。</span><span class="sxs-lookup"><span data-stu-id="933fc-121">Once you land in the Mixed Reality Home, open the Start menu using the **Start gesture** you just learned.</span></span>

6. <span data-ttu-id="933fc-122">選取 **設定** 應用程式，然後選取 [**系統**]。</span><span class="sxs-lookup"><span data-stu-id="933fc-122">Select the **Settings** app and select **System**.</span></span> <span data-ttu-id="933fc-123">您將會看到的第一項資訊是您的裝置名稱，而您的 HoloLens 2 裝置將會是 &quot; HoloLens， &quot; 後面接著6個字元的字串。</span><span class="sxs-lookup"><span data-stu-id="933fc-123">The first piece of information you'll see is your Device name, which for your HoloLens 2 device will be &quot;HOLOLENS-&quot; followed by a six character string.</span></span>

7. <span data-ttu-id="933fc-124">記下此名稱。</span><span class="sxs-lookup"><span data-stu-id="933fc-124">Take note of this name.</span></span>

    ![HoloLens 2 設定畫面](./images/hololens2-settings-about.jpg)

8. <span data-ttu-id="933fc-126">確認您的裝置已成功聯結至 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="933fc-126">Verify that your device is successfully joined to Azure AD.</span></span> <span data-ttu-id="933fc-127">有兩種方式：</span><span class="sxs-lookup"><span data-stu-id="933fc-127">There are two ways;</span></span>

    1.  <span data-ttu-id="933fc-128">設定應用程式。</span><span class="sxs-lookup"><span data-stu-id="933fc-128">The Settings app.</span></span> <span data-ttu-id="933fc-129">從 **設定** 選取[  ->  **存取公司或學校** 帳戶]。</span><span class="sxs-lookup"><span data-stu-id="933fc-129">From **Settings** select **Accounts** -> **Access work or school**.</span></span> <span data-ttu-id="933fc-130">在此畫面中，您可以看到 &quot; 連線到 nameofAAD&#39;s Azure AD，以確認您已成功註冊。</span><span class="sxs-lookup"><span data-stu-id="933fc-130">From this screen, you can verify you are successfully enrolled by seeing &quot;Connected to nameofAAD&#39;s Azure AD.</span></span> <span data-ttu-id="933fc-131">連接者 *yourusername@nameofAAD.onmicrosoft.com* 。</span><span class="sxs-lookup"><span data-stu-id="933fc-131">Connected by *yourusername@nameofAAD.onmicrosoft.com*.</span></span> <span data-ttu-id="933fc-132">這會確認您的裝置已加入您的組織&#39;s Azure AD。</span><span class="sxs-lookup"><span data-stu-id="933fc-132">This will verify your device is joined to your organization&#39;s Azure AD.</span></span>

    1. <span data-ttu-id="933fc-133">[Azure 入口網站](https://portal.azure.com/#home)。</span><span class="sxs-lookup"><span data-stu-id="933fc-133">The [Azure portal](https://portal.azure.com/#home).</span></span> <span data-ttu-id="933fc-134">移至 **Azure Active Directory**  ->  **裝置**  ->  **所有裝置**]，並搜尋裝置名稱。</span><span class="sxs-lookup"><span data-stu-id="933fc-134">Go to **Azure Active Directory** -> **Devices** -> **All devices**, and search the device name.</span></span> <span data-ttu-id="933fc-135">在 [聯結類型] 下，它會顯示為「Azure AD 聯結」。</span><span class="sxs-lookup"><span data-stu-id="933fc-135">Under Join Type, it will show as being 'Azure AD Joined'.</span></span>
        <span data-ttu-id="933fc-136">![確認 Azure AD 中的聯結類型](./images/hololens2-devices-all-devices.png)</span><span class="sxs-lookup"><span data-stu-id="933fc-136">![Verify Join Type in Azure AD](./images/hololens2-devices-all-devices.png)</span></span>

9. <span data-ttu-id="933fc-137">確認您的裝置已向 MDM 註冊。</span><span class="sxs-lookup"><span data-stu-id="933fc-137">Verify that your device is enrolled with MDM.</span></span> <span data-ttu-id="933fc-138">有兩種方式：</span><span class="sxs-lookup"><span data-stu-id="933fc-138">There are two ways;</span></span>

    1. <span data-ttu-id="933fc-139">從 **設定** 選取 [**帳戶**  ->  **存取公司或學校** 帳戶]。</span><span class="sxs-lookup"><span data-stu-id="933fc-139">From **Settings**, select **Accounts** -> **Access work or school**.</span></span> <span data-ttu-id="933fc-140">在此畫面中，您可以看到 &quot; 連線到 nameofAAD&#39;s Azure AD，以確認您已成功註冊。</span><span class="sxs-lookup"><span data-stu-id="933fc-140">From this screen, you can verify you are successfully enrolled by seeing &quot;Connected to nameofAAD&#39;s Azure AD.</span></span> <span data-ttu-id="933fc-141">連接者 *yourusername@nameofAAD.onmicrosoft.com* 。</span><span class="sxs-lookup"><span data-stu-id="933fc-141">Connected by *yourusername@nameofAAD.onmicrosoft.com*.</span></span> <span data-ttu-id="933fc-142">藉由選取 [ &quot; 連線到 nameofAAD&#39;s] Azure AD，從此存取工作或學校帳戶。</span><span class="sxs-lookup"><span data-stu-id="933fc-142">From this Access work or school account by selecting &quot;Connected to nameofAAD&#39;s Azure AD.</span></span> <span data-ttu-id="933fc-143">連接者 yourusername@nameofAAD.onmicrosoft.com &quot; ，然後選取 [**資訊**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="933fc-143">Connected by yourusername@nameofAAD.onmicrosoft.com&quot; and select the **Info** button.</span></span>

    1. <span data-ttu-id="933fc-144">[Microsoft 端點管理員系統管理中心](https://endpoint.microsoft.com/#home)。</span><span class="sxs-lookup"><span data-stu-id="933fc-144">[Microsoft Endpoint Manager Admin Center](https://endpoint.microsoft.com/#home).</span></span> <span data-ttu-id="933fc-145">登入並選取 [  **裝置**  ]，然後選取 [  **所有裝置**]。</span><span class="sxs-lookup"><span data-stu-id="933fc-145">Log in and select  **Devices**  then  **All devices**.</span></span> <span data-ttu-id="933fc-146">您可以從這裡搜尋 HoloLens 裝置&#39;的名稱。</span><span class="sxs-lookup"><span data-stu-id="933fc-146">From here, you can search your HoloLens device&#39;s name.</span></span> <span data-ttu-id="933fc-147">您應該能夠看到您的 HoloLens 列在 Intune 上。</span><span class="sxs-lookup"><span data-stu-id="933fc-147">You should be able to see your HoloLens listed on Intune.</span></span>

        ![確認 Azure AD 中的 Intune 管理](./images/hololens2-devices-all-devices2.png)


## <a name="wi-fi-certificate-validation"></a><span data-ttu-id="933fc-149">Wi-Fi 憑證驗證</span><span class="sxs-lookup"><span data-stu-id="933fc-149">Wi-Fi certificate validation</span></span>

<span data-ttu-id="933fc-150">現在，裝置應該已收到 Wi-Fi 憑證。</span><span class="sxs-lookup"><span data-stu-id="933fc-150">By now, the device should have received the Wi-Fi certificate.</span></span> <span data-ttu-id="933fc-151">您可以進行的最簡單驗證是嘗試連接到您&#39;已收到憑證的 Wi-Fi 連接。</span><span class="sxs-lookup"><span data-stu-id="933fc-151">The simplest validation you can do is attempt to connect to the Wi-Fi connection for which you&#39;ve received the certificate.</span></span> <span data-ttu-id="933fc-152">開啟 **設定** 的應用程式，並流覽至 **Network &amp; Internet**  ->  **wi-fi** ，然後選取 wi-fi 連線。</span><span class="sxs-lookup"><span data-stu-id="933fc-152">Open up the **Settings** app and navigate to **Network &amp; Internet** -> **Wi-Fi** and select the Wi-fi connection.</span></span> <span data-ttu-id="933fc-153">連接之後，開啟 Microsoft Edge 應用程式，並確認您可以流覽至網站。</span><span class="sxs-lookup"><span data-stu-id="933fc-153">Once connected, open up the Microsoft Edge app and confirm you can navigate to a website.</span></span>

<span data-ttu-id="933fc-154">若要確認您已在裝置上收到憑證，您可以使用 [ [憑證管理員](/hololens/certificate-manager)]。</span><span class="sxs-lookup"><span data-stu-id="933fc-154">To confirm that you have received the certificate on the device, you can use the [Certificate Manager](/hololens/certificate-manager).</span></span>

## <a name="validate-lob-app-install"></a><span data-ttu-id="933fc-155">驗證 LOB 應用程式安裝</span><span class="sxs-lookup"><span data-stu-id="933fc-155">Validate LOB app install</span></span>

<span data-ttu-id="933fc-156">若要查看受管理應用程式的安裝進度，您可以查看應用程式是否已安裝，或檢查設定。</span><span class="sxs-lookup"><span data-stu-id="933fc-156">To see a managed app's install progress, you either see if the app is installed or check Settings.</span></span> <span data-ttu-id="933fc-157">藉由將 LOB 應用程式設定為群組的必要安裝，在向已指派群組中的使用者註冊 HoloLens 之後，應用程式會自動下載到 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="933fc-157">By configuring a LOB app as a required installation for our group, after enrolling the HoloLens with a user in the assigned group, the app will automatically download to the HoloLens.</span></span>

<span data-ttu-id="933fc-158">開啟 [開始] 功能表，然後選取 [**所有應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="933fc-158">Open the Start menu and select **All apps**.</span></span> <span data-ttu-id="933fc-159">視您擁有的應用程式數目而定，您可能需要使用 **page up** 或 **page down** 按鈕。</span><span class="sxs-lookup"><span data-stu-id="933fc-159">Depending on the number of apps you have, you may need to use the **page up** or **page down** buttons.</span></span>

<span data-ttu-id="933fc-160">若要在裝置上驗證應用程式的安裝，您可以透過 **設定**  ->  **帳戶**  ->  **存取公司或學校** 帳戶; 選取帳戶，然後選取 [**資訊**] 按鈕，然後向下滾動查看從 MDM 套用至裝置的不同設定和應用程式。</span><span class="sxs-lookup"><span data-stu-id="933fc-160">To validate the installation of the app on device, you can do so via **Settings** -> **Accounts** -> **Access work or school**; select the account then the **Info** button, and scroll down to see different configurations and apps applied to the device from MDM.</span></span>

<span data-ttu-id="933fc-161">若要從 Intune 驗證安裝，請流覽至 [[記憶體入口網站](https://endpoint.microsoft.com/#home)  ->  **應用程式**-> 所有 **應用程式**  -> *TheNameOfYourApp*  ->  **裝置安裝狀態**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="933fc-161">To validate the install from Intune, navigate to the [MEM portal](https://endpoint.microsoft.com/#home) -> **Apps** -> All **apps** ->*TheNameOfYourApp* -> **Device install status** page.</span></span>

<span data-ttu-id="933fc-162">查看更多： [HoloLens 的 Intune 應用程式部署](/hololens/app-deploy-intune)</span><span class="sxs-lookup"><span data-stu-id="933fc-162">See more: [Intune App Deployment for HoloLens](/hololens/app-deploy-intune)</span></span>

## <a name="validate-dynamics-365-guides"></a><span data-ttu-id="933fc-163">驗證 Dynamics 365 Guides</span><span class="sxs-lookup"><span data-stu-id="933fc-163">Validate Dynamics 365 Guides</span></span>

<span data-ttu-id="933fc-164">在 HoloLens、撰寫和操作時，有一些模式可供輔助線應用程式。</span><span class="sxs-lookup"><span data-stu-id="933fc-164">There are modes for the Guides app on HoloLens, authoring and operating.</span></span> <span data-ttu-id="933fc-165">在操作之前，您必須先完成撰寫指南。</span><span class="sxs-lookup"><span data-stu-id="933fc-165">You'll need to finish authoring a guide before operating it.</span></span>

### <a name="authoring-the-guide"></a><span data-ttu-id="933fc-166">撰寫指南</span><span class="sxs-lookup"><span data-stu-id="933fc-166">Authoring the Guide</span></span>

<span data-ttu-id="933fc-167">這種快速驗證不需要這麼做。</span><span class="sxs-lookup"><span data-stu-id="933fc-167">We don't need to do much for this quick validation.</span></span> <span data-ttu-id="933fc-168">只要選取您在電腦上準備的指南。</span><span class="sxs-lookup"><span data-stu-id="933fc-168">Simply select the guide you prepared on your PC.</span></span> <span data-ttu-id="933fc-169">您將需要 [錨定節目表](/dynamics365/mixed-reality/guides/hololens-app-anchor)，以快速驗證您可以使用全息的錨點。</span><span class="sxs-lookup"><span data-stu-id="933fc-169">You'll need to [anchor the guide](/dynamics365/mixed-reality/guides/hololens-app-anchor), for a quick validation you can use a holographic anchor.</span></span> <span data-ttu-id="933fc-170">之後，您應該 [放置步驟和模型](/dynamics365/mixed-reality/guides/hololens-app-orientation)。</span><span class="sxs-lookup"><span data-stu-id="933fc-170">Afterwards, you should [place your steps and models](/dynamics365/mixed-reality/guides/hololens-app-orientation).</span></span>

>[!NOTE]
> <span data-ttu-id="933fc-171">您將需要 **撰寫** 角色才能登入電腦，並在 HoloLens 上撰寫。</span><span class="sxs-lookup"><span data-stu-id="933fc-171">You will need the **Authoring** role to login to the PC and author on the HoloLens.</span></span> <span data-ttu-id="933fc-172">操作員角色是唯讀的，而且沒有電腦應用程式的存取權。</span><span class="sxs-lookup"><span data-stu-id="933fc-172">The Operator role is read-only and has no access to the PC app.</span></span>

<iframe width="560" height="315" src="https://www.youtube.com/embed/poE7s7_zWDE" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="operating-the-guide"></a><span data-ttu-id="933fc-173">操作指南</span><span class="sxs-lookup"><span data-stu-id="933fc-173">Operating the Guide</span></span>

<span data-ttu-id="933fc-174">在您的全像地方之後，您可以測試您的指南。</span><span class="sxs-lookup"><span data-stu-id="933fc-174">Once your holograms are in place, you can test out operating your guide.</span></span> 
- <span data-ttu-id="933fc-175">選取 **運算子模式**</span><span class="sxs-lookup"><span data-stu-id="933fc-175">Select **Operator mode**</span></span>
- <span data-ttu-id="933fc-176">按一下指南的步驟。</span><span class="sxs-lookup"><span data-stu-id="933fc-176">Click through the steps of your guide.</span></span>

<span data-ttu-id="933fc-177">如需有關如何操作指南的更深入指引，請參閱下列資源：</span><span class="sxs-lookup"><span data-stu-id="933fc-177">For more in-depth guidance on how to operate a guide, check out these resources:</span></span>

[<span data-ttu-id="933fc-178">Dynamics 365 Guides 的操作指南簡介</span><span class="sxs-lookup"><span data-stu-id="933fc-178">Overview of operating a guide in Dynamics 365 Guides</span></span>](/dynamics365/mixed-reality/guides/operator-overview)

[<span data-ttu-id="933fc-179">以 Dynamics 365 Guides 中的運算子的形式取得步驟卡導向</span><span class="sxs-lookup"><span data-stu-id="933fc-179">Get oriented with the Step card as an operator in Dynamics 365 Guides</span></span>](/dynamics365/mixed-reality/guides/operator-step-card-orientation)

<iframe width="560" height="315" src="https://www.youtube.com/embed/9s41BKGHVL8" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="next-step"></a><span data-ttu-id="933fc-180">後續步驟</span><span class="sxs-lookup"><span data-stu-id="933fc-180">Next step</span></span> 
> [!div class="nextstepaction"]
> [<span data-ttu-id="933fc-181">企業連線部署-維護</span><span class="sxs-lookup"><span data-stu-id="933fc-181">Corporate connected deployment - Maintain</span></span>](hololens2-corp-connected-maintain.md)
