---
title: 在商業環境中設定 HoloLens
description: 深入瞭解在企業環境中部署和管理 HoloLens。
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: scooley
ms.author: scooley
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 07/15/2019
ms.openlocfilehash: e53e6575ef688e01ce2d1f6124f3214b18b05c95
ms.sourcegitcommit: 896bdfccf4612a692a25a6bfaecfa2146860407e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/11/2020
ms.locfileid: "10865562"
---
# <span data-ttu-id="b54c9-103">在商業環境中部署 HoloLens</span><span class="sxs-lookup"><span data-stu-id="b54c9-103">Deploy HoloLens in a commercial environment</span></span>

<span data-ttu-id="b54c9-104">您可以在商業設定中，以縮放比例部署和設定 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="b54c9-104">You can deploy and configure HoloLens at scale in a commercial setting.</span></span> <span data-ttu-id="b54c9-105">本文提供在商業環境中部署 HoloLens 裝置的相關指示。</span><span class="sxs-lookup"><span data-stu-id="b54c9-105">This article provides instructions for deploying HoloLens devices in a commercial environment.</span></span> <span data-ttu-id="b54c9-106">本指南假設您基本熟悉 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="b54c9-106">This guide assumes basic familiarity with HoloLens.</span></span> <span data-ttu-id="b54c9-107">請依照[快速入門手冊](hololens1-setup.md)，第一次設定 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="b54c9-107">Follow the [get started guide](hololens1-setup.md) to set up HoloLens for the first time.</span></span>

<span data-ttu-id="b54c9-108">本檔也假設您的 HoloLens 已由安全小組評估為可在商業網路上使用的安全小組。</span><span class="sxs-lookup"><span data-stu-id="b54c9-108">This document also assumes that the HoloLens has been evaluated by security teams as safe to use on the corporate network.</span></span>  
> [!Tip]
> <span data-ttu-id="b54c9-109">深入瞭解[HoloLens 安全性](security-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="b54c9-109">Learn more about [HoloLens security](security-overview.md).</span></span>
> <span data-ttu-id="b54c9-110">針對 HoloLens (1 Gen) 安全性請參閱[此常見問題](hololens1-faq-security.md)。</span><span class="sxs-lookup"><span data-stu-id="b54c9-110">For HoloLens (1st Gen) security please review [this FAQ](hololens1-faq-security.md).</span></span>

## <span data-ttu-id="b54c9-111">部署步驟概述</span><span class="sxs-lookup"><span data-stu-id="b54c9-111">Overview of Deployment Steps</span></span>

1. [<span data-ttu-id="b54c9-112">判斷您需要的功能</span><span class="sxs-lookup"><span data-stu-id="b54c9-112">Determine what features you need</span></span>](hololens-requirements.md#step-1-determine-what-you-need)
1. [<span data-ttu-id="b54c9-113">判斷您需要的授權</span><span class="sxs-lookup"><span data-stu-id="b54c9-113">Determine what licenses you need</span></span>](hololens-licenses-requirements.md)
1. <span data-ttu-id="b54c9-114">[針對 HoloLens 設定您的網路](hololens-commercial-infrastructure.md)。</span><span class="sxs-lookup"><span data-stu-id="b54c9-114">[Configure your network for HoloLens](hololens-commercial-infrastructure.md).</span></span>
    1. <span data-ttu-id="b54c9-115">本節包含需要在防火牆上允許的頻寬需求、URL 和埠;Azure AD 指南;行動裝置管理 (MDM) 指南;app 部署/管理指導方針;與證書指導方針。</span><span class="sxs-lookup"><span data-stu-id="b54c9-115">This section includes bandwidth requirements, URL, and ports that need to be allowed on your firewall; Azure AD guidance; Mobile Device Management (MDM) Guidance; app deployment/management guidance; and certificate guidance.</span></span>
1. <span data-ttu-id="b54c9-116"> (選擇性) [使用預配套件來設定 HoloLens](hololens-provisioning.md)</span><span class="sxs-lookup"><span data-stu-id="b54c9-116">(Optional) [Configure HoloLens using a provisioning package](hololens-provisioning.md)</span></span>
1. [<span data-ttu-id="b54c9-117">註冊裝置</span><span class="sxs-lookup"><span data-stu-id="b54c9-117">Enroll Device</span></span>](hololens-enroll-mdm.md)
1. [<span data-ttu-id="b54c9-118">設定 HoloLens 的通道步調更新</span><span class="sxs-lookup"><span data-stu-id="b54c9-118">Set up ring based updates for HoloLens</span></span>](hololens-updates.md)
1. [<span data-ttu-id="b54c9-119">針對 HoloLens 啟用 Bitlocker 裝置加密</span><span class="sxs-lookup"><span data-stu-id="b54c9-119">Enable Bitlocker device encryption for HoloLens</span></span>](security-encryption-data-protection.md)

## <span data-ttu-id="b54c9-120">步驟 1.</span><span class="sxs-lookup"><span data-stu-id="b54c9-120">Step 1.</span></span> <span data-ttu-id="b54c9-121">判斷您需要的專案</span><span class="sxs-lookup"><span data-stu-id="b54c9-121">Determine what you need</span></span>

<span data-ttu-id="b54c9-122">在您的環境中部署 HoloLens 之前，請務必先判斷需要哪些功能、應用程式及身分識別類型。</span><span class="sxs-lookup"><span data-stu-id="b54c9-122">Before deploying the HoloLens in your environment, it is important to first determine what features, apps, and type of identities are needed.</span></span> <span data-ttu-id="b54c9-123">另外，請務必確保您的安全小組已在公司的網路上使用 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="b54c9-123">It is also important to ensure that your security team has approved of the use of the HoloLens on the company's network.</span></span> <span data-ttu-id="b54c9-124">如需其他安全性資訊，請參閱[HoloLens2 安全性](security-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="b54c9-124">Please see [HoloLens2 security](security-overview.md) for additional security information.</span></span>

### <span data-ttu-id="b54c9-125">身分識別類型</span><span class="sxs-lookup"><span data-stu-id="b54c9-125">Type of Identity</span></span>

<span data-ttu-id="b54c9-126">決定將用來登入裝置的身分識別類型。</span><span class="sxs-lookup"><span data-stu-id="b54c9-126">Determine the type of identity that will be used to sign into the device.</span></span>

1. <span data-ttu-id="b54c9-127">**本機帳戶：** 這個帳戶是在 windows PC 上的本機系統管理員帳戶) 的裝置 (。</span><span class="sxs-lookup"><span data-stu-id="b54c9-127">**Local Accounts:** This account is local to the device (like a local admin account on a windows PC).</span></span> <span data-ttu-id="b54c9-128">這將只允許1位使用者登入裝置。</span><span class="sxs-lookup"><span data-stu-id="b54c9-128">This will allow only 1 user to log into the device.</span></span>
2. <span data-ttu-id="b54c9-129">**MSA：** 這是個人帳戶 (例如 outlook、hotmail、gmail、yahoo 等。 ) 這將只允許1位使用者登入裝置。</span><span class="sxs-lookup"><span data-stu-id="b54c9-129">**MSA:** This is a personal account (like outlook, hotmail, gmail, yahoo, etc.) This will allow only 1 user to log into the device.</span></span>
3. <span data-ttu-id="b54c9-130">**Azure Active Directory (AZURE AD) 帳戶：** 這是在 Azure AD 中建立的帳戶。</span><span class="sxs-lookup"><span data-stu-id="b54c9-130">**Azure Active Directory (Azure AD) accounts:** This is an account created in Azure AD.</span></span> <span data-ttu-id="b54c9-131">這可讓您的公司能夠管理 HoloLens 裝置。</span><span class="sxs-lookup"><span data-stu-id="b54c9-131">This grants your corporation the ability to manage the HoloLens device.</span></span> <span data-ttu-id="b54c9-132">這可讓多個使用者登入 HoloLens 1 Gen 商業套件/HoloLens 2 裝置。</span><span class="sxs-lookup"><span data-stu-id="b54c9-132">This will allow multiple users to log into the HoloLens 1st Gen Commercial Suite/the HoloLens 2 device.</span></span>

<span data-ttu-id="b54c9-133">如需有關身分識別類型的詳細資訊，請造訪我們的[HoloLens 身分識別](hololens-identity.md)文章。</span><span class="sxs-lookup"><span data-stu-id="b54c9-133">For more detailed information about identity types, please visit our [HoloLens Identity](hololens-identity.md) article.</span></span>

### <span data-ttu-id="b54c9-134">功能類型</span><span class="sxs-lookup"><span data-stu-id="b54c9-134">Type of Features</span></span>

<span data-ttu-id="b54c9-135">您的功能需求將決定您需要哪一種 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="b54c9-135">Your feature requirements will determine which HoloLens you need.</span></span> <span data-ttu-id="b54c9-136">我們在客戶環境中經常部署的一個常見功能是 Kiosk 模式。</span><span class="sxs-lookup"><span data-stu-id="b54c9-136">One popular feature that we see deployed in customer environments frequently is Kiosk Mode.</span></span> <span data-ttu-id="b54c9-137">您可以在[此](hololens-commercial-features.md)找到 hololens 金鑰功能清單，以及支援這些功能的 hololens 版本。</span><span class="sxs-lookup"><span data-stu-id="b54c9-137">A list of HoloLens key features, and the editions of HoloLens that support them, can be found [here](hololens-commercial-features.md).</span></span>

**<span data-ttu-id="b54c9-138">何謂 Kiosk 模式？</span><span class="sxs-lookup"><span data-stu-id="b54c9-138">What is Kiosk Mode?</span></span>**

<span data-ttu-id="b54c9-139">Kiosk 模式是一種限制使用者有權存取之 app 的方式。</span><span class="sxs-lookup"><span data-stu-id="b54c9-139">Kiosk mode is a way to restrict the apps that a user has access to.</span></span> <span data-ttu-id="b54c9-140">這表示使用者只會被允許存取某些 app。</span><span class="sxs-lookup"><span data-stu-id="b54c9-140">This means that users will only be allowed to access certain apps.</span></span>

**<span data-ttu-id="b54c9-141">我需要哪些 Kiosk 模式？</span><span class="sxs-lookup"><span data-stu-id="b54c9-141">What Kiosk Mode do I require?</span></span>**

<span data-ttu-id="b54c9-142">展臺模式有兩種：單一 app 與多重 app。</span><span class="sxs-lookup"><span data-stu-id="b54c9-142">There are two types of Kiosk Modes: Single app and multi-app.</span></span> <span data-ttu-id="b54c9-143">單一 app kiosk 模式可讓使用者只存取一個 app，而多應用程式亭模式允許使用者存取多個指定的應用程式。</span><span class="sxs-lookup"><span data-stu-id="b54c9-143">Single app kiosk mode allows user to only access one app while multi-app kiosk mode allows users to access multiple, specified apps.</span></span> <span data-ttu-id="b54c9-144">若要判斷哪個 kiosk 模式適合貴公司，以下是需要解答的兩個問題：</span><span class="sxs-lookup"><span data-stu-id="b54c9-144">To determine which kiosk mode is right for your corporation, the following two questions need to be answered:</span></span>

1. **<span data-ttu-id="b54c9-145">不同的使用者需要不同的體驗/限制嗎？</span><span class="sxs-lookup"><span data-stu-id="b54c9-145">Do different users require different experiences/restrictions?</span></span>** <span data-ttu-id="b54c9-146">請考慮下列範例：使用者 A 是只需要存取遠端協助的現場服務工程師。</span><span class="sxs-lookup"><span data-stu-id="b54c9-146">Consider the following example: User A is a field service engineer who only needs access to Remote Assist.</span></span> <span data-ttu-id="b54c9-147">使用者 B 只需要存取輔助線的 trainee。</span><span class="sxs-lookup"><span data-stu-id="b54c9-147">User B is a trainee who only needs access to Guides.</span></span>
    1. <span data-ttu-id="b54c9-148">如果是，您將需要下列各項：</span><span class="sxs-lookup"><span data-stu-id="b54c9-148">If yes, you will require the following:</span></span>
        1. <span data-ttu-id="b54c9-149">[Azure AD 帳戶] 做為登入裝置的方法。</span><span class="sxs-lookup"><span data-stu-id="b54c9-149">Azure AD Accounts as the method of signing into the device.</span></span>
        1. <span data-ttu-id="b54c9-150">**多應用程式**亭模式。</span><span class="sxs-lookup"><span data-stu-id="b54c9-150">**Multi-app** kiosk mode.</span></span>
    1. <span data-ttu-id="b54c9-151">如果不是，請繼續執行問題二</span><span class="sxs-lookup"><span data-stu-id="b54c9-151">If no, continue to question two</span></span>
1. **<span data-ttu-id="b54c9-152">您是否需要多重應用程式體驗？</span><span class="sxs-lookup"><span data-stu-id="b54c9-152">Do you require a multi-app experience?</span></span>**
    1. <span data-ttu-id="b54c9-153">如果是，則需要**多個應用程式**站模式</span><span class="sxs-lookup"><span data-stu-id="b54c9-153">If yes, **Multi-app** kiosk is mode is needed</span></span>
    1. <span data-ttu-id="b54c9-154">如果您的問題1和2答案都不是，則可以使用**單 app** kiosk 模式</span><span class="sxs-lookup"><span data-stu-id="b54c9-154">If your answer to question 1 and 2 are both no, **single-app** kiosk mode can be used</span></span>

**<span data-ttu-id="b54c9-155">如何設定 Kiosk 模式：</span><span class="sxs-lookup"><span data-stu-id="b54c9-155">How to Configure Kiosk Mode:</span></span>**

<span data-ttu-id="b54c9-156">有兩種主要方式 ([置備套件](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)與[MDM](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)) 為 HoloLens 部署 kiosk 模式。</span><span class="sxs-lookup"><span data-stu-id="b54c9-156">There are two main ways ([provisioning packages](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) and [MDM](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)) to deploy kiosk mode for HoloLens.</span></span> <span data-ttu-id="b54c9-157">這些選項稍後會在檔中討論;不過，您可以使用上方的連結來跳至此檔中的個別章節。</span><span class="sxs-lookup"><span data-stu-id="b54c9-157">These options will be discussed later in the document; however, you can use the links above to jump to the respective sections in this doc.</span></span>

### <span data-ttu-id="b54c9-158">應用程式和 App 特定案例</span><span class="sxs-lookup"><span data-stu-id="b54c9-158">Apps and App Specific Scenarios</span></span>

<span data-ttu-id="b54c9-159">本檔中的大部分步驟也會套用至下列 app：</span><span class="sxs-lookup"><span data-stu-id="b54c9-159">The majority of the steps found in this document will also apply to the following apps:</span></span>

| <span data-ttu-id="b54c9-160">App</span><span class="sxs-lookup"><span data-stu-id="b54c9-160">App</span></span> | <span data-ttu-id="b54c9-161">App 特定案例</span><span class="sxs-lookup"><span data-stu-id="b54c9-161">App Specific Scenarios</span></span> |
| --- | --- |
| <span data-ttu-id="b54c9-162">遠端協助</span><span class="sxs-lookup"><span data-stu-id="b54c9-162">Remote Assist</span></span> | [<span data-ttu-id="b54c9-163">跨租使用者通訊</span><span class="sxs-lookup"><span data-stu-id="b54c9-163">Cross Tenant Communication</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview)|
| <span data-ttu-id="b54c9-164">指南</span><span class="sxs-lookup"><span data-stu-id="b54c9-164">Guides</span></span>  | *<span data-ttu-id="b54c9-165">即將推出</span><span class="sxs-lookup"><span data-stu-id="b54c9-165">Coming Soon</span></span>* |
|<span data-ttu-id="b54c9-166">自訂應用程式</span><span class="sxs-lookup"><span data-stu-id="b54c9-166">Custom Apps</span></span> | *<span data-ttu-id="b54c9-167">即將推出</span><span class="sxs-lookup"><span data-stu-id="b54c9-167">Coming Soon</span></span>* |

### <span data-ttu-id="b54c9-168">判斷您的註冊方法</span><span class="sxs-lookup"><span data-stu-id="b54c9-168">Determine your enrollment method</span></span>

1. <span data-ttu-id="b54c9-169">使用置備套件中的安全性權杖進行大量註冊。</span><span class="sxs-lookup"><span data-stu-id="b54c9-169">Bulk enrollment with a security token in a provisioning package.</span></span>  
  <span data-ttu-id="b54c9-170">[專業人員]：這是最自動化的方法 </span><span class="sxs-lookup"><span data-stu-id="b54c9-170">Pros: this is the most automated approach</span></span>\
  <span data-ttu-id="b54c9-171">缺點：使用初始伺服器端設定</span><span class="sxs-lookup"><span data-stu-id="b54c9-171">Cons: takes initial server-side setup</span></span>  
1. <span data-ttu-id="b54c9-172">自動登入使用者登入。</span><span class="sxs-lookup"><span data-stu-id="b54c9-172">Auto-enroll on user sign in.</span></span>  
  <span data-ttu-id="b54c9-173">專業人員：最簡單的方法</span><span class="sxs-lookup"><span data-stu-id="b54c9-173">Pros: easiest approach</span></span>  
  <span data-ttu-id="b54c9-174">缺點：在套用預配套件之後，使用者將需要完成設定</span><span class="sxs-lookup"><span data-stu-id="b54c9-174">Cons: users will need to complete set up after the provisioning package has been applied</span></span>
1. <span data-ttu-id="b54c9-175">_不建議_-手動註冊安裝後。</span><span class="sxs-lookup"><span data-stu-id="b54c9-175">_not recommended_ - Manually enroll post-setup.</span></span>  
  <span data-ttu-id="b54c9-176">[專業人員]：您可以在設定完成後進行登記</span><span class="sxs-lookup"><span data-stu-id="b54c9-176">Pros: possible to enroll after set up</span></span>  
  <span data-ttu-id="b54c9-177">缺點：在手動註冊前，大多數手動方法和裝置都不能集中管理。</span><span class="sxs-lookup"><span data-stu-id="b54c9-177">Cons: most manual approach and devices aren't centrally manageable until they're manually enrolled.</span></span>

  <span data-ttu-id="b54c9-178">您可以[在此](hololens-enroll-mdm.md)找到更多相關資訊</span><span class="sxs-lookup"><span data-stu-id="b54c9-178">More information can be found [here](hololens-enroll-mdm.md)</span></span>

### <span data-ttu-id="b54c9-179">判斷您是否需要建立預配套件</span><span class="sxs-lookup"><span data-stu-id="b54c9-179">Determine if you need to create a provisioning package</span></span>

<span data-ttu-id="b54c9-180">有兩種方法可以設定 HoloLens 裝置 (置備套件與 MDMs) 。</span><span class="sxs-lookup"><span data-stu-id="b54c9-180">There are two methods to configure a HoloLens device (Provisioning packages and MDMs).</span></span> <span data-ttu-id="b54c9-181">我們建議使用您的 MDM 來設定您的 HoloLens 裝置。</span><span class="sxs-lookup"><span data-stu-id="b54c9-181">We suggest using your MDM to configure you HoloLens device.</span></span> <span data-ttu-id="b54c9-182">不過，在某些情況下，使用預配套件是比較好的選擇：</span><span class="sxs-lookup"><span data-stu-id="b54c9-182">However, there are some scenarios where using a provisioning package is the better choice:</span></span>

1. <span data-ttu-id="b54c9-183">您想要將 HoloLens 設定為略過盒外體驗 (OOBE) </span><span class="sxs-lookup"><span data-stu-id="b54c9-183">You want to configure the HoloLens to skip the Out of Box Experience (OOBE)</span></span>
1. <span data-ttu-id="b54c9-184">在複雜的網路中部署憑證時遇到問題。</span><span class="sxs-lookup"><span data-stu-id="b54c9-184">You are having trouble deploying certificate in a complex network.</span></span> <span data-ttu-id="b54c9-185">即使在複雜的環境) 中，您還是可以使用 MDM (部署憑證。</span><span class="sxs-lookup"><span data-stu-id="b54c9-185">The majority of the time you can deploy certificates using MDM (even in complex environments).</span></span> <span data-ttu-id="b54c9-186">不過，某些情況需要透過預配套件來部署證書。</span><span class="sxs-lookup"><span data-stu-id="b54c9-186">However, some scenarios require certificates to be deployed through the provisioning package.</span></span>

<span data-ttu-id="b54c9-187">有些 HoloLens 設定可套用在佈建套件中︰</span><span class="sxs-lookup"><span data-stu-id="b54c9-187">Some of the HoloLens configurations you can apply in a provisioning package:</span></span>

- <span data-ttu-id="b54c9-188">將憑證套用到裝置</span><span class="sxs-lookup"><span data-stu-id="b54c9-188">Apply certificates to the device</span></span>
- <span data-ttu-id="b54c9-189">設定 Wi-Fi 連線</span><span class="sxs-lookup"><span data-stu-id="b54c9-189">Set up a Wi-Fi connection</span></span>
- <span data-ttu-id="b54c9-190">預先設定現成的問題，例如語言和地區設定</span><span class="sxs-lookup"><span data-stu-id="b54c9-190">Pre-configure out of box questions like language and locale</span></span>
- <span data-ttu-id="b54c9-191">(HoloLens 2) 大量註冊行動裝置管理</span><span class="sxs-lookup"><span data-stu-id="b54c9-191">(HoloLens 2) bulk enroll in mobile device management</span></span>
- <span data-ttu-id="b54c9-192">(HoloLens v1) 套用金鑰以啟用 Windows Holographic for Business</span><span class="sxs-lookup"><span data-stu-id="b54c9-192">(HoloLens v1) Apply key to enable Windows Holographic for Business</span></span>

<span data-ttu-id="b54c9-193">如果您決定使用預配套件，請依照[本指南](hololens-provisioning.md)進行。</span><span class="sxs-lookup"><span data-stu-id="b54c9-193">If you decide to use provisioning packages, follow [this guide](hololens-provisioning.md).</span></span>

## <span data-ttu-id="b54c9-194">取得支援</span><span class="sxs-lookup"><span data-stu-id="b54c9-194">Get support</span></span>

<span data-ttu-id="b54c9-195">透過 Microsoft 支援網站取得支援。</span><span class="sxs-lookup"><span data-stu-id="b54c9-195">Get support through the Microsoft support site.</span></span>

[<span data-ttu-id="b54c9-196">歸檔支援要求</span><span class="sxs-lookup"><span data-stu-id="b54c9-196">File a support request</span></span>](https://support.microsoft.com/supportforbusiness/productselection?sapid=e9391227-fa6d-927b-0fff-f96288631b8f)
