---
title: 使用遠端協助來瞭解雲端連線的 HoloLens 2
description: 瞭解如何使用 Dynamics 365 遠端協助，在連線到雲端的網路上註冊 HoloLens 2 裝置。
keywords: HoloLens、管理、雲端連線、遠端協助、AAD、Azure AD、MDM、Mobile 裝置管理
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
ms.openlocfilehash: a44247b4afea747e4b75c974fcae344380909989
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923528"
---
# <a name="deployment-guide--cloud-connected-hololens-2-with-remote-assist--overview"></a><span data-ttu-id="1851b-104">部署指南–與遠端協助的雲端連線 HoloLens 2 –總覽</span><span class="sxs-lookup"><span data-stu-id="1851b-104">Deployment Guide – Cloud connected HoloLens 2 with Remote Assist – Overview</span></span>

<span data-ttu-id="1851b-105">本指南可協助 IT 專業人員規劃和部署 Microsoft HoloLens 2 裝置，並在其組織中提供遠端協助。</span><span class="sxs-lookup"><span data-stu-id="1851b-105">This guide will help IT professionals plan for and deploy Microsoft HoloLens 2 devices with Remote Assist to their organization.</span></span> <span data-ttu-id="1851b-106">這將作為您組織中各種 HoloLens 2 使用案例的概念證明部署的模型。</span><span class="sxs-lookup"><span data-stu-id="1851b-106">This will serve as a model for proof-of-concept deployments to your organization across a variety of HoloLens 2 use cases.</span></span> <span data-ttu-id="1851b-107">這項設定類似于 [案例 A：部署至雲端連接裝置](https://docs.microsoft.com/hololens/common-scenarios#scenario-a)。</span><span class="sxs-lookup"><span data-stu-id="1851b-107">The setup is similar to [Scenario A: Deploy to cloud connect devices](https://docs.microsoft.com/hololens/common-scenarios#scenario-a).</span></span> 

<span data-ttu-id="1851b-108">在本指南中，我們將討論如何在裝置管理中註冊您的裝置、視需要套用授權，以及驗證您的終端使用者是否能夠在裝置設定時立即使用遠端協助。</span><span class="sxs-lookup"><span data-stu-id="1851b-108">During the guide, we will cover how to enroll your devices into your device management, apply licenses as needed, and validate that your end users are able to immediately use Remote Assist upon device setup.</span></span> <span data-ttu-id="1851b-109">為了達成此目的，我們將探討設定和執行所需的重要基礎結構，也就是使用 HoloLens 2 來大規模部署。</span><span class="sxs-lookup"><span data-stu-id="1851b-109">To do this, we will go over the important pieces of infrastructure needed to get set up and running – achieving deployment at scale with HoloLens 2.</span></span> <span data-ttu-id="1851b-110">本指南不會再套用任何其他裝置限制或設定，但我們建議您在完成後探索這些選項。</span><span class="sxs-lookup"><span data-stu-id="1851b-110">No other device restrictions or configurations will be applied in this guide, however, we encourage you to explore those options after finishing.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1851b-111">必要條件</span><span class="sxs-lookup"><span data-stu-id="1851b-111">Prerequisites</span></span>

<span data-ttu-id="1851b-112">下列基礎結構應該已準備好部署 HoloLens 2。</span><span class="sxs-lookup"><span data-stu-id="1851b-112">The following infrastructure should be in place in order to deploy the HoloLens 2.</span></span> <span data-ttu-id="1851b-113">如果不是，則本指南包含設定 Azure 和 Intune：</span><span class="sxs-lookup"><span data-stu-id="1851b-113">If not, setting up Azure and Intune is included in this guide:</span></span>

- <span data-ttu-id="1851b-114">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="1851b-114">Wi-Fi</span></span>
    - <span data-ttu-id="1851b-115">網路通常會開放給網際網路和雲端服務</span><span class="sxs-lookup"><span data-stu-id="1851b-115">Networks are typically open to the Internet and Cloud services</span></span>
- <span data-ttu-id="1851b-116">Azure Active Directory (Azure AD) 加入 MDM 自動註冊 (Azure AD [P1 訂](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) 用帳戶) </span><span class="sxs-lookup"><span data-stu-id="1851b-116">Azure Active Directory (Azure AD) Join with MDM Auto Enrollment ([Azure AD P1 subscription](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) needed)</span></span>
- <span data-ttu-id="1851b-117">MDM (Intune) 受控</span><span class="sxs-lookup"><span data-stu-id="1851b-117">MDM (Intune) Managed</span></span>
    - <span data-ttu-id="1851b-118">透過 MDM 部署一或多個應用程式。</span><span class="sxs-lookup"><span data-stu-id="1851b-118">One or more applications are deployed via MDM.</span></span>
- <span data-ttu-id="1851b-119">使用者以自己的公司帳戶登入 (Azure AD) </span><span class="sxs-lookup"><span data-stu-id="1851b-119">Users sign in with their own corporate account (Azure AD)</span></span>
    - <span data-ttu-id="1851b-120">支援每個裝置的單一或多個使用者。</span><span class="sxs-lookup"><span data-stu-id="1851b-120">Single or multiple users per device is supported.</span></span>

:::image type="content" alt-text="雲端連線案例" source="./images/deployment-guides-revised-scenario-a.png" lightbox="./images/deployment-guides-revised-scenario-a.png":::


## <a name="learn-about-remote-assist"></a><span data-ttu-id="1851b-122">深入瞭解遠端協助</span><span class="sxs-lookup"><span data-stu-id="1851b-122">Learn about Remote Assist</span></span>

<span data-ttu-id="1851b-123">遠端協助可讓您進行共同維護和修復、遠端檢查，以及知識共用和定型。</span><span class="sxs-lookup"><span data-stu-id="1851b-123">Remote Assist allows for collaborative maintenance and repair, remote inspection, as well as knowledge sharing and training.</span></span> <span data-ttu-id="1851b-124">藉由連接不同角色和位置的人員，使用遠端協助的技術人員可以與 Microsoft 團隊的遠端共同作業者聯繫。</span><span class="sxs-lookup"><span data-stu-id="1851b-124">By connecting people in different roles and locations a technician using Remote Assist can connect with a remote collaborator on Microsoft Teams.</span></span> <span data-ttu-id="1851b-125">它們可以結合影片、螢幕擷取畫面和注釋來即時解決問題，即使它們不在相同的位置&#39;t 也一樣。</span><span class="sxs-lookup"><span data-stu-id="1851b-125">They can combine video, screenshots, and annotations to solve problems in real time even when they aren&#39;t in the same location.</span></span> <span data-ttu-id="1851b-126">遠端共同作業者可以在技術人員&#39;的實體空間中插入參考影像、圖解和其他實用資訊，讓他們可以參考此示意性，同時也能在 HoloLens 上運作並無人參與。</span><span class="sxs-lookup"><span data-stu-id="1851b-126">Remote collaborators can insert reference images, schematics, and other helpful information the technician&#39;s physical space so they can refer to the schematic while working heads-up and hands-free on HoloLens.</span></span>

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="remote-assist-licensing-and-requirements"></a><span data-ttu-id="1851b-127">遠端協助授權和需求</span><span class="sxs-lookup"><span data-stu-id="1851b-127">Remote Assist Licensing and Requirements</span></span>

- <span data-ttu-id="1851b-128">購買訂用帳戶和指派授權所需的 Azure AD 帳戶 () </span><span class="sxs-lookup"><span data-stu-id="1851b-128">Azure AD account (required for purchasing the subscription and assigning licenses)</span></span>
- <span data-ttu-id="1851b-129">[遠端協助訂閱](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (或 [遠端協助試用](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)) </span><span class="sxs-lookup"><span data-stu-id="1851b-129">[Remote Assist subscription](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (or [Remote Assist Trial](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist))</span></span>
    
#### <a name="dynamics-365-remote-assist-user"></a><span data-ttu-id="1851b-130">Dynamics 365 遠端協助使用者</span><span class="sxs-lookup"><span data-stu-id="1851b-130">Dynamics 365 Remote Assist user</span></span>

- <span data-ttu-id="1851b-131">遠端協助授權</span><span class="sxs-lookup"><span data-stu-id="1851b-131">Remote Assist license</span></span>
- <span data-ttu-id="1851b-132">網路連線</span><span class="sxs-lookup"><span data-stu-id="1851b-132">Network Connectivity</span></span>

#### <a name="microsoft-teams-user"></a><span data-ttu-id="1851b-133">Microsoft 小組使用者</span><span class="sxs-lookup"><span data-stu-id="1851b-133">Microsoft Teams user</span></span>

- <span data-ttu-id="1851b-134">Microsoft 小組或 [團隊免費增值](https://products.office.com/microsoft-teams/free)。</span><span class="sxs-lookup"><span data-stu-id="1851b-134">Microsoft Teams or [Teams Freemium](https://products.office.com/microsoft-teams/free).</span></span>
- <span data-ttu-id="1851b-135">網路連線</span><span class="sxs-lookup"><span data-stu-id="1851b-135">Network connectivity</span></span>

<span data-ttu-id="1851b-136">如果您打算執行此 [跨租使用者案例](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)，您可能需要資訊障礙授權。</span><span class="sxs-lookup"><span data-stu-id="1851b-136">If you plan on implementing this [cross-tenant scenario](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants), you may need an Information Barriers license.</span></span> <span data-ttu-id="1851b-137">請參閱 [這篇文章](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) ，以判斷是否需要資訊屏障授權。</span><span class="sxs-lookup"><span data-stu-id="1851b-137">See [this article](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) to determine if an Information Barrier License is required.</span></span>

## <a name="in-this-guide-you-will"></a><span data-ttu-id="1851b-138">在本指南中，您將會：</span><span class="sxs-lookup"><span data-stu-id="1851b-138">In this guide you will:</span></span>

<span data-ttu-id="1851b-139">準備：</span><span class="sxs-lookup"><span data-stu-id="1851b-139">Prepare:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="1851b-140">瞭解 HoloLens 2 裝置的基礎結構基本資訊。</span><span class="sxs-lookup"><span data-stu-id="1851b-140">Learn about the infrastructure essentials for HoloLens 2 devices.</span></span>](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [<span data-ttu-id="1851b-141">如果您沒有&#39;的 Azure AD，請深入瞭解並設定一個。</span><span class="sxs-lookup"><span data-stu-id="1851b-141">Learn more about Azure AD and set up one if you don&#39;t have it.</span></span>](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [<span data-ttu-id="1851b-142">瞭解身分識別管理，以及如何以最佳方式設定 Azure AD 帳戶。</span><span class="sxs-lookup"><span data-stu-id="1851b-142">Learn about Identity management and how to best set up Azure AD accounts.</span></span>](hololens2-cloud-connected-prepare.md#identity-management)
> - [<span data-ttu-id="1851b-143">如果您還&#39;沒準備好，請深入瞭解 MDM，並使用 Intune 設定。</span><span class="sxs-lookup"><span data-stu-id="1851b-143">Learn more about MDM, and set up with Intune if you don&#39;t already have one ready.</span></span>](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [<span data-ttu-id="1851b-144">瞭解遠端協助的網路需求。</span><span class="sxs-lookup"><span data-stu-id="1851b-144">Learn about the networking requirements of Remote Assist.</span></span>](hololens2-cloud-connected-prepare.md#network)
> - [<span data-ttu-id="1851b-145">（選擇性）：連線到組織資源的 VPN</span><span class="sxs-lookup"><span data-stu-id="1851b-145">Optionally: VPN to connect to organizational resources</span></span>](hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

<span data-ttu-id="1851b-146">設定：</span><span class="sxs-lookup"><span data-stu-id="1851b-146">Configure:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="1851b-147">如何建立使用者和群組。</span><span class="sxs-lookup"><span data-stu-id="1851b-147">How to create Users and Groups.</span></span>](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [<span data-ttu-id="1851b-148">如何在 Azure AD 中設定自動註冊。</span><span class="sxs-lookup"><span data-stu-id="1851b-148">How to set up Auto-enrollment within Azure AD.</span></span>](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [<span data-ttu-id="1851b-149">如何指派應用程式授權。</span><span class="sxs-lookup"><span data-stu-id="1851b-149">How to assign your Application licenses.</span></span>](hololens2-cloud-connected-configure.md#application-licenses)

<span data-ttu-id="1851b-150">部署：</span><span class="sxs-lookup"><span data-stu-id="1851b-150">Deploy:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="1851b-151">設定您的 HoloLens 2 並驗證註冊。</span><span class="sxs-lookup"><span data-stu-id="1851b-151">Set up your HoloLens 2 and validate enrollment.</span></span>](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [<span data-ttu-id="1851b-152">驗證您可以進行遠端協助通話。</span><span class="sxs-lookup"><span data-stu-id="1851b-152">Validate you can make a Remote Assist call.</span></span>](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

<span data-ttu-id="1851b-153">維護：</span><span class="sxs-lookup"><span data-stu-id="1851b-153">Maintain:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="1851b-154">如何使用 Microsoft Store 應用程式更新遠端協助。</span><span class="sxs-lookup"><span data-stu-id="1851b-154">How to update Remote Assist using the Microsoft Store app.</span></span>](hololens2-cloud-connected-maintain.md#updates)
> - [<span data-ttu-id="1851b-155">提出支援方案。</span><span class="sxs-lookup"><span data-stu-id="1851b-155">Making a support plan.</span></span>](hololens2-cloud-connected-maintain.md#support-plan)
> - [<span data-ttu-id="1851b-156">開發計畫。</span><span class="sxs-lookup"><span data-stu-id="1851b-156">Development plan.</span></span>](hololens2-cloud-connected-maintain.md#development-plan)

## <a name="next-step"></a><span data-ttu-id="1851b-157">後續步驟</span><span class="sxs-lookup"><span data-stu-id="1851b-157">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="1851b-158">雲端連線部署-準備</span><span class="sxs-lookup"><span data-stu-id="1851b-158">Cloud connected deployment - Prepare</span></span>](hololens2-cloud-connected-prepare.md)

