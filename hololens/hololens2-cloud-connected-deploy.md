---
title: 部署指南–雲端連接 HoloLens 2 部署（含遠端協助的部署）
description: 如何透過雲端連接的網路驗證 HoloLens 裝置的註冊與遠端協助
keywords: HoloLens、管理、雲端連線、遠端協助、AAD、Azure AD、MDM、行動裝置管理
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
ms.openlocfilehash: 2b38f4a76ee088d4f892c86de07d8f5a10d2a3bf
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/01/2021
ms.locfileid: "11253190"
---
# <span data-ttu-id="505c4-104">部署-雲端連線指南</span><span class="sxs-lookup"><span data-stu-id="505c4-104">Deploy - Cloud connected Guide</span></span>

<span data-ttu-id="505c4-105">現在您已設定所有內容，您應該準備好要發佈裝置。</span><span class="sxs-lookup"><span data-stu-id="505c4-105">Now that you have everything configured you should be ready to distribute devices.</span></span> <span data-ttu-id="505c4-106">不過，現在您應該先驗證您的設定。</span><span class="sxs-lookup"><span data-stu-id="505c4-106">However, now is when you should first validate your setup.</span></span> <span data-ttu-id="505c4-107">首先，必須驗證 Azure AD Join 和 MDM 註冊程式，然後再驗證是否可以設定遠端協助通話。</span><span class="sxs-lookup"><span data-stu-id="505c4-107">First the Azure AD Join and MDM Enrollment process should be validated, followed by verifying that a Remote Assist call can be placed.</span></span>

## <span data-ttu-id="505c4-108">註冊驗證</span><span class="sxs-lookup"><span data-stu-id="505c4-108">Enrollment Validation</span></span>

<span data-ttu-id="505c4-109">現在，所有內容都是針對 Azure AD 和 MDM 註冊進行正確設定，其餘部分現在應該是快照。</span><span class="sxs-lookup"><span data-stu-id="505c4-109">Now that everything is properly configured for Azure AD and MDM Enrollment, the rest should now be a snap.</span></span> <span data-ttu-id="505c4-110">您&#39;ll 需要 Wi-Fi 連線與 HoloLens 裝置，以及其中一個先前已設定的 AAD 使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="505c4-110">You&#39;ll need a Wi-Fi connection and the HoloLens device, as well as one of the previously configured AAD user accounts.</span></span>

<span data-ttu-id="505c4-111">如果您的裝置目前沒有&#39;t 坐在工廠設定狀態，現在將是 [reflash 裝置](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device)的好時機。</span><span class="sxs-lookup"><span data-stu-id="505c4-111">If your device isn&#39;t currently sitting in a factory settings state, now would be a good time to [reflash the device](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device).</span></span>

1. <span data-ttu-id="505c4-112">一旦您的裝置在 OOBE 中，您&#39;必須開始互動並遵循提示。</span><span class="sxs-lookup"><span data-stu-id="505c4-112">Once your device is in OOBE, you&#39;ll need to start interacting and following the prompts.</span></span> 
1. <span data-ttu-id="505c4-113">當系統詢問您**擁有此 HoloLens 的人**時，會出現 [重要] 提示？</span><span class="sxs-lookup"><span data-stu-id="505c4-113">The critical prompt will be when you are asked **Who owns this HoloLens?**</span></span> <span data-ttu-id="505c4-114">選取 [ **我的公司或學校擁有** ]，然後輸入您的 Azure AD 帳號憑證。</span><span class="sxs-lookup"><span data-stu-id="505c4-114">Select **My work or school owns it** and enter your Azure AD account credentials.</span></span>
1. <span data-ttu-id="505c4-115">註冊成功&#39;之後，系統會提示您設定 PIN。</span><span class="sxs-lookup"><span data-stu-id="505c4-115">When enrollment is successful, you&#39;ll be prompted to set up a PIN.</span></span> <span data-ttu-id="505c4-116">此 PIN 對於此使用者而言是唯一的裝置。</span><span class="sxs-lookup"><span data-stu-id="505c4-116">This PIN is unique to this device for this user.</span></span> <span data-ttu-id="505c4-117">您也會收到虹彩 [掃描]、[語音資料] 和 [遙測] 設定的提示，然後您&#39;可以瞭解如何開啟 [開始] 功能表並完成 OOBE。</span><span class="sxs-lookup"><span data-stu-id="505c4-117">You will also be prompted for Iris scans, voice data, and telemetry settings and finally, you&#39;ll be able to learn how to open the start menu and complete OOBE.</span></span>
1. <span data-ttu-id="505c4-118">當您進入混合現實家用版時，請使用您剛剛學到的 [ **開始** ] 功能表開啟 [開始] 功能表。</span><span class="sxs-lookup"><span data-stu-id="505c4-118">Once you land in the Mixed Reality Home open the Start menu using the **Start gesture** you just learned.</span></span>
1. <span data-ttu-id="505c4-119">選取 [ **設定** ] 應用程式，然後選取 [ **系統]。**</span><span class="sxs-lookup"><span data-stu-id="505c4-119">Select the **Settings** app and select **System.**</span></span> <span data-ttu-id="505c4-120">您&#39;的第一條資訊會看到您的裝置名稱，而您的 HoloLens 2 裝置將會是 &quot; hololens， &quot; 後接六個字元的字串。</span><span class="sxs-lookup"><span data-stu-id="505c4-120">The first piece of information you&#39;ll see is your Device name, which for your HoloLens 2 device will be &quot;HOLOLENS-&quot; followed by a six character string.</span></span>
1. <span data-ttu-id="505c4-121">記下此名稱。</span><span class="sxs-lookup"><span data-stu-id="505c4-121">Take note of this name.</span></span>

![HoloLens 2 設定-關於](./images/hololens2-settings-about.jpg)

7. <span data-ttu-id="505c4-123">您可以在 [設定] 應用程式中確認您的裝置已成功註冊到 Azure AD 中。</span><span class="sxs-lookup"><span data-stu-id="505c4-123">You can verify that your device is successfully enrolled in the Azure AD within the Settings app.</span></span> <span data-ttu-id="505c4-124">從 [**設定**] 選取 [**帳戶**  ->  **存取公司或學校**]。</span><span class="sxs-lookup"><span data-stu-id="505c4-124">From **Settings** select **Accounts** -> **Access work or school**.</span></span> <span data-ttu-id="505c4-125">在這個畫面上，您可以查看已 &quot; 連線至 _nameofAAD_&#39;s Azure AD，以驗證您是否已順利註冊。</span><span class="sxs-lookup"><span data-stu-id="505c4-125">From this screen you can verify you are successfully enrolled by seeing &quot;Connected to _nameofAAD_&#39;s Azure AD.</span></span> <span data-ttu-id="505c4-126">已透過_yourusername_ @ _nameofAAD_ &quot; 。</span><span class="sxs-lookup"><span data-stu-id="505c4-126">Connected by _yourusername_@_nameofAAD_.onmicrosoft.com&quot;.</span></span>


<span data-ttu-id="505c4-127">若要驗證裝置是否已加入 azure AD，我們可以從[azure portal](https://portal.azure.com/#home)  ->  **azure active directory**  ->  **裝置**  ->  （**所有裝置**）檢查 azure Active Directory，然後搜尋裝置名稱。</span><span class="sxs-lookup"><span data-stu-id="505c4-127">To validate the device has Azure AD Joined we can check the Azure Active Directory from the [Azure portal](https://portal.azure.com/#home) -> **Azure Active Directory** -> **Devices** -> **All devices**, and search the device name.</span></span> <span data-ttu-id="505c4-128">您&#39;就能看到裝置是 Azure Active Directory 的一部分。</span><span class="sxs-lookup"><span data-stu-id="505c4-128">You&#39;ll be able to see the device is a part of the Azure Active Directory.</span></span>


![Azure Active Directory-裝置](./images/aad-enrollment.png)

<span data-ttu-id="505c4-130">接下來，您&#39;需要登入 [Microsoft 端點](https://endpoint.microsoft.com/#home)管理員系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="505c4-130">Next you&#39;ll need to log into the [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com/#home).</span></span> <span data-ttu-id="505c4-131">登入並選取 [ **裝置** ]，然後選取 [ **所有裝置**]。</span><span class="sxs-lookup"><span data-stu-id="505c4-131">Log in and select **Devices** then **All devices**.</span></span> <span data-ttu-id="505c4-132">您可以從這裡搜尋您的 HoloLens 裝置，&#39;s 名。</span><span class="sxs-lookup"><span data-stu-id="505c4-132">From here you can search your HoloLens device&#39;s name.</span></span> <span data-ttu-id="505c4-133">您應該能夠看到您在 Intune 上列出的 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="505c4-133">You should be able to see your HoloLens listed on Intune.</span></span>

![Intune-裝置](./images/endpoint-all-devices-enrolled.png)

## <span data-ttu-id="505c4-135">遠端協助通話驗證</span><span class="sxs-lookup"><span data-stu-id="505c4-135">Remote Assist Call Validation</span></span>

<span data-ttu-id="505c4-136">當您&#39;已確認您的裝置已在您的 AAD 和 MDM 中註冊之後，就會&#39;s 時間來放置測試遠端協助通話。</span><span class="sxs-lookup"><span data-stu-id="505c4-136">Once you&#39;ve verified that your device is enrolled in both your AAD and MDM, it&#39;s time to place a test Remote Assist call.</span></span> <span data-ttu-id="505c4-137">針對這種驗證，您&#39;必須擁有 HoloLens 裝置和 Windows 10 電腦，以及適用于電腦的第二個 Azure AD 使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="505c4-137">For this validation you&#39;ll need to have the HoloLens device and a Windows 10 PC, as well as a second Azure AD user account for the PC.</span></span>

<span data-ttu-id="505c4-138">這個驗證步驟將假設您先前已完成上一個驗證步驟，且您的裝置已註冊，且您的 Azure AD 使用者位於裝置上。</span><span class="sxs-lookup"><span data-stu-id="505c4-138">This validation step will assume that you have previously completed the last validation step and your device is enrolled and your Azure AD user is on the device.</span></span>


1. <span data-ttu-id="505c4-139">如果您的電腦上還沒有安裝 Microsoft 團隊，您可以在 [此下載團隊](https://www.microsoft.com/microsoft-365/microsoft-teams/download-app)。</span><span class="sxs-lookup"><span data-stu-id="505c4-139">If you don't already have Microsoft Teams installed on your PC, you can [download Teams here](https://www.microsoft.com/microsoft-365/microsoft-teams/download-app).</span></span>
2. <span data-ttu-id="505c4-140">使用第二個 Azure AD 使用者帳戶（而非目前登入您的 HoloLens）登入團隊。</span><span class="sxs-lookup"><span data-stu-id="505c4-140">Sign into Teams using the second  Azure AD user account than the one currently signed into your HoloLens.</span></span> <span data-ttu-id="505c4-141">登入您的電腦之後，您就可以開始接聽通話。</span><span class="sxs-lookup"><span data-stu-id="505c4-141">Once signed in your PC you will be ready to receive the call.</span></span>
3. <span data-ttu-id="505c4-142">解鎖您的 HoloLens 並登入。</span><span class="sxs-lookup"><span data-stu-id="505c4-142">Unlock your HoloLens and sign in.</span></span>
4. <span data-ttu-id="505c4-143">若要啟動遠端協助應用程式，請開啟 [ **開始] 功能表** ，然後選取 [ **遠端協助**]。</span><span class="sxs-lookup"><span data-stu-id="505c4-143">To launch the Remote Assist app open the **Start Menu** and select **Remote Assist**.</span></span> <span data-ttu-id="505c4-144">遠端協助並不只捆綁成收件匣 app，但已釘選到 HoloLens 2&#39;s [開始] 功能表。</span><span class="sxs-lookup"><span data-stu-id="505c4-144">Remote Assist is not only bundled as an inbox app but pinned to the HoloLens 2&#39;s start menu.</span></span> <span data-ttu-id="505c4-145">在您不&#39;的事件中，會看到它釘選到 [開始] 功能表，然後開啟 [ **所有應用程式** ] 清單來尋找它。</span><span class="sxs-lookup"><span data-stu-id="505c4-145">In an event you don&#39;t see it pinned to the Start menu, then open the **All apps** list to look for it.</span></span>
5. <span data-ttu-id="505c4-146">遠端協助開始之後，就應該透過 [SSO](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on) 來識別裝置的使用者，並登入 app。</span><span class="sxs-lookup"><span data-stu-id="505c4-146">Once Remote Assist starts it should identify the user of the device via [SSO](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on) and log into the app.</span></span>
6. <span data-ttu-id="505c4-147">從應用程式中，選取 [ **搜尋** ]，然後搜尋電腦上的第二位使用者。</span><span class="sxs-lookup"><span data-stu-id="505c4-147">From within the app, select **Search** and search for the second user on the PC.</span></span> <span data-ttu-id="505c4-148">選取要啟動通話的使用者。</span><span class="sxs-lookup"><span data-stu-id="505c4-148">Select the user to start the call.</span></span>
7. <span data-ttu-id="505c4-149">從您的電腦接聽通話。</span><span class="sxs-lookup"><span data-stu-id="505c4-149">From your PC, answer the call.</span></span>

<span data-ttu-id="505c4-150">恭喜，您&#39;ve 已成功連線，且是在您的遠端協助通話中。</span><span class="sxs-lookup"><span data-stu-id="505c4-150">Congratulations, you&#39;ve successfully connected and are on your remote assist call.</span></span> <span data-ttu-id="505c4-151">請務必嘗試使用特定的遠端協助功能，例如使用：</span><span class="sxs-lookup"><span data-stu-id="505c4-151">Make sure to try out specific remote assist features, such as using:</span></span>

- [<span data-ttu-id="505c4-152">筆跡標注</span><span class="sxs-lookup"><span data-stu-id="505c4-152">Inking annotations</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/add-annotations-hololens)
- [<span data-ttu-id="505c4-153">在混合式現實中共用檔案和視圖</span><span class="sxs-lookup"><span data-stu-id="505c4-153">Share a file and view in mixed reality</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/display-save-files)
- [<span data-ttu-id="505c4-154">在其他 HoloLens 應用程式中取得協助</span><span class="sxs-lookup"><span data-stu-id="505c4-154">Get help in another HoloLens app</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/get-help-hololens-app-hololens)

## <span data-ttu-id="505c4-155">後續步驟</span><span class="sxs-lookup"><span data-stu-id="505c4-155">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="505c4-156">雲端連接部署-維護</span><span class="sxs-lookup"><span data-stu-id="505c4-156">Cloud connected deployment - Maintain</span></span>](hololens2-cloud-connected-maintain.md)