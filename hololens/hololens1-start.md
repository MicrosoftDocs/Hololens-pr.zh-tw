---
title: 設定 HoloLens (第 1 代)
description: 本指南會逐步解說首次設定。  您需要具備 Wi-Fi 網路以及 Microsoft (MSA) 或 Azure Active Directory (Azure AD) 帳戶。
ms.assetid: 0136188e-1305-43be-906e-151d70292e87
ms.prod: hololens
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
ms.date: 8/12/2019
manager: jarrettr
ms.localizationpriority: high
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 9a20a2ddd52c08a2b44dad452aac07ad9e69de85
ms.sourcegitcommit: 7edbb99e0972d3d857e5e87c062c3c64cacc1f41
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/01/2020
ms.locfileid: "10903229"
---
# <span data-ttu-id="ac697-104">設定您的 HoloLens (第 1 代)</span><span class="sxs-lookup"><span data-stu-id="ac697-104">Set up your HoloLens (1st gen)</span></span>

<span data-ttu-id="ac697-105">第一次開啟 HoloLens 時，系統會引導您校正裝置、設定裝置並登入。</span><span class="sxs-lookup"><span data-stu-id="ac697-105">The first time you turn on your HoloLens, you'll be guided through calibrating your device, setting up your device, and signing in.</span></span>  <span data-ttu-id="ac697-106">本文會逐步解說 HoloLens (第 1 代) 首次啟動和設定體驗。</span><span class="sxs-lookup"><span data-stu-id="ac697-106">This article walks through the HoloLens (1st gen) first start and setup experience.</span></span>

<span data-ttu-id="ac697-107">在下一節中，您將了解如何使用 HoloLens 並與全像投影互動。</span><span class="sxs-lookup"><span data-stu-id="ac697-107">In the next section, you'll learn how to work with HoloLens and interact with holograms.</span></span> <span data-ttu-id="ac697-108">若要跳到該篇文章，請參閱[開始使用 HoloLens (第 1 代)](hololens1-basic-usage.md)。</span><span class="sxs-lookup"><span data-stu-id="ac697-108">To skip ahead to that article, see [Get started with HoloLens (1st gen)](hololens1-basic-usage.md).</span></span>

## <span data-ttu-id="ac697-109">開始之前</span><span class="sxs-lookup"><span data-stu-id="ac697-109">Before you start</span></span>

<span data-ttu-id="ac697-110">開始使用之前，請確定您有下列項目可用：</span><span class="sxs-lookup"><span data-stu-id="ac697-110">Before you get started, make sure you have the following available:</span></span>

<span data-ttu-id="ac697-111">**Wi-Fi 連線**。</span><span class="sxs-lookup"><span data-stu-id="ac697-111">**A Wi-Fi connection**.</span></span> <span data-ttu-id="ac697-112">您必須將 HoloLens 連線至 Wi-Fi 網路，才能加以設定。</span><span class="sxs-lookup"><span data-stu-id="ac697-112">You'll need to connect your HoloLens to a Wi-Fi network to set it up.</span></span> <span data-ttu-id="ac697-113">第一次連線時，您需要不必瀏覽至網站或使用憑證即可連線的開放式網路或受密碼保護網路。</span><span class="sxs-lookup"><span data-stu-id="ac697-113">The first time you connect, you'll need an open or password-protected network that doesn't require navigating to a website or using certificates to connect.</span></span> <span data-ttu-id="ac697-114">[深入了解 HoloLens 所使用的網站](hololens-offline.md)。</span><span class="sxs-lookup"><span data-stu-id="ac697-114">[Learn more about the websites that HoloLens uses](hololens-offline.md).</span></span>

<span data-ttu-id="ac697-115">**Microsoft 帳戶或工作帳戶**。</span><span class="sxs-lookup"><span data-stu-id="ac697-115">**A Microsoft account or a work account**.</span></span> <span data-ttu-id="ac697-116">您也必須使用 Microsoft 帳戶 (如果您的組織擁有裝置，則是工作帳戶) 來登入 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="ac697-116">You'll also need to use a Microsoft account (or a work account, if your organization owns the device) to sign in to HoloLens.</span></span> <span data-ttu-id="ac697-117">如果沒有 Microsoft 帳戶，請前往 [account.microsoft.com](https://account.microsoft.com) 免費設定一個帳戶。</span><span class="sxs-lookup"><span data-stu-id="ac697-117">If you don't have a Microsoft account, go to [account.microsoft.com](https://account.microsoft.com) and set one up for free.</span></span>

<span data-ttu-id="ac697-118">**安全、照明充足且無絆倒危險的活動空間**。</span><span class="sxs-lookup"><span data-stu-id="ac697-118">**A safe, well-lit space with no tripping hazards**.</span></span> <span data-ttu-id="ac697-119">[健康與安全資訊](https://go.microsoft.com/fwlink/p/?LinkId=746661)。</span><span class="sxs-lookup"><span data-stu-id="ac697-119">[Health and safety info](https://go.microsoft.com/fwlink/p/?LinkId=746661).</span></span>

<span data-ttu-id="ac697-120">HoloLens 隨附的**選用舒適配件**，可協助您獲得最舒適的配戴感受。</span><span class="sxs-lookup"><span data-stu-id="ac697-120">**The optional comfort accessories** that came with your HoloLens, to help you get the most comfortable fit.</span></span> <span data-ttu-id="ac697-121">[適合和舒適性的詳細說明](https://support.microsoft.com/help/12632/hololens-fit-your-hololens)。</span><span class="sxs-lookup"><span data-stu-id="ac697-121">[More on fit and comfort](https://support.microsoft.com/help/12632/hololens-fit-your-hololens).</span></span>

> [!NOTE]
>  
> - <span data-ttu-id="ac697-122">您第一次使用 HoloLens 時，[Cortana](hololens-cortana.md) 已開啟並準備好引導您 (雖然在您設定好裝置之前，她無法回應您的問題)。</span><span class="sxs-lookup"><span data-stu-id="ac697-122">The first time that you use your HoloLens, [Cortana](hololens-cortana.md) is already on and ready to guide you (though she won't be able to respond to your questions until after you set up your device).</span></span> <span data-ttu-id="ac697-123">您隨時都可以在 Cortana 的設定中關閉 Cortana。</span><span class="sxs-lookup"><span data-stu-id="ac697-123">You can turn Cortana off at any time in Cortana's settings.</span></span>
> - <span data-ttu-id="ac697-124">若要切換到中文或日文版 HoloLens，您需要在電腦上下載該語言組建，然後將它安裝在 HoloLens 上。</span><span class="sxs-lookup"><span data-stu-id="ac697-124">In order to switch to the Chinese or Japanese version of HoloLens, you’ll need to download the build for the language on a PC and then install it on your HoloLens.</span></span> <span data-ttu-id="ac697-125">如需詳細資訊，請參閱[安裝 HoloLens (第 1 代) 的當地語系化版本](hololens1-install-localized.md)。</span><span class="sxs-lookup"><span data-stu-id="ac697-125">For more information, see [Install localized versions of HoloLens (1st gen)](hololens1-install-localized.md).</span></span>

## <span data-ttu-id="ac697-126">啟動 Hololens 並設定 Windows</span><span class="sxs-lookup"><span data-stu-id="ac697-126">Start your Hololens and set up Windows</span></span>

<span data-ttu-id="ac697-127">第一次啟動 HoloLens 時，第一項工作是在您的裝置上設定 Windows 全像攝影版。</span><span class="sxs-lookup"><span data-stu-id="ac697-127">The first time you start your HoloLens, your first task is to set up Windows Holographic on your device.</span></span>

1. <span data-ttu-id="ac697-128">連線至網際網路 (HoloLens 會引導您選取 Wi-Fi 網路)。</span><span class="sxs-lookup"><span data-stu-id="ac697-128">Connect to the internet (HoloLens guides you to select Wi-Fi network).</span></span>

1. <span data-ttu-id="ac697-129">登入您的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="ac697-129">Sign in to your user account.</span></span> <span data-ttu-id="ac697-130">選擇 [我的公司或學校擁有它]\*\*\*\* 或 [我擁有它]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ac697-130">Choose between **My work or school owns it** and **I own it**.</span></span>
    - <span data-ttu-id="ac697-131">當您選擇 [我的公司或學校擁有它]\*\*\*\* 時，請使用 Azure AD 帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="ac697-131">When you choose **My work or school owns it**, you sign in by using an Azure AD account.</span></span> <span data-ttu-id="ac697-132">如果您的組織使用 Azure AD Premium，且已設定自動 MDM 註冊，HoloLens 會自動在 MDM 中註冊。</span><span class="sxs-lookup"><span data-stu-id="ac697-132">If your organization uses Azure AD Premium and has configured automatic MDM enrollment, HoloLens automatically enrolls in MDM.</span></span> <span data-ttu-id="ac697-133">如果您的組織未使用 Azure AD Premium，就無法使用自動 MDM 註冊，因此您必須[在裝置管理中手動註冊 HoloLens](hololens-enroll-mdm.md#different-ways-to-enroll)。</span><span class="sxs-lookup"><span data-stu-id="ac697-133">If your organization does not use Azure AD Premium, automatic MDM enrollment isn't available, so you will need to [manually enroll HoloLens in device management](hololens-enroll-mdm.md#different-ways-to-enroll).</span></span> <span data-ttu-id="ac697-134">若您第一次使用工作或學校帳戶登入您的裝置，請依照下列步驟進行：</span><span class="sxs-lookup"><span data-stu-id="ac697-134">To sign in to your device the first time by using a work or school account, follow these steps:</span></span>
        1. <span data-ttu-id="ac697-135">輸入您組織的帳戶資訊。</span><span class="sxs-lookup"><span data-stu-id="ac697-135">Enter your organizational account information.</span></span>
        1. <span data-ttu-id="ac697-136">接受隱私權聲明。</span><span class="sxs-lookup"><span data-stu-id="ac697-136">Accept the privacy statement.</span></span>
        1. <span data-ttu-id="ac697-137">使用您的 Azure AD 認證登入。</span><span class="sxs-lookup"><span data-stu-id="ac697-137">Sign in by using your Azure AD credentials.</span></span> <span data-ttu-id="ac697-138">這可能會重新導向至您組織的登入頁面。</span><span class="sxs-lookup"><span data-stu-id="ac697-138">This may redirect to your organization's sign-in page.</span></span>
        1. <span data-ttu-id="ac697-139">繼續設定裝置。</span><span class="sxs-lookup"><span data-stu-id="ac697-139">Continue setting up the device.</span></span>
    - <span data-ttu-id="ac697-140">當您選擇 [我擁有它]\*\*\*\* 時，請使用 Microsoft 帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="ac697-140">When you choose **I own it**, you sign in by using a Microsoft account.</span></span> <span data-ttu-id="ac697-141">設定完成後，您可以[在裝置管理中手動註冊 HoloLens](hololens-enroll-mdm.md#different-ways-to-enroll)。</span><span class="sxs-lookup"><span data-stu-id="ac697-141">After setup is complete, you can [manually enroll HoloLens in device management](hololens-enroll-mdm.md#different-ways-to-enroll).</span></span>
        1. <span data-ttu-id="ac697-142">輸入您的 Microsoft 帳戶資訊。</span><span class="sxs-lookup"><span data-stu-id="ac697-142">Enter your Microsoft account information.</span></span>
        1. <span data-ttu-id="ac697-143">輸入您的密碼。</span><span class="sxs-lookup"><span data-stu-id="ac697-143">Enter your password.</span></span> <span data-ttu-id="ac697-144">如果您的 Microsoft 帳戶需要[兩步驟驗證 (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/)，請完成驗證程序。</span><span class="sxs-lookup"><span data-stu-id="ac697-144">If your Microsoft account requires [two-step verification (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/), complete the verification process.</span></span>

1. <span data-ttu-id="ac697-145">裝置會根據它從 Wi-Fi 網路取得的資訊來設定您的時區。</span><span class="sxs-lookup"><span data-stu-id="ac697-145">The device sets your time zone based on information that it obtains from the Wi-Fi network.</span></span>

## <span data-ttu-id="ac697-146">校正</span><span class="sxs-lookup"><span data-stu-id="ac697-146">Calibration</span></span>

<span data-ttu-id="ac697-147">當 Cortana 自我介紹之後，下一個設定步驟就是校正。</span><span class="sxs-lookup"><span data-stu-id="ac697-147">After Cortana introduces herself, the next setup step is calibration.</span></span> <span data-ttu-id="ac697-148">為了獲得最佳的 HoloLens 體驗，您應該在安裝期間完成校正程序。</span><span class="sxs-lookup"><span data-stu-id="ac697-148">For the best HoloLens experience, you should complete the calibration process during setup.</span></span>

<span data-ttu-id="ac697-149">HoloLens (第 1 代) 使用您瞳孔之間的距離 (IPD，或稱為[瞳距](https://en.wikipedia.org/wiki/Interpupillary_distance))，來讓影像清晰且易於互動。</span><span class="sxs-lookup"><span data-stu-id="ac697-149">HoloLens (1st gen) uses the distance between your pupils (IPD or [interpupillary distance](https://en.wikipedia.org/wiki/Interpupillary_distance)) to make holograms clear and easy to interact with.</span></span> <span data-ttu-id="ac697-150">如果 IPD 不正確，全像投影可能會不穩定或呈現不正確的距離。</span><span class="sxs-lookup"><span data-stu-id="ac697-150">If the IPD is not correct, holograms may appear to be unstable or at an incorrect distance.</span></span>

<span data-ttu-id="ac697-151">在校正期間，HoloLens 會要求您在每隻眼睛將手指對準一系列六個目標。</span><span class="sxs-lookup"><span data-stu-id="ac697-151">During calibration, HoloLens asks you to align your finger with a series of six targets per eye.</span></span> <span data-ttu-id="ac697-152">HoloLens 使用此程序來為眼睛設定正確的 IPD。</span><span class="sxs-lookup"><span data-stu-id="ac697-152">HoloLens uses this process to set the correct IPD for your eyes.</span></span> <span data-ttu-id="ac697-153">如果需要針對新使用者更新或調整校正，新使用者可以在安裝程式之外執行校正應用程式。</span><span class="sxs-lookup"><span data-stu-id="ac697-153">If the calibration needs to be updated or adjusted for a new user, the new user can run the Calibration app  outside of setup.</span></span>

![第二個步驟的 IPD 手指對準畫面](./images/ipd-finger-alignment-300px.jpg)

*<span data-ttu-id="ac697-155">第二個步驟的 IPD 手指對準畫面</span><span class="sxs-lookup"><span data-stu-id="ac697-155">IPD finger-alignment screen at second step</span></span>*

<span data-ttu-id="ac697-156">恭喜！</span><span class="sxs-lookup"><span data-stu-id="ac697-156">Congratulations!</span></span> <span data-ttu-id="ac697-157">設定完成後，您就可以開始使用 HoloLens 了。</span><span class="sxs-lookup"><span data-stu-id="ac697-157">Setup is complete and you can begin using HoloLens.</span></span>

## <span data-ttu-id="ac697-158">後續步驟</span><span class="sxs-lookup"><span data-stu-id="ac697-158">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="ac697-159">開始使用 HoloLens (第 1 代)</span><span class="sxs-lookup"><span data-stu-id="ac697-159">Get started with HoloLens (1st gen)</span></span>](hololens1-basic-usage.md)
