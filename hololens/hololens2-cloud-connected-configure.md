---
title: 部署指南–雲端連接 HoloLens 2 部署（含遠端協助的規模）-設定
description: 瞭解如何設定設定，以使用「遠端協助」在已連線的雲端裝置網路上註冊 HoloLens 裝置。
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
ms.openlocfilehash: 00cc3f9df1fefafc9c4c084ff642364ae3ccb85c
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283884"
---
# <span data-ttu-id="7240c-104">設定-雲端連線指南</span><span class="sxs-lookup"><span data-stu-id="7240c-104">Configure - Cloud connected Guide</span></span>

<span data-ttu-id="7240c-105">在本指南的本區段中，我們&#39;示範如何為您的租使用者設定自動註冊，以及如何為 Intune 和遠端協助應用授權。</span><span class="sxs-lookup"><span data-stu-id="7240c-105">In this section of the guide, we&#39;ll go over how to set up Auto Enrollment for your tenant, and how to apply licenses for both Intune and Remote Assist.</span></span>

## <span data-ttu-id="7240c-106">Azure 使用者和群組</span><span class="sxs-lookup"><span data-stu-id="7240c-106">Azure Users and Groups</span></span>

<span data-ttu-id="7240c-107">Azure 和 Intune （依該延伸），會使用使用者和群組來協助指派設定和授權。</span><span class="sxs-lookup"><span data-stu-id="7240c-107">Azure, and Intune by that extension, uses users and groups to help assign configurations and licenses.</span></span> <span data-ttu-id="7240c-108">為了驗證此部署流程並能夠讓一個使用者進行遠端協助呼叫，您&#39;會需要兩個使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="7240c-108">For the sake of validating this deployment flow and being able to make a Remote Assist call from one user to another you&#39;ll need two user accounts.</span></span>

<span data-ttu-id="7240c-109">我們可以將單一使用者群組設為指派授權的目的。</span><span class="sxs-lookup"><span data-stu-id="7240c-109">We can make a single user group for the purpose of assigning licenses.</span></span> <span data-ttu-id="7240c-110">我們可以將兩個使用者加入同一個群組，並將 Intune 和遠端協助的授權套用到該群組。</span><span class="sxs-lookup"><span data-stu-id="7240c-110">We can join both users to the same group and apply a license for Intune and Remote Assist to that group.</span></span>

<span data-ttu-id="7240c-111">如果您沒有&#39;t 在您可以使用的使用者群組中有兩個 Azure AD 帳戶的存取權;以下是適用的快速入門手冊：</span><span class="sxs-lookup"><span data-stu-id="7240c-111">If you don&#39;t already have access to two Azure AD accounts in a user group you can use; here are the quick start guides for:</span></span>

- [<span data-ttu-id="7240c-112">如何建立使用者</span><span class="sxs-lookup"><span data-stu-id="7240c-112">How to create a user</span></span>](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-user)
- [<span data-ttu-id="7240c-113">如何建立群組</span><span class="sxs-lookup"><span data-stu-id="7240c-113">How to create a group</span></span>](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-group)
- <span data-ttu-id="7240c-114">[將使用者新增至群組](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) -新增已建立的使用者以建立群組</span><span class="sxs-lookup"><span data-stu-id="7240c-114">[Add users to a group](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) – Add created users to create group</span></span>
- <span data-ttu-id="7240c-115">[將 AZURE AD 設定為允許使用者群組加入裝置](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) -確保新的使用者群組擁有註冊裝置至 Azure AD 的許可權</span><span class="sxs-lookup"><span data-stu-id="7240c-115">[Configure Azure AD to allow a User Group to join devices](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) – Ensure new user group has permission to enroll devices to Azure AD</span></span>

## <span data-ttu-id="7240c-116">HoloLens 2 上的自動登記</span><span class="sxs-lookup"><span data-stu-id="7240c-116">Auto Enrollment on HoloLens 2</span></span>

<span data-ttu-id="7240c-117">若要獲得流暢且流暢的體驗，請設定 Azure Active Directory Join (AADJ) ，並將自動註冊至 HoloLens 2 裝置的 Intune，就是開始使用的方法。</span><span class="sxs-lookup"><span data-stu-id="7240c-117">In order to have a smooth and seamless experience, setting up Azure Active Directory Join (AADJ) and Auto Enrollment to Intune for HoloLens 2 devices is the way to go.</span></span> <span data-ttu-id="7240c-118">這可讓使用者在 OOBE 期間輸入其組織的登入認證，並自動註冊 Azure AD 並將裝置註冊至 MDM。</span><span class="sxs-lookup"><span data-stu-id="7240c-118">This will allow users to input their organization log-in credentials during OOBE and automatically register with Azure AD and enroll the device into MDM.</span></span>

<span data-ttu-id="7240c-119">透過使用 [Microsoft 端點管理員](https://endpoint.microsoft.com/#home)，我們可以選取 [服務] 並流覽幾頁，直到我們選取 [取得 Premium 試用版]。</span><span class="sxs-lookup"><span data-stu-id="7240c-119">By using [Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home), we can select services and navigate a few pages until we can select Get a Premium trial.</span></span> <span data-ttu-id="7240c-120">您可能會注意到 Azure Active Directory Premium 1 和2，自動註冊 P1 已足夠。</span><span class="sxs-lookup"><span data-stu-id="7240c-120">You may notice there is Azure Active Directory Premium 1 and 2, for Automatic Enrollment P1 is sufficient.</span></span> <span data-ttu-id="7240c-121">我們可以選取 [Intune]，然後選取 [自動註冊的使用者範圍]，然後選取先前建立的群組。</span><span class="sxs-lookup"><span data-stu-id="7240c-121">We can select Intune and select the user scope for automatic enrollment, and select the group that was previously created.</span></span>

<span data-ttu-id="7240c-122">如需完整詳細資料和步驟，請閱讀 [如何啟用 Intune 自動註冊](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment)的指南。</span><span class="sxs-lookup"><span data-stu-id="7240c-122">For full details and steps read the guide on [how to enable auto enrollment for Intune](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment).</span></span>

## <span data-ttu-id="7240c-123">應用程式授權</span><span class="sxs-lookup"><span data-stu-id="7240c-123">Application Licenses</span></span>

<span data-ttu-id="7240c-124">應用程式授權可讓使用者安裝公司購買的應用程式，或從免費試用版升級到應用程式的完整版。</span><span class="sxs-lookup"><span data-stu-id="7240c-124">An application license allows a user to either install company purchased Apps or upgrade from a free trial to the full version of an app.</span></span> <span data-ttu-id="7240c-125">應用程式授權可以套用至使用者、使用者群組或裝置群組。</span><span class="sxs-lookup"><span data-stu-id="7240c-125">Application licenses can be applied to either users, user groups, or device groups.</span></span> <span data-ttu-id="7240c-126">您&#39;需要貴組織中的使用者使用遠端協助，才能使用遠端協助授權。</span><span class="sxs-lookup"><span data-stu-id="7240c-126">You&#39;ll need Remote Assist licenses for users in your organization to use Remote Assist.</span></span> <span data-ttu-id="7240c-127">針對本指南的目的，我們會將遠端協助授權指派給您在 [Azure 使用者和群組](hololens2-cloud-connected-configure.md#azure-users-and-groups)中建立的使用者群組。</span><span class="sxs-lookup"><span data-stu-id="7240c-127">For the purpose of this guide we'll assign Remote Assist licenses to the user group we created above in [Azure Users and Groups](hololens2-cloud-connected-configure.md#azure-users-and-groups).</span></span>

<span data-ttu-id="7240c-128">根據使用者是否要從裝置進行遠端協助呼叫，或是從 Microsoft 團隊進行遠端合作者，可能會有不同的授權需求。</span><span class="sxs-lookup"><span data-stu-id="7240c-128">The requirements for licenses can be different depending on if the user will be making the Remote Assist call from a device or will be a remote collaborator from Microsoft Teams.</span></span> <span data-ttu-id="7240c-129">根據預設，[遠端協助者] 和 [小組] 核取方塊都會標示。</span><span class="sxs-lookup"><span data-stu-id="7240c-129">By default the Remote Assist and Teams check boxes are both marked.</span></span> <span data-ttu-id="7240c-130">出於本指南的目的，建議您保留預設方塊加以選取。</span><span class="sxs-lookup"><span data-stu-id="7240c-130">For the purposes of this guide, we suggest leaving the default boxes checked.</span></span>

1. <span data-ttu-id="7240c-131">深入瞭解 [每個角色的不同授權與產品需求](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#licensing-and-product-requirements-per-role)。</span><span class="sxs-lookup"><span data-stu-id="7240c-131">Learn more about the different [Licensing and product requirements per role](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#licensing-and-product-requirements-per-role).</span></span> <span data-ttu-id="7240c-132">「遠端協助」授權有幾種不同的類型，因此請務必針對您的需求取得正確的授權。</span><span class="sxs-lookup"><span data-stu-id="7240c-132">There are a few different types of Remote Assist licenses so be sure to get the correct ones for your needs.</span></span>
2. <span data-ttu-id="7240c-133">您&#39;需要 [取得授權](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-remote-assist)。</span><span class="sxs-lookup"><span data-stu-id="7240c-133">You&#39;ll need to [acquire the license](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-remote-assist).</span></span>
3. <span data-ttu-id="7240c-134">[將您的授權](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/deploy-remote-assist) 套用至群組。</span><span class="sxs-lookup"><span data-stu-id="7240c-134">[Apply your licenses](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/deploy-remote-assist) to the group.</span></span>

## <span data-ttu-id="7240c-135">後續步驟</span><span class="sxs-lookup"><span data-stu-id="7240c-135">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="7240c-136">雲端連接部署-部署</span><span class="sxs-lookup"><span data-stu-id="7240c-136">Cloud connected deployment - Deploy</span></span>](hololens2-cloud-connected-deploy.md)