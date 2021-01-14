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
ms.openlocfilehash: c0ea468df2188700af408803ae1c55b9d0e4c763
ms.sourcegitcommit: ea5fa6c970756025b77c00b4ea600d60ce033106
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/13/2021
ms.locfileid: "11267999"
---
# <span data-ttu-id="5ca74-103">使用遠端協助將 HoloLens 2 部署到外部用戶端</span><span class="sxs-lookup"><span data-stu-id="5ca74-103">Deploying HoloLens 2 to External Clients with Remote Assist</span></span>

<span data-ttu-id="5ca74-104">這份檔可協助 IT professions 規劃並部署 HoloLens 2 裝置，並將焦點放在遠端協助上。</span><span class="sxs-lookup"><span data-stu-id="5ca74-104">This document helps IT professions plan for and deploy HoloLens 2 devices with a focus on Remote Assist.</span></span> <span data-ttu-id="5ca74-105">[深入瞭解遠端協助](https://docs.microsoft.com/hololens/hololens2-cloud-connected-overview#learn-about-remote-assist)。</span><span class="sxs-lookup"><span data-stu-id="5ca74-105">[Learn more about Remote Assist](https://docs.microsoft.com/hololens/hololens2-cloud-connected-overview#learn-about-remote-assist).</span></span>

## <span data-ttu-id="5ca74-106">案例描述</span><span class="sxs-lookup"><span data-stu-id="5ca74-106">Scenario Description</span></span>

<span data-ttu-id="5ca74-107">針對本檔的用途，Contoso 公司想要將 HoloLens 2 裝置運送到外部用戶端的工廠，以進行短期或長期使用。</span><span class="sxs-lookup"><span data-stu-id="5ca74-107">For the purpose of this document, Contoso Company wants to ship a HoloLens 2 device to an external client's plant for short-term or long-term use.</span></span> <span data-ttu-id="5ca74-108">當用戶端需要協助服務機械時，用戶端將使用 Contoso 公司提供的認證登入 HoloLens 2 裝置，並使用 [遠端協助] 與 Contoso 公司的專家取得聯繫。</span><span class="sxs-lookup"><span data-stu-id="5ca74-108">When the client needs assistance servicing machinery, the client will log into the HoloLens 2 device using credentials provided by Contoso Company and use Remote Assist to contact Contoso Company's experts.</span></span>

### <span data-ttu-id="5ca74-109">此案例的需求</span><span class="sxs-lookup"><span data-stu-id="5ca74-109">Requirements for this Scenario</span></span>

1. [<span data-ttu-id="5ca74-110">Azure AD</span><span class="sxs-lookup"><span data-stu-id="5ca74-110">Azure AD</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)
1. <span data-ttu-id="5ca74-111">行動裝置管理器-例如 [Intune](https://docs.microsoft.com/mem/intune/fundamentals/free-trial-sign-up)</span><span class="sxs-lookup"><span data-stu-id="5ca74-111">Mobile Device Manager - such as [Intune](https://docs.microsoft.com/mem/intune/fundamentals/free-trial-sign-up)</span></span>
1. <span data-ttu-id="5ca74-112">遠端協助授權</span><span class="sxs-lookup"><span data-stu-id="5ca74-112">Remote Assist License</span></span>
    1. [<span data-ttu-id="5ca74-113">購買遠端協助</span><span class="sxs-lookup"><span data-stu-id="5ca74-113">Buy Remote Assist</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-remote-assist)
    1. [<span data-ttu-id="5ca74-114">試用版遠端協助</span><span class="sxs-lookup"><span data-stu-id="5ca74-114">Trial Remote Assist</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)

## <span data-ttu-id="5ca74-115">常見的考慮</span><span class="sxs-lookup"><span data-stu-id="5ca74-115">Common Concerns</span></span>

- [<span data-ttu-id="5ca74-116">如何確保外部用戶端無法彼此通訊的能力</span><span class="sxs-lookup"><span data-stu-id="5ca74-116">How to ensure that external clients do not have the ability to communicate with one another</span></span>](#how-to-ensure-that-external-clients-do-not-have-the-ability-to-communicate-with-one-another)
- [<span data-ttu-id="5ca74-117">如何確保用戶端無法存取公司資源</span><span class="sxs-lookup"><span data-stu-id="5ca74-117">How to ensure that clients do not have access to company resources</span></span>](#how-to-ensure-that-clients-do-not-have-access-to-company-resources)
- [<span data-ttu-id="5ca74-118">如何限制 app</span><span class="sxs-lookup"><span data-stu-id="5ca74-118">How to restrict apps</span></span>](#how-to-restrict-apps)
- [<span data-ttu-id="5ca74-119">如何管理密碼</span><span class="sxs-lookup"><span data-stu-id="5ca74-119">How to manage passwords</span></span>](#how-to-manage-passwords)
- [<span data-ttu-id="5ca74-120">如何確保用戶端無法存取聊天記錄</span><span class="sxs-lookup"><span data-stu-id="5ca74-120">How to ensure that clients do not have access to chat history</span></span>](#how-to-ensure-that-clients-do-not-have-access-to-chat-history)

### <span data-ttu-id="5ca74-121">如何確保外部用戶端無法彼此通訊的能力</span><span class="sxs-lookup"><span data-stu-id="5ca74-121">How to ensure that external clients do not have the ability to communicate with one another</span></span>

<span data-ttu-id="5ca74-122">由於遠端協助 HoloLens 不支援 HoloLens 呼叫，因此用戶端可以搜尋，但無法與其他人通訊。</span><span class="sxs-lookup"><span data-stu-id="5ca74-122">Since Remote Assist HoloLens to HoloLens calls are not supported, clients are able to search for, but are unable to, communicate with one another.</span></span> <span data-ttu-id="5ca74-123">若要進一步限制客戶可以搜尋及呼叫哪些人，  [資訊障礙](https://docs.microsoft.com/microsoft-365/compliance/information-barriers?view=o365-worldwide) 可以限制用戶端可與之通訊的人員。</span><span class="sxs-lookup"><span data-stu-id="5ca74-123">To further restrict who clients can search for and call,  [Information barriers](https://docs.microsoft.com/microsoft-365/compliance/information-barriers?view=o365-worldwide) can restrict who a client can communicate with.</span></span> <span data-ttu-id="5ca74-124">另一個考慮選項是使用 [範圍內的目錄搜尋](https://docs.microsoft.com/MicrosoftTeams/teams-scoped-directory-search)</span><span class="sxs-lookup"><span data-stu-id="5ca74-124">Another option to consider is using [Scoped Directory Search](https://docs.microsoft.com/MicrosoftTeams/teams-scoped-directory-search)</span></span>

 > [!NOTE]
> <span data-ttu-id="5ca74-125">因為已啟用單一登入，所以請務必使用 [**WDAC**](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)來停用瀏覽器。</span><span class="sxs-lookup"><span data-stu-id="5ca74-125">Since single sign on is enabled, it is important to disable the browser using [**WDAC**](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac).</span></span> <span data-ttu-id="5ca74-126">如果外部用戶端開啟瀏覽器並使用 web 團隊版本，則用戶端將可以存取通話/聊天歷程記錄。</span><span class="sxs-lookup"><span data-stu-id="5ca74-126">If an external client opens the browser and uses the web version of Teams, the client will have access to call/chat history.</span></span>

### <span data-ttu-id="5ca74-127">如何確保用戶端無法存取公司資源</span><span class="sxs-lookup"><span data-stu-id="5ca74-127">How to ensure that clients do not have access to company resources</span></span>

<span data-ttu-id="5ca74-128">您可以考慮兩個選項。</span><span class="sxs-lookup"><span data-stu-id="5ca74-128">There are two options to consider.</span></span>

<span data-ttu-id="5ca74-129">第一個選項是多層方法：</span><span class="sxs-lookup"><span data-stu-id="5ca74-129">The first option is a multi-layer approach:</span></span>

1. <span data-ttu-id="5ca74-130">僅指派使用者所需的授權。</span><span class="sxs-lookup"><span data-stu-id="5ca74-130">Only assign licenses that the user requires.</span></span> <span data-ttu-id="5ca74-131">如果您沒有指派 OneDrive、Outlook、SharePoint、Yammer 等，使用者將無法存取這些資源。</span><span class="sxs-lookup"><span data-stu-id="5ca74-131">If you do not assign OneDrive, Outlook, SharePoint, Yammer, etc. to the user, he/she will not have access to those resources.</span></span> <span data-ttu-id="5ca74-132">使用者所需的唯一授權是 [遠端協助]、[Intune] 和 [AAD 授權] 開始。</span><span class="sxs-lookup"><span data-stu-id="5ca74-132">The only licenses the users will need is Remote Assist, Intune, and AAD licenses to begin.</span></span>
1. <span data-ttu-id="5ca74-133">封鎖 app (例如您不想讓用戶端存取的電子郵件)  (請參閱 [如何限制 app](#how-to-restrict-apps)) 。</span><span class="sxs-lookup"><span data-stu-id="5ca74-133">Block apps (such as email) that you don’t want clients to access (See [How to restrict apps](#how-to-restrict-apps)).</span></span>
1. <span data-ttu-id="5ca74-134">請勿與客戶共用使用者的使用者名稱和密碼。</span><span class="sxs-lookup"><span data-stu-id="5ca74-134">Do NOT share usernames nor password with clients.</span></span> <span data-ttu-id="5ca74-135">若要登入 HoloLens 2，必須輸入電子郵件和數位 PIN。</span><span class="sxs-lookup"><span data-stu-id="5ca74-135">To log into the HoloLens 2, an email and numerical PIN is required.</span></span>

<span data-ttu-id="5ca74-136">第二個選項是建立另一個承載用戶端的租使用者 (請參閱影像 1.1) 。</span><span class="sxs-lookup"><span data-stu-id="5ca74-136">The second option is to create a separate tenant that hosts clients (see Image 1.1).</span></span>

**<span data-ttu-id="5ca74-137">影像1。1</span><span class="sxs-lookup"><span data-stu-id="5ca74-137">Image 1.1</span></span>**

![服務租使用者圖像](./images/hololens-service-tenant-image.png)

### <span data-ttu-id="5ca74-139">如何限制 app</span><span class="sxs-lookup"><span data-stu-id="5ca74-139">How to restrict apps</span></span>

<span data-ttu-id="5ca74-140">[Kiosk 模式](https://docs.microsoft.com/hololens/hololens-kiosk) 和/或 [WDAC (Windows Defender 應用程式控制項) ](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) 是用於限制應用程式的選項。</span><span class="sxs-lookup"><span data-stu-id="5ca74-140">[Kiosk Mode](https://docs.microsoft.com/hololens/hololens-kiosk) and/or [WDAC (Windows Defender Application Control)](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) are options for restricting applications.</span></span>

### <span data-ttu-id="5ca74-141">如何管理密碼</span><span class="sxs-lookup"><span data-stu-id="5ca74-141">How to manage passwords</span></span>

1. <span data-ttu-id="5ca74-142">移除密碼到期日。</span><span class="sxs-lookup"><span data-stu-id="5ca74-142">Remove password expiration.</span></span> <span data-ttu-id="5ca74-143">不過，這會增加帳戶受到損害的可能性。</span><span class="sxs-lookup"><span data-stu-id="5ca74-143">However, this increases the chance that that an account will be compromised.</span></span> <span data-ttu-id="5ca74-144">NIST 密碼建議每30-90 天都會變更密碼。</span><span class="sxs-lookup"><span data-stu-id="5ca74-144">NIST password recommendation is change passwords every 30-90 days.</span></span>
1. <span data-ttu-id="5ca74-145">延長 HoloLens 2 裝置的密碼到期期限，以超過90天。</span><span class="sxs-lookup"><span data-stu-id="5ca74-145">Extend the password expiration for HoloLens 2 devices to exceed 90 days.</span></span>
1. <span data-ttu-id="5ca74-146">裝置應該傳回 Contoso 來變更密碼。</span><span class="sxs-lookup"><span data-stu-id="5ca74-146">The devices should be returned to Contoso to change the passwords.</span></span> <span data-ttu-id="5ca74-147">不過，如果裝置在用戶端的工廠中需要 90 + 天，這可能會導致問題。</span><span class="sxs-lookup"><span data-stu-id="5ca74-147">However, this can cause issues if the devices are expected to be in the client's plant for 90+ days.</span></span>  
1. <span data-ttu-id="5ca74-148">如果是傳送給多個用戶端的裝置，請先重設密碼，然後再將裝置傳送給用戶端。</span><span class="sxs-lookup"><span data-stu-id="5ca74-148">For devices that are sent to multiple clients, reset passwords before shipping the device to clients.</span></span>

### <span data-ttu-id="5ca74-149">如何確保用戶端無法存取聊天記錄</span><span class="sxs-lookup"><span data-stu-id="5ca74-149">How to ensure that clients do not have access to chat history</span></span>

<span data-ttu-id="5ca74-150">[遠端協助] 會在每個會話之後清除聊天記錄。</span><span class="sxs-lookup"><span data-stu-id="5ca74-150">Remote Assist clears chat history after each session.</span></span> <span data-ttu-id="5ca74-151">不過，Microsoft 團隊使用者將可以使用聊天記錄。</span><span class="sxs-lookup"><span data-stu-id="5ca74-151">However, the chat history will be available for the Microsoft Teams user.</span></span>

> [!NOTE]
> <span data-ttu-id="5ca74-152">因為已啟用單一登入，所以請務必使用 [**WDAC**](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)來停用瀏覽器。</span><span class="sxs-lookup"><span data-stu-id="5ca74-152">Since single sign on is enabled, it is important to disable the browser using [**WDAC**](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac).</span></span> <span data-ttu-id="5ca74-153">如果外部用戶端開啟瀏覽器並使用 web 團隊版本，則用戶端將可以存取通話/聊天歷程記錄。</span><span class="sxs-lookup"><span data-stu-id="5ca74-153">If a external client opens the browser and uses the web version of Teams, the client will have access to call/chat history.</span></span>

## <span data-ttu-id="5ca74-154">一般部署建議與指示</span><span class="sxs-lookup"><span data-stu-id="5ca74-154">General Deployment Recommendations and Instructions</span></span>

<span data-ttu-id="5ca74-155">我們建議在 HoloLens 2 部署步驟中進行下列操作：</span><span class="sxs-lookup"><span data-stu-id="5ca74-155">We recommend the following for HoloLens 2 deployment Steps:</span></span>

1. <span data-ttu-id="5ca74-156">使用 [最新的 HOLOLENS OS 版本](https://aka.ms/hololens2download) 做為基準組建。</span><span class="sxs-lookup"><span data-stu-id="5ca74-156">Use the [latest HoloLens OS release](https://aka.ms/hololens2download) as your baseline build.</span></span>
1. <span data-ttu-id="5ca74-157">指派以使用者為基礎或裝置為基礎的授權：</span><span class="sxs-lookup"><span data-stu-id="5ca74-157">Assign user-based or device-based licenses:</span></span>
    1. <span data-ttu-id="5ca74-158">使用者和裝置的授權都遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="5ca74-158">User-based and device-based licenses both follow the following steps:</span></span>
        1. <span data-ttu-id="5ca74-159">[在 AAD 中建立群組，並新增](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal#create-a-basic-group-and-add-members) HOLOLENS/RA 使用者的成員。</span><span class="sxs-lookup"><span data-stu-id="5ca74-159">[Create a group in AAD and add members](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal#create-a-basic-group-and-add-members) for HoloLens/RA users.</span></span>
        1. <span data-ttu-id="5ca74-160">[指派裝置或以使用者為基礎的授權](https://docs.microsoft.com/azure/active-directory/enterprise-users/licensing-groups-assign#:~:text=In%20this%20article%201%20Assign%20the%20required%20licenses,3%20Check%20for%20license%20problems%20and%20resolve%20them) 到這個群組。</span><span class="sxs-lookup"><span data-stu-id="5ca74-160">[Assign device-based or user-based licenses](https://docs.microsoft.com/azure/active-directory/enterprise-users/licensing-groups-assign#:~:text=In%20this%20article%201%20Assign%20the%20required%20licenses,3%20Check%20for%20license%20problems%20and%20resolve%20them) to this group.</span></span>
        1. <span data-ttu-id="5ca74-161"> (選用) 您可以將 MDM 原則設定為目標群組。</span><span class="sxs-lookup"><span data-stu-id="5ca74-161">(Optional) You can target groups for MDM policies.</span></span>

1. <span data-ttu-id="5ca74-162">裝置應該已以 AAD 連接至您的租使用者、 [自動註冊](https://docs.microsoft.com/hololens/hololens-enroll-mdm#auto-enrollment-in-mdm)，以及透過 [自動試運行](https://docs.microsoft.com/hololens/hololens2-autopilot)進行設定。</span><span class="sxs-lookup"><span data-stu-id="5ca74-162">Devices should be AAD joined to your tenant, [Auto Enrolled](https://docs.microsoft.com/hololens/hololens-enroll-mdm#auto-enrollment-in-mdm), and configured through [Auto Pilot](https://docs.microsoft.com/hololens/hololens2-autopilot).</span></span>
    1. <span data-ttu-id="5ca74-163">請注意，裝置上的第一個使用者將是裝置擁有者。</span><span class="sxs-lookup"><span data-stu-id="5ca74-163">Please note that the first user on the device will be the device owner.</span></span>
    1. <span data-ttu-id="5ca74-164">請注意，如果裝置已 AAD 加入，則執行加入的使用者會成為裝置擁有者。</span><span class="sxs-lookup"><span data-stu-id="5ca74-164">Please note that if the device is AAD joined, the user that performed the join is made device owner.</span></span>
    1. <span data-ttu-id="5ca74-165">如需詳細資訊，請參閱 [裝置擁有](https://docs.microsoft.com/hololens/security-adminless-os#device-owner)者。</span><span class="sxs-lookup"><span data-stu-id="5ca74-165">For more, see [Device Owner](https://docs.microsoft.com/hololens/security-adminless-os#device-owner).</span></span>
1. <span data-ttu-id="5ca74-166">[租](https://docs.microsoft.com/hololens/hololens-release-notes#tenantlockdown-csp-and-autopilot) 使用者可鎖定裝置，讓它只能加入您的租使用者。</span><span class="sxs-lookup"><span data-stu-id="5ca74-166">[Tenant lock](https://docs.microsoft.com/hololens/hololens-release-notes#tenantlockdown-csp-and-autopilot) the device so that it can only joined your tenant.</span></span>
    1. <span data-ttu-id="5ca74-167">**其他連結：** [租使用者鎖定 CSP](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp)。</span><span class="sxs-lookup"><span data-stu-id="5ca74-167">**Additional Link:** [Tenant lock CSP](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp).</span></span>
1. <span data-ttu-id="5ca74-168">[在這裡](https://docs.microsoft.com/hololens/hololens-global-assigned-access-kiosk)使用全域指派的存取權來設定 kiosk。</span><span class="sxs-lookup"><span data-stu-id="5ca74-168">Configure kiosk using global assigned access to [here](https://docs.microsoft.com/hololens/hololens-global-assigned-access-kiosk).</span></span>
1. <span data-ttu-id="5ca74-169">我們建議您停用下列 (選用的) 功能：</span><span class="sxs-lookup"><span data-stu-id="5ca74-169">We recommend disabling the follow (optional) capabilities:</span></span>
    1. <span data-ttu-id="5ca74-170">在 [這裡](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowdeveloperunlock)將裝置設為開發人員模式的能力。</span><span class="sxs-lookup"><span data-stu-id="5ca74-170">Ability to put the device into developer mode [here](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowdeveloperunlock).</span></span>
    1. <span data-ttu-id="5ca74-171">將 HoloLens 連接至電腦以複製日期的能力 [停用 USB](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection)。</span><span class="sxs-lookup"><span data-stu-id="5ca74-171">Ability to connect the HoloLens to a PC to copy date [disable USB](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection).</span></span>
       > [!NOTE]
        > <span data-ttu-id="5ca74-172">如果您不想停用 USB，但想要將預配套件套用至使用 USB 的裝置，請依照 [**此處**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)所列的指示進行。</span><span class="sxs-lookup"><span data-stu-id="5ca74-172">If you don’t want to disable USB but want the ability to apply a provisioning package to the device using USB, follow the instructions listed [**here**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage).</span></span>

1. <span data-ttu-id="5ca74-173">在 HoloLens 2 裝置上使用 [WDAC](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) 來允許或黑色 app。</span><span class="sxs-lookup"><span data-stu-id="5ca74-173">Use [WDAC](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) to allow or black apps on the HoloLens 2 device.</span></span>
1. <span data-ttu-id="5ca74-174">將遠端協助更新為安裝程式中的最新版本。</span><span class="sxs-lookup"><span data-stu-id="5ca74-174">Update Remote Assist to the latest version as part of the setup.</span></span> <span data-ttu-id="5ca74-175">有兩個選項可以執行此動作：</span><span class="sxs-lookup"><span data-stu-id="5ca74-175">There are two options to do this:</span></span>
    1. <span data-ttu-id="5ca74-176">若要執行此動作，您可以移至 Windows **Microsoft 網上商店，> 遠端協助--> 與更新 App**。</span><span class="sxs-lookup"><span data-stu-id="5ca74-176">This can be done by going to Windows **Microsoft Store --> Remote Assist --> and Update App**.</span></span>
    1. <span data-ttu-id="5ca74-177">另一種方法是將 HoloLens 2 插在夜間，以進行自動更新。</span><span class="sxs-lookup"><span data-stu-id="5ca74-177">Another method is to leave the HoloLens 2 plugged in overnight for auto update.</span></span>
1. <span data-ttu-id="5ca74-178">[停](https://docs.microsoft.com/hololens/settings-uri-list) 用 [網路設定] 以外的所有 [設定] 頁面，以允許使用者連線至用戶端網站上的來賓網路。</span><span class="sxs-lookup"><span data-stu-id="5ca74-178">[Disable all settings pages](https://docs.microsoft.com/hololens/settings-uri-list) except the network settings to allow users to connect to guest networks at client sites.</span></span>
1. [<span data-ttu-id="5ca74-179">管理 HoloLens 更新</span><span class="sxs-lookup"><span data-stu-id="5ca74-179">Manage HoloLens Updates</span></span>](https://docs.microsoft.com/hololens/hololens-updates)
    1. <span data-ttu-id="5ca74-180">[控制 OS 更新](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings)或允許自由流動的選項。</span><span class="sxs-lookup"><span data-stu-id="5ca74-180">Option to [control OS updates](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings) or allow to flow freely.</span></span>
1. <span data-ttu-id="5ca74-181">[常見的裝置限制](https://docs.microsoft.com/hololens/hololens-common-device-restrictions)。</span><span class="sxs-lookup"><span data-stu-id="5ca74-181">[Common Device Restrictions](https://docs.microsoft.com/hololens/hololens-common-device-restrictions).</span></span>
