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
ms.openlocfilehash: 69b31657a7efaebd5b25b742023dc8767f9c5038
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308297"
---
# <a name="deployment-guide--cloud-connected-hololens-2-with-remote-assist--overview"></a><span data-ttu-id="0227e-104">部署指南–與遠端協助的雲端連線 HoloLens 2 –總覽</span><span class="sxs-lookup"><span data-stu-id="0227e-104">Deployment Guide – Cloud connected HoloLens 2 with Remote Assist – Overview</span></span>

<span data-ttu-id="0227e-105">本指南可協助 IT 專業人員規劃 Microsoft HoloLens 2 部裝置，並將其部署到其組織，其整體目標是讓這些裝置雲端與您的組織連線，並已準備好使用 Dynamics 365 遠端協助。</span><span class="sxs-lookup"><span data-stu-id="0227e-105">This guide helps IT professionals plan for and deploy Microsoft HoloLens 2 devices to their organization with the overall goal of having those devices cloud connected to your organization with Dynamics 365 Remote Assist ready to use.</span></span> <span data-ttu-id="0227e-106">請記住，這將作為您組織中各種 HoloLens 2 使用案例的概念證明部署的模型。</span><span class="sxs-lookup"><span data-stu-id="0227e-106">Keep in mind, this will serve as a model for proof-of-concept deployments to your organization across a variety of HoloLens 2 use cases.</span></span>

<span data-ttu-id="0227e-107">在本指南中，我們將討論如何將您的裝置註冊到您的裝置管理、視需要套用授權，以及驗證您的終端使用者是否能夠在裝置設定時立即使用遠端協助。</span><span class="sxs-lookup"><span data-stu-id="0227e-107">During the guide we will cover how to enroll your devices into your device management, apply licenses as needed, and validate that your end users are able to immediately use Remote Assist upon device setup.</span></span> <span data-ttu-id="0227e-108">為了達成此目的，我們將探討設定和執行所需的重要基礎結構，也就是使用 HoloLens 2 來大規模部署。</span><span class="sxs-lookup"><span data-stu-id="0227e-108">To do this we will go over the important pieces of infrastructure needed to get set up and running – achieving deployment at scale with HoloLens 2.</span></span>

![雲端連線橫幅](./images/cloud-connected-hololens-large.png)

## <a name="in-this-guide"></a><span data-ttu-id="0227e-110">在本指南中</span><span class="sxs-lookup"><span data-stu-id="0227e-110">In this Guide</span></span>

<span data-ttu-id="0227e-111">本指南的特定目標是在您的 HoloLens 裝置上設定組織內的遠端協助。</span><span class="sxs-lookup"><span data-stu-id="0227e-111">This guide has the specific goal of setting up Remote Assist within your organization on your HoloLens devices.</span></span> <span data-ttu-id="0227e-112">我們將討論達成此目標所需的必要條件。</span><span class="sxs-lookup"><span data-stu-id="0227e-112">We will cover the necessities needed to achieve that goal.</span></span> <span data-ttu-id="0227e-113">為了將焦點放在此目標上，某些準備工作和設定將會預先選取，以針對此部署進行優化，或減少設定所需的專案。</span><span class="sxs-lookup"><span data-stu-id="0227e-113">In order to maintain focus on this goal certain preparation and configurations will be pre-selected in order to optimize for this deployment or to reduce the items needed to configure.</span></span> <span data-ttu-id="0227e-114">您將會收到這些選擇的通知，並可根據您的業務需求自訂您的部署。</span><span class="sxs-lookup"><span data-stu-id="0227e-114">You will be informed of these choices, and can customize your deployment based on your business needs.</span></span>

<span data-ttu-id="0227e-115">這是類似于 [案例 a 的設定：部署到雲端連線裝置](https://docs.microsoft.com/hololens/common-scenarios#scenario-a)，對於許多概念證明部署而言，這是很好的選擇，其中包括：</span><span class="sxs-lookup"><span data-stu-id="0227e-115">This is a set up similar to [Scenario A: Deploy to cloud connect devices](https://docs.microsoft.com/hololens/common-scenarios#scenario-a), which is a good option for many Proof of Concept deployments, which will include:</span></span>

- <span data-ttu-id="0227e-116">Wi-Fi 的網路通常完全開放到網際網路和雲端服務</span><span class="sxs-lookup"><span data-stu-id="0227e-116">Wi-Fi networks are typically fully open to the Internet and Cloud services</span></span>
- <span data-ttu-id="0227e-117">使用 MDM 自動註冊 Azure AD 聯結--MDM (Intune) 受控</span><span class="sxs-lookup"><span data-stu-id="0227e-117">Azure AD Join with MDM Auto Enrollment -- MDM (Intune) Managed</span></span>
- <span data-ttu-id="0227e-118">使用者以自己的公司帳戶登入 (Azure AD) </span><span class="sxs-lookup"><span data-stu-id="0227e-118">Users sign in with their own corporate account (Azure AD)</span></span>
  - <span data-ttu-id="0227e-119">每個裝置支援的單一或多個使用者</span><span class="sxs-lookup"><span data-stu-id="0227e-119">Single or multiple users per device supported</span></span>
- <span data-ttu-id="0227e-120">不同層級的裝置鎖定設定會根據特定使用案例套用，從完全開放到單一應用程式 Kiosk</span><span class="sxs-lookup"><span data-stu-id="0227e-120">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk</span></span>

![雲端連線案例](./images/cloud-connected-guide-diagram.png)

<span data-ttu-id="0227e-122">本指南不會再套用任何其他裝置限制或設定，不過我們建議您在完成後探索這些選項。</span><span class="sxs-lookup"><span data-stu-id="0227e-122">No other device restrictions or configurations will be applied in this guide, however we encourage you to explore those options after finishing.</span></span>

## <a name="learn-about-remote-assist"></a><span data-ttu-id="0227e-123">深入瞭解遠端協助</span><span class="sxs-lookup"><span data-stu-id="0227e-123">Learn about Remote Assist</span></span>

<span data-ttu-id="0227e-124">遠端協助可讓您進行共同維護和修復、遠端檢查，以及知識共用和定型。</span><span class="sxs-lookup"><span data-stu-id="0227e-124">Remote Assist allows for collaborative maintenance and repair, remote inspection, as well as knowledge sharing and training.</span></span> <span data-ttu-id="0227e-125">藉由連接不同角色和位置的人員，使用遠端協助的技術人員可以與 Microsoft 團隊的遠端共同作業者聯繫。</span><span class="sxs-lookup"><span data-stu-id="0227e-125">By connecting people in different roles and locations a technician using Remote Assist can connect with a remote collaborator on Microsoft Teams.</span></span> <span data-ttu-id="0227e-126">它們可以結合影片、螢幕擷取畫面和注釋來即時解決問題，即使它們不在相同的位置&#39;t 也一樣。</span><span class="sxs-lookup"><span data-stu-id="0227e-126">They can combine video, screenshots, and annotations to solve problems in real time even when they aren&#39;t in the same location.</span></span> <span data-ttu-id="0227e-127">遠端共同作業者可以在技術人員&#39;的實體空間中插入參考影像、圖解和其他實用資訊，讓他們可以參考此示意性，同時也能在 HoloLens 上運作並無人參與。</span><span class="sxs-lookup"><span data-stu-id="0227e-127">Remote collaborators can insert reference images, schematics, and other helpful information the technician&#39;s physical space so they can refer to the schematic while working heads-up and hands-free on HoloLens.</span></span>

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="in-this-guide-you-will"></a><span data-ttu-id="0227e-128">在本指南中，您將會：</span><span class="sxs-lookup"><span data-stu-id="0227e-128">In this guide you will:</span></span>

<span data-ttu-id="0227e-129">準備：</span><span class="sxs-lookup"><span data-stu-id="0227e-129">Prepare:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="0227e-130">瞭解 HoloLens 2 裝置的基礎結構基本資訊。</span><span class="sxs-lookup"><span data-stu-id="0227e-130">Learn about the infrastructure essentials for HoloLens 2 devices.</span></span>](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [<span data-ttu-id="0227e-131">如果您沒有&#39;的 Azure AD，請深入瞭解並設定一個。</span><span class="sxs-lookup"><span data-stu-id="0227e-131">Learn more about Azure AD and set up one if you don&#39;t have it.</span></span>](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [<span data-ttu-id="0227e-132">瞭解身分識別管理，以及如何以最佳方式設定 Azure AD 帳戶。</span><span class="sxs-lookup"><span data-stu-id="0227e-132">Learn about Identity management and how to best set up Azure AD accounts.</span></span>](hololens2-cloud-connected-prepare.md#identity-management)
> - [<span data-ttu-id="0227e-133">如果您還&#39;沒準備好，請深入瞭解 MDM，並使用 Intune 設定。</span><span class="sxs-lookup"><span data-stu-id="0227e-133">Learn more about MDM, and set up with Intune if you don&#39;t already have one ready.</span></span>](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [<span data-ttu-id="0227e-134">瞭解遠端協助的網路需求。</span><span class="sxs-lookup"><span data-stu-id="0227e-134">Learn about the networking requirements of Remote Assist.</span></span>](hololens2-cloud-connected-prepare.md#network)
> - [<span data-ttu-id="0227e-135">（選擇性）：連線到組織資源的 VPN</span><span class="sxs-lookup"><span data-stu-id="0227e-135">Optionally: VPN to connect to organizational resources</span></span>](/hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

<span data-ttu-id="0227e-136">設定：</span><span class="sxs-lookup"><span data-stu-id="0227e-136">Configure:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="0227e-137">如何建立使用者和群組。</span><span class="sxs-lookup"><span data-stu-id="0227e-137">How to create Users and Groups.</span></span>](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [<span data-ttu-id="0227e-138">如何在 Azure AD 中設定自動註冊。</span><span class="sxs-lookup"><span data-stu-id="0227e-138">How to set up Auto-enrollment within Azure AD.</span></span>](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [<span data-ttu-id="0227e-139">如何指派應用程式授權。</span><span class="sxs-lookup"><span data-stu-id="0227e-139">How to assign your Application licenses.</span></span>](hololens2-cloud-connected-configure.md#application-licenses)

<span data-ttu-id="0227e-140">部署：</span><span class="sxs-lookup"><span data-stu-id="0227e-140">Deploy:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="0227e-141">設定您的 HoloLens 2 並驗證註冊。</span><span class="sxs-lookup"><span data-stu-id="0227e-141">Set up your HoloLens 2 and validate enrollment.</span></span>](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [<span data-ttu-id="0227e-142">驗證您可以進行遠端協助通話。</span><span class="sxs-lookup"><span data-stu-id="0227e-142">Validate you can make a Remote Assist call.</span></span>](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

<span data-ttu-id="0227e-143">維護：</span><span class="sxs-lookup"><span data-stu-id="0227e-143">Maintain:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="0227e-144">如何使用 Microsoft Store 應用程式更新遠端協助。</span><span class="sxs-lookup"><span data-stu-id="0227e-144">How to update Remote Assist using the Microsoft Store app.</span></span>](hololens2-cloud-connected-maintain.md#updates)
> - [<span data-ttu-id="0227e-145">提出支援方案。</span><span class="sxs-lookup"><span data-stu-id="0227e-145">Making a support plan.</span></span>](hololens2-cloud-connected-maintain.md#support-plan)
> - [<span data-ttu-id="0227e-146">開發計畫。</span><span class="sxs-lookup"><span data-stu-id="0227e-146">Development plan.</span></span>](hololens2-cloud-connected-maintain.md#development-plan)

## <a name="next-step"></a><span data-ttu-id="0227e-147">後續步驟</span><span class="sxs-lookup"><span data-stu-id="0227e-147">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="0227e-148">雲端連線部署-準備</span><span class="sxs-lookup"><span data-stu-id="0227e-148">Cloud connected deployment - Prepare</span></span>](hololens2-cloud-connected-prepare.md)

