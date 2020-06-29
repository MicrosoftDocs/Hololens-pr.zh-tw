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
ms.openlocfilehash: 8aa8e0f679ad18a2e47f34c5f1233435a502dc0c
ms.sourcegitcommit: f3cda6c6b3bfb7ba4be5f4da66d8ed5b03ca807d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830127"
---
# <span data-ttu-id="6a4e5-103">在商業環境中部署 HoloLens</span><span class="sxs-lookup"><span data-stu-id="6a4e5-103">Deploy HoloLens in a commercial environment</span></span>

<span data-ttu-id="6a4e5-104">您可以在商業設定中，以縮放比例部署和設定 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="6a4e5-104">You can deploy and configure HoloLens at scale in a commercial setting.</span></span> <span data-ttu-id="6a4e5-105">本文提供在商業環境中部署 HoloLens 裝置的相關指示。</span><span class="sxs-lookup"><span data-stu-id="6a4e5-105">This article provides instructions for deploying HoloLens devices in a commercial environment.</span></span> <span data-ttu-id="6a4e5-106">本指南假設您基本熟悉 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="6a4e5-106">This guide assumes basic familiarity with HoloLens.</span></span> <span data-ttu-id="6a4e5-107">請依照[快速入門手冊](hololens1-setup.md)，第一次設定 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="6a4e5-107">Follow the [get started guide](hololens1-setup.md) to set up HoloLens for the first time.</span></span>

<span data-ttu-id="6a4e5-108">本檔也假設您的 HoloLens 已由安全小組評估為可在商業網路上使用的安全小組。</span><span class="sxs-lookup"><span data-stu-id="6a4e5-108">This document also assumes that the HoloLens has been evaluated by security teams as safe to use on the corporate network.</span></span> <span data-ttu-id="6a4e5-109">您可以[在此](hololens-faq-security.md)找到常見的安全性問題</span><span class="sxs-lookup"><span data-stu-id="6a4e5-109">Frequently asked security questions can be found [here](hololens-faq-security.md)</span></span>

## <span data-ttu-id="6a4e5-110">部署步驟概述</span><span class="sxs-lookup"><span data-stu-id="6a4e5-110">Overview of Deployment Steps</span></span>

1. [<span data-ttu-id="6a4e5-111">判斷您需要的功能</span><span class="sxs-lookup"><span data-stu-id="6a4e5-111">Determine what features you need</span></span>](hololens-requirements.md#step-1-determine-what-you-need)
1. [<span data-ttu-id="6a4e5-112">判斷您需要的授權</span><span class="sxs-lookup"><span data-stu-id="6a4e5-112">Determine what licenses you need</span></span>](hololens-licenses-requirements.md)
1. <span data-ttu-id="6a4e5-113">[針對 HoloLens 設定您的網路](hololens-commercial-infrastructure.md)。</span><span class="sxs-lookup"><span data-stu-id="6a4e5-113">[Configure your network for HoloLens](hololens-commercial-infrastructure.md).</span></span>
    1. <span data-ttu-id="6a4e5-114">本節包含需要在防火牆上允許的頻寬需求、URL 和埠;Azure AD 指南;行動裝置管理（MDM）指導方針;app 部署/管理指導方針;與證書指導方針。</span><span class="sxs-lookup"><span data-stu-id="6a4e5-114">This section includes bandwidth requirements, URL, and ports that need to be allowed on your firewall; Azure AD guidance; Mobile Device Management (MDM) Guidance; app deployment/management guidance; and certificate guidance.</span></span>
1. <span data-ttu-id="6a4e5-115">可選[使用預配套件設定 HoloLens](hololens-provisioning.md)</span><span class="sxs-lookup"><span data-stu-id="6a4e5-115">(Optional) [Configure HoloLens using a provisioning package](hololens-provisioning.md)</span></span>
1. [<span data-ttu-id="6a4e5-116">註冊裝置</span><span class="sxs-lookup"><span data-stu-id="6a4e5-116">Enroll Device</span></span>](hololens-enroll-mdm.md)
1. [<span data-ttu-id="6a4e5-117">設定 HoloLens 的通道步調更新</span><span class="sxs-lookup"><span data-stu-id="6a4e5-117">Set up ring based updates for HoloLens</span></span>](hololens-updates.md)
1. [<span data-ttu-id="6a4e5-118">針對 HoloLens 啟用 Bitlocker 裝置加密</span><span class="sxs-lookup"><span data-stu-id="6a4e5-118">Enable Bitlocker device encryption for HoloLens</span></span>](hololens-encryption.md)

## <span data-ttu-id="6a4e5-119">步驟 1.</span><span class="sxs-lookup"><span data-stu-id="6a4e5-119">Step 1.</span></span> <span data-ttu-id="6a4e5-120">判斷您需要的專案</span><span class="sxs-lookup"><span data-stu-id="6a4e5-120">Determine what you need</span></span>

<span data-ttu-id="6a4e5-121">在您的環境中部署 HoloLens 之前，請務必先判斷需要哪些功能、應用程式及身分識別類型。</span><span class="sxs-lookup"><span data-stu-id="6a4e5-121">Before deploying the HoloLens in your environment, it is important to first determine what features, apps, and type of identities are needed.</span></span> <span data-ttu-id="6a4e5-122">另外，請務必確保您的安全小組已在公司的網路上使用 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="6a4e5-122">It is also important to ensure that your security team has approved of the use of the HoloLens on the company's network.</span></span> <span data-ttu-id="6a4e5-123">如需其他安全性資訊，請參閱[經常詢問安全性問題](hololens-faq-security.md)。</span><span class="sxs-lookup"><span data-stu-id="6a4e5-123">Please see [Frequently ask security questions](hololens-faq-security.md) for additional security information.</span></span>

### <span data-ttu-id="6a4e5-124">身分識別類型</span><span class="sxs-lookup"><span data-stu-id="6a4e5-124">Type of Identity</span></span>

<span data-ttu-id="6a4e5-125">決定將用來登入裝置的身分識別類型。</span><span class="sxs-lookup"><span data-stu-id="6a4e5-125">Determine the type of identity that will be used to sign into the device.</span></span>

1. <span data-ttu-id="6a4e5-126">**本機帳戶：** 這個帳戶是裝置的本地帳戶（例如 windows 電腦上的本機系統管理員帳戶）。</span><span class="sxs-lookup"><span data-stu-id="6a4e5-126">**Local Accounts:** This account is local to the device (like a local admin account on a windows PC).</span></span> <span data-ttu-id="6a4e5-127">這將只允許1位使用者登入裝置。</span><span class="sxs-lookup"><span data-stu-id="6a4e5-127">This will allow only 1 user to log into the device.</span></span>
2. <span data-ttu-id="6a4e5-128">**MSA：** 這是個人帳戶（例如 outlook、hotmail、gmail、yahoo 等）。這將只允許1位使用者登入裝置。</span><span class="sxs-lookup"><span data-stu-id="6a4e5-128">**MSA:** This is a personal account (like outlook, hotmail, gmail, yahoo, etc.) This will allow only 1 user to log into the device.</span></span>
3. <span data-ttu-id="6a4e5-129">**Azure Active Directory （AZURE AD）帳戶：** 這是在 Azure AD 中建立的帳戶。</span><span class="sxs-lookup"><span data-stu-id="6a4e5-129">**Azure Active Directory (Azure AD) accounts:** This is an account created in Azure AD.</span></span> <span data-ttu-id="6a4e5-130">這可讓您的公司能夠管理 HoloLens 裝置。</span><span class="sxs-lookup"><span data-stu-id="6a4e5-130">This grants your corporation the ability to manage the HoloLens device.</span></span> <span data-ttu-id="6a4e5-131">這可讓多個使用者登入 HoloLens 1 Gen 商業套件/HoloLens 2 裝置。</span><span class="sxs-lookup"><span data-stu-id="6a4e5-131">This will allow multiple users to log into the HoloLens 1st Gen Commercial Suite/the HoloLens 2 device.</span></span>

<span data-ttu-id="6a4e5-132">如需有關身分識別類型的詳細資訊，請造訪我們的[HoloLens 身分識別](hololens-identity.md)文章。</span><span class="sxs-lookup"><span data-stu-id="6a4e5-132">For more detailed information about identity types, please visit our [HoloLens Identity](hololens-identity.md) article.</span></span>

### <span data-ttu-id="6a4e5-133">功能類型</span><span class="sxs-lookup"><span data-stu-id="6a4e5-133">Type of Features</span></span>

<span data-ttu-id="6a4e5-134">您的功能需求將決定您需要哪一種 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="6a4e5-134">Your feature requirements will determine which HoloLens you need.</span></span> <span data-ttu-id="6a4e5-135">我們在客戶環境中經常部署的一個常見功能是 Kiosk 模式。</span><span class="sxs-lookup"><span data-stu-id="6a4e5-135">One popular feature that we see deployed in customer environments frequently is Kiosk Mode.</span></span> <span data-ttu-id="6a4e5-136">您可以在[此](hololens-commercial-features.md)找到 hololens 金鑰功能清單，以及支援這些功能的 hololens 版本。</span><span class="sxs-lookup"><span data-stu-id="6a4e5-136">A list of HoloLens key features, and the editions of HoloLens that support them, can be found [here](hololens-commercial-features.md).</span></span>

**<span data-ttu-id="6a4e5-137">何謂 Kiosk 模式？</span><span class="sxs-lookup"><span data-stu-id="6a4e5-137">What is Kiosk Mode?</span></span>**

<span data-ttu-id="6a4e5-138">Kiosk 模式是一種限制使用者有權存取之 app 的方式。</span><span class="sxs-lookup"><span data-stu-id="6a4e5-138">Kiosk mode is a way to restrict the apps that a user has access to.</span></span> <span data-ttu-id="6a4e5-139">這表示使用者只會被允許存取某些 app。</span><span class="sxs-lookup"><span data-stu-id="6a4e5-139">This means that users will only be allowed to access certain apps.</span></span>

**<span data-ttu-id="6a4e5-140">我需要哪些 Kiosk 模式？</span><span class="sxs-lookup"><span data-stu-id="6a4e5-140">What Kiosk Mode do I require?</span></span>**

<span data-ttu-id="6a4e5-141">展臺模式有兩種：單一 app 與多重 app。</span><span class="sxs-lookup"><span data-stu-id="6a4e5-141">There are two types of Kiosk Modes: Single app and multi-app.</span></span> <span data-ttu-id="6a4e5-142">單一 app kiosk 模式可讓使用者只存取一個 app，而多應用程式亭模式允許使用者存取多個指定的應用程式。</span><span class="sxs-lookup"><span data-stu-id="6a4e5-142">Single app kiosk mode allows user to only access one app while multi-app kiosk mode allows users to access multiple, specified apps.</span></span> <span data-ttu-id="6a4e5-143">若要判斷哪個 kiosk 模式適合貴公司，以下是需要解答的兩個問題：</span><span class="sxs-lookup"><span data-stu-id="6a4e5-143">To determine which kiosk mode is right for your corporation, the following two questions need to be answered:</span></span>

1. **<span data-ttu-id="6a4e5-144">不同的使用者需要不同的體驗/限制嗎？</span><span class="sxs-lookup"><span data-stu-id="6a4e5-144">Do different users require different experiences/restrictions?</span></span>** <span data-ttu-id="6a4e5-145">請考慮下列範例：使用者 A 是只需要存取遠端協助的現場服務工程師。</span><span class="sxs-lookup"><span data-stu-id="6a4e5-145">Consider the following example: User A is a field service engineer who only needs access to Remote Assist.</span></span> <span data-ttu-id="6a4e5-146">使用者 B 只需要存取輔助線的 trainee。</span><span class="sxs-lookup"><span data-stu-id="6a4e5-146">User B is a trainee who only needs access to Guides.</span></span>
    1. <span data-ttu-id="6a4e5-147">如果是，您將需要下列各項：</span><span class="sxs-lookup"><span data-stu-id="6a4e5-147">If yes, you will require the following:</span></span>
        1. <span data-ttu-id="6a4e5-148">[Azure AD 帳戶] 做為登入裝置的方法。</span><span class="sxs-lookup"><span data-stu-id="6a4e5-148">Azure AD Accounts as the method of signing into the device.</span></span>
        1. <span data-ttu-id="6a4e5-149">**多應用程式**亭模式。</span><span class="sxs-lookup"><span data-stu-id="6a4e5-149">**Multi-app** kiosk mode.</span></span>
    1. <span data-ttu-id="6a4e5-150">如果不是，請繼續執行問題二</span><span class="sxs-lookup"><span data-stu-id="6a4e5-150">If no, continue to question two</span></span>
1. **<span data-ttu-id="6a4e5-151">您是否需要多重應用程式體驗？</span><span class="sxs-lookup"><span data-stu-id="6a4e5-151">Do you require a multi-app experience?</span></span>**
    1. <span data-ttu-id="6a4e5-152">如果是，則需要**多個應用程式**站模式</span><span class="sxs-lookup"><span data-stu-id="6a4e5-152">If yes, **Multi-app** kiosk is mode is needed</span></span>
    1. <span data-ttu-id="6a4e5-153">如果您的問題1和2答案都不是，則可以使用**單 app** kiosk 模式</span><span class="sxs-lookup"><span data-stu-id="6a4e5-153">If your answer to question 1 and 2 are both no, **single-app** kiosk mode can be used</span></span>

**<span data-ttu-id="6a4e5-154">如何設定 Kiosk 模式：</span><span class="sxs-lookup"><span data-stu-id="6a4e5-154">How to Configure Kiosk Mode:</span></span>**

<span data-ttu-id="6a4e5-155">您可以透過兩種主要方式（[配套件](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)與[MDM](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)）來部署 HoloLens 的 kiosk 模式。</span><span class="sxs-lookup"><span data-stu-id="6a4e5-155">There are two main ways ([provisioning packages](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) and [MDM](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)) to deploy kiosk mode for HoloLens.</span></span> <span data-ttu-id="6a4e5-156">這些選項稍後會在檔中討論;不過，您可以使用上方的連結來跳至此檔中的個別章節。</span><span class="sxs-lookup"><span data-stu-id="6a4e5-156">These options will be discussed later in the document; however, you can use the links above to jump to the respective sections in this doc.</span></span>

### <span data-ttu-id="6a4e5-157">應用程式和 App 特定案例</span><span class="sxs-lookup"><span data-stu-id="6a4e5-157">Apps and App Specific Scenarios</span></span>

<span data-ttu-id="6a4e5-158">本檔中的大部分步驟也會套用至下列 app：</span><span class="sxs-lookup"><span data-stu-id="6a4e5-158">The majority of the steps found in this document will also apply to the following apps:</span></span>

| <span data-ttu-id="6a4e5-159">App</span><span class="sxs-lookup"><span data-stu-id="6a4e5-159">App</span></span> | <span data-ttu-id="6a4e5-160">App 特定案例</span><span class="sxs-lookup"><span data-stu-id="6a4e5-160">App Specific Scenarios</span></span> |
| --- | --- |
| <span data-ttu-id="6a4e5-161">遠端協助</span><span class="sxs-lookup"><span data-stu-id="6a4e5-161">Remote Assist</span></span> | [<span data-ttu-id="6a4e5-162">跨租使用者通訊</span><span class="sxs-lookup"><span data-stu-id="6a4e5-162">Cross Tenant Communication</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview)|
| <span data-ttu-id="6a4e5-163">指南</span><span class="sxs-lookup"><span data-stu-id="6a4e5-163">Guides</span></span>  | *<span data-ttu-id="6a4e5-164">即將推出</span><span class="sxs-lookup"><span data-stu-id="6a4e5-164">Coming Soon</span></span>* |
|<span data-ttu-id="6a4e5-165">自訂應用程式</span><span class="sxs-lookup"><span data-stu-id="6a4e5-165">Custom Apps</span></span> | *<span data-ttu-id="6a4e5-166">即將推出</span><span class="sxs-lookup"><span data-stu-id="6a4e5-166">Coming Soon</span></span>* |

### <span data-ttu-id="6a4e5-167">判斷您的註冊方法</span><span class="sxs-lookup"><span data-stu-id="6a4e5-167">Determine your enrollment method</span></span>

1. <span data-ttu-id="6a4e5-168">使用置備套件中的安全性權杖進行大量註冊。</span><span class="sxs-lookup"><span data-stu-id="6a4e5-168">Bulk enrollment with a security token in a provisioning package.</span></span>  
  <span data-ttu-id="6a4e5-169">[專業人員]：這是最自動化的方法 </span><span class="sxs-lookup"><span data-stu-id="6a4e5-169">Pros: this is the most automated approach</span></span>\
  <span data-ttu-id="6a4e5-170">缺點：使用初始伺服器端設定</span><span class="sxs-lookup"><span data-stu-id="6a4e5-170">Cons: takes initial server-side setup</span></span>  
1. <span data-ttu-id="6a4e5-171">自動登入使用者登入。</span><span class="sxs-lookup"><span data-stu-id="6a4e5-171">Auto-enroll on user sign in.</span></span>  
  <span data-ttu-id="6a4e5-172">專業人員：最簡單的方法</span><span class="sxs-lookup"><span data-stu-id="6a4e5-172">Pros: easiest approach</span></span>  
  <span data-ttu-id="6a4e5-173">缺點：在套用預配套件之後，使用者將需要完成設定</span><span class="sxs-lookup"><span data-stu-id="6a4e5-173">Cons: users will need to complete set up after the provisioning package has been applied</span></span>
1. <span data-ttu-id="6a4e5-174">_不建議_-手動註冊安裝後。</span><span class="sxs-lookup"><span data-stu-id="6a4e5-174">_not recommended_ - Manually enroll post-setup.</span></span>  
  <span data-ttu-id="6a4e5-175">[專業人員]：您可以在設定完成後進行登記</span><span class="sxs-lookup"><span data-stu-id="6a4e5-175">Pros: possible to enroll after set up</span></span>  
  <span data-ttu-id="6a4e5-176">缺點：在手動註冊前，大多數手動方法和裝置都不能集中管理。</span><span class="sxs-lookup"><span data-stu-id="6a4e5-176">Cons: most manual approach and devices aren't centrally manageable until they're manually enrolled.</span></span>

  <span data-ttu-id="6a4e5-177">您可以[在此](hololens-enroll-mdm.md)找到更多相關資訊</span><span class="sxs-lookup"><span data-stu-id="6a4e5-177">More information can be found [here](hololens-enroll-mdm.md)</span></span>

### <span data-ttu-id="6a4e5-178">判斷您是否需要建立預配套件</span><span class="sxs-lookup"><span data-stu-id="6a4e5-178">Determine if you need to create a provisioning package</span></span>

<span data-ttu-id="6a4e5-179">有兩種方法可以設定 HoloLens 裝置（配套件與 MDMs）。</span><span class="sxs-lookup"><span data-stu-id="6a4e5-179">There are two methods to configure a HoloLens device (Provisioning packages and MDMs).</span></span> <span data-ttu-id="6a4e5-180">我們建議使用您的 MDM 來設定您的 HoloLens 裝置。</span><span class="sxs-lookup"><span data-stu-id="6a4e5-180">We suggest using your MDM to configure you HoloLens device.</span></span> <span data-ttu-id="6a4e5-181">不過，在某些情況下，使用預配套件是比較好的選擇：</span><span class="sxs-lookup"><span data-stu-id="6a4e5-181">However, there are some scenarios where using a provisioning package is the better choice:</span></span>

1. <span data-ttu-id="6a4e5-182">您想要設定 HoloLens 以略過盒外體驗（OOBE）</span><span class="sxs-lookup"><span data-stu-id="6a4e5-182">You want to configure the HoloLens to skip the Out of Box Experience (OOBE)</span></span>
1. <span data-ttu-id="6a4e5-183">在複雜的網路中部署憑證時遇到問題。</span><span class="sxs-lookup"><span data-stu-id="6a4e5-183">You are having trouble deploying certificate in a complex network.</span></span> <span data-ttu-id="6a4e5-184">您可以在大部分時間使用 MDM 部署憑證（即使在複雜的環境中也一樣）。</span><span class="sxs-lookup"><span data-stu-id="6a4e5-184">The majority of the time you can deploy certificates using MDM (even in complex environments).</span></span> <span data-ttu-id="6a4e5-185">不過，某些情況需要透過預配套件來部署證書。</span><span class="sxs-lookup"><span data-stu-id="6a4e5-185">However, some scenarios require certificates to be deployed through the provisioning package.</span></span>

<span data-ttu-id="6a4e5-186">有些 HoloLens 設定可套用在佈建套件中︰</span><span class="sxs-lookup"><span data-stu-id="6a4e5-186">Some of the HoloLens configurations you can apply in a provisioning package:</span></span>

- <span data-ttu-id="6a4e5-187">將憑證套用到裝置</span><span class="sxs-lookup"><span data-stu-id="6a4e5-187">Apply certificates to the device</span></span>
- <span data-ttu-id="6a4e5-188">設定 Wi-Fi 連線</span><span class="sxs-lookup"><span data-stu-id="6a4e5-188">Set up a Wi-Fi connection</span></span>
- <span data-ttu-id="6a4e5-189">預先設定現成的問題，例如語言和地區設定</span><span class="sxs-lookup"><span data-stu-id="6a4e5-189">Pre-configure out of box questions like language and locale</span></span>
- <span data-ttu-id="6a4e5-190">(HoloLens 2) 大量註冊行動裝置管理</span><span class="sxs-lookup"><span data-stu-id="6a4e5-190">(HoloLens 2) bulk enroll in mobile device management</span></span>
- <span data-ttu-id="6a4e5-191">(HoloLens v1) 套用金鑰以啟用 Windows Holographic for Business</span><span class="sxs-lookup"><span data-stu-id="6a4e5-191">(HoloLens v1) Apply key to enable Windows Holographic for Business</span></span>

<span data-ttu-id="6a4e5-192">如果您決定使用預配套件，請依照[本指南](hololens-provisioning.md)進行。</span><span class="sxs-lookup"><span data-stu-id="6a4e5-192">If you decide to use provisioning packages, follow [this guide](hololens-provisioning.md).</span></span>

## <span data-ttu-id="6a4e5-193">取得支援</span><span class="sxs-lookup"><span data-stu-id="6a4e5-193">Get support</span></span>

<span data-ttu-id="6a4e5-194">透過 Microsoft 支援網站取得支援。</span><span class="sxs-lookup"><span data-stu-id="6a4e5-194">Get support through the Microsoft support site.</span></span>

[<span data-ttu-id="6a4e5-195">歸檔支援要求</span><span class="sxs-lookup"><span data-stu-id="6a4e5-195">File a support request</span></span>](https://support.microsoft.com/supportforbusiness/productselection?sapid=e9391227-fa6d-927b-0fff-f96288631b8f)
