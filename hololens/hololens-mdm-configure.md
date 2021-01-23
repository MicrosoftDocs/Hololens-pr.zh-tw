---
title: 使用 Microsoft 的端點管理員 Intune 管理 HoloLens 裝置
description: 瞭解如何使用 Intune 來設定 CSP、原則，以及管理 HoloLens 混合式現實裝置。
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/9/2020
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ce288afdcb112c17ffde75078d641f3637a8448c
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283954"
---
# <span data-ttu-id="a8f3a-103">使用 Microsoft 的端點管理員 Intune 管理 HoloLens 裝置</span><span class="sxs-lookup"><span data-stu-id="a8f3a-103">Using Microsoft’s Endpoint Manager Intune to manage HoloLens devices</span></span>

<span data-ttu-id="a8f3a-104">您可以透過 MDM 管理多種不同的設定。</span><span class="sxs-lookup"><span data-stu-id="a8f3a-104">There are numerous different settings you can manage via MDM.</span></span> <span data-ttu-id="a8f3a-105">您可以將 Intune 裝置組成群組，並將配置部署到這些使用者或裝置群組。</span><span class="sxs-lookup"><span data-stu-id="a8f3a-105">Using Intune devices can be grouped together and configurations can be deployed to those groups of users or devices.</span></span> <span data-ttu-id="a8f3a-106">您也可以部署和管理 app、設定裝置以連線至您的網路，以及將更新設定為在所需的時間，以及在需要更新環路時進行。</span><span class="sxs-lookup"><span data-stu-id="a8f3a-106">Apps can also be deployed and managed, setting up devices to connect to your network, as well as configuring updates to occur at the time desired and on the update ring needed.</span></span> 

## <span data-ttu-id="a8f3a-107">如何透過 Intune 管理</span><span class="sxs-lookup"><span data-stu-id="a8f3a-107">How to manage via Intune</span></span>

### <span data-ttu-id="a8f3a-108">裝置類別和群組</span><span class="sxs-lookup"><span data-stu-id="a8f3a-108">Device categories and groups</span></span>
<span data-ttu-id="a8f3a-109">使用 Intune，您可以建立裝置類別，根據您建立的類別（例如工程、醫學、開發人員等），自動將裝置新增到群組中。</span><span class="sxs-lookup"><span data-stu-id="a8f3a-109">Using Intune, you can create device categories to automatically add devices to groups based on categories that you create, such as Engineering, Medical, Developers, and so on.</span></span> <span data-ttu-id="a8f3a-110">其目的是讓您更容易管理執行 Windows 全息版的裝置。</span><span class="sxs-lookup"><span data-stu-id="a8f3a-110">The idea is to make it easier to manage your devices running Windows Holographic for Business.</span></span>
<span data-ttu-id="a8f3a-111">延伸閱讀：將 [裝置分類成群組](https://docs.microsoft.com/mem/intune/enrollment/device-group-mapping)</span><span class="sxs-lookup"><span data-stu-id="a8f3a-111">Read more: [Categorize devices into groups](https://docs.microsoft.com/mem/intune/enrollment/device-group-mapping)</span></span>

### <span data-ttu-id="a8f3a-112">裝置設定設定檔</span><span class="sxs-lookup"><span data-stu-id="a8f3a-112">Device configuration profiles</span></span>
<span data-ttu-id="a8f3a-113">Intune 包含您可以在組織內的不同裝置上啟用或停用的設定和功能。</span><span class="sxs-lookup"><span data-stu-id="a8f3a-113">Intune includes settings and features that you can enable or disable on different devices within your organization.</span></span> <span data-ttu-id="a8f3a-114">這些設定和功能是使用設定檔來管理。</span><span class="sxs-lookup"><span data-stu-id="a8f3a-114">These settings and features are managed using profiles.</span></span> <span data-ttu-id="a8f3a-115">例如，您可以建立可在執行 Windows 全息版的裝置上啟用 Cortana 或使用 Microsoft Defender Smart 螢幕的設定檔。</span><span class="sxs-lookup"><span data-stu-id="a8f3a-115">For example, you can create a profile that enables Cortana, or uses Microsoft Defender Smart Screen on your devices running Windows Holographic for Business.</span></span>
<span data-ttu-id="a8f3a-116">在您的設定檔中，您可以使用 OMA-URI 來自訂部分設定、建立裝置限制，以及設定虛擬私人網路 (VPN) 和 Wi-fi。</span><span class="sxs-lookup"><span data-stu-id="a8f3a-116">In your profiles, you can use OMA-URI to customize some settings, create device restrictions, and configure a virtual private network (VPN) and Wi-Fi.</span></span>
<span data-ttu-id="a8f3a-117">[開始使用設定檔](https://docs.microsoft.com/mem/intune/configuration/device-profiles)和 [設定檔概覽](https://docs.microsoft.com/mem/intune/configuration/device-profile-create)。</span><span class="sxs-lookup"><span data-stu-id="a8f3a-117">[Get started with configuration profiles](https://docs.microsoft.com/mem/intune/configuration/device-profiles), and [profile overview](https://docs.microsoft.com/mem/intune/configuration/device-profile-create).</span></span>

## <span data-ttu-id="a8f3a-118">可管理和設定的範例</span><span class="sxs-lookup"><span data-stu-id="a8f3a-118">Examples of what can be managed and configured</span></span>

<span data-ttu-id="a8f3a-119">使用 MDM 管理裝置可提供大量的專案供您選取。</span><span class="sxs-lookup"><span data-stu-id="a8f3a-119">Using MDM to manage devices gives a wide array of items that can be selected.</span></span> 

### <span data-ttu-id="a8f3a-120">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="a8f3a-120">Wi-Fi</span></span>
<span data-ttu-id="a8f3a-121">[Wi-fi 設定](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-configure) 會將無線網路設定指派給使用者和裝置。</span><span class="sxs-lookup"><span data-stu-id="a8f3a-121">[Wi-Fi settings](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-configure) assigns wireless network settings to users and devices.</span></span> <span data-ttu-id="a8f3a-122">當您指派 Wi-Fi 設定檔時，使用者將無法存取您的公司 Wi-Fi，而無需自行設定。</span><span class="sxs-lookup"><span data-stu-id="a8f3a-122">When you assign a Wi-Fi profile, users get access to your corporate Wi-Fi without having to configure it themselves.</span></span>
<span data-ttu-id="a8f3a-123">進一步瞭解如何 [針對 HoloLens 設定您的網路](hololens-commercial-infrastructure.md)</span><span class="sxs-lookup"><span data-stu-id="a8f3a-123">Learn more about [configuring your network for HoloLens](hololens-commercial-infrastructure.md)</span></span>

### <span data-ttu-id="a8f3a-124">憑證</span><span class="sxs-lookup"><span data-stu-id="a8f3a-124">Certificates</span></span>
<span data-ttu-id="a8f3a-125">證書可提供帳戶驗證、Wi-Fi 驗證、VPN 加密及網頁內容 SSL 加密，以協助提高安全性。</span><span class="sxs-lookup"><span data-stu-id="a8f3a-125">Certificates help improve security by providing account authentication, Wi-Fi authentication, VPN encryption, and SSL encryption of web content.</span></span> <span data-ttu-id="a8f3a-126">雖然系統管理員可以透過預配套件手動管理裝置上的憑證，但最佳做法是使用您的 MDM system 在整個週期中管理這些憑證，從註冊到更新和吊銷等。</span><span class="sxs-lookup"><span data-stu-id="a8f3a-126">Although administrators can manage certificates on devices manually through provisioning packages, it’s a best practice to use your MDM system to manage those certificates throughout their entire lifecycle – from enrollment through renewal and revocation.</span></span> <span data-ttu-id="a8f3a-127">您可以註冊 (裝置之後，您的 MDM 系統就能自動將這些憑證部署到裝置的憑證存放區，只要 MDM system 支援簡單憑證註冊通訊協定 (SCEP) 或公開金鑰加密標準 #12 (# A5 的) PKCS # 12。</span><span class="sxs-lookup"><span data-stu-id="a8f3a-127">Your MDM system can automatically deploy these certificates to the devices’ certificate stores after you enroll the device (as long as the MDM system supports the Simple Certificate Enrollment Protocol (SCEP) or Public Key Cryptography Standards #12 (PKCS#12)).</span></span> <span data-ttu-id="a8f3a-128">MDM 也可以在目前的憑證過期前，查詢及刪除已註冊的用戶端憑證，或觸發新的註冊要求。</span><span class="sxs-lookup"><span data-stu-id="a8f3a-128">MDM can also query and delete enrolled client certificates or trigger a new enrollment request before the current certificate is expired.</span></span> 

### <span data-ttu-id="a8f3a-129">Proxy</span><span class="sxs-lookup"><span data-stu-id="a8f3a-129">Proxy</span></span>
<span data-ttu-id="a8f3a-130">大多數公司內部網路都利用 proxy 來管理內部流量。</span><span class="sxs-lookup"><span data-stu-id="a8f3a-130">Most corporate intranet networks leverage a proxy to manage internal traffic.</span></span> <span data-ttu-id="a8f3a-131">使用 HoloLens 2，您可以設定乙太網路的 proxy 伺服器與 Wi-Fi 連線。</span><span class="sxs-lookup"><span data-stu-id="a8f3a-131">With HoloLens 2 you can configure a proxy server for ethernet and Wi-Fi connections.</span></span> <span data-ttu-id="a8f3a-132">這些設定不會套用至 VPN 連線。</span><span class="sxs-lookup"><span data-stu-id="a8f3a-132">These settings do not apply to VPN connections.</span></span> <span data-ttu-id="a8f3a-133">如需 Windows 10 proxy 設定的詳細資訊，請參閱 [NETWORKPROXY CSP](https://docs.microsoft.com/windows/client-management/mdm/networkproxy-csp)。</span><span class="sxs-lookup"><span data-stu-id="a8f3a-133">For more details on proxy settings for Windows 10, see [NetworkProxy CSP](https://docs.microsoft.com/windows/client-management/mdm/networkproxy-csp).</span></span>

### <span data-ttu-id="a8f3a-134">VPN</span><span class="sxs-lookup"><span data-stu-id="a8f3a-134">VPN</span></span>
<span data-ttu-id="a8f3a-135">組織通常會使用 VPN，來控制對其公司內部網路上 app 與資源的存取權。</span><span class="sxs-lookup"><span data-stu-id="a8f3a-135">Organizations often use a VPN to control access to apps and resources on their company’s intranet.</span></span> <span data-ttu-id="a8f3a-136">HoloLens 2 支援 SSL VPN 連線，這需要來自 Microsoft Store 的可下載外掛程式，而且是您選擇的 VPN 廠商專用的。</span><span class="sxs-lookup"><span data-stu-id="a8f3a-136">HoloLens 2 supports SSL VPN connections, which require a downloadable plugin from the Microsoft Store and are specific to the VPN vendor of your choice.</span></span> 
- <span data-ttu-id="a8f3a-137">閱讀更多有關 [HoloLens 上 VPN 的](hololens-network.md#vpn)資訊。</span><span class="sxs-lookup"><span data-stu-id="a8f3a-137">Read more about [VPN on HoloLens](hololens-network.md#vpn).</span></span>
- <span data-ttu-id="a8f3a-138">如需有關 VPN 設定檔的詳細資訊，請參閱 [VPNV2 CSP](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp)。</span><span class="sxs-lookup"><span data-stu-id="a8f3a-138">For more details about VPN profiles, see the [VPNv2 CSP](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp).</span></span>

### <span data-ttu-id="a8f3a-139">部署及管理 app</span><span class="sxs-lookup"><span data-stu-id="a8f3a-139">Deploy and manage apps</span></span>
<span data-ttu-id="a8f3a-140">使用 Intune，您可以在執行 Windows 全息版的裝置上新增應用程式。</span><span class="sxs-lookup"><span data-stu-id="a8f3a-140">Using Intune, you can add apps to your devices running Windows Holographic for Business.</span></span> <span data-ttu-id="a8f3a-141">MDM 方案可讓 IT 決策者和系統管理員自行自動安裝 (推) 其內部、行業內應用程式，或透過使用者群組的商店購買 app。</span><span class="sxs-lookup"><span data-stu-id="a8f3a-141">An MDM solution enables IT decision-makers and administrators to privately auto-install (push) their in-house, line-of-business apps, or purchase apps through the store for a group of users.</span></span> <span data-ttu-id="a8f3a-142">部署應用程式的方法有很多種，包括：</span><span class="sxs-lookup"><span data-stu-id="a8f3a-142">There are many ways to deploy apps, including:</span></span>
-   [<span data-ttu-id="a8f3a-143">Intune 和公司入口網站</span><span class="sxs-lookup"><span data-stu-id="a8f3a-143">Intune and Company Portal</span></span>]( app-deploy-intune.md)
-   [<span data-ttu-id="a8f3a-144">商務用 Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="a8f3a-144">Microsoft Store for Business</span></span>]( app-deploy-store-business.md)

<span data-ttu-id="a8f3a-145">深入瞭解透過 Intune 進行的 app 管理。</span><span class="sxs-lookup"><span data-stu-id="a8f3a-145">Learn more about app management through Intune.</span></span>
-   [<span data-ttu-id="a8f3a-146">將應用程式新增至 Intune</span><span class="sxs-lookup"><span data-stu-id="a8f3a-146">Add apps to Intune</span></span>](https://docs.microsoft.com/mem/intune/apps/apps-add)
-   [<span data-ttu-id="a8f3a-147">新增 Microsoft Store 應用程式</span><span class="sxs-lookup"><span data-stu-id="a8f3a-147">Add Microsoft Store apps</span></span>](https://docs.microsoft.com/mem/intune/apps/store-apps-windows)
-   [<span data-ttu-id="a8f3a-148">新增您建立的應用程式</span><span class="sxs-lookup"><span data-stu-id="a8f3a-148">Add apps you create</span></span>](https://docs.microsoft.com/mem/intune/apps/lob-apps-windows)
- [<span data-ttu-id="a8f3a-149">將應用程式指派給群組</span><span class="sxs-lookup"><span data-stu-id="a8f3a-149">Assign apps to groups</span></span>](https://docs.microsoft.com/mem/intune/apps/apps-deploy)

### <span data-ttu-id="a8f3a-150">軟體更新</span><span class="sxs-lookup"><span data-stu-id="a8f3a-150">Software updates</span></span>
<span data-ttu-id="a8f3a-151">Intune 包括 Windows 10 裝置的「更新響鈴」功能。</span><span class="sxs-lookup"><span data-stu-id="a8f3a-151">Intune includes a feature called update rings for Windows 10 devices.</span></span> <span data-ttu-id="a8f3a-152">這些更新鈴響包括一組決定如何安裝更新的設定。</span><span class="sxs-lookup"><span data-stu-id="a8f3a-152">These update rings include a group of settings that determine how updates are installed.</span></span> <span data-ttu-id="a8f3a-153">例如，您可以建立要安裝更新的維護時段，或選擇在安裝更新後重新開機。</span><span class="sxs-lookup"><span data-stu-id="a8f3a-153">For example, you can create a maintenance window to install updates, or choose to restart after updates are installed.</span></span> <span data-ttu-id="a8f3a-154">更新環可以套用到執行 Windows 全息企業版的多個裝置。</span><span class="sxs-lookup"><span data-stu-id="a8f3a-154">An update ring can be applied to multiple devices running Windows Holographic for Business.</span></span>
<span data-ttu-id="a8f3a-155">進一步瞭解如何 [管理 HoloLens 更新](hololens-updates.md) 及透過 [Intune 管理軟體更新](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)。</span><span class="sxs-lookup"><span data-stu-id="a8f3a-155">Read more about how to [Manage HoloLens updates](hololens-updates.md) and [Manage software updates via Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span></span>

### <span data-ttu-id="a8f3a-156">設定 Kiosk 模式</span><span class="sxs-lookup"><span data-stu-id="a8f3a-156">Configure kiosk mode</span></span>
<span data-ttu-id="a8f3a-157">使用 Intune 中提供的共用或來賓電腦功能，您可以將 Windows 全息版裝置設定為以展臺方式執行。</span><span class="sxs-lookup"><span data-stu-id="a8f3a-157">Using the shared or guest PC features available in Intune, you can configure Windows Holographic for Business devices to run as a kiosk.</span></span> <span data-ttu-id="a8f3a-158">這些裝置可以 (單一 app kiosk 模式) 執行一個 app，或執行多個 app (多重 app kiosk 模式) 。</span><span class="sxs-lookup"><span data-stu-id="a8f3a-158">These devices can run one app (single-app kiosk mode), or run multiple apps (multi-app kiosk mode).</span></span> <span data-ttu-id="a8f3a-159">Kiosk 模式是一個 UI，可控制哪些身分預設可以存取哪些 app。</span><span class="sxs-lookup"><span data-stu-id="a8f3a-159">Kiosk mode is a UI to control which identities have access to which apps by default.</span></span>
<span data-ttu-id="a8f3a-160">瞭解如何 [將 HoloLens 設定為 kiosk]( hololens-kiosk.md)</span><span class="sxs-lookup"><span data-stu-id="a8f3a-160">Learn how to [set up HoloLens as a kiosk]( hololens-kiosk.md)</span></span>

