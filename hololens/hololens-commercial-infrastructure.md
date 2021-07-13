---
title: HoloLens 的基礎結構指導方針
description: 瞭解 HoloLens 裝置的基礎結構指導方針，包括無線網路支援、遠端協助和行動裝置管理。
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
ms.openlocfilehash: e3f87c524ce0f8af05ec8c92877d46facd962fb4
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639279"
---
# <a name="configure-your-network-for-hololens"></a><span data-ttu-id="6bbed-103">設定您的網路以進行 HoloLens</span><span class="sxs-lookup"><span data-stu-id="6bbed-103">Configure Your Network for HoloLens</span></span>

<span data-ttu-id="6bbed-104">檔的這個部分將需要下列人員：</span><span class="sxs-lookup"><span data-stu-id="6bbed-104">This portion of the document will require the following people:</span></span>

1. <span data-ttu-id="6bbed-105">具有對 proxy/防火牆進行變更之許可權的網路系統管理員</span><span class="sxs-lookup"><span data-stu-id="6bbed-105">Network Admin with permissions to make changes to the proxy/firewall</span></span>
2. <span data-ttu-id="6bbed-106">Azure Active Directory管理</span><span class="sxs-lookup"><span data-stu-id="6bbed-106">Azure Active Directory Admin</span></span>
3. <span data-ttu-id="6bbed-107">Mobile 裝置管理員系統管理員</span><span class="sxs-lookup"><span data-stu-id="6bbed-107">Mobile Device Manager Admin</span></span>

## <a name="infrastructure-requirements"></a><span data-ttu-id="6bbed-108">基礎結構需求</span><span class="sxs-lookup"><span data-stu-id="6bbed-108">Infrastructure Requirements</span></span>

<span data-ttu-id="6bbed-109">HoloLens 是一種與 Azure 整合 Windows 行動裝置的核心。</span><span class="sxs-lookup"><span data-stu-id="6bbed-109">HoloLens is, at its core, a Windows mobile device integrated with Azure.</span></span>  <span data-ttu-id="6bbed-110">它最適合使用無線網路可用性 (wi-fi) 和 Microsoft 服務存取的商業環境。</span><span class="sxs-lookup"><span data-stu-id="6bbed-110">It works best in commercial environments with wireless network availability (wi-fi) and access to Microsoft services.</span></span>

<span data-ttu-id="6bbed-111">重要的雲端服務包括：</span><span class="sxs-lookup"><span data-stu-id="6bbed-111">Critical cloud services include:</span></span>

- <span data-ttu-id="6bbed-112">Azure active directory (Azure AD) </span><span class="sxs-lookup"><span data-stu-id="6bbed-112">Azure active directory (Azure AD)</span></span>
- <span data-ttu-id="6bbed-113">Windows更新 (WU) </span><span class="sxs-lookup"><span data-stu-id="6bbed-113">Windows Update (WU)</span></span>

<span data-ttu-id="6bbed-114">商業客戶需要 (EMM) 或行動裝置管理 (MDM) 基礎結構的企業行動管理，以大規模管理 HoloLens 的裝置。</span><span class="sxs-lookup"><span data-stu-id="6bbed-114">Commercial customers will need enterprise mobility management (EMM) or mobile device management (MDM) infrastructure to manage HoloLens devices at scale.</span></span>  <span data-ttu-id="6bbed-115">本指南使用[Microsoft Intune](https://www.microsoft.com/enterprise-mobility-security/microsoft-intune)作為範例，但任何具有 Microsoft 原則完整支援的提供者都可支援 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="6bbed-115">This guide uses [Microsoft Intune](https://www.microsoft.com/enterprise-mobility-security/microsoft-intune) as an example, though any provider with full support for Microsoft Policy can support HoloLens.</span></span>  <span data-ttu-id="6bbed-116">如果支援 HoloLens 2，請詢問您的行動裝置管理提供者。</span><span class="sxs-lookup"><span data-stu-id="6bbed-116">Ask your mobile device management provider if they support HoloLens 2.</span></span>

<span data-ttu-id="6bbed-117">HoloLens 支援一組有限的雲端中斷連線體驗。</span><span class="sxs-lookup"><span data-stu-id="6bbed-117">HoloLens does support a limited set of cloud disconnected experiences.</span></span>

### <a name="wireless-network-eap-support"></a><span data-ttu-id="6bbed-118">無線網路 EAP 支援</span><span class="sxs-lookup"><span data-stu-id="6bbed-118">Wireless network EAP support</span></span>

- <span data-ttu-id="6bbed-119">PEAP-MS-CHAPv2</span><span class="sxs-lookup"><span data-stu-id="6bbed-119">PEAP-MS-CHAPv2</span></span>
- <span data-ttu-id="6bbed-120">PEAP-TLS</span><span class="sxs-lookup"><span data-stu-id="6bbed-120">PEAP-TLS</span></span>
- <span data-ttu-id="6bbed-121">TLS</span><span class="sxs-lookup"><span data-stu-id="6bbed-121">TLS</span></span>
- <span data-ttu-id="6bbed-122">TTLS-CHAP</span><span class="sxs-lookup"><span data-stu-id="6bbed-122">TTLS-CHAP</span></span>
- <span data-ttu-id="6bbed-123">TTLS-CHAPv2</span><span class="sxs-lookup"><span data-stu-id="6bbed-123">TTLS-CHAPv2</span></span>
- <span data-ttu-id="6bbed-124">TTLS-MS-CHAPv2</span><span class="sxs-lookup"><span data-stu-id="6bbed-124">TTLS-MS-CHAPv2</span></span>
- <span data-ttu-id="6bbed-125">TTLS-PAP</span><span class="sxs-lookup"><span data-stu-id="6bbed-125">TTLS-PAP</span></span>
- <span data-ttu-id="6bbed-126">TTLS-TLS</span><span class="sxs-lookup"><span data-stu-id="6bbed-126">TTLS-TLS</span></span>

### <a name="hololens-specific-network-requirements"></a><span data-ttu-id="6bbed-127">HoloLens特定網路需求</span><span class="sxs-lookup"><span data-stu-id="6bbed-127">HoloLens Specific Network Requirements</span></span>

<span data-ttu-id="6bbed-128">請確定您的網路防火牆上允許這份端點 [清單](hololens-offline.md) 。</span><span class="sxs-lookup"><span data-stu-id="6bbed-128">Make sure that [this list](hololens-offline.md) of endpoints are allowed on your network firewall.</span></span> <span data-ttu-id="6bbed-129">這會讓 HoloLens 能夠正常運作。</span><span class="sxs-lookup"><span data-stu-id="6bbed-129">This will enable HoloLens to function properly.</span></span>

### <a name="remote-assist-specific-network-requirements"></a><span data-ttu-id="6bbed-130">遠端協助特定的網路需求</span><span class="sxs-lookup"><span data-stu-id="6bbed-130">Remote Assist Specific Network Requirements</span></span>

1. <span data-ttu-id="6bbed-131">針對遠端協助的最佳效能，建議的頻寬為 1.5 Mbps。</span><span class="sxs-lookup"><span data-stu-id="6bbed-131">The recommended bandwidth for optimal performance of Remote Assist is 1.5Mbps.</span></span> <span data-ttu-id="6bbed-132">如需其他資訊，請參閱 [詳細的網路需求](/MicrosoftTeams/prepare-network) 。</span><span class="sxs-lookup"><span data-stu-id="6bbed-132">See the [detailed network requirements](/MicrosoftTeams/prepare-network) for additional information.</span></span>
<span data-ttu-id="6bbed-133">**(請注意，如果您不是網路的網路速度至少為 1.5 Mbps，遠端協助仍可運作。不過，品質可能會受到) 的影響。**</span><span class="sxs-lookup"><span data-stu-id="6bbed-133">**(Please note, if you don't network have network speeds of at least 1.5Mbps, Remote Assist will still work. However, quality may suffer).**</span></span>
1. <span data-ttu-id="6bbed-134">請確定您的網路防火牆上允許這些埠和 url，讓 Microsoft Teams 能夠運作。</span><span class="sxs-lookup"><span data-stu-id="6bbed-134">Make sure that these ports and URLs are allowed on your network firewall to enable Microsoft Teams to function.</span></span> <span data-ttu-id="6bbed-135">以 [最新的埠清單](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)保持最新狀態。</span><span class="sxs-lookup"><span data-stu-id="6bbed-135">Stay up to date with the [latest list of ports](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams).</span></span>

- <span data-ttu-id="6bbed-136">深入瞭解 [遠端協助的特定網路需求](/dynamics365/mixed-reality/remote-assist/requirements#network-requirements)。</span><span class="sxs-lookup"><span data-stu-id="6bbed-136">Learn more about the specific [Network Requirements for Remote Assist](/dynamics365/mixed-reality/remote-assist/requirements#network-requirements).</span></span> 
- <span data-ttu-id="6bbed-137">深入瞭解如何為[您的組織網路做好 Microsoft Teams](/MicrosoftTeams/prepare-network)</span><span class="sxs-lookup"><span data-stu-id="6bbed-137">Learn more about how to [prepare your organization's network for Microsoft Teams](/MicrosoftTeams/prepare-network)</span></span>

### <a name="guides-specific-network-requirements"></a><span data-ttu-id="6bbed-138">引導特定網路需求</span><span class="sxs-lookup"><span data-stu-id="6bbed-138">Guides Specific Network Requirements</span></span>

<span data-ttu-id="6bbed-139">指南只需要網路存取權，即可下載及使用應用程式。</span><span class="sxs-lookup"><span data-stu-id="6bbed-139">Guides only require network access to download and use the app.</span></span>

## <a name="azure-active-directory-guidance"></a><span data-ttu-id="6bbed-140">Azure Active Directory指導</span><span class="sxs-lookup"><span data-stu-id="6bbed-140">Azure Active Directory Guidance</span></span>

> [!NOTE]
> <span data-ttu-id="6bbed-141">只有當您的公司計畫管理 HoloLens 時，才需要執行此步驟。</span><span class="sxs-lookup"><span data-stu-id="6bbed-141">This step is only necessary if your company plans on managing the HoloLens.</span></span>

1. <span data-ttu-id="6bbed-142">確定您有 Azure AD 授權。</span><span class="sxs-lookup"><span data-stu-id="6bbed-142">Ensure that you have an Azure AD License.</span></span>
<span data-ttu-id="6bbed-143">如需其他資訊，請[HoloLens 授權需求](hololens-licenses-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6bbed-143">Please [HoloLens Licenses Requirements](hololens-licenses-requirements.md) for additional information.</span></span>

1. <span data-ttu-id="6bbed-144">如果您打算使用自動註冊，就必須 [設定 Azure AD 註冊。](/intune/deploy-use/.set-up-windows-device-management-with-microsoft-intune#azure-active-directory-enrollment)</span><span class="sxs-lookup"><span data-stu-id="6bbed-144">If you plan on using Auto Enrollment, you will have to [Configure Azure AD enrollment.](/intune/deploy-use/.set-up-windows-device-management-with-microsoft-intune#azure-active-directory-enrollment)</span></span>

1. <span data-ttu-id="6bbed-145">確定貴公司的使用者 Azure Active Directory (Azure AD) 。</span><span class="sxs-lookup"><span data-stu-id="6bbed-145">Ensure that your company's users are in Azure Active Directory (Azure AD).</span></span>
<span data-ttu-id="6bbed-146">請參閱下列 [指示](/azure/active-directory/fundamentals/add-users-azure-active-directory) 以新增使用者。</span><span class="sxs-lookup"><span data-stu-id="6bbed-146">See the following [instructions](/azure/active-directory/fundamentals/add-users-azure-active-directory) for adding users.</span></span>

1. <span data-ttu-id="6bbed-147">建議將需要類似授權的使用者新增至相同群組。</span><span class="sxs-lookup"><span data-stu-id="6bbed-147">We suggest that users who need similar licenses are added to the same group.</span></span>
    1. [<span data-ttu-id="6bbed-148">建立群組</span><span class="sxs-lookup"><span data-stu-id="6bbed-148">Create a Group</span></span>](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)
    1. [<span data-ttu-id="6bbed-149">將使用者新增至群組</span><span class="sxs-lookup"><span data-stu-id="6bbed-149">Add users to groups</span></span>](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal)

1. <span data-ttu-id="6bbed-150">確定已將所需的授權指派給公司的使用者 (或使用者群組) 。</span><span class="sxs-lookup"><span data-stu-id="6bbed-150">Ensure that your company's users (or group of users) are assigned the necessary licenses.</span></span>
<span data-ttu-id="6bbed-151">如果您需要指派授權，請遵循下列 [指示](/azure/active-directory/fundamentals/license-users-groups)。</span><span class="sxs-lookup"><span data-stu-id="6bbed-151">If you need to assign licenses, follow these [directions](/azure/active-directory/fundamentals/license-users-groups).</span></span>

1. <span data-ttu-id="6bbed-152">只有當使用者預期在您註冊 HoloLens/Mobile 裝置時，才執行此步驟 (有三個選項) 這些步驟可確保公司的使用者 (或使用者群組) 可以新增裝置。</span><span class="sxs-lookup"><span data-stu-id="6bbed-152">Only do this step if users are expected to enroll their HoloLens/Mobile device into you (There are three options) These steps ensure that your company's users (or a group of users) can add devices.</span></span>
    1. <span data-ttu-id="6bbed-153">**選項1：** 授與所有使用者將裝置加入 Azure AD 的許可權。</span><span class="sxs-lookup"><span data-stu-id="6bbed-153">**Option 1:** Give all users permission to join devices to Azure AD.</span></span>
<span data-ttu-id="6bbed-154">**以系統管理員**  >  身分登入 Azure 入口網站 **Azure Active Directory**  > **裝置**  > **裝置設定**  >
**設定使用者可能會將裝置加入 Azure AD *全部***</span><span class="sxs-lookup"><span data-stu-id="6bbed-154">**Sign in to the Azure portal as an administrator** > **Azure Active Directory** > **Devices** > **Device Settings** >
**Set Users may join devices to Azure AD to *All***</span></span>

    1. <span data-ttu-id="6bbed-155">**選項2：** 為選取的使用者/群組授與裝置的許可權，以將裝置加入 Azure AD 以系統管理員 Azure Active Directory 裝置裝置的身分登 **入 Azure 入口網站**  >    >    >  **設定**  >
 **設定使用者可能會將裝置加入** 至 
 ![ 顯示 Azure AD 已加入裝置設定的影像](images/azure-ad-image.png)</span><span class="sxs-lookup"><span data-stu-id="6bbed-155">**Option 2:** Give selected users/groups permission to join devices to Azure AD **Sign in to the Azure portal as an administrator** > **Azure Active Directory** > **Devices** > **Device Settings** >
\*\*Set Users may join devices to Azure AD to \*Selected\*\*\*
![Image that shows Configuration of Azure AD Joined Devices](images/azure-ad-image.png)</span></span>

    1. <span data-ttu-id="6bbed-156">**選項3：** 您可以封鎖所有使用者將其裝置加入網域。</span><span class="sxs-lookup"><span data-stu-id="6bbed-156">**Option 3:** You can block all users from joining their devices to the domain.</span></span> <span data-ttu-id="6bbed-157">這表示所有裝置都需要手動註冊。</span><span class="sxs-lookup"><span data-stu-id="6bbed-157">This means that all devices will need to be manually enrolled.</span></span>

## <a name="mobile-device-manager-guidance"></a><span data-ttu-id="6bbed-158">Mobile 裝置管理員指導方針</span><span class="sxs-lookup"><span data-stu-id="6bbed-158">Mobile Device Manager Guidance</span></span>

### <a name="ongoing-device-management"></a><span data-ttu-id="6bbed-159">進行中的裝置管理</span><span class="sxs-lookup"><span data-stu-id="6bbed-159">Ongoing device management</span></span>

> [!NOTE]
> <span data-ttu-id="6bbed-160">只有當您的公司計畫管理 HoloLens 時，才需要執行此步驟。</span><span class="sxs-lookup"><span data-stu-id="6bbed-160">This step is only necessary if your company plans to manage the HoloLens.</span></span>

<span data-ttu-id="6bbed-161">進行中的裝置管理將取決於您的行動裝置管理基礎結構。</span><span class="sxs-lookup"><span data-stu-id="6bbed-161">Ongoing device management will depend on your mobile device management infrastructure.</span></span>  <span data-ttu-id="6bbed-162">大部分都有相同的一般功能，但使用者介面可能會有很大的差異。</span><span class="sxs-lookup"><span data-stu-id="6bbed-162">Most have the same general functionality but the user interface may vary widely.</span></span>

1. <span data-ttu-id="6bbed-163">[Csp (設定服務提供者) ](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) 可讓您為網路上的裝置建立及部署管理設定。</span><span class="sxs-lookup"><span data-stu-id="6bbed-163">[CSPs (Configuration Service Providers)](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) lets you to create and deploy management settings for the devices on your network.</span></span> <span data-ttu-id="6bbed-164">請參閱[HoloLens 的 csp 清單](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices)以取得參考。</span><span class="sxs-lookup"><span data-stu-id="6bbed-164">See the [list of HoloLens CSPs](/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) for reference.</span></span>

1. <span data-ttu-id="6bbed-165">[合規性政策](/intune/device-compliance-get-started) 是裝置必須符合才能符合公司基礎結構規範的規則和設定。</span><span class="sxs-lookup"><span data-stu-id="6bbed-165">[Compliance policies](/intune/device-compliance-get-started) are rules and settings that devices must meet to be compliant in your corporate infrastructure.</span></span> <span data-ttu-id="6bbed-166">使用這些原則搭配條件式存取，以封鎖不符合規範的裝置存取公司資源。</span><span class="sxs-lookup"><span data-stu-id="6bbed-166">Use these policies with Conditional Access to block access to company resources for devices that are non-compliant.</span></span> <span data-ttu-id="6bbed-167">例如，您可以建立要求啟用 Bitlocker 的原則。</span><span class="sxs-lookup"><span data-stu-id="6bbed-167">For example, you can create a policy that requires Bitlocker be enabled.</span></span>

1. <span data-ttu-id="6bbed-168">[建立合規性政策](/intune/protect/compliance-policy-create-windows)。</span><span class="sxs-lookup"><span data-stu-id="6bbed-168">[Create Compliance Policy](/intune/protect/compliance-policy-create-windows).</span></span>

1. <span data-ttu-id="6bbed-169">條件式存取可讓/拒絕行動裝置和行動應用程式存取公司資源。</span><span class="sxs-lookup"><span data-stu-id="6bbed-169">Conditional Access allows/denies mobile devices and mobile applications from accessing company resources.</span></span> <span data-ttu-id="6bbed-170">您可能會覺得兩份檔很有説明，可 [規劃您的 CA 部署](/azure/active-directory/conditional-access/plan-conditional-access) 和 [最佳作法](/azure/active-directory/conditional-access/best-practices)。</span><span class="sxs-lookup"><span data-stu-id="6bbed-170">Two documents you may find helpful are [Plan your CA Deployment](/azure/active-directory/conditional-access/plan-conditional-access) and [Best Practices](/azure/active-directory/conditional-access/best-practices).</span></span>

1. <span data-ttu-id="6bbed-171">[本文討論 HoloLens](/intune/fundamentals/windows-holographic-for-business)的 Intune 管理工具。</span><span class="sxs-lookup"><span data-stu-id="6bbed-171">[This article](/intune/fundamentals/windows-holographic-for-business) talks about Intune's management tools for HoloLens.</span></span>

1. [<span data-ttu-id="6bbed-172">建立裝置設定檔</span><span class="sxs-lookup"><span data-stu-id="6bbed-172">Create a device profile</span></span>](/intune/configuration/device-profile-create)

### <a name="manage-updates"></a><span data-ttu-id="6bbed-173">管理更新</span><span class="sxs-lookup"><span data-stu-id="6bbed-173">Manage updates</span></span>

<span data-ttu-id="6bbed-174">Intune 包含一項稱為「更新通道」 Windows 10 裝置的功能，包括 HoloLens 2 和 HoloLens v1 (與「全像商用」) 。</span><span class="sxs-lookup"><span data-stu-id="6bbed-174">Intune includes a feature called Update rings for Windows 10 devices, including HoloLens 2 and HoloLens v1 (with Holographic for Business).</span></span> <span data-ttu-id="6bbed-175">更新通道包含一組設定，這些設定會決定安裝更新的方式和時間。</span><span class="sxs-lookup"><span data-stu-id="6bbed-175">Update rings include a group of settings that determine how and when updates are installed.</span></span>

<span data-ttu-id="6bbed-176">例如，您可以建立一個維護期間來安裝更新，或選擇在安裝更新後重新啟動。</span><span class="sxs-lookup"><span data-stu-id="6bbed-176">For example, you can create a maintenance window to install updates, or choose to restart after updates are installed.</span></span>  <span data-ttu-id="6bbed-177">您也可以選擇無限期地暫停更新，直到您準備好更新為止。</span><span class="sxs-lookup"><span data-stu-id="6bbed-177">You can also choose to pause updates indefinitely until you're ready to update.</span></span>

<span data-ttu-id="6bbed-178">深入瞭解如何 [使用 Intune 設定更新](/intune/windows-update-for-business-configure)通道。</span><span class="sxs-lookup"><span data-stu-id="6bbed-178">Read more about [configuring update rings with Intune](/intune/windows-update-for-business-configure).</span></span>

### <a name="application-management"></a><span data-ttu-id="6bbed-179">應用程式管理</span><span class="sxs-lookup"><span data-stu-id="6bbed-179">Application management</span></span>

<span data-ttu-id="6bbed-180">透過下列內容管理 HoloLens 的應用程式：</span><span class="sxs-lookup"><span data-stu-id="6bbed-180">Manage HoloLens applications through:</span></span>

1. <span data-ttu-id="6bbed-181">Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="6bbed-181">Microsoft Store</span></span>  
  <span data-ttu-id="6bbed-182">Microsoft Store 是在 HoloLens 上散發和使用應用程式的最佳方式。</span><span class="sxs-lookup"><span data-stu-id="6bbed-182">The Microsoft Store is the best way to distribute and consume applications on HoloLens.</span></span>  <span data-ttu-id="6bbed-183">存放區中已有一組絕佳的核心 HoloLens 應用程式可供使用，您也可以[發行自己](/windows/uwp/publish/)的應用程式。</span><span class="sxs-lookup"><span data-stu-id="6bbed-183">There is a great set of core HoloLens applications already available in the store or you can [publish your own](/windows/uwp/publish/).</span></span>  
  <span data-ttu-id="6bbed-184">存放區中的所有應用程式都可供所有人公開使用，但如果無法接受，請簽出商務用 Microsoft Store。</span><span class="sxs-lookup"><span data-stu-id="6bbed-184">All applications in the store are available publicly to everyone, but if it isn't acceptable, checkout the Microsoft Store for Business.</span></span>  

1. [<span data-ttu-id="6bbed-185">商務用 Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="6bbed-185">Microsoft Store for Business</span></span>](/microsoft-store/)  
  <span data-ttu-id="6bbed-186">商務用 Microsoft Store 和教育版是您公司環境的自訂存放區。</span><span class="sxs-lookup"><span data-stu-id="6bbed-186">Microsoft Store for Business and Education is a custom store for your corporate environment.</span></span>  <span data-ttu-id="6bbed-187">它可讓您使用 Windows 10 和 HoloLens 內建的 Microsoft Store 來尋找、取得、散發及管理您組織的應用程式。</span><span class="sxs-lookup"><span data-stu-id="6bbed-187">It lets you use the Microsoft Store built into Windows 10 and HoloLens to find, acquire, distribute, and manage apps for your organization.</span></span>  <span data-ttu-id="6bbed-188">它也可讓您部署商業環境專屬的應用程式，但不能部署到世界各地的應用程式。</span><span class="sxs-lookup"><span data-stu-id="6bbed-188">It also lets you deploy apps that are specific to your commercial environment but not to the world.</span></span>

1. <span data-ttu-id="6bbed-189">透過 Intune 或其他行動裝置管理解決方案的應用程式部署和管理</span><span class="sxs-lookup"><span data-stu-id="6bbed-189">Application deployment and management via Intune or another mobile device management solution</span></span>  
  <span data-ttu-id="6bbed-190">大部分的行動裝置管理解決方案（包括 Intune）提供一種方式，可將企業營運應用程式直接部署到一組已註冊的裝置。</span><span class="sxs-lookup"><span data-stu-id="6bbed-190">Most mobile device management solutions, including Intune, provide a way to deploy line of business applications directly to a set of enrolled devices.</span></span>  <span data-ttu-id="6bbed-191">請參閱這篇文章以瞭解 [Intune 應用程式安裝](/intune/apps-deploy)。</span><span class="sxs-lookup"><span data-stu-id="6bbed-191">See this article for [Intune app install](/intune/apps-deploy).</span></span>

1. <span data-ttu-id="6bbed-192">_不建議_ 裝置入口網站</span><span class="sxs-lookup"><span data-stu-id="6bbed-192">_not recommended_ Device Portal</span></span>  
  <span data-ttu-id="6bbed-193">您也可以使用 Windows 裝置入口網站直接將應用程式安裝在 HoloLens 上。</span><span class="sxs-lookup"><span data-stu-id="6bbed-193">Applications can also be installed on HoloLens directly using the Windows Device Portal.</span></span>  <span data-ttu-id="6bbed-194">這不是建議的作法，因為必須啟用開發人員模式才能使用裝置入口網站。</span><span class="sxs-lookup"><span data-stu-id="6bbed-194">This isn't recommended since Developer Mode has to be enabled to use the device portal.</span></span>

<span data-ttu-id="6bbed-195">深入瞭解如何[在 HoloLens 上安裝應用程式](hololens-install-apps.md)。</span><span class="sxs-lookup"><span data-stu-id="6bbed-195">Read more about [installing apps on HoloLens](hololens-install-apps.md).</span></span>

### <a name="certificates"></a><span data-ttu-id="6bbed-196">憑證</span><span class="sxs-lookup"><span data-stu-id="6bbed-196">Certificates</span></span>

<span data-ttu-id="6bbed-197">您可以透過 MDM 提供者發佈憑證。</span><span class="sxs-lookup"><span data-stu-id="6bbed-197">You can distribute certificates through your MDM provider.</span></span> <span data-ttu-id="6bbed-198">如果您的公司需要憑證，Intune 支援 PKCS、PFX 和 SCEP。</span><span class="sxs-lookup"><span data-stu-id="6bbed-198">If your company requires certificates, Intune supports PKCS, PFX, and SCEP.</span></span> <span data-ttu-id="6bbed-199">瞭解哪一種憑證適合您的公司是很重要的。</span><span class="sxs-lookup"><span data-stu-id="6bbed-199">It is important to understand which certificate is right for your company.</span></span> <span data-ttu-id="6bbed-200">請造訪憑證設定檔，以判斷哪一個 [憑證](/intune/protect/certificates-configure) 最適合您。</span><span class="sxs-lookup"><span data-stu-id="6bbed-200">Please visit the [certificate configurations](/intune/protect/certificates-configure) documentation to determine which cert is best for you.</span></span> <span data-ttu-id="6bbed-201">如果您打算使用憑證進行 HoloLens Authentication，PFX 或 SCEP 可能會很適合您。</span><span class="sxs-lookup"><span data-stu-id="6bbed-201">If you plan to use certificates for HoloLens Authentication, PFX or SCEP may be right for you.</span></span>

<span data-ttu-id="6bbed-202">請參閱下列步驟，以瞭解如何使用 [SCEP](/intune/protect/certificates-profile-scep)。</span><span class="sxs-lookup"><span data-stu-id="6bbed-202">See the following steps for using [SCEP](/intune/protect/certificates-profile-scep).</span></span>

### <a name="how-to-upgrade-to-holographics-for-business-commercial-suite"></a><span data-ttu-id="6bbed-203">如何升級至全像 for Business 商用套件</span><span class="sxs-lookup"><span data-stu-id="6bbed-203">How to Upgrade to Holographics for Business Commercial Suite</span></span>

> [!NOTE]
> <span data-ttu-id="6bbed-204">Windows全像 for Business (商用套件) 僅適用于 HoloLens 1 代裝置。</span><span class="sxs-lookup"><span data-stu-id="6bbed-204">Windows Holographics for Business (commercial suite) is only intended for HoloLens 1st gen devices.</span></span> <span data-ttu-id="6bbed-205">設定檔將不會套用至 HoloLens 2 裝置。</span><span class="sxs-lookup"><span data-stu-id="6bbed-205">The profile will not be applied to HoloLens 2 devices.</span></span>

<span data-ttu-id="6bbed-206">您可以在全像全像 [升級](/intune/configuration/holographic-upgrade) 的檔中找到升級至商用套件的指示。</span><span class="sxs-lookup"><span data-stu-id="6bbed-206">You can find directions for upgrading to the commercial suite in the [holographic upgrade](/intune/configuration/holographic-upgrade) documentation.</span></span>

### <a name="how-to-configure-kiosk-mode-using-microsoft-intune"></a><span data-ttu-id="6bbed-207">如何使用 Microsoft Intune 設定 Kiosk 模式</span><span class="sxs-lookup"><span data-stu-id="6bbed-207">How to Configure Kiosk Mode Using Microsoft Intune</span></span>

1. <span data-ttu-id="6bbed-208">將 Microsoft Store 同步至 Intune (參閱) 的下列[指示](/intune/apps/windows-store-for-business)。</span><span class="sxs-lookup"><span data-stu-id="6bbed-208">Sync Microsoft Store to Intune (See the following [instructions](/intune/apps/windows-store-for-business)).</span></span>

1. <span data-ttu-id="6bbed-209">檢查您的應用程式設定</span><span class="sxs-lookup"><span data-stu-id="6bbed-209">Check your app settings</span></span>
    1. <span data-ttu-id="6bbed-210">登入您的 Microsoft Store 商務帳戶</span><span class="sxs-lookup"><span data-stu-id="6bbed-210">Log into your Microsoft Store Business account</span></span>
    1. <span data-ttu-id="6bbed-211">**管理 > 應用程式和軟體的 > 產品和服務 > 選取您要同步的應用程式 > 私用存放區可用性 > 選取 [Everyone] 或 [特定群組]**</span><span class="sxs-lookup"><span data-stu-id="6bbed-211">**Manage > Products and Services > Apps and Software > Select the app you want to sync > Private Store Availability > Select "Everyone" or "Specific Groups"**</span></span>
        >[!NOTE]
        ><span data-ttu-id="6bbed-212">如果您沒有看到想要的應用程式，您必須藉由搜尋應用程式的商店來「取得」應用程式。</span><span class="sxs-lookup"><span data-stu-id="6bbed-212">If you don't see the app you want, you will have to "get" the app by searching the store for your app.</span></span> <span data-ttu-id="6bbed-213">**按一下右上角的 [搜尋] 列，> 輸入應用程式的名稱 > 按一下應用程式，> 選取 [Get]**。</span><span class="sxs-lookup"><span data-stu-id="6bbed-213">**Click the "Search" bar in the upper right-hand corner > type in the name of the app > click on the app > select "Get"**.</span></span>
    1. <span data-ttu-id="6bbed-214">如果您在 **Intune > 用戶端應用程式 > 應用** 程式中看不到您的應用程式，您可能必須重新 [同步應用程式](/intune/apps/windows-store-for-business#synchronize-apps) 。</span><span class="sxs-lookup"><span data-stu-id="6bbed-214">If you do not see your apps in **Intune > Client Apps > Apps** , you may have to [sync your apps](/intune/apps/windows-store-for-business#synchronize-apps) again.</span></span>

1. [<span data-ttu-id="6bbed-215">建立 Kiosk 模式的裝置設定檔</span><span class="sxs-lookup"><span data-stu-id="6bbed-215">Create a device profile for Kiosk mode</span></span>](/intune/configuration/kiosk-settings#create-the-profile)

> [!NOTE]
> <span data-ttu-id="6bbed-216">您可以使用 "Azure AD" 作為「使用者登入類型」，將不同的使用者設定為具有不同的 Kiosk 模式體驗。</span><span class="sxs-lookup"><span data-stu-id="6bbed-216">You can configure different users to have different Kiosk Mode experiences by using "Azure AD" as the "User logon type".</span></span> <span data-ttu-id="6bbed-217">不過，此選項僅適用于多應用程式 kiosk 模式。</span><span class="sxs-lookup"><span data-stu-id="6bbed-217">However, this option is only available in Multi-App kiosk mode.</span></span> <span data-ttu-id="6bbed-218">多應用程式 kiosk 模式只適用于一個應用程式和多個應用程式。</span><span class="sxs-lookup"><span data-stu-id="6bbed-218">Multi-App kiosk mode will work with only one app as well as multiple apps.</span></span>

![顯示 Intune 中 Kiosk 模式設定的影像](images/aad-kioskmode.png)

<span data-ttu-id="6bbed-220">如需其他 MDM 服務，請參閱提供者的檔以取得指示。</span><span class="sxs-lookup"><span data-stu-id="6bbed-220">For other MDM services, check your provider's documentation for instructions.</span></span> <span data-ttu-id="6bbed-221">如果您需要使用自訂設定和完整 XML 設定來設定 MDM 服務中的 kiosk，請參閱[HoloLens kiosk](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)指示。</span><span class="sxs-lookup"><span data-stu-id="6bbed-221">Refer to the [HoloLens kiosk](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) instructions if you need to use a custom setting and full XML configuration to set up a kiosk in your MDM service.</span></span>

## <a name="certificates-and-authentication"></a><span data-ttu-id="6bbed-222">憑證和驗證</span><span class="sxs-lookup"><span data-stu-id="6bbed-222">Certificates and Authentication</span></span>

<span data-ttu-id="6bbed-223">您可以透過 MDM 部署憑證 (請參閱 [Mdm 區段](hololens-commercial-infrastructure.md#mobile-device-manager-guidance) 中的「憑證」) 。</span><span class="sxs-lookup"><span data-stu-id="6bbed-223">Certificates can be deployed via you MDM (see "certificates" in the [MDM Section](hololens-commercial-infrastructure.md#mobile-device-manager-guidance)).</span></span> <span data-ttu-id="6bbed-224">您也可以透過套件布建，將憑證部署至 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="6bbed-224">Certificates can also be deployed to the HoloLens through package provisioning.</span></span> <span data-ttu-id="6bbed-225">如需其他資訊，請參閱[HoloLens](hololens-provisioning.md)布建。</span><span class="sxs-lookup"><span data-stu-id="6bbed-225">Please see [HoloLens Provisioning](hololens-provisioning.md) for additional information.</span></span>

### <a name="additional-intune-quick-links"></a><span data-ttu-id="6bbed-226">其他 Intune 快速連結</span><span class="sxs-lookup"><span data-stu-id="6bbed-226">Additional Intune Quick Links</span></span>

1. <span data-ttu-id="6bbed-227">[建立設定檔：](/intune/configuration/device-profile-create) 設定檔可讓您新增及設定將推送至組織中裝置的設定。</span><span class="sxs-lookup"><span data-stu-id="6bbed-227">[Create Profiles:](/intune/configuration/device-profile-create) Profiles allow you to add and configure settings that will be pushed to the devices in your organization.</span></span>

