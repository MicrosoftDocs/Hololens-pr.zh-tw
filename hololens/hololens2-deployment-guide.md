---
title: 外部用戶端部署指南
description: '使用遠端協助執行外部用戶端的 HoloLens 2 (指南，做為範例) '
ms.prod: hololens
ms.sitesec: library
author: pawinfie
ms.author: pawinfie
ms.topic: article
ms.localizationpriority: medium
ms.date: 1/12/2021
ms.custom: ''
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 56930ceea05cd5713b9c7eb57e0967a9d0cd4988
ms.sourcegitcommit: fbc8ddb17e31fea8667ece43a511592b86ac3947
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/04/2021
ms.locfileid: "11385586"
---
# <a name="deploying-hololens-2-to-external-clients-with-remote-assist"></a><span data-ttu-id="bf31f-103">使用遠端協助將 HoloLens 2 部署到外部用戶端</span><span class="sxs-lookup"><span data-stu-id="bf31f-103">Deploying HoloLens 2 to External Clients with Remote Assist</span></span>

<span data-ttu-id="bf31f-104">本指南可協助 IT 專業人員在組織中部署 Microsoft HoloLens 2 裝置，目標如下：</span><span class="sxs-lookup"><span data-stu-id="bf31f-104">This guide helps IT professionals with the following goals deploy Microsoft HoloLens 2 devices in their organization:</span></span>

1. <span data-ttu-id="bf31f-105">雲端連接 HoloLens 2 裝置</span><span class="sxs-lookup"><span data-stu-id="bf31f-105">Cloud connect HoloLens 2 devices</span></span>
1. <span data-ttu-id="bf31f-106">將 HoloLens 2 裝置貸款給外部客戶使用</span><span class="sxs-lookup"><span data-stu-id="bf31f-106">Loan HoloLens 2 devices to external clients for use</span></span>
1. <span data-ttu-id="bf31f-107">安全貸款的裝置</span><span class="sxs-lookup"><span data-stu-id="bf31f-107">Secure loaned devices</span></span>

<span data-ttu-id="bf31f-108">本指南將提供一般[HoloLens 2](#general-deployment-recommendations-and-instructions)部署建議，這些建議適用于大多數 HoloLens 2 部署[](#common-concerns)案例，以及客戶在部署外部使用遠端協助時常見的疑慮。</span><span class="sxs-lookup"><span data-stu-id="bf31f-108">This guide will provide [general HoloLens 2 deployment recommendations](#general-deployment-recommendations-and-instructions) that is applicable to most HoloLens 2 deployment scenarios and [common concerns](#common-concerns) that customers have when deploying Remote Assist for external use.</span></span>

## <a name="scenario-description"></a><span data-ttu-id="bf31f-109">案例描述</span><span class="sxs-lookup"><span data-stu-id="bf31f-109">Scenario Description</span></span>

<span data-ttu-id="bf31f-110">基於本檔的目的，Contoso Company 想要將 HoloLens 2 裝置運送至外部用戶端的植物，以便短期或長期使用。</span><span class="sxs-lookup"><span data-stu-id="bf31f-110">For the purpose of this document, Contoso Company wants to ship a HoloLens 2 device to an external client's plant for short-term or long-term use.</span></span> <span data-ttu-id="bf31f-111">當客戶需要維修機器的協助時，客戶會使用 Contoso Company 提供的認證登入 HoloLens 2 裝置，並使用遠端協助連至 Contoso 公司的專家。</span><span class="sxs-lookup"><span data-stu-id="bf31f-111">When the client needs assistance servicing machinery, the client will log into the HoloLens 2 device using credentials provided by Contoso Company and use Remote Assist to contact Contoso Company's experts.</span></span>

<span data-ttu-id="bf31f-112">在這裡深入瞭解遠端 [協助](https://docs.microsoft.com/hololens/hololens2-cloud-connected-overview#learn-about-remote-assist)。</span><span class="sxs-lookup"><span data-stu-id="bf31f-112">Learn more about Remote Assist [here](https://docs.microsoft.com/hololens/hololens2-cloud-connected-overview#learn-about-remote-assist).</span></span>

### <a name="requirements-for-this-scenario"></a><span data-ttu-id="bf31f-113">此案例的需求</span><span class="sxs-lookup"><span data-stu-id="bf31f-113">Requirements for this Scenario</span></span>

1. [<span data-ttu-id="bf31f-114">Azure AD</span><span class="sxs-lookup"><span data-stu-id="bf31f-114">Azure AD</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)
1. <span data-ttu-id="bf31f-115">行動裝置管理器 - 例如 [Intune](https://docs.microsoft.com/mem/intune/fundamentals/free-trial-sign-up)</span><span class="sxs-lookup"><span data-stu-id="bf31f-115">Mobile Device Manager - such as [Intune](https://docs.microsoft.com/mem/intune/fundamentals/free-trial-sign-up)</span></span>
1. <span data-ttu-id="bf31f-116">遠端協助授權</span><span class="sxs-lookup"><span data-stu-id="bf31f-116">Remote Assist License</span></span>
    1. [<span data-ttu-id="bf31f-117">購買遠端輔助</span><span class="sxs-lookup"><span data-stu-id="bf31f-117">Buy Remote Assist</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-remote-assist)
    1. [<span data-ttu-id="bf31f-118">試用遠端協助</span><span class="sxs-lookup"><span data-stu-id="bf31f-118">Trial Remote Assist</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)

## <a name="common-concerns"></a><span data-ttu-id="bf31f-119">常見問題</span><span class="sxs-lookup"><span data-stu-id="bf31f-119">Common Concerns</span></span>

- [<span data-ttu-id="bf31f-120">如何確保外部用戶端無法彼此通訊</span><span class="sxs-lookup"><span data-stu-id="bf31f-120">How to ensure that external clients do not have the ability to communicate with one another</span></span>](#how-to-ensure-that-external-clients-do-not-have-the-ability-to-communicate-with-one-another)
- [<span data-ttu-id="bf31f-121">如何確保用戶端無法存取公司資源</span><span class="sxs-lookup"><span data-stu-id="bf31f-121">How to ensure that clients do not have access to company resources</span></span>](#how-to-ensure-that-clients-do-not-have-access-to-company-resources)
- [<span data-ttu-id="bf31f-122">如何限制應用程式</span><span class="sxs-lookup"><span data-stu-id="bf31f-122">How to restrict apps</span></span>](#how-to-restrict-apps)
- [<span data-ttu-id="bf31f-123">如何管理密碼</span><span class="sxs-lookup"><span data-stu-id="bf31f-123">How to manage passwords</span></span>](#how-to-manage-passwords)
- [<span data-ttu-id="bf31f-124">如何確保用戶端無法存取聊天記錄</span><span class="sxs-lookup"><span data-stu-id="bf31f-124">How to ensure that clients do not have access to chat history</span></span>](#how-to-ensure-that-clients-do-not-have-access-to-chat-history)

### <a name="how-to-ensure-that-external-clients-do-not-have-the-ability-to-communicate-with-one-another"></a><span data-ttu-id="bf31f-125">如何確保外部用戶端無法彼此通訊</span><span class="sxs-lookup"><span data-stu-id="bf31f-125">How to ensure that external clients do not have the ability to communicate with one another</span></span>

<span data-ttu-id="bf31f-126">由於不支援遠端輔助 HoloLens 到 HoloLens 通話，因此用戶端可以搜尋但無法彼此通訊。</span><span class="sxs-lookup"><span data-stu-id="bf31f-126">Since Remote Assist HoloLens to HoloLens calls are not supported, clients are able to search for, but are unable to, communicate with one another.</span></span> <span data-ttu-id="bf31f-127">若要進一步限制可搜尋和通話的用戶端[](https://docs.microsoft.com/microsoft-365/compliance/information-barriers?view=o365-worldwide)，資訊障礙可以限制用戶端可以與誰通訊。</span><span class="sxs-lookup"><span data-stu-id="bf31f-127">To further restrict who clients can search for and call,  [Information barriers](https://docs.microsoft.com/microsoft-365/compliance/information-barriers?view=o365-worldwide) can restrict who a client can communicate with.</span></span> <span data-ttu-id="bf31f-128">另一個要考慮的選項是使用 [範圍目錄搜尋](https://docs.microsoft.com/MicrosoftTeams/teams-scoped-directory-search)</span><span class="sxs-lookup"><span data-stu-id="bf31f-128">Another option to consider is using [Scoped Directory Search](https://docs.microsoft.com/MicrosoftTeams/teams-scoped-directory-search)</span></span>

 > [!NOTE]
> <span data-ttu-id="bf31f-129">由於已啟用單一登入，因此使用 [**WDAC**](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)停用瀏覽器非常重要。</span><span class="sxs-lookup"><span data-stu-id="bf31f-129">Since single sign on is enabled, it is important to disable the browser using [**WDAC**](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac).</span></span> <span data-ttu-id="bf31f-130">如果外部用戶端開啟瀏覽器並使用 Teams 網頁版，用戶端將可存取通話/聊天記錄。</span><span class="sxs-lookup"><span data-stu-id="bf31f-130">If an external client opens the browser and uses the web version of Teams, the client will have access to call/chat history.</span></span>

### <a name="how-to-ensure-that-clients-do-not-have-access-to-company-resources"></a><span data-ttu-id="bf31f-131">如何確保用戶端無法存取公司資源</span><span class="sxs-lookup"><span data-stu-id="bf31f-131">How to ensure that clients do not have access to company resources</span></span>

<span data-ttu-id="bf31f-132">有兩個選項需要考慮。</span><span class="sxs-lookup"><span data-stu-id="bf31f-132">There are two options to consider.</span></span>

<span data-ttu-id="bf31f-133">第一個選項是多層次方法：</span><span class="sxs-lookup"><span data-stu-id="bf31f-133">The first option is a multi-layer approach:</span></span>

1. <span data-ttu-id="bf31f-134">只指派使用者所需的授權。</span><span class="sxs-lookup"><span data-stu-id="bf31f-134">Only assign licenses that the user requires.</span></span> <span data-ttu-id="bf31f-135">如果您未將 OneDrive、Outlook、SharePoint、Yammer 等指派給使用者，他/她將無法存取這些資源。</span><span class="sxs-lookup"><span data-stu-id="bf31f-135">If you do not assign OneDrive, Outlook, SharePoint, Yammer, etc. to the user, he/she will not have access to those resources.</span></span> <span data-ttu-id="bf31f-136">使用者只需要遠端協助、Intune 和 AAD 授權才能開始。</span><span class="sxs-lookup"><span data-stu-id="bf31f-136">The only licenses the users will need is Remote Assist, Intune, and AAD licenses to begin.</span></span>
1. <span data-ttu-id="bf31f-137">封鎖 (應用程式，) 您不希望用戶端存取的電子郵件 (請參閱如何限制應用程式) 。 [](#how-to-restrict-apps)</span><span class="sxs-lookup"><span data-stu-id="bf31f-137">Block apps (such as email) that you don’t want clients to access (See [How to restrict apps](#how-to-restrict-apps)).</span></span>
1. <span data-ttu-id="bf31f-138">請勿與客戶共用使用者名稱或密碼。</span><span class="sxs-lookup"><span data-stu-id="bf31f-138">Do NOT share usernames nor password with clients.</span></span> <span data-ttu-id="bf31f-139">若要登入 HoloLens 2，需要電子郵件和數值 PIN。</span><span class="sxs-lookup"><span data-stu-id="bf31f-139">To log into the HoloLens 2, an email and numerical PIN is required.</span></span>

<span data-ttu-id="bf31f-140">第二個選項是建立託管用戶端的個別租使用者， (圖像 1.1) 。</span><span class="sxs-lookup"><span data-stu-id="bf31f-140">The second option is to create a separate tenant that hosts clients (see Image 1.1).</span></span>

**<span data-ttu-id="bf31f-141">影像 1.1</span><span class="sxs-lookup"><span data-stu-id="bf31f-141">Image 1.1</span></span>**

![服務租使用者圖像](./images/hololens-service-tenant-image.png)

### <a name="how-to-restrict-apps"></a><span data-ttu-id="bf31f-143">如何限制應用程式</span><span class="sxs-lookup"><span data-stu-id="bf31f-143">How to restrict apps</span></span>

<span data-ttu-id="bf31f-144">[Kiosk 模式](https://docs.microsoft.com/hololens/hololens-kiosk) 和/或 [WDAC (Windows Defender 應用程式控制) ](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) 是限制應用程式的選項。</span><span class="sxs-lookup"><span data-stu-id="bf31f-144">[Kiosk Mode](https://docs.microsoft.com/hololens/hololens-kiosk) and/or [WDAC (Windows Defender Application Control)](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) are options for restricting applications.</span></span>

### <a name="how-to-manage-passwords"></a><span data-ttu-id="bf31f-145">如何管理密碼</span><span class="sxs-lookup"><span data-stu-id="bf31f-145">How to manage passwords</span></span>

1. <span data-ttu-id="bf31f-146">移除密碼到期。</span><span class="sxs-lookup"><span data-stu-id="bf31f-146">Remove password expiration.</span></span> <span data-ttu-id="bf31f-147">不過，這會增加帳戶遭到入侵的可能性。</span><span class="sxs-lookup"><span data-stu-id="bf31f-147">However, this increases the chance that that an account will be compromised.</span></span> <span data-ttu-id="bf31f-148">NIST 密碼建議是每 30-90 天變更密碼一次。</span><span class="sxs-lookup"><span data-stu-id="bf31f-148">NIST password recommendation is change passwords every 30-90 days.</span></span>
1. <span data-ttu-id="bf31f-149">將 HoloLens 2 裝置的密碼過期延長超過 90 天。</span><span class="sxs-lookup"><span data-stu-id="bf31f-149">Extend the password expiration for HoloLens 2 devices to exceed 90 days.</span></span>
1. <span data-ttu-id="bf31f-150">裝置應該會回到 Contoso 以變更密碼。</span><span class="sxs-lookup"><span data-stu-id="bf31f-150">The devices should be returned to Contoso to change the passwords.</span></span> <span data-ttu-id="bf31f-151">不過，如果裝置預計會位在用戶端工廠 90 天以上，則可能會導致問題。</span><span class="sxs-lookup"><span data-stu-id="bf31f-151">However, this can cause issues if the devices are expected to be in the client's plant for 90+ days.</span></span>  
1. <span data-ttu-id="bf31f-152">針對要寄送給多個用戶端的裝置，在將裝置寄送至用戶端之前，請重設密碼。</span><span class="sxs-lookup"><span data-stu-id="bf31f-152">For devices that are sent to multiple clients, reset passwords before shipping the device to clients.</span></span>

### <a name="how-to-ensure-that-clients-do-not-have-access-to-chat-history"></a><span data-ttu-id="bf31f-153">如何確保用戶端無法存取聊天記錄</span><span class="sxs-lookup"><span data-stu-id="bf31f-153">How to ensure that clients do not have access to chat history</span></span>

<span data-ttu-id="bf31f-154">遠端協助會在每個會話後清除聊天記錄。</span><span class="sxs-lookup"><span data-stu-id="bf31f-154">Remote Assist clears chat history after each session.</span></span> <span data-ttu-id="bf31f-155">不過，Microsoft Teams 使用者可以使用聊天記錄。</span><span class="sxs-lookup"><span data-stu-id="bf31f-155">However, the chat history will be available for the Microsoft Teams user.</span></span>

> [!NOTE]
> <span data-ttu-id="bf31f-156">由於已啟用單一登入，因此使用 [**WDAC**](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)停用瀏覽器非常重要。</span><span class="sxs-lookup"><span data-stu-id="bf31f-156">Since single sign on is enabled, it is important to disable the browser using [**WDAC**](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac).</span></span> <span data-ttu-id="bf31f-157">如果外部用戶端開啟瀏覽器並使用 Teams 網頁版，用戶端將可存取通話/聊天記錄。</span><span class="sxs-lookup"><span data-stu-id="bf31f-157">If a external client opens the browser and uses the web version of Teams, the client will have access to call/chat history.</span></span>

## <a name="general-deployment-recommendations-and-instructions"></a><span data-ttu-id="bf31f-158">一般部署建議與指示</span><span class="sxs-lookup"><span data-stu-id="bf31f-158">General Deployment Recommendations and Instructions</span></span>

<span data-ttu-id="bf31f-159">我們建議您針對 HoloLens 2 部署步驟執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="bf31f-159">We recommend the following for HoloLens 2 deployment Steps:</span></span>

1. <span data-ttu-id="bf31f-160">使用 [最新的 HoloLens OS 版本](https://aka.ms/hololens2download) 做為比較基準的建立。</span><span class="sxs-lookup"><span data-stu-id="bf31f-160">Use the [latest HoloLens OS release](https://aka.ms/hololens2download) as your baseline build.</span></span>
1. <span data-ttu-id="bf31f-161">指派使用者型或裝置型授權：</span><span class="sxs-lookup"><span data-stu-id="bf31f-161">Assign user-based or device-based licenses:</span></span>
    1. <span data-ttu-id="bf31f-162">使用者型和裝置型授權都遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="bf31f-162">User-based and device-based licenses both follow the following steps:</span></span>
        1. <span data-ttu-id="bf31f-163">[在 AAD 中建立群組，並新增](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal#create-a-basic-group-and-add-members) HoloLens/RA 使用者的成員。</span><span class="sxs-lookup"><span data-stu-id="bf31f-163">[Create a group in AAD and add members](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal#create-a-basic-group-and-add-members) for HoloLens/RA users.</span></span>
        1. <span data-ttu-id="bf31f-164">[指派裝置型或使用者型](https://docs.microsoft.com/azure/active-directory/enterprise-users/licensing-groups-assign#:~:text=In%20this%20article%201%20Assign%20the%20required%20licenses,3%20Check%20for%20license%20problems%20and%20resolve%20them) 授權給此群組。</span><span class="sxs-lookup"><span data-stu-id="bf31f-164">[Assign device-based or user-based licenses](https://docs.microsoft.com/azure/active-directory/enterprise-users/licensing-groups-assign#:~:text=In%20this%20article%201%20Assign%20the%20required%20licenses,3%20Check%20for%20license%20problems%20and%20resolve%20them) to this group.</span></span>
        1. <span data-ttu-id="bf31f-165"> (選擇性) 您可以針對 MDM 策略的目標群組。</span><span class="sxs-lookup"><span data-stu-id="bf31f-165">(Optional) You can target groups for MDM policies.</span></span>

1. <span data-ttu-id="bf31f-166">裝置應該會加入您的租使用者、自動 [註冊](https://docs.microsoft.com/hololens/hololens-enroll-mdm#auto-enrollment-in-mdm)，並透過自動試驗 [進行安裝](https://docs.microsoft.com/hololens/hololens2-autopilot)。</span><span class="sxs-lookup"><span data-stu-id="bf31f-166">Devices should be AAD joined to your tenant, [Auto Enrolled](https://docs.microsoft.com/hololens/hololens-enroll-mdm#auto-enrollment-in-mdm), and configured through [Auto Pilot](https://docs.microsoft.com/hololens/hololens2-autopilot).</span></span>
    1. <span data-ttu-id="bf31f-167">請注意，裝置上的第一個使用者就是裝置擁有者。</span><span class="sxs-lookup"><span data-stu-id="bf31f-167">Please note that the first user on the device will be the device owner.</span></span>
    1. <span data-ttu-id="bf31f-168">請注意，如果裝置已加入 AAD，則執行加入的使用者即為裝置擁有者。</span><span class="sxs-lookup"><span data-stu-id="bf31f-168">Please note that if the device is AAD joined, the user that performed the join is made device owner.</span></span>
    1. <span data-ttu-id="bf31f-169">有關更多，請參閱 [裝置擁有者](https://docs.microsoft.com/hololens/security-adminless-os#device-owner)。</span><span class="sxs-lookup"><span data-stu-id="bf31f-169">For more, see [Device Owner](https://docs.microsoft.com/hololens/security-adminless-os#device-owner).</span></span>
1. <span data-ttu-id="bf31f-170">[租使用者](https://docs.microsoft.com/hololens/hololens-release-notes#tenantlockdown-csp-and-autopilot) 鎖定裝置，以便只能加入您的租使用者。</span><span class="sxs-lookup"><span data-stu-id="bf31f-170">[Tenant lock](https://docs.microsoft.com/hololens/hololens-release-notes#tenantlockdown-csp-and-autopilot) the device so that it can only joined your tenant.</span></span>
    1. <span data-ttu-id="bf31f-171">**其他連結：**[租使用者鎖定 CSP](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp)。</span><span class="sxs-lookup"><span data-stu-id="bf31f-171">**Additional Link:** [Tenant lock CSP](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp).</span></span>
1. <span data-ttu-id="bf31f-172">使用此處的全域指派存取來設定 [資訊站](https://docs.microsoft.com/hololens/hololens-global-assigned-access-kiosk)。</span><span class="sxs-lookup"><span data-stu-id="bf31f-172">Configure kiosk using global assigned access to [here](https://docs.microsoft.com/hololens/hololens-global-assigned-access-kiosk).</span></span>
1. <span data-ttu-id="bf31f-173">我們建議您停用下列 (或) 功能：</span><span class="sxs-lookup"><span data-stu-id="bf31f-173">We recommend disabling the follow (optional) capabilities:</span></span>
    1. <span data-ttu-id="bf31f-174">在此將裝置置於開發人員模式 [的能力](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowdeveloperunlock)。</span><span class="sxs-lookup"><span data-stu-id="bf31f-174">Ability to put the device into developer mode [here](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowdeveloperunlock).</span></span>
    1. <span data-ttu-id="bf31f-175">將 HoloLens 連接到電腦以複製日期的能力會[停用 USB。](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection)</span><span class="sxs-lookup"><span data-stu-id="bf31f-175">Ability to connect the HoloLens to a PC to copy date [disable USB](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection).</span></span>
       > [!NOTE]
        > <span data-ttu-id="bf31f-176">如果您不想停用 USB，但想要使用 USB 將設置套件套用至裝置，請遵循此處列出的[**指示。**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)</span><span class="sxs-lookup"><span data-stu-id="bf31f-176">If you don’t want to disable USB but want the ability to apply a provisioning package to the device using USB, follow the instructions listed [**here**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage).</span></span>

1. <span data-ttu-id="bf31f-177">使用 [WDAC](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) 來允許或封鎖 HoloLens 2 裝置上的應用程式。</span><span class="sxs-lookup"><span data-stu-id="bf31f-177">Use [WDAC](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) to allow or block apps on the HoloLens 2 device.</span></span>
1. <span data-ttu-id="bf31f-178">在設定時將遠端協助更新為最新版本。</span><span class="sxs-lookup"><span data-stu-id="bf31f-178">Update Remote Assist to the latest version as part of the setup.</span></span> <span data-ttu-id="bf31f-179">有兩個選項可以執行此工作：</span><span class="sxs-lookup"><span data-stu-id="bf31f-179">There are two options to do this:</span></span>
    1. <span data-ttu-id="bf31f-180">若要這麼做，請至 Windows **Microsoft Store -->遠端協助 ->更新應用程式**。</span><span class="sxs-lookup"><span data-stu-id="bf31f-180">This can be done by going to Windows **Microsoft Store --> Remote Assist --> and Update App**.</span></span>
    1. <span data-ttu-id="bf31f-181">[ApplicationManagement/AllowAppStoreAutoUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowappstoreautoupdate) - 允許自動應用程式更新 - 預設為啟用。</span><span class="sxs-lookup"><span data-stu-id="bf31f-181">[ApplicationManagement/AllowAppStoreAutoUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowappstoreautoupdate) - which allows automatic app updates - is enabled by default.</span></span> <span data-ttu-id="bf31f-182">將裝置保持插入以接收更新。</span><span class="sxs-lookup"><span data-stu-id="bf31f-182">Keep the device plugged in to receive updates.</span></span>
1. <span data-ttu-id="bf31f-183">[除了網路設定](https://docs.microsoft.com/hololens/settings-uri-list) 之外，停用所有設定頁面，以允許使用者在用戶端網站連接到來賓網路。</span><span class="sxs-lookup"><span data-stu-id="bf31f-183">[Disable all settings pages](https://docs.microsoft.com/hololens/settings-uri-list) except the network settings to allow users to connect to guest networks at client sites.</span></span>
1. [<span data-ttu-id="bf31f-184">管理 HoloLens 更新</span><span class="sxs-lookup"><span data-stu-id="bf31f-184">Manage HoloLens Updates</span></span>](https://docs.microsoft.com/hololens/hololens-updates)
    1. <span data-ttu-id="bf31f-185">控制 [作業系統更新或](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings) 允許自由流程的選項。</span><span class="sxs-lookup"><span data-stu-id="bf31f-185">Option to [control OS updates](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings) or allow to flow freely.</span></span>
1. <span data-ttu-id="bf31f-186">[常見的裝置限制](https://docs.microsoft.com/hololens/hololens-common-device-restrictions)。</span><span class="sxs-lookup"><span data-stu-id="bf31f-186">[Common Device Restrictions](https://docs.microsoft.com/hololens/hololens-common-device-restrictions).</span></span>
