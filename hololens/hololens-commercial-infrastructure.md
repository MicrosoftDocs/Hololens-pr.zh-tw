---
title: HoloLens 的基礎結構指導方針
description: HoloLens 裝置的基礎結構指導方針
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
ms.openlocfilehash: a67aaa5df4c74531b5bed88abaa266b00de5c406
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/01/2021
ms.locfileid: "11253160"
---
# <span data-ttu-id="b3e84-103">設定適用於 HoloLens 的網路</span><span class="sxs-lookup"><span data-stu-id="b3e84-103">Configure Your Network for HoloLens</span></span>

<span data-ttu-id="b3e84-104">文件的此部分將需要下列人員：</span><span class="sxs-lookup"><span data-stu-id="b3e84-104">This portion of the document will require the following people:</span></span>

1. <span data-ttu-id="b3e84-105">具備權限可變更 Proxy/防火牆的網路系統管理員</span><span class="sxs-lookup"><span data-stu-id="b3e84-105">Network Admin with permissions to make changes to the proxy/firewall</span></span>
2. <span data-ttu-id="b3e84-106">Azure Active Directory 系統管理員</span><span class="sxs-lookup"><span data-stu-id="b3e84-106">Azure Active Directory Admin</span></span>
3. <span data-ttu-id="b3e84-107">行動裝置管理系統管理員</span><span class="sxs-lookup"><span data-stu-id="b3e84-107">Mobile Device Manager Admin</span></span>

## <span data-ttu-id="b3e84-108">基礎結構需求</span><span class="sxs-lookup"><span data-stu-id="b3e84-108">Infrastructure Requirements</span></span>

<span data-ttu-id="b3e84-109">HoloLens 是與 Azure 整合的 Windows 行動裝置。</span><span class="sxs-lookup"><span data-stu-id="b3e84-109">HoloLens is, at its core, a Windows mobile device integrated with Azure.</span></span>  <span data-ttu-id="b3e84-110">它在可使用無線網路 (wi-fi) 和可存取 Microsoft 服務的商業環境中效果最佳。</span><span class="sxs-lookup"><span data-stu-id="b3e84-110">It works best in commercial environments with wireless network availability (wi-fi) and access to Microsoft services.</span></span>

<span data-ttu-id="b3e84-111">重要的雲端服務包括：</span><span class="sxs-lookup"><span data-stu-id="b3e84-111">Critical cloud services include:</span></span>

- <span data-ttu-id="b3e84-112">Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="b3e84-112">Azure active directory (Azure AD)</span></span>
- <span data-ttu-id="b3e84-113">Windows Update (WU)</span><span class="sxs-lookup"><span data-stu-id="b3e84-113">Windows Update (WU)</span></span>

<span data-ttu-id="b3e84-114">商業客戶需要企業行動管理 (EMM) 或行動裝置管理 (MDM) 基礎結構，以管理大規模的 HoloLens 裝置。</span><span class="sxs-lookup"><span data-stu-id="b3e84-114">Commercial customers will need enterprise mobility management (EMM) or mobile device management (MDM) infrastructure to manage HoloLens devices at scale.</span></span>  <span data-ttu-id="b3e84-115">本指南使用 [Microsoft Intune](https://www.microsoft.com/enterprise-mobility-security/microsoft-intune) 範例，而任何提供 Microsoft Policy 完整支援的提供者都可以支援 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="b3e84-115">This guide uses [Microsoft Intune](https://www.microsoft.com/enterprise-mobility-security/microsoft-intune) as an example, though any provider with full support for Microsoft Policy can support HoloLens.</span></span>  <span data-ttu-id="b3e84-116">詢問您的行動裝置管理提供者是否支援 HoloLens 2。</span><span class="sxs-lookup"><span data-stu-id="b3e84-116">Ask your mobile device management provider if they support HoloLens 2.</span></span>

<span data-ttu-id="b3e84-117">HoloLens 也支援一組有限的雲端連線中斷體驗。</span><span class="sxs-lookup"><span data-stu-id="b3e84-117">HoloLens does support a limited set of cloud disconnected experiences.</span></span>

### <span data-ttu-id="b3e84-118">無線網路 EAP 支援</span><span class="sxs-lookup"><span data-stu-id="b3e84-118">Wireless network EAP support</span></span>

- <span data-ttu-id="b3e84-119">PEAP-MS-CHAPv2</span><span class="sxs-lookup"><span data-stu-id="b3e84-119">PEAP-MS-CHAPv2</span></span>
- <span data-ttu-id="b3e84-120">PEAP-TLS</span><span class="sxs-lookup"><span data-stu-id="b3e84-120">PEAP-TLS</span></span>
- <span data-ttu-id="b3e84-121">TLS</span><span class="sxs-lookup"><span data-stu-id="b3e84-121">TLS</span></span>
- <span data-ttu-id="b3e84-122">TTLS-CHAP</span><span class="sxs-lookup"><span data-stu-id="b3e84-122">TTLS-CHAP</span></span>
- <span data-ttu-id="b3e84-123">TTLS-CHAPv2</span><span class="sxs-lookup"><span data-stu-id="b3e84-123">TTLS-CHAPv2</span></span>
- <span data-ttu-id="b3e84-124">TTLS-MS-CHAPv2</span><span class="sxs-lookup"><span data-stu-id="b3e84-124">TTLS-MS-CHAPv2</span></span>
- <span data-ttu-id="b3e84-125">TTLS-PAP</span><span class="sxs-lookup"><span data-stu-id="b3e84-125">TTLS-PAP</span></span>
- <span data-ttu-id="b3e84-126">TTLS-TLS</span><span class="sxs-lookup"><span data-stu-id="b3e84-126">TTLS-TLS</span></span>

### <span data-ttu-id="b3e84-127">HoloLens 特定網路需求</span><span class="sxs-lookup"><span data-stu-id="b3e84-127">HoloLens Specific Network Requirements</span></span>

<span data-ttu-id="b3e84-128">請確認您的網路防火牆允許此端點[清單](hololens-offline.md)。</span><span class="sxs-lookup"><span data-stu-id="b3e84-128">Make sure that [this list](hololens-offline.md) of endpoints are allowed on your network firewall.</span></span> <span data-ttu-id="b3e84-129">這可讓 HoloLens 正常運作。</span><span class="sxs-lookup"><span data-stu-id="b3e84-129">This will enable HoloLens to function properly.</span></span>

### <span data-ttu-id="b3e84-130">遠端協助特定網路需求</span><span class="sxs-lookup"><span data-stu-id="b3e84-130">Remote Assist Specific Network Requirements</span></span>

1. <span data-ttu-id="b3e84-131">若要獲得最佳遠端協助的效能，建議使用的頻寬為 1.5Mbps。</span><span class="sxs-lookup"><span data-stu-id="b3e84-131">The recommended bandwidth for optimal performance of Remote Assist is 1.5Mbps.</span></span> <span data-ttu-id="b3e84-132">您可以在[這裡](https://docs.microsoft.com/MicrosoftTeams/prepare-network)找到詳細的網路需求及其他資訊。</span><span class="sxs-lookup"><span data-stu-id="b3e84-132">Detailed network requirements and additional information can be found [here](https://docs.microsoft.com/MicrosoftTeams/prepare-network).</span></span>
**<span data-ttu-id="b3e84-133">(請注意，如果您的網路未具備至少 1.5Mbps 的網路速度，遠端協助仍可運作。</span><span class="sxs-lookup"><span data-stu-id="b3e84-133">(Please note, if you don't network have network speeds of at least 1.5Mbps, Remote Assist will still work.</span></span> <span data-ttu-id="b3e84-134">但品質可能會受到影響。)</span><span class="sxs-lookup"><span data-stu-id="b3e84-134">However, quality may suffer).</span></span>**
1. <span data-ttu-id="b3e84-135">請確認您的網路防火牆允許這些連接埠和 URL。</span><span class="sxs-lookup"><span data-stu-id="b3e84-135">Make sure that these ports and URLs are allowed on your network firewall.</span></span> <span data-ttu-id="b3e84-136">這可讓 Microsoft Teams 正常運作。</span><span class="sxs-lookup"><span data-stu-id="b3e84-136">This will enable Microsoft Teams to function.</span></span> <span data-ttu-id="b3e84-137">您可以在[這裡](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)找到最新清單。</span><span class="sxs-lookup"><span data-stu-id="b3e84-137">The latest list can be found [here](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams).</span></span>

- <span data-ttu-id="b3e84-138">深入瞭解特定的[遠端協助的網路需求](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#network-requirements)。</span><span class="sxs-lookup"><span data-stu-id="b3e84-138">Learn more about the specific [Network Requirements for Remote Assist](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#network-requirements).</span></span> 
- <span data-ttu-id="b3e84-139">深入瞭解如何 [準備貴組織的 Microsoft Teams 網路](https://docs.microsoft.com/MicrosoftTeams/prepare-network)</span><span class="sxs-lookup"><span data-stu-id="b3e84-139">Learn more about how to [prepare your organization's network for Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/prepare-network)</span></span>

### <span data-ttu-id="b3e84-140">特定網路需求指南</span><span class="sxs-lookup"><span data-stu-id="b3e84-140">Guides Specific Network Requirements</span></span>

<span data-ttu-id="b3e84-141">只需要網路存取即可下載指南並使用應用程式。</span><span class="sxs-lookup"><span data-stu-id="b3e84-141">Guides only require network access to download and use the app.</span></span>

## <span data-ttu-id="b3e84-142">Azure Active Directory 指導方針</span><span class="sxs-lookup"><span data-stu-id="b3e84-142">Azure Active Directory Guidance</span></span>

> [!NOTE]
> <span data-ttu-id="b3e84-143">只有在公司計劃管理 HoloLens 時，才需要執行此步驟。</span><span class="sxs-lookup"><span data-stu-id="b3e84-143">This step is only necessary if your company plans on managing the HoloLens.</span></span>

1. <span data-ttu-id="b3e84-144">確定您擁有 Azure AD 授權。</span><span class="sxs-lookup"><span data-stu-id="b3e84-144">Ensure that you have an Azure AD License.</span></span>
<span data-ttu-id="b3e84-145">如需詳細資訊，請參閱 [HoloLens 授權需求](hololens-licenses-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b3e84-145">Please [HoloLens Licenses Requirements](hololens-licenses-requirements.md) for additional information.</span></span>

1. <span data-ttu-id="b3e84-146">如果您打算使用自動註冊，您必須[設定 Azure AD 註冊。](https://docs.microsoft.com/intune/deploy-use/.set-up-windows-device-management-with-microsoft-intune#azure-active-directory-enrollment)</span><span class="sxs-lookup"><span data-stu-id="b3e84-146">If you plan on using Auto Enrollment, you will have to [Configure Azure AD enrollment.](https://docs.microsoft.com/intune/deploy-use/.set-up-windows-device-management-with-microsoft-intune#azure-active-directory-enrollment)</span></span>

1. <span data-ttu-id="b3e84-147">確定貴公司的使用者位於 Azure Active Directory (Azure AD) 中。</span><span class="sxs-lookup"><span data-stu-id="b3e84-147">Ensure that your company's users are in Azure Active Directory (Azure AD).</span></span>
<span data-ttu-id="b3e84-148">您可以在[這裡](https://docs.microsoft.com/azure/active-directory/fundamentals/add-users-azure-active-directory)找到新增使用者的指示。</span><span class="sxs-lookup"><span data-stu-id="b3e84-148">Instructions for adding users can be found [here](https://docs.microsoft.com/azure/active-directory/fundamentals/add-users-azure-active-directory).</span></span>

1. <span data-ttu-id="b3e84-149">建議將需要類似授權的使用者新增至相同的群組。</span><span class="sxs-lookup"><span data-stu-id="b3e84-149">We suggest that users who need similar licenses are added to the same group.</span></span>
    1. [<span data-ttu-id="b3e84-150">建立群組</span><span class="sxs-lookup"><span data-stu-id="b3e84-150">Create a Group</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)
    1. [<span data-ttu-id="b3e84-151">新增使用者至群組</span><span class="sxs-lookup"><span data-stu-id="b3e84-151">Add users to groups</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal)

1. <span data-ttu-id="b3e84-152">確定貴公司的使用者 (或使用者群組) 已獲指派必要的授權。</span><span class="sxs-lookup"><span data-stu-id="b3e84-152">Ensure that your company's users (or group of users) are assigned the necessary licenses.</span></span>
<span data-ttu-id="b3e84-153">您可以在[這裡](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups)找到指派授權的指示。</span><span class="sxs-lookup"><span data-stu-id="b3e84-153">Directions for assigning licenses can be found [here](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups).</span></span>

1. <span data-ttu-id="b3e84-154">只有在使用者想要註冊自己的 HoloLens/行動裝置時，再執行此步驟 (有三個選項)。這些步驟可確定貴公司的使用者 (或使用者群組) 可以新增裝置。</span><span class="sxs-lookup"><span data-stu-id="b3e84-154">Only do this step if users are expected to enroll their HoloLens/Mobile device into you (There are three options) These steps ensure that your company's users (or a group of users) can add devices.</span></span>
    1. <span data-ttu-id="b3e84-155">**選項 1：** 提供所有使用者將裝置加入 Azure AD 的權限。</span><span class="sxs-lookup"><span data-stu-id="b3e84-155">**Option 1:** Give all users permission to join devices to Azure AD.</span></span>
<span data-ttu-id="b3e84-156">**以系統管理員身分登入 Azure 入口網站**  >  [Azure Active Directory]\*\*\*\*  >  [裝置]\*\*\*\*  >  [裝置設定]\*\*\*\*  >
 將 [使用者可以將裝置加入 Azure AD] 設定為 [全部]\*\*\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="b3e84-156">**Sign in to the Azure portal as an administrator** > **Azure Active Directory** > **Devices** > **Device Settings** >
**Set Users may join devices to Azure AD to *All***</span></span>

    1. <span data-ttu-id="b3e84-157">**選項 2：** 提供所選的使用者/群組將裝置加入 Azure AD 的權限。**以系統管理員身分登入 Azure 入口網站** > **Azure Active Directory** > **裝置** > **裝置設定** >
\*\*將 [使用者可以將裝置加入 Azure AD] 設定為 [已選取]\*\*\*\*
![顯示 [加入 Azure AD 之裝置的設定] 影像</span><span class="sxs-lookup"><span data-stu-id="b3e84-157">**Option 2:** Give selected users/groups permission to join devices to Azure AD **Sign in to the Azure portal as an administrator** > **Azure Active Directory** > **Devices** > **Device Settings** >
\*\*Set Users may join devices to Azure AD to \*Selected\*\*\*
![Image that shows Configuration of Azure AD Joined Devices</span></span>](images/azure-ad-image.png)

    1. <span data-ttu-id="b3e84-158">**選項 3：** 您可以封鎖所有使用者，讓他們無法將裝置加入網域。</span><span class="sxs-lookup"><span data-stu-id="b3e84-158">**Option 3:** You can block all users from joining their devices to the domain.</span></span> <span data-ttu-id="b3e84-159">這表示將必須手動註冊所有裝置。</span><span class="sxs-lookup"><span data-stu-id="b3e84-159">This means that all devices will need to be manually enrolled.</span></span>

## <span data-ttu-id="b3e84-160">行動裝置管理員指南</span><span class="sxs-lookup"><span data-stu-id="b3e84-160">Mobile Device Manager Guidance</span></span>

### <span data-ttu-id="b3e84-161">持續的裝置管理</span><span class="sxs-lookup"><span data-stu-id="b3e84-161">Ongoing device management</span></span>

> [!NOTE]
> <span data-ttu-id="b3e84-162">只有在公司計劃管理 HoloLens 時，才需要執行此步驟。</span><span class="sxs-lookup"><span data-stu-id="b3e84-162">This step is only necessary if your company plans to manage the HoloLens.</span></span>

<span data-ttu-id="b3e84-163">持續的裝置管理將視您的行動裝置管理基礎結構而定。</span><span class="sxs-lookup"><span data-stu-id="b3e84-163">Ongoing device management will depend on your mobile device management infrastructure.</span></span>  <span data-ttu-id="b3e84-164">大部分會與一般功能相同，但使用者介面可能有所差異。</span><span class="sxs-lookup"><span data-stu-id="b3e84-164">Most have the same general functionality but the user interface may vary widely.</span></span>

1. <span data-ttu-id="b3e84-165">[CSP (組態服務提供者)](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) 可讓您為網路上的裝置建立並部署管理設定。</span><span class="sxs-lookup"><span data-stu-id="b3e84-165">[CSPs (Configuration Service Providers)](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) allows you to create and deploy management settings for the devices on your network.</span></span> <span data-ttu-id="b3e84-166">您可以在[這裡](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices)找到 HoloLens 的 CSP 清單。</span><span class="sxs-lookup"><span data-stu-id="b3e84-166">A list of CSPs for HoloLens can be found [here](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices).</span></span>

1. <span data-ttu-id="b3e84-167">[合規性原則](https://docs.microsoft.com/intune/device-compliance-get-started)是裝置必須符合的規則和設定，以符合您公司的基礎結構。</span><span class="sxs-lookup"><span data-stu-id="b3e84-167">[Compliance policies](https://docs.microsoft.com/intune/device-compliance-get-started) are rules and settings that devices must meet to be compliant in your corporate infrastructure.</span></span> <span data-ttu-id="b3e84-168">使用這些原則搭配條件式存取，以封鎖不合規的裝置存取公司資源。</span><span class="sxs-lookup"><span data-stu-id="b3e84-168">Use these policies with Conditional Access to block access to company resources for devices that are non-compliant.</span></span> <span data-ttu-id="b3e84-169">例如，您可以建立必須啟用 Bitlocker 的原則。</span><span class="sxs-lookup"><span data-stu-id="b3e84-169">For example, you can create a policy that requires Bitlocker be enabled.</span></span>

1. <span data-ttu-id="b3e84-170">[建立合規性原則](https://docs.microsoft.com/intune/protect/compliance-policy-create-windows)。</span><span class="sxs-lookup"><span data-stu-id="b3e84-170">[Create Compliance Policy](https://docs.microsoft.com/intune/protect/compliance-policy-create-windows).</span></span>

1. <span data-ttu-id="b3e84-171">條件式存取可允許/拒絕行動裝置和行動應用程式存取公司資源。</span><span class="sxs-lookup"><span data-stu-id="b3e84-171">Conditional Access allows/denies mobile devices and mobile applications from accessing company resources.</span></span> <span data-ttu-id="b3e84-172">有兩份實用的文件：[規劃您的 CA 部署](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access)和[最佳做法](https://docs.microsoft.com/azure/active-directory/conditional-access/best-practices)。</span><span class="sxs-lookup"><span data-stu-id="b3e84-172">Two documents you may find helpful are [Plan your CA Deployment](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) and [Best Practices](https://docs.microsoft.com/azure/active-directory/conditional-access/best-practices).</span></span>

1. <span data-ttu-id="b3e84-173">[這篇文章](https://docs.microsoft.com/intune/fundamentals/windows-holographic-for-business)討論的是適用於 HoloLens 的 Intune 管理工具。</span><span class="sxs-lookup"><span data-stu-id="b3e84-173">[This article](https://docs.microsoft.com/intune/fundamentals/windows-holographic-for-business) talks about Intune's management tools for HoloLens.</span></span>

1. [<span data-ttu-id="b3e84-174">建立裝置設定檔</span><span class="sxs-lookup"><span data-stu-id="b3e84-174">Create a device profile</span></span>](https://docs.microsoft.com/intune/configuration/device-profile-create)

### <span data-ttu-id="b3e84-175">管理更新</span><span class="sxs-lookup"><span data-stu-id="b3e84-175">Manage updates</span></span>

<span data-ttu-id="b3e84-176">Intune 包括稱為 Windows 10 裝置更新週期的功能，包含 HoloLens 2 和 HoloLens v1 (含 Holographic for Business)。</span><span class="sxs-lookup"><span data-stu-id="b3e84-176">Intune includes a feature called Update rings for Windows 10 devices, including HoloLens 2 and HoloLens v1 (with Holographic for Business).</span></span> <span data-ttu-id="b3e84-177">更新週期包括一組設定，可決定更新的安裝方式和時間。</span><span class="sxs-lookup"><span data-stu-id="b3e84-177">Update rings include a group of settings that determine how and when updates are installed.</span></span>

<span data-ttu-id="b3e84-178">例如，您可以建立要安裝更新的維護時段，或選擇在安裝更新後重新開機。</span><span class="sxs-lookup"><span data-stu-id="b3e84-178">For example, you can create a maintenance window to install updates, or choose to restart after updates are installed.</span></span>  <span data-ttu-id="b3e84-179">您也可以選擇無限期暫停更新，直到您準備好更新為止。</span><span class="sxs-lookup"><span data-stu-id="b3e84-179">You can also choose to pause updates indefinitely until you're ready to update.</span></span>

<span data-ttu-id="b3e84-180">如需詳細資訊，請參閱[](https://docs.microsoft.com/intune/windows-update-for-business-configure)使用 Intune 設定更新週期[。](https://docs.microsoft.com/intune/windows-update-for-business-configure)</span><span class="sxs-lookup"><span data-stu-id="b3e84-180">Read more about [configuring update rings with Intune](https://docs.microsoft.com/intune/windows-update-for-business-configure).</span></span>

### <span data-ttu-id="b3e84-181">應用程式管理</span><span class="sxs-lookup"><span data-stu-id="b3e84-181">Application management</span></span>

<span data-ttu-id="b3e84-182">透過下列方法管理 HoloLens 應用程式：</span><span class="sxs-lookup"><span data-stu-id="b3e84-182">Manage HoloLens applications through:</span></span>

1. <span data-ttu-id="b3e84-183">Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="b3e84-183">Microsoft Store</span></span>  
  <span data-ttu-id="b3e84-184">Microsoft Store 是發佈和使用 HoloLens 上的應用程式的最佳方式。</span><span class="sxs-lookup"><span data-stu-id="b3e84-184">The Microsoft Store is the best way to distribute and consume applications on HoloLens.</span></span>  <span data-ttu-id="b3e84-185">商店中已有許多很棒的核心 HoloLens 應用程式，或者您也可以[發佈自己的](https://docs.microsoft.com/windows/uwp/publish/)。</span><span class="sxs-lookup"><span data-stu-id="b3e84-185">There is a great set of core HoloLens applications already available in the store or you can [publish your own](https://docs.microsoft.com/windows/uwp/publish/).</span></span>  
  <span data-ttu-id="b3e84-186">商店中的所有應用程式都能公開供所有人使用，但是若無法使用，請查看商務用 Microsoft Store。</span><span class="sxs-lookup"><span data-stu-id="b3e84-186">All applications in the store are available publicly to everyone, but if it isn't acceptable, checkout the Microsoft Store for Business.</span></span>  

1. [<span data-ttu-id="b3e84-187">商務用 Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="b3e84-187">Microsoft Store for Business</span></span>](https://docs.microsoft.com/microsoft-store/)  
  <span data-ttu-id="b3e84-188">商務與教育用 Microsoft Store 是適用於企業環境的自訂商店。</span><span class="sxs-lookup"><span data-stu-id="b3e84-188">Microsoft Store for Business and Education is a custom store for your corporate environment.</span></span>  <span data-ttu-id="b3e84-189">它可讓您使用 Windows 10 和 HoloLens 內建的 Microsoft Store 來尋找、取得、發佈及管理組織的應用程式。</span><span class="sxs-lookup"><span data-stu-id="b3e84-189">It lets you use the Microsoft Store built into Windows 10 and HoloLens to find, acquire, distribute, and manage apps for your organization.</span></span>  <span data-ttu-id="b3e84-190">它也可讓您針對您的商業環境而非全世界，部署專用的應用程式。</span><span class="sxs-lookup"><span data-stu-id="b3e84-190">It also lets you deploy apps that are specific to your commercial environment but not to the world.</span></span>

1. <span data-ttu-id="b3e84-191">透過 Intune 或其他行動裝置管理解決方案來部署和管理應用程式</span><span class="sxs-lookup"><span data-stu-id="b3e84-191">Application deployment and management via Intune or another mobile device management solution</span></span>  
  <span data-ttu-id="b3e84-192">大部分的行動裝置管理解決方案 (包括 Intune) 都能讓您直接將商務用應用程式部署到一組註冊的裝置上。</span><span class="sxs-lookup"><span data-stu-id="b3e84-192">Most mobile device management solutions, including Intune, provide a way to deploy line of business applications directly to a set of enrolled devices.</span></span>  <span data-ttu-id="b3e84-193">請參閱這篇文章，了解[如何安裝 Intune 應用程式](https://docs.microsoft.com/intune/apps-deploy)。</span><span class="sxs-lookup"><span data-stu-id="b3e84-193">See this article for [Intune app install](https://docs.microsoft.com/intune/apps-deploy).</span></span>

1. <span data-ttu-id="b3e84-194">_不建議_使用裝置入口網站</span><span class="sxs-lookup"><span data-stu-id="b3e84-194">_not recommended_ Device Portal</span></span>  
  <span data-ttu-id="b3e84-195">也可以直接使用 Windows 裝置入口網站安裝在 HoloLens 上安裝應用程式。</span><span class="sxs-lookup"><span data-stu-id="b3e84-195">Applications can also be installed on HoloLens directly using the Windows Device Portal.</span></span>  <span data-ttu-id="b3e84-196">我們不建議這樣做，因為必須啟用開發人員模式才能使用裝置入口網站。</span><span class="sxs-lookup"><span data-stu-id="b3e84-196">This isn't recommended since Developer Mode has to be enabled to use the device portal.</span></span>

<span data-ttu-id="b3e84-197">如需詳細資訊，請參閱[在 HoloLens 上安裝應用程式](https://docs.microsoft.com/hololens/hololens-install-apps)。</span><span class="sxs-lookup"><span data-stu-id="b3e84-197">Read more about [installing apps on HoloLens](https://docs.microsoft.com/hololens/hololens-install-apps).</span></span>

### <span data-ttu-id="b3e84-198">憑證</span><span class="sxs-lookup"><span data-stu-id="b3e84-198">Certificates</span></span>

<span data-ttu-id="b3e84-199">您可以透過 MDM 提供者發佈憑證。</span><span class="sxs-lookup"><span data-stu-id="b3e84-199">You can distribute certificates through your MDM provider.</span></span> <span data-ttu-id="b3e84-200">如果貴公司需要憑證，Intune 支援 PKCS、PFX 和 SCEP。</span><span class="sxs-lookup"><span data-stu-id="b3e84-200">If your company requires certificates, Intune supports PKCS, PFX, and SCEP.</span></span> <span data-ttu-id="b3e84-201">請務必了解哪個憑證適合貴公司。</span><span class="sxs-lookup"><span data-stu-id="b3e84-201">It is important to understand which certificate is right for your company.</span></span> <span data-ttu-id="b3e84-202">請造訪[這裡](https://docs.microsoft.com/intune/protect/certificates-configure)，以判斷何種憑證最適合您。</span><span class="sxs-lookup"><span data-stu-id="b3e84-202">Please visit [here](https://docs.microsoft.com/intune/protect/certificates-configure) to determine which cert is best for you.</span></span> <span data-ttu-id="b3e84-203">如果您計劃將憑證用於 HoloLens 驗證，則 PFX 或 SCEP 可能適合您。</span><span class="sxs-lookup"><span data-stu-id="b3e84-203">If you plan to use certificates for HoloLens Authentication, PFX or SCEP may be right for you.</span></span>

<span data-ttu-id="b3e84-204">您可以在[這裡](https://docs.microsoft.com/intune/protect/certificates-profile-scep)找到 SCEP 的步驟。</span><span class="sxs-lookup"><span data-stu-id="b3e84-204">Steps for SCEP can be found [here](https://docs.microsoft.com/intune/protect/certificates-profile-scep).</span></span>

### <span data-ttu-id="b3e84-205">如何升級至 Holographics for Business 商業套件</span><span class="sxs-lookup"><span data-stu-id="b3e84-205">How to Upgrade to Holographics for Business Commercial Suite</span></span>

> [!NOTE]
> <span data-ttu-id="b3e84-206">Windows Holographics for Business (商業套件) 僅適用於 HoloLens 第一代裝置。</span><span class="sxs-lookup"><span data-stu-id="b3e84-206">Windows Holographics for Business (commercial suite) is only intended for HoloLens 1st gen devices.</span></span> <span data-ttu-id="b3e84-207">設定檔將不會套用到 HoloLens 2 裝置。</span><span class="sxs-lookup"><span data-stu-id="b3e84-207">The profile will not be applied to HoloLens 2 devices.</span></span>

<span data-ttu-id="b3e84-208">您可以在[這裡](https://docs.microsoft.com/intune/configuration/holographic-upgrade)找到升級至商業套件相關指示。</span><span class="sxs-lookup"><span data-stu-id="b3e84-208">Directions for upgrading to the commercial suite can be found [here](https://docs.microsoft.com/intune/configuration/holographic-upgrade).</span></span>

### <span data-ttu-id="b3e84-209">如何使用 Microsoft Intune 設定 Kiosk 模式</span><span class="sxs-lookup"><span data-stu-id="b3e84-209">How to Configure Kiosk Mode Using Microsoft Intune</span></span>

1. <span data-ttu-id="b3e84-210">將 Microsoft Store 同步處理至 Intune ([這裡](https://docs.microsoft.com/intune/apps/windows-store-for-business))。</span><span class="sxs-lookup"><span data-stu-id="b3e84-210">Sync Microsoft Store to Intune ([Here](https://docs.microsoft.com/intune/apps/windows-store-for-business)).</span></span>

1. <span data-ttu-id="b3e84-211">檢查您的應用程式設定</span><span class="sxs-lookup"><span data-stu-id="b3e84-211">Check your app settings</span></span>
    1. <span data-ttu-id="b3e84-212">登入您的 Microsoft Store 商務帳戶</span><span class="sxs-lookup"><span data-stu-id="b3e84-212">Log into your Microsoft Store Business account</span></span>
    1. **<span data-ttu-id="b3e84-213">[管理] > [產品和服務] > [應用程式和軟體] > [選取您要同步處理的應用程式] > [私人儲存區可用性] > [選取 [所有人] 或 [特定群組]]</span><span class="sxs-lookup"><span data-stu-id="b3e84-213">Manage > Products and Services > Apps and Software > Select the app you want to sync > Private Store Availability > Select "Everyone" or "Specific Groups"</span></span>**
        >[!NOTE]
        ><span data-ttu-id="b3e84-214">如果您沒有看到您想要的應用程式，您必須在 Microsoft Store 搜尋此應用程式來「取得」它。</span><span class="sxs-lookup"><span data-stu-id="b3e84-214">If you don't see the app you want, you will have to "get" the app by searching the store for your app.</span></span> <span data-ttu-id="b3e84-215">**按一下右上角的 [搜尋] 列 > 輸入應用程式名稱 > 按一下應用程式 > 選取 [取得]**。</span><span class="sxs-lookup"><span data-stu-id="b3e84-215">**Click the "Search" bar in the upper right-hand corner > type in the name of the app > click on the app > select "Get"**.</span></span>
    1. <span data-ttu-id="b3e84-216">如果您在 [Intune] > [用戶端應用程式] > [應用程式] \*\*\*\* 中沒有看到您的應用程式，您可能需要再次[同步處理您的應用程式](https://docs.microsoft.com/intune/apps/windows-store-for-business#synchronize-apps)。</span><span class="sxs-lookup"><span data-stu-id="b3e84-216">If you do not see your apps in **Intune > Client Apps > Apps** , you may have to [sync your apps](https://docs.microsoft.com/intune/apps/windows-store-for-business#synchronize-apps) again.</span></span>

1. [<span data-ttu-id="b3e84-217">建立適用於 Kiosk 模式的裝置設定檔</span><span class="sxs-lookup"><span data-stu-id="b3e84-217">Create a device profile for Kiosk mode</span></span>](https://docs.microsoft.com/intune/configuration/kiosk-settings#create-the-profile)

> [!NOTE]
> <span data-ttu-id="b3e84-218">您可以使用「Azure AD」作為「使用者登入類型」，設定讓不同使用者有不同的 Kiosk 模式體驗。</span><span class="sxs-lookup"><span data-stu-id="b3e84-218">You can configure different users to have different Kiosk Mode experiences by using "Azure AD" as the "User logon type".</span></span> <span data-ttu-id="b3e84-219">不過，此選項僅於多重應用程式 Kiosk 模式中可用。</span><span class="sxs-lookup"><span data-stu-id="b3e84-219">However, this option is only available in Multi-App kiosk mode.</span></span> <span data-ttu-id="b3e84-220">多重應用程式 Kiosk 模式可搭配僅一個應用程式和多個應用程式使用。</span><span class="sxs-lookup"><span data-stu-id="b3e84-220">Multi-App kiosk mode will work with only one app as well as multiple apps.</span></span>

![顯示 Intune 中 Kiosk 模式設定的影像](images/aad-kioskmode.png)

<span data-ttu-id="b3e84-222">如需其他 MDM 服務，請參閱提供者文件中的指示。</span><span class="sxs-lookup"><span data-stu-id="b3e84-222">For other MDM services, check your provider's documentation for instructions.</span></span> <span data-ttu-id="b3e84-223">如果您需要在 MDM 服務中使用自訂設定和完整 XML 設定來設定 Kiosk，可在[這裡](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)找到其他指示</span><span class="sxs-lookup"><span data-stu-id="b3e84-223">If you need to use a custom setting and full XML configuration to set up a kiosk in your MDM service, additional directions can be found [here](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)</span></span>

## <span data-ttu-id="b3e84-224">憑證和驗證</span><span class="sxs-lookup"><span data-stu-id="b3e84-224">Certificates and Authentication</span></span>

<span data-ttu-id="b3e84-225">可透過您的 MDM 來部署憑證 (請參閱 [MDM 區段](hololens-commercial-infrastructure.md#mobile-device-manager-guidance)中的「憑證」)。</span><span class="sxs-lookup"><span data-stu-id="b3e84-225">Certificates can be deployed via you MDM (see "certificates" in the [MDM Section](hololens-commercial-infrastructure.md#mobile-device-manager-guidance)).</span></span> <span data-ttu-id="b3e84-226">您也可以透過套件佈建，將憑證部署至 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="b3e84-226">Certificates can also be deployed to the HoloLens through package provisioning.</span></span> <span data-ttu-id="b3e84-227">如需詳細資訊，請參閱 [HoloLens 佈建](hololens-provisioning.md)。</span><span class="sxs-lookup"><span data-stu-id="b3e84-227">Please see [HoloLens Provisioning](hololens-provisioning.md) for additional information.</span></span>

### <span data-ttu-id="b3e84-228">其他 Intune 快速連結</span><span class="sxs-lookup"><span data-stu-id="b3e84-228">Additional Intune Quick Links</span></span>

1. <span data-ttu-id="b3e84-229">[建立設定檔：](https://docs.microsoft.com/intune/configuration/device-profile-create)設定檔可讓您新增並設定將推送到組織內裝置的設定。</span><span class="sxs-lookup"><span data-stu-id="b3e84-229">[Create Profiles:](https://docs.microsoft.com/intune/configuration/device-profile-create) Profiles allow you to add and configure settings that will be pushed to the devices in your organization.</span></span>

