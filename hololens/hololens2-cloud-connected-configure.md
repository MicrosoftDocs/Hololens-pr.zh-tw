---
title: 部署指南–雲端連線 HoloLens 2 大規模部署與遠端協助-設定
description: 瞭解如何設定設定，以使用遠端協助大規模透過雲端連線網路註冊 HoloLens 裝置。
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
ms.openlocfilehash: eb96f1cdc799551297c0373268e8cc8f35c6bd06
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635138"
---
# <a name="configure---cloud-connected-guide"></a><span data-ttu-id="d316b-104">設定-雲端連線指南</span><span class="sxs-lookup"><span data-stu-id="d316b-104">Configure - Cloud connected Guide</span></span>

<span data-ttu-id="d316b-105">在本指南的這一節中，我們&#39;將逐步說明如何為您的租使用者設定自動註冊，以及如何套用 Intune 和遠端協助的授權。</span><span class="sxs-lookup"><span data-stu-id="d316b-105">In this section of the guide, we&#39;ll go over how to set up Auto Enrollment for your tenant, and how to apply licenses for both Intune and Remote Assist.</span></span>

## <a name="azure-users-and-groups"></a><span data-ttu-id="d316b-106">Azure 使用者和群組</span><span class="sxs-lookup"><span data-stu-id="d316b-106">Azure Users and Groups</span></span>

<span data-ttu-id="d316b-107">Azure 和此延伸模組的 Intune 會使用使用者和群組來協助指派設定和授權。</span><span class="sxs-lookup"><span data-stu-id="d316b-107">Azure, and Intune by that extension, uses users and groups to help assign configurations and licenses.</span></span> <span data-ttu-id="d316b-108">為了驗證這個部署流程，以及能夠從一位使用者進行遠端協助呼叫，您&#39;需要兩個使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="d316b-108">For the sake of validating this deployment flow and being able to make a Remote Assist call from one user to another you&#39;ll need two user accounts.</span></span>

<span data-ttu-id="d316b-109">針對指派授權的目的，我們可以建立單一使用者群組。</span><span class="sxs-lookup"><span data-stu-id="d316b-109">We can make a single user group for the purpose of assigning licenses.</span></span> <span data-ttu-id="d316b-110">我們可以將這兩個使用者加入相同的群組，並將 Intune 的授權和遠端協助套用至該群組。</span><span class="sxs-lookup"><span data-stu-id="d316b-110">We can join both users to the same group and apply a license for Intune and Remote Assist to that group.</span></span>

<span data-ttu-id="d316b-111">如果您沒有&#39;可以存取使用者群組中的兩個 Azure AD 帳戶，您可以使用;以下是快速入門手冊：</span><span class="sxs-lookup"><span data-stu-id="d316b-111">If you don&#39;t already have access to two Azure AD accounts in a user group you can use; here are the quick start guides for:</span></span>

- [<span data-ttu-id="d316b-112">如何建立使用者</span><span class="sxs-lookup"><span data-stu-id="d316b-112">How to create a user</span></span>](/mem/intune/fundamentals/quickstart-create-user)
- [<span data-ttu-id="d316b-113">如何建立群組</span><span class="sxs-lookup"><span data-stu-id="d316b-113">How to create a group</span></span>](/mem/intune/fundamentals/quickstart-create-group)
- <span data-ttu-id="d316b-114">[將使用者新增至群組](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) –將建立的使用者新增至建立群組</span><span class="sxs-lookup"><span data-stu-id="d316b-114">[Add users to a group](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) – Add created users to create group</span></span>
- <span data-ttu-id="d316b-115">[設定 Azure AD 允許使用者群組加入裝置](/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) –確定新的使用者群組有權註冊裝置 Azure AD</span><span class="sxs-lookup"><span data-stu-id="d316b-115">[Configure Azure AD to allow a User Group to join devices](/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) – Ensure new user group has permission to enroll devices to Azure AD</span></span>

## <a name="auto-enrollment-on-hololens-2"></a><span data-ttu-id="d316b-116">HoloLens 2 上的自動註冊</span><span class="sxs-lookup"><span data-stu-id="d316b-116">Auto Enrollment on HoloLens 2</span></span>

<span data-ttu-id="d316b-117">為了提供順暢且順暢的體驗，您可以將 Azure Active Directory 加入 (AADJ) 與 Intune 的自動註冊，以進行 HoloLens 2 裝置。</span><span class="sxs-lookup"><span data-stu-id="d316b-117">In order to have a smooth and seamless experience, setting up Azure Active Directory Join (AADJ) and Auto Enrollment to Intune for HoloLens 2 devices is the way to go.</span></span> <span data-ttu-id="d316b-118">這可讓使用者在 OOBE 期間輸入其組織的登入認證，並自動向 Azure AD 註冊，然後將裝置註冊到 MDM 中。</span><span class="sxs-lookup"><span data-stu-id="d316b-118">This will allow users to input their organization log-in credentials during OOBE and automatically register with Azure AD and enroll the device into MDM.</span></span>

<span data-ttu-id="d316b-119">藉由使用[Microsoft 端點管理員](https://endpoint.microsoft.com/#home)，我們可以選取服務並流覽幾個頁面，直到我們可以選取 [取得進階版試用版]。</span><span class="sxs-lookup"><span data-stu-id="d316b-119">By using [Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home), we can select services and navigate a few pages until we can select Get a Premium trial.</span></span> <span data-ttu-id="d316b-120">您可能會注意到 Azure Active Directory Premium 1 和2，自動註冊 P1 已足夠。</span><span class="sxs-lookup"><span data-stu-id="d316b-120">You may notice there is Azure Active Directory Premium 1 and 2, for Automatic Enrollment P1 is sufficient.</span></span> <span data-ttu-id="d316b-121">我們可以選取 [Intune] 並選取 [自動註冊的使用者範圍]，然後選取先前建立的群組。</span><span class="sxs-lookup"><span data-stu-id="d316b-121">We can select Intune and select the user scope for automatic enrollment, and select the group that was previously created.</span></span>

<span data-ttu-id="d316b-122">如需完整的詳細資訊和步驟，請參閱 [如何啟用 Intune 自動註冊](/mem/intune/enrollment/quickstart-setup-auto-enrollment)的指南。</span><span class="sxs-lookup"><span data-stu-id="d316b-122">For full details and steps read the guide on [how to enable auto enrollment for Intune](/mem/intune/enrollment/quickstart-setup-auto-enrollment).</span></span>

## <a name="application-licenses"></a><span data-ttu-id="d316b-123">應用程式授權</span><span class="sxs-lookup"><span data-stu-id="d316b-123">Application Licenses</span></span>

<span data-ttu-id="d316b-124">應用程式授權可讓使用者安裝公司購買的應用程式，或從免費試用版升級為應用程式的完整版本。</span><span class="sxs-lookup"><span data-stu-id="d316b-124">An application license allows a user to either install company purchased Apps or upgrade from a free trial to the full version of an app.</span></span> <span data-ttu-id="d316b-125">應用程式授權可以套用至使用者、使用者群組或裝置群組。</span><span class="sxs-lookup"><span data-stu-id="d316b-125">Application licenses can be applied to either users, user groups, or device groups.</span></span> <span data-ttu-id="d316b-126">您&#39;需要遠端協助的授權，讓組織中的使用者使用遠端協助。</span><span class="sxs-lookup"><span data-stu-id="d316b-126">You&#39;ll need Remote Assist licenses for users in your organization to use Remote Assist.</span></span> <span data-ttu-id="d316b-127">基於本指南的目的，我們會將遠端協助授權指派給我們在 [Azure 使用者和群組](hololens2-cloud-connected-configure.md#azure-users-and-groups)中建立的使用者群組。</span><span class="sxs-lookup"><span data-stu-id="d316b-127">For the purpose of this guide we'll assign Remote Assist licenses to the user group we created above in [Azure Users and Groups](hololens2-cloud-connected-configure.md#azure-users-and-groups).</span></span>

<span data-ttu-id="d316b-128">授權的需求可能會不同，取決於使用者是否要進行來自裝置的遠端協助呼叫，或將成為 Microsoft Teams 的遠端共同作業者。</span><span class="sxs-lookup"><span data-stu-id="d316b-128">The requirements for licenses can be different depending on if the user will be making the Remote Assist call from a device or will be a remote collaborator from Microsoft Teams.</span></span> <span data-ttu-id="d316b-129">預設會標示 [遠端協助] 和 [Teams] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="d316b-129">By default the Remote Assist and Teams check boxes are both marked.</span></span> <span data-ttu-id="d316b-130">基於本指南的目的，我們建議保持勾選預設方塊。</span><span class="sxs-lookup"><span data-stu-id="d316b-130">For the purposes of this guide, we suggest leaving the default boxes checked.</span></span>

1. <span data-ttu-id="d316b-131">深入瞭解 [每個角色的不同授權和產品需求](/dynamics365/mixed-reality/remote-assist/requirements#licensing-and-product-requirements-per-role)。</span><span class="sxs-lookup"><span data-stu-id="d316b-131">Learn more about the different [Licensing and product requirements per role](/dynamics365/mixed-reality/remote-assist/requirements#licensing-and-product-requirements-per-role).</span></span> <span data-ttu-id="d316b-132">有幾種不同類型的遠端協助授權，請務必為您的需求取得正確的授權。</span><span class="sxs-lookup"><span data-stu-id="d316b-132">There are a few different types of Remote Assist licenses so be sure to get the correct ones for your needs.</span></span>
2. <span data-ttu-id="d316b-133">您&#39;需要 [取得授權](/dynamics365/mixed-reality/remote-assist/buy-remote-assist)。</span><span class="sxs-lookup"><span data-stu-id="d316b-133">You&#39;ll need to [acquire the license](/dynamics365/mixed-reality/remote-assist/buy-remote-assist).</span></span>
3. <span data-ttu-id="d316b-134">[將您的授權](/dynamics365/mixed-reality/remote-assist/deploy-remote-assist) 套用至群組。</span><span class="sxs-lookup"><span data-stu-id="d316b-134">[Apply your licenses](/dynamics365/mixed-reality/remote-assist/deploy-remote-assist) to the group.</span></span>

## <a name="next-step"></a><span data-ttu-id="d316b-135">後續步驟</span><span class="sxs-lookup"><span data-stu-id="d316b-135">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="d316b-136">雲端連線部署-部署</span><span class="sxs-lookup"><span data-stu-id="d316b-136">Cloud connected deployment - Deploy</span></span>](hololens2-cloud-connected-deploy.md)