---
title: 外部用戶端部署指南
description: '適用于外部用戶端的 HoloLens 2 部署指南 (以遠端協助作為範例) '
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
ms.openlocfilehash: 7658ace4879fef401accabb95ca22e307e5f80a8
ms.sourcegitcommit: 50e4d61a31b94d5007776064b4012e26cf9ecbbb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/16/2021
ms.locfileid: "11271657"
---
# <span data-ttu-id="3724f-103">使用遠端協助將 HoloLens 2 部署到外部用戶端</span><span class="sxs-lookup"><span data-stu-id="3724f-103">Deploying HoloLens 2 to External Clients with Remote Assist</span></span>

<span data-ttu-id="3724f-104">本指南可協助 IT 專業人員使用下列目標，在其組織中部署 Microsoft HoloLens 2 裝置：</span><span class="sxs-lookup"><span data-stu-id="3724f-104">This guide helps IT professionals with the following goals deploy Microsoft HoloLens 2 devices in their organization:</span></span>

1. <span data-ttu-id="3724f-105">雲端連接 HoloLens 2 裝置</span><span class="sxs-lookup"><span data-stu-id="3724f-105">Cloud connect HoloLens 2 devices</span></span>
1. <span data-ttu-id="3724f-106">向外部用戶端貸款 HoloLens 2 裝置以供使用</span><span class="sxs-lookup"><span data-stu-id="3724f-106">Loan HoloLens 2 devices to external clients for use</span></span>
1. <span data-ttu-id="3724f-107">安全的借出裝置</span><span class="sxs-lookup"><span data-stu-id="3724f-107">Secure loaned devices</span></span>

<span data-ttu-id="3724f-108">本指南將提供適用于大部分 HoloLens 2 部署案例的 [一般 HoloLens 2 部署建議](#general-deployment-recommendations-and-instructions) ，以及客戶在部署外部使用的遠端協助時的 [常見考慮](#common-concerns) 。</span><span class="sxs-lookup"><span data-stu-id="3724f-108">This guide will provide [general HoloLens 2 deployment recommendations](#general-deployment-recommendations-and-instructions) that is applicable to most HoloLens 2 deployment scenarios and [common concerns](#common-concerns) that customers have when deploying Remote Assist for external use.</span></span>

## <span data-ttu-id="3724f-109">案例描述</span><span class="sxs-lookup"><span data-stu-id="3724f-109">Scenario Description</span></span>

<span data-ttu-id="3724f-110">針對本檔的用途，Contoso 公司想要將 HoloLens 2 裝置運送到外部用戶端的工廠，以進行短期或長期使用。</span><span class="sxs-lookup"><span data-stu-id="3724f-110">For the purpose of this document, Contoso Company wants to ship a HoloLens 2 device to an external client's plant for short-term or long-term use.</span></span> <span data-ttu-id="3724f-111">當用戶端需要協助服務機械時，用戶端將使用 Contoso 公司提供的認證登入 HoloLens 2 裝置，並使用 [遠端協助] 與 Contoso 公司的專家取得聯繫。</span><span class="sxs-lookup"><span data-stu-id="3724f-111">When the client needs assistance servicing machinery, the client will log into the HoloLens 2 device using credentials provided by Contoso Company and use Remote Assist to contact Contoso Company's experts.</span></span>

<span data-ttu-id="3724f-112">深入瞭解[遠端協助。](https://docs.microsoft.com/hololens/hololens2-cloud-connected-overview#learn-about-remote-assist)</span><span class="sxs-lookup"><span data-stu-id="3724f-112">Learn more about Remote Assist [here](https://docs.microsoft.com/hololens/hololens2-cloud-connected-overview#learn-about-remote-assist).</span></span>

### <span data-ttu-id="3724f-113">此案例的需求</span><span class="sxs-lookup"><span data-stu-id="3724f-113">Requirements for this Scenario</span></span>

1. [<span data-ttu-id="3724f-114">Azure AD</span><span class="sxs-lookup"><span data-stu-id="3724f-114">Azure AD</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)
1. <span data-ttu-id="3724f-115">行動裝置管理器-例如 [Intune](https://docs.microsoft.com/mem/intune/fundamentals/free-trial-sign-up)</span><span class="sxs-lookup"><span data-stu-id="3724f-115">Mobile Device Manager - such as [Intune](https://docs.microsoft.com/mem/intune/fundamentals/free-trial-sign-up)</span></span>
1. <span data-ttu-id="3724f-116">遠端協助授權</span><span class="sxs-lookup"><span data-stu-id="3724f-116">Remote Assist License</span></span>
    1. [<span data-ttu-id="3724f-117">購買遠端協助</span><span class="sxs-lookup"><span data-stu-id="3724f-117">Buy Remote Assist</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-remote-assist)
    1. [<span data-ttu-id="3724f-118">試用版遠端協助</span><span class="sxs-lookup"><span data-stu-id="3724f-118">Trial Remote Assist</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)

## <span data-ttu-id="3724f-119">常見的考慮</span><span class="sxs-lookup"><span data-stu-id="3724f-119">Common Concerns</span></span>

- [<span data-ttu-id="3724f-120">如何確保外部用戶端無法彼此通訊的能力</span><span class="sxs-lookup"><span data-stu-id="3724f-120">How to ensure that external clients do not have the ability to communicate with one another</span></span>](#how-to-ensure-that-external-clients-do-not-have-the-ability-to-communicate-with-one-another)
- [<span data-ttu-id="3724f-121">如何確保用戶端無法存取公司資源</span><span class="sxs-lookup"><span data-stu-id="3724f-121">How to ensure that clients do not have access to company resources</span></span>](#how-to-ensure-that-clients-do-not-have-access-to-company-resources)
- [<span data-ttu-id="3724f-122">如何限制 app</span><span class="sxs-lookup"><span data-stu-id="3724f-122">How to restrict apps</span></span>](#how-to-restrict-apps)
- [<span data-ttu-id="3724f-123">如何管理密碼</span><span class="sxs-lookup"><span data-stu-id="3724f-123">How to manage passwords</span></span>](#how-to-manage-passwords)
- [<span data-ttu-id="3724f-124">如何確保用戶端無法存取聊天記錄</span><span class="sxs-lookup"><span data-stu-id="3724f-124">How to ensure that clients do not have access to chat history</span></span>](#how-to-ensure-that-clients-do-not-have-access-to-chat-history)

### <span data-ttu-id="3724f-125">如何確保外部用戶端無法彼此通訊的能力</span><span class="sxs-lookup"><span data-stu-id="3724f-125">How to ensure that external clients do not have the ability to communicate with one another</span></span>

<span data-ttu-id="3724f-126">由於遠端協助 HoloLens 不支援 HoloLens 呼叫，因此用戶端可以搜尋，但無法與其他人通訊。</span><span class="sxs-lookup"><span data-stu-id="3724f-126">Since Remote Assist HoloLens to HoloLens calls are not supported, clients are able to search for, but are unable to, communicate with one another.</span></span> <span data-ttu-id="3724f-127">若要進一步限制客戶可以搜尋及呼叫哪些人，  [資訊障礙](https://docs.microsoft.com/microsoft-365/compliance/information-barriers?view=o365-worldwide) 可以限制用戶端可與之通訊的人員。</span><span class="sxs-lookup"><span data-stu-id="3724f-127">To further restrict who clients can search for and call,  [Information barriers](https://docs.microsoft.com/microsoft-365/compliance/information-barriers?view=o365-worldwide) can restrict who a client can communicate with.</span></span> <span data-ttu-id="3724f-128">另一個考慮選項是使用 [範圍內的目錄搜尋](https://docs.microsoft.com/MicrosoftTeams/teams-scoped-directory-search)</span><span class="sxs-lookup"><span data-stu-id="3724f-128">Another option to consider is using [Scoped Directory Search](https://docs.microsoft.com/MicrosoftTeams/teams-scoped-directory-search)</span></span>

 > [!NOTE]
> <span data-ttu-id="3724f-129">因為已啟用單一登入，所以請務必使用 [**WDAC**](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)來停用瀏覽器。</span><span class="sxs-lookup"><span data-stu-id="3724f-129">Since single sign on is enabled, it is important to disable the browser using [**WDAC**](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac).</span></span> <span data-ttu-id="3724f-130">如果外部用戶端開啟瀏覽器並使用 web 團隊版本，則用戶端將可以存取通話/聊天歷程記錄。</span><span class="sxs-lookup"><span data-stu-id="3724f-130">If an external client opens the browser and uses the web version of Teams, the client will have access to call/chat history.</span></span>

### <span data-ttu-id="3724f-131">如何確保用戶端無法存取公司資源</span><span class="sxs-lookup"><span data-stu-id="3724f-131">How to ensure that clients do not have access to company resources</span></span>

<span data-ttu-id="3724f-132">您可以考慮兩個選項。</span><span class="sxs-lookup"><span data-stu-id="3724f-132">There are two options to consider.</span></span>

<span data-ttu-id="3724f-133">第一個選項是多層方法：</span><span class="sxs-lookup"><span data-stu-id="3724f-133">The first option is a multi-layer approach:</span></span>

1. <span data-ttu-id="3724f-134">僅指派使用者所需的授權。</span><span class="sxs-lookup"><span data-stu-id="3724f-134">Only assign licenses that the user requires.</span></span> <span data-ttu-id="3724f-135">如果您沒有指派 OneDrive、Outlook、SharePoint、Yammer 等，使用者將無法存取這些資源。</span><span class="sxs-lookup"><span data-stu-id="3724f-135">If you do not assign OneDrive, Outlook, SharePoint, Yammer, etc. to the user, he/she will not have access to those resources.</span></span> <span data-ttu-id="3724f-136">使用者所需的唯一授權是 [遠端協助]、[Intune] 和 [AAD 授權] 開始。</span><span class="sxs-lookup"><span data-stu-id="3724f-136">The only licenses the users will need is Remote Assist, Intune, and AAD licenses to begin.</span></span>
1. <span data-ttu-id="3724f-137">封鎖 app (例如您不想讓用戶端存取的電子郵件)  (請參閱 [如何限制 app](#how-to-restrict-apps)) 。</span><span class="sxs-lookup"><span data-stu-id="3724f-137">Block apps (such as email) that you don’t want clients to access (See [How to restrict apps](#how-to-restrict-apps)).</span></span>
1. <span data-ttu-id="3724f-138">請勿與客戶共用使用者的使用者名稱和密碼。</span><span class="sxs-lookup"><span data-stu-id="3724f-138">Do NOT share usernames nor password with clients.</span></span> <span data-ttu-id="3724f-139">若要登入 HoloLens 2，必須輸入電子郵件和數位 PIN。</span><span class="sxs-lookup"><span data-stu-id="3724f-139">To log into the HoloLens 2, an email and numerical PIN is required.</span></span>

<span data-ttu-id="3724f-140">第二個選項是建立另一個承載用戶端的租使用者 (請參閱影像 1.1) 。</span><span class="sxs-lookup"><span data-stu-id="3724f-140">The second option is to create a separate tenant that hosts clients (see Image 1.1).</span></span>

**<span data-ttu-id="3724f-141">影像1。1</span><span class="sxs-lookup"><span data-stu-id="3724f-141">Image 1.1</span></span>**

![服務租使用者圖像](./images/hololens-service-tenant-image.png)

### <span data-ttu-id="3724f-143">如何限制 app</span><span class="sxs-lookup"><span data-stu-id="3724f-143">How to restrict apps</span></span>

<span data-ttu-id="3724f-144">[Kiosk 模式](https://docs.microsoft.com/hololens/hololens-kiosk) 和/或 [WDAC (Windows Defender 應用程式控制項) ](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) 是用於限制應用程式的選項。</span><span class="sxs-lookup"><span data-stu-id="3724f-144">[Kiosk Mode](https://docs.microsoft.com/hololens/hololens-kiosk) and/or [WDAC (Windows Defender Application Control)](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) are options for restricting applications.</span></span>

### <span data-ttu-id="3724f-145">如何管理密碼</span><span class="sxs-lookup"><span data-stu-id="3724f-145">How to manage passwords</span></span>

1. <span data-ttu-id="3724f-146">移除密碼到期日。</span><span class="sxs-lookup"><span data-stu-id="3724f-146">Remove password expiration.</span></span> <span data-ttu-id="3724f-147">不過，這會增加帳戶受到損害的可能性。</span><span class="sxs-lookup"><span data-stu-id="3724f-147">However, this increases the chance that that an account will be compromised.</span></span> <span data-ttu-id="3724f-148">NIST 密碼建議每30-90 天都會變更密碼。</span><span class="sxs-lookup"><span data-stu-id="3724f-148">NIST password recommendation is change passwords every 30-90 days.</span></span>
1. <span data-ttu-id="3724f-149">延長 HoloLens 2 裝置的密碼到期期限，以超過90天。</span><span class="sxs-lookup"><span data-stu-id="3724f-149">Extend the password expiration for HoloLens 2 devices to exceed 90 days.</span></span>
1. <span data-ttu-id="3724f-150">裝置應該傳回 Contoso 來變更密碼。</span><span class="sxs-lookup"><span data-stu-id="3724f-150">The devices should be returned to Contoso to change the passwords.</span></span> <span data-ttu-id="3724f-151">不過，如果裝置在用戶端的工廠中需要 90 + 天，這可能會導致問題。</span><span class="sxs-lookup"><span data-stu-id="3724f-151">However, this can cause issues if the devices are expected to be in the client's plant for 90+ days.</span></span>  
1. <span data-ttu-id="3724f-152">如果是傳送給多個用戶端的裝置，請先重設密碼，然後再將裝置傳送給用戶端。</span><span class="sxs-lookup"><span data-stu-id="3724f-152">For devices that are sent to multiple clients, reset passwords before shipping the device to clients.</span></span>

### <span data-ttu-id="3724f-153">如何確保用戶端無法存取聊天記錄</span><span class="sxs-lookup"><span data-stu-id="3724f-153">How to ensure that clients do not have access to chat history</span></span>

<span data-ttu-id="3724f-154">[遠端協助] 會在每個會話之後清除聊天記錄。</span><span class="sxs-lookup"><span data-stu-id="3724f-154">Remote Assist clears chat history after each session.</span></span> <span data-ttu-id="3724f-155">不過，Microsoft 團隊使用者將可以使用聊天記錄。</span><span class="sxs-lookup"><span data-stu-id="3724f-155">However, the chat history will be available for the Microsoft Teams user.</span></span>

> [!NOTE]
> <span data-ttu-id="3724f-156">因為已啟用單一登入，所以請務必使用 [**WDAC**](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)來停用瀏覽器。</span><span class="sxs-lookup"><span data-stu-id="3724f-156">Since single sign on is enabled, it is important to disable the browser using [**WDAC**](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac).</span></span> <span data-ttu-id="3724f-157">如果外部用戶端開啟瀏覽器並使用 web 團隊版本，則用戶端將可以存取通話/聊天歷程記錄。</span><span class="sxs-lookup"><span data-stu-id="3724f-157">If a external client opens the browser and uses the web version of Teams, the client will have access to call/chat history.</span></span>

## <span data-ttu-id="3724f-158">一般部署建議與指示</span><span class="sxs-lookup"><span data-stu-id="3724f-158">General Deployment Recommendations and Instructions</span></span>

<span data-ttu-id="3724f-159">我們建議在 HoloLens 2 部署步驟中進行下列操作：</span><span class="sxs-lookup"><span data-stu-id="3724f-159">We recommend the following for HoloLens 2 deployment Steps:</span></span>

1. <span data-ttu-id="3724f-160">使用 [最新的 HOLOLENS OS 版本](https://aka.ms/hololens2download) 做為基準組建。</span><span class="sxs-lookup"><span data-stu-id="3724f-160">Use the [latest HoloLens OS release](https://aka.ms/hololens2download) as your baseline build.</span></span>
1. <span data-ttu-id="3724f-161">指派以使用者為基礎或裝置為基礎的授權：</span><span class="sxs-lookup"><span data-stu-id="3724f-161">Assign user-based or device-based licenses:</span></span>
    1. <span data-ttu-id="3724f-162">使用者和裝置的授權都遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="3724f-162">User-based and device-based licenses both follow the following steps:</span></span>
        1. <span data-ttu-id="3724f-163">[在 AAD 中建立群組，並新增](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal#create-a-basic-group-and-add-members) HOLOLENS/RA 使用者的成員。</span><span class="sxs-lookup"><span data-stu-id="3724f-163">[Create a group in AAD and add members](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal#create-a-basic-group-and-add-members) for HoloLens/RA users.</span></span>
        1. <span data-ttu-id="3724f-164">[指派裝置或以使用者為基礎的授權](https://docs.microsoft.com/azure/active-directory/enterprise-users/licensing-groups-assign#:~:text=In%20this%20article%201%20Assign%20the%20required%20licenses,3%20Check%20for%20license%20problems%20and%20resolve%20them) 到這個群組。</span><span class="sxs-lookup"><span data-stu-id="3724f-164">[Assign device-based or user-based licenses](https://docs.microsoft.com/azure/active-directory/enterprise-users/licensing-groups-assign#:~:text=In%20this%20article%201%20Assign%20the%20required%20licenses,3%20Check%20for%20license%20problems%20and%20resolve%20them) to this group.</span></span>
        1. <span data-ttu-id="3724f-165"> (選用) 您可以將 MDM 原則設定為目標群組。</span><span class="sxs-lookup"><span data-stu-id="3724f-165">(Optional) You can target groups for MDM policies.</span></span>

1. <span data-ttu-id="3724f-166">裝置應該已以 AAD 連接至您的租使用者、 [自動註冊](https://docs.microsoft.com/hololens/hololens-enroll-mdm#auto-enrollment-in-mdm)，以及透過 [自動試運行](https://docs.microsoft.com/hololens/hololens2-autopilot)進行設定。</span><span class="sxs-lookup"><span data-stu-id="3724f-166">Devices should be AAD joined to your tenant, [Auto Enrolled](https://docs.microsoft.com/hololens/hololens-enroll-mdm#auto-enrollment-in-mdm), and configured through [Auto Pilot](https://docs.microsoft.com/hololens/hololens2-autopilot).</span></span>
    1. <span data-ttu-id="3724f-167">請注意，裝置上的第一個使用者將是裝置擁有者。</span><span class="sxs-lookup"><span data-stu-id="3724f-167">Please note that the first user on the device will be the device owner.</span></span>
    1. <span data-ttu-id="3724f-168">請注意，如果裝置已 AAD 加入，則執行加入的使用者會成為裝置擁有者。</span><span class="sxs-lookup"><span data-stu-id="3724f-168">Please note that if the device is AAD joined, the user that performed the join is made device owner.</span></span>
    1. <span data-ttu-id="3724f-169">如需詳細資訊，請參閱 [裝置擁有](https://docs.microsoft.com/hololens/security-adminless-os#device-owner)者。</span><span class="sxs-lookup"><span data-stu-id="3724f-169">For more, see [Device Owner](https://docs.microsoft.com/hololens/security-adminless-os#device-owner).</span></span>
1. <span data-ttu-id="3724f-170">[租](https://docs.microsoft.com/hololens/hololens-release-notes#tenantlockdown-csp-and-autopilot) 使用者可鎖定裝置，讓它只能加入您的租使用者。</span><span class="sxs-lookup"><span data-stu-id="3724f-170">[Tenant lock](https://docs.microsoft.com/hololens/hololens-release-notes#tenantlockdown-csp-and-autopilot) the device so that it can only joined your tenant.</span></span>
    1. <span data-ttu-id="3724f-171">**其他連結：** [租使用者鎖定 CSP](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp)。</span><span class="sxs-lookup"><span data-stu-id="3724f-171">**Additional Link:** [Tenant lock CSP](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp).</span></span>
1. <span data-ttu-id="3724f-172">[在這裡](https://docs.microsoft.com/hololens/hololens-global-assigned-access-kiosk)使用全域指派的存取權來設定 kiosk。</span><span class="sxs-lookup"><span data-stu-id="3724f-172">Configure kiosk using global assigned access to [here](https://docs.microsoft.com/hololens/hololens-global-assigned-access-kiosk).</span></span>
1. <span data-ttu-id="3724f-173">我們建議您停用下列 (選用的) 功能：</span><span class="sxs-lookup"><span data-stu-id="3724f-173">We recommend disabling the follow (optional) capabilities:</span></span>
    1. <span data-ttu-id="3724f-174">在 [這裡](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowdeveloperunlock)將裝置設為開發人員模式的能力。</span><span class="sxs-lookup"><span data-stu-id="3724f-174">Ability to put the device into developer mode [here](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowdeveloperunlock).</span></span>
    1. <span data-ttu-id="3724f-175">將 HoloLens 連接至電腦以複製日期的能力 [停用 USB](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection)。</span><span class="sxs-lookup"><span data-stu-id="3724f-175">Ability to connect the HoloLens to a PC to copy date [disable USB](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection).</span></span>
       > [!NOTE]
        > <span data-ttu-id="3724f-176">如果您不想停用 USB，但想要將預配套件套用至使用 USB 的裝置，請依照 [**此處**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)所列的指示進行。</span><span class="sxs-lookup"><span data-stu-id="3724f-176">If you don’t want to disable USB but want the ability to apply a provisioning package to the device using USB, follow the instructions listed [**here**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage).</span></span>

1. <span data-ttu-id="3724f-177">在 HoloLens 2 裝置上使用 [WDAC](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) 來允許或黑色 app。</span><span class="sxs-lookup"><span data-stu-id="3724f-177">Use [WDAC](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) to allow or black apps on the HoloLens 2 device.</span></span>
1. <span data-ttu-id="3724f-178">將遠端協助更新為安裝程式中的最新版本。</span><span class="sxs-lookup"><span data-stu-id="3724f-178">Update Remote Assist to the latest version as part of the setup.</span></span> <span data-ttu-id="3724f-179">有兩個選項可以執行此動作：</span><span class="sxs-lookup"><span data-stu-id="3724f-179">There are two options to do this:</span></span>
    1. <span data-ttu-id="3724f-180">若要執行此動作，您可以移至 Windows **Microsoft 網上商店，> 遠端協助--> 與更新 App**。</span><span class="sxs-lookup"><span data-stu-id="3724f-180">This can be done by going to Windows **Microsoft Store --> Remote Assist --> and Update App**.</span></span>
    1. <span data-ttu-id="3724f-181">使用 [ApplicationManagement/AllowAppStoreAutoUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowappstoreautoupdate) CSP 啟用自動更新，並讓裝置保持電源開啟來接收更新。</span><span class="sxs-lookup"><span data-stu-id="3724f-181">Enable auto updates using the [ApplicationManagement/AllowAppStoreAutoUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowappstoreautoupdate) CSP and keep the device plugged in to receive updates.</span></span>
1. <span data-ttu-id="3724f-182">[停](https://docs.microsoft.com/hololens/settings-uri-list) 用 [網路設定] 以外的所有 [設定] 頁面，以允許使用者連線至用戶端網站上的來賓網路。</span><span class="sxs-lookup"><span data-stu-id="3724f-182">[Disable all settings pages](https://docs.microsoft.com/hololens/settings-uri-list) except the network settings to allow users to connect to guest networks at client sites.</span></span>
1. [<span data-ttu-id="3724f-183">管理 HoloLens 更新</span><span class="sxs-lookup"><span data-stu-id="3724f-183">Manage HoloLens Updates</span></span>](https://docs.microsoft.com/hololens/hololens-updates)
    1. <span data-ttu-id="3724f-184">[控制 OS 更新](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings)或允許自由流動的選項。</span><span class="sxs-lookup"><span data-stu-id="3724f-184">Option to [control OS updates](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings) or allow to flow freely.</span></span>
1. <span data-ttu-id="3724f-185">[常見的裝置限制](https://docs.microsoft.com/hololens/hololens-common-device-restrictions)。</span><span class="sxs-lookup"><span data-stu-id="3724f-185">[Common Device Restrictions](https://docs.microsoft.com/hololens/hololens-common-device-restrictions).</span></span>
