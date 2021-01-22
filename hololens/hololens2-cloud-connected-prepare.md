---
title: 部署指南–雲端連接的 HoloLens 2 部署（含遠端協助的規模）準備
description: 瞭解如何使用 azure active directory 和身分識別管理，瞭解如何準備透過雲端連接的網路註冊 HoloLens 裝置。
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
ms.openlocfilehash: 067917396631f9a89a50b13ef1b7dcca8b631f52
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283864"
---
# <span data-ttu-id="21b62-104">準備-雲端連接指南</span><span class="sxs-lookup"><span data-stu-id="21b62-104">Prepare - Cloud connected Guide</span></span>

<span data-ttu-id="21b62-105">在本文的結尾，您將會設定 Azure AD、MDM，並深入瞭解如何使用 Azure AD 帳戶和網路需求。</span><span class="sxs-lookup"><span data-stu-id="21b62-105">By the end of this article you will have set up Azure AD, MDM, and understand more about using Azure AD accounts and network requirements.</span></span> <span data-ttu-id="21b62-106">本指南的本節將協助您和您的組織準備將 HoloLens 2 部署到雲端，並使用 Dynamics 365 遠端協助。</span><span class="sxs-lookup"><span data-stu-id="21b62-106">This section of the guide will help you and your organization get prepared to deploy HoloLens 2 to the cloud and use Dynamics 365 Remote Assist.</span></span> <span data-ttu-id="21b62-107">它將會超越您基礎結構每個部分的重要性，並提供輔助線連結，協助您視需要設定這些元件。</span><span class="sxs-lookup"><span data-stu-id="21b62-107">It will go over the importance of each piece of your infrastructure as well as providing links to guides to help you set up those pieces as needed.</span></span>

## <span data-ttu-id="21b62-108">基礎結構基本資訊</span><span class="sxs-lookup"><span data-stu-id="21b62-108">Infrastructure Essentials</span></span>

<span data-ttu-id="21b62-109">針對個人和公司部署案例，MDM system 是部署和管理 Windows 10 全息裝置所需的基本基礎結構。</span><span class="sxs-lookup"><span data-stu-id="21b62-109">For both personal and corporate deployment scenarios, an MDM system is the essential infrastructure required to deploy and manage Windows 10 Holographic devices.</span></span> <span data-ttu-id="21b62-110">建議使用 Azure AD Premium 訂用帳戶做為身分識別提供者，並且需要有此訂用帳戶才能支援特定功能。</span><span class="sxs-lookup"><span data-stu-id="21b62-110">An Azure AD premium subscription is recommended as an identity provider and required to support certain capabilities.</span></span>

### <span data-ttu-id="21b62-111">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="21b62-111">Azure Active Directory</span></span>

<span data-ttu-id="21b62-112">Azure AD 是一種雲端式的目錄服務，可提供身分識別和存取管理功能。</span><span class="sxs-lookup"><span data-stu-id="21b62-112">Azure AD is a cloud-based directory service that provides identity and access management.</span></span> <span data-ttu-id="21b62-113">使用 Microsoft Office 365 或 Intune 的組織已在使用 Azure AD，其中包含三個版本：免費、高級 P1 及 Premium P2 (請參閱 [Azure Active Directory 版本](https://azure.microsoft.com/documentation/articles/active-directory-editions)。 ) 所有版本都支援 azure AD 裝置註冊，但需要使用 Premium P1 來啟用在本指南中我們將使用的 MDM 自動註冊。</span><span class="sxs-lookup"><span data-stu-id="21b62-113">Organizations that use Microsoft Office 365 or Intune are already using Azure AD, which has three editions: Free, Premium P1, and Premium P2 (see [Azure Active Directory editions](https://azure.microsoft.com/documentation/articles/active-directory-editions).) All editions support Azure AD device registration, but Premium P1 is required to enable MDM auto-enrollment which we will be using in this guide later.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="21b62-114">若要讓 Azure Active Directory 成為 HoloLens 裝置不支援內部部署廣告連接，就是必要的做法。</span><span class="sxs-lookup"><span data-stu-id="21b62-114">It is essential to have an Azure Active Directory as HoloLens devices do not support on-premises AD join.</span></span> <span data-ttu-id="21b62-115">如果您不是&#39;t 已設定 Azure Active Directory，請依照此連結中的指示開始， [在 Azure Active directory 中建立新的租](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-access-create-new-tenant)使用者。</span><span class="sxs-lookup"><span data-stu-id="21b62-115">If you don&#39;t already have an Azure Active Directory set up follow the instructions in this link to get started and [Create a new tenant in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-access-create-new-tenant).</span></span>

## <span data-ttu-id="21b62-116">身分識別管理</span><span class="sxs-lookup"><span data-stu-id="21b62-116">Identity Management</span></span>

<span data-ttu-id="21b62-117">員工只能使用一個帳戶來初始化裝置，因此您的組織必須先控制要啟用哪個帳戶才能&#39;s。</span><span class="sxs-lookup"><span data-stu-id="21b62-117">Employees can use only one account to initialize a device so it&#39;s imperative that your organization controls which account is enabled first.</span></span> <span data-ttu-id="21b62-118">所選擇的帳戶將決定誰能夠控制裝置，而且會影響您的管理功能。</span><span class="sxs-lookup"><span data-stu-id="21b62-118">The account chosen will determine who controls the device and influence your management capabilities.</span></span>

<span data-ttu-id="21b62-119">在本指南中，我們已選取 [針對使用的身分 [識別](https://docs.microsoft.com/hololens/hololens-identity) ，我們將會使用 azure AD 帳戶或 Azure Active Directory 帳戶]。</span><span class="sxs-lookup"><span data-stu-id="21b62-119">In this guide we have chosen that for the [Identity](https://docs.microsoft.com/hololens/hololens-identity) used we will use Azure AD accounts, or Azure Active Directory accounts.</span></span> <span data-ttu-id="21b62-120">我們想要使用的 Azure AD 帳戶有數個優點，例如：</span><span class="sxs-lookup"><span data-stu-id="21b62-120">There are several benefits to Azure AD accounts we would like to use, such as:</span></span>

- <span data-ttu-id="21b62-121">員工使用其 Azure AD 帳戶在 Azure AD 中註冊裝置，並自動向組織&#39;的 MDM 方案註冊， (Azure AD + MDM –需要 Azure AD Premium) 。</span><span class="sxs-lookup"><span data-stu-id="21b62-121">Employees use their Azure AD account to register the device in Azure AD and automatically enroll it with the organization&#39;s MDM solution (Azure AD+MDM – requires Azure AD Premium).</span></span>
- <span data-ttu-id="21b62-122">Azure AD 帳戶支援 [單一登入](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on)。</span><span class="sxs-lookup"><span data-stu-id="21b62-122">Azure AD accounts support [Single Sign On](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on).</span></span> <span data-ttu-id="21b62-123">當使用者登入遠端協助時，系統就會辨識已登入的 Azure AD 使用者身分識別，且使用者會登入 app 以簡化體驗。</span><span class="sxs-lookup"><span data-stu-id="21b62-123">When a user signs into Remote Assist, their Identity from the signed in Azure AD user will be recognized and the user will be signed into the app for a streamlined experience.</span></span>
- <span data-ttu-id="21b62-124">Azure AD 帳戶透過[Windows Hello 企業版](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification)提供其他[驗證選項](https://docs.microsoft.com/hololens/hololens-identity)。</span><span class="sxs-lookup"><span data-stu-id="21b62-124">Azure AD accounts have additional [authentication options](https://docs.microsoft.com/hololens/hololens-identity) via [Windows Hello for Business](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification).</span></span> <span data-ttu-id="21b62-125">除了虹彩登入使用者之外，您還可以從另一個裝置登入，或使用 FIDO 安全性金鑰。</span><span class="sxs-lookup"><span data-stu-id="21b62-125">In addition to Iris log-in users can sign in from another device or use FIDO security keys.</span></span>

### <span data-ttu-id="21b62-126">行動裝置管理</span><span class="sxs-lookup"><span data-stu-id="21b62-126">Mobile Device Management</span></span>

<span data-ttu-id="21b62-127">Microsoft [Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)是企業行動裝置 + 安全性的一部分，是一個雲端型的 MDM 系統，可管理連接至您租使用者的裝置。</span><span class="sxs-lookup"><span data-stu-id="21b62-127">Microsoft [Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune), part of the Enterprise Mobility + Security, is a cloud-based MDM system that manages devices connected to your tenant.</span></span> <span data-ttu-id="21b62-128">就像 Office 365，Intune 使用 Azure AD 進行身分識別管理，因此員工使用相同的認證，在 Intune 中註冊裝置，以登入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="21b62-128">Like Office 365, Intune uses Azure AD for identity management, so employees use the same credentials to enroll devices in Intune that they use to sign into Office 365.</span></span> <span data-ttu-id="21b62-129">Intune 也支援執行其他作業系統（例如 iOS 和 Android）的裝置，以提供完整的 MDM 方案。</span><span class="sxs-lookup"><span data-stu-id="21b62-129">Intune also supports devices that run other operating systems, such as iOS and Android, to provide a complete MDM solution.</span></span> <span data-ttu-id="21b62-130">針對本指南的用途，我們&#39;將重點放在使用 Intune 來啟用雲端部署與 HoloLens 2。</span><span class="sxs-lookup"><span data-stu-id="21b62-130">For the purposes of this guide, we&#39;ll be focusing on using Intune for enabling a cloud deployment at scale with HoloLens 2.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="21b62-131">必須具備行動裝置管理的基本功能。</span><span class="sxs-lookup"><span data-stu-id="21b62-131">It is essential to have Mobile Device Management.</span></span> <span data-ttu-id="21b62-132">如果您不是&#39;t 已設定，請依照此指南進行，並 [開始使用 Intune](https://docs.microsoft.com/mem/intune/fundamentals/free-trial-sign-up)。</span><span class="sxs-lookup"><span data-stu-id="21b62-132">If you don&#39;t already have it set up follow this guide and [Get started with Intune](https://docs.microsoft.com/mem/intune/fundamentals/free-trial-sign-up).</span></span>

> [!NOTE]
> <span data-ttu-id="21b62-133">有多個 MDM 系統支援 Windows 10，而大部分都支援個人裝置和公司裝置的部署案例。</span><span class="sxs-lookup"><span data-stu-id="21b62-133">Multiple MDM systems support Windows 10 and most support personal and corporate device deployment scenarios.</span></span> <span data-ttu-id="21b62-134">支援 Windows 10 全息版的 MDM 提供者目前包含： AirWatch、MobileIron 及其他人。</span><span class="sxs-lookup"><span data-stu-id="21b62-134">MDM providers that support Windows 10 Holographic currently include: AirWatch, MobileIron, and others.</span></span> <span data-ttu-id="21b62-135">大部分業界領先的 MDM 廠商都已經支援與 Azure AD 整合。</span><span class="sxs-lookup"><span data-stu-id="21b62-135">Most industry-leading MDM vendors already support integration with Azure AD.</span></span> <span data-ttu-id="21b62-136">您可以在 [Azure Marketplace](https://azure.microsoft.com/marketplace/) 中找到支援 Azure AD 的 MDM 廠商。</span><span class="sxs-lookup"><span data-stu-id="21b62-136">You can find the MDM vendors that support Azure AD in [Azure Marketplace](https://azure.microsoft.com/marketplace/).</span></span>

## <span data-ttu-id="21b62-137">網路</span><span class="sxs-lookup"><span data-stu-id="21b62-137">Network</span></span>

<span data-ttu-id="21b62-138">在這項設定中，我們會預計使用任何可用的開啟 Wi-Fi 網路，將 HoloLens 2 裝置連線至網際網路。</span><span class="sxs-lookup"><span data-stu-id="21b62-138">In this setup, we anticipate HoloLens 2 devices connecting to the Internet from any available open Wi-Fi network.</span></span> <span data-ttu-id="21b62-139">因為使用者可能需要根據位置來變更網路連線，所以他們應該瞭解如何 [將 HoloLens 裝置連線到 wi-fi。](https://docs.microsoft.com/hololens/hololens-network)</span><span class="sxs-lookup"><span data-stu-id="21b62-139">Since a user could need to change the network connection based on location, they should learn how to [connect HoloLens devices to Wi-Fi.](https://docs.microsoft.com/hololens/hololens-network)</span></span>

<span data-ttu-id="21b62-140">針對 Dynamics 365 遠端協助有多種網路狀況，包括頻寬、延遲、抖動及資料包遺失等，可能會影響您的影片通話體驗。</span><span class="sxs-lookup"><span data-stu-id="21b62-140">For Dynamics 365 Remote Assist there are a variety of network conditions, including bandwidth, latency, jitter, and packet loss, that can impact your video calling experience.</span></span> <span data-ttu-id="21b62-141">雖然在頻寬降低的環境中可能會有音訊及視頻通話，但您可能會遇到功能下降的問題。</span><span class="sxs-lookup"><span data-stu-id="21b62-141">Although audio and video calls might be possible in environments with reduced bandwidth, you might experience feature degradation.</span></span> <span data-ttu-id="21b62-142">在在 HoloLens 上使用 Dynamics 365 遠端協助時，請記住下列網路需求：</span><span class="sxs-lookup"><span data-stu-id="21b62-142">When using Dynamics 365 Remote Assist on HoloLens here are the network requirements to keep in mind:</span></span>

<span data-ttu-id="21b62-143">**最低** ：針對對等 hd 品質視頻通話需要 1.5 Mbps，且解析度為 30 FPS 的 hd 1080p。</span><span class="sxs-lookup"><span data-stu-id="21b62-143">**Minimum** : 1.5 Mbps up/down is required for peer-to-peer HD quality video calling with resolution of HD 1080p at 30 fps.</span></span>

<span data-ttu-id="21b62-144">**最佳：** 針對使用高清1080p 解析度的對等 HD 品質視頻通話，應為 4-5 Mbps。</span><span class="sxs-lookup"><span data-stu-id="21b62-144">**Optimal:** For peer-to-peer HD quality video calling with resolution of HD 1080p, 4-5 Mbps up/down should be expected.</span></span>

<span data-ttu-id="21b62-145">詳細資訊：</span><span class="sxs-lookup"><span data-stu-id="21b62-145">More information:</span></span>

- [<span data-ttu-id="21b62-146">網路需求</span><span class="sxs-lookup"><span data-stu-id="21b62-146">Network requirements</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#network-requirements)
- [<span data-ttu-id="21b62-147">網路優化建議</span><span class="sxs-lookup"><span data-stu-id="21b62-147">Network optimization recommendations</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#dynamics-365-remote-assist-hololens)

### <span data-ttu-id="21b62-148">選用：將您的 HoloLens 連接至 VPN</span><span class="sxs-lookup"><span data-stu-id="21b62-148">Optional: Connect your HoloLens to VPN</span></span>

<span data-ttu-id="21b62-149">連接到本指南的裝置將會透過與外部雲端網路連線至網路。</span><span class="sxs-lookup"><span data-stu-id="21b62-149">The devices being connected into this guide are going to connect to the network via and external cloud network.</span></span> <span data-ttu-id="21b62-150">可能是要存取公司資源，您&#39;需要透過 VPN 連線裝置。</span><span class="sxs-lookup"><span data-stu-id="21b62-150">It may be that to access company resources you&#39;ll need to connect your devices via VPN.</span></span> <span data-ttu-id="21b62-151">有數種不同的方法可以將裝置連線至 VPN，使用者可以在其中使用裝置 UI 連線，或從 PPKG 或 MDM 管理裝置並接收 VPN 設定檔。</span><span class="sxs-lookup"><span data-stu-id="21b62-151">There are several different ways to connect your devices to VPN, both where the end user can connect via using the device UI, or the devices can be managed and receive the VPN profile from either a PPKG or MDM.</span></span> <span data-ttu-id="21b62-152">如何設定 VPN 獲勝&#39;在本文中，如果您&#39;想要深入瞭解不同的 VPN 協定或管理 VPN 的方法，請參閱 [這些指南以取得 HoloLens 和 VPN 的相關資訊。](https://docs.microsoft.com/hololens/hololens-network#vpn)</span><span class="sxs-lookup"><span data-stu-id="21b62-152">How to set up VPN won&#39;t be covered in this article, so if you&#39;d like to learn more about the different VPN protocols or ways to manage VPN visit [these guides for information on HoloLens and VPN.](https://docs.microsoft.com/hololens/hololens-network#vpn)</span></span>

## <span data-ttu-id="21b62-153">後續步驟</span><span class="sxs-lookup"><span data-stu-id="21b62-153">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="21b62-154">雲端連接部署-設定</span><span class="sxs-lookup"><span data-stu-id="21b62-154">Cloud connected deployment - Configure</span></span>](hololens2-cloud-connected-configure.md)
