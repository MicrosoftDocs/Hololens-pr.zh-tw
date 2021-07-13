---
title: 部署指南–雲端連線 HoloLens 2 大規模部署與遠端協助-部署
description: 瞭解如何透過雲端連線的網路，驗證 HoloLens 裝置的註冊和遠端協助。
keywords: HoloLens、管理、雲端連線、遠端協助、AAD、Azure AD、MDM、Mobile 裝置管理
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.date: 12/04/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: b0597806d58d7bf16fe6f6c766af3f9662fca7e6
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635172"
---
# <a name="deploy---cloud-connected-guide"></a><span data-ttu-id="79a81-104">部署-雲端連線指南</span><span class="sxs-lookup"><span data-stu-id="79a81-104">Deploy - Cloud connected Guide</span></span>

<span data-ttu-id="79a81-105">現在您已設定好所有專案，您應該已準備好散發裝置。</span><span class="sxs-lookup"><span data-stu-id="79a81-105">Now that you have everything configured you should be ready to distribute devices.</span></span> <span data-ttu-id="79a81-106">不過，現在您應該先驗證您的設定。</span><span class="sxs-lookup"><span data-stu-id="79a81-106">However, now is when you should first validate your setup.</span></span> <span data-ttu-id="79a81-107">首先，請先驗證 Azure AD 聯結和 MDM 註冊程式，然後確認是否可以放置遠端協助通話。</span><span class="sxs-lookup"><span data-stu-id="79a81-107">First the Azure AD Join and MDM Enrollment process should be validated, followed by verifying that a Remote Assist call can be placed.</span></span>

## <a name="enrollment-validation"></a><span data-ttu-id="79a81-108">註冊驗證</span><span class="sxs-lookup"><span data-stu-id="79a81-108">Enrollment Validation</span></span>

<span data-ttu-id="79a81-109">現在所有專案都已針對 Azure AD 和 MDM 註冊正確設定，接下來應該是貼齊。</span><span class="sxs-lookup"><span data-stu-id="79a81-109">Now that everything is properly configured for Azure AD and MDM Enrollment, the rest should now be a snap.</span></span> <span data-ttu-id="79a81-110">您&#39;需要 Wi-Fi 連線和 HoloLens 裝置，以及先前設定的其中一個 AAD 使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="79a81-110">You&#39;ll need a Wi-Fi connection and the HoloLens device, as well as one of the previously configured AAD user accounts.</span></span>

<span data-ttu-id="79a81-111">如果您的裝置目前未處於原廠設定狀態&#39;t，現在是 [重新刷新裝置](/hololens/hololens-recovery#clean-reflash-the-device)的好時機。</span><span class="sxs-lookup"><span data-stu-id="79a81-111">If your device isn&#39;t currently sitting in a factory settings state, now would be a good time to [reflash the device](/hololens/hololens-recovery#clean-reflash-the-device).</span></span>

1. <span data-ttu-id="79a81-112">當您的裝置在 OOBE 之後，您&#39;需要開始互動並遵循提示。</span><span class="sxs-lookup"><span data-stu-id="79a81-112">Once your device is in OOBE, you&#39;ll need to start interacting and following the prompts.</span></span> 
1. <span data-ttu-id="79a81-113">當系統詢問您 **神秘擁有此 HoloLens** 時，關鍵提示會是什麼？</span><span class="sxs-lookup"><span data-stu-id="79a81-113">The critical prompt will be when you are asked **Who owns this HoloLens?**</span></span> <span data-ttu-id="79a81-114">選取 [ **我的工作或學校擁有** ]，然後輸入您的 Azure AD 帳號憑證。</span><span class="sxs-lookup"><span data-stu-id="79a81-114">Select **My work or school owns it** and enter your Azure AD account credentials.</span></span>
1. <span data-ttu-id="79a81-115">註冊成功時，系統會提示您&#39;設定 PIN。</span><span class="sxs-lookup"><span data-stu-id="79a81-115">When enrollment is successful, you&#39;ll be prompted to set up a PIN.</span></span> <span data-ttu-id="79a81-116">這是此使用者對此裝置而言唯一的 PIN。</span><span class="sxs-lookup"><span data-stu-id="79a81-116">This PIN is unique to this device for this user.</span></span> <span data-ttu-id="79a81-117">系統也會提示您輸入鳶尾花掃描、語音資料和遙測設定，最後您&#39;將能夠學習如何開啟 [開始] 功能表並完成 OOBE。</span><span class="sxs-lookup"><span data-stu-id="79a81-117">You will also be prompted for Iris scans, voice data, and telemetry settings and finally, you&#39;ll be able to learn how to open the start menu and complete OOBE.</span></span>
1. <span data-ttu-id="79a81-118">當您進入混合現實首頁之後，請使用您剛剛學到的 **開始手勢** 來開啟 [開始] 功能表。</span><span class="sxs-lookup"><span data-stu-id="79a81-118">Once you land in the Mixed Reality Home open the Start menu using the **Start gesture** you just learned.</span></span>
1. <span data-ttu-id="79a81-119">選取 **設定** 應用程式，然後選取 [**系統]。**</span><span class="sxs-lookup"><span data-stu-id="79a81-119">Select the **Settings** app and select **System.**</span></span> <span data-ttu-id="79a81-120">您&#39;會看到的第一項資訊是您的裝置名稱，而您的 HoloLens 2 裝置將會是 &quot; HoloLens， &quot; 後面接著6個字元的字串。</span><span class="sxs-lookup"><span data-stu-id="79a81-120">The first piece of information you&#39;ll see is your Device name, which for your HoloLens 2 device will be &quot;HOLOLENS-&quot; followed by a six character string.</span></span>
1. <span data-ttu-id="79a81-121">記下此名稱。</span><span class="sxs-lookup"><span data-stu-id="79a81-121">Take note of this name.</span></span>

![HoloLens 2 設定-關於](./images/hololens2-settings-about.jpg)

7. <span data-ttu-id="79a81-123">您可以確認裝置已成功註冊在設定應用程式內的 Azure AD 中。</span><span class="sxs-lookup"><span data-stu-id="79a81-123">You can verify that your device is successfully enrolled in the Azure AD within the Settings app.</span></span> <span data-ttu-id="79a81-124">從 **設定** 選取[  ->  **存取公司或學校** 帳戶]。</span><span class="sxs-lookup"><span data-stu-id="79a81-124">From **Settings** select **Accounts** -> **Access work or school**.</span></span> <span data-ttu-id="79a81-125">在此畫面中，您可以看到 &quot; 連線到 _nameofAAD_&#39;s Azure AD，以確認您已成功註冊。</span><span class="sxs-lookup"><span data-stu-id="79a81-125">From this screen you can verify you are successfully enrolled by seeing &quot;Connected to _nameofAAD_&#39;s Azure AD.</span></span> <span data-ttu-id="79a81-126">由 _」_ @ _nameofAAD_. onmicrosoft.com 連接 &quot; 。</span><span class="sxs-lookup"><span data-stu-id="79a81-126">Connected by _yourusername_@_nameofAAD_.onmicrosoft.com&quot;.</span></span>


<span data-ttu-id="79a81-127">若要驗證裝置已 Azure AD 加入，我們可以從 [Azure 入口網站](https://portal.azure.com/#home)  ->  **Azure Active Directory**  ->  **裝置**  ->  **所有裝置** 檢查 Azure Active Directory，然後搜尋裝置名稱。</span><span class="sxs-lookup"><span data-stu-id="79a81-127">To validate the device has Azure AD Joined we can check the Azure Active Directory from the [Azure portal](https://portal.azure.com/#home) -> **Azure Active Directory** -> **Devices** -> **All devices**, and search the device name.</span></span> <span data-ttu-id="79a81-128">您&#39;可以看到裝置是 Azure Active Directory 的一部分。</span><span class="sxs-lookup"><span data-stu-id="79a81-128">You&#39;ll be able to see the device is a part of the Azure Active Directory.</span></span>


![Azure Active Directory-裝置](./images/aad-enrollment.png)

<span data-ttu-id="79a81-130">接下來您&#39;需要登入 Microsoft 端點管理員系統[管理中心](https://endpoint.microsoft.com/#home)。</span><span class="sxs-lookup"><span data-stu-id="79a81-130">Next you&#39;ll need to log into the [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com/#home).</span></span> <span data-ttu-id="79a81-131">登入並選取 [ **裝置** ]，然後選取 [ **所有裝置**]。</span><span class="sxs-lookup"><span data-stu-id="79a81-131">Log in and select **Devices** then **All devices**.</span></span> <span data-ttu-id="79a81-132">您可以從這裡搜尋 HoloLens 裝置&#39;的名稱。</span><span class="sxs-lookup"><span data-stu-id="79a81-132">From here you can search your HoloLens device&#39;s name.</span></span> <span data-ttu-id="79a81-133">您應該能夠看到您的 HoloLens 列在 Intune 上。</span><span class="sxs-lookup"><span data-stu-id="79a81-133">You should be able to see your HoloLens listed on Intune.</span></span>

![Intune-裝置](./images/endpoint-all-devices-enrolled.png)

## <a name="remote-assist-call-validation"></a><span data-ttu-id="79a81-135">遠端協助通話驗證</span><span class="sxs-lookup"><span data-stu-id="79a81-135">Remote Assist Call Validation</span></span>

<span data-ttu-id="79a81-136">一旦您&#39;通過確認您的裝置已在您的 AAD 和 MDM 中註冊，就&#39;s 進行測試遠端協助通話。</span><span class="sxs-lookup"><span data-stu-id="79a81-136">Once you&#39;ve verified that your device is enrolled in both your AAD and MDM, it&#39;s time to place a test Remote Assist call.</span></span> <span data-ttu-id="79a81-137">針對此驗證，您&#39;需要擁有 HoloLens 裝置和 Windows 10 的電腦，以及電腦的第二個 Azure AD 使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="79a81-137">For this validation you&#39;ll need to have the HoloLens device and a Windows 10 PC, as well as a second Azure AD user account for the PC.</span></span>

<span data-ttu-id="79a81-138">此驗證步驟將假設您先前已完成最後一個驗證步驟，而且您的裝置已註冊，而且您的 Azure AD 使用者在裝置上。</span><span class="sxs-lookup"><span data-stu-id="79a81-138">This validation step will assume that you have previously completed the last validation step and your device is enrolled and your Azure AD user is on the device.</span></span>


1. <span data-ttu-id="79a81-139">如果您的電腦上還沒有安裝 Microsoft Teams，可以在[這裡下載 Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/download-app)。</span><span class="sxs-lookup"><span data-stu-id="79a81-139">If you don't already have Microsoft Teams installed on your PC, you can [download Teams here](https://www.microsoft.com/microsoft-365/microsoft-teams/download-app).</span></span>
2. <span data-ttu-id="79a81-140">使用第二個 Azure AD 使用者帳戶登入 Teams，而不是目前登入 HoloLens 的帳戶。</span><span class="sxs-lookup"><span data-stu-id="79a81-140">Sign into Teams using the second  Azure AD user account than the one currently signed into your HoloLens.</span></span> <span data-ttu-id="79a81-141">登入您的電腦之後，您就可以開始接收電話。</span><span class="sxs-lookup"><span data-stu-id="79a81-141">Once signed in your PC you will be ready to receive the call.</span></span>
3. <span data-ttu-id="79a81-142">解除鎖定您的 HoloLens 並登入。</span><span class="sxs-lookup"><span data-stu-id="79a81-142">Unlock your HoloLens and sign in.</span></span>
4. <span data-ttu-id="79a81-143">若要啟動遠端協助應用程式，請開啟 [ **開始] 功能表** ，然後選取 [ **遠端協助**]。</span><span class="sxs-lookup"><span data-stu-id="79a81-143">To launch the Remote Assist app open the **Start Menu** and select **Remote Assist**.</span></span> <span data-ttu-id="79a81-144">遠端協助不只會以收件匣應用程式的形式組合，而是釘選到 HoloLens 2&#39;s 的 [開始] 功能表。</span><span class="sxs-lookup"><span data-stu-id="79a81-144">Remote Assist is not only bundled as an inbox app but pinned to the HoloLens 2&#39;s start menu.</span></span> <span data-ttu-id="79a81-145">在&#39;您沒有看到釘選到 [開始] 功能表的事件中，然後開啟 **所有應用程式** 清單來尋找它。</span><span class="sxs-lookup"><span data-stu-id="79a81-145">In an event you don&#39;t see it pinned to the Start menu, then open the **All apps** list to look for it.</span></span>
5. <span data-ttu-id="79a81-146">遠端協助啟動之後，應透過 [SSO](/azure/active-directory/manage-apps/what-is-single-sign-on) 識別裝置的使用者，並登入應用程式。</span><span class="sxs-lookup"><span data-stu-id="79a81-146">Once Remote Assist starts it should identify the user of the device via [SSO](/azure/active-directory/manage-apps/what-is-single-sign-on) and log into the app.</span></span>
6. <span data-ttu-id="79a81-147">從應用程式內，選取 [ **搜尋** ] 並搜尋電腦上的第二個使用者。</span><span class="sxs-lookup"><span data-stu-id="79a81-147">From within the app, select **Search** and search for the second user on the PC.</span></span> <span data-ttu-id="79a81-148">選取使用者以開始通話。</span><span class="sxs-lookup"><span data-stu-id="79a81-148">Select the user to start the call.</span></span>
7. <span data-ttu-id="79a81-149">從您的電腦回答通話。</span><span class="sxs-lookup"><span data-stu-id="79a81-149">From your PC, answer the call.</span></span>

<span data-ttu-id="79a81-150">恭喜，您&#39;成功連線，並在您的遠端協助通話中。</span><span class="sxs-lookup"><span data-stu-id="79a81-150">Congratulations, you&#39;ve successfully connected and are on your remote assist call.</span></span> <span data-ttu-id="79a81-151">請務必嘗試特定的遠端協助功能，例如使用：</span><span class="sxs-lookup"><span data-stu-id="79a81-151">Make sure to try out specific remote assist features, such as using:</span></span>

- [<span data-ttu-id="79a81-152">筆跡注釋</span><span class="sxs-lookup"><span data-stu-id="79a81-152">Inking annotations</span></span>](/dynamics365/mixed-reality/remote-assist/add-annotations-hololens)
- [<span data-ttu-id="79a81-153">共用檔案和查看混合現實</span><span class="sxs-lookup"><span data-stu-id="79a81-153">Share a file and view in mixed reality</span></span>](/dynamics365/mixed-reality/remote-assist/display-save-files)
- [<span data-ttu-id="79a81-154">在另一個 HoloLens 應用程式中取得協助</span><span class="sxs-lookup"><span data-stu-id="79a81-154">Get help in another HoloLens app</span></span>](/dynamics365/mixed-reality/remote-assist/get-help-hololens-app-hololens)

## <a name="next-step"></a><span data-ttu-id="79a81-155">後續步驟</span><span class="sxs-lookup"><span data-stu-id="79a81-155">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="79a81-156">雲端連線部署-維護</span><span class="sxs-lookup"><span data-stu-id="79a81-156">Cloud connected deployment - Maintain</span></span>](hololens2-cloud-connected-maintain.md)