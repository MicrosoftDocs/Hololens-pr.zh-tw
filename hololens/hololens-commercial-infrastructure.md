---
title: HoloLens 的基礎結構指導方針
description: 瞭解 HoloLens 裝置基礎結構指導方針，包括無線網路支援、遠端協助及行動裝置管理。
ms.prod: hololens
ms.sitesec: library
author: pawinfie
ms.author: pawinfie
ms.topic: article
ms.localizationpriority: high
ms.date: 1/23/2020
ms.reviewer: ''
audience: ITPro
manager: bradke
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 4eb55bec56e53de9195ac87e0491eefd91992f3d
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283384"
---
# <span data-ttu-id="da03b-103">設定適用於 HoloLens 的網路</span><span class="sxs-lookup"><span data-stu-id="da03b-103">Configure Your Network for HoloLens</span></span>

<span data-ttu-id="da03b-104">文件的此部分將需要下列人員：</span><span class="sxs-lookup"><span data-stu-id="da03b-104">This portion of the document will require the following people:</span></span>

1. <span data-ttu-id="da03b-105">具備權限可變更 Proxy/防火牆的網路系統管理員</span><span class="sxs-lookup"><span data-stu-id="da03b-105">Network Admin with permissions to make changes to the proxy/firewall</span></span>
2. <span data-ttu-id="da03b-106">Azure Active Directory 系統管理員</span><span class="sxs-lookup"><span data-stu-id="da03b-106">Azure Active Directory Admin</span></span>
3. <span data-ttu-id="da03b-107">行動裝置管理系統管理員</span><span class="sxs-lookup"><span data-stu-id="da03b-107">Mobile Device Manager Admin</span></span>

## <span data-ttu-id="da03b-108">基礎結構需求</span><span class="sxs-lookup"><span data-stu-id="da03b-108">Infrastructure Requirements</span></span>

<span data-ttu-id="da03b-109">HoloLens 是與 Azure 整合的 Windows 行動裝置。</span><span class="sxs-lookup"><span data-stu-id="da03b-109">HoloLens is, at its core, a Windows mobile device integrated with Azure.</span></span>  <span data-ttu-id="da03b-110">它在可使用無線網路 (wi-fi) 和可存取 Microsoft 服務的商業環境中效果最佳。</span><span class="sxs-lookup"><span data-stu-id="da03b-110">It works best in commercial environments with wireless network availability (wi-fi) and access to Microsoft services.</span></span>

<span data-ttu-id="da03b-111">重要的雲端服務包括：</span><span class="sxs-lookup"><span data-stu-id="da03b-111">Critical cloud services include:</span></span>

- <span data-ttu-id="da03b-112">Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="da03b-112">Azure active directory (Azure AD)</span></span>
- <span data-ttu-id="da03b-113">Windows Update (WU)</span><span class="sxs-lookup"><span data-stu-id="da03b-113">Windows Update (WU)</span></span>

<span data-ttu-id="da03b-114">商業客戶需要企業行動管理 (EMM) 或行動裝置管理 (MDM) 基礎結構，以管理大規模的 HoloLens 裝置。</span><span class="sxs-lookup"><span data-stu-id="da03b-114">Commercial customers will need enterprise mobility management (EMM) or mobile device management (MDM) infrastructure to manage HoloLens devices at scale.</span></span>  <span data-ttu-id="da03b-115">本指南使用 [Microsoft Intune](https://www.microsoft.com/enterprise-mobility-security/microsoft-intune) 範例，而任何提供 Microsoft Policy 完整支援的提供者都可以支援 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="da03b-115">This guide uses [Microsoft Intune](https://www.microsoft.com/enterprise-mobility-security/microsoft-intune) as an example, though any provider with full support for Microsoft Policy can support HoloLens.</span></span>  <span data-ttu-id="da03b-116">詢問您的行動裝置管理提供者是否支援 HoloLens 2。</span><span class="sxs-lookup"><span data-stu-id="da03b-116">Ask your mobile device management provider if they support HoloLens 2.</span></span>

<span data-ttu-id="da03b-117">HoloLens 也支援一組有限的雲端連線中斷體驗。</span><span class="sxs-lookup"><span data-stu-id="da03b-117">HoloLens does support a limited set of cloud disconnected experiences.</span></span>

### <span data-ttu-id="da03b-118">無線網路 EAP 支援</span><span class="sxs-lookup"><span data-stu-id="da03b-118">Wireless network EAP support</span></span>

- <span data-ttu-id="da03b-119">PEAP-MS-CHAPv2</span><span class="sxs-lookup"><span data-stu-id="da03b-119">PEAP-MS-CHAPv2</span></span>
- <span data-ttu-id="da03b-120">PEAP-TLS</span><span class="sxs-lookup"><span data-stu-id="da03b-120">PEAP-TLS</span></span>
- <span data-ttu-id="da03b-121">TLS</span><span class="sxs-lookup"><span data-stu-id="da03b-121">TLS</span></span>
- <span data-ttu-id="da03b-122">TTLS-CHAP</span><span class="sxs-lookup"><span data-stu-id="da03b-122">TTLS-CHAP</span></span>
- <span data-ttu-id="da03b-123">TTLS-CHAPv2</span><span class="sxs-lookup"><span data-stu-id="da03b-123">TTLS-CHAPv2</span></span>
- <span data-ttu-id="da03b-124">TTLS-MS-CHAPv2</span><span class="sxs-lookup"><span data-stu-id="da03b-124">TTLS-MS-CHAPv2</span></span>
- <span data-ttu-id="da03b-125">TTLS-PAP</span><span class="sxs-lookup"><span data-stu-id="da03b-125">TTLS-PAP</span></span>
- <span data-ttu-id="da03b-126">TTLS-TLS</span><span class="sxs-lookup"><span data-stu-id="da03b-126">TTLS-TLS</span></span>

### <span data-ttu-id="da03b-127">HoloLens 特定網路需求</span><span class="sxs-lookup"><span data-stu-id="da03b-127">HoloLens Specific Network Requirements</span></span>

<span data-ttu-id="da03b-128">請確認您的網路防火牆允許此端點[清單](hololens-offline.md)。</span><span class="sxs-lookup"><span data-stu-id="da03b-128">Make sure that [this list](hololens-offline.md) of endpoints are allowed on your network firewall.</span></span> <span data-ttu-id="da03b-129">這可讓 HoloLens 正常運作。</span><span class="sxs-lookup"><span data-stu-id="da03b-129">This will enable HoloLens to function properly.</span></span>

### <span data-ttu-id="da03b-130">遠端協助特定網路需求</span><span class="sxs-lookup"><span data-stu-id="da03b-130">Remote Assist Specific Network Requirements</span></span>

1. <span data-ttu-id="da03b-131">若要獲得最佳遠端協助的效能，建議使用的頻寬為 1.5Mbps。</span><span class="sxs-lookup"><span data-stu-id="da03b-131">The recommended bandwidth for optimal performance of Remote Assist is 1.5Mbps.</span></span> <span data-ttu-id="da03b-132">如需額外資訊，請參閱 [詳細網路需求](https://docs.microsoft.com/MicrosoftTeams/prepare-network)。</span><span class="sxs-lookup"><span data-stu-id="da03b-132">See the [detailed network requirements](https://docs.microsoft.com/MicrosoftTeams/prepare-network) for additional information.</span></span>
**<span data-ttu-id="da03b-133">(請注意，如果您的網路未具備至少 1.5Mbps 的網路速度，遠端協助仍可運作。</span><span class="sxs-lookup"><span data-stu-id="da03b-133">(Please note, if you don't network have network speeds of at least 1.5Mbps, Remote Assist will still work.</span></span> <span data-ttu-id="da03b-134">但品質可能會受到影響。)</span><span class="sxs-lookup"><span data-stu-id="da03b-134">However, quality may suffer).</span></span>**
1. <span data-ttu-id="da03b-135">請確定網路防火牆允許這些埠和 URL，讓 Microsoft Teams 能正常運作。</span><span class="sxs-lookup"><span data-stu-id="da03b-135">Make sure that these ports and URLs are allowed on your network firewall to enable Microsoft Teams to function.</span></span> <span data-ttu-id="da03b-136">隨時更新到 [最新的埠清單](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)。</span><span class="sxs-lookup"><span data-stu-id="da03b-136">Stay up to date with the [latest list of ports](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams).</span></span>

- <span data-ttu-id="da03b-137">深入瞭解特定的[遠端協助的網路需求](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#network-requirements)。</span><span class="sxs-lookup"><span data-stu-id="da03b-137">Learn more about the specific [Network Requirements for Remote Assist](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#network-requirements).</span></span> 
- <span data-ttu-id="da03b-138">深入瞭解如何 [準備貴組織的 Microsoft Teams 網路](https://docs.microsoft.com/MicrosoftTeams/prepare-network)</span><span class="sxs-lookup"><span data-stu-id="da03b-138">Learn more about how to [prepare your organization's network for Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/prepare-network)</span></span>

### <span data-ttu-id="da03b-139">特定網路需求指南</span><span class="sxs-lookup"><span data-stu-id="da03b-139">Guides Specific Network Requirements</span></span>

<span data-ttu-id="da03b-140">只需要網路存取即可下載指南並使用應用程式。</span><span class="sxs-lookup"><span data-stu-id="da03b-140">Guides only require network access to download and use the app.</span></span>

## <span data-ttu-id="da03b-141">Azure Active Directory 指導方針</span><span class="sxs-lookup"><span data-stu-id="da03b-141">Azure Active Directory Guidance</span></span>

> [!NOTE]
> <span data-ttu-id="da03b-142">只有在公司計劃管理 HoloLens 時，才需要執行此步驟。</span><span class="sxs-lookup"><span data-stu-id="da03b-142">This step is only necessary if your company plans on managing the HoloLens.</span></span>

1. <span data-ttu-id="da03b-143">確定您擁有 Azure AD 授權。</span><span class="sxs-lookup"><span data-stu-id="da03b-143">Ensure that you have an Azure AD License.</span></span>
<span data-ttu-id="da03b-144">如需詳細資訊，請參閱 [HoloLens 授權需求](hololens-licenses-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="da03b-144">Please [HoloLens Licenses Requirements](hololens-licenses-requirements.md) for additional information.</span></span>

1. <span data-ttu-id="da03b-145">如果您打算使用自動註冊，您必須[設定 Azure AD 註冊。](https://docs.microsoft.com/intune/deploy-use/.set-up-windows-device-management-with-microsoft-intune#azure-active-directory-enrollment)</span><span class="sxs-lookup"><span data-stu-id="da03b-145">If you plan on using Auto Enrollment, you will have to [Configure Azure AD enrollment.](https://docs.microsoft.com/intune/deploy-use/.set-up-windows-device-management-with-microsoft-intune#azure-active-directory-enrollment)</span></span>

1. <span data-ttu-id="da03b-146">確定貴公司的使用者位於 Azure Active Directory (Azure AD) 中。</span><span class="sxs-lookup"><span data-stu-id="da03b-146">Ensure that your company's users are in Azure Active Directory (Azure AD).</span></span>
<span data-ttu-id="da03b-147">請參閱下列新增使用者的[指示](https://docs.microsoft.com/azure/active-directory/fundamentals/add-users-azure-active-directory)。</span><span class="sxs-lookup"><span data-stu-id="da03b-147">See the following [instructions](https://docs.microsoft.com/azure/active-directory/fundamentals/add-users-azure-active-directory) for adding users.</span></span>

1. <span data-ttu-id="da03b-148">建議將需要類似授權的使用者新增至相同的群組。</span><span class="sxs-lookup"><span data-stu-id="da03b-148">We suggest that users who need similar licenses are added to the same group.</span></span>
    1. [<span data-ttu-id="da03b-149">建立群組</span><span class="sxs-lookup"><span data-stu-id="da03b-149">Create a Group</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)
    1. [<span data-ttu-id="da03b-150">新增使用者至群組</span><span class="sxs-lookup"><span data-stu-id="da03b-150">Add users to groups</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal)

1. <span data-ttu-id="da03b-151">確定貴公司的使用者 (或使用者群組) 已獲指派必要的授權。</span><span class="sxs-lookup"><span data-stu-id="da03b-151">Ensure that your company's users (or group of users) are assigned the necessary licenses.</span></span>
<span data-ttu-id="da03b-152">如果您需要指派授權，請按照下列 [指示](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups)進行。</span><span class="sxs-lookup"><span data-stu-id="da03b-152">If you need to assign licenses, follow these [directions](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups).</span></span>

1. <span data-ttu-id="da03b-153">只有在使用者想要註冊自己的 HoloLens/行動裝置時，再執行此步驟 (有三個選項)。這些步驟可確定貴公司的使用者 (或使用者群組) 可以新增裝置。</span><span class="sxs-lookup"><span data-stu-id="da03b-153">Only do this step if users are expected to enroll their HoloLens/Mobile device into you (There are three options) These steps ensure that your company's users (or a group of users) can add devices.</span></span>
    1. <span data-ttu-id="da03b-154">**選項 1：** 提供所有使用者將裝置加入 Azure AD 的權限。</span><span class="sxs-lookup"><span data-stu-id="da03b-154">**Option 1:** Give all users permission to join devices to Azure AD.</span></span>
<span data-ttu-id="da03b-155">**以系統管理員身分登入 Azure 入口網站**  >  [Azure Active Directory]\*\*\*\*  >  [裝置]\*\*\*\*  >  [裝置設定]\*\*\*\*  >
 將 [使用者可以將裝置加入 Azure AD] 設定為 [全部]\*\*\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="da03b-155">**Sign in to the Azure portal as an administrator** > **Azure Active Directory** > **Devices** > **Device Settings** >
**Set Users may join devices to Azure AD to *All***</span></span>

    1. <span data-ttu-id="da03b-156">**選項 2：** 提供所選的使用者/群組將裝置加入 Azure AD 的權限。**以系統管理員身分登入 Azure 入口網站** > **Azure Active Directory** > **裝置** > **裝置設定** >
\*\*將 [使用者可以將裝置加入 Azure AD] 設定為 [已選取]\*\*\*\*
![顯示 [加入 Azure AD 之裝置的設定] 影像</span><span class="sxs-lookup"><span data-stu-id="da03b-156">**Option 2:** Give selected users/groups permission to join devices to Azure AD **Sign in to the Azure portal as an administrator** > **Azure Active Directory** > **Devices** > **Device Settings** >
\*\*Set Users may join devices to Azure AD to \*Selected\*\*\*
![Image that shows Configuration of Azure AD Joined Devices</span></span>](images/azure-ad-image.png)

    1. <span data-ttu-id="da03b-157">**選項 3：** 您可以封鎖所有使用者，讓他們無法將裝置加入網域。</span><span class="sxs-lookup"><span data-stu-id="da03b-157">**Option 3:** You can block all users from joining their devices to the domain.</span></span> <span data-ttu-id="da03b-158">這表示將必須手動註冊所有裝置。</span><span class="sxs-lookup"><span data-stu-id="da03b-158">This means that all devices will need to be manually enrolled.</span></span>

## <span data-ttu-id="da03b-159">行動裝置管理員指南</span><span class="sxs-lookup"><span data-stu-id="da03b-159">Mobile Device Manager Guidance</span></span>

### <span data-ttu-id="da03b-160">持續的裝置管理</span><span class="sxs-lookup"><span data-stu-id="da03b-160">Ongoing device management</span></span>

> [!NOTE]
> <span data-ttu-id="da03b-161">只有在公司計劃管理 HoloLens 時，才需要執行此步驟。</span><span class="sxs-lookup"><span data-stu-id="da03b-161">This step is only necessary if your company plans to manage the HoloLens.</span></span>

<span data-ttu-id="da03b-162">持續的裝置管理將視您的行動裝置管理基礎結構而定。</span><span class="sxs-lookup"><span data-stu-id="da03b-162">Ongoing device management will depend on your mobile device management infrastructure.</span></span>  <span data-ttu-id="da03b-163">大部分會與一般功能相同，但使用者介面可能有所差異。</span><span class="sxs-lookup"><span data-stu-id="da03b-163">Most have the same general functionality but the user interface may vary widely.</span></span>

1. <span data-ttu-id="da03b-164">[設定檔 (服務提供者)](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) 可讓您建立及部署您網路上裝置的管理設定。</span><span class="sxs-lookup"><span data-stu-id="da03b-164">[CSPs (Configuration Service Providers)](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) lets you to create and deploy management settings for the devices on your network.</span></span> <span data-ttu-id="da03b-165">請參閱 [HoloLens CSPs 清單](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) 以供參考。</span><span class="sxs-lookup"><span data-stu-id="da03b-165">See the [list of HoloLens CSPs](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) for reference.</span></span>

1. <span data-ttu-id="da03b-166">[合規性原則](https://docs.microsoft.com/intune/device-compliance-get-started)是裝置必須符合的規則和設定，以符合您公司的基礎結構。</span><span class="sxs-lookup"><span data-stu-id="da03b-166">[Compliance policies](https://docs.microsoft.com/intune/device-compliance-get-started) are rules and settings that devices must meet to be compliant in your corporate infrastructure.</span></span> <span data-ttu-id="da03b-167">使用這些原則搭配條件式存取，以封鎖不合規的裝置存取公司資源。</span><span class="sxs-lookup"><span data-stu-id="da03b-167">Use these policies with Conditional Access to block access to company resources for devices that are non-compliant.</span></span> <span data-ttu-id="da03b-168">例如，您可以建立必須啟用 Bitlocker 的原則。</span><span class="sxs-lookup"><span data-stu-id="da03b-168">For example, you can create a policy that requires Bitlocker be enabled.</span></span>

1. <span data-ttu-id="da03b-169">[建立合規性原則](https://docs.microsoft.com/intune/protect/compliance-policy-create-windows)。</span><span class="sxs-lookup"><span data-stu-id="da03b-169">[Create Compliance Policy](https://docs.microsoft.com/intune/protect/compliance-policy-create-windows).</span></span>

1. <span data-ttu-id="da03b-170">條件式存取可允許/拒絕行動裝置和行動應用程式存取公司資源。</span><span class="sxs-lookup"><span data-stu-id="da03b-170">Conditional Access allows/denies mobile devices and mobile applications from accessing company resources.</span></span> <span data-ttu-id="da03b-171">有兩份實用的文件：[規劃您的 CA 部署](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access)和[最佳做法](https://docs.microsoft.com/azure/active-directory/conditional-access/best-practices)。</span><span class="sxs-lookup"><span data-stu-id="da03b-171">Two documents you may find helpful are [Plan your CA Deployment](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) and [Best Practices](https://docs.microsoft.com/azure/active-directory/conditional-access/best-practices).</span></span>

1. <span data-ttu-id="da03b-172">[這篇文章](https://docs.microsoft.com/intune/fundamentals/windows-holographic-for-business)討論的是適用於 HoloLens 的 Intune 管理工具。</span><span class="sxs-lookup"><span data-stu-id="da03b-172">[This article](https://docs.microsoft.com/intune/fundamentals/windows-holographic-for-business) talks about Intune's management tools for HoloLens.</span></span>

1. [<span data-ttu-id="da03b-173">建立裝置設定檔</span><span class="sxs-lookup"><span data-stu-id="da03b-173">Create a device profile</span></span>](https://docs.microsoft.com/intune/configuration/device-profile-create)

### <span data-ttu-id="da03b-174">管理更新</span><span class="sxs-lookup"><span data-stu-id="da03b-174">Manage updates</span></span>

<span data-ttu-id="da03b-175">Intune 包括稱為 Windows 10 裝置更新週期的功能，包含 HoloLens 2 和 HoloLens v1 (含 Holographic for Business)。</span><span class="sxs-lookup"><span data-stu-id="da03b-175">Intune includes a feature called Update rings for Windows 10 devices, including HoloLens 2 and HoloLens v1 (with Holographic for Business).</span></span> <span data-ttu-id="da03b-176">更新週期包括一組設定，可決定更新的安裝方式和時間。</span><span class="sxs-lookup"><span data-stu-id="da03b-176">Update rings include a group of settings that determine how and when updates are installed.</span></span>

<span data-ttu-id="da03b-177">例如，您可以建立要安裝更新的維護時段，或選擇在安裝更新後重新開機。</span><span class="sxs-lookup"><span data-stu-id="da03b-177">For example, you can create a maintenance window to install updates, or choose to restart after updates are installed.</span></span>  <span data-ttu-id="da03b-178">您也可以選擇無限期暫停更新，直到您準備好更新為止。</span><span class="sxs-lookup"><span data-stu-id="da03b-178">You can also choose to pause updates indefinitely until you're ready to update.</span></span>

<span data-ttu-id="da03b-179">如需詳細資訊，請參閱[](https://docs.microsoft.com/intune/windows-update-for-business-configure)使用 Intune 設定更新週期[。](https://docs.microsoft.com/intune/windows-update-for-business-configure)</span><span class="sxs-lookup"><span data-stu-id="da03b-179">Read more about [configuring update rings with Intune](https://docs.microsoft.com/intune/windows-update-for-business-configure).</span></span>

### <span data-ttu-id="da03b-180">應用程式管理</span><span class="sxs-lookup"><span data-stu-id="da03b-180">Application management</span></span>

<span data-ttu-id="da03b-181">透過下列方法管理 HoloLens 應用程式：</span><span class="sxs-lookup"><span data-stu-id="da03b-181">Manage HoloLens applications through:</span></span>

1. <span data-ttu-id="da03b-182">Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="da03b-182">Microsoft Store</span></span>  
  <span data-ttu-id="da03b-183">Microsoft Store 是發佈和使用 HoloLens 上的應用程式的最佳方式。</span><span class="sxs-lookup"><span data-stu-id="da03b-183">The Microsoft Store is the best way to distribute and consume applications on HoloLens.</span></span>  <span data-ttu-id="da03b-184">商店中已有許多很棒的核心 HoloLens 應用程式，或者您也可以[發佈自己的](https://docs.microsoft.com/windows/uwp/publish/)。</span><span class="sxs-lookup"><span data-stu-id="da03b-184">There is a great set of core HoloLens applications already available in the store or you can [publish your own](https://docs.microsoft.com/windows/uwp/publish/).</span></span>  
  <span data-ttu-id="da03b-185">商店中的所有應用程式都能公開供所有人使用，但是若無法使用，請查看商務用 Microsoft Store。</span><span class="sxs-lookup"><span data-stu-id="da03b-185">All applications in the store are available publicly to everyone, but if it isn't acceptable, checkout the Microsoft Store for Business.</span></span>  

1. [<span data-ttu-id="da03b-186">商務用 Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="da03b-186">Microsoft Store for Business</span></span>](https://docs.microsoft.com/microsoft-store/)  
  <span data-ttu-id="da03b-187">商務與教育用 Microsoft Store 是適用於企業環境的自訂商店。</span><span class="sxs-lookup"><span data-stu-id="da03b-187">Microsoft Store for Business and Education is a custom store for your corporate environment.</span></span>  <span data-ttu-id="da03b-188">它可讓您使用 Windows 10 和 HoloLens 內建的 Microsoft Store 來尋找、取得、發佈及管理組織的應用程式。</span><span class="sxs-lookup"><span data-stu-id="da03b-188">It lets you use the Microsoft Store built into Windows 10 and HoloLens to find, acquire, distribute, and manage apps for your organization.</span></span>  <span data-ttu-id="da03b-189">它也可讓您針對您的商業環境而非全世界，部署專用的應用程式。</span><span class="sxs-lookup"><span data-stu-id="da03b-189">It also lets you deploy apps that are specific to your commercial environment but not to the world.</span></span>

1. <span data-ttu-id="da03b-190">透過 Intune 或其他行動裝置管理解決方案來部署和管理應用程式</span><span class="sxs-lookup"><span data-stu-id="da03b-190">Application deployment and management via Intune or another mobile device management solution</span></span>  
  <span data-ttu-id="da03b-191">大部分的行動裝置管理解決方案 (包括 Intune) 都能讓您直接將商務用應用程式部署到一組註冊的裝置上。</span><span class="sxs-lookup"><span data-stu-id="da03b-191">Most mobile device management solutions, including Intune, provide a way to deploy line of business applications directly to a set of enrolled devices.</span></span>  <span data-ttu-id="da03b-192">請參閱這篇文章，了解[如何安裝 Intune 應用程式](https://docs.microsoft.com/intune/apps-deploy)。</span><span class="sxs-lookup"><span data-stu-id="da03b-192">See this article for [Intune app install](https://docs.microsoft.com/intune/apps-deploy).</span></span>

1. <span data-ttu-id="da03b-193">_不建議_使用裝置入口網站</span><span class="sxs-lookup"><span data-stu-id="da03b-193">_not recommended_ Device Portal</span></span>  
  <span data-ttu-id="da03b-194">也可以直接使用 Windows 裝置入口網站安裝在 HoloLens 上安裝應用程式。</span><span class="sxs-lookup"><span data-stu-id="da03b-194">Applications can also be installed on HoloLens directly using the Windows Device Portal.</span></span>  <span data-ttu-id="da03b-195">我們不建議這樣做，因為必須啟用開發人員模式才能使用裝置入口網站。</span><span class="sxs-lookup"><span data-stu-id="da03b-195">This isn't recommended since Developer Mode has to be enabled to use the device portal.</span></span>

<span data-ttu-id="da03b-196">如需詳細資訊，請參閱[在 HoloLens 上安裝應用程式](https://docs.microsoft.com/hololens/hololens-install-apps)。</span><span class="sxs-lookup"><span data-stu-id="da03b-196">Read more about [installing apps on HoloLens](https://docs.microsoft.com/hololens/hololens-install-apps).</span></span>

### <span data-ttu-id="da03b-197">憑證</span><span class="sxs-lookup"><span data-stu-id="da03b-197">Certificates</span></span>

<span data-ttu-id="da03b-198">您可以透過 MDM 提供者發佈憑證。</span><span class="sxs-lookup"><span data-stu-id="da03b-198">You can distribute certificates through your MDM provider.</span></span> <span data-ttu-id="da03b-199">如果貴公司需要憑證，Intune 支援 PKCS、PFX 和 SCEP。</span><span class="sxs-lookup"><span data-stu-id="da03b-199">If your company requires certificates, Intune supports PKCS, PFX, and SCEP.</span></span> <span data-ttu-id="da03b-200">請務必了解哪個憑證適合貴公司。</span><span class="sxs-lookup"><span data-stu-id="da03b-200">It is important to understand which certificate is right for your company.</span></span> <span data-ttu-id="da03b-201">請前往 [憑證設定](https://docs.microsoft.com/intune/protect/certificates-configure) 文件，以判斷哪一種憑證最適合您。</span><span class="sxs-lookup"><span data-stu-id="da03b-201">Please visit the [certificate configurations](https://docs.microsoft.com/intune/protect/certificates-configure) documentation to determine which cert is best for you.</span></span> <span data-ttu-id="da03b-202">如果您計劃將憑證用於 HoloLens 驗證，則 PFX 或 SCEP 可能適合您。</span><span class="sxs-lookup"><span data-stu-id="da03b-202">If you plan to use certificates for HoloLens Authentication, PFX or SCEP may be right for you.</span></span>

<span data-ttu-id="da03b-203">請參閱下列 [SCEP](https://docs.microsoft.com/intune/protect/certificates-profile-scep) 使用步驟。</span><span class="sxs-lookup"><span data-stu-id="da03b-203">See the following steps for using [SCEP](https://docs.microsoft.com/intune/protect/certificates-profile-scep).</span></span>

### <span data-ttu-id="da03b-204">如何升級至 Holographics for Business 商業套件</span><span class="sxs-lookup"><span data-stu-id="da03b-204">How to Upgrade to Holographics for Business Commercial Suite</span></span>

> [!NOTE]
> <span data-ttu-id="da03b-205">Windows Holographics for Business (商業套件) 僅適用於 HoloLens 第一代裝置。</span><span class="sxs-lookup"><span data-stu-id="da03b-205">Windows Holographics for Business (commercial suite) is only intended for HoloLens 1st gen devices.</span></span> <span data-ttu-id="da03b-206">設定檔將不會套用到 HoloLens 2 裝置。</span><span class="sxs-lookup"><span data-stu-id="da03b-206">The profile will not be applied to HoloLens 2 devices.</span></span>

<span data-ttu-id="da03b-207">您可以在 [全像攝影升級](https://docs.microsoft.com/intune/configuration/holographic-upgrade) 文件中找到升級至商業套件的相關指示。</span><span class="sxs-lookup"><span data-stu-id="da03b-207">You can find directions for upgrading to the commercial suite in the [holographic upgrade](https://docs.microsoft.com/intune/configuration/holographic-upgrade) documentation.</span></span>

### <span data-ttu-id="da03b-208">如何使用 Microsoft Intune 設定 Kiosk 模式</span><span class="sxs-lookup"><span data-stu-id="da03b-208">How to Configure Kiosk Mode Using Microsoft Intune</span></span>

1. <span data-ttu-id="da03b-209">將 Microsoft Store 同步處理至 Intune (請參閱[下列指示](https://docs.microsoft.com/intune/apps/windows-store-for-business))。</span><span class="sxs-lookup"><span data-stu-id="da03b-209">Sync Microsoft Store to Intune (See the following [instructions](https://docs.microsoft.com/intune/apps/windows-store-for-business)).</span></span>

1. <span data-ttu-id="da03b-210">檢查您的應用程式設定</span><span class="sxs-lookup"><span data-stu-id="da03b-210">Check your app settings</span></span>
    1. <span data-ttu-id="da03b-211">登入您的 Microsoft Store 商務帳戶</span><span class="sxs-lookup"><span data-stu-id="da03b-211">Log into your Microsoft Store Business account</span></span>
    1. **<span data-ttu-id="da03b-212">[管理] > [產品和服務] > [應用程式和軟體] > [選取您要同步處理的應用程式] > [私人儲存區可用性] > [選取 [所有人] 或 [特定群組]]</span><span class="sxs-lookup"><span data-stu-id="da03b-212">Manage > Products and Services > Apps and Software > Select the app you want to sync > Private Store Availability > Select "Everyone" or "Specific Groups"</span></span>**
        >[!NOTE]
        ><span data-ttu-id="da03b-213">如果您沒有看到您想要的應用程式，您必須在 Microsoft Store 搜尋此應用程式來「取得」它。</span><span class="sxs-lookup"><span data-stu-id="da03b-213">If you don't see the app you want, you will have to "get" the app by searching the store for your app.</span></span> <span data-ttu-id="da03b-214">**按一下右上角的 [搜尋] 列 > 輸入應用程式名稱 > 按一下應用程式 > 選取 [取得]**。</span><span class="sxs-lookup"><span data-stu-id="da03b-214">**Click the "Search" bar in the upper right-hand corner > type in the name of the app > click on the app > select "Get"**.</span></span>
    1. <span data-ttu-id="da03b-215">如果您在 [Intune] > [用戶端應用程式] > [應用程式] \*\*\*\* 中沒有看到您的應用程式，您可能需要再次[同步處理您的應用程式](https://docs.microsoft.com/intune/apps/windows-store-for-business#synchronize-apps)。</span><span class="sxs-lookup"><span data-stu-id="da03b-215">If you do not see your apps in **Intune > Client Apps > Apps** , you may have to [sync your apps](https://docs.microsoft.com/intune/apps/windows-store-for-business#synchronize-apps) again.</span></span>

1. [<span data-ttu-id="da03b-216">建立適用於 Kiosk 模式的裝置設定檔</span><span class="sxs-lookup"><span data-stu-id="da03b-216">Create a device profile for Kiosk mode</span></span>](https://docs.microsoft.com/intune/configuration/kiosk-settings#create-the-profile)

> [!NOTE]
> <span data-ttu-id="da03b-217">您可以使用「Azure AD」作為「使用者登入類型」，設定讓不同使用者有不同的 Kiosk 模式體驗。</span><span class="sxs-lookup"><span data-stu-id="da03b-217">You can configure different users to have different Kiosk Mode experiences by using "Azure AD" as the "User logon type".</span></span> <span data-ttu-id="da03b-218">不過，此選項僅於多重應用程式 Kiosk 模式中可用。</span><span class="sxs-lookup"><span data-stu-id="da03b-218">However, this option is only available in Multi-App kiosk mode.</span></span> <span data-ttu-id="da03b-219">多重應用程式 Kiosk 模式可搭配僅一個應用程式和多個應用程式使用。</span><span class="sxs-lookup"><span data-stu-id="da03b-219">Multi-App kiosk mode will work with only one app as well as multiple apps.</span></span>

![顯示 Intune 中 Kiosk 模式設定的影像](images/aad-kioskmode.png)

<span data-ttu-id="da03b-221">如需其他 MDM 服務，請參閱提供者文件中的指示。</span><span class="sxs-lookup"><span data-stu-id="da03b-221">For other MDM services, check your provider's documentation for instructions.</span></span> <span data-ttu-id="da03b-222">如果您需要使用自訂設定和完整的 XML 設定來設定 MDM 服務中的資訊站，請參閱 [HoloLens Kiosk](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) 指示。</span><span class="sxs-lookup"><span data-stu-id="da03b-222">Refer to the [HoloLens kiosk](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) instructions if you need to use a custom setting and full XML configuration to set up a kiosk in your MDM service.</span></span>

## <span data-ttu-id="da03b-223">憑證和驗證</span><span class="sxs-lookup"><span data-stu-id="da03b-223">Certificates and Authentication</span></span>

<span data-ttu-id="da03b-224">可透過您的 MDM 來部署憑證 (請參閱 [MDM 區段](hololens-commercial-infrastructure.md#mobile-device-manager-guidance)中的「憑證」)。</span><span class="sxs-lookup"><span data-stu-id="da03b-224">Certificates can be deployed via you MDM (see "certificates" in the [MDM Section](hololens-commercial-infrastructure.md#mobile-device-manager-guidance)).</span></span> <span data-ttu-id="da03b-225">您也可以透過套件佈建，將憑證部署至 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="da03b-225">Certificates can also be deployed to the HoloLens through package provisioning.</span></span> <span data-ttu-id="da03b-226">如需詳細資訊，請參閱 [HoloLens 佈建](hololens-provisioning.md)。</span><span class="sxs-lookup"><span data-stu-id="da03b-226">Please see [HoloLens Provisioning](hololens-provisioning.md) for additional information.</span></span>

### <span data-ttu-id="da03b-227">其他 Intune 快速連結</span><span class="sxs-lookup"><span data-stu-id="da03b-227">Additional Intune Quick Links</span></span>

1. <span data-ttu-id="da03b-228">[建立設定檔：](https://docs.microsoft.com/intune/configuration/device-profile-create)設定檔可讓您新增並設定將推送到組織內裝置的設定。</span><span class="sxs-lookup"><span data-stu-id="da03b-228">[Create Profiles:](https://docs.microsoft.com/intune/configuration/device-profile-create) Profiles allow you to add and configure settings that will be pushed to the devices in your organization.</span></span>

