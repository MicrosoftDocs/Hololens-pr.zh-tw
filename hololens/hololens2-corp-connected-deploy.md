---
title: 部署指南 – 使用 Dynamics 365 指南與公司連接的 HoloLens 2 - 部署
description: 瞭解如何使用 Dynamics 365 指南，在公司已連接網路上設定 HoloLens 2 裝置部署。
keywords: HoloLens，管理，公司關係，Dynamics 365 指南，AAD，Azure AD，MDM，行動裝置管理
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
ms.openlocfilehash: febf56f94a5cab623fd7ad08ae7abf7050224717
ms.sourcegitcommit: d7c86ccad7be32f7223d4b801083798454fda740
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/25/2021
ms.locfileid: "11448531"
---
# <a name="deploy---corporate-connected-guide"></a><span data-ttu-id="77b70-104">部署 - 公司關聯指南</span><span class="sxs-lookup"><span data-stu-id="77b70-104">Deploy - Corporate Connected Guide</span></span>

<span data-ttu-id="77b70-105">每一個部署的重要部分，就是先確定您的部署已正確設定，然後再自己測試，以確保使用者有順暢的體驗。</span><span class="sxs-lookup"><span data-stu-id="77b70-105">An important part of each deployment is ensuring that your deployment is properly set up before testing it yourself to ensure a smooth experience for the end user.</span></span>

<span data-ttu-id="77b70-106">由於我們正在透過 MDM 部署 Wi-Fi 憑證，因此我們一開始需要在開啟的 Wi-Fi 網路或不需要憑證的網路上設定 HoloLens 並註冊裝置。</span><span class="sxs-lookup"><span data-stu-id="77b70-106">Because we are deploying the Wi-Fi certificate via MDM, we'll need to initially set up HoloLens and enroll devices on an open Wi-Fi network, or a network that doesn't require the certificate.</span></span> <span data-ttu-id="77b70-107">一旦 HoloLens 完成 OOBE 和註冊，裝置就會收到先前所配置的網路憑證和 LOB，而且我們將能驗證裝置是否同時收到這兩者。</span><span class="sxs-lookup"><span data-stu-id="77b70-107">Once the HoloLens has finished OOBE and Enrolled, the device will receive the network certificate and LOB configured previously and we'll be able to validate both were received by the device.</span></span>

<span data-ttu-id="77b70-108">之後，您可以確認可以同時撰寫及操作測試指南。</span><span class="sxs-lookup"><span data-stu-id="77b70-108">Afterwards, you'll be able confirm you can both author and operate a test Guide.</span></span>

## <a name="enrollment-validation"></a><span data-ttu-id="77b70-109">註冊驗證</span><span class="sxs-lookup"><span data-stu-id="77b70-109">Enrollment Validation</span></span>

<span data-ttu-id="77b70-110">現在所有專案都為 Azure AD 和 MDM 註冊正確配置，剩下的應該就是快照。</span><span class="sxs-lookup"><span data-stu-id="77b70-110">Now that everything is properly configured for Azure AD and MDM Enrollment, the rest should now be a snap.</span></span> <span data-ttu-id="77b70-111">您需要一個Wi-Fi HoloLens 裝置，以及一個先前已配置的 Azure AD 使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="77b70-111">You'll need a Wi-Fi connection and the HoloLens device, and one of the previously configured Azure AD user accounts.</span></span>

<span data-ttu-id="77b70-112">如果您的裝置目前不是處於出廠設定狀態，現在是重新飛出 [裝置的時候](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device)。</span><span class="sxs-lookup"><span data-stu-id="77b70-112">If your device isn't currently sitting in a factory settings state, now would be a good time to [reflash the device](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device).</span></span>

1. <span data-ttu-id="77b70-113">一旦裝置在 OOBE 中，您必須開始互動，並遵循提示。</span><span class="sxs-lookup"><span data-stu-id="77b70-113">Once your device is in OOBE, you'll need to start interacting and following the prompts.</span></span>

2. <span data-ttu-id="77b70-114">連接到開啟Wi-Fi網路，而不需要憑證來加入 Wi-Fi。</span><span class="sxs-lookup"><span data-stu-id="77b70-114">Connect to an open Wi-Fi network that does not require certificates to join the Wi-Fi.</span></span> <span data-ttu-id="77b70-115">這可以讓裝置下載憑證，以在初始設定Wi-Fi使用。</span><span class="sxs-lookup"><span data-stu-id="77b70-115">This will allow the device to download the certificate to be used on the organization's Wi-Fi after initial setup.</span></span>

3. <span data-ttu-id="77b70-116">當系統詢問您這個**HoloLens**的擁有者時，會提示您重要提示嗎？</span><span class="sxs-lookup"><span data-stu-id="77b70-116">The critical prompt will be when you are asked **Who owns this HoloLens?**</span></span> <span data-ttu-id="77b70-117">選取 **我的公司或學校擁有** 它，然後輸入您的 Azure AD 帳號憑證。</span><span class="sxs-lookup"><span data-stu-id="77b70-117">Select **My work or school owns it** and enter your Azure AD account credentials.</span></span>

4. <span data-ttu-id="77b70-118">註冊成功時，系統會提示您設定 PIN。</span><span class="sxs-lookup"><span data-stu-id="77b70-118">When enrollment is successful, you'll be prompted to set up a PIN.</span></span> <span data-ttu-id="77b70-119">此 PIN 在此使用者裝置中是獨一無二的。</span><span class="sxs-lookup"><span data-stu-id="77b70-119">This PIN is unique to this device for this user.</span></span> <span data-ttu-id="77b70-120">系統也會提示您進行虹膜掃描、語音資料和遙測設定，最後，您將可以瞭解如何開啟開始功能表並完成 OOBE。</span><span class="sxs-lookup"><span data-stu-id="77b70-120">You will also be prompted for Iris scans, voice data, and telemetry settings and finally, you'll be able to learn how to open the start menu and complete OOBE.</span></span>

5. <span data-ttu-id="77b70-121">一旦登入混合實境首頁，使用您剛剛學會的開始手勢 **開啟開始功能表** 。</span><span class="sxs-lookup"><span data-stu-id="77b70-121">Once you land in the Mixed Reality Home, open the Start menu using the **Start gesture** you just learned.</span></span>

6. <span data-ttu-id="77b70-122">選取設定**應用程式\*\*\*\*，然後選取**系統 。</span><span class="sxs-lookup"><span data-stu-id="77b70-122">Select the **Settings** app and select **System**.</span></span> <span data-ttu-id="77b70-123">您會看到的第一個資訊是您的裝置名稱，而 HoloLens 2 裝置會為 &quot; HOLOLENS，後面接著 &quot; 六個字元字串。</span><span class="sxs-lookup"><span data-stu-id="77b70-123">The first piece of information you'll see is your Device name, which for your HoloLens 2 device will be &quot;HOLOLENS-&quot; followed by a six character string.</span></span>

7. <span data-ttu-id="77b70-124">記下這個名稱。</span><span class="sxs-lookup"><span data-stu-id="77b70-124">Take note of this name.</span></span>

    ![HoloLens 2 設定畫面](./images/hololens2-settings-about.jpg)

8. <span data-ttu-id="77b70-126">確認您的裝置已成功加入 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="77b70-126">Verify that your device is successfully joined to Azure AD.</span></span> <span data-ttu-id="77b70-127">有兩種方法;</span><span class="sxs-lookup"><span data-stu-id="77b70-127">There are two ways;</span></span>

    1.  <span data-ttu-id="77b70-128">設定應用程式。</span><span class="sxs-lookup"><span data-stu-id="77b70-128">The Settings app.</span></span> <span data-ttu-id="77b70-129">從**設定選取\*\*\*\*帳戶**  ->  **存取公司或學校**。</span><span class="sxs-lookup"><span data-stu-id="77b70-129">From **Settings** select **Accounts** -> **Access work or school**.</span></span> <span data-ttu-id="77b70-130">在此畫面中，您可以看到已連接到 Azure AD 中的 &quot; nameofAAD，&#39;註冊成功。</span><span class="sxs-lookup"><span data-stu-id="77b70-130">From this screen, you can verify you are successfully enrolled by seeing &quot;Connected to nameofAAD&#39;s Azure AD.</span></span> <span data-ttu-id="77b70-131">以 *yourusername@nameofAAD.onmicrosoft.com*連接。</span><span class="sxs-lookup"><span data-stu-id="77b70-131">Connected by *yourusername@nameofAAD.onmicrosoft.com*.</span></span> <span data-ttu-id="77b70-132">這會確認您的裝置已加入貴組織&#39;Azure AD。</span><span class="sxs-lookup"><span data-stu-id="77b70-132">This will verify your device is joined to your organization&#39;s Azure AD.</span></span>

    1. <span data-ttu-id="77b70-133">Azure [入口網站](https://portal.azure.com/#home)。</span><span class="sxs-lookup"><span data-stu-id="77b70-133">The [Azure portal](https://portal.azure.com/#home).</span></span> <span data-ttu-id="77b70-134">前往**Azure Active Directory**  ->  **Devices All**  ->  **devices**，然後搜尋裝置名稱。</span><span class="sxs-lookup"><span data-stu-id="77b70-134">Go to **Azure Active Directory** -> **Devices** -> **All devices**, and search the device name.</span></span> <span data-ttu-id="77b70-135">在加入類型下，會顯示為 'Azure AD 已加入'。</span><span class="sxs-lookup"><span data-stu-id="77b70-135">Under Join Type, it will show as being 'Azure AD Joined'.</span></span>
        ![在 Azure AD 中驗證加入類型](./images/hololens2-devices-all-devices.png)

9. <span data-ttu-id="77b70-137">確認您的裝置已註冊 MDM。</span><span class="sxs-lookup"><span data-stu-id="77b70-137">Verify that your device is enrolled with MDM.</span></span> <span data-ttu-id="77b70-138">有兩種方法;</span><span class="sxs-lookup"><span data-stu-id="77b70-138">There are two ways;</span></span>

    1. <span data-ttu-id="77b70-139">從**設定**中，選取**帳戶**  ->  **存取公司或學校**。</span><span class="sxs-lookup"><span data-stu-id="77b70-139">From **Settings**, select **Accounts** -> **Access work or school**.</span></span> <span data-ttu-id="77b70-140">在此畫面中，您可以看到已連接到 Azure AD 中的 &quot; nameofAAD，&#39;註冊成功。</span><span class="sxs-lookup"><span data-stu-id="77b70-140">From this screen, you can verify you are successfully enrolled by seeing &quot;Connected to nameofAAD&#39;s Azure AD.</span></span> <span data-ttu-id="77b70-141">以 *yourusername@nameofAAD.onmicrosoft.com*連接。</span><span class="sxs-lookup"><span data-stu-id="77b70-141">Connected by *yourusername@nameofAAD.onmicrosoft.com*.</span></span> <span data-ttu-id="77b70-142">從此 Access 公司或學校帳戶，選取 Azure AD&#39;&quot; nameofAAD。</span><span class="sxs-lookup"><span data-stu-id="77b70-142">From this Access work or school account by selecting &quot;Connected to nameofAAD&#39;s Azure AD.</span></span> <span data-ttu-id="77b70-143">以圖示 &quot; yourusername@nameofAAD.onmicrosoft.com，然後選取資訊按鈕\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="77b70-143">Connected by yourusername@nameofAAD.onmicrosoft.com&quot; and select the **Info** button.</span></span>

    1. <span data-ttu-id="77b70-144">[Microsoft 端點管理員系統管理中心](https://endpoint.microsoft.com/#home)。</span><span class="sxs-lookup"><span data-stu-id="77b70-144">[Microsoft Endpoint Manager Admin Center](https://endpoint.microsoft.com/#home).</span></span> <span data-ttu-id="77b70-145">登入並選取  **裝置**  ，然後選取  **所有裝置**。</span><span class="sxs-lookup"><span data-stu-id="77b70-145">Log in and select  **Devices**  then  **All devices**.</span></span> <span data-ttu-id="77b70-146">您可以在這裡搜尋 HoloLens 裝置&#39;名稱。</span><span class="sxs-lookup"><span data-stu-id="77b70-146">From here, you can search your HoloLens device&#39;s name.</span></span> <span data-ttu-id="77b70-147">您應該可以看到您的 HoloLens 列在 Intune 上。</span><span class="sxs-lookup"><span data-stu-id="77b70-147">You should be able to see your HoloLens listed on Intune.</span></span>

        ![在 Azure AD 中驗證由 Intune 管理](./images/hololens2-devices-all-devices2.png)


## <a name="wi-fi-certificate-validation"></a><span data-ttu-id="77b70-149">Wi-Fi憑證驗證</span><span class="sxs-lookup"><span data-stu-id="77b70-149">Wi-Fi certificate validation</span></span>

<span data-ttu-id="77b70-150">現在，裝置應該已經收到Wi-Fi憑證。</span><span class="sxs-lookup"><span data-stu-id="77b70-150">By now, the device should have received the Wi-Fi certificate.</span></span> <span data-ttu-id="77b70-151">您可以執行最簡單的驗證，就是嘗試Wi-Fi您收到憑證的&#39;連接。</span><span class="sxs-lookup"><span data-stu-id="77b70-151">The simplest validation you can do is attempt to connect to the Wi-Fi connection for which you&#39;ve received the certificate.</span></span> <span data-ttu-id="77b70-152">開啟設定**應用程式**，然後流覽至\*\* &amp; 網路網際網路\*\*  ->  **Wi-Fi，** 然後選取 Wi-Fi 連接。</span><span class="sxs-lookup"><span data-stu-id="77b70-152">Open up the **Settings** app and navigate to **Network &amp; Internet** -> **Wi-Fi** and select the Wi-fi connection.</span></span> <span data-ttu-id="77b70-153">連接之後，請開啟 Microsoft Edge 應用程式並確認您可以流覽至網站。</span><span class="sxs-lookup"><span data-stu-id="77b70-153">Once connected, open up the Microsoft Edge app and confirm you can navigate to a website.</span></span>

<span data-ttu-id="77b70-154">若要確認您已收到裝置上的憑證，您可以使用 [憑證管理員](https://docs.microsoft.com/hololens/certificate-manager)。</span><span class="sxs-lookup"><span data-stu-id="77b70-154">To confirm that you have received the certificate on the device, you can use the [Certificate Manager](https://docs.microsoft.com/hololens/certificate-manager).</span></span>

## <a name="validate-lob-app-install"></a><span data-ttu-id="77b70-155">驗證 LOB App 安裝</span><span class="sxs-lookup"><span data-stu-id="77b70-155">Validate LOB app install</span></span>

<span data-ttu-id="77b70-156">若要查看受管理 App 的安裝進度，您可以查看應用程式是否已安裝，或檢查設定。</span><span class="sxs-lookup"><span data-stu-id="77b70-156">To see a managed app's install progress, you either see if the app is installed or check Settings.</span></span> <span data-ttu-id="77b70-157">將 LOB 應用程式佈建為群組所需的安裝，在向指派群組中的使用者註冊 HoloLens 之後，應用程式會自動下載到 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="77b70-157">By configuring a LOB app as a required installation for our group, after enrolling the HoloLens with a user in the assigned group, the app will automatically download to the HoloLens.</span></span>

<span data-ttu-id="77b70-158">開啟開始功能表，然後選取所有 **應用程式**。</span><span class="sxs-lookup"><span data-stu-id="77b70-158">Open the Start menu and select **All apps**.</span></span> <span data-ttu-id="77b70-159">視您擁有的應用程式數量，您可能需要使用向上或向下**頁面按鈕。** \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="77b70-159">Depending on the number of apps you have, you may need to use the **page up** or **page down** buttons.</span></span>

<span data-ttu-id="77b70-160">若要驗證裝置上 App 的安裝，您可以透過設定帳戶\*\*\*\*  ->  \*\*\*\*  ->  \*\*存取\*\*\*\*\*\* 公司或學校執行此作業;選取帳戶，然後選取資訊按鈕，然後向下卷起以查看從 MDM 將不同的設定與應用程式所適用于裝置。</span><span class="sxs-lookup"><span data-stu-id="77b70-160">To validate the installation of the app on device, you can do so via **Settings** -> **Accounts** -> **Access work or school**; select the account then the **Info** button, and scroll down to see different configurations and apps applied to the device from MDM.</span></span>

<span data-ttu-id="77b70-161">若要驗證 Intune 的安裝，請流覽至[MEM](https://endpoint.microsoft.com/#home)入口網站  ->  **App** ->**所有應用程式**  -> *TheNameOfYourApp*  ->  **裝置安裝狀態**頁面。</span><span class="sxs-lookup"><span data-stu-id="77b70-161">To validate the install from Intune, navigate to the [MEM portal](https://endpoint.microsoft.com/#home) -> **Apps** -> All **apps** ->*TheNameOfYourApp* -> **Device install status** page.</span></span>

<span data-ttu-id="77b70-162">查看更多 [：HoloLens 的 Intune 應用程式部署](https://docs.microsoft.com/hololens/app-deploy-intune)</span><span class="sxs-lookup"><span data-stu-id="77b70-162">See more: [Intune App Deployment for HoloLens](https://docs.microsoft.com/hololens/app-deploy-intune)</span></span>

## <a name="validate-dynamics-365-guides"></a><span data-ttu-id="77b70-163">驗證 Dynamics 365 輔助線</span><span class="sxs-lookup"><span data-stu-id="77b70-163">Validate Dynamics 365 Guides</span></span>

<span data-ttu-id="77b70-164">HoloLens 上的指南應用程式有撰寫和操作模式。</span><span class="sxs-lookup"><span data-stu-id="77b70-164">There are modes for the Guides app on HoloLens, authoring and operating.</span></span> <span data-ttu-id="77b70-165">您需要先完成撰寫指南，再操作指南。</span><span class="sxs-lookup"><span data-stu-id="77b70-165">You'll need to finish authoring a guide before operating it.</span></span>

### <a name="authoring-the-guide"></a><span data-ttu-id="77b70-166">撰寫指南</span><span class="sxs-lookup"><span data-stu-id="77b70-166">Authoring the Guide</span></span>

<span data-ttu-id="77b70-167">我們不需要為此快速驗證執行太多工作。</span><span class="sxs-lookup"><span data-stu-id="77b70-167">We don't need to do much for this quick validation.</span></span> <span data-ttu-id="77b70-168">只要選取您電腦準備的指南。</span><span class="sxs-lookup"><span data-stu-id="77b70-168">Simply select the guide you prepared on your PC.</span></span> <span data-ttu-id="77b70-169">您需要錨定 [指南](https://docs.microsoft.comdynamics365/mixed-reality/guides/hololens-app-anchor)，才能快速驗證，才能使用全圖錨點。</span><span class="sxs-lookup"><span data-stu-id="77b70-169">You'll need to [anchor the guide](https://docs.microsoft.comdynamics365/mixed-reality/guides/hololens-app-anchor), for a quick validation you can use a holographic anchor.</span></span> <span data-ttu-id="77b70-170">之後，您應該 [放置您的步驟和模型](https://docs.microsoft.com/dynamics365/mixed-reality/guides/hololens-app-orientation)。</span><span class="sxs-lookup"><span data-stu-id="77b70-170">Afterwards, you should [place your steps and models](https://docs.microsoft.com/dynamics365/mixed-reality/guides/hololens-app-orientation).</span></span>

>[!NOTE]
> <span data-ttu-id="77b70-171">您需要作者 **角色** 才能登入 HoloLens 上的電腦和作者。</span><span class="sxs-lookup"><span data-stu-id="77b70-171">You will need the **Authoring** role to login to the PC and author on the HoloLens.</span></span> <span data-ttu-id="77b70-172">運算子角色為唯讀，且無法存取 PC 應用程式。</span><span class="sxs-lookup"><span data-stu-id="77b70-172">The Operator role is read-only and has no access to the PC app.</span></span>

<iframe width="560" height="315" src="https://www.youtube.com/embed/poE7s7_zWDE" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="operating-the-guide"></a><span data-ttu-id="77b70-173">操作指南</span><span class="sxs-lookup"><span data-stu-id="77b70-173">Operating the Guide</span></span>

<span data-ttu-id="77b70-174">一旦全能圖就位後，您可以測試操作指南。</span><span class="sxs-lookup"><span data-stu-id="77b70-174">Once your holograms are in place, you can test out operating your guide.</span></span> 
- <span data-ttu-id="77b70-175">選取 **運算子模式**</span><span class="sxs-lookup"><span data-stu-id="77b70-175">Select **Operator mode**</span></span>
- <span data-ttu-id="77b70-176">按一下指南的步驟。</span><span class="sxs-lookup"><span data-stu-id="77b70-176">Click through the steps of your guide.</span></span>

<span data-ttu-id="77b70-177">若要深入瞭解如何操作指南，請查看以下資源：</span><span class="sxs-lookup"><span data-stu-id="77b70-177">For more in-depth guidance on how to operate a guide, check out these resources:</span></span>

[<span data-ttu-id="77b70-178">在 Dynamics 365 指南中操作指南概觀</span><span class="sxs-lookup"><span data-stu-id="77b70-178">Overview of operating a guide in Dynamics 365 Guides</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/guides/operator-overview)

[<span data-ttu-id="77b70-179">以 Dynamics 365 輔助線中的運算子使用步驟卡片進行導向</span><span class="sxs-lookup"><span data-stu-id="77b70-179">Get oriented with the Step card as an operator in Dynamics 365 Guides</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/guides/operator-step-card-orientation)

<iframe width="560" height="315" src="https://www.youtube.com/embed/9s41BKGHVL8" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="next-step"></a><span data-ttu-id="77b70-180">下一步</span><span class="sxs-lookup"><span data-stu-id="77b70-180">Next step</span></span> 
> [!div class="nextstepaction"]
> [<span data-ttu-id="77b70-181">公司連接部署 - 維護</span><span class="sxs-lookup"><span data-stu-id="77b70-181">Corporate connected deployment - Maintain</span></span>](hololens2-corp-connected-maintain.md)
