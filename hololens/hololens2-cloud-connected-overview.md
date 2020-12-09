---
title: 部署指南–雲端連線的 HoloLens 2 （含遠端協助）-概覽
description: 透過雲端連接的網路註冊 HoloLens 裝置
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
ms.openlocfilehash: ba3f826360f999a72e671166af7a19d19ce9c567
ms.sourcegitcommit: 8e2c268733adce2662bf320cf96ccfea5919425e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/04/2020
ms.locfileid: "11196286"
---
# <span data-ttu-id="c7416-104">部署指南–雲端連線的 HoloLens 2 （含遠端協助）-概覽</span><span class="sxs-lookup"><span data-stu-id="c7416-104">Deployment Guide – Cloud connected HoloLens 2 with Remote Assist – Overview</span></span>

<span data-ttu-id="c7416-105">本指南可協助 IT 專業人員規劃 Microsoft HoloLens 2 裝置並將其部署至組織，其總體目標是將這些裝置雲與您的組織連線至您的組織，並準備好使用動態365遠端協助。</span><span class="sxs-lookup"><span data-stu-id="c7416-105">This guide helps IT professionals plan for and deploy Microsoft HoloLens 2 devices to their organization with the overall goal of having those devices cloud connected to your organization with Dynamics 365 Remote Assist ready to use.</span></span> <span data-ttu-id="c7416-106">請記住，這將會成為您組織在各種 HoloLens 2 使用案例中部署的概念驗證模型。</span><span class="sxs-lookup"><span data-stu-id="c7416-106">Keep in mind, this will serve as a model for proof-of-concept deployments to your organization across a variety of HoloLens 2 use cases.</span></span>

<span data-ttu-id="c7416-107">在本指南中，我們將說明如何將裝置註冊到您的裝置管理、根據需要套用授權，以及驗證您的最終使用者是否能夠在設定裝置時立即使用遠端協助。</span><span class="sxs-lookup"><span data-stu-id="c7416-107">During the guide we will cover how to enroll your devices into your device management, apply licenses as needed, and validate that your end users are able to immediately use Remote Assist upon device set up.</span></span> <span data-ttu-id="c7416-108">若要這樣做，我們將會透過重要的基礎結構部分來設定並執行，以使用 HoloLens 2 來實現規模的部署。</span><span class="sxs-lookup"><span data-stu-id="c7416-108">To do this we will go over the important pieces of infrastructure needed to get set up and running – achieving deployment at scale with HoloLens 2.</span></span>

## <span data-ttu-id="c7416-109">本指南中</span><span class="sxs-lookup"><span data-stu-id="c7416-109">In this Guide</span></span>

<span data-ttu-id="c7416-110">本指南具有在您的 HoloLens 裝置上設定遠端協助的特定目標。</span><span class="sxs-lookup"><span data-stu-id="c7416-110">This guide has the specific goal of setting up Remote Assist within your organization on your HoloLens devices.</span></span> <span data-ttu-id="c7416-111">我們將涵蓋完成該目標所需的 necessities。</span><span class="sxs-lookup"><span data-stu-id="c7416-111">We will cover the necessities needed to achieve that goal.</span></span> <span data-ttu-id="c7416-112">為了維持焦點在這個目標上，系統會預先選取某些準備和設定，以便針對此部署進行優化，或減少設定所需的專案。</span><span class="sxs-lookup"><span data-stu-id="c7416-112">In order to maintain focus on this goal certain preparations and configurations will be pre-selected in order to optimize for this deployment or to reduce the items needed to configure.</span></span> <span data-ttu-id="c7416-113">您將會收到這些選項的通知，您可以根據您的業務需求來自訂您的部署。</span><span class="sxs-lookup"><span data-stu-id="c7416-113">You will be informed of these choices, and can customize your deployment based on your business needs.</span></span>

<span data-ttu-id="c7416-114">這項設定與 [案例 a：部署到雲端連接裝置](https://docs.microsoft.com/hololens/common-scenarios#scenario-a)一樣，這是許多概念驗證部署的好選項，這些會包括：</span><span class="sxs-lookup"><span data-stu-id="c7416-114">This is a set up similar to [Scenario A: Deploy to cloud connect devices](https://docs.microsoft.com/hololens/common-scenarios#scenario-a), which is a good option for many Proof of Concept deployments which will include:</span></span>

- <span data-ttu-id="c7416-115">Wi-Fi 的網路通常會完全開啟網際網路和雲端服務</span><span class="sxs-lookup"><span data-stu-id="c7416-115">Wi-Fi networks are typically fully open to the Internet and Cloud services</span></span>
- <span data-ttu-id="c7416-116">使用 MDM 自動註冊的 Azure AD 聯接--MDM (Intune) 管理</span><span class="sxs-lookup"><span data-stu-id="c7416-116">Azure AD Join with MDM Auto Enrollment -- MDM (Intune) Managed</span></span>
- <span data-ttu-id="c7416-117">使用者以自己的公司帳戶登入 (AAD) </span><span class="sxs-lookup"><span data-stu-id="c7416-117">Users sign in with their own corporate account (AAD)</span></span>
  - <span data-ttu-id="c7416-118">每個裝置支援單一或多個使用者</span><span class="sxs-lookup"><span data-stu-id="c7416-118">Single or multiple users per device supported</span></span>
- <span data-ttu-id="c7416-119">根據特定的使用案例，從完全開啟到單一應用程式亭，就會套用各種不同的裝置鎖定設定等級</span><span class="sxs-lookup"><span data-stu-id="c7416-119">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk</span></span>

![雲端連接案例](./images/cloud-connected-deployment-chart.png)

<span data-ttu-id="c7416-121">本指南中不會套用其他裝置限制或設定，但我們建議您在完成後探索這些選項。</span><span class="sxs-lookup"><span data-stu-id="c7416-121">No additional device restrictions or configurations will be applied in this guide, however we encourage you to explore those options after finishing.</span></span>

## <span data-ttu-id="c7416-122">瞭解遠端協助</span><span class="sxs-lookup"><span data-stu-id="c7416-122">Learn about Remote Assist</span></span>

<span data-ttu-id="c7416-123">遠端協助可讓您進行共同維護與修復、遠端檢查，以及知識共用與訓練。</span><span class="sxs-lookup"><span data-stu-id="c7416-123">Remote Assist allows for collaborative maintenance and repair, remote inspection, as well as knowledge sharing and training.</span></span> <span data-ttu-id="c7416-124">透過將不同角色中的人員與使用 [遠端協助] 的人員連線，即可與 Microsoft 團隊中的遠端合作者連線。</span><span class="sxs-lookup"><span data-stu-id="c7416-124">By connecting people in different roles and locations a technician using Remote Assist can connect with a remote collaborator on Microsoft Teams.</span></span> <span data-ttu-id="c7416-125">即使在相同的位置&#39;t，他們也可以結合影片、螢幕擷取畫面和批註來即時解決問題。</span><span class="sxs-lookup"><span data-stu-id="c7416-125">They can combine video, screenshots, and annotations to solve problems in real time even when they aren&#39;t in the same location.</span></span> <span data-ttu-id="c7416-126">遠端共同作業者可以在技術人員&#39;的物理空間中插入參照影像、圖表及其他有用的資訊，讓他們在正常運作時可以參考示意性，並在 HoloLens 上無人參與。</span><span class="sxs-lookup"><span data-stu-id="c7416-126">Remote collaborators can insert reference images, schematics, and other helpful information the technician&#39;s physical space so they can refer to the schematic while working heads-up and hands-free on HoloLens.</span></span>

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <span data-ttu-id="c7416-127">在本指南中，您將：</span><span class="sxs-lookup"><span data-stu-id="c7416-127">In this guide you will:</span></span>

<span data-ttu-id="c7416-128">製作</span><span class="sxs-lookup"><span data-stu-id="c7416-128">Prepare:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="c7416-129">瞭解 HoloLens 2 裝置的基礎結構基礎。</span><span class="sxs-lookup"><span data-stu-id="c7416-129">Learn about the infrastructure essentials for HoloLens 2 devices.</span></span>](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [<span data-ttu-id="c7416-130">如果您沒有&#39;，請進一步瞭解 AAD 並設定一個。</span><span class="sxs-lookup"><span data-stu-id="c7416-130">Learn more about AAD and set up one if you don&#39;t have it.</span></span>](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [<span data-ttu-id="c7416-131">瞭解身分識別管理，以及如何最好地設定 AAD 帳戶。</span><span class="sxs-lookup"><span data-stu-id="c7416-131">Learn about Identity management and how to best set up AAD accounts.</span></span>](hololens2-cloud-connected-prepare.md#identity-management)
> - [<span data-ttu-id="c7416-132">深入瞭解 MDM，如果您沒有&#39;t 已準備好，就可以使用 Intune 進行設定。</span><span class="sxs-lookup"><span data-stu-id="c7416-132">Learn more about MDM, and set up with Intune if you don&#39;t already have one ready.</span></span>](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [<span data-ttu-id="c7416-133">瞭解遠端協助的網路需求。</span><span class="sxs-lookup"><span data-stu-id="c7416-133">Learn about the networking requirements of Remote Assist.</span></span>](hololens2-cloud-connected-prepare.md#network)
> - [<span data-ttu-id="c7416-134">選擇性： VPN 連接至組織資源</span><span class="sxs-lookup"><span data-stu-id="c7416-134">Optionally: VPN to connect to organizational resources</span></span>](/hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

<span data-ttu-id="c7416-135">設定</span><span class="sxs-lookup"><span data-stu-id="c7416-135">Configure:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="c7416-136">如何建立使用者和群組。</span><span class="sxs-lookup"><span data-stu-id="c7416-136">How to create Users and Groups.</span></span>](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [<span data-ttu-id="c7416-137">如何在 AAD 中設定自動註冊。</span><span class="sxs-lookup"><span data-stu-id="c7416-137">How to set up Auto-enrollment within AAD.</span></span>](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [<span data-ttu-id="c7416-138">如何指派您的應用程式授權。</span><span class="sxs-lookup"><span data-stu-id="c7416-138">How to assign your Application licenses.</span></span>](hololens2-cloud-connected-configure.md#application-licenses)

<span data-ttu-id="c7416-139">部署</span><span class="sxs-lookup"><span data-stu-id="c7416-139">Deploy:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="c7416-140">設定您的 HoloLens 2 並驗證註冊。</span><span class="sxs-lookup"><span data-stu-id="c7416-140">Set up your HoloLens 2 and validate enrollment.</span></span>](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [<span data-ttu-id="c7416-141">驗證您可以撥打遠端協助。</span><span class="sxs-lookup"><span data-stu-id="c7416-141">Validate you can make a Remote Assist call.</span></span>](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

<span data-ttu-id="c7416-142">保留</span><span class="sxs-lookup"><span data-stu-id="c7416-142">Maintain:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="c7416-143">如何使用 Microsoft Store 應用程式更新遠端協助。</span><span class="sxs-lookup"><span data-stu-id="c7416-143">How to update Remote Assist using the Microsoft Store app.</span></span>](hololens2-cloud-connected-maintain.md#updates)
> - [<span data-ttu-id="c7416-144">建立支援計畫。</span><span class="sxs-lookup"><span data-stu-id="c7416-144">Making a support plan.</span></span>](hololens2-cloud-connected-maintain.md#support-plan)
> - [<span data-ttu-id="c7416-145">開發規劃。</span><span class="sxs-lookup"><span data-stu-id="c7416-145">Development plan.</span></span>](hololens2-cloud-connected-maintain.md#development-plan)

## <span data-ttu-id="c7416-146">後續步驟</span><span class="sxs-lookup"><span data-stu-id="c7416-146">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="c7416-147">雲端連接部署-準備</span><span class="sxs-lookup"><span data-stu-id="c7416-147">Cloud connected deployment - Prepare</span></span>](hololens2-cloud-connected-prepare.md)
