---
title: 設定 HoloLens (第 1 代)
description: 瞭解如何使用 Microsoft (MSA) 或 Azure Active Directory (AAD) 帳戶，在 Wi-Fi 網路上首次設定 HoloLens (第 1 代)。
ms.assetid: 0136188e-1305-43be-906e-151d70292e87
ms.prod: hololens
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
ms.date: 8/12/2019
manager: jarrettr
ms.localizationpriority: medium
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: f0ec62e55f15fda6d5a8304ea2bb77039d644b9e
ms.sourcegitcommit: 01c0b0a789e156a9d29aaf6f61e36dfd09b8c01a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439059"
---
# <a name="set-up-your-hololens-1st-gen"></a><span data-ttu-id="5b2f8-103">設定您的 HoloLens (第 1 代)</span><span class="sxs-lookup"><span data-stu-id="5b2f8-103">Set up your HoloLens (1st gen)</span></span>

<span data-ttu-id="5b2f8-104">第一次開啟 HoloLens 時，系統會引導您校正裝置、設定裝置並登入。</span><span class="sxs-lookup"><span data-stu-id="5b2f8-104">The first time you turn on your HoloLens, you'll be guided through calibrating your device, setting up your device, and signing in.</span></span>  <span data-ttu-id="5b2f8-105">本文會逐步解說 HoloLens (第 1 代) 首次啟動和設定體驗。</span><span class="sxs-lookup"><span data-stu-id="5b2f8-105">This article walks through the HoloLens (1st gen) first start and setup experience.</span></span>

<span data-ttu-id="5b2f8-106">在下一節中，您將了解如何使用 HoloLens 並與全像投影互動。</span><span class="sxs-lookup"><span data-stu-id="5b2f8-106">In the next section, you'll learn how to work with HoloLens and interact with holograms.</span></span> <span data-ttu-id="5b2f8-107">若要跳到該篇文章，請參閱[開始使用 HoloLens (第 1 代)](hololens1-basic-usage.md)。</span><span class="sxs-lookup"><span data-stu-id="5b2f8-107">To skip ahead to that article, see [Get started with HoloLens (1st gen)](hololens1-basic-usage.md).</span></span>

## <a name="before-you-start"></a><span data-ttu-id="5b2f8-108">開始之前</span><span class="sxs-lookup"><span data-stu-id="5b2f8-108">Before you start</span></span>

<span data-ttu-id="5b2f8-109">開始使用之前，請確定您有下列項目可用：</span><span class="sxs-lookup"><span data-stu-id="5b2f8-109">Before you get started, make sure you have the following available:</span></span>

<span data-ttu-id="5b2f8-110">**Wi-Fi 連線**。</span><span class="sxs-lookup"><span data-stu-id="5b2f8-110">**A Wi-Fi connection**.</span></span> <span data-ttu-id="5b2f8-111">您必須將 HoloLens 連線至 Wi-Fi 網路，才能加以設定。</span><span class="sxs-lookup"><span data-stu-id="5b2f8-111">You'll need to connect your HoloLens to a Wi-Fi network to set it up.</span></span> <span data-ttu-id="5b2f8-112">第一次連線時，您需要不必瀏覽至網站或使用憑證即可連線的開放式網路或受密碼保護網路。</span><span class="sxs-lookup"><span data-stu-id="5b2f8-112">The first time you connect, you'll need an open or password-protected network that doesn't require navigating to a website or using certificates to connect.</span></span> <span data-ttu-id="5b2f8-113">[深入了解 HoloLens 所使用的網站](hololens-offline.md)。</span><span class="sxs-lookup"><span data-stu-id="5b2f8-113">[Learn more about the websites that HoloLens uses](hololens-offline.md).</span></span>

<span data-ttu-id="5b2f8-114">**Microsoft 帳戶或工作帳戶**。</span><span class="sxs-lookup"><span data-stu-id="5b2f8-114">**A Microsoft account or a work account**.</span></span> <span data-ttu-id="5b2f8-115">您也必須使用 Microsoft 帳戶 (如果您的組織擁有裝置，則是工作帳戶) 來登入 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="5b2f8-115">You'll also need to use a Microsoft account (or a work account, if your organization owns the device) to sign in to HoloLens.</span></span> <span data-ttu-id="5b2f8-116">如果沒有 Microsoft 帳戶，請前往 [account.microsoft.com](https://account.microsoft.com) 免費設定一個帳戶。</span><span class="sxs-lookup"><span data-stu-id="5b2f8-116">If you don't have a Microsoft account, go to [account.microsoft.com](https://account.microsoft.com) and set one up for free.</span></span>

<span data-ttu-id="5b2f8-117">**安全、照明充足且無絆倒危險的活動空間**。</span><span class="sxs-lookup"><span data-stu-id="5b2f8-117">**A safe, well-lit space with no tripping hazards**.</span></span> <span data-ttu-id="5b2f8-118">[健康與安全資訊](https://go.microsoft.com/fwlink/p/?LinkId=746661)。</span><span class="sxs-lookup"><span data-stu-id="5b2f8-118">[Health and safety info](https://go.microsoft.com/fwlink/p/?LinkId=746661).</span></span>

<span data-ttu-id="5b2f8-119">HoloLens 隨附的**選用舒適配件**，可協助您獲得最舒適的配戴感受。</span><span class="sxs-lookup"><span data-stu-id="5b2f8-119">**The optional comfort accessories** that came with your HoloLens, to help you get the most comfortable fit.</span></span> <span data-ttu-id="5b2f8-120">[適合和舒適性的詳細說明](https://support.microsoft.com/help/12632/hololens-fit-your-hololens)。</span><span class="sxs-lookup"><span data-stu-id="5b2f8-120">[More on fit and comfort](https://support.microsoft.com/help/12632/hololens-fit-your-hololens).</span></span>

> [!NOTE]
>  
> - <span data-ttu-id="5b2f8-121">您第一次使用 HoloLens 時，[Cortana](hololens-cortana.md) 已開啟並準備好引導您 (雖然在您設定好裝置之前，她無法回應您的問題)。</span><span class="sxs-lookup"><span data-stu-id="5b2f8-121">The first time that you use your HoloLens, [Cortana](hololens-cortana.md) is already on and ready to guide you (though she won't be able to respond to your questions until after you set up your device).</span></span> <span data-ttu-id="5b2f8-122">您隨時都可以在 Cortana 的設定中關閉 Cortana。</span><span class="sxs-lookup"><span data-stu-id="5b2f8-122">You can turn Cortana off at any time in Cortana's settings.</span></span>
> - <span data-ttu-id="5b2f8-123">若要切換到中文或日文版 HoloLens，您需要在電腦上下載該語言組建，然後將它安裝在 HoloLens 上。</span><span class="sxs-lookup"><span data-stu-id="5b2f8-123">In order to switch to the Chinese or Japanese version of HoloLens, you’ll need to download the build for the language on a PC and then install it on your HoloLens.</span></span> <span data-ttu-id="5b2f8-124">如需詳細資訊，請參閱[安裝 HoloLens (第 1 代) 的當地語系化版本](hololens1-install-localized.md)。</span><span class="sxs-lookup"><span data-stu-id="5b2f8-124">For more information, see [Install localized versions of HoloLens (1st gen)](hololens1-install-localized.md).</span></span>

## <a name="start-your-hololens-and-set-up-windows"></a><span data-ttu-id="5b2f8-125">啟動 Hololens 並設定 Windows</span><span class="sxs-lookup"><span data-stu-id="5b2f8-125">Start your Hololens and set up Windows</span></span>

<span data-ttu-id="5b2f8-126">第一次啟動 HoloLens 時，第一項工作是在您的裝置上設定 Windows 全像攝影版。</span><span class="sxs-lookup"><span data-stu-id="5b2f8-126">The first time you start your HoloLens, your first task is to set up Windows Holographic on your device.</span></span>

1. <span data-ttu-id="5b2f8-127">連線至網際網路 (HoloLens 會引導您選取 Wi-Fi 網路)。</span><span class="sxs-lookup"><span data-stu-id="5b2f8-127">Connect to the internet (HoloLens guides you to select Wi-Fi network).</span></span>

1. <span data-ttu-id="5b2f8-128">登入您的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="5b2f8-128">Sign in to your user account.</span></span> <span data-ttu-id="5b2f8-129">選擇 [我的公司或學校擁有它]\*\*\*\* 或 [我擁有它]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="5b2f8-129">Choose between **My work or school owns it** and **I own it**.</span></span>
    - <span data-ttu-id="5b2f8-130">當您選擇 [我的公司或學校擁有它]\*\*\*\* 時，請使用 Azure AD 帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="5b2f8-130">When you choose **My work or school owns it**, you sign in by using an Azure AD account.</span></span> <span data-ttu-id="5b2f8-131">如果您的組織使用 Azure AD Premium，且已設定自動 MDM 註冊，HoloLens 會自動在 MDM 中註冊。</span><span class="sxs-lookup"><span data-stu-id="5b2f8-131">If your organization uses Azure AD Premium and has configured automatic MDM enrollment, HoloLens automatically enrolls in MDM.</span></span> <span data-ttu-id="5b2f8-132">如果您的組織未使用 Azure AD Premium，就無法使用自動 MDM 註冊，因此您必須[在裝置管理中手動註冊 HoloLens](hololens-enroll-mdm.md#different-ways-to-enroll)。</span><span class="sxs-lookup"><span data-stu-id="5b2f8-132">If your organization does not use Azure AD Premium, automatic MDM enrollment isn't available, so you will need to [manually enroll HoloLens in device management](hololens-enroll-mdm.md#different-ways-to-enroll).</span></span> <span data-ttu-id="5b2f8-133">若您第一次使用工作或學校帳戶登入您的裝置，請依照下列步驟進行：</span><span class="sxs-lookup"><span data-stu-id="5b2f8-133">To sign in to your device the first time by using a work or school account, follow these steps:</span></span>
        1. <span data-ttu-id="5b2f8-134">輸入您組織的帳戶資訊。</span><span class="sxs-lookup"><span data-stu-id="5b2f8-134">Enter your organizational account information.</span></span>
        1. <span data-ttu-id="5b2f8-135">接受隱私權聲明。</span><span class="sxs-lookup"><span data-stu-id="5b2f8-135">Accept the privacy statement.</span></span>
        1. <span data-ttu-id="5b2f8-136">使用您的 Azure AD 認證登入。</span><span class="sxs-lookup"><span data-stu-id="5b2f8-136">Sign in by using your Azure AD credentials.</span></span> <span data-ttu-id="5b2f8-137">這可能會重新導向至您組織的登入頁面。</span><span class="sxs-lookup"><span data-stu-id="5b2f8-137">This may redirect to your organization's sign-in page.</span></span>
        1. <span data-ttu-id="5b2f8-138">繼續設定裝置。</span><span class="sxs-lookup"><span data-stu-id="5b2f8-138">Continue setting up the device.</span></span>
    - <span data-ttu-id="5b2f8-139">當您選擇 [我擁有它]\*\*\*\* 時，請使用 Microsoft 帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="5b2f8-139">When you choose **I own it**, you sign in by using a Microsoft account.</span></span> <span data-ttu-id="5b2f8-140">設定完成後，您可以[在裝置管理中手動註冊 HoloLens](hololens-enroll-mdm.md#different-ways-to-enroll)。</span><span class="sxs-lookup"><span data-stu-id="5b2f8-140">After setup is complete, you can [manually enroll HoloLens in device management](hololens-enroll-mdm.md#different-ways-to-enroll).</span></span>
        1. <span data-ttu-id="5b2f8-141">輸入您的 Microsoft 帳戶資訊。</span><span class="sxs-lookup"><span data-stu-id="5b2f8-141">Enter your Microsoft account information.</span></span>
        1. <span data-ttu-id="5b2f8-142">輸入您的密碼。</span><span class="sxs-lookup"><span data-stu-id="5b2f8-142">Enter your password.</span></span> <span data-ttu-id="5b2f8-143">如果您的 Microsoft 帳戶需要[雙步驟驗證 (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/)，請完成驗證程序。</span><span class="sxs-lookup"><span data-stu-id="5b2f8-143">If your Microsoft account requires [two-step verification (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/), complete the verification process.</span></span>

1. <span data-ttu-id="5b2f8-144">裝置會根據它從 Wi-Fi 網路取得的資訊來設定您的時區。</span><span class="sxs-lookup"><span data-stu-id="5b2f8-144">The device sets your time zone based on information that it obtains from the Wi-Fi network.</span></span>

## <a name="calibration"></a><span data-ttu-id="5b2f8-145">校正</span><span class="sxs-lookup"><span data-stu-id="5b2f8-145">Calibration</span></span>

<span data-ttu-id="5b2f8-146">當 Cortana 自我介紹之後，下一個設定步驟就是校正。</span><span class="sxs-lookup"><span data-stu-id="5b2f8-146">After Cortana introduces herself, the next setup step is calibration.</span></span> <span data-ttu-id="5b2f8-147">為了獲得最佳的 HoloLens 體驗，您應該在安裝期間完成校正程序。</span><span class="sxs-lookup"><span data-stu-id="5b2f8-147">For the best HoloLens experience, you should complete the calibration process during setup.</span></span>

<span data-ttu-id="5b2f8-148">HoloLens (第 1 代) 使用您瞳孔之間的距離 (IPD，或稱為[瞳距](https://en.wikipedia.org/wiki/Interpupillary_distance))，來讓影像清晰且易於互動。</span><span class="sxs-lookup"><span data-stu-id="5b2f8-148">HoloLens (1st gen) uses the distance between your pupils (IPD or [interpupillary distance](https://en.wikipedia.org/wiki/Interpupillary_distance)) to make holograms clear and easy to interact with.</span></span> <span data-ttu-id="5b2f8-149">如果 IPD 不正確，全像投影可能會不穩定或呈現不正確的距離。</span><span class="sxs-lookup"><span data-stu-id="5b2f8-149">If the IPD is not correct, holograms may appear to be unstable or at an incorrect distance.</span></span>

<span data-ttu-id="5b2f8-150">在校正期間，HoloLens 會要求您在每隻眼睛將手指對準一系列六個目標。</span><span class="sxs-lookup"><span data-stu-id="5b2f8-150">During calibration, HoloLens asks you to align your finger with a series of six targets per eye.</span></span> <span data-ttu-id="5b2f8-151">HoloLens 使用此程序來為眼睛設定正確的 IPD。</span><span class="sxs-lookup"><span data-stu-id="5b2f8-151">HoloLens uses this process to set the correct IPD for your eyes.</span></span> <span data-ttu-id="5b2f8-152">如果需要針對新使用者更新或調整校正，新使用者可以在安裝程式之外執行校正應用程式。</span><span class="sxs-lookup"><span data-stu-id="5b2f8-152">If the calibration needs to be updated or adjusted for a new user, the new user can run the Calibration app  outside of setup.</span></span>

![第二個步驟的 IPD 手指對準畫面](./images/ipd-finger-alignment-300px.jpg)

*<span data-ttu-id="5b2f8-154">第二個步驟的 IPD 手指對準畫面</span><span class="sxs-lookup"><span data-stu-id="5b2f8-154">IPD finger-alignment screen at second step</span></span>*

<span data-ttu-id="5b2f8-155">恭喜！</span><span class="sxs-lookup"><span data-stu-id="5b2f8-155">Congratulations!</span></span> <span data-ttu-id="5b2f8-156">設定完成後，您就可以開始使用 HoloLens 了。</span><span class="sxs-lookup"><span data-stu-id="5b2f8-156">Setup is complete and you can begin using HoloLens.</span></span>

## <a name="next-steps"></a><span data-ttu-id="5b2f8-157">後續步驟</span><span class="sxs-lookup"><span data-stu-id="5b2f8-157">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="5b2f8-158">開始使用 HoloLens (第 1 代)</span><span class="sxs-lookup"><span data-stu-id="5b2f8-158">Get started with HoloLens (1st gen)</span></span>](hololens1-basic-usage.md)
