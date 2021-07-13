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
ms.openlocfilehash: acf4b5d730b9a7eee2dedfad2bb3f866931d7455
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "113636940"
---
# <a name="deploying-hololens-2-to-external-clients-with-remote-assist"></a><span data-ttu-id="37cca-103">使用遠端協助將 HoloLens 2 部署至外部用戶端</span><span class="sxs-lookup"><span data-stu-id="37cca-103">Deploying HoloLens 2 to External Clients with Remote Assist</span></span>

<span data-ttu-id="37cca-104">本指南可協助具有下列目標的 IT 專業人員在其組織中部署 Microsoft HoloLens 2 個裝置：</span><span class="sxs-lookup"><span data-stu-id="37cca-104">This guide helps IT professionals with the following goals deploy Microsoft HoloLens 2 devices in their organization:</span></span>

1. <span data-ttu-id="37cca-105">雲端連接 HoloLens 2 裝置</span><span class="sxs-lookup"><span data-stu-id="37cca-105">Cloud connect HoloLens 2 devices</span></span>
1. <span data-ttu-id="37cca-106">貸款 HoloLens 2 裝置至外部用戶端以供使用</span><span class="sxs-lookup"><span data-stu-id="37cca-106">Loan HoloLens 2 devices to external clients for use</span></span>
1. <span data-ttu-id="37cca-107">安全的已借出裝置</span><span class="sxs-lookup"><span data-stu-id="37cca-107">Secure loaned devices</span></span>

<span data-ttu-id="37cca-108">本指南將提供適用于大部分 HoloLens 2 部署案例的[一般 HoloLens 2 部署建議](#general-deployment-recommendations-and-instructions)，以及客戶部署遠端協助以進行外部使用時所遇到的[常見疑慮](#common-concerns)。</span><span class="sxs-lookup"><span data-stu-id="37cca-108">This guide will provide [general HoloLens 2 deployment recommendations](#general-deployment-recommendations-and-instructions) that is applicable to most HoloLens 2 deployment scenarios and [common concerns](#common-concerns) that customers have when deploying Remote Assist for external use.</span></span>

## <a name="scenario-description"></a><span data-ttu-id="37cca-109">案例描述</span><span class="sxs-lookup"><span data-stu-id="37cca-109">Scenario Description</span></span>

<span data-ttu-id="37cca-110">基於本檔的目的，Contoso 公司想要將 HoloLens 2 裝置送至外部用戶端的工廠，以進行短期或長期用途。</span><span class="sxs-lookup"><span data-stu-id="37cca-110">For the purpose of this document, Contoso Company wants to ship a HoloLens 2 device to an external client's plant for short-term or long-term use.</span></span> <span data-ttu-id="37cca-111">當用戶端需要協助服務機械時，用戶端會使用 Contoso 公司提供的認證登入 HoloLens 2 裝置，並使用遠端協助來與 contoso 公司的專家聯繫。</span><span class="sxs-lookup"><span data-stu-id="37cca-111">When the client needs assistance servicing machinery, the client will log into the HoloLens 2 device using credentials provided by Contoso Company and use Remote Assist to contact Contoso Company's experts.</span></span>

<span data-ttu-id="37cca-112">請 [在這裡](/hololens/hololens2-cloud-connected-overview#learn-about-remote-assist)深入瞭解遠端協助。</span><span class="sxs-lookup"><span data-stu-id="37cca-112">Learn more about Remote Assist [here](/hololens/hololens2-cloud-connected-overview#learn-about-remote-assist).</span></span>

### <a name="requirements-for-this-scenario"></a><span data-ttu-id="37cca-113">此案例的需求</span><span class="sxs-lookup"><span data-stu-id="37cca-113">Requirements for this Scenario</span></span>

1. [<span data-ttu-id="37cca-114">Azure AD</span><span class="sxs-lookup"><span data-stu-id="37cca-114">Azure AD</span></span>](/azure/active-directory/fundamentals/active-directory-whatis)
1. <span data-ttu-id="37cca-115">Mobile 裝置管理員-例如 [Intune](/mem/intune/fundamentals/free-trial-sign-up)</span><span class="sxs-lookup"><span data-stu-id="37cca-115">Mobile Device Manager - such as [Intune](/mem/intune/fundamentals/free-trial-sign-up)</span></span>
1. <span data-ttu-id="37cca-116">遠端協助授權</span><span class="sxs-lookup"><span data-stu-id="37cca-116">Remote Assist License</span></span>
    1. [<span data-ttu-id="37cca-117">購買遠端協助</span><span class="sxs-lookup"><span data-stu-id="37cca-117">Buy Remote Assist</span></span>](/dynamics365/mixed-reality/remote-assist/buy-remote-assist)
    1. [<span data-ttu-id="37cca-118">試用遠端協助</span><span class="sxs-lookup"><span data-stu-id="37cca-118">Trial Remote Assist</span></span>](/dynamics365/mixed-reality/remote-assist/try-remote-assist)

## <a name="common-concerns"></a><span data-ttu-id="37cca-119">常見考慮</span><span class="sxs-lookup"><span data-stu-id="37cca-119">Common Concerns</span></span>

- [<span data-ttu-id="37cca-120">如何確保外部用戶端沒有彼此通訊的能力</span><span class="sxs-lookup"><span data-stu-id="37cca-120">How to ensure that external clients do not have the ability to communicate with one another</span></span>](#how-to-ensure-that-external-clients-do-not-have-the-ability-to-communicate-with-one-another)
- [<span data-ttu-id="37cca-121">如何確保用戶端無法存取公司資源</span><span class="sxs-lookup"><span data-stu-id="37cca-121">How to ensure that clients do not have access to company resources</span></span>](#how-to-ensure-that-clients-do-not-have-access-to-company-resources)
- [<span data-ttu-id="37cca-122">如何限制應用程式</span><span class="sxs-lookup"><span data-stu-id="37cca-122">How to restrict apps</span></span>](#how-to-restrict-apps)
- [<span data-ttu-id="37cca-123">如何管理密碼</span><span class="sxs-lookup"><span data-stu-id="37cca-123">How to manage passwords</span></span>](#how-to-manage-passwords)
- [<span data-ttu-id="37cca-124">如何確保用戶端沒有聊天記錄的存取權</span><span class="sxs-lookup"><span data-stu-id="37cca-124">How to ensure that clients do not have access to chat history</span></span>](#how-to-ensure-that-clients-do-not-have-access-to-chat-history)

### <a name="how-to-ensure-that-external-clients-do-not-have-the-ability-to-communicate-with-one-another"></a><span data-ttu-id="37cca-125">如何確保外部用戶端沒有彼此通訊的能力</span><span class="sxs-lookup"><span data-stu-id="37cca-125">How to ensure that external clients do not have the ability to communicate with one another</span></span>

<span data-ttu-id="37cca-126">由於遠端協助 HoloLens HoloLens 呼叫不受支援，因此用戶端可以搜尋，但無法搜尋彼此通訊。</span><span class="sxs-lookup"><span data-stu-id="37cca-126">Since Remote Assist HoloLens to HoloLens calls are not supported, clients are able to search for, but are unable to, communicate with one another.</span></span> <span data-ttu-id="37cca-127">為了進一步限制用戶端可以搜尋和呼叫的物件，  [資訊屏障](/microsoft-365/compliance/information-barriers) 可以限制用戶端可以進行通訊的物件。</span><span class="sxs-lookup"><span data-stu-id="37cca-127">To further restrict who clients can search for and call,  [Information barriers](/microsoft-365/compliance/information-barriers) can restrict who a client can communicate with.</span></span> <span data-ttu-id="37cca-128">另一個要考慮的選項是使用 [範圍目錄搜尋](/MicrosoftTeams/teams-scoped-directory-search)</span><span class="sxs-lookup"><span data-stu-id="37cca-128">Another option to consider is using [Scoped Directory Search](/MicrosoftTeams/teams-scoped-directory-search)</span></span>

 > [!NOTE]
> <span data-ttu-id="37cca-129">由於已啟用單一登入，因此請務必使用 [**WDAC**](/hololens/windows-defender-application-control-wdac)停用瀏覽器。</span><span class="sxs-lookup"><span data-stu-id="37cca-129">Since single sign on is enabled, it is important to disable the browser using [**WDAC**](/hololens/windows-defender-application-control-wdac).</span></span> <span data-ttu-id="37cca-130">如果外部用戶端開啟瀏覽器，並使用 web 版本的 Teams，用戶端就可以存取通話/聊天記錄。</span><span class="sxs-lookup"><span data-stu-id="37cca-130">If an external client opens the browser and uses the web version of Teams, the client will have access to call/chat history.</span></span>

### <a name="how-to-ensure-that-clients-do-not-have-access-to-company-resources"></a><span data-ttu-id="37cca-131">如何確保用戶端無法存取公司資源</span><span class="sxs-lookup"><span data-stu-id="37cca-131">How to ensure that clients do not have access to company resources</span></span>

<span data-ttu-id="37cca-132">有兩個選項可考慮。</span><span class="sxs-lookup"><span data-stu-id="37cca-132">There are two options to consider.</span></span>

<span data-ttu-id="37cca-133">第一個選項是一種多層式方法：</span><span class="sxs-lookup"><span data-stu-id="37cca-133">The first option is a multi-layer approach:</span></span>

1. <span data-ttu-id="37cca-134">只指派使用者需要的授權。</span><span class="sxs-lookup"><span data-stu-id="37cca-134">Only assign licenses that the user requires.</span></span> <span data-ttu-id="37cca-135">如果您未將 OneDrive、Outlook、SharePoint、Yammer 等指派給使用者，他/她將無法存取這些資源。</span><span class="sxs-lookup"><span data-stu-id="37cca-135">If you do not assign OneDrive, Outlook, SharePoint, Yammer, etc. to the user, he/she will not have access to those resources.</span></span> <span data-ttu-id="37cca-136">使用者需要的唯一授權是開始的遠端協助、Intune 和 AAD 授權。</span><span class="sxs-lookup"><span data-stu-id="37cca-136">The only licenses the users will need is Remote Assist, Intune, and AAD licenses to begin.</span></span>
1. <span data-ttu-id="37cca-137">封鎖應用程式 (例如，您不希望用戶端存取的電子郵件)  (查看 [如何限制應用程式](#how-to-restrict-apps)) 。</span><span class="sxs-lookup"><span data-stu-id="37cca-137">Block apps (such as email) that you don’t want clients to access (See [How to restrict apps](#how-to-restrict-apps)).</span></span>
1. <span data-ttu-id="37cca-138">請勿與用戶端共用使用者名稱和密碼。</span><span class="sxs-lookup"><span data-stu-id="37cca-138">Do NOT share usernames nor password with clients.</span></span> <span data-ttu-id="37cca-139">若要登入 HoloLens 2，需要電子郵件和數位 PIN。</span><span class="sxs-lookup"><span data-stu-id="37cca-139">To log into the HoloLens 2, an email and numerical PIN is required.</span></span>

<span data-ttu-id="37cca-140">第二個選項是建立裝載用戶端的個別租使用者 (請參閱映射 1.1) 。</span><span class="sxs-lookup"><span data-stu-id="37cca-140">The second option is to create a separate tenant that hosts clients (see Image 1.1).</span></span>

<span data-ttu-id="37cca-141">**影像1。1**</span><span class="sxs-lookup"><span data-stu-id="37cca-141">**Image 1.1**</span></span>

![服務租使用者映射](./images/hololens-service-tenant-image.png)

### <a name="how-to-restrict-apps"></a><span data-ttu-id="37cca-143">如何限制應用程式</span><span class="sxs-lookup"><span data-stu-id="37cca-143">How to restrict apps</span></span>

<span data-ttu-id="37cca-144">[Kiosk 模式](/hololens/hololens-kiosk)和（或） [WDAC (Windows Defender 應用程式控制) ](/hololens/windows-defender-application-control-wdac)是限制應用程式的選項。</span><span class="sxs-lookup"><span data-stu-id="37cca-144">[Kiosk Mode](/hololens/hololens-kiosk) and/or [WDAC (Windows Defender Application Control)](/hololens/windows-defender-application-control-wdac) are options for restricting applications.</span></span>

### <a name="how-to-manage-passwords"></a><span data-ttu-id="37cca-145">如何管理密碼</span><span class="sxs-lookup"><span data-stu-id="37cca-145">How to manage passwords</span></span>

1. <span data-ttu-id="37cca-146">移除密碼到期。</span><span class="sxs-lookup"><span data-stu-id="37cca-146">Remove password expiration.</span></span> <span data-ttu-id="37cca-147">不過，這會增加帳戶遭到入侵的機會。</span><span class="sxs-lookup"><span data-stu-id="37cca-147">However, this increases the chance that an account will be compromised.</span></span> <span data-ttu-id="37cca-148">NIST 密碼建議每隔30-90 天會變更密碼。</span><span class="sxs-lookup"><span data-stu-id="37cca-148">NIST password recommendation is change passwords every 30-90 days.</span></span>
1. <span data-ttu-id="37cca-149">將 HoloLens 2 裝置的密碼到期延長超過90天。</span><span class="sxs-lookup"><span data-stu-id="37cca-149">Extend the password expiration for HoloLens 2 devices to exceed 90 days.</span></span>
1. <span data-ttu-id="37cca-150">裝置應該傳回給 Contoso 以變更密碼。</span><span class="sxs-lookup"><span data-stu-id="37cca-150">The devices should be returned to Contoso to change the passwords.</span></span> <span data-ttu-id="37cca-151">但是，如果裝置預期會在用戶端工廠的90天內，就會造成問題。</span><span class="sxs-lookup"><span data-stu-id="37cca-151">However, this can cause issues if the devices are expected to be in the client's plant for 90+ days.</span></span>  
1. <span data-ttu-id="37cca-152">針對傳送至多個用戶端的裝置，請在將裝置寄送至用戶端之前重設密碼。</span><span class="sxs-lookup"><span data-stu-id="37cca-152">For devices that are sent to multiple clients, reset passwords before shipping the device to clients.</span></span>

### <a name="how-to-ensure-that-clients-do-not-have-access-to-chat-history"></a><span data-ttu-id="37cca-153">如何確保用戶端沒有聊天記錄的存取權</span><span class="sxs-lookup"><span data-stu-id="37cca-153">How to ensure that clients do not have access to chat history</span></span>

<span data-ttu-id="37cca-154">遠端協助會在每個會話之後清除聊天記錄。</span><span class="sxs-lookup"><span data-stu-id="37cca-154">Remote Assist clears chat history after each session.</span></span> <span data-ttu-id="37cca-155">不過，聊天記錄將可供 Microsoft Teams 使用者使用。</span><span class="sxs-lookup"><span data-stu-id="37cca-155">However, the chat history will be available for the Microsoft Teams user.</span></span>

> [!NOTE]
> <span data-ttu-id="37cca-156">由於已啟用單一登入，因此請務必使用 [**WDAC**](/hololens/windows-defender-application-control-wdac)停用瀏覽器。</span><span class="sxs-lookup"><span data-stu-id="37cca-156">Since single sign on is enabled, it is important to disable the browser using [**WDAC**](/hololens/windows-defender-application-control-wdac).</span></span> <span data-ttu-id="37cca-157">如果外部用戶端開啟瀏覽器，並使用 web 版本的 Teams，用戶端就可以存取通話/聊天記錄。</span><span class="sxs-lookup"><span data-stu-id="37cca-157">If a external client opens the browser and uses the web version of Teams, the client will have access to call/chat history.</span></span>

## <a name="general-deployment-recommendations-and-instructions"></a><span data-ttu-id="37cca-158">一般部署建議和指示</span><span class="sxs-lookup"><span data-stu-id="37cca-158">General Deployment Recommendations and Instructions</span></span>

<span data-ttu-id="37cca-159">針對 HoloLens 2 部署步驟，我們建議下列各項：</span><span class="sxs-lookup"><span data-stu-id="37cca-159">We recommend the following for HoloLens 2 deployment Steps:</span></span>

1. <span data-ttu-id="37cca-160">使用[最新的 HoloLens 作業系統版本](https://aka.ms/hololens2download)作為基準組建。</span><span class="sxs-lookup"><span data-stu-id="37cca-160">Use the [latest HoloLens OS release](https://aka.ms/hololens2download) as your baseline build.</span></span>
1. <span data-ttu-id="37cca-161">指派以使用者為基礎或以裝置為基礎的授權：</span><span class="sxs-lookup"><span data-stu-id="37cca-161">Assign user-based or device-based licenses:</span></span>
    1. <span data-ttu-id="37cca-162">以使用者為基礎及以裝置為基礎的授權都遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="37cca-162">User-based and device-based licenses both follow the following steps:</span></span>
        1. <span data-ttu-id="37cca-163">[在 AAD 中建立群組，並](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal#create-a-basic-group-and-add-members)為 HoloLens/RA 使用者新增成員。</span><span class="sxs-lookup"><span data-stu-id="37cca-163">[Create a group in AAD and add members](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal#create-a-basic-group-and-add-members) for HoloLens/RA users.</span></span>
        1. <span data-ttu-id="37cca-164">[將以裝置為基礎或以使用者為基礎的授權指派](/azure/active-directory/enterprise-users/licensing-groups-assign#:~:text=In%20this%20article%201%20Assign%20the%20required%20licenses,3%20Check%20for%20license%20problems%20and%20resolve%20them) 給此群組。</span><span class="sxs-lookup"><span data-stu-id="37cca-164">[Assign device-based or user-based licenses](/azure/active-directory/enterprise-users/licensing-groups-assign#:~:text=In%20this%20article%201%20Assign%20the%20required%20licenses,3%20Check%20for%20license%20problems%20and%20resolve%20them) to this group.</span></span>
        1. <span data-ttu-id="37cca-165"> (選擇性) 您可以將 MDM 原則的目標群組設為目標。</span><span class="sxs-lookup"><span data-stu-id="37cca-165">(Optional) You can target groups for MDM policies.</span></span>

1. <span data-ttu-id="37cca-166">裝置應該已加入您的租使用者、 [自動註冊](/hololens/hololens-enroll-mdm#auto-enrollment-in-mdm)，並透過 [自動試驗](/hololens/hololens2-autopilot)設定。</span><span class="sxs-lookup"><span data-stu-id="37cca-166">Devices should be AAD joined to your tenant, [Auto Enrolled](/hololens/hololens-enroll-mdm#auto-enrollment-in-mdm), and configured through [Auto Pilot](/hololens/hololens2-autopilot).</span></span>
    1. <span data-ttu-id="37cca-167">請注意，裝置上的第一個使用者將會是裝置擁有者。</span><span class="sxs-lookup"><span data-stu-id="37cca-167">Please note that the first user on the device will be the device owner.</span></span>
    1. <span data-ttu-id="37cca-168">請注意，如果裝置已加入 AAD，執行聯結的使用者就會成為裝置擁有者。</span><span class="sxs-lookup"><span data-stu-id="37cca-168">Please note that if the device is AAD joined, the user that performed the join is made device owner.</span></span>
    1. <span data-ttu-id="37cca-169">如需詳細資訊，請參閱 [裝置擁有](/hololens/security-adminless-os#device-owner)者。</span><span class="sxs-lookup"><span data-stu-id="37cca-169">For more, see [Device Owner](/hololens/security-adminless-os#device-owner).</span></span>
1. <span data-ttu-id="37cca-170">[租使用者鎖定](/hololens/hololens-release-notes#tenantlockdown-csp-and-autopilot) 裝置，使其只能加入您的租使用者。</span><span class="sxs-lookup"><span data-stu-id="37cca-170">[Tenant lock](/hololens/hololens-release-notes#tenantlockdown-csp-and-autopilot) the device so that it can only joined your tenant.</span></span>
    1. <span data-ttu-id="37cca-171">**其他連結：** [租使用者鎖定 CSP](/windows/client-management/mdm/tenantlockdown-csp)。</span><span class="sxs-lookup"><span data-stu-id="37cca-171">**Additional Link:** [Tenant lock CSP](/windows/client-management/mdm/tenantlockdown-csp).</span></span>
1. <span data-ttu-id="37cca-172">使用 [這裡](/hololens/hololens-global-assigned-access-kiosk)的全域指派存取設定 kiosk。</span><span class="sxs-lookup"><span data-stu-id="37cca-172">Configure kiosk using global assigned access to [here](/hololens/hololens-global-assigned-access-kiosk).</span></span>
1. <span data-ttu-id="37cca-173">建議您停用下列 (選用) 功能：</span><span class="sxs-lookup"><span data-stu-id="37cca-173">We recommend disabling the follow (optional) capabilities:</span></span>
    1. <span data-ttu-id="37cca-174">讓裝置進入開發 [人員模式的](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowdeveloperunlock)功能。</span><span class="sxs-lookup"><span data-stu-id="37cca-174">Ability to put the device into developer mode [here](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowdeveloperunlock).</span></span>
    1. <span data-ttu-id="37cca-175">將 HoloLens 連接到電腦以複製日期[停用 USB](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection)的能力。</span><span class="sxs-lookup"><span data-stu-id="37cca-175">Ability to connect the HoloLens to a PC to copy date [disable USB](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection).</span></span>
       > [!NOTE]
        > <span data-ttu-id="37cca-176">如果您不想要停用 USB，但想要能夠使用 USB 將布建套件套用至裝置，請遵循 [**此處**](/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)所列的指示。</span><span class="sxs-lookup"><span data-stu-id="37cca-176">If you don’t want to disable USB but want the ability to apply a provisioning package to the device using USB, follow the instructions listed [**here**](/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage).</span></span>

1. <span data-ttu-id="37cca-177">使用[WDAC](/hololens/windows-defender-application-control-wdac)來允許或封鎖 HoloLens 2 裝置上的應用程式。</span><span class="sxs-lookup"><span data-stu-id="37cca-177">Use [WDAC](/hololens/windows-defender-application-control-wdac) to allow or block apps on the HoloLens 2 device.</span></span>
1. <span data-ttu-id="37cca-178">在安裝過程中，將遠端協助更新為最新版本。</span><span class="sxs-lookup"><span data-stu-id="37cca-178">Update Remote Assist to the latest version as part of the setup.</span></span> <span data-ttu-id="37cca-179">有兩個選項可以執行此作業：</span><span class="sxs-lookup"><span data-stu-id="37cca-179">There are two options to do this:</span></span>
    1. <span data-ttu-id="37cca-180">若要這麼做，請前往 Windows **Microsoft Store--> 遠端協助--> 和更新應用程式**。</span><span class="sxs-lookup"><span data-stu-id="37cca-180">This can be done by going to Windows **Microsoft Store --> Remote Assist --> and Update App**.</span></span>
    1. <span data-ttu-id="37cca-181">[ApplicationManagement/AllowAppStoreAutoUpdate](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowappstoreautoupdate) -允許自動應用程式更新-預設為啟用。</span><span class="sxs-lookup"><span data-stu-id="37cca-181">[ApplicationManagement/AllowAppStoreAutoUpdate](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowappstoreautoupdate) - which allows automatic app updates - is enabled by default.</span></span> <span data-ttu-id="37cca-182">讓裝置保持插入以接收更新。</span><span class="sxs-lookup"><span data-stu-id="37cca-182">Keep the device plugged in to receive updates.</span></span>
1. <span data-ttu-id="37cca-183">停用網路設定以外的[所有設定頁面](/hololens/settings-uri-list)，以允許使用者連線到用戶端網站上的來賓網路。</span><span class="sxs-lookup"><span data-stu-id="37cca-183">[Disable all settings pages](/hololens/settings-uri-list) except the network settings to allow users to connect to guest networks at client sites.</span></span>
1. [<span data-ttu-id="37cca-184">管理 HoloLens 更新</span><span class="sxs-lookup"><span data-stu-id="37cca-184">Manage HoloLens Updates</span></span>](/hololens/hololens-updates)
    1. <span data-ttu-id="37cca-185">[控制作業系統更新](/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings)或允許自由流動的選項。</span><span class="sxs-lookup"><span data-stu-id="37cca-185">Option to [control OS updates](/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings) or allow to flow freely.</span></span>
1. <span data-ttu-id="37cca-186">[常見的裝置限制](/hololens/hololens-common-device-restrictions)。</span><span class="sxs-lookup"><span data-stu-id="37cca-186">[Common Device Restrictions](/hololens/hololens-common-device-restrictions).</span></span>
